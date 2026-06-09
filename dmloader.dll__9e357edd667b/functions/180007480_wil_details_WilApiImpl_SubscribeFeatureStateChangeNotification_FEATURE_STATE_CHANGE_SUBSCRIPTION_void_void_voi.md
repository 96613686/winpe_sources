# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180007480`
- end: `0x18000758d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180006dac`
- `0x180006ea8`
- `0x180007480`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000750a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000750a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007521`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007521`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800074d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800074d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007577`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007577`

## string_xrefs

- `0x180007503`: `ntdll.dll`
- `0x180007517`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v9; // eax

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_180015090 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180015090 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
      g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_10:
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_180015090);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
}

```

## disassembly

```asm
0x180007480  mov     [rsp+arg_0], rbx
0x180007485  mov     [rsp+arg_8], rsi
0x18000748a  push    rdi
0x18000748b  sub     rsp, 30h
0x18000748f  mov     rdi, r8
0x180007492  mov     rsi, rdx
0x180007495  mov     rbx, rcx
0x180007498  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000749c  jnz     short loc_1800074B5
0x18000749e  mov     r8, rdx; void (*)(void *)
0x1800074a1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800074a4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800074ab  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800074b0  jmp     loc_18000757D
0x1800074b5  mov     qword ptr [rcx], 0
0x1800074bc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800074c3  jz      loc_18000757D
0x1800074c9  lea     rcx, SRWLock; SRWLock
0x1800074d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800074d6  cmp     cs:qword_180015090, 0
0x1800074de  jnz     short loc_18000755B
0x1800074e0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800074e7  mov     cs:qword_180015090, 0
0x1800074f2  test    rax, rax
0x1800074f5  jnz     short loc_18000753A
0x1800074f7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074fe  test    rax, rax
0x180007501  jnz     short loc_180007517
0x180007503  lea     rcx, ModuleName; "ntdll.dll"
0x18000750a  call    cs:__imp_GetModuleHandleW
0x180007510  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007517  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000751e  mov     rcx, rax; hModule
0x180007521  call    cs:__imp_GetProcAddress
0x180007527  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000752e  test    rax, rax
0x180007531  jnz     short loc_18000753A
0x180007533  mov     eax, 0C0000139h
0x180007538  jmp     short loc_180007557
0x18000753a  lea     r9, qword_180015090
0x180007541  xor     r8d, r8d
0x180007544  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000754b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180007552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007557  test    eax, eax
0x180007559  jnz     short loc_180007570
0x18000755b  mov     r9, rdi; void *
0x18000755e  lea     rcx, CriticalSection; this
0x180007565  mov     r8, rsi; void (*)(void *)
0x180007568  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000756b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180007570  lea     rcx, SRWLock; SRWLock
0x180007577  call    cs:__imp_ReleaseSRWLockExclusive
0x18000757d  mov     rbx, [rsp+38h+arg_0]
0x180007582  mov     rsi, [rsp+38h+arg_8]
0x180007587  add     rsp, 30h
0x18000758b  pop     rdi
0x18000758c  retn
```
