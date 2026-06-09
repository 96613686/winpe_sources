# CCodeLoad::BindToObject(void)

- ea: `0x180e42504`
- end: `0x180e4327b`
- name: `?BindToObject@CCodeLoad@@AEAAJXZ`
- size: `3447`
- prototype: `__int64 __fastcall(CCodeLoad *__hidden this)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180e43648`

## callees

- `0x18006f7c8`
- `0x1800e2b08`
- `0x1800e45d8`
- `0x1800e4964`
- `0x1800e4c70`
- `0x1801bf344`
- `0x1801c0acc`
- `0x18021f9bc`
- `0x180300084`
- `0x18030035c`
- `0x180369bc0`
- `0x18043c328`
- `0x1804dc5f4`
- `0x1804e223c`
- `0x1805480a8`
- `0x1805ccd98`
- `0x1806b4ee0`
- `0x1806f45d8`
- `0x1807053f0`
- `0x180710b80`
- `0x180718b20`
- `0x180771400`
- `0x1807be8d8`
- `0x1807d6afc`
- `0x1807de498`
- `0x180831b94`
- `0x1808393c4`
- `0x180848cf4`
- `0x18086f73c`
- `0x18087ca0c`
- `0x18089159c`
- `0x1808f022c`
- `0x180a269bc`
- `0x180e35298`
- `0x180e3ee58`
- `0x180e42504`
- `0x180e43530`
- `0x180e44d24`
- `0x180e44ed0`
- `0x180e45214`
- `0x1810c2c92`
- `0x1810d1010`

## import_xrefs

- `msvcrt!wcschr` at `0x180e42a0d`
- `msvcrt!wcschr` at `0x180e42a0d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180e4299e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x180e4299e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180e42a51`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrIW` at `0x180e42a51`
- `iertutil!CreateUri` at `0x180e42910`
- `iertutil!CreateUri` at `0x180e42910`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e42628`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180e42628`
- `ole32!CoGetClassObject` at `0x180e431c0`
- `ole32!CoGetClassObject` at `0x180e431c0`
- `ole32!MkParseDisplayName` at `0x180e42a70`
- `ole32!MkParseDisplayName` at `0x180e42a70`
- `urlmon!CreateAsyncBindCtxEx` at `0x180e42591`
- `urlmon!CreateAsyncBindCtxEx` at `0x180e42591`
- `urlmon!RegisterBindStatusCallback` at `0x180e425c1`
- `urlmon!RegisterBindStatusCallback` at `0x180e425c1`
- `urlmon!MkParseDisplayNameEx` at `0x180e42ae3`
- `urlmon!MkParseDisplayNameEx` at `0x180e42ae3`
- `urlmon!__imp_CoGetClassObjectFromURLInternal` at `0x180e43007`
- `urlmon!__imp_CoGetClassObjectFromURLInternal` at `0x180e43007`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42b9a`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42bc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42e1c`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42e4f`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42b9a`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42bc8`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42e1c`
- `OLEAUT32!__imp_SysAllocString` at `0x180e42e4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42b90`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42bb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42e12`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42e3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42b90`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42bb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42e12`
- `OLEAUT32!__imp_SysFreeString` at `0x180e42e3d`

## string_xrefs

- `0x180e427a6`: `__SZ_MARKUP_URI`
- `0x180e42f78`: `__EXTENSIONVALIDATION`
- `0x180e426b6`: `__ACTIVEXINSTALL_MACHINE_SCOPE`
- `0x180e426c4`: `__ACTIVEXINSTALL_USER_SCOPE`
- `0x180e425fa`: `__RESTRICT_ACTIVEXINSTALL`

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
  HRESULT AsyncBindCtx; // edi
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
  enum _ELEMENT_TAG_ID v48[2]; // [rsp+30h] [rbp-D0h]
  char v49; // [rsp+60h] [rbp-A0h]
  unsigned int v50; // [rsp+64h] [rbp-9Ch] BYREF
  struct IHTMLElement *v51; // [rsp+68h] [rbp-98h] BYREF
  ULONG pchEaten; // [rsp+70h] [rbp-90h] BYREF
  struct IInternetSecurityManagerEx2 *v53; // [rsp+78h] [rbp-88h] BYREF
  int v54; // [rsp+80h] [rbp-80h]
  LPCWSTR pwzURI; // [rsp+88h] [rbp-78h] BYREF
  IUri *ppURI; // [rsp+90h] [rbp-70h] BYREF
  LPMONIKER ppmk; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v58[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v59; // [rsp+B0h] [rbp-50h]
  wchar_t *Str[2]; // [rsp+B8h] [rbp-48h]
  int v61; // [rsp+C8h] [rbp-38h]
  LPVOID ppv; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v63[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v64; // [rsp+E8h] [rbp-18h]
  PCWSTR psz1[2]; // [rsp+F0h] [rbp-10h]
  int v66; // [rsp+100h] [rbp+0h]
  struct IUnknown *v67; // [rsp+108h] [rbp+8h] BYREF
  IBindStatusCallback *v68; // [rsp+110h] [rbp+10h]

  v2 = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  v3 = (CElement *)*((_QWORD *)this + 33);
  ppv = 0;
  ppmk = 0;
  v67 = 0;
  v4 = (struct IHTMLElement *)CElement::Doc(v3);
  v5 = (CElement *)*((_QWORD *)this + 33);
  v6 = (CDoc *)v4;
  v51 = v4;
  ppURI = 0;
  v7 = (LPBC *)((char *)this + 256);
  WindowedMarkupContext = CElement::GetWindowedMarkupContext(v5);
  AsyncBindCtx = CreateAsyncBindCtxEx(0, 0, 0, 0, (IBindCtx **)this + 32, 0);
  if ( AsyncBindCtx )
    goto LABEL_154;
  v10 = *v7;
  v68 = (IBindStatusCallback *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
  AsyncBindCtx = RegisterBindStatusCallback(v10, v68, 0, 0);
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
      v6 = (CDoc *)v51;
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
    v58[0] = &CUString::`vftable';
    v58[1] = 0;
    v59 = 11;
    v61 = 0;
    v63[0] = &CUString::`vftable';
    v63[1] = 0;
    v64 = 11;
    v66 = 0;
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
      v50 = 0;
      CMarkup::ProcessURLAction(MarkupPtr, 4612, &v50, 0);
      if ( !v50 )
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
      v63[0] = &CUString::`vftable';
      CUString::Set((CUString *)v63, 0, Uri_PROPERTY_RAW_URI);
      v58[0] = &CUString::`vftable';
      CUString::Set((CUString *)v58, 0, Uri_PROPERTY_RAW_URI);
      goto LABEL_154;
    }
    if ( (unsigned int)CUString::Set((CUString *)v58, ppURI, Uri_PROPERTY_ABSOLUTE_URI)
      && (unsigned int)CUString::Set((CUString *)v58, ppURI, Uri_PROPERTY_RAW_URI) )
    {
      AsyncBindCtx = -2147467259;
      goto LABEL_39;
    }
    if ( !(unsigned int)CUString::Set((CUString *)v63, ppURI, Uri_PROPERTY_EXTENSION) && !StrCmpIW(psz1[1], L".HTA") )
      goto LABEL_39;
    v19 = (CElement *)*((_QWORD *)this + 33);
    if ( (*((_DWORD *)v19 + 15) & 0x40000) != 0 )
    {
      v20 = CElement::GetMarkupPtr(v19);
      if ( (unsigned int)CMarkup::IsUrlRecursive(v20, Str[1]) )
        goto LABEL_39;
    }
    AsyncBindCtx = -2147467259;
    if ( !(unsigned int)CUString::Set((CUString *)v63, ppURI, Uri_PROPERTY_SCHEME) )
    {
      if ( (unsigned int)_tcsnipre(L"mhtml", 5, psz1[1], v66) )
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
      v23 = CMarkup::CheckForLMZLLoad(v51, ppURI, WindowedMarkupContext, 2);
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
    v53 = 0;
    v51 = 0;
    CMarkup::GetBaseUrl(0, (const unsigned __int16 **)&v53, v24, 0, 0);
    AsyncBindCtx = CStr::Set((CStr *)&v51, (const unsigned __int16 *)v53);
    if ( AsyncBindCtx
      || (AsyncBindCtx = AddBindContextParam(*v7, (struct CStr *)&v51, *((struct IPropertyBag **)this + 47), 0, 0)) != 0 )
    {
LABEL_68:
      CStr::_Free((CStr *)&v51);
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
                     &v67);
    if ( AsyncBindCtx < 0 )
    {
      v67 = 0;
      goto LABEL_68;
    }
    CStr::_Free((CStr *)&v51);
    v63[0] = &CUString::`vftable';
    CUString::Set((CUString *)v63, 0, Uri_PROPERTY_RAW_URI);
    v58[0] = &CUString::`vftable';
    CUString::Set((CUString *)v58, 0, Uri_PROPERTY_RAW_URI);
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
        v27 = v67;
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
  v53 = 0;
  AsyncBindCtx = CDoc::GetActiveXSafetyProvider(v6, (struct IActiveXSafetyProvider **)&v53);
  if ( AsyncBindCtx )
    goto LABEL_154;
  v29 = v53;
  if ( v53 )
  {
    v48[1] = TAGID_NULL;
    ppBC = 0;
    v50 = 0;
    AsyncBindCtx = CMarkup::ProcessURLAction(WindowedMarkupContext, 4613, &v50, 0);
    if ( AsyncBindCtx )
    {
      if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
        COleSite::LogControlBlock(*((_QWORD *)this + 33), 1, 0, (char *)this + 288, *((_QWORD *)this + 40));
      goto LABEL_154;
    }
    AsyncBindCtx = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, _QWORD))v29->lpVtbl->SetSecuritySite)(
                     v29,
                     v50);
    if ( AsyncBindCtx )
      goto LABEL_154;
    v41 = (*((_BYTE *)WindowedMarkupContext + 97) & 2) == 0;
    v53 = 0;
    if ( !v41 )
    {
      SecurityManager = CDoc::Deprecated_GetSecurityManager(v6, &v53, 1);
      if ( SecurityManager >= 0 )
        goto LABEL_91;
      v6 = (CDoc *)v51;
    }
    SecurityManager = CDoc::Deprecated_GetSecurityManager(v6, &v53, 0);
LABEL_91:
    AsyncBindCtx = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, struct IInternetSecurityManagerEx2 *))v29->lpVtbl->MapUrlToZone)(
                     v29,
                     v53);
    if ( SecurityManager >= 0 )
      ((void (__fastcall *)(struct IInternetSecurityManagerEx2 *))v53->lpVtbl->Release)(v53);
    if ( AsyncBindCtx )
      goto LABEL_154;
    ProcessUrlAction = v29->lpVtbl->ProcessUrlAction;
    PrimaryUrl = CDoc::GetPrimaryUrl((CDoc *)v51);
    AsyncBindCtx = ((__int64 (__fastcall *)(struct IInternetSecurityManagerEx2 *, const unsigned __int16 *))ProcessUrlAction)(
                     v29,
                     PrimaryUrl);
    if ( AsyncBindCtx )
      goto LABEL_154;
  }
  if ( ((__int64)v51[556].lpVtbl & 0x400) != 0 )
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
    v51 = 0;
    if ( *(__int64 (__fastcall **)())(*(_QWORD *)v42 + 1624LL) != _vtguard )
      _report_securityfailure(1);
    if ( (*(int (__fastcall **)(__int64, GUID *, struct IHTMLElement **))(*(_QWORD *)v42 + 1536LL))(
           v42,
           &GUID_3050f1ff_98b5_11cf_bb82_00aa00bdce0b,
           &v51) >= 0 )
    {
      if ( (unsigned int)CMarkup::OnExtensionLoading(
                           WindowedMarkupContext,
                           (const struct _GUID *)this + 18,
                           ExtensionValidationContextParsed,
                           v43,
                           (struct CMarkup *)ppBC,
                           v51) == -2147024891 )
        AsyncBindCtx = -2147024891;
      ((void (*)(void))v51->lpVtbl->Release)();
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
  v49 = 1;
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
        v54 = 0,
        v36) )
  {
    v54 = 1;
  }
  v37 = (const unsigned __int16 *)*((_QWORD *)this + 62);
  v38 = 0;
  LODWORD(v53) = 0;
  v50 = 0;
  pchEaten = 0;
  if ( v37 )
  {
    AsyncBindCtx = IsObjectAttributeBlockedForTrackingProtection(
                     v37,
                     WindowedMarkupContext,
                     (enum _ePrivacIEURIState *)&pchEaten,
                     (int *)&v53);
    if ( AsyncBindCtx < 0 )
    {
      v38 = v50;
    }
    else
    {
      v38 = pchEaten == 2;
      v50 = v38;
    }
  }
  if ( !v54 || (v54 = 0, v38) )
    v54 = 1;
  if ( CCodeLoad::_IsPrerendering(this) )
  {
    CPreloadManagerLock::CPreloadManagerLock((CPreloadManagerLock *)&pwzURI, WindowedMarkupContext);
    if ( pwzURI )
    {
      AsyncBindCtx = CPreloadManager::SuspendDuringPrerender(pwzURI, 0);
      if ( AsyncBindCtx < 0 )
      {
        v49 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
    }
    TSmartPointer<CPreloadManager>::~TSmartPointer<CPreloadManager>(&pwzURI);
    if ( !v49 )
      goto LABEL_125;
  }
  if ( !CDoc::IsExtensionValidationEnabled((CDoc *)v51)
    || (*(int (__fastcall **)(__int64, const wchar_t *, IBindStatusCallback *))(*(_QWORD *)v33 + 72LL))(
         v33,
         L"__EXTENSIONVALIDATION",
         v68) >= 0 )
  {
    v48[0] = TAGID_B;
    AsyncBindCtx = CoGetClassObjectFromURLInternal(
                     (char *)this + 288,
                     *((_QWORD *)this + 40),
                     *((unsigned int *)this + 84),
                     *((unsigned int *)this + 85),
                     *((_QWORD *)this + 43),
                     *((_QWORD *)this + 32),
                     *(_QWORD *)v48,
                     0,
                     &IID_IClassFactory,
                     &ppv,
                     v54);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( AsyncBindCtx == -2147024891 || (_DWORD)v53 )
    {
      if ( (_DWORD)v53 )
        UpdatePrivacIENotifyUIAndConsoleForTrackingProtection(*((_QWORD *)this + 62), WindowedMarkupContext, pchEaten);
      if ( AsyncBindCtx == -2147024891 )
      {
        if ( !v50 )
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
  ReleaseInterface(v67);
  ReleaseInterface((struct IUnknown *)ppURI);
  if ( v2 )
    CCodeLoad::RevokeBindStatusCallback(this);
  CBaseFT::Release(this);
  return (unsigned int)AsyncBindCtx;
}

```

## disassembly

```asm
0x180e42504  mov     [rsp-8+arg_0], rcx
0x180e42509  push    rbp
0x180e4250a  push    rbx
0x180e4250b  push    rsi
0x180e4250c  push    rdi
0x180e4250d  push    r12
0x180e4250f  push    r13
0x180e42511  push    r14
0x180e42513  push    r15
0x180e42515  lea     rbp, [rsp-28h]
0x180e4251a  sub     rsp, 128h
0x180e42521  mov     rsi, [rbp+60h+arg_0]
0x180e42525  mov     r12d, 1
0x180e4252b  lock add [rsi+10h], r12d
0x180e42530  mov     rcx, [rsi+108h]; this
0x180e42537  mov     [rbp+60h+ppv], 0
0x180e4253f  mov     [rbp+60h+ppmk], 0
0x180e42547  mov     [rbp+60h+var_58], 0
0x180e4254f  call    ?Doc@CElement@@QEBAPEAVCDoc@@XZ; CElement::Doc(void)
0x180e42554  mov     rcx, [rsi+108h]; this
0x180e4255b  mov     rbx, rax
0x180e4255e  mov     [rsp+160h+var_F8], rax
0x180e42563  mov     [rbp+60h+ppURI], 0
0x180e4256b  call    ?GetWindowedMarkupContext@CElement@@UEBAPEAVCMarkup@@XZ; CElement::GetWindowedMarkupContext(void)
0x180e42570  lea     r15, [rsi+100h]
0x180e42577  mov     [rsp+160h+reserved], 0; reserved
0x180e4257f  xor     r9d, r9d; pEnum
0x180e42582  mov     [rsp+160h+ppBC], r15; ppBC
0x180e42587  xor     r8d, r8d; pBSCb
0x180e4258a  xor     edx, edx; dwOptions
0x180e4258c  xor     ecx, ecx; pbc
0x180e4258e  mov     r13, rax
0x180e42591  call    cs:__imp_CreateAsyncBindCtxEx
0x180e42597  mov     edi, eax
0x180e42599  test    eax, eax
0x180e4259b  jnz     loc_180E43223
0x180e425a1  lea     rdx, [rsi+18h]
0x180e425a5  mov     rcx, rsi
0x180e425a8  neg     rcx
0x180e425ab  mov     rcx, [r15]; pBC
0x180e425ae  sbb     rax, rax
0x180e425b1  xor     r9d, r9d; dwReserved
0x180e425b4  and     rax, rdx
0x180e425b7  xor     r8d, r8d; ppBSCBPrev
0x180e425ba  mov     rdx, rax; pBSCb
0x180e425bd  mov     [rbp+60h+var_50], rax
0x180e425c1  call    cs:__imp_RegisterBindStatusCallback
0x180e425c7  mov     edi, eax
0x180e425c9  cmp     eax, r12d
0x180e425cc  ja      loc_180E43223
0x180e425d2  test    rbx, rbx
0x180e425d5  jz      short loc_180E42623
0x180e425d7  test    r13, r13
0x180e425da  jz      short loc_180E42623
0x180e425dc  lea     r8d, [r12+1]; unsigned int
0x180e425e1  mov     rdx, r13; struct CMarkup *
0x180e425e4  call    ?IsPageActionAllowed@CDoc@@QEAAHPEAVCMarkup@@K@Z; CDoc::IsPageActionAllowed(CMarkup *,ulong)
0x180e425e9  test    eax, eax
0x180e425eb  jnz     short loc_180E42623
0x180e425ed  mov     r10, [r15]
0x180e425f0  lea     rcx, [rsi+0D0h]
0x180e425f7  mov     rax, rsi
0x180e425fa  lea     rdx, aRestrictActive; "__RESTRICT_ACTIVEXINSTALL"
0x180e42601  neg     rax
0x180e42604  mov     r9, [r10]
0x180e42607  sbb     r8, r8
0x180e4260a  and     r8, rcx
0x180e4260d  mov     rcx, r10
0x180e42610  mov     rax, [r9+48h]
0x180e42614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e42619  mov     edi, eax
0x180e4261b  test    eax, eax
0x180e4261d  js      loc_180E43223
0x180e42623  mov     ecx, 10000019h
0x180e42628  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180e4262e  test    al, al
0x180e42630  jz      short loc_180E42682
0x180e42632  mov     rax, [rsi+108h]
0x180e42639  test    rax, rax
0x180e4263c  jz      short loc_180E42682
0x180e4263e  mov     eax, [rax+1B0h]
0x180e42644  shr     eax, 19h
0x180e42647  test    r12b, al
0x180e4264a  jz      short loc_180E42682
0x180e4264c  mov     r10, [r15]
0x180e4264f  lea     rcx, [rsi+0D0h]
0x180e42656  mov     rax, rsi
0x180e42659  lea     rdx, aSzAllowWebbrow; "__SZ_ALLOW_WEBBROWSER_IN_IMMERSIVE_MODE"
0x180e42660  neg     rax
0x180e42663  mov     r9, [r10]
0x180e42666  sbb     r8, r8
0x180e42669  and     r8, rcx
0x180e4266c  mov     rcx, r10
0x180e4266f  mov     rax, [r9+48h]
0x180e42673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e42678  mov     edi, eax
0x180e4267a  test    eax, eax
0x180e4267c  js      loc_180E43223
0x180e42682  mov     rcx, [rsi+108h]; this
0x180e42689  lea     r14, [rsi+120h]
0x180e42690  mov     rdx, [r14+20h]; unsigned __int16 *
0x180e42694  call    ?GetInstallPackageInfo@COleSite@@QEAAPEAVINSTALLPACKAGEINFO@@PEBG@Z; COleSite::GetInstallPackageInfo(ushort const *)
0x180e42699  test    rax, rax
0x180e4269c  jz      short loc_180E426FF
0x180e4269e  mov     ebx, [rax+8]
0x180e426a1  lea     ecx, [rbx-1]
0x180e426a4  cmp     ecx, r12d
0x180e426a7  ja      short loc_180E426FA
0x180e426a9  mov     rcx, rax; this
0x180e426ac  call    ?Reset@INSTALLPACKAGEINFO@@QEAAXXZ; INSTALLPACKAGEINFO::Reset(void)
0x180e426b1  cmp     ebx, r12d
0x180e426b4  jnz     short loc_180E426BF
0x180e426b6  lea     rdx, aActivexinstall; "__ACTIVEXINSTALL_MACHINE_SCOPE"
0x180e426bd  jmp     short loc_180E426CB
0x180e426bf  cmp     ebx, 2
0x180e426c2  jnz     short loc_180E426F2
0x180e426c4  lea     rdx, aActivexinstall_0; "__ACTIVEXINSTALL_USER_SCOPE"
0x180e426cb  mov     r10, [r15]
0x180e426ce  lea     rcx, [rsi+0D0h]
0x180e426d5  mov     rax, rsi
0x180e426d8  neg     rax
0x180e426db  mov     r9, [r10]
0x180e426de  sbb     r8, r8
0x180e426e1  and     r8, rcx
0x180e426e4  mov     rcx, r10
0x180e426e7  mov     rax, [r9+48h]
0x180e426eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e426f0  mov     edi, eax
0x180e426f2  test    edi, edi
0x180e426f4  js      loc_180E43223
0x180e426fa  mov     rbx, [rsp+160h+var_F8]
0x180e426ff  cmp     dword ptr [r13+350h], 15F90h
0x180e4270a  jl      loc_180E42791
0x180e42710  mov     r8d, 10h; Size
0x180e42716  lea     rdx, CLSID_SVGDocument; Buf2
0x180e4271d  mov     rcx, r14; Buf1
0x180e42720  call    memcmp_0
0x180e42725  xor     edi, edi
0x180e42727  test    eax, eax
0x180e42729  jz      short loc_180E42787
0x180e4272b  lea     r8d, [rdi+10h]; Size
0x180e4272f  mov     rcx, r14; Buf1
0x180e42732  lea     rdx, CLSID_HTMLDocument; Buf2
0x180e42739  call    memcmp_0
0x180e4273e  test    eax, eax
0x180e42740  jz      short loc_180E42787
0x180e42742  lea     r8d, [rdi+10h]; Size
0x180e42746  mov     rcx, r14; Buf1
0x180e42749  lea     rdx, CLSID_XHTMLDocument; Buf2
0x180e42750  call    memcmp_0
0x180e42755  test    eax, eax
0x180e42757  jz      short loc_180E42787
0x180e42759  lea     r8d, [rdi+10h]; Size
0x180e4275d  mov     rcx, r14; Buf1
0x180e42760  lea     rdx, CLSID_XMLDocument; Buf2
0x180e42767  call    memcmp_0
0x180e4276c  test    eax, eax
0x180e4276e  jz      short loc_180E42787
0x180e42770  lea     r8d, [rdi+10h]; Size
0x180e42774  mov     rcx, r14; Buf1
0x180e42777  lea     rdx, CLSID_XMLDocument_Private; Buf2
0x180e4277e  call    memcmp_0
0x180e42783  test    eax, eax
0x180e42785  jnz     short loc_180E42793
0x180e42787  mov     edi, 80070005h
0x180e4278c  jmp     loc_180E43223
0x180e42791  xor     edi, edi
0x180e42793  mov     rcx, r13; this
0x180e42796  call    ?Uri@CMarkup@@QEAAPEAUIUri@@XZ; CMarkup::Uri(void)
0x180e4279b  mov     r8, rax
0x180e4279e  test    rax, rax
0x180e427a1  jz      short loc_180E427C8
0x180e427a3  mov     r9, [r15]
0x180e427a6  lea     rdx, aSzMarkupUri; "__SZ_MARKUP_URI"
0x180e427ad  mov     rcx, [r9]
0x180e427b0  mov     rax, [rcx+48h]
0x180e427b4  mov     rcx, r9
0x180e427b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180e427bc  mov     edi, eax
0x180e427be  test    eax, eax
0x180e427c0  js      loc_180E43223
0x180e427c6  xor     edi, edi
0x180e427c8  mov     r8d, 10h; Size
0x180e427ce  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; Buf1
0x180e427d5  mov     rdx, r14; Buf2
0x180e427d8  call    memcmp_0
0x180e427dd  test    eax, eax
0x180e427df  jnz     loc_180E42C72
0x180e427e5  cmp     [r14+38h], rdi
0x180e427e9  jnz     loc_180E42C72
0x180e427ef  mov     rbx, [r14+40h]
0x180e427f3  lea     rcx, ??_7CUString@@6B@; const CUString::`vftable'
0x180e427fa  mov     [rsp+160h+pchEaten], edi
0x180e427fe  mov     eax, 0Bh
0x180e42803  mov     [rbp+60h+var_C0], rcx
0x180e42807  xorps   xmm0, xmm0
0x180e4280a  mov     [rbp+60h+var_B8], rdi
0x180e4280e  mov     [rbp+60h+var_B0], eax
0x180e42811  mov     [rbp+60h+var_98], edi
0x180e42814  mov     [rbp+60h+var_88], rcx
0x180e42818  mov     [rbp+60h+var_80], rdi
0x180e4281c  mov     [rbp+60h+var_78], eax
0x180e4281f  mov     [rbp+60h+var_60], edi
0x180e42822  movdqu  xmmword ptr [rbp+60h+Str], xmm0
0x180e42827  movdqu  xmmword ptr [rbp+60h+psz1], xmm0
0x180e4282c  test    rbx, rbx
0x180e4282f  jz      short loc_180E4283E
0x180e42831  bts     dword ptr [rsi+210h], 7
0x180e42839  jmp     loc_180E42901
0x180e4283e  mov     rcx, [rsi+108h]; this
0x180e42845  mov     rbx, [r14+28h]
0x180e42849  call    ?GetMarkupPtr@CElement@@QEBAPEAVCMarkup@@XZ; CElement::GetMarkupPtr(void)
0x180e4284e  test    rax, rax
0x180e42851  jz      loc_180E42C68
0x180e42857  mov     dword ptr [rsp+160h+var_120], edi
0x180e4285b  lea     r8, [rsp+160h+var_FC]
0x180e42860  mov     [rsp+160h+var_128], edi
0x180e42864  xor     r9d, r9d
0x180e42867  mov     qword ptr [rsp+160h+var_130], rdi
0x180e4286c  mov     edx, 1204h
0x180e42871  mov     qword ptr [rsp+160h+reserved], rdi
0x180e42876  mov     rcx, rax
0x180e42879  mov     [rsp+160h+ppBC], rdi
0x180e4287e  mov     [rsp+160h+var_FC], edi
0x180e42882  call    ?ProcessURLAction@CMarkup@@QEAAJKPEAHKPEAKPEBGPEAEKW4PUA_Flags@@@Z; CMarkup::ProcessURLAction(ulong,int *,ulong,ulong *,ushort const *,uchar *,ulong,PUA_Flags)
0x180e42887  cmp     [rsp+160h+var_FC], edi
0x180e4288b  jnz     short loc_180E428F8
0x180e4288d  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, r12d; CMPTLGS g_cmptlgs
0x180e42894  jz      short loc_180E428BE
0x180e42896  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180e4289b  test    eax, eax
0x180e4289d  jz      short loc_180E428BE
0x180e4289f  mov     rax, [r14+20h]
0x180e428a3  xor     r8d, r8d
0x180e428a6  mov     rcx, [rsi+108h]
0x180e428ad  mov     r9, r14
0x180e428b0  mov     [rsp+160h+ppBC], rax
0x180e428b5  lea     edx, [r8+2]
0x180e428b9  call    ?LogControlBlock@COleSite@@QEAAXW4CtrlLoggingEvent@ControlLogging@@_NAEBU_GUID@@PEBG@Z; COleSite::LogControlBlock(ControlLogging::CtrlLoggingEvent,bool,_GUID const &,ushort const *)
0x180e428be  mov     edi, 80070005h
0x180e428c3  mov     ebx, 0Bh
0x180e428c8  lea     r15, ??_7CUString@@6B@; const CUString::`vftable'
0x180e428cf  mov     r8d, ebx; enum __MIDL_IUri_0001
0x180e428d2  mov     [rbp+60h+var_88], r15
0x180e428d6  xor     edx, edx; struct IUri *
0x180e428d8  lea     rcx, [rbp+60h+var_88]; this
0x180e428dc  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e428e1  mov     r8d, ebx; enum __MIDL_IUri_0001
0x180e428e4  xor     edx, edx; struct IUri *
0x180e428e6  mov     [rbp+60h+var_C0], r15
0x180e428ea  lea     rcx, [rbp+60h+var_C0]; this
0x180e428ee  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e428f3  jmp     loc_180E43223
0x180e428f8  test    rbx, rbx
0x180e428fb  jz      loc_180E42C68
0x180e42901  lea     r9, [rbp+60h+ppURI]; ppURI
0x180e42905  xor     r8d, r8d; dwReserved
0x180e42908  mov     edx, 3002B85h; dwFlags
0x180e4290d  mov     rcx, rbx; pwzURI
0x180e42910  call    cs:__imp_CreateUri
0x180e42916  mov     edi, eax
0x180e42918  test    eax, eax
0x180e4291a  jz      short loc_180E42926
0x180e4291c  mov     [rbp+60h+ppURI], 0
0x180e42924  jmp     short loc_180E428C3
0x180e42926  mov     rdx, [rbp+60h+ppURI]; struct IUri *
0x180e4292a  lea     rcx, [rbp+60h+var_C0]; this
0x180e4292e  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180e42931  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e42936  mov     r14d, 0Bh
0x180e4293c  test    eax, eax
0x180e4293e  jz      short loc_180E4297A
0x180e42940  mov     rdx, [rbp+60h+ppURI]; struct IUri *
0x180e42944  lea     rcx, [rbp+60h+var_C0]; this
0x180e42948  mov     r8d, r14d; enum __MIDL_IUri_0001
0x180e4294b  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e42950  test    eax, eax
0x180e42952  jz      short loc_180E4297A
0x180e42954  mov     edi, 80004005h
0x180e42959  lea     r15, ??_7CUString@@6B@; const CUString::`vftable'
0x180e42960  mov     r8d, r14d; enum __MIDL_IUri_0001
0x180e42963  xor     edx, edx; struct IUri *
0x180e42965  mov     [rbp+60h+var_88], r15
0x180e42969  lea     rcx, [rbp+60h+var_88]; this
0x180e4296d  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e42972  mov     r8d, r14d
0x180e42975  jmp     loc_180E428E4
0x180e4297a  mov     rdx, [rbp+60h+ppURI]; struct IUri *
0x180e4297e  lea     rcx, [rbp+60h+var_88]; this
0x180e42982  mov     ebx, 4
0x180e42987  mov     r8d, ebx; enum __MIDL_IUri_0001
0x180e4298a  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180e4298f  test    eax, eax
0x180e42991  jnz     short loc_180E429A8
0x180e42993  mov     rcx, [rbp+60h+psz1+8]; psz1
0x180e42997  lea     rdx, aHta_0; ".HTA"
0x180e4299e  call    cs:__imp_StrCmpIW
0x180e429a4  test    eax, eax
0x180e429a6  jz      short loc_180E42959
0x180e429a8  mov     rcx, [rsi+108h]; this
  ... truncated ...
```
