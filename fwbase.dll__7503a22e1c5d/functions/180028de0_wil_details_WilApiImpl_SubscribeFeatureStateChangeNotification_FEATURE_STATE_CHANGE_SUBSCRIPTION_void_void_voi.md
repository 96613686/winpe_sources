# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180028de0`
- end: `0x180028fb3`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `467`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800238e0`
- `0x180028330`
- `0x180028de0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028f47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028f47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028f30`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180028f30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028e57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028e81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028ef6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028e57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028e81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028ef6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028eab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028f9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028eab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028f9d`

## string_xrefs

- `0x180028f29`: `ntdll.dll`
- `0x180028f3d`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  PSRWLOCK v7; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // eax

  *this = 0;
  if ( a3 != (void (*)(void *))-1LL )
  {
    if ( !wil::details::g_featureStateManager )
      return;
    AcquireSRWLockExclusive(&stru_18003C030);
    if ( qword_18003C0A0 )
      goto LABEL_21;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    qword_18003C0A0 = 0;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
      goto LABEL_19;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_19:
      v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
              _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
              &wil::details::g_featureStateManager,
              0,
              &qword_18003C0A0);
    else
      v10 = -1073741511;
    if ( !v10 )
LABEL_21:
      wil::details_abi::SubscriptionList::SubscribeUnderLock(
        (wil::details_abi::SubscriptionList *)&CriticalSection,
        this,
        (void (*)(void *))a2,
        a3);
    goto LABEL_22;
  }
  if ( wil::details::g_featureStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress
     || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this, a2, -1, a4))
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    AcquireSRWLockExclusive(&stru_18003C030);
    if ( !xmmword_18003C0F0 )
    {
      v7 = qword_18003C028;
      if ( qword_18003C028 )
      {
        xmmword_18003C0F0 = 0;
        AcquireSRWLockExclusive(qword_18003C028);
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&v7[25],
          &xmmword_18003C0F0,
          (void (*)(void *))_lambda_152aa9d2a3a0648fa2fa7fcef514b376_::_lambda_invoker_cdecl_,
          &wil::details::g_featureStateManager);
        ReleaseSRWLockExclusive(v7);
      }
    }
    wil::details_abi::SubscriptionList::SubscribeUnderLock(
      (wil::details_abi::SubscriptionList *)&stru_18003C0A8,
      this,
      (void (*)(void *))a2,
      0);
    if ( *this )
      *this = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((unsigned __int64)*this | 0x80000000);
LABEL_22:
    ReleaseSRWLockExclusive(&stru_18003C030);
  }
}

```

## disassembly

```asm
0x180028de0  mov     [rsp+arg_8], rbx
0x180028de5  mov     [rsp+arg_10], rsi
0x180028dea  push    rdi
0x180028deb  sub     rsp, 30h
0x180028def  mov     qword ptr [rcx], 0
0x180028df6  mov     rdi, r8
0x180028df9  mov     rsi, rdx
0x180028dfc  mov     rbx, rcx
0x180028dff  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180028e03  jnz     loc_180028EE2
0x180028e09  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180028e10  jz      loc_180028FA3
0x180028e16  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180028e1d  jnz     loc_180028FA3
0x180028e23  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180028e2a  test    rax, rax
0x180028e2d  jz      short loc_180028E3C
0x180028e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e34  test    al, al
0x180028e36  jnz     loc_180028FA3
0x180028e3c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180028e43  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180028e48  test    al, al
0x180028e4a  jz      loc_180028FA3
0x180028e50  lea     rcx, stru_18003C030; SRWLock
0x180028e57  call    cs:__imp_AcquireSRWLockExclusive
0x180028e5d  cmp     qword ptr cs:xmmword_18003C0F0, 0
0x180028e65  jnz     short loc_180028EB1
0x180028e67  mov     rdi, cs:qword_18003C028
0x180028e6e  test    rdi, rdi
0x180028e71  jz      short loc_180028EB1
0x180028e73  mov     rcx, rdi; SRWLock
0x180028e76  mov     qword ptr cs:xmmword_18003C0F0, 0
0x180028e81  call    cs:__imp_AcquireSRWLockExclusive
0x180028e87  lea     rcx, [rdi+0C8h]; this
0x180028e8e  lea     r9, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; void *
0x180028e95  lea     r8, ?_lambda_invoker_cdecl_@_lambda_152aa9d2a3a0648fa2fa7fcef514b376_@@CA@PEAX@Z; void (*)(void *)
0x180028e9c  lea     rdx, xmmword_18003C0F0; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180028ea3  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180028ea8  mov     rcx, rdi; SRWLock
0x180028eab  call    cs:__imp_ReleaseSRWLockExclusive
0x180028eb1  xor     r9d, r9d; void *
0x180028eb4  lea     rcx, stru_18003C0A8; this
0x180028ebb  mov     r8, rsi; void (*)(void *)
0x180028ebe  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180028ec1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180028ec6  mov     rax, [rbx]
0x180028ec9  test    rax, rax
0x180028ecc  jz      loc_180028F96
0x180028ed2  mov     ecx, 80000000h
0x180028ed7  or      rax, rcx
0x180028eda  mov     [rbx], rax
0x180028edd  jmp     loc_180028F96
0x180028ee2  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180028ee9  jz      loc_180028FA3
0x180028eef  lea     rcx, stru_18003C030; SRWLock
0x180028ef6  call    cs:__imp_AcquireSRWLockExclusive
0x180028efc  cmp     cs:qword_18003C0A0, 0
0x180028f04  jnz     short loc_180028F81
0x180028f06  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180028f0d  mov     cs:qword_18003C0A0, 0
0x180028f18  test    rax, rax
0x180028f1b  jnz     short loc_180028F60
0x180028f1d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028f24  test    rax, rax
0x180028f27  jnz     short loc_180028F3D
0x180028f29  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180028f30  call    cs:__imp_GetModuleHandleW
0x180028f36  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180028f3d  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180028f44  mov     rcx, rax; hModule
0x180028f47  call    cs:__imp_GetProcAddress
0x180028f4d  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180028f54  test    rax, rax
0x180028f57  jnz     short loc_180028F60
0x180028f59  mov     eax, 0C0000139h
0x180028f5e  jmp     short loc_180028F7D
0x180028f60  lea     r9, qword_18003C0A0
0x180028f67  xor     r8d, r8d
0x180028f6a  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180028f71  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180028f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f7d  test    eax, eax
0x180028f7f  jnz     short loc_180028F96
0x180028f81  mov     r9, rdi; void *
0x180028f84  lea     rcx, CriticalSection; this
0x180028f8b  mov     r8, rsi; void (*)(void *)
0x180028f8e  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180028f91  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180028f96  lea     rcx, stru_18003C030; SRWLock
0x180028f9d  call    cs:__imp_ReleaseSRWLockExclusive
0x180028fa3  mov     rbx, [rsp+38h+arg_8]
0x180028fa8  mov     rsi, [rsp+38h+arg_10]
0x180028fad  add     rsp, 30h
0x180028fb1  pop     rdi
0x180028fb2  retn
```
