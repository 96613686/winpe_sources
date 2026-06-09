# DriverEntry

- ea: `0x140191240`
- end: `0x140191cf9`
- name: `DriverEntry`
- size: `2745`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `55`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140191010`

## callees

- `0x14001cf60`
- `0x14002ab60`
- `0x14005b490`
- `0x14005dee0`
- `0x14005e1a0`
- `0x140068690`
- `0x14008b360`
- `0x140092d28`
- `0x14009626c`
- `0x1400962c4`
- `0x140096488`
- `0x1400964c0`
- `0x14009920c`
- `0x140099300`
- `0x1400a6c80`
- `0x1400c94ec`
- `0x1400c9e8c`
- `0x1400caed4`
- `0x1400cd838`
- `0x1400dffa0`
- `0x1400e8a80`
- `0x1400e9190`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14013ff30`
- `0x140142d04`
- `0x140144aa8`
- `0x14014522c`
- `0x14014cc80`
- `0x14014cd48`
- `0x140150164`
- `0x140150204`
- `0x140152060`
- `0x140159118`
- `0x14016ee90`
- `0x140173580`
- `0x140191078`
- `0x140191240`
- `0x140191d00`
- `0x140192088`
- `0x140192104`
- `0x1401922bc`
- `0x140192a98`
- `0x140192bf4`
- `0x140193214`
- `0x14019351c`
- `0x140193618`
- `0x140193774`
- `0x1401937ec`
- `0x140193c78`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14019144f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14019144f`
- `ntoskrnl!KeInitializeMutex` at `0x140191820`
- `ntoskrnl!KeInitializeMutex` at `0x140191835`
- `ntoskrnl!KeInitializeMutex` at `0x140191b7d`
- `ntoskrnl!KeInitializeMutex` at `0x140191820`
- `ntoskrnl!KeInitializeMutex` at `0x140191835`
- `ntoskrnl!KeInitializeMutex` at `0x140191b7d`
- `ntoskrnl!DbgPrint` at `0x140191728`
- `ntoskrnl!DbgPrint` at `0x14019176a`
- `ntoskrnl!DbgPrint` at `0x1401918a4`
- `ntoskrnl!DbgPrint` at `0x1401918e0`
- `ntoskrnl!DbgPrint` at `0x140191728`
- `ntoskrnl!DbgPrint` at `0x14019176a`
- `ntoskrnl!DbgPrint` at `0x1401918a4`
- `ntoskrnl!DbgPrint` at `0x1401918e0`
- `ntoskrnl!PcwRegister` at `0x140191b53`
- `ntoskrnl!PcwRegister` at `0x140191b53`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401916d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401916d0`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401915de`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14019162b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1401915de`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14019162b`
- `ntoskrnl!EtwRegister` at `0x14019137a`
- `ntoskrnl!EtwRegister` at `0x14019137a`
- `ntoskrnl!DbgSetDebugFilterState` at `0x1401913f3`
- `ntoskrnl!DbgSetDebugFilterState` at `0x1401913f3`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401915f7`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401915f7`
- `ntoskrnl!ExCreateCallback` at `0x14019170f`
- `ntoskrnl!ExCreateCallback` at `0x14019170f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1401919be`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140191a0f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1401919be`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140191a0f`
- `ntoskrnl!MmSizeOfMdl` at `0x14019197e`
- `ntoskrnl!MmSizeOfMdl` at `0x1401919d4`
- `ntoskrnl!MmSizeOfMdl` at `0x14019197e`
- `ntoskrnl!MmSizeOfMdl` at `0x1401919d4`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x140191ad5`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x140191ad5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019151d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191530`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191543`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191556`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191569`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019157c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019158f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401915a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401915b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401915c8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401917c2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191c92`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019151d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191530`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191543`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191556`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191569`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019157c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019158f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401915a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401915b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401915c8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401917c2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140191c92`
- `ntoskrnl!ExAllocatePool2` at `0x140191423`
- `ntoskrnl!ExAllocatePool2` at `0x140191423`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140191753`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140191753`
- `ntoskrnl!ZwPowerInformation` at `0x14019178a`
- `ntoskrnl!ZwPowerInformation` at `0x14019178a`
- `NETIO!NmrRegisterClient` at `0x140191bcb`
- `NETIO!NmrRegisterClient` at `0x140191bcb`
- `NETIO!NetioSetTriageBlock` at `0x140191c0f`
- `NETIO!NetioSetTriageBlock` at `0x140191c0f`
- `WppRecorder!imp_WppRecorderIsDefaultLogAvailable` at `0x140191679`
- `WppRecorder!imp_WppRecorderIsDefaultLogAvailable` at `0x140191679`

## string_xrefs

- `0x140191721`: `Ndis: failed to create a Callback object. Status %lx\n`
- `0x14019189d`: `NDIS: failed to create ndis net buffer list special pool.\n`
- `0x1401918d9`: `NDIS: failed to create ndis net buffer special pool.\n`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // r8d
  unsigned __int64 v5; // r13
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // edx
  NTSTATUS v10; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned __int8 (*v12)(void *, const struct KnobDescriptor *, unsigned __int64 *); // r8
  __int64 i; // rbx
  NTSTATUS v14; // eax
  int v15; // eax
  int v16; // edx
  SIZE_T v17; // rax
  SIZE_T v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  struct _DRIVER_OBJECT *v35; // rcx
  unsigned __int8 (*v36)(void *, const struct KnobDescriptor *, unsigned __int64 *); // r8
  unsigned __int8 (*v37)(void *, const struct KnobDescriptor *, unsigned __int64 *); // r8
  PVOID *Handle; // [rsp+20h] [rbp-B9h]
  unsigned __int8 Handleb; // [rsp+20h] [rbp-B9h]
  unsigned __int8 Handlec; // [rsp+20h] [rbp-B9h]
  unsigned __int8 Handled; // [rsp+20h] [rbp-B9h]
  unsigned __int8 Handlee; // [rsp+20h] [rbp-B9h]
  PVOID *Handlea; // [rsp+20h] [rbp-B9h]
  PVOID *Handlef; // [rsp+20h] [rbp-B9h]
  struct _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+40h] [rbp-99h] BYREF
  int Status; // [rsp+58h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-69h] BYREF
  struct _PCW_REGISTRATION_INFORMATION Info; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v51; // [rsp+D0h] [rbp-9h]
  _OWORD OutputBuffer[2]; // [rsp+D8h] [rbp-1h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  ndisWppExtendedCallback(0, 0, 0);
  v5 = (unsigned int)(v4 + 1);
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NDISTraceGuid;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)v5;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  traceInited = v5;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      v5,
      10,
      (struct _GUID *)&WPP_4569b34cddb434e75d3126ba0c358221_Traceguids);
  }
  McGenEventRegister_EtwRegister(&NDIS_PROVIDER_ID, v6, NDIS_PROVIDER_ID_Context, NDIS_PROVIDER_ID_Context);
  McGenEventRegister_EtwRegister(
    SLEEPSTUDY_ETW_PROVIDER,
    v7,
    &SLEEPSTUDY_ETW_PROVIDER_Context,
    &SLEEPSTUDY_ETW_PROVIDER_Context);
  if ( Microsoft_Windows_Networking_CorrelationHandle
    || !EtwRegister(
          &Microsoft_Windows_Networking_CorrelationId,
          Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
          0,
          &Microsoft_Windows_Networking_CorrelationHandle) )
  {
    Microsoft_Windows_Networking_ProviderId = NDIS_PROVIDER_ID;
  }
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1401206F8);
  InitializeTelemetryAssertsKMByDriverObject(DriverObject);
  v8 = TlgRegisterAggregateProviderEx();
  if ( v8 && *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 3;
    WPP_RECORDER_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v9,
      v5,
      11,
      (struct _GUID *)&WPP_4569b34cddb434e75d3126ba0c358221_Traceguids,
      v8);
  }
  DbgSetDebugFilterState(0x78u, 0xFFFFFFFF, v5);
  ndisRegistryPath.Length = 0;
  ndisRegistryPath.MaximumLength = RegistryPath->Length;
  ndisRegistryPath.Buffer = (wchar_t *)ExAllocatePool2(258, RegistryPath->Length + 2LL, 538985550);
  if ( !ndisRegistryPath.Buffer )
    return -1073741670;
  RtlCopyUnicodeString(&ndisRegistryPath, RegistryPath);
  ndisDriverObject = DriverObject;
  wil_InitializeFeatureStaging();
  IsEnabledDeviceUsageNoInline = Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline();
  ndisEtwRundownEnabled = v5;
  g_featureNVBugFixes2507 = IsEnabledDeviceUsageNoInline != 0;
  NdisDllInitialize();
  qword_140122A58 = (__int64)&qword_140122A50;
  qword_140122A50 = (__int64)&qword_140122A50;
  KPushLockManualConstruct::Initialize((KPushLockManualConstruct *)&qword_140122A48);
  memset(&Parameters, 0, sizeof(Parameters));
  KnobNamespace::KnobNamespace(
    &stru_140122830,
    (struct _DRIVER_OBJECT *)ndisDriverObject,
    (struct _CONFIG_KNOB_NAMESPACE *)&Parameters);
  ndisNblTrackerInitialize();
  ndisRegisterKnobs(&stru_1400F9100, 0x11u, v12, 0, Handle);
  v10 = ndisFdoInitializeSubsystem();
  if ( v10 >= 0 )
  {
    v10 = ndisLwmInitializeSubsystem();
    if ( v10 >= 0 )
    {
      v10 = ndisStackExpansionInitializeSubsystem();
      if ( v10 >= 0 )
      {
        DriverObject->DriverUnload = 0;
        KeInitializeSpinLock(&ndisGlobalLock);
        KeInitializeSpinLock(&ndisMiniDriverListLock);
        KeInitializeSpinLock(&ndisProtocolListLock);
        KeInitializeSpinLock(&ndisMiniportListLock);
        KeInitializeSpinLock(&ndisGlobalPacketPoolListLock);
        KeInitializeSpinLock(&ndisGlobalOpenListLock);
        KeInitializeSpinLock(&ndisGlobalFilterListLock);
        KeInitializeSpinLock(&ndisFilterDriverListLock);
        KeInitializeSpinLock(&ndisAbortedRequestsListLock);
        KeInitializeSpinLock(&ndisGlobalTimerListLock);
        ndisDmaAlignment = 8;
        ndisTimeIncrement = KeQueryTimeIncrement();
        ExInitializeResourceLite(&SharedMemoryResource);
        ndisReadRegistry();
        ndisFlags &= ~0x400u;
        KeBootTime.QuadPart = MEMORY[0xFFFFF78000000014];
        PoolAgingTicks.HighPart = 0;
        PoolAgingTicks.LowPart = 0x23C34600 / KeQueryTimeIncrement();
        *((_QWORD *)ndisDriverObject + 10) = qword_1400F72E0;
        ndisInitializeStackTraces();
        ndisWorkItemLog = (struct NDIS_EVENT_LOG_HANDLE__ *)ndisAllocateEventLog(0, 7);
        imp_WppRecorderIsDefaultLogAvailable(WPP_GLOBAL_Control);
        if ( (ndisFlags & 0x100) == 0 )
          ndisVerifierInitialization();
        for ( i = 0; i != 16; i += v5 )
          memset(&ndisAbortedRequests + 31 * i, 0, 0xB0u);
        RtlInitUnicodeString(&DestinationString, L"\\CallBack\\NdisBindUnbind");
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 592;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v14 = ExCreateCallback((PCALLBACK_OBJECT *)&ndisBindUnbindCallbackObject, &ObjectAttributes, v5, v5);
        if ( v14 < 0 )
          DbgPrint("Ndis: failed to create a Callback object. Status %lx\n", v14);
        if ( PoRegisterPowerSettingCallback(
               0,
               &GUID_ACDC_POWER_SOURCE,
               ndisPowerStateCallback,
               0,
               &ndisPowerStateCallbackHandle) < 0 )
          DbgPrint("Ndis: failed to register a power state Callback routine\n");
        if ( ZwPowerInformation(SystemBatteryState, 0, 0, OutputBuffer, 0x20u) < 0 )
          goto LABEL_26;
        if ( LOBYTE(OutputBuffer[0]) )
        {
          if ( LOBYTE(OutputBuffer[0]) != (_BYTE)v5 )
            goto LABEL_25;
        }
        else if ( BYTE1(OutputBuffer[0]) )
        {
LABEL_25:
          ndisAcOnLine = 0;
LABEL_26:
          ndisAoAcInitializeSubsystem();
          KeInitializeSpinLock(&qword_140122888);
          qword_1401231F8 = (__int64)&qword_1401231F0;
          qword_1401231F0 = (__int64)&qword_1401231F0;
          ndisInitializeNblPoolGlobal();
          qword_140122CB0 = (__int64)&ndisGlobalPacketPoolList;
          ndisGlobalPacketPoolList.Flink = &ndisGlobalPacketPoolList;
          qword_1401212C8 = (__int64)&ndisGlobalTimerList;
          ndisGlobalTimerList.Flink = &ndisGlobalTimerList;
          KeInitializeMutex(&ndisPnPMutex, 0xFFFFu);
          KeInitializeMutex(&ndisPeriodicReceivesMutex, 0xFFFFu);
          ndisPcwInitialize();
          KPushLockManualConstruct::Initialize((KPushLockManualConstruct *)&WPP_MAIN_CB.Dpc.DeferredContext);
          *(_QWORD *)&Parameters.DataSize = 0;
          WPP_MAIN_CB.Dpc.SystemArgument2 = &WPP_MAIN_CB.Dpc.SystemArgument1;
          WPP_MAIN_CB.Dpc.SystemArgument1 = &WPP_MAIN_CB.Dpc.SystemArgument1;
          Parameters.PoolTag = 1684948046;
          Parameters.Header = (_NDIS_OBJECT_HEADER)1311104;
          *(_DWORD *)&Parameters.ProtocolId = 256;
          ndisNetBufferListPool = NdisAllocateNetBufferListPool(0, &Parameters);
          if ( !ndisNetBufferListPool )
            DbgPrint("NDIS: failed to create ndis net buffer list special pool.\n");
          *(_QWORD *)&Parameters.PoolTag = 0;
          Parameters.Header = (_NDIS_OBJECT_HEADER)1048960;
          *(_DWORD *)&Parameters.ProtocolId = 1684948046;
          ndisNetBufferPool = NdisAllocateNetBufferPool(0, (PNET_BUFFER_POOL_PARAMETERS)&Parameters);
          if ( !ndisNetBufferPool )
            DbgPrint("NDIS: failed to create ndis net buffer special pool.\n");
          v15 = ndisInitializePeriodicReceives();
          if ( v15 < 0
            && *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v16) = v5;
            WPP_RECORDER_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v16,
              v5,
              12,
              (struct _GUID *)&WPP_4569b34cddb434e75d3126ba0c358221_Traceguids,
              v15);
          }
          ndisInitializePerProcRcvTracker();
          Status = 0;
          NdisAllocatePacketPoolEx(&Status, &ndisSendPacketPool, 0xFFFFu, 0, 0x20u);
          NdisAllocatePacketPoolEx(&Status, &ndisRecvPacketPool, 0xFFFFu, 0, 0x30u);
          v17 = MmSizeOfMdl((PVOID)0xFFF, 0x64u);
          ExInitializeNPagedLookasideList(
            &ndisRcv100BytesLL,
            0,
            0,
            0x200u,
            ((v17 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 100,
            0x7254444Eu,
            0);
          v18 = MmSizeOfMdl((PVOID)0xFFF, 0x5EAu);
          ExInitializeNPagedLookasideList(
            &ndisRcv1514BytesLL,
            0,
            0,
            0x200u,
            ((v18 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 1514,
            0x7254444Eu,
            0);
          AllUsersAclRead = ndisCreateAcl(v20, v19, v21, v22, Handleb, v5, 0x80000001);
          AllUsersAclWrite = ndisCreateAcl(v24, v23, v25, v26, Handlec, v5, 0x40000002u);
          AllUsersAclReadWrite = ndisCreateAcl(v28, v27, v29, v30, Handled, v5, 0xC0000013);
          AdminsAcl = ndisCreateAcl(v32, v31, v33, v34, Handlee, 0, 0xC0000013);
          ndisCreateGenericSD(AllUsersAclRead, &AllUsersReadSecurityDescriptor);
          ndisCreateGenericSD(AllUsersAclWrite, &AllUsersWriteSecurityDescriptor);
          ndisCreateGenericSD(AllUsersAclReadWrite, &AllUsersReadWriteSecurityDescriptor);
          ndisCreateGenericSD(AdminsAcl, &AdminsSecurityDescriptor);
          IoRegisterBootDriverReinitialization(DriverObject, ndisBootDriverReinit, 0);
          ndisCpuInitializeSubsystemPhase2();
          v10 = ndisBindInitialize();
          if ( v10 >= 0 )
          {
            ndisIfInitializePhase1();
            v10 = ndisPDInitialize();
            if ( v10 >= 0 )
            {
              ndisVBusNmrInitializeClient();
              ndisMiniportFdoInitializeSubsystem();
              *(_QWORD *)&Info.Version = 512;
              Info.Name = (PCUNICODE_STRING)&`ndisInitRegistrationInformationNetworkDirectCounterSet'::`2'::Name;
              *(_QWORD *)&Info.CounterCount = 10;
              Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`ndisInitRegistrationInformationNetworkDirectCounterSet'::`2'::Descriptors;
              v51 = 0;
              Info.Callback = (PPCW_CALLBACK)ndisNdkPcwProviderCallback;
              Info.CallbackContext = 0;
              PcwRegister(&ndisNetworkDirectCounterSet, &Info);
              qword_140123730 = 0;
              qword_140123738 = (__int64)ndisPktMonComponentNotify;
              KeInitializeMutex(&PktMonCompMutex, 0);
              qword_1401237C8 = &PktMonCompList;
              PktMonCompList = (__int64)&PktMonCompList;
              PktMonClientNotify.ClientRegistrationInstance.ModuleId = &NPI_MS_NDIS_MODULEID;
              qword_140123728 = (__int64)ndisPktMonRegisterComponentsCallback;
              NmrRegisterClient(&PktMonClientNotify, &PktMon, &PktMon);
              ndisRegisterPDCounterSets();
              word_140120C0E = *(_WORD *)ndisNblTrackerMode;
              word_140120C10 = ndisMaxNumberOfProcessors;
              qword_140120C18 = (__int64)&qword_140123200;
              NetioSetTriageBlock(0, &ndisGlobalTriageBlock);
              ndisDoesSystemSupportSriov();
              ndisReinitializeHistograms();
              ndisInitializeDmaSubsystem();
              qword_140122A40 = (struct KPushLockBase *)KLoader::KLoader((KLoader *)qword_140122A28);
              ndisLoaderDeviceObject = ndisKLoaderCreateControlDeviceObject(v35);
              ndisRegisterKnobs(&stru_1400F8F20, 2u, v36, 0, Handlea);
              ndisRegisterKnobs(&stru_1400F8EC0, v5, v37, 0, Handlef);
              KWaitEventBase<wistd::integral_constant<enum _EVENT_TYPE,0>>::InitializeBase(&WPP_MAIN_CB.SecurityDescriptor);
              KPushLockManualConstruct::Initialize((KPushLockManualConstruct *)&WPP_MAIN_CB.ActiveThreadCount);
              ndisMpHookNmrInitializeClient();
              KeInitializeSpinLock(&qword_1401227D0);
              if ( (unsigned int)Feature_NDPQualitySpring25__private_IsEnabledDeviceUsageNoInline() )
                ndisInitializeThreadMonitorSubsystem();
              if ( (unsigned int)Feature_NdisTriageData__private_IsEnabledDeviceUsageNoInline() )
                ndisInitializeGlobalTriageData();
            }
          }
          return v10;
        }
        ndisAcOnLine = v5;
        goto LABEL_26;
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140191240  mov     [rsp-8+arg_10], rbx
0x140191245  push    rbp
0x140191246  push    rsi
0x140191247  push    rdi
0x140191248  push    r12
0x14019124a  push    r13
0x14019124c  push    r14
0x14019124e  push    r15
0x140191250  lea     rbp, [rsp-27h]
0x140191255  sub     rsp, 100h
0x14019125c  mov     rax, cs:__security_cookie
0x140191263  xor     rax, rsp
0x140191266  mov     [rbp+57h+var_38], rax
0x14019126a  xorps   xmm0, xmm0
0x14019126d  mov     rdi, rcx
0x140191270  xorps   xmm1, xmm1
0x140191273  mov     rbx, rdx
0x140191276  xor     edx, edx
0x140191278  xor     ecx, ecx
0x14019127a  xor     r8d, r8d
0x14019127d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140191281  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140191285  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140191289  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14019128d  movups  [rbp+57h+OutputBuffer], xmm1
0x140191291  movups  [rbp+57h+var_48], xmm1
0x140191295  call    ndisWppExtendedCallback
0x14019129a  xor     r12d, r12d
0x14019129d  lea     rax, WPP_ThisDir_CTLGUID_NDISTraceGuid
0x1401912a4  lea     r13d, [r8+1]
0x1401912a8  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1401912af  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x1401912b6  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x1401912bd  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x1401912c4  mov     cs:WPP_MAIN_CB.Timer, r13
0x1401912cb  mov     cs:WPP_MAIN_CB.DeviceExtension, r12
0x1401912d2  mov     cs:WPP_MAIN_CB.DeviceType, r12d
0x1401912d9  call    WppLoadTracingSupport
0x1401912de  mov     rdx, rbx; __annotation("TMC:", "dd7a21e6-a651-46d4-b7c2-66543067b869", "NDISTraceGuid", "INIT", "RUNDOWN", "SEND", "RECV", "PROTOCOL", "BINDING", "BUSINFO", "REG", "PNPEVENT", "FILTER", "REQUEST", "WORK_ITEM", "PNP", "PM", "SS", "RESERVED2", "RESET", "WMI", "CO", "REF", "ALLOC", "IF", "PORT", "INDICATION", "QUEUE", "IOV", "MISC", "BINDENGINE", "PD", "PUBLIC_TMF:")
0x1401912e1  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x1401912e8  mov     rcx, rdi
0x1401912eb  call    WppInitKm
0x1401912f0  mov     cs:?traceInited@@3KA, r13d; ulong traceInited
0x1401912f7  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401912fe  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140191305  lea     rsi, WPP_4569b34cddb434e75d3126ba0c358221_Traceguids
0x14019130c  jz      short loc_14019132D
0x14019130e  mov     rcx, cs:WPP_GLOBAL_Control
0x140191315  lea     r9d, [r12+0Ah]; int
0x14019131a  mov     r8d, r13d; int
0x14019131d  mov     [rsp+130h+Handle], rsi; struct _GUID *
0x140191322  mov     dl, 4; int
0x140191324  mov     rcx, [rcx+40h]; int
0x140191328  call    WPP_RECORDER_SF_
0x14019132d  lea     r8, NDIS_PROVIDER_ID_Context
0x140191334  mov     r9, r8
0x140191337  lea     rcx, NDIS_PROVIDER_ID
0x14019133e  call    McGenEventRegister_EtwRegister
0x140191343  lea     r8, SLEEPSTUDY_ETW_PROVIDER_Context
0x14019134a  mov     r9, r8
0x14019134d  lea     rcx, SLEEPSTUDY_ETW_PROVIDER
0x140191354  call    McGenEventRegister_EtwRegister
0x140191359  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, r12
0x140191360  jnz     short loc_14019138A
0x140191362  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140191369  xor     r8d, r8d; CallbackContext
0x14019136c  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x140191373  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x14019137a  call    cs:__imp_EtwRegister
0x140191381  nop     dword ptr [rax+rax+00h]
0x140191386  test    eax, eax
0x140191388  jnz     short loc_140191399
0x14019138a  movups  xmm0, cs:NDIS_PROVIDER_ID
0x140191391  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x140191399  xor     r8d, r8d
0x14019139c  lea     rcx, dword_1401206F8; CallbackContext
0x1401913a3  xor     edx, edx
0x1401913a5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1401913aa  mov     rcx, rdi
0x1401913ad  call    InitializeTelemetryAssertsKMByDriverObject
0x1401913b2  call    TlgRegisterAggregateProviderEx
0x1401913b7  test    eax, eax
0x1401913b9  jz      short loc_1401913E8
0x1401913bb  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1401913c2  jz      short loc_1401913E8
0x1401913c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1401913cb  mov     r9d, 0Bh; int
0x1401913d1  mov     [rsp+130h+Tag], eax; char
0x1401913d5  mov     r8d, r13d; int
0x1401913d8  mov     dl, 3; int
0x1401913da  mov     [rsp+130h+Handle], rsi; void *
0x1401913df  mov     rcx, [rcx+40h]; int
0x1401913e3  call    WPP_RECORDER_SF_d
0x1401913e8  mov     r8b, r13b; State
0x1401913eb  or      edx, 0FFFFFFFFh; Level
0x1401913ee  mov     ecx, 78h ; 'x'; ComponentId
0x1401913f3  call    cs:__imp_DbgSetDebugFilterState
0x1401913fa  nop     dword ptr [rax+rax+00h]
0x1401913ff  mov     cs:?ndisRegistryPath@@3U_UNICODE_STRING@@A.Length, r12w; _UNICODE_STRING ndisRegistryPath ...
0x140191407  mov     ecx, 102h
0x14019140c  movzx   eax, word ptr [rbx]
0x14019140f  mov     r8d, 2020444Eh
0x140191415  mov     cs:?ndisRegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, ax; _UNICODE_STRING ndisRegistryPath ...
0x14019141c  movzx   edx, word ptr [rbx]
0x14019141f  add     rdx, 2
0x140191423  call    cs:__imp_ExAllocatePool2
0x14019142a  nop     dword ptr [rax+rax+00h]
0x14019142f  mov     cs:?ndisRegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING ndisRegistryPath ...
0x140191436  test    rax, rax
0x140191439  jnz     short loc_140191445
0x14019143b  mov     ebx, 0C000009Ah
0x140191440  jmp     loc_140191CBA
0x140191445  mov     rdx, rbx; SourceString
0x140191448  lea     rcx, ?ndisRegistryPath@@3U_UNICODE_STRING@@A; DestinationString
0x14019144f  call    cs:__imp_RtlCopyUnicodeString
0x140191456  nop     dword ptr [rax+rax+00h]
0x14019145b  mov     cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA, rdi; _DRIVER_OBJECT * ndisDriverObject
0x140191462  call    wil_InitializeFeatureStaging
0x140191467  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x14019146c  mov     ecx, r12d
0x14019146f  mov     cs:?ndisEtwRundownEnabled@@3_NA, r13b; bool ndisEtwRundownEnabled
0x140191476  test    eax, eax
0x140191478  setnz   cl
0x14019147b  mov     cs:?g_featureNVBugFixes2507@@3HA, ecx; int g_featureNVBugFixes2507
0x140191481  call    NdisDllInitialize
0x140191486  lea     rax, qword_140122A50
0x14019148d  lea     rcx, qword_140122A48; this
0x140191494  mov     cs:qword_140122A58, rax
0x14019149b  mov     cs:qword_140122A50, rax
0x1401914a2  call    ?Initialize@KPushLockManualConstruct@@QEAAXXZ; KPushLockManualConstruct::Initialize(void)
0x1401914a7  mov     rdx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; struct _DRIVER_OBJECT *
0x1401914ae  lea     r8, [rsp+130h+Parameters]; struct _CONFIG_KNOB_NAMESPACE *
0x1401914b3  xorps   xmm0, xmm0
0x1401914b6  mov     dword ptr [rsp+130h+Parameters.Header.Type], r12d
0x1401914bb  lea     rcx, stru_140122830; this
0x1401914c2  movdqu  xmmword ptr [rsp+130h+Parameters.ProtocolId], xmm0
0x1401914c8  call    ??0KnobNamespace@@QEAA@PEAU_DRIVER_OBJECT@@PEAU_CONFIG_KNOB_NAMESPACE@@@Z; KnobNamespace::KnobNamespace(_DRIVER_OBJECT *,_CONFIG_KNOB_NAMESPACE *)
0x1401914cd  call    ?ndisNblTrackerInitialize@@YAXXZ; ndisNblTrackerInitialize(void)
0x1401914d2  xor     r9d, r9d; int (*)(void *, const struct KnobDescriptor *, unsigned __int64)
0x1401914d5  lea     rcx, stru_1400F9100; struct KnobDescriptor *
0x1401914dc  lea     edx, [r9+11h]; unsigned __int64
0x1401914e0  call    ?ndisRegisterKnobs@@YAJPEBUKnobDescriptor@@_KP6AEPEAX0AEA_K@ZP6AJ201@Z2@Z; ndisRegisterKnobs(KnobDescriptor const *,unsigned __int64,uchar (*)(void *,KnobDescriptor const *,unsigned __int64 &),long (*)(void *,KnobDescriptor const *,unsigned __int64),void *)
0x1401914e5  call    ?ndisFdoInitializeSubsystem@@YAJXZ; ndisFdoInitializeSubsystem(void)
0x1401914ea  mov     ebx, eax
0x1401914ec  test    eax, eax
0x1401914ee  js      loc_140191CBA
0x1401914f4  call    ?ndisLwmInitializeSubsystem@@YAJXZ; ndisLwmInitializeSubsystem(void)
0x1401914f9  mov     ebx, eax
0x1401914fb  test    eax, eax
0x1401914fd  js      loc_140191CBA
0x140191503  call    ?ndisStackExpansionInitializeSubsystem@@YAJXZ; ndisStackExpansionInitializeSubsystem(void)
0x140191508  mov     ebx, eax
0x14019150a  test    eax, eax
0x14019150c  js      loc_140191CBA
0x140191512  lea     rcx, ?ndisGlobalLock@@3_KA; SpinLock
0x140191519  mov     [rdi+68h], r12
0x14019151d  call    cs:__imp_KeInitializeSpinLock
0x140191524  nop     dword ptr [rax+rax+00h]
0x140191529  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x140191530  call    cs:__imp_KeInitializeSpinLock
0x140191537  nop     dword ptr [rax+rax+00h]
0x14019153c  lea     rcx, ?ndisProtocolListLock@@3_KA; SpinLock
0x140191543  call    cs:__imp_KeInitializeSpinLock
0x14019154a  nop     dword ptr [rax+rax+00h]
0x14019154f  lea     rcx, ?ndisMiniportListLock@@3_KA; SpinLock
0x140191556  call    cs:__imp_KeInitializeSpinLock
0x14019155d  nop     dword ptr [rax+rax+00h]
0x140191562  lea     rcx, ?ndisGlobalPacketPoolListLock@@3_KA; SpinLock
0x140191569  call    cs:__imp_KeInitializeSpinLock
0x140191570  nop     dword ptr [rax+rax+00h]
0x140191575  lea     rcx, ?ndisGlobalOpenListLock@@3_KA; SpinLock
0x14019157c  call    cs:__imp_KeInitializeSpinLock
0x140191583  nop     dword ptr [rax+rax+00h]
0x140191588  lea     rcx, ?ndisGlobalFilterListLock@@3_KA; SpinLock
0x14019158f  call    cs:__imp_KeInitializeSpinLock
0x140191596  nop     dword ptr [rax+rax+00h]
0x14019159b  lea     rcx, ?ndisFilterDriverListLock@@3_KA; SpinLock
0x1401915a2  call    cs:__imp_KeInitializeSpinLock
0x1401915a9  nop     dword ptr [rax+rax+00h]
0x1401915ae  lea     rcx, ?ndisAbortedRequestsListLock@@3_KA; SpinLock
0x1401915b5  call    cs:__imp_KeInitializeSpinLock
0x1401915bc  nop     dword ptr [rax+rax+00h]
0x1401915c1  lea     rcx, ?ndisGlobalTimerListLock@@3_KA; SpinLock
0x1401915c8  call    cs:__imp_KeInitializeSpinLock
0x1401915cf  nop     dword ptr [rax+rax+00h]
0x1401915d4  mov     cs:?ndisDmaAlignment@@3KA, 8; ulong ndisDmaAlignment
0x1401915de  call    cs:__imp_KeQueryTimeIncrement
0x1401915e5  nop     dword ptr [rax+rax+00h]
0x1401915ea  lea     rcx, ?SharedMemoryResource@@3U_ERESOURCE@@A; Resource
0x1401915f1  mov     cs:?ndisTimeIncrement@@3KA, eax; ulong ndisTimeIncrement
0x1401915f7  call    cs:__imp_ExInitializeResourceLite
0x1401915fe  nop     dword ptr [rax+rax+00h]
0x140191603  call    ?ndisReadRegistry@@YAXXZ; ndisReadRegistry(void)
0x140191608  btr     cs:?ndisFlags@@3JA, 0Ah; long ndisFlags
0x140191610  mov     rax, 0FFFFF78000000014h
0x14019161a  mov     rax, [rax]
0x14019161d  mov     cs:?KeBootTime@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER KeBootTime
0x140191624  mov     dword ptr cs:?PoolAgingTicks@@3T_LARGE_INTEGER@@A+4, r12d; _LARGE_INTEGER PoolAgingTicks
0x14019162b  call    cs:__imp_KeQueryTimeIncrement
0x140191632  nop     dword ptr [rax+rax+00h]
0x140191637  mov     ecx, eax
0x140191639  xor     edx, edx
0x14019163b  mov     eax, 23C34600h
0x140191640  div     ecx
0x140191642  lea     rcx, qword_1400F72E0
0x140191649  mov     dword ptr cs:?PoolAgingTicks@@3T_LARGE_INTEGER@@A, eax; _LARGE_INTEGER PoolAgingTicks
0x14019164f  mov     rax, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * ndisDriverObject
0x140191656  mov     [rax+50h], rcx
0x14019165a  call    ?ndisInitializeStackTraces@@YAXXZ; ndisInitializeStackTraces(void)
0x14019165f  mov     edx, 7
0x140191664  xor     ecx, ecx
0x140191666  call    ?ndisAllocateEventLog@@YAPEAUNDIS_EVENT_LOG_HANDLE__@@W4_NDIS_EVENT_LOG_SIZE@@G@Z; ndisAllocateEventLog(_NDIS_EVENT_LOG_SIZE,ushort)
0x14019166b  mov     rcx, cs:WPP_GLOBAL_Control
0x140191672  mov     cs:?ndisWorkItemLog@@3PEAUNDIS_EVENT_LOG_HANDLE__@@EA, rax; NDIS_EVENT_LOG_HANDLE__ * ndisWorkItemLog
0x140191679  call    cs:__imp_imp_WppRecorderIsDefaultLogAvailable
0x140191680  nop     dword ptr [rax+rax+00h]
0x140191685  test    cs:?ndisFlags@@3JA, 100h; long ndisFlags
0x14019168f  jnz     short loc_140191696
0x140191691  call    ?ndisVerifierInitialization@@YAEXZ; ndisVerifierInitialization(void)
0x140191696  mov     rbx, r12
0x140191699  mov     r15d, 10h
0x14019169f  lea     rax, ?ndisAbortedRequests@@3PAU_NDIS_OID_REQUEST@@A; _NDIS_OID_REQUEST near * ndisAbortedRequests
0x1401916a6  xor     edx, edx; Val
0x1401916a8  imul    rcx, rbx, 0F8h
0x1401916af  mov     r8d, 0B0h; Size
0x1401916b5  add     rcx, rax; void *
0x1401916b8  call    memset
0x1401916bd  add     rbx, r13
0x1401916c0  cmp     rbx, r15
0x1401916c3  jnz     short loc_14019169F
0x1401916c5  lea     rdx, aCallbackNdisbi; "\\CallBack\\NdisBindUnbind"
0x1401916cc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1401916d0  call    cs:__imp_RtlInitUnicodeString
0x1401916d7  nop     dword ptr [rax+rax+00h]
0x1401916dc  lea     rax, [rbp+57h+DestinationString]
0x1401916e0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1401916e7  xorps   xmm0, xmm0
0x1401916ea  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1401916ee  mov     r9b, r13b; AllowMultipleCallbacks
0x1401916f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x1401916f5  mov     r8b, r13b; Create
0x1401916f8  mov     [rbp+57h+ObjectAttributes.Attributes], 250h
0x1401916ff  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140191703  lea     rcx, ?ndisBindUnbindCallbackObject@@3PEAU_CALLBACK_OBJECT@@EA; CallbackObject
0x14019170a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14019170f  call    cs:__imp_ExCreateCallback
0x140191716  nop     dword ptr [rax+rax+00h]
0x14019171b  test    eax, eax
0x14019171d  jns     short loc_140191734
0x14019171f  mov     edx, eax
0x140191721  lea     rcx, aNdisFailedToCr; "Ndis: failed to create a Callback objec"...
0x140191728  call    cs:__imp_DbgPrint
0x14019172f  nop     dword ptr [rax+rax+00h]
0x140191734  lea     rax, ?ndisPowerStateCallbackHandle@@3PEAXEA; void * ndisPowerStateCallbackHandle
0x14019173b  xor     r9d, r9d; Context
0x14019173e  lea     r8, ?ndisPowerStateCallback@@YAJPEBU_GUID@@PEAXK1@Z; Callback
0x140191745  mov     [rsp+130h+Handle], rax; Handle
0x14019174a  lea     rdx, GUID_ACDC_POWER_SOURCE; SettingGuid
0x140191751  xor     ecx, ecx; DeviceObject
0x140191753  call    cs:__imp_PoRegisterPowerSettingCallback
0x14019175a  nop     dword ptr [rax+rax+00h]
0x14019175f  test    eax, eax
0x140191761  jns     short loc_140191776
0x140191763  lea     rcx, aNdisFailedToRe; "Ndis: failed to register a power state "...
0x14019176a  call    cs:__imp_DbgPrint
0x140191771  nop     dword ptr [rax+rax+00h]
0x140191776  xor     edx, edx; InputBuffer
0x140191778  mov     dword ptr [rsp+130h+Handle], 20h ; ' '; OutputBufferLength
0x140191780  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x140191784  xor     r8d, r8d; InputBufferLength
0x140191787  lea     ecx, [rdx+5]; InformationLevel
0x14019178a  call    cs:__imp_ZwPowerInformation
0x140191791  nop     dword ptr [rax+rax+00h]
0x140191796  test    eax, eax
0x140191798  js      short loc_1401917B6
0x14019179a  mov     al, byte ptr [rbp+57h+OutputBuffer]
0x14019179d  test    al, al
0x14019179f  jnz     loc_140191CE4
0x1401917a5  cmp     byte ptr [rbp+57h+OutputBuffer+1], r12b
0x1401917a9  jz      loc_140191CED
0x1401917af  mov     cs:?ndisAcOnLine@@3KA, r12d; ulong ndisAcOnLine
0x1401917b6  call    ?ndisAoAcInitializeSubsystem@@YAJXZ; ndisAoAcInitializeSubsystem(void)
0x1401917bb  lea     rcx, qword_140122888; SpinLock
0x1401917c2  call    cs:__imp_KeInitializeSpinLock
0x1401917c9  nop     dword ptr [rax+rax+00h]
0x1401917ce  lea     rax, qword_1401231F0
0x1401917d5  mov     cs:qword_1401231F8, rax
0x1401917dc  mov     cs:qword_1401231F0, rax
0x1401917e3  call    ?ndisInitializeNblPoolGlobal@@YAXXZ; ndisInitializeNblPoolGlobal(void)
0x1401917e8  lea     rax, ?ndisGlobalPacketPoolList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisGlobalPacketPoolList
0x1401917ef  mov     ebx, 0FFFFh
0x1401917f4  mov     cs:qword_140122CB0, rax
0x1401917fb  lea     rcx, ?ndisPnPMutex@@3U_KMUTANT@@A; Mutex
0x140191802  mov     cs:?ndisGlobalPacketPoolList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ndisGlobalPacketPoolList
0x140191809  mov     edx, ebx; Level
0x14019180b  lea     rax, ?ndisGlobalTimerList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisGlobalTimerList
0x140191812  mov     cs:qword_1401212C8, rax
0x140191819  mov     cs:?ndisGlobalTimerList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ndisGlobalTimerList
0x140191820  call    cs:__imp_KeInitializeMutex
0x140191827  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
