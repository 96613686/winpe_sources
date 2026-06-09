# CNodeChangeSetBuilder::ProcessCacheEntry(IConfigManager2 *,IConfigNode *,ushort const *,unsigned __int64,int *,ushort * *,tagVARIANT *,ConfigDataType *)

- ea: `0x18005e334`
- end: `0x18005ec68`
- name: `?ProcessCacheEntry@CNodeChangeSetBuilder@@SAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBG_KPEAHPEAPEAGPEAUtagVARIANT@@PEAW4ConfigDataType@@@Z`
- size: `2356`
- prototype: `static int(struct IConfigManager2 *, struct IConfigNode *, const unsigned __int16 *, unsigned __int64, int *, unsigned __int16 **, struct tagVARIANT *, enum ConfigDataType *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005ce1c`

## callees

- `0x1800091b0`
- `0x18000d4d4`
- `0x18000db4c`
- `0x180022e10`
- `0x180025a9c`
- `0x18002dc94`
- `0x18005a298`
- `0x18005a32c`
- `0x18005a724`
- `0x18005ade0`
- `0x18005bc4c`
- `0x18005c234`
- `0x18005cd28`
- `0x18005dcfc`
- `0x18005e334`
- `0x180060150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005e6cd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005e6cd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18005e8bc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18005e8bc`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e87a`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ea30`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ea5c`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e87a`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ea30`
- `OLEAUT32!__imp_SysStringLen` at `0x18005ea5c`
- `OLEAUT32!__imp_VariantInit` at `0x18005e3dc`
- `OLEAUT32!__imp_VariantInit` at `0x18005e54a`
- `OLEAUT32!__imp_VariantInit` at `0x18005e55c`
- `OLEAUT32!__imp_VariantInit` at `0x18005e599`
- `OLEAUT32!__imp_VariantInit` at `0x18005e3dc`
- `OLEAUT32!__imp_VariantInit` at `0x18005e54a`
- `OLEAUT32!__imp_VariantInit` at `0x18005e55c`
- `OLEAUT32!__imp_VariantInit` at `0x18005e599`
- `OLEAUT32!__imp_VariantClear` at `0x18005e733`
- `OLEAUT32!__imp_VariantClear` at `0x18005e745`
- `OLEAUT32!__imp_VariantClear` at `0x18005e757`
- `OLEAUT32!__imp_VariantClear` at `0x18005eb8f`
- `OLEAUT32!__imp_VariantClear` at `0x18005eba1`
- `OLEAUT32!__imp_VariantClear` at `0x18005ebb3`
- `OLEAUT32!__imp_VariantClear` at `0x18005ebc4`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec16`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec28`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec3a`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec4d`
- `OLEAUT32!__imp_VariantClear` at `0x18005e733`
- `OLEAUT32!__imp_VariantClear` at `0x18005e745`
- `OLEAUT32!__imp_VariantClear` at `0x18005e757`
- `OLEAUT32!__imp_VariantClear` at `0x18005eb8f`
- `OLEAUT32!__imp_VariantClear` at `0x18005eba1`
- `OLEAUT32!__imp_VariantClear` at `0x18005ebb3`
- `OLEAUT32!__imp_VariantClear` at `0x18005ebc4`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec16`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec28`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec3a`
- `OLEAUT32!__imp_VariantClear` at `0x18005ec4d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005e9ca`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005ea05`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005e9ca`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005ea05`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e7c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e7fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ea90`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e7c7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e7fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ea90`
- `DMCmnUtils!InvStrCmpIW` at `0x18005e4c8`
- `DMCmnUtils!InvStrCmpIW` at `0x18005e50f`
- `DMCmnUtils!InvStrCmpIW` at `0x18005e4c8`
- `DMCmnUtils!InvStrCmpIW` at `0x18005e50f`

## string_xrefs

- `0x18005e38b`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005e454`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005e497`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005e70e`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005e784`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005e8eb`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005eaeb`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005eb3e`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005e3f2`: `NodeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CNodeChangeSetBuilder::ProcessCacheEntry(
        struct IConfigManager2 *a1,
        struct IConfigNode *a2,
        const unsigned __int16 *a3,
        int a4,
        int *a5,
        unsigned __int16 **a6,
        struct tagVARIANT *a7,
        enum ConfigDataType *a8)
{
  enum ConfigDataType *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int CspNodeValue; // eax
  unsigned __int16 *v16; // rdi
  int v17; // eax
  __int64 v18; // rdx
  BSTR bstrVal; // rax
  BSTR v20; // rcx
  int v21; // r8d
  struct IConfigNode *v22; // rdx
  int v23; // eax
  bool v24; // zf
  int v25; // eax
  int v26; // edx
  int v27; // ecx
  unsigned int v28; // edi
  wchar_t *v29; // rax
  __int64 v30; // rdx
  const WCHAR *v31; // rsi
  int v32; // eax
  int v33; // eax
  int cchCount2; // ebx
  int v35; // esi
  UINT v36; // ebx
  int v37; // eax
  __int64 v38; // rdx
  LONGLONG v39; // rbx
  BSTR v40; // rax
  BSTR v41; // rax
  int v42; // edx
  int v43; // ecx
  LONGLONG llVal; // rbx
  UINT v45; // eax
  const WCHAR *v46; // rsi
  const WCHAR *v47; // r14
  int v48; // edi
  LONGLONG v49; // rbx
  UINT v50; // eax
  int v51; // eax
  int v52; // eax
  int lpString2; // [rsp+20h] [rbp-D9h]
  int lpString2a; // [rsp+20h] [rbp-D9h]
  PCNZWCH lpString2b; // [rsp+20h] [rbp-D9h]
  int lpString2c; // [rsp+20h] [rbp-D9h]
  int lpString2d; // [rsp+20h] [rbp-D9h]
  UINT ui[2]; // [rsp+30h] [rbp-C9h] BYREF
  VARIANTARG pvarSrc; // [rsp+38h] [rbp-C1h] BYREF
  VARIANTARG pvargDest; // [rsp+50h] [rbp-A9h] BYREF
  struct IConfigManager2 *v61; // [rsp+68h] [rbp-91h] BYREF
  void *Block; // [rsp+70h] [rbp-89h] BYREF
  VARIANTARG v63; // [rsp+78h] [rbp-81h] BYREF
  _QWORD v64[6]; // [rsp+90h] [rbp-69h] BYREF
  char v65; // [rsp+C0h] [rbp-39h]
  VARIANTARG pvarg; // [rsp+C8h] [rbp-31h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-19h] BYREF
  enum ConfigDataType *v68; // [rsp+E8h] [rbp-11h] BYREF
  unsigned __int16 **v69; // [rsp+F0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+3Fh]

  v61 = a1;
  v69 = a6;
  v11 = a8;
  v68 = a8;
  if ( !a5 )
  {
    v12 = 834;
LABEL_3:
    v13 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
      (const char *)0x80070057LL,
      lpString2);
    return v13;
  }
  *a5 = 1;
  if ( !a1 )
  {
    v12 = 837;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v12 = 838;
    goto LABEL_3;
  }
  v67 = 0;
  if ( a6 )
  {
    *a6 = 0;
    v11 = v68;
  }
  if ( v11 )
    *(_DWORD *)v11 = 10;
  VariantInit(&pvarg);
  CspNodeValue = GetCspNodeValue(v61, a2, L"NodeUri", &pvarg, 0);
  if ( CspNodeValue == -2046820316 )
  {
    *a5 = 0;
LABEL_103:
    v13 = 0;
    goto LABEL_104;
  }
  if ( CspNodeValue >= 0 && pvarg.vt == 8 )
  {
    wil::make_unique_nothrow<unsigned short [0]>(&Block, 260);
    v16 = (unsigned __int16 *)Block;
    if ( !Block )
    {
      v13 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x368,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
        (const char *)0x8007000ELL,
        lpString2a);
LABEL_104:
      VariantClear(&pvarg);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
      return v13;
    }
    lpString2b = (PCNZWCH)L"ChangedNodes";
    v17 = StringCchPrintfW((unsigned __int16 *)Block, 0x104u, L"%s/%s", a3);
    v13 = v17;
    if ( v17 < 0 )
    {
      v18 = 874;
      goto LABEL_21;
    }
    if ( !InvStrCmpIW(pvarg.bstrVal, v16) )
      goto LABEL_27;
    lpString2b = L"ChangedNodesData";
    v17 = StringCchPrintfW(v16, 0x104u, L"%s/%s", a3);
    v13 = v17;
    if ( v17 < 0 )
    {
      v18 = 881;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
        (const char *)(unsigned int)v17,
        (int)lpString2b);
      if ( v16 )
        operator delete(v16);
      goto LABEL_104;
    }
    if ( !InvStrCmpIW(pvarg.bstrVal, v16) )
    {
LABEL_27:
      *a5 = 0;
      if ( v16 )
        operator delete(v16);
      goto LABEL_98;
    }
    if ( v16 )
      operator delete(v16);
    VariantInit(&pvargDest);
    VariantInit(&v63);
    if ( (int)GetCspNodeValue(v61, a2, L"ExpectedValue", &pvargDest, &v63) < 0 )
    {
LABEL_102:
      VariantClear(&v63);
      VariantClear(&pvargDest);
      goto LABEL_103;
    }
    VariantInit(&pvarSrc);
    v64[0] = &v69;
    v64[1] = &pvarg;
    v64[2] = &a7;
    v64[3] = &pvarSrc;
    v64[4] = &v68;
    v64[5] = &v61;
    v65 = 1;
    bstrVal = v63.bstrVal;
    if ( v63.vt != 8 )
      goto LABEL_59;
    v20 = v63.bstrVal;
    do
    {
      v21 = *(unsigned __int16 *)((char *)L"application/x-nodemon-nonexistent" + (_QWORD)v20 - v63.llVal);
      v22 = (struct IConfigNode *)((unsigned int)*v20 - v21);
      if ( (_DWORD)v22 )
        break;
      ++v20;
    }
    while ( v21 );
    if ( !(_DWORD)v22 )
    {
      ui[0] = 0;
      if ( (int)IsCspNodeForUriExists(v61, v22, pvarg.bstrVal, (int *)ui) >= 0 && ui[0] )
      {
        v23 = GetCspNodeValue(v61, 0, pvarg.bstrVal, &pvarSrc, 0);
        if ( v23 >= 0 || v23 == -2046820335 || (v24 = v23 == -2147467263, v25 = 0, v24) )
          v25 = 1;
      }
      else
      {
        v25 = 0;
      }
      *a5 = v25;
      v65 = 0;
      lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
      goto LABEL_101;
    }
    do
    {
      v26 = *(unsigned __int16 *)((char *)L"application/x-nodemon-sha256" + (_QWORD)bstrVal - v63.llVal);
      v27 = *bstrVal - v26;
      if ( v27 )
        break;
      ++bstrVal;
    }
    while ( v26 );
    if ( v27 )
    {
LABEL_59:
      v35 = GetCspNodeValue(v61, 0, pvarg.bstrVal, &pvarSrc, 0);
      if ( pvarSrc.vt == 8 )
      {
        Block = pvarSrc.bstrVal;
        v36 = SysStringLen(pvarSrc.bstrVal);
        ui[0] = v36;
        v37 = Trim(&Block, ui);
        v38 = ui[0];
        if ( !v37 || ui[0] != v36 )
        {
          v39 = 0;
          *(_QWORD *)ui = 0;
          if ( v37 )
          {
            v40 = SysAllocStringLen((const OLECHAR *)Block, v38);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              ui,
              v40);
            v39 = *(_QWORD *)ui;
            if ( !*(_QWORD *)ui )
            {
              v13 = -2147024882;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x42B,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                (const char *)0x8007000ELL,
                lpString2d);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ui);
              v65 = 0;
              lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
              goto LABEL_51;
            }
          }
          wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(
            &pvarSrc,
            v38);
          *(_QWORD *)ui = 0;
          pvarSrc.llVal = v39;
          pvarSrc.vt = 8;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ui);
        }
      }
      if ( v63.vt == 8 )
      {
        v41 = v63.bstrVal;
        do
        {
          v42 = *(unsigned __int16 *)((char *)L"application/x-nodemon-nonexistent" + (_QWORD)v41 - v63.llVal);
          v43 = *v41 - v42;
          if ( v43 )
            break;
          ++v41;
        }
        while ( v42 );
        if ( !v43 )
        {
          if ( v35 < 0 )
            *a5 = 0;
          goto LABEL_100;
        }
      }
      if ( v35 < 0 )
      {
LABEL_100:
        v65 = 0;
        lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
LABEL_101:
        VariantClear(&pvarSrc);
        goto LABEL_102;
      }
    }
    else
    {
      v28 = 0;
      v29 = wcsstr(pvarg.bstrVal, L"?");
      v31 = v29;
      if ( v29 )
      {
        Block = 0;
        ui[0] = 0;
        v32 = StringCchLengthW(v29, 0x7FFFFFFFu, (unsigned __int64 *)&Block);
        v13 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3E9,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
            (const char *)(unsigned int)v32,
            lpString2c);
          v65 = 0;
          lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
LABEL_51:
          VariantClear(&pvarSrc);
          VariantClear(&v63);
          VariantClear(&pvargDest);
          goto LABEL_104;
        }
        v33 = UIntPtrToInt((unsigned __int64)Block, (int *)ui);
        v13 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3EB,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
            (const char *)(unsigned int)v33,
            lpString2c);
          v65 = 0;
          lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
          goto LABEL_51;
        }
        cchCount2 = ui[0];
        if ( CompareStringW(0x7Fu, 1u, L"?list=structData", 16, v31, ui[0]) == 2 )
          v28 = 2;
        else
          v28 = CompareStringW(0x7Fu, 1u, L"?list=struct", 12, v31, cchCount2) == 2;
      }
      lpString2d = a4;
      if ( (int)CNodeChangeSetBuilder::GetCspNodeValueHash(v61, v30, pvarg.llVal, v28) < 0 )
        goto LABEL_100;
    }
    if ( pvargDest.vt == 11 || pvarSrc.vt == 11 )
    {
      v51 = CoerceBoolToInt(&pvargDest);
      v13 = v51;
      if ( v51 == -2147352571 )
        goto LABEL_100;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x454,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
          (const char *)(unsigned int)v51,
          lpString2d);
        v65 = 0;
        lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
        goto LABEL_51;
      }
      v52 = CoerceBoolToInt(&pvarSrc);
      v13 = v52;
      if ( v52 == -2147352571 )
        goto LABEL_100;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
          (const char *)(unsigned int)v52,
          lpString2d);
        v65 = 0;
        lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
        goto LABEL_51;
      }
      if ( pvarSrc.lVal )
      {
        if ( !pvargDest.lVal )
          goto LABEL_100;
      }
      else if ( pvargDest.lVal )
      {
        goto LABEL_100;
      }
    }
    else
    {
      if ( pvargDest.vt != 8 && VariantChangeType(&pvargDest, &pvargDest, 0, 8u) < 0
        || pvarSrc.vt != 8 && VariantChangeType(&pvarSrc, &pvarSrc, 0, 8u) < 0 )
      {
        goto LABEL_100;
      }
      llVal = pvargDest.llVal;
      v45 = SysStringLen(pvargDest.bstrVal);
      v46 = &Class;
      v47 = &Class;
      if ( llVal )
        v47 = (const WCHAR *)llVal;
      v48 = llVal != 0 ? v45 : 0;
      v49 = pvarSrc.llVal;
      v50 = SysStringLen(pvarSrc.bstrVal);
      if ( v49 )
        v46 = (const WCHAR *)v49;
      if ( CompareStringW(0x7Fu, 1u, v47, v48, v46, v49 != 0 ? v50 : 0) != 2 )
        goto LABEL_100;
    }
    *a5 = 0;
    v65 = 0;
    lambda_21da5d9a6b90ddf51d45a9afba6e8ba1_::operator()(v64);
    VariantClear(&pvarSrc);
    VariantClear(&v63);
    VariantClear(&pvargDest);
  }
LABEL_98:
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v67);
  return 0;
}

```

## disassembly

```asm
0x18005e334  mov     [rsp-8+arg_18], rbx
0x18005e339  push    rbp
0x18005e33a  push    rsi
0x18005e33b  push    rdi
0x18005e33c  push    r12
0x18005e33e  push    r13
0x18005e340  push    r14
0x18005e342  push    r15
0x18005e344  lea     rbp, [rsp-7]
0x18005e349  sub     rsp, 100h
0x18005e350  mov     r12, r9
0x18005e353  mov     rsi, r8
0x18005e356  mov     r14, rdx
0x18005e359  mov     rdx, [rbp+37h+arg_28]
0x18005e35d  mov     [rsp+130h+var_C8], rcx
0x18005e362  mov     r15, [rbp+37h+arg_20]
0x18005e366  mov     [rbp+37h+var_40], rdx
0x18005e36a  mov     rax, [rbp+37h+arg_38]
0x18005e36e  mov     [rbp+37h+var_48], rax
0x18005e372  xor     r13d, r13d
0x18005e375  test    r15, r15
0x18005e378  jnz     short loc_18005E39E
0x18005e37a  mov     edx, 342h; void *
0x18005e37f  mov     ebx, 80070057h
0x18005e384  mov     rcx, [rbp+3Fh]; this
0x18005e388  mov     r9d, ebx; char *
0x18005e38b  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005e392  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e397  mov     eax, ebx
0x18005e399  jmp     loc_18005EBDC
0x18005e39e  mov     dword ptr [r15], 1
0x18005e3a5  test    rcx, rcx
0x18005e3a8  jnz     short loc_18005E3B1
0x18005e3aa  mov     edx, 345h
0x18005e3af  jmp     short loc_18005E37F
0x18005e3b1  test    rsi, rsi
0x18005e3b4  jnz     short loc_18005E3BD
0x18005e3b6  mov     edx, 346h
0x18005e3bb  jmp     short loc_18005E37F
0x18005e3bd  mov     [rbp+37h+var_50], r13
0x18005e3c1  test    rdx, rdx
0x18005e3c4  jz      short loc_18005E3CD
0x18005e3c6  mov     [rdx], r13
0x18005e3c9  mov     rax, [rbp+37h+var_48]
0x18005e3cd  test    rax, rax
0x18005e3d0  jz      short loc_18005E3D8
0x18005e3d2  mov     dword ptr [rax], 0Ah
0x18005e3d8  lea     rcx, [rbp+37h+pvarg]; pvarg
0x18005e3dc  call    cs:__imp_VariantInit
0x18005e3e3  nop     dword ptr [rax+rax+00h]
0x18005e3e8  nop
0x18005e3e9  mov     [rsp+130h+lpString2], r13; int
0x18005e3ee  lea     r9, [rbp+37h+pvarg]; struct tagVARIANT *
0x18005e3f2  lea     r8, ?c_szCacheEntryUri@CNodeChangeSetBuilder@@2QBGB; "NodeUri"
0x18005e3f9  mov     rdx, r14; struct IConfigNode *
0x18005e3fc  mov     rcx, [rsp+130h+var_C8]; struct IConfigManager2 *
0x18005e401  call    ?GetCspNodeValue@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAUtagVARIANT@@3@Z; GetCspNodeValue(IConfigManager2 *,IConfigNode *,ushort const *,tagVARIANT *,tagVARIANT *)
0x18005e406  cmp     eax, 86000024h
0x18005e40b  jnz     short loc_18005E415
0x18005e40d  mov     [r15], r13d
0x18005e410  jmp     loc_18005EC46
0x18005e415  test    eax, eax
0x18005e417  js      loc_18005EBC0
0x18005e41d  mov     eax, 8
0x18005e422  cmp     word ptr [rbp+37h+pvarg], ax
0x18005e426  jnz     loc_18005EBC0
0x18005e42c  mov     ebx, 104h
0x18005e431  mov     edx, ebx
0x18005e433  lea     rcx, [rsp+130h+Block]
0x18005e438  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18005e43d  nop
0x18005e43e  mov     rdi, [rsp+130h+Block]
0x18005e443  test    rdi, rdi
0x18005e446  jnz     short loc_18005E46B
0x18005e448  mov     rcx, [rbp+3Fh]; this
0x18005e44c  mov     ebx, 8007000Eh
0x18005e451  mov     r9d, ebx; char *
0x18005e454  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005e45b  mov     edx, 368h; void *
0x18005e460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e465  nop
0x18005e466  jmp     loc_18005EC49
0x18005e46b  lea     rax, ?c_szChangedNodes@CNodeChangeSetBuilder@@2QBGB; "ChangedNodes"
0x18005e472  mov     [rsp+130h+lpString2], rax; int
0x18005e477  mov     r9, rsi
0x18005e47a  lea     r8, aSS; "%s/%s"
0x18005e481  mov     rdx, rbx; unsigned __int64
0x18005e484  mov     rcx, rdi; unsigned __int16 *
0x18005e487  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e48c  mov     ebx, eax
0x18005e48e  test    eax, eax
0x18005e490  jns     short loc_18005E4C1
0x18005e492  mov     edx, 36Ah; void *
0x18005e497  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005e49e  mov     r9d, eax; char *
0x18005e4a1  mov     rcx, [rbp+3Fh]; this
0x18005e4a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e4aa  nop
0x18005e4ab  test    rdi, rdi
0x18005e4ae  jz      loc_18005EC49
0x18005e4b4  mov     rcx, rdi; Block
0x18005e4b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005e4bc  jmp     loc_18005EC49
0x18005e4c1  mov     rdx, rdi
0x18005e4c4  mov     rcx, qword ptr [rbp+37h+pvarg+8]
0x18005e4c8  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18005e4cf  nop     dword ptr [rax+rax+00h]
0x18005e4d4  test    eax, eax
0x18005e4d6  jz      short loc_18005E51F
0x18005e4d8  lea     rax, ?c_szChangedNodesData@CNodeChangeSetBuilder@@2QBGB; "ChangedNodesData"
0x18005e4df  mov     [rsp+130h+lpString2], rax
0x18005e4e4  mov     r9, rsi
0x18005e4e7  lea     r8, aSS; "%s/%s"
0x18005e4ee  mov     edx, 104h; unsigned __int64
0x18005e4f3  mov     rcx, rdi; unsigned __int16 *
0x18005e4f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e4fb  mov     ebx, eax
0x18005e4fd  test    eax, eax
0x18005e4ff  jns     short loc_18005E508
0x18005e501  mov     edx, 371h
0x18005e506  jmp     short loc_18005E497
0x18005e508  mov     rdx, rdi
0x18005e50b  mov     rcx, qword ptr [rbp+37h+pvarg+8]
0x18005e50f  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18005e516  nop     dword ptr [rax+rax+00h]
0x18005e51b  test    eax, eax
0x18005e51d  jnz     short loc_18005E538
0x18005e51f  mov     [r15], r13d
0x18005e522  test    rdi, rdi
0x18005e525  jz      loc_18005EBC0
0x18005e52b  mov     rcx, rdi; Block
0x18005e52e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005e533  jmp     loc_18005EBC0
0x18005e538  test    rdi, rdi
0x18005e53b  jz      short loc_18005E545
0x18005e53d  mov     rcx, rdi; Block
0x18005e540  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005e545  lea     rcx, [rsp+130h+pvargDest]; pvarg
0x18005e54a  call    cs:__imp_VariantInit
0x18005e551  nop     dword ptr [rax+rax+00h]
0x18005e556  nop
0x18005e557  lea     rcx, [rsp+130h+var_B8]; pvarg
0x18005e55c  call    cs:__imp_VariantInit
0x18005e563  nop     dword ptr [rax+rax+00h]
0x18005e568  nop
0x18005e569  lea     rax, [rsp+130h+var_B8]
0x18005e56e  mov     [rsp+130h+lpString2], rax; int
0x18005e573  lea     r9, [rsp+130h+pvargDest]; struct tagVARIANT *
0x18005e578  lea     r8, ?c_szCacheEntryExpectedValue@CNodeChangeSetBuilder@@2QBGB; "ExpectedValue"
0x18005e57f  mov     rdx, r14; struct IConfigNode *
0x18005e582  mov     rcx, [rsp+130h+var_C8]; struct IConfigManager2 *
0x18005e587  call    ?GetCspNodeValue@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAUtagVARIANT@@3@Z; GetCspNodeValue(IConfigManager2 *,IConfigNode *,ushort const *,tagVARIANT *,tagVARIANT *)
0x18005e58c  test    eax, eax
0x18005e58e  js      loc_18005EC23
0x18005e594  lea     rcx, [rsp+130h+pvarSrc]; pvarg
0x18005e599  call    cs:__imp_VariantInit
0x18005e5a0  nop     dword ptr [rax+rax+00h]
0x18005e5a5  nop
0x18005e5a6  lea     rax, [rbp+37h+var_40]
0x18005e5aa  mov     [rbp+37h+var_A0], rax
0x18005e5ae  lea     rax, [rbp+37h+pvarg]
0x18005e5b2  mov     [rbp+37h+var_98], rax
0x18005e5b6  lea     rax, [rbp+37h+arg_30]
0x18005e5ba  mov     [rbp+37h+var_90], rax
0x18005e5be  lea     rax, [rsp+130h+pvarSrc]
0x18005e5c3  mov     [rbp+37h+var_88], rax
0x18005e5c7  lea     rax, [rbp+37h+var_48]
0x18005e5cb  mov     [rbp+37h+var_80], rax
0x18005e5cf  lea     rax, [rsp+130h+var_C8]
0x18005e5d4  mov     [rbp+37h+var_78], rax
0x18005e5d8  mov     ebx, 1
0x18005e5dd  mov     [rbp+37h+var_70], bl
0x18005e5e0  lea     rdi, aApplicationXNo_1; "application/x-nodemon-nonexistent"
0x18005e5e7  mov     rax, qword ptr [rbp+37h+var_B8+8]
0x18005e5eb  lea     r14d, [rbx+7]
0x18005e5ef  cmp     word ptr [rsp+130h+var_B8], r14w
0x18005e5f5  jnz     loc_18005E848
0x18005e5fb  mov     rcx, rax
0x18005e5fe  mov     r9, rdi
0x18005e601  sub     r9, rax
0x18005e604  movzx   edx, word ptr [rcx]
0x18005e607  movzx   r8d, word ptr [rcx+r9]
0x18005e60c  sub     edx, r8d; struct IConfigNode *
0x18005e60f  jnz     short loc_18005E61A
0x18005e611  add     rcx, 2
0x18005e615  test    r8d, r8d
0x18005e618  jnz     short loc_18005E604
0x18005e61a  test    edx, edx
0x18005e61c  jnz     short loc_18005E68D
0x18005e61e  mov     [rsp+130h+ui], r13d
0x18005e623  lea     r9, [rsp+130h+ui]; int *
0x18005e628  mov     r8, qword ptr [rbp+37h+pvarg+8]; unsigned __int16 *
0x18005e62c  mov     rcx, [rsp+130h+var_C8]; struct IConfigManager2 *
0x18005e631  call    ?IsCspNodeForUriExists@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAH@Z; IsCspNodeForUriExists(IConfigManager2 *,IConfigNode *,ushort const *,int *)
0x18005e636  test    eax, eax
0x18005e638  js      short loc_18005E674
0x18005e63a  cmp     [rsp+130h+ui], r13d
0x18005e63f  jz      short loc_18005E674
0x18005e641  mov     [rsp+130h+lpString2], r13; pvarg
0x18005e646  lea     r9, [rsp+130h+pvarSrc]; struct tagVARIANT *
0x18005e64b  mov     r8, qword ptr [rbp+37h+pvarg+8]; unsigned __int16 *
0x18005e64f  xor     edx, edx; struct IConfigNode *
0x18005e651  mov     rcx, [rsp+130h+var_C8]; struct IConfigManager2 *
0x18005e656  call    ?GetCspNodeValue@@YAJPEAUIConfigManager2@@PEAUIConfigNode@@PEBGPEAUtagVARIANT@@3@Z; GetCspNodeValue(IConfigManager2 *,IConfigNode *,ushort const *,tagVARIANT *,tagVARIANT *)
0x18005e65b  test    eax, eax
0x18005e65d  jns     short loc_18005E670
0x18005e65f  cmp     eax, 86000011h
0x18005e664  jz      short loc_18005E670
0x18005e666  cmp     eax, 80004001h
0x18005e66b  mov     eax, r13d
0x18005e66e  jnz     short loc_18005E677
0x18005e670  mov     eax, ebx
0x18005e672  jmp     short loc_18005E677
0x18005e674  mov     eax, r13d
0x18005e677  mov     [r15], eax
0x18005e67a  mov     [rbp+37h+var_70], r13b
0x18005e67e  lea     rcx, [rbp+37h+var_A0]
0x18005e682  call    _lambda_21da5d9a6b90ddf51d45a9afba6e8ba1___operator__
0x18005e687  nop
0x18005e688  jmp     loc_18005EC11
0x18005e68d  cmp     word ptr [rsp+130h+var_B8], r14w
0x18005e693  jnz     loc_18005E848
0x18005e699  lea     r8, aApplicationXNo_2; "application/x-nodemon-sha256"
0x18005e6a0  sub     r8, rax
0x18005e6a3  movzx   ecx, word ptr [rax]
0x18005e6a6  movzx   edx, word ptr [rax+r8]
0x18005e6ab  sub     ecx, edx
0x18005e6ad  jnz     short loc_18005E6B7
0x18005e6af  add     rax, 2
0x18005e6b3  test    edx, edx
0x18005e6b5  jnz     short loc_18005E6A3
0x18005e6b7  test    ecx, ecx
0x18005e6b9  jnz     loc_18005E848
0x18005e6bf  mov     edi, r13d
0x18005e6c2  lea     rdx, SubStr; "?"
0x18005e6c9  mov     rcx, qword ptr [rbp+37h+pvarg+8]; Str
0x18005e6cd  call    cs:__imp_wcsstr
0x18005e6d4  nop     dword ptr [rax+rax+00h]
0x18005e6d9  mov     rsi, rax
0x18005e6dc  test    rax, rax
0x18005e6df  jz      loc_18005E80D
0x18005e6e5  mov     [rsp+130h+Block], r13
0x18005e6ea  mov     [rsp+130h+ui], r13d
0x18005e6ef  lea     r8, [rsp+130h+Block]; unsigned __int64 *
0x18005e6f4  mov     edx, 7FFFFFFFh; unsigned __int64
0x18005e6f9  mov     rcx, rax; unsigned __int16 *
0x18005e6fc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005e701  mov     ebx, eax
0x18005e703  test    eax, eax
0x18005e705  jns     short loc_18005E768
0x18005e707  mov     rcx, [rbp+3Fh]; this
0x18005e70b  mov     r9d, eax; char *
0x18005e70e  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005e715  mov     edx, 3E9h; void *
0x18005e71a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e71f  nop
0x18005e720  mov     [rbp+37h+var_70], r13b
0x18005e724  lea     rcx, [rbp+37h+var_A0]
0x18005e728  call    _lambda_21da5d9a6b90ddf51d45a9afba6e8ba1___operator__
0x18005e72d  nop
0x18005e72e  lea     rcx, [rsp+130h+pvarSrc]; pvarg
0x18005e733  call    cs:__imp_VariantClear
0x18005e73a  nop     dword ptr [rax+rax+00h]
0x18005e73f  nop
0x18005e740  lea     rcx, [rsp+130h+var_B8]; pvarg
0x18005e745  call    cs:__imp_VariantClear
0x18005e74c  nop     dword ptr [rax+rax+00h]
0x18005e751  nop
0x18005e752  lea     rcx, [rsp+130h+pvargDest]; pvarg
0x18005e757  call    cs:__imp_VariantClear
0x18005e75e  nop     dword ptr [rax+rax+00h]
0x18005e763  jmp     loc_18005EC49
0x18005e768  lea     rdx, [rsp+130h+ui]; int *
0x18005e76d  mov     rcx, [rsp+130h+Block]; unsigned __int64
0x18005e772  call    ?UIntPtrToInt@@YAJ_KPEAH@Z; UIntPtrToInt(unsigned __int64,int *)
0x18005e777  mov     ebx, eax
0x18005e779  test    eax, eax
0x18005e77b  jns     short loc_18005E7A6
0x18005e77d  mov     rcx, [rbp+3Fh]; this
0x18005e781  mov     r9d, eax; char *
0x18005e784  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005e78b  mov     edx, 3EBh; void *
0x18005e790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e795  nop
0x18005e796  mov     [rbp+37h+var_70], r13b
0x18005e79a  lea     rcx, [rbp+37h+var_A0]
0x18005e79e  call    _lambda_21da5d9a6b90ddf51d45a9afba6e8ba1___operator__
0x18005e7a3  nop
0x18005e7a4  jmp     short loc_18005E72E
0x18005e7a6  mov     ebx, [rsp+130h+ui]
0x18005e7aa  mov     [rsp+130h+cchCount2], ebx; cchCount2
0x18005e7ae  mov     [rsp+130h+lpString2], rsi; lpString2
0x18005e7b3  mov     r9d, 10h; cchCount1
0x18005e7b9  lea     r8, aListStructdata_0; "?list=structData"
0x18005e7c0  lea     edx, [r9-0Fh]; dwCmpFlags
0x18005e7c4  lea     ecx, [rdx+7Eh]; Locale
0x18005e7c7  call    cs:__imp_CompareStringW
0x18005e7ce  nop     dword ptr [rax+rax+00h]
0x18005e7d3  cmp     eax, 2
0x18005e7d6  jnz     short loc_18005E7DC
  ... truncated ...
```
