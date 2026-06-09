# _VariantArrayToStringAlloc(tagVARIANT const &,ushort * *)

- ea: `0x1800344e8`
- end: `0x1800347d2`
- name: `?_VariantArrayToStringAlloc@@YAJAEBUtagVARIANT@@PEAPEAG@Z`
- size: `746`
- prototype: `__int64 __fastcall(VARIANT *varIn, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ca30`
- `0x18002b3d4`
- `0x180033210`

## callees

- `0x18002b9e8`
- `0x180033210`
- `0x180033310`
- `0x1800335a0`
- `0x1800344e8`
- `0x1800480e8`
- `0x180052c58`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800346be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003477c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800347ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800346be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003477c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800347ca`
- `OLEAUT32!__imp_VariantClear` at `0x180034786`
- `OLEAUT32!__imp_VariantClear` at `0x180034786`

## pseudocode

```c
__int64 __fastcall _VariantArrayToStringAlloc(VARIANT *varIn, unsigned __int16 **a2)
{
  __int64 v4; // rcx
  HRESULT Count; // ebx
  unsigned __int16 *v6; // r9
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  bool v14; // zf
  struct tagSAFEARRAY *v15; // rcx
  unsigned int v16; // esi
  __int64 v17; // rdi
  _QWORD *v18; // r14
  const unsigned __int16 *v19; // r8
  struct tagSAFEARRAY *parray; // rcx
  unsigned int v21; // esi
  __int64 v22; // rdi
  const VARIANT *v23; // r14
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  ULONG v29; // esi
  ULONG v30; // edi
  unsigned int v32; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 *v33; // [rsp+28h] [rbp-38h] BYREF
  void *v34; // [rsp+30h] [rbp-30h] BYREF
  PWSTR ppszBuf; // [rsp+38h] [rbp-28h] BYREF
  VARIANT pvar; // [rsp+40h] [rbp-20h] BYREF

  *a2 = 0;
  LODWORD(ppszBuf) = 0;
  Count = SafeArrayGetCount(varIn->parray, (unsigned int *)&ppszBuf);
  if ( Count >= 0 )
  {
    v33 = 0;
    v32 = 260;
    Count = _AllocArray<unsigned short,CTCoAllocPolicy>(v4, 1, 260, &v33);
    if ( Count >= 0 )
    {
      v6 = v33;
      *v33 = 0;
      v7 = varIn->vt & 0xDFFF;
      if ( v7 <= 0xC )
      {
        if ( v7 == 12 )
        {
          parray = varIn->parray;
          v34 = 0;
          Count = SafeArrayFastAccessData(parray, &v34);
          if ( Count >= 0 )
          {
            v21 = (unsigned int)ppszBuf;
            v22 = 0;
            if ( (_DWORD)ppszBuf )
            {
              v23 = (const VARIANT *)v34;
              while ( Count >= 0 )
              {
                ppszBuf = 0;
                Count = VariantToStringAlloc(&v23[v22], &ppszBuf);
                if ( Count >= 0 )
                {
                  Count = _StringCchCatRealloc(&v33, &v32, ppszBuf);
                  if ( (_DWORD)v22 != v21 - 1 )
                    Count = _StringCchCatRealloc(&v33, &v32, L"; ");
                  CoTaskMemFree(ppszBuf);
                }
                v22 = (unsigned int)(v22 + 1);
                if ( (unsigned int)v22 >= v21 )
                {
LABEL_49:
                  if ( Count < 0 )
                    goto LABEL_53;
                  v6 = v33;
                  goto LABEL_51;
                }
              }
              goto LABEL_53;
            }
LABEL_51:
            *a2 = v6;
            return (unsigned int)Count;
          }
        }
        else
        {
          v8 = v7 - 2;
          if ( !v8 )
            goto LABEL_40;
          v9 = v8 - 1;
          if ( !v9 )
            goto LABEL_40;
          v10 = v9 - 1;
          if ( !v10 )
            goto LABEL_40;
          v11 = v10 - 1;
          if ( !v11 )
            goto LABEL_40;
          v12 = v11 - 2;
          if ( !v12 )
            goto LABEL_40;
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 == 3;
            goto LABEL_38;
          }
          v15 = varIn->parray;
          v34 = 0;
          Count = SafeArrayFastAccessData(v15, &v34);
          if ( Count >= 0 )
          {
            v16 = (unsigned int)ppszBuf;
            v17 = 0;
            if ( (_DWORD)ppszBuf )
            {
              v18 = v34;
              while ( Count >= 0 )
              {
                v19 = &Src;
                if ( v18[v17] )
                  v19 = (const unsigned __int16 *)v18[v17];
                Count = _StringCchCatRealloc(&v33, &v32, v19);
                if ( (_DWORD)v17 != v16 - 1 )
                  Count = _StringCchCatRealloc(&v33, &v32, L"; ");
                v17 = (unsigned int)(v17 + 1);
                if ( (unsigned int)v17 >= v16 )
                  goto LABEL_49;
              }
              goto LABEL_53;
            }
            goto LABEL_51;
          }
        }
LABEL_54:
        CoTaskMemFree(v6);
        return (unsigned int)Count;
      }
      v24 = v7 - 16;
      if ( !v24 )
        goto LABEL_40;
      v25 = v24 - 1;
      if ( !v25 )
        goto LABEL_40;
      v26 = v25 - 1;
      if ( !v26 )
        goto LABEL_40;
      v27 = v26 - 1;
      if ( !v27 )
        goto LABEL_40;
      v28 = v27 - 1;
      if ( !v28 )
        goto LABEL_40;
      v14 = v28 == 1;
LABEL_38:
      if ( !v14 )
      {
        Count = -2147316576;
        goto LABEL_54;
      }
LABEL_40:
      v29 = (unsigned int)ppszBuf;
      v30 = 0;
      if ( (_DWORD)ppszBuf )
      {
        while ( Count >= 0 )
        {
          memset(&pvar, 0, sizeof(pvar));
          Count = InitVariantFromVariantArrayElem(varIn, v30, &pvar);
          if ( Count >= 0 )
          {
            ppszBuf = 0;
            Count = VariantToStringAlloc(&pvar, &ppszBuf);
            if ( Count >= 0 )
            {
              Count = _StringCchCatRealloc(&v33, &v32, ppszBuf);
              if ( v30 != v29 - 1 )
                Count = _StringCchCatRealloc(&v33, &v32, L"; ");
              CoTaskMemFree(ppszBuf);
            }
            VariantClear(&pvar);
          }
          if ( ++v30 >= v29 )
            goto LABEL_49;
        }
LABEL_53:
        v6 = v33;
        goto LABEL_54;
      }
      goto LABEL_51;
    }
  }
  return (unsigned int)Count;
}

```

## disassembly

```asm
0x1800344e8  mov     [rsp-28h+arg_10], rbx
0x1800344ed  push    rbp
0x1800344ee  push    rsi
0x1800344ef  push    rdi
0x1800344f0  push    r14
0x1800344f2  push    r15
0x1800344f4  mov     rbp, rsp
0x1800344f7  sub     rsp, 60h
0x1800344fb  mov     rax, cs:__security_cookie
0x180034502  xor     rax, rsp
0x180034505  mov     [rbp+var_8], rax
0x180034509  mov     qword ptr [rdx], 0
0x180034510  mov     r15, rdx
0x180034513  mov     r14, rcx
0x180034516  mov     dword ptr [rbp+ppszBuf], 0
0x18003451d  mov     rcx, [rcx+8]; psa
0x180034521  lea     rdx, [rbp+ppszBuf]; unsigned int *
0x180034525  call    ?SafeArrayGetCount@@YAJPEAUtagSAFEARRAY@@PEAK@Z; SafeArrayGetCount(tagSAFEARRAY *,ulong *)
0x18003452a  mov     ebx, eax
0x18003452c  test    eax, eax
0x18003452e  js      loc_1800347A1
0x180034534  mov     r8d, 104h
0x18003453a  mov     [rbp+var_38], 0
0x180034542  lea     r9, [rbp+var_38]
0x180034546  mov     [rbp+var_40], r8d
0x18003454a  mov     edx, 1
0x18003454f  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180034554  mov     ebx, eax
0x180034556  test    eax, eax
0x180034558  js      loc_1800347A1
0x18003455e  mov     r9, [rbp+var_38]
0x180034562  xor     eax, eax
0x180034564  mov     [r9], ax
0x180034568  movzx   ecx, word ptr [r14]
0x18003456c  and     ecx, 0DFFFh
0x180034572  cmp     ecx, 0Ch
0x180034575  ja      loc_1800346CF
0x18003457b  jz      loc_180034637
0x180034581  sub     ecx, 2
0x180034584  jz      loc_1800346F7
0x18003458a  sub     ecx, 1
0x18003458d  jz      loc_1800346F7
0x180034593  sub     ecx, 1
0x180034596  jz      loc_1800346F7
0x18003459c  sub     ecx, 1
0x18003459f  jz      loc_1800346F7
0x1800345a5  sub     ecx, 2
0x1800345a8  jz      loc_1800346F7
0x1800345ae  sub     ecx, 1
0x1800345b1  jz      short loc_1800345BB
0x1800345b3  cmp     ecx, 3
0x1800345b6  jmp     loc_1800346EB
0x1800345bb  mov     rcx, [r14+8]; struct tagSAFEARRAY *
0x1800345bf  lea     rdx, [rbp+var_30]; void **
0x1800345c3  mov     [rbp+var_30], rax
0x1800345c7  call    ?SafeArrayFastAccessData@@YAJPEAUtagSAFEARRAY@@PEAPEAX@Z; SafeArrayFastAccessData(tagSAFEARRAY *,void * *)
0x1800345cc  mov     ebx, eax
0x1800345ce  test    eax, eax
0x1800345d0  js      loc_1800347C7
0x1800345d6  mov     esi, dword ptr [rbp+ppszBuf]
0x1800345d9  xor     edi, edi
0x1800345db  test    esi, esi
0x1800345dd  jz      loc_18003479E
0x1800345e3  mov     r14, [rbp+var_30]
0x1800345e7  test    ebx, ebx
0x1800345e9  js      loc_1800347C3
0x1800345ef  cmp     qword ptr [r14+rdi*8], 0
0x1800345f4  lea     r8, Src
0x1800345fb  lea     rdx, [rbp+var_40]; unsigned int *
0x1800345ff  cmovnz  r8, [r14+rdi*8]; unsigned __int16 *
0x180034604  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180034608  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18003460d  mov     ebx, eax
0x18003460f  lea     eax, [rsi-1]
0x180034612  cmp     edi, eax
0x180034614  jz      short loc_18003462C
0x180034616  lea     r8, asc_1800CD530; "; "
0x18003461d  lea     rdx, [rbp+var_40]; unsigned int *
0x180034621  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180034625  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18003462a  mov     ebx, eax
0x18003462c  inc     edi
0x18003462e  cmp     edi, esi
0x180034630  jb      short loc_1800345E7
0x180034632  jmp     loc_180034796
0x180034637  mov     rcx, [r14+8]; struct tagSAFEARRAY *
0x18003463b  lea     rdx, [rbp+var_30]; void **
0x18003463f  mov     [rbp+var_30], rax
0x180034643  call    ?SafeArrayFastAccessData@@YAJPEAUtagSAFEARRAY@@PEAPEAX@Z; SafeArrayFastAccessData(tagSAFEARRAY *,void * *)
0x180034648  mov     ebx, eax
0x18003464a  test    eax, eax
0x18003464c  js      loc_1800347C7
0x180034652  mov     esi, dword ptr [rbp+ppszBuf]
0x180034655  xor     edi, edi
0x180034657  test    esi, esi
0x180034659  jz      loc_18003479E
0x18003465f  mov     r14, [rbp+var_30]
0x180034663  test    ebx, ebx
0x180034665  js      loc_1800347C3
0x18003466b  lea     rcx, [rdi+rdi*2]
0x18003466f  mov     [rbp+ppszBuf], 0
0x180034677  lea     rcx, [r14+rcx*8]; varIn
0x18003467b  lea     rdx, [rbp+ppszBuf]; ppszBuf
0x18003467f  call    VariantToStringAlloc
0x180034684  mov     ebx, eax
0x180034686  test    eax, eax
0x180034688  js      short loc_1800346C4
0x18003468a  mov     r8, [rbp+ppszBuf]; unsigned __int16 *
0x18003468e  lea     rdx, [rbp+var_40]; unsigned int *
0x180034692  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180034696  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x18003469b  mov     ebx, eax
0x18003469d  lea     eax, [rsi-1]
0x1800346a0  cmp     edi, eax
0x1800346a2  jz      short loc_1800346BA
0x1800346a4  lea     r8, asc_1800CD530; "; "
0x1800346ab  lea     rdx, [rbp+var_40]; unsigned int *
0x1800346af  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x1800346b3  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x1800346b8  mov     ebx, eax
0x1800346ba  mov     rcx, [rbp+ppszBuf]; pv
0x1800346be  call    cs:__imp_CoTaskMemFree
0x1800346c4  inc     edi
0x1800346c6  cmp     edi, esi
0x1800346c8  jb      short loc_180034663
0x1800346ca  jmp     loc_180034796
0x1800346cf  sub     ecx, 10h
0x1800346d2  jz      short loc_1800346F7
0x1800346d4  sub     ecx, 1
0x1800346d7  jz      short loc_1800346F7
0x1800346d9  sub     ecx, 1
0x1800346dc  jz      short loc_1800346F7
0x1800346de  sub     ecx, 1
0x1800346e1  jz      short loc_1800346F7
0x1800346e3  sub     ecx, 1
0x1800346e6  jz      short loc_1800346F7
0x1800346e8  cmp     ecx, 1
0x1800346eb  jz      short loc_1800346F7
0x1800346ed  mov     ebx, 80028CA0h
0x1800346f2  jmp     loc_1800347C7
0x1800346f7  mov     esi, dword ptr [rbp+ppszBuf]
0x1800346fa  xor     edi, edi
0x1800346fc  test    esi, esi
0x1800346fe  jz      loc_18003479E
0x180034704  test    ebx, ebx
0x180034706  js      loc_1800347C3
0x18003470c  xorps   xmm0, xmm0
0x18003470f  lea     r8, [rbp+pvar]; pvar
0x180034713  xor     eax, eax
0x180034715  mov     edx, edi; iElem
0x180034717  mov     rcx, r14; varIn
0x18003471a  mov     qword ptr [rbp+pvar+10h], rax
0x18003471e  movups  xmmword ptr [rbp+pvar], xmm0
0x180034722  call    InitVariantFromVariantArrayElem
0x180034727  mov     ebx, eax
0x180034729  test    eax, eax
0x18003472b  js      short loc_18003478C
0x18003472d  lea     rdx, [rbp+ppszBuf]; ppszBuf
0x180034731  mov     [rbp+ppszBuf], 0
0x180034739  lea     rcx, [rbp+pvar]; varIn
0x18003473d  call    VariantToStringAlloc
0x180034742  mov     ebx, eax
0x180034744  test    eax, eax
0x180034746  js      short loc_180034782
0x180034748  mov     r8, [rbp+ppszBuf]; unsigned __int16 *
0x18003474c  lea     rdx, [rbp+var_40]; unsigned int *
0x180034750  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180034754  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x180034759  mov     ebx, eax
0x18003475b  lea     eax, [rsi-1]
0x18003475e  cmp     edi, eax
0x180034760  jz      short loc_180034778
0x180034762  lea     r8, asc_1800CD530; "; "
0x180034769  lea     rdx, [rbp+var_40]; unsigned int *
0x18003476d  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180034771  call    ?_StringCchCatRealloc@@YAJPEAPEAGPEAKPEBG@Z; _StringCchCatRealloc(ushort * *,ulong *,ushort const *)
0x180034776  mov     ebx, eax
0x180034778  mov     rcx, [rbp+ppszBuf]; pv
0x18003477c  call    cs:__imp_CoTaskMemFree
0x180034782  lea     rcx, [rbp+pvar]; pvarg
0x180034786  call    cs:__imp_VariantClear
0x18003478c  inc     edi
0x18003478e  cmp     edi, esi
0x180034790  jb      loc_180034704
0x180034796  test    ebx, ebx
0x180034798  js      short loc_1800347C3
0x18003479a  mov     r9, [rbp+var_38]
0x18003479e  mov     [r15], r9
0x1800347a1  mov     eax, ebx
0x1800347a3  mov     rcx, [rbp+var_8]
0x1800347a7  xor     rcx, rsp; StackCookie
0x1800347aa  call    __security_check_cookie
0x1800347af  mov     rbx, [rsp+60h+arg_10]
0x1800347b7  add     rsp, 60h
0x1800347bb  pop     r15
0x1800347bd  pop     r14
0x1800347bf  pop     rdi
0x1800347c0  pop     rsi
0x1800347c1  pop     rbp
0x1800347c2  retn
0x1800347c3  mov     r9, [rbp+var_38]
0x1800347c7  mov     rcx, r9; pv
0x1800347ca  call    cs:__imp_CoTaskMemFree
0x1800347d0  jmp     short loc_1800347A1
```
