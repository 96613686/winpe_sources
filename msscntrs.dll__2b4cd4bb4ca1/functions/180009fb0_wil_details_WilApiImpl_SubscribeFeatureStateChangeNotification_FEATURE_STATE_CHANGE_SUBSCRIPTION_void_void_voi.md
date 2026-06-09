# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009fb0`
- end: `0x18000a0bd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180009820`
- `0x18000991c`
- `0x180009fb0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a051`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a051`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a03a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a03a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a000`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a000`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a0a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a0a7`

## string_xrefs

- `0x18000a033`: `ntdll.dll`
- `0x18000a047`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180021180);
      if ( qword_1800211F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800211F0 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_1800211F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180021180);
    }
  }
}

```

## disassembly

```asm
0x180009fb0  mov     [rsp+arg_0], rbx
0x180009fb5  mov     [rsp+arg_8], rsi
0x180009fba  push    rdi
0x180009fbb  sub     rsp, 30h
0x180009fbf  mov     rdi, r8
0x180009fc2  mov     rsi, rdx
0x180009fc5  mov     rbx, rcx
0x180009fc8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009fcc  jnz     short loc_180009FE5
0x180009fce  mov     r8, rdx; void (*)(void *)
0x180009fd1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009fd4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009fdb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009fe0  jmp     loc_18000A0AD
0x180009fe5  mov     qword ptr [rcx], 0
0x180009fec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009ff3  jz      loc_18000A0AD
0x180009ff9  lea     rcx, stru_180021180; SRWLock
0x18000a000  call    cs:__imp_AcquireSRWLockExclusive
0x18000a006  cmp     cs:qword_1800211F0, 0
0x18000a00e  jnz     short loc_18000A08B
0x18000a010  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a017  mov     cs:qword_1800211F0, 0
0x18000a022  test    rax, rax
0x18000a025  jnz     short loc_18000A06A
0x18000a027  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a02e  test    rax, rax
0x18000a031  jnz     short loc_18000A047
0x18000a033  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000a03a  call    cs:__imp_GetModuleHandleW
0x18000a040  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a047  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a04e  mov     rcx, rax; hModule
0x18000a051  call    cs:__imp_GetProcAddress
0x18000a057  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a05e  test    rax, rax
0x18000a061  jnz     short loc_18000A06A
0x18000a063  mov     eax, 0C0000139h
0x18000a068  jmp     short loc_18000A087
0x18000a06a  lea     r9, qword_1800211F0
0x18000a071  xor     r8d, r8d
0x18000a074  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a07b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a087  test    eax, eax
0x18000a089  jnz     short loc_18000A0A0
0x18000a08b  mov     r9, rdi; void *
0x18000a08e  lea     rcx, CriticalSection; this
0x18000a095  mov     r8, rsi; void (*)(void *)
0x18000a098  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a09b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a0a0  lea     rcx, stru_180021180; SRWLock
0x18000a0a7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a0ad  mov     rbx, [rsp+38h+arg_0]
0x18000a0b2  mov     rsi, [rsp+38h+arg_8]
0x18000a0b7  add     rsp, 30h
0x18000a0bb  pop     rdi
0x18000a0bc  retn
```
