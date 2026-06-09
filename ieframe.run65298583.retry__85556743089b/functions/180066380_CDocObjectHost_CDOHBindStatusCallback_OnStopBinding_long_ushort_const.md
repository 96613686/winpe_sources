# CDocObjectHost::CDOHBindStatusCallback::OnStopBinding(long,ushort const *)

- ea: `0x180066380`
- end: `0x1800678c6`
- name: `?OnStopBinding@CDOHBindStatusCallback@CDocObjectHost@@MEAAJJPEBG@Z`
- size: `5446`
- prototype: `__int64 __fastcall(CDocObjectHost::CDOHBindStatusCallback *__hidden this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `52`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180144cd0`

## callees

- `0x18000b9e0`
- `0x18000c530`
- `0x18000f3d0`
- `0x180011230`
- `0x180012140`
- `0x18004b560`
- `0x1800567e4`
- `0x180064c38`
- `0x180066380`
- `0x18006ac58`
- `0x180078828`
- `0x18007921c`
- `0x18008e2ac`
- `0x18008e2e4`
- `0x180091450`
- `0x180095554`
- `0x1800c99cc`
- `0x1800f63cc`
- `0x1800f6ba8`
- `0x1800f754c`
- `0x1800f8af0`
- `0x1800f8c34`
- `0x1800f8cf0`
- `0x1800f8f34`
- `0x1800f9600`
- `0x1800f9670`
- `0x1800f9e1c`
- `0x1800f9f1c`
- `0x1800fb00c`
- `0x1800fb238`
- `0x1800fbba4`
- `0x1801129dc`
- `0x180136ee8`
- `0x180137230`
- `0x1801381fc`
- `0x18013a590`
- `0x18013a764`
- `0x18013d35c`
- `0x18013d7bc`
- `0x18013e99c`
- `0x18014353c`
- `0x180145eb0`
- `0x1801d8538`
- `0x1801de7dc`
- `0x18026ad50`
- `0x1803f00f0`
- `0x1804f2710`
- `0x180516fb0`
- `0x18054e27a`
- `0x18054e310`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800678b0`
- `KERNEL32!GlobalFree` at `0x1800678b0`
- `KERNEL32!LocalFree` at `0x180066698`
- `KERNEL32!LocalFree` at `0x180067899`
- `KERNEL32!LocalFree` at `0x180066698`
- `KERNEL32!LocalFree` at `0x180067899`
- `KERNEL32!FreeLibrary` at `0x18006768c`
- `KERNEL32!FreeLibrary` at `0x18006768c`
- `KERNEL32!LoadLibraryExW` at `0x180067657`
- `KERNEL32!LoadLibraryExW` at `0x180067657`
- `KERNEL32!GetProcAddress` at `0x18006766f`
- `KERNEL32!GetProcAddress` at `0x18006766f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x18006700f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x18006700f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180067288`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrChrW` at `0x180067288`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrW` at `0x18006729e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrStrW` at `0x18006729e`
- `USER32!InvalidateRect` at `0x180066d16`
- `USER32!InvalidateRect` at `0x180066d16`
- `OLEAUT32!__imp_SysAllocString` at `0x18006682f`
- `OLEAUT32!__imp_SysAllocString` at `0x180066a0d`
- `OLEAUT32!__imp_SysAllocString` at `0x18006682f`
- `OLEAUT32!__imp_SysAllocString` at `0x180066a0d`
- `OLEAUT32!__imp_SysFreeString` at `0x180066853`
- `OLEAUT32!__imp_SysFreeString` at `0x1800669c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a31`
- `OLEAUT32!__imp_SysFreeString` at `0x180067737`
- `OLEAUT32!__imp_SysFreeString` at `0x180067740`
- `OLEAUT32!__imp_SysFreeString` at `0x180067749`
- `OLEAUT32!__imp_SysFreeString` at `0x180066853`
- `OLEAUT32!__imp_SysFreeString` at `0x1800669c6`
- `OLEAUT32!__imp_SysFreeString` at `0x180066a31`
- `OLEAUT32!__imp_SysFreeString` at `0x180067737`
- `OLEAUT32!__imp_SysFreeString` at `0x180067740`
- `OLEAUT32!__imp_SysFreeString` at `0x180067749`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800666e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800671a5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800666e8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800671a5`
- `SHELL32!__imp_ILFree` at `0x180066ce3`
- `SHELL32!__imp_ILFree` at `0x180066ce3`
- `iertutil!CreateIUriBuilder` at `0x180066c1b`
- `iertutil!CreateIUriBuilder` at `0x180066c1b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180067615`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180067615`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006730b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18006730b`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800673c8`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1800673c8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800665fc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800665fc`
- `urlmon!RevokeBindStatusCallback` at `0x18006655e`
- `urlmon!RevokeBindStatusCallback` at `0x18006655e`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180066fb7`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180066ff4`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180066fb7`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180066ff4`

## string_xrefs

- `0x180067647`: `ntdll.dll`
- `0x1800664ee`: `__PrecreatedObject`

## pseudocode

```c
__int64 __fastcall CDocObjectHost::CDOHBindStatusCallback::OnStopBinding(
        CDocObjectHost::CDOHBindStatusCallback *this,
        signed int a2,
        OLECHAR *a3)
{
  char *v3; // r14
  __int64 v4; // rax
  int v7; // esi
  void (__fastcall *v8)(char *); // rax
  bool v9; // al
  int v10; // edi
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  struct IBinding **v17; // r12
  int (__fastcall ***v18)(_QWORD, GUID *, IUriBuilder **); // rcx
  int v19; // eax
  int v20; // ecx
  struct IBinding *v21; // rcx
  unsigned int v22; // r8d
  int v23; // eax
  unsigned __int16 *v24; // rax
  struct IHTMLWindow2 *v25; // rdx
  unsigned __int16 *v26; // r9
  OLECHAR *v27; // rbx
  __int64 v28; // rcx
  int v29; // esi
  __int128 v30; // xmm0
  CDocObjectHost::CDOHBindStatusCallback *v31; // rcx
  int (__fastcall ***v32)(_QWORD, GUID *, LPVOID *); // rcx
  int v33; // r12d
  unsigned int v34; // r8d
  unsigned __int16 *v35; // rax
  struct IHTMLWindow2 *v36; // rdx
  unsigned __int16 *v37; // r9
  OLECHAR *v38; // rbx
  __int64 v39; // rcx
  unsigned int v40; // edi
  int v41; // esi
  HRESULT IUriBuilder; // ebx
  HWND v43; // rcx
  int v44; // esi
  unsigned int v45; // r8d
  WCHAR *v46; // rbx
  unsigned int v47; // edx
  int v48; // r9d
  int v49; // eax
  int v50; // ebx
  const WCHAR *v51; // rcx
  const WCHAR *ExtensionW; // rax
  __int64 v53; // rcx
  int v54; // esi
  int v55; // r9d
  SAFEARRAY *v56; // rcx
  bool v57; // zf
  const unsigned __int16 *v59; // r8
  const unsigned __int16 *v60; // r8
  int v61; // esi
  const unsigned __int16 *v62; // r8
  int v63; // ebx
  int v64; // eax
  int v65; // r8d
  int (__fastcall ***v66)(_QWORD, GUID *, LPVOID *); // rcx
  int v67; // ebx
  const unsigned __int16 *v68; // r8
  __int64 v69; // rcx
  unsigned int v70; // r12d
  unsigned __int16 v71; // r8
  char IsWin10TelemetryTypeAllowed; // bl
  HMODULE Library; // rax
  HMODULE v74; // rdi
  FARPROC ProcAddress; // rax
  OLECHAR *v76; // rsi
  OLECHAR *v77; // rdi
  OLECHAR *v78; // rbx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  void *v85; // rcx
  void *v86; // rcx
  const unsigned __int16 *v87; // [rsp+30h] [rbp-D0h]
  char v88; // [rsp+60h] [rbp-A0h]
  unsigned int v89; // [rsp+64h] [rbp-9Ch] BYREF
  int v90; // [rsp+68h] [rbp-98h]
  int v91; // [rsp+6Ch] [rbp-94h] BYREF
  int v92; // [rsp+70h] [rbp-90h] BYREF
  int v93; // [rsp+78h] [rbp-88h] BYREF
  int v94; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID pv[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v96; // [rsp+90h] [rbp-70h]
  int v97; // [rsp+A0h] [rbp-60h] BYREF
  int v98; // [rsp+A4h] [rbp-5Ch]
  IUri *pIUri; // [rsp+A8h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp-50h] BYREF
  int v101; // [rsp+B8h] [rbp-48h] BYREF
  int v102; // [rsp+BCh] [rbp-44h]
  int v103; // [rsp+C0h] [rbp-40h] BYREF
  SAFEARRAY *psa; // [rsp+C8h] [rbp-38h] BYREF
  int v105; // [rsp+D0h] [rbp-30h] BYREF
  int v106; // [rsp+D4h] [rbp-2Ch] BYREF
  int v107; // [rsp+D8h] [rbp-28h] BYREF
  OLECHAR *psz; // [rsp+E0h] [rbp-20h]
  IUriBuilder *ppIUriBuilder[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v110[3]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR pszStart[2088]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v112[256]; // [rsp+1180h] [rbp+1080h] BYREF
  unsigned __int16 v113[264]; // [rsp+1280h] [rbp+1180h] BYREF
  unsigned __int16 v114[2088]; // [rsp+1490h] [rbp+1390h] BYREF

  *((_DWORD *)this + 47) &= 0xFFFFDFFD;
  v3 = (char *)this - 1952;
  LODWORD(pIUri) = *((_DWORD *)this + 47);
  v4 = *((_QWORD *)this - 244);
  psz = a3;
  v90 = 1;
  v7 = 1;
  v97 = 1;
  v8 = *(void (__fastcall **)(char *))(v4 + 8);
  v89 = 0;
  v106 = 4;
  v103 = 0;
  v107 = 0;
  v93 = 0;
  psa = 0;
  v8((char *)this - 1952);
  *((_DWORD *)this + 47) &= ~0x100u;
  if ( (*((_DWORD *)v3 + 162) & 0x10000) != 0 && a2 < 0 )
  {
    *((_DWORD *)v3 + 171) = a2;
    goto LABEL_203;
  }
  if ( a2 == -2146697190 )
  {
    v9 = CDocObjectHost::CDOHBindStatusCallback::_HandleVTabSwitch(this, (struct CDocObjectHost *)v3, 0);
    v10 = v9;
    a2 = !v9 ? 0x80004004 : 0;
  }
  else
  {
    v10 = 0;
    if ( a2 == -2146697182
      && (int)CDocObjectHost::CDOHBindStatusCallback::_HandleDualEngineSwitch(this, (struct CDocObjectHost *)v3) >= 0 )
    {
      a2 = 0;
      v10 = 1;
    }
  }
  CPrivacyQueue::Reset((CDocObjectHost::CDOHBindStatusCallback *)((char *)this + 248));
  CDocObjectHost::CDOHBindStatusCallback::ResetPrivacyInfo(this);
  if ( a2 == -2147467260 && (*((_BYTE *)this + 188) & 0x20) != 0 )
    *((_DWORD *)v3 + 162) |= 0x80000000;
  v11 = *((_DWORD *)this + 47);
  v98 = v11;
  if ( (v11 & 0x10) != 0 && a2 == -2147467260 )
    a2 = 0;
  v12 = *((_QWORD *)this + 8);
  *((_DWORD *)this + 24) = 0;
  if ( v12 && *((_QWORD *)v3 + 113) )
  {
    (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v12 + 96LL))(v12, L"__PrecreatedObject");
    v11 = v98;
  }
  if ( *((_QWORD *)this + 8) )
  {
    v13 = *((_QWORD *)v3 + 50);
    v14 = 0;
    v88 = 0;
    v101 = 0;
    v102 = 0;
    v98 = -__CFSHR__(v11, 4);
    if ( v13 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 112LL))(v13, 0);
    v15 = *((_QWORD *)v3 + 48);
    if ( v15 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 64LL))(v15, 0);
    RevokeBindStatusCallback(*((LPBC *)this + 8), (IBindStatusCallback *)this);
    (*(void (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 8) + 96LL))(
      *((_QWORD *)this + 8),
      L"{d4db6850-5385-11d0-89e9-00a0c90a90ac}");
    if ( (*((_BYTE *)this + 188) & 0x20) != 0 )
      CDocObjectHost::_HandlePageActionBlocked((CDocObjectHost *)v3, 0, 0);
    v91 = a2;
    if ( (unsigned int)(a2 + 2146697214) <= 0x506 )
    {
      v16 = *((_QWORD *)this + 7);
      if ( v16 )
      {
        pv[0] = 0;
        *(_OWORD *)ppIUriBuilder = 0;
        if ( (*(int (__fastcall **)(__int64, IUriBuilder **, int *, LPVOID *, _QWORD))(*(_QWORD *)v16 + 64LL))(
               v16,
               ppIUriBuilder,
               &v91,
               pv,
               0) >= 0 )
        {
          if ( v91 >= 1 )
            v91 = (unsigned __int16)v91 | 0x80070000;
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
        }
      }
    }
    v17 = (struct IBinding **)((char *)this + 56);
    v18 = (int (__fastcall ***)(_QWORD, GUID *, IUriBuilder **))*((_QWORD *)this + 7);
    if ( !v18 )
    {
LABEL_68:
      v28 = *((_QWORD *)this + 11);
      v29 = 0;
      if ( v28 )
      {
        *((_QWORD *)this + 11) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v30 = *(_OWORD *)(v3 + 760);
      if ( *((char *)this + 188) < 0 )
        a2 = -2147221018;
      v92 = a2;
      *(_OWORD *)pv = v30;
      if ( !memcmp_0(qword_1805C6C18, pv, 0x10u) )
      {
        v32 = (int (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)v3 + 108);
        bstrString = 0;
        ppIUriBuilder[0] = 0;
        pv[0] = 0;
        if ( v32 )
        {
          if ( (**v32)(v32, &GUID_a158a630_ed6f_45fb_b987_f68676f57752, pv) >= 0
            && !(*(unsigned int (__fastcall **)(LPVOID, IUriBuilder **))(*(_QWORD *)pv[0] + 24LL))(pv[0], ppIUriBuilder) )
          {
            ((void (__fastcall *)(IUriBuilder *, BSTR *))ppIUriBuilder[0]->lpVtbl->SetPassword)(
              ppIUriBuilder[0],
              &bstrString);
          }
          BrowserTelemetry::AdobeAcroPDFLoaded<long &,unsigned short * &>(&v92, &bstrString);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pv);
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(ppIUriBuilder);
        SysFreeString(bstrString);
      }
      if ( a2 >= 0 )
      {
        if ( v10 )
        {
          v67 = 1;
        }
        else
        {
          v67 = 0;
          if ( !*((_QWORD *)v3 + 110) && (v3[640] & 8) == 0 )
            CDocObjectHost::_CancelPendingNavigation((CDocObjectHost *)v3, 0, 0, 0, 0, 0);
        }
        if ( ((v89 - 502) & 0xFFFFFFFD) == 0 )
        {
          if ( v93 )
          {
            if ( (v3[640] & 8) == 0 )
              CDocObjectHost::_CancelPendingNavigation((CDocObjectHost *)v3, 0, 0, 0, 0, 0);
          }
          else if ( !(unsigned int)CDocObjectHost::CDOHBindStatusCallback::_HandleFailedNavigationSearch(
                                     this,
                                     &v97,
                                     v89,
                                     (struct CDocObjectHost *)v3,
                                     v91,
                                     0,
                                     v87,
                                     *v17,
                                     0) )
          {
            v67 = 1;
          }
        }
        if ( !v67 && (*((_DWORD *)v3 + 162) & 0x100000) == 0 )
        {
          CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(v31, (struct CDocObjectHost *)v3, 0, 0, 0, 0);
          if ( (*((_BYTE *)this + 188) & 0x20) == 0 )
          {
            if ( *((_QWORD *)v3 + 108) )
            {
              CDocObjectHost::_GetCurrentPage((CDocObjectHost *)v3, pszStart, 0x825u, 0);
              v68 = (const unsigned __int16 *)*((_QWORD *)v3 + 77);
              if ( v68 )
                StringCchCatW(pszStart, 0x825u, v68);
              if ( !v98 )
              {
                v69 = *((_QWORD *)v3 + 115);
                v70 = 1;
                if ( v69 )
                {
                  pv[0] = (LPVOID)21;
                  (*(void (__fastcall **)(__int64, const GUID *, __int64, LPVOID *, _QWORD))(*(_QWORD *)v69 + 24LL))(
                    v69,
                    &CGID_Explorer,
                    1,
                    pv,
                    0);
                  v70 = (BYTE4(pv[0]) >> 1) & 1;
                }
                if ( !OnlineHistorySettings::IsDataStreamFeatureEnabled() || LCIEIsCurrentProcessInPrivate() )
                  goto LABEL_276;
                if ( `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::AlreadyChecked )
                {
                  IsWin10TelemetryTypeAllowed = `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::IsOptedIn;
                }
                else
                {
                  if ( IsWindowsVersionOrGreater(0xAu, 0, v71) )
                  {
                    IsWin10TelemetryTypeAllowed = TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed();
                  }
                  else
                  {
                    IsWin10TelemetryTypeAllowed = 0;
                    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
                    v74 = Library;
                    if ( Library )
                    {
                      ProcAddress = GetProcAddress(Library, "WinSqmIsOptedInEx");
                      if ( ProcAddress )
                        IsWin10TelemetryTypeAllowed = ((unsigned int (__fastcall *)(__int64))ProcAddress)(4) == 1;
                      FreeLibrary(v74);
                    }
                  }
                  `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed;
                  `TelemetryPermissionsDownlevel::IsOptedIntoGeneral'::`2'::AlreadyChecked = 1;
                }
                if ( IsWin10TelemetryTypeAllowed )
                {
                  bstrString = 0;
                  ppIUriBuilder[0] = 0;
                  pv[0] = 0;
                  memset(v110, 0, sizeof(v110));
                  CDocObjectHost::_PopulateOnlineHistoryData(
                    (CDocObjectHost *)v3,
                    (struct _ONLINEHISTORYADDFIELDS *)v110,
                    &bstrString,
                    (unsigned __int16 **)ppIUriBuilder,
                    (unsigned __int16 **)pv);
                  v76 = (OLECHAR *)pv[0];
                  v77 = (OLECHAR *)ppIUriBuilder[0];
                  v78 = bstrString;
                  AddToHistory(
                    pszStart,
                    0,
                    0,
                    0,
                    0,
                    v70,
                    0,
                    (struct _ONLINEHISTORYADDFIELDS *)v110,
                    (__int64)bstrString,
                    (__int64)ppIUriBuilder[0],
                    (__int64)pv[0]);
                  SysFreeString(v78);
                  SysFreeString(v77);
                  SysFreeString(v76);
                }
                else
                {
LABEL_276:
                  AddToHistory(pszStart, 0, 0, 0, 0, v70, 0, 0, 0, 0, 0);
                }
              }
            }
          }
        }
        goto LABEL_277;
      }
      *((_DWORD *)v3 + 160) |= 4u;
      v33 = 0;
      pszStart[0] = 0;
      if ( !v14 )
      {
        v34 = v89;
        if ( !v89 )
        {
          if ( (unsigned int)(a2 + 2146697214) > 0x506 )
            goto LABEL_89;
          if ( a2 == -2146697189 )
          {
            v35 = SysAllocString(psz);
            v38 = v35;
            if ( v35 )
              CDocObjectHost::_FireRedirectXDomainBlockedHelper((CDocObjectHost *)v3, v36, 0x800C001B, v37, v35);
            SysFreeString(v38);
          }
          v34 = a2;
        }
        CDocObjectHost::_FireNavigateErrorHelper((CDocObjectHost *)v3, 0, v34, &v93, 0);
      }
LABEL_89:
      if ( *((_QWORD *)v3 + 108) )
        CDocObjectHost::_GetCurrentPage((CDocObjectHost *)v3, pszStart, 0x825u, 0);
      CDocObjectHost::_OnSetProgressPos((CDocObjectHost *)v3, 0, 0);
      v40 = 2;
      if ( a2 <= -2146697208 )
      {
        if ( a2 == -2146697208 )
          goto LABEL_104;
        if ( a2 != -2147467262 )
        {
          if ( a2 != -2147467260 )
          {
            if ( a2 != -2147221164 && a2 != -2147221018 )
            {
              if ( a2 != -2147023673 )
              {
                switch ( a2 )
                {
                  case -2146697211:
                    goto LABEL_101;
                  case -2146697210:
                    goto LABEL_104;
                  case -2146697209:
LABEL_101:
                    v33 = 1;
                    if ( v93 )
                    {
                      if ( (v3[640] & 8) == 0 )
                        CDocObjectHost::_CancelPendingNavigation((CDocObjectHost *)v3, 0, 0, 0, 0, 0);
                    }
                    else
                    {
                      if ( !(unsigned int)CDocObjectHost::CDOHBindStatusCallback::_HandleFailedNavigationSearch(
                                            this,
                                            &v97,
                                            v89,
                                            (struct CDocObjectHost *)v3,
                                            v91,
                                            pszStart,
                                            v87,
                                            *((struct IBinding **)this + 7),
                                            0) )
                      {
                        v41 = v97;
LABEL_105:
                        v39 = (unsigned int)v91;
                        if ( (v91 & 0x1FFF0000) == 0x70000 )
                          v39 = (unsigned __int16)v91;
                        if ( (unsigned int)(v39 - 12013) <= 2 )
                        {
                          pIUri = 0;
                          if ( CDocObjectHost::CDOHBindStatusCallback::_GetUri(this, &pIUri) >= 0 )
                          {
                            v92 = 0;
                            if ( !((unsigned int (__fastcall *)(IUri *, int *))pIUri->lpVtbl->GetScheme)(pIUri, &v92)
                              && v92 == 1
                              && v3
                              && (unsigned int)CDocObjectHost::CDOHBindStatusCallback::GetFTPCredentials(
                                                 pIUri,
                                                 *((HWND *)v3 + 16),
                                                 1) )
                            {
                              v94 = 0;
                              if ( ((int (__fastcall *)(IUri *, __int64, int *))pIUri->lpVtbl->HasProperty)(
                                     pIUri,
                                     13,
                                     &v94) < 0
                                || !v94 )
                              {
                                goto LABEL_121;
                              }
                              ppIUriBuilder[0] = 0;
                              IUriBuilder = CreateIUriBuilder(pIUri, 0, 0, ppIUriBuilder);
                              if ( IUriBuilder >= 0 )
                              {
                                IUriBuilder = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD))ppIUriBuilder[0]->lpVtbl->SetUserName)(
                                                ppIUriBuilder[0],
                                                0);
                                if ( IUriBuilder >= 0 )
                                {
                                  ((void (__fastcall *)(IUriBuilder *, _QWORD))ppIUriBuilder[0]->lpVtbl->SetPassword)(
                                    ppIUriBuilder[0],
                                    0);
                                  pv[0] = 0;
                                  IUriBuilder = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, LPVOID *))ppIUriBuilder[0]->lpVtbl->CreateUriSimple)(
                                                  ppIUriBuilder[0],
                                                  0,
                                                  0,
                                                  pv);
                                  if ( IUriBuilder >= 0 )
                                    ATL::AtlComPtrAssign((struct IUnknown **)&pIUri, (struct IUnknown *)pv[0]);
                                  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pv);
                                }
                              }
                              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(ppIUriBuilder);
                              if ( IUriBuilder >= 0 )
                              {
LABEL_121:
                                pv[0] = 0;
                                if ( (int)IECreateFromIUri(0, pIUri, pv) >= 0 )
                                {
                                  (*(void (__fastcall **)(_QWORD, LPVOID, __int64))(**((_QWORD **)v3 + 48) + 88LL))(
                                    *((_QWORD *)v3 + 48),
                                    pv[0],
                                    1);
                                  ILFree((LPITEMIDLIST)pv[0]);
                                  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pIUri);
LABEL_123:
                                  CDocObjectHost::CDOHBindStatusCallback::_MarkAsErrorPage(
                                    (CDocObjectHost::CDOHBindStatusCallback *)v39,
                                    (struct CDocObjectHost *)v3);
LABEL_124:
                                  *((_DWORD *)v3 + 160) |= 4u;
                                  v43 = (HWND)*((_QWORD *)v3 + 16);
                                  if ( v43 )
                                    InvalidateRect(v43, 0, 1);
                                  if ( (v3[640] & 8) == 0 )
                                  {
                                    if ( v107 )
                                      CDocObjectHost::_CancelPendingNavigation((CDocObjectHost *)v3, 0, 0, 0, 0, 1);
                                    else
                                      CDocObjectHost::_CancelPendingNavigation(
                                        (CDocObjectHost *)v3,
                                        v103,
                                        0,
                                        -__CFSHR__(*((_DWORD *)v3 + 162), 25),
                                        0,
                                        0);
                                    if ( (*((_DWORD *)v3 + 162) & 0x1000000) != 0 )
                                    {
                                      v66 = (int (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)v3 + 50);
                                      if ( v66 )
                                      {
                                        pv[0] = 0;
                                        if ( (**v66)(v66, &GUID_131a6950_7f78_11d0_a979_00c04fd705a2, pv) >= 0 )
                                        {
                                          (*(void (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)pv[0] + 24LL))(
                                            pv[0],
                                            0,
                                            4);
                                          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
                                        }
                                      }
                                    }
                                  }
LABEL_277:
                                  v79 = *((_QWORD *)this + 8);
                                  if ( v79 )
                                  {
                                    *((_QWORD *)this + 8) = 0;
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
                                  }
                                  v80 = *((_QWORD *)this + 9);
                                  if ( v80 )
                                    (*(void (__fastcall **)(__int64, _QWORD, OLECHAR *))(*(_QWORD *)v80 + 56LL))(
                                      v80,
                                      (unsigned int)a2,
                                      psz);
                                  v81 = *((_QWORD *)this + 9);
                                  if ( v81 )
                                  {
                                    *((_QWORD *)this + 9) = 0;
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                                  }
                                  v82 = *((_QWORD *)this + 10);
                                  if ( v82 )
                                  {
                                    *((_QWORD *)this + 10) = 0;
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
                                  }
                                  (*(void (__fastcall **)(char *, const WCHAR *, _QWORD))(*(_QWORD *)v3 + 152LL))(
                                    v3,
                                    &SrcStr,
                                    0);
                                  v83 = *((_QWORD *)v3 + 49);
                                  if ( v83 && !v88 )
                                  {
                                    v57 = (*((_BYTE *)this + 188) & 0x40) == 0;
                                    v96 = 0;
                                    *(_OWORD *)pv = 0;
                                    LOWORD(pv[0]) = 11;
                                    if ( v57 )
                                      LOWORD(pv[1]) = -1;
                                    else
                                      LOWORD(pv[1]) = 0;
                                    (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v83 + 32LL))(
                                      v83,
                                      &CGID_Explorer,
                                      113);
                                  }
                                  v84 = *((_QWORD *)v3 + 109);
                                  if ( v84 )
                                  {
                                    *((_QWORD *)v3 + 109) = 0;
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                                  }
                                  v85 = (void *)*((_QWORD *)this + 15);
                                  if ( v85 )
                                  {
                                    LocalFree(v85);
                                    *((_QWORD *)this + 15) = 0;
                                  }
                                  v86 = (void *)*((_QWORD *)this + 13);
                                  if ( v86 )
                                  {
                                    GlobalFree(v86);
                                    *((_QWORD *)this + 13) = 0;
                                  }
                                  goto LABEL_199;
                                }
                              }
                            }
                          }
                          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&pIUri);
                        }
LABEL_143:
                        if ( !v41 )
                          goto LABEL_123;
                        CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
                          (CDocObjectHost::CDOHBindStatusCallback *)v39,
                          (struct CDocObjectHost *)v3,
                          0,
                          0,
                          0,
                          0);
                        if ( v98 || v93 )
                          goto LABEL_123;
                        if ( (v3[640] & 0x20) == 0 || (v44 = 1, (v3[2224] & 1) != 0) )
                          v44 = 0;
                        if ( !(unsigned int)IsDiagnoseConnectionSettingsEnabled() )
                          goto LABEL_160;
                        v40 = 1;
                        if ( !IsNetworkConnectionAvailable() )
                          goto LABEL_160;
                        *((_DWORD *)v3 + 172) = a2;
                        v46 = pszStart;
                        if ( CDocObjectHost::CDOHBindStatusCallback::_GetUrl(this, v114, v45) >= 0 )
                          v46 = v114;
                        if ( v33 )
                        {
                          if ( CDocObjectHost::_IsTLSFailure((CDocObjectHost *)v114, v102, v46) )
                          {
                            v40 = 12;
LABEL_160:
                            CDocObjectHost::CDOHBindStatusCallback::_NavigateToErrorPage(
                              this,
                              v40,
                              (struct CDocObjectHost *)v3,
                              v44,
                              v113);
                            goto LABEL_123;
                          }
                          if ( v101 )
                          {
                            v40 = 10;
                            goto LABEL_160;
                          }
                        }
                        if ( psa && CDocObjectHost::_HandlePrivateNetworkFailure((CDocObjectHost *)v3, v46, psa, a2) )
                          goto LABEL_123;
                        goto LABEL_160;
                      }
                      v90 = 1;
                    }
LABEL_104:
                    v41 = v90;
                    goto LABEL_105;
                }
LABEL_142:
                v41 = v90;
                goto LABEL_143;
              }
              goto LABEL_133;
            }
            goto LABEL_175;
          }
          if ( !*((_BYTE *)this + 208) )
          {
LABEL_133:
            CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
              (CDocObjectHost::CDOHBindStatusCallback *)v39,
              (struct CDocObjectHost *)v3,
              0,
              0,
              0,
              0);
            goto LABEL_189;
          }
        }
LABEL_182:
        v50 = 0;
        if ( CoInternetIsFeatureEnabled(FEATURE_MIME_HANDLING, 2u) != 1 )
        {
          v51 = (const WCHAR *)*((_QWORD *)this + 17);
          if ( v51 )
          {
            ExtensionW = PathFindExtensionW(v51);
            if ( (unsigned int)RestrictShellExecute(ExtensionW) )
              v50 = 2;
          }
          if ( (*((_DWORD *)v3 + 162) & 0x8000000) != 0 )
          {
            CDocObjectHost::CDOHBindStatusCallback::_WriteCompatLogEntryForDownloadFallthrough(this, v29, pszStart);
            *((_DWORD *)this + 47) |= 0x400u;
            if ( !*((_QWORD *)this + 17) && !*((_BYTE *)this + 208) )
            {
LABEL_189:
              if ( (*((_DWORD *)v3 + 162) & 0x1000000) != 0 )
              {
                v39 = *((_QWORD *)v3 + 49);
                if ( v39 )
                {
                  v96 = 0;
                  *(_OWORD *)pv = 0;
                  (*(void (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v39 + 32LL))(
                    v39,
                    &CGID_ShellDocView,
                    69);
                }
              }
              goto LABEL_123;
            }
            *((_DWORD *)v3 + 162) &= ~0x8000000u;
            v33 = 1;
          }
        }
        v53 = *((_QWORD *)this + 8);
        pv[0] = 0;
        v54 = -__CFSHR__((_DWORD)pIUri, 9);
        if ( v53
          && (*(int (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v53 + 80LL))(
               v53,
               L"__DISABLE_BIND_TO_OBJ",
               pv) >= 0 )
        {
          v50 = 2;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
        }
        CDocObjectHost::_EnableModeless((CDocObjectHost *)v3, 0);
        v55 = v50 | 4;
        if ( (v3[640] & 0x20) == 0 )
          v55 = v50;
        v88 = CDocObjectHost::CDOHBindStatusCallback::_TransferToFileDownload(
                (const WCHAR **)this,
                v33,
                v54,
                v55,
                &v103,
                &v107);
        CDocObjectHost::_EnableModeless((CDocObjectHost *)v3, 1);
        if ( !v88 )
          goto LABEL_199;
        goto LABEL_123;
      }
      if ( a2 != -2146697203 )
      {
        if ( a2 == -2146697201 )
        {
          CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
            (CDocObjectHost::CDOHBindStatusCallback *)v39,
            (struct CDocObjectHost *)v3,
            0,
            0,
            0,
            0);
          if ( CoInternetIsFeatureEnabled(FEATURE_MIME_HANDLING, 2u) != 1 )
          {
            if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() && (*((_DWORD *)v3 + 162) & 0x8000000) == 0 )
              v29 = 1;
            *((_DWORD *)v3 + 162) |= 0x8000000u;
          }
          goto LABEL_182;
        }
        if ( a2 == -2146697200 )
        {
LABEL_175:
          CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
            (CDocObjectHost::CDOHBindStatusCallback *)v39,
            (struct CDocObjectHost *)v3,
            0,
            0,
            0,
            0);
          goto LABEL_182;
        }
        v39 = 2148270105LL;
        if ( a2 == -2146697191 || a2 == -2146697186 )
        {
          if ( (v3[640] & 0x20) == 0 || (v3[2224] & 1) != 0 )
          {
            v47 = 6;
            if ( a2 != -2146697191 )
              v47 = 14;
            v48 = 0;
          }
          else
          {
            v47 = 7;
            v48 = 1;
          }
          goto LABEL_163;
        }
        if ( a2 == -2146697185 )
        {
          if ( (v3[640] & 0x20) == 0 || (v3[2224] & 1) != 0 )
          {
            v49 = 15;
            v48 = 0;
          }
          else
          {
            v48 = 1;
            v49 = 16;
          }
          v47 = v49;
          goto LABEL_163;
        }
        if ( a2 != -2146697184 )
          goto LABEL_142;
        v47 = 19;
LABEL_162:
        v48 = 0;
LABEL_163:
        CDocObjectHost::CDOHBindStatusCallback::_NavigateToErrorPage(this, v47, (struct CDocObjectHost *)v3, v48, 0);
        goto LABEL_123;
      }
      v59 = (const unsigned __int16 *)*((_QWORD *)this + 16);
      if ( v59 )
        StringCchCopyW(pszStart, 0x825u, v59);
      v101 = 0;
      if ( ShouldShellExecURL(pszStart, &v101) )
      {
        CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
          (CDocObjectHost::CDOHBindStatusCallback *)v39,
          (struct CDocObjectHost *)v3,
          0,
          0,
          0,
          0);
        v60 = (const unsigned __int16 *)*((_QWORD *)v3 + 77);
        if ( v60 )
          StringCchCatW(pszStart, 0x825u, v60);
        v61 = v98;
      }
      else
      {
        v61 = v98;
        if ( v98 || v93 )
        {
          CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
            (CDocObjectHost::CDOHBindStatusCallback *)v39,
            (struct CDocObjectHost *)v3,
            0,
            0,
            0,
            0);
          goto LABEL_123;
        }
        if ( (*((_DWORD *)v3 + 162) & 0x40000) == 0
          && (StrChrW(pszStart, (unsigned __int16)v98 + 32) || !StrStrW(pszStart, L":/"))
          && !(unsigned int)CDocObjectHost::CDOHBindStatusCallback::_HandleFailedNavigationSearch(
                              this,
                              &v97,
                              v89,
                              (struct CDocObjectHost *)v3,
                              v91,
                              pszStart,
                              v87,
                              *((struct IBinding **)this + 7),
                              0) )
        {
          goto LABEL_123;
        }
        CDocObjectHost::CDOHBindStatusCallback::_SetSearchInfo(
          (CDocObjectHost::CDOHBindStatusCallback *)v39,
          (struct CDocObjectHost *)v3,
          0,
          0,
          0,
          0);
        if ( !IsOs_Win8OrGreater() || !(unsigned __int8)IEConfiguration_GetBool(536870914) || v101 )
        {
          v47 = 8;
          goto LABEL_162;
        }
        v62 = (const unsigned __int16 *)*((_QWORD *)v3 + 77);
        if ( v62 )
          StringCchCatW(pszStart, 0x825u, v62);
      }
      v63 = 0;
      v64 = CDocObjectHost::CDOHBindStatusCallback::_ShellExecuteURL(this, pszStart);
      if ( v64 != -2147467260 )
      {
        v65 = (unsigned __int16)v64;
        v63 = 1;
        v103 = 1;
        if ( (v64 & 0xFFFF0000) != 0x80070000 )
          v65 = 0;
        if ( v64 < 0 && !v61 && v65 != 1223 && v65 != 1460 )
          SHIEErrorMsgBox(*((IUnknown **)v3 + 48), (__int64)pszStart, 756, 0x10u);
      }
      if ( (*((_DWORD *)v3 + 162) & 0x40000) == 0 )
      {
        VirtualTab_NewTabShouldExit(0);
        if ( IsDualEngineProcess() )
          DualEngineNavigationFailed();
      }
      if ( v63 )
        goto LABEL_124;
      goto LABEL_123;
    }
    ppIUriBuilder[0] = 0;
    if ( (**v18)(v18, &GUID_f3d8f080_a5eb_476f_9d19_a5ef24e5c2e6, ppIUriBuilder) >= 0 )
    {
      pv[0] = 0;
      v94 = 0;
      v105 = 0;
      if ( !((unsigned int (__fastcall *)(IUriBuilder *, int *, LPVOID *, int *))ppIUriBuilder[0]->lpVtbl->GetPath)(
              ppIUriBuilder[0],
              &v105,
              pv,
              &v94) )
      {
        if ( v105 )
        {
          v101 = 1;
          if ( pv[0] )
          {
            StringCchPrintfW(v113, 0x106u, L"%s:%d");
            LocalFree(pv[0]);
            pv[0] = 0;
          }
        }
      }
      v92 = 0;
      v19 = ((__int64 (__fastcall *)(IUriBuilder *, int *))ppIUriBuilder[0]->lpVtbl->GetPort)(ppIUriBuilder[0], &v92);
      v20 = 0;
      if ( v19 >= 0 )
        v20 = v92;
      v102 = v20;
      if ( ((unsigned int (__fastcall *)(IUriBuilder *, SAFEARRAY **))ppIUriBuilder[0]->lpVtbl->CreateUriWithFlags)(
             ppIUriBuilder[0],
             &psa)
        && psa )
      {
        SafeArrayDestroy(psa);
        psa = 0;
      }
    }
    v21 = *v17;
    bstrString = 0;
    if ( ((__int64 (__fastcall *)(struct IBinding *, GUID *, BSTR *))v21->lpVtbl->QueryInterface)(
           v21,
           &GUID_79eac9d8_bafa_11ce_8c82_00aa004ba90b,
           &bstrString) < 0 )
    {
LABEL_67:
      ATL::CComPtr<IPrivacIEDatabase>::Release((char *)this + 56);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(ppIUriBuilder);
      goto LABEL_68;
    }
    v92 = 256;
    if ( !(*(unsigned int (__fastcall **)(BSTR, __int64, _BYTE *, int *, _QWORD, _QWORD))(*(_QWORD *)bstrString + 32LL))(
            bstrString,
            11,
            v112,
            &v92,
            0,
            0) )
      *((_DWORD *)v3 + 161) = 1;
    if ( (*(unsigned int (__fastcall **)(BSTR, __int64, unsigned int *, int *, _QWORD, _QWORD))(*(_QWORD *)bstrString
                                                                                              + 32LL))(
           bstrString,
           536870931,
           &v89,
           &v106,
           0,
           0) )
    {
      v22 = 0;
      v106 = 0;
      v89 = 0;
    }
    else
    {
      v22 = v89;
    }
    if ( v22 )
    {
      v94 = 1024;
      if ( v22 == 204 )
        v7 = 0;
      v90 = v7;
      v97 = v7;
      if ( a2 == -2146697209 )
      {
        if ( v22 < 0x258 )
        {
          v23 = (*(__int64 (__fastcall **)(BSTR, __int64, unsigned __int16 *, int *, _QWORD, _QWORD))(*(_QWORD *)bstrString + 32LL))(
                  bstrString,
                  1,
                  v114,
                  &v94,
                  0,
                  0);
          v22 = v89;
          if ( !v23 )
          {
            v90 = 0;
            v97 = 0;
          }
        }
      }
      else if ( a2 == -2146697189 )
      {
        v24 = SysAllocString(psz);
        v27 = v24;
        if ( v24 )
          CDocObjectHost::_FireRedirectXDomainBlockedHelper((CDocObjectHost *)v3, v25, 0x800C001B, v26, v24);
        SysFreeString(v27);
        v22 = v89;
        goto LABEL_62;
      }
      if ( v22 - 400 <= 0xC7 )
      {
LABEL_62:
        CDocObjectHost::_FireNavigateErrorHelper((CDocObjectHost *)v3, 0, v22, &v93, 0);
        v14 = 1;
        if ( v93 )
        {
          if ( (v3[640] & 8) == 0 )
            CDocObjectHost::_CancelPendingNavigation((CDocObjectHost *)v3, 0, 0, 0, 0, 0);
        }
        else
        {
          CDocObjectHost::CDOHBindStatusCallback::_HandleHttpErrors(
            this,
            v89,
            *((_DWORD *)this + 45),
            (struct CDocObjectHost *)v3);
        }
      }
    }
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    goto LABEL_67;
  }
LABEL_199:
  if ( (*((_DWORD *)this + 47) & 0x800) == 0 )
    CDocObjectHost::SetIgnoreMimeSettings((CDocObjectHost *)v3, 0);
  *((_DWORD *)v3 + 162) &= ~0x20000000u;
  *((_DWORD *)v3 + 163) &= ~1u;
  v56 = psa;
  *((_DWORD *)v3 + 360) = 0;
  if ( v56 )
  {
    SafeArrayDestroy(v56);
    psa = 0;
  }
LABEL_203:
  v57 = (*((_DWORD *)v3 + 63))-- == 1;
  if ( v57 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v3 + 160LL))(v3, 1);
  return 0;
}

```

## disassembly

```asm
0x180066380  mov     [rsp-8+arg_18], rbx
0x180066385  push    rbp
0x180066386  push    rsi
0x180066387  push    rdi
0x180066388  push    r12
0x18006638a  push    r13
0x18006638c  push    r14
0x18006638e  push    r15
0x180066390  lea     rbp, [rsp-23F0h]
0x180066398  mov     eax, 24F0h
0x18006639d  call    _alloca_probe
0x1800663a2  sub     rsp, rax
0x1800663a5  mov     rax, cs:__security_cookie
0x1800663ac  xor     rax, rsp
0x1800663af  mov     [rbp+2420h+var_40], rax
0x1800663b6  and     dword ptr [rcx+0BCh], 0FFFFDFFDh
0x1800663c0  lea     r14, [rcx-7A0h]
0x1800663c7  mov     eax, [rcx+0BCh]
0x1800663cd  xor     r12d, r12d
0x1800663d0  mov     dword ptr [rbp+2420h+pIUri], eax
0x1800663d3  mov     ebx, 1
0x1800663d8  mov     rax, [r14]
0x1800663db  mov     r15, rcx
0x1800663de  mov     rcx, r14
0x1800663e1  mov     [rbp+2420h+psz], r8
0x1800663e5  mov     r13d, edx
0x1800663e8  mov     [rsp+2520h+var_24B8], ebx
0x1800663ec  mov     esi, ebx
0x1800663ee  mov     [rbp+2420h+var_2480], ebx
0x1800663f1  mov     rax, [rax+8]
0x1800663f5  mov     [rsp+2520h+var_24BC], r12d
0x1800663fa  mov     [rbp+2420h+var_244C], 4
0x180066401  mov     [rbp+2420h+var_2460], r12d
0x180066405  mov     [rbp+2420h+var_2448], r12d
0x180066409  mov     [rsp+2520h+var_24A8], r12d
0x18006640e  mov     [rbp+2420h+psa], r12
0x180066412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066417  btr     dword ptr [r15+0BCh], 8
0x180066420  test    dword ptr [r14+288h], 10000h
0x18006642b  jz      short loc_18006643E
0x18006642d  test    r13d, r13d
0x180066430  jns     short loc_18006643E
0x180066432  mov     [r14+2ACh], r13d
0x180066439  jmp     loc_1800671AF
0x18006643e  cmp     r13d, 800C001Ah
0x180066445  jnz     short loc_18006646C
0x180066447  xor     r8d, r8d; bool
0x18006644a  mov     rdx, r14; struct CDocObjectHost *
0x18006644d  mov     rcx, r15; this
0x180066450  call    ?_HandleVTabSwitch@CDOHBindStatusCallback@CDocObjectHost@@IEAA_NPEAV2@_N@Z; CDocObjectHost::CDOHBindStatusCallback::_HandleVTabSwitch(CDocObjectHost *,bool)
0x180066455  movzx   edi, al
0x180066458  mov     al, dil
0x18006645b  neg     al
0x18006645d  sbb     r13d, r13d
0x180066460  not     r13d
0x180066463  and     r13d, 80004004h
0x18006646a  jmp     short loc_18006648C
0x18006646c  mov     edi, r12d
0x18006646f  cmp     r13d, 800C0022h
0x180066476  jnz     short loc_18006648C
0x180066478  mov     rdx, r14; struct CDocObjectHost *
0x18006647b  mov     rcx, r15; this
0x18006647e  call    ?_HandleDualEngineSwitch@CDOHBindStatusCallback@CDocObjectHost@@IEAAJPEAV2@@Z; CDocObjectHost::CDOHBindStatusCallback::_HandleDualEngineSwitch(CDocObjectHost *)
0x180066483  test    eax, eax
0x180066485  js      short loc_18006648C
0x180066487  mov     r13d, r12d
0x18006648a  mov     edi, ebx
0x18006648c  lea     rcx, [r15+0F8h]; this
0x180066493  call    ?Reset@CPrivacyQueue@@QEAAXXZ; CPrivacyQueue::Reset(void)
0x180066498  mov     rcx, r15; this
0x18006649b  call    ?ResetPrivacyInfo@CDOHBindStatusCallback@CDocObjectHost@@IEAAXXZ; CDocObjectHost::CDOHBindStatusCallback::ResetPrivacyInfo(void)
0x1800664a0  mov     ecx, 80004004h
0x1800664a5  cmp     r13d, ecx
0x1800664a8  jnz     short loc_1800664BF
0x1800664aa  test    byte ptr [r15+0BCh], 20h
0x1800664b2  jz      short loc_1800664BF
0x1800664b4  or      dword ptr [r14+288h], 80000000h
0x1800664bf  mov     edx, [r15+0BCh]
0x1800664c6  mov     [rbp+2420h+var_247C], edx
0x1800664c9  test    dl, 10h
0x1800664cc  jz      short loc_1800664D5
0x1800664ce  cmp     r13d, ecx
0x1800664d1  cmovz   r13d, r12d
0x1800664d5  mov     rcx, [r15+40h]
0x1800664d9  mov     [r15+60h], r12d
0x1800664dd  test    rcx, rcx
0x1800664e0  jz      short loc_180066501
0x1800664e2  cmp     [r14+388h], r12
0x1800664e9  jz      short loc_180066501
0x1800664eb  mov     rax, [rcx]
0x1800664ee  lea     rdx, aPrecreatedobje; "__PrecreatedObject"
0x1800664f5  mov     rax, [rax+60h]
0x1800664f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800664fe  mov     edx, [rbp+2420h+var_247C]
0x180066501  cmp     [r15+40h], r12
0x180066505  jz      loc_1800678BF
0x18006650b  mov     rcx, [r14+190h]
0x180066512  mov     ebx, r12d
0x180066515  shr     edx, 4
0x180066518  mov     [rsp+2520h+var_24C0], r12b
0x18006651d  sbb     edx, edx
0x18006651f  mov     [rbp+2420h+var_2468], r12d
0x180066523  mov     [rbp+2420h+var_2464], r12d
0x180066527  mov     [rbp+2420h+var_247C], edx
0x18006652a  test    rcx, rcx
0x18006652d  jz      short loc_18006653D
0x18006652f  mov     rax, [rcx]
0x180066532  xor     edx, edx
0x180066534  mov     rax, [rax+70h]
0x180066538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006653d  mov     rcx, [r14+180h]
0x180066544  test    rcx, rcx
0x180066547  jz      short loc_180066557
0x180066549  mov     rax, [rcx]
0x18006654c  xor     edx, edx
0x18006654e  mov     rax, [rax+40h]
0x180066552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066557  mov     rcx, [r15+40h]; pBC
0x18006655b  mov     rdx, r15; pBSCb
0x18006655e  call    cs:__imp_RevokeBindStatusCallback
0x180066564  mov     rcx, [r15+40h]
0x180066568  lea     rdx, aD4db6850538511; "{d4db6850-5385-11d0-89e9-00a0c90a90ac}"
0x18006656f  mov     rax, [rcx]
0x180066572  mov     rax, [rax+60h]
0x180066576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006657b  test    byte ptr [r15+0BCh], 20h
0x180066583  jz      short loc_180066592
0x180066585  xor     r8d, r8d; struct tagVARIANT *
0x180066588  xor     edx, edx; unsigned int
0x18006658a  mov     rcx, r14; this
0x18006658d  call    ?_HandlePageActionBlocked@CDocObjectHost@@IEAAXKPEAUtagVARIANT@@@Z; CDocObjectHost::_HandlePageActionBlocked(ulong,tagVARIANT *)
0x180066592  lea     eax, [r13+7FF3FFFEh]
0x180066599  mov     [rsp+2520h+var_24B4], r13d
0x18006659e  cmp     eax, 506h
0x1800665a3  ja      short loc_180066602
0x1800665a5  mov     rcx, [r15+38h]
0x1800665a9  test    rcx, rcx
0x1800665ac  jz      short loc_180066602
0x1800665ae  xorps   xmm0, xmm0
0x1800665b1  mov     [rbp+2420h+pv], r12
0x1800665b5  movups  xmmword ptr [rbp+2420h+ppIUriBuilder], xmm0
0x1800665b9  mov     rax, [rcx]
0x1800665bc  lea     r9, [rbp+2420h+pv]
0x1800665c0  lea     r8, [rsp+2520h+var_24B4]
0x1800665c5  mov     [rsp+2520h+var_2500], r12
0x1800665ca  lea     rdx, [rbp+2420h+ppIUriBuilder]
0x1800665ce  mov     rax, [rax+40h]
0x1800665d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665d7  test    eax, eax
0x1800665d9  js      short loc_180066602
0x1800665db  mov     eax, [rsp+2520h+var_24B4]
0x1800665df  cmp     eax, esi
0x1800665e1  jl      short loc_1800665F3
0x1800665e3  test    eax, eax
0x1800665e5  jle     short loc_1800665EF
0x1800665e7  movzx   eax, ax
0x1800665ea  or      eax, 80070000h
0x1800665ef  mov     [rsp+2520h+var_24B4], eax
0x1800665f3  mov     rcx, [rbp+2420h+pv]; pv
0x1800665f7  test    rcx, rcx
0x1800665fa  jz      short loc_180066602
0x1800665fc  call    cs:__imp_CoTaskMemFree
0x180066602  lea     r12, [r15+38h]
0x180066606  mov     rcx, [r12]
0x18006660a  test    rcx, rcx
0x18006660d  jz      loc_1800668E5
0x180066613  mov     [rbp+2420h+ppIUriBuilder], rbx
0x180066617  lea     r8, [rbp+2420h+ppIUriBuilder]
0x18006661b  mov     rax, [rcx]
0x18006661e  lea     rdx, _GUID_f3d8f080_a5eb_476f_9d19_a5ef24e5c2e6
0x180066625  mov     rax, [rax]
0x180066628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006662d  test    eax, eax
0x18006662f  js      loc_1800666F2
0x180066635  mov     rcx, [rbp+2420h+ppIUriBuilder]
0x180066639  lea     r9, [rsp+2520h+var_24A4]
0x18006663e  xor     eax, eax
0x180066640  lea     r8, [rbp+2420h+pv]
0x180066644  mov     [rbp+2420h+pv], rax
0x180066648  lea     rdx, [rbp+2420h+var_2450]
0x18006664c  mov     [rsp+2520h+var_24A4], eax
0x180066650  mov     [rbp+2420h+var_2450], eax
0x180066653  mov     rax, [rcx]
0x180066656  mov     rax, [rax+58h]
0x18006665a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006665f  test    eax, eax
0x180066661  jnz     short loc_1800666A2
0x180066663  cmp     [rbp+2420h+var_2450], ebx
0x180066666  jz      short loc_1800666A2
0x180066668  mov     r9, [rbp+2420h+pv]
0x18006666c  mov     [rbp+2420h+var_2468], esi
0x18006666f  test    r9, r9
0x180066672  jz      short loc_1800666A2
0x180066674  mov     eax, [rsp+2520h+var_24A4]
0x180066678  lea     r8, aSD; "%s:%d"
0x18006667f  mov     edx, 106h; unsigned __int64
0x180066684  mov     dword ptr [rsp+2520h+var_2500], eax
0x180066688  lea     rcx, [rbp+2420h+var_12A0]; unsigned __int16 *
0x18006668f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180066694  mov     rcx, [rbp+2420h+pv]; hMem
0x180066698  call    cs:__imp_LocalFree
0x18006669e  mov     [rbp+2420h+pv], rbx
0x1800666a2  mov     rcx, [rbp+2420h+ppIUriBuilder]
0x1800666a6  lea     rdx, [rsp+2520h+var_24B0]
0x1800666ab  mov     [rsp+2520h+var_24B0], ebx
0x1800666af  mov     rax, [rcx]
0x1800666b2  mov     rax, [rax+60h]
0x1800666b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666bb  test    eax, eax
0x1800666bd  lea     rdx, [rbp+2420h+psa]
0x1800666c1  mov     ecx, ebx
0x1800666c3  cmovns  ecx, [rsp+2520h+var_24B0]
0x1800666c8  mov     [rbp+2420h+var_2464], ecx
0x1800666cb  mov     rcx, [rbp+2420h+ppIUriBuilder]
0x1800666cf  mov     rax, [rcx]
0x1800666d2  mov     rax, [rax+28h]
0x1800666d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666db  test    eax, eax
0x1800666dd  jz      short loc_1800666F2
0x1800666df  mov     rcx, [rbp+2420h+psa]; psa
0x1800666e3  test    rcx, rcx
0x1800666e6  jz      short loc_1800666F2
0x1800666e8  call    cs:__imp_SafeArrayDestroy
0x1800666ee  mov     [rbp+2420h+psa], rbx
0x1800666f2  mov     rcx, [r12]
0x1800666f6  lea     r8, [rbp+2420h+bstrString]
0x1800666fa  mov     [rbp+2420h+bstrString], rbx
0x1800666fe  lea     rdx, _GUID_79eac9d8_bafa_11ce_8c82_00aa004ba90b
0x180066705  mov     rax, [rcx]
0x180066708  mov     rax, [rax]
0x18006670b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066710  test    eax, eax
0x180066712  js      loc_1800668D4
0x180066718  mov     rcx, [rbp+2420h+bstrString]
0x18006671c  lea     r9, [rsp+2520h+var_24B0]
0x180066721  mov     [rsp+2520h+var_24B0], 100h
0x180066729  lea     r8, [rbp+2420h+var_13A0]
0x180066730  mov     [rsp+2520h+var_24F8], rbx
0x180066735  mov     edx, 0Bh
0x18006673a  mov     [rsp+2520h+var_2500], rbx
0x18006673f  mov     rax, [rcx]
0x180066742  mov     rax, [rax+20h]
0x180066746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006674b  test    eax, eax
0x18006674d  jnz     short loc_180066756
0x18006674f  mov     [r14+284h], esi
0x180066756  mov     rcx, [rbp+2420h+bstrString]
0x18006675a  lea     r9, [rbp+2420h+var_244C]
0x18006675e  mov     [rsp+2520h+var_24F8], rbx
0x180066763  lea     r8, [rsp+2520h+var_24BC]
0x180066768  mov     edx, 20000013h
0x18006676d  mov     [rsp+2520h+var_2500], rbx
0x180066772  mov     rax, [rcx]
0x180066775  mov     rax, [rax+20h]
0x180066779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006677e  test    eax, eax
0x180066780  jz      short loc_18006678F
0x180066782  xor     r8d, r8d
0x180066785  mov     [rbp+2420h+var_244C], ebx
0x180066788  mov     [rsp+2520h+var_24BC], r8d
0x18006678d  jmp     short loc_180066794
0x18006678f  mov     r8d, [rsp+2520h+var_24BC]
0x180066794  test    r8d, r8d
0x180066797  jz      loc_1800668C4
0x18006679d  xor     eax, eax
0x18006679f  mov     [rsp+2520h+var_24A4], 400h
0x1800667a7  cmp     r8d, 0CCh
0x1800667ae  cmovz   esi, eax
0x1800667b1  mov     [rsp+2520h+var_24B8], esi
0x1800667b5  mov     [rbp+2420h+var_2480], esi
0x1800667b8  cmp     r13d, 800C0007h
0x1800667bf  jnz     short loc_180066807
0x1800667c1  cmp     r8d, 258h
0x1800667c8  jnb     short loc_180066810
0x1800667ca  mov     rcx, [rbp+2420h+bstrString]
0x1800667ce  lea     r9, [rsp+2520h+var_24A4]
0x1800667d3  mov     [rsp+2520h+var_24F8], rbx
0x1800667d8  lea     r8, [rbp+2420h+var_1090]
0x1800667df  mov     edx, 1
0x1800667e4  mov     [rsp+2520h+var_2500], rbx
0x1800667e9  mov     rax, [rcx]
0x1800667ec  mov     rax, [rax+20h]
0x1800667f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667f5  mov     r8d, [rsp+2520h+var_24BC]
0x1800667fa  test    eax, eax
0x1800667fc  jnz     short loc_180066810
0x1800667fe  mov     [rsp+2520h+var_24B8], eax
0x180066802  mov     [rbp+2420h+var_2480], eax
0x180066805  jmp     short loc_180066810
0x180066807  cmp     r13d, 800C001Bh
0x18006680e  jz      short loc_18006682B
0x180066810  lea     eax, [r8-190h]
0x180066817  cmp     eax, 0C7h
0x18006681c  ja      loc_1800668C4
0x180066822  cmp     r13d, 800C001Bh
0x180066829  jnz     short loc_18006685E
0x18006682b  mov     rcx, [rbp+2420h+psz]; psz
0x18006682f  call    cs:__imp_SysAllocString
0x180066835  mov     rbx, rax
0x180066838  test    rax, rax
  ... truncated ...
```
