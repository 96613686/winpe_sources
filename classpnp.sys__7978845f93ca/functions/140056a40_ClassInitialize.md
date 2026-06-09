# ClassInitialize

- ea: `0x140056a40`
- end: `0x140057520`
- name: `ClassInitialize`
- size: `2784`
- prototype: `ULONG __stdcall(PVOID Argument1, PVOID Argument2, PCLASS_INIT_DATA InitializationData)`
- caller_count: `0`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x1400010b8`
- `0x1400010f8`
- `0x14001fbf4`
- `0x14001feac`
- `0x1400266e4`
- `0x140026a6c`
- `0x140026d30`
- `0x14002c1a0`
- `0x14002c310`
- `0x1400315c4`
- `0x140036550`
- `0x14003e430`
- `0x14003e470`
- `0x14003e940`
- `0x140056a40`
- `0x14005a7b8`
- `0x14005a84c`
- `0x14005b1a8`
- `0x140065044`
- `0x14006509c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140056ae3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056af6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056b0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056bfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056e37`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056ec8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056ae3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056af6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056b0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056bfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056e37`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056ec8`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140056c30`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140056ef8`
- `ntoskrnl!ExAllocatePool2` at `0x140056c6b`
- `ntoskrnl!ExAllocatePool2` at `0x140056cf6`
- `ntoskrnl!ExAllocatePool2` at `0x140056f4c`
- `ntoskrnl!ExAllocatePool2` at `0x1400571ea`
- `ntoskrnl!ExAllocatePool2` at `0x140056c6b`
- `ntoskrnl!ExAllocatePool2` at `0x140056cf6`
- `ntoskrnl!ExAllocatePool2` at `0x140056f4c`
- `ntoskrnl!ExAllocatePool2` at `0x1400571ea`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140056c0d`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140056ed8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140056c0d`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140056ed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056d78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056d8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056da6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056dbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056d78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056d8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056da6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056dbe`
- `ntoskrnl!ZwClose` at `0x140056dcf`
- `ntoskrnl!ZwClose` at `0x140056ff2`
- `ntoskrnl!ZwClose` at `0x140056dcf`
- `ntoskrnl!ZwClose` at `0x140056ff2`
- `ntoskrnl!ZwOpenKey` at `0x140056b4c`
- `ntoskrnl!ZwOpenKey` at `0x140056e73`
- `ntoskrnl!ZwOpenKey` at `0x140056b4c`
- `ntoskrnl!ZwOpenKey` at `0x140056e73`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14005745f`
- `ntoskrnl!IoRegisterDriverReinitialization` at `0x14005745f`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140057446`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x140057446`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140056e04`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140056e04`
- `ntoskrnl!IoRegisterPriorityCallback` at `0x1400572c8`
- `ntoskrnl!IoRegisterPriorityCallback` at `0x1400572c8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140057212`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140057212`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400572ad`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400572ad`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1400571a4`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1400571a4`
- `ntoskrnl!EtwRegister` at `0x1400573bd`
- `ntoskrnl!EtwRegister` at `0x1400573bd`

## string_xrefs

- `0x140056bc0`: `RtlQueryRegistryValuesEx`
- `0x140056e97`: `RtlQueryRegistryValuesEx`
- `0x140056b02`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4d36e967-e325-11ce-bfc1-08002be10318}`
- `0x140056e2c`: `\Registry\Machine\System\CurrentControlSet\Control\Classpnp`

## pseudocode

```c
ULONG __stdcall ClassInitialize(PVOID Argument1, PVOID Argument2, PCLASS_INIT_DATA InitializationData)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  void *v9; // rbx
  PVOID SystemRoutineAddress; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  wchar_t *Buffer; // rbx
  wchar_t *v14; // r14
  wchar_t *Pool2; // r15
  __int64 v16; // rax
  wchar_t *v17; // rbx
  int v18; // r8d
  int v19; // r9d
  HANDLE v20; // rbx
  PVOID v21; // rax
  HANDLE *v22; // rax
  HANDLE v23; // rcx
  __int64 v24; // rax
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  int (__fastcall *ClassEnumerateDevice)(_DEVICE_OBJECT *); // rax
  __int64 v28; // r14
  NTSTATUS v29; // ebx
  unsigned __int16 v30; // cx
  _QWORD *v31; // rbx
  PCLASS_INIT_DATA v33; // rax
  _OWORD *v34; // rcx
  __int128 v35; // xmm1
  PVOID DriverObjectExtension; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v41; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES v43; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v44; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v45; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v46[14]; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v48[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v49[16]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v50[22]; // [rsp+1A0h] [rbp+A0h] BYREF

  DriverObjectExtension = 0;
  Handle = 0;
  v45 = 0;
  memset(&v43, 0, 44);
  memset(v46, 0, sizeof(v46));
  v38 = 0;
  KeyHandle = 0;
  v44 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v41 = 0;
  wil_InitializeFeatureStaging();
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v41, 0);
  RtlInitUnicodeString(
    &v44,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Class\\{4d36e967-e325-11ce-bfc1-08002be10318}");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v44;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    memset(v50, 0, 0xA8u);
    v9 = KeyHandle;
    v50[2] = L"UpperFilters";
    LODWORD(v50[1]) = 304;
    LODWORD(v50[4]) = 117440519;
    v50[3] = &DestinationString;
    LODWORD(v50[8]) = 304;
    v50[9] = L"LowerFilters";
    LODWORD(v50[11]) = 117440519;
    v50[10] = &v41;
    v50[5] = 0;
    LODWORD(v50[6]) = 0;
    v50[12] = 0;
    LODWORD(v50[13]) = 0;
    SystemRoutineName = 0;
    RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    if ( ((int (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
           0x40000000,
           v9,
           v50,
           0,
           0) >= 0 )
    {
      Buffer = DestinationString.Buffer;
      v14 = L"None";
      if ( DestinationString.Buffer )
      {
        Pool2 = (wchar_t *)ExAllocatePool2(64, 2 * (unsigned int)DestinationString.MaximumLength, 1883464531);
        if ( Pool2 )
        {
          while ( *Buffer )
          {
            StringCbCatW(Pool2, 2 * (unsigned int)DestinationString.MaximumLength, Buffer);
            v16 = -1;
            do
              ++v16;
            while ( Buffer[v16] );
            Buffer += v16 + 1;
            if ( !*Buffer )
              break;
            StringCbCatW(Pool2, 2 * (unsigned int)DestinationString.MaximumLength, L" ");
          }
        }
        else
        {
          Pool2 = L"Unknown";
        }
      }
      else
      {
        Pool2 = L"None";
      }
      v17 = v41.Buffer;
      if ( v41.Buffer )
      {
        v14 = (wchar_t *)ExAllocatePool2(64, 2 * (unsigned int)v41.MaximumLength, 1883464531);
        if ( v14 )
        {
          while ( *v17 )
          {
            StringCbCatW(v14, 2 * (unsigned int)v41.MaximumLength, v17);
            v24 = -1;
            do
              ++v24;
            while ( v17[v24] );
            v17 += v24 + 1;
            if ( !*v17 )
              break;
            StringCbCatW(v14, 2 * (unsigned int)v41.MaximumLength, L" ");
          }
        }
        else
        {
          v14 = L"Unknown";
        }
      }
      if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12) )
      {
        tlgCreate1Sz_wchar_t(v48, Pool2);
        tlgCreate1Sz_wchar_t(v49, v14);
        tlgWriteTransfer_EtwWriteTransfer(
          (int)&SystemRoutineName,
          (int)&byte_14004893D,
          v18,
          v19,
          4u,
          (__int64)&SystemRoutineName);
      }
      if ( Pool2 )
        ExFreePoolWithTag(Pool2, 0);
      if ( v14 )
        ExFreePoolWithTag(v14, 0);
    }
    if ( DestinationString.Buffer )
      ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( v41.Buffer )
      ExFreePoolWithTag(v41.Buffer, 0);
    ZwClose(KeyHandle);
  }
  if ( (unsigned int)dword_14004D060 > 5 )
    tlgWriteTransfer_EtwWriteTransfer(v6, (int)&qword_1400487E8, v7, v8, 2u, (__int64)&SystemRoutineName);
  TelemetryRetryLastResetTimestamp = KeQueryUnbiasedInterruptTime();
  if ( !InitSecurityCookie )
  {
    _security_init_cookie();
    InitSecurityCookie = 1;
  }
  RtlInitUnicodeString(&v45, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Classpnp");
  v43.Length = 48;
  v43.ObjectName = &v45;
  v43.RootDirectory = 0;
  v43.Attributes = 576;
  *(_OWORD *)&v43.SecurityDescriptor = 0;
  if ( ZwOpenKey(&Handle, 0x20019u, &v43) >= 0 )
  {
    v20 = Handle;
    v46[2] = L"DisablePagefileCRC";
    LODWORD(v46[1]) = 292;
    v46[3] = &v38;
    LODWORD(v46[4]) = 0x4000000;
    v46[5] = 0;
    LODWORD(v46[6]) = 0;
    SystemRoutineName = 0;
    RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
    v21 = MmGetSystemRoutineAddress(&SystemRoutineName);
    if ( !v21 )
      v21 = RtlQueryRegistryValues;
    if ( ((int (__fastcall *)(__int64, HANDLE, _QWORD *, _QWORD, _QWORD))v21)(0x40000000, v20, v46, 0, 0) >= 0 && v38 )
      ClassRegDisablePagefileCRC = 1;
    ClassUpdateDynamicRegistrySettings(Handle);
    if ( ClassIsClientOS || RegWatchContext )
    {
      v23 = Handle;
    }
    else
    {
      v22 = (HANDLE *)ExAllocatePool2(64, 192, 1465017171);
      v23 = Handle;
      RegWatchContext = v22;
      if ( v22 )
      {
        *v22 = Handle;
        v22[1] = ClassUpdateDynamicRegistrySettings;
        ClasspInitRegistryWatch(Handle);
        ClasspWatchForRegistryChanges(RegWatchContext);
        Handle = 0;
        goto LABEL_52;
      }
    }
    ZwClose(v23);
  }
LABEL_52:
  ClassSetMaxNumberOfIoRetries();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
  }
  if ( InitializationData->InitializationDataSize != 392 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return -1073741735;
    }
    v26 = 11;
LABEL_123:
    WPP_SF_(v25->AttachedDevice, v26, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    return -1073741735;
  }
  if ( !InitializationData->FdoData.ClassDeviceControl
    || !InitializationData->FdoData.ClassReadWriteVerification && !InitializationData->ClassStartIo
    || !InitializationData->ClassAddDevice
    || !InitializationData->FdoData.ClassStartDevice )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return -1073741735;
    }
    v26 = 12;
    goto LABEL_123;
  }
  ClassEnumerateDevice = InitializationData->ClassEnumerateDevice;
  if ( ClassEnumerateDevice
    && (!InitializationData->PdoData.ClassDeviceControl
     || !InitializationData->PdoData.ClassStartDevice
     || !InitializationData->PdoData.ClassReadWriteVerification && !InitializationData->ClassStartIo) )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return -1073741735;
    }
    v26 = 13;
    goto LABEL_123;
  }
  if ( !InitializationData->FdoData.ClassStopDevice
    || ClassEnumerateDevice && !InitializationData->PdoData.ClassStopDevice )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return -1073741735;
    }
    v26 = 14;
    goto LABEL_123;
  }
  if ( !InitializationData->FdoData.ClassPowerDevice )
    InitializationData->FdoData.ClassPowerDevice = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ClassMinimalPowerHandler;
  if ( ClassEnumerateDevice && !InitializationData->PdoData.ClassPowerDevice )
    InitializationData->PdoData.ClassPowerDevice = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))ClassMinimalPowerHandler;
  v28 = 3;
  if ( !InitializationData->ClassUnload
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, Argument2);
  }
  v29 = IoAllocateDriverObjectExtension((PDRIVER_OBJECT)Argument1, ClassInitialize, 0x390u, &DriverObjectExtension);
  if ( v29 >= 0 )
  {
    *(_WORD *)DriverObjectExtension = *(_WORD *)Argument2;
    v30 = *(_WORD *)Argument2 + 2;
    *((_WORD *)DriverObjectExtension + 1) = v30;
    v31 = DriverObjectExtension;
    v31[1] = ExAllocatePool2(256, v30, 826499923);
    if ( !*((_QWORD *)DriverObjectExtension + 1) )
      return -1073741670;
    RtlCopyUnicodeString((PUNICODE_STRING)DriverObjectExtension, (PCUNICODE_STRING)Argument2);
    v33 = InitializationData;
    v34 = (char *)DriverObjectExtension + 16;
    do
    {
      *v34 = *(_OWORD *)&v33->InitializationDataSize;
      v34[1] = *(_OWORD *)&v33->FdoData.StackSize;
      v34[2] = *(_OWORD *)&v33->FdoData.ClassReadWriteVerification;
      v34[3] = *(_OWORD *)&v33->FdoData.ClassShutdownFlush;
      v34[4] = *(_OWORD *)&v33->FdoData.ClassInitDevice;
      v34[5] = *(_OWORD *)&v33->FdoData.ClassPowerDevice;
      v34[6] = *(_OWORD *)&v33->FdoData.ClassRemoveDevice;
      v35 = *(_OWORD *)&v33->FdoData.ClassWmiInfo.GuidCount;
      v33 = (PCLASS_INIT_DATA)((char *)v33 + 128);
      v34[7] = v35;
      v34 += 8;
      --v28;
    }
    while ( v28 );
    *(_QWORD *)v34 = *(_QWORD *)&v33->InitializationDataSize;
    *((_DWORD *)DriverObjectExtension + 102) = 0;
    ClassInitializeDispatchTables(DriverObjectExtension, 128);
    goto LABEL_96;
  }
  if ( v29 == -1073741771 )
  {
    DriverObjectExtension = IoGetDriverObjectExtension((PDRIVER_OBJECT)Argument1, ClassInitialize);
LABEL_96:
    if ( (int)IoRegisterPriorityCallback(Argument1, ClassIoBoostPriority) < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    *((_QWORD *)Argument1 + 14) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 16) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 17) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 18) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 29) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 28) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 30) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 23) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 41) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 36) = ClassGlobalDispatch;
    *((_QWORD *)Argument1 + 37) = ClassGlobalDispatch;
    if ( InitializationData->ClassStartIo )
      *((_QWORD *)Argument1 + 12) = ClasspStartIo;
    *((_QWORD *)Argument1 + 13) = (unsigned __int64)ClassUnload & -(__int64)(InitializationData->ClassUnload != 0);
    *(_QWORD *)(*((_QWORD *)Argument1 + 6) + 8LL) = ClassAddDevice;
    McGenEventRegister_EtwRegister();
    if ( !*((_QWORD *)DriverObjectExtension + 54) )
    {
      if ( EtwRegister(&StoragePredictFailureDPSGuid, 0, 0, (PREGHANDLE)DriverObjectExtension + 54) < 0 )
        *((_QWORD *)DriverObjectExtension + 54) = 0;
      *(_QWORD *)&WPP_MAIN_CB.Type = 0;
      WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_wppCtlGuid;
      WPP_MAIN_CB.NextDevice = 0;
      WPP_MAIN_CB.CurrentIrp = 0;
      WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
      WppLoadTracingSupport();
      WPP_MAIN_CB.CurrentIrp = 0;
      WppInitKm();
    }
    if ( !IdlePowerFDOList )
    {
      qword_14004D1E8 = (__int64)&IdlePowerFDOList;
      IdlePowerFDOList = &IdlePowerFDOList;
      KeInitializeGuardedMutex((PKGUARDED_MUTEX)&WPP_MAIN_CB.DeviceExtension);
    }
    IoRegisterDriverReinitialization((PDRIVER_OBJECT)Argument1, ClassDriverReinitialization, 0);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, (unsigned int)v29);
  }
  return v29;
}

```

## disassembly

```asm
0x140056a40  mov     [rsp-8+arg_18], rbx
0x140056a45  push    rbp
0x140056a46  push    rsi
0x140056a47  push    rdi
0x140056a48  push    r12
0x140056a4a  push    r13
0x140056a4c  push    r14
0x140056a4e  push    r15
0x140056a50  lea     rbp, [rsp-160h]
0x140056a58  sub     rsp, 260h
0x140056a5f  mov     rax, cs:__security_cookie
0x140056a66  xor     rax, rsp
0x140056a69  mov     [rbp+190h+var_40], rax
0x140056a70  xorps   xmm0, xmm0
0x140056a73  xor     r13d, r13d
0x140056a76  mov     rdi, r8
0x140056a79  mov     [rsp+290h+DriverObjectExtension], r13
0x140056a7e  mov     r12, rdx
0x140056a81  mov     [rsp+290h+Handle], r13
0x140056a86  mov     rsi, rcx
0x140056a89  xor     eax, eax
0x140056a8b  movups  xmmword ptr [rbp+190h+var_1F0.ObjectName], xmm0
0x140056a8f  lea     r8d, [r13+70h]; Size
0x140056a93  xor     edx, edx; Val
0x140056a95  lea     rcx, [rbp+190h+var_1A0]; void *
0x140056a99  movups  xmmword ptr [rbp+190h+var_1B0.Length], xmm0
0x140056a9d  movups  xmmword ptr [rbp+190h+var_1F0.Length], xmm0
0x140056aa1  movups  xmmword ptr [rbp+190h+var_1F0+1Ch], xmm0
0x140056aa5  call    memset
0x140056aaa  xorps   xmm0, xmm0
0x140056aad  mov     [rsp+290h+var_250], r13d
0x140056ab2  xorps   xmm1, xmm1
0x140056ab5  mov     [rsp+290h+KeyHandle], r13
0x140056aba  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm0
0x140056abe  xor     eax, eax
0x140056ac0  movups  xmmword ptr [rbp+190h+ObjectAttributes+1Ch], xmm0
0x140056ac4  movups  xmmword ptr [rbp+190h+var_1C0.Length], xmm0
0x140056ac8  movups  xmmword ptr [rsp+290h+ObjectAttributes.Length], xmm0
0x140056acd  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x140056ad2  movups  xmmword ptr [rsp+290h+var_230.Length], xmm1
0x140056ad7  call    wil_InitializeFeatureStaging
0x140056adc  xor     edx, edx; SourceString
0x140056ade  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x140056ae3  call    cs:__imp_RtlInitUnicodeString
0x140056aea  nop     dword ptr [rax+rax+00h]
0x140056aef  xor     edx, edx; SourceString
0x140056af1  lea     rcx, [rsp+290h+var_230]; DestinationString
0x140056af6  call    cs:__imp_RtlInitUnicodeString
0x140056afd  nop     dword ptr [rax+rax+00h]
0x140056b02  lea     rdx, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140056b09  lea     rcx, [rbp+190h+var_1C0]; DestinationString
0x140056b0d  call    cs:__imp_RtlInitUnicodeString
0x140056b14  nop     dword ptr [rax+rax+00h]
0x140056b19  lea     rax, [rbp+190h+var_1C0]
0x140056b1d  mov     [rsp+290h+ObjectAttributes.Length], 30h ; '0'
0x140056b25  xorps   xmm0, xmm0
0x140056b28  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x140056b2c  lea     r8, [rsp+290h+ObjectAttributes]; ObjectAttributes
0x140056b31  mov     [rsp+290h+ObjectAttributes.RootDirectory], r13
0x140056b36  mov     edx, 20019h; DesiredAccess
0x140056b3b  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x140056b42  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x140056b47  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x140056b4c  call    cs:__imp_ZwOpenKey
0x140056b53  nop     dword ptr [rax+rax+00h]
0x140056b58  test    eax, eax
0x140056b5a  js      loc_140056DDB
0x140056b60  xor     edx, edx; Val
0x140056b62  lea     rcx, [rbp+190h+var_F0]; void *
0x140056b69  mov     r8d, 0A8h; Size
0x140056b6f  call    memset
0x140056b74  mov     rbx, [rsp+290h+KeyHandle]
0x140056b79  lea     rax, aUpperfilters; "UpperFilters"
0x140056b80  mov     [rbp+190h+var_E0], rax
0x140056b87  mov     edx, 130h
0x140056b8c  mov     ecx, 7000007h
0x140056b91  mov     [rbp+190h+var_E8], edx
0x140056b97  lea     rax, [rsp+290h+DestinationString]
0x140056b9c  mov     [rbp+190h+var_D0], ecx
0x140056ba2  mov     [rbp+190h+var_D8], rax
0x140056ba9  xorps   xmm0, xmm0
0x140056bac  lea     rax, aLowerfilters; "LowerFilters"
0x140056bb3  mov     [rbp+190h+var_B0], edx
0x140056bb9  mov     [rbp+190h+var_A8], rax
0x140056bc0  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140056bc7  lea     rax, [rsp+290h+var_230]
0x140056bcc  mov     [rbp+190h+var_98], ecx
0x140056bd2  lea     rcx, [rbp+190h+SystemRoutineName]; DestinationString
0x140056bd6  mov     [rbp+190h+var_A0], rax
0x140056bdd  mov     [rbp+190h+var_C8], r13
0x140056be4  mov     [rbp+190h+var_C0], r13d
0x140056beb  mov     [rbp+190h+var_90], r13
0x140056bf2  mov     [rbp+190h+var_88], r13d
0x140056bf9  movups  xmmword ptr [rbp+190h+SystemRoutineName.Length], xmm0
0x140056bfd  call    cs:__imp_RtlInitUnicodeString
0x140056c04  nop     dword ptr [rax+rax+00h]
0x140056c09  lea     rcx, [rbp+190h+SystemRoutineName]; SystemRoutineName
0x140056c0d  call    cs:__imp_MmGetSystemRoutineAddress
0x140056c14  nop     dword ptr [rax+rax+00h]
0x140056c19  lea     r8, [rbp+190h+var_F0]
0x140056c20  mov     qword ptr [rsp+290h+var_270], r13
0x140056c25  test    rax, rax
0x140056c28  mov     rdx, rbx
0x140056c2b  mov     ecx, 40000000h
0x140056c30  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140056c38  xor     r9d, r9d
0x140056c3b  call    _guard_dispatch_icall
0x140056c40  test    eax, eax
0x140056c42  js      loc_140056D9A
0x140056c48  mov     rbx, [rsp+290h+DestinationString.Buffer]
0x140056c4d  lea     r14, aNone; "None"
0x140056c54  test    rbx, rbx
0x140056c57  jz      short loc_140056CD6
0x140056c59  movzx   eax, [rsp+290h+DestinationString.MaximumLength]
0x140056c5e  lea     ecx, [r13+40h]
0x140056c62  mov     r8d, 70436353h
0x140056c68  lea     edx, [rax+rax]
0x140056c6b  call    cs:__imp_ExAllocatePool2
0x140056c72  nop     dword ptr [rax+rax+00h]
0x140056c77  mov     r15, rax
0x140056c7a  test    rax, rax
0x140056c7d  jnz     short loc_140056CCE
0x140056c7f  lea     r15, aUnknown; "Unknown"
0x140056c86  jmp     short loc_140056CD9
0x140056c88  movzx   ecx, [rsp+290h+DestinationString.MaximumLength]
0x140056c8d  mov     r8, rbx; pszSrc
0x140056c90  lea     edx, [rcx+rcx]; cbDest
0x140056c93  mov     rcx, r15; pszDest
0x140056c96  call    StringCbCatW
0x140056c9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140056c9f  inc     rax
0x140056ca2  cmp     [rbx+rax*2], r13w
0x140056ca7  jnz     short loc_140056C9F
0x140056ca9  lea     rbx, [rbx+rax*2]
0x140056cad  add     rbx, 2
0x140056cb1  cmp     [rbx], r13w
0x140056cb5  jz      short loc_140056CD9
0x140056cb7  movzx   eax, [rsp+290h+DestinationString.MaximumLength]
0x140056cbc  lea     r8, pszSrc; " "
0x140056cc3  mov     rcx, r15; pszDest
0x140056cc6  lea     edx, [rax+rax]; cbDest
0x140056cc9  call    StringCbCatW
0x140056cce  cmp     [rbx], r13w
0x140056cd2  jnz     short loc_140056C88
0x140056cd4  jmp     short loc_140056CD9
0x140056cd6  mov     r15, r14
0x140056cd9  mov     rbx, [rsp+290h+var_230.Buffer]
0x140056cde  test    rbx, rbx
0x140056ce1  jz      short loc_140056D15
0x140056ce3  movzx   eax, [rsp+290h+var_230.MaximumLength]
0x140056ce8  mov     ecx, 40h ; '@'
0x140056ced  mov     r8d, 70436353h
0x140056cf3  lea     edx, [rax+rax]
0x140056cf6  call    cs:__imp_ExAllocatePool2
0x140056cfd  nop     dword ptr [rax+rax+00h]
0x140056d02  mov     r14, rax
0x140056d05  test    rax, rax
0x140056d08  jnz     loc_140056FE2
0x140056d0e  lea     r14, aUnknown; "Unknown"
0x140056d15  mov     eax, cs:dword_14004D060
0x140056d1b  cmp     eax, 5
0x140056d1e  jbe     short loc_140056D6E
0x140056d20  mov     rdx, 400000000000h
0x140056d2a  call    _tlgKeywordOn
0x140056d2f  test    al, al
0x140056d31  jz      short loc_140056D6E
0x140056d33  mov     rdx, r15
0x140056d36  lea     rcx, [rbp+190h+var_110]
0x140056d3d  call    _tlgCreate1Sz_wchar_t
0x140056d42  mov     rdx, r14
0x140056d45  lea     rcx, [rbp+190h+var_100]
0x140056d4c  call    _tlgCreate1Sz_wchar_t
0x140056d51  lea     rcx, [rbp+190h+SystemRoutineName]; int
0x140056d55  mov     [rsp+290h+var_268], rcx; __int64
0x140056d5a  lea     rdx, byte_14004893D; int
0x140056d61  mov     [rsp+290h+var_270], 4; ULONG
0x140056d69  call    _tlgWriteTransfer_EtwWriteTransfer
0x140056d6e  test    r15, r15
0x140056d71  jz      short loc_140056D84
0x140056d73  xor     edx, edx; Tag
0x140056d75  mov     rcx, r15; P
0x140056d78  call    cs:__imp_ExFreePoolWithTag
0x140056d7f  nop     dword ptr [rax+rax+00h]
0x140056d84  test    r14, r14
0x140056d87  jz      short loc_140056D9A
0x140056d89  xor     edx, edx; Tag
0x140056d8b  mov     rcx, r14; P
0x140056d8e  call    cs:__imp_ExFreePoolWithTag
0x140056d95  nop     dword ptr [rax+rax+00h]
0x140056d9a  mov     rcx, [rsp+290h+DestinationString.Buffer]; P
0x140056d9f  test    rcx, rcx
0x140056da2  jz      short loc_140056DB2
0x140056da4  xor     edx, edx; Tag
0x140056da6  call    cs:__imp_ExFreePoolWithTag
0x140056dad  nop     dword ptr [rax+rax+00h]
0x140056db2  mov     rcx, [rsp+290h+var_230.Buffer]; P
0x140056db7  test    rcx, rcx
0x140056dba  jz      short loc_140056DCA
0x140056dbc  xor     edx, edx; Tag
0x140056dbe  call    cs:__imp_ExFreePoolWithTag
0x140056dc5  nop     dword ptr [rax+rax+00h]
0x140056dca  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x140056dcf  call    cs:__imp_ZwClose
0x140056dd6  nop     dword ptr [rax+rax+00h]
0x140056ddb  mov     eax, cs:dword_14004D060
0x140056de1  mov     ebx, 2
0x140056de6  cmp     eax, 5
0x140056de9  jbe     short loc_140056E04
0x140056deb  lea     rax, [rbp+190h+SystemRoutineName]
0x140056def  mov     [rsp+290h+var_268], rax; __int64
0x140056df4  lea     rdx, qword_1400487E8; int
0x140056dfb  mov     [rsp+290h+var_270], ebx; ULONG
0x140056dff  call    _tlgWriteTransfer_EtwWriteTransfer
0x140056e04  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140056e0b  nop     dword ptr [rax+rax+00h]
0x140056e10  cmp     cs:InitSecurityCookie, r13b
0x140056e17  mov     cs:TelemetryRetryLastResetTimestamp, rax
0x140056e1e  jnz     short loc_140056E2C
0x140056e20  call    __security_init_cookie
0x140056e25  mov     cs:InitSecurityCookie, 1
0x140056e2c  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x140056e33  lea     rcx, [rbp+190h+var_1B0]; DestinationString
0x140056e37  call    cs:__imp_RtlInitUnicodeString
0x140056e3e  nop     dword ptr [rax+rax+00h]
0x140056e43  lea     rax, [rbp+190h+var_1B0]
0x140056e47  mov     [rbp+190h+var_1F0.Length], 30h ; '0'
0x140056e4e  xorps   xmm0, xmm0
0x140056e51  mov     [rbp+190h+var_1F0.ObjectName], rax
0x140056e55  lea     r8, [rbp+190h+var_1F0]; ObjectAttributes
0x140056e59  mov     [rbp+190h+var_1F0.RootDirectory], r13
0x140056e5d  mov     edx, 20019h; DesiredAccess
0x140056e62  mov     [rbp+190h+var_1F0.Attributes], 240h
0x140056e69  lea     rcx, [rsp+290h+Handle]; KeyHandle
0x140056e6e  movdqu  xmmword ptr [rbp+190h+var_1F0.SecurityDescriptor], xmm0
0x140056e73  call    cs:__imp_ZwOpenKey
0x140056e7a  nop     dword ptr [rax+rax+00h]
0x140056e7f  test    eax, eax
0x140056e81  js      loc_140057003
0x140056e87  mov     rbx, [rsp+290h+Handle]
0x140056e8c  lea     rax, aDisablepagefil; "DisablePagefileCRC"
0x140056e93  mov     [rbp+190h+var_190], rax
0x140056e97  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140056e9e  lea     rax, [rsp+290h+var_250]
0x140056ea3  mov     [rbp+190h+var_198], 124h
0x140056eaa  xorps   xmm0, xmm0
0x140056ead  mov     [rbp+190h+var_188], rax
0x140056eb1  lea     rcx, [rbp+190h+SystemRoutineName]; DestinationString
0x140056eb5  mov     [rbp+190h+var_180], 4000000h
0x140056ebc  mov     [rbp+190h+var_178], r13
0x140056ec0  mov     [rbp+190h+var_170], r13d
0x140056ec4  movups  xmmword ptr [rbp+190h+SystemRoutineName.Length], xmm0
0x140056ec8  call    cs:__imp_RtlInitUnicodeString
0x140056ecf  nop     dword ptr [rax+rax+00h]
0x140056ed4  lea     rcx, [rbp+190h+SystemRoutineName]; SystemRoutineName
0x140056ed8  call    cs:__imp_MmGetSystemRoutineAddress
0x140056edf  nop     dword ptr [rax+rax+00h]
0x140056ee4  lea     r8, [rbp+190h+var_1A0]
0x140056ee8  mov     qword ptr [rsp+290h+var_270], r13
0x140056eed  test    rax, rax
0x140056ef0  mov     rdx, rbx
0x140056ef3  mov     ecx, 40000000h
0x140056ef8  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140056f00  xor     r9d, r9d
0x140056f03  call    _guard_dispatch_icall
0x140056f08  test    eax, eax
0x140056f0a  js      short loc_140056F1A
0x140056f0c  cmp     [rsp+290h+var_250], r13d
0x140056f11  jz      short loc_140056F1A
0x140056f13  mov     cs:ClassRegDisablePagefileCRC, 1
0x140056f1a  mov     rcx, [rsp+290h+Handle]; KeyHandle
0x140056f1f  call    ClassUpdateDynamicRegistrySettings
0x140056f24  cmp     cs:ClassIsClientOS, r13b
0x140056f2b  jnz     loc_140056FED
0x140056f31  cmp     cs:RegWatchContext, r13
0x140056f38  jnz     loc_140056FED
0x140056f3e  mov     edx, 0C0h
0x140056f43  mov     r8d, 57526353h
0x140056f49  lea     ecx, [rdx-80h]
0x140056f4c  call    cs:__imp_ExAllocatePool2
0x140056f53  nop     dword ptr [rax+rax+00h]
0x140056f58  mov     rcx, [rsp+290h+Handle]
0x140056f5d  mov     cs:RegWatchContext, rax
0x140056f64  test    rax, rax
0x140056f67  jz      loc_140056FF2
0x140056f6d  mov     [rax], rcx
0x140056f70  lea     rcx, ClassUpdateDynamicRegistrySettings
0x140056f77  mov     [rax+8], rcx
0x140056f7b  mov     rcx, [rsp+290h+Handle]
0x140056f80  call    ClasspInitRegistryWatch
0x140056f85  mov     rcx, cs:RegWatchContext
0x140056f8c  call    ClasspWatchForRegistryChanges
0x140056f91  mov     [rsp+290h+Handle], r13
0x140056f96  jmp     short loc_140056FFE
0x140056f98  movzx   ecx, [rsp+290h+var_230.MaximumLength]
0x140056f9d  mov     r8, rbx; pszSrc
0x140056fa0  lea     edx, [rcx+rcx]; cbDest
0x140056fa3  mov     rcx, r14; pszDest
0x140056fa6  call    StringCbCatW
0x140056fab  or      rax, 0FFFFFFFFFFFFFFFFh
0x140056faf  inc     rax
  ... truncated ...
```
