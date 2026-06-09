# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000cf80`
- end: `0x18000d08d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c7d4`
- `0x18000c8d0`
- `0x18000cf80`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d00a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d00a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d021`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d021`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d077`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d077`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cfd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cfd0`

## string_xrefs

- `0x18000d003`: `ntdll.dll`
- `0x18000d017`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800502D0);
      if ( qword_180050340 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180050340 = 0;
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
               &qword_180050340);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800502D0);
    }
  }
}

```

## disassembly

```asm
0x18000cf80  mov     [rsp+arg_0], rbx
0x18000cf85  mov     [rsp+arg_8], rsi
0x18000cf8a  push    rdi
0x18000cf8b  sub     rsp, 30h
0x18000cf8f  mov     rdi, r8
0x18000cf92  mov     rsi, rdx
0x18000cf95  mov     rbx, rcx
0x18000cf98  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000cf9c  jnz     short loc_18000CFB5
0x18000cf9e  mov     r8, rdx; void (*)(void *)
0x18000cfa1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000cfa4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000cfab  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000cfb0  jmp     loc_18000D07D
0x18000cfb5  mov     qword ptr [rcx], 0
0x18000cfbc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cfc3  jz      loc_18000D07D
0x18000cfc9  lea     rcx, stru_1800502D0; SRWLock
0x18000cfd0  call    cs:__imp_AcquireSRWLockExclusive
0x18000cfd6  cmp     cs:qword_180050340, 0
0x18000cfde  jnz     short loc_18000D05B
0x18000cfe0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000cfe7  mov     cs:qword_180050340, 0
0x18000cff2  test    rax, rax
0x18000cff5  jnz     short loc_18000D03A
0x18000cff7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cffe  test    rax, rax
0x18000d001  jnz     short loc_18000D017
0x18000d003  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d00a  call    cs:__imp_GetModuleHandleW
0x18000d010  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d017  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d01e  mov     rcx, rax; hModule
0x18000d021  call    cs:__imp_GetProcAddress
0x18000d027  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d02e  test    rax, rax
0x18000d031  jnz     short loc_18000D03A
0x18000d033  mov     eax, 0C0000139h
0x18000d038  jmp     short loc_18000D057
0x18000d03a  lea     r9, qword_180050340
0x18000d041  xor     r8d, r8d
0x18000d044  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000d04b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000d052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d057  test    eax, eax
0x18000d059  jnz     short loc_18000D070
0x18000d05b  mov     r9, rdi; void *
0x18000d05e  lea     rcx, CriticalSection; this
0x18000d065  mov     r8, rsi; void (*)(void *)
0x18000d068  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000d06b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000d070  lea     rcx, stru_1800502D0; SRWLock
0x18000d077  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d07d  mov     rbx, [rsp+38h+arg_0]
0x18000d082  mov     rsi, [rsp+38h+arg_8]
0x18000d087  add     rsp, 30h
0x18000d08b  pop     rdi
0x18000d08c  retn
```
