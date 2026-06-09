# WebViewManager::CreateCoreWebViewPrivate(CoreWebViewSettings const *,ICoreWebViewHostProcess *,ICoreWebViewComponentCallback *,Windows::Foundation::Private::IComponentSite * *,ICoreWebViewPrivate * *)

- ea: `0x180003cc0`
- end: `0x1800048ac`
- name: `?CreateCoreWebViewPrivate@WebViewManager@@YAJPEBUCoreWebViewSettings@@PEAUICoreWebViewHostProcess@@PEAUICoreWebViewComponentCallback@@PEAPEAUIComponentSite@Private@Foundation@Windows@@PEAPEAUICoreWebViewPrivate@@@Z`
- size: `3052`
- prototype: `__int64 __fastcall(WebViewManager *__hidden this, const struct CoreWebViewSettings *, struct ICoreWebViewHostProcess *, struct ICoreWebViewComponentCallback *, struct Windows::Foundation::Private::IComponentSite **, struct ICoreWebViewPrivate **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180003760`

## callees

- `0x180003cc0`
- `0x1800051c0`
- `0x180006760`
- `0x180006d90`
- `0x1800073a0`
- `0x180008150`
- `0x1800154cc`
- `0x1800183d4`
- `0x180018a18`
- `0x180018b30`
- `0x180019610`
- `0x180020ebc`
- `0x18002347c`
- `0x18002b530`
- `0x18002c5b0`
- `0x180035b88`
- `0x180085010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1800041e9`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1800041e9`
- `api-ms-win-core-localregistry-l1-1-0!RegGetValueW` at `0x180003ed7`
- `api-ms-win-core-localregistry-l1-1-0!RegGetValueW` at `0x180003ed7`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f27`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004199`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180004199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000425b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800041c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000425b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000420d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000420d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004162`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003fa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003fa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003d0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800045a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003d0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800045a8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003d18`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800045b6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003d18`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800045b6`

## string_xrefs

- `0x18000417c`: `edgehtml.dll`
- `0x180004175`: `mshtml.dll`
- `0x18000424d`: `CreateCoreWebView`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall WebViewManager::CreateCoreWebViewPrivate(
        WebViewManager *this,
        const struct CoreWebViewSettings *a2,
        struct ICoreWebViewHostProcess *a3,
        struct ICoreWebViewComponentCallback *a4,
        struct Windows::Foundation::Private::IComponentSite **a5)
{
  const char *v9; // r9
  int v10; // eax
  int v11; // eax
  const char *v12; // r9
  unsigned int ExecutionModeKey; // ebx
  int v14; // eax
  LSTATUS ValueW; // eax
  const WCHAR *CoreWebViewName; // rsi
  unsigned int v17; // edx
  unsigned int v18; // eax
  int v19; // ecx
  int v20; // eax
  HANDLE CurrentProcess; // rax
  int v22; // eax
  struct Windows::Foundation::Private::IComponentSite *v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  const char *v26; // r9
  unsigned int v27; // ebx
  BSTR v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  struct Windows::Foundation::Private::IComponentSite *v31; // rcx
  unsigned __int64 v33; // r14
  signed int v34; // ebx
  int v35; // esi
  const WCHAR *v36; // rcx
  HMODULE Library; // rcx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  struct Windows::Foundation::Private::IComponentSite *v40; // rcx
  FARPROC v41; // rax
  int v42; // eax
  ComponentSiteAdapter *v43; // rbx
  __int64 v44; // rcx
  int Interface; // eax
  const char *v46; // r9
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  void *v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  unsigned int v54; // edi
  BSTR v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  struct Windows::Foundation::Private::IComponentSite *v58; // rcx
  int v59; // eax
  BSTR v60; // rcx
  struct Windows::Foundation::Private::IComponentSite *v61; // rax
  __int64 v62; // rdx
  unsigned __int64 v63; // r8
  unsigned __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // rcx
  struct Windows::Foundation::Private::IComponentSite *v67; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Foundation::Private::IComponentSite *v72; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v73; // [rsp+60h] [rbp-A0h] BYREF
  void *v74; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbData[2]; // [rsp+80h] [rbp-80h] BYREF
  ComponentSiteAdapter *pvData; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME v78; // [rsp+90h] [rbp-70h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v80; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v82[4]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v83[5]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v84; // [rsp+110h] [rbp+10h]
  __int128 v85; // [rsp+120h] [rbp+20h]
  unsigned int v86[4]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v87; // [rsp+140h] [rbp+40h]
  __int128 v88; // [rsp+150h] [rbp+50h]
  __int128 v89; // [rsp+160h] [rbp+60h]
  __int128 v90; // [rsp+170h] [rbp+70h]
  _BYTE v91[24]; // [rsp+180h] [rbp+80h]
  struct _GUID v92; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR SubKey[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v94[524]; // [rsp+1B4h] [rbp+B4h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+318h]

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( !*((_DWORD *)this + 30) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      v9);
  v72 = 0;
  *(_QWORD *)&v73.Data1 = 0;
  v75 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, GUID *, __int64 *))(**((_QWORD **)this + 4) + 24LL))(
          *((_QWORD *)this + 4),
          qword_18009FCF8,
          &GUID_7bfa68b6_7abe_42ca_bf48_b180ae81cd20,
          &v75);
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v10,
      pdwType);
  v83[0] = *(_OWORD *)this;
  v83[1] = *((_OWORD *)this + 1);
  v83[2] = *((_OWORD *)this + 2);
  v83[3] = *((_OWORD *)this + 3);
  v83[4] = *((_OWORD *)this + 4);
  v84 = *((_OWORD *)this + 5);
  v85 = *((_OWORD *)this + 6);
  *(_OWORD *)v86 = *((_OWORD *)this + 7);
  v87 = *((_OWORD *)this + 8);
  v88 = *((_OWORD *)this + 9);
  v89 = *((_OWORD *)this + 10);
  v90 = *((_OWORD *)this + 11);
  *(_OWORD *)v91 = *((_OWORD *)this + 12);
  *(_QWORD *)&v91[16] = *((_QWORD *)this + 26);
  bstrString = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v75 + 80LL))(v75, &bstrString);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v11,
      pdwType);
  if ( byte_1800B6BA8 )
  {
    ExecutionModeKey = dword_1800B6BA4;
  }
  else
  {
    ExecutionModeKey = ReadExecutionModeKey(L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\WebView");
    dword_1800B6BA4 = ExecutionModeKey;
    if ( !ExecutionModeKey )
    {
      *(_DWORD *)SubKey = 0;
      memset_0(v94, 0, 0x204u);
      pdwTypea = (int)bstrString;
      v14 = StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\WebView");
      if ( v14 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
          (const char *)(unsigned int)v14,
          pdwTypea);
      LODWORD(pvData) = 0;
      pcbData[0] = 4;
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ExecutionMode", 0x10u, 0, &pvData, pcbData);
      if ( ValueW )
      {
        ExecutionModeKey = 0;
        if ( ValueW == 87 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x89,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
            v12);
      }
      else
      {
        ExecutionModeKey = (unsigned int)pvData;
      }
      dword_1800B6BA4 = ExecutionModeKey;
    }
    byte_1800B6BA8 = 1;
  }
  if ( ExecutionModeKey > 3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      v12);
  if ( bstrString )
    SysFreeString(bstrString);
  CoreWebViewName = (const WCHAR *)GetCoreWebViewName(*((_QWORD *)&v84 + 1));
  *(_QWORD *)&v83[0] = CoreWebViewName;
  *((_QWORD *)&v83[0] + 1) = CoreWebViewName;
  *(_DWORD *)v91 = _InterlockedIncrement(&dword_1800B6BA0);
  v17 = v86[2];
  if ( ExecutionModeKey )
    v17 = ExecutionModeKey;
  v86[2] = v17;
  if ( v17 == 1 )
    v18 = v86[3] & 0xFFFF7DFF | 0x8000;
  else
    v18 = v86[3] & 0xFFFF7DFF | 0x200;
  v19 = 3072;
  if ( (_QWORD)v90 )
    v19 = 19456;
  if ( v17 == 3 )
    v20 = v19 | v18;
  else
    v20 = ~v19 & v18;
  v86[3] = v20;
  v92 = 0;
  CurrentProcess = GetCurrentProcess();
  TelemetryHelper::GetProcessTelemetryAppSessionGuid(CurrentProcess, &v92);
  *(struct _GUID *)&v91[4] = v92;
  if ( v86[2] == 3 )
  {
    bstrString = 0;
    v22 = (**(__int64 (__fastcall ***)(struct ICoreWebViewHostProcess *, GUID *, BSTR *))a3)(
            a3,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            &bstrString);
    if ( v22 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x240,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        (const char *)(unsigned int)v22,
        pdwType);
    v23 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = *(_QWORD *)&v73.Data1;
    if ( *(_QWORD *)&v73.Data1 )
    {
      *(_QWORD *)&v73.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    *(_OWORD *)v82 = *(_OWORD *)&v91[4];
    v25 = WebViewManager::CreateCoreWebViewOOPPrivate(
            a2,
            (IUnknown *)bstrString,
            CoreWebViewName,
            (const unsigned __int16 *)*(unsigned int *)v91,
            v86[3],
            v82,
            &v73,
            &v72);
    v27 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24A,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        (const char *)(unsigned int)v25,
        pdwTypeb);
      v28 = bstrString;
      if ( bstrString )
      {
        bstrString = 0;
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v75;
      if ( v75 )
      {
        v75 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = *(_QWORD *)&v73.Data1;
      if ( *(_QWORD *)&v73.Data1 )
      {
        *(_QWORD *)&v73.Data1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      return v27;
    }
    goto LABEL_100;
  }
  v33 = *((_QWORD *)this + 11);
  v34 = 0;
  _InterlockedIncrement(&dword_1800B6D24);
  v35 = -2147467263;
  if ( !hModule )
  {
    EnterCriticalSection(&g_critSecLock);
    if ( !hModule )
    {
      v36 = L"edgehtml.dll";
      if ( v33 < 0x6000400000000LL )
        v36 = L"mshtml.dll";
      Library = LoadLibraryExW(v36, 0, 0);
      hModule = Library;
      if ( Library )
      {
        ProcAddress = (FARPROC)qword_1800B6D28;
        if ( qword_1800B6D28
          || (v34 = -2147467263,
              ProcAddress = GetProcAddress(Library, "InitializeLocalHtmlEngine"),
              (qword_1800B6D28 = (__int64)ProcAddress) != 0) )
        {
          v34 = ((__int64 (__fastcall *)(HMODULE))ProcAddress)(Library);
        }
        if ( v34 >= 0 )
          IEConfiguration_SetBool(536870927, v33 >= 0x6000400000000LL);
      }
      else
      {
        LastError = GetLastError();
        v34 = LastError;
        if ( LastError > 0 )
          v34 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    LeaveCriticalSection(&g_critSecLock);
  }
  if ( v34 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x253,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v34,
      pdwType);
  v40 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = (FARPROC)qword_1800B6D30;
  if ( qword_1800B6D30 || (v41 = GetProcAddress(hModule, "CreateCoreWebView"), (qword_1800B6D30 = (__int64)v41) != 0) )
    v35 = ((__int64 (__fastcall *)(GUID *, struct Windows::Foundation::Private::IComponentSite **))v41)(
            &GUID_f26091c4_5805_4cc0_bcc9_0f078b86949d,
            &v72);
  if ( v35 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v35,
      pdwType);
  bstrString = 0;
  v42 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, BSTR *))this + 5))(
          *((_QWORD *)this + 5),
          &GUID_6a7a1970_f4d0_42ce_b759_ba937b39f22b,
          &bstrString);
  if ( v42 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)v42,
      pdwType);
  v74 = bstrString;
  *(_QWORD *)v73.Data4 = v72;
  Microsoft::WRL::Details::Make<ComponentSiteAdapter,ICoreWebViewPrivate *,IInProcWebViewHost *>(
    &pvData,
    v73.Data4,
    &v74);
  v43 = pvData;
  v44 = *(_QWORD *)&v73.Data1;
  if ( *(_QWORD *)&v73.Data1 )
  {
    *(_QWORD *)&v73.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  Interface = ComponentSiteAdapter::QueryInterface(v43, &GUID_f2a57aa9_917a_48d5_8e22_841e6dae347a, (void **)&v73);
  if ( Interface < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x260,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
      (const char *)(unsigned int)Interface,
      pdwType);
  if ( !*((_QWORD *)this + 12) && *((_QWORD *)this + 11) > 0x6000200010000uLL )
  {
    if ( *((_QWORD *)this + 13) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x26B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        v46);
    if ( *((_QWORD *)this + 14) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x26C,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        v46);
    *(_QWORD *)v73.Data4 = 0;
    v47 = ComponentSiteAdapter::QueryInterface(v43, &GUID_e9842243_de3c_455f_bbf9_3bb34f1df001, (void **)v73.Data4);
    if ( v47 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x26F,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        (const char *)(unsigned int)v47,
        pdwType);
    *(_QWORD *)&v85 = *(_QWORD *)v73.Data4;
    v74 = 0;
    v48 = ComponentSiteAdapter::QueryInterface(v43, &GUID_59087f7a_7312_4e1e_bcc9_fb80f8f0a4d6, &v74);
    if ( v48 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x273,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        (const char *)(unsigned int)v48,
        pdwType);
    *((_QWORD *)&v85 + 1) = v74;
    *(_QWORD *)pcbData = 0;
    v49 = ComponentSiteAdapter::QueryInterface(v43, &GUID_03fb4737_769f_4b1b_a288_a4be9cd1649c, (void **)pcbData);
    if ( v49 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x277,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        (const char *)(unsigned int)v49,
        pdwType);
    v50 = *(_QWORD *)pcbData;
    *(_QWORD *)v86 = *(_QWORD *)pcbData;
    if ( *(_QWORD *)pcbData )
    {
      *(_QWORD *)pcbData = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = *(_QWORD *)v73.Data4;
    if ( *(_QWORD *)v73.Data4 )
    {
      *(_QWORD *)v73.Data4 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
  }
  if ( *((_QWORD *)this + 11) < 0x6000400000000uLL )
    v86[3] &= ~0x2000u;
  else
    SetupHostProcessForServiceWorker(&v86[3]);
  v53 = (*(__int64 (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *, _OWORD *))(*(_QWORD *)v72 + 56LL))(
          v72,
          v83);
  v54 = v53;
  if ( v53 >= 0 )
  {
    if ( (v86[3] & 0x2000) != 0 )
    {
      v59 = (*(__int64 (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *, _QWORD, _QWORD))(*(_QWORD *)v72 + 456LL))(
              v72,
              0,
              0);
      if ( v59 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x28A,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
          (const char *)(unsigned int)v59,
          pdwType);
    }
    if ( v43 )
      ComponentSiteAdapter::Release(v43);
LABEL_100:
    v60 = bstrString;
    if ( bstrString )
    {
      bstrString = 0;
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v72;
    if ( !v72 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x28E,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        v26);
    v62 = *(_QWORD *)&v73.Data1;
    if ( !*(_QWORD *)&v73.Data1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x28F,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
        v26);
    *(_QWORD *)&v73.Data1 = 0;
    *(_QWORD *)a4 = v62;
    v72 = 0;
    *a5 = v61;
    v78 = 0;
    GetSystemTimeAsFileTime(&v78);
    v80 = 0;
    QueryUnbiasedInterruptTime(&v80);
    v63 = *(_QWORD *)&v78 - *(_QWORD *)&SystemTimeAsFileTime;
    v64 = v80 - UnbiasedTime;
    if ( (unsigned int)dword_1800B60D8 > 5
      && (qword_1800B60E8 & 0x400000000000LL) != 0
      && (qword_1800B60F0 & 0x400000000000LL) == qword_1800B60F0 )
    {
      pcbData[0] = v86[2];
      LODWORD(pvData) = v64 / 0x2710;
      *(_DWORD *)v73.Data4 = v63 / 0x2710;
      LODWORD(v74) = 0;
      LODWORD(bstrString) = *(_DWORD *)v91;
      *(_QWORD *)v82 = &v92;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        0x346DC5D63886594BLL,
        (unsigned __int8 *)byte_1800A8039,
        v63,
        0x400000000000LL,
        (__int64 *)v82,
        (__int64)&bstrString,
        (__int64)&v74,
        (__int64)v73.Data4,
        (__int64)&pvData,
        (__int64)pcbData);
    }
    v65 = v75;
    if ( v75 )
    {
      v75 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(*(_QWORD *)v65 + 16LL))(v65, v64, v63);
    }
    v66 = *(_QWORD *)&v73.Data1;
    if ( *(_QWORD *)&v73.Data1 )
    {
      *(_QWORD *)&v73.Data1 = 0;
      (*(void (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(*(_QWORD *)v66 + 16LL))(v66, v64, v63);
    }
    v67 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *, unsigned __int64, unsigned __int64))(*(_QWORD *)v67 + 16LL))(
        v67,
        v64,
        v63);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x285,
    (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\webviewmanager.cpp",
    (const char *)(unsigned int)v53,
    pdwType);
  if ( v43 )
    ComponentSiteAdapter::Release(v43);
  v55 = bstrString;
  if ( bstrString )
  {
    bstrString = 0;
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v55 + 16LL))(v55);
  }
  v56 = v75;
  if ( v75 )
  {
    v75 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  v57 = *(_QWORD *)&v73.Data1;
  if ( *(_QWORD *)&v73.Data1 )
  {
    *(_QWORD *)&v73.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  }
  v58 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Private::IComponentSite *))(*(_QWORD *)v58 + 16LL))(v58);
  }
  return v54;
}

```

## disassembly

```asm
0x180003cc0  push    rbp
0x180003cc2  push    rbx
0x180003cc3  push    rsi
0x180003cc4  push    rdi
0x180003cc5  push    r12
0x180003cc7  push    r13
0x180003cc9  push    r14
0x180003ccb  push    r15
0x180003ccd  lea     rbp, [rsp-2D8h]
0x180003cd5  sub     rsp, 3D8h
0x180003cdc  mov     rax, cs:__security_cookie
0x180003ce3  xor     rax, rsp
0x180003ce6  mov     [rbp+310h+var_50], rax
0x180003ced  mov     r12, r9
0x180003cf0  mov     r14, r8
0x180003cf3  mov     r15, rdx
0x180003cf6  mov     rdi, rcx
0x180003cf9  mov     r13, [rbp+310h+arg_20]
0x180003d00  xor     esi, esi
0x180003d02  mov     qword ptr [rbp+310h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180003d06  lea     rcx, [rbp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003d0a  call    cs:__imp_GetSystemTimeAsFileTime
0x180003d10  mov     [rbp+310h+UnbiasedTime], rsi
0x180003d14  lea     rcx, [rbp+310h+UnbiasedTime]; UnbiasedTime
0x180003d18  call    cs:__imp_QueryUnbiasedInterruptTime
0x180003d1e  mov     rcx, [rbp+318h]; this
0x180003d25  cmp     [rdi+78h], esi
0x180003d28  jz      loc_180004733
0x180003d2e  mov     [rsp+410h+var_3B8], rsi
0x180003d33  mov     qword ptr [rsp+410h+var_3B0.Data1], rsi
0x180003d38  mov     [rsp+410h+var_398], rsi
0x180003d3d  mov     rcx, [rdi+20h]
0x180003d41  mov     rax, [rcx]
0x180003d44  lea     r9, [rsp+410h+var_398]
0x180003d49  lea     r8, _GUID_7bfa68b6_7abe_42ca_bf48_b180ae81cd20
0x180003d50  lea     rdx, qword_18009FCF8
0x180003d57  mov     rax, [rax+18h]
0x180003d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d60  mov     rcx, [rbp+318h]; this
0x180003d67  test    eax, eax
0x180003d69  js      loc_180004745
0x180003d6f  movups  xmm0, xmmword ptr [rdi]
0x180003d72  movups  [rbp+310h+var_350], xmm0
0x180003d76  movups  xmm1, xmmword ptr [rdi+10h]
0x180003d7a  movups  [rbp+310h+var_340], xmm1
0x180003d7e  movups  xmm0, xmmword ptr [rdi+20h]
0x180003d82  movups  [rbp+310h+var_330], xmm0
0x180003d86  movups  xmm1, xmmword ptr [rdi+30h]
0x180003d8a  movups  [rbp+310h+var_320], xmm1
0x180003d8e  movups  xmm0, xmmword ptr [rdi+40h]
0x180003d92  movups  [rbp+310h+var_310], xmm0
0x180003d96  movups  xmm1, xmmword ptr [rdi+50h]
0x180003d9a  movups  [rbp+310h+var_300], xmm1
0x180003d9e  movups  xmm0, xmmword ptr [rdi+60h]
0x180003da2  movups  [rbp+310h+var_2F0], xmm0
0x180003da6  movups  xmm1, xmmword ptr [rdi+70h]
0x180003daa  movups  xmmword ptr [rbp+310h+var_2E0], xmm1
0x180003dae  movups  xmm0, xmmword ptr [rdi+80h]
0x180003db5  movups  [rbp+310h+var_2D0], xmm0
0x180003db9  movups  xmm1, xmmword ptr [rdi+90h]
0x180003dc0  movups  [rbp+310h+var_2C0], xmm1
0x180003dc4  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180003dcb  movups  [rbp+310h+var_2B0], xmm0
0x180003dcf  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180003dd6  movups  [rbp+310h+var_2A0], xmm1
0x180003dda  movups  xmm0, xmmword ptr [rdi+0C0h]
0x180003de1  movups  xmmword ptr [rbp+310h+var_290], xmm0
0x180003de8  mov     rax, [rdi+0D0h]
0x180003def  mov     [rbp+310h+var_280], rax
0x180003df6  mov     rcx, [rsp+410h+var_398]
0x180003dfb  mov     [rsp+410h+bstrString], rsi
0x180003e00  mov     rax, [rcx]
0x180003e03  lea     rdx, [rsp+410h+bstrString]
0x180003e08  mov     rax, [rax+50h]
0x180003e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e11  mov     rcx, [rbp+318h]; this
0x180003e18  test    eax, eax
0x180003e1a  js      loc_18000475A
0x180003e20  cmp     cs:byte_1800B6BA8, sil
0x180003e27  jnz     loc_180003F07
0x180003e2d  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180003e34  call    ReadExecutionModeKey
0x180003e39  mov     ebx, eax
0x180003e3b  mov     cs:dword_1800B6BA4, eax
0x180003e41  test    eax, eax
0x180003e43  jnz     loc_180003EFE
0x180003e49  mov     dword ptr [rbp+310h+SubKey], esi
0x180003e4f  xor     edx, edx; Val
0x180003e51  mov     r8d, 204h; Size
0x180003e57  lea     rcx, [rbp+310h+var_25C]; void *
0x180003e5e  call    memset_0
0x180003e63  mov     rax, [rsp+410h+bstrString]
0x180003e68  mov     [rsp+410h+pdwType], rax; int
0x180003e6d  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180003e74  lea     r8, aSS; "%s\\%s"
0x180003e7b  mov     edx, 104h; unsigned __int64
0x180003e80  lea     rcx, [rbp+310h+SubKey]; unsigned __int16 *
0x180003e87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e8c  mov     rcx, [rbp+318h]; this
0x180003e93  test    eax, eax
0x180003e95  js      loc_18000476F
0x180003e9b  mov     dword ptr [rbp+310h+var_388], esi
0x180003e9e  mov     [rbp+310h+var_390], 4
0x180003ea5  lea     rax, [rbp+310h+var_390]
0x180003ea9  mov     [rsp+410h+pcbData], rax; pcbData
0x180003eae  lea     rax, [rbp+310h+var_388]
0x180003eb2  mov     [rsp+410h+pvData], rax; pvData
0x180003eb7  mov     [rsp+410h+pdwType], rsi; pdwType
0x180003ebc  mov     r9d, 10h; dwFlags
0x180003ec2  lea     r8, Value; "ExecutionMode"
0x180003ec9  lea     rdx, [rbp+310h+SubKey]; lpSubKey
0x180003ed0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180003ed7  call    cs:__imp_RegGetValueW
0x180003edd  test    eax, eax
0x180003edf  jz      short loc_180003EF5
0x180003ee1  mov     ebx, esi
0x180003ee3  mov     rcx, [rbp+318h]; this
0x180003eea  cmp     eax, 57h ; 'W'
0x180003eed  jz      loc_180004721
0x180003ef3  jmp     short loc_180003EF8
0x180003ef5  mov     ebx, dword ptr [rbp+310h+var_388]
0x180003ef8  mov     cs:dword_1800B6BA4, ebx
0x180003efe  mov     cs:byte_1800B6BA8, 1
0x180003f05  jmp     short loc_180003F0D
0x180003f07  mov     ebx, cs:dword_1800B6BA4
0x180003f0d  mov     rcx, [rbp+318h]; this
0x180003f14  cmp     ebx, 3
0x180003f17  ja      loc_180004784
0x180003f1d  mov     rcx, [rsp+410h+bstrString]; bstrString
0x180003f22  test    rcx, rcx
0x180003f25  jz      short loc_180003F2D
0x180003f27  call    cs:__imp_SysFreeString
0x180003f2d  mov     rcx, qword ptr [rbp+310h+var_300+8]
0x180003f31  call    GetCoreWebViewName
0x180003f36  mov     rsi, rax
0x180003f39  mov     qword ptr [rbp+310h+var_350], rax
0x180003f3d  mov     qword ptr [rbp+310h+var_350+8], rax
0x180003f41  mov     ecx, 1
0x180003f46  lock xadd cs:dword_1800B6BA0, ecx
0x180003f4e  inc     ecx
0x180003f50  mov     dword ptr [rbp+310h+var_290], ecx
0x180003f56  mov     edx, [rbp+310h+var_2E0+8]
0x180003f59  test    ebx, ebx
0x180003f5b  cmovnz  edx, ebx
0x180003f5e  mov     [rbp+310h+var_2E0+8], edx
0x180003f61  mov     eax, [rbp+310h+var_2E0+0Ch]
0x180003f64  cmp     edx, 1
0x180003f67  jz      short loc_180003F73
0x180003f69  btr     eax, 0Fh
0x180003f6d  bts     eax, 9
0x180003f71  jmp     short loc_180003F7B
0x180003f73  btr     eax, 9
0x180003f77  bts     eax, 0Fh
0x180003f7b  mov     ecx, 0C00h
0x180003f80  mov     r8d, 4C00h
0x180003f86  cmp     qword ptr [rbp+310h+var_2A0], 0
0x180003f8b  cmovnz  ecx, r8d
0x180003f8f  cmp     edx, 3
0x180003f92  jnz     short loc_180003F98
0x180003f94  or      eax, ecx
0x180003f96  jmp     short loc_180003F9C
0x180003f98  not     ecx
0x180003f9a  and     eax, ecx
0x180003f9c  mov     [rbp+310h+var_2E0+0Ch], eax
0x180003f9f  xorps   xmm0, xmm0
0x180003fa2  movups  xmmword ptr [rbp+310h+var_270.Data1], xmm0
0x180003fa9  call    cs:__imp_GetCurrentProcess
0x180003faf  lea     rdx, [rbp+310h+var_270]; struct _GUID *
0x180003fb6  mov     rcx, rax; void *
0x180003fb9  call    ?GetProcessTelemetryAppSessionGuid@TelemetryHelper@@SAJPEAXPEAU_GUID@@@Z; TelemetryHelper::GetProcessTelemetryAppSessionGuid(void *,_GUID *)
0x180003fbe  movups  xmm0, xmmword ptr [rbp+310h+var_270.Data1]
0x180003fc5  movups  xmmword ptr [rbp+310h+var_290+4], xmm0
0x180003fcc  cmp     [rbp+310h+var_2E0+8], 3
0x180003fd0  jnz     loc_18000412B
0x180003fd6  mov     [rsp+410h+bstrString], 0
0x180003fdf  mov     rax, [r14]
0x180003fe2  lea     r8, [rsp+410h+bstrString]
0x180003fe7  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180003fee  mov     rcx, r14
0x180003ff1  mov     rax, [rax]
0x180003ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff9  mov     rcx, [rbp+318h]; this
0x180004000  test    eax, eax
0x180004002  js      loc_180004796
0x180004008  mov     rcx, [rsp+410h+var_3B8]
0x18000400d  xor     r14d, r14d
0x180004010  test    rcx, rcx
0x180004013  jz      short loc_180004027
0x180004015  mov     [rsp+410h+var_3B8], r14
0x18000401a  mov     rax, [rcx]
0x18000401d  mov     rax, [rax+10h]
0x180004021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004026  nop
0x180004027  mov     rcx, qword ptr [rsp+410h+var_3B0.Data1]
0x18000402c  test    rcx, rcx
0x18000402f  jz      short loc_180004043
0x180004031  mov     qword ptr [rsp+410h+var_3B0.Data1], r14
0x180004036  mov     rax, [rcx]
0x180004039  mov     rax, [rax+10h]
0x18000403d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004042  nop
0x180004043  movups  xmm0, xmmword ptr [rbp+310h+var_290+4]
0x18000404a  movaps  xmmword ptr [rbp+310h+var_360], xmm0
0x18000404e  lea     rax, [rsp+410h+var_3B8]
0x180004053  mov     [rsp+410h+var_3D8], rax; struct Windows::Foundation::Private::IComponentSite **
0x180004058  lea     rax, [rsp+410h+var_3B0]
0x18000405d  mov     [rsp+410h+pcbData], rax; struct _GUID
0x180004062  lea     rax, [rbp+310h+var_360]
0x180004066  mov     [rsp+410h+pvData], rax; unsigned int
0x18000406b  mov     eax, [rbp+310h+var_2E0+0Ch]
0x18000406e  mov     dword ptr [rsp+410h+pdwType], eax; int
0x180004072  mov     r9d, dword ptr [rbp+310h+var_290]; unsigned __int16 *
0x180004079  mov     r8, rsi; struct IInspectable *
0x18000407c  mov     rdx, [rsp+410h+bstrString]; struct ICoreWebViewHostProcess *
0x180004081  mov     rcx, r15; this
0x180004084  call    ?CreateCoreWebViewOOPPrivate@WebViewManager@@YAJPEAUICoreWebViewHostProcess@@PEAUIInspectable@@PEBGIKU_GUID@@PEAPEAUIComponentSite@Private@Foundation@Windows@@PEAPEAUICoreWebViewPrivate@@@Z; WebViewManager::CreateCoreWebViewOOPPrivate(ICoreWebViewHostProcess *,IInspectable *,ushort const *,uint,ulong,_GUID,Windows::Foundation::Private::IComponentSite * *,ICoreWebViewPrivate * *)
0x180004089  mov     ebx, eax
0x18000408b  test    eax, eax
0x18000408d  jns     loc_180004126
0x180004093  mov     rcx, [rbp+318h]; this
0x18000409a  mov     r9d, eax; char *
0x18000409d  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800040a4  mov     edx, 24Ah; void *
0x1800040a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040ae  nop
0x1800040af  mov     rcx, [rsp+410h+bstrString]
0x1800040b4  test    rcx, rcx
0x1800040b7  jz      short loc_1800040CB
0x1800040b9  mov     [rsp+410h+bstrString], r14
0x1800040be  mov     rax, [rcx]
0x1800040c1  mov     rax, [rax+10h]
0x1800040c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ca  nop
0x1800040cb  mov     rcx, [rsp+410h+var_398]
0x1800040d0  test    rcx, rcx
0x1800040d3  jz      short loc_1800040E7
0x1800040d5  mov     [rsp+410h+var_398], r14
0x1800040da  mov     rax, [rcx]
0x1800040dd  mov     rax, [rax+10h]
0x1800040e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040e6  nop
0x1800040e7  mov     rcx, qword ptr [rsp+410h+var_3B0.Data1]
0x1800040ec  test    rcx, rcx
0x1800040ef  jz      short loc_180004103
0x1800040f1  mov     qword ptr [rsp+410h+var_3B0.Data1], r14
0x1800040f6  mov     rax, [rcx]
0x1800040f9  mov     rax, [rax+10h]
0x1800040fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004102  nop
0x180004103  mov     rcx, [rsp+410h+var_3B8]
0x180004108  test    rcx, rcx
0x18000410b  jz      short loc_18000411F
0x18000410d  mov     [rsp+410h+var_3B8], r14
0x180004112  mov     rax, [rcx]
0x180004115  mov     rax, [rax+10h]
0x180004119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411e  nop
0x18000411f  mov     eax, ebx
0x180004121  jmp     loc_1800046EC
0x180004126  jmp     loc_180004548
0x18000412b  mov     r14, [rdi+58h]
0x18000412f  xor     ebx, ebx
0x180004131  mov     rax, 6000400000000h
0x18000413b  cmp     r14, rax
0x18000413e  setnb   r15b
0x180004142  lock inc cs:dword_1800B6D24
0x180004149  mov     esi, 80004001h
0x18000414e  cmp     cs:hModule, rbx
0x180004155  jnz     loc_180004213
0x18000415b  lea     rcx, ?g_critSecLock@@3VTridentVersionHelper_StaticLock@@A; lpCriticalSection
0x180004162  call    cs:__imp_EnterCriticalSection
0x180004168  cmp     cs:hModule, rbx
0x18000416f  jnz     loc_180004206
0x180004175  lea     rax, LibFileName; "mshtml.dll"
0x18000417c  lea     rcx, aEdgehtmlDll; "edgehtml.dll"
0x180004183  mov     rdx, 6000400000000h
0x18000418d  cmp     r14, rdx
0x180004190  cmovb   rcx, rax; lpLibFileName
0x180004194  xor     r8d, r8d; dwFlags
0x180004197  xor     edx, edx; hFile
0x180004199  call    cs:__imp_LoadLibraryExW
0x18000419f  mov     rcx, rax; hModule
0x1800041a2  mov     cs:hModule, rax
0x1800041a9  test    rax, rax
0x1800041ac  jz      short loc_1800041F1
0x1800041ae  mov     rax, cs:qword_1800B6D28
0x1800041b5  test    rax, rax
0x1800041b8  jnz     short loc_1800041D5
0x1800041ba  mov     ebx, esi
0x1800041bc  lea     rdx, aInitializeloca; "InitializeLocalHtmlEngine"
0x1800041c3  call    cs:__imp_GetProcAddress
0x1800041c9  mov     cs:qword_1800B6D28, rax
0x1800041d0  test    rax, rax
0x1800041d3  jz      short loc_1800041DC
0x1800041d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041da  mov     ebx, eax
0x1800041dc  test    ebx, ebx
0x1800041de  js      short loc_180004206
0x1800041e0  movzx   edx, r15b
0x1800041e4  mov     ecx, 2000000Fh
  ... truncated ...
```
