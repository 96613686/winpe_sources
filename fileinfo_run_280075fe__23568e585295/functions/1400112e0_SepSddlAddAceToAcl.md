# SepSddlAddAceToAcl

- ea: `0x1400112e0`
- end: `0x1400113cb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400114b8`

## callees

- `0x140003a80`
- `0x140003d80`
- `0x1400112e0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140011304`
- `ntoskrnl!RtlLengthSid` at `0x140011304`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400113ad`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400113ad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001133e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001133e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001137e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001137e`

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
0x1400112e0  push    rbx
0x1400112e2  push    rbp
0x1400112e3  push    rsi
0x1400112e4  push    rdi
0x1400112e5  push    r12
0x1400112e7  push    r13
0x1400112e9  push    r14
0x1400112eb  push    r15
0x1400112ed  sub     rsp, 28h
0x1400112f1  mov     rdi, [rcx]
0x1400112f4  mov     r15, rcx
0x1400112f7  mov     rcx, [rsp+68h+Sid]; Sid
0x1400112ff  mov     r14, rdx
0x140011302  mov     esi, [rdx]
0x140011304  call    cs:__imp_RtlLengthSid
0x14001130b  nop     dword ptr [rax+rax+00h]
0x140011310  lea     r8d, [rax+8]
0x140011314  movzx   eax, word ptr [rdi+2]
0x140011318  lea     ebp, [r8+rsi]
0x14001131c  cmp     ebp, eax
0x14001131e  jbe     short loc_14001138F
0x140011320  imul    r8d, [rsp+68h+arg_28]
0x140011329  mov     ecx, 1; PoolType
0x14001132e  lea     r12d, [r8+rsi]
0x140011332  mov     r8d, 6C416553h; Tag
0x140011338  mov     edx, r12d; NumberOfBytes
0x14001133b  mov     r13d, r12d
0x14001133e  call    cs:__imp_ExAllocatePoolWithTag
0x140011345  nop     dword ptr [rax+rax+00h]
0x14001134a  mov     rbx, rax
0x14001134d  test    rax, rax
0x140011350  jnz     short loc_140011359
0x140011352  mov     eax, 0C000009Ah
0x140011357  jmp     short loc_1400113B9
0x140011359  mov     r8, r13; Size
0x14001135c  xor     edx, edx; Val
0x14001135e  mov     rcx, rbx; void *
0x140011361  call    memset
0x140011366  mov     rdx, [r15]; Src
0x140011369  mov     r8, rsi; Size
0x14001136c  mov     rcx, rbx; void *
0x14001136f  call    memmove
0x140011374  xor     edx, edx; Tag
0x140011376  mov     [rbx+2], r12w
0x14001137b  mov     rcx, rdi; P
0x14001137e  call    cs:__imp_ExFreePoolWithTag
0x140011385  nop     dword ptr [rax+rax+00h]
0x14001138a  mov     [r15], rbx
0x14001138d  jmp     short loc_140011392
0x14001138f  mov     rbx, rdi
0x140011392  mov     r9, [rsp+68h+Sid]; Sid
0x14001139a  mov     edx, 2; AceRevision
0x14001139f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400113a7  mov     rcx, rbx; Acl
0x1400113aa  mov     [r14], ebp
0x1400113ad  call    cs:__imp_RtlAddAccessAllowedAce
0x1400113b4  nop     dword ptr [rax+rax+00h]
0x1400113b9  add     rsp, 28h
0x1400113bd  pop     r15
0x1400113bf  pop     r14
0x1400113c1  pop     r13
0x1400113c3  pop     r12
0x1400113c5  pop     rdi
0x1400113c6  pop     rsi
0x1400113c7  pop     rbp
0x1400113c8  pop     rbx
0x1400113c9  retn
```
