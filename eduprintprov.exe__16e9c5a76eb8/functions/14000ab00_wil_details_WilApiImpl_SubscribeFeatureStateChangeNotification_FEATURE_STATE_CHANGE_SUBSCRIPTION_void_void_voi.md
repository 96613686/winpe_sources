# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000ab00`
- end: `0x14000ac0d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000a398`
- `0x14000a494`
- `0x14000ab00`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ab8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ab8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000aba1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000aba1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ab50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ab50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000abf7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000abf7`

## string_xrefs

- `0x14000ab83`: `ntdll.dll`
- `0x14000ab97`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_14001D0C8 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_14001D0C8 = 0;
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
               &qword_14001D0C8);
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
0x14000ab00  mov     [rsp+arg_0], rbx
0x14000ab05  mov     [rsp+arg_8], rsi
0x14000ab0a  push    rdi
0x14000ab0b  sub     rsp, 30h
0x14000ab0f  mov     rdi, r8
0x14000ab12  mov     rsi, rdx
0x14000ab15  mov     rbx, rcx
0x14000ab18  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000ab1c  jnz     short loc_14000AB35
0x14000ab1e  mov     r8, rdx; void (*)(void *)
0x14000ab21  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000ab24  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000ab2b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000ab30  jmp     loc_14000ABFD
0x14000ab35  mov     qword ptr [rcx], 0
0x14000ab3c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000ab43  jz      loc_14000ABFD
0x14000ab49  lea     rcx, SRWLock; SRWLock
0x14000ab50  call    cs:__imp_AcquireSRWLockExclusive
0x14000ab56  cmp     cs:qword_14001D0C8, 0
0x14000ab5e  jnz     short loc_14000ABDB
0x14000ab60  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000ab67  mov     cs:qword_14001D0C8, 0
0x14000ab72  test    rax, rax
0x14000ab75  jnz     short loc_14000ABBA
0x14000ab77  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ab7e  test    rax, rax
0x14000ab81  jnz     short loc_14000AB97
0x14000ab83  lea     rcx, ModuleName; "ntdll.dll"
0x14000ab8a  call    cs:__imp_GetModuleHandleW
0x14000ab90  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ab97  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000ab9e  mov     rcx, rax; hModule
0x14000aba1  call    cs:__imp_GetProcAddress
0x14000aba7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000abae  test    rax, rax
0x14000abb1  jnz     short loc_14000ABBA
0x14000abb3  mov     eax, 0C0000139h
0x14000abb8  jmp     short loc_14000ABD7
0x14000abba  lea     r9, qword_14001D0C8
0x14000abc1  xor     r8d, r8d
0x14000abc4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000abcb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000abd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abd7  test    eax, eax
0x14000abd9  jnz     short loc_14000ABF0
0x14000abdb  mov     r9, rdi; void *
0x14000abde  lea     rcx, CriticalSection; this
0x14000abe5  mov     r8, rsi; void (*)(void *)
0x14000abe8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000abeb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000abf0  lea     rcx, SRWLock; SRWLock
0x14000abf7  call    cs:__imp_ReleaseSRWLockExclusive
0x14000abfd  mov     rbx, [rsp+38h+arg_0]
0x14000ac02  mov     rsi, [rsp+38h+arg_8]
0x14000ac07  add     rsp, 30h
0x14000ac0b  pop     rdi
0x14000ac0c  retn
```
