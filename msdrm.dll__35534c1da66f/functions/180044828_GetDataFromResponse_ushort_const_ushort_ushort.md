# GetDataFromResponse(ushort const *,ushort * *,ushort * *)

- ea: `0x180044828`
- end: `0x1800454e4`
- name: `?GetDataFromResponse@@YAJPEBGPEAPEAG1@Z`
- size: `3260`
- prototype: `__int64 __fastcall(OLECHAR *psz, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180045c78`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180017210`
- `0x180044828`
- `0x180047550`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180044c54`
- `msvcrt!_wcsicmp` at `0x180044deb`
- `msvcrt!_wcsicmp` at `0x180044e97`
- `msvcrt!_wcsicmp` at `0x180044c54`
- `msvcrt!_wcsicmp` at `0x180044deb`
- `msvcrt!_wcsicmp` at `0x180044e97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800449b9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800449b9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800449d1`
- `OLEAUT32!__imp_SysAllocString` at `0x180044a18`
- `OLEAUT32!__imp_SysAllocString` at `0x1800449d1`
- `OLEAUT32!__imp_SysAllocString` at `0x180044a18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800450be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800450d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180045107`
- `OLEAUT32!__imp_SysFreeString` at `0x18004531b`
- `OLEAUT32!__imp_SysFreeString` at `0x180045330`
- `OLEAUT32!__imp_SysFreeString` at `0x180045399`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800450be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800450d3`
- `OLEAUT32!__imp_SysFreeString` at `0x180045107`
- `OLEAUT32!__imp_SysFreeString` at `0x18004531b`
- `OLEAUT32!__imp_SysFreeString` at `0x180045330`
- `OLEAUT32!__imp_SysFreeString` at `0x180045399`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453dc`
- `OLEAUT32!__imp_VariantClear` at `0x180045130`
- `OLEAUT32!__imp_VariantClear` at `0x18004543c`
- `OLEAUT32!__imp_VariantClear` at `0x180045130`
- `OLEAUT32!__imp_VariantClear` at `0x18004543c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004533e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004533e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180044a7f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180044a7f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180044abe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180044abe`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180044a4a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180044a4a`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall GetDataFromResponse(OLECHAR *psz, unsigned __int16 **a2, unsigned __int16 **a3)
{
  OLECHAR *v5; // r14
  SAFEARRAY *v6; // r13
  unsigned __int16 *v7; // r15
  unsigned __int64 v8; // r12
  BSTR v9; // rdx
  HRESULT v10; // edi
  OLECHAR *v11; // rcx
  SAFEARRAY *Vector; // rax
  int v13; // eax
  BSTR v14; // rdx
  wchar_t *v15; // r14
  unsigned int v16; // edi
  const wchar_t *v17; // rdx
  const unsigned __int16 *v18; // rcx
  unsigned __int16 *v19; // rsi
  unsigned int v20; // ecx
  unsigned __int64 v21; // rax
  unsigned __int16 *v22; // rax
  BSTR v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  signed __int64 v27; // rsi
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rcx
  unsigned __int16 *v30; // rax
  __int64 i; // rdx
  char v32; // cl
  BSTR v34; // [rsp+30h] [rbp-1A8h]
  __int16 v35; // [rsp+40h] [rbp-198h]
  char v36; // [rsp+42h] [rbp-196h]
  BSTR bstrString; // [rsp+48h] [rbp-190h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-188h] BYREF
  __int64 v39; // [rsp+58h] [rbp-180h] BYREF
  unsigned __int16 *v40; // [rsp+60h] [rbp-178h]
  __int64 v41; // [rsp+68h] [rbp-170h] BYREF
  BSTR v42; // [rsp+70h] [rbp-168h] BYREF
  void *Block; // [rsp+78h] [rbp-160h] BYREF
  int v44; // [rsp+80h] [rbp-158h] BYREF
  unsigned int v45; // [rsp+84h] [rbp-154h] BYREF
  unsigned int v46; // [rsp+88h] [rbp-150h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-148h] BYREF
  BSTR v48; // [rsp+98h] [rbp-140h] BYREF
  unsigned __int16 *v49; // [rsp+A0h] [rbp-138h] BYREF
  SAFEARRAY *v50; // [rsp+A8h] [rbp-130h]
  __int64 v51; // [rsp+B0h] [rbp-128h] BYREF
  wchar_t *String2; // [rsp+B8h] [rbp-120h] BYREF
  int v53; // [rsp+C0h] [rbp-118h] BYREF
  void *ppvData; // [rsp+C8h] [rbp-110h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-108h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-100h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-F8h] BYREF
  void *v58; // [rsp+E8h] [rbp-F0h]
  unsigned __int16 **v59; // [rsp+F0h] [rbp-E8h]
  VARIANTARG pvarg; // [rsp+F8h] [rbp-E0h] BYREF
  __int64 v61; // [rsp+110h] [rbp-C8h]
  unsigned __int16 **v62; // [rsp+118h] [rbp-C0h]
  wchar_t *v63[4]; // [rsp+120h] [rbp-B8h]
  __int128 v64; // [rsp+140h] [rbp-98h] BYREF
  __int64 v65; // [rsp+150h] [rbp-88h]
  __int128 v66; // [rsp+160h] [rbp-78h] BYREF
  __int64 v67; // [rsp+170h] [rbp-68h]

  v63[3] = (wchar_t *)-2LL;
  v59 = a3;
  v62 = a2;
  ppv = 0;
  v5 = 0;
  ppvData = 0;
  v6 = 0;
  v50 = 0;
  v51 = 0;
  v44 = 0;
  v61 = 0;
  v55 = 0;
  v41 = 0;
  v48 = 0;
  String2 = 0;
  v56 = 0;
  v57 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v39 = 0;
  v53 = 0;
  v42 = 0;
  String1 = 0;
  bstrString = 0;
  v7 = 0;
  v40 = 0;
  LODWORD(v8) = 0;
  v58 = 0;
  Block = 0;
  v45 = 0;
  v49 = 0;
  v46 = 0;
  v63[0] = L"wa";
  v63[1] = L"wctx";
  v63[2] = L"wresult";
  v35 = 0;
  v36 = 0;
  _RTLTRACE("+[msdrm]:GetDataFromResponse ");
  if ( !psz || !a2 || !v59 )
  {
    v10 = -2147024809;
    goto LABEL_122;
  }
  v10 = CoCreateInstance(&CLSID_HTMLDocument, 0, 1u, &IID_IHTMLDocument2, &ppv);
  if ( v10 < 0 )
    goto LABEL_122;
  v9 = SysAllocString(L"On");
  v34 = v9;
  if ( !v9 )
  {
    v10 = -2147024882;
    goto LABEL_122;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 152LL))(ppv);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v5 = SysAllocString(psz);
  if ( !v5 )
  {
    v10 = -2147024882;
    v5 = 0;
    v11 = v34;
    goto LABEL_118;
  }
  Vector = SafeArrayCreateVector(0xCu, 0, 1u);
  v6 = Vector;
  v50 = Vector;
  if ( !Vector )
  {
    v10 = -2147024882;
    v11 = v34;
    goto LABEL_118;
  }
  v10 = SafeArrayAccessData(Vector, &ppvData);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  *(_WORD *)ppvData = 8;
  *((_QWORD *)ppvData + 1) = v5;
  v5 = 0;
  v10 = SafeArrayUnaccessData(v6);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, SAFEARRAY *))(*(_QWORD *)ppv + 472LL))(ppv, v6);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 112LL))(ppv, &v51);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 72LL))(v51, &v44);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  if ( v44 != 1 )
  {
    _RTLTRACE("[msdrm]: InCorrect No. of Forms found in the message: %d", v44);
    v10 = -2147168441;
    v11 = v34;
    goto LABEL_118;
  }
  v64 = 0;
  v65 = v61;
  v66 = 0;
  v67 = v61;
  v10 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *, __int64 *))(*(_QWORD *)v51 + 88LL))(
          v51,
          &v66,
          &v64,
          &v55);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v55)(v55, &IID_IHTMLFormElement, &v41);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v41 + 112LL))(v41, &String2);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  if ( !String2 || _wcsicmp(L"post", String2) )
  {
    _RTLTRACE("[msdrm]: Incorrect form method: %ws");
    v10 = -2147168441;
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v41 + 64LL))(v41, &v48);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  if ( !v48 )
  {
    _RTLTRACE("[msdrm]: Incorrect form Action");
    v10 = -2147168441;
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 224LL))(v41, &v56);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 216LL))(v41, &v53);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v56)(v56, &IID_IEnumVARIANT, &v57);
  if ( v10 < 0 )
  {
    v11 = v34;
    goto LABEL_118;
  }
  while ( 1 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *))(*(_QWORD *)v57 + 24LL))(v57, 1, &pvarg);
    v10 = v13;
    if ( v13 < 0 )
    {
      v5 = 0;
      v11 = v34;
      goto LABEL_118;
    }
    if ( v13 )
      break;
    if ( pvarg.vt == 9
      && (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))pvarg.llVal)(pvarg.llVal, &IID_IHTMLInputElement, &v39) >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v39 + 64LL))(v39, &v42);
      if ( v10 < 0 )
      {
        v5 = 0;
        v11 = v34;
        goto LABEL_118;
      }
      if ( !v42 || _wcsicmp(L"hidden", v42) )
      {
        _RTLTRACE("[msdrm]: Ignoring un-known parameter type: %ws");
      }
      else
      {
        v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v39 + 96LL))(v39, &String1);
        if ( v10 < 0 )
        {
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v39 + 80LL))(v39, &bstrString);
        if ( v10 < 0 )
        {
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        _RTLTRACE("[msdrm]: Param Name = %ws", String1);
        v14 = (BSTR)&Src;
        if ( bstrString )
          v14 = bstrString;
        _RTLTRACE("[msdrm]: Param Value = %ws", v14);
        v15 = String1;
        v16 = 0;
        while ( 1 )
        {
          v17 = v63[v16];
          if ( v17 )
          {
            if ( !_wcsicmp(v15, v17) )
              break;
          }
          if ( (int)++v16 >= 3 )
            goto LABEL_63;
        }
        *((_BYTE *)&v35 + v16) = 1;
LABEL_63:
        v10 = URLEscapeData(String1, (unsigned __int16 **)&Block, &v45);
        if ( v10 < 0 )
        {
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        v18 = &Src;
        if ( bstrString )
          v18 = bstrString;
        v10 = URLEscapeData(v18, &v49, &v46);
        if ( v10 < 0 )
        {
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        v19 = v7;
        v58 = v7;
        v40 = 0;
        v20 = v8 + v45;
        if ( (unsigned int)v8 + v45 < (unsigned int)v8 )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
        if ( v20 + v46 < v20 )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
        v21 = v20 + v46 + 3LL;
        if ( v21 > 0xFFFFFFFF )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
        v8 = (unsigned int)v21;
        v22 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v21, 2u));
        v7 = v22;
        v40 = v22;
        if ( !v22 )
        {
          v10 = -2147024882;
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        if ( v19 )
        {
          v10 = StringCchCopyW(v22, v8, v19);
          if ( v10 < 0 )
          {
            v5 = 0;
            v11 = v34;
            goto LABEL_118;
          }
          v10 = StringCchCatW(v7, v8, L"&");
          if ( v10 < 0 )
          {
            v5 = 0;
            v11 = v34;
            goto LABEL_118;
          }
          v10 = StringCchCatW(v7, v8, (const unsigned __int16 *)Block);
          if ( v10 < 0 )
          {
            v5 = 0;
            v11 = v34;
            goto LABEL_118;
          }
        }
        else
        {
          v10 = StringCchCopyW(v22, v8, (const unsigned __int16 *)Block);
          if ( v10 < 0 )
          {
            v5 = 0;
            v11 = v34;
            goto LABEL_118;
          }
        }
        v10 = StringCchCatW(v7, v8, L"=");
        if ( v10 < 0 )
        {
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        v10 = StringCchCatW(v7, v8, v49);
        if ( v10 < 0 )
        {
          v5 = 0;
          v11 = v34;
          goto LABEL_118;
        }
        operator delete(v19);
        v58 = 0;
        operator delete(Block);
        Block = 0;
        operator delete(v49);
        v49 = 0;
        if ( String1 )
        {
          SysFreeString(String1);
          String1 = 0;
        }
        if ( bstrString )
        {
          SysFreeString(bstrString);
          bstrString = 0;
        }
      }
      if ( v42 )
      {
        SysFreeString(v42);
        v42 = 0;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v39 = 0;
    }
    VariantClear(&pvarg);
  }
  v23 = v48;
  if ( !v48 )
  {
    v10 = -2147024809;
LABEL_115:
    v5 = 0;
    v11 = v34;
    goto LABEL_118;
  }
  v24 = 0x7FFFFFFF;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v24;
  }
  while ( v24 );
  v10 = v24 == 0 ? 0x80070057 : 0;
  v25 = 0x7FFFFFFF - v24;
  v26 = (0x7FFFFFFF - v24) & ((unsigned __int128)-(__int128)(unsigned __int64)v24 >> 64);
  if ( !v24 )
    goto LABEL_115;
  v27 = v26 + 1;
  if ( v26 + 1 < v26 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( v27 < 0 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  v28 = 2LL * (unsigned int)v27;
  v29 = HIDWORD(v27) << 33;
  if ( v29 + v28 < v28 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( !(v29 + v28) )
    goto LABEL_109;
  v30 = (unsigned __int16 *)operator new[](saturated_mul(v27, 2u));
  *v62 = v30;
  if ( !v30 )
  {
    v10 = -2147024882;
    v5 = 0;
    v11 = v34;
    goto LABEL_118;
  }
  v10 = StringCchCopyW(v30, v27, v48);
  if ( v10 < 0 )
  {
    v5 = 0;
    v11 = v34;
  }
  else
  {
LABEL_109:
    *v59 = v7;
    v7 = 0;
    v40 = 0;
    LOBYTE(v25) = 1;
    for ( i = 0; i != 3; ++i )
    {
      v32 = *((_BYTE *)&v35 + i) != 0 ? v25 : 0;
      LOBYTE(v25) = v32;
    }
    if ( v32 )
    {
      _RTLTRACE("-[msdrm]:GetDataFromResponse: All params of interest (%d) found\n", 3);
    }
    else
    {
      _RTLTRACE("-[msdrm]:GetDataFromResponse: All params of interest NOT found\n", 3, v25);
      v10 = -2147467259;
    }
    v11 = v34;
    v5 = 0;
  }
LABEL_118:
  SysFreeString(v11);
  if ( v5 )
    SysFreeString(v5);
  if ( v6 )
    SafeArrayDestroy(v6);
LABEL_122:
  if ( v51 )
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v51 + 16LL))(v51, v9);
  if ( v55 )
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v55 + 16LL))(v55, v9);
  if ( v41 )
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v41 + 16LL))(v41, v9);
  if ( v48 )
    SysFreeString(v48);
  if ( String2 )
    SysFreeString(String2);
  if ( String1 )
    SysFreeString(String1);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v42 )
    SysFreeString(v42);
  if ( v56 )
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v56 + 16LL))(v56, v9);
  if ( v57 )
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v57 + 16LL))(v57, v9);
  if ( v39 )
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v39 + 16LL))(v39, v9);
  if ( pvarg.vt )
    VariantClear(&pvarg);
  operator delete(v58);
  operator delete(v7);
  operator delete(Block);
  operator delete(v49);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  _RTLTRACE("-[msdrm]:GetDataFromResponse 0x%x", v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180044828  mov     r11, rsp
0x18004482b  push    rbx
0x18004482c  push    rsi
0x18004482d  push    rdi
0x18004482e  push    r12
0x180044830  push    r13
0x180044832  push    r14
0x180044834  push    r15
0x180044836  sub     rsp, 1A0h
0x18004483d  mov     qword ptr [r11-0A0h], 0FFFFFFFFFFFFFFFEh
0x180044848  movaps  xmmword ptr [r11-48h], xmm6
0x18004484d  mov     rax, cs:__security_cookie
0x180044854  xor     rax, rsp
0x180044857  mov     [rsp+1D8h+var_50], rax
0x18004485f  mov     [rsp+1D8h+var_E8], r8
0x180044867  mov     rdi, rdx
0x18004486a  mov     [rsp+1D8h+var_C0], rdx
0x180044872  mov     rsi, rcx
0x180044875  xor     ebx, ebx
0x180044877  mov     [r11-148h], rbx
0x18004487e  mov     r14d, ebx
0x180044881  mov     [rsp+1D8h+var_1A0], rbx
0x180044886  mov     [r11-110h], rbx
0x18004488d  mov     r13d, ebx
0x180044890  mov     [rsp+1D8h+var_130], rbx
0x180044898  mov     [r11-128h], rbx
0x18004489f  mov     [rsp+1D8h+var_158], ebx
0x1800448a6  xorps   xmm6, xmm6
0x1800448a9  xor     eax, eax
0x1800448ab  mov     [r11-0C8h], rax
0x1800448b2  mov     [r11-108h], rbx
0x1800448b9  mov     [rsp+1D8h+var_170], rbx
0x1800448be  mov     [r11-140h], rbx
0x1800448c5  mov     [r11-120h], rbx
0x1800448cc  mov     [r11-100h], rbx
0x1800448d3  mov     [r11-0F8h], rbx
0x1800448da  xorps   xmm0, xmm0
0x1800448dd  movups  xmmword ptr [rsp+1D8h+pvarg], xmm0
0x1800448e5  mov     [r11-0D0h], rax
0x1800448ec  mov     [rsp+1D8h+var_180], rbx
0x1800448f1  mov     [rsp+1D8h+var_118], ebx
0x1800448f8  mov     [rsp+1D8h+var_168], rbx
0x1800448fd  mov     [rsp+1D8h+String1], rbx
0x180044902  mov     [rsp+1D8h+bstrString], rbx
0x180044907  mov     r15d, ebx
0x18004490a  mov     [rsp+1D8h+var_178], rbx
0x18004490f  mov     r12d, ebx
0x180044912  mov     [rsp+1D8h+var_F0], rbx
0x18004491a  mov     [rsp+1D8h+Block], rbx
0x18004491f  mov     [rsp+1D8h+var_154], ebx
0x180044926  mov     [r11-138h], rbx
0x18004492d  mov     [rsp+1D8h+var_150], ebx
0x180044934  lea     rax, aWa; "wa"
0x18004493b  mov     [r11-0B8h], rax
0x180044942  lea     rax, aWctx; "wctx"
0x180044949  mov     [r11-0B0h], rax
0x180044950  lea     rax, aWresult; "wresult"
0x180044957  mov     [r11-0A8h], rax
0x18004495e  mov     word ptr [rsp+1D8h+var_198], bx
0x180044963  mov     byte ptr [rsp+1D8h+var_198+2], bl
0x180044967  mov     [rsp+1D8h+var_1A8], rbx
0x18004496c  lea     rcx, aMsdrmGetdatafr_1; "+[msdrm]:GetDataFromResponse "
0x180044973  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180044978  test    rsi, rsi
0x18004497b  jz      loc_1800452F2
0x180044981  test    rdi, rdi
0x180044984  jz      loc_1800452F2
0x18004498a  cmp     [rsp+1D8h+var_E8], rbx
0x180044992  jz      loc_1800452F2
0x180044998  lea     rax, [rsp+1D8h+var_148]
0x1800449a0  mov     [rsp+1D8h+ppv], rax; ppv
0x1800449a5  lea     r9, IID_IHTMLDocument2; riid
0x1800449ac  xor     edx, edx; pUnkOuter
0x1800449ae  lea     r8d, [rbx+1]; dwClsContext
0x1800449b2  lea     rcx, CLSID_HTMLDocument; rclsid
0x1800449b9  call    cs:__imp_CoCreateInstance
0x1800449bf  mov     edi, eax
0x1800449c1  test    eax, eax
0x1800449c3  jns     short loc_1800449CA
0x1800449c5  jmp     loc_180045344
0x1800449ca  lea     rcx, psz; "On"
0x1800449d1  call    cs:__imp_SysAllocString
0x1800449d7  mov     rdx, rax
0x1800449da  mov     [rsp+1D8h+var_1A8], rax
0x1800449df  test    rax, rax
0x1800449e2  jnz     short loc_1800449EE
0x1800449e4  mov     edi, 8007000Eh
0x1800449e9  jmp     loc_180045344
0x1800449ee  mov     rcx, [rsp+1D8h+var_148]
0x1800449f6  mov     rax, [rcx]
0x1800449f9  mov     rax, [rax+98h]
0x180044a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a05  mov     edi, eax
0x180044a07  test    eax, eax
0x180044a09  jns     short loc_180044A15
0x180044a0b  mov     rcx, [rsp+1D8h+var_1A8]
0x180044a10  jmp     loc_18004531B
0x180044a15  mov     rcx, rsi; psz
0x180044a18  call    cs:__imp_SysAllocString
0x180044a1e  mov     r14, rax
0x180044a21  mov     [rsp+1D8h+var_1A0], rax
0x180044a26  test    rax, rax
0x180044a29  jnz     short loc_180044A3F
0x180044a2b  mov     edi, 8007000Eh
0x180044a30  mov     r14, [rsp+1D8h+var_1A0]
0x180044a35  mov     rcx, [rsp+1D8h+var_1A8]
0x180044a3a  jmp     loc_18004531B
0x180044a3f  mov     ecx, 0Ch; vt
0x180044a44  xor     edx, edx; lLbound
0x180044a46  lea     r8d, [rcx-0Bh]; cElements
0x180044a4a  call    cs:__imp_SafeArrayCreateVector
0x180044a50  mov     r13, rax
0x180044a53  mov     [rsp+1D8h+var_130], rax
0x180044a5b  test    rax, rax
0x180044a5e  jnz     short loc_180044A74
0x180044a60  mov     edi, 8007000Eh
0x180044a65  mov     r14, [rsp+1D8h+var_1A0]
0x180044a6a  mov     rcx, [rsp+1D8h+var_1A8]
0x180044a6f  jmp     loc_18004531B
0x180044a74  lea     rdx, [rsp+1D8h+ppvData]; ppvData
0x180044a7c  mov     rcx, r13; psa
0x180044a7f  call    cs:__imp_SafeArrayAccessData
0x180044a85  mov     edi, eax
0x180044a87  test    eax, eax
0x180044a89  jns     short loc_180044A9A
0x180044a8b  mov     r14, [rsp+1D8h+var_1A0]
0x180044a90  mov     rcx, [rsp+1D8h+var_1A8]
0x180044a95  jmp     loc_18004531B
0x180044a9a  mov     rax, [rsp+1D8h+ppvData]
0x180044aa2  mov     word ptr [rax], 8
0x180044aa7  mov     rax, [rsp+1D8h+ppvData]
0x180044aaf  mov     [rax+8], r14
0x180044ab3  mov     r14, rbx
0x180044ab6  mov     [rsp+1D8h+var_1A0], rbx
0x180044abb  mov     rcx, r13; psa
0x180044abe  call    cs:__imp_SafeArrayUnaccessData
0x180044ac4  mov     edi, eax
0x180044ac6  test    eax, eax
0x180044ac8  jns     short loc_180044AD4
0x180044aca  mov     rcx, [rsp+1D8h+var_1A8]
0x180044acf  jmp     loc_18004531B
0x180044ad4  mov     rcx, [rsp+1D8h+var_148]
0x180044adc  mov     rax, [rcx]
0x180044adf  mov     rdx, r13
0x180044ae2  mov     rax, [rax+1D8h]
0x180044ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044aee  mov     edi, eax
0x180044af0  test    eax, eax
0x180044af2  jns     short loc_180044AFE
0x180044af4  mov     rcx, [rsp+1D8h+var_1A8]
0x180044af9  jmp     loc_18004531B
0x180044afe  mov     rcx, [rsp+1D8h+var_148]
0x180044b06  mov     rax, [rcx]
0x180044b09  lea     rdx, [rsp+1D8h+var_128]
0x180044b11  mov     rax, [rax+70h]
0x180044b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b1a  mov     edi, eax
0x180044b1c  test    eax, eax
0x180044b1e  jns     short loc_180044B2A
0x180044b20  mov     rcx, [rsp+1D8h+var_1A8]
0x180044b25  jmp     loc_18004531B
0x180044b2a  mov     rcx, [rsp+1D8h+var_128]
0x180044b32  mov     rax, [rcx]
0x180044b35  lea     rdx, [rsp+1D8h+var_158]
0x180044b3d  mov     rax, [rax+48h]
0x180044b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b46  mov     edi, eax
0x180044b48  test    eax, eax
0x180044b4a  jns     short loc_180044B56
0x180044b4c  mov     rcx, [rsp+1D8h+var_1A8]
0x180044b51  jmp     loc_18004531B
0x180044b56  mov     edx, [rsp+1D8h+var_158]
0x180044b5d  cmp     edx, 1
0x180044b60  jz      short loc_180044B7D
0x180044b62  lea     rcx, aMsdrmIncorrect; "[msdrm]: InCorrect No. of Forms found i"...
0x180044b69  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180044b6e  mov     edi, 8004CF47h
0x180044b73  mov     rcx, [rsp+1D8h+var_1A8]
0x180044b78  jmp     loc_18004531B
0x180044b7d  movaps  [rsp+1D8h+var_98], xmm6
0x180044b85  movsd   xmm0, [rsp+1D8h+var_C8]
0x180044b8e  movsd   [rsp+1D8h+var_88], xmm0
0x180044b97  movaps  [rsp+1D8h+var_78], xmm6
0x180044b9f  movsd   [rsp+1D8h+var_68], xmm0
0x180044ba8  mov     rcx, [rsp+1D8h+var_128]
0x180044bb0  mov     rax, [rcx]
0x180044bb3  lea     r9, [rsp+1D8h+var_108]
0x180044bbb  lea     r8, [rsp+1D8h+var_98]
0x180044bc3  lea     rdx, [rsp+1D8h+var_78]
0x180044bcb  mov     rax, [rax+58h]
0x180044bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bd4  mov     edi, eax
0x180044bd6  test    eax, eax
0x180044bd8  jns     short loc_180044BE4
0x180044bda  mov     rcx, [rsp+1D8h+var_1A8]
0x180044bdf  jmp     loc_18004531B
0x180044be4  mov     rcx, [rsp+1D8h+var_108]
0x180044bec  mov     rax, [rcx]
0x180044bef  lea     r8, [rsp+1D8h+var_170]
0x180044bf4  lea     rdx, IID_IHTMLFormElement
0x180044bfb  mov     rax, [rax]
0x180044bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c03  mov     edi, eax
0x180044c05  test    eax, eax
0x180044c07  jns     short loc_180044C13
0x180044c09  mov     rcx, [rsp+1D8h+var_1A8]
0x180044c0e  jmp     loc_18004531B
0x180044c13  mov     rcx, [rsp+1D8h+var_170]
0x180044c18  mov     rax, [rcx]
0x180044c1b  lea     rdx, [rsp+1D8h+String2]
0x180044c23  mov     rax, [rax+70h]
0x180044c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c2c  mov     edi, eax
0x180044c2e  test    eax, eax
0x180044c30  jns     short loc_180044C3C
0x180044c32  mov     rcx, [rsp+1D8h+var_1A8]
0x180044c37  jmp     loc_18004531B
0x180044c3c  mov     rdx, [rsp+1D8h+String2]; String2
0x180044c44  test    rdx, rdx
0x180044c47  jz      loc_1800452D3
0x180044c4d  lea     rcx, ?g_wszPOSTconst@@3QBGB; "post"
0x180044c54  call    cs:__imp__wcsicmp
0x180044c5a  test    eax, eax
0x180044c5c  jnz     loc_1800452C6
0x180044c62  mov     rcx, [rsp+1D8h+var_170]
0x180044c67  mov     rax, [rcx]
0x180044c6a  lea     rdx, [rsp+1D8h+var_140]
0x180044c72  mov     rax, [rax+40h]
0x180044c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c7b  mov     edi, eax
0x180044c7d  test    eax, eax
0x180044c7f  jns     short loc_180044C8B
0x180044c81  mov     rcx, [rsp+1D8h+var_1A8]
0x180044c86  jmp     loc_18004531B
0x180044c8b  cmp     [rsp+1D8h+var_140], rbx
0x180044c93  jnz     short loc_180044CB0
0x180044c95  lea     rcx, aMsdrmIncorrect_1; "[msdrm]: Incorrect form Action"
0x180044c9c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180044ca1  mov     edi, 8004CF47h
0x180044ca6  mov     rcx, [rsp+1D8h+var_1A8]
0x180044cab  jmp     loc_18004531B
0x180044cb0  mov     rcx, [rsp+1D8h+var_170]
0x180044cb5  mov     rax, [rcx]
0x180044cb8  lea     rdx, [rsp+1D8h+var_100]
0x180044cc0  mov     rax, [rax+0E0h]
0x180044cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ccc  mov     edi, eax
0x180044cce  test    eax, eax
0x180044cd0  jns     short loc_180044CDC
0x180044cd2  mov     rcx, [rsp+1D8h+var_1A8]
0x180044cd7  jmp     loc_18004531B
0x180044cdc  mov     rcx, [rsp+1D8h+var_170]
0x180044ce1  mov     rax, [rcx]
0x180044ce4  lea     rdx, [rsp+1D8h+var_118]
0x180044cec  mov     rax, [rax+0D8h]
0x180044cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cf8  mov     edi, eax
0x180044cfa  test    eax, eax
0x180044cfc  jns     short loc_180044D08
0x180044cfe  mov     rcx, [rsp+1D8h+var_1A8]
0x180044d03  jmp     loc_18004531B
0x180044d08  mov     rcx, [rsp+1D8h+var_100]
0x180044d10  mov     rax, [rcx]
0x180044d13  lea     r8, [rsp+1D8h+var_F8]
0x180044d1b  lea     rdx, IID_IEnumVARIANT
0x180044d22  mov     rax, [rax]
0x180044d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d2a  mov     edi, eax
0x180044d2c  test    eax, eax
0x180044d2e  jns     short loc_180044D3A
0x180044d30  mov     rcx, [rsp+1D8h+var_1A8]
0x180044d35  jmp     loc_18004531B
0x180044d3a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180044d3e  mov     rcx, [rsp+1D8h+var_F8]
0x180044d46  mov     rax, [rcx]
0x180044d49  xor     r9d, r9d
0x180044d4c  lea     r8, [rsp+1D8h+pvarg]
0x180044d54  lea     edx, [r9+1]
0x180044d58  mov     rax, [rax+18h]
0x180044d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d61  mov     edi, eax
0x180044d63  test    eax, eax
0x180044d65  js      loc_1800452BA
0x180044d6b  jnz     loc_18004513B
0x180044d71  mov     eax, 9
0x180044d76  cmp     ax, word ptr [rsp+1D8h+pvarg]
0x180044d7e  jnz     loc_180045128
0x180044d84  mov     rcx, qword ptr [rsp+1D8h+pvarg+8]
0x180044d8c  mov     rax, [rcx]
0x180044d8f  lea     r8, [rsp+1D8h+var_180]
0x180044d94  lea     rdx, IID_IHTMLInputElement
0x180044d9b  mov     rax, [rax]
0x180044d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044da3  test    eax, eax
0x180044da5  js      loc_180045128
0x180044dab  mov     rcx, [rsp+1D8h+var_180]
0x180044db0  mov     rax, [rcx]
0x180044db3  lea     rdx, [rsp+1D8h+var_168]
0x180044db8  mov     rax, [rax+40h]
0x180044dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
