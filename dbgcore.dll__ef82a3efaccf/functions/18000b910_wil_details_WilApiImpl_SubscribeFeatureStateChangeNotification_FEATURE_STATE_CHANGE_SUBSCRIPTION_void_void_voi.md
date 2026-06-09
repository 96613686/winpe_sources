# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000b910`
- end: `0x18000ba1d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000afb4`
- `0x18000b0b0`
- `0x18000b910`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b9b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b9b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b99a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b99a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b960`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b960`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba07`

## string_xrefs

- `0x18000b993`: `ntdll.dll`
- `0x18000b9a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18003C0F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18003C0F0 = 0;
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
               &qword_18003C0F0);
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
0x18000b910  mov     [rsp+arg_0], rbx
0x18000b915  mov     [rsp+arg_8], rsi
0x18000b91a  push    rdi
0x18000b91b  sub     rsp, 30h
0x18000b91f  mov     rdi, r8
0x18000b922  mov     rsi, rdx
0x18000b925  mov     rbx, rcx
0x18000b928  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b92c  jnz     short loc_18000B945
0x18000b92e  mov     r8, rdx; void (*)(void *)
0x18000b931  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b934  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b93b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000b940  jmp     loc_18000BA0D
0x18000b945  mov     qword ptr [rcx], 0
0x18000b94c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b953  jz      loc_18000BA0D
0x18000b959  lea     rcx, SRWLock; SRWLock
0x18000b960  call    cs:__imp_AcquireSRWLockExclusive
0x18000b966  cmp     cs:qword_18003C0F0, 0
0x18000b96e  jnz     short loc_18000B9EB
0x18000b970  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b977  mov     cs:qword_18003C0F0, 0
0x18000b982  test    rax, rax
0x18000b985  jnz     short loc_18000B9CA
0x18000b987  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b98e  test    rax, rax
0x18000b991  jnz     short loc_18000B9A7
0x18000b993  lea     rcx, ModuleName; "ntdll.dll"
0x18000b99a  call    cs:__imp_GetModuleHandleW
0x18000b9a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b9a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b9ae  mov     rcx, rax; hModule
0x18000b9b1  call    cs:__imp_GetProcAddress
0x18000b9b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b9be  test    rax, rax
0x18000b9c1  jnz     short loc_18000B9CA
0x18000b9c3  mov     eax, 0C0000139h
0x18000b9c8  jmp     short loc_18000B9E7
0x18000b9ca  lea     r9, qword_18003C0F0
0x18000b9d1  xor     r8d, r8d
0x18000b9d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b9db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000b9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e7  test    eax, eax
0x18000b9e9  jnz     short loc_18000BA00
0x18000b9eb  mov     r9, rdi; void *
0x18000b9ee  lea     rcx, CriticalSection; this
0x18000b9f5  mov     r8, rsi; void (*)(void *)
0x18000b9f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000b9fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ba00  lea     rcx, SRWLock; SRWLock
0x18000ba07  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba0d  mov     rbx, [rsp+38h+arg_0]
0x18000ba12  mov     rsi, [rsp+38h+arg_8]
0x18000ba17  add     rsp, 30h
0x18000ba1b  pop     rdi
0x18000ba1c  retn
```
