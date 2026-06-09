# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000f820`
- end: `0x14000f92d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000db60`
- `0x14000dc5c`
- `0x14000f820`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f8c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f8c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f8aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f8aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f870`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000f917`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000f917`

## string_xrefs

- `0x14000f8a3`: `ntdll.dll`
- `0x14000f8b7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_14001A100 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14001A100 = 0;
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
               &qword_14001A100);
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
0x14000f820  mov     [rsp+arg_0], rbx
0x14000f825  mov     [rsp+arg_8], rsi
0x14000f82a  push    rdi
0x14000f82b  sub     rsp, 30h
0x14000f82f  mov     rdi, r8
0x14000f832  mov     rsi, rdx
0x14000f835  mov     rbx, rcx
0x14000f838  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000f83c  jnz     short loc_14000F855
0x14000f83e  mov     r8, rdx; void (*)(void *)
0x14000f841  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000f844  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000f84b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000f850  jmp     loc_14000F91D
0x14000f855  mov     qword ptr [rcx], 0
0x14000f85c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000f863  jz      loc_14000F91D
0x14000f869  lea     rcx, SRWLock; SRWLock
0x14000f870  call    cs:__imp_AcquireSRWLockExclusive
0x14000f876  cmp     cs:qword_14001A100, 0
0x14000f87e  jnz     short loc_14000F8FB
0x14000f880  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000f887  mov     cs:qword_14001A100, 0
0x14000f892  test    rax, rax
0x14000f895  jnz     short loc_14000F8DA
0x14000f897  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f89e  test    rax, rax
0x14000f8a1  jnz     short loc_14000F8B7
0x14000f8a3  lea     rcx, ModuleName; "ntdll.dll"
0x14000f8aa  call    cs:__imp_GetModuleHandleW
0x14000f8b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f8b7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000f8be  mov     rcx, rax; hModule
0x14000f8c1  call    cs:__imp_GetProcAddress
0x14000f8c7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000f8ce  test    rax, rax
0x14000f8d1  jnz     short loc_14000F8DA
0x14000f8d3  mov     eax, 0C0000139h
0x14000f8d8  jmp     short loc_14000F8F7
0x14000f8da  lea     r9, qword_14001A100
0x14000f8e1  xor     r8d, r8d
0x14000f8e4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000f8eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000f8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8f7  test    eax, eax
0x14000f8f9  jnz     short loc_14000F910
0x14000f8fb  mov     r9, rdi; void *
0x14000f8fe  lea     rcx, CriticalSection; this
0x14000f905  mov     r8, rsi; void (*)(void *)
0x14000f908  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000f90b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000f910  lea     rcx, SRWLock; SRWLock
0x14000f917  call    cs:__imp_ReleaseSRWLockExclusive
0x14000f91d  mov     rbx, [rsp+38h+arg_0]
0x14000f922  mov     rsi, [rsp+38h+arg_8]
0x14000f927  add     rsp, 30h
0x14000f92b  pop     rdi
0x14000f92c  retn
```
