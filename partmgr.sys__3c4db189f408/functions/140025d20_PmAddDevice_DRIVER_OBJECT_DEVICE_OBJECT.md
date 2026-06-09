# PmAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)

- ea: `0x140025d20`
- end: `0x1400261f3`
- name: `?PmAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z`
- size: `1235`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT Pdo)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140011440`
- `0x14002443c`
- `0x140025d20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400261cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400261cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140026170`
- `ntoskrnl!KeWaitForSingleObject` at `0x140026170`
- `ntoskrnl!IoFreeIrp` at `0x140026035`
- `ntoskrnl!IoFreeIrp` at `0x140026035`
- `ntoskrnl!KeInitializeEvent` at `0x140025f37`
- `ntoskrnl!KeInitializeEvent` at `0x140025f37`
- `ntoskrnl!IoAllocateWorkItem` at `0x140025fc5`
- `ntoskrnl!IoAllocateWorkItem` at `0x140025fe1`
- `ntoskrnl!IoAllocateWorkItem` at `0x140025fc5`
- `ntoskrnl!IoAllocateWorkItem` at `0x140025fe1`
- `ntoskrnl!IoDetachDevice` at `0x14002607a`
- `ntoskrnl!IoDetachDevice` at `0x14002607a`
- `ntoskrnl!KeInitializeMutex` at `0x140025e94`
- `ntoskrnl!KeInitializeMutex` at `0x140025fb5`
- `ntoskrnl!KeInitializeMutex` at `0x140025e94`
- `ntoskrnl!KeInitializeMutex` at `0x140025fb5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140025ea4`
- `ntoskrnl!KeInitializeSpinLock` at `0x140025ea4`
- `ntoskrnl!IoDeleteDevice` at `0x14002608a`
- `ntoskrnl!IoDeleteDevice` at `0x14002608a`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140025ecb`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140025ecb`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140025e59`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140025e59`
- `ntoskrnl!IoAllocateIrp` at `0x140025ffd`
- `ntoskrnl!IoAllocateIrp` at `0x140025ffd`
- `ntoskrnl!IoFreeWorkItem` at `0x14002604d`
- `ntoskrnl!IoFreeWorkItem` at `0x140026065`
- `ntoskrnl!IoFreeWorkItem` at `0x14002604d`
- `ntoskrnl!IoFreeWorkItem` at `0x140026065`
- `ntoskrnl!IoCreateDevice` at `0x140025de5`
- `ntoskrnl!IoCreateDevice` at `0x140025de5`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140025d98`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140025e25`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140025d98`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140025e25`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140025d89`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140025d89`
- `ntoskrnl!KeReleaseMutex` at `0x1400261a4`
- `ntoskrnl!KeReleaseMutex` at `0x1400261a4`

## pseudocode

```c
__int64 __fastcall PmAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT Pdo)
{
  char *DeviceExtension; // r13
  int DevicePropertyData; // eax
  PVOID v6; // r14
  NTSTATUS v7; // edi
  ULONG ActiveProcessorCount; // r12d
  unsigned int v9; // esi
  _QWORD *v10; // rbx
  _QWORD *v11; // rsi
  PDEVICE_OBJECT v12; // rax
  _QWORD *v13; // rsi
  PIO_WORKITEM WorkItem; // rax
  PIO_WORKITEM v15; // rax
  PIRP Irp; // rax
  IRP *v17; // rcx
  struct _IO_WORKITEM *v18; // rcx
  struct _IO_WORKITEM *v19; // rcx
  struct _DEVICE_OBJECT *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  PVOID *v23; // rdx
  PDEVICE_OBJECT SourceDevice; // [rsp+90h] [rbp+50h] BYREF
  PVOID P; // [rsp+98h] [rbp+58h] BYREF

  SourceDevice = 0;
  P = 0;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  DevicePropertyData = PmGetDevicePropertyData(Pdo, (DEVPROPKEY *)&DEVPKEY_Storage_No_Partitions, &P);
  v6 = P;
  v7 = DevicePropertyData;
  if ( DevicePropertyData >= 0 && P && *(_BYTE *)P == 0xFF )
    goto LABEL_27;
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  v9 = 192 * ActiveProcessorCount + ((unsigned __int8)PoEnergyEstimationEnabled() != 0 ? 432 : 192);
  v7 = IoCreateDevice(DriverObject, v9 + 1160, 0, 0x2Du, 0x100u, 0, &SourceDevice);
  if ( v7 < 0 )
  {
    v10 = 0;
    SourceDevice = 0;
    goto LABEL_14;
  }
  v10 = SourceDevice->DeviceExtension;
  memset(v10, 0, v9 + 1160LL);
  v11 = v10 + 145;
  if ( (unsigned __int8)PoEnergyEstimationEnabled() )
  {
    v10[143] = v11;
    v11 = v10 + 175;
  }
  v10[90] = ((unsigned __int64)v11 + 63) & 0xFFFFFFFFFFFFFFC0uLL;
  v12 = IoAttachDeviceToDeviceStack(SourceDevice, Pdo);
  v10[2] = v12;
  if ( !v12 )
  {
    v7 = -1073741810;
    goto LABEL_14;
  }
  *v10 = off_1400132A0;
  v10[1] = SourceDevice;
  v10[3] = Pdo;
  KeInitializeMutex((PRKMUTEX)v10 + 1, 0);
  KeInitializeSpinLock(v10 + 14);
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 15), 0x4C526D50u, 0xAu, 0, 0x20u);
  v10[78] = v10 + 77;
  v13 = v10 + 19;
  v10[77] = v10 + 77;
  v10[20] = v10 + 19;
  v10[80] = v10 + 79;
  v10[79] = v10 + 79;
  v10[83] = v10 + 82;
  v10[82] = v10 + 82;
  v10[85] = v10 + 84;
  v10[84] = v10 + 84;
  v10[87] = v10 + 86;
  v10[86] = v10 + 86;
  v10[19] = v10 + 19;
  KeInitializeEvent((PRKEVENT)(v10 + 103), NotificationEvent, 0);
  *((_DWORD *)v10 + 182) = 1;
  v10[113] = v10 + 112;
  v10[112] = v10 + 112;
  v10[109] = v10 + 108;
  v10[108] = v10 + 108;
  v10[92] = &PmGuidList;
  v10[93] = PmQueryWmiRegInfo;
  v10[94] = PmQueryWmiDataBlock;
  v10[98] = PmWmiFunctionControl;
  *(_DWORD *)(v10[90] + 60LL) = ActiveProcessorCount;
  KeInitializeMutex((PRKMUTEX)v10[90], 0);
  WorkItem = IoAllocateWorkItem(SourceDevice);
  v10[111] = WorkItem;
  if ( !WorkItem
    || (v15 = IoAllocateWorkItem(SourceDevice), (v10[106] = v15) == 0)
    || (Irp = IoAllocateIrp(5, 0), (v10[107] = Irp) == 0) )
  {
    v7 = -1073741670;
LABEL_14:
    if ( SourceDevice )
    {
      v17 = (IRP *)v10[107];
      if ( v17 )
        IoFreeIrp(v17);
      v18 = (struct _IO_WORKITEM *)v10[106];
      if ( v18 )
        IoFreeWorkItem(v18);
      v19 = (struct _IO_WORKITEM *)v10[111];
      if ( v19 )
        IoFreeWorkItem(v19);
      v20 = (struct _DEVICE_OBJECT *)v10[2];
      if ( v20 )
        IoDetachDevice(v20);
      IoDeleteDevice(SourceDevice);
    }
    goto LABEL_27;
  }
  *((_DWORD *)v10 + 128) = 2;
  *((_DWORD *)v10 + 102) = -1;
  *((_DWORD *)v10 + 103) = -1;
  *((_DWORD *)v10 + 108) = -1;
  *((_DWORD *)v10 + 109) = -1;
  *((_DWORD *)v10 + 110) = -1;
  *((_DWORD *)v10 + 104) = -1;
  *((_DWORD *)v10 + 105) = -1;
  *((_DWORD *)v10 + 106) = -1;
  *((_DWORD *)v10 + 107) = -1;
  *((_DWORD *)v10 + 129) |= 0x10u;
  v21 = v10[66];
  *((_DWORD *)v10 + 130) = 0;
  v10[66] = v21 | 3;
  v22 = v10[2];
  *((_DWORD *)v10 + 140) = 32;
  SourceDevice->DeviceType = *(_DWORD *)(v22 + 72);
  SourceDevice->Flags |= 0x10u;
  SourceDevice->Flags |= (*(_DWORD *)(v10[2] + 48LL) & 0x4000) != 0 ? 0x4000 : 0x2000;
  KeWaitForSingleObject(DeviceExtension + 16, Executive, 0, 0, 0);
  v23 = (PVOID *)*((_QWORD *)DeviceExtension + 12);
  if ( *v23 != DeviceExtension + 88 )
    __fastfail(3u);
  v10[20] = v23;
  *v13 = DeviceExtension + 88;
  *v23 = v13;
  *((_QWORD *)DeviceExtension + 12) = v13;
  KeReleaseMutex((PRKMUTEX)(DeviceExtension + 16), 0);
  SourceDevice->Flags &= ~0x80u;
LABEL_27:
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140025d20  mov     [rsp-38h+arg_0], rbx
0x140025d25  push    rbp
0x140025d26  push    rsi
0x140025d27  push    rdi
0x140025d28  push    r12
0x140025d2a  push    r13
0x140025d2c  push    r14
0x140025d2e  push    r15
0x140025d30  mov     rbp, rsp
0x140025d33  sub     rsp, 40h
0x140025d37  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140025d3e  lea     r8, [rbp+P]; void **
0x140025d42  mov     r15, rdx
0x140025d45  mov     [rbp+SourceDevice], 0
0x140025d4d  mov     rbx, rcx
0x140025d50  mov     [rbp+P], 0
0x140025d58  lea     rdx, DEVPKEY_Storage_No_Partitions; PropertyKey
0x140025d5f  mov     rcx, r15; Pdo
0x140025d62  mov     r13, [rax+40h]
0x140025d66  call    ?PmGetDevicePropertyData@@YAJPEAU_DEVICE_OBJECT@@PEBU_DEVPROPKEY@@PEAPEAX@Z; PmGetDevicePropertyData(_DEVICE_OBJECT *,_DEVPROPKEY const *,void * *)
0x140025d6b  mov     r14, [rbp+P]
0x140025d6f  mov     edi, eax
0x140025d71  test    eax, eax
0x140025d73  js      short loc_140025D84
0x140025d75  test    r14, r14
0x140025d78  jz      short loc_140025D84
0x140025d7a  cmp     byte ptr [r14], 0FFh
0x140025d7e  jz      loc_1400261C2
0x140025d84  mov     ecx, 0FFFFh; GroupNumber
0x140025d89  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140025d90  nop     dword ptr [rax+rax+00h]
0x140025d95  mov     r12d, eax
0x140025d98  call    cs:__imp_PoEnergyEstimationEnabled
0x140025d9f  nop     dword ptr [rax+rax+00h]
0x140025da4  lea     ecx, [r12+r12*2]
0x140025da8  mov     r9d, 2Dh ; '-'; DeviceType
0x140025dae  neg     al
0x140025db0  lea     rax, [rbp+SourceDevice]
0x140025db4  sbb     edx, edx
0x140025db6  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x140025dbb  and     edx, 0F0h
0x140025dc1  shl     ecx, 6
0x140025dc4  mov     [rsp+40h+Exclusive], 0; Exclusive
0x140025dc9  xor     r8d, r8d; DeviceName
0x140025dcc  mov     [rsp+40h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140025dd4  lea     esi, [rdx+0C0h]
0x140025dda  add     esi, ecx
0x140025ddc  mov     rcx, rbx; DriverObject
0x140025ddf  lea     edx, [rsi+488h]; DeviceExtensionSize
0x140025de5  call    cs:__imp_IoCreateDevice
0x140025dec  nop     dword ptr [rax+rax+00h]
0x140025df1  mov     edi, eax
0x140025df3  test    eax, eax
0x140025df5  jns     short loc_140025E02
0x140025df7  xor     ebx, ebx
0x140025df9  mov     [rbp+SourceDevice], rbx
0x140025dfd  jmp     loc_14002601E
0x140025e02  mov     rax, [rbp+SourceDevice]
0x140025e06  xor     edx, edx; Val
0x140025e08  mov     r8d, esi
0x140025e0b  add     r8, 488h; Size
0x140025e12  mov     rbx, [rax+40h]
0x140025e16  mov     rcx, rbx; void *
0x140025e19  call    memset
0x140025e1e  lea     rsi, [rbx+488h]
0x140025e25  call    cs:__imp_PoEnergyEstimationEnabled
0x140025e2c  nop     dword ptr [rax+rax+00h]
0x140025e31  test    al, al
0x140025e33  jz      short loc_140025E43
0x140025e35  mov     [rbx+478h], rsi
0x140025e3c  add     rsi, 0F0h
0x140025e43  lea     rax, [rsi+3Fh]
0x140025e47  mov     rdx, r15; TargetDevice
0x140025e4a  and     rax, 0FFFFFFFFFFFFFFC0h
0x140025e4e  mov     [rbx+2D0h], rax
0x140025e55  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x140025e59  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140025e60  nop     dword ptr [rax+rax+00h]
0x140025e65  mov     [rbx+10h], rax
0x140025e69  test    rax, rax
0x140025e6c  jnz     short loc_140025E78
0x140025e6e  mov     edi, 0C000000Eh
0x140025e73  jmp     loc_14002601E
0x140025e78  lea     rax, off_1400132A0
0x140025e7f  xor     edx, edx; Level
0x140025e81  mov     [rbx], rax
0x140025e84  lea     rcx, [rbx+38h]; Mutex
0x140025e88  mov     rax, [rbp+SourceDevice]
0x140025e8c  mov     [rbx+8], rax
0x140025e90  mov     [rbx+18h], r15
0x140025e94  call    cs:__imp_KeInitializeMutex
0x140025e9b  nop     dword ptr [rax+rax+00h]
0x140025ea0  lea     rcx, [rbx+70h]; SpinLock
0x140025ea4  call    cs:__imp_KeInitializeSpinLock
0x140025eab  nop     dword ptr [rax+rax+00h]
0x140025eb0  mov     r15d, 20h ; ' '
0x140025eb6  lea     rcx, [rbx+78h]; Lock
0x140025eba  xor     r9d, r9d; HighWatermark
0x140025ebd  mov     [rsp+40h+DeviceCharacteristics], r15d; RemlockSize
0x140025ec2  mov     edx, 4C526D50h; AllocateTag
0x140025ec7  lea     r8d, [r15-16h]; MaxLockedMinutes
0x140025ecb  call    cs:__imp_IoInitializeRemoveLockEx
0x140025ed2  nop     dword ptr [rax+rax+00h]
0x140025ed7  lea     rax, [rbx+268h]
0x140025ede  xor     r8d, r8d; State
0x140025ee1  mov     [rax+8], rax
0x140025ee5  lea     rsi, [rbx+98h]
0x140025eec  mov     [rax], rax
0x140025eef  lea     rcx, [rbx+338h]; Event
0x140025ef6  lea     rax, [rbx+278h]
0x140025efd  mov     [rsi+8], rsi
0x140025f01  mov     [rax+8], rax
0x140025f05  xor     edx, edx; Type
0x140025f07  mov     [rax], rax
0x140025f0a  lea     rax, [rbx+290h]
0x140025f11  mov     [rax+8], rax
0x140025f15  mov     [rax], rax
0x140025f18  lea     rax, [rbx+2A0h]
0x140025f1f  mov     [rax+8], rax
0x140025f23  mov     [rax], rax
0x140025f26  lea     rax, [rbx+2B0h]
0x140025f2d  mov     [rax+8], rax
0x140025f31  mov     [rax], rax
0x140025f34  mov     [rsi], rsi
0x140025f37  call    cs:__imp_KeInitializeEvent
0x140025f3e  nop     dword ptr [rax+rax+00h]
0x140025f43  lea     rax, [rbx+380h]
0x140025f4a  mov     dword ptr [rbx+2D8h], 1
0x140025f54  mov     [rax+8], rax
0x140025f58  xor     edx, edx; Level
0x140025f5a  mov     [rax], rax
0x140025f5d  lea     rax, [rbx+360h]
0x140025f64  mov     [rax+8], rax
0x140025f68  mov     [rax], rax
0x140025f6b  lea     rax, ?PmGuidList@@3PAU_WMIGUIDREGINFO@@A; _WMIGUIDREGINFO near * PmGuidList
0x140025f72  mov     [rbx+2E0h], rax
0x140025f79  lea     rax, ?PmQueryWmiRegInfo@@YAJPEAU_DEVICE_OBJECT@@PEAKPEAU_UNICODE_STRING@@PEAPEAU2@2PEAPEAU1@@Z; PmQueryWmiRegInfo(_DEVICE_OBJECT *,ulong *,_UNICODE_STRING *,_UNICODE_STRING * *,_UNICODE_STRING *,_DEVICE_OBJECT * *)
0x140025f80  mov     [rbx+2E8h], rax
0x140025f87  lea     rax, ?PmQueryWmiDataBlock@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@KKKPEAKKPEAE@Z; PmQueryWmiDataBlock(_DEVICE_OBJECT *,_IRP *,ulong,ulong,ulong,ulong *,ulong,uchar *)
0x140025f8e  mov     [rbx+2F0h], rax
0x140025f95  lea     rax, ?PmWmiFunctionControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@KW4_WMIENABLEDISABLECONTROL@@E@Z; PmWmiFunctionControl(_DEVICE_OBJECT *,_IRP *,ulong,_WMIENABLEDISABLECONTROL,uchar)
0x140025f9c  mov     [rbx+310h], rax
0x140025fa3  mov     rax, [rbx+2D0h]
0x140025faa  mov     [rax+3Ch], r12d
0x140025fae  mov     rcx, [rbx+2D0h]; Mutex
0x140025fb5  call    cs:__imp_KeInitializeMutex
0x140025fbc  nop     dword ptr [rax+rax+00h]
0x140025fc1  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x140025fc5  call    cs:__imp_IoAllocateWorkItem
0x140025fcc  nop     dword ptr [rax+rax+00h]
0x140025fd1  mov     [rbx+378h], rax
0x140025fd8  test    rax, rax
0x140025fdb  jz      short loc_140026019
0x140025fdd  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x140025fe1  call    cs:__imp_IoAllocateWorkItem
0x140025fe8  nop     dword ptr [rax+rax+00h]
0x140025fed  mov     [rbx+350h], rax
0x140025ff4  test    rax, rax
0x140025ff7  jz      short loc_140026019
0x140025ff9  xor     edx, edx; ChargeQuota
0x140025ffb  mov     cl, 5; StackSize
0x140025ffd  call    cs:__imp_IoAllocateIrp
0x140026004  nop     dword ptr [rax+rax+00h]
0x140026009  mov     [rbx+358h], rax
0x140026010  test    rax, rax
0x140026013  jnz     loc_14002609B
0x140026019  mov     edi, 0C000009Ah
0x14002601e  cmp     [rbp+SourceDevice], 0
0x140026023  jz      loc_1400261C2
0x140026029  mov     rcx, [rbx+358h]; Irp
0x140026030  test    rcx, rcx
0x140026033  jz      short loc_140026041
0x140026035  call    cs:__imp_IoFreeIrp
0x14002603c  nop     dword ptr [rax+rax+00h]
0x140026041  mov     rcx, [rbx+350h]; IoWorkItem
0x140026048  test    rcx, rcx
0x14002604b  jz      short loc_140026059
0x14002604d  call    cs:__imp_IoFreeWorkItem
0x140026054  nop     dword ptr [rax+rax+00h]
0x140026059  mov     rcx, [rbx+378h]; IoWorkItem
0x140026060  test    rcx, rcx
0x140026063  jz      short loc_140026071
0x140026065  call    cs:__imp_IoFreeWorkItem
0x14002606c  nop     dword ptr [rax+rax+00h]
0x140026071  mov     rcx, [rbx+10h]; TargetDevice
0x140026075  test    rcx, rcx
0x140026078  jz      short loc_140026086
0x14002607a  call    cs:__imp_IoDetachDevice
0x140026081  nop     dword ptr [rax+rax+00h]
0x140026086  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14002608a  call    cs:__imp_IoDeleteDevice
0x140026091  nop     dword ptr [rax+rax+00h]
0x140026096  jmp     loc_1400261C2
0x14002609b  or      eax, 0FFFFFFFFh
0x14002609e  mov     dword ptr [rbx+200h], 2
0x1400260a8  mov     [rbx+198h], eax
0x1400260ae  mov     [rbx+19Ch], eax
0x1400260b4  mov     [rbx+1B0h], eax
0x1400260ba  mov     [rbx+1B4h], eax
0x1400260c0  mov     [rbx+1B8h], eax
0x1400260c6  mov     [rbx+1A0h], eax
0x1400260cc  mov     [rbx+1A4h], eax
0x1400260d2  mov     [rbx+1A8h], eax
0x1400260d8  mov     [rbx+1ACh], eax
0x1400260de  mov     eax, [rbx+204h]
0x1400260e4  or      eax, 10h
0x1400260e7  mov     qword ptr [rsp+40h+DeviceCharacteristics], 0; Timeout
0x1400260f0  mov     [rbx+204h], eax
0x1400260f6  mov     rax, [rbx+210h]
0x1400260fd  mov     dword ptr [rbx+208h], 0
0x140026107  or      rax, 3
0x14002610b  mov     [rbx+210h], rax
0x140026112  mov     rax, [rbx+10h]
0x140026116  mov     [rbx+230h], r15d
0x14002611d  mov     ecx, [rax+48h]
0x140026120  mov     rax, [rbp+SourceDevice]
0x140026124  mov     [rax+48h], ecx
0x140026127  mov     rax, [rbp+SourceDevice]
0x14002612b  mov     ecx, [rax+30h]
0x14002612e  mov     rax, [rbp+SourceDevice]
0x140026132  or      ecx, 10h
0x140026135  mov     [rax+30h], ecx
0x140026138  mov     rax, [rbp+SourceDevice]
0x14002613c  mov     r8d, [rax+30h]
0x140026140  mov     rax, [rbx+10h]
0x140026144  mov     ecx, [rax+30h]
0x140026147  mov     eax, 2000h
0x14002614c  and     ecx, 4000h
0x140026152  neg     ecx
0x140026154  lea     rcx, [r13+10h]; Object
0x140026158  sbb     edx, edx
0x14002615a  xor     r9d, r9d; Alertable
0x14002615d  and     edx, eax
0x14002615f  add     edx, eax
0x140026161  mov     rax, [rbp+SourceDevice]
0x140026165  or      edx, r8d
0x140026168  xor     r8d, r8d; WaitMode
0x14002616b  mov     [rax+30h], edx
0x14002616e  xor     edx, edx; WaitReason
0x140026170  call    cs:__imp_KeWaitForSingleObject
0x140026177  nop     dword ptr [rax+rax+00h]
0x14002617c  lea     rax, [r13+58h]
0x140026180  mov     rdx, [rax+8]
0x140026184  cmp     [rdx], rax
0x140026187  jz      short loc_140026190
0x140026189  mov     ecx, 3
0x14002618e  int     29h; Win8: RtlFailFast(ecx)
0x140026190  mov     [rsi+8], rdx
0x140026194  lea     rcx, [r13+10h]; Mutex
0x140026198  mov     [rsi], rax
0x14002619b  mov     [rdx], rsi
0x14002619e  xor     edx, edx; Wait
0x1400261a0  mov     [rax+8], rsi
0x1400261a4  call    cs:__imp_KeReleaseMutex
0x1400261ab  nop     dword ptr [rax+rax+00h]
0x1400261b0  mov     rax, [rbp+SourceDevice]
0x1400261b4  mov     edx, [rax+30h]
0x1400261b7  mov     rax, [rbp+SourceDevice]
0x1400261bb  btr     edx, 7
0x1400261bf  mov     [rax+30h], edx
0x1400261c2  test    r14, r14
0x1400261c5  jz      short loc_1400261D8
0x1400261c7  xor     edx, edx; Tag
0x1400261c9  mov     rcx, r14; P
0x1400261cc  call    cs:__imp_ExFreePoolWithTag
0x1400261d3  nop     dword ptr [rax+rax+00h]
0x1400261d8  mov     rbx, [rsp+40h+arg_0]
0x1400261e0  mov     eax, edi
0x1400261e2  add     rsp, 40h
0x1400261e6  pop     r15
0x1400261e8  pop     r14
0x1400261ea  pop     r13
0x1400261ec  pop     r12
0x1400261ee  pop     rdi
0x1400261ef  pop     rsi
0x1400261f0  pop     rbp
0x1400261f1  retn
```
