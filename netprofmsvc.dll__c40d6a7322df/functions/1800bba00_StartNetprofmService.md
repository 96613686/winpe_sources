# StartNetprofmService

- ea: `0x1800bba00`
- end: `0x1800bbc45`
- name: `StartNetprofmService`
- size: `581`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009e910`

## callees

- `0x180015628`
- `0x180043488`
- `0x180043e80`
- `0x180048608`
- `0x180053988`
- `0x18005530c`
- `0x1800704dc`
- `0x18008c08c`
- `0x18009ac74`
- `0x1800a13e8`
- `0x1800a8dac`
- `0x1800b5968`
- `0x1800bb244`
- `0x1800bb288`
- `0x1800bba00`
- `0x1800bbfdc`
- `0x1800bc3b8`
- `0x1800cb538`
- `0x1800fd4f4`
- `0x18012146c`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bbb53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800bbb53`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800bbbd1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800bbbd1`
- `combase!__imp_CoGetSharedServiceId` at `0x1800bba96`
- `combase!__imp_CoGetSharedServiceId` at `0x1800bba96`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800bba65`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800bba65`

## string_xrefs

- `0x1800bba46`: `onecore\net\netprofiles\service\src\host\dll\servicemain.cpp`
- `0x1800bbc25`: `onecore\net\netprofiles\service\src\host\dll\servicemain.cpp`
- `0x1800bbaaa`: `onecore\net\netprofiles\service\src\common\module.cpp`

## pseudocode

```c
int __fastcall StartNetprofmService(__int64 a1)
{
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // edi
  __int64 v2; // rdx
  __int64 v4; // rcx
  NetworkProfileServiceModule *v5; // rsi
  int SharedServiceId; // eax
  __int64 v7; // rcx
  _DWORD *v8; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  DeadlockMonitor *v10; // rdx
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(HANDLE *, const wchar_t *, HANDLE, void (__fastcall *)(void *, unsigned __int8)); // r15
  HANDLE v13; // rsi
  HANDLE v14; // rdi
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF

  if ( (unsigned int)dword_1801BD288 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      a1,
      &byte_18018C3DF);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&qword_1801C7B40, 1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v2 = 233;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\dll\\servicemain.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v16);
    return event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = CoRegisterServerShutdownDelay(qword_1801C7B40, 30000);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v2 = 237;
    goto LABEL_5;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = InitGlobalResources();
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v2 = 239;
    goto LABEL_5;
  }
  v5 = (NetworkProfileServiceModule *)Microsoft::WRL::Details::OutOfProcModuleBase<NetworkProfileServiceModule>::Create(v4);
  SharedServiceId = CoGetSharedServiceId((char *)v5 + 24);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = SharedServiceId;
  if ( SharedServiceId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\module.cpp",
      (const char *)(unsigned int)SharedServiceId,
      v16);
    v2 = 243;
    goto LABEL_5;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = NetworkProfileServiceModule::RegisterClassObjects(v5);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v2 = 244;
    goto LABEL_5;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = StartNspRpc();
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v2 = 246;
    goto LABEL_5;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = StartNetworkProfilesTelemetryRpc(v7);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v2 = 247;
    goto LABEL_5;
  }
  StartLANIdsMgr();
  UpdateServiceStatus(4);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_DeadlockMonitor>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_DeadlockMonitor>::GetImpl'::`2'::impl) )
  {
    try
    {
      v8 = operator new(0x10u);
      *(_QWORD *)v8 = 0;
      v8[2] = 0;
      v8[3] = 0;
      ThreadpoolTimer = CreateThreadpoolTimer(DeadlockMonitor::PeriodicTimerCallback, v8, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v8,
        ThreadpoolTimer);
      v18 = 0;
      v10 = qword_1801C8568;
      qword_1801C8568 = (DeadlockMonitor *)v8;
      if ( v10 )
        std::default_delete<DeadlockMonitor>::operator()();
      std::unique_ptr<DeadlockMonitor>::~unique_ptr<DeadlockMonitor>(&v18);
      DeadlockMonitor::StartMonitoring(qword_1801C8568);
    }
    catch ( std::bad_alloc )
    {
      if ( (unsigned int)dword_1801BD288 > 4 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v11,
          &byte_18018C3AF);
    }
  }
  v12 = *(__int64 (__fastcall **)(HANDLE *, const wchar_t *, HANDLE, void (__fastcall *)(void *, unsigned __int8)))(qword_1801C7E28 + 208);
  v13 = qword_1801C7B40;
  v14 = WaitHandle;
  if ( WaitHandle )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v18);
    UnregisterWait(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v18);
  }
  WaitHandle = 0;
  v15 = v12(&WaitHandle, L"netprofm", v13, ServiceStopCallback);
  if ( v15 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x10E,
             (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\dll\\servicemain.cpp",
             (const char *)v15,
             0);
  else
    return 0;
}

```

## disassembly

```asm
0x1800bba00  push    rsi
0x1800bba02  push    rdi
0x1800bba03  push    r14
0x1800bba05  push    r15
0x1800bba07  sub     rsp, 48h
0x1800bba0b  mov     eax, cs:dword_1801BD288
0x1800bba11  cmp     eax, 4
0x1800bba14  jbe     short loc_1800BBA22
0x1800bba16  lea     rdx, byte_18018C3DF
0x1800bba1d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800bba22  mov     edx, 1
0x1800bba27  lea     rcx, qword_1801C7B40
0x1800bba2e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800bba33  mov     edi, eax
0x1800bba35  test    eax, eax
0x1800bba37  jns     short loc_1800BBA59
0x1800bba39  mov     edx, 0E9h; void *
0x1800bba3e  mov     rcx, [rsp+68h]; this
0x1800bba43  mov     r9d, edi; char *
0x1800bba46  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x1800bba4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bba52  mov     eax, edi
0x1800bba54  jmp     loc_1800BBC3A
0x1800bba59  mov     edx, 7530h
0x1800bba5e  mov     rcx, cs:qword_1801C7B40
0x1800bba65  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800bba6b  mov     edi, eax
0x1800bba6d  test    eax, eax
0x1800bba6f  jns     short loc_1800BBA78
0x1800bba71  mov     edx, 0EDh
0x1800bba76  jmp     short loc_1800BBA3E
0x1800bba78  call    ?InitGlobalResources@@YAJXZ; InitGlobalResources(void)
0x1800bba7d  mov     edi, eax
0x1800bba7f  test    eax, eax
0x1800bba81  jns     short loc_1800BBA8A
0x1800bba83  mov     edx, 0EFh
0x1800bba88  jmp     short loc_1800BBA3E
0x1800bba8a  call    ?Create@?$OutOfProcModuleBase@VNetworkProfileServiceModule@@@Details@WRL@Microsoft@@SAAEAVNetworkProfileServiceModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<NetworkProfileServiceModule>::Create(void)
0x1800bba8f  mov     rsi, rax
0x1800bba92  lea     rcx, [rax+18h]
0x1800bba96  call    cs:__imp_CoGetSharedServiceId
0x1800bba9c  mov     edi, eax
0x1800bba9e  test    eax, eax
0x1800bbaa0  jns     short loc_1800BBAC5
0x1800bbaa2  mov     rcx, [rsp+68h]; this
0x1800bbaa7  mov     r9d, eax; char *
0x1800bbaaa  lea     r8, aOnecoreNetNetp_27; "onecore\\net\\netprofiles\\service\\src"...
0x1800bbab1  mov     edx, 26h ; '&'; void *
0x1800bbab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbabb  mov     edx, 0F3h
0x1800bbac0  jmp     loc_1800BBA3E
0x1800bbac5  mov     rcx, rsi; this
0x1800bbac8  call    ?RegisterClassObjects@NetworkProfileServiceModule@@QEAAJXZ; NetworkProfileServiceModule::RegisterClassObjects(void)
0x1800bbacd  mov     edi, eax
0x1800bbacf  test    eax, eax
0x1800bbad1  jns     short loc_1800BBADD
0x1800bbad3  mov     edx, 0F4h
0x1800bbad8  jmp     loc_1800BBA3E
0x1800bbadd  call    ?StartNspRpc@@YAJXZ; StartNspRpc(void)
0x1800bbae2  mov     edi, eax
0x1800bbae4  test    eax, eax
0x1800bbae6  jns     short loc_1800BBAF2
0x1800bbae8  mov     edx, 0F6h
0x1800bbaed  jmp     loc_1800BBA3E
0x1800bbaf2  call    ?StartNetworkProfilesTelemetryRpc@@YAJXZ; StartNetworkProfilesTelemetryRpc(void)
0x1800bbaf7  mov     edi, eax
0x1800bbaf9  test    eax, eax
0x1800bbafb  jns     short loc_1800BBB07
0x1800bbafd  mov     edx, 0F7h
0x1800bbb02  jmp     loc_1800BBA3E
0x1800bbb07  call    ?StartLANIdsMgr@@YAXXZ; StartLANIdsMgr(void)
0x1800bbb0c  xor     edx, edx
0x1800bbb0e  lea     ecx, [rdx+4]
0x1800bbb11  call    UpdateServiceStatus
0x1800bbb16  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_DeadlockMonitor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_DeadlockMonitor@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_DeadlockMonitor> `wil::Feature<__WilFeatureTraits_Feature_NLM_DeadlockMonitor>::GetImpl(void)'::`2'::impl
0x1800bbb1d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_DeadlockMonitor@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_DeadlockMonitor>::__private_IsEnabled(void)
0x1800bbb22  test    al, al
0x1800bbb24  jz      short loc_1800BBB9C
0x1800bbb26  mov     ecx, 10h; Size
0x1800bbb2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bbb30  mov     rdi, rax
0x1800bbb33  mov     qword ptr [rax], 0
0x1800bbb3a  mov     dword ptr [rax+8], 0
0x1800bbb41  xor     eax, eax
0x1800bbb43  mov     [rdi+0Ch], eax
0x1800bbb46  xor     r8d, r8d; pcbe
0x1800bbb49  mov     rdx, rdi; pv
0x1800bbb4c  lea     rcx, ?PeriodicTimerCallback@DeadlockMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800bbb53  call    cs:__imp_CreateThreadpoolTimer
0x1800bbb59  mov     rdx, rax
0x1800bbb5c  mov     rcx, rdi
0x1800bbb5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800bbb64  mov     [rsp+68h+arg_0], 0
0x1800bbb6d  mov     rdx, cs:qword_1801C8568
0x1800bbb74  mov     cs:qword_1801C8568, rdi
0x1800bbb7b  test    rdx, rdx
0x1800bbb7e  jz      short loc_1800BBB85
0x1800bbb80  call    ??R?$default_delete@VDeadlockMonitor@@@std@@QEBAXPEAVDeadlockMonitor@@@Z; std::default_delete<DeadlockMonitor>::operator()(DeadlockMonitor *)
0x1800bbb85  lea     rcx, [rsp+68h+arg_0]
0x1800bbb8a  call    ??1?$unique_ptr@VDeadlockMonitor@@U?$default_delete@VDeadlockMonitor@@@std@@@std@@QEAA@XZ; std::unique_ptr<DeadlockMonitor>::~unique_ptr<DeadlockMonitor>(void)
0x1800bbb8f  mov     rcx, cs:qword_1801C8568; this
0x1800bbb96  call    ?StartMonitoring@DeadlockMonitor@@QEAAXXZ; DeadlockMonitor::StartMonitoring(void)
0x1800bbb9b  nop
0x1800bbb9c  mov     rax, cs:qword_1801C7E28
0x1800bbba3  mov     r15, [rax+0D0h]
0x1800bbbaa  mov     rsi, cs:qword_1801C7B40
0x1800bbbb1  mov     r14, cs:lpString2
0x1800bbbb8  mov     rdi, cs:WaitHandle
0x1800bbbbf  test    rdi, rdi
0x1800bbbc2  jz      short loc_1800BBBE1
0x1800bbbc4  lea     rcx, [rsp+68h+arg_0]; this
0x1800bbbc9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800bbbce  mov     rcx, rdi; WaitHandle
0x1800bbbd1  call    cs:__imp_UnregisterWait
0x1800bbbd7  lea     rcx, [rsp+68h+arg_0]; this
0x1800bbbdc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800bbbe1  mov     cs:WaitHandle, 0
0x1800bbbec  mov     [rsp+68h+var_40], 8
0x1800bbbf4  mov     qword ptr [rsp+68h+var_48], 0; unsigned int
0x1800bbbfd  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x1800bbc04  mov     r8, rsi
0x1800bbc07  mov     rdx, r14
0x1800bbc0a  lea     rcx, WaitHandle
0x1800bbc11  mov     rax, r15
0x1800bbc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc19  test    eax, eax
0x1800bbc1b  jz      short loc_1800BBC38
0x1800bbc1d  mov     rcx, [rsp+68h]; this
0x1800bbc22  mov     r9d, eax; char *
0x1800bbc25  lea     r8, aOnecoreNetNetp_5; "onecore\\net\\netprofiles\\service\\src"...
0x1800bbc2c  mov     edx, 10Eh; void *
0x1800bbc31  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800bbc36  jmp     short loc_1800BBC3A
0x1800bbc38  xor     eax, eax
0x1800bbc3a  add     rsp, 48h
0x1800bbc3e  pop     r15
0x1800bbc40  pop     r14
0x1800bbc42  pop     rdi
0x1800bbc43  pop     rsi
0x1800bbc44  retn
```
