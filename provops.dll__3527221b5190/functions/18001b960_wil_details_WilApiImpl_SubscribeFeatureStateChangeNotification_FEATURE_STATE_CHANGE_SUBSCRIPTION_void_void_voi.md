# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001b960`
- end: `0x18001ba6d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001b10c`
- `0x18001b208`
- `0x18001b960`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b9ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b9ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ba01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ba01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b9b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b9b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ba57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ba57`

## string_xrefs

- `0x18001b9e3`: `ntdll.dll`
- `0x18001b9f7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18004A0D0);
      if ( qword_18004A140 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18004A140 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
               &qword_18004A140);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18004A0D0);
    }
  }
}

```

## disassembly

```asm
0x18001b960  mov     [rsp+arg_0], rbx
0x18001b965  mov     [rsp+arg_8], rsi
0x18001b96a  push    rdi
0x18001b96b  sub     rsp, 30h
0x18001b96f  mov     rdi, r8
0x18001b972  mov     rsi, rdx
0x18001b975  mov     rbx, rcx
0x18001b978  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001b97c  jnz     short loc_18001B995
0x18001b97e  mov     r8, rdx; void (*)(void *)
0x18001b981  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001b984  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001b98b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18001b990  jmp     loc_18001BA5D
0x18001b995  mov     qword ptr [rcx], 0
0x18001b99c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001b9a3  jz      loc_18001BA5D
0x18001b9a9  lea     rcx, stru_18004A0D0; SRWLock
0x18001b9b0  call    cs:__imp_AcquireSRWLockExclusive
0x18001b9b6  cmp     cs:qword_18004A140, 0
0x18001b9be  jnz     short loc_18001BA3B
0x18001b9c0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001b9c7  mov     cs:qword_18004A140, 0
0x18001b9d2  test    rax, rax
0x18001b9d5  jnz     short loc_18001BA1A
0x18001b9d7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b9de  test    rax, rax
0x18001b9e1  jnz     short loc_18001B9F7
0x18001b9e3  lea     rcx, ModuleName; "ntdll.dll"
0x18001b9ea  call    cs:__imp_GetModuleHandleW
0x18001b9f0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001b9f7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001b9fe  mov     rcx, rax; hModule
0x18001ba01  call    cs:__imp_GetProcAddress
0x18001ba07  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001ba0e  test    rax, rax
0x18001ba11  jnz     short loc_18001BA1A
0x18001ba13  mov     eax, 0C0000139h
0x18001ba18  jmp     short loc_18001BA37
0x18001ba1a  lea     r9, qword_18004A140
0x18001ba21  xor     r8d, r8d
0x18001ba24  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001ba2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001ba32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba37  test    eax, eax
0x18001ba39  jnz     short loc_18001BA50
0x18001ba3b  mov     r9, rdi; void *
0x18001ba3e  lea     rcx, CriticalSection; this
0x18001ba45  mov     r8, rsi; void (*)(void *)
0x18001ba48  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001ba4b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001ba50  lea     rcx, stru_18004A0D0; SRWLock
0x18001ba57  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ba5d  mov     rbx, [rsp+38h+arg_0]
0x18001ba62  mov     rsi, [rsp+38h+arg_8]
0x18001ba67  add     rsp, 30h
0x18001ba6b  pop     rdi
0x18001ba6c  retn
```
