# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009d20`
- end: `0x180009e2d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180009244`
- `0x180009340`
- `0x180009d20`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009dc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009dc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009daa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009daa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009e17`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009e17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d70`

## string_xrefs

- `0x180009da3`: `ntdll.dll`
- `0x180009db7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18001B150);
      if ( qword_18001B1C0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001B1C0 = 0;
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
               &qword_18001B1C0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18001B150);
    }
  }
}

```

## disassembly

```asm
0x180009d20  mov     [rsp+arg_0], rbx
0x180009d25  mov     [rsp+arg_8], rsi
0x180009d2a  push    rdi
0x180009d2b  sub     rsp, 30h
0x180009d2f  mov     rdi, r8
0x180009d32  mov     rsi, rdx
0x180009d35  mov     rbx, rcx
0x180009d38  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009d3c  jnz     short loc_180009D55
0x180009d3e  mov     r8, rdx; void (*)(void *)
0x180009d41  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009d44  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009d4b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009d50  jmp     loc_180009E1D
0x180009d55  mov     qword ptr [rcx], 0
0x180009d5c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009d63  jz      loc_180009E1D
0x180009d69  lea     rcx, stru_18001B150; SRWLock
0x180009d70  call    cs:__imp_AcquireSRWLockExclusive
0x180009d76  cmp     cs:qword_18001B1C0, 0
0x180009d7e  jnz     short loc_180009DFB
0x180009d80  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009d87  mov     cs:qword_18001B1C0, 0
0x180009d92  test    rax, rax
0x180009d95  jnz     short loc_180009DDA
0x180009d97  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009d9e  test    rax, rax
0x180009da1  jnz     short loc_180009DB7
0x180009da3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009daa  call    cs:__imp_GetModuleHandleW
0x180009db0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009db7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180009dbe  mov     rcx, rax; hModule
0x180009dc1  call    cs:__imp_GetProcAddress
0x180009dc7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180009dce  test    rax, rax
0x180009dd1  jnz     short loc_180009DDA
0x180009dd3  mov     eax, 0C0000139h
0x180009dd8  jmp     short loc_180009DF7
0x180009dda  lea     r9, qword_18001B1C0
0x180009de1  xor     r8d, r8d
0x180009de4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009deb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180009df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df7  test    eax, eax
0x180009df9  jnz     short loc_180009E10
0x180009dfb  mov     r9, rdi; void *
0x180009dfe  lea     rcx, CriticalSection; this
0x180009e05  mov     r8, rsi; void (*)(void *)
0x180009e08  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009e0b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180009e10  lea     rcx, stru_18001B150; SRWLock
0x180009e17  call    cs:__imp_ReleaseSRWLockExclusive
0x180009e1d  mov     rbx, [rsp+38h+arg_0]
0x180009e22  mov     rsi, [rsp+38h+arg_8]
0x180009e27  add     rsp, 30h
0x180009e2b  pop     rdi
0x180009e2c  retn
```
