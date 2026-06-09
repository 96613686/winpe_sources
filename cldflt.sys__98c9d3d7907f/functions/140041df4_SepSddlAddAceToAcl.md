# SepSddlAddAceToAcl

- ea: `0x140041df4`
- end: `0x140041edf`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140041fcc`

## callees

- `0x14001e280`
- `0x14001e580`
- `0x140041df4`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140041e18`
- `ntoskrnl!RtlLengthSid` at `0x140041e18`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140041ec1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140041ec1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041e52`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041e52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e92`

## pseudocode

```c
NTSTATUS __fastcall SepSddlAddAceToAcl(
        const void **a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK AccessMask,
        int a6,
        PSID Sid)
{
  unsigned __int16 *v7; // rdi
  size_t v10; // rsi
  ULONG v11; // r8d
  int v12; // ebp
  unsigned int v13; // r12d
  struct _ACL *PoolWithTag; // rax
  struct _ACL *v15; // rbx

  v7 = (unsigned __int16 *)*a1;
  v10 = (unsigned int)*a2;
  v11 = RtlLengthSid(Sid) + 8;
  v12 = v11 + v10;
  if ( v11 + (unsigned int)v10 <= v7[1] )
  {
    v15 = (struct _ACL *)v7;
  }
  else
  {
    v13 = a6 * v11 + v10;
    PoolWithTag = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v13, 0x6C416553u);
    v15 = PoolWithTag;
    if ( !PoolWithTag )
      return -1073741670;
    memset(PoolWithTag, 0, v13);
    memmove(v15, *a1, v10);
    v15->AclSize = v13;
    ExFreePoolWithTag(v7, 0);
    *a1 = v15;
  }
  *a2 = v12;
  return RtlAddAccessAllowedAce(v15, 2u, AccessMask, Sid);
}

```

## disassembly

```asm
0x140041df4  push    rbx
0x140041df6  push    rbp
0x140041df7  push    rsi
0x140041df8  push    rdi
0x140041df9  push    r12
0x140041dfb  push    r13
0x140041dfd  push    r14
0x140041dff  push    r15
0x140041e01  sub     rsp, 28h
0x140041e05  mov     rdi, [rcx]
0x140041e08  mov     r15, rcx
0x140041e0b  mov     rcx, [rsp+68h+Sid]; Sid
0x140041e13  mov     r14, rdx
0x140041e16  mov     esi, [rdx]
0x140041e18  call    cs:__imp_RtlLengthSid
0x140041e1f  nop     dword ptr [rax+rax+00h]
0x140041e24  lea     r8d, [rax+8]
0x140041e28  movzx   eax, word ptr [rdi+2]
0x140041e2c  lea     ebp, [r8+rsi]
0x140041e30  cmp     ebp, eax
0x140041e32  jbe     short loc_140041EA3
0x140041e34  imul    r8d, [rsp+68h+arg_28]
0x140041e3d  mov     ecx, 1; PoolType
0x140041e42  lea     r12d, [r8+rsi]
0x140041e46  mov     r8d, 6C416553h; Tag
0x140041e4c  mov     edx, r12d; NumberOfBytes
0x140041e4f  mov     r13d, r12d
0x140041e52  call    cs:__imp_ExAllocatePoolWithTag
0x140041e59  nop     dword ptr [rax+rax+00h]
0x140041e5e  mov     rbx, rax
0x140041e61  test    rax, rax
0x140041e64  jnz     short loc_140041E6D
0x140041e66  mov     eax, 0C000009Ah
0x140041e6b  jmp     short loc_140041ECD
0x140041e6d  mov     r8, r13; Size
0x140041e70  xor     edx, edx; Val
0x140041e72  mov     rcx, rbx; void *
0x140041e75  call    memset
0x140041e7a  mov     rdx, [r15]; Src
0x140041e7d  mov     r8, rsi; Size
0x140041e80  mov     rcx, rbx; void *
0x140041e83  call    memmove
0x140041e88  xor     edx, edx; Tag
0x140041e8a  mov     [rbx+2], r12w
0x140041e8f  mov     rcx, rdi; P
0x140041e92  call    cs:__imp_ExFreePoolWithTag
0x140041e99  nop     dword ptr [rax+rax+00h]
0x140041e9e  mov     [r15], rbx
0x140041ea1  jmp     short loc_140041EA6
0x140041ea3  mov     rbx, rdi
0x140041ea6  mov     r9, [rsp+68h+Sid]; Sid
0x140041eae  mov     edx, 2; AceRevision
0x140041eb3  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140041ebb  mov     rcx, rbx; Acl
0x140041ebe  mov     [r14], ebp
0x140041ec1  call    cs:__imp_RtlAddAccessAllowedAce
0x140041ec8  nop     dword ptr [rax+rax+00h]
0x140041ecd  add     rsp, 28h
0x140041ed1  pop     r15
0x140041ed3  pop     r14
0x140041ed5  pop     r13
0x140041ed7  pop     r12
0x140041ed9  pop     rdi
0x140041eda  pop     rsi
0x140041edb  pop     rbp
0x140041edc  pop     rbx
0x140041edd  retn
```
