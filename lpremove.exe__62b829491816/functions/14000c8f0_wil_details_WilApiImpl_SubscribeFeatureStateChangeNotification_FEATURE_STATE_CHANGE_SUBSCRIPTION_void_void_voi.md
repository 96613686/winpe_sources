# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000c8f0`
- end: `0x14000c9fd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000bd58`
- `0x14000be54`
- `0x14000c8f0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c97a`
- `KERNEL32!GetModuleHandleW` at `0x14000c97a`
- `KERNEL32!GetProcAddress` at `0x14000c991`
- `KERNEL32!GetProcAddress` at `0x14000c991`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c940`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c940`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000c9e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000c9e7`

## string_xrefs

- `0x14000c973`: `ntdll.dll`
- `0x14000c987`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_140018128 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140018128 = 0;
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
               &qword_140018128);
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
0x14000c8f0  mov     [rsp+arg_0], rbx
0x14000c8f5  mov     [rsp+arg_8], rsi
0x14000c8fa  push    rdi
0x14000c8fb  sub     rsp, 30h
0x14000c8ff  mov     rdi, r8
0x14000c902  mov     rsi, rdx
0x14000c905  mov     rbx, rcx
0x14000c908  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000c90c  jnz     short loc_14000C925
0x14000c90e  mov     r8, rdx; void (*)(void *)
0x14000c911  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000c914  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000c91b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000c920  jmp     loc_14000C9ED
0x14000c925  mov     qword ptr [rcx], 0
0x14000c92c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000c933  jz      loc_14000C9ED
0x14000c939  lea     rcx, SRWLock; SRWLock
0x14000c940  call    cs:__imp_AcquireSRWLockExclusive
0x14000c946  cmp     cs:qword_140018128, 0
0x14000c94e  jnz     short loc_14000C9CB
0x14000c950  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000c957  mov     cs:qword_140018128, 0
0x14000c962  test    rax, rax
0x14000c965  jnz     short loc_14000C9AA
0x14000c967  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c96e  test    rax, rax
0x14000c971  jnz     short loc_14000C987
0x14000c973  lea     rcx, ModuleName; "ntdll.dll"
0x14000c97a  call    cs:__imp_GetModuleHandleW
0x14000c980  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c987  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c98e  mov     rcx, rax; hModule
0x14000c991  call    cs:__imp_GetProcAddress
0x14000c997  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c99e  test    rax, rax
0x14000c9a1  jnz     short loc_14000C9AA
0x14000c9a3  mov     eax, 0C0000139h
0x14000c9a8  jmp     short loc_14000C9C7
0x14000c9aa  lea     r9, qword_140018128
0x14000c9b1  xor     r8d, r8d
0x14000c9b4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000c9bb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000c9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9c7  test    eax, eax
0x14000c9c9  jnz     short loc_14000C9E0
0x14000c9cb  mov     r9, rdi; void *
0x14000c9ce  lea     rcx, CriticalSection; this
0x14000c9d5  mov     r8, rsi; void (*)(void *)
0x14000c9d8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000c9db  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000c9e0  lea     rcx, SRWLock; SRWLock
0x14000c9e7  call    cs:__imp_ReleaseSRWLockExclusive
0x14000c9ed  mov     rbx, [rsp+38h+arg_0]
0x14000c9f2  mov     rsi, [rsp+38h+arg_8]
0x14000c9f7  add     rsp, 30h
0x14000c9fb  pop     rdi
0x14000c9fc  retn
```
