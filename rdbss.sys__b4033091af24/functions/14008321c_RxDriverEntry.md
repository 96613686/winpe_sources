# RxDriverEntry

- ea: `0x14008321c`
- end: `0x140083c26`
- name: `RxDriverEntry`
- size: `2570`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140083078`

## callees

- `0x140016e20`
- `0x14001c1b0`
- `0x14001c854`
- `0x14001c8cc`
- `0x140025c20`
- `0x140026080`
- `0x1400491d4`
- `0x1400494b4`
- `0x140049528`
- `0x140049734`
- `0x140049bbc`
- `0x140049c50`
- `0x14004a03c`
- `0x14004a974`
- `0x14004c7b8`
- `0x14004c998`
- `0x140050900`
- `0x140051af8`
- `0x140051f1c`
- `0x140052280`
- `0x1400830a4`
- `0x14008321c`
- `0x140083c2c`
- `0x140083e08`
- `0x140083fb4`
- `0x1400842b8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140083ac4`
- `ntoskrnl!ExAllocatePool2` at `0x140083ac4`
- `ntoskrnl!KeInitializeEvent` at `0x1400833e5`
- `ntoskrnl!KeInitializeEvent` at `0x140083544`
- `ntoskrnl!KeInitializeEvent` at `0x140083a9e`
- `ntoskrnl!KeInitializeEvent` at `0x140083b5b`
- `ntoskrnl!KeInitializeEvent` at `0x1400833e5`
- `ntoskrnl!KeInitializeEvent` at `0x140083544`
- `ntoskrnl!KeInitializeEvent` at `0x140083a9e`
- `ntoskrnl!KeInitializeEvent` at `0x140083b5b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008360b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083626`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008360b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083626`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140083637`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140083637`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400835dc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400835dc`
- `ntoskrnl!ZwClose` at `0x1400835ed`
- `ntoskrnl!ZwClose` at `0x1400835ed`
- `ntoskrnl!IoCreateDevice` at `0x1400836a1`
- `ntoskrnl!IoCreateDevice` at `0x1400836a1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008346e`
- `ntoskrnl!KeInitializeSpinLock` at `0x140083485`
- `ntoskrnl!KeInitializeSpinLock` at `0x140083b20`
- `ntoskrnl!KeInitializeSpinLock` at `0x140083baf`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008346e`
- `ntoskrnl!KeInitializeSpinLock` at `0x140083485`
- `ntoskrnl!KeInitializeSpinLock` at `0x140083b20`
- `ntoskrnl!KeInitializeSpinLock` at `0x140083baf`
- `ntoskrnl!InitializeSListHead` at `0x140083a85`
- `ntoskrnl!InitializeSListHead` at `0x140083bc2`
- `ntoskrnl!InitializeSListHead` at `0x140083a85`
- `ntoskrnl!InitializeSListHead` at `0x140083bc2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140083ae7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140083ae7`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140083278`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140083278`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400832ce`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400832ce`
- `ntoskrnl!PsIsDiskCountersEnabled` at `0x1400832f3`
- `ntoskrnl!PsIsDiskCountersEnabled` at `0x1400832f3`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140083305`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140083305`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140083336`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140083351`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140083336`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140083351`
- `ntoskrnl!IoGetCurrentProcess` at `0x140083568`
- `ntoskrnl!IoGetCurrentProcess` at `0x140083568`
- `ntoskrnl!PsCreateSystemThread` at `0x1400835a1`
- `ntoskrnl!PsCreateSystemThread` at `0x1400835a1`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140083650`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140083650`
- `ntoskrnl!EtwRegister` at `0x140083869`
- `ntoskrnl!EtwRegister` at `0x140083869`
- `ntoskrnl!KeAllocateCalloutStack` at `0x1400839a8`
- `ntoskrnl!KeAllocateCalloutStack` at `0x1400839bd`
- `ntoskrnl!KeAllocateCalloutStack` at `0x1400839a8`
- `ntoskrnl!KeAllocateCalloutStack` at `0x1400839bd`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400839e4`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400839e4`
- `ntoskrnl!KeInitializeMutex` at `0x140083b71`
- `ntoskrnl!KeInitializeMutex` at `0x140083b87`
- `ntoskrnl!KeInitializeMutex` at `0x140083b71`
- `ntoskrnl!KeInitializeMutex` at `0x140083b87`
- `ntoskrnl!ExInitializeResourceLite` at `0x140083bdd`
- `ntoskrnl!ExInitializeResourceLite` at `0x140083bdd`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1400838f1`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1400838f1`

## pseudocode

```c
NTSTATUS __stdcall RxDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  unsigned __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  USHORT HighestNodeNumber; // ax
  unsigned int v9; // ebx
  USHORT NodeMaximumProcessorCount; // ax
  USHORT v11; // cx
  __int64 v12; // rdi
  __int64 v13; // rbx
  signed int v14; // eax
  unsigned int v15; // edi
  NTSTATUS Instance; // ebx
  int v17; // edx
  int v18; // r8d
  int v19; // r9d
  PRDBSS_DEVICE_OBJECT v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // r8
  unsigned int v23; // eax
  __int64 v24; // r9
  ULONGLONG CalloutStack; // rax
  ULONG MaximumProcessorCount; // eax
  PRDBSS_DEVICE_OBJECT v27; // rcx
  __int64 i; // rbx
  struct _SLIST_ENTRY *Pool2; // rax
  __int64 v31; // rdi
  __int64 v32; // rbx
  union _SLIST_HEADER *v33; // rbx
  struct _RDBSS_DEVICE_OBJECT::$8E5F2250B80FEA01BE2192B09BB2E785 *p_PagingReadBytesRequested; // rax
  void *ThreadHandle; // [rsp+90h] [rbp-80h] BYREF
  _DWORD v36[6]; // [rsp+98h] [rbp-78h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-60h] BYREF
  UNICODE_STRING DeviceName; // [rsp+C0h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v39; // [rsp+D0h] [rbp-40h] BYREF

  DeviceName = 0;
  DestinationString = 0;
  ThreadHandle = 0;
  v4 = 2LL * KeQueryActiveProcessorCountEx(0xFFFFu);
  if ( v4 > 0xFFFFFFFF )
    LODWORD(v4) = 8;
  v5 = v4;
  if ( (unsigned int)v4 < 8 )
    v5 = 8;
  v6 = 0x7FFFFFFF;
  if ( v5 <= 0x7FFFFFFF )
  {
    v6 = v4;
    if ( (unsigned int)v4 < 8 )
      v6 = 8;
  }
  FspPerDeviceThreshold = v6;
  v7 = v6 >> 1;
  if ( v7 < 4 )
    v7 = 4;
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = v7;
  wil_InitializeFeatureStaging();
  RxTicksPerSecond = 0x989680 / KeQueryTimeIncrement();
  RxCheckFcbStructuresForAlignment();
  RxEnablePerProcessCounters = PsIsDiskCountersEnabled();
  HighestNodeNumber = KeQueryHighestNodeNumber();
  RxMaxNumaNodes = HighestNodeNumber + 1;
  RxMaxProcessorsPerNode = 0;
  v9 = 0;
  if ( HighestNodeNumber != 0xFFFF )
  {
    do
    {
      NodeMaximumProcessorCount = KeQueryNodeMaximumProcessorCount(v9);
      v11 = RxMaxProcessorsPerNode;
      if ( (unsigned __int16)RxMaxProcessorsPerNode <= NodeMaximumProcessorCount )
        v11 = KeQueryNodeMaximumProcessorCount(v9);
      RxMaxProcessorsPerNode = v11;
      ++v9;
    }
    while ( v9 < (unsigned __int16)RxMaxNumaNodes );
  }
  memset(&RxContextLookasideList.L.AllocateMisses, 0, 0x120u);
  RxContextLookasideList.L.AllocateMisses = 18934528;
  *(_QWORD *)&RxContextLookasideList.L.FreeMisses = DriverObject;
  Set = -1;
  memset(&RxDeviceFCB.spacer.Flags, 0, 0x2ECu);
  *(_DWORD *)&RxDeviceFCB.Header.NodeTypeCode = 49343523;
  RxDeviceFCBHeaderMutex = 1;
  qword_140038A28 = 0;
  dword_140038A30 = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  RxDeviceFCB.Header.Flags |= 0x40u;
  RxDeviceFCB.Header.Flags2 |= 2u;
  *((_BYTE *)&RxDeviceFCB.Header.0 + 7) = *((_BYTE *)&RxDeviceFCB.Header.0 + 7) & 0xF | 0x50;
  RxDeviceFCB.Header.FilterContexts.Blink = &RxDeviceFCB.Header.FilterContexts;
  RxDeviceFCB.Header.FilterContexts.Flink = &RxDeviceFCB.Header.FilterContexts;
  RxDeviceFCB.Header.FastMutex = (PFAST_MUTEX)&RxDeviceFCBHeaderMutex;
  *(_OWORD *)&RxDeviceFCB.spacer.PushLock = 0;
  *(_OWORD *)&RxDeviceFCB.NetRoot = 0;
  *((_DWORD *)&RxDeviceFCB.1 + 26) = 0;
  *((_QWORD *)&RxDeviceFCB.1 + 14) = 0;
  v12 = 0;
  v13 = 0;
  do
  {
    KeInitializeSpinLock((KSPIN_LOCK *)((char *)&SpinLock + v13 * 8));
    KeInitializeSpinLock((PKSPIN_LOCK)&qword_140035700[v13]);
    (&RxActiveContexts.Blink)[v13] = (LIST_ENTRY *)((char *)&RxActiveContexts + v13 * 8);
    (&RxActiveContexts.Flink)[v13] = (LIST_ENTRY *)((char *)&RxActiveContexts + v13 * 8);
    qword_1400356D0[v13 + 1] = (__int64)&qword_1400356D0[v13];
    qword_1400356D0[v13] = (__int64)&qword_1400356D0[v13];
    qword_1400356E0[v13 + 1] = (__int64)&qword_1400356E0[v13];
    qword_1400356E0[v13] = (__int64)&qword_1400356E0[v13];
    ++v12;
    v13 += 24;
  }
  while ( v12 != 64 );
  v14 = 0x40u / (unsigned __int16)RxMaxNumaNodes;
  if ( v14 < 1 )
    v14 = 1;
  RxActiveContextNodeBucketSize = v14;
  RxLinkedConnectionLock = 0;
  RxContextStartStopLock = 0;
  qword_140038AF8 = (__int64)&RxOrphanedFcbListHead;
  RxOrphanedFcbListHead = (__int64)&RxOrphanedFcbListHead;
  RxOrphanedFcbListLock = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.DeviceExtension, NotificationEvent, 0);
  v15 = 9;
  RxFileSystemDeviceObject = 0;
  Object = 0;
  qword_140043098 = (__int64)IoGetCurrentProcess();
  Instance = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, RxpIdleWorkerThread, 0);
  if ( Instance >= 0 )
  {
    ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
    ZwClose(ThreadHandle);
    v15 = 8;
    RtlInitUnicodeString(&DestinationString, L"\\??\\fsWrap");
    RtlInitUnicodeString(&DeviceName, L"\\Device\\FsWrap");
    IoDeleteSymbolicLink(&DestinationString);
    Instance = IoCreateSymbolicLink(&DestinationString, &DeviceName);
    if ( Instance >= 0 )
    {
      v15 = 7;
      Instance = IoCreateDevice(
                   DriverObject,
                   0x3D0u,
                   &DeviceName,
                   0x14u,
                   0x10u,
                   0,
                   (PDEVICE_OBJECT *)&RxFileSystemDeviceObject);
      if ( Instance >= 0 )
      {
        v15 = 6;
        if ( !RxEnablePerProcessCounters )
          goto LABEL_26;
        Instance = RdbssKernelInterfaceCreateInstance(&RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27]);
        if ( Instance >= 0 )
        {
          Instance = RdbssStatisticsDatabaseCreateInstance(
                       RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Flink,
                       v17,
                       v18,
                       v19,
                       (__int64)&RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[27].Blink);
          if ( Instance >= 0 )
          {
            v20 = RxFileSystemDeviceObject;
            LOBYTE(v20->RxNetNameTableInDeviceObject.HashBuckets[29].Blink) = RxSecurityDescriptorGetFromRegistry(&RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29]);
            if ( LOBYTE(RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29].Blink) )
              goto LABEL_26;
            *(_DWORD *)v39.Value = 0;
            *(_WORD *)&v39.Value[4] = 1280;
            v36[0] = 80;
            v36[1] = -1324354722;
            v36[2] = 78537857;
            v36[3] = 698502321;
            v36[4] = 558674196;
            v36[5] = 1451644582;
            Instance = RxSecurityDescriptorCreate(
                         v21,
                         &v39,
                         v22,
                         (__int64)v36,
                         &RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29].Flink);
            if ( Instance >= 0 )
            {
LABEL_26:
              *(_QWORD *)&WPP_MAIN_CB.Type = 0;
              WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_RdbssLog;
              WPP_MAIN_CB.NextDevice = 0;
              WPP_MAIN_CB.CurrentIrp = 0;
              WPP_MAIN_CB.Timer = (PIO_TIMER)1;
              WppLoadTracingSupport();
              WPP_MAIN_CB.CurrentIrp = 0;
              WppInitKm();
              v23 = McGenEventRegister_EtwRegister();
              if ( v23
                && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7b7fb28597d5336b708e27863935177e_Traceguids, v23);
              }
              v24 = 0;
              if ( !Microsoft_Windows_Networking_CorrelationHandle )
                v24 = (unsigned int)EtwRegister(
                                      &Microsoft_Windows_Networking_CorrelationId,
                                      Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
                                      0,
                                      &Microsoft_Windows_Networking_CorrelationHandle);
              if ( (_DWORD)v24 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7b7fb28597d5336b708e27863935177e_Traceguids, v24);
                }
              }
              else
              {
                Microsoft_Windows_Networking_ProviderId = (__int128)REMOTEFS_RDBSS;
              }
              v15 = 5;
              Instance = PoRegisterPowerSettingCallback(
                           &RxFileSystemDeviceObject->DeviceObject,
                           &GUID_RX_POWER_POLICY,
                           RxPowerPolicyCallback,
                           0,
                           (PVOID *)&RxFileSystemDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[26].Blink);
              if ( Instance >= 0 )
              {
                RxPowerContext = 0;
                byte_140038BD8 = 1;
                v15 = 4;
                RxGetRegistryParameters(RegistryPath);
                RxReadRegistryParameters(0);
                Instance = RxInitializeRegistryNotification();
                if ( Instance >= 0 )
                {
                  v15 = 3;
                  RxNameCacheGlobalConfig = 0;
                  qword_140038AD0 = (__int64)&qword_140038AC8;
                  qword_140038AC8 = (__int64)&qword_140038AC8;
                  dword_140038AD8 = 0;
                  Instance = RxInitializeRegistrationStructures();
                  if ( Instance >= 0 )
                  {
                    v15 = 2;
                    Instance = RxInitializeSiloMonitor(DriverObject);
                    if ( Instance >= 0 )
                    {
                      v15 = 1;
                      *(_QWORD *)&RxContextLookasideList.L.Depth = KeAllocateCalloutStack(0);
                      CalloutStack = KeAllocateCalloutStack(0);
                      RxContextLookasideList.L.ListHead.Region = CalloutStack;
                      if ( !*(_QWORD *)&RxContextLookasideList.L.Depth
                        || !CalloutStack
                        || (MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu),
                            (RxContextLookasideList.L.ListHead.Alignment = PplpCreateLookasideListEx(MaximumProcessorCount)) == 0) )
                      {
                        Instance = -1073741670;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( Instance )
  {
    v27 = RxFileSystemDeviceObject;
    if ( RxFileSystemDeviceObject )
      RxLogEventDirect(RxFileSystemDeviceObject, 0, 0x80000BC4, Instance, 0x24Bu);
    RxInitUnwind(v27, v15);
    wil_UninitializeFeatureStaging();
    return Instance;
  }
  else
  {
    RxInitializeTurboIoSupport();
    RxInitializeWorkQueues();
    InitializeSListHead(&MustSucceedRxContextSList);
    KeInitializeEvent(&MustSucceedRxContextEvent, SynchronizationEvent, 1u);
    for ( i = 0; i != 8; ++i )
    {
      Pool2 = (struct _SLIST_ENTRY *)ExAllocatePool2(66, 896, 1917417554);
      MustSucceedRxContexts[i] = (__int64)Pool2;
      if ( Pool2 )
        ExpInterlockedPushEntrySList(&MustSucceedRxContextSList, Pool2);
    }
    v31 = 0;
    v32 = 0;
    do
    {
      RxTransportIrps[v32 + 1] = (__int64)&RxTransportIrps[v32];
      RxTransportIrps[v32] = (__int64)&RxTransportIrps[v32];
      KeInitializeSpinLock((PKSPIN_LOCK)&qword_140033700[v32]);
      ++v31;
      v32 += 16;
    }
    while ( v31 != 64 );
    RxContextPerFileSerializationMutex.Count = 1;
    RxContextPerFileSerializationMutex.Owner = 0;
    RxContextPerFileSerializationMutex.Contention = 0;
    KeInitializeEvent(&RxContextPerFileSerializationMutex.Event, SynchronizationEvent, 0);
    KeInitializeMutex(&RxScavengerMutex, 1u);
    KeInitializeMutex(&RxSerializationMutex, 1u);
    v33 = (union _SLIST_HEADER *)RxFileSystemDeviceObject;
    p_PagingReadBytesRequested = (struct _RDBSS_DEVICE_OBJECT::$8E5F2250B80FEA01BE2192B09BB2E785 *)&RxFileSystemDeviceObject->PagingReadBytesRequested;
    RxFileSystemDeviceObject->NonPagingReadBytesRequested.QuadPart = (LONGLONG)&RxFileSystemDeviceObject->PagingReadBytesRequested;
    p_PagingReadBytesRequested->PagingReadBytesRequested.QuadPart = (LONGLONG)p_PagingReadBytesRequested;
    KeInitializeSpinLock(&v33[26].Alignment);
    InitializeSListHead(v33 + 28);
    RxInitializeDispatchVectors(DriverObject);
    ExInitializeResourceLite(&Resource);
    qword_140043148 = (__int64)&qword_140043140;
    qword_140043140 = (__int64)&qword_140043140;
    Fcb = 0;
    *((_QWORD *)&RxDeviceFCB.1 + 18) = &RxContextLookasideList.L.AllocateMisses;
    RxInitializeRxTimer();
    RxIsLoadedAsDriver = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x14008321c  mov     r11, rsp
0x14008321f  mov     [r11+18h], rbx
0x140083223  mov     [r11+20h], rsi
0x140083227  push    rdi
0x140083228  push    r12
0x14008322a  push    r13
0x14008322c  push    r14
0x14008322e  push    r15
0x140083230  sub     rsp, 0B0h
0x140083237  mov     rax, cs:__security_cookie
0x14008323e  xor     rax, rsp
0x140083241  mov     qword ptr [rsp+0D8h+Line], rax
0x140083249  mov     r15, rdx
0x14008324c  mov     r14, rcx
0x14008324f  mov     [rsp+0D8h+var_88], 0C000000Dh
0x140083257  xor     r12d, r12d
0x14008325a  mov     [rsp+0D8h+var_84], r12d
0x14008325f  xorps   xmm0, xmm0
0x140083262  movups  xmmword ptr [r11-50h], xmm0
0x140083267  xorps   xmm1, xmm1
0x14008326a  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm1
0x14008326f  mov     [r11-80h], r12
0x140083273  mov     ecx, 0FFFFh; GroupNumber
0x140083278  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14008327f  nop     dword ptr [rax+rax+00h]
0x140083284  mov     edx, eax
0x140083286  add     rdx, rdx
0x140083289  mov     eax, 0FFFFFFFFh
0x14008328e  lea     esi, [r12+8]
0x140083293  cmp     rdx, rax
0x140083296  jbe     short loc_14008329A
0x140083298  mov     edx, esi
0x14008329a  mov     eax, edx
0x14008329c  cmp     edx, esi
0x14008329e  cmovb   eax, esi
0x1400832a1  mov     ecx, 7FFFFFFFh
0x1400832a6  cmp     eax, ecx
0x1400832a8  ja      short loc_1400832B1
0x1400832aa  mov     ecx, edx
0x1400832ac  cmp     edx, esi
0x1400832ae  cmovb   ecx, esi
0x1400832b1  mov     cs:FspPerDeviceThreshold, ecx
0x1400832b7  shr     ecx, 1
0x1400832b9  mov     eax, 4
0x1400832be  cmp     ecx, eax
0x1400832c0  cmovb   ecx, eax
0x1400832c3  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, ecx
0x1400832c9  call    wil_InitializeFeatureStaging
0x1400832ce  call    cs:__imp_KeQueryTimeIncrement
0x1400832d5  nop     dword ptr [rax+rax+00h]
0x1400832da  mov     ecx, eax
0x1400832dc  xor     edx, edx
0x1400832de  mov     eax, 989680h
0x1400832e3  div     ecx
0x1400832e5  mov     ecx, eax
0x1400832e7  mov     cs:RxTicksPerSecond, rcx
0x1400832ee  call    RxCheckFcbStructuresForAlignment
0x1400832f3  call    cs:__imp_PsIsDiskCountersEnabled
0x1400832fa  nop     dword ptr [rax+rax+00h]
0x1400832ff  mov     cs:RxEnablePerProcessCounters, al
0x140083305  call    cs:__imp_KeQueryHighestNodeNumber
0x14008330c  nop     dword ptr [rax+rax+00h]
0x140083311  mov     r13d, 1
0x140083317  add     ax, r13w
0x14008331b  mov     cs:RxMaxNumaNodes, ax
0x140083322  mov     cs:RxMaxProcessorsPerNode, r12w
0x14008332a  mov     ebx, r12d
0x14008332d  cmp     r12w, ax
0x140083331  jnb     short loc_140083375
0x140083333  movzx   ecx, bx; NodeNumber
0x140083336  call    cs:__imp_KeQueryNodeMaximumProcessorCount
0x14008333d  nop     dword ptr [rax+rax+00h]
0x140083342  movzx   ecx, cs:RxMaxProcessorsPerNode
0x140083349  cmp     cx, ax
0x14008334c  ja      short loc_140083360
0x14008334e  movzx   ecx, bx; NodeNumber
0x140083351  call    cs:__imp_KeQueryNodeMaximumProcessorCount
0x140083358  nop     dword ptr [rax+rax+00h]
0x14008335d  movzx   ecx, ax
0x140083360  mov     cs:RxMaxProcessorsPerNode, cx
0x140083367  add     ebx, r13d
0x14008336a  movzx   eax, cs:RxMaxNumaNodes
0x140083371  cmp     ebx, eax
0x140083373  jb      short loc_140083333
0x140083375  xor     edx, edx; Val
0x140083377  mov     r8d, 120h; Size
0x14008337d  lea     rcx, RxContextLookasideList.L.18h; void *
0x140083384  call    memset
0x140083389  mov     dword ptr cs:RxContextLookasideList.L.18h, 120EB00h
0x140083393  mov     qword ptr cs:RxContextLookasideList.L.20h, r14
0x14008339a  mov     cs:Set, 0FFFFFFFFFFFFFFFFh
0x1400833a5  xor     edx, edx; Val
0x1400833a7  mov     r8d, 2ECh; Size
0x1400833ad  lea     rcx, RxDeviceFCB+4; void *
0x1400833b4  call    memset
0x1400833b9  mov     dword ptr cs:RxDeviceFCB, 2F0EC23h
0x1400833c3  mov     cs:RxDeviceFCBHeaderMutex, r13d
0x1400833ca  mov     cs:qword_140038A28, r12
0x1400833d1  mov     cs:dword_140038A30, r12d
0x1400833d8  xor     r8d, r8d; State
0x1400833db  mov     edx, r13d; Type
0x1400833de  lea     rcx, Event; Event
0x1400833e5  call    cs:__imp_KeInitializeEvent
0x1400833ec  nop     dword ptr [rax+rax+00h]
0x1400833f1  or      byte ptr cs:RxDeviceFCB+4, 40h
0x1400833f8  or      byte ptr cs:RxDeviceFCB+6, 2
0x1400833ff  mov     al, byte ptr cs:RxDeviceFCB+7
0x140083405  and     al, 0Fh
0x140083407  or      al, 50h
0x140083409  mov     byte ptr cs:RxDeviceFCB+7, al
0x14008340f  lea     rax, RxDeviceFCB+38h
0x140083416  mov     qword ptr cs:RxDeviceFCB+40h, rax
0x14008341d  mov     qword ptr cs:RxDeviceFCB+38h, rax
0x140083424  lea     rax, RxDeviceFCBHeaderMutex
0x14008342b  mov     qword ptr cs:RxDeviceFCB+30h, rax
0x140083432  xorps   xmm0, xmm0
0x140083435  movdqu  xmmword ptr cs:RxDeviceFCB+48h, xmm0
0x14008343d  xorps   xmm1, xmm1
0x140083440  movdqu  xmmword ptr cs:RxDeviceFCB+58h, xmm1
0x140083448  mov     dword ptr cs:RxDeviceFCB+68h, r12d
0x14008344f  mov     qword ptr cs:RxDeviceFCB+70h, r12
0x140083456  mov     rdi, r12
0x140083459  mov     rbx, r12
0x14008345c  lea     r12, cs:140000000h
0x140083463  lea     rcx, rva SpinLock[r12]
0x14008346b  add     rcx, rbx; SpinLock
0x14008346e  call    cs:__imp_KeInitializeSpinLock
0x140083475  nop     dword ptr [rax+rax+00h]
0x14008347a  lea     rcx, rva qword_140035700[r12]
0x140083482  add     rcx, rbx; SpinLock
0x140083485  call    cs:__imp_KeInitializeSpinLock
0x14008348c  nop     dword ptr [rax+rax+00h]
0x140083491  lea     rax, rva RxActiveContexts.Flink[r12]
0x140083499  add     rax, rbx
0x14008349c  mov     [rbx+r12+356C8h], rax
0x1400834a4  mov     [rax], rax
0x1400834a7  lea     rax, rva qword_1400356D0[r12]
0x1400834af  add     rax, rbx
0x1400834b2  mov     [rbx+r12+356D8h], rax
0x1400834ba  mov     [rbx+r12+356D0h], rax
0x1400834c2  lea     rax, rva qword_1400356E0[r12]
0x1400834ca  add     rax, rbx
0x1400834cd  mov     [rbx+r12+356E8h], rax
0x1400834d5  mov     [rbx+r12+356E0h], rax
0x1400834dd  add     rdi, r13
0x1400834e0  add     rbx, 0C0h
0x1400834e7  cmp     rdi, 40h ; '@'
0x1400834eb  jnz     loc_140083463
0x1400834f1  movzx   ecx, cs:RxMaxNumaNodes
0x1400834f8  xor     edx, edx
0x1400834fa  mov     eax, edi
0x1400834fc  div     ecx
0x1400834fe  cmp     eax, r13d
0x140083501  cmovl   eax, r13d
0x140083505  mov     cs:RxActiveContextNodeBucketSize, eax
0x14008350b  xor     r12d, r12d
0x14008350e  mov     cs:RxLinkedConnectionLock, r12
0x140083515  mov     cs:RxContextStartStopLock, r12
0x14008351c  lea     rax, RxOrphanedFcbListHead
0x140083523  mov     cs:qword_140038AF8, rax
0x14008352a  mov     cs:RxOrphanedFcbListHead, rax
0x140083531  mov     cs:RxOrphanedFcbListLock, r12
0x140083538  xor     r8d, r8d; State
0x14008353b  xor     edx, edx; Type
0x14008353d  lea     rcx, WPP_MAIN_CB.DeviceExtension; Event
0x140083544  call    cs:__imp_KeInitializeEvent
0x14008354b  nop     dword ptr [rax+rax+00h]
0x140083550  nop
0x140083551  lea     edi, [r12+9]
0x140083556  mov     [rsp+0D8h+var_84], edi
0x14008355a  mov     cs:RxFileSystemDeviceObject, r12
0x140083561  mov     cs:Object, r12
0x140083568  call    cs:__imp_IoGetCurrentProcess
0x14008356f  nop     dword ptr [rax+rax+00h]
0x140083574  mov     cs:qword_140043098, rax
0x14008357b  mov     [rsp+0D8h+StartContext], r12; StartContext
0x140083580  lea     rax, RxpIdleWorkerThread
0x140083587  mov     [rsp+0D8h+StartRoutine], rax; StartRoutine
0x14008358c  mov     [rsp+0D8h+ClientId], r12; ClientId
0x140083591  xor     r9d, r9d; ProcessHandle
0x140083594  xor     r8d, r8d; ObjectAttributes
0x140083597  mov     edx, 1FFFFFh; DesiredAccess
0x14008359c  lea     rcx, [rsp+0D8h+ThreadHandle]; ThreadHandle
0x1400835a1  call    cs:__imp_PsCreateSystemThread
0x1400835a8  nop     dword ptr [rax+rax+00h]
0x1400835ad  mov     ebx, eax
0x1400835af  mov     [rsp+0D8h+var_88], eax
0x1400835b3  test    eax, eax
0x1400835b5  js      loc_140083A0C
0x1400835bb  mov     [rsp+0D8h+StartRoutine], r12; HandleInformation
0x1400835c0  lea     rax, Object
0x1400835c7  mov     [rsp+0D8h+ClientId], rax; Object
0x1400835cc  xor     r9d, r9d; AccessMode
0x1400835cf  xor     r8d, r8d; ObjectType
0x1400835d2  mov     edx, 1FFFFFh; DesiredAccess
0x1400835d7  mov     rcx, [rsp+0D8h+ThreadHandle]; Handle
0x1400835dc  call    cs:__imp_ObReferenceObjectByHandle
0x1400835e3  nop     dword ptr [rax+rax+00h]
0x1400835e8  mov     rcx, [rsp+0D8h+ThreadHandle]; Handle
0x1400835ed  call    cs:__imp_ZwClose
0x1400835f4  nop     dword ptr [rax+rax+00h]
0x1400835f9  mov     edi, esi
0x1400835fb  mov     [rsp+0D8h+var_84], esi
0x1400835ff  lea     rdx, SourceString; "\\??\\fsWrap"
0x140083606  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x14008360b  call    cs:__imp_RtlInitUnicodeString
0x140083612  nop     dword ptr [rax+rax+00h]
0x140083617  lea     rdx, aDeviceFswrap; "\\Device\\FsWrap"
0x14008361e  lea     rcx, [rsp+0D8h+DeviceName]; DestinationString
0x140083626  call    cs:__imp_RtlInitUnicodeString
0x14008362d  nop     dword ptr [rax+rax+00h]
0x140083632  lea     rcx, [rsp+0D8h+DestinationString]; SymbolicLinkName
0x140083637  call    cs:__imp_IoDeleteSymbolicLink
0x14008363e  nop     dword ptr [rax+rax+00h]
0x140083643  lea     rdx, [rsp+0D8h+DeviceName]; DeviceName
0x14008364b  lea     rcx, [rsp+0D8h+DestinationString]; SymbolicLinkName
0x140083650  call    cs:__imp_IoCreateSymbolicLink
0x140083657  nop     dword ptr [rax+rax+00h]
0x14008365c  mov     ebx, eax
0x14008365e  mov     [rsp+0D8h+var_88], eax
0x140083662  test    eax, eax
0x140083664  js      loc_140083A0C
0x14008366a  lea     edi, [r12+7]
0x14008366f  mov     [rsp+0D8h+var_84], edi
0x140083673  lea     rax, RxFileSystemDeviceObject
0x14008367a  mov     [rsp+0D8h+StartContext], rax; DeviceObject
0x14008367f  mov     byte ptr [rsp+0D8h+StartRoutine], r12b; Exclusive
0x140083684  mov     dword ptr [rsp+0D8h+ClientId], 10h; DeviceCharacteristics
0x14008368c  lea     r9d, [r12+14h]; DeviceType
0x140083691  lea     r8, [rsp+0D8h+DeviceName]; DeviceName
0x140083699  mov     edx, 3D0h; DeviceExtensionSize
0x14008369e  mov     rcx, r14; DriverObject
0x1400836a1  call    cs:__imp_IoCreateDevice
0x1400836a8  nop     dword ptr [rax+rax+00h]
0x1400836ad  mov     ebx, eax
0x1400836af  mov     [rsp+0D8h+var_88], eax
0x1400836b3  test    eax, eax
0x1400836b5  js      loc_140083A0C
0x1400836bb  lea     edi, [r12+6]
0x1400836c0  mov     [rsp+0D8h+var_84], edi
0x1400836c4  cmp     cs:RxEnablePerProcessCounters, r12b
0x1400836cb  jz      loc_1400837B5
0x1400836d1  mov     rcx, cs:RxFileSystemDeviceObject
0x1400836d8  add     rcx, 4E8h
0x1400836df  call    RdbssKernelInterfaceCreateInstance
0x1400836e4  mov     ebx, eax
0x1400836e6  mov     [rsp+0D8h+var_88], eax
0x1400836ea  test    eax, eax
0x1400836ec  js      loc_140083A0C
0x1400836f2  mov     rcx, cs:RxFileSystemDeviceObject
0x1400836f9  lea     rax, [rcx+4F0h]
0x140083700  mov     [rsp+0D8h+ClientId], rax
0x140083705  mov     rcx, [rcx+4E8h]
0x14008370c  call    RdbssStatisticsDatabaseCreateInstance
0x140083711  mov     ebx, eax
0x140083713  mov     [rsp+0D8h+var_88], eax
0x140083717  test    eax, eax
0x140083719  js      loc_140083A0C
0x14008371f  mov     rbx, cs:RxFileSystemDeviceObject
0x140083726  lea     rcx, [rbx+508h]
0x14008372d  call    RxSecurityDescriptorGetFromRegistry
0x140083732  mov     [rbx+510h], al
0x140083738  mov     rax, cs:RxFileSystemDeviceObject
0x14008373f  cmp     [rax+510h], r12b
0x140083746  jnz     short loc_1400837B5
0x140083748  mov     [rsp+0D8h+var_40], r12d
0x140083750  mov     [rsp+0D8h+var_3C], 500h
0x14008375a  mov     [rsp+0D8h+var_78], 50h ; 'P'
0x140083762  mov     [rsp+0D8h+var_74], 0B10FF35Eh
0x14008376a  mov     [rsp+0D8h+var_70], 4AE6481h
0x140083772  mov     [rsp+0D8h+var_6C], 29A24CB1h
0x14008377a  mov     [rsp+0D8h+var_68], 214CB114h
0x140083782  mov     [rsp+0D8h+var_64], 568656A6h
0x14008378a  add     rax, 508h
0x140083790  mov     [rsp+0D8h+ClientId], rax
0x140083795  lea     r9, [rsp+0D8h+var_78]
0x14008379a  lea     rdx, [rsp+0D8h+var_40]
0x1400837a2  call    RxSecurityDescriptorCreate
0x1400837a7  mov     ebx, eax
0x1400837a9  mov     [rsp+0D8h+var_88], eax
0x1400837ad  test    eax, eax
0x1400837af  js      loc_140083A0C
0x1400837b5  mov     qword ptr cs:WPP_MAIN_CB.Type, r12
0x1400837bc  lea     rax, WPP_ThisDir_CTLGUID_RdbssLog
0x1400837c3  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400837ca  mov     cs:WPP_MAIN_CB.NextDevice, r12
0x1400837d1  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x1400837d8  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400837e3  call    WppLoadTracingSupport
0x1400837e8  mov     cs:WPP_MAIN_CB.CurrentIrp, r12
0x1400837ef  call    WppInitKm
0x1400837f4  call    McGenEventRegister_EtwRegister
0x1400837f9  mov     [rsp+0D8h+var_88], eax
0x1400837fd  test    eax, eax
0x1400837ff  jz      short loc_14008383E
0x140083801  lea     rbx, WPP_GLOBAL_Control
0x140083808  mov     r10, cs:WPP_GLOBAL_Control
0x14008380f  cmp     r10, rbx
0x140083812  jz      short loc_140083845
0x140083814  mov     ecx, [r10+2Ch]
  ... truncated ...
```
