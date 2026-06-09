# HidpAddDevice

- ea: `0x18003a590`
- end: `0x18003b09a`
- name: `HidpAddDevice`
- size: `2826`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009778`
- `0x18000ddc8`
- `0x18001775c`
- `0x1800185e4`
- `0x18001d7b4`
- `0x18001e490`
- `0x18001fba0`
- `0x18001ffbc`
- `0x18002204c`
- `0x180023e50`
- `0x180023f18`
- `0x180027c80`
- `0x180028000`
- `0x1800377e0`
- `0x180037b20`
- `0x18003a590`
- `0x18003f8bc`
- `0x18003f980`
- `0x180041248`
- `0x1800419a8`
- `0x1800426e8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x18003a912`
- `ntoskrnl!KeInitializeEvent` at `0x18003ac6e`
- `ntoskrnl!KeInitializeEvent` at `0x18003a912`
- `ntoskrnl!KeInitializeEvent` at `0x18003ac6e`
- `ntoskrnl!MmBadPointer` at `0x18003a9dc`
- `ntoskrnl!MmBadPointer` at `0x18003ae4f`
- `ntoskrnl!ObfReferenceObject` at `0x18003a839`
- `ntoskrnl!ObfReferenceObject` at `0x18003a839`
- `ntoskrnl!IoFreeIrp` at `0x18003ae43`
- `ntoskrnl!IoFreeIrp` at `0x18003ae43`
- `ntoskrnl!IoAllocateIrp` at `0x18003a926`
- `ntoskrnl!IoAllocateIrp` at `0x18003a926`
- `ntoskrnl!ObfDereferenceObject` at `0x18003af20`
- `ntoskrnl!ObfDereferenceObject` at `0x18003af20`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x18003aac5`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x18003aac5`
- `ntoskrnl!IoCreateDevice` at `0x18003a792`
- `ntoskrnl!IoCreateDevice` at `0x18003a792`
- `ntoskrnl!IoDetachDevice` at `0x18003af0b`
- `ntoskrnl!IoDetachDevice` at `0x18003af0b`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x18003aa39`
- `ntoskrnl!KeInitializeGuardedMutex` at `0x18003aa39`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x18003a880`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x18003a880`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aa4c`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aa6d`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aa8e`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aafa`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003ab30`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003ac26`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003acad`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aa4c`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aa6d`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aa8e`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003aafa`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003ab30`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003ac26`
- `ntoskrnl!KeInitializeSpinLock` at `0x18003acad`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003af60`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003af60`
- `ntoskrnl!IoFreeWorkItem` at `0x18003ae6c`
- `ntoskrnl!IoFreeWorkItem` at `0x18003ae6c`
- `ntoskrnl!ExAllocatePool2` at `0x18003a5fd`
- `ntoskrnl!ExAllocatePool2` at `0x18003a5fd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003a755`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003a755`
- `ntoskrnl!IoAllocateWorkItem` at `0x18003ab7a`
- `ntoskrnl!IoAllocateWorkItem` at `0x18003ab7a`
- `ntoskrnl!IoDeleteDevice` at `0x18003af30`
- `ntoskrnl!IoDeleteDevice` at `0x18003af30`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x18003afe7`
- `ntoskrnl!PoDirectedDripsSetDeviceFlags` at `0x18003afe7`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x18003ae8f`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x18003aebd`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x18003aeeb`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x18003ae8f`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x18003aebd`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x18003aeeb`

## pseudocode

```c
__int64 __fastcall HidpAddDevice(PDRIVER_OBJECT DriverObject, struct _DEVICE_OBJECT *a2)
{
  int v3; // edx
  int v4; // r8d
  __int64 v5; // r14
  char v6; // si
  NTSTATUS v7; // edi
  __int64 v8; // r8
  __int64 v9; // rdx
  bool v10; // al
  unsigned __int32 v11; // r13d
  int v12; // edx
  int v13; // r8d
  ULONG v14; // r15d
  int v15; // edx
  int v16; // r8d
  _QWORD *DeviceExtension; // rbx
  struct _UNICODE_STRING v18; // xmm0
  _QWORD *v19; // r15
  PIRP Irp; // rax
  __int64 v21; // rdx
  char v22; // r13
  bool v23; // al
  _UNKNOWN **v24; // r8
  __int64 *v25; // rdx
  PIO_WORKITEM WorkItem; // rax
  __int64 v27; // r8
  __int64 v28; // rdx
  PDEVICE_OBJECT v29; // rcx
  bool v30; // al
  __int64 *v31; // rdx
  int v32; // edx
  _UNKNOWN **v33; // r8
  int v34; // edx
  __int64 v35; // r8
  IRP *v36; // rcx
  struct _IO_WORKITEM *v37; // rcx
  struct _DEVICE_OBJECT *v38; // rcx
  int v39; // edx
  int v40; // r8d
  WCHAR *SourceString; // [rsp+50h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+C8h] [rbp+58h] BYREF

  SourceDevice = 0;
  DestinationString = 0;
  v5 = RefDriverExt();
  v6 = 1;
  if ( !v5 )
  {
    v7 = -1073741438;
LABEL_94:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = v6;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        v4,
        g_RecorderLog,
        2,
        2,
        27,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        v7);
    }
    return (unsigned int)v7;
  }
  SourceString = (WCHAR *)ExAllocatePool2(64, 44, 1130654024);
  if ( !SourceString )
  {
    v9 = 3221225626LL;
    v7 = -1073741670;
    v10 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v10;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v8,
        g_RecorderLog,
        2,
        2,
        19,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        (char)DriverObject,
        154);
    }
LABEL_92:
    DerefDriverExt(DriverObject, v9, v8);
    if ( SourceString )
      ExFreePoolWithTag(SourceString, 0);
    goto LABEL_94;
  }
  v11 = _InterlockedExchangeAdd(&g_HidId, 1u);
  v7 = RtlStringCbPrintfW(SourceString, 0x2Au, L"\\Device\\_HID%08x", v11);
  if ( v7 < 0 )
  {
    LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v13,
        g_RecorderLog,
        2,
        2,
        20,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        (char)DriverObject,
        v7);
    }
    TraceLoggingStrSafeOverflow("onecore\\drivers\\input\\hid\\hidcore\\hidclass\\device.c", 666);
    goto LABEL_92;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v14 = *(_DWORD *)(v5 + 24) + 2328;
  v7 = IoCreateDevice(DriverObject, v14, &DestinationString, 0x22u, 0, 0, &SourceDevice);
  if ( v7 < 0 )
  {
    LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        v16,
        g_RecorderLog,
        2,
        2,
        21,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        (char)DriverObject,
        v7);
    }
    TraceLoggingCreateFdoFailed((unsigned int)v7, v5 + 8);
    goto LABEL_92;
  }
  ObfReferenceObject(SourceDevice);
  DeviceExtension = SourceDevice->DeviceExtension;
  memset(DeviceExtension, 0, v14);
  *((_BYTE *)DeviceExtension + 24) = 0;
  v18 = DestinationString;
  DeviceExtension[2] = DeviceExtension + 291;
  *((struct _UNICODE_STRING *)DeviceExtension + 18) = v18;
  DeviceExtension[1] = IoAttachDeviceToDeviceStack(SourceDevice, a2);
  ++SourceDevice->StackSize;
  *DeviceExtension = a2;
  v19 = DeviceExtension + 4;
  *((_DWORD *)DeviceExtension + 7) = 1164207176;
  DeviceExtension[4] = SourceDevice;
  DeviceExtension[5] = v5;
  *((_DWORD *)DeviceExtension + 70) = 1;
  *((_DWORD *)DeviceExtension + 154) = 1;
  *((_BYTE *)DeviceExtension + 620) = 1;
  *((_DWORD *)DeviceExtension + 78) = 0;
  HidpFdoAllocateIfrRecorderLogs(DeviceExtension + 4);
  HidpGetRetainWWIrpEnabledFromRegistry(DeviceExtension, a2);
  HidpGetIoctlSupportabilities(DeviceExtension + 4, a2);
  HidpGetComboHardwareIdV2Enabled(DeviceExtension + 4, a2);
  HidpGetPdoReenumerateSelfInterfaceEnabled(DeviceExtension + 4, a2);
  KeInitializeEvent((PRKEVENT)(DeviceExtension + 59), NotificationEvent, 1u);
  Irp = IoAllocateIrp(*(_BYTE *)(DeviceExtension[4] + 76LL), 0);
  DeviceExtension[58] = Irp;
  if ( !Irp )
  {
    v21 = 3221225626LL;
    v22 = 0;
    v7 = -1073741670;
    v23 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v24 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v23 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids;
      LOBYTE(v25) = v23;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v25,
        (_DWORD)v24,
        DeviceExtension[88],
        2,
        2,
        22,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        154);
    }
    TraceLoggingIoAllocateIrpFailed((unsigned int)*(char *)(*v19 + 76LL), v21, v24);
LABEL_75:
    if ( DeviceExtension )
    {
      if ( v22 )
        DequeueFdoExt(DeviceExtension + 4);
      v36 = (IRP *)DeviceExtension[58];
      if ( v36 )
      {
        IoFreeIrp(v36);
        DeviceExtension[58] = MmBadPointer;
      }
      v37 = (struct _IO_WORKITEM *)DeviceExtension[215];
      if ( v37 )
        IoFreeWorkItem(v37);
      if ( g_RecorderLog != DeviceExtension[88] )
      {
        imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
        DeviceExtension[88] = 0;
      }
      if ( g_RecorderLog != DeviceExtension[89] )
      {
        imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
        DeviceExtension[89] = 0;
      }
      v9 = DeviceExtension[90];
      if ( g_RecorderLog != v9 )
      {
        imp_WppRecorderLogDelete(WPP_GLOBAL_Control);
        DeviceExtension[90] = 0;
      }
      v38 = (struct _DEVICE_OBJECT *)DeviceExtension[1];
      if ( v38 )
        IoDetachDevice(v38);
      if ( SourceDevice )
      {
        ObfDereferenceObject(SourceDevice);
        IoDeleteDevice(SourceDevice);
      }
    }
    goto LABEL_92;
  }
  DeviceExtension[56] = HidpIdleNotificationCallback;
  DeviceExtension[57] = DeviceExtension;
  *((_DWORD *)DeviceExtension + 98) = 1;
  *((_DWORD *)DeviceExtension + 99) = 1;
  DeviceExtension[50] = MmBadPointer;
  *((_DWORD *)DeviceExtension + 102) = 1;
  DeviceExtension[67] = MmBadPointer;
  *((_OWORD *)DeviceExtension + 126) = 0;
  *((_OWORD *)DeviceExtension + 127) = 0;
  *((_OWORD *)DeviceExtension + 128) = 0;
  DeviceExtension[258] = 0;
  KeInitializeGuardedMutex((PKGUARDED_MUTEX)DeviceExtension + 36);
  KeInitializeSpinLock(DeviceExtension + 259);
  DeviceExtension[64] = DeviceExtension + 63;
  DeviceExtension[63] = DeviceExtension + 63;
  KeInitializeSpinLock(DeviceExtension + 65);
  DeviceExtension[54] = DeviceExtension + 53;
  DeviceExtension[53] = DeviceExtension + 53;
  KeInitializeSpinLock(DeviceExtension + 52);
  *((_DWORD *)DeviceExtension + 110) = 0;
  *((_DWORD *)DeviceExtension + 136) = v11;
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 21, 0x43646948u, 0, 0, 0x20u);
  v22 = 1;
  *((_DWORD *)DeviceExtension + 164) = 3;
  DeviceExtension[81] = 0;
  DeviceExtension[238] = 0;
  *((_DWORD *)DeviceExtension + 475) = 0;
  KeInitializeSpinLock(DeviceExtension + 241);
  *((_BYTE *)DeviceExtension + 1936) = 0;
  DeviceExtension[244] = DeviceExtension + 243;
  DeviceExtension[243] = DeviceExtension + 243;
  DeviceExtension[245] = 0;
  DeviceExtension[246] = 0;
  KeInitializeSpinLock(DeviceExtension + 247);
  *((_BYTE *)DeviceExtension + 1984) = 0;
  DeviceExtension[250] = DeviceExtension + 249;
  DeviceExtension[249] = DeviceExtension + 249;
  EnqueueFdoExt(DeviceExtension + 4);
  SourceDevice->Flags |= 0x10u;
  SourceDevice->Flags |= 0x2000u;
  SourceDevice->Flags &= ~0x80u;
  WorkItem = IoAllocateWorkItem(SourceDevice);
  DeviceExtension[215] = WorkItem;
  if ( !WorkItem )
  {
    v28 = 3221225626LL;
    v7 = -1073741670;
    v29 = WPP_GLOBAL_Control;
    v30 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v31 = WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids;
      LOBYTE(v31) = v30;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v31,
        v27,
        DeviceExtension[88],
        2,
        2,
        23,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        154);
    }
    TraceLoggingIoAllocateWorkItemFailed(v29, v28, v27);
    goto LABEL_75;
  }
  KeInitializeSpinLock(DeviceExtension + 197);
  *((_DWORD *)DeviceExtension + 404) = 0;
  *((_DWORD *)DeviceExtension + 397) = 2000;
  *((_DWORD *)DeviceExtension + 428) = 2000;
  DeviceExtension[213] = HIDSMStateTable;
  DeviceExtension[212] = v19;
  KeInitializeEvent((PRKEVENT)(DeviceExtension + 233), NotificationEvent, 1u);
  *((_DWORD *)DeviceExtension + 472) = 0;
  *((_DWORD *)DeviceExtension + 438) = 0;
  *((_BYTE *)DeviceExtension + 1756) = 0;
  DeviceExtension[267] = 864000000000LL;
  DeviceExtension[269] = 864000000000LL;
  KeInitializeSpinLock(DeviceExtension + 271);
  if ( *(_BYTE *)(v5 + 297) )
    v7 = HidpSetRegistryValue(**(PDEVICE_OBJECT **)(*v19 + 64LL));
  if ( *(_BYTE *)(v5 + 296) )
    v7 = HidpSetRegistryValue(**(PDEVICE_OBJECT **)(*v19 + 64LL));
  if ( v7 < 0 )
  {
    LOBYTE(v32) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v33 = &WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v32 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v32,
        (_DWORD)v33,
        DeviceExtension[88],
        2,
        2,
        24,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        v7);
    }
  }
  v7 = (*(__int64 (__fastcall **)(PDRIVER_OBJECT, PDEVICE_OBJECT))(v5 + 256))(DriverObject, SourceDevice);
  if ( v7 < 0 )
  {
    LOBYTE(v34) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v35) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v34 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v34,
        v35,
        DeviceExtension[88],
        2,
        2,
        25,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        v7);
    TraceLoggingAddDeviceFailed((unsigned int)v7, v5 + 8, v35);
    goto LABEL_75;
  }
  v7 = PoDirectedDripsSetDeviceFlags(a2, 14);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v39) = v6;
      LOBYTE(v40) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v39,
        v40,
        DeviceExtension[88],
        2,
        9,
        26,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        *v19,
        v7);
    }
    return 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003a590  mov     [rsp-38h+arg_0], rbx
0x18003a595  mov     [rsp-38h+TargetDevice], rdx
0x18003a59a  push    rbp
0x18003a59b  push    rsi
0x18003a59c  push    rdi
0x18003a59d  push    r12
0x18003a59f  push    r13
0x18003a5a1  push    r14
0x18003a5a3  push    r15
0x18003a5a5  mov     rbp, rsp
0x18003a5a8  sub     rsp, 70h
0x18003a5ac  xorps   xmm0, xmm0
0x18003a5af  mov     [rbp+SourceDevice], 0
0x18003a5b7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003a5bb  mov     r12, rcx
0x18003a5be  call    RefDriverExt
0x18003a5c3  lea     rbx, WPP_GLOBAL_Control
0x18003a5ca  mov     r14, rax
0x18003a5cd  lea     r15, WPP_RECORDER_INITIALIZED
0x18003a5d4  mov     esi, 1
0x18003a5d9  lea     r13, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003a5e0  test    rax, rax
0x18003a5e3  jnz     short loc_18003A5EF
0x18003a5e5  mov     edi, 0C0000182h
0x18003a5ea  jmp     loc_18003AF74
0x18003a5ef  mov     edx, 2Ch ; ','
0x18003a5f4  mov     r8d, 43646948h
0x18003a5fa  lea     ecx, [rdx+14h]
0x18003a5fd  call    cs:__imp_ExAllocatePool2
0x18003a604  nop     dword ptr [rax+rax+00h]
0x18003a609  mov     [rbp+SourceString], rax
0x18003a60d  mov     rcx, rax; pszDest
0x18003a610  test    rax, rax
0x18003a613  jnz     short loc_18003A690
0x18003a615  mov     edx, 0C000009Ah
0x18003a61a  mov     edi, edx
0x18003a61c  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a623  cmp     r10, rbx
0x18003a626  jz      short loc_18003A63D
0x18003a628  mov     ecx, [r10+2Ch]
0x18003a62c  test    cl, 2
0x18003a62f  jz      short loc_18003A63D
0x18003a631  cmp     byte ptr [r10+29h], 2
0x18003a636  jb      short loc_18003A63D
0x18003a638  mov     al, sil
0x18003a63b  jmp     short loc_18003A63F
0x18003a63d  xor     al, al
0x18003a63f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003a646  setnz   r8b
0x18003a64a  test    al, al
0x18003a64c  jnz     short loc_18003A657
0x18003a64e  test    r8b, r8b
0x18003a651  jz      loc_18003AF4A
0x18003a657  mov     r9, cs:g_RecorderLog
0x18003a65e  mov     rcx, [r10+18h]
0x18003a662  mov     [rsp+70h+var_28], edx
0x18003a666  mov     dl, al
0x18003a668  mov     [rsp+70h+var_30], r12
0x18003a66d  mov     [rsp+70h+var_38], r13
0x18003a672  mov     word ptr [rsp+70h+DeviceObject], 13h
0x18003a679  mov     dword ptr [rsp+70h+Exclusive], 2
0x18003a681  mov     byte ptr [rsp+70h+DeviceCharacteristics], 2
0x18003a686  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003a68b  jmp     loc_18003AF4A
0x18003a690  mov     r13d, esi
0x18003a693  lock xadd cs:g_HidId, r13d
0x18003a69c  dec     r13d
0x18003a69f  lea     r8, aDeviceHid08x; "\\Device\\_HID%08x"
0x18003a6a6  add     r13d, esi
0x18003a6a9  mov     edx, 2Ah ; '*'; cbDest
0x18003a6ae  mov     r9d, r13d
0x18003a6b1  call    RtlStringCbPrintfW
0x18003a6b6  mov     edi, eax
0x18003a6b8  test    eax, eax
0x18003a6ba  jns     loc_18003A74D
0x18003a6c0  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a6c7  cmp     rax, rbx
0x18003a6ca  jz      short loc_18003A6DF
0x18003a6cc  mov     ecx, [rax+2Ch]
0x18003a6cf  test    cl, 2
0x18003a6d2  jz      short loc_18003A6DF
0x18003a6d4  cmp     byte ptr [rax+29h], 2
0x18003a6d8  jb      short loc_18003A6DF
0x18003a6da  mov     dl, sil
0x18003a6dd  jmp     short loc_18003A6E1
0x18003a6df  xor     dl, dl
0x18003a6e1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003a6e8  setnz   r8b
0x18003a6ec  test    dl, dl
0x18003a6ee  jnz     short loc_18003A6F5
0x18003a6f0  test    r8b, r8b
0x18003a6f3  jz      short loc_18003A730
0x18003a6f5  mov     r9, cs:g_RecorderLog
0x18003a6fc  lea     r13, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003a703  mov     rcx, [rax+18h]
0x18003a707  mov     [rsp+70h+var_28], edi
0x18003a70b  mov     [rsp+70h+var_30], r12
0x18003a710  mov     [rsp+70h+var_38], r13
0x18003a715  mov     word ptr [rsp+70h+DeviceObject], 14h
0x18003a71c  mov     dword ptr [rsp+70h+Exclusive], 2
0x18003a724  mov     byte ptr [rsp+70h+DeviceCharacteristics], 2
0x18003a729  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003a72e  jmp     short loc_18003A737
0x18003a730  lea     r13, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003a737  mov     edx, 29Ah
0x18003a73c  lea     rcx, aOnecoreDrivers_0; "onecore\\drivers\\input\\hid\\hidcore\\"...
0x18003a743  call    TraceLoggingStrSafeOverflow
0x18003a748  jmp     loc_18003AF4A
0x18003a74d  mov     rdx, [rbp+SourceString]; SourceString
0x18003a751  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003a755  call    cs:__imp_RtlInitUnicodeString
0x18003a75c  nop     dword ptr [rax+rax+00h]
0x18003a761  mov     r15d, [r14+18h]
0x18003a765  lea     rax, [rbp+SourceDevice]
0x18003a769  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x18003a76e  lea     r8, [rbp+DestinationString]; DeviceName
0x18003a772  add     r15d, 918h
0x18003a779  mov     [rsp+70h+Exclusive], 0; Exclusive
0x18003a77e  mov     edx, r15d; DeviceExtensionSize
0x18003a781  mov     [rsp+70h+DeviceCharacteristics], 0; DeviceCharacteristics
0x18003a789  mov     r9d, 22h ; '"'; DeviceType
0x18003a78f  mov     rcx, r12; DriverObject
0x18003a792  call    cs:__imp_IoCreateDevice
0x18003a799  nop     dword ptr [rax+rax+00h]
0x18003a79e  mov     edi, eax
0x18003a7a0  test    eax, eax
0x18003a7a2  jns     loc_18003A835
0x18003a7a8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a7af  cmp     rcx, rbx
0x18003a7b2  jz      short loc_18003A7C6
0x18003a7b4  mov     eax, [rcx+2Ch]
0x18003a7b7  test    al, 2
0x18003a7b9  jz      short loc_18003A7C6
0x18003a7bb  cmp     byte ptr [rcx+29h], 2
0x18003a7bf  jb      short loc_18003A7C6
0x18003a7c1  mov     dl, sil
0x18003a7c4  jmp     short loc_18003A7C8
0x18003a7c6  xor     dl, dl
0x18003a7c8  lea     r15, WPP_RECORDER_INITIALIZED
0x18003a7cf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003a7d6  setnz   r8b
0x18003a7da  test    dl, dl
0x18003a7dc  jnz     short loc_18003A7E3
0x18003a7de  test    r8b, r8b
0x18003a7e1  jz      short loc_18003A81E
0x18003a7e3  mov     r9, cs:g_RecorderLog
0x18003a7ea  lea     r13, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003a7f1  mov     rcx, [rcx+18h]
0x18003a7f5  mov     [rsp+70h+var_28], edi
0x18003a7f9  mov     [rsp+70h+var_30], r12
0x18003a7fe  mov     [rsp+70h+var_38], r13
0x18003a803  mov     word ptr [rsp+70h+DeviceObject], 15h
0x18003a80a  mov     dword ptr [rsp+70h+Exclusive], 2
0x18003a812  mov     byte ptr [rsp+70h+DeviceCharacteristics], 2
0x18003a817  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003a81c  jmp     short loc_18003A825
0x18003a81e  lea     r13, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003a825  lea     rdx, [r14+8]
0x18003a829  mov     ecx, edi
0x18003a82b  call    TraceLoggingCreateFdoFailed
0x18003a830  jmp     loc_18003AF4A
0x18003a835  mov     rcx, [rbp+SourceDevice]; Object
0x18003a839  call    cs:__imp_ObfReferenceObject
0x18003a840  nop     dword ptr [rax+rax+00h]
0x18003a845  mov     rax, [rbp+SourceDevice]
0x18003a849  xor     edx, edx; Val
0x18003a84b  mov     r8d, r15d; Size
0x18003a84e  mov     rbx, [rax+40h]
0x18003a852  mov     rcx, rbx; void *
0x18003a855  call    memset
0x18003a85a  mov     r15, [rbp+TargetDevice]
0x18003a85e  lea     rax, [rbx+918h]
0x18003a865  mov     byte ptr [rbx+18h], 0
0x18003a869  mov     rdx, r15; TargetDevice
0x18003a86c  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x18003a870  mov     [rbx+10h], rax
0x18003a874  movdqu  xmmword ptr [rbx+120h], xmm0
0x18003a87c  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x18003a880  call    cs:__imp_IoAttachDeviceToDeviceStack
0x18003a887  nop     dword ptr [rax+rax+00h]
0x18003a88c  mov     [rbx+8], rax
0x18003a890  mov     rax, [rbp+SourceDevice]
0x18003a894  add     [rax+4Ch], sil
0x18003a898  mov     [rbx], r15
0x18003a89b  lea     r15, [rbx+20h]
0x18003a89f  mov     dword ptr [rbx+1Ch], 45646448h
0x18003a8a6  mov     rcx, r15
0x18003a8a9  mov     rax, [rbp+SourceDevice]
0x18003a8ad  mov     [r15], rax
0x18003a8b0  mov     [rbx+28h], r14
0x18003a8b4  mov     [rbx+118h], esi
0x18003a8ba  mov     [rbx+268h], esi
0x18003a8c0  mov     [rbx+26Ch], sil
0x18003a8c7  mov     dword ptr [rbx+138h], 0
0x18003a8d1  call    HidpFdoAllocateIfrRecorderLogs
0x18003a8d6  mov     rdx, [rbp+TargetDevice]
0x18003a8da  mov     rcx, rbx
0x18003a8dd  call    HidpGetRetainWWIrpEnabledFromRegistry
0x18003a8e2  mov     rdx, [rbp+TargetDevice]
0x18003a8e6  mov     rcx, r15
0x18003a8e9  call    HidpGetIoctlSupportabilities
0x18003a8ee  mov     rdx, [rbp+TargetDevice]
0x18003a8f2  mov     rcx, r15
0x18003a8f5  call    HidpGetComboHardwareIdV2Enabled
0x18003a8fa  mov     rdx, [rbp+TargetDevice]
0x18003a8fe  mov     rcx, r15
0x18003a901  call    HidpGetPdoReenumerateSelfInterfaceEnabled
0x18003a906  lea     rcx, [rbx+1D8h]; Event
0x18003a90d  mov     r8b, sil; State
0x18003a910  xor     edx, edx; Type
0x18003a912  call    cs:__imp_KeInitializeEvent
0x18003a919  nop     dword ptr [rax+rax+00h]
0x18003a91e  mov     rcx, [r15]
0x18003a921  xor     edx, edx; ChargeQuota
0x18003a923  mov     cl, [rcx+4Ch]; StackSize
0x18003a926  call    cs:__imp_IoAllocateIrp
0x18003a92d  nop     dword ptr [rax+rax+00h]
0x18003a932  mov     [rbx+1D0h], rax
0x18003a939  test    rax, rax
0x18003a93c  jnz     loc_18003A9DC
0x18003a942  mov     edx, 0C000009Ah
0x18003a947  xor     r13b, r13b
0x18003a94a  mov     edi, edx
0x18003a94c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a953  lea     rax, WPP_GLOBAL_Control
0x18003a95a  cmp     rcx, rax
0x18003a95d  jz      short loc_18003A971
0x18003a95f  mov     eax, [rcx+2Ch]
0x18003a962  test    al, 2
0x18003a964  jz      short loc_18003A971
0x18003a966  cmp     byte ptr [rcx+29h], 2
0x18003a96a  jb      short loc_18003A971
0x18003a96c  mov     al, sil
0x18003a96f  jmp     short loc_18003A973
0x18003a971  xor     al, al
0x18003a973  lea     r8, WPP_RECORDER_INITIALIZED
0x18003a97a  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18003a981  setnz   r8b
0x18003a985  test    al, al
0x18003a987  jnz     short loc_18003A98E
0x18003a989  test    r8b, r8b
0x18003a98c  jz      short loc_18003A9C4
0x18003a98e  mov     r9, [rbx+2C0h]
0x18003a995  mov     rcx, [rcx+18h]
0x18003a999  mov     dword ptr [rsp+70h+var_30], edx
0x18003a99d  lea     rdx, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003a9a4  mov     [rsp+70h+var_38], rdx
0x18003a9a9  mov     dl, al
0x18003a9ab  mov     word ptr [rsp+70h+DeviceObject], 16h
0x18003a9b2  mov     dword ptr [rsp+70h+Exclusive], 2
0x18003a9ba  mov     byte ptr [rsp+70h+DeviceCharacteristics], 2
0x18003a9bf  call    WPP_RECORDER_AND_TRACE_SF_d
0x18003a9c4  mov     rax, [r15]
0x18003a9c7  movsx   ecx, byte ptr [rax+4Ch]
0x18003a9cb  call    TraceLoggingIoAllocateIrpFailed
0x18003a9d0  lea     r15, WPP_RECORDER_INITIALIZED
0x18003a9d7  jmp     loc_18003AE20
0x18003a9dc  mov     rcx, cs:MmBadPointer
0x18003a9e3  lea     rax, HidpIdleNotificationCallback
0x18003a9ea  mov     [rbx+1C0h], rax
0x18003a9f1  xorps   xmm0, xmm0
0x18003a9f4  mov     [rbx+1C8h], rbx
0x18003a9fb  mov     [rbx+188h], esi
0x18003aa01  mov     [rbx+18Ch], esi
0x18003aa07  mov     rax, [rcx]
0x18003aa0a  mov     [rbx+190h], rax
0x18003aa11  mov     [rbx+198h], esi
0x18003aa17  mov     rax, [rcx]
0x18003aa1a  lea     rcx, [rbx+7E0h]; Mutex
0x18003aa21  mov     [rbx+218h], rax
0x18003aa28  xor     eax, eax
0x18003aa2a  movups  xmmword ptr [rcx], xmm0
0x18003aa2d  movups  xmmword ptr [rcx+10h], xmm0
0x18003aa31  movups  xmmword ptr [rcx+20h], xmm0
0x18003aa35  mov     [rcx+30h], rax
0x18003aa39  call    cs:__imp_KeInitializeGuardedMutex
0x18003aa40  nop     dword ptr [rax+rax+00h]
0x18003aa45  lea     rcx, [rbx+818h]; SpinLock
0x18003aa4c  call    cs:__imp_KeInitializeSpinLock
0x18003aa53  nop     dword ptr [rax+rax+00h]
0x18003aa58  lea     rax, [rbx+1F8h]
0x18003aa5f  lea     rcx, [rbx+208h]; SpinLock
0x18003aa66  mov     [rax+8], rax
0x18003aa6a  mov     [rax], rax
0x18003aa6d  call    cs:__imp_KeInitializeSpinLock
0x18003aa74  nop     dword ptr [rax+rax+00h]
0x18003aa79  lea     rax, [rbx+1A8h]
0x18003aa80  lea     rcx, [rbx+1A0h]; SpinLock
0x18003aa87  mov     [rax+8], rax
0x18003aa8b  mov     [rax], rax
0x18003aa8e  call    cs:__imp_KeInitializeSpinLock
0x18003aa95  nop     dword ptr [rax+rax+00h]
0x18003aa9a  lea     rcx, [rbx+2A0h]; Lock
0x18003aaa1  mov     dword ptr [rbx+1B8h], 0
0x18003aaab  xor     r9d, r9d; HighWatermark
0x18003aaae  mov     [rbx+220h], r13d
0x18003aab5  xor     r8d, r8d; MaxLockedMinutes
0x18003aab8  mov     [rsp+70h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x18003aac0  mov     edx, 43646948h; AllocateTag
0x18003aac5  call    cs:__imp_IoInitializeRemoveLockEx
  ... truncated ...
```
