# ClassPnpStartDevice

- ea: `0x1400579b4`
- end: `0x14005896e`
- name: `ClassPnpStartDevice`
- size: `4026`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, _DWORD *)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14005fe50`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x14000c524`
- `0x14000f3e0`
- `0x140017c2c`
- `0x140018018`
- `0x140018424`
- `0x140018dfc`
- `0x140019a4c`
- `0x140019c40`
- `0x14001cb40`
- `0x14001f154`
- `0x14001f978`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x14001ff30`
- `0x1400200ac`
- `0x140020258`
- `0x140021c08`
- `0x1400229f8`
- `0x140024c58`
- `0x140036b68`
- `0x14003dbfc`
- `0x14003e430`
- `0x14003e470`
- `0x14003e940`
- `0x140054204`
- `0x1400561c0`
- `0x1400579b4`
- `0x14005923c`
- `0x1400597c0`
- `0x1400598f0`
- `0x1400599ac`
- `0x140059afc`
- `0x14005b8b8`
- `0x14005c3d8`
- `0x14005e0a0`
- `0x14005e2e0`
- `0x14005f690`
- `0x14005f800`
- `0x14005fda0`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x140058692`
- `ntoskrnl!KeInitializeMutex` at `0x1400586a7`
- `ntoskrnl!KeInitializeMutex` at `0x140058692`
- `ntoskrnl!KeInitializeMutex` at `0x1400586a7`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140058747`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x140058747`
- `ntoskrnl!ExAllocatePool2` at `0x140057a65`
- `ntoskrnl!ExAllocatePool2` at `0x140057aee`
- `ntoskrnl!ExAllocatePool2` at `0x140057bae`
- `ntoskrnl!ExAllocatePool2` at `0x1400581a8`
- `ntoskrnl!ExAllocatePool2` at `0x140057a65`
- `ntoskrnl!ExAllocatePool2` at `0x140057aee`
- `ntoskrnl!ExAllocatePool2` at `0x140057bae`
- `ntoskrnl!ExAllocatePool2` at `0x1400581a8`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140057cbd`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140057cbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058293`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058293`
- `ntoskrnl!KeInitializeDpc` at `0x140057c90`
- `ntoskrnl!KeInitializeDpc` at `0x140057c90`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140058181`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140058181`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140057dc5`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140057dc5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140057c1a`
- `ntoskrnl!KeInitializeSpinLock` at `0x140057caa`
- `ntoskrnl!KeInitializeSpinLock` at `0x140057cfc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140057c1a`
- `ntoskrnl!KeInitializeSpinLock` at `0x140057caa`
- `ntoskrnl!KeInitializeSpinLock` at `0x140057cfc`
- `ntoskrnl!KeInitializeTimer` at `0x140057c6c`
- `ntoskrnl!KeInitializeTimer` at `0x140057c6c`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140057a1e`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140057a1e`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400587d1`
- `ntoskrnl!IoWMIRegistrationControl` at `0x1400587d1`
- `ntoskrnl!InitializeSListHead` at `0x1400581eb`
- `ntoskrnl!InitializeSListHead` at `0x1400581eb`

## string_xrefs

- `0x1400584f4`: `AccessAlignmentQueryNotSupported`

## pseudocode

```c
__int64 __fastcall ClassPnpStartDevice(PDEVICE_OBJECT DeviceObject, _DWORD *a2)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // rdi
  struct _DRIVER_OBJECT *DriverObject; // rcx
  char v6; // r13
  _QWORD *DriverObjectExtension; // rax
  bool v8; // zf
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rcx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  int ReleaseQueueIrp; // ebx
  _ADDITIONAL_FDO_DATA *AdditionalFdoData; // rax
  _CLASS_FUNCTION_SUPPORT_INFO *FunctionSupportInfo; // rcx
  KSPIN_LOCK *p_SyncLock; // rcx
  _CLASS_PRIVATE_FDO_DATA *v16; // rbx
  _LIST_ENTRY *p_DeferredClientIrpList; // rax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  struct _DEVICE_OBJECT *LowerDeviceObject; // rcx
  _STORAGE_MINIPORT_DESCRIPTOR **p_MiniportDescriptor; // rbx
  NTSTATUS v22; // eax
  _STORAGE_MINIPORT_DESCRIPTOR *v23; // rdx
  struct _DEVICE_OBJECT *v24; // rcx
  struct _DEVICE_OBJECT *v25; // rcx
  _STORAGE_DEVICE_DESCRIPTOR **p_DeviceDescriptor; // r12
  _STORAGE_MINIPORT_DESCRIPTOR *MiniportDescriptor; // rax
  _STORAGE_MINIPORT_DESCRIPTOR *v28; // rax
  ULONG MaximumProcessorCount; // eax
  _CLASS_PRIVATE_FDO_DATA *v30; // rbx
  ULONG v31; // r12d
  ULONG i; // ebx
  struct _DEVICE_OBJECT *v33; // rcx
  NTSTATUS v34; // eax
  _BYTE *v35; // r8
  _STORAGE_MINIPORT_DESCRIPTOR *v36; // rax
  _STORAGE_PORT_CODE_SET Portdriver; // ecx
  __int64 v38; // rcx
  _CLASS_FUNCTION_SUPPORT_INFO *v39; // rcx
  __int64 v40; // rdx
  PVOID v41; // rax
  __int64 v42; // rdx
  _CLASS_PRIVATE_FDO_DATA *v43; // rcx
  _CLASS_FUNCTION_SUPPORT_INFO *v44; // rax
  _FAILURE_PREDICTION_INFO *FailurePredictionInfo; // rax
  _QWORD *v46; // r12
  _BOOL8 v47; // rdx
  unsigned int DeviceType; // ecx
  _BOOL8 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // r8
  int v52; // r8d
  int v53; // r9d
  ULONG *p_DeviceGuidFlags; // rcx
  _STORAGE_MINIPORT_DESCRIPTOR *v55; // rax
  ULONG v56; // ecx
  _STORAGE_PROPERTY_ID PropertyId; // [rsp+40h] [rbp-C0h] BYREF
  char v59[4]; // [rsp+44h] [rbp-BCh] BYREF
  ULONG v60; // [rsp+48h] [rbp-B8h] BYREF
  ULONG v61; // [rsp+4Ch] [rbp-B4h] BYREF
  PVOID Descriptor; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v63; // [rsp+58h] [rbp-A8h]
  ULONG ParameterValue; // [rsp+60h] [rbp-A0h] BYREF
  ULONG v65; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG v66; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+70h] [rbp-90h] BYREF
  _OWORD Buffer[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h]
  __int64 v70[12]; // [rsp+B0h] [rbp-50h] BYREF

  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)DeviceObject->DeviceExtension;
  DriverObject = DeviceObject->DriverObject;
  v6 = *((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1;
  v59[0] = 0;
  Descriptor = 0;
  memset(Buffer, 0, sizeof(Buffer));
  v69 = 0;
  IoStatus = 0;
  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, ClassInitialize);
  v8 = (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 2) == 0;
  v63 = DriverObjectExtension;
  if ( v8 )
  {
    if ( v6 )
    {
      PrivateFdoData = DeviceExtension->PrivateFdoData;
      if ( PrivateFdoData )
        memset(PrivateFdoData, 0, sizeof(_CLASS_PRIVATE_FDO_DATA));
      else
        DeviceExtension->PrivateFdoData = (_CLASS_PRIVATE_FDO_DATA *)ExAllocatePool2(72, 3968, 1129341779);
      if ( !DeviceExtension->PrivateFdoData )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_12;
        }
        v11 = 43;
        goto LABEL_11;
      }
      AdditionalFdoData = DeviceExtension->AdditionalFdoData;
      if ( AdditionalFdoData )
      {
        *(_OWORD *)&AdditionalFdoData->DeviceGuidFlags = 0;
        *(_DWORD *)&AdditionalFdoData->DeviceGuid.Data4[4] = 0;
      }
      else
      {
        DeviceExtension->AdditionalFdoData = (_ADDITIONAL_FDO_DATA *)ExAllocatePool2(64, 20, 1145135955);
      }
      if ( !DeviceExtension->AdditionalFdoData )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_12;
        }
        v11 = 44;
        goto LABEL_11;
      }
      ReleaseQueueIrp = ClasspInitializeTimer(DeviceExtension);
      if ( ReleaseQueueIrp < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            45,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)ReleaseQueueIrp);
        }
        goto LABEL_26;
      }
      FunctionSupportInfo = DeviceExtension->FunctionSupportInfo;
      if ( FunctionSupportInfo )
        memset(FunctionSupportInfo, 0, sizeof(_CLASS_FUNCTION_SUPPORT_INFO));
      else
        DeviceExtension->FunctionSupportInfo = (_CLASS_FUNCTION_SUPPORT_INFO *)ExAllocatePool2(64, 184, 859988819);
      p_SyncLock = &DeviceExtension->FunctionSupportInfo->SyncLock;
      if ( !p_SyncLock )
      {
        ClasspDeleteTimer(DeviceExtension);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_12;
        }
        v11 = 46;
LABEL_11:
        WPP_SF_(v10->AttachedDevice, v11, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
LABEL_12:
        *a2 = 5;
        return (unsigned int)-1073741670;
      }
      KeInitializeSpinLock(p_SyncLock);
      DeviceExtension->FunctionSupportInfo->BlockLimitsData.CommandStatus = -1;
      DeviceExtension->FunctionSupportInfo->DeviceCharacteristicsData.CommandStatus = -1;
      DeviceExtension->FunctionSupportInfo->LBProvisioningData.CommandStatus = -1;
      DeviceExtension->FunctionSupportInfo->ReadCapacity16Data.CommandStatus = -1;
      DeviceExtension->FunctionSupportInfo->BlockDeviceRODLimitsData.CommandStatus = -1;
      KeInitializeTimer(&DeviceExtension->PrivateFdoData->Retry.Timer);
      KeInitializeDpc(&DeviceExtension->PrivateFdoData->Retry.Dpc, ClasspRetryRequestDpc, DeviceObject);
      KeInitializeSpinLock(&DeviceExtension->PrivateFdoData->Retry.Lock);
      v16 = DeviceExtension->PrivateFdoData;
      v16->Retry.Granularity = KeQueryTimeIncrement();
      DeviceExtension->CommonExtension.Reserved4 = 541544520;
      p_DeferredClientIrpList = &DeviceExtension->PrivateFdoData->DeferredClientIrpList;
      p_DeferredClientIrpList->Blink = p_DeferredClientIrpList;
      p_DeferredClientIrpList->Flink = p_DeferredClientIrpList;
      KeInitializeSpinLock(&DeviceExtension->PrivateFdoData->SpinLock);
      DeviceExtension->PrivateFdoData->InterpretSenseInfo = (_CLASS_INTERPRET_SENSE_INFO2 *)v63[111];
      DeviceExtension->PrivateFdoData->MaxNumberOfIoRetries = MaxNumberOfIoRetries;
      ReleaseQueueIrp = InitializeStorageRequestBlock((__int64)&DeviceExtension->PrivateFdoData->ReleaseQueueSrb);
      if ( ReleaseQueueIrp < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            47,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)ReleaseQueueIrp);
        }
        return (unsigned int)ReleaseQueueIrp;
      }
      ClasspRegisterBugcheckCallback();
      ExInterlockedInsertTailList(
        &AllFdosList,
        &DeviceExtension->PrivateFdoData->AllFdosListEntry,
        &AllFdosListSpinlock);
      ReleaseQueueIrp = ClasspAllocateReleaseQueueIrp(DeviceExtension);
      if ( ReleaseQueueIrp < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_26;
        }
        v19 = 48;
LABEL_45:
        WPP_SF_d(
          v18->AttachedDevice,
          v19,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          (unsigned int)ReleaseQueueIrp);
LABEL_26:
        *a2 = 5;
        return (unsigned int)ReleaseQueueIrp;
      }
      ReleaseQueueIrp = ClasspAllocatePowerProcessIrp(DeviceExtension);
      if ( ReleaseQueueIrp < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_26;
        }
        v19 = 49;
        goto LABEL_45;
      }
      if ( DeviceObject->DeviceType == 7 && (DeviceObject->Characteristics & 4) == 0 )
      {
        LowerDeviceObject = DeviceExtension->CommonExtension.LowerDeviceObject;
        p_MiniportDescriptor = &DeviceExtension->MiniportDescriptor;
        PropertyId = StorageMiniportProperty;
        v22 = ClassGetDescriptor(LowerDeviceObject, &PropertyId, (PVOID *)&DeviceExtension->MiniportDescriptor);
        if ( v22 >= 0
          && (v23 = *p_MiniportDescriptor, (*p_MiniportDescriptor)->Size >= 8)
          && ((v23->Portdriver - 1) & 0xFFFFFFFB) != 0 )
        {
          v23->IoTimeoutValue = 0;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            50,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)v22);
        }
      }
      v24 = DeviceExtension->CommonExtension.LowerDeviceObject;
      PropertyId = StorageAdapterProperty;
      ReleaseQueueIrp = ClassGetDescriptor(v24, &PropertyId, (PVOID *)&DeviceExtension->AdapterDescriptor);
      if ( ReleaseQueueIrp < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            51,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)ReleaseQueueIrp);
        }
        *a2 = 6;
        return (unsigned int)ReleaseQueueIrp;
      }
      v25 = DeviceExtension->CommonExtension.LowerDeviceObject;
      PropertyId = StorageDeviceProperty;
      p_DeviceDescriptor = &DeviceExtension->DeviceDescriptor;
      ReleaseQueueIrp = ClassGetDescriptor(v25, &PropertyId, (PVOID *)&DeviceExtension->DeviceDescriptor);
      if ( ReleaseQueueIrp < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            52,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)ReleaseQueueIrp);
        }
        *a2 = 7;
        return (unsigned int)ReleaseQueueIrp;
      }
      DeviceExtension->FunctionSupportInfo->UseModeSense10 = (*p_DeviceDescriptor)->BusType == BusTypeUfs;
      if ( (*p_DeviceDescriptor)->BusType == BusTypeSpaces )
      {
        DeviceExtension->DeviceFlags |= 0x40u;
        DeviceExtension->DeviceFlags |= 0x80u;
      }
      MiniportDescriptor = DeviceExtension->MiniportDescriptor;
      if ( MiniportDescriptor
        && MiniportDescriptor->Size >= 0x18
        && (MiniportDescriptor->Flags.AsUCHAR & 2) != 0
        && (*(_DWORD *)&DeviceExtension->FunctionSupportInfo->ValidInquiryPages & 0xF8000000) != 0xA0000000
        && (unsigned __int8)ClasspScanForForwardedIo(DeviceExtension) )
      {
        DeviceExtension->DeviceFlags |= 0x40u;
      }
      ClasspScanForSpecialInRegistry((__int64)DeviceExtension);
      ClassScanForSpecial(DeviceExtension, ClassBadItems, (PCLASS_SCAN_FOR_SPECIAL_HANDLER)ClasspScanForClassHacks);
      PropertyId = StorageAdapterRpmbProperty;
      ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"RestorePerfAtCount", (PULONG)&PropertyId);
      if ( (unsigned int)PropertyId >= StorageAdapterRpmbProperty )
        DeviceExtension->PrivateFdoData->Perf.ReEnableThreshhold = PropertyId;
      if ( DeviceExtension->DeviceObject->DeviceType != 7
        || (v28 = DeviceExtension->MiniportDescriptor) != 0 && v28->Size >= 0x18 && (v28->Flags.AsUCHAR & 1) != 0 )
      {
        DeviceExtension->PrivateFdoData->HackFlags |= 4u;
      }
      if ( (int)ClasspIsPortable(DeviceExtension, v59) >= 0 && v59[0] == 1 )
        DeviceObject->Characteristics |= 0x40000u;
      ReleaseQueueIrp = ClasspInitializeHotplugInfo(DeviceExtension);
      if ( ReleaseQueueIrp < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            53,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)ReleaseQueueIrp);
        }
        *a2 = 8;
        return (unsigned int)ReleaseQueueIrp;
      }
      ReleaseQueueIrp = InitializeTransferPackets(DeviceObject);
      if ( ReleaseQueueIrp < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            54,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            (unsigned int)ReleaseQueueIrp);
        }
        *a2 = 9;
        return (unsigned int)ReleaseQueueIrp;
      }
      MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
      v30 = DeviceExtension->PrivateFdoData;
      v31 = MaximumProcessorCount;
      v30->PerProcessorData = (_PP_FDO_DATA *)ExAllocatePool2(
                                                72,
                                                (unsigned __int64)MaximumProcessorCount << 6,
                                                1129341779);
      if ( !DeviceExtension->PrivateFdoData->PerProcessorData )
        goto LABEL_12;
      for ( i = 0; i < v31; ++i )
        InitializeSListHead(&DeviceExtension->PrivateFdoData->PerProcessorData[(unsigned __int64)i].FreePackets);
      if ( DeviceExtension->DeviceObject->DeviceType == 7 )
        ClasspCreateDeviceGuid(DeviceExtension);
      v33 = DeviceExtension->CommonExtension.LowerDeviceObject;
      PropertyId = StorageDevicePowerProperty;
      v34 = ClassGetDescriptor(v33, &PropertyId, &Descriptor);
      if ( v34 >= 0 && (v35 = Descriptor) != 0 )
      {
        DeviceExtension->FunctionSupportInfo->AsynchronousNotificationSupported = *((_BYTE *)Descriptor + 9);
        *(_DWORD *)&DeviceExtension->FunctionSupportInfo->IdlePower ^= ((unsigned __int8)*(_DWORD *)&DeviceExtension->FunctionSupportInfo->IdlePower
                                                                      ^ v35[12])
                                                                     & 1;
        *(_DWORD *)&DeviceExtension->FunctionSupportInfo->IdlePower ^= ((unsigned __int8)*(_DWORD *)&DeviceExtension->FunctionSupportInfo->IdlePower
                                                                      ^ (unsigned __int8)(16 * v35[13]))
                                                                     & 0x10;
        ExFreePoolWithTag(v35, 0);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          55,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          (unsigned int)v34);
      }
      if ( (*(_DWORD *)&DeviceExtension->FunctionSupportInfo->IdlePower & 4) == 0 )
      {
        v36 = DeviceExtension->MiniportDescriptor;
        if ( v36 )
        {
          if ( v36->Size >= 0xC )
          {
            Portdriver = v36->Portdriver;
            if ( ((Portdriver - 1) & 0xFFFFFFF9) == 0 && Portdriver != StoragePortCodeSetSpaceport )
            {
              PropertyId = StorageDeviceProperty;
              ClassGetDeviceParameter(
                DeviceExtension,
                (PWSTR)L"Classpnp",
                (PWSTR)L"DisableIdlePowerManagement",
                (PULONG)&PropertyId);
              if ( PropertyId == StorageDeviceProperty )
                ClasspEnableIdlePower(DeviceObject);
            }
          }
        }
      }
    }
    ReleaseQueueIrp = (*(__int64 (__fastcall **)(PDEVICE_OBJECT))((char *)v63
                                                                + (-(__int64)(v6 != 0) & 0xFFFFFFFFFFFFFF58uLL)
                                                                + 248))(DeviceObject);
    if ( ReleaseQueueIrp < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          56,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          (unsigned int)ReleaseQueueIrp);
      }
      *a2 = 10;
      return (unsigned int)ReleaseQueueIrp;
    }
    if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
    {
      DeviceExtension->PrivateFdoData->Perf.OriginalSrbFlags = DeviceExtension->SrbFlags;
      if ( DeviceObject->DeviceType == 7 && (DeviceObject->Characteristics & 4) == 0 )
      {
        Descriptor = 0;
        PropertyId = StorageDeviceProperty;
        v65 = 0;
        ParameterValue = 0;
        v66 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            57,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            DeviceObject);
        }
        ClasspInitializeIdleTimer(DeviceExtension);
        if ( (unsigned __int8)ClasspIsObsoletePortDriver(DeviceExtension) )
        {
          DeviceExtension->FunctionSupportInfo->LBProvisioningData.CommandStatus = -1073741823;
          DeviceExtension->FunctionSupportInfo->BlockLimitsData.CommandStatus = -1073741823;
          DeviceExtension->FunctionSupportInfo->BlockDeviceRODLimitsData.CommandStatus = -1073741823;
        }
        else
        {
          ClasspGetInquiryVpdSupportInfo(v38);
          ClasspGetBlockDeviceVpdInfo(DeviceExtension);
          if ( (*(_DWORD *)&DeviceExtension->FunctionSupportInfo->ValidInquiryPages & 8) != 0 )
            ClassDetermineTokenOperationCommandSupport(DeviceObject);
          if ( (*(_DWORD *)&DeviceExtension->PrivateFdoData->ValidInquiryPagesInternal & 1) != 0 )
            ClasspGetVirtualDevicePropertiesData((__int64)DeviceObject);
          ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"QERROverrideMode", &ParameterValue);
          if ( ParameterValue == 1
            || !ParameterValue
            && ((v39 = DeviceExtension->FunctionSupportInfo, (*((_BYTE *)&v39->LBProvisioningData + 6) & 7) == 2)
             && *((char *)&v39->LBProvisioningData + 5) < 0
             || (int)ClasspValidateOffloadSupported(DeviceObject, 0) >= 0) )
          {
            ClasspZeroQERR(DeviceObject);
          }
        }
        ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"AccessAlignmentQueryNotSupported", &v65);
        if ( v65 )
          DeviceExtension->FunctionSupportInfo->RegAccessAlignmentQueryNotSupported = 1;
        ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"LegacyErrorHandling", &v66);
        if ( v66 )
        {
          DeviceExtension->PrivateFdoData->MaxNumberOfIoRetries = 8;
          DeviceExtension->PrivateFdoData->LegacyErrorHandling = 1;
        }
        ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"IoThresholdTime", (PULONG)&Descriptor);
        v41 = Descriptor;
        if ( Descriptor
          || (int)ClasspGetDegradedIoThresholdTime(DeviceObject, v40, &Descriptor) >= 0 && (v41 = Descriptor) != 0 )
        {
          DeviceExtension->PrivateFdoData->DegradedIoThresholdTime.QuadPart = 10000LL * (_QWORD)v41;
        }
        PropertyId = -1;
        ClassGetDeviceParameter(
          DeviceExtension,
          (PWSTR)L"Classpnp",
          (PWSTR)L"QosTimeoutRetryCount",
          (PULONG)&PropertyId);
        v43 = DeviceExtension->PrivateFdoData;
        if ( PropertyId == -1 )
        {
          v43->QosMaxNumberOfTimeoutRetries = v43->MaxNumberOfIoRetries;
        }
        else
        {
          v43->QosMaxNumberOfTimeoutRetries = PropertyId;
          _InterlockedOr((volatile signed __int32 *)&DeviceExtension->PrivateFdoData->FdoDataFlags, 0x10u);
        }
        ClasspGetCopyOffloadMaxDuration(
          DeviceObject,
          v42,
          &DeviceExtension->PrivateFdoData->CopyOffloadMaxTargetDuration);
        v60 = 0;
        ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"IgnoreDeviceTransferLength", &v60);
        if ( v60 )
          _InterlockedOr((volatile signed __int32 *)&DeviceExtension->PrivateFdoData->FdoDataFlags, 0x40u);
        v61 = 0;
        ClassGetDeviceParameter(DeviceExtension, (PWSTR)L"Classpnp", (PWSTR)L"ForceBypassIo", &v61);
        if ( v61 )
          _InterlockedOr((volatile signed __int32 *)&DeviceExtension->PrivateFdoData->FdoDataFlags, 0x80u);
        KeInitializeMutex(&DeviceExtension->PrivateFdoData->CommandDurationLimitProperty.Mutex, 0);
        KeInitializeMutex(&DeviceExtension->PrivateFdoData->SmrReadCapacityMutex, 0);
      }
      if ( (*(_DWORD *)&DeviceExtension->FunctionSupportInfo->ValidInquiryPages & 0xF8000000) == 0xA0000000 )
        ClassDeviceGetZoneInformation((__int64)DeviceExtension);
    }
    DriverObjectExtension = v63;
  }
  *((_BYTE *)&DeviceExtension->CommonExtension + 104) |= 2u;
  if ( v6 )
  {
    if ( DriverObjectExtension[50]
      || DeviceExtension->MediaChangeDetectionInfo
      && (v44 = DeviceExtension->FunctionSupportInfo) != 0
      && !v44->AsynchronousNotificationSupported
      || (FailurePredictionInfo = DeviceExtension->FailurePredictionInfo) != 0 && FailurePredictionInfo->Method )
    {
      ClasspEnableTimer(DeviceExtension);
      if ( !WPP_MAIN_CB.Queue.Wcb.DeviceObject )
        PoRegisterPowerSettingCallback(
          DeviceObject,
          &GUID_CONSOLE_DISPLAY_STATE,
          ClasspPowerSettingCallback,
          0,
          &WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    }
  }
  v46 = v63;
  ReleaseQueueIrp = (*(__int64 (__fastcall **)(PDEVICE_OBJECT))((char *)v63
                                                              + (-(__int64)(v6 != 0) & 0xFFFFFFFFFFFFFF58uLL)
                                                              + 256))(DeviceObject);
  if ( ReleaseQueueIrp < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        59,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        (unsigned int)ReleaseQueueIrp);
    }
    *a2 = 11;
    ClasspDisableTimer(DeviceExtension);
  }
  else
  {
    LOBYTE(v47) = 1;
    DeviceExtension->CommonExtension.CurrentState = 0;
    if ( v6 )
      v47 = v46[46] == 0;
    DeviceType = DeviceObject->DeviceType;
    v49 = 0;
    if ( DeviceType == 2 )
      v49 = v47;
    if ( DeviceType == 7 && (DeviceObject->Characteristics & 4) != 0 || v49 )
      ClasspRegisterMountedDeviceInterface(DeviceObject, v47, v49);
    if ( (*((_BYTE *)&DeviceExtension->CommonExtension + 104) & 1) != 0 )
      IoWMIRegistrationControl(DeviceObject, 1u);
  }
  if ( v6 )
  {
    *(_QWORD *)&Buffer[0] = 0x2800000028LL;
    *(_GUID *)((char *)Buffer + 8) = DeviceExtension->AdditionalFdoData->DeviceGuid;
    ClassSendDeviceIoControlSynchronous(
      0x2D280Cu,
      DeviceExtension->CommonExtension.LowerDeviceObject,
      Buffer,
      0x28u,
      0x28u,
      0,
      &IoStatus);
    if ( IoStatus.Status < 0 )
    {
      memset(Buffer, 0, sizeof(Buffer));
      v69 = 0;
    }
    if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v50, 0x400000000000LL, v51) )
    {
      p_DeviceGuidFlags = &DeviceExtension->AdditionalFdoData->DeviceGuidFlags;
      v70[5] = 16;
      v70[4] = (__int64)(p_DeviceGuidFlags + 1);
      v61 = *p_DeviceGuidFlags;
      v70[6] = (__int64)&v61;
      v55 = DeviceExtension->MiniportDescriptor;
      v70[7] = 4;
      if ( v55 && v55->Size >= 0xC )
        v56 = v55->Portdriver;
      else
        v56 = 0;
      v60 = v56;
      v70[8] = (__int64)&v60;
      v70[9] = 4;
      v70[10] = (__int64)&Buffer[1] + 8;
      v70[11] = 16;
      tlgWriteTransfer_EtwWriteTransfer(v56, (int)&byte_140048611, v52, v53, 6u, (__int64)v70);
    }
    ClassPnpLogDeviceDescriptor((__int64)DeviceObject);
    ClassPnpLogDeviceVPDPages(DeviceObject);
  }
  return (unsigned int)ReleaseQueueIrp;
}

```

## disassembly

```asm
0x1400579b4  mov     [rsp-8+arg_10], rbx
0x1400579b9  push    rbp
0x1400579ba  push    rsi
0x1400579bb  push    rdi
0x1400579bc  push    r12
0x1400579be  push    r13
0x1400579c0  push    r14
0x1400579c2  push    r15
0x1400579c4  lea     rbp, [rsp-20h]
0x1400579c9  sub     rsp, 120h
0x1400579d0  mov     rax, cs:__security_cookie
0x1400579d7  xor     rax, rsp
0x1400579da  mov     [rbp+50h+var_40], rax
0x1400579de  mov     rdi, [rcx+40h]
0x1400579e2  xorps   xmm0, xmm0
0x1400579e5  mov     r15, rdx
0x1400579e8  mov     r14, rcx
0x1400579eb  mov     rcx, [rcx+8]; DriverObject
0x1400579ef  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x1400579f6  xor     r12d, r12d
0x1400579f9  xor     eax, eax
0x1400579fb  mov     r13b, [rdi+68h]
0x1400579ff  and     r13b, 1
0x140057a03  mov     [rsp+150h+var_10C], r12b
0x140057a08  mov     [rsp+150h+Descriptor], r12
0x140057a0d  movups  [rbp+50h+Buffer], xmm0
0x140057a11  mov     [rbp+50h+var_B0], rax
0x140057a15  movups  [rbp+50h+var_C0], xmm0
0x140057a19  movups  xmmword ptr [rsp+150h+var_E0], xmm0
0x140057a1e  call    cs:__imp_IoGetDriverObjectExtension
0x140057a25  nop     dword ptr [rax+rax+00h]
0x140057a2a  test    byte ptr [rdi+68h], 2
0x140057a2e  lea     rsi, WPP_GLOBAL_Control
0x140057a35  mov     [rsp+150h+var_F8], rax
0x140057a3a  jnz     loc_1400586D8
0x140057a40  test    r13b, r13b
0x140057a43  jz      loc_140058334
0x140057a49  mov     rcx, [rdi+478h]; void *
0x140057a50  test    rcx, rcx
0x140057a53  jnz     short loc_140057A7A
0x140057a55  mov     edx, 0F80h
0x140057a5a  lea     ecx, [r12+48h]
0x140057a5f  mov     r8d, 43506353h
0x140057a65  call    cs:__imp_ExAllocatePool2
0x140057a6c  nop     dword ptr [rax+rax+00h]
0x140057a71  mov     [rdi+478h], rax
0x140057a78  jmp     short loc_140057A87
0x140057a7a  xor     edx, edx; Val
0x140057a7c  mov     r8d, 0F80h; Size
0x140057a82  call    memset
0x140057a87  cmp     [rdi+478h], r12
0x140057a8e  jnz     short loc_140057AD6
0x140057a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140057a97  lea     rsi, WPP_GLOBAL_Control
0x140057a9e  cmp     rcx, rsi
0x140057aa1  jz      short loc_140057AC5
0x140057aa3  mov     eax, [rcx+2Ch]
0x140057aa6  test    al, 2
0x140057aa8  jz      short loc_140057AC5
0x140057aaa  cmp     byte ptr [rcx+29h], 2
0x140057aae  jb      short loc_140057AC5
0x140057ab0  mov     edx, 2Bh ; '+'
0x140057ab5  mov     rcx, [rcx+18h]
0x140057ab9  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140057ac0  call    WPP_SF_
0x140057ac5  mov     dword ptr [r15], 5
0x140057acc  mov     ebx, 0C000009Ah
0x140057ad1  jmp     loc_140058944
0x140057ad6  mov     rax, [rdi+490h]
0x140057add  test    rax, rax
0x140057ae0  jnz     short loc_140057B03
0x140057ae2  lea     edx, [rax+14h]
0x140057ae5  mov     r8d, 44416353h
0x140057aeb  lea     ecx, [rax+40h]
0x140057aee  call    cs:__imp_ExAllocatePool2
0x140057af5  nop     dword ptr [rax+rax+00h]
0x140057afa  mov     [rdi+490h], rax
0x140057b01  jmp     short loc_140057B0E
0x140057b03  xorps   xmm0, xmm0
0x140057b06  xor     ecx, ecx
0x140057b08  movups  xmmword ptr [rax], xmm0
0x140057b0b  mov     [rax+10h], ecx
0x140057b0e  cmp     [rdi+490h], r12
0x140057b15  jnz     short loc_140057B41
0x140057b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140057b1e  lea     rsi, WPP_GLOBAL_Control
0x140057b25  cmp     rcx, rsi
0x140057b28  jz      short loc_140057AC5
0x140057b2a  mov     eax, [rcx+2Ch]
0x140057b2d  test    al, 2
0x140057b2f  jz      short loc_140057AC5
0x140057b31  cmp     byte ptr [rcx+29h], 2
0x140057b35  jb      short loc_140057AC5
0x140057b37  mov     edx, 2Ch ; ','
0x140057b3c  jmp     loc_140057AB5
0x140057b41  mov     rcx, rdi
0x140057b44  call    ClasspInitializeTimer
0x140057b49  mov     ebx, eax
0x140057b4b  test    eax, eax
0x140057b4d  jns     short loc_140057B94
0x140057b4f  mov     rax, cs:WPP_GLOBAL_Control
0x140057b56  lea     rsi, WPP_GLOBAL_Control
0x140057b5d  cmp     rax, rsi
0x140057b60  jz      short loc_140057B88
0x140057b62  mov     ecx, [rax+2Ch]
0x140057b65  test    cl, 2
0x140057b68  jz      short loc_140057B88
0x140057b6a  cmp     byte ptr [rax+29h], 2
0x140057b6e  jb      short loc_140057B88
0x140057b70  mov     rcx, [rax+18h]
0x140057b74  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140057b7b  mov     edx, 2Dh ; '-'
0x140057b80  mov     r9d, ebx
0x140057b83  call    WPP_SF_d
0x140057b88  mov     dword ptr [r15], 5
0x140057b8f  jmp     loc_140058944
0x140057b94  mov     rcx, [rdi+480h]; void *
0x140057b9b  test    rcx, rcx
0x140057b9e  jnz     short loc_140057BC3
0x140057ba0  mov     edx, 0B8h
0x140057ba5  mov     r8d, 33426353h
0x140057bab  lea     ecx, [rdx-78h]
0x140057bae  call    cs:__imp_ExAllocatePool2
0x140057bb5  nop     dword ptr [rax+rax+00h]
0x140057bba  mov     [rdi+480h], rax
0x140057bc1  jmp     short loc_140057BD0
0x140057bc3  xor     edx, edx; Val
0x140057bc5  mov     r8d, 0B8h; Size
0x140057bcb  call    memset
0x140057bd0  mov     rcx, [rdi+480h]; SpinLock
0x140057bd7  test    rcx, rcx
0x140057bda  jnz     short loc_140057C1A
0x140057bdc  mov     rcx, rdi
0x140057bdf  call    ClasspDeleteTimer
0x140057be4  mov     rcx, cs:WPP_GLOBAL_Control
0x140057beb  lea     rsi, WPP_GLOBAL_Control
0x140057bf2  cmp     rcx, rsi
0x140057bf5  jz      loc_140057AC5
0x140057bfb  mov     eax, [rcx+2Ch]
0x140057bfe  test    al, 2
0x140057c00  jz      loc_140057AC5
0x140057c06  cmp     byte ptr [rcx+29h], 2
0x140057c0a  jb      loc_140057AC5
0x140057c10  mov     edx, 2Eh ; '.'
0x140057c15  jmp     loc_140057AB5
0x140057c1a  call    cs:__imp_KeInitializeSpinLock
0x140057c21  nop     dword ptr [rax+rax+00h]
0x140057c26  mov     rax, [rdi+480h]
0x140057c2d  or      ecx, 0FFFFFFFFh
0x140057c30  mov     [rax+28h], ecx
0x140057c33  mov     rax, [rdi+480h]
0x140057c3a  mov     [rax+48h], ecx
0x140057c3d  mov     rax, [rdi+480h]
0x140057c44  mov     [rax+58h], ecx
0x140057c47  mov     rax, [rdi+480h]
0x140057c4e  mov     [rax+64h], ecx
0x140057c51  mov     rax, [rdi+480h]
0x140057c58  mov     [rax+80h], ecx
0x140057c5e  mov     rcx, [rdi+478h]
0x140057c65  add     rcx, 5A0h; Timer
0x140057c6c  call    cs:__imp_KeInitializeTimer
0x140057c73  nop     dword ptr [rax+rax+00h]
0x140057c78  mov     rcx, [rdi+478h]
0x140057c7f  lea     rdx, ClasspRetryRequestDpc; DeferredRoutine
0x140057c86  add     rcx, 560h; Dpc
0x140057c8d  mov     r8, r14; DeferredContext
0x140057c90  call    cs:__imp_KeInitializeDpc
0x140057c97  nop     dword ptr [rax+rax+00h]
0x140057c9c  mov     rcx, [rdi+478h]
0x140057ca3  add     rcx, 558h; SpinLock
0x140057caa  call    cs:__imp_KeInitializeSpinLock
0x140057cb1  nop     dword ptr [rax+rax+00h]
0x140057cb6  mov     rbx, [rdi+478h]
0x140057cbd  call    cs:__imp_KeQueryTimeIncrement
0x140057cc4  nop     dword ptr [rax+rax+00h]
0x140057cc9  mov     [rbx+550h], eax
0x140057ccf  mov     qword ptr [rdi+1D0h], 20475048h
0x140057cda  mov     rax, [rdi+478h]
0x140057ce1  add     rax, 608h
0x140057ce7  mov     [rax+8], rax
0x140057ceb  mov     [rax], rax
0x140057cee  mov     rcx, [rdi+478h]
0x140057cf5  add     rcx, 618h; SpinLock
0x140057cfc  call    cs:__imp_KeInitializeSpinLock
0x140057d03  nop     dword ptr [rax+rax+00h]
0x140057d08  mov     rcx, [rdi+478h]
0x140057d0f  xor     r9d, r9d
0x140057d12  mov     rax, [rsp+150h+var_F8]
0x140057d17  mov     r8d, 90h
0x140057d1d  movzx   edx, r12w
0x140057d21  mov     rax, [rax+378h]
0x140057d28  mov     [rcx+0F30h], rax
0x140057d2f  mov     cl, byte ptr cs:MaxNumberOfIoRetries
0x140057d35  mov     rax, [rdi+478h]
0x140057d3c  mov     [rax+294h], cl
0x140057d42  mov     rcx, [rdi+478h]
0x140057d49  add     rcx, 468h
0x140057d50  call    InitializeStorageRequestBlock
0x140057d55  mov     ebx, eax
0x140057d57  test    eax, eax
0x140057d59  jns     short loc_140057DA4
0x140057d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140057d62  lea     rsi, WPP_GLOBAL_Control
0x140057d69  cmp     rcx, rsi
0x140057d6c  jz      loc_140058944
0x140057d72  mov     eax, [rcx+2Ch]
0x140057d75  test    al, 2
0x140057d77  jz      loc_140058944
0x140057d7d  cmp     byte ptr [rcx+29h], 2
0x140057d81  jb      loc_140058944
0x140057d87  mov     rcx, [rcx+18h]
0x140057d8b  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140057d92  mov     edx, 2Fh ; '/'
0x140057d97  mov     r9d, ebx
0x140057d9a  call    WPP_SF_d
0x140057d9f  jmp     loc_140058944
0x140057da4  call    ClasspRegisterBugcheckCallback
0x140057da9  mov     rdx, [rdi+478h]
0x140057db0  lea     r8, AllFdosListSpinlock; Lock
0x140057db7  add     rdx, 508h; ListEntry
0x140057dbe  lea     rcx, AllFdosList; ListHead
0x140057dc5  call    cs:__imp_ExInterlockedInsertTailList
0x140057dcc  nop     dword ptr [rax+rax+00h]
0x140057dd1  mov     rcx, rdi
0x140057dd4  call    ClasspAllocateReleaseQueueIrp
0x140057dd9  mov     ebx, eax
0x140057ddb  test    eax, eax
0x140057ddd  jns     short loc_140057E28
0x140057ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140057de6  lea     rsi, WPP_GLOBAL_Control
0x140057ded  cmp     rcx, rsi
0x140057df0  jz      loc_140057B88
0x140057df6  mov     eax, [rcx+2Ch]
0x140057df9  test    al, 2
0x140057dfb  jz      loc_140057B88
0x140057e01  cmp     byte ptr [rcx+29h], 2
0x140057e05  jb      loc_140057B88
0x140057e0b  mov     edx, 30h ; '0'
0x140057e10  mov     rcx, [rcx+18h]
0x140057e14  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140057e1b  mov     r9d, ebx
0x140057e1e  call    WPP_SF_d
0x140057e23  jmp     loc_140057B88
0x140057e28  mov     rcx, rdi
0x140057e2b  call    ClasspAllocatePowerProcessIrp
0x140057e30  mov     ebx, eax
0x140057e32  test    eax, eax
0x140057e34  jns     short loc_140057E69
0x140057e36  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e3d  lea     rsi, WPP_GLOBAL_Control
0x140057e44  cmp     rcx, rsi
0x140057e47  jz      loc_140057B88
0x140057e4d  mov     eax, [rcx+2Ch]
0x140057e50  test    al, 2
0x140057e52  jz      loc_140057B88
0x140057e58  cmp     byte ptr [rcx+29h], 2
0x140057e5c  jb      loc_140057B88
0x140057e62  mov     edx, 31h ; '1'
0x140057e67  jmp     short loc_140057E10
0x140057e69  cmp     dword ptr [r14+48h], 7
0x140057e6e  jnz     short loc_140057EEA
0x140057e70  mov     eax, [r14+34h]
0x140057e74  test    al, 4
0x140057e76  jnz     short loc_140057EEA
0x140057e78  mov     rcx, [rdi+10h]; DeviceObject
0x140057e7c  lea     rbx, [rdi+488h]
0x140057e83  mov     r8, rbx; Descriptor
0x140057e86  mov     [rsp+150h+PropertyId], 5
0x140057e8e  lea     rdx, [rsp+150h+PropertyId]; PropertyId
0x140057e93  call    ClassGetDescriptor
0x140057e98  mov     r9d, eax
0x140057e9b  test    eax, eax
0x140057e9d  js      short loc_140057EBC
0x140057e9f  mov     rdx, [rbx]
0x140057ea2  cmp     dword ptr [rdx+4], 8
0x140057ea6  jb      short loc_140057EBC
0x140057ea8  mov     ecx, [rdx+8]
0x140057eab  dec     ecx
0x140057ead  test    ecx, 0FFFFFFFBh
0x140057eb3  jz      short loc_140057EBC
0x140057eb5  mov     [rdx+0Eh], r12w
0x140057eba  jmp     short loc_140057EEA
0x140057ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ec3  cmp     rcx, rsi
0x140057ec6  jz      short loc_140057EEA
0x140057ec8  mov     eax, [rcx+2Ch]
0x140057ecb  test    al, 2
0x140057ecd  jz      short loc_140057EEA
0x140057ecf  cmp     byte ptr [rcx+29h], 3
0x140057ed3  jb      short loc_140057EEA
0x140057ed5  mov     rcx, [rcx+18h]
0x140057ed9  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140057ee0  mov     edx, 32h ; '2'
0x140057ee5  call    WPP_SF_d
0x140057eea  mov     rcx, [rdi+10h]; DeviceObject
0x140057eee  lea     r8, [rdi+210h]; Descriptor
0x140057ef5  lea     rdx, [rsp+150h+PropertyId]; PropertyId
0x140057efa  mov     [rsp+150h+PropertyId], 1
0x140057f02  call    ClassGetDescriptor
0x140057f07  mov     ebx, eax
  ... truncated ...
```
