# std::vector<CXdsReferenceInput *,std::allocator<CXdsReferenceInput *>>::_Insert_n(std::_Vector_iterator<CXdsReferenceInput *,std::allocator<CXdsReferenceInput *>>,unsigned __int64,CXdsReferenceInput * const &)

- ea: `0x180019f98`
- end: `0x18001a1cd`
- name: `?_Insert_n@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@IEAAXV?$_Vector_iterator@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@2@_KAEBQEAVCXdsReferenceInput@@@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a88c`

## callees

- `0x180003426`
- `0x18001722c`
- `0x180018ec4`
- `0x180019f98`
- `0x18001a248`
- `0x18001ab7c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001a066`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001a066`
- `msvcrt!free` at `0x18001a10b`
- `msvcrt!free` at `0x18001a10b`
- `msvcrt!memmove_s` at `0x18001a0c5`
- `msvcrt!memmove_s` at `0x18001a0f0`
- `msvcrt!memmove_s` at `0x18001a17a`
- `msvcrt!memmove_s` at `0x18001a1a5`
- `msvcrt!memmove_s` at `0x18001a0c5`
- `msvcrt!memmove_s` at `0x18001a0f0`
- `msvcrt!memmove_s` at `0x18001a17a`
- `msvcrt!memmove_s` at `0x18001a1a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::vector<CXdsReferenceInput *>::_Insert_n(__int64 a1, char *a2, const char *a3, const char **a4)
{
  const char *v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r8
  unsigned __int64 v21; // rcx
  char *v22; // rax
  char *v23; // r14
  _BYTE *v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rbx
  void *v29; // rcx
  __int64 result; // rax
  _BYTE *v31; // rdi
  unsigned __int64 v32; // r8
  char *v33; // rdx
  __int64 v34; // rdx
  _QWORD pExceptionObject[11]; // [rsp+20h] [rbp-58h] BYREF
  char *v36; // [rsp+90h] [rbp+18h] BYREF

  v36 = (char *)a3;
  v6 = *a4;
  v36 = (char *)*a4;
  if ( *(_QWORD *)(a1 + 8) )
    v7 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 3;
  else
    v7 = 0;
  if ( std::vector<CXdsReferenceInput *>::size(a1, v7) == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<CXdsReferenceInput *>::_Xlen();
  v9 = std::vector<CXdsReferenceInput *>::size(a1, v8);
  if ( v10 >= v12 + v9 )
  {
    v31 = *(_BYTE **)(a1 + 16);
    if ( (v31 - a2) >> 3 >= v12 )
    {
      memmove_s(*(void *const *)(a1 + 16), 8u, v31 - 8, 8u);
      *(_QWORD *)(a1 + 16) = v31 + 8;
      v34 = (v31 - a2 - 8) >> 3;
      if ( v34 > 0 )
        memmove_s(&v31[-8 * v34], 8 * v34, a2, 8 * v34);
      v33 = a2 + 8;
    }
    else
    {
      v32 = v12 - ((v31 - a2) >> 3);
      if ( v32 )
        memset64(v31, (unsigned __int64)v6, v32);
      v33 = *(char **)(a1 + 16);
      *(_QWORD *)(a1 + 16) = v33 + 8;
    }
    return std::fill<CXdsReferenceInput * *,CXdsReferenceInput *>(a2, v33, &v36);
  }
  else
  {
    v14 = 0;
    if ( v13 - (v10 >> 1) >= v10 )
      v14 = v10 + (v10 >> 1);
    v15 = std::vector<CXdsReferenceInput *>::size(v11, v10);
    if ( v14 < v18 + v15 )
    {
      v19 = std::vector<CXdsReferenceInput *>::size(v17, v16);
      v14 = v20 + v19;
    }
    if ( v14 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 8 )
      {
        v36 = 0;
        exception::exception((exception *)pExceptionObject, (const char *const *)&v36);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      v21 = v14;
    }
    else
    {
      v21 = 0;
    }
    v22 = (char *)MmAllocate(8 * v21);
    v23 = v22;
    v36 = v22;
    try
    {
      v24 = *(_BYTE **)(a1 + 8);
      v25 = (a2 - v24) >> 3;
      v26 = 8 * v25;
      if ( v25 )
        memmove_s(v22, 8 * v25, v24, 8 * v25);
      *(_QWORD *)&v23[v26] = v6;
      v27 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 3;
      if ( v27 )
        memmove_s(&v23[v26 + 8], 8 * v27, a2, 8 * v27);
    }
    catch ( ... )
    {
      free(v36);
      throw;
    }
    v28 = std::vector<CXdsReferenceInput *>::size(a1, v27);
    v29 = *(void **)(a1 + 8);
    if ( v29 )
      free(v29);
    *(_QWORD *)(a1 + 24) = &v23[8 * v14];
    result = (__int64)&v23[8 * v28 + 8];
    *(_QWORD *)(a1 + 16) = result;
    *(_QWORD *)(a1 + 8) = v23;
  }
  return result;
}

```

## disassembly

```asm
0x180019f98  mov     rax, rsp
0x180019f9b  mov     [rax+18h], r8
0x180019f9f  push    rbx
0x180019fa0  push    rsi
0x180019fa1  push    rdi
0x180019fa2  push    r12
0x180019fa4  push    r14
0x180019fa6  push    r15
0x180019fa8  sub     rsp, 48h
0x180019fac  mov     rbx, rdx
0x180019faf  mov     rsi, rcx
0x180019fb2  mov     r12, [r9]
0x180019fb5  mov     [rax+18h], r12
0x180019fb9  cmp     qword ptr [rcx+8], 0
0x180019fbe  jnz     short loc_180019FC4
0x180019fc0  xor     edx, edx
0x180019fc2  jmp     short loc_180019FD0
0x180019fc4  mov     rdx, [rcx+18h]
0x180019fc8  sub     rdx, [rcx+8]
0x180019fcc  sar     rdx, 3
0x180019fd0  call    ?size@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceInput *>::size(void)
0x180019fd5  mov     r9, 1FFFFFFFFFFFFFFFh
0x180019fdf  mov     rcx, r9
0x180019fe2  sub     rcx, rax
0x180019fe5  mov     r8d, 1
0x180019feb  cmp     rcx, r8
0x180019fee  jnb     short loc_180019FF6
0x180019ff0  call    ?_Xlen@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@KAXXZ; std::vector<CXdsReferenceInput *>::_Xlen(void)
0x180019ff6  mov     rcx, rsi
0x180019ff9  call    ?size@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceInput *>::size(void)
0x180019ffe  add     rax, r8
0x18001a001  cmp     rdx, rax
0x18001a004  jnb     loc_18001A12F
0x18001a00a  mov     rax, rdx
0x18001a00d  shr     rax, 1
0x18001a010  sub     r9, rax
0x18001a013  add     rax, rdx
0x18001a016  xor     edi, edi
0x18001a018  cmp     r9, rdx
0x18001a01b  cmovnb  rdi, rax
0x18001a01f  call    ?size@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceInput *>::size(void)
0x18001a024  add     rax, r8
0x18001a027  cmp     rdi, rax
0x18001a02a  jnb     short loc_18001A035
0x18001a02c  call    ?size@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceInput *>::size(void)
0x18001a031  lea     rdi, [r8+rax]
0x18001a035  test    rdi, rdi
0x18001a038  jnz     short loc_18001A03E
0x18001a03a  xor     ecx, ecx
0x18001a03c  jmp     short loc_18001A08D
0x18001a03e  xor     edx, edx
0x18001a040  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a044  div     rdi
0x18001a047  cmp     rax, 8
0x18001a04b  jnb     short loc_18001A08A
0x18001a04d  mov     [rsp+78h+arg_10], 0
0x18001a059  lea     rdx, [rsp+78h+arg_10]
0x18001a061  lea     rcx, [rsp+78h+pExceptionObject]
0x18001a066  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001a06c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001a073  mov     [rsp+78h+pExceptionObject], rax
0x18001a078  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a07f  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001a084  call    _CxxThrowException_0
0x18001a08a  mov     rcx, rdi
0x18001a08d  shl     rcx, 3; unsigned __int64
0x18001a091  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001a096  mov     r14, rax
0x18001a099  mov     [rsp+78h+arg_10], rax
0x18001a0a1  mov     r8, [rsi+8]; Source
0x18001a0a5  mov     rcx, rbx
0x18001a0a8  sub     rcx, r8
0x18001a0ab  sar     rcx, 3
0x18001a0af  lea     r15, ds:0[rcx*8]
0x18001a0b7  test    rcx, rcx
0x18001a0ba  jz      short loc_18001A0CB
0x18001a0bc  mov     r9, r15; SourceSize
0x18001a0bf  mov     rdx, r15; DestinationSize
0x18001a0c2  mov     rcx, rax; Destination
0x18001a0c5  call    cs:__imp_memmove_s
0x18001a0cb  mov     [r15+r14], r12
0x18001a0cf  mov     rdx, [rsi+10h]
0x18001a0d3  sub     rdx, rbx
0x18001a0d6  sar     rdx, 3
0x18001a0da  test    rdx, rdx
0x18001a0dd  jz      short loc_18001A0F7
0x18001a0df  shl     rdx, 3; DestinationSize
0x18001a0e3  lea     rcx, [r15+8]
0x18001a0e7  add     rcx, r14; Destination
0x18001a0ea  mov     r9, rdx; SourceSize
0x18001a0ed  mov     r8, rbx; Source
0x18001a0f0  call    cs:__imp_memmove_s
0x18001a0f6  nop
0x18001a0f7  mov     rcx, rsi
0x18001a0fa  call    ?size@?$vector@PEAVCXdsReferenceInput@@V?$allocator@PEAVCXdsReferenceInput@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceInput *>::size(void)
0x18001a0ff  mov     rbx, rax
0x18001a102  mov     rcx, [rsi+8]; Block
0x18001a106  test    rcx, rcx
0x18001a109  jz      short loc_18001A112
0x18001a10b  call    cs:__imp_free
0x18001a111  nop
0x18001a112  lea     rax, [r14+rdi*8]
0x18001a116  mov     [rsi+18h], rax
0x18001a11a  lea     rax, [rbx+1]
0x18001a11e  lea     rax, [r14+rax*8]
0x18001a122  mov     [rsi+10h], rax
0x18001a126  mov     [rsi+8], r14
0x18001a12a  jmp     loc_18001A1BF
0x18001a12f  mov     rdi, [rsi+10h]
0x18001a133  mov     r14, rdi
0x18001a136  sub     r14, rbx
0x18001a139  mov     rax, r14
0x18001a13c  sar     rax, 3
0x18001a140  cmp     rax, r8
0x18001a143  jnb     short loc_18001A16B
0x18001a145  mov     rdx, rdi
0x18001a148  sub     rdx, rbx
0x18001a14b  sar     rdx, 3
0x18001a14f  sub     r8, rdx
0x18001a152  jz      short loc_18001A15D
0x18001a154  mov     rax, r12
0x18001a157  mov     rcx, r8
0x18001a15a  rep stosq
0x18001a15d  mov     rdx, [rsi+10h]
0x18001a161  lea     rax, [rdx+8]
0x18001a165  mov     [rsi+10h], rax
0x18001a169  jmp     short loc_18001A1AF
0x18001a16b  lea     r8, [rdi-8]; Source
0x18001a16f  mov     edx, 8; DestinationSize
0x18001a174  mov     r9d, edx; SourceSize
0x18001a177  mov     rcx, rdi; Destination
0x18001a17a  call    cs:__imp_memmove_s
0x18001a180  lea     rax, [rdi+8]
0x18001a184  mov     [rsi+10h], rax
0x18001a188  lea     rdx, [r14-8]
0x18001a18c  sar     rdx, 3
0x18001a190  test    rdx, rdx
0x18001a193  jle     short loc_18001A1AB
0x18001a195  shl     rdx, 3; DestinationSize
0x18001a199  sub     rdi, rdx
0x18001a19c  mov     r9, rdx; SourceSize
0x18001a19f  mov     r8, rbx; Source
0x18001a1a2  mov     rcx, rdi; Destination
0x18001a1a5  call    cs:__imp_memmove_s
0x18001a1ab  lea     rdx, [rbx+8]
0x18001a1af  lea     r8, [rsp+78h+arg_10]
0x18001a1b7  mov     rcx, rbx
0x18001a1ba  call    ??$fill@PEAPEAVCXdsReferenceInput@@PEAV1@@std@@YAXPEAPEAVCXdsReferenceInput@@0AEBQEAV1@@Z; std::fill<CXdsReferenceInput * *,CXdsReferenceInput *>(CXdsReferenceInput * *,CXdsReferenceInput * *,CXdsReferenceInput * const &)
0x18001a1bf  add     rsp, 48h
0x18001a1c3  pop     r15
0x18001a1c5  pop     r14
0x18001a1c7  pop     r12
0x18001a1c9  pop     rdi
0x18001a1ca  pop     rsi
0x18001a1cb  pop     rbx
0x18001a1cc  retn
```
