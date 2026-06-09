# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x140016900`
- end: `0x140016a0d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1400164d0`
- `0x1400165cc`
- `0x140016900`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400169a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400169a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001698a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001698a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016950`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140016950`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400169f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400169f7`

## string_xrefs

- `0x140016983`: `ntdll.dll`
- `0x140016997`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_140027168 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140027168 = 0;
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
               &qword_140027168);
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
0x140016900  mov     [rsp+arg_0], rbx
0x140016905  mov     [rsp+arg_8], rsi
0x14001690a  push    rdi
0x14001690b  sub     rsp, 30h
0x14001690f  mov     rdi, r8
0x140016912  mov     rsi, rdx
0x140016915  mov     rbx, rcx
0x140016918  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14001691c  jnz     short loc_140016935
0x14001691e  mov     r8, rdx; void (*)(void *)
0x140016921  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x140016924  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14001692b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x140016930  jmp     loc_1400169FD
0x140016935  mov     qword ptr [rcx], 0
0x14001693c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140016943  jz      loc_1400169FD
0x140016949  lea     rcx, SRWLock; SRWLock
0x140016950  call    cs:__imp_AcquireSRWLockExclusive
0x140016956  cmp     cs:qword_140027168, 0
0x14001695e  jnz     short loc_1400169DB
0x140016960  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140016967  mov     cs:qword_140027168, 0
0x140016972  test    rax, rax
0x140016975  jnz     short loc_1400169BA
0x140016977  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001697e  test    rax, rax
0x140016981  jnz     short loc_140016997
0x140016983  lea     rcx, ModuleName; "ntdll.dll"
0x14001698a  call    cs:__imp_GetModuleHandleW
0x140016990  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016997  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001699e  mov     rcx, rax; hModule
0x1400169a1  call    cs:__imp_GetProcAddress
0x1400169a7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1400169ae  test    rax, rax
0x1400169b1  jnz     short loc_1400169BA
0x1400169b3  mov     eax, 0C0000139h
0x1400169b8  jmp     short loc_1400169D7
0x1400169ba  lea     r9, qword_140027168
0x1400169c1  xor     r8d, r8d
0x1400169c4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400169cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1400169d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400169d7  test    eax, eax
0x1400169d9  jnz     short loc_1400169F0
0x1400169db  mov     r9, rdi; void *
0x1400169de  lea     rcx, CriticalSection; this
0x1400169e5  mov     r8, rsi; void (*)(void *)
0x1400169e8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1400169eb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1400169f0  lea     rcx, SRWLock; SRWLock
0x1400169f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400169fd  mov     rbx, [rsp+38h+arg_0]
0x140016a02  mov     rsi, [rsp+38h+arg_8]
0x140016a07  add     rsp, 30h
0x140016a0b  pop     rdi
0x140016a0c  retn
```
