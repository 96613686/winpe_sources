# DriverEntry

- ea: `0x14034cc48`
- end: `0x14034e89b`
- name: `DriverEntry`
- size: `7251`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14034c010`

## callees

- `0x14008dbd0`
- `0x1400ac5ec`
- `0x1400ca788`
- `0x1400e1534`
- `0x1400ef8a0`
- `0x1400f45e8`
- `0x1400f4644`
- `0x1400f50b8`
- `0x1400f51e0`
- `0x1400f7f08`
- `0x1400fa3c4`
- `0x1400fa534`
- `0x1400fe510`
- `0x1400fea0c`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x1402c934c`
- `0x1402c94b8`
- `0x1402c9528`
- `0x1402c9ab0`
- `0x1402cc8e8`
- `0x1402cc97c`
- `0x14032bb14`
- `0x14034c090`
- `0x14034c36c`
- `0x14034cc48`
- `0x14034e8a4`
- `0x14034ea4c`
- `0x14034eaf4`
- `0x14034ebd8`
- `0x14034ed28`
- `0x14034ee14`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14034d0c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14034d0c0`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14034e729`
- `ntoskrnl!KeSetCoalescableTimer` at `0x14034e729`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14034d242`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14034d242`
- `ntoskrnl!IoCreateDevice` at `0x14034d0ee`
- `ntoskrnl!IoCreateDevice` at `0x14034d0ee`
- `ntoskrnl!KeInitializeSpinLock` at `0x14034e803`
- `ntoskrnl!KeInitializeSpinLock` at `0x14034e803`
- `ntoskrnl!RtlGetVersion` at `0x14034cce3`
- `ntoskrnl!RtlGetVersion` at `0x14034cce3`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14034ccf4`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14034ccf4`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14034cd24`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14034cd24`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x14034cd44`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x14034cd44`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14034cd65`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14034cd65`
- `ntoskrnl!MmLockPagableDataSection` at `0x14034ce7a`
- `ntoskrnl!MmLockPagableDataSection` at `0x14034ce7a`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x14034d162`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x14034d186`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x14034d162`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x14034d186`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x14034d41d`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x14034d439`
- `ntoskrnl!IoGetBootLayers` at `0x14034e4cf`
- `ntoskrnl!IoGetBootLayers` at `0x14034e4cf`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14034e549`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14034e549`
- `ntoskrnl!PcwRegister` at `0x14034e5c9`
- `ntoskrnl!PcwRegister` at `0x14034e5c9`
- `ntoskrnl!ExInitializeFastResource` at `0x14034cd9b`
- `ntoskrnl!ExInitializeFastResource` at `0x14034e5f6`
- `ntoskrnl!ExInitializeFastResource` at `0x14034cd9b`
- `ntoskrnl!ExInitializeFastResource` at `0x14034e5f6`
- `ntoskrnl!KeInitializeMutant` at `0x14034e661`
- `ntoskrnl!KeInitializeMutant` at `0x14034e661`
- `ntoskrnl!KeInitializeTimer` at `0x14034e6de`
- `ntoskrnl!KeInitializeTimer` at `0x14034e75f`
- `ntoskrnl!KeInitializeTimer` at `0x14034e6de`
- `ntoskrnl!KeInitializeTimer` at `0x14034e75f`
- `ntoskrnl!KeInitializeDpc` at `0x14034e6fe`
- `ntoskrnl!KeInitializeDpc` at `0x14034e77c`
- `ntoskrnl!KeInitializeDpc` at `0x14034e6fe`
- `ntoskrnl!KeInitializeDpc` at `0x14034e77c`
- `ntoskrnl!KeInitializeSemaphore` at `0x14034e7f0`
- `ntoskrnl!KeInitializeSemaphore` at `0x14034e7f0`
- `ntoskrnl!IoRegisterFileSystem` at `0x14034e82b`
- `ntoskrnl!IoRegisterFileSystem` at `0x14034e82b`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14034e844`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14034e844`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034cfc9`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034cfe8`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034cfc9`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034cfe8`
- `ntoskrnl!ExDeleteFastResource` at `0x14034cf34`
- `ntoskrnl!ExDeleteFastResource` at `0x14034cf34`
- `ntoskrnl!KeInitializeEvent` at `0x14034e679`
- `ntoskrnl!KeInitializeEvent` at `0x14034e679`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034cf62`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d009`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034cf62`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d009`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034d028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034e861`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14034ceb4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14034d1c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14034ceb4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14034d1c7`

## string_xrefs

- `0x14034cda7`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x14034d641`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x14034d743`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x14034e622`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x14034cdc0`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x14034d563`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x14034e60c`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x14034d503`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`
- `0x14034d56f`: `RefsDisableWriteThrough`
- `0x14034d65a`: `AllowOverAllocateOnVirtualMount`
- `0x14034db56`: `RefsDeferSMRWriteHeadQuery`
- `0x14034dd43`: `RefsDisableCachedPins`
- `0x14034dd93`: `RefsProcessedDeleteQueueEntryCountThreshold`
- `0x14034ddf3`: `RefsProcessedDeleteQueueThresholdBindable`
- `0x14034de4d`: `RefsDisableContainersCompaction`
- `0x14034df37`: `RefsLazyWriterWorkersPerVolume`
- `0x14034df84`: `RefsLazyWriterLogWorkersPerVolume`
- `0x14034dfd1`: `RefsLazyWriterWorkersTotal`
- `0x14034e01e`: `RefsLazyWriterLogWorkersTotal`
- `0x14034e06b`: `RefsLazyWriterScanThreshold`
- `0x14034e152`: `RefsBlockRefcountEmptyColdDelay`
- `0x14034e19f`: `RefsBlockRefcountCacheHighWaterMark`
- `0x14034e23c`: `RefsDisableWriteCombining`
- `0x14034e28c`: `RefsReallocateAllDataWrites`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  PVOID v4; // rdi
  int Directory; // ebx
  PVOID PoolWithTag; // rax
  unsigned int v7; // r9d
  unsigned int v9; // edx
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // r15d
  int v13; // eax
  unsigned int v14; // edi
  int v15; // ebx
  int v16; // ebx
  unsigned int v17; // esi
  unsigned int v18; // edx
  unsigned int v19; // edx
  unsigned int v20; // eax
  unsigned int v21; // edx
  unsigned int v22; // eax
  int v23; // eax
  int v24; // eax
  _DWORD *v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  PVOID v28; // rbx
  LONG v29; // edx
  unsigned __int8 v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v34; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v35; // [rsp+78h] [rbp-88h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+88h] [rbp-78h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+90h] [rbp-70h] BYREF
  ULONG CompressBufferWorkSpaceSize; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+F0h] [rbp-10h] BYREF
  char v44; // [rsp+170h] [rbp+70h] BYREF

  v32 = 156;
  OSVersionInfo.dwOSVersionInfoSize = 284;
  DeviceObject = 0;
  P = &v44;
  v30[0] = 0;
  v41 = 0;
  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize = 0;
  DestinationString = 0;
  v39 = 0;
  memset(&Info, 0, sizeof(Info));
  RtlGetVersion(&OSVersionInfo);
  RefsNumberProcessors = KeQueryActiveProcessorCountEx(0xFFFFu);
  RefsLastAccess = 36000000000LL;
  RtlGetCompressionWorkSpaceSize(2u, &CompressBufferWorkSpaceSize, &CompressFragmentWorkSpaceSize);
  memset(&RefsData, 0, 0x850u);
  FsRtlQueryMaximumVirtualDiskNestingLevel();
  RefsReserveStackStorage = 0;
  RefsReserveStackCleanup = 0;
  KeInitializeGuardedMutex(&stru_140261440);
  memset(&dword_1402613B8, 0, 0x80u);
  dword_1402613B8 = 18876484;
  ExInitializeFastResource(qword_1402613C8, 9);
  *(_QWORD *)&v35.Length = 6815846;
  v35.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
  *(_QWORD *)&v34.Length = 8126586;
  v34.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  *(_QWORD *)&v31.Length = 4194366;
  v31.Buffer = L"RefsForceNonPagedPoolAllocation";
  if ( RefsQueryValueKey(&v35, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) < 0
    && RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) < 0 )
  {
    v4 = P;
  }
  else
  {
    v4 = P;
    if ( !*(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
    {
      PoolType = PagedPool;
      dword_1402618CC = PagedPoolCacheAligned;
      goto LABEL_7;
    }
  }
  PoolType = 512;
  dword_1402618CC = 516;
  MmLockPagableDataSection(RefsCommonCreate);
LABEL_7:
  Directory = wil_InitializeFeatureStaging();
  if ( Directory < 0 )
  {
LABEL_16:
    ExDeleteFastResource(qword_1402613C8);
    memset(&dword_1402613B8, 0, 0x80u);
    if ( ::P )
    {
      ExFreePoolWithTag(::P, 0);
      ::P = 0;
    }
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_140261478);
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_140261490);
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402614A8);
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402614C0);
    MsKmeDeleteReservedIoRequests((struct _RESERVED_IO_REQUESTS *)qword_1402614D8);
    MsKmeDeleteReservedIoRuns((struct _RESERVED_IO_RUNS *)qword_1402616C8);
    if ( RefsReserveStackStorage )
    {
      KeFreeCalloutStack();
      RefsReserveStackStorage = 0;
    }
    if ( RefsReserveStackCleanup )
    {
      KeFreeCalloutStack();
      RefsReserveStackCleanup = 0;
    }
    if ( RefsRegistryPath.Buffer )
    {
      ExFreePoolWithTag(RefsRegistryPath.Buffer, 0);
      RefsRegistryPath.Buffer = 0;
    }
    if ( v30[0] )
      ExFreePoolWithTag(v4, 0);
    return Directory;
  }
  Feature_Servicing_ReFSStackSwapRead__private_IsEnabledPreCheck();
  RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled = 1;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x1000u, 0x4A666552u);
  ::P = PoolWithTag;
  if ( !PoolWithTag )
  {
    Directory = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids, 3221225626LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_16;
    v7 = 862;
    goto LABEL_15;
  }
  memset(PoolWithTag, 0, 0x1000u);
  Directory = RefsInitializeReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_140261478, 0x40000u);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_140261490, 0x44000u);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeReservedBuffer(
                (struct _REFS_BUFFER_AND_MDL *)&qword_1402614A8,
                CompressFragmentWorkSpaceSize);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402614C0, 0x40000u);
  if ( Directory < 0 )
    goto LABEL_16;
  RtlInitUnicodeString(&DestinationString, L"\\Refs");
  Directory = IoCreateDevice(DriverObject, 0, &DestinationString, 8u, 0, 0, &DeviceObject);
  if ( Directory < 0 )
    goto LABEL_16;
  DeviceObject->Flags |= 0x8000000u;
  Directory = MsKmeInitializeReservedIoRequests(DeviceObject, (struct _RESERVED_IO_REQUESTS *)qword_1402614D8, 20);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = MsKmeInitializeReservedIoRuns((struct _RESERVED_IO_RUNS *)qword_1402616C8, v9);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeQueryDirectory();
  if ( Directory < 0 )
    goto LABEL_16;
  LOBYTE(v10) = 3;
  Directory = KeAllocateCalloutStackEx(0, v10, 0, &RefsReserveStackStorage);
  if ( Directory < 0 )
    goto LABEL_16;
  LOBYTE(v11) = 1;
  Directory = KeAllocateCalloutStackEx(0, v11, 0, &RefsReserveStackCleanup);
  if ( Directory < 0 )
    goto LABEL_16;
  RefsRegistryPath.MaximumLength = RegistryPath->Length + 2;
  RefsRegistryPath.Length = RegistryPath->Length;
  RefsRegistryPath.Buffer = (PWSTR)ExAllocatePoolWithTag(
                                     (POOL_TYPE)(PoolType | 0x10),
                                     RefsRegistryPath.MaximumLength,
                                     0x4A666552u);
  if ( !RefsRegistryPath.Buffer )
  {
    Directory = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids, 3221225626LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_16;
    v7 = 999;
LABEL_15:
    RefsStatusDebug(-1073741670, 0, "NtfsInit.c", v7);
    goto LABEL_16;
  }
  v12 = 0;
  RtlCopyUnicodeString(&RefsRegistryPath, RegistryPath);
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[26] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[25] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[8] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[7] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[11] = (PDRIVER_DISPATCH)RefsFsdDispatch;
  DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)RefsFsdDispatch;
  DriverObject->MajorFunction[21] = (PDRIVER_DISPATCH)RefsFsdDispatch;
  DriverObject->MajorFunction[20] = (PDRIVER_DISPATCH)RefsFsdDispatch;
  DriverObject->MajorFunction[17] = (PDRIVER_DISPATCH)RefsFsdLockControl;
  DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)RefsFsdDirectoryControl;
  DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)RefsFsdSetInformation;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)RefsFsdCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)RefsFsdClose;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)RefsFsdRead;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)RefsFsdWrite;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)RefsFsdFlushBuffers;
  DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)RefsFsdFileSystemControl;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)RefsFsdCleanup;
  DriverObject->MajorFunction[16] = RefsFsdShutdown;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)RefsFsdPnp;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)RefsFsdDeviceControl;
  DriverObject->FastIoDispatch = &RefsFastIoDispatch;
  qword_140260948 = (__int64)RefsFastIoCheckIfPossible;
  qword_140260950 = (__int64)RefsCopyReadA;
  qword_140260958 = (__int64)RefsCopyWriteA;
  qword_140260960 = (__int64)&RefsFastQueryBasicInfo;
  qword_140260968 = (__int64)RefsFastQueryStdInfo;
  qword_140260970 = (__int64)RefsFastLock;
  qword_140260978 = (__int64)RefsFastUnlockSingle;
  qword_140260980 = (__int64)RefsFastUnlockAll;
  qword_140260988 = (__int64)RefsFastUnlockAllByKey;
  qword_1402609B0 = (__int64)&RefsFastQueryNetworkOpenInfo;
  qword_1402609A0 = (__int64)RefsReleaseForCreateSection;
  qword_1402609B8 = (__int64)RefsAcquireFileForModWrite;
  qword_140260A08 = (__int64)RefsReleaseFileForModWrite;
  qword_1402609C0 = (__int64)RefsMdlReadA;
  qword_1402609C8 = (__int64)FsRtlMdlReadCompleteDev;
  qword_1402609D0 = (__int64)RefsPrepareMdlWriteA;
  qword_1402609D8 = (__int64)FsRtlMdlWriteCompleteDev;
  RefsFastIoDispatch.SizeOfFastIoDispatch = 224;
  qword_140260990 = 0;
  qword_1402609A8 = 0;
  qword_140260998 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  qword_140260A00 = (__int64)RefsNetworkOpenCreate;
  qword_140260A10 = (__int64)RefsAcquireFileForCcFlush;
  qword_140260A18 = (__int64)RefsReleaseFileForCcFlush;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WppTrace;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids);
  }
  *(_QWORD *)&v34.Length = 7602290;
  v34.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT";
  v13 = RefsQueryValueKey(&v34, 0, 0, 0, 0);
  *(_QWORD *)&v34.Length = 8126586;
  *(_QWORD *)&v31.Length = 3145774;
  v14 = ((v13 >> 31) & 0xFFFFC000) + 0x4000;
  v34.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  v31.Buffer = L"RefsDisableWriteThrough";
  v15 = v14;
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
  {
    v15 = v14 | 1;
    if ( *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 1 )
      v15 = v14;
  }
  *(_QWORD *)&v31.Length = 2883626;
  v31.Buffer = L"RefsBugcheckOnCorrupt";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    v15 |= 0x10000u;
  }
  *(_QWORD *)&v31.Length = 3407922;
  v31.Buffer = L"RefsDisableDebugCodeFlags";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
  {
    v12 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  }
  *(_QWORD *)&v35.Length = 6815846;
  v35.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
  *(_QWORD *)&v31.Length = 4194366;
  v31.Buffer = L"AllowOverAllocateOnVirtualMount";
  v16 = v15 | 0x40000;
  v17 = v16;
  if ( RefsQueryValueKey(&v35, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) < 0 )
  {
    if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
      && !*(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
    {
      v17 = v16 & 0xFFFBFFFF;
    }
  }
  else
  {
    v17 = v16 & 0xFFFBFFFF;
    if ( *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
      v17 = v16;
  }
  Feature_ReFS_EFS__private_IsEnabledPreCheck();
  *(_QWORD *)&v31.Length = 4849736;
  v31.Buffer = L"NtfsEncryptPagingFileForGuardedHosts";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
  {
    v17 |= 0x18000000u;
  }
  if ( (v17 & 0x8000000) == 0 )
  {
    *(_QWORD *)&v35.Length = 6815846;
    v35.Buffer = (PWSTR)L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
    *(_QWORD *)&v31.Length = 2883626;
    v31.Buffer = L"NtfsDisableEncryption";
    if ( RefsQueryValueKey(&v35, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) < 0
      && RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) < 0
      || !*(_DWORD *)((char *)P + *((unsigned int *)P + 2)) )
    {
      v17 |= 0x8000000u;
    }
    if ( (v17 & 0x8000000) != 0 )
    {
      *(_QWORD *)&v31.Length = 2883626;
      v31.Buffer = L"NtfsEncryptPagingFile";
      if ( (RefsQueryValueKey(&v35, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
         || RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0)
        && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
      {
        v17 |= 0x10000000u;
      }
    }
  }
  *(_QWORD *)&v31.Length = 3145774;
  v31.Buffer = L"RefsEnableSMRSimulation";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsEnableSMRSimulation = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 3538996;
  v31.Buffer = L"RefsBandSizeOnSimulatedSMR";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsBandSizeOnSimulatedSMR = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 4194366;
  v31.Buffer = L"RefsCMRRegionSizeOnSimulatedSMR";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsCMRRegionOnSimulatedSMR = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3145774;
  v31.Buffer = L"RefsMakeAllFilesSMRBlob";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsMakeAllFilesSMRBlob = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 3276848;
  v31.Buffer = L"RefsDisableRedoLogReplay";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsDisableRedoLogReplay = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 4325440;
  v31.Buffer = L"RefsDisableThinProvisioningUnmap";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsDisableThinProvisioningUnmap = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 5242958;
  v31.Buffer = L"RefsDisableThinProvisioningProactiveMap";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsDisableThinProvisioningProactiveMap = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 4849736;
  v31.Buffer = L"RefsThinProvisioningMinHeadroomBytes";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsMinThinProvisioningHeadroomInBytes = *(_QWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 5242958;
  v31.Buffer = L"RefsThinProvisioningTargetHeadroomBytes";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsTargetThinProvisioningHeadroomInBytes = *(_QWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 4849736;
  v31.Buffer = L"RefsThinProvisioningMaxHeadroomBytes";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsMaxThinProvisioningHeadroomInBytes = *(_QWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3538996;
  v31.Buffer = L"RefsDeferSMRWriteHeadQuery";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsDeferSMRWriteHeadQuery = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 3014700;
  v31.Buffer = L"RefsFailUnorderedSMRIO";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsFailUnorderedSMRIO = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 4849736;
  v31.Buffer = L"RefsFullBandAllocationOnTieredVolume";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsFullBandAllocationOnTieredVolume = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
  *(_QWORD *)&v31.Length = 3932218;
  v31.Buffer = L"RefsEnableLargeWorkingSetTrim";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsEnableLargeWorkingSetTrim = 1;
  }
  *(_QWORD *)&v31.Length = 3276848;
  v31.Buffer = L"RefsNumberOfChunksToTrim";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
  {
    v18 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v18 )
    {
      RefsNumberOfChunksToTrim = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      if ( v18 > 0x200 )
        RefsNumberOfChunksToTrim = 512;
    }
  }
  *(_QWORD *)&v31.Length = 2752552;
  v31.Buffer = L"RefsEnableInlineTrim";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsEnableInlineTrim = 1;
  }
  *(_QWORD *)&v31.Length = 2883626;
  v31.Buffer = L"RefsDisableCachedPins";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsDisableCachedPins = 1;
  }
  *(_QWORD *)&v31.Length = 5767254;
  v31.Buffer = L"RefsProcessedDeleteQueueEntryCountThreshold";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
  {
    v19 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v19 )
    {
      v20 = 256;
      if ( v19 > 0x100 )
        v20 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      RefsProcessedDeleteQueueThresholdCheckpoint = v20;
    }
  }
  *(_QWORD *)&v31.Length = 5505106;
  v31.Buffer = L"RefsProcessedDeleteQueueThresholdBindable";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
  {
    v21 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( v21 )
    {
      v22 = 256;
      if ( v21 > 0x100 )
        v22 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      RefsProcessedDeleteQueueThresholdBindable = v22;
    }
  }
  *(_QWORD *)&v31.Length = 4194366;
  v31.Buffer = L"RefsDisableContainersCompaction";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsDisableContainersCompaction = 1;
  }
  *(_QWORD *)&v31.Length = 4325440;
  v31.Buffer = L"RefsAggresiveTableFlushThreshold";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsLazyWriterAggresiveBindableThreshold = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 5111884;
  v31.Buffer = L"RefsAlwaysCheckpointPageCountThreshold";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsAlwaysCheckpointPageCountThreshold = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 4063292;
  v31.Buffer = L"RefsLazyWriterWorkersPerVolume";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsLazyWriterWorkersPerVolume = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 4456514;
  v31.Buffer = L"RefsLazyWriterLogWorkersPerVolume";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsLazyWriterLogWorkersPerVolume = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3538996;
  v31.Buffer = L"RefsLazyWriterWorkersTotal";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsLazyWriterWorkersTotal = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3932218;
  v31.Buffer = L"RefsLazyWriterLogWorkersTotal";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsLazyWriterLogWorkersTotal = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3670070;
  v31.Buffer = L"RefsLazyWriterScanThreshold";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsLazyWriterScanThresholdPerVolume = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3670070;
  v31.Buffer = L"RefsBlockRefcountScanPeriod";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsBlockRefcountScanPeriod = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3538996;
  v31.Buffer = L"RefsBlockRefcountColdDelay";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsBlockRefcountColdDelay = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 4194366;
  v31.Buffer = L"RefsBlockRefcountEmptyColdDelay";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsBlockRefcountEmptyColdDelay = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 4718662;
  v31.Buffer = L"RefsBlockRefcountCacheHighWaterMark";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsBlockRefcountCacheHighWaterMark = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3407922;
  v31.Buffer = L"RefsDisableUserDataTriage";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsDisableUserDataTriage = 1;
  }
  *(_QWORD *)&v31.Length = 3407922;
  v31.Buffer = L"RefsDisableWriteCombining";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsDisableWriteCombining = 1;
  }
  *(_QWORD *)&v31.Length = 3670070;
  v31.Buffer = L"RefsReallocateAllDataWrites";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsReallocateAllDataWrites = 1;
  }
  *(_QWORD *)&v31.Length = 3932218;
  v31.Buffer = L"RefsEnableTrimOnAllMediaTypes";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsEnableTrimOnAllMediaTypes = 1;
  }
  *(_QWORD *)&v31.Length = 4456514;
  v31.Buffer = L"RefsDisableFlushAndTrimOnRotation";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsDisableFlushAndTrimOnRotation = 1;
  }
  *(_QWORD *)&v31.Length = 4325440;
  v31.Buffer = L"RefsRotationIOGranularityInBytes";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0 )
    RefsRotationIOGranularityInBytes = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  *(_QWORD *)&v31.Length = 3014700;
  v31.Buffer = L"RefsAssumeInvariantMdl";
  if ( RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30) >= 0
    && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
  {
    RefsAssumeInvariantMdl = 1;
  }
  *(_QWORD *)&v31.Length = 3538996;
  v31.Buffer = L"RefsCheckPageFailureAction";
  v23 = RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30);
  v4 = P;
  if ( v23 >= 0 && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) < 3u )
    RefsCheckPageFailureAction = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
  Directory = RefsLoadPreviousDriverVersionInfo();
  if ( Directory < 0 )
    goto LABEL_16;
  *(_QWORD *)&v31.Length = 3670070;
  v31.Buffer = L"RefsAsyncWeakReferenceBreak";
  v24 = RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30);
  v4 = P;
  if ( v24 >= 0 && *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) == 1 )
    RefsAsyncWeakReferenceBreak = 1;
  if ( (int)IoGetBootLayers(&v39) >= 0 )
  {
    if ( *(_DWORD *)v39 != 3
      || (*(_DWORD *)(v39 + 44) & 1) == 0
      || (v25 = *(_DWORD **)(v39 + 8), RefsEnableVolumeVerification = 1, *v25 != 1) )
    {
      RefsEnableVolumeVerification = 0;
    }
  }
  Directory = RefsInitializeRefsData(DriverObject, DeviceObject);
  if ( Directory < 0 )
    goto LABEL_16;
  FsLibInitialize();
  memset(&Callbacks, 0, sizeof(Callbacks));
  Callbacks.SizeOfFsFilterCallbacks = 120;
  Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)RefsFilterCallbackAcquireForCreateSection;
  Directory = FsRtlRegisterFileSystemFilterCallbacks(DriverObject, &Callbacks);
  if ( Directory < 0 )
    goto LABEL_16;
  LODWORD(dword_1402612AC) = v17 | (unsigned int)dword_1402612AC;
  dword_1402613B4 |= v12;
  McGenEventRegister_EtwRegister(RefsEventProvider, v26, &RefsEventProvider_Context, &RefsEventProvider_Context);
  RegHandle = RefsEventProvider_Context;
  *(_QWORD *)&Info.Version = 256;
  Info.Name = (PCUNICODE_STRING)L"\b\n";
  Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`RefsPcwInitRegistrationInformationCmsCounterSet'::`2'::Descriptors;
  *(_QWORD *)&Info.CounterCount = 61;
  v41 = 0;
  Info.Callback = 0;
  Info.CallbackContext = 0;
  if ( PcwRegister(&RefsPcwCmsCounterSet, &Info) < 0 )
    RefsPcwCmsCounterSet = 0;
  RefsInitializeSqm();
  RefsInitializeTelemetry();
  ExInitializeFastResource(&RefsDynamicRegistrySettingsResource, 8);
  RefsSetupWatchForRegistryChanges(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem",
    (void (*)(void *))RefsUpdateDynamicRegistrySettings,
    0);
  RefsSetupWatchForRegistryChanges(
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies",
    (void (*)(void *))RefsUpdateDynamicRegistrySettings,
    1u);
  RefsSetupSoftwareHiveDetection();
  RefsUpdateDynamicRegistrySettings(0);
  if ( IoPerfRegistryConfig )
  {
    byte_1402676A2 = 1;
    byte_1402676A0 = 1;
  }
  else
  {
    RefsInitializeIoPerf();
  }
  KeInitializeMutant(&StreamFileCreationMutex, 0);
  KeInitializeEvent(&RefsEncryptionPendingEvent, NotificationEvent, 1u);
  *(_OWORD *)&RefsZeroExtendedInfo = 0;
  xmmword_140260918 = 0;
  xmmword_140260928 = 0;
  Directory = RefsInitialize();
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeWellKnownAttributeRowKeys();
  if ( Directory < 0 )
    goto LABEL_16;
  stru_1402611D8.Parameter = 0;
  stru_1402611D8.WorkerRoutine = (PWORKER_THREAD_ROUTINE)RefsCheckUsnTimeOut;
  stru_1402611D8.List.Flink = 0;
  KeInitializeTimer(&Timer);
  KeInitializeDpc(&Dpc, RefsUsnTimeOutDpc, 0);
  KeSetCoalescableTimer(&Timer, (LARGE_INTEGER)-3000000000LL, 0, 0x3A98u, &Dpc);
  WorkItem.List.Flink = 0;
  WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)RefsPeriodicTimerCallback;
  WorkItem.Parameter = &WorkItem;
  KeInitializeTimer(&stru_140261238);
  KeInitializeDpc(&stru_1402611F8, RefsPeriodicTimerDpc, 0);
  *(_QWORD *)&v31.Length = 2621478;
  v31.Buffer = L"RefsGlobalPostLimit";
  v27 = RefsQueryValueKey(&v34, &v31, &v32, (struct _KEY_VALUE_FULL_INFORMATION **)&P, v30);
  v28 = P;
  if ( v27 < 0 || (v29 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)), v29 < 4) )
  {
    v29 = 4;
  }
  else if ( v29 > 200 )
  {
    v29 = 200;
  }
  KeInitializeSemaphore(&RefsGlobalPostThrottle, v29, v29);
  KeInitializeSpinLock(&RefsScavengerLock);
  RefsScavengerWorkList = 0;
  RefsScavengerRunning = 0;
  dword_14026186C = 4;
  IoRegisterFileSystem(DeviceObject);
  IoRegisterDriverReinitialization(DriverObject, RefsLoadAddOns, 0);
  RefsKsrInitialize();
  if ( v30[0] )
    ExFreePoolWithTag(v28, 0);
  return 0;
}

```

## disassembly

```asm
0x14034cc48  mov     [rsp-8+arg_10], rbx
0x14034cc4d  push    rbp
0x14034cc4e  push    rsi
0x14034cc4f  push    rdi
0x14034cc50  push    r12
0x14034cc52  push    r13
0x14034cc54  push    r14
0x14034cc56  push    r15
0x14034cc58  lea     rbp, [rsp-120h]
0x14034cc60  sub     rsp, 220h
0x14034cc67  mov     rax, cs:__security_cookie
0x14034cc6e  xor     rax, rsp
0x14034cc71  mov     [rbp+150h+var_40], rax
0x14034cc78  xorps   xmm0, xmm0
0x14034cc7b  mov     [rsp+250h+var_1F8], 9Ch
0x14034cc83  xor     r12d, r12d
0x14034cc86  mov     cs:?OSVersionInfo@@3U_OSVERSIONINFOEXW@@A.dwOSVersionInfoSize, 11Ch; _OSVERSIONINFOEXW OSVersionInfo ...
0x14034cc90  lea     rax, [rbp+150h+var_E0]
0x14034cc94  mov     [rbp+150h+var_1C0], r12
0x14034cc98  mov     [rsp+250h+P], rax
0x14034cc9d  mov     r13, rcx
0x14034cca0  xor     eax, eax
0x14034cca2  mov     [rsp+250h+var_210], r12b
0x14034cca7  xorps   xmm1, xmm1
0x14034ccaa  mov     [rbp+150h+var_178], rax
0x14034ccae  lea     rcx, ?OSVersionInfo@@3U_OSVERSIONINFOEXW@@A; lpVersionInformation
0x14034ccb5  mov     [rbp+150h+CompressBufferWorkSpaceSize], r12d
0x14034ccb9  mov     rsi, rdx
0x14034ccbc  mov     [rbp+150h+CompressFragmentWorkSpaceSize], r12d
0x14034ccc0  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x14034ccc4  mov     [rbp+150h+var_1B0], r12
0x14034ccc8  movups  xmmword ptr [rsp+250h+var_1E8.Length], xmm0
0x14034cccd  movups  xmmword ptr [rsp+250h+var_208.Length], xmm1
0x14034ccd2  movups  xmmword ptr [rsp+250h+var_1D8.Length], xmm0
0x14034ccd7  movups  xmmword ptr [rbp+150h+Info.Version], xmm0
0x14034ccdb  movups  xmmword ptr [rbp+150h+Info.CounterCount], xmm0
0x14034ccdf  movups  xmmword ptr [rbp+150h+Info.Callback], xmm0
0x14034cce3  call    cs:__imp_RtlGetVersion
0x14034ccea  nop     dword ptr [rax+rax+00h]
0x14034ccef  mov     ecx, 0FFFFh; GroupNumber
0x14034ccf4  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14034ccfb  nop     dword ptr [rax+rax+00h]
0x14034cd00  mov     cs:?RefsNumberProcessors@@3KA, eax; ulong RefsNumberProcessors
0x14034cd06  lea     ecx, [r12+2]; CompressionFormatAndEngine
0x14034cd0b  mov     rax, 861C46800h
0x14034cd15  lea     r8, [rbp+150h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14034cd19  lea     rdx, [rbp+150h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14034cd1d  mov     cs:?RefsLastAccess@@3_JA, rax; __int64 RefsLastAccess
0x14034cd24  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14034cd2b  nop     dword ptr [rax+rax+00h]
0x14034cd30  xor     edx, edx; Val
0x14034cd32  lea     rcx, ?RefsData@@3U_REFS_DATA@@A; void *
0x14034cd39  mov     r8d, 850h; Size
0x14034cd3f  call    memset
0x14034cd44  call    cs:__imp_FsRtlQueryMaximumVirtualDiskNestingLevel
0x14034cd4b  nop     dword ptr [rax+rax+00h]
0x14034cd50  lea     rcx, stru_140261440; Mutex
0x14034cd57  mov     cs:?RefsReserveStackStorage@@3PEAXEA, r12; void * RefsReserveStackStorage
0x14034cd5e  mov     cs:?RefsReserveStackCleanup@@3PEAXEA, r12; void * RefsReserveStackCleanup
0x14034cd65  call    cs:__imp_KeInitializeGuardedMutex
0x14034cd6c  nop     dword ptr [rax+rax+00h]
0x14034cd71  xor     edx, edx; Val
0x14034cd73  lea     rcx, dword_1402613B8; void *
0x14034cd7a  mov     r8d, 80h; Size
0x14034cd80  call    memset
0x14034cd85  lea     edx, [r12+9]
0x14034cd8a  mov     cs:dword_1402613B8, 1200844h
0x14034cd94  lea     rcx, qword_1402613C8
0x14034cd9b  call    cs:__imp_ExInitializeFastResource
0x14034cda2  nop     dword ptr [rax+rax+00h]
0x14034cda7  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x14034cdae  mov     qword ptr [rsp+250h+var_1D8.Length], 680066h
0x14034cdb7  mov     [rbp+150h+var_1D8.Buffer], rax
0x14034cdbb  lea     r9, [rsp+250h+P]; struct _KEY_VALUE_FULL_INFORMATION **
0x14034cdc0  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x14034cdc7  mov     qword ptr [rsp+250h+var_1E8.Length], 7C007Ah
0x14034cdd0  mov     [rsp+250h+var_1E8.Buffer], rax
0x14034cdd5  lea     r8, [rsp+250h+var_1F8]; unsigned int *
0x14034cdda  lea     rax, aRefsforcenonpa; "RefsForceNonPagedPoolAllocation"
0x14034cde1  mov     qword ptr [rsp+250h+var_208.Length], 40003Eh
0x14034cdea  mov     [rsp+250h+var_208.Buffer], rax
0x14034cdef  lea     rdx, [rsp+250h+var_208]; struct _UNICODE_STRING *
0x14034cdf4  lea     rax, [rsp+250h+var_210]
0x14034cdf9  lea     rcx, [rsp+250h+var_1D8]; struct _UNICODE_STRING *
0x14034cdfe  mov     qword ptr [rsp+250h+DeviceCharacteristics], rax; unsigned __int8 *
0x14034ce03  call    ?RefsQueryValueKey@@YAJPEAU_UNICODE_STRING@@0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKey(_UNICODE_STRING *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x14034ce08  mov     r14d, 200h
0x14034ce0e  test    eax, eax
0x14034ce10  jns     short loc_14034CE39
0x14034ce12  lea     rax, [rsp+250h+var_210]
0x14034ce17  lea     r9, [rsp+250h+P]; struct _KEY_VALUE_FULL_INFORMATION **
0x14034ce1c  mov     qword ptr [rsp+250h+DeviceCharacteristics], rax; unsigned __int8 *
0x14034ce21  lea     r8, [rsp+250h+var_1F8]; unsigned int *
0x14034ce26  lea     rdx, [rsp+250h+var_208]; struct _UNICODE_STRING *
0x14034ce2b  lea     rcx, [rsp+250h+var_1E8]; struct _UNICODE_STRING *
0x14034ce30  call    ?RefsQueryValueKey@@YAJPEAU_UNICODE_STRING@@0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKey(_UNICODE_STRING *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x14034ce35  test    eax, eax
0x14034ce37  js      short loc_14034CE5D
0x14034ce39  mov     rdi, [rsp+250h+P]
0x14034ce3e  mov     eax, [rdi+8]
0x14034ce41  cmp     [rax+rdi], r12d
0x14034ce45  jnz     short loc_14034CE62
0x14034ce47  mov     cs:PoolType, 1
0x14034ce51  mov     cs:dword_1402618CC, 5
0x14034ce5b  jmp     short loc_14034CE86
0x14034ce5d  mov     rdi, [rsp+250h+P]
0x14034ce62  lea     rcx, ?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; AddressWithinSection
0x14034ce69  mov     cs:PoolType, r14d
0x14034ce70  mov     cs:dword_1402618CC, 204h
0x14034ce7a  call    cs:__imp_MmLockPagableDataSection
0x14034ce81  nop     dword ptr [rax+rax+00h]
0x14034ce86  call    wil_InitializeFeatureStaging
0x14034ce8b  mov     ebx, eax
0x14034ce8d  test    eax, eax
0x14034ce8f  js      loc_14034CF2D
0x14034ce95  call    Feature_Servicing_ReFSStackSwapRead__private_IsEnabledPreCheck
0x14034ce9a  mov     r15d, 4A666552h
0x14034cea0  mov     cs:?RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled@@3EA, 1; uchar RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled
0x14034cea7  mov     ebx, 1000h
0x14034ceac  mov     r8d, r15d; Tag
0x14034ceaf  mov     edx, ebx; NumberOfBytes
0x14034ceb1  mov     ecx, r14d; PoolType
0x14034ceb4  call    cs:__imp_ExAllocatePoolWithTag
0x14034cebb  nop     dword ptr [rax+rax+00h]
0x14034cec0  mov     cs:P, rax
0x14034cec7  test    rax, rax
0x14034ceca  jnz     loc_14034D03C
0x14034ced0  mov     rcx, cs:WPP_GLOBAL_Control
0x14034ced7  lea     rax, WPP_GLOBAL_Control
0x14034cede  mov     ebx, 0C000009Ah
0x14034cee3  cmp     rcx, rax
0x14034cee6  jz      short loc_14034CF0D
0x14034cee8  bt      dword ptr [rcx+2Ch], 8
0x14034ceed  jnb     short loc_14034CF0D
0x14034ceef  cmp     byte ptr [rcx+29h], 4
0x14034cef3  jb      short loc_14034CF0D
0x14034cef5  mov     rcx, [rcx+18h]
0x14034cef9  lea     r8, WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids
0x14034cf00  mov     edx, 0Ah
0x14034cf05  mov     r9d, ebx
0x14034cf08  call    WPP_SF_d
0x14034cf0d  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14034cf13  test    al, al
0x14034cf15  jz      short loc_14034CF2D
0x14034cf17  mov     r9d, 35Eh; unsigned int
0x14034cf1d  lea     r8, aNtfsinitC; "NtfsInit.c"
0x14034cf24  xor     edx, edx; struct _IRP_CONTEXT *
0x14034cf26  mov     ecx, ebx; Status
0x14034cf28  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14034cf2d  lea     rcx, qword_1402613C8
0x14034cf34  call    cs:__imp_ExDeleteFastResource
0x14034cf3b  nop     dword ptr [rax+rax+00h]
0x14034cf40  xor     edx, edx; Val
0x14034cf42  lea     rcx, dword_1402613B8; void *
0x14034cf49  mov     r8d, 80h; Size
0x14034cf4f  call    memset
0x14034cf54  mov     rcx, cs:P; P
0x14034cf5b  test    rcx, rcx
0x14034cf5e  jz      short loc_14034CF75
0x14034cf60  xor     edx, edx; Tag
0x14034cf62  call    cs:__imp_ExFreePoolWithTag
0x14034cf69  nop     dword ptr [rax+rax+00h]
0x14034cf6e  mov     cs:P, r12
0x14034cf75  lea     rcx, qword_140261478; struct _REFS_BUFFER_AND_MDL *
0x14034cf7c  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034cf81  lea     rcx, qword_140261490; struct _REFS_BUFFER_AND_MDL *
0x14034cf88  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034cf8d  lea     rcx, qword_1402614A8; struct _REFS_BUFFER_AND_MDL *
0x14034cf94  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034cf99  lea     rcx, qword_1402614C0; struct _REFS_BUFFER_AND_MDL *
0x14034cfa0  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034cfa5  lea     rcx, qword_1402614D8; struct _RESERVED_IO_REQUESTS *
0x14034cfac  call    ?MsKmeDeleteReservedIoRequests@@YAXPEAU_RESERVED_IO_REQUESTS@@@Z; MsKmeDeleteReservedIoRequests(_RESERVED_IO_REQUESTS *)
0x14034cfb1  lea     rcx, qword_1402616C8; struct _RESERVED_IO_RUNS *
0x14034cfb8  call    ?MsKmeDeleteReservedIoRuns@@YAXPEAU_RESERVED_IO_RUNS@@@Z; MsKmeDeleteReservedIoRuns(_RESERVED_IO_RUNS *)
0x14034cfbd  mov     rcx, cs:?RefsReserveStackStorage@@3PEAXEA; void * RefsReserveStackStorage
0x14034cfc4  test    rcx, rcx
0x14034cfc7  jz      short loc_14034CFDC
0x14034cfc9  call    cs:__imp_KeFreeCalloutStack
0x14034cfd0  nop     dword ptr [rax+rax+00h]
0x14034cfd5  mov     cs:?RefsReserveStackStorage@@3PEAXEA, r12; void * RefsReserveStackStorage
0x14034cfdc  mov     rcx, cs:?RefsReserveStackCleanup@@3PEAXEA; void * RefsReserveStackCleanup
0x14034cfe3  test    rcx, rcx
0x14034cfe6  jz      short loc_14034CFFB
0x14034cfe8  call    cs:__imp_KeFreeCalloutStack
0x14034cfef  nop     dword ptr [rax+rax+00h]
0x14034cff4  mov     cs:?RefsReserveStackCleanup@@3PEAXEA, r12; void * RefsReserveStackCleanup
0x14034cffb  mov     rcx, cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Buffer; P
0x14034d002  test    rcx, rcx
0x14034d005  jz      short loc_14034D01C
0x14034d007  xor     edx, edx; Tag
0x14034d009  call    cs:__imp_ExFreePoolWithTag
0x14034d010  nop     dword ptr [rax+rax+00h]
0x14034d015  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Buffer, r12; _UNICODE_STRING RefsRegistryPath ...
0x14034d01c  cmp     [rsp+250h+var_210], r12b
0x14034d021  jz      short loc_14034D034
0x14034d023  xor     edx, edx; Tag
0x14034d025  mov     rcx, rdi; P
0x14034d028  call    cs:__imp_ExFreePoolWithTag
0x14034d02f  nop     dword ptr [rax+rax+00h]
0x14034d034  mov     eax, ebx
0x14034d036  jmp     loc_14034E871
0x14034d03c  mov     r8, rbx; Size
0x14034d03f  xor     edx, edx; Val
0x14034d041  mov     rcx, rax; void *
0x14034d044  call    memset
0x14034d049  mov     r14d, 40000h
0x14034d04f  lea     rcx, qword_140261478; struct _REFS_BUFFER_AND_MDL *
0x14034d056  mov     edx, r14d; unsigned int
0x14034d059  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x14034d05e  mov     ebx, eax
0x14034d060  test    eax, eax
0x14034d062  js      loc_14034CF2D
0x14034d068  mov     edx, 44000h; unsigned int
0x14034d06d  lea     rcx, qword_140261490; struct _REFS_BUFFER_AND_MDL *
0x14034d074  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x14034d079  mov     ebx, eax
0x14034d07b  test    eax, eax
0x14034d07d  js      loc_14034CF2D
0x14034d083  mov     edx, [rbp+150h+CompressFragmentWorkSpaceSize]; unsigned int
0x14034d086  lea     rcx, qword_1402614A8; struct _REFS_BUFFER_AND_MDL *
0x14034d08d  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x14034d092  mov     ebx, eax
0x14034d094  test    eax, eax
0x14034d096  js      loc_14034CF2D
0x14034d09c  mov     edx, r14d; unsigned int
0x14034d09f  lea     rcx, qword_1402614C0; struct _REFS_BUFFER_AND_MDL *
0x14034d0a6  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x14034d0ab  mov     ebx, eax
0x14034d0ad  test    eax, eax
0x14034d0af  js      loc_14034CF2D
0x14034d0b5  lea     rdx, aRefs; "\\Refs"
0x14034d0bc  lea     rcx, [rbp+150h+DestinationString]; DestinationString
0x14034d0c0  call    cs:__imp_RtlInitUnicodeString
0x14034d0c7  nop     dword ptr [rax+rax+00h]
0x14034d0cc  lea     rax, [rbp+150h+var_1C0]
0x14034d0d0  mov     r9d, 8; DeviceType
0x14034d0d6  mov     [rsp+250h+DeviceObject], rax; DeviceObject
0x14034d0db  lea     r8, [rbp+150h+DestinationString]; DeviceName
0x14034d0df  mov     [rsp+250h+Exclusive], r12b; Exclusive
0x14034d0e4  xor     edx, edx; DeviceExtensionSize
0x14034d0e6  mov     rcx, r13; DriverObject
0x14034d0e9  mov     [rsp+250h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x14034d0ee  call    cs:__imp_IoCreateDevice
0x14034d0f5  nop     dword ptr [rax+rax+00h]
0x14034d0fa  mov     ebx, eax
0x14034d0fc  test    eax, eax
0x14034d0fe  js      loc_14034CF2D
0x14034d104  mov     rax, [rbp+150h+var_1C0]
0x14034d108  lea     rdx, qword_1402614D8; struct _RESERVED_IO_REQUESTS *
0x14034d10f  mov     r14d, 8000000h
0x14034d115  mov     r8b, 14h; char
0x14034d118  or      [rax+30h], r14d
0x14034d11c  mov     rcx, [rbp+150h+var_1C0]; struct _DEVICE_OBJECT *
0x14034d120  call    ?MsKmeInitializeReservedIoRequests@@YAJPEAU_DEVICE_OBJECT@@PEAU_RESERVED_IO_REQUESTS@@D@Z; MsKmeInitializeReservedIoRequests(_DEVICE_OBJECT *,_RESERVED_IO_REQUESTS *,char)
0x14034d125  mov     ebx, eax
0x14034d127  test    eax, eax
0x14034d129  js      loc_14034CF2D
0x14034d12f  lea     rcx, qword_1402616C8; struct _RESERVED_IO_RUNS *
0x14034d136  call    ?MsKmeInitializeReservedIoRuns@@YAJPEAU_RESERVED_IO_RUNS@@K@Z; MsKmeInitializeReservedIoRuns(_RESERVED_IO_RUNS *,ulong)
0x14034d13b  mov     ebx, eax
0x14034d13d  test    eax, eax
0x14034d13f  js      loc_14034CF2D
0x14034d145  call    ?RefsInitializeQueryDirectory@@YAJXZ; RefsInitializeQueryDirectory(void)
0x14034d14a  mov     ebx, eax
0x14034d14c  test    eax, eax
0x14034d14e  js      loc_14034CF2D
0x14034d154  lea     r9, ?RefsReserveStackStorage@@3PEAXEA; void * RefsReserveStackStorage
0x14034d15b  xor     r8d, r8d
0x14034d15e  mov     dl, 3
0x14034d160  xor     ecx, ecx
0x14034d162  call    cs:__imp_KeAllocateCalloutStackEx
0x14034d169  nop     dword ptr [rax+rax+00h]
0x14034d16e  mov     ebx, eax
0x14034d170  test    eax, eax
0x14034d172  js      loc_14034CF2D
0x14034d178  lea     r9, ?RefsReserveStackCleanup@@3PEAXEA; void * RefsReserveStackCleanup
0x14034d17f  xor     r8d, r8d
0x14034d182  mov     dl, 1
0x14034d184  xor     ecx, ecx
0x14034d186  call    cs:__imp_KeAllocateCalloutStackEx
0x14034d18d  nop     dword ptr [rax+rax+00h]
0x14034d192  mov     ebx, eax
0x14034d194  test    eax, eax
0x14034d196  js      loc_14034CF2D
0x14034d19c  movzx   eax, word ptr [rsi]
0x14034d19f  mov     ebx, 2
0x14034d1a4  mov     ecx, cs:PoolType
0x14034d1aa  add     ax, bx
0x14034d1ad  movzx   edx, ax; NumberOfBytes
0x14034d1b0  or      ecx, 10h; PoolType
0x14034d1b3  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, dx; _UNICODE_STRING RefsRegistryPath ...
0x14034d1ba  mov     r8d, r15d; Tag
0x14034d1bd  movzx   eax, word ptr [rsi]
0x14034d1c0  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Length, ax; _UNICODE_STRING RefsRegistryPath ...
0x14034d1c7  call    cs:__imp_ExAllocatePoolWithTag
0x14034d1ce  nop     dword ptr [rax+rax+00h]
0x14034d1d3  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING RefsRegistryPath ...
0x14034d1da  test    rax, rax
0x14034d1dd  jnz     short loc_14034D235
  ... truncated ...
```
