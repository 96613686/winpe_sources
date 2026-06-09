# wWinMain

- ea: `0x1400a3f04`
- end: `0x1400a4ec6`
- name: `wWinMain`
- size: `4034`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `71`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14010dfb0`

## callees

- `0x140005ef0`
- `0x140006edc`
- `0x14000a2c4`
- `0x14000bb20`
- `0x14000d500`
- `0x140010fb4`
- `0x140012594`
- `0x14001b2c8`
- `0x14001c39c`
- `0x14001c4f8`
- `0x1400214b0`
- `0x140023118`
- `0x14004566c`
- `0x140046398`
- `0x1400468fc`
- `0x140047148`
- `0x140049308`
- `0x140066ba0`
- `0x14006a074`
- `0x14006a2d0`
- `0x14006a318`
- `0x14006a720`
- `0x140078c58`
- `0x14007abfc`
- `0x14007b4bc`
- `0x14007c1a0`
- `0x14007d980`
- `0x14007f92c`
- `0x140080f98`
- `0x140082630`
- `0x140084a38`
- `0x140084bf0`
- `0x140084ca4`
- `0x140085634`
- `0x1400858bc`
- `0x140085e18`
- `0x140086e78`
- `0x140087778`
- `0x14008de90`
- `0x14008fa98`
- `0x140090720`
- `0x140090a44`
- `0x140090ad8`
- `0x140090c2c`
- `0x1400933d8`
- `0x140093414`
- `0x140093450`
- `0x1400a3364`
- `0x1400a3ea4`
- `0x1400a3f04`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x1400a41ce`
- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x1400a41ce`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x1400a4789`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x1400a4b2c`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x1400a4789`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x1400a4b2c`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x1400a4721`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x1400a4721`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400a4e5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400a4e5f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a3f75`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400a3f75`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400a4335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400a4ad3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400a4335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400a4ad3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400a41c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400a41c0`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1400a411f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1400a411f`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400a4212`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400a4362`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400a4212`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x1400a4362`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x1400a4477`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x1400a4477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400a4bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400a4bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400a41fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400a4350`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400a41fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400a4350`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400a4761`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400a4e7e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400a4761`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400a4e7e`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x1400a4665`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x1400a4665`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1400a3f88`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1400a3f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a4344`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a4ae2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a4344`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400a4ae2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400a426f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400a426f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a48ef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400a48ef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400a4561`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400a4cf3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400a4561`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400a4cf3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a444c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a4505`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a4837`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a4b89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a444c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a4505`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a4837`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400a4b89`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400a4282`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400a43de`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400a4db5`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400a4282`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400a43de`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1400a4db5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1400a4291`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1400a43ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1400a4dc4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1400a4291`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1400a43ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1400a4dc4`
- `api-ms-win-shcore-sysinfo-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x1400a41af`
- `api-ms-win-shcore-sysinfo-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x1400a41af`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadRef` at `0x1400a4936`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadRef` at `0x1400a4936`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x1400a4964`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x1400a4964`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x1400a4947`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x1400a4947`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1400a4e30`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1400a4e30`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1400a4c00`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1400a4c00`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400a454d`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400a454d`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x1400a3fbf`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x1400a3fbf`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!EnableMouseInPointer` at `0x1400a4220`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!EnableMouseInPointer` at `0x1400a4220`
- `api-ms-win-storage-exports-internal-l1-1-0!SetThreadFlags` at `0x1400a46d5`
- `api-ms-win-storage-exports-internal-l1-1-0!SetThreadFlags` at `0x1400a46d5`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x1400a47f7`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x1400a47f7`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!UnhookWinEvent` at `0x1400a4d10`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!UnhookWinEvent` at `0x1400a4d10`
- `SHELL32!ShellExecuteExW` at `0x1400a43ad`
- `SHELL32!ShellExecuteExW` at `0x1400a43ad`
- `SHELL32!__imp_ShellDDEInit` at `0x1400a4654`
- `SHELL32!__imp_ShellDDEInit` at `0x1400a4d01`
- `SHELL32!__imp_ShellDDEInit` at `0x1400a4654`
- `SHELL32!__imp_ShellDDEInit` at `0x1400a4d01`
- `SHELL32!__imp_SHDesktopMessageLoop` at `0x1400a4c0f`
- `SHELL32!__imp_SHDesktopMessageLoop` at `0x1400a4c0f`
- `SHELL32!__imp_SHCloseDesktopHandle` at `0x1400a4c49`
- `SHELL32!__imp_SHCloseDesktopHandle` at `0x1400a4c49`
- `SHELL32!__imp_SetExplorerServerMode` at `0x1400a42f2`
- `SHELL32!__imp_SetExplorerServerMode` at `0x1400a42f2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400a4b0a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400a4b0a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x1400a4699`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x1400a4699`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x1400a42c5`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x1400a42c5`
- `ole32!OleUninitialize` at `0x1400a4ce2`
- `ole32!OleUninitialize` at `0x1400a4ce2`
- `ole32!OleInitialize` at `0x1400a46b4`
- `ole32!OleInitialize` at `0x1400a46b4`
- `WinLangdb!EnsureLanguageProfileExists` at `0x1400a48ff`
- `WinLangdb!EnsureLanguageProfileExists` at `0x1400a48ff`
- `DUI70!SkipDLLUnloadInitChecks` at `0x1400a4e70`
- `DUI70!SkipDLLUnloadInitChecks` at `0x1400a4e70`
- `NInput!__imp_ConfigureDownlevelInput` at `0x1400a42e4`
- `NInput!__imp_ConfigureDownlevelInput` at `0x1400a42e4`

## string_xrefs

- `0x1400a4eb4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1400a48a8`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a4393`: `OpenNewWindow`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int CurrentProcessExecutionOptionNoThrow; // eax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int v9; // r9d
  const unsigned __int16 *v10; // rdx
  const struct _TRACE_INFO *v11; // rcx
  __int64 v12; // r8
  int v13; // eax
  HANDLE CurrentProcess; // rax
  const WCHAR *CommandLineW; // rax
  LPWSTR ArgsW; // rax
  unsigned int v17; // ebx
  int v18; // eax
  HANDLE v19; // rdi
  HANDLE v20; // rax
  int v21; // edi
  const WCHAR *v22; // rax
  unsigned __int16 *v23; // rax
  int lpIDList_low; // eax
  int v25; // ebx
  _QWORD *v26; // rax
  __int64 v27; // r8
  int v28; // r12d
  HRESULT v29; // r13d
  bool v30; // cl
  char v31; // bl
  bool v32; // si
  int v33; // eax
  bool v34; // zf
  int v35; // eax
  bool v36; // r14
  HINSTANCE DesktopAndTray; // rdi
  HWINEVENTHOOK v38; // r15
  int v39; // eax
  wil::details::in1diag3 *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r8
  HANDLE v44; // rbx
  HRESULT v45; // eax
  __int64 v46; // r8
  HANDLE CurrentThread; // rax
  CHAR *v48; // rdx
  WORD *v49; // r8
  WORD *v50; // r9
  const WCHAR *v51; // rax
  unsigned __int16 *v52; // rax
  const unsigned __int16 *v53; // rdx
  const struct _TRACE_INFO *v54; // rcx
  _QWORD *v55; // rbx
  TRACEHANDLE v56; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  int dwOptionsc; // [rsp+20h] [rbp-E0h]
  int dwOptionsd; // [rsp+20h] [rbp-E0h]
  LPVOID v63; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  void **v65; // [rsp+60h] [rbp-A0h] BYREF
  LONG pcRef; // [rsp+68h] [rbp-98h] BYREF
  IUnknown *ppunk; // [rsp+70h] [rbp-90h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+80h] [rbp-80h] BYREF
  struct tagMSG Msg; // [rsp+F0h] [rbp-10h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v71; // [rsp+130h] [rbp+30h] BYREF
  __int64 v72; // [rsp+140h] [rbp+40h]
  ULONG_PTR dwData[3]; // [rsp+150h] [rbp+50h] BYREF
  int v74; // [rsp+168h] [rbp+68h]
  __int64 v75; // [rsp+16Ch] [rbp+6Ch]
  __int64 v76; // [rsp+178h] [rbp+78h]
  __int64 v77; // [rsp+180h] [rbp+80h]
  char v78; // [rsp+188h] [rbp+88h]
  __int128 v79; // [rsp+190h] [rbp+90h]
  __int128 v80; // [rsp+1A0h] [rbp+A0h]
  __int128 v81; // [rsp+1B0h] [rbp+B0h]
  char v82; // [rsp+1C0h] [rbp+C0h]
  int v83; // [rsp+1C4h] [rbp+C4h]
  int v84; // [rsp+1C8h] [rbp+C8h]
  _BYTE v85[112]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v86; // [rsp+240h] [rbp+140h]
  int v87; // [rsp+250h] [rbp+150h]
  char v88; // [rsp+254h] [rbp+154h]
  __int64 v89; // [rsp+258h] [rbp+158h]
  __int128 v90; // [rsp+260h] [rbp+160h]
  __int128 v91; // [rsp+270h] [rbp+170h]
  __int64 v92; // [rsp+280h] [rbp+180h]
  __int64 v93; // [rsp+288h] [rbp+188h]
  _QWORD v94[42]; // [rsp+290h] [rbp+190h] BYREF
  CLogonTaskFramework *v95[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  HANDLE hMutex[2]; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v97[4]; // [rsp+400h] [rbp+300h] BYREF
  wil::details *retaddr; // [rsp+468h] [rbp+368h]

  while ( 1 )
  {
    LODWORD(v63) = 1;
    CurrentProcessExecutionOptionNoThrow = wil::details::GetCurrentProcessExecutionOptionNoThrow(
                                             (wil::details *)hInstance,
                                             (const unsigned __int16 *)hPrevInstance,
                                             (unsigned int)&v63,
                                             *(unsigned int **)&nShowCmd);
    if ( CurrentProcessExecutionOptionNoThrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)CurrentProcessExecutionOptionNoThrow,
        dwOptions);
    v6 = (int)v63;
    if ( !(_DWORD)v63 )
      break;
    if ( wil::details::IsDebuggerPresent(retaddr) )
    {
      if ( v6 == 2 )
        DebugBreak();
      break;
    }
    Sleep(0x1F4u);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerLongPath2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FileExplorerLongPath2>::GetImpl'::`2'::impl) )
    NtCurrentPeb()->BitField = NtCurrentPeb()->BitField | 0x80;
  DXGIDeclareAdapterRemovalSupport();
  qword_14024FF70 = 0;
  WPP_MAIN_CB = (__int64)&qword_14024FF88;
  qword_14024FF78 = 1;
  qword_14024FF98 = 0;
  qword_14024FF88 = (__int64)&qword_14024FFB0;
  qword_14024FFA0 = 1;
  qword_14024FFC0 = 0;
  qword_14024FFB0 = (__int64)&qword_14024FFD8;
  qword_14024FFC8 = 1;
  qword_14024FFE8 = 0;
  qword_14024FFD8 = (__int64)&qword_140250000;
  qword_14024FFF0 = 1;
  qword_140250010 = 0;
  qword_140250000 = (__int64)&qword_140250028;
  qword_140250018 = 1;
  qword_140250038 = 0;
  qword_140250028 = 0;
  qword_140250040 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShellTraceProvider;
  qword_14024FF38 = (__int64)WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
  qword_14024FF40 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
  qword_14024FF48 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider;
  qword_14024FF50 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider;
  qword_14024FF58 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WppInitUm();
  McGenEventRegister_EventRegister(
    Microsoft_Windows_Shell_Core_Provider,
    v7,
    &Microsoft_Windows_Shell_Core_Provider_Context,
    &Microsoft_Windows_Shell_Core_Provider_Context);
  McGenEventRegister_EventRegister(
    MICROSOFT_TWINAPI_PUBLISHER,
    v8,
    MICROSOFT_TWINAPI_PUBLISHER_Context,
    MICROSOFT_TWINAPI_PUBLISHER_Context);
  EventSetInformation(
    Microsoft_Windows_Shell_Core_Provider_Context,
    2,
    &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
    (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  LODWORD(v63) = 0;
  SHRegGetBOOLWithREGSAM(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
    L"ExplorerStartupTraceRecorded",
    v9,
    (int *)&v63);
  if ( !(_DWORD)v63 )
  {
    StartLogging(v11, v10);
    SHRegSetBOOL(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
      L"ExplorerStartupTraceRecorded",
      1);
  }
  if ( (byte_14024FCC1 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Explorer_InitializingExplorer_Start,
      v12,
      1,
      hMutex);
  SetCurrentProcessExplicitAppUserModelID(L"Microsoft.Windows.Explorer");
  SetErrorMode(0x4001u);
  _set_error_mode(1);
  v13 = SeverBamChildConnectionsForProcess();
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x505,
      (unsigned int)"pcshell\\shell\\explorer\\initcab.cpp",
      (const char *)(unsigned int)v13,
      dwOptionsa);
  CurrentProcess = GetCurrentProcess();
  SetPriorityClass(CurrentProcess, 0x80u);
  EnableMouseInPointer(0);
  g_hinstCabinet = hInstance;
  Cabinet_InitGlobalMetrics(0, 0);
  RegCreateKeyExW(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
    0,
    0,
    0,
    0x2000000u,
    0,
    &g_hkeyExplorer,
    0);
  hMutex[0] = 0;
  CommandLineW = GetCommandLineW();
  ArgsW = PathGetArgsW(CommandLineW);
  ExplorerServerConfiguration::Create(&ppv, ArgsW, hMutex);
  v17 = HIDWORD(ppv);
  if ( m_firstProcessEntry )
  {
    RmEnableLimits(L"explorer");
    m_firstProcessEntry = 0;
  }
  if ( v17 != 5 )
    ConfigureDownlevelInput("-HorizontalScrollMode 2 -VerticalScrollMode 2");
  v18 = SetExplorerServerMode(v17);
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x532,
      (unsigned int)"pcshell\\shell\\explorer\\initcab.cpp",
      (const char *)(unsigned int)v18,
      dwOptionsb);
  if ( v17 != 3 )
  {
    v19 = hMutex[0];
    if ( hMutex[0] )
    {
      ReleaseMutex(hMutex[0]);
      CloseHandle(v19);
    }
    v20 = GetCurrentProcess();
    SetPriorityClass(v20, 0x20u);
    if ( v17 == 5 )
    {
      pExecInfo.cbSize = 112;
      memset_0(&pExecInfo.fMask, 0, 0x6Cu);
      pExecInfo.nShow = 1;
      pExecInfo.fMask = 33554700;
      pExecInfo.lpVerb = L"OpenNewWindow";
      pExecInfo.lpFile = L"shell:::{52205fd8-5dfb-447d-801a-d0b52f2e83e1}";
      ShellExecuteExW(&pExecInfo);
    }
    else
    {
      v21 = SHCoInitialize();
      if ( v21 >= 0 )
      {
        *(_OWORD *)pidl = 0;
        v71 = 0;
        v72 = 0;
        v22 = GetCommandLineW();
        v23 = PathGetArgsW(v22);
        if ( (unsigned int)SHExplorerParseCmdLine(v23, pidl) )
        {
          SetExplorerComGlobalOptions();
          if ( ((v17 - 4) & 0xFFFFFFFD) != 0 )
          {
            ppv = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
            if ( CoCreateInstance(&CLSID_ExplorerLauncher, 0, 1u, &GUID_9b25c299_03b6_4a14_827d_095485d0c022, &ppv) >= 0 )
            {
              *(_QWORD *)&pExecInfo.cbSize = 104;
              memset_0(&pExecInfo.hwnd, 0, 0x60u);
              GetStartupInfoW((LPSTARTUPINFOW)&pExecInfo);
              lpIDList_low = LOWORD(pExecInfo.lpIDList);
              if ( (BYTE4(pExecInfo.hInstApp) & 1) == 0 )
                lpIDList_low = 10;
              (*(void (__fastcall **)(LPVOID, GUID *, LPITEMIDLIST, _QWORD, _QWORD, int, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                &CLSID_SeparateMultipleProcessExplorerHost,
                pidl[0],
                DWORD1(v71),
                0,
                lpIDList_low,
                0,
                0,
                0);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          }
          else
          {
            v63 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
            if ( CoCreateInstance(&CLSID_ExplorerHostCreator, 0, 1u, &GUID_c4de032a_d902_450a_bc43_d9df6d0fd48c, &v63) >= 0
              && (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v63 + 24LL))(v63, (char *)&v71 + 8) >= 0 )
            {
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v63 + 32LL))(v63);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
          }
          ILFree(pidl[0]);
        }
        if ( !v21 )
          CoUninitialize();
      }
    }
    goto LABEL_106;
  }
  LODWORD(v63) = 0;
  if ( BYTE3(ppv) && BYTE1(ppv) )
  {
    v25 = 1;
  }
  else
  {
    v33 = SHIsCurrentAppElevated(&v63);
    v25 = (int)v63;
    if ( v33 >= 0 && (_DWORD)v63 )
    {
      LODWORD(v63) = 0;
      v34 = (unsigned int)CheckElevationEnabled(&v63) == 0;
      v35 = 1;
      if ( v34 )
        v35 = (int)v63;
      if ( v35
        && !(unsigned int)SHIsCurrentAccountBuiltInAdmin()
        && (int)RunExplorerUnelevated((const struct ExplorerServerConfiguration *)&ppv) >= 0 )
      {
        ExitProcess(2u);
      }
    }
  }
  ppv = 0;
  v26 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::ensure_data(&ppv);
  tip2::details::shared_data<1,0,0>::start(*v26 + 8LL, v95);
  if ( (byte_14024FCC3 & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_PerfTrack_Explorer_ExplorerStartToDesktopReady_Start,
      v27,
      1,
      v95);
  if ( (byte_14024FCC1 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      PerfTrack_Launcher_Login_Start,
      v27,
      1,
      v95);
  wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v94,
    "ExplorerBoot");
  v94[0] = &ExplorerTelemetry::ExplorerBoot::`vftable';
  ExplorerTelemetry::ExplorerBoot::StartActivity((ExplorerTelemetry::ExplorerBoot *)v94);
  DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener::CDwmWnfDumpRequestListener((DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener *)pidl);
  pidl[0] = (LPITEMIDLIST)&DwmWnfDiagnosticEvent::CDwmWnfSimpleDumpRequestListener::`vftable';
  LODWORD(v71) = 4;
  *((_QWORD *)&v71 + 1) = L"Hotkey_Explorer";
  ShellDDEInit(1);
  SetProcessShutdownParameters(3u, 0);
  _AutoRunTaskMan();
  memset(&Msg, 0, sizeof(Msg));
  PeekMessageW(&Msg, 0, 0x12u, 0x12u, 0);
  WaitForSCMToInitialize();
  v28 = SHCoInitialize();
  v29 = OleInitialize(0);
  SetExplorerComGlobalOptions();
  if ( v25 )
    InitializeSecurityToAllowAppContainerComUse(v30);
  SetThreadFlags(1, 1);
  if ( IsDesktopWindowAlreadyPresent() )
  {
    v31 = 1;
    v32 = 0;
  }
  else
  {
    v31 = 0;
    v32 = 0;
    if ( IsUserOOBE() )
      v32 = RegisterApplicationRestart(L"/LOADSAVEDWINDOWS", 0x80000008) >= 0;
  }
  v95[0] = 0;
  CImmersiveColorImpl::GetColorPreferenceImpl((struct IMMERSIVE_COLOR_PREFERENCE *)v95, 0, 1);
  v36 = CheckOobeColorSelection();
  CheckDefaultUIFonts();
  ChangeUIfontsToNewDPI();
  CheckForServerAdminUI();
  CheckHighContrast();
  EnableDpiScaledPadding(1);
  DesktopAndTray = 0;
  v38 = SetWinEventHook(0x20u, 0x20u, 0, CheckHighContrastAfterDesktopSwitch, 0, 0, 0);
  v63 = 0;
  if ( !v31 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
    if ( CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8, &v63) >= 0 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v63 + 32LL))(v63);
  }
  v95[0] = 0;
  Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(v95);
  v39 = Microsoft::WRL::Details::MakeAndInitialize<CLogonTaskFramework,CLogonTaskFramework,>(v95);
  v40 = retaddr;
  if ( v39 < 0 )
  {
    v41 = 13185;
LABEL_69:
    wil::details::in1diag3::_Log_Hr(
      v40,
      (void *)v41,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v39,
      dwOptionsc);
    goto LABEL_70;
  }
  v39 = CLogonTaskFramework::RunAllLogonTasks(v95[0]);
  v40 = retaddr;
  if ( v39 < 0 )
  {
    v41 = 13187;
    goto LABEL_69;
  }
LABEL_70:
  Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(v95);
  CreateShellDirectories();
  if ( RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\International\\User Profile", L"Languages", 0x20u, 0, 0, 0) )
    EnsureLanguageProfileExists();
  Windows::Internal::ComTaskPool::QueueTask__lambda_88be06634823c65cb119d70f83a8f03b___();
  WriteCleanShutdown(0);
  v65 = &CThreadRefHost::`vftable';
  pcRef = 0;
  ppunk = 0;
  SHCreateThreadRef(&pcRef, &ppunk);
  SHSetThreadRef(ppunk);
  v65 = &CThreadRefHost::`vftable';
  SetProcessReference(ppunk);
  if ( !v31 )
  {
    ExplorerTelemetry::ExplorerBoot::ExplorerBoot_TrayAndDesktopInit((ExplorerTelemetry::ExplorerBoot *)v94);
    DesktopAndTray = (HINSTANCE)CreateDesktopAndTray();
  }
  if ( byte_14024FCC2 < 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Activation_Watermark_Init_Start,
      v42,
      1,
      v95);
  LOWORD(dwData[0]) = 0;
  dwData[1] = 0;
  dwData[2] = 0;
  v74 = 6;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  memset_0(v85, 0, sizeof(v85));
  v86 = 0;
  v75 = 0;
  v84 = 0;
  ExplorerTelemetry::ExplorerBoot::ExplorerBoot_ImmersiveWatermarkCreate((ExplorerTelemetry::ExplorerBoot *)v94);
  CImmersiveWatermark::Initialize(dwData);
  if ( byte_14024FCC2 < 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Activation_Watermark_Init_Stop,
      v43,
      1,
      v97);
  if ( !v36 )
  {
    v95[0] = 0;
    CImmersiveColorImpl::GetColorPreferenceImpl((struct IMMERSIVE_COLOR_PREFERENCE *)v95, 1, 1);
  }
  v44 = hMutex[0];
  if ( hMutex[0] )
  {
    ReleaseMutex(hMutex[0]);
    CloseHandle(v44);
  }
  if ( DesktopAndTray )
  {
    PostMessageW(v_hwndTray, 0x590u, 1u, 0);
    EnsureTabletButtonThreadRunningIfNeeded();
    if ( !v32 )
    {
      v45 = RegisterApplicationRestart(L"/LOADSAVEDWINDOWS", 0x80000008);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x631,
          (unsigned int)"pcshell\\shell\\explorer\\initcab.cpp",
          (const char *)(unsigned int)v45,
          dwOptionsd);
    }
    hMutex[0] = 0;
    v95[0] = 0;
    if ( CoCreateInstance(&CLSID_ExplorerHostCreator, 0, 1u, &GUID_c4de032a_d902_450a_bc43_d9df6d0fd48c, (LPVOID *)v95) >= 0 )
      (*(void (__fastcall **)(CLogonTaskFramework *, GUID *))(*(_QWORD *)v95[0] + 24LL))(
        v95[0],
        &CLSID_DesktopExplorerHost);
    if ( (byte_14024FCC1 & 0x20) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        Explorer_MessageLoop_Start,
        v46,
        1,
        v97);
    wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v94);
    CurrentThread = GetCurrentThread();
    SetThreadDescription(CurrentThread, L"Desktop");
    SHDesktopMessageLoop(DesktopAndTray);
    if ( (byte_14024FCC1 & 0x20) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        Explorer_MessageLoop_Stop,
        v49,
        1,
        v97);
    SHCloseDesktopHandle(DesktopAndTray, v48, v49, v50);
    if ( v63 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v63 + 40LL))(v63);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v63 + 80LL))(v63);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59324556>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59324556>::GetImpl'::`2'::impl) )
    {
      SafeRelease<IShellItem2>(v95);
      CThreadRefHost::WaitForRefs((CThreadRefHost *)&v65);
    }
    else
    {
      CThreadRefHost::WaitForRefs((CThreadRefHost *)&v65);
      SafeRelease<IShellItem2>(v95);
    }
    WriteCleanShutdown(1);
    std::unique_ptr<ProcessShutdownWatcher>::~unique_ptr<ProcessShutdownWatcher>(hMutex);
  }
  CImmersiveWatermark::Finalize((ULONG_PTR)dwData);
  if ( v29 >= 0 )
    OleUninitialize();
  if ( !v28 )
    CoUninitialize();
  ShellDDEInit(0);
  UnhookWinEvent(v38);
  if ( ppv && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)ppv + 8) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::operator->(
                            &ppv,
                            hMutex)
             + 275LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>(hMutex);
    tip2::tip_test<tip2::details::merged_data<_tip_GenericLogonTasksStartToUxShownTest,_tip_GenericLogonTasksStartToUxShownTest>>::complete(&ppv);
  }
  CImmersiveWatermark::~CImmersiveWatermark((CImmersiveWatermark *)dwData);
  v65 = &CThreadRefHost::`vftable';
  CThreadRefHost::WaitForRefs((CThreadRefHost *)&v65);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&pidl[1]);
  ExplorerTelemetry::ExplorerBoot::~ExplorerBoot((ExplorerTelemetry::ExplorerBoot *)v94);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>(&ppv);
LABEL_106:
  v51 = GetCommandLineW();
  v52 = PathGetArgsW(v51);
  FreeSharedMemInCmdLine(v52);
  if ( qword_140250598 )
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&qword_140250598);
  CTray::~CTray((CTray *)&c_trayStatic);
  EndLogging(v54, v53);
  McGenEventUnregister_EventUnregister(&Microsoft_Windows_Shell_Core_Provider_Context);
  McGenEventUnregister_EventUnregister(MICROSOFT_TWINAPI_PUBLISHER_Context);
  v55 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v55 )
    {
      v56 = v55[1];
      if ( v56 )
      {
        UnregisterTraceGuids(v56);
        v55[1] = 0;
      }
      v55 = (_QWORD *)*v55;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  if ( g_fExitExplorer )
  {
    if ( GetModuleHandleW(L"dui70") )
      SkipDLLUnloadInitChecks();
    ExitProcess(1u);
  }
  return 1;
}

```

## disassembly

```asm
0x1400a3f04  push    rbp
0x1400a3f06  push    rbx
0x1400a3f07  push    rsi
0x1400a3f08  push    rdi
0x1400a3f09  push    r12
0x1400a3f0b  push    r13
0x1400a3f0d  push    r14
0x1400a3f0f  push    r15
0x1400a3f11  lea     rbp, [rsp-328h]
0x1400a3f19  sub     rsp, 428h
0x1400a3f20  mov     rax, cs:__security_cookie
0x1400a3f27  xor     rax, rsp
0x1400a3f2a  mov     [rbp+360h+var_50], rax
0x1400a3f31  mov     rdi, rcx
0x1400a3f34  mov     esi, 1
0x1400a3f39  xor     r14d, r14d
0x1400a3f3c  mov     dword ptr [rsp+460h+var_410], esi
0x1400a3f40  lea     r8, [rsp+460h+var_410]; unsigned int
0x1400a3f45  call    ?GetCurrentProcessExecutionOptionNoThrow@details@wil@@YAJPEBGKPEAK@Z; wil::details::GetCurrentProcessExecutionOptionNoThrow(ushort const *,ulong,ulong *)
0x1400a3f4a  mov     rcx, [rbp+368h]; this
0x1400a3f51  test    eax, eax
0x1400a3f53  js      loc_1400A4EB1
0x1400a3f59  mov     r13d, 2
0x1400a3f5f  mov     ebx, dword ptr [rsp+460h+var_410]
0x1400a3f63  test    ebx, ebx
0x1400a3f65  jz      short loc_1400A3F94
0x1400a3f67  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x1400a3f6c  test    al, al
0x1400a3f6e  jnz     short loc_1400A3F83
0x1400a3f70  mov     ecx, 1F4h; dwMilliseconds
0x1400a3f75  call    cs:__imp_Sleep
0x1400a3f7c  nop     dword ptr [rax+rax+00h]
0x1400a3f81  jmp     short loc_1400A3F3C
0x1400a3f83  cmp     ebx, r13d
0x1400a3f86  jnz     short loc_1400A3F94
0x1400a3f88  call    cs:__imp_DebugBreak
0x1400a3f8f  nop     dword ptr [rax+rax+00h]
0x1400a3f94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FileExplorerLongPath2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerLongPath2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerLongPath2> `wil::Feature<__WilFeatureTraits_Feature_FileExplorerLongPath2>::GetImpl(void)'::`2'::impl
0x1400a3f9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerLongPath2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerLongPath2>::__private_IsEnabled(wil::ReportingKind)
0x1400a3fa0  test    al, al
0x1400a3fa2  jz      short loc_1400A3FBF
0x1400a3fa4  mov     rax, gs:60h
0x1400a3fad  mov     cl, [rax+3]
0x1400a3fb0  or      cl, 80h
0x1400a3fb3  mov     rax, gs:60h
0x1400a3fbc  mov     [rax+3], cl
0x1400a3fbf  call    cs:__imp_DXGIDeclareAdapterRemovalSupport
0x1400a3fc6  nop     dword ptr [rax+rax+00h]
0x1400a3fcb  mov     cs:qword_14024FF70, r14
0x1400a3fd2  lea     rax, qword_14024FF88
0x1400a3fd9  mov     cs:WPP_MAIN_CB, rax
0x1400a3fe0  mov     cs:qword_14024FF78, rsi
0x1400a3fe7  mov     cs:qword_14024FF98, r14
0x1400a3fee  lea     rax, qword_14024FFB0
0x1400a3ff5  mov     cs:qword_14024FF88, rax
0x1400a3ffc  mov     cs:qword_14024FFA0, rsi
0x1400a4003  mov     cs:qword_14024FFC0, r14
0x1400a400a  lea     rax, qword_14024FFD8
0x1400a4011  mov     cs:qword_14024FFB0, rax
0x1400a4018  mov     cs:qword_14024FFC8, rsi
0x1400a401f  mov     cs:qword_14024FFE8, r14
0x1400a4026  lea     rax, qword_140250000
0x1400a402d  mov     cs:qword_14024FFD8, rax
0x1400a4034  mov     cs:qword_14024FFF0, rsi
0x1400a403b  mov     cs:qword_140250010, r14
0x1400a4042  lea     rax, qword_140250028
0x1400a4049  mov     cs:qword_140250000, rax
0x1400a4050  mov     cs:qword_140250018, rsi
0x1400a4057  mov     cs:qword_140250038, r14
0x1400a405e  mov     cs:qword_140250028, r14
0x1400a4065  mov     cs:qword_140250040, rsi
0x1400a406c  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x1400a4073  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1400a407a  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x1400a4081  mov     cs:qword_14024FF38, rax
0x1400a4088  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x1400a408f  mov     cs:qword_14024FF40, rax
0x1400a4096  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider
0x1400a409d  mov     cs:qword_14024FF48, rax
0x1400a40a4  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider
0x1400a40ab  mov     cs:qword_14024FF50, rax
0x1400a40b2  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider
0x1400a40b9  mov     cs:qword_14024FF58, rax
0x1400a40c0  lea     rax, WPP_MAIN_CB
0x1400a40c7  mov     cs:WPP_GLOBAL_Control, rax
0x1400a40ce  call    WppInitUm
0x1400a40d3  lea     r12, Microsoft_Windows_Shell_Core_Provider_Context
0x1400a40da  mov     r9, r12
0x1400a40dd  mov     r8, r12
0x1400a40e0  lea     rcx, Microsoft_Windows_Shell_Core_Provider
0x1400a40e7  call    McGenEventRegister_EventRegister
0x1400a40ec  lea     r9, MICROSOFT_TWINAPI_PUBLISHER_Context
0x1400a40f3  lea     r8, MICROSOFT_TWINAPI_PUBLISHER_Context
0x1400a40fa  lea     rcx, MICROSOFT_TWINAPI_PUBLISHER
0x1400a4101  call    McGenEventRegister_EventRegister
0x1400a4106  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x1400a410e  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x1400a4115  mov     edx, r13d
0x1400a4118  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x1400a411f  call    cs:__imp_EventSetInformation
0x1400a4126  nop     dword ptr [rax+rax+00h]
0x1400a412b  mov     dword ptr [rsp+460h+var_410], r14d
0x1400a4130  lea     rax, [rsp+460h+var_410]
0x1400a4135  mov     qword ptr [rsp+460h+dwOptions], rax; int *
0x1400a413a  lea     r8, aExplorerstartu; "ExplorerStartupTraceRecorded"
0x1400a4141  lea     rbx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a4148  mov     rdx, rbx; unsigned __int16 *
0x1400a414b  mov     r15, 0FFFFFFFF80000001h
0x1400a4152  mov     rcx, r15; HKEY
0x1400a4155  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1400a415a  cmp     dword ptr [rsp+460h+var_410], r14d
0x1400a415f  jnz     short loc_1400A417B
0x1400a4161  call    ?StartLogging@@YAJPEBU_TRACE_INFO@@PEBG@Z; StartLogging(_TRACE_INFO const *,ushort const *)
0x1400a4166  mov     r9d, esi; int
0x1400a4169  lea     r8, aExplorerstartu; "ExplorerStartupTraceRecorded"
0x1400a4170  mov     rdx, rbx; unsigned __int16 *
0x1400a4173  mov     rcx, r15; HKEY
0x1400a4176  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1400a417b  mov     r15d, 20h ; ' '
0x1400a4181  test    cs:byte_14024FCC1, r15b
0x1400a4188  jz      short loc_1400A41A8
0x1400a418a  lea     rax, [rbp+360h+hMutex]
0x1400a4191  mov     qword ptr [rsp+460h+dwOptions], rax; int
0x1400a4196  mov     r9d, esi
0x1400a4199  lea     rdx, ShellTraceId_Explorer_InitializingExplorer_Start
0x1400a41a0  mov     rcx, r12
0x1400a41a3  call    McGenEventWrite_EventWriteTransfer
0x1400a41a8  lea     rcx, AppID; "Microsoft.Windows.Explorer"
0x1400a41af  call    cs:__imp_SetCurrentProcessExplicitAppUserModelID
0x1400a41b6  nop     dword ptr [rax+rax+00h]
0x1400a41bb  mov     ecx, 4001h; uMode
0x1400a41c0  call    cs:__imp_SetErrorMode
0x1400a41c7  nop     dword ptr [rax+rax+00h]
0x1400a41cc  mov     ecx, esi; Mode
0x1400a41ce  call    cs:__imp__set_error_mode
0x1400a41d5  nop     dword ptr [rax+rax+00h]
0x1400a41da  call    ?SeverBamChildConnectionsForProcess@@YAJXZ; SeverBamChildConnectionsForProcess(void)
0x1400a41df  mov     rcx, [rbp+368h]; this
0x1400a41e6  test    eax, eax
0x1400a41e8  jns     short loc_1400A41FE
0x1400a41ea  mov     r9d, eax; char *
0x1400a41ed  lea     r8, aPcshellShellEx_3; "pcshell\\shell\\explorer\\initcab.cpp"
0x1400a41f4  mov     edx, 505h; void *
0x1400a41f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a41fe  call    cs:__imp_GetCurrentProcess
0x1400a4205  nop     dword ptr [rax+rax+00h]
0x1400a420a  mov     rcx, rax; hProcess
0x1400a420d  mov     edx, 80h; dwPriorityClass
0x1400a4212  call    cs:__imp_SetPriorityClass
0x1400a4219  nop     dword ptr [rax+rax+00h]
0x1400a421e  xor     ecx, ecx
0x1400a4220  call    cs:__imp_EnableMouseInPointer
0x1400a4227  nop     dword ptr [rax+rax+00h]
0x1400a422c  mov     cs:g_hinstCabinet, rdi
0x1400a4233  xor     edx, edx
0x1400a4235  xor     ecx, ecx
0x1400a4237  call    Cabinet_InitGlobalMetrics
0x1400a423c  mov     [rsp+460h+lpdwDisposition], r14; lpdwDisposition
0x1400a4241  lea     rax, g_hkeyExplorer
0x1400a4248  mov     [rsp+460h+phkResult], rax; phkResult
0x1400a424d  mov     [rsp+460h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1400a4252  mov     [rsp+460h+samDesired], 2000000h; samDesired
0x1400a425a  mov     [rsp+460h+dwOptions], r14d; int
0x1400a425f  xor     r9d, r9d; lpClass
0x1400a4262  xor     r8d, r8d; Reserved
0x1400a4265  mov     rdx, rbx; lpSubKey
0x1400a4268  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400a426f  call    cs:__imp_RegCreateKeyExW
0x1400a4276  nop     dword ptr [rax+rax+00h]
0x1400a427b  mov     [rbp+360h+hMutex], r14
0x1400a4282  call    cs:__imp_GetCommandLineW
0x1400a4289  nop     dword ptr [rax+rax+00h]
0x1400a428e  mov     rcx, rax; pszPath
0x1400a4291  call    cs:__imp_PathGetArgsW
0x1400a4298  nop     dword ptr [rax+rax+00h]
0x1400a429d  lea     r8, [rbp+360h+hMutex]
0x1400a42a4  mov     rdx, rax
0x1400a42a7  lea     rcx, [rsp+460h+ppv]
0x1400a42ac  call    ?Create@ExplorerServerConfiguration@@SA?AV1@PEBGPEAPEAX@Z; ExplorerServerConfiguration::Create(ushort const *,void * *)
0x1400a42b1  mov     ebx, dword ptr [rsp+460h+ppv+4]
0x1400a42b5  cmp     cs:?m_firstProcessEntry@@3_NA, r14b; bool m_firstProcessEntry
0x1400a42bc  jz      short loc_1400A42D8
0x1400a42be  lea     rcx, aExplorer_0; "explorer"
0x1400a42c5  call    cs:__imp_RmEnableLimits
0x1400a42cc  nop     dword ptr [rax+rax+00h]
0x1400a42d1  mov     cs:?m_firstProcessEntry@@3_NA, r14b; bool m_firstProcessEntry
0x1400a42d8  cmp     ebx, 5
0x1400a42db  jz      short loc_1400A42F0
0x1400a42dd  lea     rcx, aHorizontalscro; "-HorizontalScrollMode 2 -VerticalScroll"...
0x1400a42e4  call    cs:__imp_ConfigureDownlevelInput
0x1400a42eb  nop     dword ptr [rax+rax+00h]
0x1400a42f0  mov     ecx, ebx
0x1400a42f2  call    cs:__imp_SetExplorerServerMode
0x1400a42f9  nop     dword ptr [rax+rax+00h]
0x1400a42fe  mov     rcx, [rbp+368h]; this
0x1400a4305  test    eax, eax
0x1400a4307  jns     short loc_1400A431D
0x1400a4309  mov     r9d, eax; char *
0x1400a430c  lea     r8, aPcshellShellEx_3; "pcshell\\shell\\explorer\\initcab.cpp"
0x1400a4313  mov     edx, 532h; void *
0x1400a4318  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a431d  cmp     ebx, 3
0x1400a4320  jz      loc_1400A4572
0x1400a4326  mov     rdi, [rbp+360h+hMutex]
0x1400a432d  test    rdi, rdi
0x1400a4330  jz      short loc_1400A4350
0x1400a4332  mov     rcx, rdi; hMutex
0x1400a4335  call    cs:__imp_ReleaseMutex
0x1400a433c  nop     dword ptr [rax+rax+00h]
0x1400a4341  mov     rcx, rdi; hObject
0x1400a4344  call    cs:__imp_CloseHandle
0x1400a434b  nop     dword ptr [rax+rax+00h]
0x1400a4350  call    cs:__imp_GetCurrentProcess
0x1400a4357  nop     dword ptr [rax+rax+00h]
0x1400a435c  mov     rcx, rax; hProcess
0x1400a435f  mov     edx, r15d; dwPriorityClass
0x1400a4362  call    cs:__imp_SetPriorityClass
0x1400a4369  nop     dword ptr [rax+rax+00h]
0x1400a436e  cmp     ebx, 5
0x1400a4371  jnz     short loc_1400A43BE
0x1400a4373  mov     [rbp+360h+pExecInfo.cbSize], 70h ; 'p'
0x1400a437a  xor     edx, edx; Val
0x1400a437c  lea     r8d, [rbx+67h]; Size
0x1400a4380  lea     rcx, [rbp+360h+pExecInfo.fMask]; void *
0x1400a4384  call    memset_0
0x1400a4389  mov     [rbp+360h+pExecInfo.nShow], esi
0x1400a438c  mov     [rbp+360h+pExecInfo.fMask], 200010Ch
0x1400a4393  lea     rax, aOpennewwindow; "OpenNewWindow"
0x1400a439a  mov     [rbp+360h+pExecInfo.lpVerb], rax
0x1400a439e  lea     rax, pszName; "shell:::{52205fd8-5dfb-447d-801a-d0b52f"...
0x1400a43a5  mov     [rbp+360h+pExecInfo.lpFile], rax
0x1400a43a9  lea     rcx, [rbp+360h+pExecInfo]; pExecInfo
0x1400a43ad  call    cs:__imp_ShellExecuteExW
0x1400a43b4  nop     dword ptr [rax+rax+00h]
0x1400a43b9  jmp     loc_1400A4DB5
0x1400a43be  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1400a43c3  mov     edi, eax
0x1400a43c5  test    eax, eax
0x1400a43c7  js      loc_1400A4DB5
0x1400a43cd  xorps   xmm0, xmm0
0x1400a43d0  xor     eax, eax
0x1400a43d2  movups  xmmword ptr [rbp+360h+pidl], xmm0
0x1400a43d6  movups  [rbp+360h+var_330], xmm0
0x1400a43da  mov     [rbp+360h+var_320], rax
0x1400a43de  call    cs:__imp_GetCommandLineW
0x1400a43e5  nop     dword ptr [rax+rax+00h]
0x1400a43ea  mov     rcx, rax; pszPath
0x1400a43ed  call    cs:__imp_PathGetArgsW
0x1400a43f4  nop     dword ptr [rax+rax+00h]
0x1400a43f9  lea     rdx, [rbp+360h+pidl]; ppidl
0x1400a43fd  mov     rcx, rax; unsigned __int16 *
0x1400a4400  call    SHExplorerParseCmdLine
0x1400a4405  test    eax, eax
0x1400a4407  jz      loc_1400A4559
0x1400a440d  call    ?SetExplorerComGlobalOptions@@YAXXZ; SetExplorerComGlobalOptions(void)
0x1400a4412  lea     eax, [rbx-4]
0x1400a4415  test    eax, 0FFFFFFFDh
0x1400a441a  jz      loc_1400A44D9
0x1400a4420  mov     [rsp+460h+ppv], r14
0x1400a4425  lea     rcx, [rsp+460h+ppv]
0x1400a442a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400a442f  lea     rax, [rsp+460h+ppv]
0x1400a4434  mov     qword ptr [rsp+460h+dwOptions], rax; ppv
0x1400a4439  lea     r9, _GUID_9b25c299_03b6_4a14_827d_095485d0c022; riid
0x1400a4440  mov     r8d, esi; dwClsContext
0x1400a4443  xor     edx, edx; pUnkOuter
0x1400a4445  lea     rcx, CLSID_ExplorerLauncher; rclsid
0x1400a444c  call    cs:__imp_CoCreateInstance
0x1400a4453  nop     dword ptr [rax+rax+00h]
0x1400a4458  test    eax, eax
0x1400a445a  js      short loc_1400A44CD
0x1400a445c  mov     qword ptr [rbp+360h+pExecInfo.cbSize], 68h ; 'h'
0x1400a4464  xor     edx, edx; Val
0x1400a4466  lea     r8d, [rdx+60h]; Size
0x1400a446a  lea     rcx, [rbp+360h+pExecInfo.hwnd]; void *
0x1400a446e  call    memset_0
0x1400a4473  lea     rcx, [rbp+360h+pExecInfo]; lpStartupInfo
0x1400a4477  call    cs:__imp_GetStartupInfoW
0x1400a447e  nop     dword ptr [rax+rax+00h]
0x1400a4483  mov     rcx, [rsp+460h+ppv]
0x1400a4488  mov     rax, [rcx]
0x1400a448b  mov     r10, [rax+18h]
0x1400a448f  test    byte ptr [rbp+360h+pExecInfo.hInstApp+4], sil
0x1400a4493  movzx   eax, word ptr [rbp+360h+pExecInfo.lpIDList]
0x1400a4497  jnz     short loc_1400A449E
0x1400a4499  mov     eax, 0Ah
0x1400a449e  mov     [rsp+460h+lpdwDisposition], r14
0x1400a44a3  mov     [rsp+460h+phkResult], r14
0x1400a44a8  mov     [rsp+460h+lpSecurityAttributes], r14
0x1400a44ad  mov     [rsp+460h+samDesired], eax
0x1400a44b1  mov     qword ptr [rsp+460h+dwOptions], r14
0x1400a44b6  mov     r9d, dword ptr [rbp+360h+var_330+4]
0x1400a44ba  mov     r8, [rbp+360h+pidl]
0x1400a44be  lea     rdx, CLSID_SeparateMultipleProcessExplorerHost
0x1400a44c5  mov     rax, r10
0x1400a44c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a44cd  lea     rcx, [rsp+460h+ppv]
0x1400a44d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1400a44d7  jmp     short loc_1400A4549
0x1400a44d9  mov     [rsp+460h+var_410], r14
  ... truncated ...
```
