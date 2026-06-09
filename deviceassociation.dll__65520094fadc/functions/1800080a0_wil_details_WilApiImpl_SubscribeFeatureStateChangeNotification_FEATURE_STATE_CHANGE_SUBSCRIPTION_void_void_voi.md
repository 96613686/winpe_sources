# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800080a0`
- end: `0x1800081ad`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800079ec`
- `0x180007ae8`
- `0x1800080a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008197`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008197`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008141`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008141`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000812a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000812a`

## string_xrefs

- `0x180008123`: `ntdll.dll`
- `0x180008137`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180015040);
      if ( qword_1800150B0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800150B0 = 0;
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
               &qword_1800150B0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180015040);
    }
  }
}

```

## disassembly

```asm
0x1800080a0  mov     [rsp+arg_0], rbx
0x1800080a5  mov     [rsp+arg_8], rsi
0x1800080aa  push    rdi
0x1800080ab  sub     rsp, 30h
0x1800080af  mov     rdi, r8
0x1800080b2  mov     rsi, rdx
0x1800080b5  mov     rbx, rcx
0x1800080b8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800080bc  jnz     short loc_1800080D5
0x1800080be  mov     r8, rdx; void (*)(void *)
0x1800080c1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800080c4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800080cb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800080d0  jmp     loc_18000819D
0x1800080d5  mov     qword ptr [rcx], 0
0x1800080dc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800080e3  jz      loc_18000819D
0x1800080e9  lea     rcx, stru_180015040; SRWLock
0x1800080f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800080f6  cmp     cs:qword_1800150B0, 0
0x1800080fe  jnz     short loc_18000817B
0x180008100  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008107  mov     cs:qword_1800150B0, 0
0x180008112  test    rax, rax
0x180008115  jnz     short loc_18000815A
0x180008117  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000811e  test    rax, rax
0x180008121  jnz     short loc_180008137
0x180008123  lea     rcx, ModuleName; "ntdll.dll"
0x18000812a  call    cs:__imp_GetModuleHandleW
0x180008130  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008137  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000813e  mov     rcx, rax; hModule
0x180008141  call    cs:__imp_GetProcAddress
0x180008147  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000814e  test    rax, rax
0x180008151  jnz     short loc_18000815A
0x180008153  mov     eax, 0C0000139h
0x180008158  jmp     short loc_180008177
0x18000815a  lea     r9, qword_1800150B0
0x180008161  xor     r8d, r8d
0x180008164  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000816b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008177  test    eax, eax
0x180008179  jnz     short loc_180008190
0x18000817b  mov     r9, rdi; void *
0x18000817e  lea     rcx, CriticalSection; this
0x180008185  mov     r8, rsi; void (*)(void *)
0x180008188  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000818b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008190  lea     rcx, stru_180015040; SRWLock
0x180008197  call    cs:__imp_ReleaseSRWLockExclusive
0x18000819d  mov     rbx, [rsp+38h+arg_0]
0x1800081a2  mov     rsi, [rsp+38h+arg_8]
0x1800081a7  add     rsp, 30h
0x1800081ab  pop     rdi
0x1800081ac  retn
```
