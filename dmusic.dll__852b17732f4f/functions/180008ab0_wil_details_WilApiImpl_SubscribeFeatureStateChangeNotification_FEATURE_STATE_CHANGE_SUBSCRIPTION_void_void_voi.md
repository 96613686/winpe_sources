# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180008ab0`
- end: `0x180008bbd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180008324`
- `0x180008420`
- `0x180008ab0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008b51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008ba7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008ba7`

## string_xrefs

- `0x180008b33`: `ntdll.dll`
- `0x180008b47`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18002A060);
      if ( qword_18002A0D0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18002A0D0 = 0;
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
               &qword_18002A0D0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18002A060);
    }
  }
}

```

## disassembly

```asm
0x180008ab0  mov     [rsp+arg_0], rbx
0x180008ab5  mov     [rsp+arg_8], rsi
0x180008aba  push    rdi
0x180008abb  sub     rsp, 30h
0x180008abf  mov     rdi, r8
0x180008ac2  mov     rsi, rdx
0x180008ac5  mov     rbx, rcx
0x180008ac8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180008acc  jnz     short loc_180008AE5
0x180008ace  mov     r8, rdx; void (*)(void *)
0x180008ad1  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008ad4  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008adb  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180008ae0  jmp     loc_180008BAD
0x180008ae5  mov     qword ptr [rcx], 0
0x180008aec  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008af3  jz      loc_180008BAD
0x180008af9  lea     rcx, stru_18002A060; SRWLock
0x180008b00  call    cs:__imp_AcquireSRWLockExclusive
0x180008b06  cmp     cs:qword_18002A0D0, 0
0x180008b0e  jnz     short loc_180008B8B
0x180008b10  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180008b17  mov     cs:qword_18002A0D0, 0
0x180008b22  test    rax, rax
0x180008b25  jnz     short loc_180008B6A
0x180008b27  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008b2e  test    rax, rax
0x180008b31  jnz     short loc_180008B47
0x180008b33  lea     rcx, ModuleName; "ntdll.dll"
0x180008b3a  call    cs:__imp_GetModuleHandleW
0x180008b40  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008b47  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180008b4e  mov     rcx, rax; hModule
0x180008b51  call    cs:__imp_GetProcAddress
0x180008b57  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180008b5e  test    rax, rax
0x180008b61  jnz     short loc_180008B6A
0x180008b63  mov     eax, 0C0000139h
0x180008b68  jmp     short loc_180008B87
0x180008b6a  lea     r9, qword_18002A0D0
0x180008b71  xor     r8d, r8d
0x180008b74  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180008b7b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180008b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b87  test    eax, eax
0x180008b89  jnz     short loc_180008BA0
0x180008b8b  mov     r9, rdi; void *
0x180008b8e  lea     rcx, CriticalSection; this
0x180008b95  mov     r8, rsi; void (*)(void *)
0x180008b98  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180008b9b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180008ba0  lea     rcx, stru_18002A060; SRWLock
0x180008ba7  call    cs:__imp_ReleaseSRWLockExclusive
0x180008bad  mov     rbx, [rsp+38h+arg_0]
0x180008bb2  mov     rsi, [rsp+38h+arg_8]
0x180008bb7  add     rsp, 30h
0x180008bbb  pop     rdi
0x180008bbc  retn
```
