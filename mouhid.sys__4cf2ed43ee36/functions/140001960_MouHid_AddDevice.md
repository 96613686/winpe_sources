# MouHid_AddDevice

- ea: `0x140001960`
- end: `0x140001fed`
- name: `MouHid_AddDevice`
- size: `1677`
- prototype: `__int64 __fastcall(PVOID IoObject, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x140001464`
- `0x140001524`
- `0x14000171c`
- `0x140001960`
- `0x1400025c8`
- `0x140002830`
- `0x140002a08`

## import_xrefs

- `ntoskrnl!IoDetachDevice` at `0x140001be2`
- `ntoskrnl!IoDetachDevice` at `0x140001be2`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001ca8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001ca8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140001ce9`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140001ce9`
- `ntoskrnl!IoDeleteDevice` at `0x140001bf2`
- `ntoskrnl!IoDeleteDevice` at `0x140001bf2`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140001c65`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140001c65`
- `ntoskrnl!PoSetPowerState` at `0x140001f26`
- `ntoskrnl!PoSetPowerState` at `0x140001f26`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140001ac7`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x140001ac7`
- `ntoskrnl!IoAllocateIrp` at `0x140001b93`
- `ntoskrnl!IoAllocateIrp` at `0x140001b93`
- `ntoskrnl!IoCreateDevice` at `0x1400019fc`
- `ntoskrnl!IoCreateDevice` at `0x1400019fc`
- `ntoskrnl!KeInitializeEvent` at `0x140001c0f`
- `ntoskrnl!KeInitializeEvent` at `0x140001c27`
- `ntoskrnl!KeInitializeEvent` at `0x140001c3f`
- `ntoskrnl!KeInitializeEvent` at `0x140001c98`
- `ntoskrnl!KeInitializeEvent` at `0x140001c0f`
- `ntoskrnl!KeInitializeEvent` at `0x140001c27`
- `ntoskrnl!KeInitializeEvent` at `0x140001c3f`
- `ntoskrnl!KeInitializeEvent` at `0x140001c98`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140001a7f`
- `ntoskrnl!ZwQueryLicenseValue` at `0x140001a7f`
- `ntoskrnl!ZwClose` at `0x140001e6b`
- `ntoskrnl!ZwClose` at `0x140001e6b`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140001ae1`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140001ae1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001a57`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001a57`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140001b0f`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140001b0f`

## pseudocode

```c
__int64 __fastcall MouHid_AddDevice(struct _DRIVER_OBJECT *IoObject, PDEVICE_OBJECT DeviceObject)
{
  struct _DEVICE_OBJECT *v2; // r14
  NTSTATUS v4; // eax
  int v5; // edx
  unsigned int v6; // ebx
  char v8; // al
  int v9; // edx
  int v10; // r9d
  char *DeviceExtension; // rdi
  PDEVICE_OBJECT v12; // rax
  _DWORD *ErrorLogEntry; // rax
  int v14; // edx
  int v15; // r8d
  __int16 v16; // ax
  __int64 v17; // rcx
  PIRP Irp; // rax
  int v19; // edx
  int v20; // r8d
  NTSTATUS v21; // eax
  int v22; // r8d
  int v23; // edx
  __int16 v24; // cx
  int v25; // edx
  __int16 v26; // cx
  int v27; // edx
  int v28; // r8d
  int DeviceCharacteristics; // [rsp+20h] [rbp-40h]
  void *DeviceRegKey; // [rsp+40h] [rbp-20h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+48h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  int v33; // [rsp+B8h] [rbp+58h] BYREF

  SourceDevice = 0;
  v2 = DeviceObject;
  DeviceRegKey = 0;
  v33 = 0;
  DestinationString = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(DeviceObject) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)DeviceObject,
      5,
      12,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
  }
  v4 = IoCreateDevice(IoObject, 0x1D8u, 0, 0xFu, 0, 0, &SourceDevice);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        5,
        13,
        (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
        v4);
    }
    return v6;
  }
  *(&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 1) = -1;
  RtlInitUnicodeString(&DestinationString, L"Kernel-OneCore-DeviceFamilyID");
  v8 = ZwQueryLicenseValue(&DestinationString, 0, &WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 1, 4, &v33);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    WPP_RECORDER_SF_Dd(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      5,
      v10,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      *((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4),
      v8);
  }
  DeviceExtension = (char *)SourceDevice->DeviceExtension;
  v12 = IoAttachDeviceToDeviceStack(SourceDevice, v2);
  *((_QWORD *)DeviceExtension + 1) = v12;
  if ( !v12 )
  {
    ErrorLogEntry = IoAllocateErrorLogEntry(IoObject, 0x30u);
    v6 = -1073741667;
    if ( ErrorLogEntry )
    {
      ErrorLogEntry[3] = -1073414142;
      *ErrorLogEntry = 0;
      *((_QWORD *)ErrorLogEntry + 3) = 0;
      ErrorLogEntry[4] = 0;
      ErrorLogEntry[5] = -1073741667;
      IoWriteErrorLogEntry(ErrorLogEntry);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        v15,
        15,
        (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
        (char)SourceDevice,
        157);
    }
LABEL_19:
    IoDeleteDevice(SourceDevice);
    return v6;
  }
  *(_QWORD *)DeviceExtension = SourceDevice;
  DeviceExtension[32] = 0;
  DeviceExtension[34] = 0;
  *((_DWORD *)DeviceExtension + 14) = 0;
  *((_DWORD *)DeviceExtension + 34) = 0;
  v16 = _InterlockedExchangeAdd((volatile signed __int32 *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters, 1u);
  v17 = *((_QWORD *)DeviceExtension + 1);
  *((_WORD *)DeviceExtension + 18) = v16 + 1;
  *((_QWORD *)DeviceExtension + 2) = v2;
  Irp = IoAllocateIrp(*(_BYTE *)(v17 + 76), 0);
  *((_QWORD *)DeviceExtension + 14) = Irp;
  if ( !Irp )
  {
    v6 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        v20,
        16,
        (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
        (char)SourceDevice,
        154);
    }
    IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 1));
    goto LABEL_19;
  }
  KeInitializeEvent((PRKEVENT)DeviceExtension + 6, SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)DeviceExtension + 7, NotificationEvent, 1u);
  KeInitializeEvent((PRKEVENT)DeviceExtension + 8, NotificationEvent, 1u);
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 240), 0x48756F4Du, 1u, 0, 0x20u);
  *((_QWORD *)DeviceExtension + 16) = 0;
  *((_DWORD *)DeviceExtension + 68) = 1;
  *((_QWORD *)DeviceExtension + 35) = 0;
  *((_DWORD *)DeviceExtension + 72) = 0;
  KeInitializeEvent((PRKEVENT)(DeviceExtension + 296), SynchronizationEvent, 0);
  KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 8);
  *((_WORD *)DeviceExtension + 176) = *((_WORD *)DeviceExtension + 18);
  *((_WORD *)DeviceExtension + 188) = 128;
  *((_WORD *)DeviceExtension + 190) = 0;
  *((_DWORD *)DeviceExtension + 96) = 2;
  v21 = IoOpenDeviceRegistryKey(v2, 1u, 0x1F0000u, &DeviceRegKey);
  *((_WORD *)DeviceExtension + 24) = 0;
  DeviceExtension[88] = 0;
  *(_DWORD *)(DeviceExtension + 90) = 0;
  DeviceExtension[94] = 0;
  *((_DWORD *)DeviceExtension + 24) = 0;
  *((_DWORD *)DeviceExtension + 25) = 1;
  *((_DWORD *)DeviceExtension + 26) = 1;
  if ( v21 >= 0 )
  {
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      DeviceExtension[48] = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      DeviceExtension[49] = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) < 0 )
    {
      *((_DWORD *)DeviceExtension + 19) = 120;
      *((_DWORD *)DeviceExtension + 18) = 120;
    }
    else
    {
      *((_DWORD *)DeviceExtension + 19) = 0;
      *((_DWORD *)DeviceExtension + 18) = 0;
    }
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) < 0 )
    {
      *((_DWORD *)DeviceExtension + 21) = 120;
      *((_DWORD *)DeviceExtension + 20) = 120;
    }
    else
    {
      *((_DWORD *)DeviceExtension + 21) = 0;
      *((_DWORD *)DeviceExtension + 20) = 0;
    }
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      DeviceExtension[88] = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      *((_WORD *)DeviceExtension + 45) = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      *((_WORD *)DeviceExtension + 46) = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      DeviceExtension[94] = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      *((_WORD *)DeviceExtension + 48) = 0;
    if ( (int)MouHid_QueryDeviceKey(DeviceRegKey) >= 0 )
      *((_WORD *)DeviceExtension + 49) = 0;
    ZwClose(DeviceRegKey);
  }
  v23 = *((unsigned __int16 *)DeviceExtension + 45);
  v24 = *((_WORD *)DeviceExtension + 46);
  if ( (_WORD)v23 )
  {
    if ( v24 )
      goto LABEL_51;
  }
  else if ( !v24 )
  {
    goto LABEL_51;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v23,
      v22,
      17,
      DeviceCharacteristics,
      (char)SourceDevice,
      v23,
      v24);
  *(_DWORD *)(DeviceExtension + 90) = 0;
LABEL_51:
  v25 = *((unsigned __int16 *)DeviceExtension + 48);
  v26 = *((_WORD *)DeviceExtension + 49);
  if ( (_WORD)v25 )
  {
    if ( !v26 )
    {
LABEL_55:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          v22,
          18,
          DeviceCharacteristics,
          (char)SourceDevice,
          v25,
          v26);
      *((_DWORD *)DeviceExtension + 24) = 0;
    }
  }
  else if ( v26 )
  {
    goto LABEL_55;
  }
  PoSetPowerState(SourceDevice, DevicePowerState, (POWER_STATE)1);
  *((_DWORD *)DeviceExtension + 102) = 1;
  *((_QWORD *)DeviceExtension + 52) = &MouHid_WmiGuidList;
  *((_QWORD *)DeviceExtension + 53) = MouHid_QueryWmiRegInfo;
  *((_QWORD *)DeviceExtension + 54) = MouHid_QueryWmiDataBlock;
  *((_QWORD *)DeviceExtension + 55) = MouHid_SetWmiDataItem;
  *((_QWORD *)DeviceExtension + 56) = MouHid_SetWmiDataItem;
  *((_QWORD *)DeviceExtension + 57) = 0;
  *((_QWORD *)DeviceExtension + 58) = 0;
  SourceDevice->Flags |= 0x2000u;
  SourceDevice->Flags &= ~0x80u;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v27) = 4;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      v27,
      v28,
      19,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      (char)SourceDevice,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x140001960  mov     [rsp-38h+arg_0], rbx
0x140001965  push    rbp
0x140001966  push    rsi
0x140001967  push    rdi
0x140001968  push    r12
0x14000196a  push    r13
0x14000196c  push    r14
0x14000196e  push    r15
0x140001970  mov     rbp, rsp
0x140001973  sub     rsp, 60h
0x140001977  xor     r15d, r15d
0x14000197a  xorps   xmm0, xmm0
0x14000197d  mov     [rbp+SourceDevice], r15
0x140001981  mov     r14, rdx
0x140001984  mov     [rbp+DeviceRegKey], r15
0x140001988  mov     rsi, rcx
0x14000198b  mov     [rbp+arg_10], r15d
0x14000198f  mov     [rbp+arg_18], r15d
0x140001993  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140001997  lea     r12, WPP_RECORDER_INITIALIZED
0x14000199e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400019a5  lea     r13, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400019ac  lea     edi, [r15+5]
0x1400019b0  jz      short loc_1400019D8
0x1400019b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019b9  cmp     [rcx+48h], r15w
0x1400019be  jz      short loc_1400019D8
0x1400019c0  mov     rcx, [rcx+40h]
0x1400019c4  lea     r9d, [r15+0Ch]
0x1400019c8  mov     r8d, edi
0x1400019cb  mov     qword ptr [rsp+60h+DeviceCharacteristics], r13
0x1400019d0  mov     dl, dil
0x1400019d3  call    WPP_RECORDER_SF_
0x1400019d8  lea     rax, [rbp+SourceDevice]
0x1400019dc  mov     r9d, 0Fh; DeviceType
0x1400019e2  mov     [rsp+60h+DeviceObject], rax; DeviceObject
0x1400019e7  xor     r8d, r8d; DeviceName
0x1400019ea  mov     [rsp+60h+Exclusive], r15b; Exclusive
0x1400019ef  mov     edx, 1D8h; DeviceExtensionSize
0x1400019f4  mov     rcx, rsi; DriverObject
0x1400019f7  mov     [rsp+60h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400019fc  call    cs:__imp_IoCreateDevice
0x140001a03  nop     dword ptr [rax+rax+00h]
0x140001a08  mov     ebx, eax
0x140001a0a  test    eax, eax
0x140001a0c  jns     short loc_140001A42
0x140001a0e  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001a15  jz      short loc_140001A3B
0x140001a17  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a1e  mov     r9d, 0Dh
0x140001a24  mov     dword ptr [rsp+60h+Exclusive], eax
0x140001a28  mov     r8d, edi
0x140001a2b  mov     dl, 2
0x140001a2d  mov     qword ptr [rsp+60h+DeviceCharacteristics], r13
0x140001a32  mov     rcx, [rcx+40h]
0x140001a36  call    WPP_RECORDER_SF_d
0x140001a3b  mov     eax, ebx
0x140001a3d  jmp     loc_140001FD4
0x140001a42  lea     rdx, SourceString; "Kernel-OneCore-DeviceFamilyID"
0x140001a49  mov     dword ptr cs:WPP_MAIN_CB.Queue+2Ch, 0FFFFFFFFh
0x140001a53  lea     rcx, [rbp+DestinationString]; DestinationString
0x140001a57  call    cs:__imp_RtlInitUnicodeString
0x140001a5e  nop     dword ptr [rax+rax+00h]
0x140001a63  lea     rax, [rbp+arg_18]
0x140001a67  mov     r9d, 4
0x140001a6d  lea     r8, WPP_MAIN_CB.Queue+2Ch
0x140001a74  mov     qword ptr [rsp+60h+DeviceCharacteristics], rax
0x140001a79  xor     edx, edx
0x140001a7b  lea     rcx, [rbp+DestinationString]
0x140001a7f  call    cs:__imp_ZwQueryLicenseValue
0x140001a86  nop     dword ptr [rax+rax+00h]
0x140001a8b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001a92  jz      short loc_140001ABC
0x140001a94  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a9b  mov     r8d, edi
0x140001a9e  mov     dword ptr [rsp+60h+DeviceObject], eax
0x140001aa2  mov     dl, 4
0x140001aa4  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+2Ch
0x140001aaa  mov     dword ptr [rsp+60h+Exclusive], eax
0x140001aae  mov     rcx, [rcx+40h]
0x140001ab2  mov     qword ptr [rsp+60h+DeviceCharacteristics], r13
0x140001ab7  call    WPP_RECORDER_SF_Dd
0x140001abc  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x140001ac0  mov     rdx, r14; TargetDevice
0x140001ac3  mov     rdi, [rcx+40h]
0x140001ac7  call    cs:__imp_IoAttachDeviceToDeviceStack
0x140001ace  nop     dword ptr [rax+rax+00h]
0x140001ad3  mov     [rdi+8], rax
0x140001ad7  test    rax, rax
0x140001ada  jnz     short loc_140001B57
0x140001adc  mov     dl, 30h ; '0'; EntrySize
0x140001ade  mov     rcx, rsi; IoObject
0x140001ae1  call    cs:__imp_IoAllocateErrorLogEntry
0x140001ae8  nop     dword ptr [rax+rax+00h]
0x140001aed  mov     ebx, 0C000009Dh
0x140001af2  test    rax, rax
0x140001af5  jz      short loc_140001B1B
0x140001af7  mov     rcx, rax; ElEntry
0x140001afa  mov     dword ptr [rax+0Ch], 0C0050002h
0x140001b01  mov     [rax], r15d
0x140001b04  mov     [rax+18h], r15
0x140001b08  mov     [rax+10h], r15d
0x140001b0c  mov     [rax+14h], ebx
0x140001b0f  call    cs:__imp_IoWriteErrorLogEntry
0x140001b16  nop     dword ptr [rax+rax+00h]
0x140001b1b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001b22  jz      loc_140001BEE
0x140001b28  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b2f  mov     r9d, 0Fh
0x140001b35  mov     rax, [rbp+SourceDevice]
0x140001b39  mov     dl, 2
0x140001b3b  mov     dword ptr [rsp+60h+DeviceObject], ebx
0x140001b3f  mov     qword ptr [rsp+60h+Exclusive], rax
0x140001b44  mov     rcx, [rcx+40h]
0x140001b48  mov     qword ptr [rsp+60h+DeviceCharacteristics], r13
0x140001b4d  call    WPP_RECORDER_SF_qd
0x140001b52  jmp     loc_140001BEE
0x140001b57  mov     rax, [rbp+SourceDevice]
0x140001b5b  mov     ebx, 1
0x140001b60  mov     [rdi], rax
0x140001b63  mov     eax, ebx
0x140001b65  mov     [rdi+20h], r15b
0x140001b69  mov     [rdi+22h], r15b
0x140001b6d  mov     [rdi+38h], r15d
0x140001b71  mov     [rdi+88h], r15d
0x140001b78  lock xadd dword ptr cs:WPP_MAIN_CB.Queue+28h, eax
0x140001b80  mov     rcx, [rdi+8]
0x140001b84  add     eax, ebx
0x140001b86  mov     [rdi+24h], ax
0x140001b8a  xor     edx, edx; ChargeQuota
0x140001b8c  mov     [rdi+10h], r14
0x140001b90  mov     cl, [rcx+4Ch]; StackSize
0x140001b93  call    cs:__imp_IoAllocateIrp
0x140001b9a  nop     dword ptr [rax+rax+00h]
0x140001b9f  mov     [rdi+70h], rax
0x140001ba3  test    rax, rax
0x140001ba6  jnz     short loc_140001C03
0x140001ba8  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140001baf  mov     ebx, 0C000009Ah
0x140001bb4  jz      short loc_140001BDE
0x140001bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bbd  lea     r9d, [rax+10h]
0x140001bc1  mov     rax, [rbp+SourceDevice]
0x140001bc5  mov     dl, 2
0x140001bc7  mov     dword ptr [rsp+60h+DeviceObject], ebx
0x140001bcb  mov     qword ptr [rsp+60h+Exclusive], rax
0x140001bd0  mov     rcx, [rcx+40h]
0x140001bd4  mov     qword ptr [rsp+60h+DeviceCharacteristics], r13
0x140001bd9  call    WPP_RECORDER_SF_qd
0x140001bde  mov     rcx, [rdi+8]; TargetDevice
0x140001be2  call    cs:__imp_IoDetachDevice
0x140001be9  nop     dword ptr [rax+rax+00h]
0x140001bee  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x140001bf2  call    cs:__imp_IoDeleteDevice
0x140001bf9  nop     dword ptr [rax+rax+00h]
0x140001bfe  jmp     loc_140001A3B
0x140001c03  lea     rcx, [rdi+90h]; Event
0x140001c0a  xor     r8d, r8d; State
0x140001c0d  mov     edx, ebx; Type
0x140001c0f  call    cs:__imp_KeInitializeEvent
0x140001c16  nop     dword ptr [rax+rax+00h]
0x140001c1b  lea     rcx, [rdi+0A8h]; Event
0x140001c22  mov     r8b, bl; State
0x140001c25  xor     edx, edx; Type
0x140001c27  call    cs:__imp_KeInitializeEvent
0x140001c2e  nop     dword ptr [rax+rax+00h]
0x140001c33  lea     rcx, [rdi+0C0h]; Event
0x140001c3a  mov     r8b, bl; State
0x140001c3d  xor     edx, edx; Type
0x140001c3f  call    cs:__imp_KeInitializeEvent
0x140001c46  nop     dword ptr [rax+rax+00h]
0x140001c4b  lea     rcx, [rdi+0F0h]; Lock
0x140001c52  mov     [rsp+60h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x140001c5a  xor     r9d, r9d; HighWatermark
0x140001c5d  mov     r8d, ebx; MaxLockedMinutes
0x140001c60  mov     edx, 48756F4Dh; AllocateTag
0x140001c65  call    cs:__imp_IoInitializeRemoveLockEx
0x140001c6c  nop     dword ptr [rax+rax+00h]
0x140001c71  lea     rcx, [rdi+128h]; Event
0x140001c78  mov     [rdi+80h], r15
0x140001c7f  xor     r8d, r8d; State
0x140001c82  mov     [rdi+110h], ebx
0x140001c88  mov     edx, ebx; Type
0x140001c8a  mov     [rdi+118h], r15
0x140001c91  mov     [rdi+120h], r15d
0x140001c98  call    cs:__imp_KeInitializeEvent
0x140001c9f  nop     dword ptr [rax+rax+00h]
0x140001ca4  lea     rcx, [rdi+40h]; SpinLock
0x140001ca8  call    cs:__imp_KeInitializeSpinLock
0x140001caf  nop     dword ptr [rax+rax+00h]
0x140001cb4  movzx   eax, word ptr [rdi+24h]
0x140001cb8  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140001cbc  mov     r8d, 1F0000h; DesiredAccess
0x140001cc2  mov     [rdi+160h], ax
0x140001cc9  mov     edx, ebx; DevInstKeyType
0x140001ccb  mov     word ptr [rdi+178h], 80h
0x140001cd4  mov     rcx, r14; DeviceObject
0x140001cd7  mov     [rdi+17Ch], r15w
0x140001cdf  mov     dword ptr [rdi+180h], 2
0x140001ce9  call    cs:__imp_IoOpenDeviceRegistryKey
0x140001cf0  nop     dword ptr [rax+rax+00h]
0x140001cf5  mov     [rdi+30h], r15w
0x140001cfa  mov     [rdi+58h], r15b
0x140001cfe  mov     [rdi+5Ah], r15d
0x140001d02  mov     [rdi+5Eh], r15b
0x140001d06  mov     [rdi+60h], r15d
0x140001d0a  mov     [rdi+64h], ebx
0x140001d0d  mov     [rdi+68h], ebx
0x140001d10  test    eax, eax
0x140001d12  js      loc_140001E77
0x140001d18  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001d1c  lea     r8, [rbp+arg_10]
0x140001d20  lea     rdx, aFlipflopwheel; "FlipFlopWheel"
0x140001d27  call    MouHid_QueryDeviceKey
0x140001d2c  test    eax, eax
0x140001d2e  js      short loc_140001D36
0x140001d30  mov     al, byte ptr [rbp+arg_10]
0x140001d33  mov     [rdi+30h], al
0x140001d36  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001d3a  lea     r8, [rbp+arg_10]
0x140001d3e  lea     rdx, aFlipflophscrol; "FlipFlopHScroll"
0x140001d45  call    MouHid_QueryDeviceKey
0x140001d4a  test    eax, eax
0x140001d4c  js      short loc_140001D54
0x140001d4e  mov     al, byte ptr [rbp+arg_10]
0x140001d51  mov     [rdi+31h], al
0x140001d54  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001d58  lea     r8, [rbp+arg_10]
0x140001d5c  lea     rdx, aWheelscalingfa; "WheelScalingFactor"
0x140001d63  call    MouHid_QueryDeviceKey
0x140001d68  mov     esi, 78h ; 'x'
0x140001d6d  test    eax, eax
0x140001d6f  js      short loc_140001D7C
0x140001d71  mov     eax, [rbp+arg_10]
0x140001d74  mov     [rdi+4Ch], eax
0x140001d77  mov     [rdi+48h], eax
0x140001d7a  jmp     short loc_140001D82
0x140001d7c  mov     [rdi+4Ch], esi
0x140001d7f  mov     [rdi+48h], esi
0x140001d82  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001d86  lea     r8, [rbp+arg_10]
0x140001d8a  lea     rdx, aHscrollscaling; "HScrollScalingFactor"
0x140001d91  call    MouHid_QueryDeviceKey
0x140001d96  test    eax, eax
0x140001d98  js      short loc_140001DA5
0x140001d9a  mov     eax, [rbp+arg_10]
0x140001d9d  mov     [rdi+54h], eax
0x140001da0  mov     [rdi+50h], eax
0x140001da3  jmp     short loc_140001DAB
0x140001da5  mov     [rdi+54h], esi
0x140001da8  mov     [rdi+50h], esi
0x140001dab  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001daf  lea     r8, [rbp+arg_10]
0x140001db3  lea     rdx, aVscrollhighres; "VScrollHighResolutionDisable"
0x140001dba  call    MouHid_QueryDeviceKey
0x140001dbf  test    eax, eax
0x140001dc1  js      short loc_140001DC9
0x140001dc3  mov     al, byte ptr [rbp+arg_10]
0x140001dc6  mov     [rdi+58h], al
0x140001dc9  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001dcd  lea     r8, [rbp+arg_10]
0x140001dd1  lea     rdx, aVscrollpageove; "VScrollPageOverride"
0x140001dd8  call    MouHid_QueryDeviceKey
0x140001ddd  test    eax, eax
0x140001ddf  js      short loc_140001DE9
0x140001de1  movzx   eax, word ptr [rbp+arg_10]
0x140001de5  mov     [rdi+5Ah], ax
0x140001de9  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001ded  lea     r8, [rbp+arg_10]
0x140001df1  lea     rdx, aVscrollusageov; "VScrollUsageOverride"
0x140001df8  call    MouHid_QueryDeviceKey
0x140001dfd  test    eax, eax
0x140001dff  js      short loc_140001E09
0x140001e01  movzx   eax, word ptr [rbp+arg_10]
0x140001e05  mov     [rdi+5Ch], ax
0x140001e09  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001e0d  lea     r8, [rbp+arg_10]
0x140001e11  lea     rdx, aHscrollhighres; "HScrollHighResolutionDisable"
0x140001e18  call    MouHid_QueryDeviceKey
0x140001e1d  test    eax, eax
0x140001e1f  js      short loc_140001E27
0x140001e21  mov     al, byte ptr [rbp+arg_10]
0x140001e24  mov     [rdi+5Eh], al
0x140001e27  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001e2b  lea     r8, [rbp+arg_10]
0x140001e2f  lea     rdx, aHscrollpageove; "HScrollPageOverride"
0x140001e36  call    MouHid_QueryDeviceKey
0x140001e3b  test    eax, eax
0x140001e3d  js      short loc_140001E47
0x140001e3f  movzx   eax, word ptr [rbp+arg_10]
0x140001e43  mov     [rdi+60h], ax
0x140001e47  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001e4b  lea     r8, [rbp+arg_10]
0x140001e4f  lea     rdx, aHscrollusageov; "HScrollUsageOverride"
0x140001e56  call    MouHid_QueryDeviceKey
0x140001e5b  test    eax, eax
0x140001e5d  js      short loc_140001E67
0x140001e5f  movzx   eax, word ptr [rbp+arg_10]
0x140001e63  mov     [rdi+62h], ax
0x140001e67  mov     rcx, [rbp+DeviceRegKey]; Handle
  ... truncated ...
```
