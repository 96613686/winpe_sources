# DriverEntry

- ea: `0x14034fc48`
- end: `0x14035189b`
- name: `DriverEntry`
- size: `7251`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14034f010`

## callees

- `0x1400862c0`
- `0x1400a7b1c`
- `0x1400d0fd8`
- `0x1400e6524`
- `0x1400f4bb4`
- `0x1400f982c`
- `0x1400f9888`
- `0x1400fa2fc`
- `0x1400fa424`
- `0x1400fcdc8`
- `0x1400ff284`
- `0x1400ff3f4`
- `0x1401033d0`
- `0x1401038cc`
- `0x1401f3fb0`
- `0x1401f4400`
- `0x1402ce36c`
- `0x1402ce4d8`
- `0x1402ce548`
- `0x1402cead0`
- `0x1402d17c8`
- `0x1402d185c`
- `0x14032cd14`
- `0x14034f090`
- `0x14034f36c`
- `0x14034fc48`
- `0x1403518a4`
- `0x140351a4c`
- `0x140351af4`
- `0x140351bd8`
- `0x140351d24`
- `0x140351e10`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1403500c0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1403500c0`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140351729`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140351729`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140350242`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140350242`
- `ntoskrnl!IoCreateDevice` at `0x1403500ee`
- `ntoskrnl!IoCreateDevice` at `0x1403500ee`
- `ntoskrnl!KeInitializeSpinLock` at `0x140351803`
- `ntoskrnl!KeInitializeSpinLock` at `0x140351803`
- `ntoskrnl!RtlGetVersion` at `0x14034fce3`
- `ntoskrnl!RtlGetVersion` at `0x14034fce3`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14034fcf4`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14034fcf4`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14034fd24`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14034fd24`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x14034fd44`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x14034fd44`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14034fd65`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14034fd65`
- `ntoskrnl!MmLockPagableDataSection` at `0x14034fe7a`
- `ntoskrnl!MmLockPagableDataSection` at `0x14034fe7a`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x14035041d`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x140350439`
- `ntoskrnl!IoGetBootLayers` at `0x1403514cf`
- `ntoskrnl!IoGetBootLayers` at `0x1403514cf`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x140351549`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x140351549`
- `ntoskrnl!PcwRegister` at `0x1403515c9`
- `ntoskrnl!PcwRegister` at `0x1403515c9`
- `ntoskrnl!ExInitializeFastResource` at `0x14034fd9b`
- `ntoskrnl!ExInitializeFastResource` at `0x1403515f6`
- `ntoskrnl!ExInitializeFastResource` at `0x14034fd9b`
- `ntoskrnl!ExInitializeFastResource` at `0x1403515f6`
- `ntoskrnl!KeInitializeMutant` at `0x140351661`
- `ntoskrnl!KeInitializeMutant` at `0x140351661`
- `ntoskrnl!KeInitializeTimer` at `0x1403516de`
- `ntoskrnl!KeInitializeTimer` at `0x14035175f`
- `ntoskrnl!KeInitializeTimer` at `0x1403516de`
- `ntoskrnl!KeInitializeTimer` at `0x14035175f`
- `ntoskrnl!KeInitializeDpc` at `0x1403516fe`
- `ntoskrnl!KeInitializeDpc` at `0x14035177c`
- `ntoskrnl!KeInitializeDpc` at `0x1403516fe`
- `ntoskrnl!KeInitializeDpc` at `0x14035177c`
- `ntoskrnl!KeInitializeSemaphore` at `0x1403517f0`
- `ntoskrnl!KeInitializeSemaphore` at `0x1403517f0`
- `ntoskrnl!IoRegisterFileSystem` at `0x14035182b`
- `ntoskrnl!IoRegisterFileSystem` at `0x14035182b`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x140351844`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x140351844`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034ffc9`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034ffe8`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034ffc9`
- `ntoskrnl!KeFreeCalloutStack` at `0x14034ffe8`
- `ntoskrnl!ExDeleteFastResource` at `0x14034ff34`
- `ntoskrnl!ExDeleteFastResource` at `0x14034ff34`
- `ntoskrnl!KeInitializeEvent` at `0x140351679`
- `ntoskrnl!KeInitializeEvent` at `0x140351679`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ff62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140350009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140350028`
- `ntoskrnl!ExFreePoolWithTag` at `0x140351861`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034ff62`
- `ntoskrnl!ExFreePoolWithTag` at `0x140350009`
- `ntoskrnl!ExFreePoolWithTag` at `0x140350028`
- `ntoskrnl!ExFreePoolWithTag` at `0x140351861`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14034feb4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1403501c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14034feb4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1403501c7`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x140350162`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x140350186`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x140350162`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x140350186`

## string_xrefs

- `0x14034fda7`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x140350641`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x140350743`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x140351622`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x14034fdc0`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x140350563`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x14035160c`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x140350503`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`
- `0x14035056f`: `RefsDisableWriteThrough`
- `0x14035065a`: `AllowOverAllocateOnVirtualMount`
- `0x140350b56`: `RefsDeferSMRWriteHeadQuery`
- `0x140350d43`: `RefsDisableCachedPins`
- `0x140350d93`: `RefsProcessedDeleteQueueEntryCountThreshold`
- `0x140350df3`: `RefsProcessedDeleteQueueThresholdBindable`
- `0x140350e4d`: `RefsDisableContainersCompaction`
- `0x140350f37`: `RefsLazyWriterWorkersPerVolume`
- `0x140350f84`: `RefsLazyWriterLogWorkersPerVolume`
- `0x140350fd1`: `RefsLazyWriterWorkersTotal`
- `0x14035101e`: `RefsLazyWriterLogWorkersTotal`
- `0x14035106b`: `RefsLazyWriterScanThreshold`
- `0x140351152`: `RefsBlockRefcountEmptyColdDelay`
- `0x14035119f`: `RefsBlockRefcountCacheHighWaterMark`
- `0x14035123c`: `RefsDisableWriteCombining`
- `0x14035128c`: `RefsReallocateAllDataWrites`

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
  memset(&RefsData, 0, 0x840u);
  FsRtlQueryMaximumVirtualDiskNestingLevel();
  RefsReserveStackStorage = 0;
  RefsReserveStackCleanup = 0;
  KeInitializeGuardedMutex(&stru_140268480);
  memset(&dword_1402683F8, 0, 0x80u);
  dword_1402683F8 = 18876484;
  ExInitializeFastResource(qword_140268408, 9);
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
      dword_1402688FC = PagedPoolCacheAligned;
      goto LABEL_7;
    }
  }
  PoolType = 512;
  dword_1402688FC = 516;
  MmLockPagableDataSection(RefsCommonCreate);
LABEL_7:
  Directory = wil_InitializeFeatureStaging();
  if ( Directory < 0 )
  {
LABEL_16:
    ExDeleteFastResource(qword_140268408);
    memset(&dword_1402683F8, 0, 0x80u);
    if ( ::P )
    {
      ExFreePoolWithTag(::P, 0);
      ::P = 0;
    }
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402684B8);
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402684D0);
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402684E8);
    RefsDeleteReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_140268500);
    MsKmeDeleteReservedIoRequests((struct _RESERVED_IO_REQUESTS *)qword_140268518);
    MsKmeDeleteReservedIoRuns((struct _RESERVED_IO_RUNS *)qword_1402686F8);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids, 3221225626LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_16;
    v7 = 849;
    goto LABEL_15;
  }
  memset(PoolWithTag, 0, 0x1000u);
  Directory = RefsInitializeReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402684B8, 0x40000u);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_1402684D0, 0x44000u);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeReservedBuffer(
                (struct _REFS_BUFFER_AND_MDL *)&qword_1402684E8,
                CompressFragmentWorkSpaceSize);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeReservedBuffer((struct _REFS_BUFFER_AND_MDL *)&qword_140268500, 0x40000u);
  if ( Directory < 0 )
    goto LABEL_16;
  RtlInitUnicodeString(&DestinationString, L"\\Refs");
  Directory = IoCreateDevice(DriverObject, 0, &DestinationString, 8u, 0, 0, &DeviceObject);
  if ( Directory < 0 )
    goto LABEL_16;
  DeviceObject->Flags |= 0x8000000u;
  Directory = MsKmeInitializeReservedIoRequests(DeviceObject, (struct _RESERVED_IO_REQUESTS *)qword_140268518, 20);
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = MsKmeInitializeReservedIoRuns((struct _RESERVED_IO_RUNS *)qword_1402686F8, v9);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids, 3221225626LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_16;
    v7 = 986;
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
  qword_140267978 = (__int64)RefsFastIoCheckIfPossible;
  qword_140267980 = (__int64)RefsCopyReadA;
  qword_140267988 = (__int64)RefsCopyWriteA;
  qword_140267990 = (__int64)&RefsFastQueryBasicInfo;
  qword_140267998 = (__int64)RefsFastQueryStdInfo;
  qword_1402679A0 = (__int64)RefsFastLock;
  qword_1402679A8 = (__int64)RefsFastUnlockSingle;
  qword_1402679B0 = (__int64)RefsFastUnlockAll;
  qword_1402679B8 = (__int64)RefsFastUnlockAllByKey;
  qword_1402679E0 = (__int64)&RefsFastQueryNetworkOpenInfo;
  qword_1402679D0 = (__int64)RefsReleaseForCreateSection;
  qword_1402679E8 = (__int64)RefsAcquireFileForModWrite;
  qword_140267A38 = (__int64)RefsReleaseFileForModWrite;
  qword_1402679F0 = (__int64)RefsMdlReadA;
  qword_1402679F8 = (__int64)FsRtlMdlReadCompleteDev;
  qword_140267A00 = (__int64)RefsPrepareMdlWriteA;
  qword_140267A08 = (__int64)FsRtlMdlWriteCompleteDev;
  RefsFastIoDispatch.SizeOfFastIoDispatch = 224;
  qword_1402679C0 = 0;
  qword_1402679D8 = 0;
  qword_1402679C8 = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  qword_140267A30 = (__int64)RefsNetworkOpenCreate;
  qword_140267A40 = (__int64)RefsAcquireFileForCcFlush;
  qword_140267A48 = (__int64)RefsReleaseFileForCcFlush;
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids);
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
  LODWORD(dword_1402682EC) = v17 | (unsigned int)dword_1402682EC;
  dword_1402683F4 |= v12;
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
    byte_14026E662 = 1;
    byte_14026E660 = 1;
  }
  else
  {
    RefsInitializeIoPerf();
  }
  KeInitializeMutant(&StreamFileCreationMutex, 0);
  KeInitializeEvent(&RefsEncryptionPendingEvent, NotificationEvent, 1u);
  *(_OWORD *)&RefsZeroExtendedInfo = 0;
  xmmword_140267950 = 0;
  xmmword_140267960 = 0;
  Directory = RefsInitialize();
  if ( Directory < 0 )
    goto LABEL_16;
  Directory = RefsInitializeWellKnownAttributeRowKeys();
  if ( Directory < 0 )
    goto LABEL_16;
  stru_140268218.Parameter = 0;
  stru_140268218.WorkerRoutine = (PWORKER_THREAD_ROUTINE)RefsCheckUsnTimeOut;
  stru_140268218.List.Flink = 0;
  KeInitializeTimer(&Timer);
  KeInitializeDpc(&Dpc, RefsUsnTimeOutDpc, 0);
  KeSetCoalescableTimer(&Timer, (LARGE_INTEGER)-3000000000LL, 0, 0x3A98u, &Dpc);
  WorkItem.List.Flink = 0;
  WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)RefsPeriodicTimerCallback;
  WorkItem.Parameter = &WorkItem;
  KeInitializeTimer(&stru_140268278);
  KeInitializeDpc(&stru_140268238, RefsPeriodicTimerDpc, 0);
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
  dword_14026889C = 4;
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
0x14034fc48  mov     [rsp-8+arg_10], rbx
0x14034fc4d  push    rbp
0x14034fc4e  push    rsi
0x14034fc4f  push    rdi
0x14034fc50  push    r12
0x14034fc52  push    r13
0x14034fc54  push    r14
0x14034fc56  push    r15
0x14034fc58  lea     rbp, [rsp-120h]
0x14034fc60  sub     rsp, 220h
0x14034fc67  mov     rax, cs:__security_cookie
0x14034fc6e  xor     rax, rsp
0x14034fc71  mov     [rbp+150h+var_40], rax
0x14034fc78  xorps   xmm0, xmm0
0x14034fc7b  mov     [rsp+250h+var_1F8], 9Ch
0x14034fc83  xor     r12d, r12d
0x14034fc86  mov     cs:?OSVersionInfo@@3U_OSVERSIONINFOEXW@@A.dwOSVersionInfoSize, 11Ch; _OSVERSIONINFOEXW OSVersionInfo ...
0x14034fc90  lea     rax, [rbp+150h+var_E0]
0x14034fc94  mov     [rbp+150h+var_1C0], r12
0x14034fc98  mov     [rsp+250h+P], rax
0x14034fc9d  mov     r13, rcx
0x14034fca0  xor     eax, eax
0x14034fca2  mov     [rsp+250h+var_210], r12b
0x14034fca7  xorps   xmm1, xmm1
0x14034fcaa  mov     [rbp+150h+var_178], rax
0x14034fcae  lea     rcx, ?OSVersionInfo@@3U_OSVERSIONINFOEXW@@A; lpVersionInformation
0x14034fcb5  mov     [rbp+150h+CompressBufferWorkSpaceSize], r12d
0x14034fcb9  mov     rsi, rdx
0x14034fcbc  mov     [rbp+150h+CompressFragmentWorkSpaceSize], r12d
0x14034fcc0  movups  xmmword ptr [rbp+150h+DestinationString.Length], xmm0
0x14034fcc4  mov     [rbp+150h+var_1B0], r12
0x14034fcc8  movups  xmmword ptr [rsp+250h+var_1E8.Length], xmm0
0x14034fccd  movups  xmmword ptr [rsp+250h+var_208.Length], xmm1
0x14034fcd2  movups  xmmword ptr [rsp+250h+var_1D8.Length], xmm0
0x14034fcd7  movups  xmmword ptr [rbp+150h+Info.Version], xmm0
0x14034fcdb  movups  xmmword ptr [rbp+150h+Info.CounterCount], xmm0
0x14034fcdf  movups  xmmword ptr [rbp+150h+Info.Callback], xmm0
0x14034fce3  call    cs:__imp_RtlGetVersion
0x14034fcea  nop     dword ptr [rax+rax+00h]
0x14034fcef  mov     ecx, 0FFFFh; GroupNumber
0x14034fcf4  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14034fcfb  nop     dword ptr [rax+rax+00h]
0x14034fd00  mov     cs:?RefsNumberProcessors@@3KA, eax; ulong RefsNumberProcessors
0x14034fd06  lea     ecx, [r12+2]; CompressionFormatAndEngine
0x14034fd0b  mov     rax, 861C46800h
0x14034fd15  lea     r8, [rbp+150h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x14034fd19  lea     rdx, [rbp+150h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x14034fd1d  mov     cs:?RefsLastAccess@@3_JA, rax; __int64 RefsLastAccess
0x14034fd24  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x14034fd2b  nop     dword ptr [rax+rax+00h]
0x14034fd30  xor     edx, edx; Val
0x14034fd32  lea     rcx, ?RefsData@@3U_REFS_DATA@@A; void *
0x14034fd39  mov     r8d, 840h; Size
0x14034fd3f  call    memset
0x14034fd44  call    cs:__imp_FsRtlQueryMaximumVirtualDiskNestingLevel
0x14034fd4b  nop     dword ptr [rax+rax+00h]
0x14034fd50  lea     rcx, stru_140268480; Mutex
0x14034fd57  mov     cs:?RefsReserveStackStorage@@3PEAXEA, r12; void * RefsReserveStackStorage
0x14034fd5e  mov     cs:?RefsReserveStackCleanup@@3PEAXEA, r12; void * RefsReserveStackCleanup
0x14034fd65  call    cs:__imp_KeInitializeGuardedMutex
0x14034fd6c  nop     dword ptr [rax+rax+00h]
0x14034fd71  xor     edx, edx; Val
0x14034fd73  lea     rcx, dword_1402683F8; void *
0x14034fd7a  mov     r8d, 80h; Size
0x14034fd80  call    memset
0x14034fd85  lea     edx, [r12+9]
0x14034fd8a  mov     cs:dword_1402683F8, 1200844h
0x14034fd94  lea     rcx, qword_140268408
0x14034fd9b  call    cs:__imp_ExInitializeFastResource
0x14034fda2  nop     dword ptr [rax+rax+00h]
0x14034fda7  lea     rax, aRegistryMachin_10; "\\Registry\\Machine\\System\\CurrentCon"...
0x14034fdae  mov     qword ptr [rsp+250h+var_1D8.Length], 680066h
0x14034fdb7  mov     [rbp+150h+var_1D8.Buffer], rax
0x14034fdbb  lea     r9, [rsp+250h+P]; struct _KEY_VALUE_FULL_INFORMATION **
0x14034fdc0  lea     rax, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x14034fdc7  mov     qword ptr [rsp+250h+var_1E8.Length], 7C007Ah
0x14034fdd0  mov     [rsp+250h+var_1E8.Buffer], rax
0x14034fdd5  lea     r8, [rsp+250h+var_1F8]; unsigned int *
0x14034fdda  lea     rax, aRefsforcenonpa; "RefsForceNonPagedPoolAllocation"
0x14034fde1  mov     qword ptr [rsp+250h+var_208.Length], 40003Eh
0x14034fdea  mov     [rsp+250h+var_208.Buffer], rax
0x14034fdef  lea     rdx, [rsp+250h+var_208]; struct _UNICODE_STRING *
0x14034fdf4  lea     rax, [rsp+250h+var_210]
0x14034fdf9  lea     rcx, [rsp+250h+var_1D8]; struct _UNICODE_STRING *
0x14034fdfe  mov     qword ptr [rsp+250h+DeviceCharacteristics], rax; unsigned __int8 *
0x14034fe03  call    ?RefsQueryValueKey@@YAJPEAU_UNICODE_STRING@@0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKey(_UNICODE_STRING *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x14034fe08  mov     r14d, 200h
0x14034fe0e  test    eax, eax
0x14034fe10  jns     short loc_14034FE39
0x14034fe12  lea     rax, [rsp+250h+var_210]
0x14034fe17  lea     r9, [rsp+250h+P]; struct _KEY_VALUE_FULL_INFORMATION **
0x14034fe1c  mov     qword ptr [rsp+250h+DeviceCharacteristics], rax; unsigned __int8 *
0x14034fe21  lea     r8, [rsp+250h+var_1F8]; unsigned int *
0x14034fe26  lea     rdx, [rsp+250h+var_208]; struct _UNICODE_STRING *
0x14034fe2b  lea     rcx, [rsp+250h+var_1E8]; struct _UNICODE_STRING *
0x14034fe30  call    ?RefsQueryValueKey@@YAJPEAU_UNICODE_STRING@@0PEAKPEAPEAU_KEY_VALUE_FULL_INFORMATION@@PEAE@Z; RefsQueryValueKey(_UNICODE_STRING *,_UNICODE_STRING *,ulong *,_KEY_VALUE_FULL_INFORMATION * *,uchar *)
0x14034fe35  test    eax, eax
0x14034fe37  js      short loc_14034FE5D
0x14034fe39  mov     rdi, [rsp+250h+P]
0x14034fe3e  mov     eax, [rdi+8]
0x14034fe41  cmp     [rax+rdi], r12d
0x14034fe45  jnz     short loc_14034FE62
0x14034fe47  mov     cs:PoolType, 1
0x14034fe51  mov     cs:dword_1402688FC, 5
0x14034fe5b  jmp     short loc_14034FE86
0x14034fe5d  mov     rdi, [rsp+250h+P]
0x14034fe62  lea     rcx, ?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; AddressWithinSection
0x14034fe69  mov     cs:PoolType, r14d
0x14034fe70  mov     cs:dword_1402688FC, 204h
0x14034fe7a  call    cs:__imp_MmLockPagableDataSection
0x14034fe81  nop     dword ptr [rax+rax+00h]
0x14034fe86  call    wil_InitializeFeatureStaging
0x14034fe8b  mov     ebx, eax
0x14034fe8d  test    eax, eax
0x14034fe8f  js      loc_14034FF2D
0x14034fe95  call    Feature_Servicing_ReFSStackSwapRead__private_IsEnabledPreCheck
0x14034fe9a  mov     r15d, 4A666552h
0x14034fea0  mov     cs:?RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled@@3EA, 1; uchar RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled
0x14034fea7  mov     ebx, 1000h
0x14034feac  mov     r8d, r15d; Tag
0x14034feaf  mov     edx, ebx; NumberOfBytes
0x14034feb1  mov     ecx, r14d; PoolType
0x14034feb4  call    cs:__imp_ExAllocatePoolWithTag
0x14034febb  nop     dword ptr [rax+rax+00h]
0x14034fec0  mov     cs:P, rax
0x14034fec7  test    rax, rax
0x14034feca  jnz     loc_14035003C
0x14034fed0  mov     rcx, cs:WPP_GLOBAL_Control
0x14034fed7  lea     rax, WPP_GLOBAL_Control
0x14034fede  mov     ebx, 0C000009Ah
0x14034fee3  cmp     rcx, rax
0x14034fee6  jz      short loc_14034FF0D
0x14034fee8  bt      dword ptr [rcx+2Ch], 8
0x14034feed  jnb     short loc_14034FF0D
0x14034feef  cmp     byte ptr [rcx+29h], 4
0x14034fef3  jb      short loc_14034FF0D
0x14034fef5  mov     rcx, [rcx+18h]
0x14034fef9  lea     r8, WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids
0x14034ff00  mov     edx, 0Ah
0x14034ff05  mov     r9d, ebx
0x14034ff08  call    WPP_SF_d
0x14034ff0d  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14034ff13  test    al, al
0x14034ff15  jz      short loc_14034FF2D
0x14034ff17  mov     r9d, 351h; unsigned int
0x14034ff1d  lea     r8, aNtfsinitC; "NtfsInit.c"
0x14034ff24  xor     edx, edx; struct _IRP_CONTEXT *
0x14034ff26  mov     ecx, ebx; Status
0x14034ff28  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14034ff2d  lea     rcx, qword_140268408
0x14034ff34  call    cs:__imp_ExDeleteFastResource
0x14034ff3b  nop     dword ptr [rax+rax+00h]
0x14034ff40  xor     edx, edx; Val
0x14034ff42  lea     rcx, dword_1402683F8; void *
0x14034ff49  mov     r8d, 80h; Size
0x14034ff4f  call    memset
0x14034ff54  mov     rcx, cs:P; P
0x14034ff5b  test    rcx, rcx
0x14034ff5e  jz      short loc_14034FF75
0x14034ff60  xor     edx, edx; Tag
0x14034ff62  call    cs:__imp_ExFreePoolWithTag
0x14034ff69  nop     dword ptr [rax+rax+00h]
0x14034ff6e  mov     cs:P, r12
0x14034ff75  lea     rcx, qword_1402684B8; struct _REFS_BUFFER_AND_MDL *
0x14034ff7c  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034ff81  lea     rcx, qword_1402684D0; struct _REFS_BUFFER_AND_MDL *
0x14034ff88  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034ff8d  lea     rcx, qword_1402684E8; struct _REFS_BUFFER_AND_MDL *
0x14034ff94  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034ff99  lea     rcx, qword_140268500; struct _REFS_BUFFER_AND_MDL *
0x14034ffa0  call    ?RefsDeleteReservedBuffer@@YAXPEAU_REFS_BUFFER_AND_MDL@@@Z; RefsDeleteReservedBuffer(_REFS_BUFFER_AND_MDL *)
0x14034ffa5  lea     rcx, qword_140268518; struct _RESERVED_IO_REQUESTS *
0x14034ffac  call    ?MsKmeDeleteReservedIoRequests@@YAXPEAU_RESERVED_IO_REQUESTS@@@Z; MsKmeDeleteReservedIoRequests(_RESERVED_IO_REQUESTS *)
0x14034ffb1  lea     rcx, qword_1402686F8; struct _RESERVED_IO_RUNS *
0x14034ffb8  call    ?MsKmeDeleteReservedIoRuns@@YAXPEAU_RESERVED_IO_RUNS@@@Z; MsKmeDeleteReservedIoRuns(_RESERVED_IO_RUNS *)
0x14034ffbd  mov     rcx, cs:?RefsReserveStackStorage@@3PEAXEA; void * RefsReserveStackStorage
0x14034ffc4  test    rcx, rcx
0x14034ffc7  jz      short loc_14034FFDC
0x14034ffc9  call    cs:__imp_KeFreeCalloutStack
0x14034ffd0  nop     dword ptr [rax+rax+00h]
0x14034ffd5  mov     cs:?RefsReserveStackStorage@@3PEAXEA, r12; void * RefsReserveStackStorage
0x14034ffdc  mov     rcx, cs:?RefsReserveStackCleanup@@3PEAXEA; void * RefsReserveStackCleanup
0x14034ffe3  test    rcx, rcx
0x14034ffe6  jz      short loc_14034FFFB
0x14034ffe8  call    cs:__imp_KeFreeCalloutStack
0x14034ffef  nop     dword ptr [rax+rax+00h]
0x14034fff4  mov     cs:?RefsReserveStackCleanup@@3PEAXEA, r12; void * RefsReserveStackCleanup
0x14034fffb  mov     rcx, cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Buffer; P
0x140350002  test    rcx, rcx
0x140350005  jz      short loc_14035001C
0x140350007  xor     edx, edx; Tag
0x140350009  call    cs:__imp_ExFreePoolWithTag
0x140350010  nop     dword ptr [rax+rax+00h]
0x140350015  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Buffer, r12; _UNICODE_STRING RefsRegistryPath ...
0x14035001c  cmp     [rsp+250h+var_210], r12b
0x140350021  jz      short loc_140350034
0x140350023  xor     edx, edx; Tag
0x140350025  mov     rcx, rdi; P
0x140350028  call    cs:__imp_ExFreePoolWithTag
0x14035002f  nop     dword ptr [rax+rax+00h]
0x140350034  mov     eax, ebx
0x140350036  jmp     loc_140351871
0x14035003c  mov     r8, rbx; Size
0x14035003f  xor     edx, edx; Val
0x140350041  mov     rcx, rax; void *
0x140350044  call    memset
0x140350049  mov     r14d, 40000h
0x14035004f  lea     rcx, qword_1402684B8; struct _REFS_BUFFER_AND_MDL *
0x140350056  mov     edx, r14d; unsigned int
0x140350059  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x14035005e  mov     ebx, eax
0x140350060  test    eax, eax
0x140350062  js      loc_14034FF2D
0x140350068  mov     edx, 44000h; unsigned int
0x14035006d  lea     rcx, qword_1402684D0; struct _REFS_BUFFER_AND_MDL *
0x140350074  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x140350079  mov     ebx, eax
0x14035007b  test    eax, eax
0x14035007d  js      loc_14034FF2D
0x140350083  mov     edx, [rbp+150h+CompressFragmentWorkSpaceSize]; unsigned int
0x140350086  lea     rcx, qword_1402684E8; struct _REFS_BUFFER_AND_MDL *
0x14035008d  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x140350092  mov     ebx, eax
0x140350094  test    eax, eax
0x140350096  js      loc_14034FF2D
0x14035009c  mov     edx, r14d; unsigned int
0x14035009f  lea     rcx, qword_140268500; struct _REFS_BUFFER_AND_MDL *
0x1403500a6  call    ?RefsInitializeReservedBuffer@@YAJPEAU_REFS_BUFFER_AND_MDL@@K@Z; RefsInitializeReservedBuffer(_REFS_BUFFER_AND_MDL *,ulong)
0x1403500ab  mov     ebx, eax
0x1403500ad  test    eax, eax
0x1403500af  js      loc_14034FF2D
0x1403500b5  lea     rdx, aRefs; "\\Refs"
0x1403500bc  lea     rcx, [rbp+150h+DestinationString]; DestinationString
0x1403500c0  call    cs:__imp_RtlInitUnicodeString
0x1403500c7  nop     dword ptr [rax+rax+00h]
0x1403500cc  lea     rax, [rbp+150h+var_1C0]
0x1403500d0  mov     r9d, 8; DeviceType
0x1403500d6  mov     [rsp+250h+DeviceObject], rax; DeviceObject
0x1403500db  lea     r8, [rbp+150h+DestinationString]; DeviceName
0x1403500df  mov     [rsp+250h+Exclusive], r12b; Exclusive
0x1403500e4  xor     edx, edx; DeviceExtensionSize
0x1403500e6  mov     rcx, r13; DriverObject
0x1403500e9  mov     [rsp+250h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x1403500ee  call    cs:__imp_IoCreateDevice
0x1403500f5  nop     dword ptr [rax+rax+00h]
0x1403500fa  mov     ebx, eax
0x1403500fc  test    eax, eax
0x1403500fe  js      loc_14034FF2D
0x140350104  mov     rax, [rbp+150h+var_1C0]
0x140350108  lea     rdx, qword_140268518; struct _RESERVED_IO_REQUESTS *
0x14035010f  mov     r14d, 8000000h
0x140350115  mov     r8b, 14h; char
0x140350118  or      [rax+30h], r14d
0x14035011c  mov     rcx, [rbp+150h+var_1C0]; struct _DEVICE_OBJECT *
0x140350120  call    ?MsKmeInitializeReservedIoRequests@@YAJPEAU_DEVICE_OBJECT@@PEAU_RESERVED_IO_REQUESTS@@D@Z; MsKmeInitializeReservedIoRequests(_DEVICE_OBJECT *,_RESERVED_IO_REQUESTS *,char)
0x140350125  mov     ebx, eax
0x140350127  test    eax, eax
0x140350129  js      loc_14034FF2D
0x14035012f  lea     rcx, qword_1402686F8; struct _RESERVED_IO_RUNS *
0x140350136  call    ?MsKmeInitializeReservedIoRuns@@YAJPEAU_RESERVED_IO_RUNS@@K@Z; MsKmeInitializeReservedIoRuns(_RESERVED_IO_RUNS *,ulong)
0x14035013b  mov     ebx, eax
0x14035013d  test    eax, eax
0x14035013f  js      loc_14034FF2D
0x140350145  call    ?RefsInitializeQueryDirectory@@YAJXZ; RefsInitializeQueryDirectory(void)
0x14035014a  mov     ebx, eax
0x14035014c  test    eax, eax
0x14035014e  js      loc_14034FF2D
0x140350154  lea     r9, ?RefsReserveStackStorage@@3PEAXEA; void * RefsReserveStackStorage
0x14035015b  xor     r8d, r8d
0x14035015e  mov     dl, 3
0x140350160  xor     ecx, ecx
0x140350162  call    cs:__imp_KeAllocateCalloutStackEx
0x140350169  nop     dword ptr [rax+rax+00h]
0x14035016e  mov     ebx, eax
0x140350170  test    eax, eax
0x140350172  js      loc_14034FF2D
0x140350178  lea     r9, ?RefsReserveStackCleanup@@3PEAXEA; void * RefsReserveStackCleanup
0x14035017f  xor     r8d, r8d
0x140350182  mov     dl, 1
0x140350184  xor     ecx, ecx
0x140350186  call    cs:__imp_KeAllocateCalloutStackEx
0x14035018d  nop     dword ptr [rax+rax+00h]
0x140350192  mov     ebx, eax
0x140350194  test    eax, eax
0x140350196  js      loc_14034FF2D
0x14035019c  movzx   eax, word ptr [rsi]
0x14035019f  mov     ebx, 2
0x1403501a4  mov     ecx, cs:PoolType
0x1403501aa  add     ax, bx
0x1403501ad  movzx   edx, ax; NumberOfBytes
0x1403501b0  or      ecx, 10h; PoolType
0x1403501b3  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.MaximumLength, dx; _UNICODE_STRING RefsRegistryPath ...
0x1403501ba  mov     r8d, r15d; Tag
0x1403501bd  movzx   eax, word ptr [rsi]
0x1403501c0  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Length, ax; _UNICODE_STRING RefsRegistryPath ...
0x1403501c7  call    cs:__imp_ExAllocatePoolWithTag
0x1403501ce  nop     dword ptr [rax+rax+00h]
0x1403501d3  mov     cs:?RefsRegistryPath@@3U_UNICODE_STRING@@A.Buffer, rax; _UNICODE_STRING RefsRegistryPath ...
0x1403501da  test    rax, rax
0x1403501dd  jnz     short loc_140350235
  ... truncated ...
```
