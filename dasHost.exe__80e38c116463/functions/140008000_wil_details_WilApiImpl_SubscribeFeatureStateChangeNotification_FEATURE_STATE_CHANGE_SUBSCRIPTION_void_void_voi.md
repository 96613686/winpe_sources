# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140008000`
- end: `0x14000810d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400078d8`
- `0x1400079d4`
- `0x140008000`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000808a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000808a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400080a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400080a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008050`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400080f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400080f7`

## string_xrefs

- `0x140008083`: `ntdll.dll`
- `0x140008097`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_140029130 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140029130 = 0;
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
               &qword_140029130);
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
0x140008000  mov     [rsp+arg_0], rbx
0x140008005  mov     [rsp+arg_8], rsi
0x14000800a  push    rdi
0x14000800b  sub     rsp, 30h
0x14000800f  mov     rdi, r8
0x140008012  mov     rsi, rdx
0x140008015  mov     rbx, rcx
0x140008018  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000801c  jnz     short loc_140008035
0x14000801e  mov     r8, rdx; void (*)(void *)
0x140008021  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140008024  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000802b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140008030  jmp     loc_1400080FD
0x140008035  mov     qword ptr [rcx], 0
0x14000803c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140008043  jz      loc_1400080FD
0x140008049  lea     rcx, SRWLock; SRWLock
0x140008050  call    cs:__imp_AcquireSRWLockExclusive
0x140008056  cmp     cs:qword_140029130, 0
0x14000805e  jnz     short loc_1400080DB
0x140008060  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140008067  mov     cs:qword_140029130, 0
0x140008072  test    rax, rax
0x140008075  jnz     short loc_1400080BA
0x140008077  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000807e  test    rax, rax
0x140008081  jnz     short loc_140008097
0x140008083  lea     rcx, ModuleName; "ntdll.dll"
0x14000808a  call    cs:__imp_GetModuleHandleW
0x140008090  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008097  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000809e  mov     rcx, rax; hModule
0x1400080a1  call    cs:__imp_GetProcAddress
0x1400080a7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400080ae  test    rax, rax
0x1400080b1  jnz     short loc_1400080BA
0x1400080b3  mov     eax, 0C0000139h
0x1400080b8  jmp     short loc_1400080D7
0x1400080ba  lea     r9, qword_140029130
0x1400080c1  xor     r8d, r8d
0x1400080c4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400080cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400080d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080d7  test    eax, eax
0x1400080d9  jnz     short loc_1400080F0
0x1400080db  mov     r9, rdi; void *
0x1400080de  lea     rcx, CriticalSection; this
0x1400080e5  mov     r8, rsi; void (*)(void *)
0x1400080e8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400080eb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400080f0  lea     rcx, SRWLock; SRWLock
0x1400080f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400080fd  mov     rbx, [rsp+38h+arg_0]
0x140008102  mov     rsi, [rsp+38h+arg_8]
0x140008107  add     rsp, 30h
0x14000810b  pop     rdi
0x14000810c  retn
```
