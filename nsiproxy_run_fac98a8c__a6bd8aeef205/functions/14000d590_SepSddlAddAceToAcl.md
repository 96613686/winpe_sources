# SepSddlAddAceToAcl

- ea: `0x14000d590`
- end: `0x14000d67b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000d768`

## callees

- `0x140006680`
- `0x140006980`
- `0x14000d590`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14000d5b4`
- `ntoskrnl!RtlLengthSid` at `0x14000d5b4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000d65d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000d65d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d62e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d62e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d5ee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d5ee`

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
0x14000d590  push    rbx
0x14000d592  push    rbp
0x14000d593  push    rsi
0x14000d594  push    rdi
0x14000d595  push    r12
0x14000d597  push    r13
0x14000d599  push    r14
0x14000d59b  push    r15
0x14000d59d  sub     rsp, 28h
0x14000d5a1  mov     rdi, [rcx]
0x14000d5a4  mov     r15, rcx
0x14000d5a7  mov     rcx, [rsp+68h+Sid]; Sid
0x14000d5af  mov     r14, rdx
0x14000d5b2  mov     esi, [rdx]
0x14000d5b4  call    cs:__imp_RtlLengthSid
0x14000d5bb  nop     dword ptr [rax+rax+00h]
0x14000d5c0  lea     r8d, [rax+8]
0x14000d5c4  movzx   eax, word ptr [rdi+2]
0x14000d5c8  lea     ebp, [r8+rsi]
0x14000d5cc  cmp     ebp, eax
0x14000d5ce  jbe     short loc_14000D63F
0x14000d5d0  imul    r8d, [rsp+68h+arg_28]
0x14000d5d9  mov     ecx, 1; PoolType
0x14000d5de  lea     r12d, [r8+rsi]
0x14000d5e2  mov     r8d, 6C416553h; Tag
0x14000d5e8  mov     edx, r12d; NumberOfBytes
0x14000d5eb  mov     r13d, r12d
0x14000d5ee  call    cs:__imp_ExAllocatePoolWithTag
0x14000d5f5  nop     dword ptr [rax+rax+00h]
0x14000d5fa  mov     rbx, rax
0x14000d5fd  test    rax, rax
0x14000d600  jnz     short loc_14000D609
0x14000d602  mov     eax, 0C000009Ah
0x14000d607  jmp     short loc_14000D669
0x14000d609  mov     r8, r13; Size
0x14000d60c  xor     edx, edx; Val
0x14000d60e  mov     rcx, rbx; void *
0x14000d611  call    memset
0x14000d616  mov     rdx, [r15]; Src
0x14000d619  mov     r8, rsi; Size
0x14000d61c  mov     rcx, rbx; void *
0x14000d61f  call    memmove
0x14000d624  xor     edx, edx; Tag
0x14000d626  mov     [rbx+2], r12w
0x14000d62b  mov     rcx, rdi; P
0x14000d62e  call    cs:__imp_ExFreePoolWithTag
0x14000d635  nop     dword ptr [rax+rax+00h]
0x14000d63a  mov     [r15], rbx
0x14000d63d  jmp     short loc_14000D642
0x14000d63f  mov     rbx, rdi
0x14000d642  mov     r9, [rsp+68h+Sid]; Sid
0x14000d64a  mov     edx, 2; AceRevision
0x14000d64f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14000d657  mov     rcx, rbx; Acl
0x14000d65a  mov     [r14], ebp
0x14000d65d  call    cs:__imp_RtlAddAccessAllowedAce
0x14000d664  nop     dword ptr [rax+rax+00h]
0x14000d669  add     rsp, 28h
0x14000d66d  pop     r15
0x14000d66f  pop     r14
0x14000d671  pop     r13
0x14000d673  pop     r12
0x14000d675  pop     rdi
0x14000d676  pop     rsi
0x14000d677  pop     rbp
0x14000d678  pop     rbx
0x14000d679  retn
```
