# ClassRemoveDevice

- ea: `0x1400231f0`
- end: `0x14002396c`
- name: `ClassRemoveDevice`
- size: `1916`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, UCHAR RemoveType)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x1400231f0`
- `0x140057820`
- `0x14005fe50`

## callees

- `0x1400134a0`
- `0x1400157d0`
- `0x140015ae0`
- `0x140018018`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14002001c`
- `0x140021c08`
- `0x140023110`
- `0x14002314c`
- `0x1400231f0`
- `0x14003e470`
- `0x140054160`
- `0x1400542a0`
- `0x1400559f0`
- `0x140057890`
- `0x14005b740`
- `0x14005d068`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400232ab`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400232ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400232bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023844`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400232bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023844`
- `ntoskrnl!KeSetEvent` at `0x140023330`
- `ntoskrnl!KeSetEvent` at `0x140023330`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023517`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002354c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023688`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400236f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002373a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023769`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023798`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400237c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400237ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023810`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002382e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002386a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023892`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023517`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002354c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023688`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400236f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002373a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023769`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023798`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400237c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400237ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023810`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002382e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002386a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023892`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400235ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400235ca`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002331b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140023667`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002331b`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140023667`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14002329c`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14002329c`
- `ntoskrnl!IoDetachDevice` at `0x14002390b`
- `ntoskrnl!IoDetachDevice` at `0x14002390b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400236d8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400236d8`
- `ntoskrnl!IoDeleteDevice` at `0x14002394e`
- `ntoskrnl!IoDeleteDevice` at `0x14002394e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002360a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002360a`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140023210`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140023210`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002364d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002364d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14002352a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14002352a`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140023245`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140023245`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140023403`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140023403`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400234b1`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x1400234b1`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400234e6`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400234e6`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400236b0`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400236b0`

## pseudocode

```c
NTSTATUS __stdcall ClassRemoveDevice(PDEVICE_OBJECT DeviceObject, UCHAR RemoveType)
{
  _QWORD *DriverObjectExtension; // rax
  __int64 Timer_high; // rdx
  unsigned int *DeviceExtension; // rbp
  struct _DEVICE_OBJECT *v7; // r15
  NTSTATUS v8; // eax
  __int64 v9; // rbx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  struct _FUNCTIONAL_DEVICE_EXTENSION *v12; // rbx
  _CLASS_FUNCTION_SUPPORT_INFO *FunctionSupportInfo; // rax
  PDEVICE_OBJECT *v14; // rcx
  PDEVICE_OBJECT v15; // rax
  __int64 v16; // rcx
  PVOID *v17; // rdx
  _FAILURE_PREDICTION_INFO *FailurePredictionInfo; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rdi
  _LIST_ENTRY *p_AllFdosListEntry; // rdi
  KIRQL v23; // al
  _LIST_ENTRY *Flink; // rdx
  _LIST_ENTRY *Blink; // rcx
  _CLASS_PRIVATE_FDO_DATA *v26; // rcx
  _CLASS_PAGE_HASH_DATA *PageHashErrorLog; // rcx
  void *v28; // rax
  _STORAGE_ZONE_GROUP *ZoneGroup; // rcx
  _IRP *PowerProcessIrp; // rcx
  _PNL_SLIST_HEADER *FreeTransferPacketsLists; // rcx
  _PP_FDO_DATA *PerProcessorData; // rcx
  _CLASS_PRIVATE_FDO_DATA *v33; // rcx
  _ADDITIONAL_FDO_DATA *AdditionalFdoData; // rcx
  void *v35; // rcx
  _CLASS_FUNCTION_SUPPORT_INFO *v36; // rax
  _STORAGE_HW_FIRMWARE_INFO *HwFirmwareInfo; // rcx
  _CLASS_FUNCTION_SUPPORT_INFO *v38; // rcx
  _STORAGE_MINIPORT_DESCRIPTOR *MiniportDescriptor; // rcx
  _STORAGE_ADAPTER_DESCRIPTOR *AdapterDescriptor; // rcx
  _STORAGE_DEVICE_DESCRIPTOR *DeviceDescriptor; // rcx

  DriverObjectExtension = IoGetDriverObjectExtension(DeviceObject->DriverObject, ClassInitialize);
  DeviceExtension = (unsigned int *)DeviceObject->DeviceExtension;
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
  if ( (DeviceExtension[26] & 1) != 0 || DriverObjectExtension[38] )
  {
    v8 = IoWMIRegistrationControl(DeviceObject, 2u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          180,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          DeviceObject,
          v8);
    }
  }
  if ( *((_QWORD *)DeviceExtension + 49) )
  {
    IoSetDeviceInterfaceState((PUNICODE_STRING)DeviceExtension + 24, 0);
    RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 24);
    RtlInitUnicodeString((PUNICODE_STRING)DeviceExtension + 24, 0);
  }
  if ( RemoveType != 2 )
    goto LABEL_24;
  ClassReleaseRemoveLock(DeviceObject, DeviceObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      181,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      DeviceExtension[10]);
  }
  v9 = *((_QWORD *)DeviceExtension + 55);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v9 + 8));
  KeSetEvent((PRKEVENT)DeviceExtension + 2, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 182, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
  }
  if ( (DeviceExtension[26] & 1) != 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v11 = 183;
LABEL_23:
      WPP_SF_q(v10->AttachedDevice, v11, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  if ( *((_BYTE *)DeviceObject->DeviceExtension + 512) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v11 = 184;
      goto LABEL_23;
    }
LABEL_24:
    LOBYTE(Timer_high) = RemoveType;
    (*(void (__fastcall **)(PDEVICE_OBJECT, __int64))(*((_QWORD *)DeviceExtension + 20) + 88LL))(
      DeviceObject,
      Timer_high);
    if ( (DeviceExtension[26] & 1) == 0 )
    {
      if ( RemoveType == 2 )
        ClassRemoveChild(*((PFUNCTIONAL_DEVICE_EXTENSION *)DeviceExtension + 3));
      goto LABEL_95;
    }
    v12 = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
    ClasspDisableTimer(v12);
    if ( RemoveType != 2 )
    {
      if ( RemoveType == 23 )
        ClassMarkChildrenMissing(v12);
      goto LABEL_95;
    }
    FunctionSupportInfo = v12->FunctionSupportInfo;
    if ( FunctionSupportInfo && (*(_DWORD *)&FunctionSupportInfo->IdlePower & 4) != 0 )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceExtension);
      v14 = (PDEVICE_OBJECT *)IdlePowerFDOList;
      if ( IdlePowerFDOList != &IdlePowerFDOList )
      {
        while ( 1 )
        {
          v15 = *v14;
          if ( v14[2] == DeviceObject )
            break;
          v14 = (PDEVICE_OBJECT *)*v14;
          if ( v15 == (PDEVICE_OBJECT)&IdlePowerFDOList )
            goto LABEL_45;
        }
        if ( (PDEVICE_OBJECT *)v15->DriverObject != v14 )
          goto LABEL_61;
        v17 = (PVOID *)v14[1];
        if ( *v17 != v14 )
          goto LABEL_61;
        *v17 = v15;
        v15->DriverObject = (_DRIVER_OBJECT *)v17;
        ExFreePoolWithTag(v14, 0);
      }
LABEL_45:
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceExtension);
    }
    ClassCleanupMediaChangeDetection(v12);
    FailurePredictionInfo = v12->FailurePredictionInfo;
    if ( FailurePredictionInfo )
    {
      ExFreePoolWithTag(FailurePredictionInfo, 0);
      v12->FailurePredictionInfo = 0;
    }
    ClassAcquireChildLock(v12);
    while ( 1 )
    {
      v20 = ClassRemoveChild(v12);
      if ( !v20 )
        break;
      v19 = *(_QWORD *)(*(_QWORD *)(v20 + 8) + 64LL);
      *(_BYTE *)(v20 + 512) = 1;
      *(_DWORD *)(v19 + 108) = 1;
      ClassRemoveDevice(*(PDEVICE_OBJECT *)(v20 + 8), 2u);
    }
    ClassReleaseChildLock(v12);
    ClasspFreeReleaseRequest(DeviceObject);
    PrivateFdoData = v12->PrivateFdoData;
    if ( !PrivateFdoData )
      goto LABEL_75;
    p_AllFdosListEntry = &PrivateFdoData->AllFdosListEntry;
    v23 = KeAcquireSpinLockRaiseToDpc(&AllFdosListSpinlock);
    Flink = p_AllFdosListEntry->Flink;
    if ( !p_AllFdosListEntry->Flink || (Blink = p_AllFdosListEntry->Blink) == 0 )
    {
LABEL_57:
      KeReleaseSpinLock(&AllFdosListSpinlock, v23);
      p_AllFdosListEntry->Blink = p_AllFdosListEntry;
      p_AllFdosListEntry->Flink = p_AllFdosListEntry;
      DestroyAllTransferPackets(DeviceObject);
      ClasspDeleteTimer(v12);
      ClasspUnregisterBugcheckCallback();
      v26 = v12->PrivateFdoData;
      if ( v26->PageHashErrorLog )
      {
        ExAcquireFastMutex(&v26->PageFileInfoMutex);
        ExWaitForRundownProtectionReleaseCacheAware(v12->PrivateFdoData->PageFileRunDown);
        PageHashErrorLog = v12->PrivateFdoData->PageHashErrorLog;
        if ( PageHashErrorLog )
        {
          ExFreePoolWithTag(PageHashErrorLog, 0);
          v12->PrivateFdoData->PageHashErrorLog = 0;
        }
        ExFreeCacheAwareRundownProtection(v12->PrivateFdoData->PageFileRunDown);
        v12->PrivateFdoData->PageFileRunDown = 0;
        ExReleaseFastMutex(&v12->PrivateFdoData->PageFileInfoMutex);
        while ( 1 )
        {
          v28 = (void *)SimplePopSlist(&v12->PrivateFdoData->PageFilesInfo);
          if ( !v28 )
            break;
          ExFreePoolWithTag(v28, 0);
        }
        v12->PrivateFdoData->PageFilesInfo.Next = 0;
      }
      ZoneGroup = v12->PrivateFdoData->ZoneGroup;
      if ( ZoneGroup )
      {
        ExFreePoolWithTag(ZoneGroup, 0);
        v12->PrivateFdoData->ZoneGroup = 0;
      }
      PowerProcessIrp = v12->PrivateFdoData->PowerProcessIrp;
      if ( PowerProcessIrp )
      {
        ExFreePoolWithTag(PowerProcessIrp, 0);
        v12->PrivateFdoData->PowerProcessIrp = 0;
      }
      FreeTransferPacketsLists = v12->PrivateFdoData->FreeTransferPacketsLists;
      if ( FreeTransferPacketsLists )
      {
        ExFreePoolWithTag(FreeTransferPacketsLists, 0);
        v12->PrivateFdoData->FreeTransferPacketsLists = 0;
      }
      PerProcessorData = v12->PrivateFdoData->PerProcessorData;
      if ( PerProcessorData )
      {
        ExFreePoolWithTag(PerProcessorData, 0);
        v12->PrivateFdoData->PerProcessorData = 0;
      }
      v33 = v12->PrivateFdoData;
      if ( v33 )
      {
        ExFreePoolWithTag(v33, 0);
        v12->PrivateFdoData = 0;
      }
LABEL_75:
      AdditionalFdoData = v12->AdditionalFdoData;
      if ( AdditionalFdoData )
      {
        ExFreePoolWithTag(AdditionalFdoData, 0);
        v12->AdditionalFdoData = 0;
      }
      v35 = (void *)*((_QWORD *)DeviceExtension + 15);
      if ( v35 )
      {
        ExFreePoolWithTag(v35, 0);
        *((_QWORD *)DeviceExtension + 15) = 0;
        RtlInitUnicodeString((PUNICODE_STRING)DeviceExtension + 7, 0);
      }
      v36 = v12->FunctionSupportInfo;
      if ( v36 )
      {
        HwFirmwareInfo = v36->HwFirmwareInfo;
        if ( HwFirmwareInfo )
        {
          ExFreePoolWithTag(HwFirmwareInfo, 0);
          v12->FunctionSupportInfo->HwFirmwareInfo = 0;
        }
      }
      v38 = v12->FunctionSupportInfo;
      if ( v38 )
      {
        ExFreePoolWithTag(v38, 0);
        v12->FunctionSupportInfo = 0;
      }
      MiniportDescriptor = v12->MiniportDescriptor;
      if ( MiniportDescriptor )
      {
        ExFreePoolWithTag(MiniportDescriptor, 0);
        v12->MiniportDescriptor = 0;
      }
      AdapterDescriptor = v12->AdapterDescriptor;
      if ( AdapterDescriptor )
      {
        ExFreePoolWithTag(AdapterDescriptor, 0);
        v12->AdapterDescriptor = 0;
      }
      DeviceDescriptor = v12->DeviceDescriptor;
      if ( DeviceDescriptor )
      {
        ExFreePoolWithTag(DeviceDescriptor, 0);
        v12->DeviceDescriptor = 0;
      }
      IoDetachDevice(v7);
LABEL_95:
      *((_QWORD *)DeviceExtension + 18) = 0;
      if ( RemoveType == 2 )
        IoDeleteDevice(DeviceObject);
      return 0;
    }
    if ( Flink->Blink == p_AllFdosListEntry && Blink->Flink == p_AllFdosListEntry )
    {
      Blink->Flink = Flink;
      Flink->Blink = Blink;
      goto LABEL_57;
    }
LABEL_61:
    __fastfail(3u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 185, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
  }
  ExReInitializeRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v9 + 8));
  ClassAcquireRemoveLockEx(DeviceObject, DeviceObject, "minkernel\\storage\\classpnp\\class.c", 0x3340u);
  v16 = *((_QWORD *)DeviceExtension + 3);
  DeviceExtension[27] = 0;
  IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v16 + 512), BusRelations);
  return 0;
}

```

## disassembly

```asm
0x1400231f0  push    rbx
0x1400231f2  push    rbp
0x1400231f3  push    rsi
0x1400231f4  push    rdi
0x1400231f5  push    r12
0x1400231f7  push    r14
0x1400231f9  push    r15
0x1400231fb  sub     rsp, 30h
0x1400231ff  mov     r14b, dl
0x140023202  mov     rsi, rcx
0x140023205  mov     rcx, [rcx+8]; DriverObject
0x140023209  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140023210  call    cs:__imp_IoGetDriverObjectExtension
0x140023217  nop     dword ptr [rax+rax+00h]
0x14002321c  mov     rbp, [rsi+40h]
0x140023220  lea     rdi, WPP_GLOBAL_Control
0x140023227  xor     r12d, r12d
0x14002322a  test    byte ptr [rbp+68h], 1
0x14002322e  mov     r15, [rbp+10h]
0x140023232  jnz     short loc_14002323D
0x140023234  cmp     [rax+130h], r12
0x14002323b  jz      short loc_140023287
0x14002323d  mov     edx, 2; Action
0x140023242  mov     rcx, rsi; DeviceObject
0x140023245  call    cs:__imp_IoWMIRegistrationControl
0x14002324c  nop     dword ptr [rax+rax+00h]
0x140023251  mov     rcx, cs:WPP_GLOBAL_Control
0x140023258  cmp     rcx, rdi
0x14002325b  jz      short loc_140023287
0x14002325d  mov     edx, [rcx+2Ch]
0x140023260  test    dl, 40h
0x140023263  jz      short loc_140023287
0x140023265  cmp     byte ptr [rcx+29h], 4
0x140023269  jb      short loc_140023287
0x14002326b  mov     rcx, [rcx+18h]
0x14002326f  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140023276  mov     edx, 0B4h
0x14002327b  mov     [rsp+68h+var_48], eax
0x14002327f  mov     r9, rsi
0x140023282  call    WPP_SF_qD
0x140023287  cmp     [rbp+188h], r12
0x14002328e  jz      short loc_1400232C8
0x140023290  lea     rbx, [rbp+180h]
0x140023297  xor     edx, edx; Enable
0x140023299  mov     rcx, rbx; SymbolicLinkName
0x14002329c  call    cs:__imp_IoSetDeviceInterfaceState
0x1400232a3  nop     dword ptr [rax+rax+00h]
0x1400232a8  mov     rcx, rbx; UnicodeString
0x1400232ab  call    cs:__imp_RtlFreeUnicodeString
0x1400232b2  nop     dword ptr [rax+rax+00h]
0x1400232b7  xor     edx, edx; SourceString
0x1400232b9  mov     rcx, rbx; DestinationString
0x1400232bc  call    cs:__imp_RtlInitUnicodeString
0x1400232c3  nop     dword ptr [rax+rax+00h]
0x1400232c8  cmp     r14b, 2
0x1400232cc  jnz     loc_1400233A8
0x1400232d2  mov     rdx, rsi; Tag
0x1400232d5  mov     rcx, rsi; DeviceObject
0x1400232d8  call    ClassReleaseRemoveLock
0x1400232dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232e4  cmp     rcx, rdi
0x1400232e7  jz      short loc_140023310
0x1400232e9  mov     eax, [rcx+2Ch]
0x1400232ec  test    r14b, al
0x1400232ef  jz      short loc_140023310
0x1400232f1  cmp     byte ptr [rcx+29h], 3
0x1400232f5  jb      short loc_140023310
0x1400232f7  mov     r9d, [rbp+28h]
0x1400232fb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140023302  mov     rcx, [rcx+18h]
0x140023306  mov     edx, 0B5h
0x14002330b  call    WPP_SF_d
0x140023310  mov     rbx, [rbp+1B8h]
0x140023317  lea     rcx, [rbx+8]; RunRef
0x14002331b  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140023322  nop     dword ptr [rax+rax+00h]
0x140023327  lea     rcx, [rbp+30h]; Event
0x14002332b  xor     r8d, r8d; Wait
0x14002332e  xor     edx, edx; Increment
0x140023330  call    cs:__imp_KeSetEvent
0x140023337  nop     dword ptr [rax+rax+00h]
0x14002333c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023343  cmp     rcx, rdi
0x140023346  jz      short loc_14002336D
0x140023348  mov     eax, [rcx+2Ch]
0x14002334b  test    al, 2
0x14002334d  jz      short loc_14002336D
0x14002334f  cmp     byte ptr [rcx+29h], 3
0x140023353  jb      short loc_14002336D
0x140023355  mov     rcx, [rcx+18h]
0x140023359  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140023360  mov     edx, 0B6h
0x140023365  mov     r9, rsi
0x140023368  call    WPP_SF_q
0x14002336d  test    byte ptr [rbp+68h], 1
0x140023371  jz      loc_140023440
0x140023377  mov     rcx, cs:WPP_GLOBAL_Control
0x14002337e  cmp     rcx, rdi
0x140023381  jz      short loc_1400233A8
0x140023383  mov     eax, [rcx+2Ch]
0x140023386  test    al, 2
0x140023388  jz      short loc_1400233A8
0x14002338a  cmp     byte ptr [rcx+29h], 3
0x14002338e  jb      short loc_1400233A8
0x140023390  mov     edx, 0B7h
0x140023395  mov     rcx, [rcx+18h]
0x140023399  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400233a0  mov     r9, rsi
0x1400233a3  call    WPP_SF_q
0x1400233a8  mov     rax, [rbp+0A0h]
0x1400233af  mov     dl, r14b
0x1400233b2  mov     rcx, rsi
0x1400233b5  mov     rax, [rax+58h]
0x1400233b9  call    _guard_dispatch_icall
0x1400233be  test    byte ptr [rbp+68h], 1
0x1400233c2  jz      loc_140023929
0x1400233c8  mov     rbx, [rsi+40h]
0x1400233cc  mov     rcx, rbx
0x1400233cf  call    ClasspDisableTimer
0x1400233d4  cmp     r14b, 2
0x1400233d8  jnz     loc_140023919
0x1400233de  mov     rax, [rbx+480h]
0x1400233e5  test    rax, rax
0x1400233e8  jz      loc_140023536
0x1400233ee  mov     eax, [rax+0A0h]
0x1400233f4  test    al, 4
0x1400233f6  jz      loc_140023536
0x1400233fc  lea     rcx, WPP_MAIN_CB.DeviceExtension; Mutex
0x140023403  call    cs:__imp_KeAcquireGuardedMutex
0x14002340a  nop     dword ptr [rax+rax+00h]
0x14002340f  mov     rcx, cs:IdlePowerFDOList; P
0x140023416  lea     rdx, IdlePowerFDOList
0x14002341d  cmp     rcx, rdx
0x140023420  jz      loc_140023523
0x140023426  mov     rax, [rcx]
0x140023429  cmp     [rcx+10h], rsi
0x14002342d  jz      loc_1400234F7
0x140023433  mov     rcx, rax
0x140023436  cmp     rax, rdx
0x140023439  jnz     short loc_140023426
0x14002343b  jmp     loc_140023523
0x140023440  mov     rax, [rsi+40h]
0x140023444  cmp     [rax+200h], r12b
0x14002344b  jz      short loc_14002347C
0x14002344d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023454  cmp     rcx, rdi
0x140023457  jz      loc_1400233A8
0x14002345d  mov     eax, [rcx+2Ch]
0x140023460  test    al, 2
0x140023462  jz      loc_1400233A8
0x140023468  cmp     byte ptr [rcx+29h], 3
0x14002346c  jb      loc_1400233A8
0x140023472  mov     edx, 0B8h
0x140023477  jmp     loc_140023395
0x14002347c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023483  cmp     rcx, rdi
0x140023486  jz      short loc_1400234AD
0x140023488  mov     eax, [rcx+2Ch]
0x14002348b  test    al, 2
0x14002348d  jz      short loc_1400234AD
0x14002348f  cmp     byte ptr [rcx+29h], 3
0x140023493  jb      short loc_1400234AD
0x140023495  mov     rcx, [rcx+18h]
0x140023499  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400234a0  mov     edx, 0B9h
0x1400234a5  mov     r9, rsi
0x1400234a8  call    WPP_SF_q
0x1400234ad  lea     rcx, [rbx+8]; RunRefCacheAware
0x1400234b1  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x1400234b8  nop     dword ptr [rax+rax+00h]
0x1400234bd  mov     r9d, 3340h; Line
0x1400234c3  lea     r8, File; "minkernel\\storage\\classpnp\\class.c"
0x1400234ca  mov     rdx, rsi; Tag
0x1400234cd  mov     rcx, rsi; DeviceObject
0x1400234d0  call    ClassAcquireRemoveLockEx
0x1400234d5  mov     rcx, [rbp+18h]
0x1400234d9  xor     edx, edx; Type
0x1400234db  mov     [rbp+6Ch], r12d
0x1400234df  mov     rcx, [rcx+200h]; DeviceObject
0x1400234e6  call    cs:__imp_IoInvalidateDeviceRelations
0x1400234ed  nop     dword ptr [rax+rax+00h]
0x1400234f2  jmp     loc_14002395A
0x1400234f7  cmp     [rax+8], rcx
0x1400234fb  jnz     loc_1400236EB
0x140023501  mov     rdx, [rcx+8]
0x140023505  cmp     [rdx], rcx
0x140023508  jnz     loc_1400236EB
0x14002350e  mov     [rdx], rax
0x140023511  mov     [rax+8], rdx
0x140023515  xor     edx, edx; Tag
0x140023517  call    cs:__imp_ExFreePoolWithTag
0x14002351e  nop     dword ptr [rax+rax+00h]
0x140023523  lea     rcx, WPP_MAIN_CB.DeviceExtension; Mutex
0x14002352a  call    cs:__imp_KeReleaseGuardedMutex
0x140023531  nop     dword ptr [rax+rax+00h]
0x140023536  mov     rcx, rbx; FdoExtension
0x140023539  call    ClassCleanupMediaChangeDetection
0x14002353e  mov     rcx, [rbx+338h]; P
0x140023545  test    rcx, rcx
0x140023548  jz      short loc_14002355F
0x14002354a  xor     edx, edx; Tag
0x14002354c  call    cs:__imp_ExFreePoolWithTag
0x140023553  nop     dword ptr [rax+rax+00h]
0x140023558  mov     [rbx+338h], r12
0x14002355f  mov     rcx, rbx; FdoExtension
0x140023562  call    ClassAcquireChildLock
0x140023567  jmp     short loc_14002358A
0x140023569  mov     rcx, [rax+8]
0x14002356d  mov     rdx, [rcx+40h]
0x140023571  mov     byte ptr [rax+200h], 1
0x140023578  mov     dword ptr [rdx+6Ch], 1
0x14002357f  mov     dl, 2; RemoveType
0x140023581  mov     rcx, [rax+8]; DeviceObject
0x140023585  call    ClassRemoveDevice
0x14002358a  xor     r8d, r8d
0x14002358d  xor     edx, edx
0x14002358f  mov     rcx, rbx; FdoExtension
0x140023592  call    ClassRemoveChild
0x140023597  test    rax, rax
0x14002359a  jnz     short loc_140023569
0x14002359c  mov     rcx, rbx; FdoExtension
0x14002359f  call    ClassReleaseChildLock
0x1400235a4  mov     rcx, rsi
0x1400235a7  call    ClasspFreeReleaseRequest
0x1400235ac  mov     rdi, [rbx+478h]
0x1400235b3  test    rdi, rdi
0x1400235b6  jz      loc_140023802
0x1400235bc  lea     rcx, AllFdosListSpinlock; SpinLock
0x1400235c3  add     rdi, 508h
0x1400235ca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400235d1  nop     dword ptr [rax+rax+00h]
0x1400235d6  mov     rdx, [rdi]
0x1400235d9  test    rdx, rdx
0x1400235dc  jz      short loc_140023601
0x1400235de  mov     rcx, [rdi+8]
0x1400235e2  test    rcx, rcx
0x1400235e5  jz      short loc_140023601
0x1400235e7  cmp     [rdx+8], rdi
0x1400235eb  jnz     loc_1400236EB
0x1400235f1  cmp     [rcx], rdi
0x1400235f4  jnz     loc_1400236EB
0x1400235fa  mov     [rcx], rdx
0x1400235fd  mov     [rdx+8], rcx
0x140023601  mov     dl, al; NewIrql
0x140023603  lea     rcx, AllFdosListSpinlock; SpinLock
0x14002360a  call    cs:__imp_KeReleaseSpinLock
0x140023611  nop     dword ptr [rax+rax+00h]
0x140023616  mov     rcx, rsi
0x140023619  mov     [rdi+8], rdi
0x14002361d  mov     [rdi], rdi
0x140023620  call    DestroyAllTransferPackets
0x140023625  mov     rcx, rbx
0x140023628  call    ClasspDeleteTimer
0x14002362d  call    ClasspUnregisterBugcheckCallback
0x140023632  mov     rcx, [rbx+478h]
0x140023639  cmp     [rcx+2A0h], r12
0x140023640  jz      loc_140023725
0x140023646  add     rcx, 2F8h; FastMutex
0x14002364d  call    cs:__imp_ExAcquireFastMutex
0x140023654  nop     dword ptr [rax+rax+00h]
0x140023659  mov     rcx, [rbx+478h]
0x140023660  mov     rcx, [rcx+2F0h]; RunRef
0x140023667  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14002366e  nop     dword ptr [rax+rax+00h]
0x140023673  mov     rax, [rbx+478h]
0x14002367a  mov     rcx, [rax+2A0h]; P
0x140023681  test    rcx, rcx
0x140023684  jz      short loc_1400236A2
0x140023686  xor     edx, edx; Tag
0x140023688  call    cs:__imp_ExFreePoolWithTag
0x14002368f  nop     dword ptr [rax+rax+00h]
0x140023694  mov     rax, [rbx+478h]
0x14002369b  mov     [rax+2A0h], r12
0x1400236a2  mov     rcx, [rbx+478h]
0x1400236a9  mov     rcx, [rcx+2F0h]; RunRefCacheAware
0x1400236b0  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400236b7  nop     dword ptr [rax+rax+00h]
0x1400236bc  mov     rax, [rbx+478h]
0x1400236c3  mov     [rax+2F0h], r12
0x1400236ca  mov     rcx, [rbx+478h]
0x1400236d1  add     rcx, 2F8h; FastMutex
0x1400236d8  call    cs:__imp_ExReleaseFastMutex
0x1400236df  nop     dword ptr [rax+rax+00h]
0x1400236e4  mov     edi, 2E0h
0x1400236e9  jmp     short loc_140023703
0x1400236eb  mov     ecx, 3
0x1400236f0  int     29h; Win8: RtlFailFast(ecx)
0x1400236f2  xor     edx, edx; Tag
0x1400236f4  mov     rcx, rax; P
0x1400236f7  call    cs:__imp_ExFreePoolWithTag
0x1400236fe  nop     dword ptr [rax+rax+00h]
0x140023703  mov     rcx, [rbx+478h]
0x14002370a  add     rcx, rdi
0x14002370d  call    SimplePopSlist
0x140023712  test    rax, rax
0x140023715  jnz     short loc_1400236F2
0x140023717  mov     rax, [rbx+478h]
0x14002371e  mov     [rax+2E0h], r12
0x140023725  mov     rax, [rbx+478h]
0x14002372c  mov     rcx, [rax+278h]; P
  ... truncated ...
```
