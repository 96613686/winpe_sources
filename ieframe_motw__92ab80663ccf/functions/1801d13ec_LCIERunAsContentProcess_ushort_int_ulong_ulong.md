# LCIERunAsContentProcess(ushort *,int,ulong,ulong)

- ea: `0x1801d13ec`
- end: `0x1801d1c3b`
- name: `?LCIERunAsContentProcess@@YAKPEAGHKK@Z`
- size: `2127`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a1fac`
- `0x1800a200c`

## callees

- `0x180005030`
- `0x180074e98`
- `0x18009ccb8`
- `0x1800a2320`
- `0x1800bdf3c`
- `0x1800f89b0`
- `0x1800fde98`
- `0x18012894c`
- `0x1801cde94`
- `0x1801cf1a0`
- `0x1801d13ec`
- `0x1801d31dc`
- `0x1801d3600`
- `0x1801d36b8`
- `0x1801e55c4`
- `0x1801e7bf4`
- `0x1801e8de8`
- `0x1801e8e50`
- `0x180265350`
- `0x180266048`
- `0x180269768`
- `0x1802a10b8`
- `0x1802a1c40`
- `0x1802a7024`
- `0x18042ada8`
- `0x180438fb8`
- `0x1805291f8`
- `0x1805292a4`
- `0x18052a3e4`
- `0x18052aad0`
- `0x1805588b8`
- `0x18056d79c`
- `0x18057a240`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1801d17be`
- `KERNEL32!InitializeCriticalSection` at `0x1801d17be`
- `KERNEL32!CreateEventW` at `0x1801d188f`
- `KERNEL32!CreateEventW` at `0x1801d188f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801d157c`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801d157c`
- `KERNEL32!SetProcessShutdownParameters` at `0x1801d158f`
- `KERNEL32!SetProcessShutdownParameters` at `0x1801d158f`
- `KERNEL32!GetModuleHandleW` at `0x1801d152f`
- `KERNEL32!GetModuleHandleW` at `0x1801d152f`
- `KERNEL32!DeleteCriticalSection` at `0x1801d1b6e`
- `KERNEL32!DeleteCriticalSection` at `0x1801d1b6e`
- `KERNEL32!CloseHandle` at `0x1801d18cc`
- `KERNEL32!CloseHandle` at `0x1801d18cc`
- `KERNEL32!GetLastError` at `0x1801d1569`
- `KERNEL32!GetLastError` at `0x1801d1569`
- `KERNEL32!GetCurrentThreadId` at `0x1801d1511`
- `KERNEL32!GetCurrentThreadId` at `0x1801d1511`
- `KERNEL32!LeaveCriticalSection` at `0x1801d1b05`
- `KERNEL32!LeaveCriticalSection` at `0x1801d1b05`
- `KERNEL32!EnterCriticalSection` at `0x1801d1ac9`
- `KERNEL32!EnterCriticalSection` at `0x1801d1ac9`
- `KERNEL32!GetProcAddress` at `0x1801d154f`
- `KERNEL32!GetProcAddress` at `0x1801d154f`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x1801d1505`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x1801d1505`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801d162a`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801d1bbf`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801d162a`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801d1bbf`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801d165a`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801d165a`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801d1873`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801d1b2d`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801d1873`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801d1b2d`
- `iertutil!__imp_DPA_DestroyCallback` at `0x1801d1aeb`
- `iertutil!__imp_DPA_DestroyCallback` at `0x1801d1aeb`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801d1c01`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801d1c01`
- `iertutil!__imp_?LCIESetCurrentProcessInPrivate@@YAXXZ` at `0x1801d18f3`
- `iertutil!__imp_?LCIESetCurrentProcessInPrivate@@YAXXZ` at `0x1801d18f3`
- `iertutil!__imp_SuggestHintKey` at `0x1801d14c2`
- `iertutil!__imp_SuggestHintKey` at `0x1801d14c2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1437`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1458`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d14a9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d179e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1b47`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1437`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1458`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d14a9`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d179e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1b47`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801d17d6`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801d17d6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801d1468`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801d1468`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeSecurity` at `0x1801d1694`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeSecurity` at `0x1801d1694`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801d1646`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801d1646`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801d1bb3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801d1bb3`
- `api-ms-win-downlevel-shell32-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x1801d1490`
- `api-ms-win-downlevel-shell32-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x1801d1490`
- `WININET!InternetSetOptionW` at `0x1801d16e1`
- `WININET!InternetSetOptionW` at `0x1801d1916`
- `WININET!InternetSetOptionW` at `0x1801d1a83`
- `WININET!InternetSetOptionW` at `0x1801d16e1`
- `WININET!InternetSetOptionW` at `0x1801d1916`
- `WININET!InternetSetOptionW` at `0x1801d1a83`
- `MSHTML!InitializeLocalHtmlEngine` at `0x1801d16a5`
- `MSHTML!InitializeLocalHtmlEngine` at `0x1801d16a5`
- `MSHTML!UninitializeLocalHtmlEngine` at `0x1801d1ba2`
- `MSHTML!UninitializeLocalHtmlEngine` at `0x1801d1ba2`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x1801d183e`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x1801d183e`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801d1741`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801d1741`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801d1b1f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801d1b1f`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801d1b11`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801d1b11`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801d1981`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801d1981`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801d1a9f`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801d1a9f`
- `msIso!__imp_?IsoGetSharedMemoryAddress@@YAJKPEAPEAXPEAK@Z` at `0x1801d17f9`
- `msIso!__imp_?IsoGetSharedMemoryAddress@@YAJKPEAPEAXPEAK@Z` at `0x1801d17f9`
- `msIso!__imp_?IsoSetManagerExitBehavior@@YAJKPEAUIsoScope@@@Z` at `0x1801d178d`
- `msIso!__imp_?IsoSetManagerExitBehavior@@YAJKPEAUIsoScope@@@Z` at `0x1801d178d`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801d1729`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801d1729`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801d160a`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801d189e`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801d160a`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801d189e`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801d1bf5`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801d1bf5`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801d15f0`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801d15f0`
- `msIso!__imp_?IsoCreateThreadAndComponentFromProcessCreationData@@YAJKPEAKPEAUIsoScope@@@Z` at `0x1801d195d`
- `msIso!__imp_?IsoCreateThreadAndComponentFromProcessCreationData@@YAJKPEAKPEAUIsoScope@@@Z` at `0x1801d195d`
- `msIso!__imp_?IsoManagerThreadZero_WindowsPump@@YAK_NPEAUIsoScope@@@Z` at `0x1801d19ee`
- `msIso!__imp_?IsoManagerThreadZero_WindowsPump@@YAK_NPEAUIsoScope@@@Z` at `0x1801d19ee`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801d16f5`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801d16f5`
- `msIso!__imp_?LCIEIsCurrentProcessIMPinnedSite@@YA_NXZ` at `0x1801d1b57`
- `msIso!__imp_?LCIEIsCurrentProcessIMPinnedSite@@YA_NXZ` at `0x1801d1b57`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801d19ab`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801d19ab`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1801d14d6`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1801d14d6`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x1801d14f4`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x1801d14f4`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801d1bd4`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801d1be2`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801d1bd4`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801d1be2`
- `urlmon!__imp_CoInternetSetExtensionsOff` at `0x1801d1447`
- `urlmon!__imp_CoInternetSetExtensionsOff` at `0x1801d1447`
- `urlmon!__imp_CreateVersionManager` at `0x1801d19bc`
- `urlmon!__imp_CreateVersionManager` at `0x1801d19bc`
- `urlmon!__imp_DestroyVersionManager` at `0x1801d1a1e`
- `urlmon!__imp_DestroyVersionManager` at `0x1801d1a1e`
- `ieapfltr!DestroyUrlBlockClient` at `0x1801d1a12`
- `ieapfltr!DestroyUrlBlockClient` at `0x1801d1a12`
- `ieapfltr!CreateUrlBlockClient` at `0x1801d19c8`
- `ieapfltr!CreateUrlBlockClient` at `0x1801d19c8`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterDestroy` at `0x1801d1a06`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterDestroy` at `0x1801d1a06`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterCreate` at `0x1801d19dd`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterCreate` at `0x1801d19dd`

## string_xrefs

- `0x1801d1528`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall LCIERunAsContentProcess(unsigned __int16 *a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // r12d
  unsigned __int64 v7; // rdx
  char v8; // r14
  int *RefCountAddress; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  struct IsoScope *DefaultScope; // rax
  struct IESubscriptionManager *v13; // rax
  unsigned int CurrentProcessManager; // eax
  EnterpriseIdManager *v15; // rcx
  unsigned int CurrentIsoProcessEnterpriseIDHandle; // eax
  unsigned __int8 *v17; // rsi
  int v18; // edi
  HANDLE EventW; // rbx
  struct IsoScope *v20; // rax
  bool v21; // zf
  unsigned int CurrentThreadHandle; // eax
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-ACh] BYREF
  int Buffer; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v27; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _IsoArtifact *v28; // [rsp+60h] [rbp-A0h] BYREF
  IUnknown *punk; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v30; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  void *v33; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[96]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR AppID[128]; // [rsp+F0h] [rbp-10h] BYREF

  v30 = a3;
  v4 = 0;
  SetProcessDpiAwareness();
  if ( (unsigned __int8)IEConfiguration_GetBool(268435493) )
    CoInternetSetExtensionsOff();
  if ( !(unsigned __int8)IEConfiguration_GetBool(268435465) && !IsDualEngineProcess()
    || CSiteModeInfo::GetAppIDFromTabCmdArgs(a1, v7, AppID) >= 0 && SetCurrentProcessExplicitAppUserModelID(AppID) >= 0 )
  {
    g_fHangRecovery = IEConfiguration_GetBool(268435460);
    SuggestHintKey(SettingStore::IEKEY_Browser_RootHint);
    punk = 0;
    v8 = 0;
    RefCountAddress = ProcessGetRefCountAddress();
    CTabProcessReference::CreateInstance(RefCountAddress, &punk);
    ProcessSetRefCountIUnknown(punk);
    SHSetInstanceExplorer(punk);
    g_tidParking = GetCurrentThreadId();
    IESetProcessExports();
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "WerSetFlags");
      if ( ProcAddress )
        ((void (__fastcall *)(__int64))ProcAddress)(16);
    }
    else
    {
      GetLastError();
    }
    SetUnhandledExceptionFilter(LCIEExceptionFilter);
    SetProcessShutdownParameters(0x27Fu, 0);
    if ( (int)CreateLCIEDefinitions() < 0 )
      goto LABEL_66;
    if ( (int)LowRightsAware_SetTempFolderForProcess() < 0 )
      goto LABEL_66;
    UpdateGlobalCompatibilityFlags();
    if ( !AttachShims() )
      goto LABEL_66;
    memset_0(v34, 0, sizeof(v34));
    InitializeIsoScopeCreationData((struct SIsoScopeCreationData *)v34);
    if ( (int)IsoInitDefaultScope(0x201u, &v30, a4, (const struct SIsoScopeCreationData *)v34) < 0 )
      goto LABEL_66;
    v8 = 1;
    DefaultScope = IsoGetDefaultScope();
    (*(void (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 72LL))(DefaultScope, 16);
    if ( !IsProtectedModeProcess() )
      InitLrieAppCompatLogger();
    if ( CoInitializeEx(0, 2u) < 0 )
    {
LABEL_64:
      if ( !IsProtectedModeProcess() )
      {
        TermLrieAppCompatLogger();
        ProcessRefCountRelease();
        goto LABEL_67;
      }
LABEL_66:
      ProcessRefCountRelease();
      if ( !v8 )
      {
LABEL_68:
        IAS_Close();
        return v4;
      }
LABEL_67:
      IsoReleaseDefaultScope(0);
      goto LABEL_68;
    }
    if ( !IsElevatedProcess() )
    {
      CoInitializeSecurity(0, -1, 0, 0, 2u, 3u, 0, 0, 0);
      RefreshTabProtectedPolicies();
    }
    if ( InitializeLocalHtmlEngine() < 0 )
    {
LABEL_63:
      OpenServiceUninitialize();
      CoUninitialize();
      goto LABEL_64;
    }
    Buffer = 1;
    GetBOOL((__int64 *)SettingStore::IEVALUE_wininet_BackgroundConnections[0], &Buffer);
    if ( !InternetSetOptionW(0, 0x79u, &Buffer, 4u) )
      goto LABEL_62;
    v13 = IsoSubscriptionManager();
    (*(void (__fastcall **)(struct IESubscriptionManager *, __int64, _QWORD, __int64 (__fastcall *)(), _QWORD))(*(_QWORD *)v13 + 56LL))(
      v13,
      4,
      0,
      ScopeProcessCallback,
      0);
    v28 = 0;
    CurrentProcessManager = IsoGetCurrentProcessManager();
    if ( (int)IsoGetArtifactAddress(CurrentProcessManager, 0x14u, &v28, 0) < 0 )
      goto LABEL_62;
    _IsoComponent::SetFromSHAREDMEM_64BITVALUE(v28, 4, LCIETabManagerWinProc);
    v24 = 0;
    *((_DWORD *)v28 + 5) &= ~0x2000000u;
    GetEmptyTabTimeoutAndContentProcessShutdownDelay(0, &v24);
    if ( v24 )
      IsoSetManagerExitBehavior(v24, 0);
    if ( (unsigned __int8)IEConfiguration_GetBool(268435465) && (int)CSiteModeInfo::_GetTabInfo() >= 0 )
      InitializeCriticalSection(&CSiteModeInfo::s_csSiteModeInfo);
    CurrentIsoProcessEnterpriseIDHandle = EnterpriseIdManager::GetCurrentIsoProcessEnterpriseIDHandle(v15);
    IEConfiguration_SetDWORD(536870929, CurrentIsoProcessEnterpriseIDHandle);
    v31 = 0;
    v27 = 0;
    if ( (int)IsoGetSharedMemoryAddress(a4, (void **)&v31, &v27) < 0 || v27 < 0x164 )
    {
LABEL_62:
      UninitializeLocalHtmlEngine();
      goto LABEL_63;
    }
    v17 = v31;
    v24 = 0;
    v33 = 0;
    if ( (int)LCIEUnmarshalInterfaceFromBuffer(&IID_IEUserBroker, &v33, v31 + 47, 0x80u) < 0
      || (int)MarshalToGIT(v33, &IID_IEUserBroker, &v24) < 0 )
    {
LABEL_57:
      if ( (unsigned __int8)IEConfiguration_GetBool(268435465) || LCIEIsCurrentProcessIMPinnedSite() )
      {
        DeleteCriticalSection(&CSiteModeInfo::s_csSiteModeInfo);
        if ( CSiteModeInfo::s_pSecurityManager )
        {
          ((void (__fastcall *)(struct IUnknown *))CSiteModeInfo::s_pSecurityManager->lpVtbl->Release)(CSiteModeInfo::s_pSecurityManager);
          CSiteModeInfo::s_pSecurityManager = 0;
        }
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v33);
      goto LABEL_62;
    }
    v18 = SetUserBroker(v24);
    if ( v18 >= 0 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v20 = IsoGetDefaultScope();
      v18 = (*(__int64 (__fastcall **)(struct IsoScope *, __int64, HANDLE))(*(_QWORD *)v20 + 248LL))(v20, 25, EventW);
      CloseHandle(EventW);
    }
    v21 = (v17[35] & 0x40) == 0;
    dword_1806AA8E8 = 2 - (*(_DWORD *)(v17 + 43) != 0);
    if ( !v21 )
    {
      LCIESetCurrentProcessInPrivate();
      v25 = 3;
      if ( !InternetSetOptionW(0, 0x51u, &v25, 4u) )
      {
LABEL_56:
        SetUserBroker(0);
        RevokeFromGIT(v24);
        goto LABEL_57;
      }
      v18 = DisableTelemetryForCurrentProcess(5);
    }
    if ( v18 >= 0
      && (int)ProcessPICOperationalChanges() >= 0
      && (*v31 != 20 || (int)IsoCreateThreadAndComponentFromProcessCreationData(a4, 0, 0) >= 0) )
    {
      if ( LCIEUnifiedFrame() )
        SignalIEInitializedEvent();
      if ( (int)IsoInitializeThread(0) >= 0 )
      {
        v25 = 0;
        StartThumbnailServices(&v25);
        IsoSetCreateProcessCallback((int (*)(bool, int, struct _IsoCreationProcessData *))LCIEOnCreateProcess);
        AsyncKeyState_Initialize();
        CreateVersionManager();
        CreateUrlBlockClient();
        if ( (unsigned int)WpcWebFilterIsEnabledForCurrentUser() )
          WpcWebFilterCreate();
        v4 = IsoManagerThreadZero_WindowsPump(1, 0);
        if ( (unsigned int)WpcWebFilterIsEnabledForCurrentUser() )
          WpcWebFilterDestroy();
        DestroyUrlBlockClient();
        DestroyVersionManager();
        v32 = 0;
        if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punk->lpVtbl->QueryInterface)(
               punk,
               &GUID_14e03031_ba5b_41d2_bbb5_3204f1e0ea67,
               &v32) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 32LL))(v32);
        *((_DWORD *)v28 + 5) &= ~0x4000000u;
        *((_DWORD *)v28 + 5) |= 0x2000000u;
        IEHistoryJournalInstance::CloseJournal();
        InternetSetOptionW(0, 0x87u, 0, 0);
        CGlobalImageProcessTaskQueue::Dispose();
        ShutdownThumbnailServices(v25);
        IsoUninitializeThread(0);
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v32);
      }
      if ( LCIEUnifiedFrame() )
        SignalIEShutdownEvent();
      EnterCriticalSection(&g_csDll);
      if ( CBrowserApplicationState::_dpaFrames )
      {
        DPA_DestroyCallback(CBrowserApplicationState::_dpaFrames, DPA_ReleaseCB<CBrowserFrameState>, 0);
        CBrowserApplicationState::_dpaFrames = 0;
      }
      LeaveCriticalSection(&g_csDll);
      CurrentThreadHandle = IsoGetCurrentThreadHandle();
      IsoRemoveArtifact(CurrentThreadHandle);
    }
    goto LABEL_56;
  }
  return v4;
}

```

## disassembly

```asm
0x1801d13ec  mov     [rsp-8+arg_8], rbx
0x1801d13f1  push    rbp
0x1801d13f2  push    rsi
0x1801d13f3  push    rdi
0x1801d13f4  push    r12
0x1801d13f6  push    r13
0x1801d13f8  push    r14
0x1801d13fa  push    r15
0x1801d13fc  lea     rbp, [rsp-100h]
0x1801d1404  sub     rsp, 200h
0x1801d140b  mov     rax, cs:__security_cookie
0x1801d1412  xor     rax, rsp
0x1801d1415  mov     [rbp+130h+var_40], rax
0x1801d141c  xor     r13d, r13d
0x1801d141f  mov     [rsp+230h+var_1C0], r8d
0x1801d1424  mov     r12d, r13d
0x1801d1427  mov     r15d, r9d
0x1801d142a  mov     rbx, rcx
0x1801d142d  call    ?SetProcessDpiAwareness@@YAXXZ; SetProcessDpiAwareness(void)
0x1801d1432  mov     ecx, 10000025h
0x1801d1437  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d143e  nop     dword ptr [rax+rax+00h]
0x1801d1443  test    al, al
0x1801d1445  jz      short loc_1801D1453
0x1801d1447  call    cs:__imp_CoInternetSetExtensionsOff
0x1801d144e  nop     dword ptr [rax+rax+00h]
0x1801d1453  mov     ecx, 10000009h
0x1801d1458  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d145f  nop     dword ptr [rax+rax+00h]
0x1801d1464  test    al, al
0x1801d1466  jnz     short loc_1801D1478
0x1801d1468  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801d146f  nop     dword ptr [rax+rax+00h]
0x1801d1474  test    al, al
0x1801d1476  jz      short loc_1801D14A4
0x1801d1478  lea     r8, [rbp+130h+AppID]; unsigned __int16 *
0x1801d147c  mov     rcx, rbx; unsigned __int16 *
0x1801d147f  call    ?GetAppIDFromTabCmdArgs@CSiteModeInfo@@SAJPEBG_KPEAG@Z; CSiteModeInfo::GetAppIDFromTabCmdArgs(ushort const *,unsigned __int64,ushort *)
0x1801d1484  test    eax, eax
0x1801d1486  js      loc_1801D1C0D
0x1801d148c  lea     rcx, [rbp+130h+AppID]; AppID
0x1801d1490  call    cs:__imp_SetCurrentProcessExplicitAppUserModelID
0x1801d1497  nop     dword ptr [rax+rax+00h]
0x1801d149c  test    eax, eax
0x1801d149e  js      loc_1801D1C0D
0x1801d14a4  mov     ecx, 10000004h
0x1801d14a9  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d14b0  nop     dword ptr [rax+rax+00h]
0x1801d14b5  mov     rcx, cs:?IEKEY_Browser_RootHint@SettingStore@@3UKEYID@1@B; SettingStore::KEYID const SettingStore::IEKEY_Browser_RootHint
0x1801d14bc  mov     cs:?g_fHangRecovery@@3_NA, al; bool g_fHangRecovery
0x1801d14c2  call    cs:__imp_SuggestHintKey
0x1801d14c9  nop     dword ptr [rax+rax+00h]
0x1801d14ce  mov     [rsp+230h+punk], r13
0x1801d14d3  mov     r14b, r13b
0x1801d14d6  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x1801d14dd  nop     dword ptr [rax+rax+00h]
0x1801d14e2  mov     rcx, rax; int *
0x1801d14e5  lea     rdx, [rsp+230h+punk]; ppv
0x1801d14ea  call    ?CreateInstance@CTabProcessReference@@SAJPEAJPEAPEAUIUnknown@@@Z; CTabProcessReference::CreateInstance(long *,IUnknown * *)
0x1801d14ef  mov     rcx, [rsp+230h+punk]
0x1801d14f4  call    cs:__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z; ProcessSetRefCountIUnknown(IUnknown *)
0x1801d14fb  nop     dword ptr [rax+rax+00h]
0x1801d1500  mov     rcx, [rsp+230h+punk]; punk
0x1801d1505  call    cs:__imp_SHSetInstanceExplorer
0x1801d150c  nop     dword ptr [rax+rax+00h]
0x1801d1511  call    cs:__imp_GetCurrentThreadId
0x1801d1518  nop     dword ptr [rax+rax+00h]
0x1801d151d  mov     cs:g_tidParking, eax
0x1801d1523  call    ?IESetProcessExports@@YAXXZ; IESetProcessExports(void)
0x1801d1528  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1801d152f  call    cs:__imp_GetModuleHandleW
0x1801d1536  nop     dword ptr [rax+rax+00h]
0x1801d153b  mov     ebx, 10h
0x1801d1540  test    rax, rax
0x1801d1543  jz      short loc_1801D1569
0x1801d1545  lea     rdx, aWersetflags; "WerSetFlags"
0x1801d154c  mov     rcx, rax; hModule
0x1801d154f  call    cs:__imp_GetProcAddress
0x1801d1556  nop     dword ptr [rax+rax+00h]
0x1801d155b  test    rax, rax
0x1801d155e  jz      short loc_1801D1575
0x1801d1560  mov     ecx, ebx
0x1801d1562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1567  jmp     short loc_1801D1575
0x1801d1569  call    cs:__imp_GetLastError
0x1801d1570  nop     dword ptr [rax+rax+00h]
0x1801d1575  lea     rcx, ?LCIEExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x1801d157c  call    cs:__imp_SetUnhandledExceptionFilter
0x1801d1583  nop     dword ptr [rax+rax+00h]
0x1801d1588  xor     edx, edx; dwFlags
0x1801d158a  mov     ecx, 27Fh; dwLevel
0x1801d158f  call    cs:__imp_SetProcessShutdownParameters
0x1801d1596  nop     dword ptr [rax+rax+00h]
0x1801d159b  call    ?CreateLCIEDefinitions@@YAJXZ; CreateLCIEDefinitions(void)
0x1801d15a0  test    eax, eax
0x1801d15a2  js      loc_1801D1BE2
0x1801d15a8  call    ?LowRightsAware_SetTempFolderForProcess@@YAJXZ; LowRightsAware_SetTempFolderForProcess(void)
0x1801d15ad  test    eax, eax
0x1801d15af  js      loc_1801D1BE2
0x1801d15b5  call    ?UpdateGlobalCompatibilityFlags@@YAXXZ; UpdateGlobalCompatibilityFlags(void)
0x1801d15ba  call    ?AttachShims@@YA_NXZ; AttachShims(void)
0x1801d15bf  test    al, al
0x1801d15c1  jz      loc_1801D1BE2
0x1801d15c7  xor     edx, edx; Val
0x1801d15c9  lea     rcx, [rbp+130h+var_1A0]; void *
0x1801d15cd  lea     r8d, [rdx+60h]; Size
0x1801d15d1  call    memset_0
0x1801d15d6  lea     rcx, [rbp+130h+var_1A0]; struct SIsoScopeCreationData *
0x1801d15da  call    ?InitializeIsoScopeCreationData@@YAXPEAUSIsoScopeCreationData@@@Z; InitializeIsoScopeCreationData(SIsoScopeCreationData *)
0x1801d15df  lea     r9, [rbp+130h+var_1A0]
0x1801d15e3  mov     r8d, r15d
0x1801d15e6  lea     rdx, [rsp+230h+var_1C0]
0x1801d15eb  mov     ecx, 201h
0x1801d15f0  call    cs:__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z; IsoInitDefaultScope(ulong,ulong *,ulong,SIsoScopeCreationData const *)
0x1801d15f7  nop     dword ptr [rax+rax+00h]
0x1801d15fc  test    eax, eax
0x1801d15fe  js      loc_1801D1BE2
0x1801d1604  mov     r14d, 1
0x1801d160a  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801d1611  nop     dword ptr [rax+rax+00h]
0x1801d1616  mov     r8, rax
0x1801d1619  mov     edx, ebx
0x1801d161b  mov     rcx, [rax]
0x1801d161e  mov     rax, [rcx+48h]
0x1801d1622  mov     rcx, r8
0x1801d1625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d162a  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1801d1631  nop     dword ptr [rax+rax+00h]
0x1801d1636  test    eax, eax
0x1801d1638  jnz     short loc_1801D163F
0x1801d163a  call    ?InitLrieAppCompatLogger@@YAJXZ; InitLrieAppCompatLogger(void)
0x1801d163f  mov     edx, 2; dwCoInit
0x1801d1644  xor     ecx, ecx; pvReserved
0x1801d1646  call    cs:__imp_CoInitializeEx
0x1801d164d  nop     dword ptr [rax+rax+00h]
0x1801d1652  test    eax, eax
0x1801d1654  js      loc_1801D1BBF
0x1801d165a  call    cs:__imp_?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x1801d1661  nop     dword ptr [rax+rax+00h]
0x1801d1666  test    eax, eax
0x1801d1668  jnz     short loc_1801D16A5
0x1801d166a  mov     [rsp+230h+pReserved3], r13; pReserved3
0x1801d166f  xor     r9d, r9d; pReserved1
0x1801d1672  mov     [rsp+230h+dwCapabilities], r13d; dwCapabilities
0x1801d1677  xor     r8d, r8d; asAuthSvc
0x1801d167a  mov     [rsp+230h+pAuthList], r13; pAuthList
0x1801d167f  or      edx, 0FFFFFFFFh; cAuthSvc
0x1801d1682  mov     [rsp+230h+dwImpLevel], 3; dwImpLevel
0x1801d168a  xor     ecx, ecx; pSecDesc
0x1801d168c  mov     [rsp+230h+dwAuthnLevel], 2; dwAuthnLevel
0x1801d1694  call    cs:__imp_CoInitializeSecurity
0x1801d169b  nop     dword ptr [rax+rax+00h]
0x1801d16a0  call    ?RefreshTabProtectedPolicies@@YAJXZ; RefreshTabProtectedPolicies(void)
0x1801d16a5  call    cs:__imp_InitializeLocalHtmlEngine
0x1801d16ac  nop     dword ptr [rax+rax+00h]
0x1801d16b1  test    eax, eax
0x1801d16b3  js      loc_1801D1BAE
0x1801d16b9  mov     rcx, cs:?IEVALUE_wininet_BackgroundConnections@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_wininet_BackgroundConnections
0x1801d16c0  lea     rdx, [rsp+230h+Buffer]
0x1801d16c5  mov     [rsp+230h+Buffer], r14d
0x1801d16ca  call    GetBOOL
0x1801d16cf  mov     ebx, 4
0x1801d16d4  lea     r8, [rsp+230h+Buffer]; lpBuffer
0x1801d16d9  mov     r9d, ebx; dwBufferLength
0x1801d16dc  xor     ecx, ecx; hInternet
0x1801d16de  lea     edx, [rbx+75h]; dwOption
0x1801d16e1  call    cs:__imp_InternetSetOptionW
0x1801d16e8  nop     dword ptr [rax+rax+00h]
0x1801d16ed  test    eax, eax
0x1801d16ef  jz      loc_1801D1BA2
0x1801d16f5  call    cs:__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ; IsoSubscriptionManager(void)
0x1801d16fc  nop     dword ptr [rax+rax+00h]
0x1801d1701  lea     r9, _ScopeProcessCallback
0x1801d1708  mov     qword ptr [rsp+230h+dwAuthnLevel], r13
0x1801d170d  mov     r10, rax
0x1801d1710  xor     r8d, r8d
0x1801d1713  mov     edx, ebx
0x1801d1715  mov     rcx, [rax]
0x1801d1718  mov     rax, [rcx+38h]
0x1801d171c  mov     rcx, r10
0x1801d171f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1724  mov     [rsp+230h+var_1D0], r13
0x1801d1729  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801d1730  nop     dword ptr [rax+rax+00h]
0x1801d1735  xor     r9d, r9d
0x1801d1738  lea     r8, [rsp+230h+var_1D0]
0x1801d173d  mov     ecx, eax
0x1801d173f  mov     dl, 14h
0x1801d1741  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x1801d1748  nop     dword ptr [rax+rax+00h]
0x1801d174d  test    eax, eax
0x1801d174f  js      loc_1801D1BA2
0x1801d1755  mov     rcx, [rsp+230h+var_1D0]
0x1801d175a  lea     r8, ?LCIETabManagerWinProc@@YA_JPEAUHWND__@@I_K_J@Z; LCIETabManagerWinProc(HWND__ *,uint,unsigned __int64,__int64)
0x1801d1761  mov     edx, ebx
0x1801d1763  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x1801d1768  mov     rax, [rsp+230h+var_1D0]
0x1801d176d  lea     rdx, [rsp+230h+var_1E0]; unsigned int *
0x1801d1772  xor     ecx, ecx; unsigned int *
0x1801d1774  mov     [rsp+230h+var_1E0], r13d
0x1801d1779  btr     dword ptr [rax+14h], 19h
0x1801d177e  call    ?GetEmptyTabTimeoutAndContentProcessShutdownDelay@@YAJPEAK0@Z; GetEmptyTabTimeoutAndContentProcessShutdownDelay(ulong *,ulong *)
0x1801d1783  mov     ecx, [rsp+230h+var_1E0]
0x1801d1787  test    ecx, ecx
0x1801d1789  jz      short loc_1801D1799
0x1801d178b  xor     edx, edx
0x1801d178d  call    cs:__imp_?IsoSetManagerExitBehavior@@YAJKPEAUIsoScope@@@Z; IsoSetManagerExitBehavior(ulong,IsoScope *)
0x1801d1794  nop     dword ptr [rax+rax+00h]
0x1801d1799  mov     ecx, 10000009h
0x1801d179e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d17a5  nop     dword ptr [rax+rax+00h]
0x1801d17aa  test    al, al
0x1801d17ac  jz      short loc_1801D17CA
0x1801d17ae  call    ?_GetTabInfo@CSiteModeInfo@@CAJXZ; CSiteModeInfo::_GetTabInfo(void)
0x1801d17b3  test    eax, eax
0x1801d17b5  js      short loc_1801D17CA
0x1801d17b7  lea     rcx, ?s_csSiteModeInfo@CSiteModeInfo@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801d17be  call    cs:__imp_InitializeCriticalSection
0x1801d17c5  nop     dword ptr [rax+rax+00h]
0x1801d17ca  call    ?GetCurrentIsoProcessEnterpriseIDHandle@EnterpriseIdManager@@YAKXZ; EnterpriseIdManager::GetCurrentIsoProcessEnterpriseIDHandle(void)
0x1801d17cf  mov     edx, eax
0x1801d17d1  mov     ecx, 20000011h
0x1801d17d6  call    cs:__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x1801d17dd  nop     dword ptr [rax+rax+00h]
0x1801d17e2  lea     r8, [rsp+230h+var_1D4]
0x1801d17e7  mov     [rsp+230h+var_1B8], r13
0x1801d17ec  lea     rdx, [rsp+230h+var_1B8]
0x1801d17f1  mov     [rsp+230h+var_1D4], r13d
0x1801d17f6  mov     ecx, r15d
0x1801d17f9  call    cs:__imp_?IsoGetSharedMemoryAddress@@YAJKPEAPEAXPEAK@Z; IsoGetSharedMemoryAddress(ulong,void * *,ulong *)
0x1801d1800  nop     dword ptr [rax+rax+00h]
0x1801d1805  test    eax, eax
0x1801d1807  js      loc_1801D1BA2
0x1801d180d  cmp     [rsp+230h+var_1D4], 164h
0x1801d1815  jb      loc_1801D1BA2
0x1801d181b  mov     rsi, [rsp+230h+var_1B8]
0x1801d1820  lea     rdx, [rbp+130h+var_1A8]
0x1801d1824  mov     r9d, 80h
0x1801d182a  mov     [rsp+230h+var_1E0], r13d
0x1801d182f  lea     rcx, IID_IEUserBroker
0x1801d1836  mov     [rbp+130h+var_1A8], r13
0x1801d183a  lea     r8, [rsi+2Fh]
0x1801d183e  call    cs:__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z; LCIEUnmarshalInterfaceFromBuffer(_GUID const &,void * *,uchar *,unsigned __int64)
0x1801d1845  nop     dword ptr [rax+rax+00h]
0x1801d184a  test    eax, eax
0x1801d184c  js      loc_1801D1B42
0x1801d1852  mov     rcx, [rbp+130h+var_1A8]
0x1801d1856  lea     r8, [rsp+230h+var_1E0]
0x1801d185b  lea     rdx, IID_IEUserBroker
0x1801d1862  call    MarshalToGIT
0x1801d1867  test    eax, eax
0x1801d1869  js      loc_1801D1B42
0x1801d186f  mov     ecx, [rsp+230h+var_1E0]
0x1801d1873  call    cs:__imp_?SetUserBroker@@YAJK@Z; SetUserBroker(ulong)
0x1801d187a  nop     dword ptr [rax+rax+00h]
0x1801d187f  mov     edi, eax
0x1801d1881  test    eax, eax
0x1801d1883  js      short loc_1801D18DD
0x1801d1885  xor     r9d, r9d; lpName
0x1801d1888  xor     r8d, r8d; bInitialState
0x1801d188b  xor     edx, edx; bManualReset
0x1801d188d  xor     ecx, ecx; lpEventAttributes
0x1801d188f  call    cs:__imp_CreateEventW
0x1801d1896  nop     dword ptr [rax+rax+00h]
0x1801d189b  mov     rbx, rax
0x1801d189e  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801d18a5  nop     dword ptr [rax+rax+00h]
0x1801d18aa  mov     r8, rbx
0x1801d18ad  mov     edx, 19h
0x1801d18b2  mov     r9, rax
0x1801d18b5  mov     rcx, [rax]
0x1801d18b8  mov     rax, [rcx+0F8h]
0x1801d18bf  mov     rcx, r9
0x1801d18c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d18c7  mov     rcx, rbx; hObject
0x1801d18ca  mov     edi, eax
0x1801d18cc  call    cs:__imp_CloseHandle
0x1801d18d3  nop     dword ptr [rax+rax+00h]
0x1801d18d8  mov     ebx, 4
0x1801d18dd  mov     eax, [rsi+2Bh]
0x1801d18e0  neg     eax
0x1801d18e2  sbb     ecx, ecx
0x1801d18e4  add     ecx, 2
0x1801d18e7  test    byte ptr [rsi+23h], 40h
0x1801d18eb  mov     cs:dword_1806AA8E8, ecx
0x1801d18f1  jz      short loc_1801D1936
0x1801d18f3  call    cs:__imp_?LCIESetCurrentProcessInPrivate@@YAXXZ; LCIESetCurrentProcessInPrivate(void)
0x1801d18fa  nop     dword ptr [rax+rax+00h]
0x1801d18ff  mov     r9d, ebx; dwBufferLength
0x1801d1902  mov     [rsp+230h+var_1DC], 3
0x1801d190a  lea     r8, [rsp+230h+var_1DC]; lpBuffer
0x1801d190f  mov     edx, 51h ; 'Q'; dwOption
0x1801d1914  xor     ecx, ecx; hInternet
0x1801d1916  call    cs:__imp_InternetSetOptionW
0x1801d191d  nop     dword ptr [rax+rax+00h]
0x1801d1922  test    eax, eax
0x1801d1924  jz      loc_1801D1B2B
0x1801d192a  mov     ecx, 5
0x1801d192f  call    ?DisableTelemetryForCurrentProcess@@YAJW4MarkProcessTelemetryStateFailed_Trigger@@@Z; DisableTelemetryForCurrentProcess(MarkProcessTelemetryStateFailed_Trigger)
0x1801d1934  mov     edi, eax
  ... truncated ...
```
