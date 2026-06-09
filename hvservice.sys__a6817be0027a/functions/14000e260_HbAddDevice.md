# HbAddDevice

- ea: `0x14000e260`
- end: `0x14000e51a`
- name: `HbAddDevice`
- size: `698`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001600`
- `0x14000e260`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000e44a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e44a`
- `ntoskrnl!IoDeleteDevice` at `0x14000e4cd`
- `ntoskrnl!IoDeleteDevice` at `0x14000e4cd`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14000e3b5`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14000e3b5`
- `ntoskrnl!PoSetPowerState` at `0x14000e3f4`
- `ntoskrnl!PoSetPowerState` at `0x14000e3f4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000e4a2`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000e4a2`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14000e408`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14000e408`
- `ntoskrnl!IoCreateDevice` at `0x14000e350`
- `ntoskrnl!IoCreateDevice` at `0x14000e350`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000e461`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14000e461`
- `ntoskrnl!KeInitializeTimerEx` at `0x14000e3da`
- `ntoskrnl!KeInitializeTimerEx` at `0x14000e3da`
- `ntoskrnl!IoDetachDevice` at `0x14000e4b7`
- `ntoskrnl!IoDetachDevice` at `0x14000e4b7`
- `HAL!KeQueryPerformanceCounter` at `0x14000e285`
- `HAL!KeQueryPerformanceCounter` at `0x14000e285`

## string_xrefs

- `0x14000e362`: `IoCreateDevice failed with 0x%x`
- `0x14000e43f`: `\DosDevices\HvServiceDevice`
- `0x14000e473`: `IoCreateSymbolicLink failed with 0x%x`
- `0x14000e4e5`: `Completed with status 0x%x`

## pseudocode

```c
__int64 __fastcall HbAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v5; // rdx
  LONGLONG v6; // rcx
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  char *DeviceExtension; // rdi
  PDEVICE_OBJECT v10; // rax
  NTSTATUS SymbolicLink; // eax
  struct _DEVICE_OBJECT *v12; // rcx
  PDEVICE_OBJECT SourceDevice; // [rsp+60h] [rbp+18h] BYREF

  SourceDevice = 0;
  PerformanceCounter = KeQueryPerformanceCounter(&PerformanceFrequency);
  qword_1400091F0 = PerformanceCounter.QuadPart;
  v5 = qword_1400091D8[3 * HbDriverLastRecordedLifecyclePhase];
  if ( v5 && PerformanceCounter.QuadPart && PerformanceFrequency.QuadPart )
    v6 = 1000 * (PerformanceCounter.QuadPart - v5) / PerformanceFrequency.QuadPart;
  else
    v6 = 0;
  HbpTraceEvent(
    3,
    "HbRecordPhaseTimestamp",
    185,
    "Phase %s reached (%llu ms since %s)",
    "Load.AddDevice",
    v6,
    HbDriverPhaseNames[HbDriverLastRecordedLifecyclePhase]);
  HbDriverLastRecordedLifecyclePhase = 1;
  v7 = IoCreateDevice(DriverObject, 0x160u, (PUNICODE_STRING)&HbpNameOfHvBootDevice, 0x22u, 0x100u, 0, &SourceDevice);
  v8 = v7;
  if ( v7 >= 0 )
  {
    DeviceExtension = (char *)SourceDevice->DeviceExtension;
    *(_QWORD *)DeviceExtension = SourceDevice;
    *((_QWORD *)DeviceExtension + 2) = TargetDevice;
    *((_QWORD *)DeviceExtension + 3) = 0;
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)DeviceExtension + 2, 0x6C526248u, 0, 0, 0x20u);
    SourceDevice->Flags |= 0x2000u;
    SourceDevice->Flags |= 4u;
    KeInitializeTimerEx((PKTIMER)(DeviceExtension + 96), NotificationTimer);
    PoSetPowerState(SourceDevice, DevicePowerState, (POWER_STATE)4);
    v10 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
    *((_QWORD *)DeviceExtension + 3) = v10;
    if ( v10 )
    {
      RtlInitUnicodeString((PUNICODE_STRING)DeviceExtension + 3, L"\\DosDevices\\HvServiceDevice");
      SymbolicLink = IoCreateSymbolicLink((PUNICODE_STRING)DeviceExtension + 3, (PUNICODE_STRING)&HbpNameOfHvBootDevice);
      v8 = SymbolicLink;
      if ( SymbolicLink >= 0 )
      {
        SourceDevice->Flags &= ~0x80u;
        goto LABEL_20;
      }
      HbpTraceEvent(0, "HbAddDevice", 324, "IoCreateSymbolicLink failed with 0x%x", SymbolicLink);
    }
    else
    {
      HbpTraceEvent(0, "HbAddDevice", 315, "IoAttachDeviceToDeviceStack failed");
      v8 = -1073741810;
    }
    if ( DeviceExtension )
    {
      if ( *((_QWORD *)DeviceExtension + 7) )
        IoDeleteSymbolicLink((PUNICODE_STRING)DeviceExtension + 3);
      v12 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 3);
      if ( v12 )
        IoDetachDevice(v12);
    }
  }
  else
  {
    HbpTraceEvent(0, "HbAddDevice", 286, "IoCreateDevice failed with 0x%x", v7);
  }
  if ( SourceDevice )
    IoDeleteDevice(SourceDevice);
LABEL_20:
  HbpTraceEvent(2, "HbAddDevice", 352, "Completed with status 0x%x", v8);
  return v8;
}

```

## disassembly

```asm
0x14000e260  mov     [rsp+arg_0], rbx
0x14000e265  mov     [rsp+arg_8], rsi
0x14000e26a  push    rdi
0x14000e26b  sub     rsp, 40h
0x14000e26f  mov     rbx, rcx
0x14000e272  mov     [rsp+48h+SourceDevice], 0
0x14000e27b  lea     rcx, PerformanceFrequency; PerformanceFrequency
0x14000e282  mov     rsi, rdx
0x14000e285  call    cs:__imp_KeQueryPerformanceCounter
0x14000e28c  nop     dword ptr [rax+rax+00h]
0x14000e291  mov     cs:qword_1400091F0, rax
0x14000e298  movsxd  r9, cs:HbDriverLastRecordedLifecyclePhase
0x14000e29f  lea     r10, cs:140000000h
0x14000e2a6  lea     r8, [r9+r9*2]
0x14000e2aa  mov     rdx, rva qword_1400091D8[r10+r8*8]
0x14000e2b2  test    rdx, rdx
0x14000e2b5  jz      short loc_14000E2DC
0x14000e2b7  test    rax, rax
0x14000e2ba  jz      short loc_14000E2DC
0x14000e2bc  mov     rcx, qword ptr cs:PerformanceFrequency
0x14000e2c3  test    rcx, rcx
0x14000e2c6  jz      short loc_14000E2DC
0x14000e2c8  sub     rax, rdx
0x14000e2cb  imul    rax, 3E8h
0x14000e2d2  cqo
0x14000e2d4  idiv    rcx
0x14000e2d7  mov     rcx, rax
0x14000e2da  jmp     short loc_14000E2DE
0x14000e2dc  xor     ecx, ecx
0x14000e2de  mov     rax, ds:rva HbDriverPhaseNames[r10+r9*8]
0x14000e2e6  lea     rdx, aHbrecordphaset; "HbRecordPhaseTimestamp"
0x14000e2ed  mov     [rsp+48h+DeviceObject], rax
0x14000e2f2  lea     r9, aPhaseSReachedL; "Phase %s reached (%llu ms since %s)"
0x14000e2f9  mov     rax, cs:off_140005008; "Load.AddDevice"
0x14000e300  mov     r8d, 0B9h
0x14000e306  mov     qword ptr [rsp+48h+Exclusive], rcx
0x14000e30b  mov     ecx, 3
0x14000e310  mov     qword ptr [rsp+48h+DeviceCharacteristics], rax
0x14000e315  call    HbpTraceEvent
0x14000e31a  lea     rax, [rsp+48h+SourceDevice]
0x14000e31f  mov     cs:HbDriverLastRecordedLifecyclePhase, 1
0x14000e329  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x14000e32e  lea     r8, HbpNameOfHvBootDevice; DeviceName
0x14000e335  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14000e33a  mov     r9d, 22h ; '"'; DeviceType
0x14000e340  mov     edx, 160h; DeviceExtensionSize
0x14000e345  mov     [rsp+48h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14000e34d  mov     rcx, rbx; DriverObject
0x14000e350  call    cs:__imp_IoCreateDevice
0x14000e357  nop     dword ptr [rax+rax+00h]
0x14000e35c  mov     ebx, eax
0x14000e35e  test    eax, eax
0x14000e360  jns     short loc_14000E386
0x14000e362  lea     r9, aIocreatedevice; "IoCreateDevice failed with 0x%x"
0x14000e369  mov     [rsp+48h+DeviceCharacteristics], eax
0x14000e36d  mov     r8d, 11Eh
0x14000e373  lea     rdx, aHbadddevice; "HbAddDevice"
0x14000e37a  xor     ecx, ecx
0x14000e37c  call    HbpTraceEvent
0x14000e381  jmp     loc_14000E4C3
0x14000e386  mov     rax, [rsp+48h+SourceDevice]
0x14000e38b  xor     r9d, r9d; HighWatermark
0x14000e38e  xor     r8d, r8d; MaxLockedMinutes
0x14000e391  mov     [rsp+48h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x14000e399  mov     edx, 6C526248h; AllocateTag
0x14000e39e  mov     rdi, [rax+40h]
0x14000e3a2  lea     rcx, [rdi+40h]; Lock
0x14000e3a6  mov     [rdi], rax
0x14000e3a9  mov     [rdi+10h], rsi
0x14000e3ad  mov     qword ptr [rdi+18h], 0
0x14000e3b5  call    cs:__imp_IoInitializeRemoveLockEx
0x14000e3bc  nop     dword ptr [rax+rax+00h]
0x14000e3c1  mov     rax, [rsp+48h+SourceDevice]
0x14000e3c6  lea     rcx, [rdi+60h]; Timer
0x14000e3ca  xor     edx, edx; Type
0x14000e3cc  bts     dword ptr [rax+30h], 0Dh
0x14000e3d1  mov     rax, [rsp+48h+SourceDevice]
0x14000e3d6  or      dword ptr [rax+30h], 4
0x14000e3da  call    cs:__imp_KeInitializeTimerEx
0x14000e3e1  nop     dword ptr [rax+rax+00h]
0x14000e3e6  mov     rcx, [rsp+48h+SourceDevice]; DeviceObject
0x14000e3eb  mov     edx, 1; Type
0x14000e3f0  lea     r8d, [rdx+3]; State
0x14000e3f4  call    cs:__imp_PoSetPowerState
0x14000e3fb  nop     dword ptr [rax+rax+00h]
0x14000e400  mov     rcx, [rsp+48h+SourceDevice]; SourceDevice
0x14000e405  mov     rdx, rsi; TargetDevice
0x14000e408  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14000e40f  nop     dword ptr [rax+rax+00h]
0x14000e414  mov     [rdi+18h], rax
0x14000e418  test    rax, rax
0x14000e41b  jnz     short loc_14000E43F
0x14000e41d  lea     r9, aIoattachdevice; "IoAttachDeviceToDeviceStack failed"
0x14000e424  mov     r8d, 13Bh
0x14000e42a  lea     rdx, aHbadddevice; "HbAddDevice"
0x14000e431  xor     ecx, ecx
0x14000e433  call    HbpTraceEvent
0x14000e438  mov     ebx, 0C000000Eh
0x14000e43d  jmp     short loc_14000E492
0x14000e43f  lea     rdx, SourceString; "\\DosDevices\\HvServiceDevice"
0x14000e446  lea     rcx, [rdi+30h]; DestinationString
0x14000e44a  call    cs:__imp_RtlInitUnicodeString
0x14000e451  nop     dword ptr [rax+rax+00h]
0x14000e456  lea     rdx, HbpNameOfHvBootDevice; DeviceName
0x14000e45d  lea     rcx, [rdi+30h]; SymbolicLinkName
0x14000e461  call    cs:__imp_IoCreateSymbolicLink
0x14000e468  nop     dword ptr [rax+rax+00h]
0x14000e46d  mov     ebx, eax
0x14000e46f  test    eax, eax
0x14000e471  jns     short loc_14000E4DB
0x14000e473  lea     r9, aIocreatesymbol; "IoCreateSymbolicLink failed with 0x%x"
0x14000e47a  mov     [rsp+48h+DeviceCharacteristics], eax
0x14000e47e  mov     r8d, 144h
0x14000e484  lea     rdx, aHbadddevice; "HbAddDevice"
0x14000e48b  xor     ecx, ecx
0x14000e48d  call    HbpTraceEvent
0x14000e492  test    rdi, rdi
0x14000e495  jz      short loc_14000E4C3
0x14000e497  cmp     qword ptr [rdi+38h], 0
0x14000e49c  jz      short loc_14000E4AE
0x14000e49e  lea     rcx, [rdi+30h]; SymbolicLinkName
0x14000e4a2  call    cs:__imp_IoDeleteSymbolicLink
0x14000e4a9  nop     dword ptr [rax+rax+00h]
0x14000e4ae  mov     rcx, [rdi+18h]; TargetDevice
0x14000e4b2  test    rcx, rcx
0x14000e4b5  jz      short loc_14000E4C3
0x14000e4b7  call    cs:__imp_IoDetachDevice
0x14000e4be  nop     dword ptr [rax+rax+00h]
0x14000e4c3  mov     rcx, [rsp+48h+SourceDevice]; DeviceObject
0x14000e4c8  test    rcx, rcx
0x14000e4cb  jz      short loc_14000E4E5
0x14000e4cd  call    cs:__imp_IoDeleteDevice
0x14000e4d4  nop     dword ptr [rax+rax+00h]
0x14000e4d9  jmp     short loc_14000E4E5
0x14000e4db  mov     rax, [rsp+48h+SourceDevice]
0x14000e4e0  btr     dword ptr [rax+30h], 7
0x14000e4e5  lea     r9, aCompletedWithS; "Completed with status 0x%x"
0x14000e4ec  mov     [rsp+48h+DeviceCharacteristics], ebx
0x14000e4f0  mov     r8d, 160h
0x14000e4f6  lea     rdx, aHbadddevice; "HbAddDevice"
0x14000e4fd  mov     ecx, 2
0x14000e502  call    HbpTraceEvent
0x14000e507  mov     rsi, [rsp+48h+arg_8]
0x14000e50c  mov     eax, ebx
0x14000e50e  mov     rbx, [rsp+48h+arg_0]
0x14000e513  add     rsp, 40h
0x14000e517  pop     rdi
0x14000e518  retn
```
