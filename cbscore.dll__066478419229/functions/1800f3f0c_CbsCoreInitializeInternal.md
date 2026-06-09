# CbsCoreInitializeInternal

- ea: `0x1800f3f0c`
- end: `0x1800f5232`
- name: `CbsCoreInitializeInternal`
- size: `4902`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f5a80`

## callees

- `0x18000b3f0`
- `0x18000b46c`
- `0x180010cc0`
- `0x180010f54`
- `0x1800110d0`
- `0x180013250`
- `0x18003330c`
- `0x180034954`
- `0x1800441fc`
- `0x1800499e0`
- `0x18004a920`
- `0x180051dd4`
- `0x180059160`
- `0x18005b7e4`
- `0x180064cb0`
- `0x180095924`
- `0x180095e34`
- `0x180096e6c`
- `0x18009753c`
- `0x180097bd0`
- `0x180098538`
- `0x1800986f4`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a02ec`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800b0b0c`
- `0x1800b32cc`
- `0x1800c5e14`
- `0x1800c6c0c`
- `0x1800cf2f0`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800f1eb4`
- `0x1800f203c`
- `0x1800f384c`
- `0x1800f3a04`
- `0x1800f3ca8`
- `0x1800f3f0c`
- `0x1800f5238`
- `0x1800f5288`
- `0x1800f574c`
- `0x1800f580c`
- `0x1800ff418`
- `0x18010a68c`
- `0x18010b49c`
- `0x18010d06c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800f4524`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800f4524`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1800f4345`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1800f4345`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f4675`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f4675`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f462a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800f462a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4e6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4fb9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f5060`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4e6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4f12`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f4fb9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f5060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f507c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4fd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f507c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800f5109`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800f5109`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800f4561`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800f4561`

## string_xrefs

- `0x1800f451d`: `wdscore.dll`
- `0x1800f40f6`: `Invalid InstanceCreated callback passed in.`
- `0x1800f428f`: `Failed to acquire backup and restore privileges.`
- `0x1800f4378`: `Failed to get Core DLL's path.`
- `0x1800f4439`: `Failed to find the cbscore.dll in the path: {}`
- `0x1800f44c9`: `Failed to copy core DLL path into servicing stack directory string: {}`
- `0x1800f4662`: `Open of SC_BOOT_SERVICING_DONE event failed {}`
- `0x1800f46bb`: `Unable to load catalog installation apis (possibly expected).`
- `0x1800f46cd`: `Offline servicing, skipping online catalog installation`
- `0x1800f4822`: `Failed opening SYSTEM key`
- `0x1800f49b5`: `Failed to load DPX DLL.`
- `0x1800f4a2c`: `Failed to load WCP DLL.`
- `0x1800f4a96`: `Failed to load DrUpdate DLL.`
- `0x1800f4ae2`: `Unable to load CfgMgr32 DLL.`
- `0x1800f4af7`: `Unable to load SrClient DLL, continuing without restore point support.`
- `0x1800f4b31`: `Failed to load TurboStack DLL.`
- `0x1800f4d4b`: `Failed to initialize component analyzer`
- `0x1800f4e1a`: `Failed to create class factory.`

## pseudocode

```c
__int64 __fastcall CbsCoreInitializeInternal(
        struct IMalloc *a1,
        __int64 a2,
        void (*a3)(void),
        void (*a4)(void),
        void (*a5)(void),
        void (*a6)(void),
        void (*a7)(void),
        __int64 a8)
{
  unsigned int v12; // ebx
  __int64 v13; // rdx
  signed int v14; // eax
  DWORD ModuleFileNameW; // eax
  signed int LastError; // ebx
  int v17; // edx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // edx
  signed int v22; // eax
  int v23; // edx
  unsigned int v24; // ebx
  wchar_t *v25; // rax
  DWORD v26; // ebx
  unsigned int v27; // eax
  signed int v28; // eax
  int v29; // edx
  int v30; // edx
  HKEY *InitPointer; // rax
  int v32; // ebx
  int v33; // edx
  unsigned int v34; // eax
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // edx
  unsigned int v38; // eax
  int v39; // edx
  int v40; // eax
  HINSTANCE *v41; // rdx
  int v42; // edx
  int v43; // eax
  int v44; // edx
  int v45; // eax
  HINSTANCE *v46; // rdx
  int v47; // edx
  int v48; // eax
  HINSTANCE *v49; // rdx
  const wchar_t *v50; // rcx
  int v51; // edx
  unsigned int v52; // eax
  HINSTANCE *v53; // rcx
  unsigned int v54; // eax
  int v55; // eax
  HINSTANCE *v56; // rdx
  int v57; // edx
  unsigned int v58; // eax
  int v59; // eax
  int v60; // edx
  int v61; // eax
  int v62; // edx
  int v63; // eax
  int v64; // edx
  int v65; // eax
  int v66; // edx
  int v67; // eax
  int v68; // edx
  int v69; // eax
  int v70; // edx
  int ClassFactory; // eax
  int v72; // edx
  int v73; // edx
  unsigned int v74; // eax
  int v75; // edx
  unsigned int v76; // eax
  int v77; // edx
  unsigned int v78; // eax
  int v79; // edx
  unsigned int v80; // eax
  CServicingStackMemoryProfiler *v81; // rax
  CServicingStackMemoryProfiler *v82; // rax
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v86; // [rsp+20h] [rbp-E0h]
  unsigned int v87[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v88; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v89[2]; // [rsp+70h] [rbp-90h] BYREF
  char v90; // [rsp+80h] [rbp-80h]
  void (*v91)(void); // [rsp+88h] [rbp-78h]
  HMODULE phModule; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v93; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v94; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v95; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v96; // [rsp+ACh] [rbp-54h] BYREF
  HKEY v97; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-48h] BYREF
  int v99; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t v100[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Filename[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  v89[1] = &vCoreInitializeLock;
  *(_QWORD *)v87 = a2;
  v89[0] = &PackageTrackerLocker::`vftable';
  v91 = a3;
  v90 = 0;
  memset_0(Filename, 0, 0x208u);
  memset_0(v100, 0, 0x208u);
  v93 = 0;
  v95 = 0;
  phModule = 0;
  SystemTime = 0;
  if ( !a1 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid Malloc pointer passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 280;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\core\\cbscoreinitialization.cpp",
      (const char *)v12,
      v86);
    goto LABEL_184;
  }
  if ( !a2 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid TiLockProcess function passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 281;
    goto LABEL_33;
  }
  if ( !a3 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid TiUnlockProcess function passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 282;
    goto LABEL_33;
  }
  if ( !a4 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid InstanceCreated callback passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 283;
    goto LABEL_33;
  }
  if ( !a5 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid InstanceDestroyed callback passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 284;
    goto LABEL_33;
  }
  if ( !a7 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Invalid RequireShutdownProcessing callback passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 285;
    goto LABEL_33;
  }
  if ( !a8 )
  {
    v12 = -2147467261;
    v93 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid ClassFactory pointer passed in.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 286;
    goto LABEL_33;
  }
  v14 = EnableBackupRestorePrivileges();
  v12 = v14;
  if ( v14 < 0 )
  {
    v93 = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to acquire backup and restore privileges.");
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 289;
    goto LABEL_33;
  }
  if ( !CbsRegQueryDWORDValue(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Tracing", 1u, L"CbsCheckRefCount", &v93) )
  {
    LogAdapter::TraceAtLevel<>(
      1,
      "CbsCheckRefCount flag is set, CBS object addref/release information will be saved to log");
    vbTraceInterfaceRefCount = 1;
  }
  ModuleFileNameW = GetModuleFileNameW(vhInstance, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get Core DLL's path.");
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      else
        v18 = LastError;
      v93 = v18;
      LOBYTE(v17) = 1;
      v88 = (wchar_t *)&v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {0}",
        (__int64)&v88);
    }
    if ( LastError )
    {
      v19 = 302;
LABEL_44:
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v19,
              (unsigned int)"onecore\\base\\cbs\\core\\cbscoreinitialization.cpp",
              (const char *)(unsigned int)LastError,
              v86);
      goto LABEL_184;
    }
    goto LABEL_183;
  }
  if ( ModuleFileNameW == 260 )
  {
    v12 = -2147024774;
    goto LABEL_184;
  }
  v20 = FileFromPath(Filename);
  if ( !v20 )
  {
    v12 = -2147418113;
    v93 = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t [12]>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to find the cbscore.dll in the path: {}",
        (__int64)Filename);
      v88 = (wchar_t *)&v93;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 310;
    goto LABEL_33;
  }
  v22 = StringCchCopyNW(v100, 0x104u, Filename, (v20 - (__int64)Filename) >> 1);
  v12 = v22;
  if ( v22 < 0 )
  {
    v93 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t [12]>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to copy core DLL path into servicing stack directory string: {}",
        (__int64)Filename);
      v88 = (wchar_t *)&v93;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 314;
    goto LABEL_33;
  }
  MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v89);
  if ( GetModuleHandleExW(0, L"wdscore.dll", &phModule) )
    WdsPostLoad(phModule);
  else
    WdsLoad(v100, vhInstance);
  LogAdapter::g_Logger = (struct LogAdapter::Logger *)&vWdsLogger;
  GetSystemTime(&SystemTime);
  CBSWdsLog(
    0x4000000,
    0,
    0,
    "Universal Time is: %04d-%02d-%02d %02d:%02d:%02d.%03d",
    SystemTime.wYear,
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond,
    SystemTime.wMilliseconds);
  v24 = CbsTransactionInitialize(vbOfflineStack | (unsigned int)vbInTestMode);
  if ( v24 == 1 )
    LogAdapter::TraceAtLevel<>(1, "Kernel transactions are disabled, continuing without transaction support.");
  LogAdapter::TraceAtLevelIfFailed<long,>(
    1,
    v24,
    "Unable to load and initialize KTM, continuing without transaction support.");
  ConfigGetProperty(0, L"DisablePSRL", &v95);
  if ( v95 )
    SetCbsCoreMode(4, 1);
  v25 = (wchar_t *)OpenEventW(0x100000u, 0, L"Global\\SC_BOOT_SERVICING_DONE");
  v88 = v25;
  if ( (((unsigned __int64)v25 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v26 = WaitForSingleObject(v25, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v88,
      0);
    if ( v26 == 258 )
      SetCbsCoreMode(2, 1);
  }
  else
  {
    v93 = GetLastError();
    if ( v93 != 2 )
      LogAdapter::TraceAtLevel<unsigned long>(1, "Open of SC_BOOT_SERVICING_DONE event failed {}", &v93);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v88);
  if ( vbOfflineStack )
  {
    LogAdapter::TraceAtLevel<>(1, "Offline servicing, skipping online catalog installation");
  }
  else
  {
    v27 = CbsCatalogInstallationApiLoad();
    LogAdapter::TraceAtLevelIfFailed<long,>(1, v27, "Unable to load catalog installation apis (possibly expected).");
  }
  AppContainerLoad();
  v28 = DetermineServicingStackVersion(Filename, v100);
  v12 = v28;
  if ( v28 < 0 )
  {
    v93 = v28;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to determine servicing stack version.");
      v88 = (wchar_t *)&v93;
      LOBYTE(v29) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v29,
        3,
        (unsigned int)": {}",
        (__int64)&v88);
    }
    v13 = 394;
    goto LABEL_33;
  }
  if ( vbOfflineStack )
  {
    SetCbsCoreMode(1, 1);
    if ( vbOfflineStack )
    {
LABEL_91:
      v38 = InitializeRebootInProgressFlag();
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v38, "Unable to get reboot in progress volatile key");
      v40 = CoreResourcesLoad(v100, v39);
      v12 = v40;
      if ( v40 < 0 )
      {
        LODWORD(v94) = v40;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize core resources.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v42) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v42,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 466;
        goto LABEL_33;
      }
      v43 = DpxLoad(v100, v41);
      v12 = v43;
      if ( v43 < 0 )
      {
        LODWORD(v94) = v43;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load DPX DLL.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v44) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v44,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 468;
        goto LABEL_33;
      }
      v45 = WcpLoad(v100, vbOfflineStack, &vhWcpDll);
      v12 = v45;
      if ( v45 < 0 )
      {
        LODWORD(v94) = v45;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load WCP DLL.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v47) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v47,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 470;
        goto LABEL_33;
      }
      v48 = DrupLoad(v100, v46);
      v12 = v48;
      if ( v48 < 0 )
      {
        LODWORD(v94) = v48;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load DrUpdate DLL.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v51) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v51,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 472;
        goto LABEL_33;
      }
      v52 = CfgMgr32Load(v50, v49);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v52, "Unable to load CfgMgr32 DLL.");
      v54 = SrLoad(v53);
      LogAdapter::TraceAtLevelIfFailed<long,>(
        1,
        v54,
        "Unable to load SrClient DLL, continuing without restore point support.");
      v55 = TurboStackLoad(v100, &vhTurboStackDll);
      v12 = v55;
      if ( v55 < 0 )
      {
        LODWORD(v94) = v55;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load TurboStack DLL.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v57) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v57,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 478;
        goto LABEL_33;
      }
      v58 = TurboContainerLoad(v100, v56);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, v58, "Continuing without TurboContainer support.");
      v59 = WcpSetIsolationIMalloc(a1);
      v12 = v59;
      if ( v59 < 0 )
      {
        LODWORD(v94) = v59;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set IMalloc for CSI.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v60) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v60,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 482;
        goto LABEL_33;
      }
      v61 = SessionManagerInitialize();
      v12 = v61;
      if ( v61 < 0 )
      {
        LODWORD(v94) = v61;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize session manager.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v62) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v62,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 488;
        goto LABEL_33;
      }
      v63 = CapabilityManagerInitialize();
      v12 = v63;
      if ( v63 < 0 )
      {
        LODWORD(v94) = v63;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize session manager.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v64) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v64,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 490;
        goto LABEL_33;
      }
      v65 = PublicObjectMonitorInitialize();
      v12 = v65;
      if ( v65 < 0 )
      {
        LODWORD(v94) = v65;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize public object monitor.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v66) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v66,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 492;
        goto LABEL_33;
      }
      v67 = ComponentAnalyzerInitialize();
      v12 = v67;
      if ( v67 < 0 )
      {
        LODWORD(v94) = v67;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize component analyzer");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v68) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v68,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 494;
        goto LABEL_33;
      }
      v69 = ExecutionEngineInitialize();
      v12 = v69;
      if ( v69 < 0 )
      {
        LODWORD(v94) = v69;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize execution engine.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v70) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v70,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 496;
        goto LABEL_33;
      }
      ClassFactory = CreateClassFactory(a8);
      v12 = ClassFactory;
      if ( ClassFactory < 0 )
      {
        LODWORD(v94) = ClassFactory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create class factory.");
          *(_QWORD *)v87 = &v94;
          LOBYTE(v72) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v72,
            3,
            (unsigned int)": {}",
            (__int64)v87);
        }
        v13 = 498;
        goto LABEL_33;
      }
      vhNoActiveSessions = CreateEventW(0, 1, 1, 0);
      if ( vhNoActiveSessions )
      {
        vhPauseIdleProcessing = CreateEventW(0, 1, 1, 0);
        if ( vhPauseIdleProcessing )
        {
          vhIdleProcessingPaused = CreateEventW(0, 1, 1, 0);
          if ( vhIdleProcessingPaused )
          {
            vhStopIdleProcessing = CreateEventW(0, 1, 1, 0);
            if ( vhStopIdleProcessing )
            {
              if ( GetEnvironmentVariableW(L"TRACK_WCP_MEMORY_USAGE", 0, 0) )
              {
                v81 = (CServicingStackMemoryProfiler *)operator new(0xC8u);
                if ( v81 )
                {
                  v82 = CServicingStackMemoryProfiler::CServicingStackMemoryProfiler(v81);
                  vpCbsMemoryProfiler = v82;
                  if ( v82 )
                  {
                    *((_DWORD *)v82 + 33) = 1;
                    CServicingStackMemoryProfiler::ResetAll(v82);
                  }
                }
                else
                {
                  vpCbsMemoryProfiler = 0;
                }
              }
              if ( (vdwCbsCoreMode & 2) == 0 )
                CbsCoreInitializePhase2();
              if ( !vbOfflineStack )
              {
                v83 = CbsEventRegister();
                LogAdapter::TraceAtLevelIfFailed<long,>(
                  1,
                  v83,
                  "Unable to register with event system.  We will continue without events.");
              }
              v84 = CbsOneSettingsInitialize();
              LogAdapter::TraceAtLevelIfFailed<long,>(1, v84, "Unable to initialize onesettings.");
              ((void (__fastcall *)(struct IMalloc *))a1->lpVtbl->AddRef)(a1);
              if ( vpMalloc )
                ((void (__fastcall *)(struct IMalloc *))vpMalloc->lpVtbl->Release)(vpMalloc);
              vpfnTiLockProcess = *(int (**)(int))v87;
              vpfnTiUnlockProcess = v91;
              vpfnRequireShutdownNow = a6;
              vpMalloc = a1;
              vpfnInstanceCreated = a4;
              vpfnInstanceDestroyed = a5;
              vpfnRequireShutdownProcessing = a7;
            }
            else
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed creating StopIdleProcessing event");
                if ( LastError > 0 )
                  v80 = (unsigned __int16)LastError | 0x80070000;
                else
                  v80 = LastError;
                LODWORD(v94) = v80;
                LOBYTE(v79) = 1;
                *(_QWORD *)v87 = &v94;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v79,
                  3,
                  (unsigned int)": {0}",
                  (__int64)v87);
              }
              if ( LastError )
              {
                v19 = 510;
                goto LABEL_44;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed creating IdleProcessingPaused event");
              if ( LastError > 0 )
                v78 = (unsigned __int16)LastError | 0x80070000;
              else
                v78 = LastError;
              LODWORD(v94) = v78;
              LOBYTE(v77) = 1;
              *(_QWORD *)v87 = &v94;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v77,
                3,
                (unsigned int)": {0}",
                (__int64)v87);
            }
            if ( LastError )
            {
              v19 = 507;
              goto LABEL_44;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed creating PauseIdleProcessing event");
            if ( LastError > 0 )
              v76 = (unsigned __int16)LastError | 0x80070000;
            else
              v76 = LastError;
            LODWORD(v94) = v76;
            LOBYTE(v75) = 1;
            *(_QWORD *)v87 = &v94;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v75,
              3,
              (unsigned int)": {0}",
              (__int64)v87);
          }
          if ( LastError )
          {
            v19 = 504;
            goto LABEL_44;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed creating NoActiveSessions event");
          if ( LastError > 0 )
            v74 = (unsigned __int16)LastError | 0x80070000;
          else
            v74 = LastError;
          LODWORD(v94) = v74;
          LOBYTE(v73) = 1;
          *(_QWORD *)v87 = &v94;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v73,
            3,
            (unsigned int)": {0}",
            (__int64)v87);
        }
        if ( LastError )
        {
          v19 = 501;
          goto LABEL_44;
        }
      }
LABEL_183:
      v12 = 0;
      goto LABEL_184;
    }
  }
  v88 = 0;
  if ( !(unsigned int)CbsRegQueryStringValue(
                        HKEY_LOCAL_MACHINE,
                        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                        1u,
                        L"BuildLabEx",
                        &v88) )
  {
    v94 = v88;
    if ( LogAdapter::g_Logger )
    {
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        1,
        (unsigned int)"Build: {}",
        (__int64)&v94);
    }
  }
  v95 = 0;
  v93 = 0;
  v99 = 0;
  v97 = 0;
  InitPointer = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v97);
  v32 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet", 0, 0x20019u, InitPointer);
  if ( !v32 )
  {
    if ( HelperIsImageLayercake(v97) )
      v95 = 1;
    v37 = 0;
    v96 = 0;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<unsigned long,unsigned long,unsigned long,unsigned long>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        v35,
        v36,
        (__int64)&v95,
        (__int64)&v96,
        (__int64)&v93,
        (__int64)&v99);
      v37 = v96;
    }
    CbsReportOverlayStatus(v95, v37, v93);
    Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v97);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v88);
    goto LABEL_91;
  }
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed opening SYSTEM key");
    if ( v32 > 0 )
      v34 = (unsigned __int16)v32 | 0x80070000;
    else
      v34 = v32;
    LODWORD(v94) = v34;
    LOBYTE(v33) = 1;
    *(_QWORD *)v87 = &v94;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v33,
      3,
      (unsigned int)": {0}",
      (__int64)v87);
  }
  v12 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x1A8,
          (unsigned int)"onecore\\base\\cbs\\core\\cbscoreinitialization.cpp",
          (const char *)(unsigned int)v32,
          v86);
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v97);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v88);
LABEL_184:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v89);
  return v12;
}

```

## disassembly

```asm
0x1800f3f0c  push    rbp
0x1800f3f0e  push    rbx
0x1800f3f0f  push    rsi
0x1800f3f10  push    rdi
0x1800f3f11  push    r12
0x1800f3f13  push    r13
0x1800f3f15  push    r14
0x1800f3f17  push    r15
0x1800f3f19  lea     rbp, [rsp-408h]
0x1800f3f21  sub     rsp, 508h
0x1800f3f28  mov     rax, cs:__security_cookie
0x1800f3f2f  xor     rax, rsp
0x1800f3f32  mov     [rbp+440h+var_50], rax
0x1800f3f39  mov     r14, [rbp+440h+arg_38]
0x1800f3f40  lea     rax, ?vCoreInitializeLock@@3UMonitoredCritSec@@A; MonitoredCritSec vCoreInitializeLock
0x1800f3f47  mov     rbx, r8
0x1800f3f4a  mov     [rsp+540h+var_4C8], rax
0x1800f3f4f  lea     rax, ??_7PackageTrackerLocker@@6B@; const PackageTrackerLocker::`vftable'
0x1800f3f56  mov     qword ptr [rsp+540h+var_4E0], rdx
0x1800f3f5b  mov     rsi, rdx
0x1800f3f5e  mov     [rsp+540h+var_4D0], rax
0x1800f3f63  mov     rdi, rcx
0x1800f3f66  mov     [rbp+440h+var_4B8], rbx
0x1800f3f6a  mov     r15d, 208h
0x1800f3f70  mov     [rbp+440h+var_4C0], 0
0x1800f3f74  mov     r8d, r15d; Size
0x1800f3f77  lea     rcx, [rbp+440h+Filename]; void *
0x1800f3f7e  xor     edx, edx; Val
0x1800f3f80  mov     r13, r9
0x1800f3f83  call    memset_0
0x1800f3f88  mov     r8d, r15d; Size
0x1800f3f8b  lea     rcx, [rbp+440h+var_470]; void *
0x1800f3f8f  xor     edx, edx; Val
0x1800f3f91  call    memset_0
0x1800f3f96  xor     eax, eax
0x1800f3f98  xorps   xmm0, xmm0
0x1800f3f9b  mov     [rbp+440h+var_4A8], eax
0x1800f3f9e  mov     [rbp+440h+var_498], eax
0x1800f3fa1  mov     [rbp+440h+phModule], rax
0x1800f3fa5  movups  xmmword ptr [rbp+440h+SystemTime.wYear], xmm0
0x1800f3fa9  test    rdi, rdi
0x1800f3fac  jnz     short loc_1800F400C
0x1800f3fae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f3fb5  mov     ebx, 80004003h
0x1800f3fba  mov     [rbp+440h+var_4A8], ebx
0x1800f3fbd  test    rcx, rcx
0x1800f3fc0  jz      short loc_1800F4002
0x1800f3fc2  lea     edi, [rax+3]
0x1800f3fc5  xor     edx, edx
0x1800f3fc7  mov     r8d, edi
0x1800f3fca  lea     r9, aInvalidMallocP; "Invalid Malloc pointer passed in."
0x1800f3fd1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f3fd6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f3fdd  lea     rax, [rbp+440h+var_4A8]
0x1800f3fe1  mov     [rsp+540h+var_4D8], rax
0x1800f3fe6  lea     r9, asc_1802EE7AC; ": {}"
0x1800f3fed  lea     rax, [rsp+540h+var_4D8]
0x1800f3ff2  mov     r8d, edi
0x1800f3ff5  lea     edx, [rdi-2]
0x1800f3ff8  mov     [rsp+540h+var_520], rax
0x1800f3ffd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f4002  mov     edx, 118h
0x1800f4007  jmp     loc_1800F42D1
0x1800f400c  test    rsi, rsi
0x1800f400f  jnz     short loc_1800F406F
0x1800f4011  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4018  mov     ebx, 80004003h
0x1800f401d  mov     [rbp+440h+var_4A8], ebx
0x1800f4020  test    rcx, rcx
0x1800f4023  jz      short loc_1800F4065
0x1800f4025  lea     edi, [rsi+3]
0x1800f4028  xor     edx, edx
0x1800f402a  mov     r8d, edi
0x1800f402d  lea     r9, aInvalidTilockp; "Invalid TiLockProcess function passed i"...
0x1800f4034  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f4039  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4040  lea     rax, [rbp+440h+var_4A8]
0x1800f4044  mov     [rsp+540h+var_4D8], rax
0x1800f4049  lea     r9, asc_1802EE7AC; ": {}"
0x1800f4050  lea     rax, [rsp+540h+var_4D8]
0x1800f4055  mov     r8d, edi
0x1800f4058  lea     edx, [rsi+1]
0x1800f405b  mov     [rsp+540h+var_520], rax
0x1800f4060  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f4065  mov     edx, 119h
0x1800f406a  jmp     loc_1800F42D1
0x1800f406f  test    rbx, rbx
0x1800f4072  jnz     short loc_1800F40D4
0x1800f4074  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f407b  mov     ebx, 80004003h
0x1800f4080  mov     [rbp+440h+var_4A8], ebx
0x1800f4083  test    rcx, rcx
0x1800f4086  jz      short loc_1800F40CA
0x1800f4088  mov     edi, 3
0x1800f408d  lea     r9, aInvalidTiunloc; "Invalid TiUnlockProcess function passed"...
0x1800f4094  mov     r8d, edi
0x1800f4097  xor     edx, edx
0x1800f4099  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f409e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f40a5  lea     rax, [rbp+440h+var_4A8]
0x1800f40a9  mov     [rsp+540h+var_4D8], rax
0x1800f40ae  lea     r9, asc_1802EE7AC; ": {}"
0x1800f40b5  lea     rax, [rsp+540h+var_4D8]
0x1800f40ba  mov     r8d, edi
0x1800f40bd  lea     edx, [rdi-2]
0x1800f40c0  mov     [rsp+540h+var_520], rax
0x1800f40c5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f40ca  mov     edx, 11Ah
0x1800f40cf  jmp     loc_1800F42D1
0x1800f40d4  test    r13, r13
0x1800f40d7  jnz     short loc_1800F4138
0x1800f40d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f40e0  mov     ebx, 80004003h
0x1800f40e5  mov     [rbp+440h+var_4A8], ebx
0x1800f40e8  test    rcx, rcx
0x1800f40eb  jz      short loc_1800F412E
0x1800f40ed  lea     edi, [r13+3]
0x1800f40f1  xor     edx, edx
0x1800f40f3  mov     r8d, edi
0x1800f40f6  lea     r9, aInvalidInstanc_0; "Invalid InstanceCreated callback passed"...
0x1800f40fd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f4102  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4109  lea     rax, [rbp+440h+var_4A8]
0x1800f410d  mov     [rsp+540h+var_4D8], rax
0x1800f4112  lea     r9, asc_1802EE7AC; ": {}"
0x1800f4119  lea     rax, [rsp+540h+var_4D8]
0x1800f411e  mov     r8d, edi
0x1800f4121  lea     edx, [rdi-2]
0x1800f4124  mov     [rsp+540h+var_520], rax
0x1800f4129  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f412e  mov     edx, 11Bh
0x1800f4133  jmp     loc_1800F42D1
0x1800f4138  mov     r15, [rbp+440h+arg_20]
0x1800f413f  test    r15, r15
0x1800f4142  jnz     short loc_1800F41A3
0x1800f4144  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f414b  mov     ebx, 80004003h
0x1800f4150  mov     [rbp+440h+var_4A8], ebx
0x1800f4153  test    rcx, rcx
0x1800f4156  jz      short loc_1800F4199
0x1800f4158  lea     edi, [r15+3]
0x1800f415c  xor     edx, edx
0x1800f415e  mov     r8d, edi
0x1800f4161  lea     r9, aInvalidInstanc; "Invalid InstanceDestroyed callback pass"...
0x1800f4168  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f416d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4174  lea     rax, [rbp+440h+var_4A8]
0x1800f4178  mov     [rsp+540h+var_4D8], rax
0x1800f417d  lea     r9, asc_1802EE7AC; ": {}"
0x1800f4184  lea     rax, [rsp+540h+var_4D8]
0x1800f4189  mov     r8d, edi
0x1800f418c  lea     edx, [rdi-2]
0x1800f418f  mov     [rsp+540h+var_520], rax
0x1800f4194  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f4199  mov     edx, 11Ch
0x1800f419e  jmp     loc_1800F42D1
0x1800f41a3  mov     r12, [rbp+440h+arg_30]
0x1800f41aa  test    r12, r12
0x1800f41ad  jnz     short loc_1800F420F
0x1800f41af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f41b6  mov     ebx, 80004003h
0x1800f41bb  mov     [rbp+440h+var_4A8], ebx
0x1800f41be  test    rcx, rcx
0x1800f41c1  jz      short loc_1800F4205
0x1800f41c3  lea     edi, [r12+3]
0x1800f41c8  xor     edx, edx
0x1800f41ca  mov     r8d, edi
0x1800f41cd  lea     r9, aInvalidRequire; "Invalid RequireShutdownProcessing callb"...
0x1800f41d4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f41d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f41e0  lea     rax, [rbp+440h+var_4A8]
0x1800f41e4  mov     [rsp+540h+var_4D8], rax
0x1800f41e9  lea     r9, asc_1802EE7AC; ": {}"
0x1800f41f0  lea     rax, [rsp+540h+var_4D8]
0x1800f41f5  mov     r8d, edi
0x1800f41f8  lea     edx, [rdi-2]
0x1800f41fb  mov     [rsp+540h+var_520], rax
0x1800f4200  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f4205  mov     edx, 11Dh
0x1800f420a  jmp     loc_1800F42D1
0x1800f420f  test    r14, r14
0x1800f4212  jnz     short loc_1800F4270
0x1800f4214  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f421b  mov     ebx, 80004003h
0x1800f4220  mov     [rbp+440h+var_4A8], ebx
0x1800f4223  test    rcx, rcx
0x1800f4226  jz      short loc_1800F4269
0x1800f4228  lea     edi, [r14+3]
0x1800f422c  xor     edx, edx
0x1800f422e  mov     r8d, edi
0x1800f4231  lea     r9, aInvalidClassfa; "Invalid ClassFactory pointer passed in."
0x1800f4238  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f423d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4244  lea     rax, [rbp+440h+var_4A8]
0x1800f4248  mov     [rsp+540h+var_4D8], rax
0x1800f424d  lea     r9, asc_1802EE7AC; ": {}"
0x1800f4254  lea     rax, [rsp+540h+var_4D8]
0x1800f4259  mov     r8d, edi
0x1800f425c  lea     edx, [rdi-2]
0x1800f425f  mov     [rsp+540h+var_520], rax
0x1800f4264  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f4269  mov     edx, 11Eh
0x1800f426e  jmp     short loc_1800F42D1
0x1800f4270  call    EnableBackupRestorePrivileges
0x1800f4275  mov     ebx, eax
0x1800f4277  test    eax, eax
0x1800f4279  jns     short loc_1800F42EC
0x1800f427b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4282  mov     [rbp+440h+var_4A8], eax
0x1800f4285  test    rcx, rcx
0x1800f4288  jz      short loc_1800F42CC
0x1800f428a  mov     edi, 3
0x1800f428f  lea     r9, aFailedToAcquir_1; "Failed to acquire backup and restore pr"...
0x1800f4296  mov     r8d, edi
0x1800f4299  xor     edx, edx
0x1800f429b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f42a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f42a7  lea     rax, [rbp+440h+var_4A8]
0x1800f42ab  mov     [rsp+540h+var_4D8], rax
0x1800f42b0  lea     r9, asc_1802EE7AC; ": {}"
0x1800f42b7  lea     rax, [rsp+540h+var_4D8]
0x1800f42bc  mov     r8d, edi
0x1800f42bf  lea     edx, [rdi-2]
0x1800f42c2  mov     [rsp+540h+var_520], rax; int
0x1800f42c7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f42cc  mov     edx, 121h; void *
0x1800f42d1  mov     rcx, [rbp+448h]; this
0x1800f42d8  lea     r8, aOnecoreBaseCbs_16; "onecore\\base\\cbs\\core\\cbscoreinitia"...
0x1800f42df  mov     r9d, ebx; char *
0x1800f42e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f42e7  jmp     loc_1800F5202
0x1800f42ec  lea     rax, [rbp+440h+var_4A8]
0x1800f42f0  mov     esi, 1
0x1800f42f5  mov     r8d, esi; unsigned int
0x1800f42f8  mov     [rsp+540h+var_520], rax; unsigned int *
0x1800f42fd  lea     r9, aCbscheckrefcou_0; "CbsCheckRefCount"
0x1800f4304  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800f430b  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Tracing"
0x1800f4312  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1800f4317  test    eax, eax
0x1800f4319  jnz     short loc_1800F432F
0x1800f431b  lea     rdx, aCbscheckrefcou; "CbsCheckRefCount flag is set, CBS objec"...
0x1800f4322  mov     ecx, esi
0x1800f4324  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1800f4329  mov     cs:?vbTraceInterfaceRefCount@@3HA, esi; int vbTraceInterfaceRefCount
0x1800f432f  mov     rcx, cs:?vhInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800f4336  lea     rdx, [rbp+440h+Filename]; lpFilename
0x1800f433d  mov     ebx, 104h
0x1800f4342  mov     r8d, ebx; nSize
0x1800f4345  call    cs:__imp_GetModuleFileNameW
0x1800f434c  nop     dword ptr [rax+rax+00h]
0x1800f4351  test    eax, eax
0x1800f4353  jnz     loc_1800F43F2
0x1800f4359  call    cs:__imp_GetLastError
0x1800f4360  nop     dword ptr [rax+rax+00h]
0x1800f4365  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f436c  mov     ebx, eax
0x1800f436e  test    rcx, rcx
0x1800f4371  jz      short loc_1800F43C8
0x1800f4373  mov     edi, 3
0x1800f4378  lea     r9, aFailedToGetCor; "Failed to get Core DLL's path."
0x1800f437f  mov     r8d, edi
0x1800f4382  xor     edx, edx
0x1800f4384  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f4389  test    ebx, ebx
0x1800f438b  jg      short loc_1800F4391
0x1800f438d  mov     eax, ebx
0x1800f438f  jmp     short loc_1800F4399
0x1800f4391  movzx   eax, bx
0x1800f4394  or      eax, 80070000h
0x1800f4399  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f43a0  lea     r9, a0; ": {0}"
0x1800f43a7  mov     [rbp+440h+var_4A8], eax
0x1800f43aa  mov     r8d, edi
0x1800f43ad  lea     rax, [rbp+440h+var_4A8]
0x1800f43b1  mov     dl, sil
0x1800f43b4  mov     [rsp+540h+var_4D8], rax
0x1800f43b9  lea     rax, [rsp+540h+var_4D8]
0x1800f43be  mov     [rsp+540h+var_520], rax; unsigned int
0x1800f43c3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f43c8  test    ebx, ebx
0x1800f43ca  jz      loc_1800F5200
0x1800f43d0  mov     edx, 12Eh; void *
0x1800f43d5  mov     rcx, [rbp+448h]; this
0x1800f43dc  lea     r8, aOnecoreBaseCbs_16; "onecore\\base\\cbs\\core\\cbscoreinitia"...
0x1800f43e3  mov     r9d, ebx; char *
0x1800f43e6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f43eb  mov     ebx, eax
0x1800f43ed  jmp     loc_1800F5202
0x1800f43f2  cmp     eax, ebx
0x1800f43f4  jnz     short loc_1800F4400
0x1800f43f6  mov     ebx, 8007007Ah
0x1800f43fb  jmp     loc_1800F5202
0x1800f4400  lea     rcx, [rbp+440h+Filename]
0x1800f4407  call    FileFromPath
0x1800f440c  test    rax, rax
0x1800f440f  jnz     short loc_1800F447D
0x1800f4411  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f4418  mov     ebx, 8000FFFFh
0x1800f441d  mov     [rbp+440h+var_4A8], ebx
  ... truncated ...
```
