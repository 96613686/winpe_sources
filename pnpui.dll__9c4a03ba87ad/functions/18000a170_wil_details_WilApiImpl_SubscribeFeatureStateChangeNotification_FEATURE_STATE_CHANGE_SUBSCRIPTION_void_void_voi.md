# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a170`
- end: `0x18000a27d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180009a44`
- `0x180009b40`
- `0x18000a170`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a211`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a211`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a1fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a1c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a1c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a267`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a267`

## string_xrefs

- `0x18000a1f3`: `ntdll.dll`
- `0x18000a207`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180014020);
      if ( qword_180014090 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180014090 = 0;
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
               &qword_180014090);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180014020);
    }
  }
}

```

## disassembly

```asm
0x18000a170  mov     [rsp+arg_0], rbx
0x18000a175  mov     [rsp+arg_8], rsi
0x18000a17a  push    rdi
0x18000a17b  sub     rsp, 30h
0x18000a17f  mov     rdi, r8
0x18000a182  mov     rsi, rdx
0x18000a185  mov     rbx, rcx
0x18000a188  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a18c  jnz     short loc_18000A1A5
0x18000a18e  mov     r8, rdx; void (*)(void *)
0x18000a191  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a194  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a19b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000a1a0  jmp     loc_18000A26D
0x18000a1a5  mov     qword ptr [rcx], 0
0x18000a1ac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a1b3  jz      loc_18000A26D
0x18000a1b9  lea     rcx, stru_180014020; SRWLock
0x18000a1c0  call    cs:__imp_AcquireSRWLockExclusive
0x18000a1c6  cmp     cs:qword_180014090, 0
0x18000a1ce  jnz     short loc_18000A24B
0x18000a1d0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a1d7  mov     cs:qword_180014090, 0
0x18000a1e2  test    rax, rax
0x18000a1e5  jnz     short loc_18000A22A
0x18000a1e7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a1ee  test    rax, rax
0x18000a1f1  jnz     short loc_18000A207
0x18000a1f3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a1fa  call    cs:__imp_GetModuleHandleW
0x18000a200  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a207  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a20e  mov     rcx, rax; hModule
0x18000a211  call    cs:__imp_GetProcAddress
0x18000a217  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a21e  test    rax, rax
0x18000a221  jnz     short loc_18000A22A
0x18000a223  mov     eax, 0C0000139h
0x18000a228  jmp     short loc_18000A247
0x18000a22a  lea     r9, qword_180014090
0x18000a231  xor     r8d, r8d
0x18000a234  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a23b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000a242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a247  test    eax, eax
0x18000a249  jnz     short loc_18000A260
0x18000a24b  mov     r9, rdi; void *
0x18000a24e  lea     rcx, CriticalSection; this
0x18000a255  mov     r8, rsi; void (*)(void *)
0x18000a258  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a25b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000a260  lea     rcx, stru_180014020; SRWLock
0x18000a267  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a26d  mov     rbx, [rsp+38h+arg_0]
0x18000a272  mov     rsi, [rsp+38h+arg_8]
0x18000a277  add     rsp, 30h
0x18000a27b  pop     rdi
0x18000a27c  retn
```
