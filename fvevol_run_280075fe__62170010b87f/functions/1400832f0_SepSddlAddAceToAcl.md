# SepSddlAddAceToAcl

- ea: `0x1400832f0`
- end: `0x1400833db`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400834c8`

## callees

- `0x140021a00`
- `0x140021d00`
- `0x1400832f0`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140083314`
- `ntoskrnl!RtlLengthSid` at `0x140083314`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400833bd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400833bd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14008334e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14008334e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008338e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008338e`

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
0x1400832f0  push    rbx
0x1400832f2  push    rbp
0x1400832f3  push    rsi
0x1400832f4  push    rdi
0x1400832f5  push    r12
0x1400832f7  push    r13
0x1400832f9  push    r14
0x1400832fb  push    r15
0x1400832fd  sub     rsp, 28h
0x140083301  mov     rdi, [rcx]
0x140083304  mov     r15, rcx
0x140083307  mov     rcx, [rsp+68h+Sid]; Sid
0x14008330f  mov     r14, rdx
0x140083312  mov     esi, [rdx]
0x140083314  call    cs:__imp_RtlLengthSid
0x14008331b  nop     dword ptr [rax+rax+00h]
0x140083320  lea     r8d, [rax+8]
0x140083324  movzx   eax, word ptr [rdi+2]
0x140083328  lea     ebp, [r8+rsi]
0x14008332c  cmp     ebp, eax
0x14008332e  jbe     short loc_14008339F
0x140083330  imul    r8d, [rsp+68h+arg_28]
0x140083339  mov     ecx, 1; PoolType
0x14008333e  lea     r12d, [r8+rsi]
0x140083342  mov     r8d, 6C416553h; Tag
0x140083348  mov     edx, r12d; NumberOfBytes
0x14008334b  mov     r13d, r12d
0x14008334e  call    cs:__imp_ExAllocatePoolWithTag
0x140083355  nop     dword ptr [rax+rax+00h]
0x14008335a  mov     rbx, rax
0x14008335d  test    rax, rax
0x140083360  jnz     short loc_140083369
0x140083362  mov     eax, 0C000009Ah
0x140083367  jmp     short loc_1400833C9
0x140083369  mov     r8, r13; Size
0x14008336c  xor     edx, edx; Val
0x14008336e  mov     rcx, rbx; void *
0x140083371  call    memset
0x140083376  mov     rdx, [r15]; Src
0x140083379  mov     r8, rsi; Size
0x14008337c  mov     rcx, rbx; void *
0x14008337f  call    memmove
0x140083384  xor     edx, edx; Tag
0x140083386  mov     [rbx+2], r12w
0x14008338b  mov     rcx, rdi; P
0x14008338e  call    cs:__imp_ExFreePoolWithTag
0x140083395  nop     dword ptr [rax+rax+00h]
0x14008339a  mov     [r15], rbx
0x14008339d  jmp     short loc_1400833A2
0x14008339f  mov     rbx, rdi
0x1400833a2  mov     r9, [rsp+68h+Sid]; Sid
0x1400833aa  mov     edx, 2; AceRevision
0x1400833af  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400833b7  mov     rcx, rbx; Acl
0x1400833ba  mov     [r14], ebp
0x1400833bd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400833c4  nop     dword ptr [rax+rax+00h]
0x1400833c9  add     rsp, 28h
0x1400833cd  pop     r15
0x1400833cf  pop     r14
0x1400833d1  pop     r13
0x1400833d3  pop     r12
0x1400833d5  pop     rdi
0x1400833d6  pop     rsi
0x1400833d7  pop     rbp
0x1400833d8  pop     rbx
0x1400833d9  retn
```
