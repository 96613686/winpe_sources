# DriverEntry

- ea: `0x140010f18`
- end: `0x1400118f6`
- name: `DriverEntry`
- size: `2526`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `29`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140021010`

## callees

- `0x140002798`
- `0x1400027d0`
- `0x140002810`
- `0x140002828`
- `0x140002870`
- `0x140002a14`
- `0x140002e74`
- `0x140003350`
- `0x1400038a4`
- `0x1400051f0`
- `0x1400059c0`
- `0x14000f104`
- `0x14000f188`
- `0x14000fcf4`
- `0x140010774`
- `0x140010f18`
- `0x1400118fc`
- `0x140012194`
- `0x140012510`
- `0x140014de8`
- `0x1400158a4`
- `0x1400162d0`
- `0x14001642c`
- `0x140016f88`
- `0x1400171e8`
- `0x14001f2c0`
- `0x140021078`
- `0x1400210b4`
- `0x1400210f4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140010f59`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010f6b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011387`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400113bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001141b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011457`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010f59`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010f6b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011387`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400113bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001141b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011457`
- `ntoskrnl!ExAllocatePool2` at `0x1400110d0`
- `ntoskrnl!ExAllocatePool2` at `0x140011667`
- `ntoskrnl!ExAllocatePool2` at `0x1400110d0`
- `ntoskrnl!ExAllocatePool2` at `0x140011667`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011140`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011140`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112b1`
- `ntoskrnl!KeInitializeEvent` at `0x140011704`
- `ntoskrnl!KeInitializeEvent` at `0x140011704`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140011577`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14001159f`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140011577`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x14001159f`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400117d4`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140011837`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400117d4`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140011837`
- `ntoskrnl!KeCancelTimer` at `0x1400111f3`
- `ntoskrnl!KeCancelTimer` at `0x1400111f3`
- `ntoskrnl!IoFreeWorkItem` at `0x140011206`
- `ntoskrnl!IoFreeWorkItem` at `0x140011206`
- `ntoskrnl!ZwClose` at `0x14001118c`
- `ntoskrnl!ZwClose` at `0x1400111e0`
- `ntoskrnl!ZwClose` at `0x140011252`
- `ntoskrnl!ZwClose` at `0x140011290`
- `ntoskrnl!ZwClose` at `0x14001118c`
- `ntoskrnl!ZwClose` at `0x1400111e0`
- `ntoskrnl!ZwClose` at `0x140011252`
- `ntoskrnl!ZwClose` at `0x140011290`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140011117`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140011117`
- `ntoskrnl!IoDeleteDevice` at `0x1400112c9`
- `ntoskrnl!IoDeleteDevice` at `0x1400112c9`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400112df`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001142b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400112df`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001142b`
- `ntoskrnl!IoRegisterFileSystem` at `0x1400118c7`
- `ntoskrnl!IoRegisterFileSystem` at `0x1400118c7`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14001163f`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14001163f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140011325`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140011325`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140011306`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140011306`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400116c9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400116c9`
- `ntoskrnl!IoCreateDevice` at `0x1400113ef`
- `ntoskrnl!IoCreateDevice` at `0x1400113ef`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001143f`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001143f`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400111b0`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400111b0`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140011168`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001122e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001126c`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140011168`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001122e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001126c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140011488`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400114f4`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140011488`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400114f4`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400115d7`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400115d7`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140011497`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140011503`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140011497`
- `ntoskrnl!RtlRunOnceInitialize` at `0x140011503`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400114c9`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400114c9`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v4; // esi
  int v5; // r12d
  int v6; // r15d
  int v7; // r14d
  int v8; // r13d
  int v9; // eax
  __int64 v10; // rdx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 Length; // rdx
  int v15; // edi
  unsigned int v16; // eax
  size_t v17; // r15
  wchar_t *Pool2; // r14
  int v19; // ebx
  int inited; // eax
  int v22; // eax
  int v23; // eax
  int v24; // edi
  _BYTE *v25; // rdi
  char IrpStackSize; // al
  struct _DEVICE_OBJECT *v27; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING DeviceName; // [rsp+68h] [rbp-18h] BYREF
  int v31; // [rsp+D0h] [rbp+50h]
  int v32; // [rsp+D8h] [rbp+58h]

  DeviceObject = 0;
  DeviceName = 0;
  DestinationString = 0;
  wil_InitializeFeatureStaging();
  RtlInitUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Dpc.DeferredRoutine, 0);
  RtlInitUnicodeString(&DestinationString, 0);
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  v4 = 259;
  MupDeviceObject = 0;
  v31 = 259;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_MupLog;
  v5 = 259;
  v32 = 259;
  WPP_MAIN_CB.NextDevice = (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension;
  v6 = 259;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  *(_QWORD *)&WPP_MAIN_CB.DeviceType = WPP_ThisDir_CTLGUID_RFSMon;
  v7 = 259;
  v8 = 259;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_28988ea4fccc34e34a882626d4fa5735_Traceguids);
  }
  v9 = McGenEventRegister_EtwRegister();
  v13 = (unsigned int)v9;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_28988ea4fccc34e34a882626d4fa5735_Traceguids,
        (unsigned int)v9);
    }
  }
  MupRegisterTelemetryProvider(v11, v10, v12, v13);
  Length = RegistryPath->Length;
  if ( (Length & 1) != 0 || (unsigned int)Length < 2 )
    goto LABEL_9;
  if ( RegistryPath->Buffer[(Length >> 1) - 1] == 92 )
  {
    LOWORD(Length) = Length - 2;
    RegistryPath->Length = Length;
  }
  v16 = (unsigned __int16)Length + 24;
  if ( v16 > 0xFFFF )
  {
LABEL_9:
    v15 = -1073741811;
LABEL_17:
    v19 = 0;
    if ( MupiIrpContextLookasideLists )
    {
      if ( MupiIrpContextLookasideListsCeLength )
      {
        do
          ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MupiIrpContextLookasideLists + v19++);
        while ( v19 < (unsigned __int16)MupiIrpContextLookasideListsCeLength );
        v6 = v31;
      }
      ExFreePoolWithTag(MupiIrpContextLookasideLists, 0x2070754Du);
      MupiIrpContextLookasideLists = 0;
      MupiIrpContextLookasideListsCeLength = 0;
    }
    if ( !v7 )
    {
      ExWaitForRundownProtectionRelease(&RunRef);
      RfsTimerCleanup(qword_14000A288);
      if ( Handle )
        ZwClose(Handle);
      MupiFreeUncHardeningConfigurationEntryList(&qword_14000A220);
    }
    if ( !v6 )
      ExDeleteResourceLite(&stru_14000A5A0);
    if ( !v8 )
      MupTerminateContainerModule();
    if ( !v5 )
    {
      if ( MupiMupServicesKeyHandleValid )
      {
        MupiMupServicesKeyHandleValid = 0;
        ZwClose(WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink);
      }
      KeCancelTimer(&MupiPrefixGarbageCollectionTimer);
      IoFreeWorkItem(pMupiPrefixGarbageCollectionWorkItem);
      pMupiPrefixGarbageCollectionWorkItem = 0;
    }
    if ( !v4 )
      MupDeInitUncProviderModule();
    if ( !v32 )
    {
      ExWaitForRundownProtectionRelease(&stru_14000A358);
      RfsTimerCleanup(qword_14000A3A0);
      if ( qword_14000A368 )
      {
        ZwClose(qword_14000A368);
        qword_14000A368 = 0;
      }
      ExWaitForRundownProtectionRelease(&stru_14000A468);
      RfsTimerCleanup(qword_14000A4B0);
      if ( qword_14000A478 )
      {
        ZwClose(qword_14000A478);
        qword_14000A478 = 0;
      }
    }
    if ( WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
      ExFreePoolWithTag(WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0);
    if ( MupDeviceObject )
      IoDeleteDevice((PDEVICE_OBJECT)MupDeviceObject);
    if ( DestinationString.Buffer )
      IoDeleteSymbolicLink(&DestinationString);
    McGenEventUnregister_EtwUnregister();
    MupUnregisterTelemetryProvider();
    WppCleanupKm();
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
    return v15;
  }
  v17 = v16;
  Pool2 = (wchar_t *)ExAllocatePool2(66, v16, 544240973);
  if ( !Pool2 )
  {
    v15 = -1073741670;
LABEL_16:
    v7 = 259;
    v6 = 259;
    goto LABEL_17;
  }
  RtlStringCbPrintfW(Pool2, v17, L"%wZ%s", RegistryPath, L"\\Parameters");
  RtlInitUnicodeString((PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, Pool2);
  WPP_MAIN_CB.Dpc.DeferredContext = WPP_MAIN_CB.Queue.Wcb.CurrentIrp;
  WORD1(WPP_MAIN_CB.Dpc.DeferredRoutine) = RegistryPath->Length;
  LOWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) = WORD1(WPP_MAIN_CB.Dpc.DeferredRoutine);
  RtlInitUnicodeString(&DeviceName, L"\\Device\\Mup");
  v7 = 0;
  v15 = IoCreateDevice(DriverObject, 0, &DeviceName, 0x14u, 0x20010u, 0, &DeviceObject);
  if ( v15 < 0 )
    goto LABEL_16;
  MupDeviceObject = DeviceObject;
  RtlInitUnicodeString(&DestinationString, L"\\??\\UNC");
  IoDeleteSymbolicLink(&DestinationString);
  v15 = IoCreateSymbolicLink(&DestinationString, &DeviceName);
  if ( v15 < 0 )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    goto LABEL_16;
  }
  memset(&Parameter, 0, 0x110u);
  ExInitializeRundownProtection(&stru_14000A358);
  RtlRunOnceInitialize(&Parameter);
  RfsTimerInitialize(qword_14000A3A0);
  RtlRunOnceExecuteOnce(&Parameter, MupAttempttoLoadRegistryParametersKeyRunOnce, &Parameter, 0);
  v32 = 0;
  memset(&MupiPoliciesKeyRegistryWatcher, 0, 0x110u);
  ExInitializeRundownProtection(&stru_14000A468);
  RtlRunOnceInitialize(&MupiPoliciesKeyRegistryWatcher);
  RfsTimerInitialize(qword_14000A4B0);
  MupiTryStartPoliciesKeyRegistryWatcher();
  inited = MupInitUncProviderModule();
  v4 = inited;
  if ( inited )
  {
    v15 = inited;
    v7 = 259;
    v6 = 259;
    goto LABEL_17;
  }
  v22 = MupInitPrefixCache();
  v5 = v22;
  if ( v22 )
  {
    v15 = v22;
    v7 = 259;
    v6 = 259;
    goto LABEL_17;
  }
  MupQueryContextTable = 5796102;
  dword_14000AB04 = 1;
  KeInitializeGuardedMutex(&Mutex);
  qword_14000AB10 = (__int64)&qword_14000AB08;
  qword_14000AB08 = (__int64)&qword_14000AB08;
  KeInitializeGuardedMutex(&MupiMupDeviceOpenCountMutex);
  MupiSurrogateList = 9466124;
  qword_14000A590 = (__int64)&qword_14000A588;
  qword_14000A588 = (__int64)&qword_14000A588;
  dword_14000A584 = 1;
  ExInitializeResourceLite(&stru_14000A5A0);
  dword_14000A608 = 0;
  v6 = 0;
  dword_14000A598 = 0;
  v31 = 0;
  v15 = MupInitIrpContextList();
  if ( v15 || (v15 = MupInitReserveIrpContext()) != 0 || (v15 = MupRegisterFileSystemFilterCallbacks(DriverObject)) != 0 )
  {
    v7 = 259;
    goto LABEL_17;
  }
  MupInitializeUncHardeningModule();
  v23 = MupInitializeContainerModule(DriverObject);
  v8 = v23;
  if ( v23 )
  {
    v15 = v23;
    goto LABEL_17;
  }
  MupiIrpContextLookasideListsCeLength = KeQueryHighestNodeNumber() + 1;
  MupiIrpContextLookasideLists = (PVOID)ExAllocatePool2(
                                          74,
                                          (unsigned __int64)(unsigned __int16)MupiIrpContextLookasideListsCeLength << 7,
                                          544240973);
  if ( !MupiIrpContextLookasideLists )
  {
    v15 = -1073741670;
    goto LABEL_17;
  }
  v24 = 0;
  if ( MupiIrpContextLookasideListsCeLength )
  {
    do
      ExInitializeNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)MupiIrpContextLookasideLists + v24++,
        0,
        0,
        0x200u,
        0x118u,
        0x6349754Du,
        0);
    while ( v24 < (unsigned __int16)MupiIrpContextLookasideListsCeLength );
  }
  *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 1;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = 0;
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.DeviceQueue.Lock, SynchronizationEvent, 0);
  g_MupAdvancedFcbHeader.Flags |= 0x40u;
  g_MupAdvancedFcbHeader.Flags2 |= 2u;
  *((_BYTE *)&g_MupAdvancedFcbHeader.0 + 7) = *((_BYTE *)&g_MupAdvancedFcbHeader.0 + 7) & 0xF | 0x50;
  dword_14000A868 = 0;
  g_MupAdvancedFcbHeader.FilterContexts.Blink = &g_MupAdvancedFcbHeader.FilterContexts;
  g_MupAdvancedFcbHeader.FilterContexts.Flink = &g_MupAdvancedFcbHeader.FilterContexts;
  g_MupAdvancedFcbHeader.FastMutex = (PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue;
  *(_OWORD *)&g_MupAdvancedFcbHeader.PushLock = 0;
  qword_14000A870 = 0;
  xmmword_14000A858 = 0;
  if ( MupiOrderKeyHandleValid )
  {
    qword_14000A650 = (__int64)MupiOrderRegKeyChangeHandler;
    qword_14000A658 = 0;
    *(_QWORD *)MupiProviderOrderWork = 0;
    ZwNotifyChangeKey(
      MupiOrderKeyHandle,
      0,
      MupiProviderOrderWork,
      (PVOID)1,
      &MupiProviderOrderIoStatus,
      4u,
      0,
      0,
      0,
      1u);
  }
  if ( MupiNetworkProviderOrderKeyHandle )
  {
    qword_14000A630 = (__int64)MupiProviderOrderRegKeyChangeHandler;
    qword_14000A638 = 0;
    *(_QWORD *)MupiNetworkProviderOrderWork = 0;
    ZwNotifyChangeKey(
      MupiNetworkProviderOrderKeyHandle,
      0,
      MupiNetworkProviderOrderWork,
      (PVOID)1,
      &MupiNetworkProviderOrderIoStatus,
      4u,
      0,
      0,
      0,
      1u);
  }
  MupRegisterPrefixCacheKeyChangeNotification();
  memset64(DriverObject->MajorFunction, (unsigned __int64)MupFsdIrpPassThrough, 0x1Cu);
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&MupCreate;
  DriverObject->MajorFunction[1] = (PDRIVER_DISPATCH)&MupCreate;
  DriverObject->MajorFunction[19] = (PDRIVER_DISPATCH)&MupCreate;
  DriverObject->MajorFunction[13] = (PDRIVER_DISPATCH)&MupFsControl;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)MupCleanup;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)MupClose;
  DriverObject->MajorFunction[6] = (PDRIVER_DISPATCH)MupSetInformationFile;
  MupInitFastIo(DriverObject);
  v25 = MupDeviceObject;
  IrpStackSize = MupiGetIrpStackSize();
  v27 = (struct _DEVICE_OBJECT *)MupDeviceObject;
  v25[76] = IrpStackSize;
  IoRegisterFileSystem(v27);
  MupiInitSuccessful = 1;
  *((_DWORD *)MupDeviceObject + 12) = *((_DWORD *)MupDeviceObject + 12) & 0xFFFBFF7F | 0x40000;
  return 0;
}

```

## disassembly

```asm
0x140010f18  mov     [rsp-38h+arg_0], rbx
0x140010f1d  push    rbp
0x140010f1e  push    rsi
0x140010f1f  push    rdi
0x140010f20  push    r12
0x140010f22  push    r13
0x140010f24  push    r14
0x140010f26  push    r15
0x140010f28  mov     rbp, rsp
0x140010f2b  sub     rsp, 80h
0x140010f32  xorps   xmm0, xmm0
0x140010f35  mov     [rbp+var_30], 0
0x140010f3d  movups  xmmword ptr [rbp+DeviceName.Length], xmm0
0x140010f41  mov     rdi, rdx
0x140010f44  mov     rbx, rcx
0x140010f47  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140010f4b  call    wil_InitializeFeatureStaging
0x140010f50  xor     edx, edx; SourceString
0x140010f52  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; DestinationString
0x140010f59  call    cs:__imp_RtlInitUnicodeString
0x140010f60  nop     dword ptr [rax+rax+00h]
0x140010f65  xor     edx, edx; SourceString
0x140010f67  lea     rcx, [rbp+DestinationString]; DestinationString
0x140010f6b  call    cs:__imp_RtlInitUnicodeString
0x140010f72  nop     dword ptr [rax+rax+00h]
0x140010f77  xor     ecx, ecx
0x140010f79  mov     cs:WPP_MAIN_CB.Timer, 1
0x140010f84  mov     esi, 103h
0x140010f89  mov     cs:MupDeviceObject, rcx
0x140010f90  lea     rax, WPP_ThisDir_CTLGUID_MupLog
0x140010f97  mov     [rbp+arg_10], esi
0x140010f9a  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x140010fa1  mov     r12d, esi
0x140010fa4  lea     rax, WPP_MAIN_CB.DeviceExtension
0x140010fab  mov     [rbp+arg_18], esi
0x140010fae  mov     cs:WPP_MAIN_CB.NextDevice, rax
0x140010fb5  mov     r15d, esi
0x140010fb8  lea     rax, WPP_ThisDir_CTLGUID_RFSMon
0x140010fbf  mov     qword ptr cs:WPP_MAIN_CB.Type, rcx
0x140010fc6  mov     qword ptr cs:WPP_MAIN_CB.DeviceType, rax
0x140010fcd  mov     r14d, esi
0x140010fd0  mov     r13d, esi
0x140010fd3  mov     cs:WPP_MAIN_CB.CurrentIrp, rcx
0x140010fda  mov     cs:WPP_MAIN_CB.DeviceExtension, rcx
0x140010fe1  mov     qword ptr cs:WPP_MAIN_CB.Queue, rcx
0x140010fe8  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rcx
0x140010fef  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, 1
0x140010ffa  call    WppLoadTracingSupport
0x140010fff  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14001100a  call    WppInitKm
0x14001100f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011016  lea     rax, WPP_GLOBAL_Control
0x14001101d  cmp     rcx, rax
0x140011020  jz      short loc_140011040
0x140011022  test    dword ptr [rcx+2Ch], 4000000h
0x140011029  jz      short loc_140011040
0x14001102b  mov     rcx, [rcx+18h]
0x14001102f  lea     r8, WPP_28988ea4fccc34e34a882626d4fa5735_Traceguids
0x140011036  mov     edx, 0Ah
0x14001103b  call    WPP_SF_
0x140011040  call    McGenEventRegister_EtwRegister
0x140011045  mov     r9d, eax
0x140011048  test    eax, eax
0x14001104a  jns     short loc_14001107D
0x14001104c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011053  lea     rax, WPP_GLOBAL_Control
0x14001105a  cmp     rcx, rax
0x14001105d  jz      short loc_14001107D
0x14001105f  test    dword ptr [rcx+2Ch], 2000000h
0x140011066  jz      short loc_14001107D
0x140011068  mov     rcx, [rcx+18h]
0x14001106c  lea     r8, WPP_28988ea4fccc34e34a882626d4fa5735_Traceguids
0x140011073  mov     edx, 0Bh
0x140011078  call    WPP_SF_d
0x14001107d  call    MupRegisterTelemetryProvider
0x140011082  movzx   edx, word ptr [rdi]
0x140011085  mov     ecx, 1
0x14001108a  test    cl, dl
0x14001108c  jz      short loc_140011095
0x14001108e  mov     edi, 0C000000Dh
0x140011093  jmp     short loc_1400110F3
0x140011095  cmp     edx, 2
0x140011098  jb      short loc_14001108E
0x14001109a  mov     rax, [rdi+8]
0x14001109e  mov     rcx, rdx
0x1400110a1  shr     rcx, 1
0x1400110a4  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400110aa  jnz     short loc_1400110B3
0x1400110ac  sub     dx, 2
0x1400110b0  mov     [rdi], dx
0x1400110b3  movzx   eax, dx
0x1400110b6  add     eax, 18h
0x1400110b9  cmp     eax, 0FFFFh
0x1400110be  ja      short loc_14001108E
0x1400110c0  mov     r8d, 2070754Dh
0x1400110c6  mov     edx, eax
0x1400110c8  mov     ecx, 42h ; 'B'
0x1400110cd  mov     r15d, eax
0x1400110d0  call    cs:__imp_ExAllocatePool2
0x1400110d7  nop     dword ptr [rax+rax+00h]
0x1400110dc  mov     r14, rax
0x1400110df  test    rax, rax
0x1400110e2  jnz     loc_14001135C
0x1400110e8  mov     edi, 0C000009Ah
0x1400110ed  mov     r14d, esi
0x1400110f0  mov     r15d, esi
0x1400110f3  xor     ebx, ebx
0x1400110f5  cmp     cs:MupiIrpContextLookasideLists, rbx
0x1400110fc  jz      short loc_14001115C
0x1400110fe  xor     eax, eax
0x140011100  cmp     ax, cs:MupiIrpContextLookasideListsCeLength
0x140011107  jnb     short loc_140011134
0x140011109  movsxd  rcx, ebx
0x14001110c  shl     rcx, 7
0x140011110  add     rcx, cs:MupiIrpContextLookasideLists; Lookaside
0x140011117  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001111e  nop     dword ptr [rax+rax+00h]
0x140011123  movzx   eax, cs:MupiIrpContextLookasideListsCeLength
0x14001112a  inc     ebx
0x14001112c  cmp     ebx, eax
0x14001112e  jl      short loc_140011109
0x140011130  mov     r15d, [rbp+arg_10]
0x140011134  mov     rcx, cs:MupiIrpContextLookasideLists; P
0x14001113b  mov     edx, 2070754Dh; Tag
0x140011140  call    cs:__imp_ExFreePoolWithTag
0x140011147  nop     dword ptr [rax+rax+00h]
0x14001114c  xor     ebx, ebx
0x14001114e  mov     cs:MupiIrpContextLookasideLists, rbx
0x140011155  mov     cs:MupiIrpContextLookasideListsCeLength, bx
0x14001115c  test    r14d, r14d
0x14001115f  jnz     short loc_1400111A4
0x140011161  lea     rcx, RunRef; RunRef
0x140011168  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14001116f  nop     dword ptr [rax+rax+00h]
0x140011174  lea     rcx, qword_14000A288
0x14001117b  call    RfsTimerCleanup
0x140011180  mov     rcx, cs:Handle; Handle
0x140011187  test    rcx, rcx
0x14001118a  jz      short loc_140011198
0x14001118c  call    cs:__imp_ZwClose
0x140011193  nop     dword ptr [rax+rax+00h]
0x140011198  lea     rcx, qword_14000A220
0x14001119f  call    MupiFreeUncHardeningConfigurationEntryList
0x1400111a4  test    r15d, r15d
0x1400111a7  jnz     short loc_1400111BC
0x1400111a9  lea     rcx, stru_14000A5A0; Resource
0x1400111b0  call    cs:__imp_ExDeleteResourceLite
0x1400111b7  nop     dword ptr [rax+rax+00h]
0x1400111bc  test    r13d, r13d
0x1400111bf  jnz     short loc_1400111C6
0x1400111c1  call    MupTerminateContainerModule
0x1400111c6  test    r12d, r12d
0x1400111c9  jnz     short loc_140011219
0x1400111cb  cmp     cs:MupiMupServicesKeyHandleValid, bl
0x1400111d1  jz      short loc_1400111EC
0x1400111d3  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; Handle
0x1400111da  mov     cs:MupiMupServicesKeyHandleValid, bl
0x1400111e0  call    cs:__imp_ZwClose
0x1400111e7  nop     dword ptr [rax+rax+00h]
0x1400111ec  lea     rcx, MupiPrefixGarbageCollectionTimer; PKTIMER
0x1400111f3  call    cs:__imp_KeCancelTimer
0x1400111fa  nop     dword ptr [rax+rax+00h]
0x1400111ff  mov     rcx, cs:pMupiPrefixGarbageCollectionWorkItem; IoWorkItem
0x140011206  call    cs:__imp_IoFreeWorkItem
0x14001120d  nop     dword ptr [rax+rax+00h]
0x140011212  mov     cs:pMupiPrefixGarbageCollectionWorkItem, rbx
0x140011219  test    esi, esi
0x14001121b  jnz     short loc_140011222
0x14001121d  call    MupDeInitUncProviderModule
0x140011222  cmp     [rbp+arg_18], ebx
0x140011225  jnz     short loc_1400112A3
0x140011227  lea     rcx, stru_14000A358; RunRef
0x14001122e  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140011235  nop     dword ptr [rax+rax+00h]
0x14001123a  lea     rcx, qword_14000A3A0
0x140011241  call    RfsTimerCleanup
0x140011246  mov     rcx, cs:qword_14000A368; Handle
0x14001124d  test    rcx, rcx
0x140011250  jz      short loc_140011265
0x140011252  call    cs:__imp_ZwClose
0x140011259  nop     dword ptr [rax+rax+00h]
0x14001125e  mov     cs:qword_14000A368, rbx
0x140011265  lea     rcx, stru_14000A468; RunRef
0x14001126c  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140011273  nop     dword ptr [rax+rax+00h]
0x140011278  lea     rcx, qword_14000A4B0
0x14001127f  call    RfsTimerCleanup
0x140011284  mov     rcx, cs:qword_14000A478; Handle
0x14001128b  test    rcx, rcx
0x14001128e  jz      short loc_1400112A3
0x140011290  call    cs:__imp_ZwClose
0x140011297  nop     dword ptr [rax+rax+00h]
0x14001129c  mov     cs:qword_14000A478, rbx
0x1400112a3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; P
0x1400112aa  test    rcx, rcx
0x1400112ad  jz      short loc_1400112BD
0x1400112af  xor     edx, edx; Tag
0x1400112b1  call    cs:__imp_ExFreePoolWithTag
0x1400112b8  nop     dword ptr [rax+rax+00h]
0x1400112bd  mov     rcx, cs:MupDeviceObject; DeviceObject
0x1400112c4  test    rcx, rcx
0x1400112c7  jz      short loc_1400112D5
0x1400112c9  call    cs:__imp_IoDeleteDevice
0x1400112d0  nop     dword ptr [rax+rax+00h]
0x1400112d5  cmp     [rbp+DestinationString.Buffer], rbx
0x1400112d9  jz      short loc_1400112EB
0x1400112db  lea     rcx, [rbp+DestinationString]; SymbolicLinkName
0x1400112df  call    cs:__imp_IoDeleteSymbolicLink
0x1400112e6  nop     dword ptr [rax+rax+00h]
0x1400112eb  call    McGenEventUnregister_EtwUnregister
0x1400112f0  call    MupUnregisterTelemetryProvider
0x1400112f5  call    WppCleanupKm
0x1400112fa  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140011301  test    rcx, rcx
0x140011304  jz      short loc_140011319
0x140011306  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14001130d  nop     dword ptr [rax+rax+00h]
0x140011312  mov     cs:g_wil_details_featureChangeNotification, rbx
0x140011319  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140011320  test    rcx, rcx
0x140011323  jz      short loc_140011338
0x140011325  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14001132c  nop     dword ptr [rax+rax+00h]
0x140011331  mov     cs:g_wil_details_featureUsageProvider, rbx
0x140011338  mov     cs:g_wil_details_isFeatureStagingInitialized, ebx
0x14001133e  mov     eax, edi
0x140011340  mov     rbx, [rsp+80h+arg_0]
0x140011348  add     rsp, 80h
0x14001134f  pop     r15
0x140011351  pop     r14
0x140011353  pop     r13
0x140011355  pop     r12
0x140011357  pop     rdi
0x140011358  pop     rsi
0x140011359  pop     rbp
0x14001135a  retn
0x14001135c  lea     rax, aParameters; "\\Parameters"
0x140011363  mov     r9, rdi
0x140011366  lea     r8, aWzS; "%wZ%s"
0x14001136d  mov     qword ptr [rsp+80h+DeviceCharacteristics], rax
0x140011372  mov     rdx, r15; cbDest
0x140011375  mov     rcx, r14; pszDest
0x140011378  call    RtlStringCbPrintfW
0x14001137d  mov     rdx, r14; SourceString
0x140011380  lea     rcx, WPP_MAIN_CB.Queue+30h; DestinationString
0x140011387  call    cs:__imp_RtlInitUnicodeString
0x14001138e  nop     dword ptr [rax+rax+00h]
0x140011393  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001139a  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x1400113a1  mov     cs:WPP_MAIN_CB.Dpc.DeferredContext, rax
0x1400113a8  lea     rcx, [rbp+DeviceName]; DestinationString
0x1400113ac  movzx   eax, word ptr [rdi]
0x1400113af  mov     word ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, ax
0x1400113b6  mov     word ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, ax
0x1400113bd  call    cs:__imp_RtlInitUnicodeString
0x1400113c4  nop     dword ptr [rax+rax+00h]
0x1400113c9  xor     r14d, r14d
0x1400113cc  lea     rax, [rbp+var_30]
0x1400113d0  mov     [rsp+80h+DeviceObject], rax; DeviceObject
0x1400113d5  lea     r8, [rbp+DeviceName]; DeviceName
0x1400113d9  mov     [rsp+80h+Exclusive], r14b; Exclusive
0x1400113de  xor     edx, edx; DeviceExtensionSize
0x1400113e0  mov     rcx, rbx; DriverObject
0x1400113e3  mov     [rsp+80h+DeviceCharacteristics], 20010h; DeviceCharacteristics
0x1400113eb  lea     r9d, [r14+14h]; DeviceType
0x1400113ef  call    cs:__imp_IoCreateDevice
0x1400113f6  nop     dword ptr [rax+rax+00h]
0x1400113fb  mov     edi, eax
0x1400113fd  test    eax, eax
0x1400113ff  js      loc_1400110ED
0x140011405  mov     rax, [rbp+var_30]
0x140011409  lea     rdx, aUnc; "\\??\\UNC"
0x140011410  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011414  mov     cs:MupDeviceObject, rax
0x14001141b  call    cs:__imp_RtlInitUnicodeString
0x140011422  nop     dword ptr [rax+rax+00h]
0x140011427  lea     rcx, [rbp+DestinationString]; SymbolicLinkName
0x14001142b  call    cs:__imp_IoDeleteSymbolicLink
0x140011432  nop     dword ptr [rax+rax+00h]
0x140011437  lea     rdx, [rbp+DeviceName]; DeviceName
0x14001143b  lea     rcx, [rbp+DestinationString]; SymbolicLinkName
0x14001143f  call    cs:__imp_IoCreateSymbolicLink
0x140011446  nop     dword ptr [rax+rax+00h]
0x14001144b  mov     edi, eax
0x14001144d  test    eax, eax
0x14001144f  jns     short loc_140011468
0x140011451  xor     edx, edx; SourceString
0x140011453  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011457  call    cs:__imp_RtlInitUnicodeString
0x14001145e  nop     dword ptr [rax+rax+00h]
0x140011463  jmp     loc_1400110ED
0x140011468  mov     esi, 110h
0x14001146d  lea     rdi, Parameter
0x140011474  mov     r8d, esi; Size
0x140011477  mov     rcx, rdi; void *
0x14001147a  xor     edx, edx; Val
0x14001147c  call    memset
0x140011481  lea     rcx, stru_14000A358; RunRef
0x140011488  call    cs:__imp_ExInitializeRundownProtection
0x14001148f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
