# CDwnBindData::OnStopBinding(long,ushort const *)

- ea: `0x1804e7d30`
- end: `0x1804e885f`
- name: `?OnStopBinding@CDwnBindData@@EEAAJJPEBG@Z`
- size: `2863`
- prototype: `__int64 __fastcall(CDwnBindData *this, int, IUri *)`
- caller_count: `0`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180146f6c`
- `0x1801a194c`
- `0x18021fdac`
- `0x180222728`
- `0x180282f30`
- `0x1802fe254`
- `0x1802fe388`
- `0x180300074`
- `0x18034a080`
- `0x18043c328`
- `0x180494570`
- `0x180497b20`
- `0x180497b40`
- `0x1804e15e8`
- `0x1804e223c`
- `0x1804e3010`
- `0x1804e7880`
- `0x1804e7d30`
- `0x1805a5094`
- `0x18063b8a8`
- `0x1806b7810`
- `0x180731bd0`
- `0x18074db7c`
- `0x1807b3584`
- `0x1807d076c`
- `0x1807d1bfc`
- `0x180860900`
- `0x180861a7c`
- `0x1808705f0`
- `0x180a27ba0`
- `0x180a28264`
- `0x180a28710`
- `0x180b3e264`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1804e7f3b`
- `msvcrt!_wcsnicmp` at `0x1804e7f3b`
- `KERNEL32!LeaveCriticalSection` at `0x1804e7e70`
- `KERNEL32!LeaveCriticalSection` at `0x1804e7e70`
- `KERNEL32!EnterCriticalSection` at `0x1804e7e53`
- `KERNEL32!EnterCriticalSection` at `0x1804e7e53`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e85f7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e8613`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e862f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e864b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e8667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e85f7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e8613`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e862f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e864b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x1804e8667`
- `USER32!AllowSetForegroundWindow` at `0x1804e8437`
- `USER32!AllowSetForegroundWindow` at `0x1804e8437`
- `USER32!GetDesktopWindow` at `0x1804e8440`
- `USER32!GetDesktopWindow` at `0x1804e844b`
- `USER32!GetDesktopWindow` at `0x1804e8440`
- `USER32!GetDesktopWindow` at `0x1804e844b`
- `USER32!GetAncestor` at `0x1804e8459`
- `USER32!GetAncestor` at `0x1804e8459`
- `USER32!EnableWindow` at `0x1804e846c`
- `USER32!EnableWindow` at `0x1804e84ce`
- `USER32!EnableWindow` at `0x1804e846c`
- `USER32!EnableWindow` at `0x1804e84ce`
- `iertutil!CreateUri` at `0x1804e86ac`
- `iertutil!CreateUri` at `0x1804e86c6`
- `iertutil!CreateUri` at `0x1804e86ac`
- `iertutil!CreateUri` at `0x1804e86c6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804e835b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1804e835b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1804e82ab`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1804e82ab`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804e7e8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804e7fac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804e7e8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804e7fac`
- `OLEAUT32!__imp_SysFreeString` at `0x1804e7f4f`
- `OLEAUT32!__imp_SysFreeString` at `0x1804e7f4f`

## pseudocode

```c
__int64 __fastcall CDwnBindData::OnStopBinding(CDwnBindData *this, int a2, IUri *a3)
{
  volatile signed __int32 *v3; // rsi
  const struct MIMEINFO *v5; // rcx
  const unsigned __int16 *v6; // r12
  int v7; // edi
  char v8; // r13
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // r15d
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v15; // rcx
  int v16; // eax
  BOOL v17; // r14d
  BOOL v18; // r14d
  struct IUri *v19; // r14
  int v20; // r14d
  const struct CMarkup *v21; // r14
  CMarkup *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  struct GWND *Gwnd; // rax
  __int64 v27; // r14
  const unsigned __int16 *v28; // rdx
  CMarkup *v29; // rax
  __int64 v30; // rax
  CDoc *v31; // r14
  CMarkup *v32; // rax
  __int64 v33; // rax
  struct IUri *v34; // r14
  __int64 v35; // rcx
  int v36; // eax
  DWORD v37; // edx
  int v38; // r15d
  HWND v39; // r12
  HWND DesktopWindow; // rax
  HWND Ancestor; // rax
  __int64 v42; // r15
  CDoc *v43; // r15
  CMarkup *v44; // rax
  struct GWND *v45; // rax
  int v46; // eax
  __int64 v47; // rcx
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  const WCHAR *v50; // r14
  int v51; // eax
  struct CMarkup *v52; // rdx
  int v53; // edx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rcx
  int v57; // [rsp+30h] [rbp-89h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-81h] BYREF
  IUri *ppURI; // [rsp+40h] [rbp-79h] BYREF
  int v60; // [rsp+48h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v62[2]; // [rsp+58h] [rbp-61h] BYREF
  int v63; // [rsp+68h] [rbp-51h]
  __int128 v64; // [rsp+70h] [rbp-49h]
  int v65; // [rsp+80h] [rbp-39h]
  __int128 v66; // [rsp+88h] [rbp-31h] BYREF
  __int128 v67; // [rsp+98h] [rbp-21h]
  DWORD dwProcessId; // [rsp+A8h] [rbp-11h]
  __int64 v69; // [rsp+B0h] [rbp-9h]
  __int128 v70; // [rsp+C0h] [rbp+7h] BYREF

  ppURI = a3;
  v3 = (volatile signed __int32 *)((char *)this - 24);
  v60 = 0;
  pv = 0;
  v5 = (const struct MIMEINFO *)*((_QWORD *)this + 54);
  v6 = (const unsigned __int16 *)a3;
  v7 = a2;
  v8 = 0;
  v70 = 0;
  if ( v5 )
  {
    if ( IsMimeTypeOldXML(v5) )
    {
      v23 = *((_QWORD *)this + 7);
      v24 = *(_QWORD *)(v23 + 112);
      if ( v24 )
      {
        if ( !*(_DWORD *)(v24 + 764) )
          *(_BYTE *)(v23 + 731) = 1;
      }
    }
  }
  if ( (unsigned int)(a2 + 2146697211) > 0x13 || (v9 = 590081, v57 = 1, !_bittest(&v9, a2 + 2146697211)) )
    v57 = 0;
  switch ( a2 )
  {
    case -2146697190:
      v27 = *(_QWORD *)(*((_QWORD *)this + 7) + 104LL);
      if ( !v27
        || *(char *)(v27 + 4868) >= 0
        || (unsigned __int8)IsWebPlatformHostBehaviorSupported<6>(
                              *(unsigned int *)(v27 + 5040),
                              *(unsigned int *)(v27 + 5044),
                              *(unsigned int *)(v27 + 5052),
                              *(unsigned int *)(v27 + 5048)) )
      {
        v28 = (const unsigned __int16 *)*((_QWORD *)this + 61);
        if ( !v28 )
          v28 = (const unsigned __int16 *)*((_QWORD *)this + 113);
        if ( !(unsigned int)CDwnBindData::HandleBrokerRedirect((CDwnBindData *)v3, v28, (int)a3) )
        {
          v7 = 0;
          if ( IsDualEngineProcess() )
          {
            if ( v27 )
            {
              v29 = CDoc::PendingPrimaryMarkup((CDoc *)v27);
              if ( v29 )
                CMarkup::TearDownMarkup(v29, 1, 0);
            }
          }
          goto LABEL_96;
        }
      }
      break;
    case -2146697182:
      v30 = *((_QWORD *)this + 7);
      v31 = *(CDoc **)(v30 + 104);
      if ( v31
        && (int)CDwnBindData::ContinueDualEngineNavigationInEdge((CDwnBindData *)v3, *(struct CDoc **)(v30 + 104)) >= 0 )
      {
        v7 = 0;
        v32 = CDoc::PendingPrimaryMarkup(v31);
        if ( v32 )
          CMarkup::TearDownMarkup(v32, 1, 0);
        v33 = *((_QWORD *)this + 53);
        v8 = 1;
        *(_WORD *)((char *)this + 775) = 257;
        if ( v33 )
          *(_BYTE *)(*(_QWORD *)(v33 + 32) + 348LL) = 1;
      }
      break;
    case -2146697184:
      if ( (unsigned __int8)IEConfiguration_GetBool(268435482) )
      {
        v34 = (struct IUri *)*((_QWORD *)this + 56);
        if ( v34 )
        {
          ((void (__fastcall *)(_QWORD))v34->lpVtbl->AddRef)(*((_QWORD *)this + 56));
          LODWORD(String1) = 0;
          GetBOOL(
            (__int64 *)SettingStore::IEVALUE_Browser_EnterpriseMode_RestrictIE_ShowNeedEdgeInterstitial[0],
            &String1);
          if ( (_DWORD)String1 )
          {
            v35 = *(_QWORD *)(*((_QWORD *)this + 7) + 112LL);
            if ( v35 )
            {
              v25 = *(_QWORD *)(v35 + 352);
              if ( v25 )
              {
                if ( *(_QWORD *)(v25 + 120) )
                {
                  Gwnd = GetGwnd();
                  if ( (int)_GWPostMethodCallEx(Gwnd, 0, (__int64)CDoc::ReleasePostedIUri) < 0 )
                  {
                    CDoc::ReleasePostedIUri((unsigned __int64)v34);
                    break;
                  }
                  v7 = 0;
LABEL_96:
                  v8 = 1;
                  *((_BYTE *)this + 775) = 1;
                }
              }
            }
          }
          else
          {
            v62[1] = 0;
            v62[0] = &CUString::`vftable';
            v63 = 11;
            v65 = 0;
            v64 = 0;
            if ( (int)CUString::Set((CUString *)v62, v34, Uri_PROPERTY_ABSOLUTE_URI) >= 0 )
            {
              dwProcessId = 0;
              v69 = 0;
              v66 = 0;
              v67 = 0;
              v36 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v66);
              v37 = -1;
              v38 = v36;
              if ( dwProcessId )
                v37 = dwProcessId;
              AllowSetForegroundWindow(v37);
              v39 = 0;
              if ( GetDesktopWindow() )
              {
                DesktopWindow = GetDesktopWindow();
                Ancestor = GetAncestor(DesktopWindow, 2u);
                v39 = Ancestor;
                if ( Ancestor )
                  EnableWindow(Ancestor, 0);
              }
              if ( v38 >= 0 )
              {
                v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)&v67 + 1) + 2424LL))(
                        *((_QWORD *)&v67 + 1),
                        *((_QWORD *)&v64 + 1),
                        0);
                if ( v38 >= 0 )
                {
                  v38 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(&v66);
                  if ( v38 >= 0 )
                    v38 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v67 + 1) + 2432LL))(*((_QWORD *)&v67 + 1));
                }
              }
              if ( v39 )
                EnableWindow(v39, 1);
              CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>(&v66);
              if ( v38 >= 0 )
              {
                v42 = *((_QWORD *)this + 7);
                v7 = 0;
                if ( v42 )
                {
                  v43 = *(CDoc **)(v42 + 104);
                  if ( v43 )
                  {
                    v44 = CDoc::PendingPrimaryMarkup(v43);
                    if ( v44 )
                      CMarkup::TearDownMarkup(v44, 1, 0);
                    v45 = GetGwnd();
                    _GWPostMethodCallEx(v45, 1, 0);
                  }
                }
                v8 = 1;
                *((_BYTE *)this + 775) = 1;
              }
              v6 = (const unsigned __int16 *)ppURI;
            }
            ((void (__fastcall *)(struct IUri *))v34->lpVtbl->Release)(v34);
            v62[0] = &CUString::`vftable';
            CUString::Set((CUString *)v62, 0, Uri_PROPERTY_RAW_URI);
          }
        }
      }
      break;
  }
  if ( (*((_BYTE *)this + 156) & 1) != 0 )
  {
    v22 = *(CMarkup **)(*((_QWORD *)this + 7) + 112LL);
    if ( v22 )
      CMarkup::UpdateSameSiteCookieState(v22, 1);
  }
  v10 = *((_QWORD *)this + 34);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64, __int128 *, int *, LPVOID *, _QWORD))(*(_QWORD *)v10 + 64LL))(
      v10,
      &v70,
      &v60,
      &pv,
      0);
    v10 = (unsigned int)v60;
    if ( v60 >= 0 )
    {
      if ( v60 > 0 )
        v10 = (unsigned __int16)v60 | 0x80070000;
      v60 = v10;
    }
    if ( v7 == -2146697210 )
    {
      if ( (v10 & 0x1FFF0000) == 0x70000 )
        v10 = (unsigned __int16)v10;
      if ( (unsigned int)(v10 - 12013) <= 2 )
      {
        v21 = *(const struct CMarkup **)(*((_QWORD *)this + 7) + 112LL);
        if ( v21 )
        {
          ppURI = 0;
          if ( CMarkup::GetUri(v21, &ppURI) >= 0 )
          {
            LODWORD(String1) = 0;
            if ( ((int (__fastcall *)(IUri *, wchar_t **))ppURI->lpVtbl->GetScheme)(ppURI, &String1) >= 0
              && (_DWORD)String1 == 1 )
            {
              *((_BYTE *)v21 + 98) |= 0x40u;
              v7 = -2146697192;
              v57 = 1;
            }
            ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
          }
        }
      }
    }
  }
  v11 = v57;
  if ( v57 )
  {
    v46 = *((_DWORD *)this + 39);
    if ( (v46 & 0x10) != 0 && (v46 & 1) != 0 )
    {
      CBaseFT::EnterCriticalSection((CBaseFT *)v3);
      v47 = *(_QWORD *)(*((_QWORD *)this + 7) + 104LL);
      if ( v47 )
      {
        v48 = *(const unsigned __int16 **)(v47 + 4528);
        if ( v48 )
          *((_QWORD *)this + 54) = GetMimeInfoFromMimeType(v48, (*((_BYTE *)this + 395) & 0x20) != 0);
      }
      CBaseFT::LeaveCriticalSection((CBaseFT *)v3);
      v10 = *((_QWORD *)this + 54);
      if ( v10
        && (!StrCmpICW(*(LPCWSTR *)(v10 + 8), L"video/avi")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"video/x-msvideo")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"video/mpeg")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"video/quicktime")
         || !StrCmpICW(*(LPCWSTR *)(*((_QWORD *)this + 54) + 8LL), L"application/hta")) )
      {
        v49 = *((_QWORD *)this + 7);
        v10 = *(_QWORD *)(v49 + 656);
        v50 = *(const WCHAR **)(v49 + 800);
        ppURI = 0;
        String1 = 0;
        v57 = 0;
        if ( !v10 || !v50 )
          goto LABEL_136;
        if ( !CreateUri((LPCWSTR)v10, 0x3002B84u, 0, &ppURI)
          && !CreateUri(v50, 0x3002B84u, 0, (IUri **)&String1)
          && ((unsigned int (__fastcall *)(IUri *, wchar_t *, int *))ppURI->lpVtbl->IsEqual)(ppURI, String1, &v57) )
        {
          v57 = 0;
        }
        ReleaseInterface((struct IUnknown *)ppURI);
        ReleaseInterface((struct IUnknown *)String1);
        if ( !v57 )
        {
LABEL_136:
          v7 = 0;
          *((_BYTE *)this + 784) = 0;
        }
      }
    }
  }
  *((_BYTE *)this + 799) = 1;
  _InterlockedIncrement(v3 + 5);
  *((_BYTE *)this + 777) = 1;
  if ( v7 >= 0 )
  {
    if ( g_fDisableUnTrustedProtocol )
    {
      v10 = *((_QWORD *)this + 7) + 800LL;
      if ( *(_QWORD *)v10 )
      {
        if ( CStr::Length((CStr *)v10) )
        {
          v19 = (struct IUri *)*((_QWORD *)this + 108);
          if ( (unsigned int)IsDangerousProtocol(v19) )
          {
            if ( (unsigned int)IsDangerousChmMime(v19) )
            {
              LODWORD(String1) = 4;
              v20 = -2147467259;
              AddRefSharedSecurityManager();
              if ( s_pISM )
                v20 = ((__int64 (__fastcall *)(IInternetSecurityManager *, _QWORD, wchar_t **, _QWORD))s_pISM->lpVtbl->MapUrlToZone)(
                        s_pISM,
                        *(_QWORD *)(*((_QWORD *)this + 7) + 800LL),
                        &String1,
                        0);
              DecrementSharedSecurityManager();
              if ( v20 < 0 || ((unsigned int)String1 & 0xFFFFFFFD) != 0 )
                v7 = -2147024891;
            }
          }
        }
      }
    }
  }
  if ( !g_EnableSyncAsyncErrorHandling )
  {
LABEL_12:
    if ( v7 )
    {
      if ( v7 != -2147467260 && v7 != -2146697192 )
      {
        if ( v7 == -2146697189 )
        {
          v52 = *(struct CMarkup **)(*((_QWORD *)this + 7) + 112LL);
          if ( v52 )
            CWebOCEvents::RedirectXDomainBlocked((CWebOCEvents *)v10, v52, -2146697189, v6);
        }
        else if ( v7 == -2146695935 )
        {
          CDwnBindData::PrivacIEPostStateChangeToUIThread(v3, 2);
        }
        if ( !*((_BYTE *)this + 800) )
          CDwnBindData::HandleFailedNavigation((CDwnBindData *)v3, v7);
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
        CDwnBindData::SignalData((CDwnBindData *)v3);
        goto LABEL_18;
      }
      v54 = *((_QWORD *)this + 7);
      *((_BYTE *)this + 783) = 1;
      v55 = *(_QWORD *)(v54 + 112);
      if ( !v55 )
        goto LABEL_18;
      if ( *(_QWORD *)(v55 + 144) )
        v55 = *(_QWORD *)(v55 + 144);
      v56 = *(_QWORD *)(*(_QWORD *)(v55 + 352) + 120LL);
      if ( !v56 || (*(_BYTE *)(v56 + 224) & 0x40) == 0 )
        goto LABEL_18;
      goto LABEL_156;
    }
    if ( !*((_QWORD *)this + 34) || CDwnBindData::GetErrorStatusCode((CDwnBindData *)v3) != 204 )
    {
      v53 = v60;
      if ( v60 >= 0 || v8 )
        v53 = v7;
      goto LABEL_166;
    }
    if ( !*((_BYTE *)this + 800) )
      CDwnBindData::HandleFailedNavigation((CDwnBindData *)v3, 0);
LABEL_156:
    v53 = -2146697209;
LABEL_166:
    CDwnBindData::SignalDone((CDwnBindData *)v3, v53);
LABEL_18:
    CBaseFT::SubRelease((CBaseFT *)v3);
    CoTaskMemFree(pv);
    return 0;
  }
  v13 = *((_QWORD *)this + 108);
  v57 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 192LL))(v13, &v57) )
  {
    v14 = 0;
    v57 = 0;
  }
  else
  {
    v14 = v57;
  }
  if ( (unsigned int)(v14 - 15) <= 2 || v14 == 9 )
  {
    v17 = 1;
    goto LABEL_26;
  }
  v15 = *((_QWORD *)this + 108);
  String1 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v15 + 152LL))(v15, &String1);
  if ( v16 )
  {
    v17 = 0;
    if ( v16 != 1 )
      goto LABEL_26;
  }
  else
  {
    v17 = _wcsnicmp(String1, L"mhtml", 5u) == 0;
  }
  SysFreeString(String1);
LABEL_26:
  v18 = 0;
  if ( *((_BYTE *)this + 780) != 1 )
  {
    v51 = *((_DWORD *)this + 39);
    if ( (v51 & 0x10) == 0 && !v17 && (v51 & 1) != 0 )
      v18 = 1;
  }
  CBaseFT::EnterCriticalSection((CBaseFT *)v3);
  if ( *((_BYTE *)this + 798) || v7 >= 0 && !v18 || v11 )
  {
    CBaseFT::LeaveCriticalSection((CBaseFT *)v3);
    goto LABEL_12;
  }
  *((_BYTE *)this + 800) = 1;
  if ( v7 >= 0 )
    v7 = v8 == 0 ? 0x80004005 : 0;
  *((_DWORD *)v3 + 207) = v7;
  CBaseFT::SubRelease((CBaseFT *)v3);
  CoTaskMemFree(pv);
  CBaseFT::LeaveCriticalSection((CBaseFT *)v3);
  return *((unsigned int *)this + 201);
}

```

## disassembly

```asm
0x1804e7d30  mov     [rsp-8+arg_18], rbx
0x1804e7d35  push    rbp
0x1804e7d36  push    rsi
0x1804e7d37  push    rdi
0x1804e7d38  push    r12
0x1804e7d3a  push    r13
0x1804e7d3c  push    r14
0x1804e7d3e  push    r15
0x1804e7d40  lea     rbp, [rsp-27h]
0x1804e7d45  sub     rsp, 0E0h
0x1804e7d4c  mov     rax, cs:__security_cookie
0x1804e7d53  xor     rax, rsp
0x1804e7d56  mov     [rbp+57h+var_40], rax
0x1804e7d5a  xor     r15d, r15d
0x1804e7d5d  mov     [rbp+57h+ppURI], r8
0x1804e7d61  lea     rsi, [rcx-18h]
0x1804e7d65  mov     [rbp+57h+var_C8], r15d
0x1804e7d69  mov     rbx, rcx
0x1804e7d6c  mov     [rbp+57h+pv], r15
0x1804e7d70  mov     rcx, [rsi+1C8h]; struct MIMEINFO *
0x1804e7d77  xorps   xmm0, xmm0
0x1804e7d7a  mov     r12, r8
0x1804e7d7d  mov     edi, edx
0x1804e7d7f  mov     r13b, r15b
0x1804e7d82  movups  [rbp+57h+var_50], xmm0
0x1804e7d86  test    rcx, rcx
0x1804e7d89  jnz     loc_1804E81A3
0x1804e7d8f  lea     eax, [rdx+7FF3FFFBh]
0x1804e7d95  cmp     eax, 13h
0x1804e7d98  ja      loc_1804E807E
0x1804e7d9e  mov     ecx, 90101h
0x1804e7da3  mov     [rsp+110h+var_E0], 1
0x1804e7dab  bt      ecx, eax
0x1804e7dae  jnb     loc_1804E807E
0x1804e7db4  cmp     edx, 800C001Ah
0x1804e7dba  jz      loc_1804E8245
0x1804e7dc0  cmp     edx, 800C0022h
0x1804e7dc6  jz      loc_1804E82E7
0x1804e7dcc  cmp     edx, 800C0020h
0x1804e7dd2  jz      loc_1804E8356
0x1804e7dd8  test    byte ptr [rbx+9Ch], 1
0x1804e7ddf  jnz     loc_1804E816A
0x1804e7de5  mov     rcx, [rbx+110h]; this
0x1804e7dec  test    rcx, rcx
0x1804e7def  jnz     loc_1804E8088
0x1804e7df5  mov     r15d, [rsp+110h+var_E0]
0x1804e7dfa  test    r15d, r15d
0x1804e7dfd  jnz     loc_1804E8585
0x1804e7e03  mov     byte ptr [rbx+31Fh], 1
0x1804e7e0a  lock inc dword ptr [rsi+14h]
0x1804e7e0e  mov     byte ptr [rbx+309h], 1
0x1804e7e15  test    edi, edi
0x1804e7e17  jns     loc_1804E7FC5
0x1804e7e1d  cmp     cs:?g_EnableSyncAsyncErrorHandling@@3HA, 0; int g_EnableSyncAsyncErrorHandling
0x1804e7e24  jnz     loc_1804E7EB9
0x1804e7e2a  test    edi, edi
0x1804e7e2c  jnz     loc_1804E876F
0x1804e7e32  cmp     [rbx+307h], dil
0x1804e7e39  jnz     loc_1804E87C9
0x1804e7e3f  cmp     [rbx+30Eh], dil
0x1804e7e46  jz      loc_1804E87FC
0x1804e7e4c  lea     rcx, ?g_csDwnBindPend@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1804e7e53  call    cs:__imp_EnterCriticalSection
0x1804e7e59  cmp     [rbx+306h], dil
0x1804e7e60  jnz     short loc_1804E7E69
0x1804e7e62  mov     [rbx+305h], dil
0x1804e7e69  lea     rcx, ?g_csDwnBindPend@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1804e7e70  call    cs:__imp_LeaveCriticalSection
0x1804e7e76  mov     rcx, rsi; this
0x1804e7e79  call    ?SignalData@CDwnBindData@@AEAAXXZ; CDwnBindData::SignalData(void)
0x1804e7e7e  mov     rcx, rsi; this
0x1804e7e81  call    ?SubRelease@CBaseFT@@QEAAKXZ; CBaseFT::SubRelease(void)
0x1804e7e86  mov     rcx, [rbp+57h+pv]; pv
0x1804e7e8a  call    cs:__imp_CoTaskMemFree
0x1804e7e90  xor     eax, eax
0x1804e7e92  mov     rcx, [rbp+57h+var_40]
0x1804e7e96  xor     rcx, rsp; StackCookie
0x1804e7e99  call    __security_check_cookie
0x1804e7e9e  mov     rbx, [rsp+110h+arg_18]
0x1804e7ea6  add     rsp, 0E0h
0x1804e7ead  pop     r15
0x1804e7eaf  pop     r14
0x1804e7eb1  pop     r13
0x1804e7eb3  pop     r12
0x1804e7eb5  pop     rdi
0x1804e7eb6  pop     rsi
0x1804e7eb7  pop     rbp
0x1804e7eb8  retn
0x1804e7eb9  mov     rcx, [rbx+360h]
0x1804e7ec0  lea     rdx, [rsp+110h+var_E0]
0x1804e7ec5  mov     [rsp+110h+var_E0], 0
0x1804e7ecd  mov     rax, [rcx]
0x1804e7ed0  mov     rax, [rax+0C0h]
0x1804e7ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e7edc  test    eax, eax
0x1804e7ede  jz      loc_1804E8161
0x1804e7ee4  xor     ecx, ecx
0x1804e7ee6  mov     [rsp+110h+var_E0], ecx
0x1804e7eea  lea     eax, [rcx-0Fh]
0x1804e7eed  cmp     eax, 2
0x1804e7ef0  jbe     loc_1804E8198
0x1804e7ef6  cmp     ecx, 9
0x1804e7ef9  jz      loc_1804E8198
0x1804e7eff  mov     rcx, [rbx+360h]
0x1804e7f06  lea     rdx, [rsp+110h+String1]
0x1804e7f0b  mov     [rsp+110h+String1], 0
0x1804e7f14  mov     rax, [rcx]
0x1804e7f17  mov     rax, [rax+98h]
0x1804e7f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e7f23  test    eax, eax
0x1804e7f25  jnz     loc_1804E8187
0x1804e7f2b  mov     rcx, [rsp+110h+String1]; String1
0x1804e7f30  lea     r8d, [rax+5]; MaxCount
0x1804e7f34  lea     rdx, aMhtml; "mhtml"
0x1804e7f3b  call    cs:__imp__wcsnicmp
0x1804e7f41  xor     r14d, r14d
0x1804e7f44  test    eax, eax
0x1804e7f46  setz    r14b
0x1804e7f4a  mov     rcx, [rsp+110h+String1]; bstrString
0x1804e7f4f  call    cs:__imp_SysFreeString
0x1804e7f55  cmp     byte ptr [rbx+30Ch], 1
0x1804e7f5c  jnz     loc_1804E8725
0x1804e7f62  xor     r14d, r14d
0x1804e7f65  mov     rcx, rsi; this
0x1804e7f68  call    ?EnterCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::EnterCriticalSection(void)
0x1804e7f6d  cmp     byte ptr [rbx+31Eh], 0
0x1804e7f74  jnz     loc_1804E8154
0x1804e7f7a  test    edi, edi
0x1804e7f7c  jns     loc_1804E874F
0x1804e7f82  test    r15d, r15d
0x1804e7f85  jnz     loc_1804E8154
0x1804e7f8b  mov     byte ptr [rbx+320h], 1
0x1804e7f92  test    edi, edi
0x1804e7f94  jns     loc_1804E875D
0x1804e7f9a  mov     rcx, rsi; this
0x1804e7f9d  mov     [rsi+33Ch], edi
0x1804e7fa3  call    ?SubRelease@CBaseFT@@QEAAKXZ; CBaseFT::SubRelease(void)
0x1804e7fa8  mov     rcx, [rbp+57h+pv]; pv
0x1804e7fac  call    cs:__imp_CoTaskMemFree
0x1804e7fb2  mov     rcx, rsi; this
0x1804e7fb5  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x1804e7fba  mov     eax, [rbx+324h]
0x1804e7fc0  jmp     loc_1804E7E92
0x1804e7fc5  cmp     cs:?g_fDisableUnTrustedProtocol@@3HA, 0; int g_fDisableUnTrustedProtocol
0x1804e7fcc  jz      loc_1804E7E1D
0x1804e7fd2  mov     rcx, [rbx+38h]
0x1804e7fd6  add     rcx, 320h; this
0x1804e7fdd  cmp     qword ptr [rcx], 0
0x1804e7fe1  jz      loc_1804E7E1D
0x1804e7fe7  call    ?Length@CStr@@QEBAIXZ; CStr::Length(void)
0x1804e7fec  test    eax, eax
0x1804e7fee  jz      loc_1804E7E1D
0x1804e7ff4  mov     r14, [rbx+360h]
0x1804e7ffb  mov     rcx, r14; struct IUri *
0x1804e7ffe  call    ?IsDangerousProtocol@@YAHPEAUIUri@@@Z; IsDangerousProtocol(IUri *)
0x1804e8003  test    eax, eax
0x1804e8005  jz      loc_1804E7E1D
0x1804e800b  mov     rcx, r14; struct IUri *
0x1804e800e  call    ?IsDangerousChmMime@@YAHPEAUIUri@@@Z; IsDangerousChmMime(IUri *)
0x1804e8013  test    eax, eax
0x1804e8015  jz      loc_1804E7E1D
0x1804e801b  mov     dword ptr [rsp+110h+String1], 4
0x1804e8023  mov     r14d, 80004005h
0x1804e8029  call    ?AddRefSharedSecurityManager@@YAXXZ; AddRefSharedSecurityManager(void)
0x1804e802e  mov     rcx, cs:?s_pISM@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * s_pISM
0x1804e8035  test    rcx, rcx
0x1804e8038  jz      short loc_1804E805C
0x1804e803a  mov     rax, [rcx]
0x1804e803d  lea     r8, [rsp+110h+String1]
0x1804e8042  mov     rdx, [rbx+38h]
0x1804e8046  xor     r9d, r9d
0x1804e8049  mov     rax, [rax+28h]
0x1804e804d  mov     rdx, [rdx+320h]
0x1804e8054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e8059  mov     r14d, eax
0x1804e805c  call    ?DecrementSharedSecurityManager@@YAXXZ; DecrementSharedSecurityManager(void)
0x1804e8061  test    r14d, r14d
0x1804e8064  js      short loc_1804E8074
0x1804e8066  test    dword ptr [rsp+110h+String1], 0FFFFFFFDh
0x1804e806e  jz      loc_1804E7E1D
0x1804e8074  mov     edi, 80070005h
0x1804e8079  jmp     loc_1804E7E1D
0x1804e807e  mov     [rsp+110h+var_E0], r15d
0x1804e8083  jmp     loc_1804E7DB4
0x1804e8088  mov     rax, [rcx]
0x1804e808b  lea     r9, [rbp+57h+pv]
0x1804e808f  lea     r8, [rbp+57h+var_C8]
0x1804e8093  mov     qword ptr [rsp+110h+var_F0], r15
0x1804e8098  lea     rdx, [rbp+57h+var_50]
0x1804e809c  mov     rax, [rax+40h]
0x1804e80a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e80a5  mov     ecx, [rbp+57h+var_C8]
0x1804e80a8  test    ecx, ecx
0x1804e80aa  jns     loc_1804E8237
0x1804e80b0  cmp     edi, 800C0006h
0x1804e80b6  jnz     loc_1804E7DF5
0x1804e80bc  mov     eax, ecx
0x1804e80be  and     eax, 1FFF0000h
0x1804e80c3  cmp     eax, 70000h
0x1804e80c8  jnz     short loc_1804E80CD
0x1804e80ca  movzx   ecx, cx
0x1804e80cd  lea     eax, [rcx-2EEDh]
0x1804e80d3  cmp     eax, 2
0x1804e80d6  ja      loc_1804E7DF5
0x1804e80dc  mov     rax, [rbx+38h]
0x1804e80e0  mov     r14, [rax+70h]
0x1804e80e4  test    r14, r14
0x1804e80e7  jz      loc_1804E7DF5
0x1804e80ed  lea     rdx, [rbp+57h+ppURI]; struct IUri **
0x1804e80f1  mov     [rbp+57h+ppURI], r15
0x1804e80f5  mov     rcx, r14; struct CMarkup *
0x1804e80f8  call    ?GetUri@CMarkup@@SAJQEBV1@PEAPEAUIUri@@@Z; CMarkup::GetUri(CMarkup const * const,IUri * *)
0x1804e80fd  test    eax, eax
0x1804e80ff  js      loc_1804E7DF5
0x1804e8105  mov     rcx, [rbp+57h+ppURI]
0x1804e8109  lea     rdx, [rsp+110h+String1]
0x1804e810e  mov     dword ptr [rsp+110h+String1], r15d
0x1804e8113  mov     rax, [rcx]
0x1804e8116  mov     rax, [rax+0C0h]
0x1804e811d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e8122  test    eax, eax
0x1804e8124  js      short loc_1804E813F
0x1804e8126  cmp     dword ptr [rsp+110h+String1], 1
0x1804e812b  jnz     short loc_1804E813F
0x1804e812d  or      byte ptr [r14+62h], 40h
0x1804e8132  mov     edi, 800C0018h
0x1804e8137  mov     [rsp+110h+var_E0], 1
0x1804e813f  mov     rcx, [rbp+57h+ppURI]
0x1804e8143  mov     rax, [rcx]
0x1804e8146  mov     rax, [rax+10h]
0x1804e814a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e814f  jmp     loc_1804E7DF5
0x1804e8154  mov     rcx, rsi; this
0x1804e8157  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x1804e815c  jmp     loc_1804E7E2A
0x1804e8161  mov     ecx, [rsp+110h+var_E0]
0x1804e8165  jmp     loc_1804E7EEA
0x1804e816a  mov     rax, [rbx+38h]
0x1804e816e  mov     rcx, [rax+70h]; this
0x1804e8172  test    rcx, rcx
0x1804e8175  jz      loc_1804E7DE5
0x1804e817b  mov     dl, 1; bool
0x1804e817d  call    ?UpdateSameSiteCookieState@CMarkup@@QEAAX_N@Z; CMarkup::UpdateSameSiteCookieState(bool)
0x1804e8182  jmp     loc_1804E7DE5
0x1804e8187  xor     r14d, r14d
0x1804e818a  cmp     eax, 1
0x1804e818d  jnz     loc_1804E7F55
0x1804e8193  jmp     loc_1804E7F4A
0x1804e8198  mov     r14d, 1
0x1804e819e  jmp     loc_1804E7F55
0x1804e81a3  call    ?IsMimeTypeOldXML@@YA_NPEBUMIMEINFO@@@Z; IsMimeTypeOldXML(MIMEINFO const *)
0x1804e81a8  test    al, al
0x1804e81aa  jz      loc_1804E7D8F
0x1804e81b0  mov     rcx, [rbx+38h]
0x1804e81b4  mov     rax, [rcx+70h]
0x1804e81b8  test    rax, rax
0x1804e81bb  jz      loc_1804E7D8F
0x1804e81c1  cmp     [rax+2FCh], r15d
0x1804e81c8  jnz     loc_1804E7D8F
0x1804e81ce  mov     byte ptr [rcx+2DBh], 1
0x1804e81d5  jmp     loc_1804E7D8F
0x1804e81da  mov     rax, [rcx+160h]
0x1804e81e1  test    rax, rax
0x1804e81e4  jz      loc_1804E7DD8
0x1804e81ea  mov     r10, [rax+78h]
0x1804e81ee  test    r10, r10
0x1804e81f1  jz      loc_1804E7DD8
0x1804e81f7  call    ?GetGwnd@@YAPEAVGWND@@XZ; GetGwnd(void)
0x1804e81fc  lea     rcx, ?ReleasePostedIUri@CDoc@@SAX_K@Z; CDoc::ReleasePostedIUri(unsigned __int64)
0x1804e8203  mov     r9, r14
0x1804e8206  mov     [rsp+110h+var_E8], rcx; __int64
0x1804e820b  lea     r8, ?NavigateToNeedEdgeErrorPageCallback@CWindow@@QEAAX_K@Z; CWindow::NavigateToNeedEdgeErrorPageCallback(unsigned __int64)
0x1804e8212  mov     rcx, rax; struct GWND *
0x1804e8215  mov     [rsp+110h+var_F0], r15d; int
0x1804e821a  mov     rdx, r10
0x1804e821d  call    ?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z; _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))
0x1804e8222  test    eax, eax
0x1804e8224  jns     loc_1804E83BB
0x1804e822a  mov     rcx, r14; unsigned __int64
0x1804e822d  call    ?ReleasePostedIUri@CDoc@@SAX_K@Z; CDoc::ReleasePostedIUri(unsigned __int64)
0x1804e8232  jmp     loc_1804E7DD8
0x1804e8237  jg      loc_1804E8577
0x1804e823d  mov     [rbp+57h+var_C8], ecx
0x1804e8240  jmp     loc_1804E80B0
0x1804e8245  mov     rax, [rbx+38h]
0x1804e8249  mov     r14, [rax+68h]
0x1804e824d  test    r14, r14
0x1804e8250  jz      short loc_1804E8285
0x1804e8252  test    byte ptr [r14+1304h], 80h
0x1804e825a  jz      short loc_1804E8285
0x1804e825c  mov     r9d, [r14+13B8h]
0x1804e8263  mov     r8d, [r14+13BCh]
0x1804e826a  mov     edx, [r14+13B4h]
0x1804e8271  mov     ecx, [r14+13B0h]
0x1804e8278  call    ??$IsWebPlatformHostBehaviorSupported@$05@@YA_NW4WebPlatformHostType@@KKK@Z; IsWebPlatformHostBehaviorSupported<6>(WebPlatformHostType,ulong,ulong,ulong)
0x1804e827d  test    al, al
0x1804e827f  jz      loc_1804E7DD8
0x1804e8285  mov     rdx, [rbx+1E8h]
0x1804e828c  test    rdx, rdx
0x1804e828f  jnz     short loc_1804E8298
  ... truncated ...
```
