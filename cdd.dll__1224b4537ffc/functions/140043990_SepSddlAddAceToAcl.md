# SepSddlAddAceToAcl

- ea: `0x140043990`
- end: `0x140043a7b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140043b68`

## callees

- `0x140037340`
- `0x140037640`
- `0x140043990`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400439ee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400439ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043a2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043a2e`
- `ntoskrnl!RtlLengthSid` at `0x1400439b4`
- `ntoskrnl!RtlLengthSid` at `0x1400439b4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140043a5d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140043a5d`

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
0x140043990  push    rbx
0x140043992  push    rbp
0x140043993  push    rsi
0x140043994  push    rdi
0x140043995  push    r12
0x140043997  push    r13
0x140043999  push    r14
0x14004399b  push    r15
0x14004399d  sub     rsp, 28h
0x1400439a1  mov     rdi, [rcx]
0x1400439a4  mov     r15, rcx
0x1400439a7  mov     rcx, [rsp+68h+Sid]; Sid
0x1400439af  mov     r14, rdx
0x1400439b2  mov     esi, [rdx]
0x1400439b4  call    cs:__imp_RtlLengthSid
0x1400439bb  nop     dword ptr [rax+rax+00h]
0x1400439c0  lea     r8d, [rax+8]
0x1400439c4  movzx   eax, word ptr [rdi+2]
0x1400439c8  lea     ebp, [r8+rsi]
0x1400439cc  cmp     ebp, eax
0x1400439ce  jbe     short loc_140043A3F
0x1400439d0  imul    r8d, [rsp+68h+arg_28]
0x1400439d9  mov     ecx, 1; PoolType
0x1400439de  lea     r12d, [r8+rsi]
0x1400439e2  mov     r8d, 6C416553h; Tag
0x1400439e8  mov     edx, r12d; NumberOfBytes
0x1400439eb  mov     r13d, r12d
0x1400439ee  call    cs:__imp_ExAllocatePoolWithTag
0x1400439f5  nop     dword ptr [rax+rax+00h]
0x1400439fa  mov     rbx, rax
0x1400439fd  test    rax, rax
0x140043a00  jnz     short loc_140043A09
0x140043a02  mov     eax, 0C000009Ah
0x140043a07  jmp     short loc_140043A69
0x140043a09  mov     r8, r13; Size
0x140043a0c  xor     edx, edx; Val
0x140043a0e  mov     rcx, rbx; void *
0x140043a11  call    memset
0x140043a16  mov     rdx, [r15]; Src
0x140043a19  mov     r8, rsi; Size
0x140043a1c  mov     rcx, rbx; void *
0x140043a1f  call    memmove
0x140043a24  xor     edx, edx; Tag
0x140043a26  mov     [rbx+2], r12w
0x140043a2b  mov     rcx, rdi; P
0x140043a2e  call    cs:__imp_ExFreePoolWithTag
0x140043a35  nop     dword ptr [rax+rax+00h]
0x140043a3a  mov     [r15], rbx
0x140043a3d  jmp     short loc_140043A42
0x140043a3f  mov     rbx, rdi
0x140043a42  mov     r9, [rsp+68h+Sid]; Sid
0x140043a4a  mov     edx, 2; AceRevision
0x140043a4f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140043a57  mov     rcx, rbx; Acl
0x140043a5a  mov     [r14], ebp
0x140043a5d  call    cs:__imp_RtlAddAccessAllowedAce
0x140043a64  nop     dword ptr [rax+rax+00h]
0x140043a69  add     rsp, 28h
0x140043a6d  pop     r15
0x140043a6f  pop     r14
0x140043a71  pop     r13
0x140043a73  pop     r12
0x140043a75  pop     rdi
0x140043a76  pop     rsi
0x140043a77  pop     rbp
0x140043a78  pop     rbx
0x140043a79  retn
```
