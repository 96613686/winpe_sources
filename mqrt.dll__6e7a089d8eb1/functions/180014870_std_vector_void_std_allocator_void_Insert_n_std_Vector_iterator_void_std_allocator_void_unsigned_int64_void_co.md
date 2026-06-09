# std::vector<void *,std::allocator<void *>>::_Insert_n(std::_Vector_iterator<void *,std::allocator<void *>>,unsigned __int64,void * const &)

- ea: `0x180014870`
- end: `0x180014aa5`
- name: `?_Insert_n@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEAAXV?$_Vector_iterator@PEAXV?$allocator@PEAX@std@@@2@_KAEBQEAX@Z`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013448`

## callees

- `0x1800022d6`
- `0x180012f34`
- `0x180014870`
- `0x180014b9c`
- `0x180014dd4`
- `0x180021010`

## import_xrefs

- `msvcrt!free` at `0x1800149e3`
- `msvcrt!free` at `0x1800149e3`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001493e`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001493e`
- `msvcrt!memmove_s` at `0x18001499d`
- `msvcrt!memmove_s` at `0x1800149c8`
- `msvcrt!memmove_s` at `0x180014a52`
- `msvcrt!memmove_s` at `0x180014a7d`
- `msvcrt!memmove_s` at `0x18001499d`
- `msvcrt!memmove_s` at `0x1800149c8`
- `msvcrt!memmove_s` at `0x180014a52`
- `msvcrt!memmove_s` at `0x180014a7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::vector<void *>::_Insert_n(__int64 a1, char *a2, const char *a3, const char **a4)
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
  if ( std::vector<void *>::size(a1, v7) == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<void *>::_Xlen();
  v9 = std::vector<void *>::size(a1, v8);
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
    return std::fill<void * *,void *>(a2, v33, &v36);
  }
  else
  {
    v14 = 0;
    if ( v13 - (v10 >> 1) >= v10 )
      v14 = v10 + (v10 >> 1);
    v15 = std::vector<void *>::size(v11, v10);
    if ( v14 < v18 + v15 )
    {
      v19 = std::vector<void *>::size(v17, v16);
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
    v28 = std::vector<void *>::size(a1, v27);
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
0x180014870  mov     rax, rsp
0x180014873  mov     [rax+18h], r8
0x180014877  push    rbx
0x180014878  push    rsi
0x180014879  push    rdi
0x18001487a  push    r12
0x18001487c  push    r14
0x18001487e  push    r15
0x180014880  sub     rsp, 48h
0x180014884  mov     rbx, rdx
0x180014887  mov     rsi, rcx
0x18001488a  mov     r12, [r9]
0x18001488d  mov     [rax+18h], r12
0x180014891  cmp     qword ptr [rcx+8], 0
0x180014896  jnz     short loc_18001489C
0x180014898  xor     edx, edx
0x18001489a  jmp     short loc_1800148A8
0x18001489c  mov     rdx, [rcx+18h]
0x1800148a0  sub     rdx, [rcx+8]
0x1800148a4  sar     rdx, 3
0x1800148a8  call    ?size@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEBA_KXZ; std::vector<void *>::size(void)
0x1800148ad  mov     r9, 1FFFFFFFFFFFFFFFh
0x1800148b7  mov     rcx, r9
0x1800148ba  sub     rcx, rax
0x1800148bd  mov     r8d, 1
0x1800148c3  cmp     rcx, r8
0x1800148c6  jnb     short loc_1800148CE
0x1800148c8  call    ?_Xlen@?$vector@PEAXV?$allocator@PEAX@std@@@std@@KAXXZ; std::vector<void *>::_Xlen(void)
0x1800148ce  mov     rcx, rsi
0x1800148d1  call    ?size@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEBA_KXZ; std::vector<void *>::size(void)
0x1800148d6  add     rax, r8
0x1800148d9  cmp     rdx, rax
0x1800148dc  jnb     loc_180014A07
0x1800148e2  mov     rax, rdx
0x1800148e5  shr     rax, 1
0x1800148e8  sub     r9, rax
0x1800148eb  add     rax, rdx
0x1800148ee  xor     edi, edi
0x1800148f0  cmp     r9, rdx
0x1800148f3  cmovnb  rdi, rax
0x1800148f7  call    ?size@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEBA_KXZ; std::vector<void *>::size(void)
0x1800148fc  add     rax, r8
0x1800148ff  cmp     rdi, rax
0x180014902  jnb     short loc_18001490D
0x180014904  call    ?size@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEBA_KXZ; std::vector<void *>::size(void)
0x180014909  lea     rdi, [r8+rax]
0x18001490d  test    rdi, rdi
0x180014910  jnz     short loc_180014916
0x180014912  xor     ecx, ecx
0x180014914  jmp     short loc_180014965
0x180014916  xor     edx, edx
0x180014918  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001491c  div     rdi
0x18001491f  cmp     rax, 8
0x180014923  jnb     short loc_180014962
0x180014925  mov     [rsp+78h+arg_10], 0
0x180014931  lea     rdx, [rsp+78h+arg_10]
0x180014939  lea     rcx, [rsp+78h+pExceptionObject]
0x18001493e  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180014944  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001494b  mov     [rsp+78h+pExceptionObject], rax
0x180014950  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180014957  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001495c  call    _CxxThrowException_0
0x180014962  mov     rcx, rdi
0x180014965  shl     rcx, 3; unsigned __int64
0x180014969  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001496e  mov     r14, rax
0x180014971  mov     [rsp+78h+arg_10], rax
0x180014979  mov     r8, [rsi+8]; Source
0x18001497d  mov     rcx, rbx
0x180014980  sub     rcx, r8
0x180014983  sar     rcx, 3
0x180014987  lea     r15, ds:0[rcx*8]
0x18001498f  test    rcx, rcx
0x180014992  jz      short loc_1800149A3
0x180014994  mov     r9, r15; SourceSize
0x180014997  mov     rdx, r15; DestinationSize
0x18001499a  mov     rcx, rax; Destination
0x18001499d  call    cs:__imp_memmove_s
0x1800149a3  mov     [r15+r14], r12
0x1800149a7  mov     rdx, [rsi+10h]
0x1800149ab  sub     rdx, rbx
0x1800149ae  sar     rdx, 3
0x1800149b2  test    rdx, rdx
0x1800149b5  jz      short loc_1800149CF
0x1800149b7  shl     rdx, 3; DestinationSize
0x1800149bb  lea     rcx, [r15+8]
0x1800149bf  add     rcx, r14; Destination
0x1800149c2  mov     r9, rdx; SourceSize
0x1800149c5  mov     r8, rbx; Source
0x1800149c8  call    cs:__imp_memmove_s
0x1800149ce  nop
0x1800149cf  mov     rcx, rsi
0x1800149d2  call    ?size@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEBA_KXZ; std::vector<void *>::size(void)
0x1800149d7  mov     rbx, rax
0x1800149da  mov     rcx, [rsi+8]; Block
0x1800149de  test    rcx, rcx
0x1800149e1  jz      short loc_1800149EA
0x1800149e3  call    cs:__imp_free
0x1800149e9  nop
0x1800149ea  lea     rax, [r14+rdi*8]
0x1800149ee  mov     [rsi+18h], rax
0x1800149f2  lea     rax, [rbx+1]
0x1800149f6  lea     rax, [r14+rax*8]
0x1800149fa  mov     [rsi+10h], rax
0x1800149fe  mov     [rsi+8], r14
0x180014a02  jmp     loc_180014A97
0x180014a07  mov     rdi, [rsi+10h]
0x180014a0b  mov     r14, rdi
0x180014a0e  sub     r14, rbx
0x180014a11  mov     rax, r14
0x180014a14  sar     rax, 3
0x180014a18  cmp     rax, r8
0x180014a1b  jnb     short loc_180014A43
0x180014a1d  mov     rdx, rdi
0x180014a20  sub     rdx, rbx
0x180014a23  sar     rdx, 3
0x180014a27  sub     r8, rdx
0x180014a2a  jz      short loc_180014A35
0x180014a2c  mov     rax, r12
0x180014a2f  mov     rcx, r8
0x180014a32  rep stosq
0x180014a35  mov     rdx, [rsi+10h]
0x180014a39  lea     rax, [rdx+8]
0x180014a3d  mov     [rsi+10h], rax
0x180014a41  jmp     short loc_180014A87
0x180014a43  lea     r8, [rdi-8]; Source
0x180014a47  mov     edx, 8; DestinationSize
0x180014a4c  mov     r9d, edx; SourceSize
0x180014a4f  mov     rcx, rdi; Destination
0x180014a52  call    cs:__imp_memmove_s
0x180014a58  lea     rax, [rdi+8]
0x180014a5c  mov     [rsi+10h], rax
0x180014a60  lea     rdx, [r14-8]
0x180014a64  sar     rdx, 3
0x180014a68  test    rdx, rdx
0x180014a6b  jle     short loc_180014A83
0x180014a6d  shl     rdx, 3; DestinationSize
0x180014a71  sub     rdi, rdx
0x180014a74  mov     r9, rdx; SourceSize
0x180014a77  mov     r8, rbx; Source
0x180014a7a  mov     rcx, rdi; Destination
0x180014a7d  call    cs:__imp_memmove_s
0x180014a83  lea     rdx, [rbx+8]
0x180014a87  lea     r8, [rsp+78h+arg_10]
0x180014a8f  mov     rcx, rbx
0x180014a92  call    ??$fill@PEAPEAXPEAX@std@@YAXPEAPEAX0AEBQEAX@Z; std::fill<void * *,void *>(void * *,void * *,void * const &)
0x180014a97  add     rsp, 48h
0x180014a9b  pop     r15
0x180014a9d  pop     r14
0x180014a9f  pop     r12
0x180014aa1  pop     rdi
0x180014aa2  pop     rsi
0x180014aa3  pop     rbx
0x180014aa4  retn
```
