# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180014c40`
- end: `0x180014d4d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800136ac`
- `0x1800137a8`
- `0x180014c40`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180014cca`
- `KERNEL32!GetModuleHandleW` at `0x180014cca`
- `KERNEL32!GetProcAddress` at `0x180014ce1`
- `KERNEL32!GetProcAddress` at `0x180014ce1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014c90`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014c90`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180014d37`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180014d37`

## string_xrefs

- `0x180014cc3`: `ntdll.dll`
- `0x180014cd7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18002F0A8);
      if ( qword_18002F118 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18002F118 = 0;
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
               &qword_18002F118);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18002F0A8);
    }
  }
}

```

## disassembly

```asm
0x180014c40  mov     [rsp+arg_0], rbx
0x180014c45  mov     [rsp+arg_8], rsi
0x180014c4a  push    rdi
0x180014c4b  sub     rsp, 30h
0x180014c4f  mov     rdi, r8
0x180014c52  mov     rsi, rdx
0x180014c55  mov     rbx, rcx
0x180014c58  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180014c5c  jnz     short loc_180014C75
0x180014c5e  mov     r8, rdx; void (*)(void *)
0x180014c61  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180014c64  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180014c6b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180014c70  jmp     loc_180014D3D
0x180014c75  mov     qword ptr [rcx], 0
0x180014c7c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180014c83  jz      loc_180014D3D
0x180014c89  lea     rcx, stru_18002F0A8; SRWLock
0x180014c90  call    cs:__imp_AcquireSRWLockExclusive
0x180014c96  cmp     cs:qword_18002F118, 0
0x180014c9e  jnz     short loc_180014D1B
0x180014ca0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180014ca7  mov     cs:qword_18002F118, 0
0x180014cb2  test    rax, rax
0x180014cb5  jnz     short loc_180014CFA
0x180014cb7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014cbe  test    rax, rax
0x180014cc1  jnz     short loc_180014CD7
0x180014cc3  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180014cca  call    cs:__imp_GetModuleHandleW
0x180014cd0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014cd7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180014cde  mov     rcx, rax; hModule
0x180014ce1  call    cs:__imp_GetProcAddress
0x180014ce7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180014cee  test    rax, rax
0x180014cf1  jnz     short loc_180014CFA
0x180014cf3  mov     eax, 0C0000139h
0x180014cf8  jmp     short loc_180014D17
0x180014cfa  lea     r9, qword_18002F118
0x180014d01  xor     r8d, r8d
0x180014d04  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180014d0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180014d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d17  test    eax, eax
0x180014d19  jnz     short loc_180014D30
0x180014d1b  mov     r9, rdi; void *
0x180014d1e  lea     rcx, CriticalSection; this
0x180014d25  mov     r8, rsi; void (*)(void *)
0x180014d28  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180014d2b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180014d30  lea     rcx, stru_18002F0A8; SRWLock
0x180014d37  call    cs:__imp_ReleaseSRWLockExclusive
0x180014d3d  mov     rbx, [rsp+38h+arg_0]
0x180014d42  mov     rsi, [rsp+38h+arg_8]
0x180014d47  add     rsp, 30h
0x180014d4b  pop     rdi
0x180014d4c  retn
```
