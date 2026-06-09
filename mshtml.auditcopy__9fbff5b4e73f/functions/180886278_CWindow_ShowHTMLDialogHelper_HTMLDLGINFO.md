# CWindow::ShowHTMLDialogHelper(HTMLDLGINFO *)

- ea: `0x180886278`
- end: `0x180886b5e`
- name: `?ShowHTMLDialogHelper@CWindow@@QEAAJPEAUHTMLDLGINFO@@@Z`
- size: `2278`
- prototype: `__int64 __fastcall(CWindow *__hidden this, struct HTMLDLGINFO *)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180897520`
- `0x1808975e0`

## callees

- `0x18000224c`
- `0x180012dac`
- `0x18005e648`
- `0x1800ea428`
- `0x1801086ac`
- `0x180139080`
- `0x180155b88`
- `0x18027775c`
- `0x18030172c`
- `0x1803e13d4`
- `0x1803e5fac`
- `0x1803e6270`
- `0x1803e7198`
- `0x180402a74`
- `0x1804117fc`
- `0x180475a10`
- `0x1806bdc40`
- `0x180744fd4`
- `0x180768058`
- `0x18077c370`
- `0x180792fac`
- `0x1807b8210`
- `0x18084ed20`
- `0x180854878`
- `0x180880048`
- `0x180886278`
- `0x180899fa0`
- `0x1808d3c9c`
- `0x1809e583c`
- `0x1809ec814`
- `0x180d34b14`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180886389`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x180886389`
- `iertutil!__imp_GetValue` at `0x180886a98`
- `iertutil!__imp_GetValue` at `0x180886a98`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180886332`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180886332`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180886433`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1808864ca`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180886433`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1808864ca`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18088641e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808864b5`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18088641e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1808864b5`
- `urlmon!CreateURLMonikerEx` at `0x1808868c2`
- `urlmon!CreateURLMonikerEx` at `0x1808868c2`
- `urlmon!CoInternetCombineUrl` at `0x18088676f`
- `urlmon!CoInternetCombineUrl` at `0x1808867b3`
- `urlmon!CoInternetCombineUrl` at `0x18088676f`
- `urlmon!CoInternetCombineUrl` at `0x1808867b3`
- `OLEAUT32!__imp_SysAllocString` at `0x180886608`
- `OLEAUT32!__imp_SysAllocString` at `0x180886608`
- `OLEAUT32!__imp_SysFreeString` at `0x18088651a`
- `OLEAUT32!__imp_SysFreeString` at `0x1808867d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1808867ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18088651a`
- `OLEAUT32!__imp_SysFreeString` at `0x1808867d1`
- `OLEAUT32!__imp_SysFreeString` at `0x1808867ee`
- `OLEAUT32!__imp_VariantInit` at `0x18088696b`
- `OLEAUT32!__imp_VariantInit` at `0x1808869a3`
- `OLEAUT32!__imp_VariantInit` at `0x18088696b`
- `OLEAUT32!__imp_VariantInit` at `0x1808869a3`
- `OLEAUT32!__imp_VariantClear` at `0x18088680f`
- `OLEAUT32!__imp_VariantClear` at `0x18088680f`
- `OLEAUT32!__imp_VariantCopy` at `0x1808869b7`
- `OLEAUT32!__imp_VariantCopy` at `0x1808869b7`

## pseudocode

```c
__int64 __fastcall CWindow::ShowHTMLDialogHelper(CWindow *this, struct HTMLDLGINFO *a2)
{
  int URLMoniker; // edi
  const struct CMarkup *v4; // rcx
  OLECHAR *v6; // r12
  int v7; // ebx
  const unsigned __int16 *Url; // rax
  unsigned __int16 *v9; // r13
  CMarkup *v10; // rcx
  struct IUri *v11; // rax
  int DomainFromUri; // eax
  BSTR v13; // rcx
  CDoc *v14; // rbx
  bool IsPendingRoot; // al
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  struct IDispatch *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rax
  const WCHAR *v25; // rcx
  OLECHAR *v26; // rcx
  const unsigned __int16 *v27; // r9
  __int64 v28; // rdx
  unsigned __int16 *v29; // rdx
  __int64 v30; // rdx
  void *v31; // r8
  struct CDoc *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  OLECHAR *v35; // r8
  const WCHAR *v36; // rdx
  struct IDispatch *pdispVal; // r13
  unsigned __int16 *v38; // r15
  unsigned int v39; // ebx
  __int64 v40; // rdx
  void *v41; // r8
  CMarkup *v43; // r8
  BOOL v44; // r12d
  int *v45; // r9
  CDoc *v46; // rax
  VARIANTARG *v47; // rcx
  __int64 v48; // rax
  struct CSecurityContext *v49; // rax
  CDoc *v50; // rax
  struct CDoc *v51; // rax
  CZoomState *v52; // r13
  int v53; // ebx
  int FactorPercent; // edx
  int Value; // eax
  unsigned int v56; // ecx
  struct CDoc *v57; // rax
  __int64 v58; // rdx
  void *v59; // r8
  char v60; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v61[7]; // [rsp+51h] [rbp-AFh] BYREF
  BSTR v62; // [rsp+58h] [rbp-A8h]
  struct IDispatch *v63; // [rsp+60h] [rbp-A0h]
  LONGLONG llVal; // [rsp+68h] [rbp-98h]
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchResult; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v67; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v68; // [rsp+88h] [rbp-78h] BYREF
  const WCHAR *v69; // [rsp+90h] [rbp-70h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v70; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *CLSID; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v72; // [rsp+A8h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v74[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v75; // [rsp+E8h] [rbp-18h]
  _BYTE v76[56]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR *v77; // [rsp+128h] [rbp+28h]
  int v78; // [rsp+134h] [rbp+34h]
  WCHAR pszResult[4096]; // [rsp+150h] [rbp+50h] BYREF

  URLMoniker = 0;
  v4 = (const struct CMarkup *)*((_QWORD *)this + 13);
  pcchResult = 0;
  v6 = 0;
  v62 = 0;
  bstrString = 0;
  v7 = ~(4 * *((_DWORD *)v4 + 187));
  v68 = 0;
  v72 = 0;
  Url = CMarkup::GetUrl(v4);
  *((_DWORD *)a2 + 26) |= v7 & 0x8000000;
  v9 = (unsigned __int16 *)Url;
  v63 = 0;
  llVal = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v67 = 0;
  if ( !CWindow::Doc(this) || !*((_QWORD *)CWindow::Doc(this) + 12) )
  {
    URLMoniker = -2147483638;
    goto LABEL_16;
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435481) )
  {
    URLMoniker = -2147024891;
    memset_0(v76, 0, 0x58u);
    v10 = (CMarkup *)*((_QWORD *)this + 13);
    bstrString = 0;
    v78 = 32;
    if ( CMarkup::Uri(v10) )
    {
      v11 = CMarkup::Uri(*((CMarkup **)this + 13));
      DomainFromUri = EDL_GetDomainFromUri(v11, &bstrString);
      v13 = v77;
      if ( DomainFromUri >= 0 )
        v13 = bstrString;
      v77 = v13;
    }
    v14 = CWindow::Doc(this);
    IsPendingRoot = CMarkup::IsPendingRoot(*((CMarkup **)this + 13));
    CDoc::OnPageActionBlocked(v14, 0x40000000, IsPendingRoot, (struct BLOCKED_ACTION_DETAILS *)v76);
    if ( *((_DWORD *)a2 + 16) )
    {
      if ( (unsigned int)dword_18158CCA8 > 5 && tlgKeywordOn((__int64)&dword_18158CCA8, 0x408000000000LL) )
      {
        v60 = 0;
        v61[0] = 1;
        v69 = bstrString;
        v70 = GlobalThreadState();
        CLSID = (const WCHAR *)IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
          v16,
          (__int64)byte_18154C1A5,
          v17,
          v18,
          (__int64 *)&CLSID,
          (__int64 *)&v70,
          (__int64)v61,
          &v69,
          (__int64)&v60);
      }
    }
    else if ( (unsigned int)dword_18158CCA8 > 5 && tlgKeywordOn((__int64)&dword_18158CCA8, 0x408000000000LL) )
    {
      v61[0] = 0;
      v60 = 1;
      CLSID = bstrString;
      v70 = GlobalThreadState();
      v69 = (const WCHAR *)IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        v19,
        (__int64)&word_18154C136,
        v20,
        v21,
        (__int64 *)&v69,
        (__int64 *)&v70,
        (__int64)&v60,
        &CLSID,
        (__int64)v61);
    }
    SysFreeString(bstrString);
    goto LABEL_16;
  }
  v23 = *((_QWORD *)a2 + 7);
  if ( v23 )
  {
    if ( *(_WORD *)v23 == 16396 )
    {
      v23 = *(_QWORD *)(v23 + 8);
      *((_QWORD *)a2 + 7) = v23;
    }
  }
  else
  {
    v23 = 0;
  }
  v24 = *((_QWORD *)a2 + 4);
  if ( v24 && *(_WORD *)v24 == 16396 )
    *((_QWORD *)a2 + 4) = *(_QWORD *)(v24 + 8);
  if ( !v23 )
    goto LABEL_28;
  if ( *(_WORD *)v23 == 10 )
  {
    if ( *(_DWORD *)(v23 + 8) == -2147352572 )
      *((_QWORD *)a2 + 7) = 0;
    goto LABEL_28;
  }
  if ( *(_WORD *)v23 != 8 )
  {
    URLMoniker = -2147024809;
LABEL_16:
    v22 = 0;
LABEL_60:
    v26 = v62;
    goto LABEL_61;
  }
LABEL_28:
  v25 = (const WCHAR *)*((_QWORD *)a2 + 3);
  v22 = 0;
  if ( v25 && *v25 )
  {
    if ( IsSpecialUrl(v25) )
    {
      if ( (unsigned int)WrapSpecialUrl(*((unsigned __int16 **)a2 + 3), &v68, v9) )
        goto LABEL_60;
      URLMoniker = CStr::AllocBSTR(&v68, &bstrString);
      if ( URLMoniker )
      {
        v26 = bstrString;
LABEL_61:
        pdispVal = v22;
        goto LABEL_62;
      }
      v6 = bstrString;
      LODWORD(v22) = 1;
      v62 = bstrString;
    }
  }
  else
  {
    if ( !*((_DWORD *)a2 + 16) )
    {
      URLMoniker = -2147024809;
      goto LABEL_60;
    }
    v6 = SysAllocString(L"about:blank");
    v62 = v6;
  }
  if ( IsUrlHandledByBlobProtocol(*((const unsigned __int16 **)a2 + 3)) )
    goto LABEL_40;
  v28 = *((_QWORD *)a2 + 7);
  if ( *(_WORD *)v28 == 8 )
  {
    v29 = *(unsigned __int16 **)(v28 + 8);
    if ( v29 )
    {
      if ( *v29 )
      {
        bstrString = 0;
        v72 = v29;
        CWindow::FilterOutFeaturesString(this, v29, (const unsigned __int16 **)&bstrString, v27, 1);
        URLMoniker = CStr::AllocBSTR((const OLECHAR **)&bstrString, (unsigned __int16 **)(*((_QWORD *)a2 + 7) + 8LL));
        if ( URLMoniker )
        {
          CStr::_Free((CStr *)&bstrString, v30, v31);
          goto LABEL_41;
        }
        CStr::_Free((CStr *)&bstrString, v30, v31);
      }
    }
  }
  if ( *((char *)CWindow::Doc(this) + 4868) < 0 )
  {
    v32 = CWindow::Doc(this);
    if ( !IsWebPlatformHostBehaviorSupported<6>(*((_DWORD *)v32 + 1260)) )
    {
      URLMoniker = -2147467263;
      v33 = *((_QWORD *)CWindow::Doc(this) + 12);
      if ( v33 )
      {
        v34 = *(_QWORD *)(v33 + 136);
        if ( v34 )
        {
          v35 = v6;
          if ( !v6 )
            v35 = (OLECHAR *)*((_QWORD *)a2 + 3);
          URLMoniker = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
                         v34,
                         *((unsigned int *)a2 + 16),
                         v35,
                         *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL),
                         *((_QWORD *)a2 + 19));
        }
      }
      goto LABEL_41;
    }
  }
  v36 = v6;
  if ( !v6 )
    v36 = (const WCHAR *)*((_QWORD *)a2 + 3);
  URLMoniker = CoInternetCombineUrl(v9, v36, 0x6000000u, pszResult, 0x1000u, &pcchResult, 0);
  if ( URLMoniker )
    goto LABEL_41;
  if ( (_DWORD)v22 )
  {
    v22 = 0;
    URLMoniker = CoInternetCombineUrl(v9, *((LPCWSTR *)a2 + 3), 0x6000000u, pszResult, 0x1000u, &pcchResult, 0);
    if ( URLMoniker )
      goto LABEL_60;
  }
  v44 = (*(_DWORD *)(*((_QWORD *)this + 13) + 748LL) & 0x2000000) == 0
     && (*((_BYTE *)CWindow::Doc(this) + 4860) & 1) == 0
     && (unsigned int)CMarkup::AccessAllowed(v43, pszResult) == 0;
  URLMoniker = CreateURLMonikerEx(0, pszResult, (LPMONIKER *)a2 + 1, 1u);
  if ( URLMoniker )
    goto LABEL_41;
  if ( !(unsigned int)COmWindowProxy::CanNavigateToUrlWithZoneCheck(*((struct CMarkup ***)this + 13), 0, pszResult, v45) )
  {
LABEL_40:
    URLMoniker = -2147024891;
LABEL_41:
    v22 = v63;
    goto LABEL_60;
  }
  *(_QWORD *)a2 = *(_QWORD *)(*((_QWORD *)CWindow::Doc(this) + 12) + 168LL);
  *((_QWORD *)a2 + 15) = *((_QWORD *)this + 13);
  v46 = CWindow::Doc(this);
  if ( (unsigned int)CDoc::QueryPopupMgr(v46, pszResult, 0, 0, (struct IUnknown *)v9, 0, 0, 0x20u, this) )
  {
    if ( (*(_DWORD *)(*((_QWORD *)this + 13) + 756LL) & 0x1100) == 0x100 )
    {
      v47 = (VARIANTARG *)*((_QWORD *)a2 + 5);
      if ( v47 )
        VariantInit(v47);
      URLMoniker = 0;
      goto LABEL_41;
    }
    goto LABEL_40;
  }
  v48 = *((_QWORD *)a2 + 4);
  if ( v48 && *(_WORD *)v48 == 9 && *(_QWORD *)(v48 + 8) )
  {
    VariantInit(&pvarg);
    VariantCopy(&pvarg, *((const VARIANTARG **)a2 + 4));
    pdispVal = pvarg.pdispVal;
    v22 = (struct IDispatch *)*((_QWORD *)a2 + 4);
    v63 = v22;
    llVal = pvarg.llVal;
    (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 8))(pvarg.llVal);
    v49 = CWindow::SecurityContext(this);
    URLMoniker = CSecureDispatchProxy::Create(pdispVal, (struct IDispatch **)&v67, v49);
    if ( URLMoniker < 0 || !v67 )
    {
      v26 = v62;
      goto LABEL_62;
    }
    ReplaceInterfaceFn(&pvarg.punkVal, v67);
    *((_QWORD *)a2 + 4) = &pvarg;
  }
  v50 = CWindow::Doc(this);
  CDoc::UpdateEffectiveDpi(v50);
  v51 = CWindow::Doc(this);
  v52 = (CZoomState *)*((_QWORD *)v51 + 649);
  if ( v52 )
  {
    v53 = *((_DWORD *)v52 + 17);
    if ( v53 != CZoomState::GetPersistentFactor(*((CZoomState **)v51 + 649)) )
      CZoomState::ClearTransientZoomState(v52);
    FactorPercent = CZoomState::GetFactorPercent(v52);
  }
  else
  {
    LODWORD(bstrString) = 0;
    Value = GetValue((__int64 *)SettingStore::IEVALUE_Zoom_ZoomFactor[0], 1, 1, &bstrString, 4, 0, 0);
    v56 = 100000;
    if ( Value >= 0 )
      v56 = (unsigned int)bstrString;
    FactorPercent = v56 / 0x3E8;
  }
  *((_DWORD *)a2 + 41) = FactorPercent;
  if ( *((_DWORD *)a2 + 16) )
  {
    if ( v44 )
      *((_QWORD *)a2 + 4) = 0;
    URLMoniker = InternalModelessDialog(a2, 1);
  }
  else
  {
    v57 = CWindow::Doc(this);
    CDoEnableModeless::CDoEnableModeless((CDoEnableModeless *)v74, v57, this, 1, 1, 0);
    if ( v75 )
    {
      if ( v44 )
      {
        *((_QWORD *)a2 + 4) = 0;
        *((_QWORD *)a2 + 5) = 0;
      }
      URLMoniker = InternalShowModalDialog(a2, 0, 1);
    }
    CDoEnableModeless::~CDoEnableModeless((CDoEnableModeless *)v74, v58, v59);
  }
  v26 = v62;
  v22 = v63;
  pdispVal = (struct IDispatch *)llVal;
LABEL_62:
  SysFreeString(v26);
  v38 = v72;
  if ( v72 )
  {
    SysFreeString(*(BSTR *)(*((_QWORD *)a2 + 7) + 8LL));
    *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL) = v38;
  }
  if ( v22 )
  {
    *((_QWORD *)a2 + 4) = v22;
    VariantClear(&pvarg);
  }
  ReleaseInterface(v67);
  ReleaseInterface((struct IUnknown *)pdispVal);
  ReleaseInterface(*((struct IUnknown **)a2 + 1));
  v39 = CBase::SetErrorInfo(this, URLMoniker);
  CStr::_Free((CStr *)&v68, v40, v41);
  return v39;
}

```

## disassembly

```asm
0x180886278  mov     [rsp-8+arg_10], rbx
0x18088627d  push    rbp
0x18088627e  push    rsi
0x18088627f  push    rdi
0x180886280  push    r12
0x180886282  push    r13
0x180886284  push    r14
0x180886286  push    r15
0x180886288  lea     rbp, [rsp-2060h]
0x180886290  mov     eax, 2160h
0x180886295  call    _alloca_probe
0x18088629a  sub     rsp, rax
0x18088629d  mov     rax, cs:__security_cookie
0x1808862a4  xor     rax, rsp
0x1808862a7  mov     [rbp+2090h+var_40], rax
0x1808862ae  xor     edi, edi
0x1808862b0  mov     r14, rcx
0x1808862b3  mov     rcx, [rcx+68h]; struct CMarkup *
0x1808862b7  mov     rsi, rdx
0x1808862ba  mov     [rsp+2190h+var_2118], edi
0x1808862be  mov     r12d, edi
0x1808862c1  mov     [rsp+2190h+var_2138], rdi
0x1808862c6  mov     [rsp+2190h+bstrString], rdi
0x1808862cb  mov     ebx, [rcx+2ECh]
0x1808862d1  shl     ebx, 2
0x1808862d4  not     ebx
0x1808862d6  mov     [rbp+2090h+var_2108], rdi
0x1808862da  and     ebx, 8000000h
0x1808862e0  mov     [rbp+2090h+var_20E8], rdi
0x1808862e4  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x1808862e9  or      [rsi+68h], ebx
0x1808862ec  mov     r13, rax
0x1808862ef  xor     eax, eax
0x1808862f1  mov     [rsp+2190h+var_2130], rdi
0x1808862f6  xorps   xmm0, xmm0
0x1808862f9  mov     qword ptr [rbp+2090h+pvarg+10h], rax
0x1808862fd  mov     rcx, r14; this
0x180886300  mov     [rsp+2190h+var_2128], rdi
0x180886305  movups  xmmword ptr [rbp+2090h+pvarg], xmm0
0x180886309  mov     [rbp+2090h+var_2110], rdi
0x18088630d  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x180886312  test    rax, rax
0x180886315  jz      loc_180886B4A
0x18088631b  mov     rcx, r14; this
0x18088631e  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x180886323  cmp     [rax+60h], rdi
0x180886327  jz      loc_180886B4A
0x18088632d  mov     ecx, 10000019h
0x180886332  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180886339  nop     dword ptr [rax+rax+00h]
0x18088633e  test    al, al
0x180886340  jz      loc_18088652E
0x180886346  xor     edx, edx; Val
0x180886348  lea     r8d, [r12+58h]; Size
0x18088634d  lea     rcx, [rbp+2090h+var_20A0]; void *
0x180886351  mov     edi, 80070005h
0x180886356  call    memset_0
0x18088635b  mov     rcx, [r14+68h]; this
0x18088635f  xor     r15d, r15d
0x180886362  mov     [rsp+2190h+bstrString], r15
0x180886367  mov     [rbp+2090h+var_205C], 20h ; ' '
0x18088636e  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180886373  test    rax, rax
0x180886376  jz      short loc_1808863A5
0x180886378  mov     rcx, [r14+68h]; this
0x18088637c  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180886381  mov     rcx, rax
0x180886384  lea     rdx, [rsp+2190h+bstrString]
0x180886389  call    cs:__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z; EDL_GetDomainFromUri(IUri *,ushort * *)
0x180886390  nop     dword ptr [rax+rax+00h]
0x180886395  mov     rcx, [rbp+2090h+var_2068]
0x180886399  test    eax, eax
0x18088639b  cmovns  rcx, [rsp+2190h+bstrString]
0x1808863a1  mov     [rbp+2090h+var_2068], rcx
0x1808863a5  mov     rcx, r14; this
0x1808863a8  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1808863ad  mov     rcx, [r14+68h]; this
0x1808863b1  mov     rbx, rax
0x1808863b4  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x1808863b9  movzx   r8d, al; int
0x1808863bd  lea     r9, [rbp+2090h+var_20A0]; struct BLOCKED_ACTION_DETAILS *
0x1808863c1  mov     edx, 40000000h; unsigned int
0x1808863c6  mov     rcx, rbx; this
0x1808863c9  call    ?OnPageActionBlocked@CDoc@@QEAAJKHPEAUBLOCKED_ACTION_DETAILS@@@Z; CDoc::OnPageActionBlocked(ulong,int,BLOCKED_ACTION_DETAILS *)
0x1808863ce  mov     eax, cs:dword_18158CCA8
0x1808863d4  cmp     [rsi+40h], r15d
0x1808863d8  jz      loc_180886479
0x1808863de  cmp     eax, 5
0x1808863e1  jbe     loc_180886515
0x1808863e7  mov     rdx, 408000000000h
0x1808863f1  lea     rcx, dword_18158CCA8
0x1808863f8  call    _tlgKeywordOn
0x1808863fd  test    al, al
0x1808863ff  jz      loc_180886515
0x180886405  mov     rax, [rsp+2190h+bstrString]
0x18088640a  mov     [rsp+2190h+var_2140], r15b
0x18088640f  mov     r15d, 1
0x180886415  mov     [rsp+2190h+var_213F], r15b
0x18088641a  mov     [rbp+2090h+var_2100], rax
0x18088641e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180886425  nop     dword ptr [rax+rax+00h]
0x18088642a  mov     ecx, 10000003h
0x18088642f  mov     [rbp+2090h+var_20F8], rax
0x180886433  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18088643a  nop     dword ptr [rax+rax+00h]
0x18088643f  mov     [rbp+2090h+var_20F0], rax
0x180886443  lea     rdx, byte_18154C1A5
0x18088644a  lea     rax, [rsp+2190h+var_2140]
0x18088644f  mov     [rsp+2190h+var_2150], rax
0x180886454  lea     rax, [rbp+2090h+var_2100]
0x180886458  mov     qword ptr [rsp+2190h+var_2158], rax
0x18088645d  lea     rax, [rsp+2190h+var_213F]
0x180886462  mov     qword ptr [rsp+2190h+dwReserved], rax
0x180886467  lea     rax, [rbp+2090h+var_20F8]
0x18088646b  mov     [rsp+2190h+pcchResult], rax
0x180886470  lea     rax, [rbp+2090h+var_20F0]
0x180886474  jmp     loc_18088650B
0x180886479  cmp     eax, 5
0x18088647c  jbe     loc_180886515
0x180886482  mov     rdx, 408000000000h
0x18088648c  lea     rcx, dword_18158CCA8
0x180886493  call    _tlgKeywordOn
0x180886498  test    al, al
0x18088649a  jz      short loc_180886515
0x18088649c  mov     rax, [rsp+2190h+bstrString]
0x1808864a1  mov     [rsp+2190h+var_213F], r15b
0x1808864a6  mov     r15d, 1
0x1808864ac  mov     [rsp+2190h+var_2140], r15b
0x1808864b1  mov     [rbp+2090h+var_20F0], rax
0x1808864b5  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1808864bc  nop     dword ptr [rax+rax+00h]
0x1808864c1  mov     ecx, 10000003h
0x1808864c6  mov     [rbp+2090h+var_20F8], rax
0x1808864ca  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1808864d1  nop     dword ptr [rax+rax+00h]
0x1808864d6  mov     [rbp+2090h+var_2100], rax
0x1808864da  lea     rdx, word_18154C136
0x1808864e1  lea     rax, [rsp+2190h+var_213F]
0x1808864e6  mov     [rsp+2190h+var_2150], rax
0x1808864eb  lea     rax, [rbp+2090h+var_20F0]
0x1808864ef  mov     qword ptr [rsp+2190h+var_2158], rax
0x1808864f4  lea     rax, [rsp+2190h+var_2140]
0x1808864f9  mov     qword ptr [rsp+2190h+dwReserved], rax
0x1808864fe  lea     rax, [rbp+2090h+var_20F8]
0x180886502  mov     [rsp+2190h+pcchResult], rax
0x180886507  lea     rax, [rbp+2090h+var_2100]
0x18088650b  mov     qword ptr [rsp+2190h+cchResult], rax
0x180886510  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x180886515  mov     rcx, [rsp+2190h+bstrString]; bstrString
0x18088651a  call    cs:__imp_SysFreeString
0x180886521  nop     dword ptr [rax+rax+00h]
0x180886526  mov     rbx, r12
0x180886529  jmp     loc_1808867C9
0x18088652e  mov     rcx, [rsi+38h]
0x180886532  mov     edx, 400Ch
0x180886537  test    rcx, rcx
0x18088653a  jz      short loc_18088654B
0x18088653c  cmp     [rcx], dx
0x18088653f  jnz     short loc_18088654E
0x180886541  mov     rcx, [rcx+8]
0x180886545  mov     [rsi+38h], rcx
0x180886549  jmp     short loc_18088654E
0x18088654b  mov     rcx, rdi
0x18088654e  mov     rax, [rsi+20h]
0x180886552  test    rax, rax
0x180886555  jz      short loc_180886564
0x180886557  cmp     [rax], dx
0x18088655a  jnz     short loc_180886564
0x18088655c  mov     rax, [rax+8]
0x180886560  mov     [rsi+20h], rax
0x180886564  mov     edx, 8
0x180886569  test    rcx, rcx
0x18088656c  jz      short loc_180886583
0x18088656e  lea     eax, [rdx+2]
0x180886571  cmp     ax, [rcx]
0x180886574  jnz     short loc_1808865DF
0x180886576  cmp     dword ptr [rcx+8], 80020004h
0x18088657d  jnz     short loc_180886583
0x18088657f  mov     [rsi+38h], rdi
0x180886583  mov     rcx, [rsi+18h]
0x180886587  mov     ebx, edi
0x180886589  mov     r15d, 1
0x18088658f  test    rcx, rcx
0x180886592  jz      short loc_1808865F8
0x180886594  cmp     [rcx], di
0x180886597  jz      short loc_1808865F8
0x180886599  call    IsSpecialUrl
0x18088659e  test    eax, eax
0x1808865a0  jz      short loc_18088661C
0x1808865a2  mov     rcx, [rsi+18h]; unsigned __int16 *
0x1808865a6  lea     rdx, [rbp+2090h+var_2108]; struct CStr *
0x1808865aa  mov     r8, r13; unsigned __int16 *
0x1808865ad  call    ?WrapSpecialUrl@@YAJPEAGPEAVCStr@@PEBG@Z; WrapSpecialUrl(ushort *,CStr *,ushort const *)
0x1808865b2  test    eax, eax
0x1808865b4  jnz     loc_1808867C9
0x1808865ba  lea     rdx, [rsp+2190h+bstrString]; unsigned __int16 **
0x1808865bf  lea     rcx, [rbp+2090h+var_2108]; this
0x1808865c3  call    ?AllocBSTR@CStr@@QEBAJPEAPEAG@Z; CStr::AllocBSTR(ushort * *)
0x1808865c8  mov     edi, eax
0x1808865ca  test    eax, eax
0x1808865cc  jnz     short loc_1808865EE
0x1808865ce  mov     r12, [rsp+2190h+bstrString]
0x1808865d3  mov     ebx, r15d
0x1808865d6  mov     [rsp+2190h+var_2138], r12
0x1808865db  xor     edi, edi
0x1808865dd  jmp     short loc_18088661C
0x1808865df  cmp     dx, [rcx]
0x1808865e2  jz      short loc_180886583
0x1808865e4  mov     edi, 80070057h
0x1808865e9  jmp     loc_180886526
0x1808865ee  mov     rcx, [rsp+2190h+bstrString]
0x1808865f3  jmp     loc_1808867CE
0x1808865f8  cmp     [rsi+40h], edi
0x1808865fb  jz      loc_180886B40
0x180886601  lea     rcx, pcszURL; "about:blank"
0x180886608  call    cs:__imp_SysAllocString
0x18088660f  nop     dword ptr [rax+rax+00h]
0x180886614  mov     r12, rax
0x180886617  mov     [rsp+2190h+var_2138], rax
0x18088661c  mov     rcx, [rsi+18h]; unsigned __int16 *
0x180886620  call    ?IsUrlHandledByBlobProtocol@@YA_NPEBG@Z; IsUrlHandledByBlobProtocol(ushort const *)
0x180886625  test    al, al
0x180886627  jz      short loc_180886638
0x180886629  mov     edi, 80070005h
0x18088662e  mov     rbx, [rsp+2190h+var_2130]
0x180886633  jmp     loc_1808867C9
0x180886638  mov     rdx, [rsi+38h]
0x18088663c  mov     eax, 8
0x180886641  cmp     ax, [rdx]
0x180886644  jnz     short loc_18088669A
0x180886646  mov     rdx, [rdx+8]; unsigned __int16 *
0x18088664a  test    rdx, rdx
0x18088664d  jz      short loc_18088669A
0x18088664f  cmp     di, [rdx]
0x180886652  jz      short loc_18088669A
0x180886654  lea     r8, [rsp+2190h+bstrString]; struct CStr *
0x180886659  mov     [rsp+2190h+bstrString], rdi
0x18088665e  mov     rcx, r14; this
0x180886661  mov     [rbp+2090h+var_20E8], rdx
0x180886665  mov     byte ptr [rsp+2190h+cchResult], r15b; bool
0x18088666a  call    ?FilterOutFeaturesString@CWindow@@IEAAJPEAGPEAVCStr@@PEBG_N@Z; CWindow::FilterOutFeaturesString(ushort *,CStr *,ushort const *,bool)
0x18088666f  mov     rdx, [rsi+38h]
0x180886673  lea     rcx, [rsp+2190h+bstrString]; this
0x180886678  add     rdx, 8; unsigned __int16 **
0x18088667c  call    ?AllocBSTR@CStr@@QEBAJPEAPEAG@Z; CStr::AllocBSTR(ushort * *)
0x180886681  lea     rcx, [rsp+2190h+bstrString]; this
0x180886686  mov     edi, eax
0x180886688  test    eax, eax
0x18088668a  jz      short loc_180886693
0x18088668c  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180886691  jmp     short loc_18088662E
0x180886693  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x180886698  xor     edi, edi
0x18088669a  mov     rcx, r14; this
0x18088669d  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1808866a2  test    byte ptr [rax+1304h], 80h
0x1808866a9  jz      loc_18088673D
0x1808866af  mov     rcx, r14; this
0x1808866b2  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1808866b7  mov     r9d, [rax+13B8h]
0x1808866be  mov     r8d, [rax+13BCh]
0x1808866c5  mov     edx, [rax+13B4h]
0x1808866cb  mov     ecx, [rax+13B0h]
0x1808866d1  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x1808866d6  test    al, al
0x1808866d8  jnz     short loc_18088673D
0x1808866da  mov     rcx, r14; this
0x1808866dd  mov     edi, 80004001h
0x1808866e2  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x1808866e7  mov     rcx, [rax+60h]
0x1808866eb  test    rcx, rcx
0x1808866ee  jz      loc_18088662E
0x1808866f4  mov     rcx, [rcx+88h]
0x1808866fb  test    rcx, rcx
0x1808866fe  jz      loc_18088662E
0x180886704  mov     rax, [rcx]
0x180886707  mov     r8, r12
0x18088670a  mov     rdx, [rsi+98h]
0x180886711  mov     r10, [rax+40h]
0x180886715  mov     rax, [rsi+38h]
0x180886719  test    r12, r12
0x18088671c  jnz     short loc_180886722
0x18088671e  mov     r8, [rsi+18h]
0x180886722  mov     r9, [rax+8]
0x180886726  mov     rax, r10
0x180886729  mov     qword ptr [rsp+2190h+cchResult], rdx
0x18088672e  mov     edx, [rsi+40h]
0x180886731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180886736  mov     edi, eax
0x180886738  jmp     loc_18088662E
0x18088673d  mov     rdx, r12
0x180886740  test    r12, r12
0x180886743  jnz     short loc_180886749
0x180886745  mov     rdx, [rsi+18h]; pwzRelativeUrl
0x180886749  lea     rax, [rsp+2190h+var_2118]
0x18088674e  mov     [rsp+2190h+dwReserved], edi; dwReserved
0x180886752  mov     [rsp+2190h+pcchResult], rax; pcchResult
0x180886757  lea     r9, [rbp+2090h+pszResult]; pszResult
0x18088675b  mov     r12d, 1000h
0x180886761  mov     r8d, 6000000h; dwCombineFlags
  ... truncated ...
```
