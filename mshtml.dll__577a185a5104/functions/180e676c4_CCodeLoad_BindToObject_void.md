# CCodeLoad::BindToObject(void)

- ea: `0x180e676c4`
- end: `0x180e684ae`
- name: `?BindToObject@CCodeLoad@@AEAAJXZ`
- size: `3562`
- prototype: `__int64 __fastcall(CCodeLoad *__hidden this)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180e6887c`

## callees

- `0x18005ce98`
- `0x18005e648`
- `0x180066940`
- `0x1800ea428`
- `0x180138ce4`
- `0x180139080`
- `0x1801393a8`
- `0x18015a504`
- `0x18028fff0`
- `0x180306fdc`
- `0x1803e13d4`
- `0x1803e41f0`
- `0x180402a84`
- `0x180402d68`
- `0x180422abc`
- `0x1805be6ec`
- `0x1806b2820`
- `0x180709f4c`
- `0x180712534`
- `0x180716bf0`
- `0x180722a10`
- `0x18077b900`
- `0x1807cc154`
- `0x1807e2190`
- `0x1807ead80`
- `0x18083bed4`
- `0x18084bd8c`
- `0x18087594c`
- `0x180883a8c`
- `0x180899984`
- `0x1808fc784`
- `0x180a39750`
- `0x180e5a014`
- `0x180e5a990`
- `0x180e63eac`
- `0x180e676c4`
- `0x180e6876c`
- `0x180e6a004`
- `0x180e6a1b8`
- `0x180e6a51c`
- `0x1810f64f2`
- `0x181104010`

## import_xrefs

- `msvcrt!wcschr` at `0x180e67beb`
- `msvcrt!wcschr` at `0x180e67beb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180e67b76`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180e67b76`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180e67c35`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180e67c35`
- `iertutil!CreateUri` at `0x180e67ae2`
- `iertutil!CreateUri` at `0x180e67ae2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e677f4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e677f4`
- `ole32!CoGetClassObject` at `0x180e683ec`
- `ole32!CoGetClassObject` at `0x180e683ec`
- `ole32!MkParseDisplayName` at `0x180e67c5a`
- `ole32!MkParseDisplayName` at `0x180e67c5a`
- `urlmon!CreateAsyncBindCtxEx` at `0x180e67751`
- `urlmon!CreateAsyncBindCtxEx` at `0x180e67751`
- `urlmon!RegisterBindStatusCallback` at `0x180e67787`
- `urlmon!RegisterBindStatusCallback` at `0x180e67787`
- `urlmon!MkParseDisplayNameEx` at `0x180e67cd3`
- `urlmon!MkParseDisplayNameEx` at `0x180e67cd3`
- `urlmon!__imp_CoGetClassObjectFromURLInternal` at `0x180e6822d`
- `urlmon!__imp_CoGetClassObjectFromURLInternal` at `0x180e6822d`
- `OLEAUT32!__imp_SysAllocString` at `0x180e67d96`
- `OLEAUT32!__imp_SysAllocString` at `0x180e67dd0`
- `OLEAUT32!__imp_SysAllocString` at `0x180e68030`
- `OLEAUT32!__imp_SysAllocString` at `0x180e6806f`
- `OLEAUT32!__imp_SysAllocString` at `0x180e67d96`
- `OLEAUT32!__imp_SysAllocString` at `0x180e67dd0`
- `OLEAUT32!__imp_SysAllocString` at `0x180e68030`
- `OLEAUT32!__imp_SysAllocString` at `0x180e6806f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e67d86`
- `OLEAUT32!__imp_SysFreeString` at `0x180e67db9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e68020`
- `OLEAUT32!__imp_SysFreeString` at `0x180e68057`
- `OLEAUT32!__imp_SysFreeString` at `0x180e67d86`
- `OLEAUT32!__imp_SysFreeString` at `0x180e67db9`
- `OLEAUT32!__imp_SysFreeString` at `0x180e68020`
- `OLEAUT32!__imp_SysFreeString` at `0x180e68057`

## string_xrefs

- `0x180e6819e`: `__EXTENSIONVALIDATION`
- `0x180e67896`: `__ACTIVEXINSTALL_USER_SCOPE`
- `0x180e67978`: `__SZ_MARKUP_URI`
- `0x180e67888`: `__ACTIVEXINSTALL_MACHINE_SCOPE`
- `0x180e677c6`: `__RESTRICT_ACTIVEXINSTALL`

## pseudocode

```c
__int64 __fastcall CCodeLoad::BindToObject(CCodeLoad *this)
{
  int v2; // r12d
  CElement *v3; // rcx
  struct IHTMLElement *v4; // rax
  CElement *v5; // rcx
  CDoc *v6; // rbx
  LPBC *v7; // r15
  struct CMarkup *WindowedMarkupContext; // r13
  int AsyncBindCtx; // edi
  IBindCtx *v10; // rcx
  CDoc *v11; // rcx
  __int64 v12; // rax
  struct INSTALLPACKAGEINFO *InstallPackageInfo; // rax
  int v14; // ebx
  const wchar_t *v15; // rdx
  struct IUri *v16; // r8
  const WCHAR *v17; // rbx
  struct CMarkup *MarkupPtr; // rax
  CElement *v19; // rcx
  CMarkup *v20; // rax
  wchar_t *v21; // rax
  LPMONIKER v22; // rax
  HRESULT v23; // ebx
  const struct CElement *v24; // r8
  CHtmCtx *v25; // rbx
  const OLECHAR *ReferrerUrl; // rax
  struct IUnknown *v27; // r8
  GUID *v28; // rdx
  struct IInternetSecurityManagerEx2 *v29; // r15
  int SecurityManager; // ebx
  HRESULT (__stdcall *ProcessUrlAction)(IInternetSecurityManagerEx2 *, LPCWSTR, DWORD, BYTE *, DWORD, BYTE *, DWORD, DWORD, DWORD); // rbx
  const unsigned __int16 *PrimaryUrl; // rax
  __int64 v33; // r15
  const OLECHAR *v34; // rax
  bool IsPendingRoot; // al
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  BOOL v38; // eax
  const WCHAR *v39; // rbx
  bool v40; // al
  bool v41; // zf
  __int64 v42; // rcx
  struct IHTMLDocument2 *v43; // r9
  HRESULT ClassObject; // eax
  int v45; // eax
  IBindCtx **ppBC; // [rsp+20h] [rbp-E0h]
  char v48; // [rsp+60h] [rbp-A0h]
  unsigned int v49; // [rsp+64h] [rbp-9Ch] BYREF
  struct IHTMLElement *v50; // [rsp+68h] [rbp-98h] BYREF
  ULONG pchEaten; // [rsp+70h] [rbp-90h] BYREF
  struct IInternetSecurityManagerEx2 *v52; // [rsp+78h] [rbp-88h] BYREF
  int v53; // [rsp+80h] [rbp-80h]
  LPCWSTR pwzURI; // [rsp+88h] [rbp-78h] BYREF
  IUri *ppURI; // [rsp+90h] [rbp-70h] BYREF
  LPMONIKER ppmk; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v57[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v58; // [rsp+B0h] [rbp-50h]
  wchar_t *Str[2]; // [rsp+B8h] [rbp-48h]
  int v60; // [rsp+C8h] [rbp-38h]
  LPVOID ppv; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v62[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v63; // [rsp+E8h] [rbp-18h]
  PCWSTR psz1[2]; // [rsp+F0h] [rbp-10h]
  int v65; // [rsp+100h] [rbp+0h]
  struct IUnknown *v66; // [rsp+108h] [rbp+8h] BYREF
  IBindStatusCallback *v67; // [rsp+110h] [rbp+10h]

  v2 = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  v3 = (CElement *)*((_QWORD *)this + 33);
  ppv = 0;
  ppmk = 0;
  v66 = 0;
  v4 = (struct IHTMLElement *)CElement::Doc(v3);
  v5 = (CElement *)*((_QWORD *)this + 33);
  v6 = (CDoc *)v4;
  v50 = v4;
  ppURI = 0;
  v7 = (LPBC *)((char *)this + 256);
  WindowedMarkupContext = CElement::GetWindowedMarkupContext(v5);
  AsyncBindCtx = CreateAsyncBindCtxEx(0, 0, 0, 0, (IBindCtx **)this + 32, 0);
  if ( AsyncBindCtx )
    goto LABEL_154;
  v10 = *v7;
  v67 = (IBindStatusCallback *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
  AsyncBindCtx = RegisterBindStatusCallback(v10, v67, 0, 0);
  if ( (unsigned int)AsyncBindCtx > 1 )
    goto LABEL_154;
  if ( v6 )
  {
    if ( WindowedMarkupContext )
    {
      if ( !CDoc::IsPageActionAllowed(v11, WindowedMarkupContext, 2u) )
      {
        AsyncBindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, unsigned __int64))(*v7)->lpVtbl->RegisterObjectParam)(
                         *v7,
                         L"__RESTRICT_ACTIVEXINSTALL",
                         ((unsigned __int64)this + 208) & -(__int64)(this != 0));
        if ( AsyncBindCtx < 0 )
          goto LABEL_154;
      }
    }
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435481) )
  {
    v12 = *((_QWORD *)this + 33);
    if ( v12 )
    {
      if ( (*(_DWORD *)(v12 + 432) & 0x2000000) != 0 )
      {
        AsyncBindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, unsigned __int64))(*v7)->lpVtbl->RegisterObjectParam)(
                         *v7,
                         L"__SZ_ALLOW_WEBBROWSER_IN_IMMERSIVE_MODE",
                         ((unsigned __int64)this + 208) & -(__int64)(this != 0));
        if ( AsyncBindCtx < 0 )
          goto LABEL_154;
      }
    }
  }
  InstallPackageInfo = COleSite::GetInstallPackageInfo(
                         *((COleSite **)this + 33),
                         *((const unsigned __int16 **)this + 40));
  if ( InstallPackageInfo )
  {
    v14 = *((_DWORD *)InstallPackageInfo + 2);
    if ( (unsigned int)(v14 - 1) > 1 )
    {
LABEL_19:
      v6 = (CDoc *)v50;
      goto LABEL_20;
    }
    INSTALLPACKAGEINFO::Reset(InstallPackageInfo);
    if ( v14 == 1 )
    {
      v15 = L"__ACTIVEXINSTALL_MACHINE_SCOPE";
    }
    else
    {
      if ( v14 != 2 )
        goto LABEL_18;
      v15 = L"__ACTIVEXINSTALL_USER_SCOPE";
    }
    AsyncBindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, unsigned __int64))(*v7)->lpVtbl->RegisterObjectParam)(
                     *v7,
                     v15,
                     ((unsigned __int64)this + 208) & -(__int64)(this != 0));
LABEL_18:
    if ( AsyncBindCtx < 0 )
      goto LABEL_154;
    goto LABEL_19;
  }
LABEL_20:
  if ( *((int *)WindowedMarkupContext + 212) >= 90000
    && (!memcmp_0((char *)this + 288, &CLSID_SVGDocument, 0x10u)
     || !memcmp_0((char *)this + 288, &CLSID_HTMLDocument, 0x10u)
     || !memcmp_0((char *)this + 288, &CLSID_XHTMLDocument, 0x10u)
     || !memcmp_0((char *)this + 288, &CLSID_XMLDocument, 0x10u)
     || !memcmp_0((char *)this + 288, &CLSID_XMLDocument_Private, 0x10u)) )
  {
    AsyncBindCtx = -2147024891;
    goto LABEL_154;
  }
  v16 = CMarkup::Uri(WindowedMarkupContext);
  if ( v16 )
  {
    AsyncBindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, struct IUri *))(*v7)->lpVtbl->RegisterObjectParam)(
                     *v7,
                     L"__SZ_MARKUP_URI",
                     v16);
    if ( AsyncBindCtx < 0 )
      goto LABEL_154;
  }
  if ( !memcmp_0(&g_Zero, (char *)this + 288, 0x10u) && !*((_QWORD *)this + 43) )
  {
    v17 = (const WCHAR *)*((_QWORD *)this + 44);
    pchEaten = 0;
    v57[0] = &CUString::`vftable';
    v57[1] = 0;
    v58 = 11;
    v60 = 0;
    v62[0] = &CUString::`vftable';
    v62[1] = 0;
    v63 = 11;
    v65 = 0;
    *(_OWORD *)Str = 0;
    *(_OWORD *)psz1 = 0;
    if ( v17 )
    {
      *((_DWORD *)this + 132) |= 0x80u;
    }
    else
    {
      v17 = (const WCHAR *)*((_QWORD *)this + 41);
      MarkupPtr = CElement::GetMarkupPtr(*((CElement **)this + 33));
      if ( !MarkupPtr )
        goto LABEL_77;
      v49 = 0;
      CMarkup::ProcessURLAction(MarkupPtr, 4612, &v49, 0, 0, 0, 0, 0, 0);
      if ( !v49 )
      {
        if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
          COleSite::LogControlBlock(*((_QWORD *)this + 33), 2, 0, (char *)this + 288, *((_QWORD *)this + 40));
        AsyncBindCtx = -2147024891;
        goto LABEL_39;
      }
      if ( !v17 )
      {
LABEL_77:
        AsyncBindCtx = -2147467259;
        goto LABEL_39;
      }
    }
    AsyncBindCtx = CreateUri(v17, 0x3002B85u, 0, &ppURI);
    if ( AsyncBindCtx )
    {
      ppURI = 0;
LABEL_39:
      v62[0] = &CUString::`vftable';
      CUString::Set((CUString *)v62, 0, Uri_PROPERTY_RAW_URI);
      v57[0] = &CUString::`vftable';
      CUString::Set((CUString *)v57, 0, Uri_PROPERTY_RAW_URI);
      goto LABEL_154;
    }
    if ( (unsigned int)CUString::Set((CUString *)v57, ppURI, Uri_PROPERTY_ABSOLUTE_URI)
      && (unsigned int)CUString::Set((CUString *)v57, ppURI, Uri_PROPERTY_RAW_URI) )
    {
      AsyncBindCtx = -2147467259;
      goto LABEL_39;
    }
    if ( !(unsigned int)CUString::Set((CUString *)v62, ppURI, Uri_PROPERTY_EXTENSION) && !StrCmpIW(psz1[1], L".HTA") )
      goto LABEL_39;
    v19 = (CElement *)*((_QWORD *)this + 33);
    if ( (*((_DWORD *)v19 + 15) & 0x40000) != 0 )
    {
      v20 = CElement::GetMarkupPtr(v19);
      if ( (unsigned int)CMarkup::IsUrlRecursive(v20, Str[1]) )
        goto LABEL_39;
    }
    AsyncBindCtx = -2147467259;
    if ( !(unsigned int)CUString::Set((CUString *)v62, ppURI, Uri_PROPERTY_SCHEME) )
    {
      if ( (unsigned int)_tcsnipre(L"mhtml", 5, psz1[1], v65) )
      {
        v21 = wcschr(Str[1], 0x21u);
        if ( v21 )
        {
          if ( (unsigned int)_tcsnipre(L"cid:", 4, v21 + 1, -1) )
            goto LABEL_39;
        }
      }
    }
    if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_LIMIT_MONIKERS) )
      goto LABEL_59;
    if ( StrStrIW(Str[1], L"winmgmts") )
      goto LABEL_39;
    if ( MkParseDisplayName(*v7, Str[1], &pchEaten, &ppmk) )
    {
      v22 = 0;
      ppmk = 0;
    }
    else
    {
LABEL_59:
      v22 = ppmk;
    }
    if ( !v22 )
    {
      if ( ((unsigned int (__fastcall *)(LPBC, const wchar_t *, LPBC))(*v7)->lpVtbl->RegisterObjectParam)(
             *v7,
             L"NO_OLE_FALLBACK",
             *v7) )
      {
LABEL_62:
        AsyncBindCtx = -2147024891;
        goto LABEL_39;
      }
      v23 = CMarkup::CheckForLMZLLoad(v50, ppURI, WindowedMarkupContext, 2);
      if ( !v23 )
        v23 = MkParseDisplayNameEx(*v7, Str[1], &pchEaten, &ppmk);
      ((void (__fastcall *)(LPBC, const wchar_t *))(*v7)->lpVtbl->RevokeObjectParam)(*v7, L"NO_OLE_FALLBACK");
      if ( v23 )
      {
        ppmk = 0;
        goto LABEL_62;
      }
    }
    v24 = (const struct CElement *)*((_QWORD *)this + 33);
    v52 = 0;
    v50 = 0;
    CMarkup::GetBaseUrl(0, (const unsigned __int16 **)&v52, v24, 0, 0);
    AsyncBindCtx = CStr::Set((const unsigned __int16 **)&v50, (const unsigned __int16 *)v52);
    if ( AsyncBindCtx
      || (AsyncBindCtx = AddBindContextParam(*v7, (struct CStr *)&v50, *((struct IPropertyBag **)this + 47), 0, 0)) != 0 )
    {
LABEL_68:
      CStr::_Free((CStr *)&v50);
      goto LABEL_39;
    }
    SysFreeString(*((BSTR *)this + 62));
    *((_QWORD *)this + 62) = SysAllocString(Str[1]);
    v25 = (CHtmCtx *)*((_QWORD *)WindowedMarkupContext + 15);
    if ( v25 )
    {
      SysFreeString(*((BSTR *)this + 63));
      ReferrerUrl = CHtmCtx::GetReferrerUrl(v25);
      *((_QWORD *)this + 63) = SysAllocString(ReferrerUrl);
    }
    AsyncBindCtx = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, struct IUnknown **))ppmk->lpVtbl->BindToObject)(
                     ppmk,
                     *v7,
                     0,
                     &IID_IUnknown,
                     &v66);
    if ( AsyncBindCtx < 0 )
    {
      v66 = 0;
      goto LABEL_68;
    }
    CStr::_Free((CStr *)&v50);
    v62[0] = &CUString::`vftable';
    CUString::Set((CUString *)v62, 0, Uri_PROPERTY_RAW_URI);
    v57[0] = &CUString::`vftable';
    CUString::Set((CUString *)v57, 0, Uri_PROPERTY_RAW_URI);
    if ( !AsyncBindCtx )
    {
LABEL_75:
      v27 = (struct IUnknown *)ppv;
      if ( ppv )
      {
        v28 = &IID_IClassFactory;
      }
      else
      {
        v27 = v66;
        v28 = &IID_IUnknown;
      }
      AsyncBindCtx = CCodeLoad::OnObjectAvailable((CCodeLoad *)((char *)this + 24), v28, v27);
      goto LABEL_154;
    }
    goto LABEL_128;
  }
  if ( !v6 )
  {
    AsyncBindCtx = -2147467259;
    goto LABEL_154;
  }
  v52 = 0;
  AsyncBindCtx = CDoc::GetActiveXSafetyProvider(v6, (struct IActiveXSafetyProvider **)&v52);
  if ( AsyncBindCtx )
    goto LABEL_154;
  v29 = v52;
  if ( v52 )
  {
    v49 = 0;
    AsyncBindCtx = CMarkup::ProcessURLAction(WindowedMarkupContext, 4613, &v49, 0, 0, 0, 0, 0, 0);
    if ( AsyncBindCtx )
    {
      if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        COleSite::LogControlBlock(*((_QWORD *)this + 33), 1, 0, (char *)this + 288, *((_QWORD *)this + 40));
      goto LABEL_154;
    }
    AsyncBindCtx = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, _QWORD))v29->lpVtbl->SetSecuritySite)(
                     v29,
                     v49);
    if ( AsyncBindCtx )
      goto LABEL_154;
    v41 = (*((_BYTE *)WindowedMarkupContext + 97) & 2) == 0;
    v52 = 0;
    if ( !v41 )
    {
      SecurityManager = CDoc::Deprecated_GetSecurityManager(v6, &v52, 1);
      if ( SecurityManager >= 0 )
        goto LABEL_91;
      v6 = (CDoc *)v50;
    }
    SecurityManager = CDoc::Deprecated_GetSecurityManager(v6, &v52, 0);
LABEL_91:
    AsyncBindCtx = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, struct IInternetSecurityManagerEx2 *))v29->lpVtbl->MapUrlToZone)(
                     v29,
                     v52);
    if ( SecurityManager >= 0 )
      ((void (__fastcall *)(struct IInternetSecurityManagerEx2 *))v52->lpVtbl->Release)(v52);
    if ( AsyncBindCtx )
      goto LABEL_154;
    ProcessUrlAction = v29->lpVtbl->ProcessUrlAction;
    PrimaryUrl = CDoc::GetPrimaryUrl((CDoc *)v50);
    AsyncBindCtx = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, const unsigned __int16 *))ProcessUrlAction)(
                     v29,
                     PrimaryUrl);
    if ( AsyncBindCtx )
      goto LABEL_154;
  }
  if ( ((__int64)v50[556].lpVtbl & 0x400) != 0 )
  {
    if ( CCodeLoad::_IsPrerendering(this) )
    {
      CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&pwzURI, WindowedMarkupContext);
      if ( pwzURI )
        AsyncBindCtx = CPreloadManager::SuspendDuringPrerender(pwzURI, 0);
      TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(&pwzURI);
    }
    v41 = AsyncBindCtx == 0;
    if ( AsyncBindCtx < 0 )
      goto LABEL_126;
    v42 = *((_QWORD *)this + 33);
    v50 = 0;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v42 + 1624LL) != _vtguard )
      _report_securityfailure(1);
    if ( (*(int (__fastcall **)(__int64, GUID *, struct IHTMLElement **))(*(_QWORD *)v42 + 1536LL))(
           v42,
           &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b,
           &v50) >= 0 )
    {
      if ( (unsigned int)CMarkup::OnExtensionLoading(
                           WindowedMarkupContext,
                           (const struct _GUID *)this + 18,
                           ExtensionValidationContextParsed,
                           v43,
                           (struct CMarkup *)ppBC,
                           v50) == -2147024891 )
        AsyncBindCtx = -2147024891;
      ((void (*)(void))v50->lpVtbl->Release)();
      v41 = AsyncBindCtx == 0;
      if ( AsyncBindCtx < 0 )
      {
LABEL_126:
        if ( v41 )
        {
          if ( *((_QWORD *)this + 33) )
            goto LABEL_75;
          AsyncBindCtx = -2147024891;
          goto LABEL_154;
        }
        goto LABEL_127;
      }
    }
    if ( v29 )
      ClassObject = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, char *, __int64))v29->lpVtbl->ProcessUrlActionEx2)(
                      v29,
                      (char *)this + 288,
                      7);
    else
      ClassObject = CoGetClassObject((const IID *const)this + 18, 7u, 0, &IID_IClassFactory, &ppv);
    AsyncBindCtx = ClassObject;
LABEL_125:
    v41 = AsyncBindCtx == 0;
    goto LABEL_126;
  }
  v33 = *((_QWORD *)this + 32);
  v48 = 1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
  SysFreeString(*((BSTR *)this + 62));
  *((_QWORD *)this + 62) = SysAllocString(*((const OLECHAR **)this + 40));
  pwzURI = (LPCWSTR)*((_QWORD *)WindowedMarkupContext + 15);
  if ( pwzURI )
  {
    SysFreeString(*((BSTR *)this + 63));
    v34 = CHtmCtx::GetReferrerUrl((CHtmCtx *)pwzURI);
    *((_QWORD *)this + 63) = SysAllocString(v34);
  }
  pwzURI = (LPCWSTR)*((_QWORD *)this + 62);
  if ( !pwzURI
    || (IsPendingRoot = CMarkup::IsPendingRoot(WindowedMarkupContext),
        v36 = CMarkup::ValidateSecureUrl(WindowedMarkupContext, IsPendingRoot, pwzURI, 0, 0, 0, TAGID_OBJECT, 1),
        v53 = 0,
        v36) )
  {
    v53 = 1;
  }
  v37 = (const unsigned __int16 *)*((_QWORD *)this + 62);
  v38 = 0;
  LODWORD(v52) = 0;
  v49 = 0;
  pchEaten = 0;
  if ( v37 )
  {
    AsyncBindCtx = IsObjectAttributeBlockedForTrackingProtection(
                     v37,
                     WindowedMarkupContext,
                     (enum _ePrivacIEURIState *)&pchEaten,
                     (int *)&v52);
    if ( AsyncBindCtx < 0 )
    {
      v38 = v49;
    }
    else
    {
      v38 = pchEaten == 2;
      v49 = v38;
    }
  }
  if ( !v53 || (v53 = 0, v38) )
    v53 = 1;
  if ( CCodeLoad::_IsPrerendering(this) )
  {
    CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&pwzURI, WindowedMarkupContext);
    if ( pwzURI )
    {
      AsyncBindCtx = CPreloadManager::SuspendDuringPrerender(pwzURI, 0);
      if ( AsyncBindCtx < 0 )
      {
        v48 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
    }
    TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(&pwzURI);
    if ( !v48 )
      goto LABEL_125;
  }
  if ( !CDoc::IsExtensionValidationEnabled((CDoc *)v50)
    || (*(int (__fastcall **)(__int64, const wchar_t *, IBindStatusCallback *))(*(_QWORD *)v33 + 72LL))(
         v33,
         L"__EXTENSIONVALIDATION",
         v67) >= 0 )
  {
    AsyncBindCtx = CoGetClassObjectFromURLInternal(
                     (char *)this + 288,
                     *((_QWORD *)this + 40),
                     *((unsigned int *)this + 84),
                     *((unsigned int *)this + 85),
                     *((_QWORD *)this + 43),
                     *((_QWORD *)this + 32),
                     7,
                     0,
                     &IID_IClassFactory,
                     &ppv,
                     v53);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( AsyncBindCtx == -2147024891 || (_DWORD)v52 )
    {
      if ( (_DWORD)v52 )
        UpdatePrivacIENotifyUIAndConsoleForTrackingProtection(*((_QWORD *)this + 62), WindowedMarkupContext, pchEaten);
      if ( AsyncBindCtx == -2147024891 )
      {
        if ( !v49 )
        {
          v39 = (const WCHAR *)*((_QWORD *)this + 62);
          v40 = CMarkup::IsPendingRoot(WindowedMarkupContext);
          CMarkup::ValidateSecureUrl(WindowedMarkupContext, v40, v39, 0, 0, 0, TAGID_OBJECT, 0);
        }
        goto LABEL_127;
      }
    }
    if ( AsyncBindCtx == -2146695934 )
      AsyncBindCtx = -2146697200;
    goto LABEL_125;
  }
  AsyncBindCtx = -2147024891;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_127:
  ppv = 0;
LABEL_128:
  if ( AsyncBindCtx == 262632 )
  {
    v2 = 0;
    goto LABEL_154;
  }
  v45 = *((_DWORD *)this + 122);
  switch ( v45 )
  {
    case 0:
LABEL_147:
      CCodeLoad::SyncBindError(this, AsyncBindCtx);
      break;
    case 3:
      if ( (*((_BYTE *)this + 528) & 8) != 0 )
        break;
      goto LABEL_147;
    case 2:
      *((_DWORD *)this + 132) |= 2u;
      *((_DWORD *)this + 130) = AsyncBindCtx;
      break;
  }
LABEL_154:
  ReleaseInterface((struct IUnknown *)ppv);
  ReleaseInterface((struct IUnknown *)ppmk);
  ReleaseInterface(v66);
  ReleaseInterface((struct IUnknown *)ppURI);
  if ( v2 )
    CCodeLoad::RevokeBindStatusCallback(this);
  CBaseFT::Release(this);
  return (unsigned int)AsyncBindCtx;
}

```

## disassembly

```asm
0x180e676c4  mov     [rsp-8+arg_0], rcx
0x180e676c9  push    rbp
0x180e676ca  push    rbx
0x180e676cb  push    rsi
0x180e676cc  push    rdi
0x180e676cd  push    r12
0x180e676cf  push    r13
0x180e676d1  push    r14
0x180e676d3  push    r15
0x180e676d5  lea     rbp, [rsp-28h]
0x180e676da  sub     rsp, 128h
0x180e676e1  mov     rsi, [rbp+60h+arg_0]
0x180e676e5  mov     r12d, 1
0x180e676eb  lock add [rsi+10h], r12d
0x180e676f0  mov     rcx, [rsi+108h]; this
0x180e676f7  mov     [rbp+60h+ppv], 0
0x180e676ff  mov     [rbp+60h+ppmk], 0
0x180e67707  mov     [rbp+60h+var_58], 0
0x180e6770f  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180e67714  mov     rcx, [rsi+108h]; this
0x180e6771b  mov     rbx, rax
0x180e6771e  mov     [rsp+160h+var_F8], rax
0x180e67723  mov     [rbp+60h+ppURI], 0
0x180e6772b  call    ?GetWindowedMarkupContext@CElement@@UEBAPEAVCMarkup@@XZ; CElement::GetWindowedMarkupContext(void)
0x180e67730  lea     r15, [rsi+100h]
0x180e67737  mov     [rsp+160h+reserved], 0; reserved
0x180e6773f  xor     r9d, r9d; pEnum
0x180e67742  mov     [rsp+160h+ppBC], r15; ppBC
0x180e67747  xor     r8d, r8d; pBSCb
0x180e6774a  xor     edx, edx; dwOptions
0x180e6774c  xor     ecx, ecx; pbc
0x180e6774e  mov     r13, rax
0x180e67751  call    cs:__imp_CreateAsyncBindCtxEx
0x180e67758  nop     dword ptr [rax+rax+00h]
0x180e6775d  mov     edi, eax
0x180e6775f  test    eax, eax
0x180e67761  jnz     loc_180E68455
0x180e67767  lea     rdx, [rsi+18h]
0x180e6776b  mov     rcx, rsi
0x180e6776e  neg     rcx
0x180e67771  mov     rcx, [r15]; pBC
0x180e67774  sbb     rax, rax
0x180e67777  xor     r9d, r9d; dwReserved
0x180e6777a  and     rax, rdx
0x180e6777d  xor     r8d, r8d; ppBSCBPrev
0x180e67780  mov     rdx, rax; pBSCb
0x180e67783  mov     [rbp+60h+var_50], rax
0x180e67787  call    cs:__imp_RegisterBindStatusCallback
0x180e6778e  nop     dword ptr [rax+rax+00h]
0x180e67793  mov     edi, eax
0x180e67795  cmp     eax, r12d
0x180e67798  ja      loc_180E68455
0x180e6779e  test    rbx, rbx
0x180e677a1  jz      short loc_180E677EF
0x180e677a3  test    r13, r13
0x180e677a6  jz      short loc_180E677EF
0x180e677a8  lea     r8d, [r12+1]; unsigned int
0x180e677ad  mov     rdx, r13; struct CMarkup *
0x180e677b0  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180e677b5  test    eax, eax
0x180e677b7  jnz     short loc_180E677EF
0x180e677b9  mov     r10, [r15]
0x180e677bc  lea     rcx, [rsi+0D0h]
0x180e677c3  mov     rax, rsi
0x180e677c6  lea     rdx, aRestrictActive; "__RESTRICT_ACTIVEXINSTALL"
0x180e677cd  neg     rax
0x180e677d0  mov     r9, [r10]
0x180e677d3  sbb     r8, r8
0x180e677d6  and     r8, rcx
0x180e677d9  mov     rcx, r10
0x180e677dc  mov     rax, [r9+48h]
0x180e677e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e677e5  mov     edi, eax
0x180e677e7  test    eax, eax
0x180e677e9  js      loc_180E68455
0x180e677ef  mov     ecx, 10000019h
0x180e677f4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180e677fb  nop     dword ptr [rax+rax+00h]
0x180e67800  test    al, al
0x180e67802  jz      short loc_180E67854
0x180e67804  mov     rax, [rsi+108h]
0x180e6780b  test    rax, rax
0x180e6780e  jz      short loc_180E67854
0x180e67810  mov     eax, [rax+1B0h]
0x180e67816  shr     eax, 19h
0x180e67819  test    r12b, al
0x180e6781c  jz      short loc_180E67854
0x180e6781e  mov     r10, [r15]
0x180e67821  lea     rcx, [rsi+0D0h]
0x180e67828  mov     rax, rsi
0x180e6782b  lea     rdx, aSzAllowWebbrow; "__SZ_ALLOW_WEBBROWSER_IN_IMMERSIVE_MODE"
0x180e67832  neg     rax
0x180e67835  mov     r9, [r10]
0x180e67838  sbb     r8, r8
0x180e6783b  and     r8, rcx
0x180e6783e  mov     rcx, r10
0x180e67841  mov     rax, [r9+48h]
0x180e67845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e6784a  mov     edi, eax
0x180e6784c  test    eax, eax
0x180e6784e  js      loc_180E68455
0x180e67854  mov     rcx, [rsi+108h]; this
0x180e6785b  lea     r14, [rsi+120h]
0x180e67862  mov     rdx, [r14+20h]; unsigned __int16 *
0x180e67866  call    ?GetInstallPackageInfo@COleSite@@QEAAPEAVINSTALLPACKAGEINFO@@PEBG@Z; COleSite::GetInstallPackageInfo(ushort const *)
0x180e6786b  test    rax, rax
0x180e6786e  jz      short loc_180E678D1
0x180e67870  mov     ebx, [rax+8]
0x180e67873  lea     ecx, [rbx-1]
0x180e67876  cmp     ecx, r12d
0x180e67879  ja      short loc_180E678CC
0x180e6787b  mov     rcx, rax; this
0x180e6787e  call    ?Reset@INSTALLPACKAGEINFO@@QEAAXXZ; INSTALLPACKAGEINFO::Reset(void)
0x180e67883  cmp     ebx, r12d
0x180e67886  jnz     short loc_180E67891
0x180e67888  lea     rdx, aActivexinstall; "__ACTIVEXINSTALL_MACHINE_SCOPE"
0x180e6788f  jmp     short loc_180E6789D
0x180e67891  cmp     ebx, 2
0x180e67894  jnz     short loc_180E678C4
0x180e67896  lea     rdx, aActivexinstall_0; "__ACTIVEXINSTALL_USER_SCOPE"
0x180e6789d  mov     r10, [r15]
0x180e678a0  lea     rcx, [rsi+0D0h]
0x180e678a7  mov     rax, rsi
0x180e678aa  neg     rax
0x180e678ad  mov     r9, [r10]
0x180e678b0  sbb     r8, r8
0x180e678b3  and     r8, rcx
0x180e678b6  mov     rcx, r10
0x180e678b9  mov     rax, [r9+48h]
0x180e678bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e678c2  mov     edi, eax
0x180e678c4  test    edi, edi
0x180e678c6  js      loc_180E68455
0x180e678cc  mov     rbx, [rsp+160h+var_F8]
0x180e678d1  cmp     dword ptr [r13+350h], 15F90h
0x180e678dc  jl      loc_180E67963
0x180e678e2  mov     r8d, 10h; Size
0x180e678e8  lea     rdx, CLSID_SVGDocument; Buf2
0x180e678ef  mov     rcx, r14; Buf1
0x180e678f2  call    memcmp_0
0x180e678f7  xor     edi, edi
0x180e678f9  test    eax, eax
0x180e678fb  jz      short loc_180E67959
0x180e678fd  lea     r8d, [rdi+10h]; Size
0x180e67901  mov     rcx, r14; Buf1
0x180e67904  lea     rdx, CLSID_HTMLDocument; Buf2
0x180e6790b  call    memcmp_0
0x180e67910  test    eax, eax
0x180e67912  jz      short loc_180E67959
0x180e67914  lea     r8d, [rdi+10h]; Size
0x180e67918  mov     rcx, r14; Buf1
0x180e6791b  lea     rdx, CLSID_XHTMLDocument; Buf2
0x180e67922  call    memcmp_0
0x180e67927  test    eax, eax
0x180e67929  jz      short loc_180E67959
0x180e6792b  lea     r8d, [rdi+10h]; Size
0x180e6792f  mov     rcx, r14; Buf1
0x180e67932  lea     rdx, CLSID_XMLDocument; Buf2
0x180e67939  call    memcmp_0
0x180e6793e  test    eax, eax
0x180e67940  jz      short loc_180E67959
0x180e67942  lea     r8d, [rdi+10h]; Size
0x180e67946  mov     rcx, r14; Buf1
0x180e67949  lea     rdx, CLSID_XMLDocument_Private; Buf2
0x180e67950  call    memcmp_0
0x180e67955  test    eax, eax
0x180e67957  jnz     short loc_180E67965
0x180e67959  mov     edi, 80070005h
0x180e6795e  jmp     loc_180E68455
0x180e67963  xor     edi, edi
0x180e67965  mov     rcx, r13; this
0x180e67968  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e6796d  mov     r8, rax
0x180e67970  test    rax, rax
0x180e67973  jz      short loc_180E6799A
0x180e67975  mov     r9, [r15]
0x180e67978  lea     rdx, aSzMarkupUri; "__SZ_MARKUP_URI"
0x180e6797f  mov     rcx, [r9]
0x180e67982  mov     rax, [rcx+48h]
0x180e67986  mov     rcx, r9
0x180e67989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e6798e  mov     edi, eax
0x180e67990  test    eax, eax
0x180e67992  js      loc_180E68455
0x180e67998  xor     edi, edi
0x180e6799a  mov     r8d, 10h; Size
0x180e679a0  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; Buf1
0x180e679a7  mov     rdx, r14; Buf2
0x180e679aa  call    memcmp_0
0x180e679af  test    eax, eax
0x180e679b1  jnz     loc_180E67E80
0x180e679b7  cmp     [r14+38h], rdi
0x180e679bb  jnz     loc_180E67E80
0x180e679c1  mov     rbx, [r14+40h]
0x180e679c5  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x180e679cc  mov     [rsp+160h+pchEaten], edi
0x180e679d0  mov     eax, 0Bh
0x180e679d5  mov     [rbp+60h+var_C0], rcx
0x180e679d9  xorps   xmm0, xmm0
0x180e679dc  mov     [rbp+60h+var_B8], rdi
0x180e679e0  mov     [rbp+60h+var_B0], eax
0x180e679e3  mov     [rbp+60h+var_98], edi
0x180e679e6  mov     [rbp+60h+var_88], rcx
0x180e679ea  mov     [rbp+60h+var_80], rdi
0x180e679ee  mov     [rbp+60h+var_78], eax
0x180e679f1  mov     [rbp+60h+var_60], edi
0x180e679f4  movdqu  xmmword ptr [rbp+60h+Str], xmm0
0x180e679f9  movdqu  xmmword ptr [rbp+60h+psz1], xmm0
0x180e679fe  test    rbx, rbx
0x180e67a01  jz      short loc_180E67A10
0x180e67a03  bts     dword ptr [rsi+210h], 7
0x180e67a0b  jmp     loc_180E67AD3
0x180e67a10  mov     rcx, [rsi+108h]; this
0x180e67a17  mov     rbx, [r14+28h]
0x180e67a1b  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x180e67a20  test    rax, rax
0x180e67a23  jz      loc_180E67E76
0x180e67a29  mov     dword ptr [rsp+160h+var_120], edi
0x180e67a2d  lea     r8, [rsp+160h+var_FC]
0x180e67a32  mov     [rsp+160h+var_128], edi
0x180e67a36  xor     r9d, r9d
0x180e67a39  mov     qword ptr [rsp+160h+var_130], rdi
0x180e67a3e  mov     edx, 1204h
0x180e67a43  mov     qword ptr [rsp+160h+reserved], rdi
0x180e67a48  mov     rcx, rax
0x180e67a4b  mov     [rsp+160h+ppBC], rdi
0x180e67a50  mov     [rsp+160h+var_FC], edi
0x180e67a54  call    ?ProcessURLAction@CMarkup@@QEAAJKPEAHKPEAKPEBGPEAEKW4PUA_Flags@@@Z; CMarkup::ProcessURLAction(ulong,int *,ulong,ulong *,ushort const *,uchar *,ulong,PUA_Flags)
0x180e67a59  cmp     [rsp+160h+var_FC], edi
0x180e67a5d  jnz     short loc_180E67ACA
0x180e67a5f  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r12d; CMPTLGS g_cmptlgs
0x180e67a66  jz      short loc_180E67A90
0x180e67a68  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e67a6d  test    eax, eax
0x180e67a6f  jz      short loc_180E67A90
0x180e67a71  mov     rax, [r14+20h]
0x180e67a75  xor     r8d, r8d
0x180e67a78  mov     rcx, [rsi+108h]
0x180e67a7f  mov     r9, r14
0x180e67a82  mov     [rsp+160h+ppBC], rax
0x180e67a87  lea     edx, [r8+2]
0x180e67a8b  call    ?LogControlBlock@COleSite@@QEAAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEBG@Z; COleSite::LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,ushort const *)
0x180e67a90  mov     edi, 80070005h
0x180e67a95  mov     ebx, 0Bh
0x180e67a9a  lea     r15, ??_7CUString@@6B@; const CUString::`vftable'
0x180e67aa1  mov     r8d, ebx; enum __MIDL_IUri_0001
0x180e67aa4  mov     [rbp+60h+var_88], r15
0x180e67aa8  xor     edx, edx; struct IUri *
0x180e67aaa  lea     rcx, [rbp+60h+var_88]; this
0x180e67aae  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e67ab3  mov     r8d, ebx; enum __MIDL_IUri_0001
0x180e67ab6  xor     edx, edx; struct IUri *
0x180e67ab8  mov     [rbp+60h+var_C0], r15
0x180e67abc  lea     rcx, [rbp+60h+var_C0]; this
0x180e67ac0  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e67ac5  jmp     loc_180E68455
0x180e67aca  test    rbx, rbx
0x180e67acd  jz      loc_180E67E76
0x180e67ad3  lea     r9, [rbp+60h+ppURI]; ppURI
0x180e67ad7  xor     r8d, r8d; dwReserved
0x180e67ada  mov     edx, 3002B85h; dwFlags
0x180e67adf  mov     rcx, rbx; pwzURI
0x180e67ae2  call    cs:__imp_CreateUri
0x180e67ae9  nop     dword ptr [rax+rax+00h]
0x180e67aee  mov     edi, eax
0x180e67af0  test    eax, eax
0x180e67af2  jz      short loc_180E67AFE
0x180e67af4  mov     [rbp+60h+ppURI], 0
0x180e67afc  jmp     short loc_180E67A95
0x180e67afe  mov     rdx, [rbp+60h+ppURI]; struct IUri *
0x180e67b02  lea     rcx, [rbp+60h+var_C0]; this
0x180e67b06  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180e67b09  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e67b0e  mov     r14d, 0Bh
0x180e67b14  test    eax, eax
0x180e67b16  jz      short loc_180E67B52
0x180e67b18  mov     rdx, [rbp+60h+ppURI]; struct IUri *
0x180e67b1c  lea     rcx, [rbp+60h+var_C0]; this
0x180e67b20  mov     r8d, r14d; enum __MIDL_IUri_0001
0x180e67b23  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e67b28  test    eax, eax
0x180e67b2a  jz      short loc_180E67B52
0x180e67b2c  mov     edi, 80004005h
0x180e67b31  lea     r15, ??_7CUString@@6B@; const CUString::`vftable'
0x180e67b38  mov     r8d, r14d; enum __MIDL_IUri_0001
0x180e67b3b  xor     edx, edx; struct IUri *
0x180e67b3d  mov     [rbp+60h+var_88], r15
0x180e67b41  lea     rcx, [rbp+60h+var_88]; this
0x180e67b45  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e67b4a  mov     r8d, r14d
0x180e67b4d  jmp     loc_180E67AB6
0x180e67b52  mov     rdx, [rbp+60h+ppURI]; struct IUri *
0x180e67b56  lea     rcx, [rbp+60h+var_88]; this
0x180e67b5a  mov     ebx, 4
0x180e67b5f  mov     r8d, ebx; enum __MIDL_IUri_0001
0x180e67b62  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e67b67  test    eax, eax
0x180e67b69  jnz     short loc_180E67B86
0x180e67b6b  mov     rcx, [rbp+60h+psz1+8]; psz1
0x180e67b6f  lea     rdx, aHta_0; ".HTA"
  ... truncated ...
```
