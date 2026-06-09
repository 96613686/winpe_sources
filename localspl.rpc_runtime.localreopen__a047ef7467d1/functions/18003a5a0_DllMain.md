# DllMain

- ea: `0x18003a5a0`
- end: `0x18003a882`
- name: `DllMain`
- size: `738`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800464c4`

## callees

- `0x18002a3b8`
- `0x18002d16c`
- `0x18003a5a0`
- `0x18003e984`
- `0x180072fbc`
- `0x18007efa4`
- `0x18007efdc`
- `0x1800cc9e0`
- `0x1800cca40`
- `0x1800df488`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003a5e7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003a5e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a758`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a7d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a7eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a83e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a758`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a7d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a7eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a819`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a83e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a67a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a696`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a67a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003a696`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003a614`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003a627`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003a614`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003a627`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a649`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a6cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a717`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a649`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a6cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003a717`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18003a6a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18003a6a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003a77f`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003a77f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a79b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a7b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a79b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a7b4`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18003a850`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18003a850`

## string_xrefs

- `0x18003a5ce`: `DllMain`
- `0x18003a864`: `DllMain`
- `0x18003a5c7`: `DLL_PROCESS_ATTACH`
- `0x18003a85d`: `DLL_PROCESS_DETACH`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx
  BOOL v5; // eax
  HINSTANCE v6; // rbx

  v4 = 0;
  if ( fdwReason )
  {
    if ( fdwReason != 1 )
      return v4;
    LocalSpoolerTelemetry::WriteDbgTraceInfo("DllMain", L"DLL_PROCESS_ATTACH", lpvReserved);
    SplEventLogRegister();
    McGenEventRegister_EtwEventRegister();
    DisableThreadLibraryCalls(hinstDLL);
    hInst = hinstDLL;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl'::`2'::impl) )
    {
      gbSpoolerSectionInit = 1;
      InitializeCriticalSection(&SpoolerSection);
      dword_18013F160 = 1;
      InitializeCriticalSection(&RegistryLock);
    }
    else
    {
      gbSingleCore = IsSingleCore();
      v5 = InitializeCriticalSectionAndSpinCount(&SpoolerSection, 0x2710u);
      v4 = v5;
      if ( v5 )
        gbSpoolerSectionInit = 1;
      if ( gbSingleCore )
      {
        if ( !v5 )
          goto LABEL_20;
      }
      else
      {
        if ( !v5 )
          goto LABEL_20;
        ghNoThreadsHaveSharedLock = CreateEventW(0, 1, 1, 0);
        if ( !ghNoThreadsHaveSharedLock )
          goto LABEL_17;
        ghNoThreadsWaitingForUpgrade = CreateEventW(0, 1, 1, 0);
        if ( !ghNoThreadsWaitingForUpgrade )
          goto LABEL_17;
        gRecursiveLockSlot = TlsAlloc();
        if ( gRecursiveLockSlot == -1 )
          goto LABEL_17;
      }
      v4 = InitializeCriticalSectionAndSpinCount(&RegistryLock, 0x80000000);
      if ( !v4 )
        goto LABEL_20;
      dword_18013F160 = 1;
    }
    if ( (int)NPackageInstallLocalspl::TDriverStore::CreatePackageLock() >= 0 )
    {
      v6 = hInst;
      LocalMonTelemetry::WriteDbgTraceInfo("LocalMonInit", L"Entering");
      LcmhInst = v6;
      v4 = InitializeCriticalSectionAndSpinCount(&LcmSpoolerSection, 0x80000000);
      if ( v4 )
        dword_18013F1E0 = 1;
LABEL_20:
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl'::`2'::impl);
      if ( v4 )
        return v4;
      goto LABEL_21;
    }
LABEL_17:
    v4 = 0;
    goto LABEL_20;
  }
LABEL_21:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl'::`2'::impl);
  if ( bPackageLockInit )
  {
    DeleteCriticalSection(&g_PackageLock);
    bPackageLockInit = 0;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl'::`2'::impl) )
  {
    if ( gRecursiveLockSlot != -1 )
    {
      TlsFree(gRecursiveLockSlot);
      gRecursiveLockSlot = -1;
    }
    if ( ghNoThreadsWaitingForUpgrade )
    {
      CloseHandle(ghNoThreadsWaitingForUpgrade);
      ghNoThreadsWaitingForUpgrade = 0;
    }
    if ( ghNoThreadsHaveSharedLock )
    {
      CloseHandle(ghNoThreadsHaveSharedLock);
      ghNoThreadsHaveSharedLock = 0;
    }
  }
  if ( gbSpoolerSectionInit )
  {
    DeleteCriticalSection(&SpoolerSection);
    gbSpoolerSectionInit = 0;
  }
  if ( dword_18013F160 )
  {
    DeleteCriticalSection(&RegistryLock);
    dword_18013F160 = 0;
  }
  if ( dword_18013F1E0 )
  {
    LocalMonTelemetry::WriteDbgTraceInfo("LocalMonCleanUp", L"Entering");
    DeleteCriticalSection(&LcmSpoolerSection);
    dword_18013F1E0 = 0;
  }
  McGenEventUnregister_EtwEventUnregister();
  SplEventLogUnregister();
  if ( g_3dSectionInitialized )
    DeleteCriticalSection(&g_3dSection);
  if ( g_hNotification )
  {
    CM_Unregister_Notification();
    g_hNotification = 0;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo("DllMain", L"DLL_PROCESS_DETACH");
  return v4;
}

```

## disassembly

```asm
0x18003a5a0  mov     [rsp+arg_0], rbx
0x18003a5a5  mov     [rsp+arg_8], rsi
0x18003a5aa  push    rdi
0x18003a5ab  sub     rsp, 20h
0x18003a5af  xor     esi, esi
0x18003a5b1  mov     rdi, rcx
0x18003a5b4  mov     ebx, esi
0x18003a5b6  test    edx, edx
0x18003a5b8  jz      loc_18003A73D
0x18003a5be  cmp     edx, 1
0x18003a5c1  jnz     loc_18003A870
0x18003a5c7  lea     rdx, aDllProcessAtta; "DLL_PROCESS_ATTACH"
0x18003a5ce  lea     rcx, aDllmain_0; "DllMain"
0x18003a5d5  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003a5da  call    ?SplEventLogRegister@@YAKXZ; SplEventLogRegister(void)
0x18003a5df  call    McGenEventRegister_EtwEventRegister
0x18003a5e4  mov     rcx, rdi; hLibModule
0x18003a5e7  call    cs:__imp_DisableThreadLibraryCalls
0x18003a5ed  mov     cs:hInst, rdi
0x18003a5f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl(void)'::`2'::impl
0x18003a5fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(void)
0x18003a600  test    al, al
0x18003a602  jz      short loc_18003A632
0x18003a604  lea     edi, [rsi+1]
0x18003a607  lea     rcx, SpoolerSection; lpCriticalSection
0x18003a60e  mov     cs:gbSpoolerSectionInit, edi
0x18003a614  call    cs:__imp_InitializeCriticalSection
0x18003a61a  lea     rcx, RegistryLock; lpCriticalSection
0x18003a621  mov     cs:dword_18013F160, edi
0x18003a627  call    cs:__imp_InitializeCriticalSection
0x18003a62d  jmp     loc_18003A6DD
0x18003a632  call    ?IsSingleCore@@YAHXZ; IsSingleCore(void)
0x18003a637  mov     edx, 2710h; dwSpinCount
0x18003a63c  mov     cs:gbSingleCore, eax
0x18003a642  lea     rcx, SpoolerSection; lpCriticalSection
0x18003a649  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003a64f  mov     ebx, eax
0x18003a651  mov     edi, 1
0x18003a656  test    eax, eax
0x18003a658  jz      short loc_18003A660
0x18003a65a  mov     cs:gbSpoolerSectionInit, edi
0x18003a660  cmp     cs:gbSingleCore, esi
0x18003a666  jnz     short loc_18003A6BB
0x18003a668  test    eax, eax
0x18003a66a  jz      loc_18003A729
0x18003a670  xor     r9d, r9d; lpName
0x18003a673  mov     r8d, edi; bInitialState
0x18003a676  mov     edx, edi; bManualReset
0x18003a678  xor     ecx, ecx; lpEventAttributes
0x18003a67a  call    cs:__imp_CreateEventW
0x18003a680  mov     cs:ghNoThreadsHaveSharedLock, rax
0x18003a687  test    rax, rax
0x18003a68a  jz      short loc_18003A6E6
0x18003a68c  xor     r9d, r9d; lpName
0x18003a68f  mov     r8d, edi; bInitialState
0x18003a692  mov     edx, edi; bManualReset
0x18003a694  xor     ecx, ecx; lpEventAttributes
0x18003a696  call    cs:__imp_CreateEventW
0x18003a69c  mov     cs:ghNoThreadsWaitingForUpgrade, rax
0x18003a6a3  test    rax, rax
0x18003a6a6  jz      short loc_18003A6E6
0x18003a6a8  call    cs:__imp_TlsAlloc
0x18003a6ae  mov     cs:gRecursiveLockSlot, eax
0x18003a6b4  cmp     eax, 0FFFFFFFFh
0x18003a6b7  jnz     short loc_18003A6BF
0x18003a6b9  jmp     short loc_18003A6E6
0x18003a6bb  test    eax, eax
0x18003a6bd  jz      short loc_18003A729
0x18003a6bf  mov     edx, 80000000h; dwSpinCount
0x18003a6c4  lea     rcx, RegistryLock; lpCriticalSection
0x18003a6cb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003a6d1  mov     ebx, eax
0x18003a6d3  test    eax, eax
0x18003a6d5  jz      short loc_18003A729
0x18003a6d7  mov     cs:dword_18013F160, edi
0x18003a6dd  call    ?CreatePackageLock@TDriverStore@NPackageInstallLocalspl@@SAJXZ; NPackageInstallLocalspl::TDriverStore::CreatePackageLock(void)
0x18003a6e2  test    eax, eax
0x18003a6e4  jns     short loc_18003A6EA
0x18003a6e6  mov     ebx, esi
0x18003a6e8  jmp     short loc_18003A729
0x18003a6ea  mov     rbx, cs:hInst
0x18003a6f1  lea     rdx, aEntering; "Entering"
0x18003a6f8  lea     rcx, aLocalmoninit; "LocalMonInit"
0x18003a6ff  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003a704  mov     edx, 80000000h; dwSpinCount
0x18003a709  mov     cs:?LcmhInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * LcmhInst
0x18003a710  lea     rcx, ?LcmSpoolerSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a717  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003a71d  mov     ebx, eax
0x18003a71f  test    eax, eax
0x18003a721  jz      short loc_18003A729
0x18003a723  mov     cs:dword_18013F1E0, edi
0x18003a729  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl(void)'::`2'::impl
0x18003a730  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(void)
0x18003a735  test    ebx, ebx
0x18003a737  jnz     loc_18003A870
0x18003a73d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl(void)'::`2'::impl
0x18003a744  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(void)
0x18003a749  cmp     cs:?bPackageLockInit@@3HA, esi; int bPackageLockInit
0x18003a74f  jz      short loc_18003A764
0x18003a751  lea     rcx, ?g_PackageLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a758  call    cs:__imp_DeleteCriticalSection
0x18003a75e  mov     cs:?bPackageLockInit@@3HA, esi; int bPackageLockInit
0x18003a764  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::GetImpl(void)'::`2'::impl
0x18003a76b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_Print_SpoolerDeadlockFix>::__private_IsEnabled(void)
0x18003a770  test    al, al
0x18003a772  jnz     short loc_18003A7C1
0x18003a774  mov     ecx, cs:gRecursiveLockSlot; dwTlsIndex
0x18003a77a  cmp     ecx, 0FFFFFFFFh
0x18003a77d  jz      short loc_18003A78F
0x18003a77f  call    cs:__imp_TlsFree
0x18003a785  mov     cs:gRecursiveLockSlot, 0FFFFFFFFh
0x18003a78f  mov     rcx, cs:ghNoThreadsWaitingForUpgrade; hObject
0x18003a796  test    rcx, rcx
0x18003a799  jz      short loc_18003A7A8
0x18003a79b  call    cs:__imp_CloseHandle
0x18003a7a1  mov     cs:ghNoThreadsWaitingForUpgrade, rsi
0x18003a7a8  mov     rcx, cs:ghNoThreadsHaveSharedLock; hObject
0x18003a7af  test    rcx, rcx
0x18003a7b2  jz      short loc_18003A7C1
0x18003a7b4  call    cs:__imp_CloseHandle
0x18003a7ba  mov     cs:ghNoThreadsHaveSharedLock, rsi
0x18003a7c1  cmp     cs:gbSpoolerSectionInit, esi
0x18003a7c7  jz      short loc_18003A7DC
0x18003a7c9  lea     rcx, SpoolerSection; lpCriticalSection
0x18003a7d0  call    cs:__imp_DeleteCriticalSection
0x18003a7d6  mov     cs:gbSpoolerSectionInit, esi
0x18003a7dc  cmp     cs:dword_18013F160, esi
0x18003a7e2  jz      short loc_18003A7F7
0x18003a7e4  lea     rcx, RegistryLock; lpCriticalSection
0x18003a7eb  call    cs:__imp_DeleteCriticalSection
0x18003a7f1  mov     cs:dword_18013F160, esi
0x18003a7f7  cmp     cs:dword_18013F1E0, esi
0x18003a7fd  jz      short loc_18003A825
0x18003a7ff  lea     rdx, aEntering; "Entering"
0x18003a806  lea     rcx, aLocalmoncleanu; "LocalMonCleanUp"
0x18003a80d  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003a812  lea     rcx, ?LcmSpoolerSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a819  call    cs:__imp_DeleteCriticalSection
0x18003a81f  mov     cs:dword_18013F1E0, esi
0x18003a825  call    McGenEventUnregister_EtwEventUnregister
0x18003a82a  call    ?SplEventLogUnregister@@YAKXZ; SplEventLogUnregister(void)
0x18003a82f  cmp     cs:?g_3dSectionInitialized@@3HA, esi; int g_3dSectionInitialized
0x18003a835  jz      short loc_18003A844
0x18003a837  lea     rcx, ?g_3dSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003a83e  call    cs:__imp_DeleteCriticalSection
0x18003a844  mov     rcx, cs:?g_hNotification@@3PEAXEA; void * g_hNotification
0x18003a84b  test    rcx, rcx
0x18003a84e  jz      short loc_18003A85D
0x18003a850  call    cs:__imp_CM_Unregister_Notification
0x18003a856  mov     cs:?g_hNotification@@3PEAXEA, rsi; void * g_hNotification
0x18003a85d  lea     rdx, aDllProcessDeta; "DLL_PROCESS_DETACH"
0x18003a864  lea     rcx, aDllmain_0; "DllMain"
0x18003a86b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18003a870  mov     rsi, [rsp+28h+arg_8]
0x18003a875  mov     eax, ebx
0x18003a877  mov     rbx, [rsp+28h+arg_0]
0x18003a87c  add     rsp, 20h
0x18003a880  pop     rdi
0x18003a881  retn
```
