# SepSddlAddAceToAcl

- ea: `0x140009500`
- end: `0x1400095eb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400096d8`

## callees

- `0x140002640`
- `0x140002940`
- `0x140009500`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140009524`
- `ntoskrnl!RtlLengthSid` at `0x140009524`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400095cd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400095cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000959e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000959e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000955e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000955e`

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
0x140009500  push    rbx
0x140009502  push    rbp
0x140009503  push    rsi
0x140009504  push    rdi
0x140009505  push    r12
0x140009507  push    r13
0x140009509  push    r14
0x14000950b  push    r15
0x14000950d  sub     rsp, 28h
0x140009511  mov     rdi, [rcx]
0x140009514  mov     r15, rcx
0x140009517  mov     rcx, [rsp+68h+Sid]; Sid
0x14000951f  mov     r14, rdx
0x140009522  mov     esi, [rdx]
0x140009524  call    cs:__imp_RtlLengthSid
0x14000952b  nop     dword ptr [rax+rax+00h]
0x140009530  lea     r8d, [rax+8]
0x140009534  movzx   eax, word ptr [rdi+2]
0x140009538  lea     ebp, [r8+rsi]
0x14000953c  cmp     ebp, eax
0x14000953e  jbe     short loc_1400095AF
0x140009540  imul    r8d, [rsp+68h+arg_28]
0x140009549  mov     ecx, 1; PoolType
0x14000954e  lea     r12d, [r8+rsi]
0x140009552  mov     r8d, 6C416553h; Tag
0x140009558  mov     edx, r12d; NumberOfBytes
0x14000955b  mov     r13d, r12d
0x14000955e  call    cs:__imp_ExAllocatePoolWithTag
0x140009565  nop     dword ptr [rax+rax+00h]
0x14000956a  mov     rbx, rax
0x14000956d  test    rax, rax
0x140009570  jnz     short loc_140009579
0x140009572  mov     eax, 0C000009Ah
0x140009577  jmp     short loc_1400095D9
0x140009579  mov     r8, r13; Size
0x14000957c  xor     edx, edx; Val
0x14000957e  mov     rcx, rbx; void *
0x140009581  call    memset
0x140009586  mov     rdx, [r15]; Src
0x140009589  mov     r8, rsi; Size
0x14000958c  mov     rcx, rbx; void *
0x14000958f  call    memmove
0x140009594  xor     edx, edx; Tag
0x140009596  mov     [rbx+2], r12w
0x14000959b  mov     rcx, rdi; P
0x14000959e  call    cs:__imp_ExFreePoolWithTag
0x1400095a5  nop     dword ptr [rax+rax+00h]
0x1400095aa  mov     [r15], rbx
0x1400095ad  jmp     short loc_1400095B2
0x1400095af  mov     rbx, rdi
0x1400095b2  mov     r9, [rsp+68h+Sid]; Sid
0x1400095ba  mov     edx, 2; AceRevision
0x1400095bf  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x1400095c7  mov     rcx, rbx; Acl
0x1400095ca  mov     [r14], ebp
0x1400095cd  call    cs:__imp_RtlAddAccessAllowedAce
0x1400095d4  nop     dword ptr [rax+rax+00h]
0x1400095d9  add     rsp, 28h
0x1400095dd  pop     r15
0x1400095df  pop     r14
0x1400095e1  pop     r13
0x1400095e3  pop     r12
0x1400095e5  pop     rdi
0x1400095e6  pop     rsi
0x1400095e7  pop     rbp
0x1400095e8  pop     rbx
0x1400095e9  retn
```
