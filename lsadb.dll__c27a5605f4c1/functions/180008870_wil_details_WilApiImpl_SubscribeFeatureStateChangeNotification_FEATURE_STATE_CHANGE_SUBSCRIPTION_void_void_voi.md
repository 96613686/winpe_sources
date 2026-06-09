# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008870`
- end: `0x18000897d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180008124`
- `0x180008220`
- `0x180008870`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008911`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008911`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008967`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008967`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088c0`

## string_xrefs

- `0x1800088f3`: `ntdll.dll`
- `0x180008907`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180047510);
      if ( qword_180047580 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180047580 = 0;
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
               &qword_180047580);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180047510);
    }
  }
}

```

## disassembly

```asm
0x180008870  mov     [rsp+arg_0], rbx
0x180008875  mov     [rsp+arg_8], rsi
0x18000887a  push    rdi
0x18000887b  sub     rsp, 30h
0x18000887f  mov     rdi, r8
0x180008882  mov     rsi, rdx
0x180008885  mov     rbx, rcx
0x180008888  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000888c  jnz     short loc_1800088A5
0x18000888e  mov     r8, rdx; void (*)(void *)
0x180008891  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008894  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000889b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x1800088a0  jmp     loc_18000896D
0x1800088a5  mov     qword ptr [rcx], 0
0x1800088ac  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800088b3  jz      loc_18000896D
0x1800088b9  lea     rcx, stru_180047510; SRWLock
0x1800088c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800088c6  cmp     cs:qword_180047580, 0
0x1800088ce  jnz     short loc_18000894B
0x1800088d0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800088d7  mov     cs:qword_180047580, 0
0x1800088e2  test    rax, rax
0x1800088e5  jnz     short loc_18000892A
0x1800088e7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800088ee  test    rax, rax
0x1800088f1  jnz     short loc_180008907
0x1800088f3  lea     rcx, ModuleName; "ntdll.dll"
0x1800088fa  call    cs:__imp_GetModuleHandleW
0x180008900  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008907  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000890e  mov     rcx, rax; hModule
0x180008911  call    cs:__imp_GetProcAddress
0x180008917  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000891e  test    rax, rax
0x180008921  jnz     short loc_18000892A
0x180008923  mov     eax, 0C0000139h
0x180008928  jmp     short loc_180008947
0x18000892a  lea     r9, qword_180047580
0x180008931  xor     r8d, r8d
0x180008934  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000893b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008947  test    eax, eax
0x180008949  jnz     short loc_180008960
0x18000894b  mov     r9, rdi; void *
0x18000894e  lea     rcx, CriticalSection; this
0x180008955  mov     r8, rsi; void (*)(void *)
0x180008958  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000895b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008960  lea     rcx, stru_180047510; SRWLock
0x180008967  call    cs:__imp_ReleaseSRWLockExclusive
0x18000896d  mov     rbx, [rsp+38h+arg_0]
0x180008972  mov     rsi, [rsp+38h+arg_8]
0x180008977  add     rsp, 30h
0x18000897b  pop     rdi
0x18000897c  retn
```
