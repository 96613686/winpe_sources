# DriverEntry

- ea: `0x18008c078`
- end: `0x18008cc57`
- name: `DriverEntry`
- size: `3039`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18008c010`

## callees

- `0x180009f20`
- `0x180014cf0`
- `0x180020180`
- `0x18002129c`
- `0x1800213a4`
- `0x180021ac4`
- `0x180021b30`
- `0x180024800`
- `0x1800248e0`
- `0x180024c40`
- `0x18004c008`
- `0x180051060`
- `0x180051b20`
- `0x180057dc4`
- `0x180077740`
- `0x18008c078`
- `0x18008ccec`
- `0x18008d130`
- `0x18008d2d8`
- `0x18008d618`
- `0x18008d978`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18008cb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008cb61`
- `ntoskrnl!ExAllocatePool2` at `0x18008c591`
- `ntoskrnl!ExAllocatePool2` at `0x18008c591`
- `ntoskrnl!KeInitializeEvent` at `0x18008c779`
- `ntoskrnl!KeInitializeEvent` at `0x18008c791`
- `ntoskrnl!KeInitializeEvent` at `0x18008ca01`
- `ntoskrnl!KeInitializeEvent` at `0x18008c779`
- `ntoskrnl!KeInitializeEvent` at `0x18008c791`
- `ntoskrnl!KeInitializeEvent` at `0x18008ca01`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008cb0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008cb0b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18008c314`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18008c314`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008c3e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cb95`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008c3e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008cb95`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008ca2f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18008ca2f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008ca7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18008ca7b`
- `ntoskrnl!ExReleaseFastResource` at `0x18008ca6f`
- `ntoskrnl!ExReleaseFastResource` at `0x18008ca6f`
- `ntoskrnl!IoCreateDevice` at `0x18008c397`
- `ntoskrnl!IoCreateDevice` at `0x18008c397`
- `ntoskrnl!IoDeleteDevice` at `0x18008cb7d`
- `ntoskrnl!IoDeleteDevice` at `0x18008cb7d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x18008c34d`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x18008c34d`
- `ntoskrnl!ZwClose` at `0x18008c8a7`
- `ntoskrnl!ZwClose` at `0x18008c8a7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18008c886`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18008c886`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x18008c2b5`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x18008c2b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x18008c97a`
- `ntoskrnl!KeInitializeSpinLock` at `0x18008c97a`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18008ca47`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18008ca47`
- `ntoskrnl!EtwSetInformation` at `0x18008c254`
- `ntoskrnl!EtwSetInformation` at `0x18008c254`
- `ntoskrnl!EtwRegister` at `0x18008c1eb`
- `ntoskrnl!EtwRegister` at `0x18008c1eb`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18008c0e9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18008c0e9`
- `ntoskrnl!FsRtlRegisterFltMgrCalls` at `0x18008c184`
- `ntoskrnl!FsRtlRegisterFltMgrCalls` at `0x18008c184`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x18008c2c7`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x18008c2c7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008c3f5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008c431`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008c3f5`
- `ntoskrnl!IoCreateSymbolicLink` at `0x18008c431`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x18008c41d`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x18008cba6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x18008c41d`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x18008cba6`
- `ntoskrnl!WmiQueryTraceInformation` at `0x18008c494`
- `ntoskrnl!WmiQueryTraceInformation` at `0x18008c494`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x18008c708`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x18008c708`
- `ntoskrnl!ExAllocateTimer` at `0x18008c7a4`
- `ntoskrnl!ExAllocateTimer` at `0x18008c7a4`
- `ntoskrnl!PsCreateSystemThread` at `0x18008c839`
- `ntoskrnl!PsCreateSystemThread` at `0x18008c839`
- `ntoskrnl!DbgPrintEx` at `0x18008c8f6`
- `ntoskrnl!DbgPrintEx` at `0x18008c937`
- `ntoskrnl!DbgPrintEx` at `0x18008c94f`
- `ntoskrnl!DbgPrintEx` at `0x18008c967`
- `ntoskrnl!DbgPrintEx` at `0x18008c8f6`
- `ntoskrnl!DbgPrintEx` at `0x18008c937`
- `ntoskrnl!DbgPrintEx` at `0x18008c94f`
- `ntoskrnl!DbgPrintEx` at `0x18008c967`
- `ntoskrnl!KeSetEvent` at `0x18008caeb`
- `ntoskrnl!KeSetEvent` at `0x18008caeb`
- `ntoskrnl!ExDeleteTimer` at `0x18008cb43`
- `ntoskrnl!ExDeleteTimer` at `0x18008cb43`
- `ntoskrnl!EtwUnregister` at `0x18008cbc5`
- `ntoskrnl!EtwUnregister` at `0x18008cbc5`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x18008cbfc`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x18008cbfc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x18008cbdd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x18008cbdd`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x18008cc25`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x18008cc25`
- `ntoskrnl!FsRtlIsMobileOS` at `0x18008c4fe`
- `ntoskrnl!FsRtlIsMobileOS` at `0x18008c4fe`
- `HAL!KeQueryPerformanceCounter` at `0x18008c4f2`
- `HAL!KeQueryPerformanceCounter` at `0x18008c4f2`

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
  *(_QWORD *)&SystemRoutineName[8] = L"ZwQuerySystemInformation";
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
  dword_18003ECD0 = 1;
  FsRtlRegisterFltMgrCalls(FsrtlFltMgrCallbacks);
  dword_18003ECD0 |= 0x102u;
  memset(SystemRoutineName, 0, sizeof(SystemRoutineName));
  dword_18003EF70 = 5;
  qword_18003EF74 = 15;
  dword_18003EF80 = 18432;
  McGenEventRegisterContext_EtwRegister_EtwSetInformation();
  FltpReadDriverParameters(RegistryPath);
  McGenEventRegister_EtwRegister();
  v5 = (unsigned int)EtwRegister(&PROV_FLTMGR, 0, 0, &qword_18003ECD8);
  if ( (int)FltpDbgStatus(v5, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 993, 0) >= 0 )
  {
    EtwSetInformation(qword_18003ECD8, EventProviderSetTraits, EventInformation, LOWORD(EventInformation[0]));
  }
  else
  {
    if ( (byte_180040A41 & 0x40) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v6, fltmgr_c995, "DriverEntry", (unsigned int)v5);
    qword_18003ECD8 = 0;
  }
  started = (unsigned int)FltpStartRegWatch();
  if ( (int)FltpDbgStatus(started, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1030, 0) < 0 )
  {
    if ( (byte_180040A41 & 0x40) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v8, fltmgr_c1032, "DriverEntry", (unsigned int)started);
    FltpUpdateDynamicRegistrySettings(&FltpDynamicConfigRegWatchContext);
  }
  ::DriverObject = DriverObject;
  dword_18003ECE0 = KeQueryActiveProcessorCountEx(0xFFFFu);
  dword_18003ECE4 = KeGetRecommendedSharedDataAlignment();
  ::DestinationString = 0;
  ::DestinationString.MaximumLength = 320;
  dword_18003ECE8 = -dword_18003ECE4 & (dword_18003ECE4 + 47);
  ::DestinationString.Buffer = (wchar_t *)qword_18003EDE0;
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
    if ( (byte_180040A41 & 0x40) == 0 )
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
      if ( (byte_180040A41 & 0x40) == 0 )
        goto LABEL_57;
      v12 = fltmgr_c1218;
      goto LABEL_56;
    }
  }
  DeviceObject->DeviceExtension = 0;
  TraceInformation = (unsigned int)WmiQueryTraceInformation(FltIoNotifyRoutinesClass, &qword_180040318, 8u, 0, 0);
  if ( (int)FltpDbgStatus(TraceInformation, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1267, 0) < 0 )
  {
    if ( (byte_180040A42 & 2) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v15, fltmgr_c1269, "DriverEntry", (unsigned int)TraceInformation);
    qword_180040318 = (__int64)qword_180040320;
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
      if ( (byte_180040A41 & 0x40) == 0 )
        goto LABEL_57;
      v12 = fltmgr_c1411;
      goto LABEL_56;
    }
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    KeInitializeEvent(&stru_180040418, NotificationEvent, 0);
    qword_180040430 = ExAllocateTimer(0, 0, 8);
    if ( qword_180040430 )
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
        if ( (byte_180040A41 & 0x40) == 0 )
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
          if ( (byte_180040A41 & 0x40) != 0 )
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
        *(_QWORD *)&FltGlobals[v25 / 4 + 1404] = &qword_1800402A8[v25 / 8];
        ++v24;
        *(_QWORD *)&FltGlobals[v25 / 4 + 1402] = &qword_1800402A8[v25 / 8];
        v25 += 24LL;
      }
      while ( v24 != 3 );
      dword_18003ED98 = 1;
      dword_1800402D4 = 30;
      dword_1800402BC = 30;
      qword_18003EDA0 = 0;
      dword_18003EDA8 = 0;
      KeInitializeEvent(&stru_18003EDB0, SynchronizationEvent, 0);
      Device = (unsigned int)FltpCompletePhase2Init();
      if ( (int)FltpDbgStatus(Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1555, 0) >= 0 )
      {
        KeEnterCriticalRegion();
        LOBYTE(v26) = 1;
        ExAcquireFastResourceExclusive(qword_18003ED18, 0, v26);
        LODWORD(Device) = FltpAttachFrame(&FrameZeroAltitude, SystemRoutineName);
        ExReleaseFastResource(qword_18003ED18, 0);
        KeLeaveCriticalRegion();
        FltpDbgStatus((unsigned int)Device, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 1570, 0);
      }
    }
    else
    {
      LODWORD(Device) = -1073741670;
      if ( (byte_180040A41 & 0x40) != 0 )
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
      KeSetEvent(&stru_180040418, 0, 0);
      KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      Object = 0;
    }
    if ( qword_180040430 )
    {
      LOBYTE(v27) = 1;
      memset(SystemRoutineName, 0, sizeof(SystemRoutineName));
      ExDeleteTimer(qword_180040430, v27, 0, SystemRoutineName);
      qword_180040430 = 0;
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
    dword_18003ECD0 &= ~1u;
    if ( qword_18003ECD8 )
      EtwUnregister(qword_18003ECD8);
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
0x18008c078  mov     [rsp-8+arg_10], rbx
0x18008c07d  push    rbp
0x18008c07e  push    rsi
0x18008c07f  push    rdi
0x18008c080  push    r14
0x18008c082  push    r15
0x18008c084  lea     rbp, [rsp-40h]
0x18008c089  sub     rsp, 140h
0x18008c090  mov     rax, cs:__security_cookie
0x18008c097  xor     rax, rsp
0x18008c09a  mov     [rbp+60h+var_28], rax
0x18008c09e  mov     r14, rdx
0x18008c0a1  mov     rbx, rcx
0x18008c0a4  xor     edx, edx; Val
0x18008c0a6  lea     rcx, [rbp+60h+Callbacks]; void *
0x18008c0aa  xorps   xmm0, xmm0
0x18008c0ad  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x18008c0b2  lea     r8d, [rdx+78h]; Size
0x18008c0b6  call    memset
0x18008c0bb  call    wil_InitializeFeatureStaging
0x18008c0c0  lea     rax, aZwquerysystemi; "ZwQuerySystemInformation"
0x18008c0c7  mov     qword ptr [rsp+160h+SystemRoutineName], 320030h
0x18008c0d0  xor     r15d, r15d
0x18008c0d3  mov     qword ptr [rsp+160h+SystemRoutineName+8], rax
0x18008c0d8  lea     rcx, [rsp+160h+SystemRoutineName]; SystemRoutineName
0x18008c0dd  mov     cs:FltpVelocity, r15b
0x18008c0e4  mov     [rsp+160h+var_120], r15b
0x18008c0e9  call    cs:__imp_MmGetSystemRoutineAddress
0x18008c0f0  nop     dword ptr [rax+rax+00h]
0x18008c0f5  test    rax, rax
0x18008c0f8  jz      short loc_18008C122
0x18008c0fa  xor     r9d, r9d
0x18008c0fd  lea     r8d, [r15+1]
0x18008c101  lea     rdx, [rsp+160h+var_120]
0x18008c106  mov     ecx, 0E3h
0x18008c10b  call    _guard_dispatch_icall
0x18008c110  test    eax, eax
0x18008c112  js      short loc_18008C122
0x18008c114  cmp     [rsp+160h+var_120], r15b
0x18008c119  jz      short loc_18008C122
0x18008c11b  mov     cs:ExPoolZeroingNativelySupported, 1
0x18008c122  xor     edx, edx; Val
0x18008c124  mov     cs:ExDefaultNonPagedPoolType, 200h
0x18008c12e  mov     r8d, 1780h; Size
0x18008c134  mov     cs:ExDefaultMdlProtection, 40000000h
0x18008c13e  lea     rcx, FltGlobals; void *
0x18008c145  mov     [rbp+60h+EventInformation], 13000016h
0x18008c14c  mov     [rbp+60h+var_3C], 731A0100h
0x18008c153  mov     [rbp+60h+var_38], 89CF4F50h
0x18008c15a  mov     [rbp+60h+var_34], 0E0B34782h
0x18008c161  mov     [rbp+60h+var_30], 4C9E8DCh
0x18008c168  mov     [rbp+60h+var_2C], 0BA76h
0x18008c16e  call    memset
0x18008c173  lea     rcx, FsrtlFltMgrCallbacks
0x18008c17a  mov     cs:dword_18003ECD0, 1
0x18008c184  call    cs:__imp_FsRtlRegisterFltMgrCalls
0x18008c18b  nop     dword ptr [rax+rax+00h]
0x18008c190  or      cs:dword_18003ECD0, 102h
0x18008c19a  xorps   xmm0, xmm0
0x18008c19d  movups  xmmword ptr [rsp+160h+SystemRoutineName+8], xmm0
0x18008c1a2  mov     qword ptr [rsp+160h+SystemRoutineName], r15
0x18008c1a7  mov     cs:dword_18003EF70, 5
0x18008c1b1  mov     cs:qword_18003EF74, 0Fh
0x18008c1bc  mov     cs:dword_18003EF80, 4800h
0x18008c1c6  call    McGenEventRegisterContext_EtwRegister_EtwSetInformation
0x18008c1cb  mov     rcx, r14
0x18008c1ce  call    FltpReadDriverParameters
0x18008c1d3  call    McGenEventRegister_EtwRegister
0x18008c1d8  lea     r9, qword_18003ECD8; RegHandle
0x18008c1df  xor     r8d, r8d; CallbackContext
0x18008c1e2  xor     edx, edx; EnableCallback
0x18008c1e4  lea     rcx, PROV_FLTMGR; ProviderId
0x18008c1eb  call    cs:__imp_EtwRegister
0x18008c1f2  nop     dword ptr [rax+rax+00h]
0x18008c1f7  lea     rsi, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18008c1fe  mov     r8d, 3E1h
0x18008c204  mov     rdx, rsi
0x18008c207  mov     ecx, eax
0x18008c209  xor     r9d, r9d
0x18008c20c  mov     edi, eax
0x18008c20e  call    FltpDbgStatus
0x18008c213  test    eax, eax
0x18008c215  jns     short loc_18008C23F
0x18008c217  test    cs:byte_180040A41, 40h
0x18008c21e  jz      short loc_18008C236
0x18008c220  mov     r9d, edi
0x18008c223  lea     r8, aDriverentry; "DriverEntry"
0x18008c22a  lea     rdx, fltmgr_c995
0x18008c231  call    McTemplateU0sd_EtwWriteTransfer
0x18008c236  mov     cs:qword_18003ECD8, r15
0x18008c23d  jmp     short loc_18008C260
0x18008c23f  movzx   r9d, word ptr [rbp+60h+EventInformation]; InformationLength
0x18008c244  lea     r8, [rbp+60h+EventInformation]; EventInformation
0x18008c248  mov     rcx, cs:qword_18003ECD8; RegHandle
0x18008c24f  mov     edx, 2; InformationClass
0x18008c254  call    cs:__imp_EtwSetInformation
0x18008c25b  nop     dword ptr [rax+rax+00h]
0x18008c260  call    FltpStartRegWatch
0x18008c265  mov     r8d, 406h
0x18008c26b  xor     r9d, r9d
0x18008c26e  mov     rdx, rsi
0x18008c271  mov     ecx, eax
0x18008c273  mov     edi, eax
0x18008c275  call    FltpDbgStatus
0x18008c27a  test    eax, eax
0x18008c27c  jns     short loc_18008C2A9
0x18008c27e  test    cs:byte_180040A41, 40h
0x18008c285  jz      short loc_18008C29D
0x18008c287  mov     r9d, edi
0x18008c28a  lea     r8, aDriverentry; "DriverEntry"
0x18008c291  lea     rdx, fltmgr_c1032
0x18008c298  call    McTemplateU0sd_EtwWriteTransfer
0x18008c29d  lea     rcx, FltpDynamicConfigRegWatchContext
0x18008c2a4  call    FltpUpdateDynamicRegistrySettings
0x18008c2a9  mov     ecx, 0FFFFh; GroupNumber
0x18008c2ae  mov     cs:DriverObject, rbx
0x18008c2b5  call    cs:__imp_KeQueryActiveProcessorCountEx
0x18008c2bc  nop     dword ptr [rax+rax+00h]
0x18008c2c1  mov     cs:dword_18003ECE0, eax
0x18008c2c7  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x18008c2ce  nop     dword ptr [rax+rax+00h]
0x18008c2d3  mov     cs:dword_18003ECE4, eax
0x18008c2d9  xorps   xmm0, xmm0
0x18008c2dc  mov     rdx, r14; SourceString
0x18008c2df  movups  xmmword ptr cs:DestinationString.Length, xmm0
0x18008c2e6  lea     ecx, [rax+2Fh]
0x18008c2e9  neg     eax
0x18008c2eb  and     ecx, eax
0x18008c2ed  mov     eax, 140h
0x18008c2f2  mov     cs:DestinationString.MaximumLength, ax
0x18008c2f9  lea     rax, qword_18003EDE0
0x18008c300  mov     cs:dword_18003ECE8, ecx
0x18008c306  lea     rcx, DestinationString; DestinationString
0x18008c30d  mov     cs:DestinationString.Buffer, rax
0x18008c314  call    cs:__imp_RtlCopyUnicodeString
0x18008c31b  nop     dword ptr [rax+rax+00h]
0x18008c320  mov     rax, [rbp+68h]
0x18008c324  lea     rdx, [rsp+160h+SystemRoutineName]; Parameter
0x18008c329  xor     r9d, r9d; Wait
0x18008c32c  mov     qword ptr [rsp+160h+SystemRoutineName], rax
0x18008c331  mov     r8d, 6000h; Size
0x18008c337  mov     qword ptr [rsp+160h+SystemRoutineName+8], r15
0x18008c33c  lea     rcx, FltpMeasureExpandedStackCalloutDepthCallout; Callout
0x18008c343  mov     [rsp+160h+Context], r15; Context
0x18008c348  mov     edi, 34CDh
0x18008c34d  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x18008c354  nop     dword ptr [rax+rax+00h]
0x18008c359  xor     r9d, r9d
0x18008c35c  mov     r8d, edi
0x18008c35f  mov     ecx, eax
0x18008c361  mov     rdx, rsi
0x18008c364  call    FltpDbgStatus
0x18008c369  lea     rax, DeviceObject
0x18008c370  mov     r9d, 8; DeviceType
0x18008c376  mov     [rsp+160h+DeviceObject], rax; DeviceObject
0x18008c37b  lea     r14, FltMgrDeviceName
0x18008c382  mov     [rsp+160h+Exclusive], r15b; Exclusive
0x18008c387  mov     r8, r14; DeviceName
0x18008c38a  xor     edx, edx; DeviceExtensionSize
0x18008c38c  mov     dword ptr [rsp+160h+Context], 100h; DeviceCharacteristics
0x18008c394  mov     rcx, rbx; DriverObject
0x18008c397  call    cs:__imp_IoCreateDevice
0x18008c39e  nop     dword ptr [rax+rax+00h]
0x18008c3a3  mov     r8d, 4A2h
0x18008c3a9  xor     r9d, r9d
0x18008c3ac  mov     ecx, eax
0x18008c3ae  mov     rdx, rsi
0x18008c3b1  mov     edi, eax
0x18008c3b3  call    FltpDbgStatus
0x18008c3b8  test    eax, eax
0x18008c3ba  jns     short loc_18008C3D5
0x18008c3bc  test    cs:byte_180040A41, 40h
0x18008c3c3  jz      loc_18008CABB
0x18008c3c9  lea     rdx, fltmgr_c1188
0x18008c3d0  jmp     loc_18008CAAC
0x18008c3d5  lea     rdx, aDosdevicesFltm_0; "\\DosDevices\\FltMgr"
0x18008c3dc  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x18008c3e1  call    cs:__imp_RtlInitUnicodeString
0x18008c3e8  nop     dword ptr [rax+rax+00h]
0x18008c3ed  mov     rdx, r14; DeviceName
0x18008c3f0  lea     rcx, [rsp+160h+DestinationString]; SymbolicLinkName
0x18008c3f5  call    cs:__imp_IoCreateSymbolicLink
0x18008c3fc  nop     dword ptr [rax+rax+00h]
0x18008c401  mov     r8d, 4B5h
0x18008c407  xor     r9d, r9d
0x18008c40a  mov     ecx, eax
0x18008c40c  mov     rdx, rsi
0x18008c40f  call    FltpDbgStatus
0x18008c414  test    eax, eax
0x18008c416  jns     short loc_18008C46F
0x18008c418  lea     rcx, [rsp+160h+DestinationString]; SymbolicLinkName
0x18008c41d  call    cs:__imp_IoDeleteSymbolicLink
0x18008c424  nop     dword ptr [rax+rax+00h]
0x18008c429  mov     rdx, r14; DeviceName
0x18008c42c  lea     rcx, [rsp+160h+DestinationString]; SymbolicLinkName
0x18008c431  call    cs:__imp_IoCreateSymbolicLink
0x18008c438  nop     dword ptr [rax+rax+00h]
0x18008c43d  mov     r8d, 4C0h
0x18008c443  xor     r9d, r9d
0x18008c446  mov     ecx, eax
0x18008c448  mov     rdx, rsi
0x18008c44b  mov     edi, eax
0x18008c44d  call    FltpDbgStatus
0x18008c452  test    eax, eax
0x18008c454  jns     short loc_18008C46F
0x18008c456  test    cs:byte_180040A41, 40h
0x18008c45d  jz      loc_18008CABB
0x18008c463  lea     rdx, fltmgr_c1218
0x18008c46a  jmp     loc_18008CAAC
0x18008c46f  mov     rax, cs:DeviceObject
0x18008c476  lea     rdx, qword_180040318; TraceInformation
0x18008c47d  xor     r9d, r9d; RequiredLength
0x18008c480  mov     [rsp+160h+Context], r15; Buffer
0x18008c485  mov     [rax+40h], r15
0x18008c489  lea     r14d, [r9+8]
0x18008c48d  mov     r8d, r14d; TraceInformationLength
0x18008c490  lea     ecx, [r9+0Dh]; TraceInformationClass
0x18008c494  call    cs:__imp_WmiQueryTraceInformation
0x18008c49b  nop     dword ptr [rax+rax+00h]
0x18008c4a0  mov     r8d, 4F3h
0x18008c4a6  xor     r9d, r9d
0x18008c4a9  mov     ecx, eax
0x18008c4ab  mov     rdx, rsi
0x18008c4ae  mov     edi, eax
0x18008c4b0  call    FltpDbgStatus
0x18008c4b5  test    eax, eax
0x18008c4b7  jns     short loc_18008C4E6
0x18008c4b9  test    cs:byte_180040A42, 2
0x18008c4c0  jz      short loc_18008C4D8
0x18008c4c2  mov     r9d, edi
0x18008c4c5  lea     r8, aDriverentry; "DriverEntry"
0x18008c4cc  lea     rdx, fltmgr_c1269
0x18008c4d3  call    McTemplateU0sd_EtwWriteTransfer
0x18008c4d8  lea     rax, qword_180040320
0x18008c4df  mov     cs:qword_180040318, rax
0x18008c4e6  call    TlgRegisterAggregateProvider
0x18008c4eb  lea     rcx, PerformanceFrequency; PerformanceFrequency
0x18008c4f2  call    cs:__imp_KeQueryPerformanceCounter
0x18008c4f9  nop     dword ptr [rax+rax+00h]
0x18008c4fe  call    cs:__imp_FsRtlIsMobileOS
0x18008c505  nop     dword ptr [rax+rax+00h]
0x18008c50a  test    al, al
0x18008c50c  lea     rdx, FltpMeasureInitInstance
0x18008c513  lea     rcx, FltpTelemetryInitInstance
0x18008c51a  cmovz   rcx, rdx
0x18008c51e  lea     rdx, FltpMeasureFreeInstance
0x18008c525  mov     cs:FltpLogInitInstanceFunction, rcx
0x18008c52c  lea     rcx, FltpTelemetryFreeInstance
0x18008c533  cmovz   rcx, rdx
0x18008c537  mov     cs:FltpLogFreeInstanceFunction, rcx
0x18008c53e  call    FltpInitializeIoPerf
0x18008c543  call    FltpInitializeIoPerfCheckpoint
0x18008c548  lea     rax, FltpDispatch
0x18008c54f  mov     ecx, 1Ch
0x18008c554  lea     rdi, [rbx+70h]
0x18008c558  mov     r8d, 69664D46h
0x18008c55e  rep stosq
0x18008c561  lea     rax, FltpCreate
0x18008c568  mov     edi, 0E0h
0x18008c56d  mov     [rbx+70h], rax
0x18008c571  mov     edx, edi
0x18008c573  mov     [rbx+78h], rax
0x18008c577  mov     ecx, 40h ; '@'
0x18008c57c  mov     [rbx+108h], rax
0x18008c583  lea     rax, FltpFsControl
0x18008c58a  mov     [rbx+0D8h], rax
0x18008c591  call    cs:__imp_ExAllocatePool2
0x18008c598  nop     dword ptr [rax+rax+00h]
0x18008c59d  test    rax, rax
0x18008c5a0  jnz     short loc_18008C5AC
0x18008c5a2  mov     edi, 0C000009Ah
0x18008c5a7  jmp     loc_18008CABB
0x18008c5ac  mov     [rax], edi
0x18008c5ae  lea     rcx, FltpFastIoCheckIfPossible
0x18008c5b5  mov     [rax+8], rcx
0x18008c5b9  lea     rdx, [rbp+60h+Callbacks]; Callbacks
0x18008c5bd  lea     rcx, FltpFastIoRead
0x18008c5c4  mov     [rax+10h], rcx
0x18008c5c8  lea     rcx, FltpFastIoWrite
0x18008c5cf  mov     [rax+18h], rcx
0x18008c5d3  lea     rcx, FltpFastIoQueryBasicInfo
0x18008c5da  mov     [rax+20h], rcx
0x18008c5de  lea     rcx, FltpFastIoQueryStandardInfo
0x18008c5e5  mov     [rax+28h], rcx
0x18008c5e9  lea     rcx, FltpFastIoLock
0x18008c5f0  mov     [rax+30h], rcx
0x18008c5f4  lea     rcx, FltpFastIoUnlockSingle
0x18008c5fb  mov     [rax+38h], rcx
0x18008c5ff  lea     rcx, FltpFastIoUnlockAll
0x18008c606  mov     [rax+40h], rcx
0x18008c60a  lea     rcx, FltpFastIoUnlockAllByKey
0x18008c611  mov     [rax+48h], rcx
0x18008c615  lea     rcx, FltpFastIoDeviceControl
0x18008c61c  mov     [rax+50h], rcx
0x18008c620  lea     rcx, FltpFastIoDetachDevice
0x18008c627  mov     [rax+68h], rcx
0x18008c62b  lea     rcx, FltpFastIoQueryNetworkOpenInfo
0x18008c632  mov     [rax+70h], rcx
0x18008c636  lea     rcx, FltpFastIoQueryOpen
0x18008c63d  mov     [rax+0C0h], rcx
  ... truncated ...
```
