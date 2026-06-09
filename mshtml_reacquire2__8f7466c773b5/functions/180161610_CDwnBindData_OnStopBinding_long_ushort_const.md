# CDwnBindData::OnStopBinding(long,ushort const *)

- ea: `0x180161610`
- end: `0x1801621ca`
- name: `?OnStopBinding@CDwnBindData@@EEAAJJPEBG@Z`
- size: `3002`
- prototype: `int(CDwnBindData *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800ea428`
- `0x1800f9604`
- `0x18011a7c4`
- `0x180157d14`
- `0x180157d3c`
- `0x18015b784`
- `0x180160818`
- `0x180161610`
- `0x180163740`
- `0x180265374`
- `0x1803b024c`
- `0x1803e17b0`
- `0x1803e41f0`
- `0x1803e434c`
- `0x180400d3c`
- `0x180400e88`
- `0x180402a74`
- `0x1804134dc`
- `0x180413b4c`
- `0x180413e44`
- `0x180475504`
- `0x180636de0`
- `0x180756c14`
- `0x1807bf19c`
- `0x1807dc988`
- `0x1807de32c`
- `0x180865980`
- `0x180866bb4`
- `0x180876b80`
- `0x180a3a9e0`
- `0x180a3b100`
- `0x180a3b5c4`
- `0x180b56744`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18016182e`
- `msvcrt!_wcsnicmp` at `0x18016182e`
- `KERNEL32!LeaveCriticalSection` at `0x180161756`
- `KERNEL32!LeaveCriticalSection` at `0x180161756`
- `KERNEL32!EnterCriticalSection` at `0x180161733`
- `KERNEL32!EnterCriticalSection` at `0x180161733`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f2c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f52`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f74`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f96`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161fb8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f2c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f52`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f74`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161f96`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180161fb8`
- `USER32!AllowSetForegroundWindow` at `0x180161d48`
- `USER32!AllowSetForegroundWindow` at `0x180161d48`
- `USER32!GetDesktopWindow` at `0x180161d57`
- `USER32!GetDesktopWindow` at `0x180161d68`
- `USER32!GetDesktopWindow` at `0x180161d57`
- `USER32!GetDesktopWindow` at `0x180161d68`
- `USER32!GetAncestor` at `0x180161d7c`
- `USER32!GetAncestor` at `0x180161d7c`
- `USER32!EnableWindow` at `0x180161d95`
- `USER32!EnableWindow` at `0x180161dfd`
- `USER32!EnableWindow` at `0x180161d95`
- `USER32!EnableWindow` at `0x180161dfd`
- `iertutil!CreateUri` at `0x18016200b`
- `iertutil!CreateUri` at `0x18016202b`
- `iertutil!CreateUri` at `0x18016200b`
- `iertutil!CreateUri` at `0x18016202b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180161c66`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180161c66`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180161bb0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180161bb0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180161776`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801618ab`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180161776`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801618ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180161848`
- `OLEAUT32!__imp_SysFreeString` at `0x180161848`

## pseudocode

```c
__int64 __fastcall CDwnBindData::OnStopBinding(CDwnBindData *this, __int64 a2, IUri *a3, __int64 a4)
{
  volatile signed __int32 *v4; // rsi
  const struct MIMEINFO *v6; // rcx
  const unsigned __int16 *v7; // r12
  int v8; // edi
  char v9; // r13
  int v10; // ecx
  __int64 v11; // rcx
  int v12; // r15d
  __int64 v14; // rcx
  int v15; // ecx
  __int64 v16; // rcx
  int v17; // eax
  BOOL v18; // r14d
  BOOL v19; // r14d
  struct IUri *v20; // r14
  int v21; // r14d
  const struct CMarkup *v22; // r14
  CMarkup *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  struct GWND *Gwnd; // rax
  __int64 v28; // r14
  const unsigned __int16 *v29; // rdx
  CMarkup *v30; // rax
  __int64 v31; // rax
  CDoc *v32; // r14
  CMarkup *v33; // rax
  __int64 v34; // rax
  struct IUri *v35; // r14
  __int64 v36; // rcx
  int v37; // eax
  DWORD v38; // edx
  int v39; // r15d
  HWND v40; // r12
  HWND DesktopWindow; // rax
  HWND Ancestor; // rax
  __int64 v43; // r15
  CDoc *v44; // r15
  CMarkup *v45; // rax
  struct GWND *v46; // rax
  int v47; // eax
  __int64 v48; // rcx
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  const WCHAR *v51; // r14
  int v52; // eax
  struct CMarkup *v53; // rdx
  int v54; // edx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  int v58; // [rsp+30h] [rbp-89h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-81h] BYREF
  IUri *ppURI; // [rsp+40h] [rbp-79h] BYREF
  int v61; // [rsp+48h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v63[2]; // [rsp+58h] [rbp-61h] BYREF
  int v64; // [rsp+68h] [rbp-51h]
  __int128 v65; // [rsp+70h] [rbp-49h]
  int v66; // [rsp+80h] [rbp-39h]
  __int128 v67; // [rsp+88h] [rbp-31h] BYREF
  __int128 v68; // [rsp+98h] [rbp-21h]
  DWORD dwProcessId; // [rsp+A8h] [rbp-11h]
  __int64 v70; // [rsp+B0h] [rbp-9h]
  __int128 v71; // [rsp+C0h] [rbp+7h] BYREF

  ppURI = a3;
  v4 = (volatile signed __int32 *)((char *)this - 24);
  v61 = 0;
  pv = 0;
  v6 = (const struct MIMEINFO *)*((_QWORD *)this + 54);
  v7 = (const unsigned __int16 *)a3;
  v8 = a2;
  v9 = 0;
  v71 = 0;
  if ( v6 )
  {
    if ( IsMimeTypeOldXML(v6) )
    {
      v24 = *((_QWORD *)this + 7);
      v25 = *(_QWORD *)(v24 + 112);
      if ( v25 )
      {
        if ( !*(_DWORD *)(v25 + 764) )
          *(_BYTE *)(v24 + 731) = 1;
      }
    }
  }
  if ( (unsigned int)(a2 + 2146697211) > 0x13 || (v10 = 590081, v58 = 1, !_bittest(&v10, a2 + 2146697211)) )
    v58 = 0;
  switch ( (_DWORD)a2 )
  {
    case 0x800C001A:
      v28 = *(_QWORD *)(*((_QWORD *)this + 7) + 104LL);
      if ( !v28
        || *(char *)(v28 + 4868) >= 0
        || (unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(
                              *(unsigned int *)(v28 + 5040),
                              *(unsigned int *)(v28 + 5044),
                              *(unsigned int *)(v28 + 5052),
                              *(unsigned int *)(v28 + 5048)) )
      {
        v29 = (const unsigned __int16 *)*((_QWORD *)this + 61);
        if ( !v29 )
          v29 = (const unsigned __int16 *)*((_QWORD *)this + 113);
        if ( !(unsigned int)CDwnBindData::HandleBrokerRedirect((CDwnBindData *)v4, v29) )
        {
          v8 = 0;
          if ( IsDualEngineProcess() )
          {
            if ( v28 )
            {
              v30 = CDoc::PendingPrimaryMarkup((CDoc *)v28);
              if ( v30 )
                CMarkup::TearDownMarkup(v30, 1, 0);
            }
          }
          goto LABEL_96;
        }
      }
      break;
    case 0x800C0022:
      v31 = *((_QWORD *)this + 7);
      v32 = *(CDoc **)(v31 + 104);
      if ( v32
        && (int)CDwnBindData::ContinueDualEngineNavigationInEdge((CDwnBindData *)v4, *(struct CDoc **)(v31 + 104)) >= 0 )
      {
        v8 = 0;
        v33 = CDoc::PendingPrimaryMarkup(v32);
        if ( v33 )
          CMarkup::TearDownMarkup(v33, 1, 0);
        v34 = *((_QWORD *)this + 53);
        v9 = 1;
        *(_WORD *)((char *)this + 775) = 257;
        if ( v34 )
          *(_BYTE *)(*(_QWORD *)(v34 + 32) + 348LL) = 1;
      }
      break;
    case 0x800C0020:
      if ( (unsigned __int8)IEConfiguration_GetBool(268435482, a2, a3, a4) )
      {
        v35 = (struct IUri *)*((_QWORD *)this + 56);
        if ( v35 )
        {
          ((void (__fastcall *)(_QWORD))v35->lpVtbl->AddRef)(*((_QWORD *)this + 56));
          LODWORD(String1) = 0;
          GetBOOL(
            (__int64 *)SettingStore::IEVALUE_Browser_EnterpriseMode_RestrictIE_ShowNeedEdgeInterstitial[0],
            &String1);
          if ( (_DWORD)String1 )
          {
            v36 = *(_QWORD *)(*((_QWORD *)this + 7) + 112LL);
            if ( v36 )
            {
              v26 = *(_QWORD *)(v36 + 352);
              if ( v26 )
              {
                if ( *(_QWORD *)(v26 + 120) )
                {
                  Gwnd = GetGwnd();
                  if ( (int)_GWPostMethodCallEx(Gwnd, 0, (__int64)CDoc::ReleasePostedIUri) < 0 )
                  {
                    CDoc::ReleasePostedIUri((unsigned __int64)v35);
                    break;
                  }
                  v8 = 0;
LABEL_96:
                  v9 = 1;
                  *((_BYTE *)this + 775) = 1;
                }
              }
            }
          }
          else
          {
            v63[1] = 0;
            v63[0] = &CUString::`vftable';
            v64 = 11;
            v66 = 0;
            v65 = 0;
            if ( (int)CUString::Set((CUString *)v63, v35, Uri_PROPERTY_ABSOLUTE_URI) >= 0 )
            {
              dwProcessId = 0;
              v70 = 0;
              v67 = 0;
              v68 = 0;
              v37 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v67);
              v38 = -1;
              v39 = v37;
              if ( dwProcessId )
                v38 = dwProcessId;
              AllowSetForegroundWindow(v38);
              v40 = 0;
              if ( GetDesktopWindow() )
              {
                DesktopWindow = GetDesktopWindow();
                Ancestor = GetAncestor(DesktopWindow, 2u);
                v40 = Ancestor;
                if ( Ancestor )
                  EnableWindow(Ancestor, 0);
              }
              if ( v39 >= 0 )
              {
                v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)&v68 + 1) + 2424LL))(
                        *((_QWORD *)&v68 + 1),
                        *((_QWORD *)&v65 + 1),
                        0);
                if ( v39 >= 0 )
                {
                  v39 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(&v67);
                  if ( v39 >= 0 )
                    v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v68 + 1) + 2432LL))(*((_QWORD *)&v68 + 1));
                }
              }
              if ( v40 )
                EnableWindow(v40, 1);
              CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>(&v67);
              if ( v39 >= 0 )
              {
                v43 = *((_QWORD *)this + 7);
                v8 = 0;
                if ( v43 )
                {
                  v44 = *(CDoc **)(v43 + 104);
                  if ( v44 )
                  {
                    v45 = CDoc::PendingPrimaryMarkup(v44);
                    if ( v45 )
                      CMarkup::TearDownMarkup(v45, 1, 0);
                    v46 = GetGwnd();
                    _GWPostMethodCallEx(v46, 1, 0);
                  }
                }
                v9 = 1;
                *((_BYTE *)this + 775) = 1;
              }
              v7 = (const unsigned __int16 *)ppURI;
            }
            ((void (__fastcall *)(struct IUri *))v35->lpVtbl->Release)(v35);
            v63[0] = &CUString::`vftable';
            CUString::Set((CUString *)v63, 0, Uri_PROPERTY_RAW_URI);
          }
        }
      }
      break;
  }
  if ( (*((_BYTE *)this + 156) & 1) != 0 )
  {
    v23 = *(CMarkup **)(*((_QWORD *)this + 7) + 112LL);
    if ( v23 )
      CMarkup::UpdateSameSiteCookieState(v23, 1);
  }
  v11 = *((_QWORD *)this + 34);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64, __int128 *, int *, LPVOID *, _QWORD))(*(_QWORD *)v11 + 64LL))(
      v11,
      &v71,
      &v61,
      &pv,
      0);
    v11 = (unsigned int)v61;
    if ( v61 >= 0 )
    {
      if ( v61 > 0 )
        v11 = (unsigned __int16)v61 | 0x80070000;
      v61 = v11;
    }
    if ( v8 == -2146697210 )
    {
      if ( (v11 & 0x1FFF0000) == 0x70000 )
        v11 = (unsigned __int16)v11;
      if ( (unsigned int)(v11 - 12013) <= 2 )
      {
        v22 = *(const struct CMarkup **)(*((_QWORD *)this + 7) + 112LL);
        if ( v22 )
        {
          ppURI = 0;
          if ( CMarkup::GetUri(v22, &ppURI) >= 0 )
          {
            LODWORD(String1) = 0;
            if ( ((int (__fastcall *)(IUri *, wchar_t **))ppURI->lpVtbl->GetScheme)(ppURI, &String1) >= 0
              && (_DWORD)String1 == 1 )
            {
              *((_BYTE *)v22 + 98) |= 0x40u;
              v8 = -2146697192;
              v58 = 1;
            }
            ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
          }
        }
      }
    }
  }
  v12 = v58;
  if ( v58 )
  {
    v47 = *((_DWORD *)this + 39);
    if ( (v47 & 0x10) != 0 && (v47 & 1) != 0 )
    {
      CBaseFT::EnterCriticalSection((CBaseFT *)v4);
      v48 = *(_QWORD *)(*((_QWORD *)this + 7) + 104LL);
      if ( v48 )
      {
        v49 = *(const unsigned __int16 **)(v48 + 4528);
        if ( v49 )
          *((_QWORD *)this + 54) = GetMimeInfoFromMimeType(v49, (*((_BYTE *)this + 395) & 0x20) != 0);
      }
      CBaseFT::LeaveCriticalSection((CBaseFT *)v4);
      v11 = *((_QWORD *)this + 54);
      if ( v11
        && (!StrCmpICW(*(LPCWSTR *)(v11 + 8), L"video/avi")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"video/x-msvideo")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"video/mpeg")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"video/quicktime")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"application/hta")) )
      {
        v50 = *((_QWORD *)this + 7);
        v11 = *(_QWORD *)(v50 + 656);
        v51 = *(const WCHAR **)(v50 + 800);
        ppURI = 0;
        String1 = 0;
        v58 = 0;
        if ( !v11 || !v51 )
          goto LABEL_136;
        if ( !CreateUri((LPCWSTR)v11, 0x3002B84u, 0, &ppURI)
          && !CreateUri(v51, 0x3002B84u, 0, (IUri **)&String1)
          && ((unsigned int (__fastcall *)(IUri *, wchar_t *, int *))ppURI->lpVtbl->IsEqual)(ppURI, String1, &v58) )
        {
          v58 = 0;
        }
        ReleaseInterface((struct IUnknown *)ppURI);
        ReleaseInterface((struct IUnknown *)String1);
        if ( !v58 )
        {
LABEL_136:
          v8 = 0;
          *((_BYTE *)this + 784) = 0;
        }
      }
    }
  }
  *((_BYTE *)this + 799) = 1;
  _InterlockedIncrement(v4 + 5);
  *((_BYTE *)this + 777) = 1;
  if ( v8 >= 0 )
  {
    if ( g_fDisableUnTrustedProtocol )
    {
      v11 = *((_QWORD *)this + 7) + 800LL;
      if ( *(_QWORD *)v11 )
      {
        if ( CStr::Length((CStr *)v11) )
        {
          v20 = (struct IUri *)*((_QWORD *)this + 108);
          if ( (unsigned int)IsDangerousProtocol(v20) )
          {
            if ( (unsigned int)IsDangerousChmMime(v20) )
            {
              LODWORD(String1) = 4;
              v21 = -2147467259;
              AddRefSharedSecurityManager();
              if ( s_pISM )
                v21 = ((__int64 (__fastcall *)(IInternetSecurityManager *, _QWORD, wchar_t **, _QWORD))s_pISM->lpVtbl->MapUrlToZone)(
                        s_pISM,
                        *(_QWORD *)(*((_QWORD *)this + 7) + 800LL),
                        &String1,
                        0);
              DecrementSharedSecurityManager();
              if ( v21 < 0 || ((unsigned int)String1 & 0xFFFFFFFD) != 0 )
                v8 = -2147024891;
            }
          }
        }
      }
    }
  }
  if ( !g_EnableSyncAsyncErrorHandling )
  {
LABEL_12:
    if ( v8 )
    {
      if ( v8 != -2147467260 && v8 != -2146697192 )
      {
        if ( v8 == -2146697189 )
        {
          v53 = *(struct CMarkup **)(*((_QWORD *)this + 7) + 112LL);
          if ( v53 )
            CWebOCEvents::RedirectXDomainBlocked((CWebOCEvents *)v11, v53, -2146697189, v7);
        }
        else if ( v8 == -2146695935 )
        {
          CDwnBindData::PrivacIEPostStateChangeToUIThread(v4, 2);
        }
        if ( !*((_BYTE *)this + 800) )
          CDwnBindData::HandleFailedNavigation((CDwnBindData *)v4, v8);
      }
    }
    else if ( !*((_BYTE *)this + 775) )
    {
      if ( *((_BYTE *)this + 782) )
      {
        EnterCriticalSection(&g_csDwnBindPend);
        if ( !*((_BYTE *)this + 774) )
          *((_BYTE *)this + 773) = 0;
        LeaveCriticalSection(&g_csDwnBindPend);
        CDwnBindData::SignalData((CDwnBindData *)v4);
        goto LABEL_18;
      }
      v55 = *((_QWORD *)this + 7);
      *((_BYTE *)this + 783) = 1;
      v56 = *(_QWORD *)(v55 + 112);
      if ( !v56 )
        goto LABEL_18;
      if ( *(_QWORD *)(v56 + 144) )
        v56 = *(_QWORD *)(v56 + 144);
      v57 = *(_QWORD *)(*(_QWORD *)(v56 + 352) + 120LL);
      if ( !v57 || (*(_BYTE *)(v57 + 224) & 0x40) == 0 )
        goto LABEL_18;
      goto LABEL_156;
    }
    if ( !*((_QWORD *)this + 34) || CDwnBindData::GetErrorStatusCode((CDwnBindData *)v4) != 204 )
    {
      v54 = v61;
      if ( v61 >= 0 || v9 )
        v54 = v8;
      goto LABEL_166;
    }
    if ( !*((_BYTE *)this + 800) )
      CDwnBindData::HandleFailedNavigation((CDwnBindData *)v4, 0);
LABEL_156:
    v54 = -2146697209;
LABEL_166:
    CDwnBindData::SignalDone((CDwnBindData *)v4, v54);
LABEL_18:
    CBaseFT::SubRelease((CBaseFT *)v4);
    CoTaskMemFree(pv);
    return 0;
  }
  v14 = *((_QWORD *)this + 108);
  v58 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 192LL))(v14, &v58) )
  {
    v15 = 0;
    v58 = 0;
  }
  else
  {
    v15 = v58;
  }
  if ( (unsigned int)(v15 - 15) <= 2 || v15 == 9 )
  {
    v18 = 1;
    goto LABEL_26;
  }
  v16 = *((_QWORD *)this + 108);
  String1 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v16 + 152LL))(v16, &String1);
  if ( v17 )
  {
    v18 = 0;
    if ( v17 != 1 )
      goto LABEL_26;
  }
  else
  {
    v18 = _wcsnicmp(String1, L"mhtml", 5u) == 0;
  }
  SysFreeString(String1);
LABEL_26:
  v19 = 0;
  if ( *((_BYTE *)this + 780) != 1 )
  {
    v52 = *((_DWORD *)this + 39);
    if ( (v52 & 0x10) == 0 && !v18 && (v52 & 1) != 0 )
      v19 = 1;
  }
  CBaseFT::EnterCriticalSection((CBaseFT *)v4);
  if ( *((_BYTE *)this + 798) || v8 >= 0 && !v19 || v12 )
  {
    CBaseFT::LeaveCriticalSection((CBaseFT *)v4);
    goto LABEL_12;
  }
  *((_BYTE *)this + 800) = 1;
  if ( v8 >= 0 )
    v8 = v9 == 0 ? 0x80004005 : 0;
  *((_DWORD *)v4 + 207) = v8;
  CBaseFT::SubRelease((CBaseFT *)v4);
  CoTaskMemFree(pv);
  CBaseFT::LeaveCriticalSection((CBaseFT *)v4);
  return *((unsigned int *)this + 201);
}

```

## disassembly

```asm
0x180161610  mov     [rsp-8+arg_18], rbx
0x180161615  push    rbp
0x180161616  push    rsi
0x180161617  push    rdi
0x180161618  push    r12
0x18016161a  push    r13
0x18016161c  push    r14
0x18016161e  push    r15
0x180161620  lea     rbp, [rsp-27h]
0x180161625  sub     rsp, 0E0h
0x18016162c  mov     rax, cs:__security_cookie
0x180161633  xor     rax, rsp
0x180161636  mov     [rbp+57h+var_40], rax
0x18016163a  xor     r15d, r15d
0x18016163d  mov     [rbp+57h+ppURI], r8
0x180161641  lea     rsi, [rcx-18h]
0x180161645  mov     [rbp+57h+var_C8], r15d
0x180161649  mov     rbx, rcx
0x18016164c  mov     [rbp+57h+pv], r15
0x180161650  mov     rcx, [rsi+1C8h]; struct MIMEINFO *
0x180161657  xorps   xmm0, xmm0
0x18016165a  mov     r12, r8
0x18016165d  mov     edi, edx
0x18016165f  mov     r13b, r15b
0x180161662  movups  [rbp+57h+var_50], xmm0
0x180161666  test    rcx, rcx
0x180161669  jnz     loc_180161AA8
0x18016166f  lea     eax, [rdx+7FF3FFFBh]
0x180161675  cmp     eax, 13h
0x180161678  ja      loc_180161983
0x18016167e  mov     ecx, 90101h
0x180161683  mov     [rsp+110h+var_E0], 1
0x18016168b  bt      ecx, eax
0x18016168e  jnb     loc_180161983
0x180161694  cmp     edx, 800C001Ah
0x18016169a  jz      loc_180161B4A
0x1801616a0  cmp     edx, 800C0022h
0x1801616a6  jz      loc_180161BF2
0x1801616ac  cmp     edx, 800C0020h
0x1801616b2  jz      loc_180161C61
0x1801616b8  test    byte ptr [rbx+9Ch], 1
0x1801616bf  jnz     loc_180161A6F
0x1801616c5  mov     rcx, [rbx+110h]; this
0x1801616cc  test    rcx, rcx
0x1801616cf  jnz     loc_18016198D
0x1801616d5  mov     r15d, [rsp+110h+var_E0]
0x1801616da  test    r15d, r15d
0x1801616dd  jnz     loc_180161EBA
0x1801616e3  mov     byte ptr [rbx+31Fh], 1
0x1801616ea  lock inc dword ptr [rsi+14h]
0x1801616ee  mov     byte ptr [rbx+309h], 1
0x1801616f5  test    edi, edi
0x1801616f7  jns     loc_1801618CA
0x1801616fd  cmp     cs:?g_EnableSyncAsyncErrorHandling@@3HA, 0; int g_EnableSyncAsyncErrorHandling
0x180161704  jnz     loc_1801617AC
0x18016170a  test    edi, edi
0x18016170c  jnz     loc_1801620DA
0x180161712  cmp     [rbx+307h], dil
0x180161719  jnz     loc_180162134
0x18016171f  cmp     [rbx+30Eh], dil
0x180161726  jz      loc_180162167
0x18016172c  lea     rcx, ?g_csDwnBindPend@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x180161733  call    cs:__imp_EnterCriticalSection
0x18016173a  nop     dword ptr [rax+rax+00h]
0x18016173f  cmp     [rbx+306h], dil
0x180161746  jnz     short loc_18016174F
0x180161748  mov     [rbx+305h], dil
0x18016174f  lea     rcx, ?g_csDwnBindPend@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x180161756  call    cs:__imp_LeaveCriticalSection
0x18016175d  nop     dword ptr [rax+rax+00h]
0x180161762  mov     rcx, rsi; this
0x180161765  call    ?SignalData@CDwnBindData@@AEAAXXZ; CDwnBindData::SignalData(void)
0x18016176a  mov     rcx, rsi; this
0x18016176d  call    ?SubRelease@CBaseFT@@QEAAKXZ; CBaseFT::SubRelease(void)
0x180161772  mov     rcx, [rbp+57h+pv]; pv
0x180161776  call    cs:__imp_CoTaskMemFree
0x18016177d  nop     dword ptr [rax+rax+00h]
0x180161782  xor     eax, eax
0x180161784  mov     rcx, [rbp+57h+var_40]
0x180161788  xor     rcx, rsp; StackCookie
0x18016178b  call    __security_check_cookie
0x180161790  mov     rbx, [rsp+110h+arg_18]
0x180161798  add     rsp, 0E0h
0x18016179f  pop     r15
0x1801617a1  pop     r14
0x1801617a3  pop     r13
0x1801617a5  pop     r12
0x1801617a7  pop     rdi
0x1801617a8  pop     rsi
0x1801617a9  pop     rbp
0x1801617aa  retn
0x1801617ac  mov     rcx, [rbx+360h]
0x1801617b3  lea     rdx, [rsp+110h+var_E0]
0x1801617b8  mov     [rsp+110h+var_E0], 0
0x1801617c0  mov     rax, [rcx]
0x1801617c3  mov     rax, [rax+0C0h]
0x1801617ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801617cf  test    eax, eax
0x1801617d1  jz      loc_180161A66
0x1801617d7  xor     ecx, ecx
0x1801617d9  mov     [rsp+110h+var_E0], ecx
0x1801617dd  lea     eax, [rcx-0Fh]
0x1801617e0  cmp     eax, 2
0x1801617e3  jbe     loc_180161A9D
0x1801617e9  cmp     ecx, 9
0x1801617ec  jz      loc_180161A9D
0x1801617f2  mov     rcx, [rbx+360h]
0x1801617f9  lea     rdx, [rsp+110h+String1]
0x1801617fe  mov     [rsp+110h+String1], 0
0x180161807  mov     rax, [rcx]
0x18016180a  mov     rax, [rax+98h]
0x180161811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161816  test    eax, eax
0x180161818  jnz     loc_180161A8C
0x18016181e  mov     rcx, [rsp+110h+String1]; String1
0x180161823  lea     r8d, [rax+5]; MaxCount
0x180161827  lea     rdx, aMhtml; "mhtml"
0x18016182e  call    cs:__imp__wcsnicmp
0x180161835  nop     dword ptr [rax+rax+00h]
0x18016183a  xor     r14d, r14d
0x18016183d  test    eax, eax
0x18016183f  setz    r14b
0x180161843  mov     rcx, [rsp+110h+String1]; bstrString
0x180161848  call    cs:__imp_SysFreeString
0x18016184f  nop     dword ptr [rax+rax+00h]
0x180161854  cmp     byte ptr [rbx+30Ch], 1
0x18016185b  jnz     loc_180162090
0x180161861  xor     r14d, r14d
0x180161864  mov     rcx, rsi; this
0x180161867  call    ?EnterCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::EnterCriticalSection(void)
0x18016186c  cmp     byte ptr [rbx+31Eh], 0
0x180161873  jnz     loc_180161A59
0x180161879  test    edi, edi
0x18016187b  jns     loc_1801620BA
0x180161881  test    r15d, r15d
0x180161884  jnz     loc_180161A59
0x18016188a  mov     byte ptr [rbx+320h], 1
0x180161891  test    edi, edi
0x180161893  jns     loc_1801620C8
0x180161899  mov     rcx, rsi; this
0x18016189c  mov     [rsi+33Ch], edi
0x1801618a2  call    ?SubRelease@CBaseFT@@QEAAKXZ; CBaseFT::SubRelease(void)
0x1801618a7  mov     rcx, [rbp+57h+pv]; pv
0x1801618ab  call    cs:__imp_CoTaskMemFree
0x1801618b2  nop     dword ptr [rax+rax+00h]
0x1801618b7  mov     rcx, rsi; this
0x1801618ba  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x1801618bf  mov     eax, [rbx+324h]
0x1801618c5  jmp     loc_180161784
0x1801618ca  cmp     cs:?g_fDisableUnTrustedProtocol@@3HA, 0; int g_fDisableUnTrustedProtocol
0x1801618d1  jz      loc_1801616FD
0x1801618d7  mov     rcx, [rbx+38h]
0x1801618db  add     rcx, 320h; this
0x1801618e2  cmp     qword ptr [rcx], 0
0x1801618e6  jz      loc_1801616FD
0x1801618ec  call    ?Length@CStr@@QEBAIXZ; CStr::Length(void)
0x1801618f1  test    eax, eax
0x1801618f3  jz      loc_1801616FD
0x1801618f9  mov     r14, [rbx+360h]
0x180161900  mov     rcx, r14; struct IUri *
0x180161903  call    ?IsDangerousProtocol@@YAHPEAUIUri@@@Z; IsDangerousProtocol(IUri *)
0x180161908  test    eax, eax
0x18016190a  jz      loc_1801616FD
0x180161910  mov     rcx, r14; struct IUri *
0x180161913  call    ?IsDangerousChmMime@@YAHPEAUIUri@@@Z; IsDangerousChmMime(IUri *)
0x180161918  test    eax, eax
0x18016191a  jz      loc_1801616FD
0x180161920  mov     dword ptr [rsp+110h+String1], 4
0x180161928  mov     r14d, 80004005h
0x18016192e  call    ?AddRefSharedSecurityManager@@YAXXZ; AddRefSharedSecurityManager(void)
0x180161933  mov     rcx, cs:?s_pISM@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * s_pISM
0x18016193a  test    rcx, rcx
0x18016193d  jz      short loc_180161961
0x18016193f  mov     rax, [rcx]
0x180161942  lea     r8, [rsp+110h+String1]
0x180161947  mov     rdx, [rbx+38h]
0x18016194b  xor     r9d, r9d
0x18016194e  mov     rax, [rax+28h]
0x180161952  mov     rdx, [rdx+320h]
0x180161959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016195e  mov     r14d, eax
0x180161961  call    ?DecrementSharedSecurityManager@@YAXXZ; DecrementSharedSecurityManager(void)
0x180161966  test    r14d, r14d
0x180161969  js      short loc_180161979
0x18016196b  test    dword ptr [rsp+110h+String1], 0FFFFFFFDh
0x180161973  jz      loc_1801616FD
0x180161979  mov     edi, 80070005h
0x18016197e  jmp     loc_1801616FD
0x180161983  mov     [rsp+110h+var_E0], r15d
0x180161988  jmp     loc_180161694
0x18016198d  mov     rax, [rcx]
0x180161990  lea     r9, [rbp+57h+pv]
0x180161994  lea     r8, [rbp+57h+var_C8]
0x180161998  mov     qword ptr [rsp+110h+var_F0], r15
0x18016199d  lea     rdx, [rbp+57h+var_50]
0x1801619a1  mov     rax, [rax+40h]
0x1801619a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801619aa  mov     ecx, [rbp+57h+var_C8]
0x1801619ad  test    ecx, ecx
0x1801619af  jns     loc_180161B3C
0x1801619b5  cmp     edi, 800C0006h
0x1801619bb  jnz     loc_1801616D5
0x1801619c1  mov     eax, ecx
0x1801619c3  and     eax, 1FFF0000h
0x1801619c8  cmp     eax, 70000h
0x1801619cd  jnz     short loc_1801619D2
0x1801619cf  movzx   ecx, cx
0x1801619d2  lea     eax, [rcx-2EEDh]
0x1801619d8  cmp     eax, 2
0x1801619db  ja      loc_1801616D5
0x1801619e1  mov     rax, [rbx+38h]
0x1801619e5  mov     r14, [rax+70h]
0x1801619e9  test    r14, r14
0x1801619ec  jz      loc_1801616D5
0x1801619f2  lea     rdx, [rbp+57h+ppURI]; struct IUri **
0x1801619f6  mov     [rbp+57h+ppURI], r15
0x1801619fa  mov     rcx, r14; struct CMarkup *
0x1801619fd  call    ?GetUri@CMarkup@@SAJQEBV1@PEAPEAUIUri@@@Z; CMarkup::GetUri(CMarkup const * const,IUri * *)
0x180161a02  test    eax, eax
0x180161a04  js      loc_1801616D5
0x180161a0a  mov     rcx, [rbp+57h+ppURI]
0x180161a0e  lea     rdx, [rsp+110h+String1]
0x180161a13  mov     dword ptr [rsp+110h+String1], r15d
0x180161a18  mov     rax, [rcx]
0x180161a1b  mov     rax, [rax+0C0h]
0x180161a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161a27  test    eax, eax
0x180161a29  js      short loc_180161A44
0x180161a2b  cmp     dword ptr [rsp+110h+String1], 1
0x180161a30  jnz     short loc_180161A44
0x180161a32  or      byte ptr [r14+62h], 40h
0x180161a37  mov     edi, 800C0018h
0x180161a3c  mov     [rsp+110h+var_E0], 1
0x180161a44  mov     rcx, [rbp+57h+ppURI]
0x180161a48  mov     rax, [rcx]
0x180161a4b  mov     rax, [rax+10h]
0x180161a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161a54  jmp     loc_1801616D5
0x180161a59  mov     rcx, rsi; this
0x180161a5c  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x180161a61  jmp     loc_18016170A
0x180161a66  mov     ecx, [rsp+110h+var_E0]
0x180161a6a  jmp     loc_1801617DD
0x180161a6f  mov     rax, [rbx+38h]
0x180161a73  mov     rcx, [rax+70h]; this
0x180161a77  test    rcx, rcx
0x180161a7a  jz      loc_1801616C5
0x180161a80  mov     dl, 1; bool
0x180161a82  call    ?UpdateSameSiteCookieState@CMarkup@@QEAAX_N@Z; CMarkup::UpdateSameSiteCookieState(bool)
0x180161a87  jmp     loc_1801616C5
0x180161a8c  xor     r14d, r14d
0x180161a8f  cmp     eax, 1
0x180161a92  jnz     loc_180161854
0x180161a98  jmp     loc_180161843
0x180161a9d  mov     r14d, 1
0x180161aa3  jmp     loc_180161854
0x180161aa8  call    ?IsMimeTypeOldXML@@YA_NPEBUMIMEINFO@@@Z; IsMimeTypeOldXML(MIMEINFO const *)
0x180161aad  test    al, al
0x180161aaf  jz      loc_18016166F
0x180161ab5  mov     rcx, [rbx+38h]
0x180161ab9  mov     rax, [rcx+70h]
0x180161abd  test    rax, rax
0x180161ac0  jz      loc_18016166F
0x180161ac6  cmp     [rax+2FCh], r15d
0x180161acd  jnz     loc_18016166F
0x180161ad3  mov     byte ptr [rcx+2DBh], 1
0x180161ada  jmp     loc_18016166F
0x180161adf  mov     rax, [rcx+160h]
0x180161ae6  test    rax, rax
0x180161ae9  jz      loc_1801616B8
0x180161aef  mov     r10, [rax+78h]
0x180161af3  test    r10, r10
0x180161af6  jz      loc_1801616B8
0x180161afc  call    ?GetGwnd@@YAPEAVGWND@@XZ; GetGwnd(void)
0x180161b01  lea     rcx, ?ReleasePostedIUri@CDoc@@SAX_K@Z; CDoc::ReleasePostedIUri(unsigned __int64)
0x180161b08  mov     r9, r14
0x180161b0b  mov     [rsp+110h+var_E8], rcx; __int64
0x180161b10  lea     r8, ?NavigateToNeedEdgeErrorPageCallback@CWindow@@QEAAX_K@Z; CWindow::NavigateToNeedEdgeErrorPageCallback(unsigned __int64)
0x180161b17  mov     rcx, rax; struct GWND *
0x180161b1a  mov     [rsp+110h+var_F0], r15d; int
0x180161b1f  mov     rdx, r10
0x180161b22  call    ?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z; _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))
0x180161b27  test    eax, eax
0x180161b29  jns     loc_180161CCC
0x180161b2f  mov     rcx, r14; unsigned __int64
0x180161b32  call    ?ReleasePostedIUri@CDoc@@SAX_K@Z; CDoc::ReleasePostedIUri(unsigned __int64)
0x180161b37  jmp     loc_1801616B8
0x180161b3c  jg      loc_180161EAC
0x180161b42  mov     [rbp+57h+var_C8], ecx
0x180161b45  jmp     loc_1801619B5
0x180161b4a  mov     rax, [rbx+38h]
0x180161b4e  mov     r14, [rax+68h]
0x180161b52  test    r14, r14
0x180161b55  jz      short loc_180161B8A
0x180161b57  test    byte ptr [r14+1304h], 80h
0x180161b5f  jz      short loc_180161B8A
0x180161b61  mov     r9d, [r14+13B8h]
0x180161b68  mov     r8d, [r14+13BCh]
0x180161b6f  mov     edx, [r14+13B4h]
0x180161b76  mov     ecx, [r14+13B0h]
  ... truncated ...
```
