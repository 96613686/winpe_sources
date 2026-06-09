# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140013970`
- end: `0x140013a7d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400131e0`
- `0x1400132dc`
- `0x140013970`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140013a11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140013a11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400139fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400139fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013a67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013a67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400139c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400139c0`

## string_xrefs

- `0x1400139f3`: `ntdll.dll`
- `0x140013a07`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140075110);
      if ( qword_140075180 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140075180 = 0;
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
        v9 = ((__int64 (__fastcall *)(void (__fastcall *)(__int64), void *, _QWORD, __int64 *))ProcAddress)(
               `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_140075180);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140075110);
    }
  }
}

```

## disassembly

```asm
0x140013970  mov     [rsp+arg_0], rbx
0x140013975  mov     [rsp+arg_8], rsi
0x14001397a  push    rdi
0x14001397b  sub     rsp, 30h
0x14001397f  mov     rdi, r8
0x140013982  mov     rsi, rdx
0x140013985  mov     rbx, rcx
0x140013988  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14001398c  jnz     short loc_1400139A5
0x14001398e  mov     r8, rdx; void (*)(void *)
0x140013991  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140013994  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14001399b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1400139a0  jmp     loc_140013A6D
0x1400139a5  mov     qword ptr [rcx], 0
0x1400139ac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400139b3  jz      loc_140013A6D
0x1400139b9  lea     rcx, stru_140075110; SRWLock
0x1400139c0  call    cs:__imp_AcquireSRWLockExclusive
0x1400139c6  cmp     cs:qword_140075180, 0
0x1400139ce  jnz     short loc_140013A4B
0x1400139d0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1400139d7  mov     cs:qword_140075180, 0
0x1400139e2  test    rax, rax
0x1400139e5  jnz     short loc_140013A2A
0x1400139e7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400139ee  test    rax, rax
0x1400139f1  jnz     short loc_140013A07
0x1400139f3  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1400139fa  call    cs:__imp_GetModuleHandleW
0x140013a00  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140013a07  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140013a0e  mov     rcx, rax; hModule
0x140013a11  call    cs:__imp_GetProcAddress
0x140013a17  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140013a1e  test    rax, rax
0x140013a21  jnz     short loc_140013A2A
0x140013a23  mov     eax, 0C0000139h
0x140013a28  jmp     short loc_140013A47
0x140013a2a  lea     r9, qword_140075180
0x140013a31  xor     r8d, r8d
0x140013a34  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140013a3b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x140013a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013a47  test    eax, eax
0x140013a49  jnz     short loc_140013A60
0x140013a4b  mov     r9, rdi; void *
0x140013a4e  lea     rcx, CriticalSection; this
0x140013a55  mov     r8, rsi; void (*)(void *)
0x140013a58  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140013a5b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140013a60  lea     rcx, stru_140075110; SRWLock
0x140013a67  call    cs:__imp_ReleaseSRWLockExclusive
0x140013a6d  mov     rbx, [rsp+38h+arg_0]
0x140013a72  mov     rsi, [rsp+38h+arg_8]
0x140013a77  add     rsp, 30h
0x140013a7b  pop     rdi
0x140013a7c  retn
```
