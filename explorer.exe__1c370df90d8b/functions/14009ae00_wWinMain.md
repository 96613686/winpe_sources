# wWinMain

- ea: `0x14009ae00`
- end: `0x14009bd18`
- name: `wWinMain`
- size: `3864`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `72`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140103f30`

## callees

- `0x140007048`
- `0x1400077d4`
- `0x14000c61c`
- `0x14000d890`
- `0x14000deb4`
- `0x14000e0dc`
- `0x14000e118`
- `0x14000e4a8`
- `0x14000e744`
- `0x14000edcc`
- `0x14000fea4`
- `0x1400103bc`
- `0x140010bb8`
- `0x140016b74`
- `0x140016c40`
- `0x140019308`
- `0x14001c7c0`
- `0x14001ca18`
- `0x14001cac4`
- `0x14001cb84`
- `0x14001eba8`
- `0x140023f78`
- `0x140030944`
- `0x140036b10`
- `0x14004b0e0`
- `0x1400632b0`
- `0x140074154`
- `0x140075bcc`
- `0x140076410`
- `0x140078d64`
- `0x14007a3f8`
- `0x14007b748`
- `0x14007ca08`
- `0x14007f724`
- `0x14007fa9c`
- `0x14007ffc0`
- `0x140080bd0`
- `0x140087328`
- `0x140087de0`
- `0x1400882a4`
- `0x14008a77c`
- `0x14008b158`
- `0x14008b3a8`
- `0x14008b434`
- `0x14008ba1c`
- `0x14008ddc0`
- `0x14008ddfc`
- `0x14009ada8`
- `0x14009ae00`
- `0x14009bd20`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x14009b0a4`
- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x14009b0a4`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x14009b5ac`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x14009b9df`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x14009b5ac`
- `api-ms-win-core-windowserrorreporting-l1-1-3!RegisterApplicationRestart` at `0x14009b9df`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x14009b555`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x14009b555`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14009bcc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14009bcc2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14009ae70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14009ae70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14009b1ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14009b999`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14009b1ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14009b999`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14009b09b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14009b09b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14009b008`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14009b008`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14009b0dc`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14009b1e9`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14009b0dc`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14009b1e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009b0ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009b1dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009b0ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14009b1dd`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x14009b4b2`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x14009b4b2`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14009b590`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14009bcd6`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14009b590`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14009bcd6`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x14009b2e1`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x14009b2e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14009ba8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14009ba8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14009b7a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14009b7a0`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14009ae7d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14009ae7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009b1d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009b9a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009b1d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009b9a2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14009b12c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14009b12c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14009b744`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14009b744`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14009b3b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14009bb72`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14009b3b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14009bb72`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009b2bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009b369`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009b64f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009ba31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009b2bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009b369`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009b64f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14009ba31`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14009b139`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14009b25a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14009bc2b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14009b139`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14009b25a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x14009bc2b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x14009b142`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x14009b263`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x14009bc34`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x14009b142`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x14009b263`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x14009bc34`
- `api-ms-win-shcore-sysinfo-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x14009b090`
- `api-ms-win-shcore-sysinfo-l1-1-0!SetCurrentProcessExplicitAppUserModelID` at `0x14009b090`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14009b7be`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14009b7be`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x14009b813`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x14009b813`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x14009b82a`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x14009b82a`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadRef` at `0x14009b808`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThreadRef` at `0x14009b808`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x14009bc9a`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x14009bc9a`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x14009ba9c`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x14009ba9c`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14009b3ab`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14009b3ab`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x14009aeae`
- `dxgi!DXGIDeclareAdapterRemovalSupport` at `0x14009aeae`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!EnableMouseInPointer` at `0x14009b0e4`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!EnableMouseInPointer` at `0x14009b0e4`
- `api-ms-win-storage-exports-internal-l1-1-0!SetThreadFlags` at `0x14009b512`
- `api-ms-win-storage-exports-internal-l1-1-0!SetThreadFlags` at `0x14009b512`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x14009b614`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!SetWinEventHook` at `0x14009b614`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!UnhookWinEvent` at `0x14009bb83`
- `api-ms-win-rtcore-ntuser-winevent-l1-1-0!UnhookWinEvent` at `0x14009bb83`
- `SHELL32!ShellExecuteExW` at `0x14009b22f`
- `SHELL32!ShellExecuteExW` at `0x14009b22f`
- `SHELL32!__imp_ShellDDEInit` at `0x14009b4a7`
- `SHELL32!__imp_ShellDDEInit` at `0x14009bb7a`
- `SHELL32!__imp_ShellDDEInit` at `0x14009b4a7`
- `SHELL32!__imp_ShellDDEInit` at `0x14009bb7a`
- `SHELL32!__imp_SHDesktopMessageLoop` at `0x14009baa5`
- `SHELL32!__imp_SHDesktopMessageLoop` at `0x14009baa5`
- `SHELL32!__imp_SHCloseDesktopHandle` at `0x14009bad9`
- `SHELL32!__imp_SHCloseDesktopHandle` at `0x14009bad9`
- `SHELL32!__imp_SetExplorerServerMode` at `0x14009b191`
- `SHELL32!__imp_SetExplorerServerMode` at `0x14009b191`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x14009b9c3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x14009b9c3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x14009b4df`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x14009b4df`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14009b6e4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14009b6fc`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14009b714`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14009b6e4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14009b6fc`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x14009b714`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x14009b170`
- `ext-ms-win-resourcemanager-limits-l1-1-0!RmEnableLimits` at `0x14009b170`
- `ole32!OleUninitialize` at `0x14009bb67`
- `ole32!OleUninitialize` at `0x14009bb67`
- `ole32!OleInitialize` at `0x14009b4f4`
- `ole32!OleInitialize` at `0x14009b4f4`
- `WinLangdb!EnsureLanguageProfileExists` at `0x14009b74e`
- `WinLangdb!EnsureLanguageProfileExists` at `0x14009b74e`
- `DUI70!SkipDLLUnloadInitChecks` at `0x14009bccd`
- `DUI70!SkipDLLUnloadInitChecks` at `0x14009bccd`
- `NInput!__imp_ConfigureDownlevelInput` at `0x14009b189`
- `NInput!__imp_ConfigureDownlevelInput` at `0x14009b189`

## string_xrefs

- `0x14009bd06`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x14009b6ba`: `shell\lib\logontasks\logontasks.cpp`
- `0x14009b215`: `OpenNewWindow`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  char v5; // si
  int CurrentProcessExecutionOptionNoThrow; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx
  unsigned int v10; // r9d
  const unsigned __int16 *v11; // rdx
  const struct _TRACE_INFO *v12; // rcx
  __int64 v13; // r8
  int v14; // eax
  HANDLE CurrentProcess; // rax
  const WCHAR *CommandLineW; // rax
  LPWSTR ArgsW; // rax
  unsigned int v18; // ebx
  int v19; // eax
  HANDLE v20; // rdi
  HANDLE v21; // rax
  int v22; // edi
  const WCHAR *v23; // rax
  unsigned __int16 *v24; // rax
  int lpIDList_low; // eax
  unsigned int v26; // ebx
  _QWORD *v27; // rax
  __int64 v28; // r8
  int v29; // r13d
  bool v30; // cl
  CLogonTaskFramework *v31; // rbx
  bool v32; // r14
  int v33; // eax
  bool v34; // zf
  unsigned int v35; // eax
  bool v36; // r15
  HWINEVENTHOOK v37; // r12
  int v38; // eax
  wil::details::in1diag3 *v39; // rcx
  __int64 v40; // rdx
  CLogonTaskFramework *v41; // rax
  CLogonTaskFramework *v42; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v44; // r8
  HINSTANCE DesktopAndTray; // rdi
  __int64 v46; // r8
  HANDLE v47; // rbx
  HRESULT v48; // eax
  __int64 v49; // r8
  HANDLE CurrentThread; // rax
  CHAR *v51; // rdx
  WORD *v52; // r8
  WORD *v53; // r9
  const WCHAR *v54; // rax
  unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // rdx
  const struct _TRACE_INFO *v57; // rcx
  _QWORD *v58; // rbx
  TRACEHANDLE v59; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  HANDLE *dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  int dwOptionsc; // [rsp+20h] [rbp-E0h]
  void *dwOptionsd; // [rsp+20h] [rbp-E0h]
  unsigned int v66; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v68; // [rsp+60h] [rbp-A0h] BYREF
  void **v69; // [rsp+68h] [rbp-98h] BYREF
  LONG pcRef; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *ppunk; // [rsp+78h] [rbp-88h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+80h] [rbp-80h] BYREF
  struct tagMSG Msg; // [rsp+F0h] [rbp-10h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v75; // [rsp+130h] [rbp+30h] BYREF
  __int64 v76; // [rsp+140h] [rbp+40h]
  ULONG_PTR dwData[3]; // [rsp+150h] [rbp+50h] BYREF
  int v78; // [rsp+168h] [rbp+68h]
  __int64 v79; // [rsp+16Ch] [rbp+6Ch]
  __int64 v80; // [rsp+178h] [rbp+78h]
  __int64 v81; // [rsp+180h] [rbp+80h]
  char v82; // [rsp+188h] [rbp+88h]
  __int128 v83; // [rsp+190h] [rbp+90h]
  __int128 v84; // [rsp+1A0h] [rbp+A0h]
  __int128 v85; // [rsp+1B0h] [rbp+B0h]
  char v86; // [rsp+1C0h] [rbp+C0h]
  int v87; // [rsp+1C4h] [rbp+C4h]
  int v88; // [rsp+1C8h] [rbp+C8h]
  _BYTE v89[112]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v90; // [rsp+240h] [rbp+140h]
  int v91; // [rsp+250h] [rbp+150h]
  char v92; // [rsp+254h] [rbp+154h]
  __int64 v93; // [rsp+258h] [rbp+158h]
  __int128 v94; // [rsp+260h] [rbp+160h]
  __int128 v95; // [rsp+270h] [rbp+170h]
  __int64 v96; // [rsp+280h] [rbp+180h]
  __int64 v97; // [rsp+288h] [rbp+188h]
  _QWORD v98[42]; // [rsp+290h] [rbp+190h] BYREF
  CLogonTaskFramework *v99[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  HANDLE hMutex[2]; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v101; // [rsp+400h] [rbp+300h] BYREF
  WCHAR pszPath[264]; // [rsp+410h] [rbp+310h] BYREF
  wil::details *retaddr; // [rsp+678h] [rbp+578h]

  v5 = 0;
  while ( 1 )
  {
    v66 = 1;
    CurrentProcessExecutionOptionNoThrow = wil::details::GetCurrentProcessExecutionOptionNoThrow(
                                             (wil::details *)hInstance,
                                             (const unsigned __int16 *)hPrevInstance,
                                             (unsigned int)&v66,
                                             *(unsigned int **)&nShowCmd);
    if ( CurrentProcessExecutionOptionNoThrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)CurrentProcessExecutionOptionNoThrow,
        dwOptions);
    v7 = v66;
    if ( !v66 )
      break;
    if ( wil::details::IsDebuggerPresent(retaddr) )
    {
      if ( v7 == 2 )
        DebugBreak();
      break;
    }
    Sleep(0x1F4u);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerLongPath2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FileExplorerLongPath2>::GetImpl'::`2'::impl) )
    NtCurrentPeb()->BitField = NtCurrentPeb()->BitField | 0x80;
  DXGIDeclareAdapterRemovalSupport();
  qword_140253E00 = 0;
  WPP_MAIN_CB = (__int64)&qword_140253E18;
  qword_140253E08 = 1;
  qword_140253E28 = 0;
  qword_140253E18 = (__int64)&qword_140253E40;
  qword_140253E30 = 1;
  qword_140253E50 = 0;
  qword_140253E40 = (__int64)&qword_140253E68;
  qword_140253E58 = 1;
  qword_140253E78 = 0;
  qword_140253E68 = (__int64)&qword_140253E90;
  qword_140253E80 = 1;
  qword_140253EA0 = 0;
  qword_140253E90 = (__int64)&qword_140253EB8;
  qword_140253EA8 = 1;
  qword_140253EC8 = 0;
  qword_140253EB8 = 0;
  qword_140253ED0 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShellTraceProvider;
  qword_140253DC8 = (__int64)WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
  qword_140253DD0 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
  qword_140253DD8 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider;
  qword_140253DE0 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider;
  qword_140253DE8 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WppInitUm();
  McGenEventRegister_EventRegister(
    Microsoft_Windows_Shell_Core_Provider,
    v8,
    &Microsoft_Windows_Shell_Core_Provider_Context,
    &Microsoft_Windows_Shell_Core_Provider_Context);
  McGenEventRegister_EventRegister(
    MICROSOFT_TWINAPI_PUBLISHER,
    v9,
    MICROSOFT_TWINAPI_PUBLISHER_Context,
    MICROSOFT_TWINAPI_PUBLISHER_Context);
  EventSetInformation(
    Microsoft_Windows_Shell_Core_Provider_Context,
    2,
    &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
    (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  v66 = 0;
  SHRegGetBOOLWithREGSAM(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
    L"ExplorerStartupTraceRecorded",
    v10,
    (int *)&v66);
  if ( !v66 )
  {
    StartLogging(v12, v11);
    SHRegSetBOOL(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
      L"ExplorerStartupTraceRecorded",
      1);
  }
  if ( (byte_140253B81 & 0x20) != 0 )
  {
    dwOptionsa = hMutex;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Explorer_InitializingExplorer_Start,
      v13,
      1);
  }
  SetCurrentProcessExplicitAppUserModelID(L"Microsoft.Windows.Explorer");
  SetErrorMode(0x4001u);
  _set_error_mode(1);
  v14 = SeverBamChildConnectionsForProcess();
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x505,
      (unsigned int)"pcshell\\shell\\explorer\\initcab.cpp",
      (const char *)(unsigned int)v14,
      (int)dwOptionsa);
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
  v18 = HIDWORD(ppv);
  if ( m_firstProcessEntry )
  {
    RmEnableLimits(L"explorer");
    m_firstProcessEntry = 0;
  }
  if ( v18 != 5 )
    ConfigureDownlevelInput("-HorizontalScrollMode 2 -VerticalScrollMode 2");
  v19 = SetExplorerServerMode(v18);
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x532,
      (unsigned int)"pcshell\\shell\\explorer\\initcab.cpp",
      (const char *)(unsigned int)v19,
      dwOptionsb);
  if ( v18 != 3 )
  {
    v20 = hMutex[0];
    if ( hMutex[0] )
    {
      ReleaseMutex(hMutex[0]);
      CloseHandle(v20);
    }
    v21 = GetCurrentProcess();
    SetPriorityClass(v21, 0x20u);
    if ( v18 == 5 )
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
      v22 = SHCoInitialize();
      if ( v22 >= 0 )
      {
        *(_OWORD *)pidl = 0;
        v75 = 0;
        v76 = 0;
        v23 = GetCommandLineW();
        v24 = PathGetArgsW(v23);
        if ( (unsigned int)SHExplorerParseCmdLine(v24, pidl) )
        {
          SetExplorerComGlobalOptions();
          if ( ((v18 - 4) & 0xFFFFFFFD) != 0 )
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
                DWORD1(v75),
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
            v68 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
            if ( CoCreateInstance(&CLSID_ExplorerHostCreator, 0, 1u, &GUID_c4de032a_d902_450a_bc43_d9df6d0fd48c, &v68) >= 0
              && (*(int (__fastcall **)(LPVOID, char *))(*(_QWORD *)v68 + 24LL))(v68, (char *)&v75 + 8) >= 0 )
            {
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v68 + 32LL))(v68);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          }
          ILFree(pidl[0]);
        }
        if ( !v22 )
          CoUninitialize();
      }
    }
    goto LABEL_112;
  }
  v66 = 0;
  if ( BYTE3(ppv) && BYTE1(ppv) )
  {
    v26 = 1;
  }
  else
  {
    v33 = SHIsCurrentAppElevated(&v66);
    v26 = v66;
    if ( v33 >= 0 && v66 )
    {
      v66 = 0;
      v34 = (unsigned int)CheckElevationEnabled(&v66) == 0;
      v35 = 1;
      if ( v34 )
        v35 = v66;
      if ( v35
        && !(unsigned int)SHIsCurrentAccountBuiltInAdmin()
        && (int)RunExplorerUnelevated((const struct ExplorerServerConfiguration *)&ppv) >= 0 )
      {
        ExitProcess(2u);
      }
    }
  }
  ppv = 0;
  v27 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::ensure_data(&ppv);
  tip2::details::shared_data<1,0,0>::start(*v27 + 8LL, v99);
  if ( (byte_140253B83 & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_PerfTrack_Explorer_ExplorerStartToDesktopReady_Start,
      v28,
      1);
  if ( (byte_140253B81 & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      PerfTrack_Launcher_Login_Start,
      v28,
      1);
  wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v98,
    "ExplorerBoot");
  v98[0] = &ExplorerTelemetry::ExplorerBoot::`vftable';
  ExplorerTelemetry::ExplorerBoot::StartActivity((ExplorerTelemetry::ExplorerBoot *)v98);
  DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener::CDwmWnfDumpRequestListener((DwmWnfDiagnosticEvent::CDwmWnfDumpRequestListener *)pidl);
  pidl[0] = (LPITEMIDLIST)&DwmWnfDiagnosticEvent::CDwmWnfSimpleDumpRequestListener::`vftable';
  LODWORD(v75) = 4;
  *((_QWORD *)&v75 + 1) = L"Hotkey_Explorer";
  ShellDDEInit(1);
  SetProcessShutdownParameters(3u, 0);
  _AutoRunTaskMan();
  memset(&Msg, 0, sizeof(Msg));
  PeekMessageW(&Msg, 0, 0x12u, 0x12u, 0);
  WaitForSCMToInitialize();
  v29 = SHCoInitialize();
  v66 = OleInitialize(0);
  SetExplorerComGlobalOptions();
  if ( v26 )
    InitializeSecurityToAllowAppContainerComUse(v30);
  SetThreadFlags(1, 1);
  v31 = 0;
  v32 = 0;
  if ( IsDesktopWindowAlreadyPresent() )
  {
    v5 = 1;
  }
  else if ( IsUserOOBE() )
  {
    v32 = RegisterApplicationRestart(L"/LOADSAVEDWINDOWS", 0x80000008) >= 0;
  }
  v99[0] = 0;
  CImmersiveColorImpl::GetColorPreferenceImpl((struct IMMERSIVE_COLOR_PREFERENCE *)v99, 0, 1);
  v36 = CheckOobeColorSelection();
  CheckDefaultUIFonts();
  ChangeUIfontsToNewDPI();
  CheckForServerAdminUI();
  CheckHighContrast();
  EnableDpiScaledPadding(1);
  v37 = SetWinEventHook(0x20u, 0x20u, 0, CheckHighContrastAfterDesktopSwitch, 0, 0, 0);
  v68 = 0;
  if ( !v5 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
    if ( CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8, &v68) >= 0 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v68 + 32LL))(v68);
  }
  v99[0] = 0;
  Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(v99);
  v38 = Microsoft::WRL::Details::MakeAndInitialize<CLogonTaskFramework,CLogonTaskFramework,>(v99);
  v39 = retaddr;
  if ( v38 < 0 )
  {
    v40 = 13155;
LABEL_70:
    wil::details::in1diag3::_Log_Hr(
      v39,
      (void *)v40,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v38,
      dwOptionsc);
    goto LABEL_71;
  }
  v38 = CLogonTaskFramework::RunAllLogonTasks(v99[0]);
  v39 = retaddr;
  if ( v38 < 0 )
  {
    v40 = 13157;
    goto LABEL_70;
  }
LABEL_71:
  Microsoft::WRL::ComPtr<CLogonTaskFramework>::InternalRelease(v99);
  SHGetSpecialFolderPathW(0, pszPath, 16, 1);
  SHGetSpecialFolderPathW(0, pszPath, 2, 1);
  SHGetSpecialFolderPathW(0, pszPath, 11, 1);
  if ( RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\International\\User Profile", L"Languages", 0x20u, 0, 0, 0) )
    EnsureLanguageProfileExists();
  v41 = (CLogonTaskFramework *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v42 = v41;
  v99[0] = v41;
  if ( v41 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v41);
    *(_QWORD *)v42 = &off_1401E07F0;
    v31 = v42;
    v99[0] = 0;
  }
  Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_deee8152b7769f5e304c76a887ad1fef_____(v99);
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(dwOptionsd) = (_DWORD)v31;
  SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v31 )
    (*(void (__fastcall **)(CLogonTaskFramework *))(*(_QWORD *)v31 + 16LL))(v31);
  WriteCleanShutdown(0);
  v69 = &CThreadRefHost::`vftable';
  pcRef = 0;
  ppunk = 0;
  SHCreateThreadRef(&pcRef, &ppunk);
  SHSetThreadRef(ppunk);
  v69 = &CThreadRefHost::`vftable';
  SetProcessReference(ppunk);
  DesktopAndTray = 0;
  if ( !v5 )
  {
    ExplorerTelemetry::ExplorerBoot::ExplorerBoot_TrayAndDesktopInit((ExplorerTelemetry::ExplorerBoot *)v98);
    DesktopAndTray = (HINSTANCE)CreateDesktopAndTray();
  }
  if ( byte_140253B82 < 0 )
  {
    dwOptionsd = v99;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Activation_Watermark_Init_Start,
      v44,
      1);
  }
  LOWORD(dwData[0]) = 0;
  dwData[1] = 0;
  dwData[2] = 0;
  v78 = 6;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  memset_0(v89, 0, sizeof(v89));
  v90 = 0;
  v79 = 0;
  v88 = 0;
  ExplorerTelemetry::ExplorerBoot::ExplorerBoot_ImmersiveWatermarkCreate((ExplorerTelemetry::ExplorerBoot *)v98);
  sub_140016C40(dwData);
  if ( byte_140253B82 < 0 )
  {
    dwOptionsd = &v101;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Activation_Watermark_Init_Stop,
      v46,
      1);
  }
  if ( !v36 )
  {
    v99[0] = 0;
    CImmersiveColorImpl::GetColorPreferenceImpl((struct IMMERSIVE_COLOR_PREFERENCE *)v99, 1, 1);
  }
  v47 = hMutex[0];
  if ( hMutex[0] )
  {
    ReleaseMutex(hMutex[0]);
    CloseHandle(v47);
  }
  if ( DesktopAndTray )
  {
    PostMessageW(v_hwndTray, 0x590u, 1u, 0);
    EnsureTabletButtonThreadRunningIfNeeded();
    if ( !v32 )
    {
      v48 = RegisterApplicationRestart(L"/LOADSAVEDWINDOWS", 0x80000008);
      if ( v48 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x631,
          (unsigned int)"pcshell\\shell\\explorer\\initcab.cpp",
          (const char *)(unsigned int)v48,
          (int)dwOptionsd);
    }
    hMutex[0] = 0;
    v99[0] = 0;
    if ( CoCreateInstance(&CLSID_ExplorerHostCreator, 0, 1u, &GUID_c4de032a_d902_450a_bc43_d9df6d0fd48c, (LPVOID *)v99) >= 0 )
      (*(void (__fastcall **)(CLogonTaskFramework *, GUID *))(*(_QWORD *)v99[0] + 24LL))(
        v99[0],
        &CLSID_DesktopExplorerHost);
    if ( (byte_140253B81 & 0x20) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        Explorer_MessageLoop_Start,
        v49,
        1);
    wil::ActivityBase<ExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v98);
    CurrentThread = GetCurrentThread();
    SetThreadDescription(CurrentThread, L"Desktop");
    SHDesktopMessageLoop(DesktopAndTray);
    if ( (byte_140253B81 & 0x20) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        Explorer_MessageLoop_Stop,
        v52,
        1);
    SHCloseDesktopHandle(DesktopAndTray, v51, v52, v53);
    if ( v68 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v68 + 40LL))(v68);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v68 + 80LL))(v68);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59324556>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59324556>::GetImpl'::`2'::impl) )
    {
      SafeRelease<IShellItem2>(v99);
      CThreadRefHost::WaitForRefs((CThreadRefHost *)&v69);
    }
    else
    {
      CThreadRefHost::WaitForRefs((CThreadRefHost *)&v69);
      SafeRelease<IShellItem2>(v99);
    }
    WriteCleanShutdown(1);
    std::unique_ptr<ProcessShutdownWatcher>::~unique_ptr<ProcessShutdownWatcher>(hMutex);
  }
  sub_1400A79FC((ULONG_PTR)dwData);
  if ( (v66 & 0x80000000) == 0 )
    OleUninitialize();
  if ( !v29 )
    CoUninitialize();
  ShellDDEInit(0);
  UnhookWinEvent(v37);
  if ( ppv )
  {
    if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running((char *)ppv + 8) )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::operator->(
                              &ppv,
                              hMutex)
               + 275LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>::~test_data_control<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>>(hMutex);
      if ( ppv )
        tip2::details::shared_data<1,0,0>::complete_without_lock((char *)ppv + 8);
    }
  }
  sub_14009BD68(dwData);
  v69 = &CThreadRefHost::`vftable';
  CThreadRefHost::WaitForRefs((CThreadRefHost *)&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&pidl[1]);
  ExplorerTelemetry::ExplorerBoot::~ExplorerBoot((ExplorerTelemetry::ExplorerBoot *)v98);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ShellStartupHealthTest,_tip_ShellStartupHealthTest>,wil::err_returncode_policy>(&ppv);
LABEL_112:
  v54 = GetCommandLineW();
  v55 = PathGetArgsW(v54);
  FreeSharedMemInCmdLine(v55);
  if ( qword_140254428 )
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&qword_140254428);
  CTray::~CTray((CTray *)&c_trayStatic);
  EndLogging(v57, v56);
  McGenEventUnregister_EventUnregister(&Microsoft_Windows_Shell_Core_Provider_Context);
  McGenEventUnregister_EventUnregister(MICROSOFT_TWINAPI_PUBLISHER_Context);
  v58 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v58 )
    {
      v59 = v58[1];
      if ( v59 )
      {
        UnregisterTraceGuids(v59);
        v58[1] = 0;
      }
      v58 = (_QWORD *)*v58;
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
0x14009ae00  push    rbp
0x14009ae02  push    rbx
0x14009ae03  push    rsi
0x14009ae04  push    rdi
0x14009ae05  push    r12
0x14009ae07  push    r13
0x14009ae09  push    r14
0x14009ae0b  push    r15
0x14009ae0d  lea     rbp, [rsp-538h]
0x14009ae15  sub     rsp, 638h
0x14009ae1c  mov     rax, cs:__security_cookie
0x14009ae23  xor     rax, rsp
0x14009ae26  mov     [rbp+570h+var_50], rax
0x14009ae2d  mov     rdi, rcx
0x14009ae30  xor     esi, esi
0x14009ae32  lea     r15d, [rsi+1]
0x14009ae36  mov     [rsp+670h+var_620], r15d
0x14009ae3b  lea     r8, [rsp+670h+var_620]; unsigned int
0x14009ae40  call    ?GetCurrentProcessExecutionOptionNoThrow@details@wil@@YAJPEBGKPEAK@Z; wil::details::GetCurrentProcessExecutionOptionNoThrow(ushort const *,ulong,ulong *)
0x14009ae45  mov     rcx, [rbp+578h]; this
0x14009ae4c  test    eax, eax
0x14009ae4e  js      loc_14009BD03
0x14009ae54  mov     r13d, 2
0x14009ae5a  mov     ebx, [rsp+670h+var_620]
0x14009ae5e  test    ebx, ebx
0x14009ae60  jz      short loc_14009AE83
0x14009ae62  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x14009ae67  test    al, al
0x14009ae69  jnz     short loc_14009AE78
0x14009ae6b  mov     ecx, 1F4h; dwMilliseconds
0x14009ae70  call    cs:__imp_Sleep
0x14009ae76  jmp     short loc_14009AE36
0x14009ae78  cmp     ebx, r13d
0x14009ae7b  jnz     short loc_14009AE83
0x14009ae7d  call    cs:__imp_DebugBreak
0x14009ae83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FileExplorerLongPath2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerLongPath2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerLongPath2> `wil::Feature<__WilFeatureTraits_Feature_FileExplorerLongPath2>::GetImpl(void)'::`2'::impl
0x14009ae8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FileExplorerLongPath2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FileExplorerLongPath2>::__private_IsEnabled(wil::ReportingKind)
0x14009ae8f  test    al, al
0x14009ae91  jz      short loc_14009AEAE
0x14009ae93  mov     rax, gs:60h
0x14009ae9c  mov     cl, [rax+3]
0x14009ae9f  or      cl, 80h
0x14009aea2  mov     rax, gs:60h
0x14009aeab  mov     [rax+3], cl
0x14009aeae  call    cs:__imp_DXGIDeclareAdapterRemovalSupport
0x14009aeb4  mov     cs:qword_140253E00, rsi
0x14009aebb  lea     rax, qword_140253E18
0x14009aec2  mov     cs:WPP_MAIN_CB, rax
0x14009aec9  mov     cs:qword_140253E08, r15
0x14009aed0  mov     cs:qword_140253E28, rsi
0x14009aed7  lea     rax, qword_140253E40
0x14009aede  mov     cs:qword_140253E18, rax
0x14009aee5  mov     cs:qword_140253E30, r15
0x14009aeec  mov     cs:qword_140253E50, rsi
0x14009aef3  lea     rax, qword_140253E68
0x14009aefa  mov     cs:qword_140253E40, rax
0x14009af01  mov     cs:qword_140253E58, r15
0x14009af08  mov     cs:qword_140253E78, rsi
0x14009af0f  lea     rax, qword_140253E90
0x14009af16  mov     cs:qword_140253E68, rax
0x14009af1d  mov     cs:qword_140253E80, r15
0x14009af24  mov     cs:qword_140253EA0, rsi
0x14009af2b  lea     rax, qword_140253EB8
0x14009af32  mov     cs:qword_140253E90, rax
0x14009af39  mov     cs:qword_140253EA8, r15
0x14009af40  mov     cs:qword_140253EC8, rsi
0x14009af47  mov     cs:qword_140253EB8, rsi
0x14009af4e  mov     cs:qword_140253ED0, r15
0x14009af55  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x14009af5c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x14009af63  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x14009af6a  mov     cs:qword_140253DC8, rax
0x14009af71  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x14009af78  mov     cs:qword_140253DD0, rax
0x14009af7f  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider
0x14009af86  mov     cs:qword_140253DD8, rax
0x14009af8d  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider
0x14009af94  mov     cs:qword_140253DE0, rax
0x14009af9b  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider
0x14009afa2  mov     cs:qword_140253DE8, rax
0x14009afa9  lea     rax, WPP_MAIN_CB
0x14009afb0  mov     cs:WPP_GLOBAL_Control, rax
0x14009afb7  call    WppInitUm
0x14009afbc  lea     r14, Microsoft_Windows_Shell_Core_Provider_Context
0x14009afc3  mov     r9, r14
0x14009afc6  mov     r8, r14
0x14009afc9  lea     rcx, Microsoft_Windows_Shell_Core_Provider
0x14009afd0  call    McGenEventRegister_EventRegister
0x14009afd5  lea     r9, MICROSOFT_TWINAPI_PUBLISHER_Context
0x14009afdc  lea     r8, MICROSOFT_TWINAPI_PUBLISHER_Context
0x14009afe3  lea     rcx, MICROSOFT_TWINAPI_PUBLISHER
0x14009afea  call    McGenEventRegister_EventRegister
0x14009afef  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x14009aff7  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@YAK_K@Z@4QBEB; uchar const near * const `EnableManifestedProviderForMicrosoftTelemetry(unsigned __int64)'::`2'::Traits
0x14009affe  mov     edx, r13d
0x14009b001  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x14009b008  call    cs:__imp_EventSetInformation
0x14009b00e  mov     [rsp+670h+var_620], esi
0x14009b012  lea     rax, [rsp+670h+var_620]
0x14009b017  mov     qword ptr [rsp+670h+dwOptions], rax; int *
0x14009b01c  lea     r8, aExplorerstartu; "ExplorerStartupTraceRecorded"
0x14009b023  lea     rbx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14009b02a  mov     rdx, rbx; unsigned __int16 *
0x14009b02d  mov     r12, 0FFFFFFFF80000001h
0x14009b034  mov     rcx, r12; HKEY
0x14009b037  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x14009b03c  cmp     [rsp+670h+var_620], esi
0x14009b040  jnz     short loc_14009B05C
0x14009b042  call    ?StartLogging@@YAJPEBU_TRACE_INFO@@PEBG@Z; StartLogging(_TRACE_INFO const *,ushort const *)
0x14009b047  mov     r9d, r15d; int
0x14009b04a  lea     r8, aExplorerstartu; "ExplorerStartupTraceRecorded"
0x14009b051  mov     rdx, rbx; unsigned __int16 *
0x14009b054  mov     rcx, r12; HKEY
0x14009b057  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x14009b05c  mov     r12d, 20h ; ' '
0x14009b062  test    cs:byte_140253B81, r12b
0x14009b069  jz      short loc_14009B089
0x14009b06b  lea     rax, [rbp+570h+hMutex]
0x14009b072  mov     qword ptr [rsp+670h+dwOptions], rax; int
0x14009b077  mov     r9d, r15d
0x14009b07a  lea     rdx, ShellTraceId_Explorer_InitializingExplorer_Start
0x14009b081  mov     rcx, r14
0x14009b084  call    McGenEventWrite_EventWriteTransfer
0x14009b089  lea     rcx, AppID; "Microsoft.Windows.Explorer"
0x14009b090  call    cs:__imp_SetCurrentProcessExplicitAppUserModelID
0x14009b096  mov     ecx, 4001h; uMode
0x14009b09b  call    cs:__imp_SetErrorMode
0x14009b0a1  mov     ecx, r15d; Mode
0x14009b0a4  call    cs:__imp__set_error_mode
0x14009b0aa  call    ?SeverBamChildConnectionsForProcess@@YAJXZ; SeverBamChildConnectionsForProcess(void)
0x14009b0af  mov     rcx, [rbp+578h]; this
0x14009b0b6  test    eax, eax
0x14009b0b8  jns     short loc_14009B0CE
0x14009b0ba  mov     r9d, eax; char *
0x14009b0bd  lea     r8, aPcshellShellEx_3; "pcshell\\shell\\explorer\\initcab.cpp"
0x14009b0c4  mov     edx, 505h; void *
0x14009b0c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009b0ce  call    cs:__imp_GetCurrentProcess
0x14009b0d4  mov     rcx, rax; hProcess
0x14009b0d7  mov     edx, 80h; dwPriorityClass
0x14009b0dc  call    cs:__imp_SetPriorityClass
0x14009b0e2  xor     ecx, ecx
0x14009b0e4  call    cs:__imp_EnableMouseInPointer
0x14009b0ea  mov     cs:g_hinstCabinet, rdi
0x14009b0f1  xor     edx, edx
0x14009b0f3  xor     ecx, ecx
0x14009b0f5  call    Cabinet_InitGlobalMetrics
0x14009b0fa  mov     [rsp+670h+lpdwDisposition], rsi; lpdwDisposition
0x14009b0ff  lea     rax, g_hkeyExplorer
0x14009b106  mov     [rsp+670h+phkResult], rax; phkResult
0x14009b10b  mov     [rsp+670h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x14009b110  mov     [rsp+670h+samDesired], 2000000h; samDesired
0x14009b118  mov     [rsp+670h+dwOptions], esi; int
0x14009b11c  xor     r9d, r9d; lpClass
0x14009b11f  xor     r8d, r8d; Reserved
0x14009b122  mov     rdx, rbx; lpSubKey
0x14009b125  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14009b12c  call    cs:__imp_RegCreateKeyExW
0x14009b132  mov     [rbp+570h+hMutex], rsi
0x14009b139  call    cs:__imp_GetCommandLineW
0x14009b13f  mov     rcx, rax; pszPath
0x14009b142  call    cs:__imp_PathGetArgsW
0x14009b148  lea     r8, [rbp+570h+hMutex]
0x14009b14f  mov     rdx, rax
0x14009b152  lea     rcx, [rsp+670h+ppv]
0x14009b157  call    ?Create@ExplorerServerConfiguration@@SA?AV1@PEBGPEAPEAX@Z; ExplorerServerConfiguration::Create(ushort const *,void * *)
0x14009b15c  mov     ebx, dword ptr [rsp+670h+ppv+4]
0x14009b160  cmp     cs:?m_firstProcessEntry@@3_NA, sil; bool m_firstProcessEntry
0x14009b167  jz      short loc_14009B17D
0x14009b169  lea     rcx, aExplorer_0; "explorer"
0x14009b170  call    cs:__imp_RmEnableLimits
0x14009b176  mov     cs:?m_firstProcessEntry@@3_NA, sil; bool m_firstProcessEntry
0x14009b17d  cmp     ebx, 5
0x14009b180  jz      short loc_14009B18F
0x14009b182  lea     rcx, aHorizontalscro; "-HorizontalScrollMode 2 -VerticalScroll"...
0x14009b189  call    cs:__imp_ConfigureDownlevelInput
0x14009b18f  mov     ecx, ebx
0x14009b191  call    cs:__imp_SetExplorerServerMode
0x14009b197  mov     rcx, [rbp+578h]; this
0x14009b19e  test    eax, eax
0x14009b1a0  jns     short loc_14009B1B6
0x14009b1a2  mov     r9d, eax; char *
0x14009b1a5  lea     r8, aPcshellShellEx_3; "pcshell\\shell\\explorer\\initcab.cpp"
0x14009b1ac  mov     edx, 532h; void *
0x14009b1b1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009b1b6  cmp     ebx, 3
0x14009b1b9  jz      loc_14009B3C4
0x14009b1bf  mov     rdi, [rbp+570h+hMutex]
0x14009b1c6  test    rdi, rdi
0x14009b1c9  jz      short loc_14009B1DD
0x14009b1cb  mov     rcx, rdi; hMutex
0x14009b1ce  call    cs:__imp_ReleaseMutex
0x14009b1d4  mov     rcx, rdi; hObject
0x14009b1d7  call    cs:__imp_CloseHandle
0x14009b1dd  call    cs:__imp_GetCurrentProcess
0x14009b1e3  mov     rcx, rax; hProcess
0x14009b1e6  mov     edx, r12d; dwPriorityClass
0x14009b1e9  call    cs:__imp_SetPriorityClass
0x14009b1ef  cmp     ebx, 5
0x14009b1f2  jnz     short loc_14009B23A
0x14009b1f4  mov     [rbp+570h+pExecInfo.cbSize], 70h ; 'p'
0x14009b1fb  xor     edx, edx; Val
0x14009b1fd  lea     r8d, [rbx+67h]; Size
0x14009b201  lea     rcx, [rbp+570h+pExecInfo.fMask]; void *
0x14009b205  call    memset_0
0x14009b20a  mov     [rbp+570h+pExecInfo.nShow], r15d
0x14009b20e  mov     [rbp+570h+pExecInfo.fMask], 200010Ch
0x14009b215  lea     rax, aOpennewwindow; "OpenNewWindow"
0x14009b21c  mov     [rbp+570h+pExecInfo.lpVerb], rax
0x14009b220  lea     rax, pszName; "shell:::{52205fd8-5dfb-447d-801a-d0b52f"...
0x14009b227  mov     [rbp+570h+pExecInfo.lpFile], rax
0x14009b22b  lea     rcx, [rbp+570h+pExecInfo]; pExecInfo
0x14009b22f  call    cs:__imp_ShellExecuteExW
0x14009b235  jmp     loc_14009BC2B
0x14009b23a  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x14009b23f  mov     edi, eax
0x14009b241  test    eax, eax
0x14009b243  js      loc_14009BC2B
0x14009b249  xorps   xmm0, xmm0
0x14009b24c  xor     eax, eax
0x14009b24e  movups  xmmword ptr [rbp+570h+pidl], xmm0
0x14009b252  movups  [rbp+570h+var_540], xmm0
0x14009b256  mov     [rbp+570h+var_530], rax
0x14009b25a  call    cs:__imp_GetCommandLineW
0x14009b260  mov     rcx, rax; pszPath
0x14009b263  call    cs:__imp_PathGetArgsW
0x14009b269  lea     rdx, [rbp+570h+pidl]; ppidl
0x14009b26d  mov     rcx, rax; unsigned __int16 *
0x14009b270  call    SHExplorerParseCmdLine
0x14009b275  test    eax, eax
0x14009b277  jz      loc_14009B3B1
0x14009b27d  call    ?SetExplorerComGlobalOptions@@YAXXZ; SetExplorerComGlobalOptions(void)
0x14009b282  lea     eax, [rbx-4]
0x14009b285  test    eax, 0FFFFFFFDh
0x14009b28a  jz      loc_14009B33D
0x14009b290  mov     [rsp+670h+ppv], rsi
0x14009b295  lea     rcx, [rsp+670h+ppv]
0x14009b29a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14009b29f  lea     rax, [rsp+670h+ppv]
0x14009b2a4  mov     qword ptr [rsp+670h+dwOptions], rax; ppv
0x14009b2a9  lea     r9, _GUID_9b25c299_03b6_4a14_827d_095485d0c022; riid
0x14009b2b0  mov     r8d, r15d; dwClsContext
0x14009b2b3  xor     edx, edx; pUnkOuter
0x14009b2b5  lea     rcx, CLSID_ExplorerLauncher; rclsid
0x14009b2bc  call    cs:__imp_CoCreateInstance
0x14009b2c2  test    eax, eax
0x14009b2c4  js      short loc_14009B331
0x14009b2c6  mov     qword ptr [rbp+570h+pExecInfo.cbSize], 68h ; 'h'
0x14009b2ce  xor     edx, edx; Val
0x14009b2d0  lea     r8d, [rdx+60h]; Size
0x14009b2d4  lea     rcx, [rbp+570h+pExecInfo.hwnd]; void *
0x14009b2d8  call    memset_0
0x14009b2dd  lea     rcx, [rbp+570h+pExecInfo]; lpStartupInfo
0x14009b2e1  call    cs:__imp_GetStartupInfoW
0x14009b2e7  mov     rcx, [rsp+670h+ppv]
0x14009b2ec  mov     rax, [rcx]
0x14009b2ef  mov     r10, [rax+18h]
0x14009b2f3  test    byte ptr [rbp+570h+pExecInfo.hInstApp+4], r15b
0x14009b2f7  movzx   eax, word ptr [rbp+570h+pExecInfo.lpIDList]
0x14009b2fb  jnz     short loc_14009B302
0x14009b2fd  mov     eax, 0Ah
0x14009b302  mov     [rsp+670h+lpdwDisposition], rsi
0x14009b307  mov     [rsp+670h+phkResult], rsi
0x14009b30c  mov     [rsp+670h+lpSecurityAttributes], rsi
0x14009b311  mov     [rsp+670h+samDesired], eax
0x14009b315  mov     qword ptr [rsp+670h+dwOptions], rsi
0x14009b31a  mov     r9d, dword ptr [rbp+570h+var_540+4]
0x14009b31e  mov     r8, [rbp+570h+pidl]
0x14009b322  lea     rdx, CLSID_SeparateMultipleProcessExplorerHost
0x14009b329  mov     rax, r10
0x14009b32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b331  lea     rcx, [rsp+670h+ppv]
0x14009b336  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14009b33b  jmp     short loc_14009B3A7
0x14009b33d  mov     [rsp+670h+var_610], rsi
0x14009b342  lea     rcx, [rsp+670h+var_610]
0x14009b347  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14009b34c  lea     rax, [rsp+670h+var_610]
0x14009b351  mov     qword ptr [rsp+670h+dwOptions], rax; ppv
0x14009b356  lea     r9, _GUID_c4de032a_d902_450a_bc43_d9df6d0fd48c; riid
0x14009b35d  mov     r8d, r15d; dwClsContext
0x14009b360  xor     edx, edx; pUnkOuter
0x14009b362  lea     rcx, CLSID_ExplorerHostCreator; rclsid
0x14009b369  call    cs:__imp_CoCreateInstance
0x14009b36f  test    eax, eax
0x14009b371  js      short loc_14009B39D
0x14009b373  mov     rcx, [rsp+670h+var_610]
0x14009b378  mov     rax, [rcx]
0x14009b37b  lea     rdx, [rbp+570h+var_540+8]
0x14009b37f  mov     rax, [rax+18h]
0x14009b383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b388  test    eax, eax
0x14009b38a  js      short loc_14009B39D
0x14009b38c  mov     rcx, [rsp+670h+var_610]
0x14009b391  mov     rax, [rcx]
0x14009b394  mov     rax, [rax+20h]
0x14009b398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009b39d  lea     rcx, [rsp+670h+var_610]
0x14009b3a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14009b3a7  mov     rcx, [rbp+570h+pidl]; pidl
  ... truncated ...
```
