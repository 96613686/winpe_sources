# KbdHid_AddDevice

- ea: `0x140010690`
- end: `0x140010c26`
- name: `KbdHid_AddDevice`
- size: `1430`
- prototype: `__int64 __fastcall(PVOID IoObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400052a0`
- `0x140005a0c`
- `0x140007540`
- `0x140010690`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400107c0`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400107c0`
- `ntoskrnl!IoAllocateWorkItem` at `0x140010b21`
- `ntoskrnl!IoAllocateWorkItem` at `0x140010b21`
- `ntoskrnl!KeInitializeDpc` at `0x1400109e6`
- `ntoskrnl!KeInitializeDpc` at `0x140010a2b`
- `ntoskrnl!KeInitializeDpc` at `0x1400109e6`
- `ntoskrnl!KeInitializeDpc` at `0x140010a2b`
- `ntoskrnl!IoDetachDevice` at `0x140010bce`
- `ntoskrnl!IoDetachDevice` at `0x140010bce`
- `ntoskrnl!IoFreeIrp` at `0x140010be3`
- `ntoskrnl!IoFreeIrp` at `0x140010be3`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010831`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010b0d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010831`
- `ntoskrnl!KeInitializeSpinLock` at `0x140010b0d`
- `ntoskrnl!IoDeleteDevice` at `0x140010bf7`
- `ntoskrnl!IoDeleteDevice` at `0x140010bf7`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1400108cf`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1400108cf`
- `ntoskrnl!KeInitializeTimer` at `0x1400109f9`
- `ntoskrnl!KeInitializeTimer` at `0x140010a3e`
- `ntoskrnl!KeInitializeTimer` at `0x1400109f9`
- `ntoskrnl!KeInitializeTimer` at `0x140010a3e`
- `ntoskrnl!PoSetPowerState` at `0x140010a6c`
- `ntoskrnl!PoSetPowerState` at `0x140010a6c`
- `ntoskrnl!IoAllocateIrp` at `0x140010847`
- `ntoskrnl!IoAllocateIrp` at `0x140010847`
- `ntoskrnl!IoCreateDevice` at `0x140010727`
- `ntoskrnl!IoCreateDevice` at `0x140010727`
- `ntoskrnl!KeInitializeEvent` at `0x140010893`
- `ntoskrnl!KeInitializeEvent` at `0x1400108a9`
- `ntoskrnl!KeInitializeEvent` at `0x140010902`
- `ntoskrnl!KeInitializeEvent` at `0x1400109a5`
- `ntoskrnl!KeInitializeEvent` at `0x140010893`
- `ntoskrnl!KeInitializeEvent` at `0x1400108a9`
- `ntoskrnl!KeInitializeEvent` at `0x140010902`
- `ntoskrnl!KeInitializeEvent` at `0x1400109a5`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400107ed`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400107ed`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400107a1`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400107a1`

## pseudocode

```c
__int64 __fastcall KbdHid_AddDevice(struct _DRIVER_OBJECT *IoObject, PDEVICE_OBJECT TargetDevice)
{
  NTSTATUS v4; // eax
  int v5; // edx
  int v6; // esi
  _QWORD *DeviceExtension; // rdi
  int v8; // r9d
  int v9; // edx
  PDEVICE_OBJECT v10; // rax
  _DWORD *ErrorLogEntry; // rax
  __int16 v12; // ax
  PIRP Irp; // rax
  __int16 v14; // cx
  __int16 v15; // cx
  PIO_WORKITEM WorkItem; // rax
  struct _DEVICE_OBJECT *v17; // rcx
  IRP *v18; // rcx
  char Exclusive; // [rsp+28h] [rbp-40h]
  char DeviceObject; // [rsp+30h] [rbp-38h]
  PDEVICE_OBJECT SourceDevice; // [rsp+80h] [rbp+18h] BYREF

  SourceDevice = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      5,
      12,
      (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
  v4 = IoCreateDevice(IoObject, 0x328u, 0, 0xBu, 0, 0, &SourceDevice);
  v6 = v4;
  if ( v4 < 0 )
  {
    DeviceExtension = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      DeviceObject = v4;
      v8 = 13;
      Exclusive = (char)IoObject;
LABEL_7:
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        5,
        v8,
        (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
        Exclusive,
        DeviceObject);
      goto LABEL_18;
    }
    goto LABEL_21;
  }
  DeviceExtension = SourceDevice->DeviceExtension;
  memset(DeviceExtension, 0, 0x328u);
  v10 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
  DeviceExtension[1] = v10;
  if ( v10 )
  {
    *DeviceExtension = SourceDevice;
    *((_BYTE *)DeviceExtension + 88) = 0;
    *((_BYTE *)DeviceExtension + 90) = 0;
    v12 = _InterlockedExchangeAdd((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext, 1u) + 1;
    DeviceExtension[2] = TargetDevice;
    *((_WORD *)DeviceExtension + 46) = v12;
    KeInitializeSpinLock(DeviceExtension + 93);
    Irp = IoAllocateIrp(*(_BYTE *)(DeviceExtension[1] + 76LL), 0);
    DeviceExtension[13] = Irp;
    if ( Irp )
    {
      KeInitializeEvent((PRKEVENT)(DeviceExtension + 5), SynchronizationEvent, 0);
      KeInitializeEvent((PRKEVENT)(DeviceExtension + 8), NotificationEvent, 1u);
      IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 19), 0x4864624Bu, 1u, 0, 0x20u);
      DeviceExtension[16] = 0;
      *((_DWORD *)DeviceExtension + 46) = 1;
      DeviceExtension[24] = 0;
      *((_DWORD *)DeviceExtension + 50) = 0;
      KeInitializeEvent((PRKEVENT)(DeviceExtension + 26), SynchronizationEvent, 0);
      v14 = *((_WORD *)DeviceExtension + 46);
      *((_WORD *)DeviceExtension + 132) = v14;
      *((_WORD *)DeviceExtension + 148) = v14;
      *((_WORD *)DeviceExtension + 151) = v14;
      *(_DWORD *)((char *)DeviceExtension + 266) = 0;
      *((_DWORD *)DeviceExtension + 69) = 0;
      *((_DWORD *)DeviceExtension + 70) = 65617;
      DeviceExtension[43] = 81;
      *((_DWORD *)DeviceExtension + 71) = 196620;
      *((_WORD *)DeviceExtension + 144) = 101;
      *((_DWORD *)DeviceExtension + 73) = 1;
      *(_DWORD *)((char *)DeviceExtension + 298) = 16384002;
      *((_DWORD *)DeviceExtension + 76) = 65536030;
      *((_DWORD *)DeviceExtension + 77) = 1;
      *((_WORD *)DeviceExtension + 156) = 0;
      *((_BYTE *)DeviceExtension + 314) = 0;
      *((_DWORD *)DeviceExtension + 79) = 0;
      KeInitializeEvent((PRKEVENT)(DeviceExtension + 40), NotificationEvent, 0);
      v15 = *((_WORD *)DeviceExtension + 46);
      *((_WORD *)DeviceExtension + 176) = v15;
      *((_WORD *)DeviceExtension + 178) = v15;
      *((_WORD *)DeviceExtension + 177) = 0;
      *(_DWORD *)((char *)DeviceExtension + 358) = 16384030;
      KeInitializeDpc((PRKDPC)(DeviceExtension + 46), KbdHid_AutoRepeat, DeviceExtension);
      KeInitializeTimer((PKTIMER)(DeviceExtension + 54));
      *((_DWORD *)DeviceExtension + 126) = 33;
      DeviceExtension[62] = -2500000;
      KeInitializeDpc((PRKDPC)DeviceExtension + 8, KbdHid_InitiateStartRead, DeviceExtension);
      KeInitializeTimer((PKTIMER)DeviceExtension + 9);
      DeviceExtension[80] = -500000;
      *((_BYTE *)DeviceExtension + 648) = 0;
      *((_DWORD *)DeviceExtension + 6) = 1;
      PoSetPowerState(SourceDevice, DevicePowerState, (POWER_STATE)1);
      *((_DWORD *)DeviceExtension + 168) = 2;
      DeviceExtension[85] = &KbdHid_WmiGuidList;
      DeviceExtension[86] = KbdHid_QueryWmiRegInfo;
      DeviceExtension[87] = &KbdHid_QueryWmiDataBlock;
      DeviceExtension[88] = KbdHid_SetWmiDataBlock;
      DeviceExtension[89] = KbdHid_SetWmiDataBlock;
      DeviceExtension[90] = 0;
      DeviceExtension[91] = 0;
      SourceDevice->Flags |= 0x2000u;
      SourceDevice->Flags &= ~0x80u;
      *((_DWORD *)DeviceExtension + 192) = 0;
      *((_DWORD *)DeviceExtension + 196) = 0;
      *((_BYTE *)DeviceExtension + 788) = 0;
      KeInitializeSpinLock(DeviceExtension + 97);
      WorkItem = IoAllocateWorkItem(SourceDevice);
      DeviceExtension[95] = WorkItem;
      if ( WorkItem )
        goto LABEL_18;
      v6 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          15,
          (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
          (char)SourceDevice,
          154);
        goto LABEL_18;
      }
    }
    else
    {
      v6 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v8 = 14;
        DeviceObject = -102;
        Exclusive = (char)SourceDevice;
        goto LABEL_7;
      }
    }
LABEL_21:
    if ( SourceDevice )
    {
      if ( DeviceExtension )
      {
        v17 = (struct _DEVICE_OBJECT *)DeviceExtension[1];
        if ( v17 )
          IoDetachDevice(v17);
        v18 = (IRP *)DeviceExtension[13];
        if ( v18 )
          IoFreeIrp(v18);
      }
      IoDeleteDevice(SourceDevice);
    }
    return (unsigned int)v6;
  }
  v6 = -1073741667;
  ErrorLogEntry = IoAllocateErrorLogEntry(IoObject, 0x30u);
  if ( ErrorLogEntry )
  {
    ErrorLogEntry[3] = -1073414142;
    *ErrorLogEntry = 0;
    *((_QWORD *)ErrorLogEntry + 3) = 0;
    ErrorLogEntry[4] = 0;
    ErrorLogEntry[5] = -1073741667;
    IoWriteErrorLogEntry(ErrorLogEntry);
  }
LABEL_18:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      5,
      16,
      (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
      (char)SourceDevice,
      v6);
  }
  if ( v6 < 0 )
    goto LABEL_21;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140010690  mov     rax, rsp
0x140010693  mov     [rax+10h], rbx
0x140010697  mov     [rax+20h], rbp
0x14001069b  push    rsi
0x14001069c  push    r12
0x14001069e  push    r13
0x1400106a0  push    r14
0x1400106a2  push    r15
0x1400106a4  sub     rsp, 40h
0x1400106a8  xor     r12d, r12d
0x1400106ab  mov     rbp, rdx
0x1400106ae  mov     [rax+18h], r12
0x1400106b2  mov     rbx, rcx
0x1400106b5  lea     r13, WPP_RECORDER_INITIALIZED
0x1400106bc  mov     r15d, 0Ch
0x1400106c2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400106c9  lea     r14, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x1400106d0  jz      short loc_1400106FA
0x1400106d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106d9  cmp     [rcx+48h], r12w
0x1400106de  jz      short loc_1400106FA
0x1400106e0  mov     rcx, [rcx+40h]
0x1400106e4  mov     r8d, 5
0x1400106ea  movzx   edx, r8b
0x1400106ee  mov     [rax-48h], r14
0x1400106f2  mov     r9d, r15d
0x1400106f5  call    WPP_RECORDER_SF_
0x1400106fa  lea     rax, [rsp+68h+SourceDevice]
0x140010702  mov     [rsp+68h+arg_0], rdi
0x140010707  mov     qword ptr [rsp+68h+DeviceObject], rax; DeviceObject
0x14001070c  mov     r9d, 0Bh; DeviceType
0x140010712  mov     [rsp+68h+Exclusive], r12b; Exclusive
0x140010717  xor     r8d, r8d; DeviceName
0x14001071a  mov     edx, 328h; DeviceExtensionSize
0x14001071f  mov     [rsp+68h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x140010724  mov     rcx, rbx; DriverObject
0x140010727  call    cs:__imp_IoCreateDevice
0x14001072e  nop     dword ptr [rax+rax+00h]
0x140010733  mov     esi, eax
0x140010735  test    eax, eax
0x140010737  jns     short loc_14001077A
0x140010739  mov     rdi, r12
0x14001073c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140010743  jz      loc_140010BB6
0x140010749  mov     dword ptr [rsp+68h+DeviceObject], eax
0x14001074d  mov     r9d, 0Dh
0x140010753  mov     qword ptr [rsp+68h+Exclusive], rbx
0x140010758  mov     dl, 2
0x14001075a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010761  mov     r8d, 5
0x140010767  mov     qword ptr [rsp+68h+DeviceCharacteristics], r14
0x14001076c  mov     rcx, [rcx+40h]
0x140010770  call    WPP_RECORDER_SF_qd
0x140010775  jmp     loc_140010B75
0x14001077a  mov     rax, [rsp+68h+SourceDevice]
0x140010782  xor     edx, edx; Val
0x140010784  mov     r8d, 328h; Size
0x14001078a  mov     rdi, [rax+40h]
0x14001078e  mov     rcx, rdi; void *
0x140010791  call    memset
0x140010796  mov     rcx, [rsp+68h+SourceDevice]; SourceDevice
0x14001079e  mov     rdx, rbp; TargetDevice
0x1400107a1  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400107a8  nop     dword ptr [rax+rax+00h]
0x1400107ad  mov     [rdi+8], rax
0x1400107b1  test    rax, rax
0x1400107b4  jnz     short loc_1400107FE
0x1400107b6  mov     dl, 30h ; '0'; EntrySize
0x1400107b8  mov     rcx, rbx; IoObject
0x1400107bb  mov     esi, 0C000009Dh
0x1400107c0  call    cs:__imp_IoAllocateErrorLogEntry
0x1400107c7  nop     dword ptr [rax+rax+00h]
0x1400107cc  test    rax, rax
0x1400107cf  jz      loc_140010B75
0x1400107d5  mov     rcx, rax; ElEntry
0x1400107d8  mov     dword ptr [rax+0Ch], 0C0050002h
0x1400107df  mov     [rax], r12d
0x1400107e2  mov     [rax+18h], r12
0x1400107e6  mov     [rax+10h], r12d
0x1400107ea  mov     [rax+14h], esi
0x1400107ed  call    cs:__imp_IoWriteErrorLogEntry
0x1400107f4  nop     dword ptr [rax+rax+00h]
0x1400107f9  jmp     loc_140010B75
0x1400107fe  mov     rax, [rsp+68h+SourceDevice]
0x140010806  mov     ebx, 1
0x14001080b  mov     [rdi], rax
0x14001080e  mov     eax, ebx
0x140010810  mov     [rdi+58h], r12b
0x140010814  mov     [rdi+5Ah], r12b
0x140010818  lock xadd dword ptr cs:WPP_MAIN_CB.Queue+20h, eax
0x140010820  inc     eax
0x140010822  mov     [rdi+10h], rbp
0x140010826  lea     rcx, [rdi+2E8h]; SpinLock
0x14001082d  mov     [rdi+5Ch], ax
0x140010831  call    cs:__imp_KeInitializeSpinLock
0x140010838  nop     dword ptr [rax+rax+00h]
0x14001083d  mov     rcx, [rdi+8]
0x140010841  xor     edx, edx; ChargeQuota
0x140010843  movzx   ecx, byte ptr [rcx+4Ch]; StackSize
0x140010847  call    cs:__imp_IoAllocateIrp
0x14001084e  nop     dword ptr [rax+rax+00h]
0x140010853  mov     [rdi+68h], rax
0x140010857  test    rax, rax
0x14001085a  jnz     short loc_14001088A
0x14001085c  mov     esi, 0C000009Ah
0x140010861  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140010868  jz      loc_140010BB6
0x14001086e  mov     rax, [rsp+68h+SourceDevice]
0x140010876  mov     r9d, 0Eh
0x14001087c  mov     dword ptr [rsp+68h+DeviceObject], esi
0x140010880  mov     qword ptr [rsp+68h+Exclusive], rax
0x140010885  jmp     loc_140010758
0x14001088a  lea     rcx, [rdi+28h]; Event
0x14001088e  xor     r8d, r8d; State
0x140010891  mov     edx, ebx; Type
0x140010893  call    cs:__imp_KeInitializeEvent
0x14001089a  nop     dword ptr [rax+rax+00h]
0x14001089f  lea     rcx, [rdi+40h]; Event
0x1400108a3  movzx   r8d, bl; State
0x1400108a7  xor     edx, edx; Type
0x1400108a9  call    cs:__imp_KeInitializeEvent
0x1400108b0  nop     dword ptr [rax+rax+00h]
0x1400108b5  lea     rcx, [rdi+98h]; Lock
0x1400108bc  mov     [rsp+68h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x1400108c4  xor     r9d, r9d; HighWatermark
0x1400108c7  mov     r8d, ebx; MaxLockedMinutes
0x1400108ca  mov     edx, 4864624Bh; AllocateTag
0x1400108cf  call    cs:__imp_IoInitializeRemoveLockEx
0x1400108d6  nop     dword ptr [rax+rax+00h]
0x1400108db  lea     rcx, [rdi+0D0h]; Event
0x1400108e2  mov     [rdi+80h], r12
0x1400108e9  xor     r8d, r8d; State
0x1400108ec  mov     [rdi+0B8h], ebx
0x1400108f2  mov     edx, ebx; Type
0x1400108f4  mov     [rdi+0C0h], r12
0x1400108fb  mov     [rdi+0C8h], r12d
0x140010902  call    cs:__imp_KeInitializeEvent
0x140010909  nop     dword ptr [rax+rax+00h]
0x14001090e  movzx   ecx, word ptr [rdi+5Ch]
0x140010912  xor     r8d, r8d; State
0x140010915  mov     [rdi+108h], cx
0x14001091c  xor     edx, edx; Type
0x14001091e  mov     [rdi+128h], cx
0x140010925  mov     r15d, 2
0x14001092b  mov     [rdi+12Eh], cx
0x140010932  lea     rcx, [rdi+140h]; Event
0x140010939  mov     [rdi+10Ah], r12d
0x140010940  mov     [rdi+114h], r12d
0x140010947  mov     dword ptr [rdi+118h], 10051h
0x140010951  mov     qword ptr [rdi+158h], 51h ; 'Q'
0x14001095c  mov     dword ptr [rdi+11Ch], 3000Ch
0x140010966  mov     word ptr [rdi+120h], 65h ; 'e'
0x14001096f  mov     [rdi+124h], ebx
0x140010975  mov     dword ptr [rdi+12Ah], 0FA0002h
0x14001097f  mov     dword ptr [rdi+130h], 3E8001Eh
0x140010989  mov     [rdi+134h], ebx
0x14001098f  mov     [rdi+138h], r12w
0x140010997  mov     [rdi+13Ah], r12b
0x14001099e  mov     [rdi+13Ch], r12d
0x1400109a5  call    cs:__imp_KeInitializeEvent
0x1400109ac  nop     dword ptr [rax+rax+00h]
0x1400109b1  movzx   ecx, word ptr [rdi+5Ch]
0x1400109b5  lea     rdx, KbdHid_AutoRepeat; DeferredRoutine
0x1400109bc  mov     [rdi+160h], cx
0x1400109c3  mov     r8, rdi; DeferredContext
0x1400109c6  mov     [rdi+164h], cx
0x1400109cd  lea     rcx, [rdi+170h]; Dpc
0x1400109d4  mov     [rdi+162h], r12w
0x1400109dc  mov     dword ptr [rdi+166h], 0FA001Eh
0x1400109e6  call    cs:__imp_KeInitializeDpc
0x1400109ed  nop     dword ptr [rax+rax+00h]
0x1400109f2  lea     rcx, [rdi+1B0h]; Timer
0x1400109f9  call    cs:__imp_KeInitializeTimer
0x140010a00  nop     dword ptr [rax+rax+00h]
0x140010a05  lea     rcx, [rdi+200h]; Dpc
0x140010a0c  mov     dword ptr [rdi+1F8h], 21h ; '!'
0x140010a16  mov     r8, rdi; DeferredContext
0x140010a19  mov     qword ptr [rdi+1F0h], 0FFFFFFFFFFD9DA60h
0x140010a24  lea     rdx, KbdHid_InitiateStartRead; DeferredRoutine
0x140010a2b  call    cs:__imp_KeInitializeDpc
0x140010a32  nop     dword ptr [rax+rax+00h]
0x140010a37  lea     rcx, [rdi+240h]; Timer
0x140010a3e  call    cs:__imp_KeInitializeTimer
0x140010a45  nop     dword ptr [rax+rax+00h]
0x140010a4a  mov     qword ptr [rdi+280h], 0FFFFFFFFFFF85EE0h
0x140010a55  mov     r8d, ebx; State
0x140010a58  mov     [rdi+288h], r12b
0x140010a5f  mov     edx, ebx; Type
0x140010a61  mov     [rdi+18h], ebx
0x140010a64  mov     rcx, [rsp+68h+SourceDevice]; DeviceObject
0x140010a6c  call    cs:__imp_PoSetPowerState
0x140010a73  nop     dword ptr [rax+rax+00h]
0x140010a78  lea     rax, KbdHid_WmiGuidList
0x140010a7f  mov     [rdi+2A0h], r15d
0x140010a86  mov     [rdi+2A8h], rax
0x140010a8d  lea     rax, KbdHid_QueryWmiRegInfo
0x140010a94  mov     [rdi+2B0h], rax
0x140010a9b  lea     rax, KbdHid_QueryWmiDataBlock
0x140010aa2  mov     [rdi+2B8h], rax
0x140010aa9  lea     rax, KbdHid_SetWmiDataBlock
0x140010ab0  mov     [rdi+2C0h], rax
0x140010ab7  lea     rax, KbdHid_SetWmiDataBlock
0x140010abe  mov     [rdi+2C8h], rax
0x140010ac5  mov     [rdi+2D0h], r12
0x140010acc  lea     rcx, [rdi+308h]; SpinLock
0x140010ad3  mov     [rdi+2D8h], r12
0x140010ada  mov     rax, [rsp+68h+SourceDevice]
0x140010ae2  or      dword ptr [rax+30h], 2000h
0x140010ae9  mov     rax, [rsp+68h+SourceDevice]
0x140010af1  and     dword ptr [rax+30h], 0FFFFFF7Fh
0x140010af8  mov     [rdi+300h], r12d
0x140010aff  mov     [rdi+310h], r12d
0x140010b06  mov     [rdi+314h], r12b
0x140010b0d  call    cs:__imp_KeInitializeSpinLock
0x140010b14  nop     dword ptr [rax+rax+00h]
0x140010b19  mov     rcx, [rsp+68h+SourceDevice]; DeviceObject
0x140010b21  call    cs:__imp_IoAllocateWorkItem
0x140010b28  nop     dword ptr [rax+rax+00h]
0x140010b2d  mov     [rdi+2F8h], rax
0x140010b34  test    rax, rax
0x140010b37  jnz     short loc_140010B6E
0x140010b39  mov     esi, 0C000009Ah
0x140010b3e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140010b45  jz      short loc_140010BB6
0x140010b47  mov     rax, [rsp+68h+SourceDevice]
0x140010b4f  lea     r14, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140010b56  mov     dword ptr [rsp+68h+DeviceObject], esi
0x140010b5a  mov     r9d, 0Fh
0x140010b60  mov     qword ptr [rsp+68h+Exclusive], rax
0x140010b65  movzx   edx, r15b
0x140010b69  jmp     loc_14001075A
0x140010b6e  lea     r14, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140010b75  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140010b7c  jz      short loc_140010BB2
0x140010b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b85  mov     r9d, 10h
0x140010b8b  mov     rax, [rsp+68h+SourceDevice]
0x140010b93  mov     r8d, 5
0x140010b99  mov     dword ptr [rsp+68h+DeviceObject], esi
0x140010b9d  mov     dl, 4
0x140010b9f  mov     qword ptr [rsp+68h+Exclusive], rax
0x140010ba4  mov     rcx, [rcx+40h]
0x140010ba8  mov     qword ptr [rsp+68h+DeviceCharacteristics], r14
0x140010bad  call    WPP_RECORDER_SF_qd
0x140010bb2  test    esi, esi
0x140010bb4  jns     short loc_140010C03
0x140010bb6  cmp     [rsp+68h+SourceDevice], r12
0x140010bbe  jz      short loc_140010C03
0x140010bc0  test    rdi, rdi
0x140010bc3  jz      short loc_140010BEF
0x140010bc5  mov     rcx, [rdi+8]; TargetDevice
0x140010bc9  test    rcx, rcx
0x140010bcc  jz      short loc_140010BDA
0x140010bce  call    cs:__imp_IoDetachDevice
0x140010bd5  nop     dword ptr [rax+rax+00h]
0x140010bda  mov     rcx, [rdi+68h]; Irp
0x140010bde  test    rcx, rcx
0x140010be1  jz      short loc_140010BEF
0x140010be3  call    cs:__imp_IoFreeIrp
0x140010bea  nop     dword ptr [rax+rax+00h]
0x140010bef  mov     rcx, [rsp+68h+SourceDevice]; DeviceObject
0x140010bf7  call    cs:__imp_IoDeleteDevice
0x140010bfe  nop     dword ptr [rax+rax+00h]
0x140010c03  mov     rdi, [rsp+68h+arg_0]
0x140010c08  mov     eax, esi
0x140010c0a  mov     rbx, [rsp+68h+arg_8]
0x140010c0f  mov     rbp, [rsp+68h+arg_18]
0x140010c17  add     rsp, 40h
0x140010c1b  pop     r15
0x140010c1d  pop     r14
0x140010c1f  pop     r13
0x140010c21  pop     r12
0x140010c23  pop     rsi
0x140010c24  retn
```
