# CWindow::ShowHTMLDialogHelper(HTMLDLGINFO *)

- ea: `0x18087efc8`
- end: `0x18087f83d`
- name: `?ShowHTMLDialogHelper@CWindow@@QEAAJPEAUHTMLDLGINFO@@@Z`
- size: `2165`
- prototype: `__int64 __fastcall(CWindow *__hidden this, struct HTMLDLGINFO *)`
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18088f260`
- `0x18088f320`

## callees

- `0x180002238`
- `0x1800bc2b4`
- `0x1800e4964`
- `0x180135278`
- `0x1801c0acc`
- `0x18021f9bc`
- `0x180226578`
- `0x1802cca88`
- `0x180300074`
- `0x180370004`
- `0x180373368`
- `0x18043c328`
- `0x180491cfc`
- `0x180497c34`
- `0x1805017a0`
- `0x1805c35b4`
- `0x18063a220`
- `0x1806bd190`
- `0x18073c80c`
- `0x180771b58`
- `0x18077e38c`
- `0x1807b11f8`
- `0x180811274`
- `0x1808510b4`
- `0x180879424`
- `0x18087efc8`
- `0x180891ba0`
- `0x1808c906c`
- `0x1809d4d58`
- `0x1809db94c`
- `0x180d12bb0`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x18087f0d3`
- `iertutil!__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z` at `0x18087f0d3`
- `iertutil!__imp_GetValue` at `0x18087f77d`
- `iertutil!__imp_GetValue` at `0x18087f77d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18087f082`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18087f082`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18087f171`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18087f1fc`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18087f171`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18087f1fc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18087f162`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18087f1ed`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18087f162`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18087f1ed`
- `urlmon!CreateURLMonikerEx` at `0x18087f5c3`
- `urlmon!CreateURLMonikerEx` at `0x18087f5c3`
- `urlmon!CoInternetCombineUrl` at `0x18087f48f`
- `urlmon!CoInternetCombineUrl` at `0x18087f4cd`
- `urlmon!CoInternetCombineUrl` at `0x18087f48f`
- `urlmon!CoInternetCombineUrl` at `0x18087f4cd`
- `OLEAUT32!__imp_SysAllocString` at `0x18087f32e`
- `OLEAUT32!__imp_SysAllocString` at `0x18087f32e`
- `OLEAUT32!__imp_SysFreeString` at `0x18087f246`
- `OLEAUT32!__imp_SysFreeString` at `0x18087f4e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18087f4fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18087f246`
- `OLEAUT32!__imp_SysFreeString` at `0x18087f4e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18087f4fc`
- `OLEAUT32!__imp_VariantInit` at `0x18087f666`
- `OLEAUT32!__imp_VariantInit` at `0x18087f694`
- `OLEAUT32!__imp_VariantInit` at `0x18087f666`
- `OLEAUT32!__imp_VariantInit` at `0x18087f694`
- `OLEAUT32!__imp_VariantClear` at `0x18087f517`
- `OLEAUT32!__imp_VariantClear` at `0x18087f517`
- `OLEAUT32!__imp_VariantCopy` at `0x18087f6a2`
- `OLEAUT32!__imp_VariantCopy` at `0x18087f6a2`

## pseudocode

```c
__int64 __fastcall CWindow::ShowHTMLDialogHelper(CWindow *this, struct HTMLDLGINFO *a2)
{
  HRESULT URLMoniker; // edi
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
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  struct IDispatch *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rax
  _WORD *v25; // rcx
  OLECHAR *v26; // rcx
  const unsigned __int16 *v27; // r9
  __int64 v28; // rdx
  unsigned __int16 *v29; // rdx
  unsigned int *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  OLECHAR *v33; // r8
  const WCHAR *v34; // rdx
  struct IDispatch *pdispVal; // r13
  unsigned __int16 *v36; // r15
  unsigned int v37; // ebx
  CMarkup *v39; // r8
  BOOL v40; // r12d
  int *v41; // r9
  CDoc *v42; // rax
  VARIANTARG *v43; // rcx
  __int64 v44; // rax
  struct CSecurityContext *v45; // rax
  CDoc *v46; // rax
  struct CDoc *v47; // rax
  CZoomState *v48; // r13
  int v49; // ebx
  unsigned int FactorPercent; // edx
  int Value; // eax
  unsigned int v52; // ecx
  struct CDoc *v53; // rax
  int cchResult; // [rsp+20h] [rbp-E0h]
  char v55; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v56[7]; // [rsp+51h] [rbp-AFh] BYREF
  BSTR v57; // [rsp+58h] [rbp-A8h]
  struct IDispatch *v58; // [rsp+60h] [rbp-A0h]
  LONGLONG llVal; // [rsp+68h] [rbp-98h]
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchResult; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v62; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h] BYREF
  BSTR v64; // [rsp+90h] [rbp-70h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v65; // [rsp+98h] [rbp-68h] BYREF
  BSTR CLSID; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v67; // [rsp+A8h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v69[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v70; // [rsp+E8h] [rbp-18h]
  _BYTE v71[56]; // [rsp+F0h] [rbp-10h] BYREF
  OLECHAR *v72; // [rsp+128h] [rbp+28h]
  int v73; // [rsp+134h] [rbp+34h]
  WCHAR pszResult[4096]; // [rsp+150h] [rbp+50h] BYREF

  URLMoniker = 0;
  v4 = (const struct CMarkup *)*((_QWORD *)this + 13);
  pcchResult = 0;
  v6 = 0;
  v57 = 0;
  bstrString = 0;
  v7 = ~(4 * *((_DWORD *)v4 + 187));
  v63 = 0;
  v67 = 0;
  Url = CMarkup::GetUrl(v4);
  *((_DWORD *)a2 + 26) |= v7 & 0x8000000;
  v9 = (unsigned __int16 *)Url;
  v58 = 0;
  llVal = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v62 = 0;
  if ( !CWindow::Doc(this) || !*((_QWORD *)CWindow::Doc(this) + 12) )
  {
    URLMoniker = -2147483638;
    goto LABEL_16;
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435481) )
  {
    URLMoniker = -2147024891;
    memset_0(v71, 0, 0x58u);
    v10 = (CMarkup *)*((_QWORD *)this + 13);
    bstrString = 0;
    v73 = 32;
    if ( CMarkup::Uri(v10) )
    {
      v11 = CMarkup::Uri(*((CMarkup **)this + 13));
      DomainFromUri = EDL_GetDomainFromUri(v11, &bstrString);
      v13 = v72;
      if ( DomainFromUri >= 0 )
        v13 = bstrString;
      v72 = v13;
    }
    v14 = CWindow::Doc(this);
    IsPendingRoot = CMarkup::IsPendingRoot(*((CMarkup **)this + 13));
    CDoc::OnPageActionBlocked(v14, 0x40000000u, IsPendingRoot, (struct BLOCKED_ACTION_DETAILS *)v71);
    if ( *((_DWORD *)a2 + 16) )
    {
      if ( (unsigned int)dword_181559C88 > 5 && (unsigned __int8)tlgKeywordOn(&dword_181559C88, 0x408000000000LL) )
      {
        v55 = 0;
        v56[0] = 1;
        v64 = bstrString;
        v65 = GlobalThreadState();
        CLSID = (BSTR)IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
          v16,
          (unsigned int)byte_181519145,
          v17,
          v18,
          (__int64)&CLSID,
          (__int64)&v65,
          (__int64)v56,
          (__int64)&v64,
          (__int64)&v55);
      }
    }
    else if ( (unsigned int)dword_181559C88 > 5 && (unsigned __int8)tlgKeywordOn(&dword_181559C88, 0x408000000000LL) )
    {
      v56[0] = 0;
      v55 = 1;
      CLSID = bstrString;
      v65 = GlobalThreadState();
      v64 = (BSTR)IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        v19,
        (unsigned int)&word_1815190D6,
        v20,
        v21,
        (__int64)&v64,
        (__int64)&v65,
        (__int64)&v55,
        (__int64)&CLSID,
        (__int64)v56);
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
    v26 = v57;
    goto LABEL_61;
  }
LABEL_28:
  v25 = (_WORD *)*((_QWORD *)a2 + 3);
  v22 = 0;
  if ( v25 && *v25 )
  {
    if ( (unsigned int)IsSpecialUrl(v25, 8) )
    {
      if ( (unsigned int)WrapSpecialUrl(*((unsigned __int16 **)a2 + 3), (struct CStr *)&v63, v9) )
        goto LABEL_60;
      URLMoniker = CStr::AllocBSTR((CStr *)&v63, &bstrString);
      if ( URLMoniker )
      {
        v26 = bstrString;
LABEL_61:
        pdispVal = v22;
        goto LABEL_62;
      }
      v6 = bstrString;
      LODWORD(v22) = 1;
      v57 = bstrString;
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
    v57 = v6;
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
        v67 = v29;
        CWindow::FilterOutFeaturesString(this, v29, (struct CStr *)&bstrString, v27, 1);
        URLMoniker = CStr::AllocBSTR((CStr *)&bstrString, (unsigned __int16 **)(*((_QWORD *)a2 + 7) + 8LL));
        if ( URLMoniker )
        {
          CStr::_Free((CStr *)&bstrString);
          goto LABEL_41;
        }
        CStr::_Free((CStr *)&bstrString);
      }
    }
  }
  if ( *((char *)CWindow::Doc(this) + 4868) < 0 )
  {
    v30 = (unsigned int *)CWindow::Doc(this);
    if ( !(unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(v30[1260], v30[1261], v30[1263], v30[1262]) )
    {
      URLMoniker = -2147467263;
      v31 = *((_QWORD *)CWindow::Doc(this) + 12);
      if ( v31 )
      {
        v32 = *(_QWORD *)(v31 + 136);
        if ( v32 )
        {
          v33 = v6;
          if ( !v6 )
            v33 = (OLECHAR *)*((_QWORD *)a2 + 3);
          URLMoniker = (*(__int64 (__fastcall **)(__int64, _QWORD, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)v32 + 64LL))(
                         v32,
                         *((unsigned int *)a2 + 16),
                         v33,
                         *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL),
                         *((_QWORD *)a2 + 19));
        }
      }
      goto LABEL_41;
    }
  }
  v34 = v6;
  if ( !v6 )
    v34 = (const WCHAR *)*((_QWORD *)a2 + 3);
  URLMoniker = CoInternetCombineUrl(v9, v34, 0x6000000u, pszResult, 0x1000u, &pcchResult, 0);
  if ( URLMoniker )
    goto LABEL_41;
  if ( (_DWORD)v22 )
  {
    v22 = 0;
    URLMoniker = CoInternetCombineUrl(v9, *((LPCWSTR *)a2 + 3), 0x6000000u, pszResult, 0x1000u, &pcchResult, 0);
    if ( URLMoniker )
      goto LABEL_60;
  }
  v40 = (*(_DWORD *)(*((_QWORD *)this + 13) + 748LL) & 0x2000000) == 0
     && (*((_BYTE *)CWindow::Doc(this) + 4860) & 1) == 0
     && (unsigned int)CMarkup::AccessAllowed(v39, pszResult) == 0;
  URLMoniker = CreateURLMonikerEx(0, pszResult, (LPMONIKER *)a2 + 1, 1u);
  if ( URLMoniker )
    goto LABEL_41;
  if ( !(unsigned int)COmWindowProxy::CanNavigateToUrlWithZoneCheck(
                        *((struct CMarkup **)this + 13),
                        0,
                        pszResult,
                        v41,
                        cchResult) )
  {
LABEL_40:
    URLMoniker = -2147024891;
LABEL_41:
    v22 = v58;
    goto LABEL_60;
  }
  *(_QWORD *)a2 = *(_QWORD *)(*((_QWORD *)CWindow::Doc(this) + 12) + 168LL);
  *((_QWORD *)a2 + 15) = *((_QWORD *)this + 13);
  v42 = CWindow::Doc(this);
  if ( (unsigned int)CDoc::QueryPopupMgr(v42, pszResult, 0, 0, (struct IUnknown *)v9, 0, 0, 0x20u, this) )
  {
    if ( (*(_DWORD *)(*((_QWORD *)this + 13) + 756LL) & 0x1100) == 0x100 )
    {
      v43 = (VARIANTARG *)*((_QWORD *)a2 + 5);
      if ( v43 )
        VariantInit(v43);
      URLMoniker = 0;
      goto LABEL_41;
    }
    goto LABEL_40;
  }
  v44 = *((_QWORD *)a2 + 4);
  if ( v44 && *(_WORD *)v44 == 9 && *(_QWORD *)(v44 + 8) )
  {
    VariantInit(&pvarg);
    VariantCopy(&pvarg, *((const VARIANTARG **)a2 + 4));
    pdispVal = pvarg.pdispVal;
    v22 = (struct IDispatch *)*((_QWORD *)a2 + 4);
    v58 = v22;
    llVal = pvarg.llVal;
    (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 8))(pvarg.llVal);
    v45 = CWindow::SecurityContext(this);
    URLMoniker = CSecureDispatchProxy::Create(pdispVal, (struct IDispatch **)&v62, v45);
    if ( URLMoniker < 0 || !v62 )
    {
      v26 = v57;
      goto LABEL_62;
    }
    ReplaceInterfaceFn(&pvarg.punkVal, v62);
    *((_QWORD *)a2 + 4) = &pvarg;
  }
  v46 = CWindow::Doc(this);
  CDoc::UpdateEffectiveDpi(v46);
  v47 = CWindow::Doc(this);
  v48 = (CZoomState *)*((_QWORD *)v47 + 649);
  if ( v48 )
  {
    v49 = *((_DWORD *)v48 + 17);
    if ( v49 != CZoomState::GetPersistentFactor(*((CZoomState **)v47 + 649)) )
      CZoomState::ClearTransientZoomState(v48);
    FactorPercent = CZoomState::GetFactorPercent(v48);
  }
  else
  {
    LODWORD(bstrString) = 0;
    Value = GetValue((__int64 *)SettingStore::IEVALUE_Zoom_ZoomFactor[0], 1, 1, &bstrString, 4, 0, 0);
    v52 = 100000;
    if ( Value >= 0 )
      v52 = (unsigned int)bstrString;
    FactorPercent = v52 / 0x3E8;
  }
  *((_DWORD *)a2 + 41) = FactorPercent;
  if ( *((_DWORD *)a2 + 16) )
  {
    if ( v40 )
      *((_QWORD *)a2 + 4) = 0;
    URLMoniker = InternalModelessDialog(a2, 1);
  }
  else
  {
    v53 = CWindow::Doc(this);
    CDoEnableModeless::CDoEnableModeless((CDoEnableModeless *)v69, v53, this, 1, 1, 0);
    if ( v70 )
    {
      if ( v40 )
      {
        *((_QWORD *)a2 + 4) = 0;
        *((_QWORD *)a2 + 5) = 0;
      }
      URLMoniker = InternalShowModalDialog(a2, 0, 1);
    }
    CDoEnableModeless::~CDoEnableModeless((CDoEnableModeless *)v69);
  }
  v26 = v57;
  v22 = v58;
  pdispVal = (struct IDispatch *)llVal;
LABEL_62:
  SysFreeString(v26);
  v36 = v67;
  if ( v67 )
  {
    SysFreeString(*(BSTR *)(*((_QWORD *)a2 + 7) + 8LL));
    *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL) = v36;
  }
  if ( v22 )
  {
    *((_QWORD *)a2 + 4) = v22;
    VariantClear(&pvarg);
  }
  ReleaseInterface(v62);
  ReleaseInterface((struct IUnknown *)pdispVal);
  ReleaseInterface(*((struct IUnknown **)a2 + 1));
  v37 = CBase::SetErrorInfo(this, URLMoniker);
  CStr::_Free((CStr *)&v63);
  return v37;
}

```

## disassembly

```asm
0x18087efc8  mov     [rsp-8+arg_10], rbx
0x18087efcd  push    rbp
0x18087efce  push    rsi
0x18087efcf  push    rdi
0x18087efd0  push    r12
0x18087efd2  push    r13
0x18087efd4  push    r14
0x18087efd6  push    r15
0x18087efd8  lea     rbp, [rsp-2060h]
0x18087efe0  mov     eax, 2160h
0x18087efe5  call    _alloca_probe
0x18087efea  sub     rsp, rax
0x18087efed  mov     rax, cs:__security_cookie
0x18087eff4  xor     rax, rsp
0x18087eff7  mov     [rbp+2090h+var_40], rax
0x18087effe  xor     edi, edi
0x18087f000  mov     r14, rcx
0x18087f003  mov     rcx, [rcx+68h]; struct CMarkup *
0x18087f007  mov     rsi, rdx
0x18087f00a  mov     [rsp+2190h+var_2118], edi
0x18087f00e  mov     r12d, edi
0x18087f011  mov     [rsp+2190h+var_2138], rdi
0x18087f016  mov     [rsp+2190h+bstrString], rdi
0x18087f01b  mov     ebx, [rcx+2ECh]
0x18087f021  shl     ebx, 2
0x18087f024  not     ebx
0x18087f026  mov     [rbp+2090h+var_2108], rdi
0x18087f02a  and     ebx, 8000000h
0x18087f030  mov     [rbp+2090h+var_20E8], rdi
0x18087f034  call    ?GetUrl@CMarkup@@SAPEBGQEBV1@@Z; CMarkup::GetUrl(CMarkup const * const)
0x18087f039  or      [rsi+68h], ebx
0x18087f03c  mov     r13, rax
0x18087f03f  xor     eax, eax
0x18087f041  mov     [rsp+2190h+var_2130], rdi
0x18087f046  xorps   xmm0, xmm0
0x18087f049  mov     qword ptr [rbp+2090h+pvarg+10h], rax
0x18087f04d  mov     rcx, r14; this
0x18087f050  mov     [rsp+2190h+var_2128], rdi
0x18087f055  movups  xmmword ptr [rbp+2090h+pvarg], xmm0
0x18087f059  mov     [rbp+2090h+var_2110], rdi
0x18087f05d  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18087f062  test    rax, rax
0x18087f065  jz      loc_18087F829
0x18087f06b  mov     rcx, r14; this
0x18087f06e  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18087f073  cmp     [rax+60h], rdi
0x18087f077  jz      loc_18087F829
0x18087f07d  mov     ecx, 10000019h
0x18087f082  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18087f088  test    al, al
0x18087f08a  jz      loc_18087F254
0x18087f090  xor     edx, edx; Val
0x18087f092  lea     r8d, [r12+58h]; Size
0x18087f097  lea     rcx, [rbp+2090h+var_20A0]; void *
0x18087f09b  mov     edi, 80070005h
0x18087f0a0  call    memset_0
0x18087f0a5  mov     rcx, [r14+68h]; this
0x18087f0a9  xor     r15d, r15d
0x18087f0ac  mov     [rsp+2190h+bstrString], r15
0x18087f0b1  mov     [rbp+2090h+var_205C], 20h ; ' '
0x18087f0b8  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x18087f0bd  test    rax, rax
0x18087f0c0  jz      short loc_18087F0E9
0x18087f0c2  mov     rcx, [r14+68h]; this
0x18087f0c6  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x18087f0cb  mov     rcx, rax
0x18087f0ce  lea     rdx, [rsp+2190h+bstrString]
0x18087f0d3  call    cs:__imp_?EDL_GetDomainFromUri@@YAJPEAUIUri@@PEAPEAG@Z; EDL_GetDomainFromUri(IUri *,ushort * *)
0x18087f0d9  mov     rcx, [rbp+2090h+var_2068]
0x18087f0dd  test    eax, eax
0x18087f0df  cmovns  rcx, [rsp+2190h+bstrString]
0x18087f0e5  mov     [rbp+2090h+var_2068], rcx
0x18087f0e9  mov     rcx, r14; this
0x18087f0ec  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18087f0f1  mov     rcx, [r14+68h]; this
0x18087f0f5  mov     rbx, rax
0x18087f0f8  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x18087f0fd  movzx   r8d, al; int
0x18087f101  lea     r9, [rbp+2090h+var_20A0]; struct BLOCKED_ACTION_DETAILS *
0x18087f105  mov     edx, 40000000h; unsigned int
0x18087f10a  mov     rcx, rbx; this
0x18087f10d  call    ?OnPageActionBlocked@CDoc@@QEAAJKHPEAUBLOCKED_ACTION_DETAILS@@@Z; CDoc::OnPageActionBlocked(ulong,int,BLOCKED_ACTION_DETAILS *)
0x18087f112  mov     eax, cs:dword_181559C88
0x18087f118  cmp     [rsi+40h], r15d
0x18087f11c  jz      loc_18087F1B1
0x18087f122  cmp     eax, 5
0x18087f125  jbe     loc_18087F241
0x18087f12b  mov     rdx, 408000000000h
0x18087f135  lea     rcx, dword_181559C88
0x18087f13c  call    _tlgKeywordOn
0x18087f141  test    al, al
0x18087f143  jz      loc_18087F241
0x18087f149  mov     rax, [rsp+2190h+bstrString]
0x18087f14e  mov     [rsp+2190h+var_2140], r15b
0x18087f153  mov     r15d, 1
0x18087f159  mov     [rsp+2190h+var_213F], r15b
0x18087f15e  mov     [rbp+2090h+var_2100], rax
0x18087f162  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18087f168  mov     ecx, 10000003h
0x18087f16d  mov     [rbp+2090h+var_20F8], rax
0x18087f171  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18087f177  mov     [rbp+2090h+var_20F0], rax
0x18087f17b  lea     rdx, byte_181519145
0x18087f182  lea     rax, [rsp+2190h+var_2140]
0x18087f187  mov     [rsp+2190h+var_2150], rax
0x18087f18c  lea     rax, [rbp+2090h+var_2100]
0x18087f190  mov     qword ptr [rsp+2190h+var_2158], rax
0x18087f195  lea     rax, [rsp+2190h+var_213F]
0x18087f19a  mov     qword ptr [rsp+2190h+dwReserved], rax
0x18087f19f  lea     rax, [rbp+2090h+var_20F8]
0x18087f1a3  mov     [rsp+2190h+pcchResult], rax
0x18087f1a8  lea     rax, [rbp+2090h+var_20F0]
0x18087f1ac  jmp     loc_18087F237
0x18087f1b1  cmp     eax, 5
0x18087f1b4  jbe     loc_18087F241
0x18087f1ba  mov     rdx, 408000000000h
0x18087f1c4  lea     rcx, dword_181559C88
0x18087f1cb  call    _tlgKeywordOn
0x18087f1d0  test    al, al
0x18087f1d2  jz      short loc_18087F241
0x18087f1d4  mov     rax, [rsp+2190h+bstrString]
0x18087f1d9  mov     [rsp+2190h+var_213F], r15b
0x18087f1de  mov     r15d, 1
0x18087f1e4  mov     [rsp+2190h+var_2140], r15b
0x18087f1e9  mov     [rbp+2090h+var_20F0], rax
0x18087f1ed  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18087f1f3  mov     ecx, 10000003h
0x18087f1f8  mov     [rbp+2090h+var_20F8], rax
0x18087f1fc  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18087f202  mov     [rbp+2090h+var_2100], rax
0x18087f206  lea     rdx, word_1815190D6
0x18087f20d  lea     rax, [rsp+2190h+var_213F]
0x18087f212  mov     [rsp+2190h+var_2150], rax
0x18087f217  lea     rax, [rbp+2090h+var_20F0]
0x18087f21b  mov     qword ptr [rsp+2190h+var_2158], rax
0x18087f220  lea     rax, [rsp+2190h+var_2140]
0x18087f225  mov     qword ptr [rsp+2190h+dwReserved], rax
0x18087f22a  lea     rax, [rbp+2090h+var_20F8]
0x18087f22e  mov     [rsp+2190h+pcchResult], rax
0x18087f233  lea     rax, [rbp+2090h+var_2100]
0x18087f237  mov     qword ptr [rsp+2190h+cchResult], rax
0x18087f23c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x18087f241  mov     rcx, [rsp+2190h+bstrString]; bstrString
0x18087f246  call    cs:__imp_SysFreeString
0x18087f24c  mov     rbx, r12
0x18087f24f  jmp     loc_18087F4DD
0x18087f254  mov     rcx, [rsi+38h]
0x18087f258  mov     edx, 400Ch
0x18087f25d  test    rcx, rcx
0x18087f260  jz      short loc_18087F271
0x18087f262  cmp     [rcx], dx
0x18087f265  jnz     short loc_18087F274
0x18087f267  mov     rcx, [rcx+8]
0x18087f26b  mov     [rsi+38h], rcx
0x18087f26f  jmp     short loc_18087F274
0x18087f271  mov     rcx, rdi
0x18087f274  mov     rax, [rsi+20h]
0x18087f278  test    rax, rax
0x18087f27b  jz      short loc_18087F28A
0x18087f27d  cmp     [rax], dx
0x18087f280  jnz     short loc_18087F28A
0x18087f282  mov     rax, [rax+8]
0x18087f286  mov     [rsi+20h], rax
0x18087f28a  mov     edx, 8
0x18087f28f  test    rcx, rcx
0x18087f292  jz      short loc_18087F2A9
0x18087f294  lea     eax, [rdx+2]
0x18087f297  cmp     ax, [rcx]
0x18087f29a  jnz     short loc_18087F305
0x18087f29c  cmp     dword ptr [rcx+8], 80020004h
0x18087f2a3  jnz     short loc_18087F2A9
0x18087f2a5  mov     [rsi+38h], rdi
0x18087f2a9  mov     rcx, [rsi+18h]
0x18087f2ad  mov     ebx, edi
0x18087f2af  mov     r15d, 1
0x18087f2b5  test    rcx, rcx
0x18087f2b8  jz      short loc_18087F31E
0x18087f2ba  cmp     [rcx], di
0x18087f2bd  jz      short loc_18087F31E
0x18087f2bf  call    IsSpecialUrl
0x18087f2c4  test    eax, eax
0x18087f2c6  jz      short loc_18087F33C
0x18087f2c8  mov     rcx, [rsi+18h]; unsigned __int16 *
0x18087f2cc  lea     rdx, [rbp+2090h+var_2108]; struct CStr *
0x18087f2d0  mov     r8, r13; unsigned __int16 *
0x18087f2d3  call    ?WrapSpecialUrl@@YAJPEAGPEAVCStr@@PEBG@Z; WrapSpecialUrl(ushort *,CStr *,ushort const *)
0x18087f2d8  test    eax, eax
0x18087f2da  jnz     loc_18087F4DD
0x18087f2e0  lea     rdx, [rsp+2190h+bstrString]; unsigned __int16 **
0x18087f2e5  lea     rcx, [rbp+2090h+var_2108]; this
0x18087f2e9  call    ?AllocBSTR@CStr@@QEBAJPEAPEAG@Z; CStr::AllocBSTR(ushort * *)
0x18087f2ee  mov     edi, eax
0x18087f2f0  test    eax, eax
0x18087f2f2  jnz     short loc_18087F314
0x18087f2f4  mov     r12, [rsp+2190h+bstrString]
0x18087f2f9  mov     ebx, r15d
0x18087f2fc  mov     [rsp+2190h+var_2138], r12
0x18087f301  xor     edi, edi
0x18087f303  jmp     short loc_18087F33C
0x18087f305  cmp     dx, [rcx]
0x18087f308  jz      short loc_18087F2A9
0x18087f30a  mov     edi, 80070057h
0x18087f30f  jmp     loc_18087F24C
0x18087f314  mov     rcx, [rsp+2190h+bstrString]
0x18087f319  jmp     loc_18087F4E2
0x18087f31e  cmp     [rsi+40h], edi
0x18087f321  jz      loc_18087F81F
0x18087f327  lea     rcx, pcszURL; "about:blank"
0x18087f32e  call    cs:__imp_SysAllocString
0x18087f334  mov     r12, rax
0x18087f337  mov     [rsp+2190h+var_2138], rax
0x18087f33c  mov     rcx, [rsi+18h]; unsigned __int16 *
0x18087f340  call    ?IsUrlHandledByBlobProtocol@@YA_NPEBG@Z; IsUrlHandledByBlobProtocol(ushort const *)
0x18087f345  test    al, al
0x18087f347  jz      short loc_18087F358
0x18087f349  mov     edi, 80070005h
0x18087f34e  mov     rbx, [rsp+2190h+var_2130]
0x18087f353  jmp     loc_18087F4DD
0x18087f358  mov     rdx, [rsi+38h]
0x18087f35c  mov     eax, 8
0x18087f361  cmp     ax, [rdx]
0x18087f364  jnz     short loc_18087F3BA
0x18087f366  mov     rdx, [rdx+8]; unsigned __int16 *
0x18087f36a  test    rdx, rdx
0x18087f36d  jz      short loc_18087F3BA
0x18087f36f  cmp     di, [rdx]
0x18087f372  jz      short loc_18087F3BA
0x18087f374  lea     r8, [rsp+2190h+bstrString]; struct CStr *
0x18087f379  mov     [rsp+2190h+bstrString], rdi
0x18087f37e  mov     rcx, r14; this
0x18087f381  mov     [rbp+2090h+var_20E8], rdx
0x18087f385  mov     byte ptr [rsp+2190h+cchResult], r15b; bool
0x18087f38a  call    ?FilterOutFeaturesString@CWindow@@IEAAJPEAGPEAVCStr@@PEBG_N@Z; CWindow::FilterOutFeaturesString(ushort *,CStr *,ushort const *,bool)
0x18087f38f  mov     rdx, [rsi+38h]
0x18087f393  lea     rcx, [rsp+2190h+bstrString]; this
0x18087f398  add     rdx, 8; unsigned __int16 **
0x18087f39c  call    ?AllocBSTR@CStr@@QEBAJPEAPEAG@Z; CStr::AllocBSTR(ushort * *)
0x18087f3a1  lea     rcx, [rsp+2190h+bstrString]; this
0x18087f3a6  mov     edi, eax
0x18087f3a8  test    eax, eax
0x18087f3aa  jz      short loc_18087F3B3
0x18087f3ac  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x18087f3b1  jmp     short loc_18087F34E
0x18087f3b3  call    ?_Free@CStr@@AEAAXXZ; CStr::_Free(void)
0x18087f3b8  xor     edi, edi
0x18087f3ba  mov     rcx, r14; this
0x18087f3bd  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18087f3c2  test    byte ptr [rax+1304h], 80h
0x18087f3c9  jz      loc_18087F45D
0x18087f3cf  mov     rcx, r14; this
0x18087f3d2  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18087f3d7  mov     r9d, [rax+13B8h]
0x18087f3de  mov     r8d, [rax+13BCh]
0x18087f3e5  mov     edx, [rax+13B4h]
0x18087f3eb  mov     ecx, [rax+13B0h]
0x18087f3f1  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x18087f3f6  test    al, al
0x18087f3f8  jnz     short loc_18087F45D
0x18087f3fa  mov     rcx, r14; this
0x18087f3fd  mov     edi, 80004001h
0x18087f402  call    ?Doc@CWindow@@QEAAPEAVCDoc@@XZ; CWindow::Doc(void)
0x18087f407  mov     rcx, [rax+60h]
0x18087f40b  test    rcx, rcx
0x18087f40e  jz      loc_18087F34E
0x18087f414  mov     rcx, [rcx+88h]
0x18087f41b  test    rcx, rcx
0x18087f41e  jz      loc_18087F34E
0x18087f424  mov     rax, [rcx]
0x18087f427  mov     r8, r12
0x18087f42a  mov     rdx, [rsi+98h]
0x18087f431  mov     r10, [rax+40h]
0x18087f435  mov     rax, [rsi+38h]
0x18087f439  test    r12, r12
0x18087f43c  jnz     short loc_18087F442
0x18087f43e  mov     r8, [rsi+18h]
0x18087f442  mov     r9, [rax+8]
0x18087f446  mov     rax, r10
0x18087f449  mov     qword ptr [rsp+2190h+cchResult], rdx
0x18087f44e  mov     edx, [rsi+40h]
0x18087f451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18087f456  mov     edi, eax
0x18087f458  jmp     loc_18087F34E
0x18087f45d  mov     rdx, r12
0x18087f460  test    r12, r12
0x18087f463  jnz     short loc_18087F469
0x18087f465  mov     rdx, [rsi+18h]; pwzRelativeUrl
0x18087f469  lea     rax, [rsp+2190h+var_2118]
0x18087f46e  mov     [rsp+2190h+dwReserved], edi; dwReserved
0x18087f472  mov     [rsp+2190h+pcchResult], rax; pcchResult
0x18087f477  lea     r9, [rbp+2090h+pszResult]; pszResult
0x18087f47b  mov     r12d, 1000h
0x18087f481  mov     r8d, 6000000h; dwCombineFlags
0x18087f487  mov     rcx, r13; pwzBaseUrl
0x18087f48a  mov     [rsp+2190h+cchResult], r12d; int
0x18087f48f  call    cs:__imp_CoInternetCombineUrl
0x18087f495  mov     edi, eax
0x18087f497  test    eax, eax
0x18087f499  jnz     loc_18087F34E
0x18087f49f  test    ebx, ebx
0x18087f4a1  jz      loc_18087F578
  ... truncated ...
```
