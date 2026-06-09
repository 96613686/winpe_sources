# SepSddlAddAceToAcl

- ea: `0x1400aac10`
- end: `0x1400aacfb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400aade8`

## callees

- `0x140078100`
- `0x140078400`
- `0x1400aac10`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x1400aac34`
- `ntoskrnl!RtlLengthSid` at `0x1400aac34`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aacae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aacae`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400aacdd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400aacdd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aac6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400aac6e`

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
0x1400aac10  push    rbx
0x1400aac12  push    rbp
0x1400aac13  push    rsi
0x1400aac14  push    rdi
0x1400aac15  push    r12
0x1400aac17  push    r13
0x1400aac19  push    r14
0x1400aac1b  push    r15
0x1400aac1d  sub     rsp, 28h
0x1400aac21  mov     rdi, [rcx]
0x1400aac24  mov     r15, rcx
0x1400aac27  mov     rcx, [rsp+68h+Sid]; Sid
0x1400aac2f  mov     r14, rdx
0x1400aac32  mov     esi, [rdx]
0x1400aac34  call    cs:__imp_RtlLengthSid
0x1400aac3b  nop     dword ptr [rax+rax+00h]
0x1400aac40  lea     r8d, [rax+8]
0x1400aac44  movzx   eax, word ptr [rdi+2]
0x1400aac48  lea     ebp, [r8+rsi]
0x1400aac4c  cmp     ebp, eax
0x1400aac4e  jbe     short loc_1400AACBF
0x1400aac50  imul    r8d, [rsp+68h+arg_28]
0x1400aac59  mov     ecx, 1; PoolType
0x1400aac5e  lea     r12d, [r8+rsi]
0x1400aac62  mov     r8d, 6C416553h; Tag
0x1400aac68  mov     edx, r12d; NumberOfBytes
0x1400aac6b  mov     r13d, r12d
0x1400aac6e  call    cs:__imp_ExAllocatePoolWithTag
0x1400aac75  nop     dword ptr [rax+rax+00h]
0x1400aac7a  mov     rbx, rax
0x1400aac7d  test    rax, rax
0x1400aac80  jnz     short loc_1400AAC89
0x1400aac82  mov     eax, 0C000009Ah
0x1400aac87  jmp     short loc_1400AACE9
0x1400aac89  mov     r8, r13; Size
0x1400aac8c  xor     edx, edx; Val
0x1400aac8e  mov     rcx, rbx; void *
0x1400aac91  call    memset
0x1400aac96  mov     rdx, [r15]; Src
0x1400aac99  mov     r8, rsi; Size
0x1400aac9c  mov     rcx, rbx; void *
0x1400aac9f  call    memmove
0x1400aaca4  xor     edx, edx; Tag
0x1400aaca6  mov     [rbx+2], r12w
0x1400aacab  mov     rcx, rdi; P
0x1400aacae  call    cs:__imp_ExFreePoolWithTag
0x1400aacb5  nop     dword ptr [rax+rax+00h]
0x1400aacba  mov     [r15], rbx
0x1400aacbd  jmp     short loc_1400AACC2
0x1400aacbf  mov     rbx, rdi
0x1400aacc2  mov     r9, [rsp+68h+Sid]; Sid
0x1400aacca  mov     edx, 2; AceRevision
0x1400aaccf  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400aacd7  mov     rcx, rbx; Acl
0x1400aacda  mov     [r14], ebp
0x1400aacdd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400aace4  nop     dword ptr [rax+rax+00h]
0x1400aace9  add     rsp, 28h
0x1400aaced  pop     r15
0x1400aacef  pop     r14
0x1400aacf1  pop     r13
0x1400aacf3  pop     r12
0x1400aacf5  pop     rdi
0x1400aacf6  pop     rsi
0x1400aacf7  pop     rbp
0x1400aacf8  pop     rbx
0x1400aacf9  retn
```
