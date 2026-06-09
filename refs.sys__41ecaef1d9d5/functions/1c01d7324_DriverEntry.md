# DriverEntry

- ea: `0x1c01d7324`
- end: `0x1c01d97a6`
- name: `DriverEntry`
- size: `9346`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `31`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1c01d7010`

## callees

- `0x1c000f770`
- `0x1c003fd04`
- `0x1c0054d68`
- `0x1c0055e54`
- `0x1c00565b0`
- `0x1c0063558`
- `0x1c0063620`
- `0x1c0067060`
- `0x1c0067ba4`
- `0x1c0068000`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c009a564`
- `0x1c009a5b0`
- `0x1c00a7b68`
- `0x1c014d2a4`
- `0x1c0175740`
- `0x1c017597c`
- `0x1c0175ab0`
- `0x1c0177498`
- `0x1c017d40c`
- `0x1c017d8fc`
- `0x1c017da90`
- `0x1c01d7078`
- `0x1c01d71ec`
- `0x1c01d7270`
- `0x1c01d7324`
- `0x1c01d97ac`
- `0x1c01da058`
- `0x1c01da954`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d747f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d7682`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d92b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d9303`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d9413`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d747f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d7682`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d92b0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d9303`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01d9413`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01d9699`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01d9740`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01d9761`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01d9699`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01d9740`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01d9761`
- `ntoskrnl!KeInitializeEvent` at `0x1c01d9367`
- `ntoskrnl!KeInitializeEvent` at `0x1c01d9367`
- `ntoskrnl!KeBugCheckEx` at `0x1c01d93fb`
- `ntoskrnl!KeBugCheckEx` at `0x1c01d93fb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d7582`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8db4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8dcb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8de2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8e45`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8e5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8e73`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8ed6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8eed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8f51`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8f68`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8f7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8fe2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8ff9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9010`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9073`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d908a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d90e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9100`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9117`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d917a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9191`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d91a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d920b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9222`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d7582`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8db4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8dcb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8de2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8e45`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8e5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8e73`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8ed6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8eed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8f51`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8f68`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8f7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8fe2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d8ff9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9010`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9073`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d908a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d90e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9100`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9117`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d917a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9191`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d91a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d920b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c01d9222`
- `ntoskrnl!ExInitializeResourceLite` at `0x1c01d7452`
- `ntoskrnl!ExInitializeResourceLite` at `0x1c01d9294`
- `ntoskrnl!ExInitializeResourceLite` at `0x1c01d7452`
- `ntoskrnl!ExInitializeResourceLite` at `0x1c01d9294`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c01d966b`
- `ntoskrnl!ExDeleteResourceLite` at `0x1c01d966b`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1c01d9521`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1c01d9521`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c01d76fd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1c01d76fd`
- `ntoskrnl!IoCreateDevice` at `0x1c01d75b0`
- `ntoskrnl!IoCreateDevice` at `0x1c01d75b0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c01d9626`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c01d9626`
- `ntoskrnl!RtlGetVersion` at `0x1c01d739e`
- `ntoskrnl!RtlGetVersion` at `0x1c01d739e`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c01d73af`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1c01d73af`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x1c01d73e2`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x1c01d73e2`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x1c01d7402`
- `ntoskrnl!FsRtlQueryMaximumVirtualDiskNestingLevel` at `0x1c01d7402`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1c01d7423`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1c01d937a`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1c01d7423`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x1c01d937a`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1c01d7622`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1c01d7646`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1c01d7622`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1c01d7646`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x1c01d78d8`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x1c01d78f4`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x1c01d8c0a`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x1c01d8c0a`
- `ntoskrnl!KeInitializeMutant` at `0x1c01d934f`
- `ntoskrnl!KeInitializeMutant` at `0x1c01d934f`
- `ntoskrnl!InitializeSListHead` at `0x1c01d93a2`
- `ntoskrnl!InitializeSListHead` at `0x1c01d93a2`
- `ntoskrnl!KeInitializeTimer` at `0x1c01d94d6`
- `ntoskrnl!KeInitializeTimer` at `0x1c01d9557`
- `ntoskrnl!KeInitializeTimer` at `0x1c01d94d6`
- `ntoskrnl!KeInitializeTimer` at `0x1c01d9557`
- `ntoskrnl!KeInitializeDpc` at `0x1c01d94f6`
- `ntoskrnl!KeInitializeDpc` at `0x1c01d9574`
- `ntoskrnl!KeInitializeDpc` at `0x1c01d94f6`
- `ntoskrnl!KeInitializeDpc` at `0x1c01d9574`
- `ntoskrnl!KeInitializeSemaphore` at `0x1c01d9605`
- `ntoskrnl!KeInitializeSemaphore` at `0x1c01d9605`
- `ntoskrnl!IoRegisterFileSystem` at `0x1c01d964e`
- `ntoskrnl!IoRegisterFileSystem` at `0x1c01d964e`
- `ntoskrnl!KeFreeCalloutStack` at `0x1c01d9700`
- `ntoskrnl!KeFreeCalloutStack` at `0x1c01d971f`
- `ntoskrnl!KeFreeCalloutStack` at `0x1c01d9700`
- `ntoskrnl!KeFreeCalloutStack` at `0x1c01d971f`
- `ntoskrnl!PcwRegister` at `0x1c01d8c9d`
- `ntoskrnl!PcwRegister` at `0x1c01d8c9d`

## string_xrefs

- `0x1c01d79bf`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`
- `0x1c01d7a0a`: `\Registry\Machine\System\Setup`
- `0x1c01d7a9a`: `\Registry\Machine\System\CurrentControlSet\Services\Setupdd`
- `0x1c01d7b10`: `\Registry\Machine\Cluster\OperatingVersion`
- `0x1c01d7b70`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x1c01d7bdf`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x1c01d92c8`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`
- `0x1c01d7c10`: `RefsDisableLastAccessUpdate`
- `0x1c01d7c8b`: `RefsDisableWriteThrough`
- `0x1c01d7e45`: `RefsEnablePersistentReadCache`
- `0x1c01d7eb5`: `RefsEnableReadCacheOverRead`
- `0x1c01d7f24`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x1c01d9314`: `\Registry\Machine\System\CurrentControlSet\Policies`
- `0x1c01d7f3b`: `AllowOverAllocateOnVirtualMount`
- `0x1c01d8145`: `RefsDeferSMRWriteHeadQuery`
- `0x1c01d8249`: `RefsEnableDirtyRemount`
- `0x1c01d840c`: `RefsDisableCachedPins`
- `0x1c01d8479`: `RefsProcessedDeleteQueueEntryCountThreshold`
- `0x1c01d84d5`: `RefsProcessedDeleteQueueThresholdBindable`
- `0x1c01d854e`: `RefsDisableContainersCompaction`
- `0x1c01d8639`: `RefsLazyWriterWorkersPerVolume`
- `0x1c01d8685`: `RefsLazyWriterLogWorkersPerVolume`
- `0x1c01d86d1`: `RefsLazyWriterWorkersTotal`
- `0x1c01d871d`: `RefsLazyWriterLogWorkersTotal`
- `0x1c01d8769`: `RefsLazyWriterScanThreshold`
- `0x1c01d884d`: `RefsBlockRefcountEmptyColdDelay`
- `0x1c01d8899`: `RefsBlockRefcountCacheHighWaterMark`
- `0x1c01d88e5`: `DisallowInvalidReparsePoint`
- `0x1c01d89bc`: `RefsDisableWriteCombining`
- `0x1c01d8a29`: `RefsReallocateAllDataWrites`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v2; // r15d
  NTSTATUS Directory; // ebx
  PVOID PoolWithTag; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  bool v9; // sf
  int v10; // ebx
  _BYTE *v11; // rdx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // edi
  int v17; // eax
  int v18; // r12d
  int v19; // edi
  unsigned int v20; // eax
  unsigned int v21; // ecx
  unsigned int v22; // edx
  unsigned int v23; // ecx
  int v24; // eax
  _BYTE *v25; // r15
  __int64 v26; // rdx
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  char v32; // cl
  int v33; // eax
  __int64 v34; // rcx
  _WORD *v35; // rax
  _WORD *v36; // rax
  SIZE_T v37; // rdx
  PVOID v38; // rax
  LONG v39; // edx
  _BYTE v41[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE *v43; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v44[2]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v45; // [rsp+68h] [rbp-98h]
  __int128 v46; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v47; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v48; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v49; // [rsp+A0h] [rbp-60h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+B0h] [rbp-50h] BYREF
  int v51; // [rsp+B4h] [rbp-4Ch]
  PDEVICE_OBJECT DeviceObject; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v54; // [rsp+D0h] [rbp-30h]
  ULONG CompressBufferWorkSpaceSize; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v56; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v57[2]; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+8h] BYREF
  _PCW_REGISTRATION_INFORMATION Info; // [rsp+118h] [rbp+18h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v61[160]; // [rsp+1D0h] [rbp+D0h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  v44[1] = 0;
  v2 = 0;
  v46 = 0;
  v51 = 0;
  v56 = 0;
  CompressBufferWorkSpaceSize = 0;
  CompressFragmentWorkSpaceSize = 0;
  wil_InitializeFeatureStaging();
  LODWORD(WPP_MAIN_CB.DeviceExtension) = 284;
  RtlGetVersion((PRTL_OSVERSIONINFOW)&WPP_MAIN_CB.DeviceExtension);
  RefsNumberProcessors = KeQueryActiveProcessorCountEx(0xFFFFu);
  RefsLastAccess = 36000000000LL;
  RtlGetCompressionWorkSpaceSize(2u, &CompressBufferWorkSpaceSize, &CompressFragmentWorkSpaceSize);
  memset(&RefsData, 0, 0x898u);
  FsRtlQueryMaximumVirtualDiskNestingLevel();
  RefsReserveStackStorage = 0;
  RefsReserveStackCleanup = 0;
  KeInitializeGuardedMutex(&stru_1C012E258);
  memset(&dword_1C012E1D0, 0, 0x80u);
  dword_1C012E1D0 = 18876484;
  ExInitializeResourceLite(&stru_1C012E1E0);
  Directory = MsInitializeFastResourceLibrary();
  if ( Directory < 0 )
    goto LABEL_250;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x1000u, 0x4A666552u);
  P = PoolWithTag;
  if ( !PoolWithTag )
  {
    Directory = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids, 3221225626LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_250;
    goto LABEL_8;
  }
  memset(PoolWithTag, 0, 0x1000u);
  Directory = RefsInitializeReservedBuffer(&qword_1C012E290, 0x40000);
  if ( Directory < 0 )
    goto LABEL_250;
  Directory = RefsInitializeReservedBuffer(&qword_1C012E2A8, 278528);
  if ( Directory < 0 )
    goto LABEL_250;
  Directory = RefsInitializeReservedBuffer(&qword_1C012E2C0, CompressFragmentWorkSpaceSize);
  if ( Directory < 0 )
    goto LABEL_250;
  Directory = RefsInitializeReservedBuffer(&qword_1C012E2D8, 0x40000);
  if ( Directory < 0 )
    goto LABEL_250;
  RtlInitUnicodeString(&DestinationString, L"\\Refs");
  Directory = IoCreateDevice(DriverObject, 0, &DestinationString, 8u, 0, 0, &DeviceObject);
  if ( Directory < 0 )
    goto LABEL_250;
  DeviceObject->Flags |= 0x8000000u;
  Directory = MsKmeInitializeReservedIoRequests(DeviceObject, qword_1C012E2F0, 20);
  if ( Directory < 0 )
    goto LABEL_250;
  Directory = MsKmeInitializeReservedIoRuns(qword_1C012E4F0);
  if ( Directory < 0 )
    goto LABEL_250;
  Directory = RefsInitializeQueryDirectory();
  if ( Directory < 0 )
    goto LABEL_250;
  LOBYTE(v7) = 3;
  Directory = KeAllocateCalloutStackEx(0, v7, 0, &RefsReserveStackStorage);
  if ( Directory < 0 )
    goto LABEL_250;
  LOBYTE(v8) = 1;
  Directory = KeAllocateCalloutStackEx(0, v8, 0, &RefsReserveStackCleanup);
  if ( Directory < 0 )
    goto LABEL_250;
  RefsRegistryPath.MaximumLength = RegistryPath->Length + 2;
  RefsRegistryPath.Length = RegistryPath->Length;
  RefsRegistryPath.Buffer = (PWSTR)ExAllocatePoolWithTag((POOL_TYPE)17, RefsRegistryPath.MaximumLength, 0x4A666552u);
  if ( !RefsRegistryPath.Buffer )
  {
    Directory = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids, 3221225626LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_250;
    goto LABEL_8;
  }
  RtlCopyUnicodeString(&RefsRegistryPath, RegistryPath);
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[26] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[25] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[8] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[7] = (PDRIVER_DISPATCH)RefsFsdDispatchWait;
  DriverObject->MajorFunction[11] = (PDRIVER_DISPATCH)&RefsFsdDispatch;
  DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)&RefsFsdDispatch;
  DriverObject->MajorFunction[21] = (PDRIVER_DISPATCH)&RefsFsdDispatch;
  DriverObject->MajorFunction[20] = (PDRIVER_DISPATCH)&RefsFsdDispatch;
  DriverObject->MajorFunction[17] = (PDRIVER_DISPATCH)&RefsFsdLockControl;
  DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)&RefsFsdDirectoryControl;
  DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)&RefsFsdSetInformation;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&RefsFsdCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&RefsFsdClose;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&RefsFsdRead;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&RefsFsdWrite;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)&RefsFsdFlushBuffers;
  DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)&RefsFsdFileSystemControl;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&RefsFsdCleanup;
  DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)RefsFsdShutdown;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)RefsFsdPnp;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&RefsFsdDeviceControl;
  DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&RefsFastIoDispatch;
  qword_1C012DC28 = (__int64)RefsFastIoCheckIfPossible;
  qword_1C012DC30 = (__int64)RefsCopyReadA;
  qword_1C012DC38 = (__int64)RefsCopyWriteA;
  qword_1C012DC40 = (__int64)RefsFastQueryBasicInfo;
  qword_1C012DC48 = (__int64)RefsFastQueryStdInfo;
  qword_1C012DC50 = (__int64)RefsFastLock;
  qword_1C012DC58 = (__int64)RefsFastUnlockSingle;
  qword_1C012DC60 = (__int64)RefsFastUnlockAll;
  qword_1C012DC68 = (__int64)RefsFastUnlockAllByKey;
  qword_1C012DC90 = (__int64)RefsFastQueryNetworkOpenInfo;
  qword_1C012DC80 = (__int64)RefsReleaseForCreateSection;
  qword_1C012DC98 = (__int64)RefsAcquireFileForModWrite;
  qword_1C012DCE8 = (__int64)RefsReleaseFileForModWrite;
  qword_1C012DCA0 = (__int64)RefsMdlReadA;
  qword_1C012DCA8 = (__int64)FsRtlMdlReadCompleteDev;
  qword_1C012DCB0 = (__int64)RefsPrepareMdlWriteA;
  qword_1C012DCB8 = (__int64)FsRtlMdlWriteCompleteDev;
  RefsFastIoDispatch = 224;
  qword_1C012DC70 = 0;
  qword_1C012DC88 = 0;
  qword_1C012DC78 = 0;
  qword_1C012DCE0 = (__int64)RefsNetworkOpenCreate;
  qword_1C012DCF0 = (__int64)RefsAcquireFileForCcFlush;
  qword_1C012DCF8 = (__int64)RefsReleaseFileForCcFlush;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WppTrace;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids);
  }
  LODWORD(v46) = 7602290;
  *((_QWORD *)&v46 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT";
  v9 = (int)RefsQueryValueKey(&v46, 0, 0, 0, 0) < 0;
  v41[0] = 0;
  LODWORD(v46) = 4063292;
  v43 = v61;
  v44[0] = 2883626;
  *((_QWORD *)&v46 + 1) = L"\\Registry\\Machine\\System\\Setup";
  v45 = L"SystemSetupInProgress";
  v10 = 0;
  if ( !v9 )
    v10 = 0x4000;
  v42 = 156;
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) < 0 )
  {
    if ( !v43 )
    {
      v41[0] = 0;
      v43 = v61;
      v42 = 156;
    }
    LODWORD(v46) = 7864438;
    *((_QWORD *)&v46 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Setupdd";
    v44[0] = 786442;
    v45 = L"Start";
    v13 = RefsQueryValueKey(&v46, v44, &v42, &v43, v41);
    v11 = v43;
    if ( v13 >= 0 )
      v10 |= 0x100u;
  }
  else
  {
    v11 = v43;
    v12 = v10 | 0x100;
    if ( *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 1 )
      v12 = v10;
    v10 = v12;
  }
  if ( (v10 & 0x100) == 0 )
  {
    if ( !v11 )
    {
      v41[0] = 0;
      v43 = v61;
      v42 = 156;
    }
    LODWORD(v46) = 5636180;
    *((_QWORD *)&v46 + 1) = L"\\Registry\\Machine\\Cluster\\OperatingVersion";
    v44[0] = 1310738;
    v45 = L"MixedMode";
    v14 = RefsQueryValueKey(&v46, v44, &v42, &v43, v41);
    v11 = v43;
    if ( v14 >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] )
      v10 |= 0x100u;
  }
  if ( (v10 & 0x100) == 0 )
  {
    if ( !v11 )
    {
      v41[0] = 0;
      v43 = v61;
      v42 = 156;
    }
    *((_QWORD *)&v46 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
    v45 = L"RefsDisableVolumeUpgrade";
    LODWORD(v46) = 8126586;
    v44[0] = 3276848;
    v15 = RefsQueryValueKey(&v46, v44, &v42, &v43, v41);
    v11 = v43;
    if ( v15 >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] )
      v10 |= 0x100u;
  }
  if ( !v11 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  *((_QWORD *)&v46 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  v45 = L"RefsDisableLastAccessUpdate";
  LODWORD(v46) = 8126586;
  v44[0] = 3670070;
  v16 = v10 | 0x40;
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 1 )
    v16 = v10;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3145774;
  v45 = L"RefsDisableWriteThrough";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
  {
    v17 = v16 | 1;
    if ( *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 1 )
      v17 = v16;
    v16 = v17;
  }
  v18 = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 2097182;
  v45 = L"RefsMemoryUsage";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0
    && (unsigned int)(*(_DWORD *)&v43[*((unsigned int *)v43 + 2)] - 1) <= 1 )
  {
    v18 = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  }
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 2883626;
  v45 = L"RefsBugcheckOnCorrupt";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    v16 |= 0x10000u;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3407922;
  v45 = L"RefsDisableDebugCodeFlags";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
  {
    if ( *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] )
      v2 = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
    v51 = v2;
  }
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3932218;
  v45 = L"RefsEnablePersistentReadCache";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    v16 |= 0x800000u;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3670070;
  v45 = L"RefsEnableReadCacheOverRead";
  if ( ((int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) < 0 || *(_DWORD *)&v43[*((unsigned int *)v43 + 2)])
    && (v16 & 0x800000) == 0 )
  {
    v16 |= 0x1000000u;
  }
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  LODWORD(v56) = 6815846;
  *((_QWORD *)&v56 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
  v44[0] = 4194366;
  v45 = L"AllowOverAllocateOnVirtualMount";
  v19 = v16 | 0x40000;
  if ( (int)RefsQueryValueKey(&v56, v44, &v42, &v43, v41) < 0 )
  {
    if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && !*(_DWORD *)&v43[*((unsigned int *)v43 + 2)] )
      v19 &= ~0x40000u;
  }
  else
  {
    v20 = v19 & 0xFFFBFFFF;
    if ( *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] )
      v20 = v19;
    v19 = v20;
  }
  v44[0] = 3145774;
  v45 = L"RefsEnableSMRSimulation";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsEnableSMRSimulation = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  v44[0] = 3538996;
  v45 = L"RefsBandSizeOnSimulatedSMR";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsBandSizeOnSimulatedSMR = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 4194366;
  v45 = L"RefsCMRRegionSizeOnSimulatedSMR";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsCMRRegionOnSimulatedSMR = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3145774;
  v45 = L"RefsMakeAllFilesSMRBlob";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsMakeAllFilesSMRBlob = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  v44[0] = 3276848;
  v45 = L"RefsDisableRedoLogReplay";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsDisableRedoLogReplay = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  v44[0] = 3538996;
  v45 = L"RefsDeferSMRWriteHeadQuery";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsDeferSMRWriteHeadQuery = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  v44[0] = 3014700;
  v45 = L"RefsFailUnorderedSMRIO";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsFailUnorderedSMRIO = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  v44[0] = 4849736;
  v45 = L"RefsFullBandAllocationOnTieredVolume";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsFullBandAllocationOnTieredVolume = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3014700;
  v45 = L"RefsEnableDirtyRemount";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsEnableDirtyRemount = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3932218;
  v45 = L"RefsEnableLargeWorkingSetTrim";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsEnableLargeWorkingSetTrim = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3276848;
  v45 = L"RefsNumberOfChunksToTrim";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
  {
    v21 = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
    if ( v21 )
    {
      RefsNumberOfChunksToTrim = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
      if ( v21 > 0x200 )
        RefsNumberOfChunksToTrim = 512;
    }
  }
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 2752552;
  v45 = L"RefsEnableInlineTrim";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsEnableInlineTrim = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 2883626;
  v45 = L"RefsDisableCachedPins";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsDisableCachedPins = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 5767254;
  v45 = L"RefsProcessedDeleteQueueEntryCountThreshold";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
  {
    v22 = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
    if ( v22 )
    {
      RefsProcessedDeleteQueueThresholdCheckpoint = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
      if ( v22 < 0x100 )
        RefsProcessedDeleteQueueThresholdCheckpoint = 256;
    }
  }
  v44[0] = 5505106;
  v45 = L"RefsProcessedDeleteQueueThresholdBindable";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
  {
    v23 = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
    if ( v23 )
    {
      RefsProcessedDeleteQueueThresholdBindable = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
      if ( v23 < 0x100 )
        RefsProcessedDeleteQueueThresholdBindable = 256;
    }
  }
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 4194366;
  v45 = L"RefsDisableContainersCompaction";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsDisableContainersCompaction = 1;
  v44[0] = 3801144;
  v45 = L"RefsDisableRefCountRangeLock";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsEnableRefcountRangeLock = 0;
  v44[0] = 4325440;
  v45 = L"RefsAggresiveTableFlushThreshold";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsLazyWriterAggresiveBindableThreshold = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 4063292;
  v45 = L"RefsLazyWriterWorkersPerVolume";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsLazyWriterWorkersPerVolume = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 4456514;
  v45 = L"RefsLazyWriterLogWorkersPerVolume";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsLazyWriterLogWorkersPerVolume = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3538996;
  v45 = L"RefsLazyWriterWorkersTotal";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsLazyWriterWorkersTotal = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3932218;
  v45 = L"RefsLazyWriterLogWorkersTotal";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsLazyWriterLogWorkersTotal = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3670070;
  v45 = L"RefsLazyWriterScanThreshold";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsLazyWriterScanThresholdPerVolume = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3670070;
  v45 = L"RefsBlockRefcountScanPeriod";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsBlockRefcountScanPeriod = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3538996;
  v45 = L"RefsBlockRefcountColdDelay";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsBlockRefcountColdDelay = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 4194366;
  v45 = L"RefsBlockRefcountEmptyColdDelay";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsBlockRefcountEmptyColdDelay = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 4718662;
  v45 = L"RefsBlockRefcountCacheHighWaterMark";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsBlockRefcountCacheHighWaterMark = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  v44[0] = 3670070;
  v45 = L"DisallowInvalidReparsePoint";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    RefsDisallowInvalidReparsePoint = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] != 0;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3407922;
  v45 = L"RefsDisableUserDataTriage";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsDisableUserDataTriage = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3407922;
  v45 = L"RefsDisableWriteCombining";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsDisableWriteCombining = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3670070;
  v45 = L"RefsReallocateAllDataWrites";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsReallocateAllDataWrites = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 3932218;
  v45 = L"RefsEnableTrimOnAllMediaTypes";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsEnableTrimOnAllMediaTypes = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 4456514;
  v45 = L"RefsDisableFlushAndTrimOnRotation";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 && *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
    RefsDisableFlushAndTrimOnRotation = 1;
  if ( !v43 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 4325440;
  v45 = L"RefsRotationIOGranularityInBytes";
  v24 = RefsQueryValueKey(&v46, v44, &v42, &v43, v41);
  v25 = v43;
  if ( v24 >= 0 )
    RefsRotationIOGranularityInBytes = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)];
  Directory = RefsInitializeRefsData(DriverObject, (__int64)DeviceObject, v18);
  if ( Directory < 0 )
    goto LABEL_250;
  FsLibInitializeRangeLocks();
  FsLibInitializeDAX();
  memset(&Callbacks, 0, sizeof(Callbacks));
  Callbacks.SizeOfFsFilterCallbacks = 120;
  Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)RefsFilterCallbackAcquireForCreateSection;
  Directory = FsRtlRegisterFileSystemFilterCallbacks(DriverObject, &Callbacks);
  if ( Directory < 0 )
    goto LABEL_250;
  dword_1C012E0B0 |= v19;
  dword_1C012E1CC |= v51;
  McGenEventRegister_EtwRegister(RefsEventProvider, v26, &RefsEventProvider_Context, &RefsEventProvider_Context);
  qword_1C012E1C0 = RefsEventProvider_Context;
  v57[0] = 655368;
  v57[1] = L"ReFS";
  *(_QWORD *)&Info.Version = 256;
  Info.Counters = (PPCW_COUNTER_DESCRIPTOR)`CmsRegisterRefsPerfCounterSet'::`2'::Descriptors;
  Info.Name = (PCUNICODE_STRING)v57;
  *(_QWORD *)&Info.CounterCount = 50;
  Info.Callback = 0;
  Info.CallbackContext = 0;
  PcwRegister(&CmsRefsPerfCounterSet, &Info);
  RefsInitializeSqm();
  v53 = 0;
  v54 = 0;
  v48 = 0;
  v49 = 0;
  v47 = 0;
  if ( (unsigned __int8)FsLibInitializeIoPerfTelemetrySettings(v28, v27, v29, v30, (__int64)&v53) )
  {
    BYTE9(v54) = 1;
    v45 = L"RefsDisableIoPerfTelemetry";
    v44[0] = 3538996;
    v31 = RefsQueryValueKey(&v46, v44, &v42, &v43, v41);
    v25 = v43;
    if ( v31 >= 0 && *((_DWORD *)v43 + 3) == 4 )
    {
      v32 = BYTE8(v54);
      if ( *(_DWORD *)&v43[*((unsigned int *)v43 + 2)] == 1 )
        v32 = 1;
      BYTE8(v54) = v32;
    }
    else
    {
      v32 = BYTE8(v54);
    }
    if ( v32 )
      goto LABEL_227;
    v44[0] = 4718662;
    v45 = L"RefsTelemetryPerfCollectionInterval";
    if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) >= 0 )
    {
      v33 = *((_DWORD *)v43 + 3);
      if ( v33 == 4 )
      {
        v34 = *(unsigned int *)&v43[*((unsigned int *)v43 + 2)];
LABEL_225:
        *(_QWORD *)&v54 = v34;
        goto LABEL_226;
      }
      if ( v33 == 8 )
      {
        v34 = *(_QWORD *)&v43[*((unsigned int *)v43 + 2)];
        goto LABEL_225;
      }
    }
LABEL_226:
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCount");
    RtlInitUnicodeString(&v49, L"RefsTelemetryIoSizeLevels");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevels");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      0,
      0,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountTrim");
    RtlInitUnicodeString(&v49, L"RefsTelemetryIoSizeLevelsTrim");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsTrim");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      0,
      1,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountFlush");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsFlush");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      0,
      2,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      0,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountDax");
    RtlInitUnicodeString(&v49, L"RefsTelemetryIoSizeLevelsDax");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsDax");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      1,
      0,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountTrimDax");
    RtlInitUnicodeString(&v49, L"RefsTelemetryIoSizeLevelsTrimDax");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsTrimDax");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      1,
      1,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountFlushDax");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsFlushDax");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      1,
      2,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      0,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountSmr");
    RtlInitUnicodeString(&v49, L"RefsTelemetryIoSizeLevelsSmr");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsSmr");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      2,
      0,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountTrimSmr");
    RtlInitUnicodeString(&v49, L"RefsTelemetryIoSizeLevelsTrimSmr");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsTrimSmr");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      2,
      1,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    RtlInitUnicodeString(&v48, L"RefsTelemetryPerfMinimumIoCountFlushSmr");
    RtlInitUnicodeString(&v47, L"RefsTelemetryLatencyLevelsFlushSmr");
    RefsTelemetryReadIoPerfRegistry(
      (unsigned int)&v53,
      2,
      2,
      (unsigned int)&v46,
      (__int64)&v42,
      (__int64)&v48,
      0,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)v41);
    v25 = v43;
LABEL_227:
    RefsInitializeTelemetry(&v53);
  }
  FsLibCleanupIoPerfTelemetrySettings(&v53);
  ExInitializeResourceLite(&RefsDynamicRegistrySettingsResource);
  v35 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x4A666552u);
  if ( v35 )
  {
    v35[16] = 256;
    *((_QWORD *)v35 + 6) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
    *((_BYTE *)v35 + 34) = 0;
    *((_DWORD *)v35 + 10) = 8126586;
    *((_QWORD *)v35 + 7) = 0;
    *((_QWORD *)v35 + 8) = RefsUpdateDynamicRegistrySettings;
    RefsWatchForRegistryChanges(v35);
  }
  v36 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x4A666552u);
  if ( v36 )
  {
    v36[16] = 256;
    *((_QWORD *)v36 + 6) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies";
    *((_BYTE *)v36 + 34) = 0;
    *((_DWORD *)v36 + 10) = 6815846;
    *((_QWORD *)v36 + 7) = 0;
    *((_QWORD *)v36 + 8) = RefsUpdateDynamicRegistrySettings;
    RefsWatchForRegistryChanges(v36);
  }
  RefsUpdateDynamicRegistrySettings(0);
  KeInitializeMutant(&StreamFileCreationMutex, 0);
  KeInitializeEvent(&RefsEncryptionPendingEvent, NotificationEvent, 1u);
  KeInitializeGuardedMutex(&RefsMcbMutex);
  qword_1C012D968 = (__int64)&RefsMcbLruQueue;
  RefsMcbLruQueue = (__int64)&RefsMcbLruQueue;
  InitializeSListHead(&RefsUnchainedMcbQueue);
  v37 = 8LL * (unsigned int)dword_1C012DF34;
  RefsMcbHighWaterMark = 16000 * v18;
  RefsMcbCurrentLevel = 0;
  RefsMcbLowWaterMark = 8000 * v18;
  if ( v37 > 0xFFFFFFFF )
    KeBugCheckEx(0x149u, 0x1A09F9u, 0, 0, 0);
  v38 = ExAllocatePoolWithTag((POOL_TYPE)512, v37, 0x72666552u);
  qword_1C012DF40 = v38;
  if ( !v38 )
  {
    Directory = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids, 3221225626LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_250;
LABEL_8:
    RefsStatusDebug(-1073741670);
LABEL_250:
    ExDeleteResourceLite(&stru_1C012E1E0);
    memset(&dword_1C012E1D0, 0, 0x80u);
    if ( P )
    {
      ExFreePoolWithTag(P, 0);
      P = 0;
    }
    RefsDeleteReservedBuffer(&qword_1C012E290);
    RefsDeleteReservedBuffer(&qword_1C012E2A8);
    RefsDeleteReservedBuffer(&qword_1C012E2C0);
    RefsDeleteReservedBuffer(&qword_1C012E2D8);
    MsKmeDeleteReservedIoRequests(qword_1C012E2F0);
    MsKmeDeleteReservedIoRuns(qword_1C012E4F0);
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
    if ( qword_1C012DF40 )
    {
      ExFreePoolWithTag(qword_1C012DF40, 0);
      qword_1C012DF40 = 0;
    }
    wil_UninitializeFeatureStaging();
    return Directory;
  }
  memset(v38, 0, 8LL * (unsigned int)dword_1C012DF34);
  RefsZeroExtendedInfo = 0;
  xmmword_1C012DD10 = 0;
  xmmword_1C012DD20 = 0;
  Directory = RefsInitialize();
  if ( Directory < 0 )
    goto LABEL_250;
  stru_1C012DFE8.Parameter = 0;
  stru_1C012DFE8.WorkerRoutine = (PWORKER_THREAD_ROUTINE)RefsCheckUsnTimeOut;
  stru_1C012DFE8.List.Flink = 0;
  KeInitializeTimer(&stru_1C012DFA8);
  KeInitializeDpc(&stru_1C012DF68, RefsUsnTimeOutDpc, 0);
  KeSetCoalescableTimer(&stru_1C012DFA8, (LARGE_INTEGER)-3000000000LL, 0, 0x3A98u, &stru_1C012DF68);
  stru_1C012E088.List.Flink = 0;
  stru_1C012E088.WorkerRoutine = (PWORKER_THREAD_ROUTINE)RefsPeriodicTimerCallback;
  stru_1C012E088.Parameter = &stru_1C012E088;
  KeInitializeTimer(&Timer);
  KeInitializeDpc(&Dpc, RefsPeriodicTimerDpc, 0);
  if ( !v25 )
  {
    v41[0] = 0;
    v43 = v61;
    v42 = 156;
  }
  v44[0] = 2621478;
  v45 = L"RefsGlobalPostLimit";
  if ( (int)RefsQueryValueKey(&v46, v44, &v42, &v43, v41) < 0
    || (v39 = *(_DWORD *)&v43[*((unsigned int *)v43 + 2)], v39 < 4) )
  {
    v39 = 4;
  }
  else if ( v39 > 200 )
  {
    v39 = 200;
  }
  KeInitializeSemaphore(&RefsGlobalPostThrottle, v39, v39);
  qword_1C012E0B8 = 0;
  dword_1C012E0C0 = 0;
  KeInitializeSpinLock(&RefsScavengerLock);
  RefsScavengerWorkList = 0;
  RefsScavengerRunning = 0;
  dword_1C012E6B4 = 4;
  IoRegisterFileSystem(DeviceObject);
  return 0;
}

```

## disassembly

```asm
0x1c01d7324  mov     [rsp-8+arg_10], rbx
0x1c01d7329  push    rbp
0x1c01d732a  push    rsi
0x1c01d732b  push    rdi
0x1c01d732c  push    r12
0x1c01d732e  push    r13
0x1c01d7330  push    r14
0x1c01d7332  push    r15
0x1c01d7334  lea     rbp, [rsp-180h]
0x1c01d733c  sub     rsp, 280h
0x1c01d7343  mov     rax, cs:__security_cookie
0x1c01d734a  xor     rax, rsp
0x1c01d734d  mov     [rbp+1B0h+var_40], rax
0x1c01d7354  xor     r12d, r12d
0x1c01d7357  xorps   xmm0, xmm0
0x1c01d735a  xorps   xmm1, xmm1
0x1c01d735d  mov     [rbp+1B0h+var_1F8], r12
0x1c01d7361  movups  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm0
0x1c01d7365  mov     [rsp+2B0h+var_24C], r12d
0x1c01d736a  mov     r15d, r12d
0x1c01d736d  movups  [rsp+2B0h+var_240], xmm0
0x1c01d7372  mov     [rbp+1B0h+var_1FC], r12d
0x1c01d7376  mov     rdi, rdx
0x1c01d7379  movups  [rbp+1B0h+var_1C8], xmm1
0x1c01d737d  mov     [rbp+1B0h+CompressBufferWorkSpaceSize], r12d
0x1c01d7381  mov     rsi, rcx
0x1c01d7384  mov     [rbp+1B0h+CompressFragmentWorkSpaceSize], r12d
0x1c01d7388  call    wil_InitializeFeatureStaging
0x1c01d738d  lea     rcx, WPP_MAIN_CB.DeviceExtension; lpVersionInformation
0x1c01d7394  mov     dword ptr cs:WPP_MAIN_CB.DeviceExtension, 11Ch
0x1c01d739e  call    cs:__imp_RtlGetVersion
0x1c01d73a5  nop     dword ptr [rax+rax+00h]
0x1c01d73aa  mov     ecx, 0FFFFh; GroupNumber
0x1c01d73af  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1c01d73b6  nop     dword ptr [rax+rax+00h]
0x1c01d73bb  mov     cs:RefsNumberProcessors, eax
0x1c01d73c1  lea     r13d, [r12+2]
0x1c01d73c6  mov     rax, 861C46800h
0x1c01d73d0  lea     r8, [rbp+1B0h+CompressFragmentWorkSpaceSize]; CompressFragmentWorkSpaceSize
0x1c01d73d4  mov     ecx, r13d; CompressionFormatAndEngine
0x1c01d73d7  mov     cs:RefsLastAccess, rax
0x1c01d73de  lea     rdx, [rbp+1B0h+CompressBufferWorkSpaceSize]; CompressBufferWorkSpaceSize
0x1c01d73e2  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x1c01d73e9  nop     dword ptr [rax+rax+00h]
0x1c01d73ee  xor     edx, edx; Val
0x1c01d73f0  lea     rcx, RefsData; void *
0x1c01d73f7  mov     r8d, 898h; Size
0x1c01d73fd  call    memset
0x1c01d7402  call    cs:__imp_FsRtlQueryMaximumVirtualDiskNestingLevel
0x1c01d7409  nop     dword ptr [rax+rax+00h]
0x1c01d740e  lea     rcx, stru_1C012E258; Mutex
0x1c01d7415  mov     cs:RefsReserveStackStorage, r12
0x1c01d741c  mov     cs:RefsReserveStackCleanup, r12
0x1c01d7423  call    cs:__imp_KeInitializeGuardedMutex
0x1c01d742a  nop     dword ptr [rax+rax+00h]
0x1c01d742f  xor     edx, edx; Val
0x1c01d7431  lea     r8d, [r13+7Eh]; Size
0x1c01d7435  lea     rcx, dword_1C012E1D0; void *
0x1c01d743c  call    memset
0x1c01d7441  lea     rcx, stru_1C012E1E0; Resource
0x1c01d7448  mov     cs:dword_1C012E1D0, 1200844h
0x1c01d7452  call    cs:__imp_ExInitializeResourceLite
0x1c01d7459  nop     dword ptr [rax+rax+00h]
0x1c01d745e  call    MsInitializeFastResourceLibrary
0x1c01d7463  mov     ebx, eax
0x1c01d7465  test    eax, eax
0x1c01d7467  js      loc_1C01D9664
0x1c01d746d  mov     ebx, 1000h
0x1c01d7472  mov     r8d, 4A666552h; Tag
0x1c01d7478  mov     edx, ebx; NumberOfBytes
0x1c01d747a  mov     ecx, 200h; PoolType
0x1c01d747f  call    cs:__imp_ExAllocatePoolWithTag
0x1c01d7486  nop     dword ptr [rax+rax+00h]
0x1c01d748b  mov     cs:P, rax
0x1c01d7492  test    rax, rax
0x1c01d7495  jnz     short loc_1C01D74FE
0x1c01d7497  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d749e  lea     r13, WPP_GLOBAL_Control
0x1c01d74a5  mov     ebx, 0C000009Ah
0x1c01d74aa  cmp     rcx, r13
0x1c01d74ad  jz      short loc_1C01D74D7
0x1c01d74af  mov     r14d, 100h
0x1c01d74b5  test    [rcx+2Ch], r14d
0x1c01d74b9  jz      short loc_1C01D74D7
0x1c01d74bb  cmp     byte ptr [rcx+29h], 4
0x1c01d74bf  jb      short loc_1C01D74D7
0x1c01d74c1  mov     rcx, [rcx+18h]
0x1c01d74c5  lea     edx, [rax+0Bh]
0x1c01d74c8  mov     r9d, ebx
0x1c01d74cb  lea     r8, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids
0x1c01d74d2  call    WPP_SF_D
0x1c01d74d7  mov     al, cs:RefsStatusDebugEnabled
0x1c01d74dd  test    al, al
0x1c01d74df  jz      loc_1C01D9664
0x1c01d74e5  mov     r8d, 37Ch
0x1c01d74eb  lea     rdx, aNtfsinitC; "NtfsInit.c"
0x1c01d74f2  mov     ecx, ebx; Status
0x1c01d74f4  call    RefsStatusDebug
0x1c01d74f9  jmp     loc_1C01D9664
0x1c01d74fe  mov     r8, rbx; Size
0x1c01d7501  xor     edx, edx; Val
0x1c01d7503  mov     rcx, rax; void *
0x1c01d7506  call    memset
0x1c01d750b  mov     r14d, 40000h
0x1c01d7511  lea     rcx, qword_1C012E290
0x1c01d7518  mov     edx, r14d
0x1c01d751b  call    RefsInitializeReservedBuffer
0x1c01d7520  mov     ebx, eax
0x1c01d7522  test    eax, eax
0x1c01d7524  js      loc_1C01D9664
0x1c01d752a  mov     edx, 44000h
0x1c01d752f  lea     rcx, qword_1C012E2A8
0x1c01d7536  call    RefsInitializeReservedBuffer
0x1c01d753b  mov     ebx, eax
0x1c01d753d  test    eax, eax
0x1c01d753f  js      loc_1C01D9664
0x1c01d7545  mov     edx, [rbp+1B0h+CompressFragmentWorkSpaceSize]
0x1c01d7548  lea     rcx, qword_1C012E2C0
0x1c01d754f  call    RefsInitializeReservedBuffer
0x1c01d7554  mov     ebx, eax
0x1c01d7556  test    eax, eax
0x1c01d7558  js      loc_1C01D9664
0x1c01d755e  mov     edx, r14d
0x1c01d7561  lea     rcx, qword_1C012E2D8
0x1c01d7568  call    RefsInitializeReservedBuffer
0x1c01d756d  mov     ebx, eax
0x1c01d756f  test    eax, eax
0x1c01d7571  js      loc_1C01D9664
0x1c01d7577  lea     rdx, aRefs; "\\Refs"
0x1c01d757e  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x1c01d7582  call    cs:__imp_RtlInitUnicodeString
0x1c01d7589  nop     dword ptr [rax+rax+00h]
0x1c01d758e  lea     rax, [rbp+1B0h+var_1F8]
0x1c01d7592  mov     r9d, 8; DeviceType
0x1c01d7598  mov     [rsp+2B0h+DeviceObject], rax; DeviceObject
0x1c01d759d  lea     r8, [rbp+1B0h+DestinationString]; DeviceName
0x1c01d75a1  mov     [rsp+2B0h+Exclusive], r12b; Exclusive
0x1c01d75a6  xor     edx, edx; DeviceExtensionSize
0x1c01d75a8  mov     rcx, rsi; DriverObject
0x1c01d75ab  mov     [rsp+2B0h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x1c01d75b0  call    cs:__imp_IoCreateDevice
0x1c01d75b7  nop     dword ptr [rax+rax+00h]
0x1c01d75bc  mov     ebx, eax
0x1c01d75be  test    eax, eax
0x1c01d75c0  js      loc_1C01D9664
0x1c01d75c6  mov     rax, [rbp+1B0h+var_1F8]
0x1c01d75ca  lea     rdx, qword_1C012E2F0
0x1c01d75d1  mov     r8d, 14h
0x1c01d75d7  bts     dword ptr [rax+30h], 1Bh
0x1c01d75dc  mov     rcx, [rbp+1B0h+var_1F8]
0x1c01d75e0  call    MsKmeInitializeReservedIoRequests
0x1c01d75e5  mov     ebx, eax
0x1c01d75e7  test    eax, eax
0x1c01d75e9  js      loc_1C01D9664
0x1c01d75ef  lea     rcx, qword_1C012E4F0
0x1c01d75f6  call    MsKmeInitializeReservedIoRuns
0x1c01d75fb  mov     ebx, eax
0x1c01d75fd  test    eax, eax
0x1c01d75ff  js      loc_1C01D9664
0x1c01d7605  call    RefsInitializeQueryDirectory
0x1c01d760a  mov     ebx, eax
0x1c01d760c  test    eax, eax
0x1c01d760e  js      loc_1C01D9664
0x1c01d7614  lea     r9, RefsReserveStackStorage
0x1c01d761b  xor     r8d, r8d
0x1c01d761e  mov     dl, 3
0x1c01d7620  xor     ecx, ecx
0x1c01d7622  call    cs:__imp_KeAllocateCalloutStackEx
0x1c01d7629  nop     dword ptr [rax+rax+00h]
0x1c01d762e  mov     ebx, eax
0x1c01d7630  test    eax, eax
0x1c01d7632  js      loc_1C01D9664
0x1c01d7638  lea     r9, RefsReserveStackCleanup
0x1c01d763f  xor     r8d, r8d
0x1c01d7642  mov     dl, 1
0x1c01d7644  xor     ecx, ecx
0x1c01d7646  call    cs:__imp_KeAllocateCalloutStackEx
0x1c01d764d  nop     dword ptr [rax+rax+00h]
0x1c01d7652  mov     ebx, eax
0x1c01d7654  test    eax, eax
0x1c01d7656  js      loc_1C01D9664
0x1c01d765c  movzx   eax, word ptr [rdi]
0x1c01d765f  mov     ecx, 11h; PoolType
0x1c01d7664  add     ax, r13w
0x1c01d7668  mov     r8d, 4A666552h; Tag
0x1c01d766e  movzx   edx, ax; NumberOfBytes
0x1c01d7671  mov     cs:RefsRegistryPath.MaximumLength, dx
0x1c01d7678  movzx   eax, word ptr [rdi]
0x1c01d767b  mov     cs:RefsRegistryPath.Length, ax
0x1c01d7682  call    cs:__imp_ExAllocatePoolWithTag
0x1c01d7689  nop     dword ptr [rax+rax+00h]
0x1c01d768e  mov     cs:RefsRegistryPath.Buffer, rax
0x1c01d7695  test    rax, rax
0x1c01d7698  jnz     short loc_1C01D76F3
0x1c01d769a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01d76a1  lea     r13, WPP_GLOBAL_Control
0x1c01d76a8  mov     ebx, 0C000009Ah
0x1c01d76ad  cmp     rcx, r13
0x1c01d76b0  jz      short loc_1C01D76DA
0x1c01d76b2  mov     r14d, 100h
0x1c01d76b8  test    [rcx+2Ch], r14d
0x1c01d76bc  jz      short loc_1C01D76DA
0x1c01d76be  cmp     byte ptr [rcx+29h], 4
0x1c01d76c2  jb      short loc_1C01D76DA
0x1c01d76c4  mov     rcx, [rcx+18h]
0x1c01d76c8  lea     edx, [rax+0Ch]
0x1c01d76cb  mov     r9d, ebx
0x1c01d76ce  lea     r8, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids
0x1c01d76d5  call    WPP_SF_D
0x1c01d76da  mov     al, cs:RefsStatusDebugEnabled
0x1c01d76e0  test    al, al
0x1c01d76e2  jz      loc_1C01D9664
0x1c01d76e8  mov     r8d, 405h
0x1c01d76ee  jmp     loc_1C01D74EB
0x1c01d76f3  mov     rdx, rdi; SourceString
0x1c01d76f6  lea     rcx, RefsRegistryPath; DestinationString
0x1c01d76fd  call    cs:__imp_RtlCopyUnicodeString
0x1c01d7704  nop     dword ptr [rax+rax+00h]
0x1c01d7709  lea     rax, RefsFsdDispatchWait
0x1c01d7710  mov     [rsi+98h], rax
0x1c01d7717  mov     [rsi+140h], rax
0x1c01d771e  mov     [rsi+138h], rax
0x1c01d7725  mov     [rsi+0B0h], rax
0x1c01d772c  mov     [rsi+0A8h], rax
0x1c01d7733  lea     rax, RefsFsdDispatch
0x1c01d773a  mov     [rsi+0C8h], rax
0x1c01d7741  mov     [rsi+0C0h], rax
0x1c01d7748  mov     [rsi+118h], rax
0x1c01d774f  mov     [rsi+110h], rax
0x1c01d7756  lea     rax, RefsFsdLockControl
0x1c01d775d  mov     [rsi+0F8h], rax
0x1c01d7764  lea     rax, RefsFsdDirectoryControl
0x1c01d776b  mov     [rsi+0D0h], rax
0x1c01d7772  lea     rax, RefsFsdSetInformation
0x1c01d7779  mov     [rsi+0A0h], rax
0x1c01d7780  lea     rax, RefsFsdCreate
0x1c01d7787  mov     [rsi+70h], rax
0x1c01d778b  lea     rax, RefsFsdClose
0x1c01d7792  mov     [rsi+80h], rax
0x1c01d7799  lea     rax, RefsFsdRead
0x1c01d77a0  mov     [rsi+88h], rax
0x1c01d77a7  lea     rax, RefsFsdWrite
0x1c01d77ae  mov     [rsi+90h], rax
0x1c01d77b5  lea     rax, RefsFsdFlushBuffers
0x1c01d77bc  mov     [rsi+0B8h], rax
0x1c01d77c3  lea     rax, RefsFsdFileSystemControl
0x1c01d77ca  mov     [rsi+0D8h], rax
0x1c01d77d1  lea     rax, RefsFsdCleanup
0x1c01d77d8  mov     [rsi+100h], rax
0x1c01d77df  lea     rax, RefsFsdShutdown
0x1c01d77e6  mov     [rsi+0F0h], rax
0x1c01d77ed  lea     rax, RefsFsdPnp
0x1c01d77f4  mov     [rsi+148h], rax
0x1c01d77fb  lea     rax, RefsFsdDeviceControl
0x1c01d7802  mov     [rsi+0E0h], rax
0x1c01d7809  lea     rax, RefsFastIoDispatch
0x1c01d7810  mov     [rsi+50h], rax
0x1c01d7814  lea     rax, RefsFastIoCheckIfPossible
0x1c01d781b  mov     cs:qword_1C012DC28, rax
0x1c01d7822  lea     rax, RefsCopyReadA
0x1c01d7829  mov     cs:qword_1C012DC30, rax
0x1c01d7830  lea     rax, RefsCopyWriteA
0x1c01d7837  mov     cs:qword_1C012DC38, rax
0x1c01d783e  lea     rax, RefsFastQueryBasicInfo
0x1c01d7845  mov     cs:qword_1C012DC40, rax
0x1c01d784c  lea     rax, RefsFastQueryStdInfo
0x1c01d7853  mov     cs:qword_1C012DC48, rax
0x1c01d785a  lea     rax, RefsFastLock
0x1c01d7861  mov     cs:qword_1C012DC50, rax
0x1c01d7868  lea     rax, RefsFastUnlockSingle
0x1c01d786f  mov     cs:qword_1C012DC58, rax
0x1c01d7876  lea     rax, RefsFastUnlockAll
0x1c01d787d  mov     cs:qword_1C012DC60, rax
0x1c01d7884  lea     rax, RefsFastUnlockAllByKey
0x1c01d788b  mov     cs:qword_1C012DC68, rax
0x1c01d7892  lea     rax, RefsFastQueryNetworkOpenInfo
0x1c01d7899  mov     cs:qword_1C012DC90, rax
0x1c01d78a0  lea     rax, RefsReleaseForCreateSection
0x1c01d78a7  mov     cs:qword_1C012DC80, rax
0x1c01d78ae  lea     rax, RefsAcquireFileForModWrite
0x1c01d78b5  mov     cs:qword_1C012DC98, rax
0x1c01d78bc  lea     rax, RefsReleaseFileForModWrite
0x1c01d78c3  mov     cs:qword_1C012DCE8, rax
0x1c01d78ca  lea     rax, RefsMdlReadA
0x1c01d78d1  mov     cs:qword_1C012DCA0, rax
0x1c01d78d8  mov     rax, cs:__imp_FsRtlMdlReadCompleteDev
0x1c01d78df  mov     cs:qword_1C012DCA8, rax
0x1c01d78e6  lea     rax, RefsPrepareMdlWriteA
0x1c01d78ed  mov     cs:qword_1C012DCB0, rax
0x1c01d78f4  mov     rax, cs:__imp_FsRtlMdlWriteCompleteDev
0x1c01d78fb  mov     cs:qword_1C012DCB8, rax
0x1c01d7902  lea     rax, RefsNetworkOpenCreate
0x1c01d7909  mov     cs:RefsFastIoDispatch, 0E0h
0x1c01d7913  mov     cs:qword_1C012DC70, r12
0x1c01d791a  mov     cs:qword_1C012DC88, r12
0x1c01d7921  mov     cs:qword_1C012DC78, r12
0x1c01d7928  mov     cs:qword_1C012DCE0, rax
0x1c01d792f  lea     rax, RefsAcquireFileForCcFlush
0x1c01d7936  mov     cs:qword_1C012DCF0, rax
0x1c01d793d  lea     rax, RefsReleaseFileForCcFlush
  ... truncated ...
```
