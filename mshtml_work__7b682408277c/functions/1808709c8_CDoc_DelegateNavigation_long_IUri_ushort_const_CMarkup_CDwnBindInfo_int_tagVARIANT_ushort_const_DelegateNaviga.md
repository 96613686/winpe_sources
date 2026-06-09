# CDoc::DelegateNavigation(long,IUri *,ushort const *,CMarkup *,CDwnBindInfo *,int *,tagVARIANT *,ushort const *,DelegateNavigationFlags)

- ea: `0x1808709c8`
- end: `0x1808716ea`
- name: `?DelegateNavigation@CDoc@@QEAAJJPEAUIUri@@PEBGPEAVCMarkup@@PEAVCDwnBindInfo@@PEAHPEAUtagVARIANT@@1W4DelegateNavigationFlags@@@Z`
- size: `3362`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1803dd3b0`
- `0x1808d0060`

## callees

- `0x1800151f0`
- `0x18005d080`
- `0x18005e648`
- `0x18005e684`
- `0x1800ea428`
- `0x1801296e4`
- `0x180133b3c`
- `0x180139080`
- `0x1801dc4a4`
- `0x180215264`
- `0x180217070`
- `0x1803c1b74`
- `0x1803c2b10`
- `0x1803e41a0`
- `0x1803e41f0`
- `0x1803e434c`
- `0x1805f76bc`
- `0x1805f7f7c`
- `0x18063375c`
- `0x18071f204`
- `0x1807b7a7c`
- `0x1807db3f4`
- `0x18084ed20`
- `0x180851414`
- `0x18086f4d4`
- `0x18086f92c`
- `0x1808709c8`
- `0x1808716f0`
- `0x180871ad4`
- `0x180878a6c`
- `0x1808d44bc`
- `0x180b5513c`
- `0x180b57d60`
- `0x181093184`
- `0x181104010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18087109a`
- `msvcrt!memcpy_s` at `0x1808710e9`
- `msvcrt!memcpy_s` at `0x18087109a`
- `msvcrt!memcpy_s` at `0x1808710e9`
- `iertutil!CreateIUriBuilder` at `0x180871364`
- `iertutil!CreateIUriBuilder` at `0x180871364`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180871521`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180871521`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180870ce7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180870ce7`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180870adf`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180870adf`
- `urlmon!CreateAsyncBindCtxEx` at `0x18087148b`
- `urlmon!CreateAsyncBindCtxEx` at `0x18087148b`
- `OLEAUT32!__imp_SysAllocString` at `0x180870fa7`
- `OLEAUT32!__imp_SysAllocString` at `0x180870fa7`
- `OLEAUT32!__imp_VariantClear` at `0x180870da4`
- `OLEAUT32!__imp_VariantClear` at `0x180870db4`
- `OLEAUT32!__imp_VariantClear` at `0x180870dc4`
- `OLEAUT32!__imp_VariantClear` at `0x180870dd4`
- `OLEAUT32!__imp_VariantClear` at `0x180870da4`
- `OLEAUT32!__imp_VariantClear` at `0x180870db4`
- `OLEAUT32!__imp_VariantClear` at `0x180870dc4`
- `OLEAUT32!__imp_VariantClear` at `0x180870dd4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180870d23`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180870d23`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1808710c3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1808710c3`

## pseudocode

```c
__int64 CDoc::DelegateNavigation(__int64 a1, int a2, ...)
{
  CMarkup *v2; // rsi
  unsigned int v3; // ebx
  int v5; // r15d
  struct COmWindowProxy *v6; // r14
  struct CDwnPostStm *v7; // r12
  int v8; // edi
  HRESULT IsFeatureEnabled; // eax
  __int64 v10; // r8
  HRESULT v11; // r15d
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // ecx
  struct CDwnDoc *DwnDoc; // r14
  __int64 v18; // r8
  struct tagVARIANT *v19; // r11
  __int64 v20; // rax
  struct IUnknown *v21; // r10
  const WCHAR *pwzURI; // r15
  VARIANTARG *v23; // r12
  __int64 v24; // rcx
  BOOL v25; // r8d
  struct COmWindowProxy *v26; // rbx
  unsigned __int8 *v27; // r14
  void *v28; // r8
  __int64 v30; // rcx
  __int64 v31; // rax
  struct CDwnPost *v33; // r14
  const OLECHAR *DwnHeader; // rax
  __int64 v35; // r8
  void *v36; // rax
  const void *v37; // r14
  __int64 v38; // r8
  unsigned __int8 *v39; // rax
  SAFEARRAY *Vector; // rax
  char v41; // r14
  CWindow *v42; // rdx
  int v43; // eax
  const unsigned __int16 *v44; // rbx
  int v45; // r11d
  int IsPrimaryMarkup; // eax
  int v47; // edx
  int v48; // edx
  unsigned __int16 *v49; // r10
  unsigned __int16 *bstrVal; // rdx
  CWebOCEvents *llVal; // rcx
  struct IUri *v52; // r8
  unsigned __int16 *v53; // rcx
  unsigned int v54; // ebx
  struct IUri *v55; // rdx
  int v56; // eax
  unsigned __int16 *v57; // [rsp+78h] [rbp-A0h]
  unsigned __int8 *v58; // [rsp+A0h] [rbp-78h]
  struct CDwnPostStm *v59; // [rsp+A8h] [rbp-70h] BYREF
  ULONG SourceSize; // [rsp+B0h] [rbp-68h] BYREF
  unsigned int SourceSize_4; // [rsp+B4h] [rbp-64h] BYREF
  unsigned int v62; // [rsp+B8h] [rbp-60h] BYREF
  struct COmWindowProxy *v63; // [rsp+C0h] [rbp-58h]
  int v64; // [rsp+C8h] [rbp-50h]
  LPBC ppBC; // [rsp+D0h] [rbp-48h] BYREF
  IUriBuilder *ppIUriBuilder; // [rsp+D8h] [rbp-40h] BYREF
  struct IUri *DwnPost; // [rsp+E0h] [rbp-38h] BYREF
  VARIANTARG v68; // [rsp+E8h] [rbp-30h] BYREF
  int v69; // [rsp+100h] [rbp-18h]
  int v70; // [rsp+104h] [rbp-14h] BYREF
  const unsigned __int16 *v71; // [rsp+108h] [rbp-10h] BYREF
  struct tagVARIANT *p_pvarg; // [rsp+110h] [rbp-8h]
  int v73; // [rsp+118h] [rbp+0h] BYREF
  unsigned int v74; // [rsp+11Ch] [rbp+4h] BYREF
  LPVOID pv; // [rsp+120h] [rbp+8h] BYREF
  SAFEARRAY *psa; // [rsp+128h] [rbp+10h]
  void *Source; // [rsp+130h] [rbp+18h]
  VARIANTARG v78; // [rsp+138h] [rbp+20h] BYREF
  VARIANTARG pvarg; // [rsp+150h] [rbp+38h] BYREF
  VARIANTARG v80; // [rsp+168h] [rbp+50h] BYREF
  _QWORD v81[13]; // [rsp+180h] [rbp+68h] BYREF
  int v82; // [rsp+200h] [rbp+E8h] BYREF
  IUri *pIUri; // [rsp+208h] [rbp+F0h] BYREF
  va_list pIUria; // [rsp+208h] [rbp+F0h]
  unsigned __int16 *UrlLocation; // [rsp+210h] [rbp+F8h]
  CMarkup *v86; // [rsp+218h] [rbp+100h] BYREF
  va_list va1; // [rsp+218h] [rbp+100h]
  struct CDwnBindInfo *v88; // [rsp+220h] [rbp+108h]
  int *v89; // [rsp+228h] [rbp+110h]
  struct tagVARIANT *v90; // [rsp+230h] [rbp+118h]
  const WCHAR *v91; // [rsp+238h] [rbp+120h]
  __int64 v92; // [rsp+240h] [rbp+128h]
  va_list va2; // [rsp+248h] [rbp+130h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(pIUria, a2);
  pIUri = va_arg(va1, IUri *);
  UrlLocation = va_arg(va1, unsigned __int16 *);
  va_copy(va2, va1);
  v86 = va_arg(va2, CMarkup *);
  v88 = va_arg(va2, struct CDwnBindInfo *);
  v89 = va_arg(va2, int *);
  v90 = va_arg(va2, struct tagVARIANT *);
  v91 = va_arg(va2, const WCHAR *);
  v92 = va_arg(va2, _QWORD);
  v82 = a2;
  v2 = v86;
  v3 = 0;
  v62 = 0;
  pv = 0;
  psa = 0;
  memset(&v68, 0, sizeof(v68));
  v68.vt = 3;
  v5 = 0;
  v70 = 0;
  memset(&v78, 0, sizeof(v78));
  v78.vt = 13;
  memset(&v80, 0, sizeof(v80));
  v80.vt = 8;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0x2000;
  if ( v86 )
    v6 = (struct COmWindowProxy *)*((_QWORD *)v86 + 44);
  else
    v6 = 0;
  v63 = v6;
  v59 = 0;
  Source = 0;
  SourceSize_4 = 0;
  v7 = 0;
  v74 = 0;
  ppBC = 0;
  v58 = 0;
  CUString::CUString((CUString *)v81, pIUri, Uri_PROPERTY_ABSOLUTE_URI, (int *)&v62);
  v8 = v62;
  if ( (v62 & 0x80000000) != 0 )
  {
    v26 = v63;
    v27 = 0;
    goto LABEL_55;
  }
  v64 = 0;
  if ( pIUri )
    ((void (__fastcall *)(IUri *))pIUri->lpVtbl->AddRef)(pIUri);
  else
    CMarkup::GetUri(v2, (struct IUri **)pIUria);
  IsFeatureEnabled = CoInternetIsFeatureEnabled(FEATURE_RESTRICT_FILEDOWNLOAD, 2u);
  v10 = 0;
  v11 = IsFeatureEnabled;
  LOBYTE(v7) = IsFeatureEnabled == 1;
  if ( v6 && (*(_BYTE *)(*((_QWORD *)v6 + 15) + 224LL) & 0x40) != 0 )
    v3 = 256;
  if ( v2 )
  {
    v12 = *((_QWORD *)v2 + 15);
    if ( !v12 )
      goto LABEL_21;
    v13 = *(_QWORD *)(v12 + 96);
    v14 = *(_QWORD *)(v13 + 280);
    if ( v14 )
    {
      v15 = *(_QWORD *)(v14 + 40);
      if ( !v15 )
      {
        v64 = 0;
        goto LABEL_19;
      }
      v16 = *(unsigned __int8 *)(v15 + 808);
    }
    else
    {
      v16 = *(_DWORD *)(v13 + 500);
    }
    v64 = v16;
LABEL_19:
    if ( *(_BYTE *)(v13 + 504) )
      v68.lVal |= 0x4000000u;
LABEL_21:
    v69 = CMarkup::TerminateLookForBookmarkTask(v2);
    DwnDoc = CMarkup::GetDwnDoc(v2);
    DwnPost = (struct IUri *)CMarkup::GetDwnPost(v2);
    v19 = 0;
    LOBYTE(v86) = *((_BYTE *)v2 + 98);
    if ( DwnDoc )
    {
      v20 = *((_QWORD *)DwnDoc + 13);
      if ( v20 )
      {
        if ( *(_QWORD *)(v20 + 64)
          && (*((_DWORD *)v2 + 188) & 0x100000) != 0
          && (unsigned int)CMarkup::IsPrimaryMarkup(v2) )
        {
          CTExec(v21, &CGID_ShellDocView, 0x8Au, 0, v19, v19);
          v19 = 0;
        }
      }
    }
    if ( v11 == 1 )
    {
      pwzURI = v91;
      goto LABEL_71;
    }
    SourceSize_4 = *((_DWORD *)v2 + 29);
    if ( DwnDoc )
    {
      pwzURI = (const WCHAR *)*((_QWORD *)DwnDoc + 100);
      if ( pwzURI && *pwzURI != (_WORD)v19 && !(unsigned int)ZoneCheckAutoDownloadUI(*((_QWORD *)DwnDoc + 100), v3, v18) )
      {
        SourceSize_4 = 0;
        LODWORD(v7) = 1;
LABEL_36:
        if ( (*((_BYTE *)v2 + 97) & 2) == 0 )
        {
LABEL_38:
          if ( (v68.bVal & 1) != 0 && !(_DWORD)v7 )
          {
            v23 = 0;
            if ( (v68.iVal & 0x200) != 0
              || *((_DWORD *)v2 + 29)
              && ((v24 = *(_QWORD *)(a1 + 5008)) == 0
               || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24)) )
            {
              v25 = CMarkup::IsPendingRoot(v2) && (!v63 || v63 != *(struct COmWindowProxy **)(a1 + 824));
              CDoc::OnPageActionBlocked((CDoc *)a1, 1u, v25, 0);
              v8 = -2147024891;
              goto LABEL_51;
            }
            SourceSize_4 = 0;
            goto LABEL_72;
          }
LABEL_71:
          v23 = 0;
LABEL_72:
          LODWORD(ppIUriBuilder) = ((unsigned __int8)v86 >> 6) & 1;
          goto LABEL_84;
        }
LABEL_37:
        v68.lVal |= 0x200u;
        goto LABEL_38;
      }
    }
    else
    {
      pwzURI = &v19->vt;
    }
    if ( (*((_BYTE *)v2 + 97) & 0x10) == 0 && (*((_DWORD *)v2 + 34) & 0x800000) != 0 )
      goto LABEL_37;
    goto LABEL_36;
  }
  v23 = 0;
  LODWORD(ppIUriBuilder) = 0;
  v69 = 0;
  if ( v88 )
  {
    DwnDoc = (struct CDwnDoc *)*((_QWORD *)v88 + 10);
    DwnPost = (struct IUri *)*((_QWORD *)v88 + 11);
  }
  else
  {
    DwnDoc = 0;
    DwnPost = 0;
  }
  pwzURI = v91;
  if ( IsFeatureEnabled != 1 && (!v91 || !*v91 || (unsigned int)ZoneCheckAutoDownloadUI(v91, v3, 0)) )
  {
    if ( (*(_BYTE *)(a1 + 4872) & 0x20) == 0 )
      v68.lVal |= 0x200u;
    v30 = *(_QWORD *)(a1 + 5008);
    if ( v30 )
      (*(void (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v30 + 40LL))(v30, &SourceSize_4, v10);
  }
LABEL_84:
  if ( DwnDoc && (*((_DWORD *)DwnDoc + 35) & 0x400) != 0 )
    v68.lVal |= 0x40u;
  v26 = v63;
  if ( v63 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)v63 + 15) + 224LL) & 0x40) != 0 )
    {
      v68.lVal |= 0x80u;
      if ( *((_BYTE *)CMarkup::GetDwnDoc(v2) + 731) )
      {
        v8 = -2147024891;
        goto LABEL_52;
      }
    }
  }
  p_pvarg = 0;
  v62 = 0;
  if ( v88 )
  {
    v31 = *((_QWORD *)v88 + 10);
    if ( v31 )
    {
      if ( !((*((_BYTE *)v88 + 180) & 1) != 0 ? (*(_DWORD *)(v31 + 156) & 8) == 0 : (*(_BYTE *)(v31 + 144) & 8) == 0) )
        v68.lVal |= 0x8000u;
    }
  }
  if ( (v92 & 2) != 0 )
    v68.lVal |= 0x400000u;
  if ( (*(_DWORD *)(a1 + 4864) & 0x2000) != 0 )
    v68.lVal |= 0x2000000u;
  v33 = (struct CDwnPost *)DwnPost;
  if ( !DwnPost )
    goto LABEL_121;
  if ( v2 )
  {
    DwnHeader = CMarkup::GetDwnHeader(v2);
LABEL_107:
    v80.llVal = (LONGLONG)SysAllocString(DwnHeader);
    if ( !v80.llVal )
    {
LABEL_108:
      v8 = -2147024882;
      goto LABEL_52;
    }
    v8 = CDwnPostStm::Create(v33, &v59);
    if ( v8 )
      goto LABEL_52;
    SourceSize = 0;
    v7 = v59;
    v8 = (*(__int64 (__fastcall **)(struct CDwnPostStm *, ULONG *))(*(_QWORD *)v59 + 16LL))(v59, &SourceSize);
    if ( v8 )
    {
      v5 = 0;
      v27 = 0;
      goto LABEL_55;
    }
    v23 = &v80;
    if ( SourceSize )
    {
      v36 = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, SourceSize, v35);
      Source = v36;
      v37 = v36;
      if ( !v36 )
      {
        v8 = -2147024882;
        v27 = 0;
        goto LABEL_53;
      }
      v73 = 0;
      v8 = (*(__int64 (__fastcall **)(char *, void *, _QWORD, int *))(*((_QWORD *)v59 + 3) + 24LL))(
             (char *)v59 + 24,
             v36,
             SourceSize,
             &v73);
      if ( v8 )
      {
LABEL_52:
        v27 = v58;
LABEL_53:
        v5 = 0;
LABEL_54:
        v7 = v59;
        goto LABEL_55;
      }
      if ( *(char *)(a1 + 4868) >= 0 )
      {
        Vector = SafeArrayCreateVector(0x11u, 0, SourceSize);
        psa = Vector;
        if ( !Vector )
          goto LABEL_108;
        memcpy_s(Vector->pvData, SourceSize, v37, SourceSize);
        pvarg.llVal = (LONGLONG)psa;
        p_pvarg = &pvarg;
      }
      else
      {
        v39 = (unsigned __int8 *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, SourceSize, v38);
        v58 = v39;
        v27 = v39;
        if ( !v39 )
        {
          v8 = -2147024882;
          goto LABEL_53;
        }
        memcpy_s(v39, SourceSize, Source, SourceSize);
        v62 = SourceSize;
      }
    }
LABEL_121:
    if ( !v2
      || (*((_DWORD *)v2 + 189) & 0x100) != 0
      || !v26
      || v26 == *(struct COmWindowProxy **)(a1 + 824)
      || v64 && *(_QWORD *)(a1 + 5144) )
    {
      v41 = 0;
    }
    else
    {
      v41 = 1;
      if ( *(char *)(a1 + 4868) >= 0 )
      {
        v42 = (CWindow *)*((_QWORD *)v26 + 15);
        if ( !*((_QWORD *)v42 + 17) && ((*((_DWORD *)CMarkup::Root(v2) + 15) & 0x200) == 0 || v82 != -2146697192) )
          goto LABEL_52;
        CWindow::ReleaseViewLinkedWebOC(v42);
        v78.vt = 13;
        CMarkup::GetUri(v2, (struct IUri **)&v78.llVal);
        if ( !v78.llVal )
        {
          v8 = -2147467262;
          goto LABEL_52;
        }
        v43 = CMarkup::ViewLinkWebOC(v2, &v78, &v68, 0, p_pvarg, v23, SourceSize_4);
        v7 = v59;
        v8 = v43;
        v27 = v58;
        if ( !v43 )
        {
          v5 = 1;
          goto LABEL_55;
        }
        goto LABEL_202;
      }
    }
    if ( !*(_QWORD *)(a1 + 5144) )
      goto LABEL_52;
    v44 = 0;
    v71 = 0;
    if ( (v92 & 1) != 0 )
      CTExec(*(struct IUnknown **)(a1 + 64), &CGID_ShellDocView, 0x3Eu, 0, 0, 0);
    CDoc::SetHostNavigation((CDoc *)a1, 1);
    v45 = 0;
    if ( v64 )
    {
      if ( !v2 || (IsPrimaryMarkup = CMarkup::IsPrimaryMarkup(v2), v47 = v45 + 1, IsPrimaryMarkup) )
        v47 = v45;
      CDoc::SetHostCDA((CDoc *)a1, v47);
    }
    if ( v63 )
      ppBC = *(LPBC *)(*((_QWORD *)v63 + 15) + 208LL);
    if ( ppBC )
    {
      ((void (__fastcall *)(LPBC))ppBC->lpVtbl->AddRef)(ppBC);
      v8 = 0;
      if ( *(char *)(a1 + 4868) < 0 )
      {
        GetBindContextParam(ppBC, (struct CStr *)&v71, L"WebPlatformDelegatedMime");
        v44 = v71;
      }
    }
    else
    {
      if ( __PAIR64__((unsigned int)ppIUriBuilder, 0) != SourceSize_4 )
        v8 = CreateAsyncBindCtxEx(0, 0, 0, 0, &ppBC, 0);
      if ( v8 )
      {
LABEL_174:
        CStr::_Free((CStr *)&v71);
LABEL_51:
        v26 = v63;
        goto LABEL_52;
      }
    }
    v48 = SourceSize_4;
    if ( !SourceSize_4 || (v8 = CMarkup::AddUserActionLabel(ppBC, SourceSize_4)) == 0 )
    {
      DwnPost = 0;
      if ( (_DWORD)ppIUriBuilder )
      {
        v8 = CMarkup::AddFTPAuthDelegation(ppBC, &v74);
        LODWORD(v86) = 0;
        if ( ((int (__fastcall *)(IUri *, __int64, CMarkup **))pIUri->lpVtbl->HasProperty)(pIUri, 13, (CMarkup **)va1) >= 0 )
        {
          if ( (_DWORD)v86 )
          {
            ppIUriBuilder = 0;
            v8 = CreateIUriBuilder(pIUri, 0, 0, &ppIUriBuilder);
            if ( v8 >= 0 )
            {
              v8 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD))ppIUriBuilder->lpVtbl->SetUserName)(ppIUriBuilder, 0);
              if ( v8 >= 0 )
              {
                v8 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD))ppIUriBuilder->lpVtbl->SetPassword)(
                       ppIUriBuilder,
                       0);
                if ( v8 >= 0 )
                  v8 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, struct IUri **))ppIUriBuilder->lpVtbl->CreateUriSimple)(
                         ppIUriBuilder,
                         0,
                         0,
                         &DwnPost);
              }
              ((void (__fastcall *)(IUriBuilder *))ppIUriBuilder->lpVtbl->Release)(ppIUriBuilder);
            }
          }
        }
      }
      if ( v69 )
        GWKillMethodCall(v2, CMarkup::SetInteractiveInternal, 0);
      if ( (*(_BYTE *)(a1 + 6428) & 1) != 0 || v2 && (*((_DWORD *)v2 + 189) & 0x100) != 0 )
      {
        v27 = v58;
        if ( (unsigned int)ShouldShellExecURL(pIUri, v48) )
        {
          v26 = v63;
          v5 = 0;
        }
        else
        {
          v57 = (unsigned __int16 *)v44;
          v26 = v63;
          v56 = CDoc::DelegateSandboxNavigation(
                  (CDoc *)a1,
                  v63,
                  v2,
                  pIUri,
                  &v68,
                  v90,
                  p_pvarg,
                  v23,
                  ppBC,
                  UrlLocation,
                  pwzURI,
                  v58,
                  v62,
                  v88,
                  v57,
                  &v82,
                  &v70);
          v5 = v70;
          v8 = v56;
        }
      }
      else
      {
        if ( *(char *)(a1 + 4868) >= 0 )
        {
          if ( (unsigned __int8)IEConfiguration_GetBool(268435481) && v41 && ppBC )
            DisableBindToObjectForCtx();
          v53 = UrlLocation;
          v54 = (*(_DWORD *)(a1 + 4864) >> 13) & 1;
          if ( !UrlLocation )
          {
            UrlLocation = (unsigned __int16 *)CMarkup::GetUrlLocation(v2);
            v53 = UrlLocation;
          }
          v55 = pIUri;
          if ( DwnPost )
            v55 = DwnPost;
          v8 = NavigateWebOCWithBindCtx(
                 *(struct IWebBrowser2 **)(a1 + 5144),
                 v55,
                 &v68,
                 v90,
                 p_pvarg,
                 v23,
                 ppBC,
                 v53,
                 pwzURI,
                 &v82,
                 v54);
        }
        else
        {
          if ( v88 )
            v44 = (const unsigned __int16 *)*((_QWORD *)v88 + 19);
          v49 = UrlLocation;
          if ( !UrlLocation )
            v49 = (unsigned __int16 *)CMarkup::GetUrlLocation(v2);
          if ( v23 )
            bstrVal = v23->bstrVal;
          else
            bstrVal = 0;
          if ( v90 )
            llVal = (CWebOCEvents *)v90->llVal;
          else
            llVal = 0;
          v52 = pIUri;
          if ( DwnPost )
            v52 = DwnPost;
          CWebOCEvents::DelegateNavigate(
            llVal,
            v63,
            v52,
            v68.cyVal.Lo,
            (unsigned __int16 *)llVal,
            v58,
            v62,
            bstrVal,
            ppBC,
            v49,
            pwzURI,
            v44);
        }
        v26 = v63;
        v5 = 1;
        v27 = v58;
        if ( v2 )
          *((_BYTE *)v2 + 103) |= 0x40u;
      }
      if ( DwnPost )
        ((void (__fastcall *)(struct IUri *))DwnPost->lpVtbl->Release)(DwnPost);
      CStr::_Free((CStr *)&v71);
      goto LABEL_54;
    }
    goto LABEL_174;
  }
  LOWORD(v86) = 0;
  v8 = (*(__int64 (__fastcall **)(char *, _QWORD, CMarkup **, _QWORD, LPVOID *))(*((_QWORD *)v88 + 6) + 24LL))(
         (char *)v88 + 48,
         v81[4],
         (CMarkup **)va1,
         0,
         &pv);
  if ( !v8 )
  {
    DwnHeader = (const OLECHAR *)pv;
    goto LABEL_107;
  }
  v7 = v59;
  v27 = 0;
LABEL_202:
  v5 = 0;
LABEL_55:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v89 )
    *v89 = v5;
  if ( v26 )
    TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>((void *)(*((_QWORD *)v26 + 15) + 208LL));
  if ( psa )
    SafeArrayDestroy(psa);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v7 + 3) + 16LL))((__int64)v7 + 24);
  ReleaseInterface((struct IUnknown *)ppBC);
  ReleaseInterface((struct IUnknown *)pIUri);
  if ( Source )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, Source, v28);
  if ( v27 )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v27, v28);
  v81[0] = &CUString::`vftable';
  CUString::Set((CUString *)v81, 0, Uri_PROPERTY_RAW_URI);
  VariantClear(&pvarg);
  VariantClear(&v80);
  VariantClear(&v78);
  VariantClear(&v68);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1808709c8  mov     rax, rsp
0x1808709cb  mov     [rax+8], rbx
0x1808709cf  mov     [rax+20h], r9
0x1808709d3  mov     [rax+18h], r8
0x1808709d7  mov     [rax+10h], edx
0x1808709da  push    rbp
0x1808709db  push    rsi
0x1808709dc  push    rdi
0x1808709dd  push    r12
0x1808709df  push    r13
0x1808709e1  push    r14
0x1808709e3  push    r15
0x1808709e5  lea     rbp, [rax-0D8h]
0x1808709ec  sub     rsp, 1B0h
0x1808709f3  mov     rsi, [rbp+0D0h+arg_20]
0x1808709fa  xor     ebx, ebx
0x1808709fc  mov     r13, rcx
0x1808709ff  mov     [rbp+0D0h+var_130], ebx
0x180870a02  xor     ecx, ecx
0x180870a04  mov     [rbp+0D0h+pv], rbx
0x180870a08  mov     qword ptr [rbp+0D0h+var_100+10h], rcx
0x180870a0c  xorps   xmm0, xmm0
0x180870a0f  lea     ecx, [rbx+3]
0x180870a12  mov     [rbp+0D0h+psa], rbx
0x180870a16  movups  xmmword ptr [rbp+0D0h+var_100], xmm0
0x180870a1a  mov     word ptr [rbp+0D0h+var_100], cx
0x180870a1e  mov     rax, r8
0x180870a21  xor     ecx, ecx
0x180870a23  mov     [rbp+0D0h+var_150], ebx
0x180870a26  mov     qword ptr [rbp+0D0h+var_B0+10h], rcx
0x180870a2a  mov     r15d, ebx
0x180870a2d  lea     ecx, [rbx+0Dh]
0x180870a30  mov     [rbp+0D0h+var_E4], ebx
0x180870a33  movups  xmmword ptr [rbp+0D0h+var_B0], xmm0
0x180870a37  mov     word ptr [rbp+0D0h+var_B0], cx
0x180870a3b  xor     ecx, ecx
0x180870a3d  mov     qword ptr [rbp+0D0h+var_80+10h], rcx
0x180870a41  lea     ecx, [rbx+8]
0x180870a44  movups  xmmword ptr [rbp+0D0h+var_80], xmm0
0x180870a48  mov     word ptr [rbp+0D0h+var_80], cx
0x180870a4c  xor     ecx, ecx
0x180870a4e  mov     qword ptr [rbp+0D0h+pvarg+10h], rcx
0x180870a52  mov     ecx, 2000h
0x180870a57  movups  xmmword ptr [rbp+0D0h+pvarg], xmm0
0x180870a5b  mov     word ptr [rbp+0D0h+pvarg], cx
0x180870a5f  test    rsi, rsi
0x180870a62  jz      short loc_180870A6D
0x180870a64  mov     r14, [rsi+160h]
0x180870a6b  jmp     short loc_180870A70
0x180870a6d  mov     r14, rbx
0x180870a70  lea     r9, [rbp+0D0h+var_130]; int *
0x180870a74  mov     [rbp+0D0h+var_128], r14
0x180870a78  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180870a7b  mov     [rbp+0D0h+var_140], rbx
0x180870a7f  mov     rdx, rax; struct IUri *
0x180870a82  mov     [rbp+0D0h+Source], rbx
0x180870a86  lea     rcx, [rbp+0D0h+var_68]; this
0x180870a8a  mov     dword ptr [rbp+0D0h+SourceSize+4], ebx
0x180870a8d  mov     r12, rbx
0x180870a90  mov     [rbp+0D0h+var_CC], ebx
0x180870a93  mov     [rbp+0D0h+var_118], rbx
0x180870a97  mov     [rbp+0D0h+var_148], rbx
0x180870a9b  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180870aa0  mov     edi, [rbp+0D0h+var_130]
0x180870aa3  test    edi, edi
0x180870aa5  js      loc_1808716C1
0x180870aab  mov     rcx, [rbp+0D0h+pIUri]
0x180870ab2  mov     [rbp+0D0h+var_120], ebx
0x180870ab5  test    rcx, rcx
0x180870ab8  jnz     short loc_180870ACB
0x180870aba  lea     rdx, [rbp+0D0h+pIUri]; struct IUri **
0x180870ac1  mov     rcx, rsi; struct CMarkup *
0x180870ac4  call    ?GetUri@CMarkup@@SAJQEBV1@PEAPEAUIUri@@@Z; CMarkup::GetUri(CMarkup const * const,IUri * *)
0x180870ac9  jmp     short loc_180870AD7
0x180870acb  mov     rax, [rcx]
0x180870ace  mov     rax, [rax+8]
0x180870ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180870ad7  mov     edx, 2; dwFlags
0x180870adc  lea     ecx, [rdx+0Ah]; FeatureEntry
0x180870adf  call    cs:__imp_CoInternetIsFeatureEnabled
0x180870ae6  nop     dword ptr [rax+rax+00h]
0x180870aeb  xor     r8d, r8d
0x180870aee  mov     r15d, eax
0x180870af1  cmp     eax, 1
0x180870af4  setz    r12b
0x180870af8  test    r14, r14
0x180870afb  jz      short loc_180870B10
0x180870afd  mov     rax, [r14+78h]
0x180870b01  test    byte ptr [rax+0E0h], 40h
0x180870b08  mov     eax, 100h
0x180870b0d  cmovnz  ebx, eax
0x180870b10  test    rsi, rsi
0x180870b13  jz      loc_180870E1A
0x180870b19  mov     rax, [rsi+78h]
0x180870b1d  test    rax, rax
0x180870b20  jz      short loc_180870B61
0x180870b22  mov     rax, [rax+60h]
0x180870b26  mov     rcx, [rax+118h]
0x180870b2d  test    rcx, rcx
0x180870b30  jz      short loc_180870B4A
0x180870b32  mov     rdx, [rcx+28h]
0x180870b36  test    rdx, rdx
0x180870b39  jz      short loc_180870B44
0x180870b3b  movzx   ecx, byte ptr [rdx+328h]
0x180870b42  jmp     short loc_180870B50
0x180870b44  mov     [rbp+0D0h+var_120], r8d
0x180870b48  jmp     short loc_180870B53
0x180870b4a  mov     ecx, [rax+1F4h]
0x180870b50  mov     [rbp+0D0h+var_120], ecx
0x180870b53  cmp     [rax+1F8h], r8b
0x180870b5a  jz      short loc_180870B61
0x180870b5c  bts     dword ptr [rbp+0D0h+var_100+8], 1Ah
0x180870b61  mov     rcx, rsi; this
0x180870b64  call    ?TerminateLookForBookmarkTask@CMarkup@@QEAAHXZ; CMarkup::TerminateLookForBookmarkTask(void)
0x180870b69  mov     rcx, rsi; this
0x180870b6c  mov     [rbp+0D0h+var_E8], eax
0x180870b6f  call    ?GetDwnDoc@CMarkup@@QEAAPEAVCDwnDoc@@XZ; CMarkup::GetDwnDoc(void)
0x180870b74  mov     rcx, rsi; this
0x180870b77  mov     r14, rax
0x180870b7a  call    ?GetDwnPost@CMarkup@@QEAAPEAVCDwnPost@@XZ; CMarkup::GetDwnPost(void)
0x180870b7f  mov     [rbp+0D0h+var_108], rax
0x180870b83  xor     r11d, r11d
0x180870b86  mov     al, [rsi+62h]
0x180870b89  mov     byte ptr [rbp+0D0h+arg_20], al
0x180870b8f  test    r14, r14
0x180870b92  jz      short loc_180870BE3
0x180870b94  mov     rax, [r14+68h]
0x180870b98  test    rax, rax
0x180870b9b  jz      short loc_180870BE3
0x180870b9d  mov     r10, [rax+40h]
0x180870ba1  test    r10, r10
0x180870ba4  jz      short loc_180870BE3
0x180870ba6  test    dword ptr [rsi+2F0h], 100000h
0x180870bb0  jz      short loc_180870BE3
0x180870bb2  mov     rcx, rsi; this
0x180870bb5  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x180870bba  test    eax, eax
0x180870bbc  jz      short loc_180870BE3
0x180870bbe  mov     qword ptr [rsp+1E0h+reserved], r11; struct tagVARIANT *
0x180870bc3  lea     rdx, CGID_ShellDocView; struct _GUID *
0x180870bca  xor     r9d, r9d; unsigned int
0x180870bcd  mov     [rsp+1E0h+ppBC], r11; struct tagVARIANT *
0x180870bd2  mov     r8d, 8Ah; unsigned int
0x180870bd8  mov     rcx, r10; struct IUnknown *
0x180870bdb  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x180870be0  xor     r11d, r11d
0x180870be3  cmp     r15d, 1
0x180870be7  jz      loc_180870DFE
0x180870bed  mov     eax, [rsi+74h]
0x180870bf0  mov     dword ptr [rbp+0D0h+SourceSize+4], eax
0x180870bf3  test    r14, r14
0x180870bf6  jz      short loc_180870C25
0x180870bf8  mov     r15, [r14+320h]
0x180870bff  test    r15, r15
0x180870c02  jz      short loc_180870C28
0x180870c04  cmp     [r15], r11w
0x180870c08  jz      short loc_180870C28
0x180870c0a  mov     edx, ebx
0x180870c0c  mov     rcx, r15
0x180870c0f  call    ZoneCheckAutoDownloadUI
0x180870c14  xor     r11d, r11d
0x180870c17  test    eax, eax
0x180870c19  jnz     short loc_180870C28
0x180870c1b  mov     dword ptr [rbp+0D0h+SourceSize+4], r11d
0x180870c1f  lea     r12d, [r11+1]
0x180870c23  jmp     short loc_180870C3B
0x180870c25  mov     r15, r11
0x180870c28  test    byte ptr [rsi+61h], 10h
0x180870c2c  jnz     short loc_180870C3B
0x180870c2e  mov     eax, [rsi+88h]
0x180870c34  bt      rax, 17h
0x180870c39  jb      short loc_180870C41
0x180870c3b  test    byte ptr [rsi+61h], 2
0x180870c3f  jz      short loc_180870C46
0x180870c41  bts     dword ptr [rbp+0D0h+var_100+8], 9
0x180870c46  test    byte ptr [rbp+0D0h+var_100+8], 1
0x180870c4a  jz      loc_180870E05
0x180870c50  test    r12d, r12d
0x180870c53  jnz     loc_180870E05
0x180870c59  xor     r12d, r12d
0x180870c5c  test    dword ptr [rbp+0D0h+var_100+8], 200h
0x180870c63  jnz     short loc_180870C91
0x180870c65  mov     edx, [rsi+74h]
0x180870c68  test    edx, edx
0x180870c6a  jz      short loc_180870C88
0x180870c6c  mov     rcx, [r13+1390h]
0x180870c73  test    rcx, rcx
0x180870c76  jz      short loc_180870C91
0x180870c78  mov     rax, [rcx]
0x180870c7b  mov     rax, [rax+18h]
0x180870c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180870c84  test    eax, eax
0x180870c86  jnz     short loc_180870C91
0x180870c88  mov     dword ptr [rbp+0D0h+SourceSize+4], r12d
0x180870c8c  jmp     loc_180870E08
0x180870c91  mov     rcx, rsi; this
0x180870c94  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x180870c99  test    al, al
0x180870c9b  jz      short loc_180870CB7
0x180870c9d  mov     rdx, [rbp+0D0h+var_128]
0x180870ca1  test    rdx, rdx
0x180870ca4  jz      short loc_180870CAF
0x180870ca6  cmp     rdx, [r13+338h]
0x180870cad  jz      short loc_180870CB7
0x180870caf  mov     r8d, 1
0x180870cb5  jmp     short loc_180870CBA
0x180870cb7  mov     r8d, r12d; int
0x180870cba  xor     r9d, r9d; struct BLOCKED_ACTION_DETAILS *
0x180870cbd  mov     rcx, r13; this
0x180870cc0  lea     edx, [r9+1]; unsigned int
0x180870cc4  call    ?OnPageActionBlocked@CDoc@@QEAAJKHPEAUBLOCKED_ACTION_DETAILS@@@Z; CDoc::OnPageActionBlocked(ulong,int,BLOCKED_ACTION_DETAILS *)
0x180870cc9  mov     edi, 80070005h
0x180870cce  mov     rbx, [rbp+0D0h+var_128]
0x180870cd2  mov     r14, [rbp+0D0h+var_148]
0x180870cd6  mov     r15d, [rbp+0D0h+var_150]
0x180870cda  mov     r12, [rbp+0D0h+var_140]
0x180870cde  mov     rcx, [rbp+0D0h+pv]; pv
0x180870ce2  test    rcx, rcx
0x180870ce5  jz      short loc_180870CF3
0x180870ce7  call    cs:__imp_CoTaskMemFree
0x180870cee  nop     dword ptr [rax+rax+00h]
0x180870cf3  mov     rax, [rbp+0D0h+arg_30]
0x180870cfa  test    rax, rax
0x180870cfd  jz      short loc_180870D02
0x180870cff  mov     [rax], r15d
0x180870d02  test    rbx, rbx
0x180870d05  jz      short loc_180870D17
0x180870d07  mov     rcx, [rbx+78h]
0x180870d0b  add     rcx, 0D0h; void *
0x180870d12  call    ??1?$TSmartPointer@VCTransitionClient@@@@QEAA@XZ; TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>(void)
0x180870d17  mov     rax, [rbp+0D0h+psa]
0x180870d1b  test    rax, rax
0x180870d1e  jz      short loc_180870D2F
0x180870d20  mov     rcx, rax; psa
0x180870d23  call    cs:__imp_SafeArrayDestroy
0x180870d2a  nop     dword ptr [rax+rax+00h]
0x180870d2f  test    r12, r12
0x180870d32  jz      short loc_180870D45
0x180870d34  lea     rcx, [r12+18h]
0x180870d39  mov     rax, [rcx]
0x180870d3c  mov     rax, [rax+10h]
0x180870d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180870d45  mov     rcx, [rbp+0D0h+var_118]; struct IUnknown *
0x180870d49  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180870d4e  mov     rcx, [rbp+0D0h+pIUri]; struct IUnknown *
0x180870d55  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180870d5a  mov     rax, [rbp+0D0h+Source]
0x180870d5e  test    rax, rax
0x180870d61  jz      short loc_180870D72
0x180870d63  mov     rcx, cs:g_hProcessHeap; this
0x180870d6a  mov     rdx, rax; void *
0x180870d6d  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180870d72  test    r14, r14
0x180870d75  jz      short loc_180870D86
0x180870d77  mov     rcx, cs:g_hProcessHeap; this
0x180870d7e  mov     rdx, r14; void *
0x180870d81  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x180870d86  xor     edx, edx; struct IUri *
0x180870d88  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180870d8f  lea     rcx, [rbp+0D0h+var_68]; this
0x180870d93  mov     [rbp+0D0h+var_68], rax
0x180870d97  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180870d9b  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180870da0  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x180870da4  call    cs:__imp_VariantClear
0x180870dab  nop     dword ptr [rax+rax+00h]
0x180870db0  lea     rcx, [rbp+0D0h+var_80]; pvarg
0x180870db4  call    cs:__imp_VariantClear
0x180870dbb  nop     dword ptr [rax+rax+00h]
0x180870dc0  lea     rcx, [rbp+0D0h+var_B0]; pvarg
0x180870dc4  call    cs:__imp_VariantClear
0x180870dcb  nop     dword ptr [rax+rax+00h]
0x180870dd0  lea     rcx, [rbp+0D0h+var_100]; pvarg
0x180870dd4  call    cs:__imp_VariantClear
0x180870ddb  nop     dword ptr [rax+rax+00h]
0x180870de0  mov     rbx, [rsp+1E0h+arg_0]
0x180870de8  mov     eax, edi
0x180870dea  add     rsp, 1B0h
0x180870df1  pop     r15
0x180870df3  pop     r14
0x180870df5  pop     r13
0x180870df7  pop     r12
0x180870df9  pop     rdi
0x180870dfa  pop     rsi
0x180870dfb  pop     rbp
0x180870dfc  retn
0x180870dfe  mov     r15, [rbp+0D0h+arg_40]
0x180870e05  xor     r12d, r12d
0x180870e08  movzx   eax, byte ptr [rbp+0D0h+arg_20]
0x180870e0f  shr     eax, 6
0x180870e12  and     eax, 1
0x180870e15  mov     dword ptr [rbp+0D0h+ppIUriBuilder], eax
0x180870e18  jmp     short loc_180870E97
0x180870e1a  mov     rcx, [rbp+0D0h+arg_28]
0x180870e21  xor     r12d, r12d
0x180870e24  mov     dword ptr [rbp+0D0h+ppIUriBuilder], r12d
0x180870e28  mov     [rbp+0D0h+var_E8], r12d
0x180870e2c  test    rcx, rcx
0x180870e2f  jz      short loc_180870E3F
0x180870e31  mov     rax, [rcx+58h]
  ... truncated ...
```
