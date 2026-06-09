# SepSddlAddAceToAcl

- ea: `0x14000f6a0`
- end: `0x14000f78b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000f878`

## callees

- `0x1400014c0`
- `0x1400017c0`
- `0x14000f6a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f73e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f73e`
- `ntoskrnl!RtlLengthSid` at `0x14000f6c4`
- `ntoskrnl!RtlLengthSid` at `0x14000f6c4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000f76d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000f76d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f6fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f6fe`

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
0x14000f6a0  push    rbx
0x14000f6a2  push    rbp
0x14000f6a3  push    rsi
0x14000f6a4  push    rdi
0x14000f6a5  push    r12
0x14000f6a7  push    r13
0x14000f6a9  push    r14
0x14000f6ab  push    r15
0x14000f6ad  sub     rsp, 28h
0x14000f6b1  mov     rdi, [rcx]
0x14000f6b4  mov     r15, rcx
0x14000f6b7  mov     rcx, [rsp+68h+Sid]; Sid
0x14000f6bf  mov     r14, rdx
0x14000f6c2  mov     esi, [rdx]
0x14000f6c4  call    cs:__imp_RtlLengthSid
0x14000f6cb  nop     dword ptr [rax+rax+00h]
0x14000f6d0  lea     r8d, [rax+8]
0x14000f6d4  movzx   eax, word ptr [rdi+2]
0x14000f6d8  lea     ebp, [r8+rsi]
0x14000f6dc  cmp     ebp, eax
0x14000f6de  jbe     short loc_14000F74F
0x14000f6e0  imul    r8d, [rsp+68h+arg_28]
0x14000f6e9  mov     ecx, 1; PoolType
0x14000f6ee  lea     r12d, [r8+rsi]
0x14000f6f2  mov     r8d, 6C416553h; Tag
0x14000f6f8  mov     edx, r12d; NumberOfBytes
0x14000f6fb  mov     r13d, r12d
0x14000f6fe  call    cs:__imp_ExAllocatePoolWithTag
0x14000f705  nop     dword ptr [rax+rax+00h]
0x14000f70a  mov     rbx, rax
0x14000f70d  test    rax, rax
0x14000f710  jnz     short loc_14000F719
0x14000f712  mov     eax, 0C000009Ah
0x14000f717  jmp     short loc_14000F779
0x14000f719  mov     r8, r13; Size
0x14000f71c  xor     edx, edx; Val
0x14000f71e  mov     rcx, rbx; void *
0x14000f721  call    memset
0x14000f726  mov     rdx, [r15]; Src
0x14000f729  mov     r8, rsi; Size
0x14000f72c  mov     rcx, rbx; void *
0x14000f72f  call    memmove
0x14000f734  xor     edx, edx; Tag
0x14000f736  mov     [rbx+2], r12w
0x14000f73b  mov     rcx, rdi; P
0x14000f73e  call    cs:__imp_ExFreePoolWithTag
0x14000f745  nop     dword ptr [rax+rax+00h]
0x14000f74a  mov     [r15], rbx
0x14000f74d  jmp     short loc_14000F752
0x14000f74f  mov     rbx, rdi
0x14000f752  mov     r9, [rsp+68h+Sid]; Sid
0x14000f75a  mov     edx, 2; AceRevision
0x14000f75f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x14000f767  mov     rcx, rbx; Acl
0x14000f76a  mov     [r14], ebp
0x14000f76d  call    cs:__imp_RtlAddAccessAllowedAce
0x14000f774  nop     dword ptr [rax+rax+00h]
0x14000f779  add     rsp, 28h
0x14000f77d  pop     r15
0x14000f77f  pop     r14
0x14000f781  pop     r13
0x14000f783  pop     r12
0x14000f785  pop     rdi
0x14000f786  pop     rsi
0x14000f787  pop     rbp
0x14000f788  pop     rbx
0x14000f789  retn
```
