# DasStop(void)

- ea: `0x1800436e4`
- end: `0x180044057`
- name: `?DasStop@@YAXXZ`
- size: `2419`
- prototype: `void __fastcall(__int64, int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180042f44`
- `0x180044ae0`

## callees

- `0x180007500`
- `0x1800153e0`
- `0x180021830`
- `0x18002394c`
- `0x180024a64`
- `0x180028f58`
- `0x180028f9c`
- `0x1800344e4`
- `0x1800436e4`
- `0x180044c70`
- `0x180044fb0`
- `0x180048244`
- `0x1800482a4`
- `0x180048304`
- `0x180048364`
- `0x1800483c4`
- `0x180048424`
- `0x180048484`
- `0x1800484e4`
- `0x18004863c`
- `0x18004869c`
- `0x180048924`
- `0x180048e24`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180043f9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180043f9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043f7d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043f7d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043f8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043f8f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180043746`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180043746`

## pseudocode

```c
void __fastcall DasStop(__int64 a1, int a2, int a3)
{
  int v3; // ebx
  signed __int64 i; // rax
  struct SERVICE_STATUS_HANDLE__ *v5; // rcx
  int v6; // edx
  struct SERVICE_STATUS_HANDLE__ *v7; // rcx
  int v8; // r8d
  int active; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // edx
  struct SERVICE_STATUS_HANDLE__ *v13; // rcx
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // edx
  struct SERVICE_STATUS_HANDLE__ *v19; // rcx
  int v20; // r8d
  int v21; // eax
  int v22; // edx
  int v23; // r8d
  int v24; // edx
  struct SERVICE_STATUS_HANDLE__ *v25; // rcx
  int v26; // r8d
  int v27; // eax
  int v28; // edx
  int v29; // r8d
  int v30; // edx
  int v31; // r8d
  __int64 v32; // rcx
  int v33; // edx
  int v34; // r8d
  int v35; // edx
  int v36; // r8d
  int v37; // r9d
  const wchar_t *v38; // rax
  int v39; // edx
  struct SERVICE_STATUS_HANDLE__ *v40; // rcx
  int v41; // r8d
  int v42; // eax
  int v43; // edx
  int v44; // r8d
  int v45; // edx
  struct SERVICE_STATUS_HANDLE__ *v46; // rcx
  int v47; // r8d
  int Services; // eax
  int v49; // edx
  int v50; // r8d
  int v51; // edx
  struct SERVICE_STATUS_HANDLE__ *v52; // rcx
  int v53; // r8d
  int v54; // eax
  int v55; // edx
  int v56; // r8d
  int v57; // edx
  struct SERVICE_STATUS_HANDLE__ *v58; // rcx
  int v59; // r8d
  int v60; // eax
  int v61; // edx
  int v62; // r8d
  int v63; // edx
  struct SERVICE_STATUS_HANDLE__ *v64; // rcx
  int v65; // r8d
  int v66; // eax
  int v67; // edx
  int v68; // r8d
  int v69; // edx
  struct SERVICE_STATUS_HANDLE__ *v70; // rcx
  int v71; // r8d
  int v72; // eax
  int v73; // edx
  int v74; // r8d
  int v75; // edx
  struct SERVICE_STATUS_HANDLE__ *v76; // rcx
  int v77; // r8d
  int v78; // eax
  int v79; // edx
  int v80; // r8d
  int v81; // edx
  DAS::Dispatcher *v82; // rcx
  int v83; // r8d
  int v84; // edx
  int v85; // r8d
  int v86; // edx
  struct SERVICE_STATUS_HANDLE__ *v87; // rcx
  int v88; // r8d

  LOWORD(v3) = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 15, &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  _m_prefetchw((const void *)&g_ServiceControlFlags);
  for ( i = _InterlockedOr64((volatile signed __int64 *)&g_ServiceControlFlags, 1u);
        (i & 0xFFFFFFFFFFFFFFFEuLL) != 0;
        i = _InterlockedOr64((volatile signed __int64 *)&g_ServiceControlFlags, 1u) )
  {
    Sleep(0x32u);
    _m_prefetchw((const void *)&g_ServiceControlFlags);
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 16, &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  DasStatusUpdate(v5, 3u, 0, 0);
  if ( (g_DasStartedSubsystems[0] & 2) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v6,
        v8,
        17,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    active = DAS::Dispatcher::Dispatch::InvalidateActiveQueries();
    LOWORD(v3) = active;
    if ( active >= 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v10,
          v11,
          19,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v10,
        v11,
        18,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        active);
    }
  }
  DasStatusUpdate(v7, 3u, 1u, 0);
  if ( (g_DasStartedSubsystems[0] & 1) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v12,
        v14,
        20,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v15 = DAS::Dispatcher::Dispatch::DestroyRpcServices();
    LOWORD(v3) = v15;
    if ( v15 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~1u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v16,
          v17,
          22,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v16,
        v17,
        21,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v15);
    }
  }
  DasStatusUpdate(v13, 3u, 2u, 0);
  if ( g_DasStartedSubsystems[0] < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v18,
        v20,
        23,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v21 = DAS::Dispatcher::Dispatch::DestroyImportExportServices();
    LOWORD(v3) = v21;
    if ( v21 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~0x80u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v22,
          v23,
          25,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v23,
        24,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v21);
    }
  }
  DasStatusUpdate(v19, 3u, 3u, 0);
  if ( (g_DasStartedSubsystems[0] & 0x40) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v24,
        v26,
        26,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v27 = DAS::Dispatcher::Dispatch::DestroyChallengeServices();
    LOWORD(v3) = v27;
    if ( v27 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~0x40u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v28,
          v29,
          28,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v28,
        v29,
        27,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v27);
    }
  }
  DasStatusUpdate(v25, 3u, 4u, 0);
  v32 = 272;
  if ( (*(_WORD *)g_DasStartedSubsystems & 0x110) == 0x110 )
  {
    if ( DAS::DevnodeManagment::DevnodeManager::IsManagingDevnodes(g_devnodeManager, 0)
      || (unsigned int)AnyInboundOperationsToManage() )
    {
      v3 = DasChangeServiceStartType(2u, v33, v34);
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_52;
      v37 = 30;
    }
    else
    {
      v3 = DasChangeServiceStartType(3u, v33, v34);
      if ( *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        goto LABEL_52;
      v37 = 29;
    }
    v38 = L"failed";
    if ( v3 >= 0 )
      v38 = &dword_18008C97C;
    WPP_RECORDER_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v35,
      v36,
      v37,
      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
      (__int64)v38,
      v3);
  }
  else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v30,
      v31,
      31,
      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  }
LABEL_52:
  DasStatusUpdate((struct SERVICE_STATUS_HANDLE__ *)v32, 3u, 5u, 0);
  if ( (*(_WORD *)g_DasStartedSubsystems & 0x100) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v39,
        v41,
        32,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v42 = DAS::Dispatcher::Dispatch::DestroyInboundServices();
    LOWORD(v3) = v42;
    if ( v42 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~0x100u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v43,
          v44,
          34,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v43,
        v44,
        33,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v42);
    }
  }
  DasStatusUpdate(v40, 3u, 6u, 0);
  if ( (g_DasStartedSubsystems[0] & 2) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v45,
        v47,
        35,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    Services = DAS::Dispatcher::Dispatch::DestroyQueryServices();
    LOWORD(v3) = Services;
    if ( Services >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~2u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v49,
          v50,
          37,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v49,
        v50,
        36,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        Services);
    }
  }
  DasStatusUpdate(v46, 3u, 7u, 0);
  if ( (g_DasStartedSubsystems[0] & 4) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v51,
        v53,
        38,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v54 = DAS::Dispatcher::Dispatch::DestroyAssociationServices();
    LOWORD(v3) = v54;
    if ( v54 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~4u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v55,
          v56,
          40,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v55,
        v56,
        39,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v54);
    }
  }
  DasStatusUpdate(v52, 3u, 8u, 0);
  if ( (g_DasStartedSubsystems[0] & 0x10) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v57,
        v59,
        41,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v60 = DAS::Dispatcher::Dispatch::DeactivateDevnodeManager();
    LOWORD(v3) = v60;
    if ( v60 >= 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v61,
          v62,
          43,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v61,
        v62,
        42,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v60);
    }
  }
  DasStatusUpdate(v58, 3u, 9u, 0);
  if ( (g_DasStartedSubsystems[0] & 8) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v63,
        v65,
        44,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v66 = DAS::Dispatcher::Dispatch::DestroyProviderServices();
    LOWORD(v3) = v66;
    if ( v66 >= 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v67,
          v68,
          46,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
      *(_DWORD *)g_DasStartedSubsystems &= ~8u;
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v67,
        v68,
        45,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v66);
    }
  }
  DasStatusUpdate(v64, 3u, 0xAu, 0);
  if ( (g_DasStartedSubsystems[0] & 0x10) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v69,
        v71,
        47,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v72 = DAS::Dispatcher::Dispatch::DestroyDevnodeManager();
    LOWORD(v3) = v72;
    if ( v72 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~0x10u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v73,
          v74,
          49,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v73,
        v74,
        48,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v72);
    }
  }
  DasStatusUpdate(v70, 3u, 0xBu, 0);
  if ( (g_DasStartedSubsystems[0] & 0x20) != 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v75,
        v77,
        50,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    v78 = DAS::Dispatcher::Dispatch::DestroyAepStores();
    LOWORD(v3) = v78;
    if ( v78 >= 0 )
    {
      *(_DWORD *)g_DasStartedSubsystems &= ~0x20u;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v79,
          v80,
          52,
          &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v79,
        v80,
        51,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        v78);
    }
  }
  DasStatusUpdate(v76, 3u, 0xCu, 0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
    DAS::Dispatcher::UninitializeDispatchServices(v82);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v81,
      v83,
      53,
      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  SetThreadpoolTimer(g_DasStopTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(g_DasStopTimer, 1);
  CloseThreadpoolTimer(g_DasStopTimer);
  g_DasStopTimer = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v84,
      v85,
      54,
      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &g_stopEvent,
    0);
  if ( *(_DWORD *)g_DasStartedSubsystems )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v86,
        v88,
        55,
        &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids,
        g_DasStartedSubsystems[0]);
  }
  else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v86,
      v88,
      56,
      &WPP_f5243b9130583a582cae89f06194ea2b_Traceguids);
  }
  DasStatusUpdate(v87, 1u, 0xDu, (unsigned __int16)v3);
  McGenEventUnregister_EventUnregister();
}

```

## disassembly

```asm
0x1800436e4  push    rbx
0x1800436e6  push    rbp
0x1800436e7  push    rsi
0x1800436e8  push    rdi
0x1800436e9  sub     rsp, 48h
0x1800436ed  xor     ebx, ebx
0x1800436ef  lea     rdi, WPP_RECORDER_INITIALIZED
0x1800436f6  lea     rsi, WPP_f5243b9130583a582cae89f06194ea2b_Traceguids
0x1800436fd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043704  jz      short loc_18004371F
0x180043706  lea     r9d, [rbx+0Fh]; int
0x18004370a  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004370f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043716  mov     rcx, [rcx+28h]; int
0x18004371a  call    WPP_RECORDER_SF_
0x18004371f  prefetchw byte ptr cs:?g_ServiceControlFlags@@3_KC; unsigned __int64 volatile g_ServiceControlFlags
0x180043726  mov     rax, cs:?g_ServiceControlFlags@@3_KC; unsigned __int64 volatile g_ServiceControlFlags
0x18004372d  mov     rcx, rax
0x180043730  or      rcx, 1
0x180043734  lock cmpxchg cs:?g_ServiceControlFlags@@3_KC, rcx; unsigned __int64 volatile g_ServiceControlFlags
0x18004373d  jnz     short loc_18004372D
0x18004373f  jmp     short loc_18004376C
0x180043741  mov     ecx, 32h ; '2'; dwMilliseconds
0x180043746  call    cs:__imp_Sleep
0x18004374c  prefetchw byte ptr cs:?g_ServiceControlFlags@@3_KC; unsigned __int64 volatile g_ServiceControlFlags
0x180043753  mov     rax, cs:?g_ServiceControlFlags@@3_KC; unsigned __int64 volatile g_ServiceControlFlags
0x18004375a  mov     rcx, rax
0x18004375d  or      rcx, 1
0x180043761  lock cmpxchg cs:?g_ServiceControlFlags@@3_KC, rcx; unsigned __int64 volatile g_ServiceControlFlags
0x18004376a  jnz     short loc_18004375A
0x18004376c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180043772  jnz     short loc_180043741
0x180043774  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004377b  jz      short loc_180043798
0x18004377d  mov     r9d, 10h; int
0x180043783  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043788  mov     rcx, cs:WPP_GLOBAL_Control
0x18004378f  mov     rcx, [rcx+28h]; int
0x180043793  call    WPP_RECORDER_SF_
0x180043798  xor     r9d, r9d; unsigned int
0x18004379b  xor     r8d, r8d; unsigned int
0x18004379e  lea     ebp, [r9+3]
0x1800437a2  mov     edx, ebp; unsigned int
0x1800437a4  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x1800437a9  test    byte ptr cs:?g_DasStartedSubsystems@@3KA, 2; ulong g_DasStartedSubsystems
0x1800437b0  jz      short loc_18004382D
0x1800437b2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800437b9  jz      short loc_1800437D4
0x1800437bb  lea     r9d, [rbp+0Eh]; int
0x1800437bf  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x1800437c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800437cb  mov     rcx, [rcx+28h]; int
0x1800437cf  call    WPP_RECORDER_SF_
0x1800437d4  call    ?InvalidateActiveQueries@Dispatch@Dispatcher@DAS@@SAJXZ; DAS::Dispatcher::Dispatch::InvalidateActiveQueries(void)
0x1800437d9  mov     ebx, eax
0x1800437db  test    eax, eax
0x1800437dd  jns     short loc_180043809
0x1800437df  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800437e6  jz      short loc_18004382D
0x1800437e8  mov     r9d, 12h; int
0x1800437ee  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800437f2  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x1800437f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800437fe  mov     rcx, [rcx+28h]; int
0x180043802  call    WPP_RECORDER_SF_D
0x180043807  jmp     short loc_18004382D
0x180043809  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043810  jz      short loc_18004382D
0x180043812  mov     r9d, 13h; int
0x180043818  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004381d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043824  mov     rcx, [rcx+28h]; int
0x180043828  call    WPP_RECORDER_SF_
0x18004382d  xor     r9d, r9d; unsigned int
0x180043830  lea     r8d, [r9+1]; unsigned int
0x180043834  mov     edx, ebp; unsigned int
0x180043836  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x18004383b  test    byte ptr cs:?g_DasStartedSubsystems@@3KA, 1; ulong g_DasStartedSubsystems
0x180043842  jz      loc_1800438CC
0x180043848  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004384f  jz      short loc_18004386C
0x180043851  mov     r9d, 14h; int
0x180043857  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004385c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043863  mov     rcx, [rcx+28h]; int
0x180043867  call    WPP_RECORDER_SF_
0x18004386c  call    ?DestroyRpcServices@Dispatch@Dispatcher@DAS@@SAJXZ; DAS::Dispatcher::Dispatch::DestroyRpcServices(void)
0x180043871  mov     ebx, eax
0x180043873  test    eax, eax
0x180043875  jns     short loc_1800438A1
0x180043877  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004387e  jz      short loc_1800438CC
0x180043880  mov     r9d, 15h; int
0x180043886  mov     dword ptr [rsp+68h+var_40], eax; char
0x18004388a  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004388f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043896  mov     rcx, [rcx+28h]; int
0x18004389a  call    WPP_RECORDER_SF_D
0x18004389f  jmp     short loc_1800438CC
0x1800438a1  and     cs:?g_DasStartedSubsystems@@3KA, 0FFFFFFFEh; ulong g_DasStartedSubsystems
0x1800438a8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800438af  jz      short loc_1800438CC
0x1800438b1  mov     r9d, 16h; int
0x1800438b7  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x1800438bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438c3  mov     rcx, [rcx+28h]; int
0x1800438c7  call    WPP_RECORDER_SF_
0x1800438cc  xor     r9d, r9d; unsigned int
0x1800438cf  lea     r8d, [r9+2]; unsigned int
0x1800438d3  mov     edx, ebp; unsigned int
0x1800438d5  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x1800438da  test    byte ptr cs:?g_DasStartedSubsystems@@3KA, 80h; ulong g_DasStartedSubsystems
0x1800438e1  jz      loc_18004396C
0x1800438e7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800438ee  jz      short loc_18004390B
0x1800438f0  mov     r9d, 17h; int
0x1800438f6  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x1800438fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180043902  mov     rcx, [rcx+28h]; int
0x180043906  call    WPP_RECORDER_SF_
0x18004390b  call    ?DestroyImportExportServices@Dispatch@Dispatcher@DAS@@SAJXZ; DAS::Dispatcher::Dispatch::DestroyImportExportServices(void)
0x180043910  mov     ebx, eax
0x180043912  test    eax, eax
0x180043914  jns     short loc_180043940
0x180043916  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004391d  jz      short loc_18004396C
0x18004391f  mov     r9d, 18h; int
0x180043925  mov     dword ptr [rsp+68h+var_40], eax; char
0x180043929  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004392e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043935  mov     rcx, [rcx+28h]; int
0x180043939  call    WPP_RECORDER_SF_D
0x18004393e  jmp     short loc_18004396C
0x180043940  btr     cs:?g_DasStartedSubsystems@@3KA, 7; ulong g_DasStartedSubsystems
0x180043948  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004394f  jz      short loc_18004396C
0x180043951  mov     r9d, 19h; int
0x180043957  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004395c  mov     rcx, cs:WPP_GLOBAL_Control
0x180043963  mov     rcx, [rcx+28h]; int
0x180043967  call    WPP_RECORDER_SF_
0x18004396c  xor     r9d, r9d; unsigned int
0x18004396f  mov     r8d, ebp; unsigned int
0x180043972  mov     edx, ebp; unsigned int
0x180043974  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043979  test    byte ptr cs:?g_DasStartedSubsystems@@3KA, 40h; ulong g_DasStartedSubsystems
0x180043980  jz      loc_180043A0A
0x180043986  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004398d  jz      short loc_1800439AA
0x18004398f  mov     r9d, 1Ah; int
0x180043995  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x18004399a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439a1  mov     rcx, [rcx+28h]; int
0x1800439a5  call    WPP_RECORDER_SF_
0x1800439aa  call    ?DestroyChallengeServices@Dispatch@Dispatcher@DAS@@SAJXZ; DAS::Dispatcher::Dispatch::DestroyChallengeServices(void)
0x1800439af  mov     ebx, eax
0x1800439b1  test    eax, eax
0x1800439b3  jns     short loc_1800439DF
0x1800439b5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800439bc  jz      short loc_180043A0A
0x1800439be  mov     r9d, 1Bh; int
0x1800439c4  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800439c8  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x1800439cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439d4  mov     rcx, [rcx+28h]; int
0x1800439d8  call    WPP_RECORDER_SF_D
0x1800439dd  jmp     short loc_180043A0A
0x1800439df  and     cs:?g_DasStartedSubsystems@@3KA, 0FFFFFFBFh; ulong g_DasStartedSubsystems
0x1800439e6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800439ed  jz      short loc_180043A0A
0x1800439ef  mov     r9d, 1Ch; int
0x1800439f5  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x1800439fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a01  mov     rcx, [rcx+28h]; int
0x180043a05  call    WPP_RECORDER_SF_
0x180043a0a  xor     r9d, r9d; unsigned int
0x180043a0d  lea     r8d, [r9+4]; unsigned int
0x180043a11  mov     edx, ebp; unsigned int
0x180043a13  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043a18  mov     eax, cs:?g_DasStartedSubsystems@@3KA; ulong g_DasStartedSubsystems
0x180043a1e  mov     ecx, 110h
0x180043a23  and     eax, ecx
0x180043a25  cmp     eax, ecx
0x180043a27  jnz     loc_180043AB1
0x180043a2d  xor     edx, edx; bool
0x180043a2f  mov     rcx, cs:?g_devnodeManager@@3V?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@A; this
0x180043a36  call    ?IsManagingDevnodes@DevnodeManager@DevnodeManagment@DAS@@QEAA_N_N@Z; DAS::DevnodeManagment::DevnodeManager::IsManagingDevnodes(bool)
0x180043a3b  test    al, al
0x180043a3d  jnz     short loc_180043A62
0x180043a3f  call    ?AnyInboundOperationsToManage@@YAHXZ; AnyInboundOperationsToManage(void)
0x180043a44  test    eax, eax
0x180043a46  jnz     short loc_180043A62
0x180043a48  mov     ecx, ebp; dwStartType
0x180043a4a  call    ?DasChangeServiceStartType@@YAJK@Z; DasChangeServiceStartType(ulong)
0x180043a4f  mov     ebx, eax
0x180043a51  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043a58  jz      short loc_180043AD5
0x180043a5a  mov     r9d, 1Dh
0x180043a60  jmp     short loc_180043A7D
0x180043a62  mov     ecx, 2; dwStartType
0x180043a67  call    ?DasChangeServiceStartType@@YAJK@Z; DasChangeServiceStartType(ulong)
0x180043a6c  mov     ebx, eax
0x180043a6e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043a75  jz      short loc_180043AD5
0x180043a77  mov     r9d, 1Eh; int
0x180043a7d  lea     rax, aFailed; "failed"
0x180043a84  test    ebx, ebx
0x180043a86  lea     rcx, dword_18008C97C
0x180043a8d  cmovns  rax, rcx
0x180043a91  mov     dword ptr [rsp+68h+var_38], ebx; char
0x180043a95  mov     qword ptr [rsp+68h+var_40], rax; __int64
0x180043a9a  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043aa6  mov     rcx, [rcx+28h]; int
0x180043aaa  call    WPP_RECORDER_SF_Sd
0x180043aaf  jmp     short loc_180043AD5
0x180043ab1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043ab8  jz      short loc_180043AD5
0x180043aba  mov     r9d, 1Fh; int
0x180043ac0  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180043acc  mov     rcx, [rcx+28h]; int
0x180043ad0  call    WPP_RECORDER_SF_
0x180043ad5  xor     r9d, r9d; unsigned int
0x180043ad8  lea     r8d, [r9+5]; unsigned int
0x180043adc  mov     edx, ebp; unsigned int
0x180043ade  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043ae3  test    cs:?g_DasStartedSubsystems@@3KA, 100h; ulong g_DasStartedSubsystems
0x180043aed  jz      loc_180043B78
0x180043af3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043afa  jz      short loc_180043B17
0x180043afc  mov     r9d, 20h ; ' '; int
0x180043b02  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b0e  mov     rcx, [rcx+28h]; int
0x180043b12  call    WPP_RECORDER_SF_
0x180043b17  call    ?DestroyInboundServices@Dispatch@Dispatcher@DAS@@SAJXZ; DAS::Dispatcher::Dispatch::DestroyInboundServices(void)
0x180043b1c  mov     ebx, eax
0x180043b1e  test    eax, eax
0x180043b20  jns     short loc_180043B4C
0x180043b22  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043b29  jz      short loc_180043B78
0x180043b2b  mov     r9d, 21h ; '!'; int
0x180043b31  mov     dword ptr [rsp+68h+var_40], eax; char
0x180043b35  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b41  mov     rcx, [rcx+28h]; int
0x180043b45  call    WPP_RECORDER_SF_D
0x180043b4a  jmp     short loc_180043B78
0x180043b4c  btr     cs:?g_DasStartedSubsystems@@3KA, 8; ulong g_DasStartedSubsystems
0x180043b54  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043b5b  jz      short loc_180043B78
0x180043b5d  mov     r9d, 22h ; '"'; int
0x180043b63  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b6f  mov     rcx, [rcx+28h]; int
0x180043b73  call    WPP_RECORDER_SF_
0x180043b78  xor     r9d, r9d; unsigned int
0x180043b7b  lea     r8d, [r9+6]; unsigned int
0x180043b7f  mov     edx, ebp; unsigned int
0x180043b81  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043b86  test    byte ptr cs:?g_DasStartedSubsystems@@3KA, 2; ulong g_DasStartedSubsystems
0x180043b8d  jz      loc_180043C17
0x180043b93  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043b9a  jz      short loc_180043BB7
0x180043b9c  mov     r9d, 23h ; '#'; int
0x180043ba2  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bae  mov     rcx, [rcx+28h]; int
0x180043bb2  call    WPP_RECORDER_SF_
0x180043bb7  call    ?DestroyQueryServices@Dispatch@Dispatcher@DAS@@SAJXZ; DAS::Dispatcher::Dispatch::DestroyQueryServices(void)
0x180043bbc  mov     ebx, eax
0x180043bbe  test    eax, eax
0x180043bc0  jns     short loc_180043BEC
0x180043bc2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043bc9  jz      short loc_180043C17
0x180043bcb  mov     r9d, 24h ; '$'; int
0x180043bd1  mov     dword ptr [rsp+68h+var_40], eax; char
0x180043bd5  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180043be1  mov     rcx, [rcx+28h]; int
0x180043be5  call    WPP_RECORDER_SF_D
0x180043bea  jmp     short loc_180043C17
0x180043bec  and     cs:?g_DasStartedSubsystems@@3KA, 0FFFFFFFDh; ulong g_DasStartedSubsystems
0x180043bf3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043bfa  jz      short loc_180043C17
0x180043bfc  mov     r9d, 25h ; '%'; int
0x180043c02  mov     [rsp+68h+MessageGuid], rsi; MessageGuid
0x180043c07  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c0e  mov     rcx, [rcx+28h]; int
0x180043c12  call    WPP_RECORDER_SF_
0x180043c17  xor     r9d, r9d; unsigned int
0x180043c1a  lea     r8d, [r9+7]; unsigned int
0x180043c1e  mov     edx, ebp; unsigned int
0x180043c20  call    ?DasStatusUpdate@@YAXPEAUSERVICE_STATUS_HANDLE__@@KKK@Z; DasStatusUpdate(SERVICE_STATUS_HANDLE__ *,ulong,ulong,ulong)
0x180043c25  test    byte ptr cs:?g_DasStartedSubsystems@@3KA, 4; ulong g_DasStartedSubsystems
0x180043c2c  jz      loc_180043CB6
0x180043c32  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180043c39  jz      short loc_180043C56
0x180043c3b  mov     r9d, 26h ; '&'; int
  ... truncated ...
```
