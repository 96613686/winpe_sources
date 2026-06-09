# DriverEntry

- ea: `0x140061078`
- end: `0x14006192f`
- name: `DriverEntry`
- size: `2231`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140061010`

## callees

- `0x14000c680`
- `0x14004d5c0`
- `0x140061078`
- `0x140061938`
- `0x140061b08`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14006153d`
- `ntoskrnl!KeInitializeEvent` at `0x1400617f7`
- `ntoskrnl!KeInitializeEvent` at `0x140061810`
- `ntoskrnl!KeInitializeEvent` at `0x14006153d`
- `ntoskrnl!KeInitializeEvent` at `0x1400617f7`
- `ntoskrnl!KeInitializeEvent` at `0x140061810`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400615fc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400615fc`
- `ntoskrnl!ObfReferenceObject` at `0x140061836`
- `ntoskrnl!ObfReferenceObject` at `0x14006185c`
- `ntoskrnl!ObfReferenceObject` at `0x140061836`
- `ntoskrnl!ObfReferenceObject` at `0x14006185c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400610cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061121`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400610cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061121`
- `ntoskrnl!IoCreateDevice` at `0x140061102`
- `ntoskrnl!IoCreateDevice` at `0x140061153`
- `ntoskrnl!IoCreateDevice` at `0x140061102`
- `ntoskrnl!IoCreateDevice` at `0x140061153`
- `ntoskrnl!IoDeleteDevice` at `0x14006116c`
- `ntoskrnl!IoDeleteDevice` at `0x1400614f2`
- `ntoskrnl!IoDeleteDevice` at `0x14006116c`
- `ntoskrnl!IoDeleteDevice` at `0x1400614f2`
- `ntoskrnl!FsRtlCopyRead` at `0x1400612aa`
- `ntoskrnl!FsRtlCopyWrite` at `0x1400612bd`
- `ntoskrnl!FsRtlMdlReadDev` at `0x140061349`
- `ntoskrnl!FsRtlMdlReadCompleteDev` at `0x140061357`
- `ntoskrnl!FsRtlPrepareMdlWriteDev` at `0x140061365`
- `ntoskrnl!FsRtlMdlWriteCompleteDev` at `0x140061373`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14006139c`
- `ntoskrnl!FsRtlRegisterFileSystemFilterCallbacks` at `0x14006139c`
- `ntoskrnl!IoAllocateWorkItem` at `0x140061432`
- `ntoskrnl!IoAllocateWorkItem` at `0x140061432`
- `ntoskrnl!IoFreeWorkItem` at `0x1400614c5`
- `ntoskrnl!IoFreeWorkItem` at `0x14006151d`
- `ntoskrnl!IoFreeWorkItem` at `0x1400614c5`
- `ntoskrnl!IoFreeWorkItem` at `0x14006151d`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1400614ae`
- `ntoskrnl!KeAllocateCalloutStackEx` at `0x1400614ae`
- `ntoskrnl!KeInitializeSpinLock` at `0x140061550`
- `ntoskrnl!KeInitializeSpinLock` at `0x140061550`
- `ntoskrnl!MmQuerySystemSize` at `0x14006155c`
- `ntoskrnl!MmQuerySystemSize` at `0x14006155c`
- `ntoskrnl!KeQueryActiveProcessorCount` at `0x140061611`
- `ntoskrnl!KeQueryActiveProcessorCount` at `0x140061611`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006171b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006171b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140061751`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14006177e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400617af`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140061751`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14006177e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400617af`
- `ntoskrnl!InitializeSListHead` at `0x1400617c2`
- `ntoskrnl!InitializeSListHead` at `0x1400617c2`
- `ntoskrnl!IoRegisterFileSystem` at `0x140061823`
- `ntoskrnl!IoRegisterFileSystem` at `0x140061849`
- `ntoskrnl!IoRegisterFileSystem` at `0x140061823`
- `ntoskrnl!IoRegisterFileSystem` at `0x140061849`
- `ntoskrnl!PsIsDiskCountersEnabled` at `0x140061883`
- `ntoskrnl!PsIsDiskCountersEnabled` at `0x140061883`
- `ntoskrnl!PoRegisterCoalescingCallback` at `0x1400618ac`
- `ntoskrnl!PoRegisterCoalescingCallback` at `0x1400618ac`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x140061904`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x140061904`
- `ntoskrnl!EtwRegister` at `0x1400618cb`
- `ntoskrnl!EtwRegister` at `0x1400618cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400614da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400614da`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140061462`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140061462`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  USHORT v3; // si
  NTSTATUS result; // eax
  int v5; // ebx
  struct _DEVICE_OBJECT *v6; // rcx
  PVOID PoolWithTag; // rax
  __int64 v8; // rdx
  void *v9; // rbx
  MM_SYSTEMSIZE SystemSize; // eax
  ULONG ActiveProcessorCount; // eax
  __int64 v12; // rdx
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-59h] BYREF
  _FS_FILTER_CALLBACKS Callbacks; // [rsp+60h] [rbp-49h] BYREF

  DestinationString = 0;
  memset(&Callbacks, 0, sizeof(Callbacks));
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Fat");
  v3 = 8;
  result = IoCreateDevice(DriverObject, 0, &DestinationString, 8u, 0, 0, &FatDiskFileSystemDeviceObject);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"\\FatCdrom");
    v5 = IoCreateDevice(DriverObject, 0, &DestinationString, 3u, 0, 0, &FatCdromFileSystemDeviceObject);
    if ( v5 < 0 )
    {
      v6 = FatDiskFileSystemDeviceObject;
LABEL_4:
      IoDeleteDevice(v6);
      return v5;
    }
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&FatFsdCreate;
    DriverObject->FastIoDispatch = (PFAST_IO_DISPATCH)&FatFastIoDispatch;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&FatFsdClose;
    DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)&FatFsdRead;
    DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)&FatFsdWrite;
    DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)&FatFsdQueryInformation;
    DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)&FatFsdSetInformation;
    DriverObject->MajorFunction[7] = (PDRIVER_DISPATCH)&FatFsdQueryEa;
    DriverObject->MajorFunction[8] = (PDRIVER_DISPATCH)&FatFsdQueryEa;
    DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)&FatFsdFlushBuffers;
    DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)&FatFsdQueryVolumeInformation;
    DriverObject->MajorFunction[11] = (PDRIVER_DISPATCH)&FatFsdSetVolumeInformation;
    DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)&FatFsdCleanup;
    DriverObject->MajorFunction[12] = (PDRIVER_DISPATCH)&FatFsdDirectoryControl;
    DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)&FatFsdFileSystemControl;
    DriverObject->MajorFunction[17] = (PDRIVER_DISPATCH)&FatFsdLockControl;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&FatFsdDeviceControl;
    DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)&FatFsdShutdown;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)&FatFsdPnp;
    memset(&FatFastIoDispatch, 0, 0xE0u);
    FatFastIoDispatch = 224;
    qword_140017F08 = (__int64)FatFastIoCheckIfPossible;
    qword_140017F10 = (__int64)FsRtlCopyRead;
    qword_140017F18 = (__int64)FsRtlCopyWrite;
    qword_140017F20 = (__int64)&FatFastQueryBasicInfo;
    qword_140017F28 = (__int64)&FatFastQueryStdInfo;
    qword_140017F30 = (__int64)FatFastLock;
    qword_140017F38 = (__int64)FatFastUnlockSingle;
    qword_140017F40 = (__int64)FatFastUnlockAll;
    qword_140017F48 = (__int64)FatFastUnlockAllByKey;
    qword_140017F70 = (__int64)&FatFastQueryNetworkOpenInfo;
    qword_140017FD0 = (__int64)FatAcquireForCcFlush;
    qword_140017FD8 = (__int64)FatReleaseForCcFlush;
    qword_140017F80 = (__int64)FsRtlMdlReadDev;
    qword_140017F88 = (__int64)FsRtlMdlReadCompleteDev;
    qword_140017F90 = (__int64)FsRtlPrepareMdlWriteDev;
    qword_140017F98 = (__int64)FsRtlMdlWriteCompleteDev;
    memset(&Callbacks, 0, sizeof(Callbacks));
    Callbacks.SizeOfFsFilterCallbacks = 120;
    Callbacks.PreAcquireForSectionSynchronization = (PFS_FILTER_CALLBACK)FatFilterCallbackAcquireForCreateSection;
    v5 = FsRtlRegisterFileSystemFilterCallbacks(DriverObject, &Callbacks);
    if ( v5 < 0 )
    {
LABEL_13:
      IoDeleteDevice(FatDiskFileSystemDeviceObject);
      v6 = FatCdromFileSystemDeviceObject;
      goto LABEL_4;
    }
    memset(&FatData, 0, 0x200u);
    qword_140017CB8 = (__int64)&qword_140017CB0;
    qword_140017CB0 = (__int64)&qword_140017CB0;
    qword_140017CD0 = (__int64)FatCdromFileSystemDeviceObject;
    qword_140017D60 = (__int64)&qword_140017D58;
    qword_140017D58 = (__int64)&qword_140017D58;
    qword_140017D78 = (__int64)&qword_140017D70;
    qword_140017D70 = (__int64)&qword_140017D70;
    FatData = 33555712;
    ::DriverObject = DriverObject;
    qword_140017CC8 = (__int64)FatDiskFileSystemDeviceObject;
    IoWorkItem = IoAllocateWorkItem(FatDiskFileSystemDeviceObject);
    if ( !IoWorkItem )
    {
LABEL_12:
      v5 = -1073741670;
      goto LABEL_13;
    }
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x1000u, 0x5A746146u);
    v9 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported || !PoolWithTag )
    {
      P = PoolWithTag;
      if ( !PoolWithTag )
      {
        IoFreeWorkItem(IoWorkItem);
        goto LABEL_12;
      }
    }
    else
    {
      memset(PoolWithTag, 0, 0x1000u);
      P = v9;
    }
    LOBYTE(v8) = 4;
    if ( (int)KeAllocateCalloutStackEx(0, v8, 0, &qword_140017E98) < 0 )
    {
      IoFreeWorkItem(IoWorkItem);
      ExFreePoolWithTag(P, 0);
      goto LABEL_12;
    }
    KeInitializeEvent(&Event, NotificationEvent, 1u);
    KeInitializeSpinLock(&SpinLock);
    SystemSize = MmQuerySystemSize();
    if ( SystemSize )
    {
      if ( SystemSize == MmMediumSystem )
      {
        FatMaxDelayedCloseCount = 64;
      }
      else
      {
        v3 = 16;
        FatMaxDelayedCloseCount = 256;
      }
    }
    else
    {
      v3 = 4;
      FatMaxDelayedCloseCount = 16;
    }
    *(_QWORD *)&qword_140017DB0 = FatNoOpAcquire;
    *(_QWORD *)&qword_140017D90 = FatAcquireFcbForLazyWrite;
    qword_140017D98 = (__int64)FatReleaseFcbFromLazyWrite;
    qword_140017DA0 = (__int64)FatAcquireFcbForReadAhead;
    qword_140017DA8 = (__int64)FatReleaseFcbFromReadAhead;
    qword_140017DB8 = (__int64)FatNoOpRelease;
    qword_140017DC8 = (__int64)FatNoOpRelease;
    qword_140017DC0 = (__int64)FatNoOpAcquire;
    qword_140017D40 = (__int64)IoGetCurrentProcess();
    ActiveProcessorCount = KeQueryActiveProcessorCount(0);
    byte_140017D4D |= 2u;
    dword_140017D48 = ActiveProcessorCount;
    *(_DWORD *)&ValueName.Length = 1703960;
    ValueName.Buffer = L"FatEnableEfs";
    if ( (int)FatGetCompatibilityModeValue(&ValueName) >= 0 )
      byte_140017D4D &= ~2u;
    byte_140017D4C &= ~0x80u;
    ValueName.Buffer = L"Fat12DisableFlushOnCleanup";
    *(_DWORD *)&ValueName.Length = 3538996;
    if ( (int)FatGetCompatibilityModeValue(&ValueName) >= 0 )
      byte_140017D4C &= ~0x80u;
    *(_DWORD *)&ValueName.Length = 2097182;
    ValueName.Buffer = L"Win31FileSystem";
    FatGetCompatibilityModeValue(&ValueName);
    byte_140017D4C |= 1u;
    *(_DWORD *)&ValueName.Length = 3801144;
    ValueName.Buffer = L"FatDisableCodePageInvariance";
    FatGetCompatibilityModeValue(&ValueName);
    byte_140017D4C |= 0x10u;
    ExInitializeResourceLite(&Resource);
    ExInitializeNPagedLookasideList(&FatIrpContextLookasideList, 0, 0, 0x210u, 0x90u, 0x49746146u, v3);
    ExInitializeNPagedLookasideList(&FatNonPagedFcbLookasideList, 0, 0, 0x210u, 0x78u, 0x4E746146u, v3);
    ExInitializeNPagedLookasideList(&FatEResourceLookasideList, 0, 0, 0x210u, 0x68u, 0x45746146u, v3);
    InitializeSListHead(&FatCloseContextSList);
    FatCloseQueueMutex.Count = 1;
    FatCloseQueueMutex.Owner = 0;
    FatCloseQueueMutex.Contention = 0;
    KeInitializeEvent(&FatCloseQueueMutex.Event, SynchronizationEvent, 0);
    KeInitializeEvent(&FatReserveEvent, SynchronizationEvent, 1u);
    IoRegisterFileSystem(FatDiskFileSystemDeviceObject);
    ObfReferenceObject(FatDiskFileSystemDeviceObject);
    IoRegisterFileSystem(FatCdromFileSystemDeviceObject);
    ObfReferenceObject(FatCdromFileSystemDeviceObject);
    byte_140017D4C = byte_140017D4C & 0xFD | (2 * (FatIsFujitsuFMR() & 1));
    FatDiskAccountingEnabled = (unsigned __int8)PsIsDiskCountersEnabled();
    LOBYTE(v12) = 1;
    PoRegisterCoalescingCallback(FatCoalescingCallback, v12, FatCoalescingRegistration, 0);
    if ( EtwRegister(&FatSqmEventProvider, 0, 0, &RegHandle) < 0 )
      RegHandle = 0;
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1400170C0);
    IoRegisterDriverReinitialization(DriverObject, FatLoadAddOns, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140061078  mov     [rsp-8+arg_0], rbx
0x14006107d  mov     [rsp-8+arg_8], rsi
0x140061082  push    rbp
0x140061083  push    rdi
0x140061084  push    r12
0x140061086  push    r13
0x140061088  push    r15
0x14006108a  lea     rbp, [rsp-37h]
0x14006108f  sub     rsp, 0E0h
0x140061096  mov     rdi, rcx
0x140061099  xorps   xmm0, xmm0
0x14006109c  mov     r13d, 78h ; 'x'
0x1400610a2  lea     rcx, [rbp+57h+Callbacks]; void *
0x1400610a6  mov     r8d, r13d; Size
0x1400610a9  xor     edx, edx; Val
0x1400610ab  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400610af  call    memset
0x1400610b4  xorps   xmm0, xmm0
0x1400610b7  mov     [rbp+57h+arg_10], 0
0x1400610be  lea     rdx, aFat; "\\Fat"
0x1400610c5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400610c9  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1400610cd  call    cs:__imp_RtlInitUnicodeString
0x1400610d4  nop     dword ptr [rax+rax+00h]
0x1400610d9  lea     rax, FatDiskFileSystemDeviceObject
0x1400610e0  xor     edx, edx; DeviceExtensionSize
0x1400610e2  mov     [rsp+100h+DeviceObject], rax; DeviceObject
0x1400610e7  lea     esi, [r13-70h]
0x1400610eb  mov     [rsp+100h+Exclusive], 0; Exclusive
0x1400610f0  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x1400610f4  mov     r9d, esi; DeviceType
0x1400610f7  mov     [rsp+100h+DeviceCharacteristics], 0; DeviceCharacteristics
0x1400610ff  mov     rcx, rdi; DriverObject
0x140061102  call    cs:__imp_IoCreateDevice
0x140061109  nop     dword ptr [rax+rax+00h]
0x14006110e  test    eax, eax
0x140061110  js      loc_140061912
0x140061116  lea     rdx, aFatcdrom; "\\FatCdrom"
0x14006111d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140061121  call    cs:__imp_RtlInitUnicodeString
0x140061128  nop     dword ptr [rax+rax+00h]
0x14006112d  lea     rax, FatCdromFileSystemDeviceObject
0x140061134  xor     edx, edx; DeviceExtensionSize
0x140061136  mov     [rsp+100h+DeviceObject], rax; DeviceObject
0x14006113b  lea     r9d, [r13-75h]; DeviceType
0x14006113f  mov     [rsp+100h+Exclusive], 0; Exclusive
0x140061144  lea     r8, [rbp+57h+DestinationString]; DeviceName
0x140061148  mov     rcx, rdi; DriverObject
0x14006114b  mov     [rsp+100h+DeviceCharacteristics], 0; DeviceCharacteristics
0x140061153  call    cs:__imp_IoCreateDevice
0x14006115a  nop     dword ptr [rax+rax+00h]
0x14006115f  mov     ebx, eax
0x140061161  test    eax, eax
0x140061163  jns     short loc_14006117F
0x140061165  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x14006116c  call    cs:__imp_IoDeleteDevice
0x140061173  nop     dword ptr [rax+rax+00h]
0x140061178  mov     eax, ebx
0x14006117a  jmp     loc_140061912
0x14006117f  lea     rax, FatFsdCreate
0x140061186  mov     ebx, 0E0h
0x14006118b  mov     [rdi+70h], rax
0x14006118f  lea     rcx, FatFastIoDispatch; void *
0x140061196  lea     rax, FatFsdClose
0x14006119d  mov     [rdi+50h], rcx
0x1400611a1  mov     [rdi+80h], rax
0x1400611a8  mov     r8d, ebx; Size
0x1400611ab  lea     rax, FatFsdRead
0x1400611b2  xor     edx, edx; Val
0x1400611b4  mov     [rdi+88h], rax
0x1400611bb  lea     rax, FatFsdWrite
0x1400611c2  mov     [rdi+90h], rax
0x1400611c9  lea     rax, FatFsdQueryInformation
0x1400611d0  mov     [rdi+98h], rax
0x1400611d7  lea     rax, FatFsdSetInformation
0x1400611de  mov     [rdi+0A0h], rax
0x1400611e5  lea     rax, FatFsdQueryEa
0x1400611ec  mov     [rdi+0A8h], rax
0x1400611f3  lea     rax, FatFsdQueryEa
0x1400611fa  mov     [rdi+0B0h], rax
0x140061201  lea     rax, FatFsdFlushBuffers
0x140061208  mov     [rdi+0B8h], rax
0x14006120f  lea     rax, FatFsdQueryVolumeInformation
0x140061216  mov     [rdi+0C0h], rax
0x14006121d  lea     rax, FatFsdSetVolumeInformation
0x140061224  mov     [rdi+0C8h], rax
0x14006122b  lea     rax, FatFsdCleanup
0x140061232  mov     [rdi+100h], rax
0x140061239  lea     rax, FatFsdDirectoryControl
0x140061240  mov     [rdi+0D0h], rax
0x140061247  lea     rax, FatFsdFileSystemControl
0x14006124e  mov     [rdi+0D8h], rax
0x140061255  lea     rax, FatFsdLockControl
0x14006125c  mov     [rdi+0F8h], rax
0x140061263  lea     rax, FatFsdDeviceControl
0x14006126a  mov     [rdi+0E0h], rax
0x140061271  lea     rax, FatFsdShutdown
0x140061278  mov     [rdi+0F0h], rax
0x14006127f  lea     rax, FatFsdPnp
0x140061286  mov     [rdi+148h], rax
0x14006128d  call    memset
0x140061292  lea     rax, FatFastIoCheckIfPossible
0x140061299  mov     cs:FatFastIoDispatch, ebx
0x14006129f  mov     cs:qword_140017F08, rax
0x1400612a6  lea     rcx, [rbp+57h+Callbacks]; void *
0x1400612aa  mov     rax, cs:__imp_FsRtlCopyRead
0x1400612b1  mov     r8, r13; Size
0x1400612b4  mov     cs:qword_140017F10, rax
0x1400612bb  xor     edx, edx; Val
0x1400612bd  mov     rax, cs:__imp_FsRtlCopyWrite
0x1400612c4  mov     cs:qword_140017F18, rax
0x1400612cb  lea     rax, FatFastQueryBasicInfo
0x1400612d2  mov     cs:qword_140017F20, rax
0x1400612d9  lea     rax, FatFastQueryStdInfo
0x1400612e0  mov     cs:qword_140017F28, rax
0x1400612e7  lea     rax, FatFastLock
0x1400612ee  mov     cs:qword_140017F30, rax
0x1400612f5  lea     rax, FatFastUnlockSingle
0x1400612fc  mov     cs:qword_140017F38, rax
0x140061303  lea     rax, FatFastUnlockAll
0x14006130a  mov     cs:qword_140017F40, rax
0x140061311  lea     rax, FatFastUnlockAllByKey
0x140061318  mov     cs:qword_140017F48, rax
0x14006131f  lea     rax, FatFastQueryNetworkOpenInfo
0x140061326  mov     cs:qword_140017F70, rax
0x14006132d  lea     rax, FatAcquireForCcFlush
0x140061334  mov     cs:qword_140017FD0, rax
0x14006133b  lea     rax, FatReleaseForCcFlush
0x140061342  mov     cs:qword_140017FD8, rax
0x140061349  mov     rax, cs:__imp_FsRtlMdlReadDev
0x140061350  mov     cs:qword_140017F80, rax
0x140061357  mov     rax, cs:__imp_FsRtlMdlReadCompleteDev
0x14006135e  mov     cs:qword_140017F88, rax
0x140061365  mov     rax, cs:__imp_FsRtlPrepareMdlWriteDev
0x14006136c  mov     cs:qword_140017F90, rax
0x140061373  mov     rax, cs:__imp_FsRtlMdlWriteCompleteDev
0x14006137a  mov     cs:qword_140017F98, rax
0x140061381  call    memset
0x140061386  lea     rax, FatFilterCallbackAcquireForCreateSection
0x14006138d  mov     [rbp+57h+Callbacks.SizeOfFsFilterCallbacks], r13d
0x140061391  lea     rdx, [rbp+57h+Callbacks]; Callbacks
0x140061395  mov     [rbp+57h+Callbacks.PreAcquireForSectionSynchronization], rax
0x140061399  mov     rcx, rdi; FilterDriverObject
0x14006139c  call    cs:__imp_FsRtlRegisterFileSystemFilterCallbacks
0x1400613a3  nop     dword ptr [rax+rax+00h]
0x1400613a8  mov     ebx, eax
0x1400613aa  test    eax, eax
0x1400613ac  js      loc_1400614EB
0x1400613b2  xor     edx, edx; Val
0x1400613b4  lea     rcx, FatData; void *
0x1400613bb  mov     r8d, 200h; Size
0x1400613c1  call    memset
0x1400613c6  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x1400613cd  lea     rax, qword_140017CB0
0x1400613d4  mov     cs:qword_140017CB8, rax
0x1400613db  mov     cs:qword_140017CB0, rax
0x1400613e2  mov     rax, cs:FatCdromFileSystemDeviceObject
0x1400613e9  mov     cs:qword_140017CD0, rax
0x1400613f0  lea     rax, qword_140017D58
0x1400613f7  mov     cs:qword_140017D60, rax
0x1400613fe  mov     cs:qword_140017D58, rax
0x140061405  lea     rax, qword_140017D70
0x14006140c  mov     cs:qword_140017D78, rax
0x140061413  mov     cs:qword_140017D70, rax
0x14006141a  mov     cs:FatData, 2000500h
0x140061424  mov     cs:DriverObject, rdi
0x14006142b  mov     cs:qword_140017CC8, rcx
0x140061432  call    cs:__imp_IoAllocateWorkItem
0x140061439  nop     dword ptr [rax+rax+00h]
0x14006143e  mov     cs:IoWorkItem, rax
0x140061445  test    rax, rax
0x140061448  jz      loc_1400614E6
0x14006144e  mov     r15d, 1000h
0x140061454  mov     r8d, 5A746146h; Tag
0x14006145a  mov     edx, r15d; NumberOfBytes
0x14006145d  mov     ecx, 600h; PoolType
0x140061462  call    cs:__imp_ExAllocatePoolWithTag
0x140061469  nop     dword ptr [rax+rax+00h]
0x14006146e  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140061475  mov     rbx, rax
0x140061478  jnz     loc_14006150A
0x14006147e  test    rax, rax
0x140061481  jz      loc_14006150A
0x140061487  mov     r8d, r15d; Size
0x14006148a  xor     edx, edx; Val
0x14006148c  mov     rcx, rax; void *
0x14006148f  call    memset
0x140061494  mov     cs:P, rbx
0x14006149b  xor     r8d, r8d
0x14006149e  lea     r9, qword_140017E98
0x1400614a5  xor     ecx, ecx
0x1400614a7  lea     r12d, [r8+4]
0x1400614ab  mov     dl, r12b
0x1400614ae  call    cs:__imp_KeAllocateCalloutStackEx
0x1400614b5  nop     dword ptr [rax+rax+00h]
0x1400614ba  test    eax, eax
0x1400614bc  jns     short loc_14006152B
0x1400614be  mov     rcx, cs:IoWorkItem; IoWorkItem
0x1400614c5  call    cs:__imp_IoFreeWorkItem
0x1400614cc  nop     dword ptr [rax+rax+00h]
0x1400614d1  mov     rcx, cs:P; P
0x1400614d8  xor     edx, edx; Tag
0x1400614da  call    cs:__imp_ExFreePoolWithTag
0x1400614e1  nop     dword ptr [rax+rax+00h]
0x1400614e6  mov     ebx, 0C000009Ah
0x1400614eb  mov     rcx, cs:FatDiskFileSystemDeviceObject; DeviceObject
0x1400614f2  call    cs:__imp_IoDeleteDevice
0x1400614f9  nop     dword ptr [rax+rax+00h]
0x1400614fe  mov     rcx, cs:FatCdromFileSystemDeviceObject
0x140061505  jmp     loc_14006116C
0x14006150a  mov     cs:P, rbx
0x140061511  test    rbx, rbx
0x140061514  jnz     short loc_14006149B
0x140061516  mov     rcx, cs:IoWorkItem; IoWorkItem
0x14006151d  call    cs:__imp_IoFreeWorkItem
0x140061524  nop     dword ptr [rax+rax+00h]
0x140061529  jmp     short loc_1400614E6
0x14006152b  mov     r15d, 1
0x140061531  lea     rcx, Event; Event
0x140061538  mov     r8b, r15b; State
0x14006153b  xor     edx, edx; Type
0x14006153d  call    cs:__imp_KeInitializeEvent
0x140061544  nop     dword ptr [rax+rax+00h]
0x140061549  lea     rcx, SpinLock; SpinLock
0x140061550  call    cs:__imp_KeInitializeSpinLock
0x140061557  nop     dword ptr [rax+rax+00h]
0x14006155c  call    cs:__imp_MmQuerySystemSize
0x140061563  nop     dword ptr [rax+rax+00h]
0x140061568  lea     ebx, [r15+0Fh]
0x14006156c  test    eax, eax
0x14006156e  jz      short loc_140061590
0x140061570  cmp     eax, r15d
0x140061573  jz      short loc_140061584
0x140061575  movzx   esi, bx
0x140061578  mov     cs:FatMaxDelayedCloseCount, 100h
0x140061582  jmp     short loc_14006159A
0x140061584  mov     cs:FatMaxDelayedCloseCount, 40h ; '@'
0x14006158e  jmp     short loc_14006159A
0x140061590  movzx   esi, r12w
0x140061594  mov     cs:FatMaxDelayedCloseCount, ebx
0x14006159a  lea     rcx, FatNoOpAcquire
0x1400615a1  lea     rax, FatAcquireFcbForLazyWrite
0x1400615a8  mov     cs:qword_140017DB0, rcx
0x1400615af  mov     cs:qword_140017D90, rax
0x1400615b6  lea     rax, FatReleaseFcbFromLazyWrite
0x1400615bd  mov     cs:qword_140017D98, rax
0x1400615c4  lea     rax, FatAcquireFcbForReadAhead
0x1400615cb  mov     cs:qword_140017DA0, rax
0x1400615d2  lea     rax, FatReleaseFcbFromReadAhead
0x1400615d9  mov     cs:qword_140017DA8, rax
0x1400615e0  lea     rax, FatNoOpRelease
0x1400615e7  mov     cs:qword_140017DB8, rax
0x1400615ee  mov     cs:qword_140017DC8, rax
0x1400615f5  mov     cs:qword_140017DC0, rcx
0x1400615fc  call    cs:__imp_IoGetCurrentProcess
0x140061603  nop     dword ptr [rax+rax+00h]
0x140061608  xor     ecx, ecx; ActiveProcessors
0x14006160a  mov     cs:qword_140017D40, rax
0x140061611  call    cs:__imp_KeQueryActiveProcessorCount
0x140061618  nop     dword ptr [rax+rax+00h]
0x14006161d  or      cs:byte_140017D4D, 2
0x140061624  lea     rdx, [rbp+57h+arg_10]
0x140061628  mov     cs:dword_140017D48, eax
0x14006162e  lea     rcx, [rbp+57h+ValueName]; ValueName
0x140061632  lea     rax, aFatenableefs; "FatEnableEfs"
0x140061639  mov     dword ptr [rbp+57h+ValueName.Length], 1A0018h
0x140061640  mov     [rbp+57h+ValueName.Buffer], rax
0x140061644  call    FatGetCompatibilityModeValue
0x140061649  test    eax, eax
0x14006164b  js      short loc_140061663
0x14006164d  test    byte ptr [rbp+57h+arg_10], r15b
0x140061651  jz      short loc_14006165C
0x140061653  or      cs:byte_140017D4D, 2
0x14006165a  jmp     short loc_140061663
0x14006165c  and     cs:byte_140017D4D, 0FDh
0x140061663  and     cs:byte_140017D4C, 7Fh
0x14006166a  lea     rax, aFat12disablefl; "Fat12DisableFlushOnCleanup"
0x140061671  lea     rdx, [rbp+57h+arg_10]
0x140061675  mov     [rbp+57h+ValueName.Buffer], rax
0x140061679  lea     rcx, [rbp+57h+ValueName]; ValueName
0x14006167d  mov     dword ptr [rbp+57h+ValueName.Length], 360034h
0x140061684  call    FatGetCompatibilityModeValue
0x140061689  test    eax, eax
0x14006168b  js      short loc_1400616A3
0x14006168d  test    byte ptr [rbp+57h+arg_10], r15b
0x140061691  jz      short loc_14006169C
0x140061693  or      cs:byte_140017D4C, 80h
0x14006169a  jmp     short loc_1400616A3
0x14006169c  and     cs:byte_140017D4C, 7Fh
0x1400616a3  lea     rax, aWin31filesyste; "Win31FileSystem"
0x1400616aa  mov     dword ptr [rbp+57h+ValueName.Length], 20001Eh
0x1400616b1  lea     rdx, [rbp+57h+arg_10]
0x1400616b5  mov     [rbp+57h+ValueName.Buffer], rax
0x1400616b9  lea     rcx, [rbp+57h+ValueName]; ValueName
0x1400616bd  call    FatGetCompatibilityModeValue
0x1400616c2  test    eax, eax
0x1400616c4  js      short loc_1400616D5
0x1400616c6  test    byte ptr [rbp+57h+arg_10], r15b
0x1400616ca  jz      short loc_1400616D5
0x1400616cc  and     cs:byte_140017D4C, 0FEh
  ... truncated ...
```
