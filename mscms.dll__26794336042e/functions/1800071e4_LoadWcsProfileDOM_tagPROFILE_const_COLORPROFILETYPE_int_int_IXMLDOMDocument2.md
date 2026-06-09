# LoadWcsProfileDOM(tagPROFILE const *,COLORPROFILETYPE,int,int,IXMLDOMDocument2 * *)

- ea: `0x1800071e4`
- end: `0x180007a8e`
- name: `?LoadWcsProfileDOM@@YAJPEBUtagPROFILE@@W4COLORPROFILETYPE@@HHPEAPEAUIXMLDOMDocument2@@@Z`
- size: `2218`
- prototype: `__int64 __fastcall(const struct tagPROFILE *, enum COLORPROFILETYPE, int, int, struct IXMLDOMDocument2 **)`
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006b40`
- `0x180006e64`
- `0x180051968`
- `0x180056ec8`

## callees

- `0x1800071e4`
- `0x1800089d8`
- `0x180008bf0`
- `0x180009810`
- `0x18001c130`
- `0x180020944`
- `0x180029f14`
- `0x18002e5f0`
- `0x18002f2dc`
- `0x180056e90`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007878`
- `ntdll!EtwEventWrite` at `0x180007878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007542`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007969`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800079c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007969`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800079c4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007351`
- `OLEAUT32!__imp_SysAllocString` at `0x180007376`
- `OLEAUT32!__imp_SysAllocString` at `0x1800073f7`
- `OLEAUT32!__imp_SysAllocString` at `0x180007443`
- `OLEAUT32!__imp_SysAllocString` at `0x1800075b4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007351`
- `OLEAUT32!__imp_SysAllocString` at `0x180007376`
- `OLEAUT32!__imp_SysAllocString` at `0x1800073f7`
- `OLEAUT32!__imp_SysAllocString` at `0x180007443`
- `OLEAUT32!__imp_SysAllocString` at `0x1800075b4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800074ec`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800074ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800073c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007495`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075aa`
- `OLEAUT32!__imp_SysFreeString` at `0x180007883`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800073c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007495`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075aa`
- `OLEAUT32!__imp_SysFreeString` at `0x180007883`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079e9`
- `OLEAUT32!__imp_VariantInit` at `0x18000735f`
- `OLEAUT32!__imp_VariantInit` at `0x180007405`
- `OLEAUT32!__imp_VariantInit` at `0x1800074cd`
- `OLEAUT32!__imp_VariantInit` at `0x180007727`
- `OLEAUT32!__imp_VariantInit` at `0x18000735f`
- `OLEAUT32!__imp_VariantInit` at `0x180007405`
- `OLEAUT32!__imp_VariantInit` at `0x1800074cd`
- `OLEAUT32!__imp_VariantInit` at `0x180007727`
- `OLEAUT32!__imp_VariantClear` at `0x1800073d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800074a0`
- `OLEAUT32!__imp_VariantClear` at `0x180007a17`
- `OLEAUT32!__imp_VariantClear` at `0x1800073d3`
- `OLEAUT32!__imp_VariantClear` at `0x1800074a0`
- `OLEAUT32!__imp_VariantClear` at `0x180007a17`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000760b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000760b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180007632`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180007632`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800075e4`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800075e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000730b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000730b`

## string_xrefs

- `0x18000740b`: `xmlns:wcs='http://schemas.microsoft.com/windows/2005/02/color/WcsCommonProfileTypes'`
- `0x1800072da`: `xmlns:cdm='http://schemas.microsoft.com/windows/2005/02/color/ColorDeviceModel' xmlns:cal='http://schemas.microsoft.com/windows/2007/11/color/Calibration'`
- `0x18000736a`: `XPath`
- `0x1800072a6`: `xmlns:cam='http://schemas.microsoft.com/windows/2005/02/color/ColorAppearanceModel'`
- `0x180007270`: `xmlns:gmm='http://schemas.microsoft.com/windows/2005/02/color/GamutMapModel'`

## pseudocode

```c
__int64 __fastcall LoadWcsProfileDOM(
        const struct tagPROFILE *a1,
        enum COLORPROFILETYPE a2,
        int a3,
        int a4,
        struct IXMLDOMDocument2 **a5)
{
  LONGLONG v6; // r13
  int v7; // edx
  int v8; // edx
  signed int v9; // ebx
  unsigned int v10; // r15d
  unsigned __int16 **v11; // r12
  const struct IXMLDOMElement *v12; // rsi
  const wchar_t *v13; // rdi
  const WCHAR *v14; // rax
  OLECHAR *v15; // rsi
  BSTR v16; // rax
  __int64 v17; // rax
  OLECHAR *v18; // rsi
  BSTR v19; // rax
  __int64 v20; // rax
  const OLECHAR *pProfileData; // rcx
  UINT v22; // edx
  const WCHAR *v23; // rax
  const WCHAR *v24; // rbx
  const WCHAR *FilenameFromPath; // rax
  const unsigned __int16 *v26; // rdi
  signed int LastError; // eax
  ULONG cbDataSize; // r8d
  SAFEARRAY *Vector; // rax
  __int64 v30; // rax
  int v31; // eax
  int CompatibilityMarkupProcessor; // eax
  void (__fastcall ***v33)(_QWORD, __int64); // rdi
  __int64 v34; // rax
  __int64 (__fastcall *v35)(LPVOID, __int128 *); // rax
  int v36; // eax
  const WCHAR *v37; // rdi
  _WORD *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  unsigned int v41; // eax
  const OLECHAR *v42; // rcx
  __int64 v43; // rcx
  int v44; // eax
  int v45; // eax
  const WCHAR *v46; // r8
  int v47; // eax
  int v48; // ecx
  LPVOID v49; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v52; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v54)(_QWORD, __int64); // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwSize[2]; // [rsp+68h] [rbp-98h] BYREF
  PCNZWCH lpString1; // [rsp+70h] [rbp-90h] BYREF
  PCNZWCH lpString2; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v59; // [rsp+80h] [rbp-80h] BYREF
  PCNZWCH v60; // [rsp+A0h] [rbp-60h]
  LONGLONG v61; // [rsp+A8h] [rbp-58h] BYREF
  struct IXMLDOMDocument2 **v62; // [rsp+B0h] [rbp-50h]
  __int128 v63; // [rsp+C0h] [rbp-40h] BYREF
  const OLECHAR *pRecInfo; // [rsp+D0h] [rbp-30h]
  int v65; // [rsp+D8h] [rbp-28h]
  int v66; // [rsp+DCh] [rbp-24h]
  OLECHAR psz[520]; // [rsp+E0h] [rbp-20h] BYREF

  v62 = a5;
  LODWORD(bstrString) = a4;
  v6 = 0;
  LODWORD(v54) = a3;
  v61 = 0;
  ppv = 0;
  v7 = a2 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
        return (unsigned int)-2147024809;
      v10 = 2;
      lpString1 = (PCNZWCH)&qword_18008CA98;
      v11 = &off_18009E100;
      v12 = &stru_18008E320;
      v13 = L"xmlns:gmm='http://schemas.microsoft.com/windows/2005/02/color/GamutMapModel'";
      v14 = L"GamutMapModel";
    }
    else
    {
      v10 = 2;
      lpString1 = (PCNZWCH)&qword_18008CAA0;
      v11 = &off_18009E0F0;
      v12 = &stru_18008DEB0;
      v13 = L"xmlns:cam='http://schemas.microsoft.com/windows/2005/02/color/ColorAppearanceModel'";
      v14 = L"ColorAppearanceModel";
    }
    v60 = v14;
    lpString2 = (PCNZWCH)v12;
  }
  else
  {
    v10 = 3;
    lpString1 = (PCNZWCH)qword_180088280;
    v11 = off_18009E0D8;
    v60 = L"ColorDeviceModel";
    v13 = L"xmlns:cdm='http://schemas.microsoft.com/windows/2005/02/color/ColorDeviceModel' xmlns:cal='http://schemas.micr"
           "osoft.com/windows/2007/11/color/Calibration'";
    lpString2 = (PCNZWCH)&stru_1800882C0;
  }
  v9 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
  if ( v9 < 0 )
    goto LABEL_108;
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v9 < 0 )
    goto LABEL_108;
  memset(&pvarg, 0, sizeof(pvarg));
  v15 = SysAllocString(L"SelectionLanguage");
  VariantInit(&pvarg);
  pvarg.vt = 8;
  v16 = SysAllocString(L"XPath");
  pvarg.llVal = (LONGLONG)v16;
  if ( !v15 || !v16 )
    v9 = -2147024882;
  if ( v9 >= 0 )
  {
    v17 = *(_QWORD *)ppv;
    v59 = pvarg;
    v9 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v17 + 640))(ppv, v15, &v59);
  }
  SysFreeString(v15);
  VariantClear(&pvarg);
  if ( v9 < 0 )
    goto LABEL_108;
  memset(&pvarg, 0, sizeof(pvarg));
  v18 = SysAllocString(L"SelectionNamespaces");
  VariantInit(&pvarg);
  v9 = StringCchPrintfW(
         psz,
         0x208u,
         L"%s %s",
         v13,
         L"xmlns:wcs='http://schemas.microsoft.com/windows/2005/02/color/WcsCommonProfileTypes'");
  if ( v9 >= 0 )
  {
    pvarg.vt = 8;
    v19 = SysAllocString(psz);
    pvarg.llVal = (LONGLONG)v19;
    if ( !v18 || !v19 )
      v9 = -2147024882;
    if ( v9 >= 0 )
    {
      v20 = *(_QWORD *)ppv;
      v59 = pvarg;
      v9 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v20 + 640))(ppv, v18, &v59);
    }
  }
  SysFreeString(v18);
  VariantClear(&pvarg);
  if ( v9 < 0 )
    goto LABEL_108;
  v52 = -1;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a1->dwType != 1 )
  {
    if ( a1->dwType == 2 )
    {
      cbDataSize = a1->cbDataSize;
      pvarg.vt = 8209;
      Vector = SafeArrayCreateVector(0x11u, 0, cbDataSize);
      pvarg.llVal = (LONGLONG)Vector;
      if ( !Vector )
        goto LABEL_41;
      *(_QWORD *)pdwSize = 0;
      v9 = SafeArrayAccessData(Vector, (void **)pdwSize);
      if ( v9 < 0 )
        goto LABEL_104;
      memcpy_0(*(void **)pdwSize, a1->pProfileData, a1->cbDataSize);
      v9 = SafeArrayUnaccessData(pvarg.parray);
    }
    else
    {
      v9 = -2147024809;
    }
    if ( v9 < 0 )
      goto LABEL_104;
    goto LABEL_46;
  }
  pProfileData = (const OLECHAR *)a1->pProfileData;
  v22 = a1->cbDataSize >> 1;
  pvarg.vt = 8;
  v23 = SysAllocStringLen(pProfileData, v22);
  pvarg.llVal = (LONGLONG)v23;
  v24 = v23;
  if ( !v23 )
  {
LABEL_41:
    v9 = -2147024882;
    goto LABEL_104;
  }
  FilenameFromPath = GetFilenameFromPath(v23);
  v26 = FilenameFromPath;
  if ( FilenameFromPath )
  {
    if ( FilenameFromPath != v24 )
      goto LABEL_46;
    pdwSize[0] = 520;
    if ( !GetColorDirectoryW(0, psz, pdwSize) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( !LastError )
      {
        v9 = -2147467259;
        goto LABEL_104;
      }
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 < 0 )
        goto LABEL_104;
    }
    v9 = StringCchCatW(psz, 0x104u, L"\\");
    if ( v9 < 0 )
      goto LABEL_104;
    v9 = StringCchCatW(psz, 0x104u, v26);
    if ( v9 < 0 )
      goto LABEL_104;
    SysFreeString(pvarg.bstrVal);
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( pvarg.llVal )
    {
LABEL_46:
      v30 = *(_QWORD *)ppv;
      v59 = pvarg;
      v31 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(v30 + 464))(ppv, &v59, &v52);
      v9 = v31;
      if ( v31 == 1 || !v52 )
      {
        v9 = -2147022885;
        goto LABEL_104;
      }
      if ( v31 < 0 || !(_DWORD)v54 )
        goto LABEL_104;
      v54 = 0;
      CompatibilityMarkupProcessor = CreateCompatibilityMarkupProcessor(v10, v11);
      v33 = v54;
      v9 = CompatibilityMarkupProcessor;
      if ( CompatibilityMarkupProcessor >= 0 )
        v9 = ((__int64 (__fastcall *)(_QWORD, LPVOID))(*v54)[1])(v54, ppv);
      if ( v33 )
        (**v33)(v33, 1);
      if ( v9 < 0 )
        goto LABEL_104;
      v9 = CreateWcsProfileSchemaCache(v10, lpString1, v11, &v61);
      if ( v9 < 0 )
      {
        v6 = v61;
        goto LABEL_104;
      }
      memset(&v59, 0, sizeof(v59));
      VariantInit(&v59);
      v6 = v61;
      v59.vt = 13;
      v59.llVal = v61;
      v34 = *(_QWORD *)ppv;
      pRecInfo = (const OLECHAR *)v59.pRecInfo;
      v35 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(v34 + 624);
      v63 = *(_OWORD *)&v59.vt;
      v9 = v35(ppv, &v63);
      if ( v9 < 0 )
        goto LABEL_104;
      v54 = 0;
      v36 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 632LL))(ppv, &v54);
      v37 = &word_1800884E0;
      v9 = v36;
      if ( (v36 < 0 || v36 == 1) && (_DWORD)bstrString )
      {
        bstrString = 0;
        pdwSize[0] = 0;
        if ( ((int (__fastcall *)(_QWORD, BSTR *))(*v54)[9])(v54, &bstrString) >= 0 )
        {
          if ( a1->dwType == 1 )
          {
            v38 = a1->pProfileData;
            if ( v38 )
            {
              v39 = -1;
              do
                ++v39;
              while ( v38[v39] );
              v40 = 2 * v39 + 2;
            }
            else
            {
              v40 = 0;
            }
            v41 = wil::safe_cast<unsigned int,unsigned __int64,0>(v40);
            v42 = (const OLECHAR *)a1->pProfileData;
          }
          else
          {
            v41 = 2;
            v42 = &word_1800884E0;
          }
          *((_QWORD *)&v63 + 1) = v41;
          *(_QWORD *)&v63 = v42;
          if ( bstrString && *bstrString )
          {
            v43 = -1;
            do
              ++v43;
            while ( bstrString[v43] );
            v44 = wil::safe_cast<unsigned int,unsigned __int64,0>(2 * v43 + 2);
            pRecInfo = bstrString;
          }
          else
          {
            pRecInfo = &word_1800884E0;
            v44 = 2;
          }
          v65 = v44;
          v66 = 0;
          EtwEventWrite(g_etwHandle, INVALID_WCS_PROFILE, 2, &v63);
          SysFreeString(bstrString);
        }
        if ( ((int (__fastcall *)(_QWORD, DWORD *))(*v54)[7])(v54, pdwSize) >= 0 && pdwSize[0] )
        {
          v9 = (int)pdwSize[0] > 0 ? LOWORD(pdwSize[0]) | 0x80070000 : pdwSize[0];
          if ( v9 == -2146697210 )
            v9 = -2147024894;
        }
      }
      if ( v54 )
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v54)[2])(v54);
      if ( v9 < 0 )
        goto LABEL_104;
      bstrString = 0;
      lpString1 = 0;
      v45 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 360LL))(ppv, &bstrString);
      v9 = v45;
      if ( v45 != 1 )
      {
        if ( v45 < 0
          || (v9 = (*(__int64 (__fastcall **)(BSTR, PCNZWCH *))(*(_QWORD *)bstrString + 312LL))(bstrString, &lpString1),
              v9 < 0) )
        {
LABEL_100:
          SysFreeString((BSTR)lpString1);
          if ( bstrString )
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
          goto LABEL_104;
        }
        v46 = &word_1800884E0;
        if ( lpString1 )
          v46 = lpString1;
        if ( CompareStringW(0x7Fu, 0, v46, -1, lpString2, -1) == 2 )
        {
          lpString2 = 0;
          v9 = (*(__int64 (__fastcall **)(BSTR, PCNZWCH *))(*(_QWORD *)bstrString + 328LL))(bstrString, &lpString2);
          if ( v9 >= 0 )
          {
            if ( lpString2 )
              v37 = lpString2;
            v47 = CompareStringW(0x7Fu, 0, v37, -1, v60, -1);
            v48 = v9;
            if ( v47 != 2 )
              v48 = -2147022885;
            v9 = v48;
          }
          SysFreeString((BSTR)lpString2);
          goto LABEL_100;
        }
      }
      v9 = -2147022885;
      goto LABEL_100;
    }
    goto LABEL_41;
  }
  v9 = -2147024809;
LABEL_104:
  VariantClear(&pvarg);
  v49 = ppv;
  if ( v9 >= 0 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
    v49 = ppv;
    *v62 = (struct IXMLDOMDocument2 *)ppv;
  }
  if ( !v6 )
    goto LABEL_109;
  (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v6 + 16LL))(v6);
LABEL_108:
  v49 = ppv;
LABEL_109:
  if ( v49 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800071e4  push    rbp
0x1800071e6  push    rbx
0x1800071e7  push    rsi
0x1800071e8  push    rdi
0x1800071e9  push    r12
0x1800071eb  push    r13
0x1800071ed  push    r14
0x1800071ef  push    r15
0x1800071f1  lea     rbp, [rsp-408h]
0x1800071f9  sub     rsp, 508h
0x180007200  mov     rax, cs:__security_cookie
0x180007207  xor     rax, rsp
0x18000720a  mov     [rbp+440h+var_50], rax
0x180007211  mov     rax, [rbp+440h+arg_20]
0x180007218  xor     esi, esi
0x18000721a  mov     [rbp+440h+var_490], rax
0x18000721e  mov     r14, rcx
0x180007221  mov     dword ptr [rsp+540h+bstrString], r9d
0x180007226  mov     r13d, esi
0x180007229  mov     dword ptr [rsp+540h+var_4F8], r8d
0x18000722e  mov     [rbp+440h+var_498], rsi
0x180007232  lea     eax, [rsi+2]
0x180007235  mov     [rsp+540h+var_510], rsi
0x18000723a  sub     edx, 1
0x18000723d  jz      short loc_1800072B6
0x18000723f  sub     edx, 1
0x180007242  jz      short loc_180007289
0x180007244  cmp     edx, 1
0x180007247  jz      short loc_180007253
0x180007249  mov     ebx, 80070057h
0x18000724e  jmp     loc_180007A69
0x180007253  lea     rsi, qword_18008CA98
0x18000725a  mov     r15d, eax
0x18000725d  mov     [rsp+540h+lpString1], rsi
0x180007262  lea     r12, off_18009E100; "http://schemas.microsoft.com/windows/20"...
0x180007269  lea     rsi, stru_18008E320
0x180007270  lea     rdi, aXmlnsGmmHttpSc; "xmlns:gmm='http://schemas.microsoft.com"...
0x180007277  lea     rax, aGamutmapmodel; "GamutMapModel"
0x18000727e  mov     [rbp+440h+var_4A0], rax
0x180007282  mov     [rsp+540h+lpString2], rsi
0x180007287  jmp     short loc_1800072ED
0x180007289  lea     rsi, qword_18008CAA0
0x180007290  mov     r15d, eax
0x180007293  mov     [rsp+540h+lpString1], rsi
0x180007298  lea     r12, off_18009E0F0; "http://schemas.microsoft.com/windows/20"...
0x18000729f  lea     rsi, stru_18008DEB0
0x1800072a6  lea     rdi, aXmlnsCamHttpSc; "xmlns:cam='http://schemas.microsoft.com"...
0x1800072ad  lea     rax, aColorappearanc; "ColorAppearanceModel"
0x1800072b4  jmp     short loc_18000727E
0x1800072b6  lea     rax, qword_180088280
0x1800072bd  mov     r15d, 3
0x1800072c3  mov     [rsp+540h+lpString1], rax
0x1800072c8  lea     r12, off_18009E0D8; "http://schemas.microsoft.com/windows/20"...
0x1800072cf  lea     rax, aColordevicemod; "ColorDeviceModel"
0x1800072d6  mov     [rbp+440h+var_4A0], rax
0x1800072da  lea     rdi, aXmlnsCdmHttpSc; "xmlns:cdm='http://schemas.microsoft.com"...
0x1800072e1  lea     rax, stru_1800882C0
0x1800072e8  mov     [rsp+540h+lpString2], rax
0x1800072ed  xor     edx, edx; pUnkOuter
0x1800072ef  lea     rax, [rsp+540h+var_510]
0x1800072f4  lea     r9, IID_IXMLDOMDocument2; riid
0x1800072fb  mov     [rsp+540h+ppv], rax; ppv
0x180007300  lea     rcx, CLSID_DOMDocument60; rclsid
0x180007307  lea     r8d, [rdx+1]; dwClsContext
0x18000730b  call    cs:__imp_CoCreateInstance
0x180007311  mov     ebx, eax
0x180007313  test    eax, eax
0x180007315  js      loc_180007A53
0x18000731b  mov     rcx, [rsp+540h+var_510]
0x180007320  xor     edx, edx
0x180007322  mov     rax, [rcx]
0x180007325  mov     rax, [rax+1F8h]
0x18000732c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007331  mov     ebx, eax
0x180007333  test    eax, eax
0x180007335  js      loc_180007A53
0x18000733b  xorps   xmm0, xmm0
0x18000733e  lea     rcx, psz; "SelectionLanguage"
0x180007345  xor     eax, eax
0x180007347  movups  xmmword ptr [rsp+540h+pvarg], xmm0
0x18000734c  mov     qword ptr [rsp+540h+pvarg+10h], rax
0x180007351  call    cs:__imp_SysAllocString
0x180007357  lea     rcx, [rsp+540h+pvarg]; pvarg
0x18000735c  mov     rsi, rax
0x18000735f  call    cs:__imp_VariantInit
0x180007365  mov     eax, 8
0x18000736a  lea     rcx, aXpath; "XPath"
0x180007371  mov     word ptr [rsp+540h+pvarg], ax
0x180007376  call    cs:__imp_SysAllocString
0x18000737c  mov     qword ptr [rsp+540h+pvarg+8], rax
0x180007381  test    rsi, rsi
0x180007384  jz      short loc_18000738B
0x180007386  test    rax, rax
0x180007389  jnz     short loc_180007390
0x18000738b  mov     ebx, 8007000Eh
0x180007390  test    ebx, ebx
0x180007392  js      short loc_1800073C5
0x180007394  mov     rcx, [rsp+540h+var_510]
0x180007399  lea     r8, [rbp+440h+var_4C0]
0x18000739d  movups  xmm0, xmmword ptr [rsp+540h+pvarg]
0x1800073a2  mov     rdx, rsi
0x1800073a5  movsd   xmm1, qword ptr [rsp+540h+pvarg+10h]
0x1800073ab  mov     rax, [rcx]
0x1800073ae  movaps  xmmword ptr [rbp+440h+var_4C0], xmm0
0x1800073b2  movsd   qword ptr [rbp+440h+var_4C0+10h], xmm1
0x1800073b7  mov     rax, [rax+280h]
0x1800073be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c3  mov     ebx, eax
0x1800073c5  mov     rcx, rsi; bstrString
0x1800073c8  call    cs:__imp_SysFreeString
0x1800073ce  lea     rcx, [rsp+540h+pvarg]; pvarg
0x1800073d3  call    cs:__imp_VariantClear
0x1800073d9  test    ebx, ebx
0x1800073db  js      loc_180007A53
0x1800073e1  xorps   xmm0, xmm0
0x1800073e4  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x1800073eb  xor     eax, eax
0x1800073ed  movups  xmmword ptr [rsp+540h+pvarg], xmm0
0x1800073f2  mov     qword ptr [rsp+540h+pvarg+10h], rax
0x1800073f7  call    cs:__imp_SysAllocString
0x1800073fd  lea     rcx, [rsp+540h+pvarg]; pvarg
0x180007402  mov     rsi, rax
0x180007405  call    cs:__imp_VariantInit
0x18000740b  lea     rax, aXmlnsWcsHttpSc; "xmlns:wcs='http://schemas.microsoft.com"...
0x180007412  mov     r9, rdi
0x180007415  lea     r8, aSS_0; "%s %s"
0x18000741c  mov     [rsp+540h+ppv], rax
0x180007421  mov     edx, 208h; unsigned __int64
0x180007426  lea     rcx, [rbp+440h+psz]; unsigned __int16 *
0x18000742a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000742f  mov     ebx, eax
0x180007431  mov     edi, 8
0x180007436  test    eax, eax
0x180007438  js      short loc_180007492
0x18000743a  lea     rcx, [rbp+440h+psz]; psz
0x18000743e  mov     word ptr [rsp+540h+pvarg], di
0x180007443  call    cs:__imp_SysAllocString
0x180007449  mov     qword ptr [rsp+540h+pvarg+8], rax
0x18000744e  test    rsi, rsi
0x180007451  jz      short loc_180007458
0x180007453  test    rax, rax
0x180007456  jnz     short loc_18000745D
0x180007458  mov     ebx, 8007000Eh
0x18000745d  test    ebx, ebx
0x18000745f  js      short loc_180007492
0x180007461  mov     rcx, [rsp+540h+var_510]
0x180007466  lea     r8, [rbp+440h+var_4C0]
0x18000746a  movups  xmm0, xmmword ptr [rsp+540h+pvarg]
0x18000746f  mov     rdx, rsi
0x180007472  movsd   xmm1, qword ptr [rsp+540h+pvarg+10h]
0x180007478  mov     rax, [rcx]
0x18000747b  movaps  xmmword ptr [rbp+440h+var_4C0], xmm0
0x18000747f  movsd   qword ptr [rbp+440h+var_4C0+10h], xmm1
0x180007484  mov     rax, [rax+280h]
0x18000748b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007490  mov     ebx, eax
0x180007492  mov     rcx, rsi; bstrString
0x180007495  call    cs:__imp_SysFreeString
0x18000749b  lea     rcx, [rsp+540h+pvarg]; pvarg
0x1800074a0  call    cs:__imp_VariantClear
0x1800074a6  xor     esi, esi
0x1800074a8  test    ebx, ebx
0x1800074aa  js      loc_180007A53
0x1800074b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800074b4  lea     rcx, [rsp+540h+pvarg]; pvarg
0x1800074b9  mov     [rsp+540h+var_508], ax
0x1800074be  xorps   xmm0, xmm0
0x1800074c1  xor     eax, eax
0x1800074c3  mov     qword ptr [rsp+540h+pvarg+10h], rax
0x1800074c8  movups  xmmword ptr [rsp+540h+pvarg], xmm0
0x1800074cd  call    cs:__imp_VariantInit
0x1800074d3  cmp     dword ptr [r14], 1
0x1800074d7  jnz     loc_1800075C9
0x1800074dd  mov     edx, [r14+10h]
0x1800074e1  mov     rcx, [r14+8]; strIn
0x1800074e5  shr     edx, 1; ui
0x1800074e7  mov     word ptr [rsp+540h+pvarg], di
0x1800074ec  call    cs:__imp_SysAllocStringLen
0x1800074f2  mov     qword ptr [rsp+540h+pvarg+8], rax
0x1800074f7  mov     rbx, rax
0x1800074fa  test    rax, rax
0x1800074fd  jz      loc_1800075F4
0x180007503  mov     rcx, rax; lpStringSource
0x180007506  call    GetFilenameFromPath
0x18000750b  mov     rdi, rax
0x18000750e  test    rax, rax
0x180007511  jnz     short loc_18000751D
0x180007513  mov     ebx, 80070057h
0x180007518  jmp     loc_180007A12
0x18000751d  cmp     rdi, rbx
0x180007520  jnz     loc_180007649
0x180007526  lea     r8, [rsp+540h+pdwSize]; pdwSize
0x18000752b  mov     [rsp+540h+pdwSize], 208h
0x180007533  lea     rdx, [rbp+440h+psz]; pBuffer
0x180007537  xor     ecx, ecx; pMachineName
0x180007539  call    GetColorDirectoryW
0x18000753e  test    eax, eax
0x180007540  jnz     short loc_18000756B
0x180007542  call    cs:__imp_GetLastError
0x180007548  mov     ebx, eax
0x18000754a  test    eax, eax
0x18000754c  jnz     short loc_180007558
0x18000754e  mov     ebx, 80004005h
0x180007553  jmp     loc_180007A12
0x180007558  jle     short loc_180007563
0x18000755a  movzx   ebx, ax
0x18000755d  or      ebx, 80070000h
0x180007563  test    ebx, ebx
0x180007565  js      loc_180007A12
0x18000756b  lea     r8, StringValue; "\\"
0x180007572  mov     edx, 104h; unsigned __int64
0x180007577  lea     rcx, [rbp+440h+psz]; unsigned __int16 *
0x18000757b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007580  mov     ebx, eax
0x180007582  test    eax, eax
0x180007584  js      loc_180007A12
0x18000758a  mov     r8, rdi; unsigned __int16 *
0x18000758d  lea     rcx, [rbp+440h+psz]; unsigned __int16 *
0x180007591  mov     edx, 104h; unsigned __int64
0x180007596  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000759b  mov     ebx, eax
0x18000759d  test    eax, eax
0x18000759f  js      loc_180007A12
0x1800075a5  mov     rcx, qword ptr [rsp+540h+pvarg+8]; bstrString
0x1800075aa  call    cs:__imp_SysFreeString
0x1800075b0  lea     rcx, [rbp+440h+psz]; psz
0x1800075b4  call    cs:__imp_SysAllocString
0x1800075ba  mov     qword ptr [rsp+540h+pvarg+8], rax
0x1800075bf  test    rax, rax
0x1800075c2  jz      short loc_1800075F4
0x1800075c4  jmp     loc_180007649
0x1800075c9  cmp     dword ptr [r14], 2
0x1800075cd  jnz     short loc_18000763C
0x1800075cf  mov     r8d, [r14+10h]; cElements
0x1800075d3  mov     eax, 2011h
0x1800075d8  mov     ecx, 11h; vt
0x1800075dd  mov     word ptr [rsp+540h+pvarg], ax
0x1800075e2  xor     edx, edx; lLbound
0x1800075e4  call    cs:__imp_SafeArrayCreateVector
0x1800075ea  mov     qword ptr [rsp+540h+pvarg+8], rax
0x1800075ef  test    rax, rax
0x1800075f2  jnz     short loc_1800075FE
0x1800075f4  mov     ebx, 8007000Eh
0x1800075f9  jmp     loc_180007A12
0x1800075fe  lea     rdx, [rsp+540h+pdwSize]; ppvData
0x180007603  mov     qword ptr [rsp+540h+pdwSize], rsi
0x180007608  mov     rcx, rax; psa
0x18000760b  call    cs:__imp_SafeArrayAccessData
0x180007611  mov     ebx, eax
0x180007613  test    eax, eax
0x180007615  js      loc_180007A12
0x18000761b  mov     r8d, [r14+10h]; Size
0x18000761f  mov     rdx, [r14+8]; Src
0x180007623  mov     rcx, qword ptr [rsp+540h+pdwSize]; void *
0x180007628  call    memcpy_0
0x18000762d  mov     rcx, qword ptr [rsp+540h+pvarg+8]; psa
0x180007632  call    cs:__imp_SafeArrayUnaccessData
0x180007638  mov     ebx, eax
0x18000763a  jmp     short loc_180007641
0x18000763c  mov     ebx, 80070057h
0x180007641  test    ebx, ebx
0x180007643  js      loc_180007A12
0x180007649  mov     rcx, [rsp+540h+var_510]
0x18000764e  lea     r8, [rsp+540h+var_508]
0x180007653  movups  xmm0, xmmword ptr [rsp+540h+pvarg]
0x180007658  lea     rdx, [rbp+440h+var_4C0]
0x18000765c  movsd   xmm1, qword ptr [rsp+540h+pvarg+10h]
0x180007662  mov     rax, [rcx]
0x180007665  movaps  xmmword ptr [rbp+440h+var_4C0], xmm0
0x180007669  movsd   qword ptr [rbp+440h+var_4C0+10h], xmm1
0x18000766e  mov     rax, [rax+1D0h]
0x180007675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767a  mov     ebx, eax
0x18000767c  cmp     eax, 1
0x18000767f  jz      loc_180007A0D
0x180007685  cmp     si, [rsp+540h+var_508]
0x18000768a  jz      loc_180007A0D
0x180007690  test    eax, eax
0x180007692  js      loc_180007A12
0x180007698  cmp     dword ptr [rsp+540h+var_4F8], esi
0x18000769c  jz      loc_180007A12
0x1800076a2  lea     r8, [rsp+540h+var_4F8]
0x1800076a7  mov     [rsp+540h+var_4F8], rsi
0x1800076ac  mov     rdx, r12; unsigned __int16 **
0x1800076af  mov     ecx, r15d; int
0x1800076b2  call    CreateCompatibilityMarkupProcessor
0x1800076b7  mov     rdi, [rsp+540h+var_4F8]
0x1800076bc  mov     ebx, eax
0x1800076be  test    eax, eax
0x1800076c0  js      short loc_1800076D8
0x1800076c2  mov     rax, [rdi]
0x1800076c5  mov     rcx, rdi
0x1800076c8  mov     rdx, [rsp+540h+var_510]
0x1800076cd  mov     rax, [rax+8]
0x1800076d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d6  mov     ebx, eax
0x1800076d8  test    rdi, rdi
0x1800076db  jz      short loc_1800076F0
0x1800076dd  mov     rax, [rdi]
0x1800076e0  mov     edx, 1
  ... truncated ...
```
