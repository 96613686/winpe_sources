# LCIERunAsContentProcess(ushort *,int,ulong,ulong)

- ea: `0x1801bb128`
- end: `0x1801bb7e4`
- name: `?LCIERunAsContentProcess@@YAKPEAGHKK@Z`
- size: `1724`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009ab9c`
- `0x18009abfc`

## callees

- `0x18000b9e0`
- `0x18006f940`
- `0x1800959cc`
- `0x18009aed0`
- `0x1800b72c8`
- `0x1800ee720`
- `0x1800f352c`
- `0x18011bb1c`
- `0x1801b80e0`
- `0x1801b9250`
- `0x1801bb128`
- `0x1801bcb08`
- `0x1801bcecc`
- `0x1801bcf7c`
- `0x1801cd94c`
- `0x1801cfc00`
- `0x1801d0d20`
- `0x1801d0d78`
- `0x180246e7c`
- `0x1802479e8`
- `0x18024ae04`
- `0x18027f778`
- `0x1802801e8`
- `0x180285234`
- `0x1803f4a34`
- `0x180401c1c`
- `0x1804ea658`
- `0x1804ea6ec`
- `0x1804eb6fc`
- `0x1804ebd54`
- `0x1805177b4`
- `0x18052ba60`
- `0x180537c30`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1801bb44c`
- `KERNEL32!InitializeCriticalSection` at `0x1801bb44c`
- `KERNEL32!CreateEventW` at `0x1801bb4ff`
- `KERNEL32!CreateEventW` at `0x1801bb4ff`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801bb264`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x1801bb264`
- `KERNEL32!SetProcessShutdownParameters` at `0x1801bb271`
- `KERNEL32!SetProcessShutdownParameters` at `0x1801bb271`
- `KERNEL32!GetModuleHandleW` at `0x1801bb229`
- `KERNEL32!GetModuleHandleW` at `0x1801bb229`
- `KERNEL32!DeleteCriticalSection` at `0x1801bb748`
- `KERNEL32!DeleteCriticalSection` at `0x1801bb748`
- `KERNEL32!CloseHandle` at `0x1801bb530`
- `KERNEL32!CloseHandle` at `0x1801bb530`
- `KERNEL32!GetLastError` at `0x1801bb257`
- `KERNEL32!GetLastError` at `0x1801bb257`
- `KERNEL32!GetCurrentThreadId` at `0x1801bb211`
- `KERNEL32!GetCurrentThreadId` at `0x1801bb211`
- `KERNEL32!LeaveCriticalSection` at `0x1801bb703`
- `KERNEL32!LeaveCriticalSection` at `0x1801bb703`
- `KERNEL32!EnterCriticalSection` at `0x1801bb6d3`
- `KERNEL32!EnterCriticalSection` at `0x1801bb6d3`
- `KERNEL32!GetProcAddress` at `0x1801bb243`
- `KERNEL32!GetProcAddress` at `0x1801bb243`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x1801bb20b`
- `SHELL32!__imp_SHSetInstanceExplorer` at `0x1801bb20b`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801bb2fa`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801bb787`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801bb2fa`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801bb787`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801bb31e`
- `iertutil!__imp_?IsElevatedProcess@@YAHXZ` at `0x1801bb31e`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801bb4e9`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801bb719`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801bb4e9`
- `iertutil!__imp_?SetUserBroker@@YAJK@Z` at `0x1801bb719`
- `iertutil!__imp_DPA_DestroyCallback` at `0x1801bb6ef`
- `iertutil!__imp_DPA_DestroyCallback` at `0x1801bb6ef`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801bb7b1`
- `iertutil!__imp_?IAS_Close@@YAXXZ` at `0x1801bb7b1`
- `iertutil!__imp_?LCIESetCurrentProcessInPrivate@@YAXXZ` at `0x1801bb551`
- `iertutil!__imp_?LCIESetCurrentProcessInPrivate@@YAXXZ` at `0x1801bb551`
- `iertutil!__imp_SuggestHintKey` at `0x1801bb1da`
- `iertutil!__imp_SuggestHintKey` at `0x1801bb1da`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb173`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb188`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb1c7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb432`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb72d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb173`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb188`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb1c7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb432`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bb72d`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801bb45e`
- `iertutil!__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z` at `0x1801bb45e`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801bb192`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801bb192`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeSecurity` at `0x1801bb352`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeSecurity` at `0x1801bb352`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801bb310`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1801bb310`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801bb781`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1801bb781`
- `api-ms-win-downlevel-shell32-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x1801bb1b4`
- `api-ms-win-downlevel-shell32-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x1801bb1b4`
- `WININET!InternetSetOptionW` at `0x1801bb393`
- `WININET!InternetSetOptionW` at `0x1801bb56e`
- `WININET!InternetSetOptionW` at `0x1801bb699`
- `WININET!InternetSetOptionW` at `0x1801bb393`
- `WININET!InternetSetOptionW` at `0x1801bb56e`
- `WININET!InternetSetOptionW` at `0x1801bb699`
- `MSHTML!InitializeLocalHtmlEngine` at `0x1801bb35d`
- `MSHTML!InitializeLocalHtmlEngine` at `0x1801bb35d`
- `MSHTML!UninitializeLocalHtmlEngine` at `0x1801bb776`
- `MSHTML!UninitializeLocalHtmlEngine` at `0x1801bb776`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x1801bb4ba`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x1801bb4ba`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801bb3e1`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801bb3e1`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801bb711`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801bb711`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801bb709`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801bb709`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801bb5cd`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801bb5cd`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801bb6af`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801bb6af`
- `msIso!__imp_?IsoGetSharedMemoryAddress@@YAJKPEAPEAXPEAK@Z` at `0x1801bb47b`
- `msIso!__imp_?IsoGetSharedMemoryAddress@@YAJKPEAPEAXPEAK@Z` at `0x1801bb47b`
- `msIso!__imp_?IsoSetManagerExitBehavior@@YAJKPEAUIsoScope@@@Z` at `0x1801bb427`
- `msIso!__imp_?IsoSetManagerExitBehavior@@YAJKPEAUIsoScope@@@Z` at `0x1801bb427`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801bb3cf`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801bb3cf`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801bb2e0`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801bb508`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801bb2e0`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801bb508`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801bb7ab`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801bb7ab`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801bb2cc`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801bb2cc`
- `msIso!__imp_?IsoCreateThreadAndComponentFromProcessCreationData@@YAJKPEAKPEAUIsoScope@@@Z` at `0x1801bb5af`
- `msIso!__imp_?IsoCreateThreadAndComponentFromProcessCreationData@@YAJKPEAKPEAUIsoScope@@@Z` at `0x1801bb5af`
- `msIso!__imp_?IsoManagerThreadZero_WindowsPump@@YAK_NPEAUIsoScope@@@Z` at `0x1801bb61c`
- `msIso!__imp_?IsoManagerThreadZero_WindowsPump@@YAK_NPEAUIsoScope@@@Z` at `0x1801bb61c`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801bb3a1`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801bb3a1`
- `msIso!__imp_?LCIEIsCurrentProcessIMPinnedSite@@YA_NXZ` at `0x1801bb737`
- `msIso!__imp_?LCIEIsCurrentProcessIMPinnedSite@@YA_NXZ` at `0x1801bb737`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801bb5f1`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801bb5f1`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1801bb1e8`
- `msIso!__imp_?ProcessGetRefCountAddress@@YAPEAJXZ` at `0x1801bb1e8`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x1801bb200`
- `msIso!__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z` at `0x1801bb200`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801bb796`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801bb79e`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801bb796`
- `msIso!__imp_?ProcessRefCountRelease@@YAKXZ` at `0x1801bb79e`
- `urlmon!__imp_CoInternetSetExtensionsOff` at `0x1801bb17d`
- `urlmon!__imp_CoInternetSetExtensionsOff` at `0x1801bb17d`
- `urlmon!__imp_CreateVersionManager` at `0x1801bb5fc`
- `urlmon!__imp_CreateVersionManager` at `0x1801bb5fc`
- `urlmon!__imp_DestroyVersionManager` at `0x1801bb63a`
- `urlmon!__imp_DestroyVersionManager` at `0x1801bb63a`
- `ieapfltr!DestroyUrlBlockClient` at `0x1801bb634`
- `ieapfltr!DestroyUrlBlockClient` at `0x1801bb634`
- `ieapfltr!CreateUrlBlockClient` at `0x1801bb602`
- `ieapfltr!CreateUrlBlockClient` at `0x1801bb602`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterDestroy` at `0x1801bb62e`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterDestroy` at `0x1801bb62e`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterCreate` at `0x1801bb611`
- `ext-ms-win-wpc-webfilter-l1-1-0!WpcWebFilterCreate` at `0x1801bb611`

## string_xrefs

- `0x1801bb222`: `kernel32.dll`

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
    dword_1806668B8 = 2 - (*(_DWORD *)(v17 + 43) != 0);
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
0x1801bb128  mov     [rsp-8+arg_8], rbx
0x1801bb12d  push    rbp
0x1801bb12e  push    rsi
0x1801bb12f  push    rdi
0x1801bb130  push    r12
0x1801bb132  push    r13
0x1801bb134  push    r14
0x1801bb136  push    r15
0x1801bb138  lea     rbp, [rsp-100h]
0x1801bb140  sub     rsp, 200h
0x1801bb147  mov     rax, cs:__security_cookie
0x1801bb14e  xor     rax, rsp
0x1801bb151  mov     [rbp+130h+var_40], rax
0x1801bb158  xor     r13d, r13d
0x1801bb15b  mov     [rsp+230h+var_1C0], r8d
0x1801bb160  mov     r12d, r13d
0x1801bb163  mov     r15d, r9d
0x1801bb166  mov     rbx, rcx
0x1801bb169  call    ?SetProcessDpiAwareness@@YAXXZ; SetProcessDpiAwareness(void)
0x1801bb16e  mov     ecx, 10000025h
0x1801bb173  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bb179  test    al, al
0x1801bb17b  jz      short loc_1801BB183
0x1801bb17d  call    cs:__imp_CoInternetSetExtensionsOff
0x1801bb183  mov     ecx, 10000009h
0x1801bb188  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bb18e  test    al, al
0x1801bb190  jnz     short loc_1801BB19C
0x1801bb192  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801bb198  test    al, al
0x1801bb19a  jz      short loc_1801BB1C2
0x1801bb19c  lea     r8, [rbp+130h+AppID]; unsigned __int16 *
0x1801bb1a0  mov     rcx, rbx; unsigned __int16 *
0x1801bb1a3  call    ?GetAppIDFromTabCmdArgs@CSiteModeInfo@@SAJPEBG_KPEAG@Z; CSiteModeInfo::GetAppIDFromTabCmdArgs(ushort const *,unsigned __int64,ushort *)
0x1801bb1a8  test    eax, eax
0x1801bb1aa  js      loc_1801BB7B7
0x1801bb1b0  lea     rcx, [rbp+130h+AppID]; AppID
0x1801bb1b4  call    cs:__imp_SetCurrentProcessExplicitAppUserModelID
0x1801bb1ba  test    eax, eax
0x1801bb1bc  js      loc_1801BB7B7
0x1801bb1c2  mov     ecx, 10000004h
0x1801bb1c7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bb1cd  mov     rcx, cs:?IEKEY_Browser_RootHint@SettingStore@@3UKEYID@1@B; SettingStore::KEYID const SettingStore::IEKEY_Browser_RootHint
0x1801bb1d4  mov     cs:?g_fHangRecovery@@3_NA, al; bool g_fHangRecovery
0x1801bb1da  call    cs:__imp_SuggestHintKey
0x1801bb1e0  mov     [rsp+230h+punk], r13
0x1801bb1e5  mov     r14b, r13b
0x1801bb1e8  call    cs:__imp_?ProcessGetRefCountAddress@@YAPEAJXZ; ProcessGetRefCountAddress(void)
0x1801bb1ee  mov     rcx, rax; int *
0x1801bb1f1  lea     rdx, [rsp+230h+punk]; ppv
0x1801bb1f6  call    ?CreateInstance@CTabProcessReference@@SAJPEAJPEAPEAUIUnknown@@@Z; CTabProcessReference::CreateInstance(long *,IUnknown * *)
0x1801bb1fb  mov     rcx, [rsp+230h+punk]
0x1801bb200  call    cs:__imp_?ProcessSetRefCountIUnknown@@YAXPEAUIUnknown@@@Z; ProcessSetRefCountIUnknown(IUnknown *)
0x1801bb206  mov     rcx, [rsp+230h+punk]; punk
0x1801bb20b  call    cs:__imp_SHSetInstanceExplorer
0x1801bb211  call    cs:__imp_GetCurrentThreadId
0x1801bb217  mov     cs:g_tidParking, eax
0x1801bb21d  call    ?IESetProcessExports@@YAXXZ; IESetProcessExports(void)
0x1801bb222  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1801bb229  call    cs:__imp_GetModuleHandleW
0x1801bb22f  mov     ebx, 10h
0x1801bb234  test    rax, rax
0x1801bb237  jz      short loc_1801BB257
0x1801bb239  lea     rdx, aWersetflags; "WerSetFlags"
0x1801bb240  mov     rcx, rax; hModule
0x1801bb243  call    cs:__imp_GetProcAddress
0x1801bb249  test    rax, rax
0x1801bb24c  jz      short loc_1801BB25D
0x1801bb24e  mov     ecx, ebx
0x1801bb250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb255  jmp     short loc_1801BB25D
0x1801bb257  call    cs:__imp_GetLastError
0x1801bb25d  lea     rcx, ?LCIEExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x1801bb264  call    cs:__imp_SetUnhandledExceptionFilter
0x1801bb26a  xor     edx, edx; dwFlags
0x1801bb26c  mov     ecx, 27Fh; dwLevel
0x1801bb271  call    cs:__imp_SetProcessShutdownParameters
0x1801bb277  call    ?CreateLCIEDefinitions@@YAJXZ; CreateLCIEDefinitions(void)
0x1801bb27c  test    eax, eax
0x1801bb27e  js      loc_1801BB79E
0x1801bb284  call    ?LowRightsAware_SetTempFolderForProcess@@YAJXZ; LowRightsAware_SetTempFolderForProcess(void)
0x1801bb289  test    eax, eax
0x1801bb28b  js      loc_1801BB79E
0x1801bb291  call    ?UpdateGlobalCompatibilityFlags@@YAXXZ; UpdateGlobalCompatibilityFlags(void)
0x1801bb296  call    ?AttachShims@@YA_NXZ; AttachShims(void)
0x1801bb29b  test    al, al
0x1801bb29d  jz      loc_1801BB79E
0x1801bb2a3  xor     edx, edx; Val
0x1801bb2a5  lea     rcx, [rbp+130h+var_1A0]; void *
0x1801bb2a9  lea     r8d, [rdx+60h]; Size
0x1801bb2ad  call    memset_0
0x1801bb2b2  lea     rcx, [rbp+130h+var_1A0]; struct SIsoScopeCreationData *
0x1801bb2b6  call    ?InitializeIsoScopeCreationData@@YAXPEAUSIsoScopeCreationData@@@Z; InitializeIsoScopeCreationData(SIsoScopeCreationData *)
0x1801bb2bb  lea     r9, [rbp+130h+var_1A0]
0x1801bb2bf  mov     r8d, r15d
0x1801bb2c2  lea     rdx, [rsp+230h+var_1C0]
0x1801bb2c7  mov     ecx, 201h
0x1801bb2cc  call    cs:__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z; IsoInitDefaultScope(ulong,ulong *,ulong,SIsoScopeCreationData const *)
0x1801bb2d2  test    eax, eax
0x1801bb2d4  js      loc_1801BB79E
0x1801bb2da  mov     r14d, 1
0x1801bb2e0  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801bb2e6  mov     r8, rax
0x1801bb2e9  mov     edx, ebx
0x1801bb2eb  mov     rcx, [rax]
0x1801bb2ee  mov     rax, [rcx+48h]
0x1801bb2f2  mov     rcx, r8
0x1801bb2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb2fa  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1801bb300  test    eax, eax
0x1801bb302  jnz     short loc_1801BB309
0x1801bb304  call    ?InitLrieAppCompatLogger@@YAJXZ; InitLrieAppCompatLogger(void)
0x1801bb309  mov     edx, 2; dwCoInit
0x1801bb30e  xor     ecx, ecx; pvReserved
0x1801bb310  call    cs:__imp_CoInitializeEx
0x1801bb316  test    eax, eax
0x1801bb318  js      loc_1801BB787
0x1801bb31e  call    cs:__imp_?IsElevatedProcess@@YAHXZ; IsElevatedProcess(void)
0x1801bb324  test    eax, eax
0x1801bb326  jnz     short loc_1801BB35D
0x1801bb328  mov     [rsp+230h+pReserved3], r13; pReserved3
0x1801bb32d  xor     r9d, r9d; pReserved1
0x1801bb330  mov     [rsp+230h+dwCapabilities], r13d; dwCapabilities
0x1801bb335  xor     r8d, r8d; asAuthSvc
0x1801bb338  mov     [rsp+230h+pAuthList], r13; pAuthList
0x1801bb33d  or      edx, 0FFFFFFFFh; cAuthSvc
0x1801bb340  mov     [rsp+230h+dwImpLevel], 3; dwImpLevel
0x1801bb348  xor     ecx, ecx; pSecDesc
0x1801bb34a  mov     [rsp+230h+dwAuthnLevel], 2; dwAuthnLevel
0x1801bb352  call    cs:__imp_CoInitializeSecurity
0x1801bb358  call    ?RefreshTabProtectedPolicies@@YAJXZ; RefreshTabProtectedPolicies(void)
0x1801bb35d  call    cs:__imp_InitializeLocalHtmlEngine
0x1801bb363  test    eax, eax
0x1801bb365  js      loc_1801BB77C
0x1801bb36b  mov     rcx, cs:?IEVALUE_wininet_BackgroundConnections@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_wininet_BackgroundConnections
0x1801bb372  lea     rdx, [rsp+230h+Buffer]
0x1801bb377  mov     [rsp+230h+Buffer], r14d
0x1801bb37c  call    GetBOOL
0x1801bb381  mov     ebx, 4
0x1801bb386  lea     r8, [rsp+230h+Buffer]; lpBuffer
0x1801bb38b  mov     r9d, ebx; dwBufferLength
0x1801bb38e  xor     ecx, ecx; hInternet
0x1801bb390  lea     edx, [rbx+75h]; dwOption
0x1801bb393  call    cs:__imp_InternetSetOptionW
0x1801bb399  test    eax, eax
0x1801bb39b  jz      loc_1801BB776
0x1801bb3a1  call    cs:__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ; IsoSubscriptionManager(void)
0x1801bb3a7  lea     r9, _ScopeProcessCallback
0x1801bb3ae  mov     qword ptr [rsp+230h+dwAuthnLevel], r13
0x1801bb3b3  mov     r10, rax
0x1801bb3b6  xor     r8d, r8d
0x1801bb3b9  mov     edx, ebx
0x1801bb3bb  mov     rcx, [rax]
0x1801bb3be  mov     rax, [rcx+38h]
0x1801bb3c2  mov     rcx, r10
0x1801bb3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb3ca  mov     [rsp+230h+var_1D0], r13
0x1801bb3cf  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801bb3d5  xor     r9d, r9d
0x1801bb3d8  lea     r8, [rsp+230h+var_1D0]
0x1801bb3dd  mov     ecx, eax
0x1801bb3df  mov     dl, 14h
0x1801bb3e1  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x1801bb3e7  test    eax, eax
0x1801bb3e9  js      loc_1801BB776
0x1801bb3ef  mov     rcx, [rsp+230h+var_1D0]
0x1801bb3f4  lea     r8, ?LCIETabManagerWinProc@@YA_JPEAUHWND__@@I_K_J@Z; LCIETabManagerWinProc(HWND__ *,uint,unsigned __int64,__int64)
0x1801bb3fb  mov     edx, ebx
0x1801bb3fd  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x1801bb402  mov     rax, [rsp+230h+var_1D0]
0x1801bb407  lea     rdx, [rsp+230h+var_1E0]; unsigned int *
0x1801bb40c  xor     ecx, ecx; unsigned int *
0x1801bb40e  mov     [rsp+230h+var_1E0], r13d
0x1801bb413  btr     dword ptr [rax+14h], 19h
0x1801bb418  call    ?GetEmptyTabTimeoutAndContentProcessShutdownDelay@@YAJPEAK0@Z; GetEmptyTabTimeoutAndContentProcessShutdownDelay(ulong *,ulong *)
0x1801bb41d  mov     ecx, [rsp+230h+var_1E0]
0x1801bb421  test    ecx, ecx
0x1801bb423  jz      short loc_1801BB42D
0x1801bb425  xor     edx, edx
0x1801bb427  call    cs:__imp_?IsoSetManagerExitBehavior@@YAJKPEAUIsoScope@@@Z; IsoSetManagerExitBehavior(ulong,IsoScope *)
0x1801bb42d  mov     ecx, 10000009h
0x1801bb432  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bb438  test    al, al
0x1801bb43a  jz      short loc_1801BB452
0x1801bb43c  call    ?_GetTabInfo@CSiteModeInfo@@CAJXZ; CSiteModeInfo::_GetTabInfo(void)
0x1801bb441  test    eax, eax
0x1801bb443  js      short loc_1801BB452
0x1801bb445  lea     rcx, ?s_csSiteModeInfo@CSiteModeInfo@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801bb44c  call    cs:__imp_InitializeCriticalSection
0x1801bb452  call    ?GetCurrentIsoProcessEnterpriseIDHandle@EnterpriseIdManager@@YAKXZ; EnterpriseIdManager::GetCurrentIsoProcessEnterpriseIDHandle(void)
0x1801bb457  mov     edx, eax
0x1801bb459  mov     ecx, 20000011h
0x1801bb45e  call    cs:__imp_?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x1801bb464  lea     r8, [rsp+230h+var_1D4]
0x1801bb469  mov     [rsp+230h+var_1B8], r13
0x1801bb46e  lea     rdx, [rsp+230h+var_1B8]
0x1801bb473  mov     [rsp+230h+var_1D4], r13d
0x1801bb478  mov     ecx, r15d
0x1801bb47b  call    cs:__imp_?IsoGetSharedMemoryAddress@@YAJKPEAPEAXPEAK@Z; IsoGetSharedMemoryAddress(ulong,void * *,ulong *)
0x1801bb481  test    eax, eax
0x1801bb483  js      loc_1801BB776
0x1801bb489  cmp     [rsp+230h+var_1D4], 164h
0x1801bb491  jb      loc_1801BB776
0x1801bb497  mov     rsi, [rsp+230h+var_1B8]
0x1801bb49c  lea     rdx, [rbp+130h+var_1A8]
0x1801bb4a0  mov     r9d, 80h
0x1801bb4a6  mov     [rsp+230h+var_1E0], r13d
0x1801bb4ab  lea     rcx, IID_IEUserBroker
0x1801bb4b2  mov     [rbp+130h+var_1A8], r13
0x1801bb4b6  lea     r8, [rsi+2Fh]
0x1801bb4ba  call    cs:__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z; LCIEUnmarshalInterfaceFromBuffer(_GUID const &,void * *,uchar *,unsigned __int64)
0x1801bb4c0  test    eax, eax
0x1801bb4c2  js      loc_1801BB728
0x1801bb4c8  mov     rcx, [rbp+130h+var_1A8]
0x1801bb4cc  lea     r8, [rsp+230h+var_1E0]
0x1801bb4d1  lea     rdx, IID_IEUserBroker
0x1801bb4d8  call    MarshalToGIT
0x1801bb4dd  test    eax, eax
0x1801bb4df  js      loc_1801BB728
0x1801bb4e5  mov     ecx, [rsp+230h+var_1E0]
0x1801bb4e9  call    cs:__imp_?SetUserBroker@@YAJK@Z; SetUserBroker(ulong)
0x1801bb4ef  mov     edi, eax
0x1801bb4f1  test    eax, eax
0x1801bb4f3  js      short loc_1801BB53B
0x1801bb4f5  xor     r9d, r9d; lpName
0x1801bb4f8  xor     r8d, r8d; bInitialState
0x1801bb4fb  xor     edx, edx; bManualReset
0x1801bb4fd  xor     ecx, ecx; lpEventAttributes
0x1801bb4ff  call    cs:__imp_CreateEventW
0x1801bb505  mov     rbx, rax
0x1801bb508  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801bb50e  mov     r8, rbx
0x1801bb511  mov     edx, 19h
0x1801bb516  mov     r9, rax
0x1801bb519  mov     rcx, [rax]
0x1801bb51c  mov     rax, [rcx+0F8h]
0x1801bb523  mov     rcx, r9
0x1801bb526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb52b  mov     rcx, rbx; hObject
0x1801bb52e  mov     edi, eax
0x1801bb530  call    cs:__imp_CloseHandle
0x1801bb536  mov     ebx, 4
0x1801bb53b  mov     eax, [rsi+2Bh]
0x1801bb53e  neg     eax
0x1801bb540  sbb     ecx, ecx
0x1801bb542  add     ecx, 2
0x1801bb545  test    byte ptr [rsi+23h], 40h
0x1801bb549  mov     cs:dword_1806668B8, ecx
0x1801bb54f  jz      short loc_1801BB588
0x1801bb551  call    cs:__imp_?LCIESetCurrentProcessInPrivate@@YAXXZ; LCIESetCurrentProcessInPrivate(void)
0x1801bb557  mov     r9d, ebx; dwBufferLength
0x1801bb55a  mov     [rsp+230h+var_1DC], 3
0x1801bb562  lea     r8, [rsp+230h+var_1DC]; lpBuffer
0x1801bb567  mov     edx, 51h ; 'Q'; dwOption
0x1801bb56c  xor     ecx, ecx; hInternet
0x1801bb56e  call    cs:__imp_InternetSetOptionW
0x1801bb574  test    eax, eax
0x1801bb576  jz      loc_1801BB717
0x1801bb57c  mov     ecx, 5
0x1801bb581  call    ?DisableTelemetryForCurrentProcess@@YAJW4MarkProcessTelemetryStateFailed_Trigger@@@Z; DisableTelemetryForCurrentProcess(MarkProcessTelemetryStateFailed_Trigger)
0x1801bb586  mov     edi, eax
0x1801bb588  test    edi, edi
0x1801bb58a  js      loc_1801BB717
0x1801bb590  call    ?ProcessPICOperationalChanges@@YAJXZ; ProcessPICOperationalChanges(void)
0x1801bb595  test    eax, eax
0x1801bb597  js      loc_1801BB717
0x1801bb59d  mov     rax, [rsp+230h+var_1B8]
0x1801bb5a2  cmp     byte ptr [rax], 14h
0x1801bb5a5  jnz     short loc_1801BB5BD
0x1801bb5a7  xor     r8d, r8d
0x1801bb5aa  xor     edx, edx
0x1801bb5ac  mov     ecx, r15d
0x1801bb5af  call    cs:__imp_?IsoCreateThreadAndComponentFromProcessCreationData@@YAJKPEAKPEAUIsoScope@@@Z; IsoCreateThreadAndComponentFromProcessCreationData(ulong,ulong *,IsoScope *)
0x1801bb5b5  test    eax, eax
0x1801bb5b7  js      loc_1801BB717
0x1801bb5bd  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x1801bb5c2  test    al, al
0x1801bb5c4  jz      short loc_1801BB5CB
0x1801bb5c6  call    ?SignalIEInitializedEvent@@YAXXZ; SignalIEInitializedEvent(void)
0x1801bb5cb  xor     ecx, ecx
0x1801bb5cd  call    cs:__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z; IsoInitializeThread(IsoScope *)
0x1801bb5d3  test    eax, eax
0x1801bb5d5  js      loc_1801BB6BE
0x1801bb5db  lea     rcx, [rsp+230h+var_1DC]; unsigned int *
0x1801bb5e0  mov     [rsp+230h+var_1DC], r13d
0x1801bb5e5  call    ?StartThumbnailServices@@YAJPEAK@Z; StartThumbnailServices(ulong *)
0x1801bb5ea  lea     rcx, ?LCIEOnCreateProcess@@YAJ_NJPEAU_IsoCreationProcessData@@@Z; LCIEOnCreateProcess(bool,long,_IsoCreationProcessData *)
0x1801bb5f1  call    cs:__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z; IsoSetCreateProcessCallback(long (*)(bool,long,_IsoCreationProcessData *))
0x1801bb5f7  call    ?AsyncKeyState_Initialize@@YAJXZ; AsyncKeyState_Initialize(void)
0x1801bb5fc  call    cs:__imp_CreateVersionManager
0x1801bb602  call    cs:__imp_CreateUrlBlockClient
0x1801bb608  call    ?WpcWebFilterIsEnabledForCurrentUser@@YAHXZ; WpcWebFilterIsEnabledForCurrentUser(void)
0x1801bb60d  test    eax, eax
0x1801bb60f  jz      short loc_1801BB617
0x1801bb611  call    cs:__imp_WpcWebFilterCreate
0x1801bb617  xor     edx, edx
0x1801bb619  mov     cl, r14b
0x1801bb61c  call    cs:__imp_?IsoManagerThreadZero_WindowsPump@@YAK_NPEAUIsoScope@@@Z; IsoManagerThreadZero_WindowsPump(bool,IsoScope *)
0x1801bb622  mov     r12d, eax
0x1801bb625  call    ?WpcWebFilterIsEnabledForCurrentUser@@YAHXZ; WpcWebFilterIsEnabledForCurrentUser(void)
  ... truncated ...
```
