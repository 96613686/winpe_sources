# _AfxCompareSafeArrays(tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x180278984`
- end: `0x180278c8b`
- name: `?_AfxCompareSafeArrays@@YAHPEAUtagSAFEARRAY@@0@Z`
- size: `775`
- prototype: `int __fastcall(tagSAFEARRAY *parray1, tagSAFEARRAY *parray2)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1802792d0`
- `0x18027b690`
- `0x18027b6a0`

## callees

- `0x1800027e0`
- `0x180278960`
- `0x180278984`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180278c13`
- `VCRUNTIME140!memcmp` at `0x180278c13`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278b98`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278ba3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278bae`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278bb7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c44`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c4f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c5a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c63`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278b98`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278ba3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278bae`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278bb7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c44`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c4f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c5a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180278c63`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1802789ba`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1802789c6`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1802789ba`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1802789c6`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1802789e8`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1802789fb`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1802789e8`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1802789fb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180278b39`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180278b63`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180278b39`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180278b63`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180278ae1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180278b0d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180278ae1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180278b0d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180278bdb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180278bf0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180278bdb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180278bf0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180278c21`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180278c31`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180278c21`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180278c31`

## pseudocode

```c
__int64 __fastcall _AfxCompareSafeArrays(tagSAFEARRAY *parray1, tagSAFEARRAY *parray2)
{
  unsigned int v4; // ebx
  unsigned __int64 Dim; // r15
  UINT v6; // eax
  unsigned __int64 v7; // r14
  UINT Elemsize; // r12d
  unsigned __int64 v10; // rax
  int *v11; // r12
  UINT v12; // r13d
  HRESULT LBound; // eax
  HRESULT v14; // eax
  HRESULT UBound; // eax
  HRESULT v16; // eax
  int v17; // edx
  __int64 v18; // r14
  HRESULT v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // eax
  int *Block; // [rsp+20h] [rbp-A8h]
  int *v26; // [rsp+28h] [rbp-A0h]
  int *v27; // [rsp+30h] [rbp-98h]
  void *pData1; // [rsp+38h] [rbp-90h] BYREF
  void *pData2; // [rsp+40h] [rbp-88h] BYREF
  int *pLBound1; // [rsp+48h] [rbp-80h]
  int *pLBound2; // [rsp+50h] [rbp-78h]
  int *pUBound1; // [rsp+58h] [rbp-70h]
  int *pUBound2; // [rsp+60h] [rbp-68h]
  LONG *v34; // [rsp+68h] [rbp-60h]
  LONG *v35; // [rsp+70h] [rbp-58h]
  LONG *v36; // [rsp+78h] [rbp-50h]
  CException *e; // [rsp+80h] [rbp-48h] BYREF
  UINT v40; // [rsp+E0h] [rbp+18h]
  __int64 v41; // [rsp+E8h] [rbp+20h]
  LONG *v42; // [rsp+E8h] [rbp+20h]

  v4 = 0;
  if ( parray1 && parray2 )
  {
    Dim = SafeArrayGetDim(parray1);
    v6 = SafeArrayGetDim(parray2);
    v7 = v6;
    if ( (_DWORD)Dim != v6 )
      return 0;
    if ( !(_DWORD)Dim )
      return 1;
    Elemsize = SafeArrayGetElemsize(parray1);
    v40 = Elemsize;
    if ( Elemsize != SafeArrayGetElemsize(parray2) )
      return 0;
    pLBound1 = 0;
    pLBound2 = 0;
    pUBound1 = 0;
    pUBound2 = 0;
    pData1 = 0;
    pData2 = 0;
    v10 = 4 * Dim;
    if ( !is_mul_ok(Dim, 4u) )
      v10 = -1;
    try
    {
      Block = (int *)operator new(v10);
      pLBound1 = Block;
      v26 = (int *)operator new(saturated_mul(v7, 4u));
      pLBound2 = v26;
      v27 = (int *)operator new(saturated_mul(Dim, 4u));
      pUBound1 = v27;
      v11 = (int *)operator new(saturated_mul(v7, 4u));
      pUBound2 = v11;
      v18 = 1;
      v12 = 0;
    }
    catch ( CException *e )
    {
      operator delete(pLBound1);
      operator delete(pLBound2);
      operator delete(pUBound1);
      operator delete(pUBound2);
      if ( pData1 )
      {
        v23 = SafeArrayUnaccessData(parray1);
        AfxCheckError(v23);
      }
      if ( pData2 )
      {
        v24 = SafeArrayUnaccessData(parray2);
        AfxCheckError(v24);
      }
      throw;
    }
    while ( v12 < (unsigned int)Dim )
    {
      v41 = v12;
      v35 = &Block[v12++];
      LBound = SafeArrayGetLBound(parray1, v12, v35);
      AfxCheckError(LBound);
      v36 = &v26[v41];
      v14 = SafeArrayGetLBound(parray2, v12, v36);
      AfxCheckError(v14);
      v34 = &v27[v41];
      UBound = SafeArrayGetUBound(parray1, v12, v34);
      AfxCheckError(UBound);
      v42 = &v11[v41];
      v16 = SafeArrayGetUBound(parray2, v12, v42);
      AfxCheckError(v16);
      v17 = *v34 - *v35;
      if ( v17 != *v42 - *v36 )
      {
        free(Block);
        free(v26);
        free(v27);
        free(v11);
        return 0;
      }
      v18 *= v17 + 1;
    }
    v19 = SafeArrayAccessData(parray1, &pData1);
    AfxCheckError(v19);
    v20 = SafeArrayAccessData(parray2, &pData2);
    AfxCheckError(v20);
    LOBYTE(v4) = memcmp(pData1, pData2, v18 * v40) == 0;
    v21 = SafeArrayUnaccessData(parray1);
    AfxCheckError(v21);
    v22 = SafeArrayUnaccessData(parray2);
    AfxCheckError(v22);
    free(Block);
    free(v26);
    free(v27);
    free(v11);
  }
  else
  {
    LOBYTE(v4) = parray1 == parray2;
  }
  return v4;
}

```

## disassembly

```asm
0x180278984  mov     [rsp+arg_8], parray2
0x180278989  mov     [rsp+arg_0], parray1
0x18027898e  push    rbx
0x18027898f  push    rsi
0x180278990  push    rdi
0x180278991  push    r12
0x180278993  push    r13
0x180278995  push    r14
0x180278997  push    r15
0x180278999  sub     rsp, 90h
0x1802789a0  mov     rdi, parray2
0x1802789a3  mov     rsi, parray1
0x1802789a6  xor     ebx, ebx
0x1802789a8  test    parray1, parray1
0x1802789ab  jz      loc_180278C6F
0x1802789b1  test    parray2, parray2
0x1802789b4  jz      loc_180278C6F
0x1802789ba  call    cs:__imp_SafeArrayGetDim
0x1802789c0  mov     r15d, eax
0x1802789c3  mov     parray1, rdi; psa
0x1802789c6  call    cs:__imp_SafeArrayGetDim
0x1802789cc  mov     r14d, eax
0x1802789cf  cmp     r15d, eax
0x1802789d2  jnz     loc_180278C6B
0x1802789d8  test    r15d, r15d
0x1802789db  jnz     short loc_1802789E5
0x1802789dd  lea     eax, [rbx+1]
0x1802789e0  jmp     loc_180278C77
0x1802789e5  mov     parray1, rsi; psa
0x1802789e8  call    cs:__imp_SafeArrayGetElemsize
0x1802789ee  mov     r12d, eax
0x1802789f1  mov     [rsp+0C8h+arg_10], eax
0x1802789f8  mov     parray1, rdi; psa
0x1802789fb  call    cs:__imp_SafeArrayGetElemsize
0x180278a01  cmp     r12d, eax
0x180278a04  jnz     loc_180278C6B
0x180278a0a  mov     [rsp+0C8h+pLBound1], rbx
0x180278a0f  mov     [rsp+0C8h+pLBound2], rbx
0x180278a14  mov     [rsp+0C8h+pUBound1], rbx
0x180278a19  mov     [rsp+0C8h+pUBound2], rbx
0x180278a1e  mov     [rsp+0C8h+pData1], rbx
0x180278a23  mov     [rsp+0C8h+pData2], rbx
0x180278a28  mov     r12, r15
0x180278a2b  mov     r13d, 4
0x180278a31  mov     eax, r13d
0x180278a34  mul     r15
0x180278a37  lea     parray1, [r13-5]
0x180278a3b  cmovb   rax, parray1
0x180278a3f  mov     parray1, rax; nSize
0x180278a42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180278a47  mov     [rsp+0C8h+Block], rax
0x180278a4c  mov     [rsp+0C8h+pLBound1], rax
0x180278a51  mov     eax, r13d
0x180278a54  mul     r14
0x180278a57  lea     parray1, [r13-5]
0x180278a5b  cmovb   rax, parray1
0x180278a5f  mov     parray1, rax; nSize
0x180278a62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180278a67  mov     [rsp+0C8h+var_A0], rax
0x180278a6c  mov     [rsp+0C8h+pLBound2], rax
0x180278a71  mov     eax, r13d
0x180278a74  mul     r12
0x180278a77  lea     r12, [r13-5]
0x180278a7b  cmovb   rax, r12
0x180278a7f  mov     parray1, rax; nSize
0x180278a82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180278a87  mov     [rsp+0C8h+var_98], rax
0x180278a8c  mov     [rsp+0C8h+pUBound1], rax
0x180278a91  mov     eax, r13d
0x180278a94  mul     r14
0x180278a97  cmovb   rax, r12
0x180278a9b  mov     parray1, rax; nSize
0x180278a9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180278aa3  mov     r12, rax
0x180278aa6  mov     [rsp+0C8h+pUBound2], rax
0x180278aab  lea     r14d, [r13-3]
0x180278aaf  mov     r13d, ebx
0x180278ab2  cmp     r13d, r15d
0x180278ab5  jnb     loc_180278BD3
0x180278abb  mov     ecx, r13d
0x180278abe  mov     [rsp+0C8h+arg_18], parray1
0x180278ac6  mov     rax, [rsp+0C8h+Block]
0x180278acb  lea     rax, [rax+parray1*4]
0x180278acf  mov     [rsp+0C8h+var_58], rax
0x180278ad4  lea     edx, [r13+1]; nDim
0x180278ad8  mov     r13d, edx
0x180278adb  mov     r8, rax; plLbound
0x180278ade  mov     parray1, rsi; psa
0x180278ae1  call    cs:__imp_SafeArrayGetLBound
0x180278ae7  mov     ecx, eax; sc
0x180278ae9  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278aee  mov     rax, [rsp+0C8h+var_A0]
0x180278af3  mov     parray1, [rsp+0C8h+arg_18]
0x180278afb  lea     rax, [rax+parray1*4]
0x180278aff  mov     [rsp+0C8h+var_50], rax
0x180278b04  mov     r8, rax; plLbound
0x180278b07  mov     edx, r13d; nDim
0x180278b0a  mov     parray1, rdi; psa
0x180278b0d  call    cs:__imp_SafeArrayGetLBound
0x180278b13  mov     ecx, eax; sc
0x180278b15  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278b1a  mov     rax, [rsp+0C8h+var_98]
0x180278b1f  mov     parray1, [rsp+0C8h+arg_18]
0x180278b27  lea     rax, [rax+parray1*4]
0x180278b2b  mov     [rsp+0C8h+var_60], rax
0x180278b30  mov     r8, rax; plUbound
0x180278b33  mov     edx, r13d; nDim
0x180278b36  mov     parray1, rsi; psa
0x180278b39  call    cs:__imp_SafeArrayGetUBound
0x180278b3f  mov     ecx, eax; sc
0x180278b41  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278b46  mov     rax, [rsp+0C8h+arg_18]
0x180278b4e  lea     rax, [r12+rax*4]
0x180278b52  mov     [rsp+0C8h+arg_18], rax
0x180278b5a  mov     r8, rax; plUbound
0x180278b5d  mov     edx, r13d; nDim
0x180278b60  mov     parray1, rdi; psa
0x180278b63  call    cs:__imp_SafeArrayGetUBound
0x180278b69  mov     ecx, eax; sc
0x180278b6b  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278b70  mov     parray2, [rsp+0C8h+var_60]
0x180278b75  mov     edx, [parray2]
0x180278b77  mov     rax, [rsp+0C8h+var_58]
0x180278b7c  sub     edx, [rax]
0x180278b7e  mov     rax, [rsp+0C8h+arg_18]
0x180278b86  mov     eax, [rax]
0x180278b88  mov     parray1, [rsp+0C8h+var_50]
0x180278b8d  sub     eax, [parray1]
0x180278b8f  cmp     edx, eax
0x180278b91  jz      short loc_180278BC4
0x180278b93  mov     parray1, [rsp+0C8h+Block]; Block
0x180278b98  call    cs:__imp_free
0x180278b9e  mov     parray1, [rsp+0C8h+var_A0]; Block
0x180278ba3  call    cs:__imp_free
0x180278ba9  mov     parray1, [rsp+0C8h+var_98]; Block
0x180278bae  call    cs:__imp_free
0x180278bb4  mov     parray1, r12; Block
0x180278bb7  call    cs:__imp_free
0x180278bbd  xor     eax, eax
0x180278bbf  jmp     loc_180278C77
0x180278bc4  lea     eax, [parray2+1]
0x180278bc7  movsxd  parray1, eax
0x180278bca  imul    r14, parray1
0x180278bce  jmp     loc_180278AB2
0x180278bd3  lea     parray2, [rsp+0C8h+pData1]; ppvData
0x180278bd8  mov     parray1, rsi; psa
0x180278bdb  call    cs:__imp_SafeArrayAccessData
0x180278be1  mov     ecx, eax; sc
0x180278be3  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278be8  lea     parray2, [rsp+0C8h+pData2]; ppvData
0x180278bed  mov     parray1, rdi; psa
0x180278bf0  call    cs:__imp_SafeArrayAccessData
0x180278bf6  mov     ecx, eax; sc
0x180278bf8  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278bfd  mov     r8d, [rsp+0C8h+arg_10]
0x180278c05  imul    r8, r14; Size
0x180278c09  mov     parray2, [rsp+0C8h+pData2]; Buf2
0x180278c0e  mov     parray1, [rsp+0C8h+pData1]; Buf1
0x180278c13  call    cs:__imp_memcmp
0x180278c19  test    eax, eax
0x180278c1b  setz    bl
0x180278c1e  mov     parray1, rsi; psa
0x180278c21  call    cs:__imp_SafeArrayUnaccessData
0x180278c27  mov     ecx, eax; sc
0x180278c29  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278c2e  mov     parray1, rdi; psa
0x180278c31  call    cs:__imp_SafeArrayUnaccessData
0x180278c37  mov     ecx, eax; sc
0x180278c39  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180278c3e  nop
0x180278c3f  mov     parray1, [rsp+0C8h+Block]; Block
0x180278c44  call    cs:__imp_free
0x180278c4a  mov     parray1, [rsp+0C8h+var_A0]; Block
0x180278c4f  call    cs:__imp_free
0x180278c55  mov     parray1, [rsp+0C8h+var_98]; Block
0x180278c5a  call    cs:__imp_free
0x180278c60  mov     parray1, r12; Block
0x180278c63  call    cs:__imp_free
0x180278c69  jmp     short loc_180278C75
0x180278c6b  xor     eax, eax
0x180278c6d  jmp     short loc_180278C77
0x180278c6f  cmp     rsi, rdi
0x180278c72  setz    bl
0x180278c75  mov     eax, ebx
0x180278c77  add     rsp, 90h
0x180278c7e  pop     r15
0x180278c80  pop     r14
0x180278c82  pop     r13
0x180278c84  pop     r12
0x180278c86  pop     rdi
0x180278c87  pop     rsi
0x180278c88  pop     rbx
0x180278c89  retn
```
