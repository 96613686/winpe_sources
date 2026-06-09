# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000cb40`
- end: `0x18000cc4d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c458`
- `0x18000c554`
- `0x18000cb40`
- `0x180017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cc37`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cc37`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cb90`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cb90`
- `KERNEL32!GetModuleHandleW` at `0x18000cbca`
- `KERNEL32!GetModuleHandleW` at `0x18000cbca`
- `KERNEL32!GetProcAddress` at `0x18000cbe1`
- `KERNEL32!GetProcAddress` at `0x18000cbe1`

## string_xrefs

- `0x18000cbc3`: `ntdll.dll`
- `0x18000cbd7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_18001E330 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_18001E330 = 0;
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
               &qword_18001E330);
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
0x18000cb40  mov     [rsp+arg_0], rbx
0x18000cb45  mov     [rsp+arg_8], rsi
0x18000cb4a  push    rdi
0x18000cb4b  sub     rsp, 30h
0x18000cb4f  mov     rdi, r8
0x18000cb52  mov     rsi, rdx
0x18000cb55  mov     rbx, rcx
0x18000cb58  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000cb5c  jnz     short loc_18000CB75
0x18000cb5e  mov     r8, rdx; void (*)(void *)
0x18000cb61  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000cb64  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000cb6b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x18000cb70  jmp     loc_18000CC3D
0x18000cb75  mov     qword ptr [rcx], 0
0x18000cb7c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cb83  jz      loc_18000CC3D
0x18000cb89  lea     rcx, SRWLock; SRWLock
0x18000cb90  call    cs:__imp_AcquireSRWLockExclusive
0x18000cb96  cmp     cs:qword_18001E330, 0
0x18000cb9e  jnz     short loc_18000CC1B
0x18000cba0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000cba7  mov     cs:qword_18001E330, 0
0x18000cbb2  test    rax, rax
0x18000cbb5  jnz     short loc_18000CBFA
0x18000cbb7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cbbe  test    rax, rax
0x18000cbc1  jnz     short loc_18000CBD7
0x18000cbc3  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000cbca  call    cs:__imp_GetModuleHandleW
0x18000cbd0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cbd7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000cbde  mov     rcx, rax; hModule
0x18000cbe1  call    cs:__imp_GetProcAddress
0x18000cbe7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000cbee  test    rax, rax
0x18000cbf1  jnz     short loc_18000CBFA
0x18000cbf3  mov     eax, 0C0000139h
0x18000cbf8  jmp     short loc_18000CC17
0x18000cbfa  lea     r9, qword_18001E330
0x18000cc01  xor     r8d, r8d
0x18000cc04  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cc0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000cc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc17  test    eax, eax
0x18000cc19  jnz     short loc_18000CC30
0x18000cc1b  mov     r9, rdi; void *
0x18000cc1e  lea     rcx, CriticalSection; this
0x18000cc25  mov     r8, rsi; void (*)(void *)
0x18000cc28  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000cc2b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000cc30  lea     rcx, SRWLock; SRWLock
0x18000cc37  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc3d  mov     rbx, [rsp+38h+arg_0]
0x18000cc42  mov     rsi, [rsp+38h+arg_8]
0x18000cc47  add     rsp, 30h
0x18000cc4b  pop     rdi
0x18000cc4c  retn
```
