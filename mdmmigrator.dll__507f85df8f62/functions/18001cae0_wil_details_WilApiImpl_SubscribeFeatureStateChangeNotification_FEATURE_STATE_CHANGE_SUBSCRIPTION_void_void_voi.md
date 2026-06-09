# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001cae0`
- end: `0x18001cbed`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18001bdb8`
- `0x18001beb4`
- `0x18001cae0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cb6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001cb6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cb81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cb30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cb30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cbd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001cbd7`

## string_xrefs

- `0x18001cb63`: `ntdll.dll`
- `0x18001cb77`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18002B210 )
        goto LABEL_12;
      qword_18002B210 = 0;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_18002B210);
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
0x18001cae0  mov     [rsp+arg_0], rbx
0x18001cae5  mov     [rsp+arg_8], rsi
0x18001caea  push    rdi
0x18001caeb  sub     rsp, 30h
0x18001caef  mov     rdi, r8
0x18001caf2  mov     rsi, rdx
0x18001caf5  mov     rbx, rcx
0x18001caf8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001cafc  jnz     short loc_18001CB15
0x18001cafe  mov     r8, rdx; void (*)(void *)
0x18001cb01  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001cb04  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001cb0b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18001cb10  jmp     loc_18001CBDD
0x18001cb15  mov     qword ptr [rcx], 0
0x18001cb1c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cb23  jz      loc_18001CBDD
0x18001cb29  lea     rcx, SRWLock; SRWLock
0x18001cb30  call    cs:__imp_AcquireSRWLockExclusive
0x18001cb36  cmp     cs:qword_18002B210, 0
0x18001cb3e  jnz     short loc_18001CBBB
0x18001cb40  mov     cs:qword_18002B210, 0
0x18001cb4b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001cb52  test    rax, rax
0x18001cb55  jnz     short loc_18001CB9A
0x18001cb57  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cb5e  test    rax, rax
0x18001cb61  jnz     short loc_18001CB77
0x18001cb63  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001cb6a  call    cs:__imp_GetModuleHandleW
0x18001cb70  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001cb77  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001cb7e  mov     rcx, rax; hModule
0x18001cb81  call    cs:__imp_GetProcAddress
0x18001cb87  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001cb8e  test    rax, rax
0x18001cb91  jnz     short loc_18001CB9A
0x18001cb93  mov     eax, 0C0000139h
0x18001cb98  jmp     short loc_18001CBB7
0x18001cb9a  lea     r9, qword_18002B210
0x18001cba1  xor     r8d, r8d
0x18001cba4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001cbab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18001cbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbb7  test    eax, eax
0x18001cbb9  jnz     short loc_18001CBD0
0x18001cbbb  mov     r9, rdi; void *
0x18001cbbe  mov     r8, rsi; void (*)(void *)
0x18001cbc1  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001cbc4  lea     rcx, CriticalSection; this
0x18001cbcb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18001cbd0  lea     rcx, SRWLock; SRWLock
0x18001cbd7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cbdd  mov     rbx, [rsp+38h+arg_0]
0x18001cbe2  mov     rsi, [rsp+38h+arg_8]
0x18001cbe7  add     rsp, 30h
0x18001cbeb  pop     rdi
0x18001cbec  retn
```
