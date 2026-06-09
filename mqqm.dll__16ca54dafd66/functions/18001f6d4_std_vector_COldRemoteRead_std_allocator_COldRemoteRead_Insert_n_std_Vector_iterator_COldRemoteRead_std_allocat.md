# std::vector<COldRemoteRead *,std::allocator<COldRemoteRead *>>::_Insert_n(std::_Vector_iterator<COldRemoteRead *,std::allocator<COldRemoteRead *>>,unsigned __int64,COldRemoteRead * const &)

- ea: `0x18001f6d4`
- end: `0x18001f909`
- name: `?_Insert_n@?$vector@PEAVCOldRemoteRead@@V?$allocator@PEAVCOldRemoteRead@@@std@@@std@@IEAAXV?$_Vector_iterator@PEAVCOldRemoteRead@@V?$allocator@PEAVCOldRemoteRead@@@std@@@2@_KAEBQEAVCOldRemoteRead@@@Z`
- size: `565`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e7e4`
- `0x18004368c`
- `0x1800995d8`

## callees

- `0x180004d91`
- `0x1800111d0`
- `0x180011540`
- `0x18001d810`
- `0x18001f6d4`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18001f847`
- `msvcrt!free` at `0x18001f847`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001f7a2`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001f7a2`
- `msvcrt!memmove_s` at `0x18001f801`
- `msvcrt!memmove_s` at `0x18001f82c`
- `msvcrt!memmove_s` at `0x18001f8b6`
- `msvcrt!memmove_s` at `0x18001f8e1`
- `msvcrt!memmove_s` at `0x18001f801`
- `msvcrt!memmove_s` at `0x18001f82c`
- `msvcrt!memmove_s` at `0x18001f8b6`
- `msvcrt!memmove_s` at `0x18001f8e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::vector<COldRemoteRead *>::_Insert_n(__int64 a1, char *a2, const char *a3, const char **a4)
{
  const char *v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  __int64 v14; // r9
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // rcx
  char *v23; // rax
  char *v24; // r14
  _BYTE *v25; // r8
  __int64 v26; // rcx
  __int64 v27; // r15
  __int64 v28; // rdx
  __int64 v29; // rbx
  void *v30; // rcx
  __int64 result; // rax
  _BYTE *v32; // rdi
  unsigned __int64 v33; // r8
  char *v34; // rdx
  __int64 v35; // rdx
  _QWORD pExceptionObject[11]; // [rsp+20h] [rbp-58h] BYREF
  char *v37; // [rsp+90h] [rbp+18h] BYREF

  v37 = (char *)a3;
  v6 = *a4;
  v37 = (char *)*a4;
  if ( *(_QWORD *)(a1 + 8) )
    v7 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 3;
  else
    v7 = 0;
  v8 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v7);
  if ( v8 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<CAttachment>::_Xlen(0, v9, 1);
  v10 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v9);
  if ( v11 >= v13 + v10 )
  {
    v32 = *(_BYTE **)(a1 + 16);
    if ( (v32 - a2) >> 3 >= v13 )
    {
      memmove_s(*(void *const *)(a1 + 16), 8u, v32 - 8, 8u);
      *(_QWORD *)(a1 + 16) = v32 + 8;
      v35 = (v32 - a2 - 8) >> 3;
      if ( v35 > 0 )
        memmove_s(&v32[-8 * v35], 8 * v35, a2, 8 * v35);
      v34 = a2 + 8;
    }
    else
    {
      v33 = v13 - ((v32 - a2) >> 3);
      if ( v33 )
        memset64(v32, (unsigned __int64)v6, v33);
      v34 = *(char **)(a1 + 16);
      *(_QWORD *)(a1 + 16) = v34 + 8;
    }
    return std::fill<COldRemoteRead * *,COldRemoteRead *>(a2, v34, &v37);
  }
  else
  {
    v15 = 0;
    if ( v14 - (v11 >> 1) >= v11 )
      v15 = v11 + (v11 >> 1);
    v16 = std::vector<CXdsReferenceValidateInfo *>::size(v12, v11);
    if ( v15 < v19 + v16 )
    {
      v20 = std::vector<CXdsReferenceValidateInfo *>::size(v18, v17);
      v15 = v21 + v20;
    }
    if ( v15 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 8 )
      {
        v37 = 0;
        exception::exception((exception *)pExceptionObject, (const char *const *)&v37);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      v22 = v15;
    }
    else
    {
      v22 = 0;
    }
    v23 = (char *)MmAllocate(8 * v22);
    v24 = v23;
    v37 = v23;
    try
    {
      v25 = *(_BYTE **)(a1 + 8);
      v26 = (a2 - v25) >> 3;
      v27 = 8 * v26;
      if ( v26 )
        memmove_s(v23, 8 * v26, v25, 8 * v26);
      *(_QWORD *)&v24[v27] = v6;
      v28 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 3;
      if ( v28 )
        memmove_s(&v24[v27 + 8], 8 * v28, a2, 8 * v28);
    }
    catch ( ... )
    {
      free(v37);
      throw;
    }
    v29 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v28);
    v30 = *(void **)(a1 + 8);
    if ( v30 )
      free(v30);
    *(_QWORD *)(a1 + 24) = &v24[8 * v15];
    result = (__int64)&v24[8 * v29 + 8];
    *(_QWORD *)(a1 + 16) = result;
    *(_QWORD *)(a1 + 8) = v24;
  }
  return result;
}

```

## disassembly

```asm
0x18001f6d4  mov     rax, rsp
0x18001f6d7  mov     [rax+18h], r8
0x18001f6db  push    rbx
0x18001f6dc  push    rsi
0x18001f6dd  push    rdi
0x18001f6de  push    r12
0x18001f6e0  push    r14
0x18001f6e2  push    r15
0x18001f6e4  sub     rsp, 48h
0x18001f6e8  mov     rbx, rdx
0x18001f6eb  mov     rsi, rcx
0x18001f6ee  mov     r12, [r9]
0x18001f6f1  mov     [rax+18h], r12
0x18001f6f5  cmp     qword ptr [rcx+8], 0
0x18001f6fa  jnz     short loc_18001F700
0x18001f6fc  xor     edx, edx
0x18001f6fe  jmp     short loc_18001F70C
0x18001f700  mov     rdx, [rcx+18h]
0x18001f704  sub     rdx, [rcx+8]
0x18001f708  sar     rdx, 3
0x18001f70c  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f711  mov     r9, 1FFFFFFFFFFFFFFFh
0x18001f71b  mov     rcx, r9
0x18001f71e  sub     rcx, rax
0x18001f721  mov     r8d, 1
0x18001f727  cmp     rcx, r8
0x18001f72a  jnb     short loc_18001F732
0x18001f72c  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x18001f732  mov     rcx, rsi
0x18001f735  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f73a  add     rax, r8
0x18001f73d  cmp     rdx, rax
0x18001f740  jnb     loc_18001F86B
0x18001f746  mov     rax, rdx
0x18001f749  shr     rax, 1
0x18001f74c  sub     r9, rax
0x18001f74f  add     rax, rdx
0x18001f752  xor     edi, edi
0x18001f754  cmp     r9, rdx
0x18001f757  cmovnb  rdi, rax
0x18001f75b  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f760  add     rax, r8
0x18001f763  cmp     rdi, rax
0x18001f766  jnb     short loc_18001F771
0x18001f768  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f76d  lea     rdi, [r8+rax]
0x18001f771  test    rdi, rdi
0x18001f774  jnz     short loc_18001F77A
0x18001f776  xor     ecx, ecx
0x18001f778  jmp     short loc_18001F7C9
0x18001f77a  xor     edx, edx
0x18001f77c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f780  div     rdi
0x18001f783  cmp     rax, 8
0x18001f787  jnb     short loc_18001F7C6
0x18001f789  mov     [rsp+78h+arg_10], 0
0x18001f795  lea     rdx, [rsp+78h+arg_10]
0x18001f79d  lea     rcx, [rsp+78h+pExceptionObject]
0x18001f7a2  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001f7a8  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001f7af  mov     [rsp+78h+pExceptionObject], rax
0x18001f7b4  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001f7bb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001f7c0  call    _CxxThrowException_0
0x18001f7c6  mov     rcx, rdi
0x18001f7c9  shl     rcx, 3; unsigned __int64
0x18001f7cd  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001f7d2  mov     r14, rax
0x18001f7d5  mov     [rsp+78h+arg_10], rax
0x18001f7dd  mov     r8, [rsi+8]; Source
0x18001f7e1  mov     rcx, rbx
0x18001f7e4  sub     rcx, r8
0x18001f7e7  sar     rcx, 3
0x18001f7eb  lea     r15, ds:0[rcx*8]
0x18001f7f3  test    rcx, rcx
0x18001f7f6  jz      short loc_18001F807
0x18001f7f8  mov     r9, r15; SourceSize
0x18001f7fb  mov     rdx, r15; DestinationSize
0x18001f7fe  mov     rcx, rax; Destination
0x18001f801  call    cs:__imp_memmove_s
0x18001f807  mov     [r15+r14], r12
0x18001f80b  mov     rdx, [rsi+10h]
0x18001f80f  sub     rdx, rbx
0x18001f812  sar     rdx, 3
0x18001f816  test    rdx, rdx
0x18001f819  jz      short loc_18001F833
0x18001f81b  shl     rdx, 3; DestinationSize
0x18001f81f  lea     rcx, [r15+8]
0x18001f823  add     rcx, r14; Destination
0x18001f826  mov     r9, rdx; SourceSize
0x18001f829  mov     r8, rbx; Source
0x18001f82c  call    cs:__imp_memmove_s
0x18001f832  nop
0x18001f833  mov     rcx, rsi
0x18001f836  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18001f83b  mov     rbx, rax
0x18001f83e  mov     rcx, [rsi+8]; Block
0x18001f842  test    rcx, rcx
0x18001f845  jz      short loc_18001F84E
0x18001f847  call    cs:__imp_free
0x18001f84d  nop
0x18001f84e  lea     rax, [r14+rdi*8]
0x18001f852  mov     [rsi+18h], rax
0x18001f856  lea     rax, [rbx+1]
0x18001f85a  lea     rax, [r14+rax*8]
0x18001f85e  mov     [rsi+10h], rax
0x18001f862  mov     [rsi+8], r14
0x18001f866  jmp     loc_18001F8FB
0x18001f86b  mov     rdi, [rsi+10h]
0x18001f86f  mov     r14, rdi
0x18001f872  sub     r14, rbx
0x18001f875  mov     rax, r14
0x18001f878  sar     rax, 3
0x18001f87c  cmp     rax, r8
0x18001f87f  jnb     short loc_18001F8A7
0x18001f881  mov     rdx, rdi
0x18001f884  sub     rdx, rbx
0x18001f887  sar     rdx, 3
0x18001f88b  sub     r8, rdx
0x18001f88e  jz      short loc_18001F899
0x18001f890  mov     rax, r12
0x18001f893  mov     rcx, r8
0x18001f896  rep stosq
0x18001f899  mov     rdx, [rsi+10h]
0x18001f89d  lea     rax, [rdx+8]
0x18001f8a1  mov     [rsi+10h], rax
0x18001f8a5  jmp     short loc_18001F8EB
0x18001f8a7  lea     r8, [rdi-8]; Source
0x18001f8ab  mov     edx, 8; DestinationSize
0x18001f8b0  mov     r9d, edx; SourceSize
0x18001f8b3  mov     rcx, rdi; Destination
0x18001f8b6  call    cs:__imp_memmove_s
0x18001f8bc  lea     rax, [rdi+8]
0x18001f8c0  mov     [rsi+10h], rax
0x18001f8c4  lea     rdx, [r14-8]
0x18001f8c8  sar     rdx, 3
0x18001f8cc  test    rdx, rdx
0x18001f8cf  jle     short loc_18001F8E7
0x18001f8d1  shl     rdx, 3; DestinationSize
0x18001f8d5  sub     rdi, rdx
0x18001f8d8  mov     r9, rdx; SourceSize
0x18001f8db  mov     r8, rbx; Source
0x18001f8de  mov     rcx, rdi; Destination
0x18001f8e1  call    cs:__imp_memmove_s
0x18001f8e7  lea     rdx, [rbx+8]
0x18001f8eb  lea     r8, [rsp+78h+arg_10]
0x18001f8f3  mov     rcx, rbx
0x18001f8f6  call    ??$fill@PEAPEAVCOldRemoteRead@@PEAV1@@std@@YAXPEAPEAVCOldRemoteRead@@0AEBQEAV1@@Z; std::fill<COldRemoteRead * *,COldRemoteRead *>(COldRemoteRead * *,COldRemoteRead * *,COldRemoteRead * const &)
0x18001f8fb  add     rsp, 48h
0x18001f8ff  pop     r15
0x18001f901  pop     r14
0x18001f903  pop     r12
0x18001f905  pop     rdi
0x18001f906  pop     rsi
0x18001f907  pop     rbx
0x18001f908  retn
```
