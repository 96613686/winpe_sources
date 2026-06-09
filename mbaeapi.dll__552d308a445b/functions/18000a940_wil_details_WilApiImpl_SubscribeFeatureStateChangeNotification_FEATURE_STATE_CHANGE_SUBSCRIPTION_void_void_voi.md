# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000a940`
- end: `0x18000aa4d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a194`
- `0x18000a290`
- `0x18000a940`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a9ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a9e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a990`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa37`

## string_xrefs

- `0x18000a9c3`: `ntdll.dll`
- `0x18000a9d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180084298);
      if ( qword_180084308 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180084308 = 0;
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
               &qword_180084308);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180084298);
    }
  }
}

```

## disassembly

```asm
0x18000a940  mov     [rsp+arg_0], rbx
0x18000a945  mov     [rsp+arg_8], rsi
0x18000a94a  push    rdi
0x18000a94b  sub     rsp, 30h
0x18000a94f  mov     rdi, r8
0x18000a952  mov     rsi, rdx
0x18000a955  mov     rbx, rcx
0x18000a958  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a95c  jnz     short loc_18000A975
0x18000a95e  mov     r8, rdx; void (*)(void *)
0x18000a961  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000a964  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000a96b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000a970  jmp     loc_18000AA3D
0x18000a975  mov     qword ptr [rcx], 0
0x18000a97c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000a983  jz      loc_18000AA3D
0x18000a989  lea     rcx, stru_180084298; SRWLock
0x18000a990  call    cs:__imp_AcquireSRWLockExclusive
0x18000a996  cmp     cs:qword_180084308, 0
0x18000a99e  jnz     short loc_18000AA1B
0x18000a9a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000a9a7  mov     cs:qword_180084308, 0
0x18000a9b2  test    rax, rax
0x18000a9b5  jnz     short loc_18000A9FA
0x18000a9b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a9be  test    rax, rax
0x18000a9c1  jnz     short loc_18000A9D7
0x18000a9c3  lea     rcx, ModuleName; "ntdll.dll"
0x18000a9ca  call    cs:__imp_GetModuleHandleW
0x18000a9d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a9d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000a9de  mov     rcx, rax; hModule
0x18000a9e1  call    cs:__imp_GetProcAddress
0x18000a9e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000a9ee  test    rax, rax
0x18000a9f1  jnz     short loc_18000A9FA
0x18000a9f3  mov     eax, 0C0000139h
0x18000a9f8  jmp     short loc_18000AA17
0x18000a9fa  lea     r9, qword_180084308
0x18000aa01  xor     r8d, r8d
0x18000aa04  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000aa0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x18000aa12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa17  test    eax, eax
0x18000aa19  jnz     short loc_18000AA30
0x18000aa1b  mov     r9, rdi; void *
0x18000aa1e  lea     rcx, CriticalSection; this
0x18000aa25  mov     r8, rsi; void (*)(void *)
0x18000aa28  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000aa2b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000aa30  lea     rcx, stru_180084298; SRWLock
0x18000aa37  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aa3d  mov     rbx, [rsp+38h+arg_0]
0x18000aa42  mov     rsi, [rsp+38h+arg_8]
0x18000aa47  add     rsp, 30h
0x18000aa4b  pop     rdi
0x18000aa4c  retn
```
