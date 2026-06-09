# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011310`
- end: `0x18001141d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180010e54`
- `0x180010f50`
- `0x180011310`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800113b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800113b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001139a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001139a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011360`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011360`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011407`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011407`

## string_xrefs

- `0x180011393`: `ntdll.dll`
- `0x1800113a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18001E0D8);
      if ( qword_18001E148 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001E148 = 0;
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
               &qword_18001E148);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18001E0D8);
    }
  }
}

```

## disassembly

```asm
0x180011310  mov     [rsp+arg_0], rbx
0x180011315  mov     [rsp+arg_8], rsi
0x18001131a  push    rdi
0x18001131b  sub     rsp, 30h
0x18001131f  mov     rdi, r8
0x180011322  mov     rsi, rdx
0x180011325  mov     rbx, rcx
0x180011328  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001132c  jnz     short loc_180011345
0x18001132e  mov     r8, rdx; void (*)(void *)
0x180011331  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011334  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001133b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180011340  jmp     loc_18001140D
0x180011345  mov     qword ptr [rcx], 0
0x18001134c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011353  jz      loc_18001140D
0x180011359  lea     rcx, stru_18001E0D8; SRWLock
0x180011360  call    cs:__imp_AcquireSRWLockExclusive
0x180011366  cmp     cs:qword_18001E148, 0
0x18001136e  jnz     short loc_1800113EB
0x180011370  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180011377  mov     cs:qword_18001E148, 0
0x180011382  test    rax, rax
0x180011385  jnz     short loc_1800113CA
0x180011387  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001138e  test    rax, rax
0x180011391  jnz     short loc_1800113A7
0x180011393  lea     rcx, ModuleName; "ntdll.dll"
0x18001139a  call    cs:__imp_GetModuleHandleW
0x1800113a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800113a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800113ae  mov     rcx, rax; hModule
0x1800113b1  call    cs:__imp_GetProcAddress
0x1800113b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800113be  test    rax, rax
0x1800113c1  jnz     short loc_1800113CA
0x1800113c3  mov     eax, 0C0000139h
0x1800113c8  jmp     short loc_1800113E7
0x1800113ca  lea     r9, qword_18001E148
0x1800113d1  xor     r8d, r8d
0x1800113d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800113db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800113e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113e7  test    eax, eax
0x1800113e9  jnz     short loc_180011400
0x1800113eb  mov     r9, rdi; void *
0x1800113ee  lea     rcx, CriticalSection; this
0x1800113f5  mov     r8, rsi; void (*)(void *)
0x1800113f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800113fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011400  lea     rcx, stru_18001E0D8; SRWLock
0x180011407  call    cs:__imp_ReleaseSRWLockExclusive
0x18001140d  mov     rbx, [rsp+38h+arg_0]
0x180011412  mov     rsi, [rsp+38h+arg_8]
0x180011417  add     rsp, 30h
0x18001141b  pop     rdi
0x18001141c  retn
```
