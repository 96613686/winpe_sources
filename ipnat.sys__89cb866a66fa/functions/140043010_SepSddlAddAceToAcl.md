# SepSddlAddAceToAcl

- ea: `0x140043010`
- end: `0x1400430fb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400431e8`

## callees

- `0x14002c8c0`
- `0x14002cbc0`
- `0x140043010`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140043034`
- `ntoskrnl!RtlLengthSid` at `0x140043034`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400430dd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400430dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004306e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004306e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400430ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400430ae`

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
0x140043010  push    rbx
0x140043012  push    rbp
0x140043013  push    rsi
0x140043014  push    rdi
0x140043015  push    r12
0x140043017  push    r13
0x140043019  push    r14
0x14004301b  push    r15
0x14004301d  sub     rsp, 28h
0x140043021  mov     rdi, [rcx]
0x140043024  mov     r15, rcx
0x140043027  mov     rcx, [rsp+68h+Sid]; Sid
0x14004302f  mov     r14, rdx
0x140043032  mov     esi, [rdx]
0x140043034  call    cs:__imp_RtlLengthSid
0x14004303b  nop     dword ptr [rax+rax+00h]
0x140043040  lea     r8d, [rax+8]
0x140043044  movzx   eax, word ptr [rdi+2]
0x140043048  lea     ebp, [r8+rsi]
0x14004304c  cmp     ebp, eax
0x14004304e  jbe     short loc_1400430BF
0x140043050  imul    r8d, [rsp+68h+arg_28]
0x140043059  mov     ecx, 1; PoolType
0x14004305e  lea     r12d, [r8+rsi]
0x140043062  mov     r8d, 6C416553h; Tag
0x140043068  mov     edx, r12d; NumberOfBytes
0x14004306b  mov     r13d, r12d
0x14004306e  call    cs:__imp_ExAllocatePoolWithTag
0x140043075  nop     dword ptr [rax+rax+00h]
0x14004307a  mov     rbx, rax
0x14004307d  test    rax, rax
0x140043080  jnz     short loc_140043089
0x140043082  mov     eax, 0C000009Ah
0x140043087  jmp     short loc_1400430E9
0x140043089  mov     r8, r13; Size
0x14004308c  xor     edx, edx; Val
0x14004308e  mov     rcx, rbx; void *
0x140043091  call    memset
0x140043096  mov     rdx, [r15]; Src
0x140043099  mov     r8, rsi; Size
0x14004309c  mov     rcx, rbx; void *
0x14004309f  call    memmove
0x1400430a4  xor     edx, edx; Tag
0x1400430a6  mov     [rbx+2], r12w
0x1400430ab  mov     rcx, rdi; P
0x1400430ae  call    cs:__imp_ExFreePoolWithTag
0x1400430b5  nop     dword ptr [rax+rax+00h]
0x1400430ba  mov     [r15], rbx
0x1400430bd  jmp     short loc_1400430C2
0x1400430bf  mov     rbx, rdi
0x1400430c2  mov     r9, [rsp+68h+Sid]; Sid
0x1400430ca  mov     edx, 2; AceRevision
0x1400430cf  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400430d7  mov     rcx, rbx; Acl
0x1400430da  mov     [r14], ebp
0x1400430dd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400430e4  nop     dword ptr [rax+rax+00h]
0x1400430e9  add     rsp, 28h
0x1400430ed  pop     r15
0x1400430ef  pop     r14
0x1400430f1  pop     r13
0x1400430f3  pop     r12
0x1400430f5  pop     rdi
0x1400430f6  pop     rsi
0x1400430f7  pop     rbp
0x1400430f8  pop     rbx
0x1400430f9  retn
```
