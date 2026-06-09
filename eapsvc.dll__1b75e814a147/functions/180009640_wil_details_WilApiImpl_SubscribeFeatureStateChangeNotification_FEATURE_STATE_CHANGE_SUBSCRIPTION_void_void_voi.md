# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009640`
- end: `0x18000974d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180008ecc`
- `0x180008fc8`
- `0x180009640`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009690`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009690`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009737`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009737`

## string_xrefs

- `0x1800096c3`: `ntdll.dll`
- `0x1800096d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1800200B0);
      if ( qword_180020120 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180020120 = 0;
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
               &qword_180020120);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800200B0);
    }
  }
}

```

## disassembly

```asm
0x180009640  mov     [rsp+arg_0], rbx
0x180009645  mov     [rsp+arg_8], rsi
0x18000964a  push    rdi
0x18000964b  sub     rsp, 30h
0x18000964f  mov     rdi, r8
0x180009652  mov     rsi, rdx
0x180009655  mov     rbx, rcx
0x180009658  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000965c  jnz     short loc_180009675
0x18000965e  mov     r8, rdx; void (*)(void *)
0x180009661  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009664  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000966b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009670  jmp     loc_18000973D
0x180009675  mov     qword ptr [rcx], 0
0x18000967c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009683  jz      loc_18000973D
0x180009689  lea     rcx, stru_1800200B0; SRWLock
0x180009690  call    cs:__imp_AcquireSRWLockExclusive
0x180009696  cmp     cs:qword_180020120, 0
0x18000969e  jnz     short loc_18000971B
0x1800096a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800096a7  mov     cs:qword_180020120, 0
0x1800096b2  test    rax, rax
0x1800096b5  jnz     short loc_1800096FA
0x1800096b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800096be  test    rax, rax
0x1800096c1  jnz     short loc_1800096D7
0x1800096c3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800096ca  call    cs:__imp_GetModuleHandleW
0x1800096d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800096d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800096de  mov     rcx, rax; hModule
0x1800096e1  call    cs:__imp_GetProcAddress
0x1800096e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800096ee  test    rax, rax
0x1800096f1  jnz     short loc_1800096FA
0x1800096f3  mov     eax, 0C0000139h
0x1800096f8  jmp     short loc_180009717
0x1800096fa  lea     r9, qword_180020120
0x180009701  xor     r8d, r8d
0x180009704  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000970b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009717  test    eax, eax
0x180009719  jnz     short loc_180009730
0x18000971b  mov     r9, rdi; void *
0x18000971e  lea     rcx, CriticalSection; this
0x180009725  mov     r8, rsi; void (*)(void *)
0x180009728  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000972b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180009730  lea     rcx, stru_1800200B0; SRWLock
0x180009737  call    cs:__imp_ReleaseSRWLockExclusive
0x18000973d  mov     rbx, [rsp+38h+arg_0]
0x180009742  mov     rsi, [rsp+38h+arg_8]
0x180009747  add     rsp, 30h
0x18000974b  pop     rdi
0x18000974c  retn
```
