# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x1000d080`
- end: `0x1000d216`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YGXPAPAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6GXPAX@Z1@Z`
- size: `406`
- prototype: `void(wil::details *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (__stdcall *)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1000c3c0`
- `0x1000cad0`
- `0x1000d080`
- `0x1000eb60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d0ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d10e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d178`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d0ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d10e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d178`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d12c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d158`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d208`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d12c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d158`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000d1ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1000d1ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000d1a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1000d1a9`

## string_xrefs

- `0x1000d1a4`: `ntdll.dll`
- `0x1000d1b4`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __userpurge wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (__stdcall *a3)(void *),
        void *a4)
{
  PSRWLOCK v4; // edi
  FARPROC RtlRegisterFeatureConfigurationChangeNotification; // edi
  HMODULE ModuleHandleW; // eax
  int v7; // eax

  *this = 0;
  if ( a3 != (void (__stdcall *)(void *))-1 )
  {
    if ( !wil::details::g_featureStateManager )
      return;
    AcquireSRWLockExclusive(&stru_10066160);
    if ( HIDWORD(xmmword_10066190) )
      goto LABEL_21;
    RtlRegisterFeatureConfigurationChangeNotification = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    HIDWORD(xmmword_10066190) = 0;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
      goto LABEL_19;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    RtlRegisterFeatureConfigurationChangeNotification = GetProcAddress(
                                                          ModuleHandleW,
                                                          "RtlRegisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (int)RtlRegisterFeatureConfigurationChangeNotification;
    if ( RtlRegisterFeatureConfigurationChangeNotification )
LABEL_19:
      v7 = ((int (__thiscall *)(FARPROC, _DWORD (__stdcall *)(void *), void *, _DWORD, char *))RtlRegisterFeatureConfigurationChangeNotification)(
             RtlRegisterFeatureConfigurationChangeNotification,
             _lambda_916099de8e98bbd3652c02d0a4306512_::_lambda_invoker_stdcall_,
             &wil::details::g_featureStateManager,
             0,
             (char *)&xmmword_10066190 + 12);
    else
      v7 = -1073741511;
    if ( !v7 )
LABEL_21:
      wil::details_abi::SubscriptionList::SubscribeUnderLock(
        (wil::details_abi::SubscriptionList *)&CriticalSection,
        this,
        (void (__stdcall *)(void *))a2,
        a3);
    goto LABEL_22;
  }
  if ( wil::details::g_featureStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress
     || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(wil::details::g_pfnDllShutdownInProgress))
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    AcquireSRWLockExclusive(&stru_10066160);
    if ( !DWORD2(xmmword_100661C0) )
    {
      v4 = SRWLock;
      if ( SRWLock )
      {
        DWORD2(xmmword_100661C0) = 0;
        AcquireSRWLockExclusive(SRWLock);
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&v4[28],
          (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)&xmmword_100661C0 + 2,
          (void (__stdcall *)(void *))_lambda_77c69ec77c2e182bbb26fd2c4014c4e3_::_lambda_invoker_stdcall_,
          &wil::details::g_featureStateManager);
        ReleaseSRWLockExclusive(v4);
      }
    }
    wil::details_abi::SubscriptionList::SubscribeUnderLock(
      (wil::details_abi::SubscriptionList *)&stru_100661A0,
      this,
      (void (__stdcall *)(void *))a2,
      0);
    if ( *this )
    {
      *this = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((unsigned int)*this | 0x80000000);
      ReleaseSRWLockExclusive(&stru_10066160);
      return;
    }
LABEL_22:
    ReleaseSRWLockExclusive(&stru_10066160);
  }
}

```

## disassembly

```asm
0x1000d080  mov     edi, edi
0x1000d082  push    ebp
0x1000d083  mov     ebp, esp
0x1000d085  and     esp, 0FFFFFFF8h
0x1000d088  cmp     [ebp+arg_8], 0FFFFFFFFh
0x1000d08c  push    esi; unsigned int
0x1000d08d  mov     esi, [ebp+arg_0]
0x1000d090  push    edi; void *
0x1000d091  mov     dword ptr [esi], 0
0x1000d097  jnz     loc_1000D166
0x1000d09d  cmp     ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1000d0a4  jz      loc_1000D20E
0x1000d0aa  cmp     ?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1000d0b1  jnz     loc_1000D20E
0x1000d0b7  mov     edi, ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x1000d0bd  test    edi, edi
0x1000d0bf  jz      short loc_1000D0D3
0x1000d0c1  mov     ecx, edi
0x1000d0c3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d0c9  call    edi ; ?g_pfnDllShutdownInProgress@details@wil@@3P6GEX_EA
0x1000d0cb  test    al, al
0x1000d0cd  jnz     loc_1000D20E
0x1000d0d3  mov     ecx, offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1000d0d8  call    ?EnsureStateData@FeatureStateManager@details@wil@@AAE_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1000d0dd  test    al, al
0x1000d0df  jz      loc_1000D20E
0x1000d0e5  push    offset stru_10066160; SRWLock
0x1000d0ea  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d0f0  cmp     dword ptr xmmword_100661C0+8, 0
0x1000d0f7  jnz     short loc_1000D132
0x1000d0f9  mov     edi, SRWLock
0x1000d0ff  test    edi, edi
0x1000d101  jz      short loc_1000D132
0x1000d103  push    edi; SRWLock
0x1000d104  mov     dword ptr xmmword_100661C0+8, 0
0x1000d10e  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d114  push    offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; void *
0x1000d119  push    offset ?_lambda_invoker_stdcall_@_lambda_77c69ec77c2e182bbb26fd2c4014c4e3_@@CG@PAX@Z; void (__stdcall *)(void *)
0x1000d11e  push    (offset xmmword_100661C0+8); struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1000d123  lea     ecx, [edi+70h]; this
0x1000d126  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QAEXPAPAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6GXPAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1000d12b  push    edi; SRWLock
0x1000d12c  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d132  push    0; void *
0x1000d134  push    [ebp+arg_4]; void (__stdcall *)(void *)
0x1000d137  mov     ecx, offset stru_100661A0; this
0x1000d13c  push    esi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1000d13d  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QAEXPAPAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6GXPAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1000d142  mov     eax, [esi]
0x1000d144  test    eax, eax
0x1000d146  jz      loc_1000D203
0x1000d14c  or      eax, 80000000h
0x1000d151  push    offset stru_10066160; SRWLock
0x1000d156  mov     [esi], eax
0x1000d158  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d15e  pop     edi
0x1000d15f  pop     esi
0x1000d160  mov     esp, ebp
0x1000d162  pop     ebp
0x1000d163  retn    0Ch
0x1000d166  cmp     ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1000d16d  jz      loc_1000D20E
0x1000d173  push    offset stru_10066160; SRWLock
0x1000d178  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d17e  cmp     dword ptr xmmword_10066190+0Ch, 0
0x1000d185  jnz     short loc_1000D1F2
0x1000d187  mov     edi, _g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1000d18d  mov     dword ptr xmmword_10066190+0Ch, 0
0x1000d197  test    edi, edi
0x1000d199  jnz     short loc_1000D1D3
0x1000d19b  mov     eax, ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000d1a0  test    eax, eax
0x1000d1a2  jnz     short loc_1000D1B4
0x1000d1a4  push    offset ModuleName; "ntdll.dll"
0x1000d1a9  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x1000d1af  mov     ?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YGPAUHINSTANCE__@@XZ@4PAU2@A, eax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1000d1b4  push    offset aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1000d1b9  push    eax; hModule
0x1000d1ba  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1000d1c0  mov     edi, eax
0x1000d1c2  mov     _g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, edi
0x1000d1c8  test    edi, edi
0x1000d1ca  jnz     short loc_1000D1D3
0x1000d1cc  mov     eax, 0C0000139h
0x1000d1d1  jmp     short loc_1000D1EE
0x1000d1d3  push    (offset xmmword_10066190+0Ch)
0x1000d1d8  push    0
0x1000d1da  push    offset ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; unsigned int
0x1000d1df  push    offset ?_lambda_invoker_stdcall_@_lambda_916099de8e98bbd3652c02d0a4306512_@@CG@PAX@Z; void *
0x1000d1e4  mov     ecx, edi
0x1000d1e6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d1ec  call    edi ; _g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1000d1ee  test    eax, eax
0x1000d1f0  jnz     short loc_1000D203
0x1000d1f2  push    [ebp+arg_8]; void *
0x1000d1f5  mov     ecx, offset CriticalSection; this
0x1000d1fa  push    [ebp+arg_4]; void (__stdcall *)(void *)
0x1000d1fd  push    esi; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1000d1fe  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QAEXPAPAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6GXPAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1000d203  push    offset stru_10066160; SRWLock
0x1000d208  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d20e  pop     edi
0x1000d20f  pop     esi
0x1000d210  mov     esp, ebp
0x1000d212  pop     ebp
0x1000d213  retn    0Ch
```
