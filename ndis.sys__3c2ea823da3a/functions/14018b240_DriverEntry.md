# DriverEntry

- ea: `0x14018b240`
- end: `0x14018bcf0`
- name: `DriverEntry`
- size: `2736`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14018b010`

## callees

- `0x140028e00`
- `0x140029620`
- `0x140056c50`
- `0x1400597f0`
- `0x140059ab0`
- `0x1400632c0`
- `0x1400860e0`
- `0x14008e2e8`
- `0x14009103c`
- `0x140091208`
- `0x140091240`
- `0x140093f8c`
- `0x140094080`
- `0x1400a1840`
- `0x1400c433c`
- `0x1400c4cdc`
- `0x1400c5d24`
- `0x1400c8688`
- `0x1400dadf0`
- `0x1400e38d0`
- `0x1400e3fe0`
- `0x1400e6160`
- `0x1400e65c0`
- `0x140138f30`
- `0x14013bd00`
- `0x14013db08`
- `0x14013e28c`
- `0x140145ce0`
- `0x140145da8`
- `0x1401491c4`
- `0x140149264`
- `0x14014b0c0`
- `0x140152178`
- `0x140167fa0`
- `0x14016c710`
- `0x14018b078`
- `0x14018b240`
- `0x14018bcf8`
- `0x14018c078`
- `0x14018c0f4`
- `0x14018c2ac`
- `0x14018ca88`
- `0x14018cbe4`
- `0x14018d204`
- `0x14018d50c`
- `0x14018d608`
- `0x14018d764`
- `0x14018d7dc`
- `0x14018dc68`
- `0x14018dd54`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14018b44f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14018b44f`
- `ntoskrnl!KeInitializeMutex` at `0x14018b820`
- `ntoskrnl!KeInitializeMutex` at `0x14018b835`
- `ntoskrnl!KeInitializeMutex` at `0x14018bb7d`
- `ntoskrnl!KeInitializeMutex` at `0x14018b820`
- `ntoskrnl!KeInitializeMutex` at `0x14018b835`
- `ntoskrnl!KeInitializeMutex` at `0x14018bb7d`
- `ntoskrnl!DbgPrint` at `0x14018b728`
- `ntoskrnl!DbgPrint` at `0x14018b76a`
- `ntoskrnl!DbgPrint` at `0x14018b8a4`
- `ntoskrnl!DbgPrint` at `0x14018b8e0`
- `ntoskrnl!DbgPrint` at `0x14018b728`
- `ntoskrnl!DbgPrint` at `0x14018b76a`
- `ntoskrnl!DbgPrint` at `0x14018b8a4`
- `ntoskrnl!DbgPrint` at `0x14018b8e0`
- `ntoskrnl!PcwRegister` at `0x14018bb53`
- `ntoskrnl!PcwRegister` at `0x14018bb53`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018b6d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018b6d0`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14018b5de`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14018b62b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14018b5de`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14018b62b`
- `ntoskrnl!EtwRegister` at `0x14018b37a`
- `ntoskrnl!EtwRegister` at `0x14018b37a`
- `ntoskrnl!DbgSetDebugFilterState` at `0x14018b3f3`
- `ntoskrnl!DbgSetDebugFilterState` at `0x14018b3f3`
- `ntoskrnl!ExInitializeResourceLite` at `0x14018b5f7`
- `ntoskrnl!ExInitializeResourceLite` at `0x14018b5f7`
- `ntoskrnl!ExCreateCallback` at `0x14018b70f`
- `ntoskrnl!ExCreateCallback` at `0x14018b70f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018b9be`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018ba0f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018b9be`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14018ba0f`
- `ntoskrnl!MmSizeOfMdl` at `0x14018b97e`
- `ntoskrnl!MmSizeOfMdl` at `0x14018b9d4`
- `ntoskrnl!MmSizeOfMdl` at `0x14018b97e`
- `ntoskrnl!MmSizeOfMdl` at `0x14018b9d4`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x14018bad5`
- `ntoskrnl!IoRegisterBootDriverReinitialization` at `0x14018bad5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b51d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b530`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b543`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b556`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b569`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b57c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b58f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b5a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b5b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b5c8`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b7c2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018bc92`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b51d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b530`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b543`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b556`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b569`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b57c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b58f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b5a2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b5b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b5c8`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018b7c2`
- `ntoskrnl!KeInitializeSpinLock` at `0x14018bc92`
- `ntoskrnl!ExAllocatePool2` at `0x14018b423`
- `ntoskrnl!ExAllocatePool2` at `0x14018b423`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14018b753`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14018b753`
- `ntoskrnl!ZwPowerInformation` at `0x14018b78a`
- `ntoskrnl!ZwPowerInformation` at `0x14018b78a`
- `NETIO!NmrRegisterClient` at `0x14018bbcb`
- `NETIO!NmrRegisterClient` at `0x14018bbcb`
- `NETIO!NetioSetTriageBlock` at `0x14018bc0f`
- `NETIO!NetioSetTriageBlock` at `0x14018bc0f`
- `WppRecorder!imp_WppRecorderIsDefaultLogAvailable` at `0x14018b679`
- `WppRecorder!imp_WppRecorderIsDefaultLogAvailable` at `0x14018b679`

## string_xrefs

- `0x14018b721`: `Ndis: failed to create a Callback object. Status %lx\n`
- `0x14018b89d`: `NDIS: failed to create ndis net buffer list special pool.\n`
- `0x14018b8d9`: `NDIS: failed to create ndis net buffer special pool.\n`

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
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_14011A6F8);
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
  qword_14011CA58 = (__int64)&qword_14011CA50;
  qword_14011CA50 = (__int64)&qword_14011CA50;
  KPushLockManualConstruct::Initialize((KPushLockManualConstruct *)&qword_14011CA48);
  memset(&Parameters, 0, sizeof(Parameters));
  KnobNamespace::KnobNamespace(
    &stru_14011C830,
    (struct _DRIVER_OBJECT *)ndisDriverObject,
    (struct _CONFIG_KNOB_NAMESPACE *)&Parameters);
  ndisNblTrackerInitialize();
  ndisRegisterKnobs(&stru_1400F40E0, 0x11u, v12, 0, Handle);
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
        *((_QWORD *)ndisDriverObject + 10) = qword_1400F22E0;
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
          KeInitializeSpinLock(&qword_14011C888);
          qword_14011D1F8 = (__int64)&qword_14011D1F0;
          qword_14011D1F0 = (__int64)&qword_14011D1F0;
          ndisInitializeNblPoolGlobal();
          qword_14011CCB0 = (__int64)&ndisGlobalPacketPoolList;
          ndisGlobalPacketPoolList.Flink = &ndisGlobalPacketPoolList;
          qword_14011B2C8 = (__int64)&ndisGlobalTimerList;
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
              qword_14011D740 = 0;
              qword_14011D748 = (__int64)ndisPktMonComponentNotify;
              KeInitializeMutex(&PktMonCompMutex, 0);
              qword_14011D7C8 = &PktMonCompList;
              PktMonCompList = (__int64)&PktMonCompList;
              PktMonClientNotify.ClientRegistrationInstance.ModuleId = &NPI_MS_NDIS_MODULEID;
              qword_14011D738 = (__int64)ndisPktMonRegisterComponentsCallback;
              NmrRegisterClient(&PktMonClientNotify, &PktMon, &PktMon);
              ndisRegisterPDCounterSets();
              word_14011AC0E = *(_WORD *)ndisNblTrackerMode;
              word_14011AC10 = ndisMaxNumberOfProcessors;
              qword_14011AC18 = (__int64)&qword_14011D200;
              NetioSetTriageBlock(0, &ndisGlobalTriageBlock);
              ndisDoesSystemSupportSriov();
              ndisReinitializeHistograms();
              ndisInitializeDmaSubsystem();
              qword_14011CA40 = (struct KPushLockBase *)KLoader::KLoader((KLoader *)qword_14011CA28);
              ndisLoaderDeviceObject = ndisKLoaderCreateControlDeviceObject(v35);
              ndisRegisterKnobs(&stru_1400F3F00, 2u, v36, 0, Handlea);
              ndisRegisterKnobs(&stru_1400F3EA0, v5, v37, 0, Handlef);
              KWaitEventBase<wistd::integral_constant<enum _EVENT_TYPE,0>>::InitializeBase(&WPP_MAIN_CB.SecurityDescriptor);
              KPushLockManualConstruct::Initialize((KPushLockManualConstruct *)&WPP_MAIN_CB.ActiveThreadCount);
              ndisMpHookNmrInitializeClient();
              KeInitializeSpinLock(&qword_14011C7D0);
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
0x14018b240  mov     [rsp-8+arg_10], rbx
0x14018b245  push    rbp
0x14018b246  push    rsi
0x14018b247  push    rdi
0x14018b248  push    r12
0x14018b24a  push    r13
0x14018b24c  push    r14
0x14018b24e  push    r15
0x14018b250  lea     rbp, [rsp-27h]
0x14018b255  sub     rsp, 100h
0x14018b25c  mov     rax, cs:__security_cookie
0x14018b263  xor     rax, rsp
0x14018b266  mov     [rbp+57h+var_38], rax
0x14018b26a  xorps   xmm0, xmm0
0x14018b26d  mov     rdi, rcx
0x14018b270  xorps   xmm1, xmm1
0x14018b273  mov     rbx, rdx
0x14018b276  xor     edx, edx
0x14018b278  xor     ecx, ecx
0x14018b27a  xor     r8d, r8d
0x14018b27d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14018b281  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14018b285  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14018b289  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14018b28d  movups  [rbp+57h+OutputBuffer], xmm1
0x14018b291  movups  [rbp+57h+var_48], xmm1
0x14018b295  call    ndisWppExtendedCallback
0x14018b29a  xor     r12d, r12d
0x14018b29d  lea     rax, WPP_ThisDir_CTLGUID_NDISTraceGuid
0x14018b2a4  lea     r13d, [r8+1]
0x14018b2a8  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14018b2af  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x14018b2b6  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x14018b2bd  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x14018b2c4  mov     cs:WPP_MAIN_CB.Timer, r13
0x14018b2cb  mov     cs:WPP_MAIN_CB.DeviceExtension, r12
0x14018b2d2  mov     cs:WPP_MAIN_CB.DeviceType, r12d
0x14018b2d9  call    WppLoadTracingSupport
0x14018b2de  mov     rdx, rbx; __annotation("TMC:", "dd7a21e6-a651-46d4-b7c2-66543067b869", "NDISTraceGuid", "INIT", "RUNDOWN", "SEND", "RECV", "PROTOCOL", "BINDING", "BUSINFO", "REG", "PNPEVENT", "FILTER", "REQUEST", "WORK_ITEM", "PNP", "PM", "SS", "RESERVED2", "RESET", "WMI", "CO", "REF", "ALLOC", "IF", "PORT", "INDICATION", "QUEUE", "IOV", "MISC", "BINDENGINE", "PD", "PUBLIC_TMF:")
0x14018b2e1  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x14018b2e8  mov     rcx, rdi
0x14018b2eb  call    WppInitKm
0x14018b2f0  mov     cs:?traceInited@@3KA, r13d; ulong traceInited
0x14018b2f7  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14018b2fe  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14018b305  lea     rsi, WPP_4569b34cddb434e75d3126ba0c358221_Traceguids
0x14018b30c  jz      short loc_14018B32D
0x14018b30e  mov     rcx, cs:WPP_GLOBAL_Control
0x14018b315  lea     r9d, [r12+0Ah]; int
0x14018b31a  mov     r8d, r13d; int
0x14018b31d  mov     [rsp+130h+Handle], rsi; struct _GUID *
0x14018b322  mov     dl, 4; int
0x14018b324  mov     rcx, [rcx+40h]; int
0x14018b328  call    WPP_RECORDER_SF_
0x14018b32d  lea     r8, NDIS_PROVIDER_ID_Context
0x14018b334  mov     r9, r8
0x14018b337  lea     rcx, NDIS_PROVIDER_ID
0x14018b33e  call    McGenEventRegister_EtwRegister
0x14018b343  lea     r8, SLEEPSTUDY_ETW_PROVIDER_Context
0x14018b34a  mov     r9, r8
0x14018b34d  lea     rcx, SLEEPSTUDY_ETW_PROVIDER
0x14018b354  call    McGenEventRegister_EtwRegister
0x14018b359  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, r12
0x14018b360  jnz     short loc_14018B38A
0x14018b362  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14018b369  xor     r8d, r8d; CallbackContext
0x14018b36c  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x14018b373  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x14018b37a  call    cs:__imp_EtwRegister
0x14018b381  nop     dword ptr [rax+rax+00h]
0x14018b386  test    eax, eax
0x14018b388  jnz     short loc_14018B399
0x14018b38a  movups  xmm0, cs:NDIS_PROVIDER_ID
0x14018b391  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x14018b399  xor     r8d, r8d
0x14018b39c  lea     rcx, dword_14011A6F8; CallbackContext
0x14018b3a3  xor     edx, edx
0x14018b3a5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14018b3aa  mov     rcx, rdi
0x14018b3ad  call    InitializeTelemetryAssertsKMByDriverObject
0x14018b3b2  call    TlgRegisterAggregateProviderEx
0x14018b3b7  test    eax, eax
0x14018b3b9  jz      short loc_14018B3E8
0x14018b3bb  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14018b3c2  jz      short loc_14018B3E8
0x14018b3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14018b3cb  mov     r9d, 0Bh; int
0x14018b3d1  mov     [rsp+130h+Tag], eax; char
0x14018b3d5  mov     r8d, r13d; int
0x14018b3d8  mov     dl, 3; int
0x14018b3da  mov     [rsp+130h+Handle], rsi; void *
0x14018b3df  mov     rcx, [rcx+40h]; int
0x14018b3e3  call    WPP_RECORDER_SF_d
0x14018b3e8  mov     r8b, r13b; State
0x14018b3eb  or      edx, 0FFFFFFFFh; Level
0x14018b3ee  mov     ecx, 78h ; 'x'; ComponentId
0x14018b3f3  call    cs:__imp_DbgSetDebugFilterState
0x14018b3fa  nop     dword ptr [rax+rax+00h]
0x14018b3ff  mov     cs:?ndisRegistryPath@@3U_UNICODE_STRING@@A.Length, r12w; _UNICODE_STRING ndisRegistryPath ...
0x14018b407  mov     ecx, 102h
0x14018b40c  movzx   eax, word ptr [rbx]
0x14018b40f  mov     r8d, 2020444Eh
0x14018b415  mov     cs:?ndisRegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, ax; _UNICODE_STRING ndisRegistryPath ...
0x14018b41c  movzx   edx, word ptr [rbx]
0x14018b41f  add     rdx, 2
0x14018b423  call    cs:__imp_ExAllocatePool2
0x14018b42a  nop     dword ptr [rax+rax+00h]
0x14018b42f  mov     cs:?ndisRegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING ndisRegistryPath ...
0x14018b436  test    rax, rax
0x14018b439  jnz     short loc_14018B445
0x14018b43b  mov     ebx, 0C000009Ah
0x14018b440  jmp     loc_14018BCB1
0x14018b445  mov     rdx, rbx; SourceString
0x14018b448  lea     rcx, ?ndisRegistryPath@@3U_UNICODE_STRING@@A; DestinationString
0x14018b44f  call    cs:__imp_RtlCopyUnicodeString
0x14018b456  nop     dword ptr [rax+rax+00h]
0x14018b45b  mov     cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA, rdi; _DRIVER_OBJECT * ndisDriverObject
0x14018b462  call    wil_InitializeFeatureStaging
0x14018b467  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x14018b46c  mov     ecx, r12d
0x14018b46f  mov     cs:?ndisEtwRundownEnabled@@3_NA, r13b; bool ndisEtwRundownEnabled
0x14018b476  test    eax, eax
0x14018b478  setnz   cl
0x14018b47b  mov     cs:?g_featureNVBugFixes2507@@3HA, ecx; int g_featureNVBugFixes2507
0x14018b481  call    NdisDllInitialize
0x14018b486  lea     rax, qword_14011CA50
0x14018b48d  lea     rcx, qword_14011CA48; this
0x14018b494  mov     cs:qword_14011CA58, rax
0x14018b49b  mov     cs:qword_14011CA50, rax
0x14018b4a2  call    ?Initialize@KPushLockManualConstruct@@QEAAXXZ; KPushLockManualConstruct::Initialize(void)
0x14018b4a7  mov     rdx, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; struct _DRIVER_OBJECT *
0x14018b4ae  lea     r8, [rsp+130h+Parameters]; struct _CONFIG_KNOB_NAMESPACE *
0x14018b4b3  xorps   xmm0, xmm0
0x14018b4b6  mov     dword ptr [rsp+130h+Parameters.Header.Type], r12d
0x14018b4bb  lea     rcx, stru_14011C830; this
0x14018b4c2  movdqu  xmmword ptr [rsp+130h+Parameters.ProtocolId], xmm0
0x14018b4c8  call    ??0KnobNamespace@@QEAA@PEAU_DRIVER_OBJECT@@PEAU_CONFIG_KNOB_NAMESPACE@@@Z; KnobNamespace::KnobNamespace(_DRIVER_OBJECT *,_CONFIG_KNOB_NAMESPACE *)
0x14018b4cd  call    ?ndisNblTrackerInitialize@@YAXXZ; ndisNblTrackerInitialize(void)
0x14018b4d2  xor     r9d, r9d; int (*)(void *, const struct KnobDescriptor *, unsigned __int64)
0x14018b4d5  lea     rcx, stru_1400F40E0; struct KnobDescriptor *
0x14018b4dc  lea     edx, [r9+11h]; unsigned __int64
0x14018b4e0  call    ?ndisRegisterKnobs@@YAJPEBUKnobDescriptor@@_KP6AEPEAX0AEA_K@ZP6AJ201@Z2@Z; ndisRegisterKnobs(KnobDescriptor const *,unsigned __int64,uchar (*)(void *,KnobDescriptor const *,unsigned __int64 &),long (*)(void *,KnobDescriptor const *,unsigned __int64),void *)
0x14018b4e5  call    ?ndisFdoInitializeSubsystem@@YAJXZ; ndisFdoInitializeSubsystem(void)
0x14018b4ea  mov     ebx, eax
0x14018b4ec  test    eax, eax
0x14018b4ee  js      loc_14018BCB1
0x14018b4f4  call    ?ndisLwmInitializeSubsystem@@YAJXZ; ndisLwmInitializeSubsystem(void)
0x14018b4f9  mov     ebx, eax
0x14018b4fb  test    eax, eax
0x14018b4fd  js      loc_14018BCB1
0x14018b503  call    ?ndisStackExpansionInitializeSubsystem@@YAJXZ; ndisStackExpansionInitializeSubsystem(void)
0x14018b508  mov     ebx, eax
0x14018b50a  test    eax, eax
0x14018b50c  js      loc_14018BCB1
0x14018b512  lea     rcx, ?ndisGlobalLock@@3_KA; SpinLock
0x14018b519  mov     [rdi+68h], r12
0x14018b51d  call    cs:__imp_KeInitializeSpinLock
0x14018b524  nop     dword ptr [rax+rax+00h]
0x14018b529  lea     rcx, ?ndisMiniDriverListLock@@3_KA; SpinLock
0x14018b530  call    cs:__imp_KeInitializeSpinLock
0x14018b537  nop     dword ptr [rax+rax+00h]
0x14018b53c  lea     rcx, ?ndisProtocolListLock@@3_KA; SpinLock
0x14018b543  call    cs:__imp_KeInitializeSpinLock
0x14018b54a  nop     dword ptr [rax+rax+00h]
0x14018b54f  lea     rcx, ?ndisMiniportListLock@@3_KA; SpinLock
0x14018b556  call    cs:__imp_KeInitializeSpinLock
0x14018b55d  nop     dword ptr [rax+rax+00h]
0x14018b562  lea     rcx, ?ndisGlobalPacketPoolListLock@@3_KA; SpinLock
0x14018b569  call    cs:__imp_KeInitializeSpinLock
0x14018b570  nop     dword ptr [rax+rax+00h]
0x14018b575  lea     rcx, ?ndisGlobalOpenListLock@@3_KA; SpinLock
0x14018b57c  call    cs:__imp_KeInitializeSpinLock
0x14018b583  nop     dword ptr [rax+rax+00h]
0x14018b588  lea     rcx, ?ndisGlobalFilterListLock@@3_KA; SpinLock
0x14018b58f  call    cs:__imp_KeInitializeSpinLock
0x14018b596  nop     dword ptr [rax+rax+00h]
0x14018b59b  lea     rcx, ?ndisFilterDriverListLock@@3_KA; SpinLock
0x14018b5a2  call    cs:__imp_KeInitializeSpinLock
0x14018b5a9  nop     dword ptr [rax+rax+00h]
0x14018b5ae  lea     rcx, ?ndisAbortedRequestsListLock@@3_KA; SpinLock
0x14018b5b5  call    cs:__imp_KeInitializeSpinLock
0x14018b5bc  nop     dword ptr [rax+rax+00h]
0x14018b5c1  lea     rcx, ?ndisGlobalTimerListLock@@3_KA; SpinLock
0x14018b5c8  call    cs:__imp_KeInitializeSpinLock
0x14018b5cf  nop     dword ptr [rax+rax+00h]
0x14018b5d4  mov     cs:?ndisDmaAlignment@@3KA, 8; ulong ndisDmaAlignment
0x14018b5de  call    cs:__imp_KeQueryTimeIncrement
0x14018b5e5  nop     dword ptr [rax+rax+00h]
0x14018b5ea  lea     rcx, ?SharedMemoryResource@@3U_ERESOURCE@@A; Resource
0x14018b5f1  mov     cs:?ndisTimeIncrement@@3KA, eax; ulong ndisTimeIncrement
0x14018b5f7  call    cs:__imp_ExInitializeResourceLite
0x14018b5fe  nop     dword ptr [rax+rax+00h]
0x14018b603  call    ?ndisReadRegistry@@YAXXZ; ndisReadRegistry(void)
0x14018b608  btr     cs:?ndisFlags@@3JA, 0Ah; long ndisFlags
0x14018b610  mov     rax, 0FFFFF78000000014h
0x14018b61a  mov     rax, [rax]
0x14018b61d  mov     cs:?KeBootTime@@3T_LARGE_INTEGER@@A, rax; _LARGE_INTEGER KeBootTime
0x14018b624  mov     dword ptr cs:?PoolAgingTicks@@3T_LARGE_INTEGER@@A+4, r12d; _LARGE_INTEGER PoolAgingTicks
0x14018b62b  call    cs:__imp_KeQueryTimeIncrement
0x14018b632  nop     dword ptr [rax+rax+00h]
0x14018b637  mov     ecx, eax
0x14018b639  xor     edx, edx
0x14018b63b  mov     eax, 23C34600h
0x14018b640  div     ecx
0x14018b642  lea     rcx, qword_1400F22E0
0x14018b649  mov     dword ptr cs:?PoolAgingTicks@@3T_LARGE_INTEGER@@A, eax; _LARGE_INTEGER PoolAgingTicks
0x14018b64f  mov     rax, cs:?ndisDriverObject@@3PEAU_DRIVER_OBJECT@@EA; _DRIVER_OBJECT * ndisDriverObject
0x14018b656  mov     [rax+50h], rcx
0x14018b65a  call    ?ndisInitializeStackTraces@@YAXXZ; ndisInitializeStackTraces(void)
0x14018b65f  mov     edx, 7
0x14018b664  xor     ecx, ecx
0x14018b666  call    ?ndisAllocateEventLog@@YAPEAUNDIS_EVENT_LOG_HANDLE__@@W4_NDIS_EVENT_LOG_SIZE@@G@Z; ndisAllocateEventLog(_NDIS_EVENT_LOG_SIZE,ushort)
0x14018b66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14018b672  mov     cs:?ndisWorkItemLog@@3PEAUNDIS_EVENT_LOG_HANDLE__@@EA, rax; NDIS_EVENT_LOG_HANDLE__ * ndisWorkItemLog
0x14018b679  call    cs:__imp_imp_WppRecorderIsDefaultLogAvailable
0x14018b680  nop     dword ptr [rax+rax+00h]
0x14018b685  test    cs:?ndisFlags@@3JA, 100h; long ndisFlags
0x14018b68f  jnz     short loc_14018B696
0x14018b691  call    ?ndisVerifierInitialization@@YAEXZ; ndisVerifierInitialization(void)
0x14018b696  mov     rbx, r12
0x14018b699  mov     r15d, 10h
0x14018b69f  lea     rax, ?ndisAbortedRequests@@3PAU_NDIS_OID_REQUEST@@A; _NDIS_OID_REQUEST near * ndisAbortedRequests
0x14018b6a6  xor     edx, edx; Val
0x14018b6a8  imul    rcx, rbx, 0F8h
0x14018b6af  mov     r8d, 0B0h; Size
0x14018b6b5  add     rcx, rax; void *
0x14018b6b8  call    memset
0x14018b6bd  add     rbx, r13
0x14018b6c0  cmp     rbx, r15
0x14018b6c3  jnz     short loc_14018B69F
0x14018b6c5  lea     rdx, aCallbackNdisbi; "\\CallBack\\NdisBindUnbind"
0x14018b6cc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14018b6d0  call    cs:__imp_RtlInitUnicodeString
0x14018b6d7  nop     dword ptr [rax+rax+00h]
0x14018b6dc  lea     rax, [rbp+57h+DestinationString]
0x14018b6e0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14018b6e7  xorps   xmm0, xmm0
0x14018b6ea  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14018b6ee  mov     r9b, r13b; AllowMultipleCallbacks
0x14018b6f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x14018b6f5  mov     r8b, r13b; Create
0x14018b6f8  mov     [rbp+57h+ObjectAttributes.Attributes], 250h
0x14018b6ff  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14018b703  lea     rcx, ?ndisBindUnbindCallbackObject@@3PEAU_CALLBACK_OBJECT@@EA; CallbackObject
0x14018b70a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14018b70f  call    cs:__imp_ExCreateCallback
0x14018b716  nop     dword ptr [rax+rax+00h]
0x14018b71b  test    eax, eax
0x14018b71d  jns     short loc_14018B734
0x14018b71f  mov     edx, eax
0x14018b721  lea     rcx, aNdisFailedToCr; "Ndis: failed to create a Callback objec"...
0x14018b728  call    cs:__imp_DbgPrint
0x14018b72f  nop     dword ptr [rax+rax+00h]
0x14018b734  lea     rax, ?ndisPowerStateCallbackHandle@@3PEAXEA; void * ndisPowerStateCallbackHandle
0x14018b73b  xor     r9d, r9d; Context
0x14018b73e  lea     r8, ?ndisPowerStateCallback@@YAJPEBU_GUID@@PEAXK1@Z; Callback
0x14018b745  mov     [rsp+130h+Handle], rax; Handle
0x14018b74a  lea     rdx, GUID_ACDC_POWER_SOURCE; SettingGuid
0x14018b751  xor     ecx, ecx; DeviceObject
0x14018b753  call    cs:__imp_PoRegisterPowerSettingCallback
0x14018b75a  nop     dword ptr [rax+rax+00h]
0x14018b75f  test    eax, eax
0x14018b761  jns     short loc_14018B776
0x14018b763  lea     rcx, aNdisFailedToRe; "Ndis: failed to register a power state "...
0x14018b76a  call    cs:__imp_DbgPrint
0x14018b771  nop     dword ptr [rax+rax+00h]
0x14018b776  xor     edx, edx; InputBuffer
0x14018b778  mov     dword ptr [rsp+130h+Handle], 20h ; ' '; OutputBufferLength
0x14018b780  lea     r9, [rbp+57h+OutputBuffer]; OutputBuffer
0x14018b784  xor     r8d, r8d; InputBufferLength
0x14018b787  lea     ecx, [rdx+5]; InformationLevel
0x14018b78a  call    cs:__imp_ZwPowerInformation
0x14018b791  nop     dword ptr [rax+rax+00h]
0x14018b796  test    eax, eax
0x14018b798  js      short loc_14018B7B6
0x14018b79a  mov     al, byte ptr [rbp+57h+OutputBuffer]
0x14018b79d  test    al, al
0x14018b79f  jnz     loc_14018BCDB
0x14018b7a5  cmp     byte ptr [rbp+57h+OutputBuffer+1], r12b
0x14018b7a9  jz      loc_14018BCE4
0x14018b7af  mov     cs:?ndisAcOnLine@@3KA, r12d; ulong ndisAcOnLine
0x14018b7b6  call    ?ndisAoAcInitializeSubsystem@@YAJXZ; ndisAoAcInitializeSubsystem(void)
0x14018b7bb  lea     rcx, qword_14011C888; SpinLock
0x14018b7c2  call    cs:__imp_KeInitializeSpinLock
0x14018b7c9  nop     dword ptr [rax+rax+00h]
0x14018b7ce  lea     rax, qword_14011D1F0
0x14018b7d5  mov     cs:qword_14011D1F8, rax
0x14018b7dc  mov     cs:qword_14011D1F0, rax
0x14018b7e3  call    ?ndisInitializeNblPoolGlobal@@YAXXZ; ndisInitializeNblPoolGlobal(void)
0x14018b7e8  lea     rax, ?ndisGlobalPacketPoolList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisGlobalPacketPoolList
0x14018b7ef  mov     ebx, 0FFFFh
0x14018b7f4  mov     cs:qword_14011CCB0, rax
0x14018b7fb  lea     rcx, ?ndisPnPMutex@@3U_KMUTANT@@A; Mutex
0x14018b802  mov     cs:?ndisGlobalPacketPoolList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ndisGlobalPacketPoolList
0x14018b809  mov     edx, ebx; Level
0x14018b80b  lea     rax, ?ndisGlobalTimerList@@3U_LIST_ENTRY@@A; _LIST_ENTRY ndisGlobalTimerList
0x14018b812  mov     cs:qword_14011B2C8, rax
0x14018b819  mov     cs:?ndisGlobalTimerList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY ndisGlobalTimerList
0x14018b820  call    cs:__imp_KeInitializeMutex
0x14018b827  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
