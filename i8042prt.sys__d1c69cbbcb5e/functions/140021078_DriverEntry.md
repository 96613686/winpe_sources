# DriverEntry

- ea: `0x140021078`
- end: `0x1400213e6`
- name: `DriverEntry`
- size: `878`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140021010`

## callees

- `0x140004530`
- `0x140007b10`
- `0x140009f9c`
- `0x14000db80`
- `0x14000de80`
- `0x140017504`
- `0x1400175b0`
- `0x1400175e8`
- `0x14001769c`
- `0x140017764`
- `0x140017b4c`
- `0x140021078`
- `0x1400213ec`
- `0x1400219d8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140021123`
- `ntoskrnl!ExAllocatePool2` at `0x140021188`
- `ntoskrnl!ExAllocatePool2` at `0x140021123`
- `ntoskrnl!ExAllocatePool2` at `0x140021188`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021204`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002121e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021204`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002121e`
- `ntoskrnl!KeInitializeEvent` at `0x1400212a0`
- `ntoskrnl!KeInitializeEvent` at `0x1400212a0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400212ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400212d4`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400212ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400212d4`
- `ntoskrnl!KeInitializeTimer` at `0x1400212eb`
- `ntoskrnl!KeInitializeTimer` at `0x1400212eb`
- `ntoskrnl!IoDeleteController` at `0x1400211ef`
- `ntoskrnl!IoDeleteController` at `0x1400211ef`
- `ntoskrnl!IoCreateController` at `0x140021144`
- `ntoskrnl!IoCreateController` at `0x140021144`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v4; // r9
  __int64 v5; // rsi
  __int64 v6; // r9
  struct _KDPC *Pool2; // rax
  int v8; // edx
  struct _CONTROLLER_OBJECT *v9; // rcx
  int v11; // edx

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_I8042prtTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  wil_InitializeFeatureStaging();
  memset(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0, 0x88u);
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = ExAllocatePool2(64, 248, 842281016, v4);
  v5 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  if ( !*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
    || (*(_QWORD *)(v5 + 8) = IoCreateController(0),
        !*(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL)) )
  {
LABEL_6:
    if ( *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels )
    {
      v9 = *(struct _CONTROLLER_OBJECT **)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL);
      if ( v9 )
        IoDeleteController(v9);
      ExFreePoolWithTag(*(PVOID *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels, 0);
    }
    if ( WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
      ExFreePoolWithTag(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, 0);
    TraceLoggingDriverLoaded(3221225626LL);
    wil_UninitializeFeatureStaging();
    TraceLoggingUnregister_EtwUnregister();
    WppCleanupKm(DriverObject);
    return -1073741670;
  }
  WORD1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) = RegistryPath->Length + 2;
  LOWORD(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) = RegistryPath->Length;
  Pool2 = (struct _KDPC *)ExAllocatePool2(64, WORD1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp), 842281016, v6);
  WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        17,
        10,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    goto LABEL_6;
  }
  memmove(Pool2, RegistryPath->Buffer, RegistryPath->Length);
  I8xServiceParameters(DriverObject);
  LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = 1;
  WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = 0;
  LODWORD(WPP_MAIN_CB.DeviceQueue.Lock) = 0;
  KeInitializeEvent((PRKEVENT)&WPP_MAIN_CB.DeviceQueue.32, SynchronizationEvent, 0);
  KeInitializeSpinLock((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 184LL));
  KeInitializeSpinLock((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 192LL));
  KeInitializeTimer((PKTIMER)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 120LL));
  *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 204LL) = -1;
  DriverObject->DriverStartIo = (PDRIVER_STARTIO)I8xStartIo;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)I8xUnload;
  DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)I8xAddDevice;
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)&I8xCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&I8xClose;
  DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)I8xInternalDeviceControl;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)&I8xDeviceControl;
  DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)I8xFlush;
  DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)I8xPnP;
  DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)I8xPower;
  DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)I8xSystemControl;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      15,
      11,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      0);
  TraceLoggingDriverLoaded(0);
  return 0;
}

```

## disassembly

```asm
0x140021078  mov     [rsp+arg_0], rbx
0x14002107d  mov     [rsp+arg_8], rsi
0x140021082  push    rdi
0x140021083  sub     rsp, 30h
0x140021087  lea     rax, WPP_ThisDir_CTLGUID_I8042prtTraceGuid
0x14002108e  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x140021099  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400210a0  mov     rdi, rdx
0x1400210a3  xor     eax, eax
0x1400210a5  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400210b0  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x1400210b6  mov     rbx, rcx
0x1400210b9  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400210c4  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400210cf  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400210da  call    WppLoadTracingSupport
0x1400210df  mov     rdx, rdi
0x1400210e2  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400210ed  mov     rcx, rbx
0x1400210f0  call    WppInitKm
0x1400210f5  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400210fa  call    wil_InitializeFeatureStaging
0x1400210ff  xor     edx, edx; Val
0x140021101  lea     rcx, WPP_MAIN_CB.Queue+10h; void *
0x140021108  mov     r8d, 88h; Size
0x14002110e  call    memset
0x140021113  mov     edx, 0F8h
0x140021118  mov     ecx, 40h ; '@'
0x14002111d  mov     r8d, 32343038h
0x140021123  call    cs:__imp_ExAllocatePool2
0x14002112a  nop     dword ptr [rax+rax+00h]
0x14002112f  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rax
0x140021136  mov     rsi, rax
0x140021139  test    rax, rax
0x14002113c  jz      loc_1400211DA
0x140021142  xor     ecx, ecx; Size
0x140021144  call    cs:__imp_IoCreateController
0x14002114b  nop     dword ptr [rax+rax+00h]
0x140021150  mov     [rsi+8], rax
0x140021154  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14002115b  cmp     qword ptr [rax+8], 0
0x140021160  jz      short loc_1400211DA
0x140021162  movzx   eax, word ptr [rdi]
0x140021165  mov     ecx, 40h ; '@'
0x14002116a  add     ax, 2
0x14002116e  mov     r8d, 32343038h
0x140021174  movzx   edx, ax
0x140021177  mov     word ptr cs:WPP_MAIN_CB.Queue+3Ah, dx
0x14002117e  movzx   eax, word ptr [rdi]
0x140021181  mov     word ptr cs:WPP_MAIN_CB.Queue+38h, ax
0x140021188  call    cs:__imp_ExAllocatePool2
0x14002118f  nop     dword ptr [rax+rax+00h]
0x140021194  mov     qword ptr cs:WPP_MAIN_CB.Queue+40h, rax
0x14002119b  test    rax, rax
0x14002119e  jnz     loc_14002125B
0x1400211a4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400211ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400211b2  jz      short loc_1400211DA
0x1400211b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211bb  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x1400211c2  mov     r9d, 0Ah
0x1400211c8  mov     [rsp+38h+var_18], rax
0x1400211cd  mov     rcx, [rcx+40h]
0x1400211d1  lea     r8d, [r9+7]
0x1400211d5  call    WPP_RECORDER_SF_
0x1400211da  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400211e1  test    rax, rax
0x1400211e4  jz      short loc_140021210
0x1400211e6  mov     rcx, [rax+8]; ControllerObject
0x1400211ea  test    rcx, rcx
0x1400211ed  jz      short loc_1400211FB
0x1400211ef  call    cs:__imp_IoDeleteController
0x1400211f6  nop     dword ptr [rax+rax+00h]
0x1400211fb  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h; P
0x140021202  xor     edx, edx; Tag
0x140021204  call    cs:__imp_ExFreePoolWithTag
0x14002120b  nop     dword ptr [rax+rax+00h]
0x140021210  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h; P
0x140021217  test    rcx, rcx
0x14002121a  jz      short loc_14002122A
0x14002121c  xor     edx, edx; Tag
0x14002121e  call    cs:__imp_ExFreePoolWithTag
0x140021225  nop     dword ptr [rax+rax+00h]
0x14002122a  mov     edi, 0C000009Ah
0x14002122f  mov     ecx, edi
0x140021231  call    TraceLoggingDriverLoaded
0x140021236  call    wil_UninitializeFeatureStaging
0x14002123b  call    TraceLoggingUnregister_EtwUnregister
0x140021240  mov     rcx, rbx
0x140021243  call    WppCleanupKm
0x140021248  mov     eax, edi
0x14002124a  mov     rbx, [rsp+38h+arg_0]
0x14002124f  mov     rsi, [rsp+38h+arg_8]
0x140021254  add     rsp, 30h
0x140021258  pop     rdi
0x140021259  retn
0x14002125b  movzx   r8d, word ptr [rdi]; Size
0x14002125f  mov     rcx, rax; void *
0x140021262  mov     rdx, [rdi+8]; Src
0x140021266  call    memmove
0x14002126b  mov     rcx, rbx
0x14002126e  call    I8xServiceParameters
0x140021273  xor     r8d, r8d; State
0x140021276  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, 1
0x140021280  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h; Event
0x140021287  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, 0
0x140021292  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.Lock, 0
0x14002129c  lea     edx, [r8+1]; Type
0x1400212a0  call    cs:__imp_KeInitializeEvent
0x1400212a7  nop     dword ptr [rax+rax+00h]
0x1400212ac  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400212b3  add     rcx, 0B8h; SpinLock
0x1400212ba  call    cs:__imp_KeInitializeSpinLock
0x1400212c1  nop     dword ptr [rax+rax+00h]
0x1400212c6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400212cd  add     rcx, 0C0h; SpinLock
0x1400212d4  call    cs:__imp_KeInitializeSpinLock
0x1400212db  nop     dword ptr [rax+rax+00h]
0x1400212e0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400212e7  add     rcx, 78h ; 'x'; Timer
0x1400212eb  call    cs:__imp_KeInitializeTimer
0x1400212f2  nop     dword ptr [rax+rax+00h]
0x1400212f7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400212fe  lea     rcx, I8xAddDevice
0x140021305  mov     dword ptr [rax+0CCh], 0FFFFFFFFh
0x14002130f  lea     rax, I8xStartIo
0x140021316  mov     [rbx+60h], rax
0x14002131a  lea     rax, I8xUnload
0x140021321  mov     [rbx+68h], rax
0x140021325  mov     rax, [rbx+30h]
0x140021329  mov     [rax+8], rcx
0x14002132d  lea     rax, I8xCreate
0x140021334  mov     [rbx+70h], rax
0x140021338  lea     rax, I8xClose
0x14002133f  mov     [rbx+80h], rax
0x140021346  lea     rax, I8xInternalDeviceControl
0x14002134d  mov     [rbx+0E8h], rax
0x140021354  lea     rax, I8xDeviceControl
0x14002135b  mov     [rbx+0E0h], rax
0x140021362  lea     rax, I8xFlush
0x140021369  mov     [rbx+0B8h], rax
0x140021370  lea     rax, I8xPnP
0x140021377  mov     [rbx+148h], rax
0x14002137e  lea     rax, I8xPower
0x140021385  mov     [rbx+120h], rax
0x14002138c  lea     rax, I8xSystemControl
0x140021393  mov     [rbx+128h], rax
0x14002139a  lea     rax, WPP_RECORDER_INITIALIZED
0x1400213a1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400213a8  jz      short loc_1400213D8
0x1400213aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213b1  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x1400213b8  mov     r9d, 0Bh
0x1400213be  mov     [rsp+38h+var_10], 0
0x1400213c6  mov     [rsp+38h+var_18], rax
0x1400213cb  mov     rcx, [rcx+40h]
0x1400213cf  lea     r8d, [r9+4]
0x1400213d3  call    WPP_RECORDER_SF_D
0x1400213d8  xor     ecx, ecx
0x1400213da  call    TraceLoggingDriverLoaded
0x1400213df  xor     eax, eax
0x1400213e1  jmp     loc_14002124A
```
