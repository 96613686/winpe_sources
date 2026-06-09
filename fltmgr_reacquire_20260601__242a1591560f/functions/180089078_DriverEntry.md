# DriverEntry

- ea: `0x180089078`
- end: `0x180089c57`
- name: `DriverEntry`
- size: `3039`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180089010`

## callees

- `0x180009f20`
- `0x180014cf0`
- `0x180020180`
- `0x18002129c`
- `0x1800213a4`
- `0x180021a64`
- `0x180021ad0`
- `0x1800247a0`
- `0x180024880`
- `0x180024c00`
- `0x18004c008`
- `0x180051060`
- `0x180051b20`
- `0x180057dc4`
- `0x180077690`
- `0x180089078`
- `0x180089cec`
- `0x18008a130`
- `0x18008a2d8`
- `0x18008a618`
- `0x18008a978`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180089b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089b61`
- `ntoskrnl!ExAllocatePool2` at `0x180089591`
- `ntoskrnl!ExAllocatePool2` at `0x180089591`
- `ntoskrnl!KeInitializeEvent` at `0x180089779`
- `ntoskrnl!KeInitializeEvent` at `0x180089791`
- `ntoskrnl!KeInitializeEvent` at `0x180089a01`
- `ntoskrnl!KeInitializeEvent` at `0x180089779`
- `ntoskrnl!KeInitializeEvent` at `0x180089791`
- `ntoskrnl!KeInitializeEvent` at `0x180089a01`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089b0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089b0b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180089314`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180089314`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800893e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089b95`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800893e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x180089b95`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180089a2f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180089a2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180089a7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180089a7b`
- `ntoskrnl!ExReleaseFastResource` at `0x180089a6f`
- `ntoskrnl!ExReleaseFastResource` at `0x180089a6f`
- `ntoskrnl!IoCreateDevice` at `0x180089397`
- `ntoskrnl!IoCreateDevice` at `0x180089397`
- `ntoskrnl!IoDeleteDevice` at `0x180089b7d`
- `ntoskrnl!IoDeleteDevice` at `0x180089b7d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x18008934d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x18008934d`
- `ntoskrnl!ZwClose` at `0x1800898a7`
- `ntoskrnl!ZwClose` at `0x1800898a7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180089886`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180089886`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1800892b5`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1800892b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x18008997a`
- `ntoskrnl!KeInitializeSpinLock` at `0x18008997a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x180089a47`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x180089a47`
- `ntoskrnl!EtwSetInformation` at `0x180089254`
- `ntoskrnl!EtwSetInformation` at `0x180089254`
- `ntoskrnl!EtwRegister` at `0x1800891eb`
- `ntoskrnl!EtwRegister` at `0x1800891eb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800890e9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1800890e9`
- `ntoskrnl!FsRtlRegisterFltMgrCalls` at `0x180089184`
- `ntoskrnl!FsRtlRegisterFltMgrCalls` at `0x180089184`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1800892c7`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1800892c7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1800893f5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x180089431`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1800893f5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x180089431`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x18008941d`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x180089ba6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x18008941d`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x180089ba6`
- `ntoskrnl!WmiQueryTraceInformation` at `0x180089494`
- `ntoskrnl!WmiQueryTraceInformation` at `0x180089494`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x180089708`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x180089708`
- `ntoskrnl!ExAllocateTimer` at `0x1800897a4`
- `ntoskrnl!ExAllocateTimer` at `0x1800897a4`
- `ntoskrnl!PsCreateSystemThread` at `0x180089839`
- `ntoskrnl!PsCreateSystemThread` at `0x180089839`
- `ntoskrnl!DbgPrintEx` at `0x1800898f6`
- `ntoskrnl!DbgPrintEx` at `0x180089937`
- `ntoskrnl!DbgPrintEx` at `0x18008994f`
- `ntoskrnl!DbgPrintEx` at `0x180089967`
- `ntoskrnl!DbgPrintEx` at `0x1800898f6`
- `ntoskrnl!DbgPrintEx` at `0x180089937`
- `ntoskrnl!DbgPrintEx` at `0x18008994f`
- `ntoskrnl!DbgPrintEx` at `0x180089967`
- `ntoskrnl!KeSetEvent` at `0x180089aeb`
- `ntoskrnl!KeSetEvent` at `0x180089aeb`
- `ntoskrnl!ExDeleteTimer` at `0x180089b43`
- `ntoskrnl!ExDeleteTimer` at `0x180089b43`
- `ntoskrnl!EtwUnregister` at `0x180089bc5`
- `ntoskrnl!EtwUnregister` at `0x180089bc5`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180089bfc`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180089bfc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180089bdd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180089bdd`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x180089c25`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x180089c25`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1800894fe`
- `ntoskrnl!FsRtlIsMobileOS` at `0x1800894fe`
- `HAL!KeQueryPerformanceCounter` at `0x1800894f2`
- `HAL!KeQueryPerformanceCounter` at `0x1800894f2`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  PVOID SystemRoutineAddress; // rax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 started; // rdi
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 Device; // rdi
  __int64 v11; // rcx
  __int64 *v12; // rdx
  unsigned int v13; // eax
  __int64 TraceInformation; // rdi
  __int64 v15; // rcx
  char IsMobileOS; // al
  __int64 (__fastcall *v17)(int, int, int, int, int); // rcx
  __int64 (__fastcall *v18)(int, int, int, int, __int64); // rcx
  struct _FAST_IO_DISPATCH *Pool2; // rax
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rdx
  PFAST_IO_DISPATCH FastIoDispatch; // rcx
  _BYTE v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE SystemRoutineName[24]; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD EventInformation[5]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v36; // [rsp+134h] [rbp+34h]
  _UNKNOWN *retaddr; // [rsp+168h] [rbp+68h]

  DestinationString = 0;
  memset(&Callbacks, 0, sizeof(Callbacks));
  wil_InitializeFeatureStaging();
  *(_QWORD *)SystemRoutineName = 3276848;
  *(_QWORD *)&SystemRoutineName[8] = L"NtQuerySystemInformation";
  FltpVelocity = 0;
  v30[0] = 0;
  SystemRoutineAddress = MmGetSystemRoutineAddress((PUNICODE_STRING)SystemRoutineName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v30, 1, 0) >= 0
    && v30[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  ExDefaultMdlProtection = 0x40000000;
  EventInformation[0] = 318767126;
  EventInformation[1] = 1931084032;
  EventInformation[2] = -1982902448;
  EventInformation[3] = -525121662;
  EventInformation[4] = 80341212;
  v36 = -17802;
  memset(FltGlobals, 0, 0x1780u);
  dword_18003E750 = 1;
  FsRtlRegisterFltMgrCalls(FsrtlFltMgrCallbacks);
  dword_18003E750 |= 0x102u;
  memset(SystemRoutineName, 0, sizeof(SystemRoutineName));
  dword_18003E9F0 = 5;
  qword_18003E9F4 = 15;
  dword_18003EA00 = 18432;
  McGenEventRegisterContext_EtwRegister_EtwSetInformation();
  FltpReadDriverParameters(RegistryPath);
  McGenEventRegister_EtwRegister();
  v5 = (unsigned int)EtwRegister(&PROV_FLTMGR, 0, 0, &qword_18003E758);
  if ( (int)FltpDbgStatus(v5, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 993, 0) >= 0 )
  {
    EtwSetInformation(qword_18003E758, EventProviderSetTraits, EventInformation, LOWORD(EventInformation[0]));
  }
  else
  {
    if ( (byte_1800404C1 & 0x40) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v6, fltmgr_c995, "DriverEntry", (unsigned int)v5);
    qword_18003E758 = 0;
  }
  started = (unsigned int)FltpStartRegWatch();
  if ( (int)FltpDbgStatus(started, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1030, 0) < 0 )
  {
    if ( (byte_1800404C1 & 0x40) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v8, fltmgr_c1032, "DriverEntry", (unsigned int)started);
    FltpUpdateDynamicRegistrySettings(&FltpDynamicConfigRegWatchContext);
  }
  ::DriverObject = DriverObject;
  dword_18003E760 = KeQueryActiveProcessorCountEx(0xFFFFu);
  dword_18003E764 = KeGetRecommendedSharedDataAlignment();
  ::DestinationString = 0;
  ::DestinationString.MaximumLength = 320;
  dword_18003E768 = -dword_18003E764 & (dword_18003E764 + 47);
  ::DestinationString.Buffer = (wchar_t *)qword_18003E860;
  RtlCopyUnicodeString(&::DestinationString, RegistryPath);
  *(_QWORD *)SystemRoutineName = retaddr;
  *(_QWORD *)&SystemRoutineName[8] = 0;
  v9 = KeExpandKernelStackAndCalloutEx(FltpMeasureExpandedStackCalloutDepthCallout, SystemRoutineName, 0x6000u, 0, 0);
  FltpDbgStatus(v9, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 13517, 0);
  Device = (unsigned int)IoCreateDevice(
                           DriverObject,
                           0,
                           (PUNICODE_STRING)&FltMgrDeviceName,
                           8u,
                           0x100u,
                           0,
                           &DeviceObject);
  if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1186, 0) < 0 )
  {
    if ( (byte_1800404C1 & 0x40) == 0 )
      goto LABEL_57;
    v12 = fltmgr_c1188;
LABEL_56:
    McTemplateU0sd_EtwWriteTransfer(v11, v12, "DriverEntry", (unsigned int)Device);
    goto LABEL_57;
  }
  RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\FltMgr");
  v13 = IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)&FltMgrDeviceName);
  if ( (int)FltpDbgStatus(v13, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1205, 0) < 0 )
  {
    IoDeleteSymbolicLink(&DestinationString);
    Device = (unsigned int)IoCreateSymbolicLink(&DestinationString, (PUNICODE_STRING)&FltMgrDeviceName);
    if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1216, 0) < 0 )
    {
      if ( (byte_1800404C1 & 0x40) == 0 )
        goto LABEL_57;
      v12 = fltmgr_c1218;
      goto LABEL_56;
    }
  }
  DeviceObject->DeviceExtension = 0;
  TraceInformation = (unsigned int)WmiQueryTraceInformation(FltIoNotifyRoutinesClass, &qword_18003FD98, 8u, 0, 0);
  if ( (int)FltpDbgStatus(TraceInformation, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1267, 0) < 0 )
  {
    if ( (byte_1800404C2 & 2) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v15, fltmgr_c1269, "DriverEntry", (unsigned int)TraceInformation);
    qword_18003FD98 = (__int64)qword_18003FDA0;
  }
  TlgRegisterAggregateProvider();
  KeQueryPerformanceCounter(&PerformanceFrequency);
  IsMobileOS = FsRtlIsMobileOS();
  v17 = FltpTelemetryInitInstance;
  if ( !IsMobileOS )
    v17 = FltpMeasureInitInstance;
  FltpLogInitInstanceFunction = (__int64)v17;
  v18 = FltpTelemetryFreeInstance;
  if ( !IsMobileOS )
    v18 = FltpMeasureFreeInstance;
  FltpLogFreeInstanceFunction = (__int64)v18;
  FltpInitializeIoPerf();
  FltpInitializeIoPerfCheckpoint();
  memset64(DriverObject->MajorFunction, (unsigned __int64)FltpDispatch, 0x1Cu);
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&FltpCreate;
  DriverObject->MajorFunction[1] = (PDRIVER_DISPATCH)&FltpCreate;
  DriverObject->MajorFunction[19] = (PDRIVER_DISPATCH)&FltpCreate;
  DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)FltpFsControl;
  Pool2 = (struct _FAST_IO_DISPATCH *)ExAllocatePool2(64, 224, 1768312134);
  if ( !Pool2 )
  {
    LODWORD(Device) = -1073741670;
    goto LABEL_57;
  }
  Pool2->SizeOfFastIoDispatch = 224;
  Pool2->FastIoCheckIfPossible = (PFAST_IO_CHECK_IF_POSSIBLE)FltpFastIoCheckIfPossible;
  Pool2->FastIoRead = (PFAST_IO_READ)FltpFastIoRead;
  Pool2->FastIoWrite = (PFAST_IO_WRITE)FltpFastIoWrite;
  Pool2->FastIoQueryBasicInfo = (PFAST_IO_QUERY_BASIC_INFO)FltpFastIoQueryBasicInfo;
  Pool2->FastIoQueryStandardInfo = (PFAST_IO_QUERY_STANDARD_INFO)FltpFastIoQueryStandardInfo;
  Pool2->FastIoLock = (PFAST_IO_LOCK)FltpFastIoLock;
  Pool2->FastIoUnlockSingle = (PFAST_IO_UNLOCK_SINGLE)FltpFastIoUnlockSingle;
  Pool2->FastIoUnlockAll = (PFAST_IO_UNLOCK_ALL)FltpFastIoUnlockAll;
  Pool2->FastIoUnlockAllByKey = (PFAST_IO_UNLOCK_ALL_BY_KEY)FltpFastIoUnlockAllByKey;
  Pool2->FastIoDeviceControl = (PFAST_IO_DEVICE_CONTROL)FltpFastIoDeviceControl;
  Pool2->FastIoDetachDevice = (PFAST_IO_DETACH_DEVICE)FltpFastIoDetachDevice;
  Pool2->FastIoQueryNetworkOpenInfo = (PFAST_IO_QUERY_NETWORK_OPEN_INFO)FltpFastIoQueryNetworkOpenInfo;
  Pool2->FastIoQueryOpen = (PFAST_IO_QUERY_OPEN)FltpFastIoQueryOpen;
  Pool2->MdlRead = (PFAST_IO_MDL_READ)FltpFastIoMdlRead;
  Pool2->MdlReadComplete = (PFAST_IO_MDL_READ_COMPLETE)FltpFastIoMdlReadComplete;
  Pool2->PrepareMdlWrite = (PFAST_IO_PREPARE_MDL_WRITE)FltpFastIoPrepareMdlWrite;
  Pool2->MdlWriteComplete = (PFAST_IO_MDL_WRITE_COMPLETE)FltpFastIoMdlWriteComplete;
  Pool2->FastIoReadCompressed = (PFAST_IO_READ_COMPRESSED)FltpFastIoReadCompressed;
  Pool2->FastIoWriteCompressed = (PFAST_IO_WRITE_COMPRESSED)FltpFastIoWriteCompressed;
  Pool2->MdlReadCompleteCompressed = (PFAST_IO_MDL_READ_COMPLETE_COMPRESSED)FltpFastIoMdlReadCompleteCompressed;
  Pool2->MdlWriteCompleteCompressed = (PFAST_IO_MDL_WRITE_COMPLETE_COMPRESSED)FltpFastIoMdlWriteCompleteCompressed;
  DriverObject->FastIoDispatch = Pool2;
  Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.PreReleaseForSectionSynchronization = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.PreAcquireForCcFlush = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.PreReleaseForCcFlush = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.PreAcquireForModifiedPageWriter = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.PreReleaseForModifiedPageWriter = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.PreQueryOpen = (PFS_FILTER_CALLBACK)FltpPreFsFilterOperation;
  Callbacks.SizeOfFsFilterCallbacks = 120;
  Callbacks.PostAcquireForSectionSynchronization = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Callbacks.PostReleaseForSectionSynchronization = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Callbacks.PostAcquireForCcFlush = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Callbacks.PostReleaseForCcFlush = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Callbacks.PostAcquireForModifiedPageWriter = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Callbacks.PostReleaseForModifiedPageWriter = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Callbacks.PostQueryOpen = (PFS_FILTER_COMPLETION_CALLBACK)&FltpPostFsFilterOperation;
  Device = (unsigned int)FsRtlRegisterFileSystemFilterCallbacks(DriverObject, &Callbacks);
  if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1394, 0) >= 0 )
  {
    Device = (unsigned int)FltpInitializeMessagingSupport(DriverObject);
    if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1405, 0) < 0 )
    {
      if ( (byte_1800404C1 & 0x40) == 0 )
        goto LABEL_57;
      v12 = fltmgr_c1411;
      goto LABEL_56;
    }
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    KeInitializeEvent(&stru_18003FE98, NotificationEvent, 0);
    qword_18003FEB0 = ExAllocateTimer(0, 0, 8);
    if ( qword_18003FEB0 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 512;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      *(_QWORD *)SystemRoutineName = 0;
      Device = (unsigned int)PsCreateSystemThread(
                               (PHANDLE)SystemRoutineName,
                               0x1FFFFFu,
                               &ObjectAttributes,
                               0,
                               0,
                               FltpNamePurgeWorker,
                               0);
      if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1461, 0) < 0 )
      {
        if ( (byte_1800404C1 & 0x40) == 0 )
          goto LABEL_57;
        v12 = fltmgr_c1474;
        goto LABEL_56;
      }
      v21 = ObReferenceObjectByHandle(*(HANDLE *)SystemRoutineName, 0x1FFFFFu, 0, 0, &Object, 0);
      FltpDbgStatus(v21, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1468, 0);
      ZwClose(*(HANDLE *)SystemRoutineName);
      FltpBuildParameterOffsetTable();
      v22 = (unsigned int)FltpInitializeVerifier();
      if ( (int)FltpDbgStatus(v22, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1495, 0) < 0 )
      {
        if ( (_DWORD)v22 == -1073738636 )
        {
          DbgPrintEx(0x2Fu, 2u, "[FltMgr] Filter Verifier not enabled for this boot session.\n");
        }
        else
        {
          if ( (byte_1800404C1 & 0x40) != 0 )
            McTemplateU0sd_EtwWriteTransfer(v23, fltmgr_c1510, "DriverEntry", (unsigned int)v22);
          if ( (_DWORD)v22 == -1073738635 )
            DbgPrintEx(
              0x2Fu,
              0,
              "[FltMgr] Filter Verifier DISABLED: ntoskrnl verification disables driver verification.\n");
          else
            DbgPrintEx(0x2Fu, 0, "[FltMgr] Filter Verifier DISABLED: 0x%08x\n", v22);
          DbgPrintEx(0x2Fu, 0, "[FltMgr] No minifilters will be verified.\n");
        }
      }
      else
      {
        DbgPrintEx(0x2Fu, 2u, "[FltMgr] Filter Verifier initialized successfully.\n");
      }
      KeInitializeSpinLock(&SpinLock);
      v24 = 0;
      v25 = 0;
      do
      {
        FltGlobals[v25 / 4 + 1406] = 0;
        FltGlobals[v25 / 4 + 1407] = 10;
        *(_QWORD *)&FltGlobals[v25 / 4 + 1404] = &qword_18003FD28[v25 / 8];
        ++v24;
        *(_QWORD *)&FltGlobals[v25 / 4 + 1402] = &qword_18003FD28[v25 / 8];
        v25 += 24LL;
      }
      while ( v24 != 3 );
      dword_18003E818 = 1;
      dword_18003FD54 = 30;
      dword_18003FD3C = 30;
      qword_18003E820 = 0;
      dword_18003E828 = 0;
      KeInitializeEvent(&stru_18003E830, SynchronizationEvent, 0);
      Device = (unsigned int)FltpCompletePhase2Init();
      if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1555, 0) >= 0 )
      {
        KeEnterCriticalRegion();
        LOBYTE(v26) = 1;
        ExAcquireFastResourceExclusive(qword_18003E798, 0, v26);
        LODWORD(Device) = FltpAttachFrame(&FrameZeroAltitude, SystemRoutineName);
        ExReleaseFastResource(qword_18003E798, 0);
        KeLeaveCriticalRegion();
        FltpDbgStatus((unsigned int)Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1570, 0);
      }
    }
    else
    {
      LODWORD(Device) = -1073741670;
      if ( (byte_1800404C1 & 0x40) != 0 )
        McTemplateU0s_EtwWriteTransfer(v20, fltmgr_c1438, "DriverEntry");
    }
  }
LABEL_57:
  if ( (int)FltpDbgStatus((unsigned int)Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1577, 0) >= 0 )
  {
    IoRegisterDriverReinitialization(DriverObject, FltpDriverReinitialization, 0);
  }
  else
  {
    if ( Object )
    {
      KeSetEvent(&stru_18003FE98, 0, 0);
      KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      Object = 0;
    }
    if ( qword_18003FEB0 )
    {
      LOBYTE(v27) = 1;
      memset(SystemRoutineName, 0, sizeof(SystemRoutineName));
      ExDeleteTimer(qword_18003FEB0, v27, 0, SystemRoutineName);
      qword_18003FEB0 = 0;
    }
    FastIoDispatch = DriverObject->FastIoDispatch;
    if ( FastIoDispatch )
    {
      ExFreePoolWithTag(FastIoDispatch, 0);
      DriverObject->FastIoDispatch = 0;
    }
    if ( DeviceObject )
      IoDeleteDevice(DeviceObject);
    RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\FltMgr");
    IoDeleteSymbolicLink(&DestinationString);
    dword_18003E750 &= ~1u;
    if ( qword_18003E758 )
      EtwUnregister(qword_18003E758);
    if ( g_wil_details_featureChangeNotification )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      g_wil_details_featureChangeNotification = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
  }
  return Device;
}

```

## disassembly

```asm
0x180089078  mov     [rsp-8+arg_10], rbx
0x18008907d  push    rbp
0x18008907e  push    rsi
0x18008907f  push    rdi
0x180089080  push    r14
0x180089082  push    r15
0x180089084  lea     rbp, [rsp-40h]
0x180089089  sub     rsp, 140h
0x180089090  mov     rax, cs:__security_cookie
0x180089097  xor     rax, rsp
0x18008909a  mov     [rbp+60h+var_28], rax
0x18008909e  mov     r14, rdx
0x1800890a1  mov     rbx, rcx
0x1800890a4  xor     edx, edx; Val
0x1800890a6  lea     rcx, [rbp+60h+Callbacks]; void *
0x1800890aa  xorps   xmm0, xmm0
0x1800890ad  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1800890b2  lea     r8d, [rdx+78h]; Size
0x1800890b6  call    memset
0x1800890bb  call    wil_InitializeFeatureStaging
0x1800890c0  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x1800890c7  mov     qword ptr [rsp+160h+SystemRoutineName], 320030h
0x1800890d0  xor     r15d, r15d
0x1800890d3  mov     qword ptr [rsp+160h+SystemRoutineName+8], rax
0x1800890d8  lea     rcx, [rsp+160h+SystemRoutineName]; SystemRoutineName
0x1800890dd  mov     cs:FltpVelocity, r15b
0x1800890e4  mov     [rsp+160h+var_120], r15b
0x1800890e9  call    cs:__imp_MmGetSystemRoutineAddress
0x1800890f0  nop     dword ptr [rax+rax+00h]
0x1800890f5  test    rax, rax
0x1800890f8  jz      short loc_180089122
0x1800890fa  xor     r9d, r9d
0x1800890fd  lea     r8d, [r15+1]
0x180089101  lea     rdx, [rsp+160h+var_120]
0x180089106  mov     ecx, 0E3h
0x18008910b  call    _guard_dispatch_icall
0x180089110  test    eax, eax
0x180089112  js      short loc_180089122
0x180089114  cmp     [rsp+160h+var_120], r15b
0x180089119  jz      short loc_180089122
0x18008911b  mov     cs:ExPoolZeroingNativelySupported, 1
0x180089122  xor     edx, edx; Val
0x180089124  mov     cs:ExDefaultNonPagedPoolType, 200h
0x18008912e  mov     r8d, 1780h; Size
0x180089134  mov     cs:ExDefaultMdlProtection, 40000000h
0x18008913e  lea     rcx, FltGlobals; void *
0x180089145  mov     [rbp+60h+EventInformation], 13000016h
0x18008914c  mov     [rbp+60h+var_3C], 731A0100h
0x180089153  mov     [rbp+60h+var_38], 89CF4F50h
0x18008915a  mov     [rbp+60h+var_34], 0E0B34782h
0x180089161  mov     [rbp+60h+var_30], 4C9E8DCh
0x180089168  mov     [rbp+60h+var_2C], 0BA76h
0x18008916e  call    memset
0x180089173  lea     rcx, FsrtlFltMgrCallbacks
0x18008917a  mov     cs:dword_18003E750, 1
0x180089184  call    cs:__imp_FsRtlRegisterFltMgrCalls
0x18008918b  nop     dword ptr [rax+rax+00h]
0x180089190  or      cs:dword_18003E750, 102h
0x18008919a  xorps   xmm0, xmm0
0x18008919d  movups  xmmword ptr [rsp+160h+SystemRoutineName+8], xmm0
0x1800891a2  mov     qword ptr [rsp+160h+SystemRoutineName], r15
0x1800891a7  mov     cs:dword_18003E9F0, 5
0x1800891b1  mov     cs:qword_18003E9F4, 0Fh
0x1800891bc  mov     cs:dword_18003EA00, 4800h
0x1800891c6  call    McGenEventRegisterContext_EtwRegister_EtwSetInformation
0x1800891cb  mov     rcx, r14
0x1800891ce  call    FltpReadDriverParameters
0x1800891d3  call    McGenEventRegister_EtwRegister
0x1800891d8  lea     r9, qword_18003E758; RegHandle
0x1800891df  xor     r8d, r8d; CallbackContext
0x1800891e2  xor     edx, edx; EnableCallback
0x1800891e4  lea     rcx, PROV_FLTMGR; ProviderId
0x1800891eb  call    cs:__imp_EtwRegister
0x1800891f2  nop     dword ptr [rax+rax+00h]
0x1800891f7  lea     rsi, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800891fe  mov     r8d, 3E1h
0x180089204  mov     rdx, rsi
0x180089207  mov     ecx, eax
0x180089209  xor     r9d, r9d
0x18008920c  mov     edi, eax
0x18008920e  call    FltpDbgStatus
0x180089213  test    eax, eax
0x180089215  jns     short loc_18008923F
0x180089217  test    cs:byte_1800404C1, 40h
0x18008921e  jz      short loc_180089236
0x180089220  mov     r9d, edi
0x180089223  lea     r8, aDriverentry; "DriverEntry"
0x18008922a  lea     rdx, fltmgr_c995
0x180089231  call    McTemplateU0sd_EtwWriteTransfer
0x180089236  mov     cs:qword_18003E758, r15
0x18008923d  jmp     short loc_180089260
0x18008923f  movzx   r9d, word ptr [rbp+60h+EventInformation]; InformationLength
0x180089244  lea     r8, [rbp+60h+EventInformation]; EventInformation
0x180089248  mov     rcx, cs:qword_18003E758; RegHandle
0x18008924f  mov     edx, 2; InformationClass
0x180089254  call    cs:__imp_EtwSetInformation
0x18008925b  nop     dword ptr [rax+rax+00h]
0x180089260  call    FltpStartRegWatch
0x180089265  mov     r8d, 406h
0x18008926b  xor     r9d, r9d
0x18008926e  mov     rdx, rsi
0x180089271  mov     ecx, eax
0x180089273  mov     edi, eax
0x180089275  call    FltpDbgStatus
0x18008927a  test    eax, eax
0x18008927c  jns     short loc_1800892A9
0x18008927e  test    cs:byte_1800404C1, 40h
0x180089285  jz      short loc_18008929D
0x180089287  mov     r9d, edi
0x18008928a  lea     r8, aDriverentry; "DriverEntry"
0x180089291  lea     rdx, fltmgr_c1032
0x180089298  call    McTemplateU0sd_EtwWriteTransfer
0x18008929d  lea     rcx, FltpDynamicConfigRegWatchContext
0x1800892a4  call    FltpUpdateDynamicRegistrySettings
0x1800892a9  mov     ecx, 0FFFFh; GroupNumber
0x1800892ae  mov     cs:DriverObject, rbx
0x1800892b5  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1800892bc  nop     dword ptr [rax+rax+00h]
0x1800892c1  mov     cs:dword_18003E760, eax
0x1800892c7  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1800892ce  nop     dword ptr [rax+rax+00h]
0x1800892d3  mov     cs:dword_18003E764, eax
0x1800892d9  xorps   xmm0, xmm0
0x1800892dc  mov     rdx, r14; SourceString
0x1800892df  movups  xmmword ptr cs:DestinationString.Length, xmm0
0x1800892e6  lea     ecx, [rax+2Fh]
0x1800892e9  neg     eax
0x1800892eb  and     ecx, eax
0x1800892ed  mov     eax, 140h
0x1800892f2  mov     cs:DestinationString.MaximumLength, ax
0x1800892f9  lea     rax, qword_18003E860
0x180089300  mov     cs:dword_18003E768, ecx
0x180089306  lea     rcx, DestinationString; DestinationString
0x18008930d  mov     cs:DestinationString.Buffer, rax
0x180089314  call    cs:__imp_RtlCopyUnicodeString
0x18008931b  nop     dword ptr [rax+rax+00h]
0x180089320  mov     rax, [rbp+68h]
0x180089324  lea     rdx, [rsp+160h+SystemRoutineName]; Parameter
0x180089329  xor     r9d, r9d; Wait
0x18008932c  mov     qword ptr [rsp+160h+SystemRoutineName], rax
0x180089331  mov     r8d, 6000h; Size
0x180089337  mov     qword ptr [rsp+160h+SystemRoutineName+8], r15
0x18008933c  lea     rcx, FltpMeasureExpandedStackCalloutDepthCallout; Callout
0x180089343  mov     [rsp+160h+Context], r15; Context
0x180089348  mov     edi, 34CDh
0x18008934d  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x180089354  nop     dword ptr [rax+rax+00h]
0x180089359  xor     r9d, r9d
0x18008935c  mov     r8d, edi
0x18008935f  mov     ecx, eax
0x180089361  mov     rdx, rsi
0x180089364  call    FltpDbgStatus
0x180089369  lea     rax, DeviceObject
0x180089370  mov     r9d, 8; DeviceType
0x180089376  mov     [rsp+160h+DeviceObject], rax; DeviceObject
0x18008937b  lea     r14, FltMgrDeviceName
0x180089382  mov     [rsp+160h+Exclusive], r15b; Exclusive
0x180089387  mov     r8, r14; DeviceName
0x18008938a  xor     edx, edx; DeviceExtensionSize
0x18008938c  mov     dword ptr [rsp+160h+Context], 100h; DeviceCharacteristics
0x180089394  mov     rcx, rbx; DriverObject
0x180089397  call    cs:__imp_IoCreateDevice
0x18008939e  nop     dword ptr [rax+rax+00h]
0x1800893a3  mov     r8d, 4A2h
0x1800893a9  xor     r9d, r9d
0x1800893ac  mov     ecx, eax
0x1800893ae  mov     rdx, rsi
0x1800893b1  mov     edi, eax
0x1800893b3  call    FltpDbgStatus
0x1800893b8  test    eax, eax
0x1800893ba  jns     short loc_1800893D5
0x1800893bc  test    cs:byte_1800404C1, 40h
0x1800893c3  jz      loc_180089ABB
0x1800893c9  lea     rdx, fltmgr_c1188
0x1800893d0  jmp     loc_180089AAC
0x1800893d5  lea     rdx, aDosdevicesFltm_0; "\\DosDevices\\FltMgr"
0x1800893dc  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1800893e1  call    cs:__imp_RtlInitUnicodeString
0x1800893e8  nop     dword ptr [rax+rax+00h]
0x1800893ed  mov     rdx, r14; DeviceName
0x1800893f0  lea     rcx, [rsp+160h+DestinationString]; SymbolicLinkName
0x1800893f5  call    cs:__imp_IoCreateSymbolicLink
0x1800893fc  nop     dword ptr [rax+rax+00h]
0x180089401  mov     r8d, 4B5h
0x180089407  xor     r9d, r9d
0x18008940a  mov     ecx, eax
0x18008940c  mov     rdx, rsi
0x18008940f  call    FltpDbgStatus
0x180089414  test    eax, eax
0x180089416  jns     short loc_18008946F
0x180089418  lea     rcx, [rsp+160h+DestinationString]; SymbolicLinkName
0x18008941d  call    cs:__imp_IoDeleteSymbolicLink
0x180089424  nop     dword ptr [rax+rax+00h]
0x180089429  mov     rdx, r14; DeviceName
0x18008942c  lea     rcx, [rsp+160h+DestinationString]; SymbolicLinkName
0x180089431  call    cs:__imp_IoCreateSymbolicLink
0x180089438  nop     dword ptr [rax+rax+00h]
0x18008943d  mov     r8d, 4C0h
0x180089443  xor     r9d, r9d
0x180089446  mov     ecx, eax
0x180089448  mov     rdx, rsi
0x18008944b  mov     edi, eax
0x18008944d  call    FltpDbgStatus
0x180089452  test    eax, eax
0x180089454  jns     short loc_18008946F
0x180089456  test    cs:byte_1800404C1, 40h
0x18008945d  jz      loc_180089ABB
0x180089463  lea     rdx, fltmgr_c1218
0x18008946a  jmp     loc_180089AAC
0x18008946f  mov     rax, cs:DeviceObject
0x180089476  lea     rdx, qword_18003FD98; TraceInformation
0x18008947d  xor     r9d, r9d; RequiredLength
0x180089480  mov     [rsp+160h+Context], r15; Buffer
0x180089485  mov     [rax+40h], r15
0x180089489  lea     r14d, [r9+8]
0x18008948d  mov     r8d, r14d; TraceInformationLength
0x180089490  lea     ecx, [r9+0Dh]; TraceInformationClass
0x180089494  call    cs:__imp_WmiQueryTraceInformation
0x18008949b  nop     dword ptr [rax+rax+00h]
0x1800894a0  mov     r8d, 4F3h
0x1800894a6  xor     r9d, r9d
0x1800894a9  mov     ecx, eax
0x1800894ab  mov     rdx, rsi
0x1800894ae  mov     edi, eax
0x1800894b0  call    FltpDbgStatus
0x1800894b5  test    eax, eax
0x1800894b7  jns     short loc_1800894E6
0x1800894b9  test    cs:byte_1800404C2, 2
0x1800894c0  jz      short loc_1800894D8
0x1800894c2  mov     r9d, edi
0x1800894c5  lea     r8, aDriverentry; "DriverEntry"
0x1800894cc  lea     rdx, fltmgr_c1269
0x1800894d3  call    McTemplateU0sd_EtwWriteTransfer
0x1800894d8  lea     rax, qword_18003FDA0
0x1800894df  mov     cs:qword_18003FD98, rax
0x1800894e6  call    TlgRegisterAggregateProvider
0x1800894eb  lea     rcx, PerformanceFrequency; PerformanceFrequency
0x1800894f2  call    cs:__imp_KeQueryPerformanceCounter
0x1800894f9  nop     dword ptr [rax+rax+00h]
0x1800894fe  call    cs:__imp_FsRtlIsMobileOS
0x180089505  nop     dword ptr [rax+rax+00h]
0x18008950a  test    al, al
0x18008950c  lea     rdx, FltpMeasureInitInstance
0x180089513  lea     rcx, FltpTelemetryInitInstance
0x18008951a  cmovz   rcx, rdx
0x18008951e  lea     rdx, FltpMeasureFreeInstance
0x180089525  mov     cs:FltpLogInitInstanceFunction, rcx
0x18008952c  lea     rcx, FltpTelemetryFreeInstance
0x180089533  cmovz   rcx, rdx
0x180089537  mov     cs:FltpLogFreeInstanceFunction, rcx
0x18008953e  call    FltpInitializeIoPerf
0x180089543  call    FltpInitializeIoPerfCheckpoint
0x180089548  lea     rax, FltpDispatch
0x18008954f  mov     ecx, 1Ch
0x180089554  lea     rdi, [rbx+70h]
0x180089558  mov     r8d, 69664D46h
0x18008955e  rep stosq
0x180089561  lea     rax, FltpCreate
0x180089568  mov     edi, 0E0h
0x18008956d  mov     [rbx+70h], rax
0x180089571  mov     edx, edi
0x180089573  mov     [rbx+78h], rax
0x180089577  mov     ecx, 40h ; '@'
0x18008957c  mov     [rbx+108h], rax
0x180089583  lea     rax, FltpFsControl
0x18008958a  mov     [rbx+0D8h], rax
0x180089591  call    cs:__imp_ExAllocatePool2
0x180089598  nop     dword ptr [rax+rax+00h]
0x18008959d  test    rax, rax
0x1800895a0  jnz     short loc_1800895AC
0x1800895a2  mov     edi, 0C000009Ah
0x1800895a7  jmp     loc_180089ABB
0x1800895ac  mov     [rax], edi
0x1800895ae  lea     rcx, FltpFastIoCheckIfPossible
0x1800895b5  mov     [rax+8], rcx
0x1800895b9  lea     rdx, [rbp+60h+Callbacks]; Callbacks
0x1800895bd  lea     rcx, FltpFastIoRead
0x1800895c4  mov     [rax+10h], rcx
0x1800895c8  lea     rcx, FltpFastIoWrite
0x1800895cf  mov     [rax+18h], rcx
0x1800895d3  lea     rcx, FltpFastIoQueryBasicInfo
0x1800895da  mov     [rax+20h], rcx
0x1800895de  lea     rcx, FltpFastIoQueryStandardInfo
0x1800895e5  mov     [rax+28h], rcx
0x1800895e9  lea     rcx, FltpFastIoLock
0x1800895f0  mov     [rax+30h], rcx
0x1800895f4  lea     rcx, FltpFastIoUnlockSingle
0x1800895fb  mov     [rax+38h], rcx
0x1800895ff  lea     rcx, FltpFastIoUnlockAll
0x180089606  mov     [rax+40h], rcx
0x18008960a  lea     rcx, FltpFastIoUnlockAllByKey
0x180089611  mov     [rax+48h], rcx
0x180089615  lea     rcx, FltpFastIoDeviceControl
0x18008961c  mov     [rax+50h], rcx
0x180089620  lea     rcx, FltpFastIoDetachDevice
0x180089627  mov     [rax+68h], rcx
0x18008962b  lea     rcx, FltpFastIoQueryNetworkOpenInfo
0x180089632  mov     [rax+70h], rcx
0x180089636  lea     rcx, FltpFastIoQueryOpen
0x18008963d  mov     [rax+0C0h], rcx
  ... truncated ...
```
