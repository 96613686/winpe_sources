# SepSddlAddAceToAcl

- ea: `0x140041ee4`
- end: `0x140041fcf`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400420bc`

## callees

- `0x14001e300`
- `0x14001e600`
- `0x140041ee4`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140041f08`
- `ntoskrnl!RtlLengthSid` at `0x140041f08`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140041fb1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140041fb1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041f42`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041f82`

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
0x140041ee4  push    rbx
0x140041ee6  push    rbp
0x140041ee7  push    rsi
0x140041ee8  push    rdi
0x140041ee9  push    r12
0x140041eeb  push    r13
0x140041eed  push    r14
0x140041eef  push    r15
0x140041ef1  sub     rsp, 28h
0x140041ef5  mov     rdi, [rcx]
0x140041ef8  mov     r15, rcx
0x140041efb  mov     rcx, [rsp+68h+Sid]; Sid
0x140041f03  mov     r14, rdx
0x140041f06  mov     esi, [rdx]
0x140041f08  call    cs:__imp_RtlLengthSid
0x140041f0f  nop     dword ptr [rax+rax+00h]
0x140041f14  lea     r8d, [rax+8]
0x140041f18  movzx   eax, word ptr [rdi+2]
0x140041f1c  lea     ebp, [r8+rsi]
0x140041f20  cmp     ebp, eax
0x140041f22  jbe     short loc_140041F93
0x140041f24  imul    r8d, [rsp+68h+arg_28]
0x140041f2d  mov     ecx, 1; PoolType
0x140041f32  lea     r12d, [r8+rsi]
0x140041f36  mov     r8d, 6C416553h; Tag
0x140041f3c  mov     edx, r12d; NumberOfBytes
0x140041f3f  mov     r13d, r12d
0x140041f42  call    cs:__imp_ExAllocatePoolWithTag
0x140041f49  nop     dword ptr [rax+rax+00h]
0x140041f4e  mov     rbx, rax
0x140041f51  test    rax, rax
0x140041f54  jnz     short loc_140041F5D
0x140041f56  mov     eax, 0C000009Ah
0x140041f5b  jmp     short loc_140041FBD
0x140041f5d  mov     r8, r13; Size
0x140041f60  xor     edx, edx; Val
0x140041f62  mov     rcx, rbx; void *
0x140041f65  call    memset
0x140041f6a  mov     rdx, [r15]; Src
0x140041f6d  mov     r8, rsi; Size
0x140041f70  mov     rcx, rbx; void *
0x140041f73  call    memmove
0x140041f78  xor     edx, edx; Tag
0x140041f7a  mov     [rbx+2], r12w
0x140041f7f  mov     rcx, rdi; P
0x140041f82  call    cs:__imp_ExFreePoolWithTag
0x140041f89  nop     dword ptr [rax+rax+00h]
0x140041f8e  mov     [r15], rbx
0x140041f91  jmp     short loc_140041F96
0x140041f93  mov     rbx, rdi
0x140041f96  mov     r9, [rsp+68h+Sid]; Sid
0x140041f9e  mov     edx, 2; AceRevision
0x140041fa3  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140041fab  mov     rcx, rbx; Acl
0x140041fae  mov     [r14], ebp
0x140041fb1  call    cs:__imp_RtlAddAccessAllowedAce
0x140041fb8  nop     dword ptr [rax+rax+00h]
0x140041fbd  add     rsp, 28h
0x140041fc1  pop     r15
0x140041fc3  pop     r14
0x140041fc5  pop     r13
0x140041fc7  pop     r12
0x140041fc9  pop     rdi
0x140041fca  pop     rsi
0x140041fcb  pop     rbp
0x140041fcc  pop     rbx
0x140041fcd  retn
```
