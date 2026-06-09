# DriverEntry

- ea: `0x18002b078`
- end: `0x18002b6e4`
- name: `DriverEntry`
- size: `1644`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b010`

## callees

- `0x180007ba8`
- `0x180007bd8`
- `0x18000b3c4`
- `0x180010840`
- `0x180010c80`
- `0x18001f4b8`
- `0x180020f30`
- `0x180020f58`
- `0x180020fec`
- `0x180022cc0`
- `0x180023048`
- `0x18002313c`
- `0x1800232d0`
- `0x18002b078`
- `0x18002b6ec`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x18002b27d`
- `ntoskrnl!KeInitializeEvent` at `0x18002b2ab`
- `ntoskrnl!KeInitializeEvent` at `0x18002b2d9`
- `ntoskrnl!KeInitializeEvent` at `0x18002b2f1`
- `ntoskrnl!KeInitializeEvent` at `0x18002b27d`
- `ntoskrnl!KeInitializeEvent` at `0x18002b2ab`
- `ntoskrnl!KeInitializeEvent` at `0x18002b2d9`
- `ntoskrnl!KeInitializeEvent` at `0x18002b2f1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18002b1fa`
- `ntoskrnl!ObOpenObjectByPointer` at `0x18002b1fa`
- `ntoskrnl!IoCreateDevice` at `0x18002b232`
- `ntoskrnl!IoCreateDevice` at `0x18002b232`
- `ntoskrnl!ExRegisterExtension` at `0x18002b32e`
- `ntoskrnl!ExRegisterExtension` at `0x18002b32e`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x18002b3a5`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x18002b669`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x18002b3a5`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx2` at `0x18002b669`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18002b467`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18002b467`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x18002b4ac`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x18002b4ac`
- `ntoskrnl!PsStartSiloMonitor` at `0x18002b4c5`
- `ntoskrnl!PsStartSiloMonitor` at `0x18002b4c5`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18002b510`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x18002b510`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x18002b525`
- `ntoskrnl!IoRegisterShutdownNotification` at `0x18002b525`
- `ntoskrnl!ExUnregisterExtension` at `0x18002b67c`
- `ntoskrnl!ExUnregisterExtension` at `0x18002b67c`
- `ntoskrnl!IoDeleteDevice` at `0x18002b375`
- `ntoskrnl!IoDeleteDevice` at `0x18002b375`
- `ntoskrnl!PsGetCurrentProcess` at `0x18002b1a7`
- `ntoskrnl!PsGetCurrentProcess` at `0x18002b1a7`
- `ntoskrnl!PsGetProcessId` at `0x18002b1bd`
- `ntoskrnl!PsGetProcessId` at `0x18002b1bd`
- `ntoskrnl!ExAllocatePool2` at `0x18002b17e`
- `ntoskrnl!ExAllocatePool2` at `0x18002b17e`
- `ntoskrnl!ZwClose` at `0x18002b388`
- `ntoskrnl!ZwClose` at `0x18002b388`
- `HAL!KeQueryPerformanceCounter` at `0x18002b613`
- `HAL!KeQueryPerformanceCounter` at `0x18002b613`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  NTSTATUS ProcessNotifyRoutineEx2; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-29h] BYREF
  __int128 v13; // [rsp+48h] [rbp-21h] BYREF
  __int128 v14; // [rsp+58h] [rbp-11h]
  __int128 v15; // [rsp+68h] [rbp-1h] BYREF
  __int128 v16; // [rsp+78h] [rbp+Fh]

  DeviceObject = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_SspiKernelTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  v13 = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[3] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[4] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[5] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[10] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)KsecDispatch;
  DriverObject->MajorFunction[16] = (PDRIVER_DISPATCH)KsecDispatch;
  memset(&KsecFastIoDispatch, 0, sizeof(KsecFastIoDispatch));
  KsecFastIoDispatch.SizeOfFastIoDispatch = 224;
  qword_180019490 = (__int64)KsecFastIoDeviceControl;
  DriverObject->FastIoDispatch = &KsecFastIoDispatch;
  KsecRpcLock = 0;
  KsecRpcConnections = (PVOID)ExAllocatePool2(256, 4096, 1667593035);
  if ( !KsecRpcConnections )
    return -1073741670;
  KsecRpcConnectionsSize = 256;
  KsecRpcConnectionsCount = 0;
  WPP_MAIN_CB.DeviceExtension = (PVOID)PsGetCurrentProcess(v4, v3, v5, v6);
  KsecSystemProcessId = (unsigned int)PsGetProcessId((PEPROCESS)WPP_MAIN_CB.DeviceExtension);
  ProcessNotifyRoutineEx2 = ObOpenObjectByPointer(
                              WPP_MAIN_CB.DeviceExtension,
                              0x200u,
                              0,
                              0x440u,
                              0,
                              0,
                              &KsecSystemProcessHandle);
  if ( ProcessNotifyRoutineEx2 < 0 )
    return ProcessNotifyRoutineEx2;
  ProcessNotifyRoutineEx2 = IoCreateDevice(DriverObject, 0, &DeviceName, 0x39u, 0x100u, 0, &DeviceObject);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
LABEL_10:
    ZwClose(KsecSystemProcessHandle);
    return ProcessNotifyRoutineEx2;
  }
  ProcessNotifyRoutineEx2 = KsecSetDeviceSecurity((__int64)DeviceObject);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
LABEL_9:
    IoDeleteDevice(DeviceObject);
    goto LABEL_10;
  }
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 1;
  WPP_MAIN_CB.Dpc.SystemArgument1 = 0;
  LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.Dpc.DpcData, SynchronizationEvent, 0);
  LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = 1;
  WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, SynchronizationEvent, 0);
  *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 1;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = 0;
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink) = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.DeviceQueue.Lock, SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.Queue, NotificationEvent, 0);
  *(_QWORD *)&v13 = 0x7000000010002LL;
  *((_QWORD *)&v13 + 1) = &off_180013188;
  *(_QWORD *)&v14 = 0;
  *((_QWORD *)&v14 + 1) = DriverObject;
  ProcessNotifyRoutineEx2 = ExRegisterExtension(&KsecExtensionRegistration, 65537, &v13);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        18,
        WPP_47798432cc4f3443573e38da5669f213_Traceguids,
        (unsigned int)ProcessNotifyRoutineEx2);
    goto LABEL_9;
  }
  ProcessNotifyRoutineEx2 = PsSetCreateProcessNotifyRoutineEx2(0, KsecCreateProcessNotifyRoutine, 0);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        19,
        WPP_47798432cc4f3443573e38da5669f213_Traceguids,
        (unsigned int)ProcessNotifyRoutineEx2);
    goto LABEL_52;
  }
  ProcessNotifyRoutineEx2 = LoadCngExtension();
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_51;
    v10 = 20;
LABEL_50:
    WPP_SF_D(v9[3], v10, WPP_47798432cc4f3443573e38da5669f213_Traceguids, (unsigned int)ProcessNotifyRoutineEx2);
LABEL_51:
    LOBYTE(v8) = 1;
    PsSetCreateProcessNotifyRoutineEx2(0, KsecCreateProcessNotifyRoutine, v8);
LABEL_52:
    ExUnregisterExtension(KsecExtensionRegistration);
    goto LABEL_9;
  }
  *(_DWORD *)((char *)&v15 + 2) = 0;
  *((_QWORD *)&v15 + 1) = &DriverObject->DriverName;
  WORD3(v15) = 0;
  *(_QWORD *)&v16 = KsecdCreateSiloNotification;
  LOWORD(v15) = 257;
  *((_QWORD *)&v16 + 1) = KsecdTerminateSiloNotification;
  ProcessNotifyRoutineEx2 = PsRegisterSiloMonitor(&v15, &WPP_MAIN_CB.Reserved + 1);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0 )
      goto LABEL_51;
    v10 = 21;
    goto LABEL_50;
  }
  KsecddSiloContextSlot = PsGetSiloMonitorContextSlot(*((_QWORD *)&WPP_MAIN_CB.Reserved + 1));
  ProcessNotifyRoutineEx2 = PsStartSiloMonitor(*((_QWORD *)&WPP_MAIN_CB.Reserved + 1));
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        22,
        WPP_47798432cc4f3443573e38da5669f213_Traceguids,
        (unsigned int)ProcessNotifyRoutineEx2);
    PsUnregisterSiloMonitor(*((_QWORD *)&WPP_MAIN_CB.Reserved + 1));
    goto LABEL_51;
  }
  ProcessNotifyRoutineEx2 = IoRegisterShutdownNotification(DeviceObject);
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_51;
    v10 = 23;
    goto LABEL_50;
  }
  ProcessNotifyRoutineEx2 = KsecPerfCountersInitGlobal();
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_51;
    v10 = 24;
    goto LABEL_50;
  }
  ProcessNotifyRoutineEx2 = IoctlIpcInitGlobal();
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_51;
    v10 = 25;
    goto LABEL_50;
  }
  ProcessNotifyRoutineEx2 = SspiInitAsyncInterface();
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    IoctlIpcCleanupGlobal();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_51;
    v10 = 26;
    goto LABEL_50;
  }
  if ( !(unsigned int)TraceLoggingRegisterEx_EtwRegister_EtwSetInformation() )
    KeQueryPerformanceCounter(&PerformanceFrequency);
  ProcessNotifyRoutineEx2 = wil_InitializeFeatureStaging();
  if ( ProcessNotifyRoutineEx2 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
      goto LABEL_51;
    v10 = 28;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 29, WPP_47798432cc4f3443573e38da5669f213_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18002b078  push    rbp
0x18002b07a  push    rbx
0x18002b07b  push    rsi
0x18002b07c  push    rdi
0x18002b07d  push    r14
0x18002b07f  push    r15
0x18002b081  lea     rbp, [rsp-2Fh]
0x18002b086  sub     rsp, 98h
0x18002b08d  mov     rax, cs:__security_cookie
0x18002b094  xor     rax, rsp
0x18002b097  mov     [rbp+57h+var_38], rax
0x18002b09b  xor     r14d, r14d
0x18002b09e  lea     rax, WPP_ThisDir_CTLGUID_SspiKernelTraceGuid
0x18002b0a5  xorps   xmm0, xmm0
0x18002b0a8  mov     [rbp+57h+DeviceObject], r14
0x18002b0ac  xorps   xmm1, xmm1
0x18002b0af  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x18002b0b6  mov     rdi, rcx
0x18002b0b9  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x18002b0c0  lea     r15d, [r14+1]
0x18002b0c4  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x18002b0cb  mov     cs:WPP_MAIN_CB.Timer, r15
0x18002b0d2  movups  [rbp+57h+var_78], xmm0
0x18002b0d6  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x18002b0dd  movups  [rbp+57h+var_68], xmm0
0x18002b0e1  movups  [rbp+57h+var_58], xmm1
0x18002b0e5  movups  [rbp+57h+var_48], xmm1
0x18002b0e9  call    WppLoadTracingSupport
0x18002b0ee  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x18002b0f5  call    WppInitKm
0x18002b0fa  lea     rax, KsecDispatch
0x18002b101  mov     ebx, 0E0h
0x18002b106  lea     rsi, ?KsecFastIoDispatch@@3U_FAST_IO_DISPATCH@@A; _FAST_IO_DISPATCH KsecFastIoDispatch
0x18002b10d  mov     [rdi+70h], rax
0x18002b111  mov     r8d, ebx; Size
0x18002b114  mov     [rdi+80h], rax
0x18002b11b  mov     rcx, rsi; void *
0x18002b11e  mov     [rdi+88h], rax
0x18002b125  xor     edx, edx; Val
0x18002b127  mov     [rdi+90h], rax
0x18002b12e  mov     [rdi+98h], rax
0x18002b135  mov     [rdi+0C0h], rax
0x18002b13c  mov     [rdi+0E0h], rax
0x18002b143  mov     [rdi+0F0h], rax
0x18002b14a  call    memset
0x18002b14f  lea     rax, KsecFastIoDeviceControl
0x18002b156  mov     cs:?KsecFastIoDispatch@@3U_FAST_IO_DISPATCH@@A, ebx; _FAST_IO_DISPATCH KsecFastIoDispatch
0x18002b15c  mov     cs:qword_180019490, rax
0x18002b163  mov     edx, 1000h
0x18002b168  mov     [rdi+50h], rsi
0x18002b16c  mov     r8d, 6365734Bh
0x18002b172  lea     esi, [rbx+20h]
0x18002b175  mov     cs:?KsecRpcLock@@3U_EX_PUSH_LOCK@@A, r14; _EX_PUSH_LOCK KsecRpcLock
0x18002b17c  mov     ecx, esi
0x18002b17e  call    cs:__imp_ExAllocatePool2
0x18002b185  nop     dword ptr [rax+rax+00h]
0x18002b18a  mov     cs:?KsecRpcConnections@@3PEAU_KSEC_RPC_CONNECTION@@EA, rax; _KSEC_RPC_CONNECTION * KsecRpcConnections
0x18002b191  test    rax, rax
0x18002b194  jz      loc_18002B6C0
0x18002b19a  mov     cs:?KsecRpcConnectionsSize@@3KA, esi; ulong KsecRpcConnectionsSize
0x18002b1a0  mov     cs:?KsecRpcConnectionsCount@@3KA, r14d; ulong KsecRpcConnectionsCount
0x18002b1a7  call    cs:__imp_PsGetCurrentProcess
0x18002b1ae  nop     dword ptr [rax+rax+00h]
0x18002b1b3  mov     rcx, rax; Process
0x18002b1b6  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x18002b1bd  call    cs:__imp_PsGetProcessId
0x18002b1c4  nop     dword ptr [rax+rax+00h]
0x18002b1c9  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension; Object
0x18002b1d0  mov     r9d, 440h; DesiredAccess
0x18002b1d6  mov     cs:KsecSystemProcessId, eax
0x18002b1dc  xor     r8d, r8d; PassedAccessState
0x18002b1df  lea     rax, KsecSystemProcessHandle
0x18002b1e6  mov     edx, 200h; HandleAttributes
0x18002b1eb  mov     [rsp+0C0h+Handle], rax; Handle
0x18002b1f0  mov     [rsp+0C0h+AccessMode], r14b; AccessMode
0x18002b1f5  mov     [rsp+0C0h+ObjectType], r14; ObjectType
0x18002b1fa  call    cs:__imp_ObOpenObjectByPointer
0x18002b201  nop     dword ptr [rax+rax+00h]
0x18002b206  mov     ebx, eax
0x18002b208  test    eax, eax
0x18002b20a  js      loc_18002B6C5
0x18002b210  lea     rax, [rbp+57h+DeviceObject]
0x18002b214  xor     edx, edx; DeviceExtensionSize
0x18002b216  mov     [rsp+0C0h+Handle], rax; DeviceObject
0x18002b21b  lea     r9d, [r14+39h]; DeviceType
0x18002b21f  mov     [rsp+0C0h+AccessMode], r14b; Exclusive
0x18002b224  lea     r8, DeviceName; DeviceName
0x18002b22b  mov     rcx, rdi; DriverObject
0x18002b22e  mov     dword ptr [rsp+0C0h+ObjectType], esi; DeviceCharacteristics
0x18002b232  call    cs:__imp_IoCreateDevice
0x18002b239  nop     dword ptr [rax+rax+00h]
0x18002b23e  mov     ebx, eax
0x18002b240  test    eax, eax
0x18002b242  js      loc_18002B381
0x18002b248  mov     rcx, [rbp+57h+DeviceObject]
0x18002b24c  call    KsecSetDeviceSecurity
0x18002b251  mov     ebx, eax
0x18002b253  test    eax, eax
0x18002b255  js      loc_18002B371
0x18002b25b  xor     r8d, r8d; State
0x18002b25e  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, r15d
0x18002b265  mov     edx, r15d; Type
0x18002b268  mov     cs:WPP_MAIN_CB.Dpc.SystemArgument1, r14
0x18002b26f  lea     rcx, WPP_MAIN_CB.Dpc.DpcData; Event
0x18002b276  mov     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, r14d
0x18002b27d  call    cs:__imp_KeInitializeEvent
0x18002b284  nop     dword ptr [rax+rax+00h]
0x18002b289  xor     r8d, r8d; State
0x18002b28c  mov     dword ptr cs:WPP_MAIN_CB.Queue+18h, r15d
0x18002b293  mov     edx, r15d; Type
0x18002b296  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, r14
0x18002b29d  lea     rcx, WPP_MAIN_CB.Queue+30h; Event
0x18002b2a4  mov     dword ptr cs:WPP_MAIN_CB.Queue+28h, r14d
0x18002b2ab  call    cs:__imp_KeInitializeEvent
0x18002b2b2  nop     dword ptr [rax+rax+00h]
0x18002b2b7  xor     r8d, r8d; State
0x18002b2ba  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, r15d
0x18002b2c1  mov     edx, r15d; Type
0x18002b2c4  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, r14
0x18002b2cb  lea     rcx, WPP_MAIN_CB.DeviceQueue.Lock; Event
0x18002b2d2  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, r14d
0x18002b2d9  call    cs:__imp_KeInitializeEvent
0x18002b2e0  nop     dword ptr [rax+rax+00h]
0x18002b2e5  xor     r8d, r8d; State
0x18002b2e8  lea     rcx, WPP_MAIN_CB.Queue; Event
0x18002b2ef  xor     edx, edx; Type
0x18002b2f1  call    cs:__imp_KeInitializeEvent
0x18002b2f8  nop     dword ptr [rax+rax+00h]
0x18002b2fd  lea     rax, off_180013188
0x18002b304  mov     dword ptr [rbp+57h+var_78], 10002h
0x18002b30b  lea     r8, [rbp+57h+var_78]
0x18002b30f  mov     qword ptr [rbp+57h+var_78+8], rax
0x18002b313  mov     edx, 10001h
0x18002b318  mov     dword ptr [rbp+57h+var_78+4], 70000h
0x18002b31f  lea     rcx, ?KsecExtensionRegistration@@3PEAU_EX_EXTENSION@@EA; _EX_EXTENSION * KsecExtensionRegistration
0x18002b326  mov     qword ptr [rbp+57h+var_68], r14
0x18002b32a  mov     qword ptr [rbp+57h+var_68+8], rdi
0x18002b32e  call    cs:__imp_ExRegisterExtension
0x18002b335  nop     dword ptr [rax+rax+00h]
0x18002b33a  mov     ebx, eax
0x18002b33c  test    eax, eax
0x18002b33e  jns     short loc_18002B399
0x18002b340  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b347  lea     rax, WPP_GLOBAL_Control
0x18002b34e  cmp     rcx, rax
0x18002b351  jz      short loc_18002B371
0x18002b353  mov     eax, [rcx+2Ch]
0x18002b356  test    al, 4
0x18002b358  jz      short loc_18002B371
0x18002b35a  mov     rcx, [rcx+18h]
0x18002b35e  lea     edx, [r14+12h]
0x18002b362  mov     r9d, ebx
0x18002b365  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x18002b36c  call    WPP_SF_D
0x18002b371  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x18002b375  call    cs:__imp_IoDeleteDevice
0x18002b37c  nop     dword ptr [rax+rax+00h]
0x18002b381  mov     rcx, cs:KsecSystemProcessHandle; Handle
0x18002b388  call    cs:__imp_ZwClose
0x18002b38f  nop     dword ptr [rax+rax+00h]
0x18002b394  jmp     loc_18002B6C5
0x18002b399  xor     r8d, r8d
0x18002b39c  lea     rdx, KsecCreateProcessNotifyRoutine
0x18002b3a3  xor     ecx, ecx
0x18002b3a5  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx2
0x18002b3ac  nop     dword ptr [rax+rax+00h]
0x18002b3b1  mov     ebx, eax
0x18002b3b3  test    eax, eax
0x18002b3b5  jns     short loc_18002B3F7
0x18002b3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3be  lea     rax, WPP_GLOBAL_Control
0x18002b3c5  cmp     rcx, rax
0x18002b3c8  jz      loc_18002B675
0x18002b3ce  mov     eax, [rcx+2Ch]
0x18002b3d1  test    r15b, al
0x18002b3d4  jz      loc_18002B675
0x18002b3da  mov     rcx, [rcx+18h]
0x18002b3de  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x18002b3e5  mov     edx, 13h
0x18002b3ea  mov     r9d, ebx
0x18002b3ed  call    WPP_SF_D
0x18002b3f2  jmp     loc_18002B675
0x18002b3f7  call    ?LoadCngExtension@@YAJXZ; LoadCngExtension(void)
0x18002b3fc  mov     ebx, eax
0x18002b3fe  test    eax, eax
0x18002b400  jns     short loc_18002B42F
0x18002b402  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b409  lea     rax, WPP_GLOBAL_Control
0x18002b410  cmp     rcx, rax
0x18002b413  jz      loc_18002B65D
0x18002b419  mov     eax, [rcx+2Ch]
0x18002b41c  test    r15b, al
0x18002b41f  jz      loc_18002B65D
0x18002b425  mov     edx, 14h
0x18002b42a  jmp     loc_18002B64A
0x18002b42f  lea     rax, [rdi+38h]
0x18002b433  mov     dword ptr [rbp+57h+var_58+2], r14d
0x18002b437  mov     qword ptr [rbp+57h+var_58+8], rax
0x18002b43b  lea     rdx, WPP_MAIN_CB+148h
0x18002b442  lea     rax, KsecdCreateSiloNotification
0x18002b449  mov     word ptr [rbp+57h+var_58+6], r14w
0x18002b44e  mov     qword ptr [rbp+57h+var_48], rax
0x18002b452  lea     rcx, [rbp+57h+var_58]
0x18002b456  lea     rax, KsecdTerminateSiloNotification
0x18002b45d  mov     word ptr [rbp+57h+var_58], 101h
0x18002b463  mov     qword ptr [rbp+57h+var_48+8], rax
0x18002b467  call    cs:__imp_PsRegisterSiloMonitor
0x18002b46e  nop     dword ptr [rax+rax+00h]
0x18002b473  mov     ebx, eax
0x18002b475  test    eax, eax
0x18002b477  jns     short loc_18002B4A5
0x18002b479  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b480  lea     rax, WPP_GLOBAL_Control
0x18002b487  cmp     rcx, rax
0x18002b48a  jz      loc_18002B65D
0x18002b490  mov     eax, [rcx+2Ch]
0x18002b493  test    al, 4
0x18002b495  jz      loc_18002B65D
0x18002b49b  mov     edx, 15h
0x18002b4a0  jmp     loc_18002B64A
0x18002b4a5  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x18002b4ac  call    cs:__imp_PsGetSiloMonitorContextSlot
0x18002b4b3  nop     dword ptr [rax+rax+00h]
0x18002b4b8  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x18002b4bf  mov     cs:?KsecddSiloContextSlot@@3KA, eax; ulong KsecddSiloContextSlot
0x18002b4c5  call    cs:__imp_PsStartSiloMonitor
0x18002b4cc  nop     dword ptr [rax+rax+00h]
0x18002b4d1  mov     ebx, eax
0x18002b4d3  test    eax, eax
0x18002b4d5  jns     short loc_18002B521
0x18002b4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4de  lea     rax, WPP_GLOBAL_Control
0x18002b4e5  cmp     rcx, rax
0x18002b4e8  jz      short loc_18002B509
0x18002b4ea  mov     eax, [rcx+2Ch]
0x18002b4ed  test    al, 4
0x18002b4ef  jz      short loc_18002B509
0x18002b4f1  mov     rcx, [rcx+18h]
0x18002b4f5  lea     r8, WPP_47798432cc4f3443573e38da5669f213_Traceguids
0x18002b4fc  mov     edx, 16h
0x18002b501  mov     r9d, ebx
0x18002b504  call    WPP_SF_D
0x18002b509  mov     rcx, qword ptr cs:WPP_MAIN_CB+148h
0x18002b510  call    cs:__imp_PsUnregisterSiloMonitor
0x18002b517  nop     dword ptr [rax+rax+00h]
0x18002b51c  jmp     loc_18002B65D
0x18002b521  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x18002b525  call    cs:__imp_IoRegisterShutdownNotification
0x18002b52c  nop     dword ptr [rax+rax+00h]
0x18002b531  mov     ebx, eax
0x18002b533  test    eax, eax
0x18002b535  jns     short loc_18002B564
0x18002b537  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b53e  lea     rax, WPP_GLOBAL_Control
0x18002b545  cmp     rcx, rax
0x18002b548  jz      loc_18002B65D
0x18002b54e  mov     eax, [rcx+2Ch]
0x18002b551  test    r15b, al
0x18002b554  jz      loc_18002B65D
0x18002b55a  mov     edx, 17h
0x18002b55f  jmp     loc_18002B64A
0x18002b564  call    KsecPerfCountersInitGlobal
0x18002b569  mov     ebx, eax
0x18002b56b  test    eax, eax
0x18002b56d  jns     short loc_18002B59C
0x18002b56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b576  lea     rax, WPP_GLOBAL_Control
0x18002b57d  cmp     rcx, rax
0x18002b580  jz      loc_18002B65D
0x18002b586  mov     eax, [rcx+2Ch]
0x18002b589  test    r15b, al
0x18002b58c  jz      loc_18002B65D
0x18002b592  mov     edx, 18h
0x18002b597  jmp     loc_18002B64A
0x18002b59c  call    IoctlIpcInitGlobal
0x18002b5a1  mov     ebx, eax
0x18002b5a3  test    eax, eax
0x18002b5a5  jns     short loc_18002B5D1
0x18002b5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5ae  lea     rax, WPP_GLOBAL_Control
0x18002b5b5  cmp     rcx, rax
0x18002b5b8  jz      loc_18002B65D
0x18002b5be  mov     eax, [rcx+2Ch]
0x18002b5c1  test    r15b, al
0x18002b5c4  jz      loc_18002B65D
0x18002b5ca  mov     edx, 19h
0x18002b5cf  jmp     short loc_18002B64A
0x18002b5d1  call    SspiInitAsyncInterface
0x18002b5d6  mov     ebx, eax
0x18002b5d8  test    eax, eax
0x18002b5da  jns     short loc_18002B603
0x18002b5dc  call    IoctlIpcCleanupGlobal
0x18002b5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5e8  lea     rax, WPP_GLOBAL_Control
0x18002b5ef  cmp     rcx, rax
0x18002b5f2  jz      short loc_18002B65D
0x18002b5f4  mov     eax, [rcx+2Ch]
0x18002b5f7  test    r15b, al
0x18002b5fa  jz      short loc_18002B65D
0x18002b5fc  mov     edx, 1Ah
  ... truncated ...
```
