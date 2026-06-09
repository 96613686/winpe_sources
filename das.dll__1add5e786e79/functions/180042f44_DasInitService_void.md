# DasInitService(void)

- ea: `0x180042f44`
- end: `0x1800436dd`
- name: `?DasInitService@@YAXXZ`
- size: `1945`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040430`

## callees

- `0x180005770`
- `0x180007500`
- `0x1800153e0`
- `0x180021830`
- `0x18002c700`
- `0x180033c70`
- `0x180036494`
- `0x1800364cc`
- `0x180036b18`
- `0x1800387a4`
- `0x18003c9f8`
- `0x180042ea8`
- `0x180042f44`
- `0x1800436e4`
- `0x180044b7c`
- `0x180044ce8`
- `0x180044d64`
- `0x180044d90`
- `0x180044dbc`
- `0x180044de8`
- `0x180044e14`
- `0x180044f78`
- `0x180046420`
- `0x1800486fc`
- `0x18004a280`
- `0x18004a5cc`
- `0x18004b0cc`
- `0x18004d1f0`
- `0x180060a3c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800434a0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800434a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800430ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800430ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004309a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004309a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004344b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004344b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180043060`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180043060`

## string_xrefs

- `0x180043059`: `DeviceAssociationService`
- `0x180043625`: `DeviceAssociationService`

## pseudocode

```c
void DasInitService(void)
{
  int v0; // edx
  __int64 v1; // rcx
  int v2; // r8d
  struct DAS::DevnodeManagment::DevnodeManager *v3; // rbx
  __int64 v4; // rcx
  int v5; // edx
  int v6; // r8d
  DAS::Dispatcher *v7; // rcx
  signed int LastError; // eax
  _BYTE *v9; // rdx
  int v10; // r8d
  const char *v11; // r9
  PSRWLOCK v12; // rbx
  struct SERVICE_STATUS_HANDLE__ *v13; // rcx
  signed int v14; // eax
  struct DAS::DevnodeManagment::DevnodeManager *v15; // rbx
  __int64 v16; // rcx
  PSRWLOCK v17; // rbx
  int Store; // eax
  int v19; // eax
  int v20; // edx
  struct SERVICE_STATUS_HANDLE__ *v21; // rcx
  int v22; // r8d
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // rcx
  unsigned __int16 *v25; // r8
  int started; // eax
  __int64 v27; // rcx
  int v28; // r9d
  int v29; // edx
  struct SERVICE_STATUS_HANDLE__ *v30; // rcx
  int v31; // r8d
  __int64 v32; // rcx
  struct SERVICE_STATUS_HANDLE__ *v33; // rcx
  struct SERVICE_STATUS_HANDLE__ *v34; // rcx
  int v35; // edx
  int v36; // r8d
  struct SERVICE_STATUS_HANDLE__ *v37; // rcx
  struct SERVICE_STATUS_HANDLE__ *v38; // rcx
  int v39; // edx
  int v40; // r8d
  int v41; // edx
  struct SERVICE_STATUS_HANDLE__ *v42; // rcx
  int v43; // r8d
  struct SERVICE_STATUS_HANDLE__ *v44; // rcx
  int v45; // edx
  struct SERVICE_STATUS_HANDLE__ *v46; // rcx
  int v47; // r8d
  struct SERVICE_STATUS_HANDLE__ *v48; // rcx
  void (__fastcall *v49)(HANDLE *, const WCHAR *, wil::details *, void (__fastcall *)(void *, unsigned __int8), _QWORD, int); // rdi
  wil::details *v50; // rbx
  __int64 v51; // rcx
  struct SERVICE_STATUS_HANDLE__ *v52; // rcx
  _BYTE v53[32]; // [rsp+0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  struct DAS::DevnodeManagment::DevnodeManager *v55; // [rsp+70h] [rbp+8h] BYREF

  McGenEventRegister_EventRegister();
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*((_QWORD *)WPP_GLOBAL_Control + 5), v0, v2, 66, &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  _InterlockedExchange64((volatile __int64 *)&g_ServiceControlFlags, 0);
  g_bDasStopping = 0;
  g_DasStopTimer = 0;
  g_DasCurrentState = 2;
  g_hDasStatus = 0;
  std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>::reset(v1, 0);
  Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&g_AepStore);
  Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&g_AppStore);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v3 = (struct DAS::DevnodeManagment::DevnodeManager *)operator new(0x18u);
    v55 = v3;
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 2) = 0;
    std::_Tree<std::_Tmap_traits<unsigned long,_SYSTEMTIME,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SYSTEMTIME>>,0>>::_Alloc_sentinel_and_proxy();
    v55 = 0;
    std::unique_ptr<DAS::Dispatcher::Watchdog>::reset(v4, v3);
    std::unique_ptr<DAS::Dispatcher::Watchdog>::~unique_ptr<DAS::Dispatcher::Watchdog>(&v55);
    if ( *(_DWORD *)g_DasStartedSubsystems && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v5,
        v6,
        67,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        g_DasStartedSubsystems[0]);
    *(_DWORD *)g_DasStartedSubsystems = 0;
    g_hDasStatus = RegisterServiceCtrlHandlerExW(L"DeviceAssociationService", DasControlHandlerEx, 0);
    if ( !g_hDasStatus )
    {
      LastError = GetLastError();
      LODWORD(v12) = LastError;
      if ( LastError > 0 )
        LODWORD(v12) = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_15;
    }
    DAS::Dispatcher::InitializeDispatchServices(v7);
    g_DasStopTimer = CreateThreadpoolTimer(DasStopTimerCallback, 0, 0);
    if ( !g_DasStopTimer )
    {
      v14 = GetLastError();
      LODWORD(v12) = v14;
      if ( v14 > 0 )
        LODWORD(v12) = (unsigned __int16)v14 | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v9,
          v10,
          68,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
          (char)v12);
LABEL_15:
      if ( (int)v12 >= 0 )
      {
LABEL_75:
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (int)v9,
            v10,
            93,
            &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
        return;
      }
      goto LABEL_71;
    }
    DasStatusUpdate(v13, 2u, 0, 0);
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      v15 = (struct DAS::DevnodeManagment::DevnodeManager *)operator new(0x18u);
      v55 = v15;
      *(_QWORD *)v15 = 0;
      *((_QWORD *)v15 + 1) = 0;
      *((_QWORD *)v15 + 2) = 0;
      std::_Tree<std::_Tmap_traits<unsigned long,_SYSTEMTIME,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_SYSTEMTIME>>,0>>::_Alloc_sentinel_and_proxy();
      v55 = 0;
      std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>::reset(v16, v15);
      std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>::~unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>(&v55);
      v17 = g_StoreManager;
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&g_AepStore);
      Store = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(v17, 7, g_hDasStatus, &g_AepStore);
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v9 = v53;
        LODWORD(v55) = -2147024882;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            (int)v53,
            v10,
            69,
            &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
            14);
        LOBYTE(v12) = (_BYTE)v55;
        __eh34_try_continuation(1, &std::bad_alloc `RTTI Type Descriptor', &loc_180043653);
        goto LABEL_71;
      }
    }
    LOBYTE(v12) = Store;
    if ( Store < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v9,
          v10,
          70,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
          Store);
      goto LABEL_71;
    }
    v12 = g_StoreManager;
    Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&g_AppStore);
    v19 = Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(v12, 9, g_hDasStatus, &g_AppStore);
    LOBYTE(v12) = v19;
    if ( v19 < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v20,
          v22,
          71,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
          v19);
      Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(&g_AppStore);
      goto LABEL_71;
    }
    *(_DWORD *)g_DasStartedSubsystems |= 0x20u;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v20,
        v22,
        72,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    DasStatusUpdate(v21, 2u, 1u, 0);
    v55 = 0;
    started = DAS::DevnodeManagment::DevnodeManager::MakeAndInitialize(v24, v23, v25, (PVOID **)&v55);
    LOBYTE(v12) = started;
    if ( started >= 0 )
    {
      std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::reset(v27, v55);
      *(_DWORD *)g_DasStartedSubsystems |= 0x10u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v29,
          v31,
          74,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
      DasStatusUpdate(v30, 2u, 2u, 0);
      v55 = 0;
      started = DAS::ProviderManagement::ProviderManager::MakeAndInitialize(&v55);
      LOBYTE(v12) = started;
      if ( started >= 0 )
      {
        std::unique_ptr<DAS::ProviderManagement::ProviderManager>::reset(v32, v55);
        started = InitializeProviderHosts();
        LOBYTE(v12) = started;
        if ( started >= 0 )
        {
          started = DasEvaluateUserSessionStartTrigger();
          LOBYTE(v12) = started;
          if ( started >= 0 )
          {
            *(_DWORD *)g_DasStartedSubsystems |= 8u;
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                (int)v9,
                v10,
                78,
                &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
            DasStatusUpdate(v33, 2u, 3u, 0);
            started = InitializeAssociationServices();
            LOBYTE(v12) = started;
            if ( started >= 0 )
            {
              *(_DWORD *)g_DasStartedSubsystems |= 4u;
              DasStatusUpdate(v34, 2u, 4u, 0);
              if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_(
                  *((_QWORD *)WPP_GLOBAL_Control + 5),
                  v35,
                  v36,
                  80,
                  &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
              started = InitializeQueryServices();
              LOBYTE(v12) = started;
              if ( started >= 0 )
              {
                *(_DWORD *)g_DasStartedSubsystems |= 2u;
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_(
                    *((_QWORD *)WPP_GLOBAL_Control + 5),
                    (int)v9,
                    v10,
                    82,
                    &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
                DasStatusUpdate(v37, 2u, 5u, 0);
                SubmitThreadpoolWork(*((PTP_WORK *)g_devnodeManager + 12));
                DasStatusUpdate(v38, 2u, 6u, 0);
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_(
                    *((_QWORD *)WPP_GLOBAL_Control + 5),
                    v39,
                    v40,
                    84,
                    &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
                *(_QWORD *)&qword_1800A4558 = &g_ChallengeList;
                g_ChallengeList.Flink = &g_ChallengeList;
                InitializeCriticalSection(&g_csChallengeList);
                g_bChallengeListInitialized = 1;
                g_bChallengeSubsystemStopping = 0;
                *(_DWORD *)g_DasStartedSubsystems |= 0x40u;
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_(
                    *((_QWORD *)WPP_GLOBAL_Control + 5),
                    v41,
                    v43,
                    86,
                    &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
                DasStatusUpdate(v42, 2u, 7u, 0);
                started = InitializeInboundServices();
                LOBYTE(v12) = started;
                if ( started >= 0 )
                {
                  *(_DWORD *)g_DasStartedSubsystems |= 0x100u;
                  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_(
                      *((_QWORD *)WPP_GLOBAL_Control + 5),
                      (int)v9,
                      v10,
                      88,
                      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
                  DasStatusUpdate(v44, 2u, 8u, 0);
                  InitializeImportExportServices();
                  *(_DWORD *)g_DasStartedSubsystems |= 0x80u;
                  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_(
                      *((_QWORD *)WPP_GLOBAL_Control + 5),
                      v45,
                      v47,
                      89,
                      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
                  DasStatusUpdate(v46, 2u, 9u, 0);
                  started = InitializeRpcServices();
                  LOBYTE(v12) = started;
                  if ( started >= 0 )
                  {
                    *(_DWORD *)g_DasStartedSubsystems |= 1u;
                    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                      WPP_RECORDER_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 5),
                        (int)v9,
                        v10,
                        91,
                        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
                    DasStatusUpdate(v48, 2u, 0xAu, 0);
                    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)&g_stopEvent);
                    v49 = (void (__fastcall *)(HANDLE *, const WCHAR *, wil::details *, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))*((_QWORD *)g_svcHostGlobalData + 24);
                    v50 = g_stopEvent;
                    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int UnregisterWait(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                      v51,
                      0);
                    v49(&g_serviceStopWait, L"DeviceAssociationService", v50, ServiceStopCallback, 0, 8);
                    DasStatusUpdate(v52, 4u, 0, 0);
                    DasEvaluateIdleStop(0);
                    goto LABEL_75;
                  }
                  if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                    goto LABEL_73;
                  v28 = 90;
                  goto LABEL_30;
                }
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  v28 = 87;
                  goto LABEL_30;
                }
              }
              else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                v28 = 81;
                goto LABEL_30;
              }
            }
            else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v28 = 79;
              goto LABEL_30;
            }
          }
          else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v28 = 77;
            goto LABEL_30;
          }
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v28 = 76;
          goto LABEL_30;
        }
      }
      else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v28 = 75;
        goto LABEL_30;
      }
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v28 = 73;
LABEL_30:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)v9,
        v10,
        v28,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        started);
LABEL_71:
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v9,
          v10,
          92,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
          (char)v12);
    }
LABEL_73:
    if ( !_InterlockedExchange(&g_bDasStopping, 1) )
      ((void (*)(void))DasStop)();
    goto LABEL_75;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_ellipsis(0) )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x36E,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\srventry.cpp",
        v11);
      __eh34_try_continuation(0, &loc_1800436C8);
    }
  }
}

```

## disassembly

```asm
0x180042f44  mov     [rsp+arg_10], rbx
0x180042f49  push    rsi
0x180042f4a  push    rdi
0x180042f4b  push    r12
0x180042f4d  push    r14
0x180042f4f  push    r15
0x180042f51  sub     rsp, 40h
0x180042f55  xor     esi, esi
0x180042f57  call    McGenEventRegister_EventRegister
0x180042f5c  lea     r14, WPP_RECORDER_INITIALIZED
0x180042f63  lea     r15, WPP_f5243b9130583a582cae89f06194ea2b_Traceguids
0x180042f6a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180042f71  jz      short loc_180042F8C
0x180042f73  lea     r9d, [rsi+42h]; int
0x180042f77  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180042f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042f83  mov     rcx, [rcx+28h]; int
0x180042f87  call    WPP_RECORDER_SF_
0x180042f8c  mov     rax, rsi
0x180042f8f  xchg    rax, cs:?g_ServiceControlFlags@@3_KC; unsigned __int64 volatile g_ServiceControlFlags
0x180042f96  mov     cs:?g_bDasStopping@@3JA, esi; long g_bDasStopping
0x180042f9c  mov     cs:?g_DasStopTimer@@3PEAU_TP_TIMER@@EA, rsi; _TP_TIMER * g_DasStopTimer
0x180042fa3  mov     r12d, 2
0x180042fa9  mov     cs:?g_DasCurrentState@@3KA, r12d; ulong g_DasCurrentState
0x180042fb0  mov     cs:?g_hDasStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rsi; SERVICE_STATUS_HANDLE__ * g_hDasStatus
0x180042fb7  xor     edx, edx
0x180042fb9  call    ?reset@?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@QEAAXPEAVPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@Z; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>::reset(Windows::Devices::Pnp::Internal::PnpObjectStoreManager *)
0x180042fbe  lea     rcx, ?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> g_AepStore
0x180042fc5  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180042fca  lea     rdi, ?g_AppStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> g_AppStore
0x180042fd1  mov     rcx, rdi
0x180042fd4  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180042fd9  lea     ecx, [r12+16h]; Size
0x180042fde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042fe3  mov     rbx, rax
0x180042fe6  mov     [rsp+68h+arg_0], rax
0x180042feb  xor     eax, eax
0x180042fed  mov     [rbx], rax
0x180042ff0  lea     rcx, [rbx+8]
0x180042ff4  mov     [rcx], rsi
0x180042ff7  mov     [rcx+8], rsi
0x180042ffb  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@KU_SYSTEMTIME@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_SYSTEMTIME@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,_SYSTEMTIME,std::less<ulong>,std::allocator<std::pair<ulong const,_SYSTEMTIME>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180043000  nop
0x180043001  mov     [rsp+68h+arg_0], rsi
0x180043006  mov     rdx, rbx
0x180043009  call    ?reset@?$unique_ptr@VWatchdog@Dispatcher@DAS@@U?$default_delete@VWatchdog@Dispatcher@DAS@@@std@@@std@@QEAAXPEAVWatchdog@Dispatcher@DAS@@@Z; std::unique_ptr<DAS::Dispatcher::Watchdog>::reset(DAS::Dispatcher::Watchdog *)
0x18004300e  lea     rcx, [rsp+68h+arg_0]
0x180043013  call    ??1?$unique_ptr@VWatchdog@Dispatcher@DAS@@U?$default_delete@VWatchdog@Dispatcher@DAS@@@std@@@std@@QEAA@XZ; std::unique_ptr<DAS::Dispatcher::Watchdog>::~unique_ptr<DAS::Dispatcher::Watchdog>(void)
0x180043018  mov     eax, cs:?g_DasStartedSubsystems@@3KA; ulong g_DasStartedSubsystems
0x18004301e  test    eax, eax
0x180043020  jz      short loc_180043049
0x180043022  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043029  jz      short loc_180043049
0x18004302b  lea     r9d, [r12+41h]; int
0x180043030  mov     dword ptr [rsp+68h+var_40], eax; char
0x180043034  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043039  mov     rcx, cs:WPP_GLOBAL_Control
0x180043040  mov     rcx, [rcx+28h]; int
0x180043044  call    WPP_RECORDER_SF_D
0x180043049  mov     cs:?g_DasStartedSubsystems@@3KA, esi; ulong g_DasStartedSubsystems
0x18004304f  xor     r8d, r8d; lpContext
0x180043052  lea     rdx, ?DasControlHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x180043059  lea     rcx, ServiceName; "DeviceAssociationService"
0x180043060  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180043066  mov     cs:?g_hDasStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hDasStatus
0x18004306d  test    rax, rax
0x180043070  jnz     short loc_180043089
0x180043072  call    cs:__imp_GetLastError
0x180043078  mov     ebx, eax
0x18004307a  test    eax, eax
0x18004307c  jle     short loc_1800430E9
0x18004307e  movzx   ebx, ax
0x180043081  or      ebx, 80070000h
0x180043087  jmp     short loc_1800430E9
0x180043089  call    ?InitializeDispatchServices@Dispatcher@DAS@@YAXXZ; DAS::Dispatcher::InitializeDispatchServices(void)
0x18004308e  xor     r8d, r8d; pcbe
0x180043091  xor     edx, edx; pv
0x180043093  lea     rcx, ?DasStopTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004309a  call    cs:__imp_CreateThreadpoolTimer
0x1800430a0  mov     cs:?g_DasStopTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_DasStopTimer
0x1800430a7  test    rax, rax
0x1800430aa  jnz     short loc_1800430F6
0x1800430ac  call    cs:__imp_GetLastError
0x1800430b2  mov     ebx, eax
0x1800430b4  test    eax, eax
0x1800430b6  jle     short loc_1800430C1
0x1800430b8  movzx   ebx, ax
0x1800430bb  or      ebx, 80070000h
0x1800430c1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800430c8  jz      short loc_1800430E9
0x1800430ca  mov     r9d, 44h ; 'D'; int
0x1800430d0  mov     dword ptr [rsp+68h+var_40], ebx; char
0x1800430d4  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x1800430d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800430e0  mov     rcx, [rcx+28h]; int
0x1800430e4  call    WPP_RECORDER_SF_D
0x1800430e9  test    ebx, ebx
0x1800430eb  jns     loc_1800436A1
0x1800430f1  jmp     loc_180043665
0x1800430f6  xor     r9d, r9d; unsigned int
0x1800430f9  xor     r8d, r8d; unsigned int
0x1800430fc  mov     edx, r12d; unsigned int
0x1800430ff  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043104  nop
0x180043105  mov     ecx, 18h; Size
0x18004310a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004310f  mov     rbx, rax
0x180043112  mov     [rsp+68h+arg_0], rax
0x180043117  xor     eax, eax
0x180043119  mov     [rbx], rax
0x18004311c  lea     rcx, [rbx+8]
0x180043120  mov     [rcx], rsi
0x180043123  mov     [rcx+8], rsi
0x180043127  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@KU_SYSTEMTIME@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_SYSTEMTIME@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,_SYSTEMTIME,std::less<ulong>,std::allocator<std::pair<ulong const,_SYSTEMTIME>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18004312c  nop
0x18004312d  mov     [rsp+68h+arg_0], rsi
0x180043132  mov     rdx, rbx
0x180043135  call    ?reset@?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@QEAAXPEAVPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@Z; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>::reset(Windows::Devices::Pnp::Internal::PnpObjectStoreManager *)
0x18004313a  lea     rcx, [rsp+68h+arg_0]
0x18004313f  call    ??1?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>::~unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager>(void)
0x180043144  nop
0x180043145  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x18004314c  lea     rcx, ?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> g_AepStore
0x180043153  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180043158  lea     r9, ?g_AepStore@@3V?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> g_AepStore
0x18004315f  mov     r8, cs:?g_hDasStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hDasStatus
0x180043166  mov     edx, 7
0x18004316b  mov     rcx, rbx
0x18004316e  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJW4_PNP_OBJECT_TYPE@@PEAUSERVICE_STATUS_HANDLE__@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(_PNP_OBJECT_TYPE,SERVICE_STATUS_HANDLE__ *,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180043173  mov     ebx, eax
0x180043175  test    eax, eax
0x180043177  jns     short loc_1800431AA
0x180043179  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043180  jz      loc_180043665
0x180043186  mov     r9d, 46h ; 'F'; int
0x18004318c  mov     dword ptr [rsp+68h+var_40], eax; char
0x180043190  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043195  mov     rcx, cs:WPP_GLOBAL_Control
0x18004319c  mov     rcx, [rcx+28h]; int
0x1800431a0  call    WPP_RECORDER_SF_D
0x1800431a5  jmp     loc_180043665
0x1800431aa  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x1800431b1  mov     rcx, rdi
0x1800431b4  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x1800431b9  mov     r9, rdi
0x1800431bc  mov     r8, cs:?g_hDasStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hDasStatus
0x1800431c3  mov     edx, 9
0x1800431c8  mov     rcx, rbx
0x1800431cb  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJW4_PNP_OBJECT_TYPE@@PEAUSERVICE_STATUS_HANDLE__@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(_PNP_OBJECT_TYPE,SERVICE_STATUS_HANDLE__ *,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x1800431d0  mov     ebx, eax
0x1800431d2  test    eax, eax
0x1800431d4  jns     short loc_18004320B
0x1800431d6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800431dd  jz      short loc_1800431FE
0x1800431df  mov     r9d, 47h ; 'G'; int
0x1800431e5  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800431e9  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x1800431ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431f5  mov     rcx, [rcx+28h]; int
0x1800431f9  call    WPP_RECORDER_SF_D
0x1800431fe  mov     rcx, rdi
0x180043201  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180043206  jmp     loc_180043665
0x18004320b  or      cs:?g_DasStartedSubsystems@@3KA, 20h; ulong g_DasStartedSubsystems
0x180043212  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043219  jz      short loc_180043236
0x18004321b  mov     r9d, 48h ; 'H'; int
0x180043221  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043226  mov     rcx, cs:WPP_GLOBAL_Control
0x18004322d  mov     rcx, [rcx+28h]; int
0x180043231  call    WPP_RECORDER_SF_
0x180043236  xor     r9d, r9d; unsigned int
0x180043239  lea     edi, [r9+1]
0x18004323d  mov     r8d, edi; unsigned int
0x180043240  mov     edx, r12d; unsigned int
0x180043243  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043248  mov     [rsp+68h+arg_0], rsi
0x18004324d  lea     r9, [rsp+68h+arg_0]; struct DAS::DevnodeManagment::DevnodeManager **
0x180043252  call    ?MakeAndInitialize@DevnodeManager@DevnodeManagment@DAS@@SAJPEBG00PEAPEAV123@@Z; DAS::DevnodeManagment::DevnodeManager::MakeAndInitialize(ushort const *,ushort const *,ushort const *,DAS::DevnodeManagment::DevnodeManager * *)
0x180043257  mov     ebx, eax
0x180043259  test    eax, eax
0x18004325b  jns     short loc_18004328C
0x18004325d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043264  jz      loc_180043692
0x18004326a  lea     r9d, [rdi+48h]; int
0x18004326e  mov     dword ptr [rsp+68h+var_40], eax; char
0x180043272  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043277  mov     rcx, cs:WPP_GLOBAL_Control
0x18004327e  mov     rcx, [rcx+28h]; int
0x180043282  call    WPP_RECORDER_SF_D
0x180043287  jmp     loc_18004366A
0x18004328c  mov     rdx, [rsp+68h+arg_0]
0x180043291  call    ?reset@?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@QEAAXPEAVDevnodeManager@DevnodeManagment@DAS@@@Z; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager>::reset(DAS::DevnodeManagment::DevnodeManager *)
0x180043296  or      cs:?g_DasStartedSubsystems@@3KA, 10h; ulong g_DasStartedSubsystems
0x18004329d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800432a4  jz      short loc_1800432C1
0x1800432a6  mov     r9d, 4Ah ; 'J'; int
0x1800432ac  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x1800432b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432b8  mov     rcx, [rcx+28h]; int
0x1800432bc  call    WPP_RECORDER_SF_
0x1800432c1  xor     r9d, r9d; unsigned int
0x1800432c4  mov     r8d, r12d; unsigned int
0x1800432c7  mov     edx, r12d; unsigned int
0x1800432ca  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x1800432cf  mov     [rsp+68h+arg_0], rsi
0x1800432d4  lea     rcx, [rsp+68h+arg_0]; struct DAS::ProviderManagement::ProviderManager **
0x1800432d9  call    ?MakeAndInitialize@ProviderManager@ProviderManagement@DAS@@SAJPEAPEAV123@@Z; DAS::ProviderManagement::ProviderManager::MakeAndInitialize(DAS::ProviderManagement::ProviderManager * *)
0x1800432de  mov     ebx, eax
0x1800432e0  test    eax, eax
0x1800432e2  jns     short loc_1800432FC
0x1800432e4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800432eb  jz      loc_180043692
0x1800432f1  mov     r9d, 4Bh ; 'K'
0x1800432f7  jmp     loc_18004326E
0x1800432fc  mov     rdx, [rsp+68h+arg_0]
0x180043301  call    ?reset@?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@QEAAXPEAVProviderManager@ProviderManagement@DAS@@@Z; std::unique_ptr<DAS::ProviderManagement::ProviderManager>::reset(DAS::ProviderManagement::ProviderManager *)
0x180043306  call    ?InitializeProviderHosts@@YAJXZ; InitializeProviderHosts(void)
0x18004330b  mov     ebx, eax
0x18004330d  test    eax, eax
0x18004330f  jns     short loc_180043329
0x180043311  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043318  jz      loc_180043692
0x18004331e  mov     r9d, 4Ch ; 'L'
0x180043324  jmp     loc_18004326E
0x180043329  call    ?DasEvaluateUserSessionStartTrigger@@YAJXZ; DasEvaluateUserSessionStartTrigger(void)
0x18004332e  mov     ebx, eax
0x180043330  test    eax, eax
0x180043332  jns     short loc_18004334C
0x180043334  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004333b  jz      loc_180043692
0x180043341  mov     r9d, 4Dh ; 'M'
0x180043347  jmp     loc_18004326E
0x18004334c  or      cs:?g_DasStartedSubsystems@@3KA, 8; ulong g_DasStartedSubsystems
0x180043353  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004335a  jz      short loc_180043377
0x18004335c  mov     r9d, 4Eh ; 'N'; int
0x180043362  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043367  mov     rcx, cs:WPP_GLOBAL_Control
0x18004336e  mov     rcx, [rcx+28h]; int
0x180043372  call    WPP_RECORDER_SF_
0x180043377  xor     r9d, r9d; unsigned int
0x18004337a  lea     r8d, [r9+3]; unsigned int
0x18004337e  mov     edx, r12d; unsigned int
0x180043381  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043386  call    ?InitializeAssociationServices@@YAJXZ; InitializeAssociationServices(void)
0x18004338b  mov     ebx, eax
0x18004338d  test    eax, eax
0x18004338f  jns     short loc_1800433A9
0x180043391  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043398  jz      loc_180043692
0x18004339e  mov     r9d, 4Fh ; 'O'
0x1800433a4  jmp     loc_18004326E
0x1800433a9  or      cs:?g_DasStartedSubsystems@@3KA, 4; ulong g_DasStartedSubsystems
0x1800433b0  xor     r9d, r9d; unsigned int
0x1800433b3  lea     r8d, [r9+4]; unsigned int
0x1800433b7  mov     edx, r12d; unsigned int
0x1800433ba  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x1800433bf  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800433c6  jz      short loc_1800433E3
0x1800433c8  mov     r9d, 50h ; 'P'; int
0x1800433ce  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x1800433d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800433da  mov     rcx, [rcx+28h]; int
0x1800433de  call    WPP_RECORDER_SF_
0x1800433e3  call    ?InitializeQueryServices@@YAJXZ; InitializeQueryServices(void)
0x1800433e8  mov     ebx, eax
0x1800433ea  test    eax, eax
0x1800433ec  jns     short loc_180043406
0x1800433ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800433f5  jz      loc_180043692
0x1800433fb  mov     r9d, 51h ; 'Q'
0x180043401  jmp     loc_18004326E
0x180043406  or      cs:?g_DasStartedSubsystems@@3KA, r12d; ulong g_DasStartedSubsystems
0x18004340d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043414  jz      short loc_180043431
0x180043416  mov     r9d, 52h ; 'R'; int
0x18004341c  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043421  mov     rcx, cs:WPP_GLOBAL_Control
0x180043428  mov     rcx, [rcx+28h]; int
0x18004342c  call    WPP_RECORDER_SF_
0x180043431  xor     r9d, r9d; unsigned int
0x180043434  lea     r8d, [r9+5]; unsigned int
0x180043438  mov     edx, r12d; unsigned int
0x18004343b  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043440  mov     rcx, cs:?g_devnodeManager@@3V?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@A; std::unique_ptr<DAS::DevnodeManagment::DevnodeManager> g_devnodeManager
0x180043447  mov     rcx, [rcx+60h]; pwk
0x18004344b  call    cs:__imp_SubmitThreadpoolWork
0x180043451  xor     r9d, r9d; unsigned int
0x180043454  lea     r8d, [r9+6]; unsigned int
0x180043458  mov     edx, r12d; unsigned int
0x18004345b  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043460  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180043467  jz      short loc_180043484
0x180043469  mov     r9d, 54h ; 'T'; int
0x18004346f  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x180043474  mov     rcx, cs:WPP_GLOBAL_Control
0x18004347b  mov     rcx, [rcx+28h]; int
0x18004347f  call    WPP_RECORDER_SF_
0x180043484  lea     rax, ?g_ChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ChallengeList
  ... truncated ...
```
