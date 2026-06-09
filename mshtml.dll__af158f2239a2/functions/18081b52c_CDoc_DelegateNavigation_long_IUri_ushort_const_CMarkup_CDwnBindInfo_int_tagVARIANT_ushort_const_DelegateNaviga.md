# CDoc::DelegateNavigation(long,IUri *,ushort const *,CMarkup *,CDwnBindInfo *,int *,tagVARIANT *,ushort const *,DelegateNavigationFlags)

- ea: `0x18081b52c`
- end: `0x18081c1f9`
- name: `?DelegateNavigation@CDoc@@QEAAJJPEAUIUri@@PEBGPEAVCMarkup@@PEAVCDwnBindInfo@@PEAHPEAUtagVARIANT@@1W4DelegateNavigationFlags@@@Z`
- size: `3277`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d55a4`
- `0x18081b3d4`

## callees

- `0x1800ad370`
- `0x1800e2b60`
- `0x1800e4964`
- `0x18011f0ac`
- `0x180154a54`
- `0x1801bf528`
- `0x1801c0acc`
- `0x1801c0b08`
- `0x180222728`
- `0x180225058`
- `0x1802e8b74`
- `0x1802e97e0`
- `0x18043c328`
- `0x1804e223c`
- `0x1804e23dc`
- `0x1804f7e30`
- `0x1804f9d94`
- `0x1804fa5e0`
- `0x180635b34`
- `0x180717fc4`
- `0x1807abb64`
- `0x1807bfa9c`
- `0x1807cde14`
- `0x180811274`
- `0x18081b52c`
- `0x18084deec`
- `0x18086a158`
- `0x18086a5b4`
- `0x18086b600`
- `0x18086b9e4`
- `0x180872494`
- `0x1808c980c`
- `0x180b3f72c`
- `0x181062c34`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18081bbcd`
- `msvcrt!memcpy_s` at `0x18081bc10`
- `msvcrt!memcpy_s` at `0x18081bbcd`
- `msvcrt!memcpy_s` at `0x18081bc10`
- `iertutil!CreateIUriBuilder` at `0x18081be85`
- `iertutil!CreateIUriBuilder` at `0x18081be85`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18081c036`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18081c036`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18081b845`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18081b845`
- `urlmon!CoInternetIsFeatureEnabled` at `0x18081b643`
- `urlmon!CoInternetIsFeatureEnabled` at `0x18081b643`
- `urlmon!CreateAsyncBindCtxEx` at `0x18081bfa6`
- `urlmon!CreateAsyncBindCtxEx` at `0x18081bfa6`
- `OLEAUT32!__imp_SysAllocString` at `0x18081bae0`
- `OLEAUT32!__imp_SysAllocString` at `0x18081bae0`
- `OLEAUT32!__imp_VariantClear` at `0x18081b8f6`
- `OLEAUT32!__imp_VariantClear` at `0x18081b900`
- `OLEAUT32!__imp_VariantClear` at `0x18081b90a`
- `OLEAUT32!__imp_VariantClear` at `0x18081b914`
- `OLEAUT32!__imp_VariantClear` at `0x18081b8f6`
- `OLEAUT32!__imp_VariantClear` at `0x18081b900`
- `OLEAUT32!__imp_VariantClear` at `0x18081b90a`
- `OLEAUT32!__imp_VariantClear` at `0x18081b914`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18081b87b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18081b87b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18081bbf0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18081bbf0`

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
  void *v35; // rax
  const void *v36; // r14
  unsigned __int8 *v37; // rax
  SAFEARRAY *Vector; // rax
  char v39; // r14
  CWindow *v40; // rdx
  int v41; // eax
  const unsigned __int16 *v42; // rbx
  int v43; // r11d
  int IsPrimaryMarkup; // eax
  int v45; // edx
  int v46; // edx
  unsigned __int16 *v47; // r10
  unsigned __int16 *bstrVal; // rdx
  CWebOCEvents *llVal; // rcx
  struct IUri *v50; // r8
  unsigned __int16 *v51; // rcx
  unsigned int v52; // ebx
  struct IUri *v53; // rdx
  int v54; // eax
  unsigned __int16 *v55; // [rsp+78h] [rbp-A0h]
  unsigned __int8 *v56; // [rsp+A0h] [rbp-78h]
  struct CDwnPostStm *v57; // [rsp+A8h] [rbp-70h] BYREF
  ULONG SourceSize; // [rsp+B0h] [rbp-68h] BYREF
  unsigned int SourceSize_4; // [rsp+B4h] [rbp-64h] BYREF
  unsigned int v60; // [rsp+B8h] [rbp-60h] BYREF
  struct COmWindowProxy *v61; // [rsp+C0h] [rbp-58h]
  int v62; // [rsp+C8h] [rbp-50h]
  LPBC ppBC; // [rsp+D0h] [rbp-48h] BYREF
  IUriBuilder *ppIUriBuilder; // [rsp+D8h] [rbp-40h] BYREF
  struct IUri *DwnPost; // [rsp+E0h] [rbp-38h] BYREF
  VARIANTARG v66; // [rsp+E8h] [rbp-30h] BYREF
  int v67; // [rsp+100h] [rbp-18h]
  int v68; // [rsp+104h] [rbp-14h] BYREF
  const unsigned __int16 *v69; // [rsp+108h] [rbp-10h] BYREF
  struct tagVARIANT *p_pvarg; // [rsp+110h] [rbp-8h]
  int v71; // [rsp+118h] [rbp+0h] BYREF
  unsigned int v72; // [rsp+11Ch] [rbp+4h] BYREF
  LPVOID pv; // [rsp+120h] [rbp+8h] BYREF
  SAFEARRAY *psa; // [rsp+128h] [rbp+10h]
  void *Source; // [rsp+130h] [rbp+18h]
  VARIANTARG v76; // [rsp+138h] [rbp+20h] BYREF
  VARIANTARG pvarg; // [rsp+150h] [rbp+38h] BYREF
  VARIANTARG v78; // [rsp+168h] [rbp+50h] BYREF
  _QWORD v79[13]; // [rsp+180h] [rbp+68h] BYREF
  int v80; // [rsp+200h] [rbp+E8h] BYREF
  IUri *pIUri; // [rsp+208h] [rbp+F0h] BYREF
  va_list pIUria; // [rsp+208h] [rbp+F0h]
  unsigned __int16 *UrlLocation; // [rsp+210h] [rbp+F8h]
  CMarkup *v84; // [rsp+218h] [rbp+100h] BYREF
  va_list va1; // [rsp+218h] [rbp+100h]
  struct CDwnBindInfo *v86; // [rsp+220h] [rbp+108h]
  int *v87; // [rsp+228h] [rbp+110h]
  struct tagVARIANT *v88; // [rsp+230h] [rbp+118h]
  const WCHAR *v89; // [rsp+238h] [rbp+120h]
  __int64 v90; // [rsp+240h] [rbp+128h]
  va_list va2; // [rsp+248h] [rbp+130h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(pIUria, a2);
  pIUri = va_arg(va1, IUri *);
  UrlLocation = va_arg(va1, unsigned __int16 *);
  va_copy(va2, va1);
  v84 = va_arg(va2, CMarkup *);
  v86 = va_arg(va2, struct CDwnBindInfo *);
  v87 = va_arg(va2, int *);
  v88 = va_arg(va2, struct tagVARIANT *);
  v89 = va_arg(va2, const WCHAR *);
  v90 = va_arg(va2, _QWORD);
  v80 = a2;
  v2 = v84;
  v3 = 0;
  v60 = 0;
  pv = 0;
  psa = 0;
  memset(&v66, 0, sizeof(v66));
  v66.vt = 3;
  v5 = 0;
  v68 = 0;
  memset(&v76, 0, sizeof(v76));
  v76.vt = 13;
  memset(&v78, 0, sizeof(v78));
  v78.vt = 8;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0x2000;
  if ( v84 )
    v6 = (struct COmWindowProxy *)*((_QWORD *)v84 + 44);
  else
    v6 = 0;
  v61 = v6;
  v57 = 0;
  Source = 0;
  SourceSize_4 = 0;
  v7 = 0;
  v72 = 0;
  ppBC = 0;
  v56 = 0;
  CUString::CUString((CUString *)v79, pIUri, Uri_PROPERTY_ABSOLUTE_URI, (int *)&v60);
  v8 = v60;
  if ( (v60 & 0x80000000) != 0 )
  {
    v26 = v61;
    v27 = 0;
    goto LABEL_55;
  }
  v62 = 0;
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
        v62 = 0;
        goto LABEL_19;
      }
      v16 = *(unsigned __int8 *)(v15 + 808);
    }
    else
    {
      v16 = *(_DWORD *)(v13 + 500);
    }
    v62 = v16;
LABEL_19:
    if ( *(_BYTE *)(v13 + 504) )
      v66.lVal |= 0x4000000u;
LABEL_21:
    v67 = CMarkup::TerminateLookForBookmarkTask(v2);
    DwnDoc = CMarkup::GetDwnDoc(v2);
    DwnPost = (struct IUri *)CMarkup::GetDwnPost(v2);
    v19 = 0;
    LOBYTE(v84) = *((_BYTE *)v2 + 98);
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
      pwzURI = v89;
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
          if ( (v66.bVal & 1) != 0 && !(_DWORD)v7 )
          {
            v23 = 0;
            if ( (v66.iVal & 0x200) != 0
              || *((_DWORD *)v2 + 29)
              && ((v24 = *(_QWORD *)(a1 + 5008)) == 0
               || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24)) )
            {
              v25 = CMarkup::IsPendingRoot(v2) && (!v61 || v61 != *(struct COmWindowProxy **)(a1 + 824));
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
          LODWORD(ppIUriBuilder) = ((unsigned __int8)v84 >> 6) & 1;
          goto LABEL_84;
        }
LABEL_37:
        v66.lVal |= 0x200u;
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
  v67 = 0;
  if ( v86 )
  {
    DwnDoc = (struct CDwnDoc *)*((_QWORD *)v86 + 10);
    DwnPost = (struct IUri *)*((_QWORD *)v86 + 11);
  }
  else
  {
    DwnDoc = 0;
    DwnPost = 0;
  }
  pwzURI = v89;
  if ( IsFeatureEnabled != 1 && (!v89 || !*v89 || (unsigned int)ZoneCheckAutoDownloadUI(v89, v3, 0)) )
  {
    if ( (*(_BYTE *)(a1 + 4872) & 0x20) == 0 )
      v66.lVal |= 0x200u;
    v30 = *(_QWORD *)(a1 + 5008);
    if ( v30 )
      (*(void (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v30 + 40LL))(v30, &SourceSize_4, v10);
  }
LABEL_84:
  if ( DwnDoc && (*((_DWORD *)DwnDoc + 35) & 0x400) != 0 )
    v66.lVal |= 0x40u;
  v26 = v61;
  if ( v61 )
  {
    if ( (*(_BYTE *)(*((_QWORD *)v61 + 15) + 224LL) & 0x40) != 0 )
    {
      v66.lVal |= 0x80u;
      if ( *((_BYTE *)CMarkup::GetDwnDoc(v2) + 731) )
      {
        v8 = -2147024891;
        goto LABEL_52;
      }
    }
  }
  p_pvarg = 0;
  v60 = 0;
  if ( v86 )
  {
    v31 = *((_QWORD *)v86 + 10);
    if ( v31 )
    {
      if ( !((*((_BYTE *)v86 + 180) & 1) != 0 ? (*(_DWORD *)(v31 + 156) & 8) == 0 : (*(_BYTE *)(v31 + 144) & 8) == 0) )
        v66.lVal |= 0x8000u;
    }
  }
  if ( (v90 & 2) != 0 )
    v66.lVal |= 0x400000u;
  if ( (*(_DWORD *)(a1 + 4864) & 0x2000) != 0 )
    v66.lVal |= 0x2000000u;
  v33 = (struct CDwnPost *)DwnPost;
  if ( !DwnPost )
    goto LABEL_121;
  if ( v2 )
  {
    DwnHeader = CMarkup::GetDwnHeader(v2);
LABEL_107:
    v78.llVal = (LONGLONG)SysAllocString(DwnHeader);
    if ( !v78.llVal )
    {
LABEL_108:
      v8 = -2147024882;
      goto LABEL_52;
    }
    v8 = CDwnPostStm::Create(v33, &v57);
    if ( v8 )
      goto LABEL_52;
    SourceSize = 0;
    v7 = v57;
    v8 = (*(__int64 (__fastcall **)(struct CDwnPostStm *, ULONG *))(*(_QWORD *)v57 + 16LL))(v57, &SourceSize);
    if ( v8 )
    {
      v5 = 0;
      v27 = 0;
      goto LABEL_55;
    }
    v23 = &v78;
    if ( SourceSize )
    {
      v35 = (void *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, SourceSize);
      Source = v35;
      v36 = v35;
      if ( !v35 )
      {
        v8 = -2147024882;
        v27 = 0;
        goto LABEL_53;
      }
      v71 = 0;
      v8 = (*(__int64 (__fastcall **)(char *, void *, _QWORD, int *))(*((_QWORD *)v57 + 3) + 24LL))(
             (char *)v57 + 24,
             v35,
             SourceSize,
             &v71);
      if ( v8 )
      {
LABEL_52:
        v27 = v56;
LABEL_53:
        v5 = 0;
LABEL_54:
        v7 = v57;
        goto LABEL_55;
      }
      if ( *(char *)(a1 + 4868) >= 0 )
      {
        Vector = SafeArrayCreateVector(0x11u, 0, SourceSize);
        psa = Vector;
        if ( !Vector )
          goto LABEL_108;
        memcpy_s(Vector->pvData, SourceSize, v36, SourceSize);
        pvarg.llVal = (LONGLONG)psa;
        p_pvarg = &pvarg;
      }
      else
      {
        v37 = (unsigned __int8 *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, SourceSize);
        v56 = v37;
        v27 = v37;
        if ( !v37 )
        {
          v8 = -2147024882;
          goto LABEL_53;
        }
        memcpy_s(v37, SourceSize, Source, SourceSize);
        v60 = SourceSize;
      }
    }
LABEL_121:
    if ( !v2
      || (*((_DWORD *)v2 + 189) & 0x100) != 0
      || !v26
      || v26 == *(struct COmWindowProxy **)(a1 + 824)
      || v62 && *(_QWORD *)(a1 + 5144) )
    {
      v39 = 0;
    }
    else
    {
      v39 = 1;
      if ( *(char *)(a1 + 4868) >= 0 )
      {
        v40 = (CWindow *)*((_QWORD *)v26 + 15);
        if ( !*((_QWORD *)v40 + 17) && ((*((_DWORD *)CMarkup::Root(v2) + 15) & 0x200) == 0 || v80 != -2146697192) )
          goto LABEL_52;
        CWindow::ReleaseViewLinkedWebOC(v40);
        v76.vt = 13;
        CMarkup::GetUri(v2, (struct IUri **)&v76.llVal);
        if ( !v76.llVal )
        {
          v8 = -2147467262;
          goto LABEL_52;
        }
        v41 = CMarkup::ViewLinkWebOC(v2, &v76, &v66, 0, p_pvarg, v23, SourceSize_4);
        v7 = v57;
        v8 = v41;
        v27 = v56;
        if ( !v41 )
        {
          v5 = 1;
          goto LABEL_55;
        }
        goto LABEL_202;
      }
    }
    if ( !*(_QWORD *)(a1 + 5144) )
      goto LABEL_52;
    v42 = 0;
    v69 = 0;
    if ( (v90 & 1) != 0 )
      CTExec(*(struct IUnknown **)(a1 + 64), &CGID_ShellDocView, 0x3Eu, 0, 0, 0);
    CDoc::SetHostNavigation((CDoc *)a1, 1);
    v43 = 0;
    if ( v62 )
    {
      if ( !v2 || (IsPrimaryMarkup = CMarkup::IsPrimaryMarkup(v2), v45 = v43 + 1, IsPrimaryMarkup) )
        v45 = v43;
      CDoc::SetHostCDA((CDoc *)a1, v45);
    }
    if ( v61 )
      ppBC = *(LPBC *)(*((_QWORD *)v61 + 15) + 208LL);
    if ( ppBC )
    {
      ((void (__fastcall *)(LPBC))ppBC->lpVtbl->AddRef)(ppBC);
      v8 = 0;
      if ( *(char *)(a1 + 4868) < 0 )
      {
        GetBindContextParam(ppBC, (struct CStr *)&v69, L"WebPlatformDelegatedMime");
        v42 = v69;
      }
    }
    else
    {
      if ( __PAIR64__((unsigned int)ppIUriBuilder, 0) != SourceSize_4 )
        v8 = CreateAsyncBindCtxEx(0, 0, 0, 0, &ppBC, 0);
      if ( v8 )
      {
LABEL_174:
        CStr::_Free((CStr *)&v69);
LABEL_51:
        v26 = v61;
        goto LABEL_52;
      }
    }
    v46 = SourceSize_4;
    if ( !SourceSize_4 || (v8 = CMarkup::AddUserActionLabel(ppBC, SourceSize_4)) == 0 )
    {
      DwnPost = 0;
      if ( (_DWORD)ppIUriBuilder )
      {
        v8 = CMarkup::AddFTPAuthDelegation(ppBC, &v72);
        LODWORD(v84) = 0;
        if ( ((int (__fastcall *)(IUri *, __int64, CMarkup **))pIUri->lpVtbl->HasProperty)(pIUri, 13, (CMarkup **)va1) >= 0 )
        {
          if ( (_DWORD)v84 )
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
      if ( v67 )
        GWKillMethodCall(v2, CMarkup::SetInteractiveInternal, 0);
      if ( (*(_BYTE *)(a1 + 6428) & 1) != 0 || v2 && (*((_DWORD *)v2 + 189) & 0x100) != 0 )
      {
        v27 = v56;
        if ( (unsigned int)ShouldShellExecURL(pIUri, v46) )
        {
          v26 = v61;
          v5 = 0;
        }
        else
        {
          v55 = (unsigned __int16 *)v42;
          v26 = v61;
          v54 = CDoc::DelegateSandboxNavigation(
                  (CDoc *)a1,
                  v61,
                  v2,
                  pIUri,
                  &v66,
                  v88,
                  p_pvarg,
                  v23,
                  ppBC,
                  UrlLocation,
                  pwzURI,
                  v56,
                  v60,
                  v86,
                  v55,
                  &v80,
                  &v68);
          v5 = v68;
          v8 = v54;
        }
      }
      else
      {
        if ( *(char *)(a1 + 4868) >= 0 )
        {
          if ( (unsigned __int8)IEConfiguration_GetBool(268435481) && v39 && ppBC )
            DisableBindToObjectForCtx();
          v51 = UrlLocation;
          v52 = (*(_DWORD *)(a1 + 4864) >> 13) & 1;
          if ( !UrlLocation )
          {
            UrlLocation = (unsigned __int16 *)CMarkup::GetUrlLocation(v2);
            v51 = UrlLocation;
          }
          v53 = pIUri;
          if ( DwnPost )
            v53 = DwnPost;
          v8 = NavigateWebOCWithBindCtx(
                 *(struct IWebBrowser2 **)(a1 + 5144),
                 v53,
                 &v66,
                 v88,
                 p_pvarg,
                 v23,
                 ppBC,
                 v51,
                 pwzURI,
                 &v80,
                 v52);
        }
        else
        {
          if ( v86 )
            v42 = (const unsigned __int16 *)*((_QWORD *)v86 + 19);
          v47 = UrlLocation;
          if ( !UrlLocation )
            v47 = (unsigned __int16 *)CMarkup::GetUrlLocation(v2);
          if ( v23 )
            bstrVal = v23->bstrVal;
          else
            bstrVal = 0;
          if ( v88 )
            llVal = (CWebOCEvents *)v88->llVal;
          else
            llVal = 0;
          v50 = pIUri;
          if ( DwnPost )
            v50 = DwnPost;
          CWebOCEvents::DelegateNavigate(
            llVal,
            v61,
            v50,
            v66.cyVal.Lo,
            (unsigned __int16 *)llVal,
            v56,
            v60,
            bstrVal,
            ppBC,
            v47,
            pwzURI,
            v42);
        }
        v26 = v61;
        v5 = 1;
        v27 = v56;
        if ( v2 )
          *((_BYTE *)v2 + 103) |= 0x40u;
      }
      if ( DwnPost )
        ((void (__fastcall *)(struct IUri *))DwnPost->lpVtbl->Release)(DwnPost);
      CStr::_Free((CStr *)&v69);
      goto LABEL_54;
    }
    goto LABEL_174;
  }
  LOWORD(v84) = 0;
  v8 = (*(__int64 (__fastcall **)(char *, _QWORD, CMarkup **, _QWORD, LPVOID *))(*((_QWORD *)v86 + 6) + 24LL))(
         (char *)v86 + 48,
         v79[4],
         (CMarkup **)va1,
         0,
         &pv);
  if ( !v8 )
  {
    DwnHeader = (const OLECHAR *)pv;
    goto LABEL_107;
  }
  v7 = v57;
  v27 = 0;
LABEL_202:
  v5 = 0;
LABEL_55:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v87 )
    *v87 = v5;
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
  v79[0] = &CUString::`vftable';
  CUString::Set((CUString *)v79, 0, Uri_PROPERTY_RAW_URI);
  VariantClear(&pvarg);
  VariantClear(&v78);
  VariantClear(&v76);
  VariantClear(&v66);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18081b52c  mov     rax, rsp
0x18081b52f  mov     [rax+8], rbx
0x18081b533  mov     [rax+20h], r9
0x18081b537  mov     [rax+18h], r8
0x18081b53b  mov     [rax+10h], edx
0x18081b53e  push    rbp
0x18081b53f  push    rsi
0x18081b540  push    rdi
0x18081b541  push    r12
0x18081b543  push    r13
0x18081b545  push    r14
0x18081b547  push    r15
0x18081b549  lea     rbp, [rax-0D8h]
0x18081b550  sub     rsp, 1B0h
0x18081b557  mov     rsi, [rbp+0D0h+arg_20]
0x18081b55e  xor     ebx, ebx
0x18081b560  mov     r13, rcx
0x18081b563  mov     [rbp+0D0h+var_130], ebx
0x18081b566  xor     ecx, ecx
0x18081b568  mov     [rbp+0D0h+pv], rbx
0x18081b56c  mov     qword ptr [rbp+0D0h+var_100+10h], rcx
0x18081b570  xorps   xmm0, xmm0
0x18081b573  lea     ecx, [rbx+3]
0x18081b576  mov     [rbp+0D0h+psa], rbx
0x18081b57a  movups  xmmword ptr [rbp+0D0h+var_100], xmm0
0x18081b57e  mov     word ptr [rbp+0D0h+var_100], cx
0x18081b582  mov     rax, r8
0x18081b585  xor     ecx, ecx
0x18081b587  mov     [rbp+0D0h+var_150], ebx
0x18081b58a  mov     qword ptr [rbp+0D0h+var_B0+10h], rcx
0x18081b58e  mov     r15d, ebx
0x18081b591  lea     ecx, [rbx+0Dh]
0x18081b594  mov     [rbp+0D0h+var_E4], ebx
0x18081b597  movups  xmmword ptr [rbp+0D0h+var_B0], xmm0
0x18081b59b  mov     word ptr [rbp+0D0h+var_B0], cx
0x18081b59f  xor     ecx, ecx
0x18081b5a1  mov     qword ptr [rbp+0D0h+var_80+10h], rcx
0x18081b5a5  lea     ecx, [rbx+8]
0x18081b5a8  movups  xmmword ptr [rbp+0D0h+var_80], xmm0
0x18081b5ac  mov     word ptr [rbp+0D0h+var_80], cx
0x18081b5b0  xor     ecx, ecx
0x18081b5b2  mov     qword ptr [rbp+0D0h+pvarg+10h], rcx
0x18081b5b6  mov     ecx, 2000h
0x18081b5bb  movups  xmmword ptr [rbp+0D0h+pvarg], xmm0
0x18081b5bf  mov     word ptr [rbp+0D0h+pvarg], cx
0x18081b5c3  test    rsi, rsi
0x18081b5c6  jz      short loc_18081B5D1
0x18081b5c8  mov     r14, [rsi+160h]
0x18081b5cf  jmp     short loc_18081B5D4
0x18081b5d1  mov     r14, rbx
0x18081b5d4  lea     r9, [rbp+0D0h+var_130]; int *
0x18081b5d8  mov     [rbp+0D0h+var_128], r14
0x18081b5dc  xor     r8d, r8d; enum __MIDL_IUri_0001
0x18081b5df  mov     [rbp+0D0h+var_140], rbx
0x18081b5e3  mov     rdx, rax; struct IUri *
0x18081b5e6  mov     [rbp+0D0h+Source], rbx
0x18081b5ea  lea     rcx, [rbp+0D0h+var_68]; this
0x18081b5ee  mov     dword ptr [rbp+0D0h+SourceSize+4], ebx
0x18081b5f1  mov     r12, rbx
0x18081b5f4  mov     [rbp+0D0h+var_CC], ebx
0x18081b5f7  mov     [rbp+0D0h+var_118], rbx
0x18081b5fb  mov     [rbp+0D0h+var_148], rbx
0x18081b5ff  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x18081b604  mov     edi, [rbp+0D0h+var_130]
0x18081b607  test    edi, edi
0x18081b609  js      loc_18081C1D0
0x18081b60f  mov     rcx, [rbp+0D0h+pIUri]
0x18081b616  mov     [rbp+0D0h+var_120], ebx
0x18081b619  test    rcx, rcx
0x18081b61c  jnz     short loc_18081B62F
0x18081b61e  lea     rdx, [rbp+0D0h+pIUri]; struct IUri **
0x18081b625  mov     rcx, rsi; struct CMarkup *
0x18081b628  call    ?GetUri@CMarkup@@SAJQEBV1@PEAPEAUIUri@@@Z; CMarkup::GetUri(CMarkup const * const,IUri * *)
0x18081b62d  jmp     short loc_18081B63B
0x18081b62f  mov     rax, [rcx]
0x18081b632  mov     rax, [rax+8]
0x18081b636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081b63b  mov     edx, 2; dwFlags
0x18081b640  lea     ecx, [rdx+0Ah]; FeatureEntry
0x18081b643  call    cs:__imp_CoInternetIsFeatureEnabled
0x18081b649  xor     r8d, r8d
0x18081b64c  mov     r15d, eax
0x18081b64f  cmp     eax, 1
0x18081b652  setz    r12b
0x18081b656  test    r14, r14
0x18081b659  jz      short loc_18081B66E
0x18081b65b  mov     rax, [r14+78h]
0x18081b65f  test    byte ptr [rax+0E0h], 40h
0x18081b666  mov     eax, 100h
0x18081b66b  cmovnz  ebx, eax
0x18081b66e  test    rsi, rsi
0x18081b671  jz      loc_18081B953
0x18081b677  mov     rax, [rsi+78h]
0x18081b67b  test    rax, rax
0x18081b67e  jz      short loc_18081B6BF
0x18081b680  mov     rax, [rax+60h]
0x18081b684  mov     rcx, [rax+118h]
0x18081b68b  test    rcx, rcx
0x18081b68e  jz      short loc_18081B6A8
0x18081b690  mov     rdx, [rcx+28h]
0x18081b694  test    rdx, rdx
0x18081b697  jz      short loc_18081B6A2
0x18081b699  movzx   ecx, byte ptr [rdx+328h]
0x18081b6a0  jmp     short loc_18081B6AE
0x18081b6a2  mov     [rbp+0D0h+var_120], r8d
0x18081b6a6  jmp     short loc_18081B6B1
0x18081b6a8  mov     ecx, [rax+1F4h]
0x18081b6ae  mov     [rbp+0D0h+var_120], ecx
0x18081b6b1  cmp     [rax+1F8h], r8b
0x18081b6b8  jz      short loc_18081B6BF
0x18081b6ba  bts     dword ptr [rbp+0D0h+var_100+8], 1Ah
0x18081b6bf  mov     rcx, rsi; this
0x18081b6c2  call    ?TerminateLookForBookmarkTask@CMarkup@@QEAAHXZ; CMarkup::TerminateLookForBookmarkTask(void)
0x18081b6c7  mov     rcx, rsi; this
0x18081b6ca  mov     [rbp+0D0h+var_E8], eax
0x18081b6cd  call    ?GetDwnDoc@CMarkup@@QEAAPEAVCDwnDoc@@XZ; CMarkup::GetDwnDoc(void)
0x18081b6d2  mov     rcx, rsi; this
0x18081b6d5  mov     r14, rax
0x18081b6d8  call    ?GetDwnPost@CMarkup@@QEAAPEAVCDwnPost@@XZ; CMarkup::GetDwnPost(void)
0x18081b6dd  mov     [rbp+0D0h+var_108], rax
0x18081b6e1  xor     r11d, r11d
0x18081b6e4  mov     al, [rsi+62h]
0x18081b6e7  mov     byte ptr [rbp+0D0h+arg_20], al
0x18081b6ed  test    r14, r14
0x18081b6f0  jz      short loc_18081B741
0x18081b6f2  mov     rax, [r14+68h]
0x18081b6f6  test    rax, rax
0x18081b6f9  jz      short loc_18081B741
0x18081b6fb  mov     r10, [rax+40h]
0x18081b6ff  test    r10, r10
0x18081b702  jz      short loc_18081B741
0x18081b704  test    dword ptr [rsi+2F0h], 100000h
0x18081b70e  jz      short loc_18081B741
0x18081b710  mov     rcx, rsi; this
0x18081b713  call    ?IsPrimaryMarkup@CMarkup@@QEBAHXZ; CMarkup::IsPrimaryMarkup(void)
0x18081b718  test    eax, eax
0x18081b71a  jz      short loc_18081B741
0x18081b71c  mov     qword ptr [rsp+1E0h+reserved], r11; struct tagVARIANT *
0x18081b721  lea     rdx, CGID_ShellDocView; struct _GUID *
0x18081b728  xor     r9d, r9d; unsigned int
0x18081b72b  mov     [rsp+1E0h+ppBC], r11; struct tagVARIANT *
0x18081b730  mov     r8d, 8Ah; unsigned int
0x18081b736  mov     rcx, r10; struct IUnknown *
0x18081b739  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x18081b73e  xor     r11d, r11d
0x18081b741  cmp     r15d, 1
0x18081b745  jz      loc_18081B937
0x18081b74b  mov     eax, [rsi+74h]
0x18081b74e  mov     dword ptr [rbp+0D0h+SourceSize+4], eax
0x18081b751  test    r14, r14
0x18081b754  jz      short loc_18081B783
0x18081b756  mov     r15, [r14+320h]
0x18081b75d  test    r15, r15
0x18081b760  jz      short loc_18081B786
0x18081b762  cmp     [r15], r11w
0x18081b766  jz      short loc_18081B786
0x18081b768  mov     edx, ebx
0x18081b76a  mov     rcx, r15
0x18081b76d  call    ZoneCheckAutoDownloadUI
0x18081b772  xor     r11d, r11d
0x18081b775  test    eax, eax
0x18081b777  jnz     short loc_18081B786
0x18081b779  mov     dword ptr [rbp+0D0h+SourceSize+4], r11d
0x18081b77d  lea     r12d, [r11+1]
0x18081b781  jmp     short loc_18081B799
0x18081b783  mov     r15, r11
0x18081b786  test    byte ptr [rsi+61h], 10h
0x18081b78a  jnz     short loc_18081B799
0x18081b78c  mov     eax, [rsi+88h]
0x18081b792  bt      rax, 17h
0x18081b797  jb      short loc_18081B79F
0x18081b799  test    byte ptr [rsi+61h], 2
0x18081b79d  jz      short loc_18081B7A4
0x18081b79f  bts     dword ptr [rbp+0D0h+var_100+8], 9
0x18081b7a4  test    byte ptr [rbp+0D0h+var_100+8], 1
0x18081b7a8  jz      loc_18081B93E
0x18081b7ae  test    r12d, r12d
0x18081b7b1  jnz     loc_18081B93E
0x18081b7b7  xor     r12d, r12d
0x18081b7ba  test    dword ptr [rbp+0D0h+var_100+8], 200h
0x18081b7c1  jnz     short loc_18081B7EF
0x18081b7c3  mov     edx, [rsi+74h]
0x18081b7c6  test    edx, edx
0x18081b7c8  jz      short loc_18081B7E6
0x18081b7ca  mov     rcx, [r13+1390h]
0x18081b7d1  test    rcx, rcx
0x18081b7d4  jz      short loc_18081B7EF
0x18081b7d6  mov     rax, [rcx]
0x18081b7d9  mov     rax, [rax+18h]
0x18081b7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081b7e2  test    eax, eax
0x18081b7e4  jnz     short loc_18081B7EF
0x18081b7e6  mov     dword ptr [rbp+0D0h+SourceSize+4], r12d
0x18081b7ea  jmp     loc_18081B941
0x18081b7ef  mov     rcx, rsi; this
0x18081b7f2  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x18081b7f7  test    al, al
0x18081b7f9  jz      short loc_18081B815
0x18081b7fb  mov     rdx, [rbp+0D0h+var_128]
0x18081b7ff  test    rdx, rdx
0x18081b802  jz      short loc_18081B80D
0x18081b804  cmp     rdx, [r13+338h]
0x18081b80b  jz      short loc_18081B815
0x18081b80d  mov     r8d, 1
0x18081b813  jmp     short loc_18081B818
0x18081b815  mov     r8d, r12d; int
0x18081b818  xor     r9d, r9d; struct BLOCKED_ACTION_DETAILS *
0x18081b81b  mov     rcx, r13; this
0x18081b81e  lea     edx, [r9+1]; unsigned int
0x18081b822  call    ?OnPageActionBlocked@CDoc@@QEAAJKHPEAUBLOCKED_ACTION_DETAILS@@@Z; CDoc::OnPageActionBlocked(ulong,int,BLOCKED_ACTION_DETAILS *)
0x18081b827  mov     edi, 80070005h
0x18081b82c  mov     rbx, [rbp+0D0h+var_128]
0x18081b830  mov     r14, [rbp+0D0h+var_148]
0x18081b834  mov     r15d, [rbp+0D0h+var_150]
0x18081b838  mov     r12, [rbp+0D0h+var_140]
0x18081b83c  mov     rcx, [rbp+0D0h+pv]; pv
0x18081b840  test    rcx, rcx
0x18081b843  jz      short loc_18081B84B
0x18081b845  call    cs:__imp_CoTaskMemFree
0x18081b84b  mov     rax, [rbp+0D0h+arg_30]
0x18081b852  test    rax, rax
0x18081b855  jz      short loc_18081B85A
0x18081b857  mov     [rax], r15d
0x18081b85a  test    rbx, rbx
0x18081b85d  jz      short loc_18081B86F
0x18081b85f  mov     rcx, [rbx+78h]
0x18081b863  add     rcx, 0D0h; void *
0x18081b86a  call    ??1?$TSmartPointer@VCTransitionClient@@@@QEAA@XZ; TSmartPointer<CTransitionClient>::~TSmartPointer<CTransitionClient>(void)
0x18081b86f  mov     rax, [rbp+0D0h+psa]
0x18081b873  test    rax, rax
0x18081b876  jz      short loc_18081B881
0x18081b878  mov     rcx, rax; psa
0x18081b87b  call    cs:__imp_SafeArrayDestroy
0x18081b881  test    r12, r12
0x18081b884  jz      short loc_18081B897
0x18081b886  lea     rcx, [r12+18h]
0x18081b88b  mov     rax, [rcx]
0x18081b88e  mov     rax, [rax+10h]
0x18081b892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18081b897  mov     rcx, [rbp+0D0h+var_118]; struct IUnknown *
0x18081b89b  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x18081b8a0  mov     rcx, [rbp+0D0h+pIUri]; struct IUnknown *
0x18081b8a7  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x18081b8ac  mov     rax, [rbp+0D0h+Source]
0x18081b8b0  test    rax, rax
0x18081b8b3  jz      short loc_18081B8C4
0x18081b8b5  mov     rcx, cs:g_hProcessHeap; this
0x18081b8bc  mov     rdx, rax; void *
0x18081b8bf  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18081b8c4  test    r14, r14
0x18081b8c7  jz      short loc_18081B8D8
0x18081b8c9  mov     rcx, cs:g_hProcessHeap; this
0x18081b8d0  mov     rdx, r14; void *
0x18081b8d3  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x18081b8d8  xor     edx, edx; struct IUri *
0x18081b8da  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18081b8e1  lea     rcx, [rbp+0D0h+var_68]; this
0x18081b8e5  mov     [rbp+0D0h+var_68], rax
0x18081b8e9  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x18081b8ed  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x18081b8f2  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x18081b8f6  call    cs:__imp_VariantClear
0x18081b8fc  lea     rcx, [rbp+0D0h+var_80]; pvarg
0x18081b900  call    cs:__imp_VariantClear
0x18081b906  lea     rcx, [rbp+0D0h+var_B0]; pvarg
0x18081b90a  call    cs:__imp_VariantClear
0x18081b910  lea     rcx, [rbp+0D0h+var_100]; pvarg
0x18081b914  call    cs:__imp_VariantClear
0x18081b91a  mov     rbx, [rsp+1E0h+arg_0]
0x18081b922  mov     eax, edi
0x18081b924  add     rsp, 1B0h
0x18081b92b  pop     r15
0x18081b92d  pop     r14
0x18081b92f  pop     r13
0x18081b931  pop     r12
0x18081b933  pop     rdi
0x18081b934  pop     rsi
0x18081b935  pop     rbp
0x18081b936  retn
0x18081b937  mov     r15, [rbp+0D0h+arg_40]
0x18081b93e  xor     r12d, r12d
0x18081b941  movzx   eax, byte ptr [rbp+0D0h+arg_20]
0x18081b948  shr     eax, 6
0x18081b94b  and     eax, 1
0x18081b94e  mov     dword ptr [rbp+0D0h+ppIUriBuilder], eax
0x18081b951  jmp     short loc_18081B9D0
0x18081b953  mov     rcx, [rbp+0D0h+arg_28]
0x18081b95a  xor     r12d, r12d
0x18081b95d  mov     dword ptr [rbp+0D0h+ppIUriBuilder], r12d
0x18081b961  mov     [rbp+0D0h+var_E8], r12d
0x18081b965  test    rcx, rcx
0x18081b968  jz      short loc_18081B978
0x18081b96a  mov     rax, [rcx+58h]
0x18081b96e  mov     r14, [rcx+50h]
0x18081b972  mov     [rbp+0D0h+var_108], rax
0x18081b976  jmp     short loc_18081B97F
0x18081b978  mov     r14, r12
0x18081b97b  mov     [rbp+0D0h+var_108], r12
0x18081b97f  cmp     r15d, 1
0x18081b983  mov     r15, [rbp+0D0h+arg_40]
  ... truncated ...
```
