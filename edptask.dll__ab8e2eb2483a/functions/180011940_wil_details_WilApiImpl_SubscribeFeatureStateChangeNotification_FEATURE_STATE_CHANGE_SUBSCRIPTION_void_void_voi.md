# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180011940`
- end: `0x180011a4d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180011498`
- `0x180011594`
- `0x180011940`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800119ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800119ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800119e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800119e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a37`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011990`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011990`

## string_xrefs

- `0x1800119c3`: `ntdll.dll`
- `0x1800119d7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_18001D080);
      if ( qword_18001D0F0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001D0F0 = 0;
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
               &qword_18001D0F0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_18001D080);
    }
  }
}

```

## disassembly

```asm
0x180011940  mov     [rsp+arg_0], rbx
0x180011945  mov     [rsp+arg_8], rsi
0x18001194a  push    rdi
0x18001194b  sub     rsp, 30h
0x18001194f  mov     rdi, r8
0x180011952  mov     rsi, rdx
0x180011955  mov     rbx, rcx
0x180011958  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001195c  jnz     short loc_180011975
0x18001195e  mov     r8, rdx; void (*)(void *)
0x180011961  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011964  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001196b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180011970  jmp     loc_180011A3D
0x180011975  mov     qword ptr [rcx], 0
0x18001197c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011983  jz      loc_180011A3D
0x180011989  lea     rcx, stru_18001D080; SRWLock
0x180011990  call    cs:__imp_AcquireSRWLockExclusive
0x180011996  cmp     cs:qword_18001D0F0, 0
0x18001199e  jnz     short loc_180011A1B
0x1800119a0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800119a7  mov     cs:qword_18001D0F0, 0
0x1800119b2  test    rax, rax
0x1800119b5  jnz     short loc_1800119FA
0x1800119b7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800119be  test    rax, rax
0x1800119c1  jnz     short loc_1800119D7
0x1800119c3  lea     rcx, ModuleName; "ntdll.dll"
0x1800119ca  call    cs:__imp_GetModuleHandleW
0x1800119d0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800119d7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800119de  mov     rcx, rax; hModule
0x1800119e1  call    cs:__imp_GetProcAddress
0x1800119e7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800119ee  test    rax, rax
0x1800119f1  jnz     short loc_1800119FA
0x1800119f3  mov     eax, 0C0000139h
0x1800119f8  jmp     short loc_180011A17
0x1800119fa  lea     r9, qword_18001D0F0
0x180011a01  xor     r8d, r8d
0x180011a04  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011a0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180011a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a17  test    eax, eax
0x180011a19  jnz     short loc_180011A30
0x180011a1b  mov     r9, rdi; void *
0x180011a1e  lea     rcx, CriticalSection; this
0x180011a25  mov     r8, rsi; void (*)(void *)
0x180011a28  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180011a2b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180011a30  lea     rcx, stru_18001D080; SRWLock
0x180011a37  call    cs:__imp_ReleaseSRWLockExclusive
0x180011a3d  mov     rbx, [rsp+38h+arg_0]
0x180011a42  mov     rsi, [rsp+38h+arg_8]
0x180011a47  add     rsp, 30h
0x180011a4b  pop     rdi
0x180011a4c  retn
```
