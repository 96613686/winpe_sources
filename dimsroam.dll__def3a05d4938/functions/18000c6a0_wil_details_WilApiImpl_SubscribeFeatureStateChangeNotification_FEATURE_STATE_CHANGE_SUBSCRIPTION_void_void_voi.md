# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000c6a0`
- end: `0x18000c7ad`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000bfec`
- `0x18000c0e8`
- `0x18000c6a0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c797`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c797`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c6f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c6f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c72a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c72a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c741`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c741`

## string_xrefs

- `0x18000c723`: `ntdll.dll`
- `0x18000c737`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_1800130B0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800130B0 = 0;
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
               &qword_1800130B0);
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
0x18000c6a0  mov     [rsp+arg_0], rbx
0x18000c6a5  mov     [rsp+arg_8], rsi
0x18000c6aa  push    rdi
0x18000c6ab  sub     rsp, 30h
0x18000c6af  mov     rdi, r8
0x18000c6b2  mov     rsi, rdx
0x18000c6b5  mov     rbx, rcx
0x18000c6b8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c6bc  jnz     short loc_18000C6D5
0x18000c6be  mov     r8, rdx; void (*)(void *)
0x18000c6c1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c6c4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000c6cb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000c6d0  jmp     loc_18000C79D
0x18000c6d5  mov     qword ptr [rcx], 0
0x18000c6dc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c6e3  jz      loc_18000C79D
0x18000c6e9  lea     rcx, SRWLock; SRWLock
0x18000c6f0  call    cs:__imp_AcquireSRWLockExclusive
0x18000c6f6  cmp     cs:qword_1800130B0, 0
0x18000c6fe  jnz     short loc_18000C77B
0x18000c700  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000c707  mov     cs:qword_1800130B0, 0
0x18000c712  test    rax, rax
0x18000c715  jnz     short loc_18000C75A
0x18000c717  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c71e  test    rax, rax
0x18000c721  jnz     short loc_18000C737
0x18000c723  lea     rcx, ModuleName; "ntdll.dll"
0x18000c72a  call    cs:__imp_GetModuleHandleW
0x18000c730  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c737  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000c73e  mov     rcx, rax; hModule
0x18000c741  call    cs:__imp_GetProcAddress
0x18000c747  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000c74e  test    rax, rax
0x18000c751  jnz     short loc_18000C75A
0x18000c753  mov     eax, 0C0000139h
0x18000c758  jmp     short loc_18000C777
0x18000c75a  lea     r9, qword_1800130B0
0x18000c761  xor     r8d, r8d
0x18000c764  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c76b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000c772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c777  test    eax, eax
0x18000c779  jnz     short loc_18000C790
0x18000c77b  mov     r9, rdi; void *
0x18000c77e  lea     rcx, CriticalSection; this
0x18000c785  mov     r8, rsi; void (*)(void *)
0x18000c788  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000c78b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000c790  lea     rcx, SRWLock; SRWLock
0x18000c797  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c79d  mov     rbx, [rsp+38h+arg_0]
0x18000c7a2  mov     rsi, [rsp+38h+arg_8]
0x18000c7a7  add     rsp, 30h
0x18000c7ab  pop     rdi
0x18000c7ac  retn
```
