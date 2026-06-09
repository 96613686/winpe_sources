# SepSddlAddAceToAcl

- ea: `0x140045d4c`
- end: `0x140045e37`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140045f24`

## callees

- `0x14000bb80`
- `0x14000be80`
- `0x140045d4c`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140045d70`
- `ntoskrnl!RtlLengthSid` at `0x140045d70`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140045e19`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140045e19`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045daa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140045daa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045dea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045dea`

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
0x140045d4c  push    rbx
0x140045d4e  push    rbp
0x140045d4f  push    rsi
0x140045d50  push    rdi
0x140045d51  push    r12
0x140045d53  push    r13
0x140045d55  push    r14
0x140045d57  push    r15
0x140045d59  sub     rsp, 28h
0x140045d5d  mov     rdi, [rcx]
0x140045d60  mov     r15, rcx
0x140045d63  mov     rcx, [rsp+68h+Sid]; Sid
0x140045d6b  mov     r14, rdx
0x140045d6e  mov     esi, [rdx]
0x140045d70  call    cs:__imp_RtlLengthSid
0x140045d77  nop     dword ptr [rax+rax+00h]
0x140045d7c  lea     r8d, [rax+8]
0x140045d80  movzx   eax, word ptr [rdi+2]
0x140045d84  lea     ebp, [r8+rsi]
0x140045d88  cmp     ebp, eax
0x140045d8a  jbe     short loc_140045DFB
0x140045d8c  imul    r8d, [rsp+68h+arg_28]
0x140045d95  mov     ecx, 1; PoolType
0x140045d9a  lea     r12d, [r8+rsi]
0x140045d9e  mov     r8d, 6C416553h; Tag
0x140045da4  mov     edx, r12d; NumberOfBytes
0x140045da7  mov     r13d, r12d
0x140045daa  call    cs:__imp_ExAllocatePoolWithTag
0x140045db1  nop     dword ptr [rax+rax+00h]
0x140045db6  mov     rbx, rax
0x140045db9  test    rax, rax
0x140045dbc  jnz     short loc_140045DC5
0x140045dbe  mov     eax, 0C000009Ah
0x140045dc3  jmp     short loc_140045E25
0x140045dc5  mov     r8, r13; Size
0x140045dc8  xor     edx, edx; Val
0x140045dca  mov     rcx, rbx; void *
0x140045dcd  call    memset
0x140045dd2  mov     rdx, [r15]; Src
0x140045dd5  mov     r8, rsi; Size
0x140045dd8  mov     rcx, rbx; void *
0x140045ddb  call    memmove
0x140045de0  xor     edx, edx; Tag
0x140045de2  mov     [rbx+2], r12w
0x140045de7  mov     rcx, rdi; P
0x140045dea  call    cs:__imp_ExFreePoolWithTag
0x140045df1  nop     dword ptr [rax+rax+00h]
0x140045df6  mov     [r15], rbx
0x140045df9  jmp     short loc_140045DFE
0x140045dfb  mov     rbx, rdi
0x140045dfe  mov     r9, [rsp+68h+Sid]; Sid
0x140045e06  mov     edx, 2; AceRevision
0x140045e0b  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140045e13  mov     rcx, rbx; Acl
0x140045e16  mov     [r14], ebp
0x140045e19  call    cs:__imp_RtlAddAccessAllowedAce
0x140045e20  nop     dword ptr [rax+rax+00h]
0x140045e25  add     rsp, 28h
0x140045e29  pop     r15
0x140045e2b  pop     r14
0x140045e2d  pop     r13
0x140045e2f  pop     r12
0x140045e31  pop     rdi
0x140045e32  pop     rsi
0x140045e33  pop     rbp
0x140045e34  pop     rbx
0x140045e35  retn
```
