# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c220`
- end: `0x18000c32d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000bcbc`
- `0x18000bdb8`
- `0x18000c220`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c2aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c2aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c2c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c2c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c317`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c317`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c270`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c270`

## string_xrefs

- `0x18000c2a3`: `ntdll.dll`
- `0x18000c2b7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180043380);
      if ( qword_1800433F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800433F0 = 0;
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
               &qword_1800433F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180043380);
    }
  }
}

```

## disassembly

```asm
0x18000c220  mov     [rsp+arg_0], rbx
0x18000c225  mov     [rsp+arg_8], rsi
0x18000c22a  push    rdi
0x18000c22b  sub     rsp, 30h
0x18000c22f  mov     rdi, r8
0x18000c232  mov     rsi, rdx
0x18000c235  mov     rbx, rcx
0x18000c238  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c23c  jnz     short loc_18000C255
0x18000c23e  mov     r8, rdx; void (*)(void *)
0x18000c241  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c244  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c24b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000c250  jmp     loc_18000C31D
0x18000c255  mov     qword ptr [rcx], 0
0x18000c25c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c263  jz      loc_18000C31D
0x18000c269  lea     rcx, stru_180043380; SRWLock
0x18000c270  call    cs:__imp_AcquireSRWLockExclusive
0x18000c276  cmp     cs:qword_1800433F0, 0
0x18000c27e  jnz     short loc_18000C2FB
0x18000c280  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c287  mov     cs:qword_1800433F0, 0
0x18000c292  test    rax, rax
0x18000c295  jnz     short loc_18000C2DA
0x18000c297  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c29e  test    rax, rax
0x18000c2a1  jnz     short loc_18000C2B7
0x18000c2a3  lea     rcx, ModuleName; "ntdll.dll"
0x18000c2aa  call    cs:__imp_GetModuleHandleW
0x18000c2b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c2b7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c2be  mov     rcx, rax; hModule
0x18000c2c1  call    cs:__imp_GetProcAddress
0x18000c2c7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c2ce  test    rax, rax
0x18000c2d1  jnz     short loc_18000C2DA
0x18000c2d3  mov     eax, 0C0000139h
0x18000c2d8  jmp     short loc_18000C2F7
0x18000c2da  lea     r9, qword_1800433F0
0x18000c2e1  xor     r8d, r8d
0x18000c2e4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c2eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000c2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2f7  test    eax, eax
0x18000c2f9  jnz     short loc_18000C310
0x18000c2fb  mov     r9, rdi; void *
0x18000c2fe  lea     rcx, CriticalSection; this
0x18000c305  mov     r8, rsi; void (*)(void *)
0x18000c308  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c30b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000c310  lea     rcx, stru_180043380; SRWLock
0x18000c317  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c31d  mov     rbx, [rsp+38h+arg_0]
0x18000c322  mov     rsi, [rsp+38h+arg_8]
0x18000c327  add     rsp, 30h
0x18000c32b  pop     rdi
0x18000c32c  retn
```
