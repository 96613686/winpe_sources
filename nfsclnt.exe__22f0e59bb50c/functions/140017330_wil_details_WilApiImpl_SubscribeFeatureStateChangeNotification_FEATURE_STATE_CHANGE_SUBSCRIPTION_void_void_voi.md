# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140017330`
- end: `0x14001743d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140016c7c`
- `0x140016d78`
- `0x140017330`
- `0x140019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140017427`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140017427`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140017380`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140017380`
- `KERNEL32!GetProcAddress` at `0x1400173d1`
- `KERNEL32!GetProcAddress` at `0x1400173d1`
- `KERNEL32!GetModuleHandleW` at `0x1400173ba`
- `KERNEL32!GetModuleHandleW` at `0x1400173ba`

## string_xrefs

- `0x1400173b3`: `ntdll.dll`
- `0x1400173c7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_140020170);
      if ( qword_1400201E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1400201E0 = 0;
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
               &qword_1400201E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_140020170);
    }
  }
}

```

## disassembly

```asm
0x140017330  mov     [rsp+arg_0], rbx
0x140017335  mov     [rsp+arg_8], rsi
0x14001733a  push    rdi
0x14001733b  sub     rsp, 30h
0x14001733f  mov     rdi, r8
0x140017342  mov     rsi, rdx
0x140017345  mov     rbx, rcx
0x140017348  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14001734c  jnz     short loc_140017365
0x14001734e  mov     r8, rdx; void (*)(void *)
0x140017351  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140017354  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14001735b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140017360  jmp     loc_14001742D
0x140017365  mov     qword ptr [rcx], 0
0x14001736c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140017373  jz      loc_14001742D
0x140017379  lea     rcx, stru_140020170; SRWLock
0x140017380  call    cs:__imp_AcquireSRWLockExclusive
0x140017386  cmp     cs:qword_1400201E0, 0
0x14001738e  jnz     short loc_14001740B
0x140017390  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140017397  mov     cs:qword_1400201E0, 0
0x1400173a2  test    rax, rax
0x1400173a5  jnz     short loc_1400173EA
0x1400173a7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400173ae  test    rax, rax
0x1400173b1  jnz     short loc_1400173C7
0x1400173b3  lea     rcx, ModuleName; "ntdll.dll"
0x1400173ba  call    cs:__imp_GetModuleHandleW
0x1400173c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400173c7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1400173ce  mov     rcx, rax; hModule
0x1400173d1  call    cs:__imp_GetProcAddress
0x1400173d7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400173de  test    rax, rax
0x1400173e1  jnz     short loc_1400173EA
0x1400173e3  mov     eax, 0C0000139h
0x1400173e8  jmp     short loc_140017407
0x1400173ea  lea     r9, qword_1400201E0
0x1400173f1  xor     r8d, r8d
0x1400173f4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400173fb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x140017402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017407  test    eax, eax
0x140017409  jnz     short loc_140017420
0x14001740b  mov     r9, rdi; void *
0x14001740e  lea     rcx, CriticalSection; this
0x140017415  mov     r8, rsi; void (*)(void *)
0x140017418  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14001741b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x140017420  lea     rcx, stru_140020170; SRWLock
0x140017427  call    cs:__imp_ReleaseSRWLockExclusive
0x14001742d  mov     rbx, [rsp+38h+arg_0]
0x140017432  mov     rsi, [rsp+38h+arg_8]
0x140017437  add     rsp, 30h
0x14001743b  pop     rdi
0x14001743c  retn
```
