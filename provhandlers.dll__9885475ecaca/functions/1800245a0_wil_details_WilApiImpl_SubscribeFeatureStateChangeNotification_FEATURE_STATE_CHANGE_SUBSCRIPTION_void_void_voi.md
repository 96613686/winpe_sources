# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1800245a0`
- end: `0x1800246ad`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180024100`
- `0x1800241fc`
- `0x1800245a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002462a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002462a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024641`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024641`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800245f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800245f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024697`

## string_xrefs

- `0x180024623`: `ntdll.dll`
- `0x180024637`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800521F0);
      if ( qword_180052260 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180052260 = 0;
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
               &qword_180052260);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800521F0);
    }
  }
}

```

## disassembly

```asm
0x1800245a0  mov     [rsp+arg_0], rbx
0x1800245a5  mov     [rsp+arg_8], rsi
0x1800245aa  push    rdi
0x1800245ab  sub     rsp, 30h
0x1800245af  mov     rdi, r8
0x1800245b2  mov     rsi, rdx
0x1800245b5  mov     rbx, rcx
0x1800245b8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800245bc  jnz     short loc_1800245D5
0x1800245be  mov     r8, rdx; void (*)(void *)
0x1800245c1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800245c4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800245cb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800245d0  jmp     loc_18002469D
0x1800245d5  mov     qword ptr [rcx], 0
0x1800245dc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800245e3  jz      loc_18002469D
0x1800245e9  lea     rcx, stru_1800521F0; SRWLock
0x1800245f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800245f6  cmp     cs:qword_180052260, 0
0x1800245fe  jnz     short loc_18002467B
0x180024600  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180024607  mov     cs:qword_180052260, 0
0x180024612  test    rax, rax
0x180024615  jnz     short loc_18002465A
0x180024617  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002461e  test    rax, rax
0x180024621  jnz     short loc_180024637
0x180024623  lea     rcx, ModuleName; "ntdll.dll"
0x18002462a  call    cs:__imp_GetModuleHandleW
0x180024630  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024637  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002463e  mov     rcx, rax; hModule
0x180024641  call    cs:__imp_GetProcAddress
0x180024647  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002464e  test    rax, rax
0x180024651  jnz     short loc_18002465A
0x180024653  mov     eax, 0C0000139h
0x180024658  jmp     short loc_180024677
0x18002465a  lea     r9, qword_180052260
0x180024661  xor     r8d, r8d
0x180024664  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18002466b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180024672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024677  test    eax, eax
0x180024679  jnz     short loc_180024690
0x18002467b  mov     r9, rdi; void *
0x18002467e  lea     rcx, CriticalSection; this
0x180024685  mov     r8, rsi; void (*)(void *)
0x180024688  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18002468b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180024690  lea     rcx, stru_1800521F0; SRWLock
0x180024697  call    cs:__imp_ReleaseSRWLockExclusive
0x18002469d  mov     rbx, [rsp+38h+arg_0]
0x1800246a2  mov     rsi, [rsp+38h+arg_8]
0x1800246a7  add     rsp, 30h
0x1800246ab  pop     rdi
0x1800246ac  retn
```
