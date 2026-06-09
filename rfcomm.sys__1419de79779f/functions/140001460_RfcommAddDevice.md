# RfcommAddDevice

- ea: `0x140001460`
- end: `0x1400017f8`
- name: `RfcommAddDevice`
- size: `920`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001460`
- `0x140001d24`
- `0x140004e58`
- `0x140005050`
- `0x1400060c4`
- `0x14001bfa8`
- `0x14001fd40`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140001623`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000164b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001676`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001623`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000164b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001676`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400014c4`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x1400014c4`
- `ntoskrnl!IoCreateDevice` at `0x140001511`
- `ntoskrnl!IoCreateDevice` at `0x140001511`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140001555`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x140001555`
- `ntoskrnl!IoDeleteDevice` at `0x14000156f`
- `ntoskrnl!IoDeleteDevice` at `0x140001727`
- `ntoskrnl!IoDeleteDevice` at `0x14000156f`
- `ntoskrnl!IoDeleteDevice` at `0x140001727`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001685`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001685`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001713`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001713`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14000175b`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14000175b`
- `ntoskrnl!KeInitializeTimer` at `0x14000176e`
- `ntoskrnl!KeInitializeTimer` at `0x14000176e`
- `ntoskrnl!KeInitializeDpc` at `0x14000178b`
- `ntoskrnl!KeInitializeDpc` at `0x14000178b`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400017b8`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400017b8`

## pseudocode

```c
__int64 __fastcall RfcommAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  KSPIN_LOCK *DriverObjectExtension; // rsi
  NTSTATUS v5; // edi
  char *DeviceExtension; // rbx
  void *v7; // rbx
  const char *v8; // rax
  int v9; // edx
  char **v11; // rax
  KSPIN_LOCK v12; // rcx
  _QWORD *v13; // rcx
  void **v14; // rax
  PDEVICE_OBJECT v15; // rax
  PDEVICE_OBJECT SourceDevice; // [rsp+90h] [rbp+18h] BYREF

  SourceDevice = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)TargetDevice,
      3,
      16,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (char)DriverObject,
      (char)TargetDevice);
  DriverObjectExtension = (KSPIN_LOCK *)IoGetDriverObjectExtension(DriverObject, DriverEntry);
  if ( !DriverObjectExtension )
  {
    v5 = -1073741670;
    goto LABEL_9;
  }
  v5 = IoCreateDevice(DriverObject, 0x1A8u, 0, 0x12u, 0x100u, 0, &SourceDevice);
  if ( v5 >= 0 && SourceDevice )
  {
    DeviceExtension = (char *)SourceDevice->DeviceExtension;
    memset(DeviceExtension, 0, 0x1A8u);
    v5 = IoRegisterDeviceInterface(
           TargetDevice,
           &GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE,
           0,
           (PUNICODE_STRING)(DeviceExtension + 344));
    if ( v5 < 0 )
    {
      IoDeleteDevice(SourceDevice);
      goto LABEL_9;
    }
    *((_DWORD *)DeviceExtension + 4) = 542065734;
    *((_QWORD *)DeviceExtension + 9) = TargetDevice;
    *((_QWORD *)DeviceExtension + 10) = SourceDevice;
    *((_QWORD *)DeviceExtension + 35) = DeviceExtension + 272;
    *((_QWORD *)DeviceExtension + 34) = DeviceExtension + 272;
    *((_QWORD *)DeviceExtension + 37) = DeviceExtension + 288;
    *((_QWORD *)DeviceExtension + 36) = DeviceExtension + 288;
    *((_QWORD *)DeviceExtension + 12) = DriverObjectExtension;
    *((_QWORD *)DeviceExtension + 38) = 0;
    *((_DWORD *)DeviceExtension + 28) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 3);
    DeviceExtension[265] = 1;
    *((_QWORD *)DeviceExtension + 49) = DeviceExtension + 384;
    *((_QWORD *)DeviceExtension + 48) = DeviceExtension + 384;
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 46);
    *((_DWORD *)DeviceExtension + 94) = 0;
    *((_QWORD *)DeviceExtension + 52) = DeviceExtension + 408;
    *((_QWORD *)DeviceExtension + 51) = DeviceExtension + 408;
    KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 50);
    *((_BYTE *)DriverObjectExtension + 8) = KeAcquireSpinLockRaiseToDpc(DriverObjectExtension);
    v11 = (char **)(DriverObjectExtension + 3);
    v12 = DriverObjectExtension[3];
    if ( *(KSPIN_LOCK **)(v12 + 8) != DriverObjectExtension + 3 )
      goto LABEL_20;
    *(_QWORD *)DeviceExtension = v12;
    *((_QWORD *)DeviceExtension + 1) = v11;
    *(_QWORD *)(v12 + 8) = DeviceExtension;
    *v11 = DeviceExtension;
    KeReleaseSpinLock(DriverObjectExtension, *((_BYTE *)DriverObjectExtension + 8));
    v5 = TdiAddDevice(DriverObjectExtension);
    if ( v5 < 0 )
    {
      *((_BYTE *)DriverObjectExtension + 8) = KeAcquireSpinLockRaiseToDpc(DriverObjectExtension);
      v13 = *(_QWORD **)DeviceExtension;
      if ( *(char **)(*(_QWORD *)DeviceExtension + 8LL) == DeviceExtension )
      {
        v14 = (void **)*((_QWORD *)DeviceExtension + 1);
        if ( *v14 == DeviceExtension )
        {
          *v14 = v13;
          v13[1] = v14;
          *((_QWORD *)DeviceExtension + 1) = DeviceExtension;
          *(_QWORD *)DeviceExtension = DeviceExtension;
          KeReleaseSpinLock(DriverObjectExtension, *((_BYTE *)DriverObjectExtension + 8));
          IoDeleteDevice(SourceDevice);
          SourceDevice = 0;
          goto LABEL_9;
        }
      }
LABEL_20:
      __fastfail(3u);
    }
    IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), 0x42436652u, 0, 0, 0x20u);
    KeInitializeTimer((PKTIMER)(DeviceExtension + 136));
    KeInitializeDpc((PRKDPC)(DeviceExtension + 200), RfcommIoTimerDpc, 0);
    DeviceExtension[264] = 0;
    SourceDevice->Flags |= 0x2010u;
    v15 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
    *((_QWORD *)DeviceExtension + 11) = v15;
    if ( v15 )
    {
      SourceDevice->Flags &= ~0x80u;
    }
    else
    {
      v5 = -1073741823;
      RfcommDeleteDevice(DeviceExtension);
    }
  }
LABEL_9:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = WPP_GLOBAL_Control->DeviceExtension;
    v8 = NtStatusTxt(v5);
    WPP_RECORDER_SF_qs(
      (_DWORD)v7,
      v9,
      4,
      17,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      (char)SourceDevice,
      (__int64)v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140001460  mov     rax, rsp
0x140001463  push    rbx
0x140001464  push    rbp
0x140001465  push    rsi
0x140001466  push    rdi
0x140001467  push    r12
0x140001469  push    r13
0x14000146b  sub     rsp, 48h
0x14000146f  mov     rbp, rdx
0x140001472  mov     qword ptr [rax+18h], 0
0x14000147a  mov     rbx, rcx
0x14000147d  lea     r12, WPP_RECORDER_INITIALIZED
0x140001484  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000148b  lea     r13, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001492  jz      short loc_1400014BA
0x140001494  mov     [rax-48h], rdx
0x140001498  mov     r9d, 10h
0x14000149e  mov     [rax-50h], rcx
0x1400014a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400014a9  mov     [rax-58h], r13
0x1400014ad  lea     r8d, [r9-0Dh]
0x1400014b1  mov     rcx, [rcx+40h]
0x1400014b5  call    WPP_RECORDER_SF_qq
0x1400014ba  lea     rdx, DriverEntry; ClientIdentificationAddress
0x1400014c1  mov     rcx, rbx; DriverObject
0x1400014c4  call    cs:__imp_IoGetDriverObjectExtension
0x1400014cb  nop     dword ptr [rax+rax+00h]
0x1400014d0  mov     rsi, rax
0x1400014d3  test    rax, rax
0x1400014d6  jnz     short loc_1400014E2
0x1400014d8  mov     edi, 0C000009Ah
0x1400014dd  jmp     loc_140001582
0x1400014e2  lea     rax, [rsp+78h+SourceDevice]
0x1400014ea  mov     r13d, 1A8h
0x1400014f0  mov     [rsp+78h+DeviceObject], rax; DeviceObject
0x1400014f5  mov     r9d, 12h; DeviceType
0x1400014fb  mov     [rsp+78h+Exclusive], 0; Exclusive
0x140001500  xor     r8d, r8d; DeviceName
0x140001503  mov     edx, r13d; DeviceExtensionSize
0x140001506  mov     [rsp+78h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14000150e  mov     rcx, rbx; DriverObject
0x140001511  call    cs:__imp_IoCreateDevice
0x140001518  nop     dword ptr [rax+rax+00h]
0x14000151d  mov     edi, eax
0x14000151f  test    eax, eax
0x140001521  js      short loc_14000157B
0x140001523  mov     rbx, [rsp+78h+SourceDevice]
0x14000152b  test    rbx, rbx
0x14000152e  jz      short loc_14000157B
0x140001530  mov     rbx, [rbx+40h]
0x140001534  mov     r8d, r13d; Size
0x140001537  mov     rcx, rbx; void *
0x14000153a  xor     edx, edx; Val
0x14000153c  call    memset
0x140001541  lea     r9, [rbx+158h]; SymbolicLinkName
0x140001548  xor     r8d, r8d; ReferenceString
0x14000154b  lea     rdx, GUID_BTH_RFCOMM_FIREWALL_DEVICE_INTERFACE; InterfaceClassGuid
0x140001552  mov     rcx, rbp; PhysicalDeviceObject
0x140001555  call    cs:__imp_IoRegisterDeviceInterface
0x14000155c  nop     dword ptr [rax+rax+00h]
0x140001561  mov     edi, eax
0x140001563  test    eax, eax
0x140001565  jns     short loc_1400015D6
0x140001567  mov     rcx, [rsp+78h+SourceDevice]; DeviceObject
0x14000156f  call    cs:__imp_IoDeleteDevice
0x140001576  nop     dword ptr [rax+rax+00h]
0x14000157b  lea     r13, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001582  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001589  jz      short loc_1400015C6
0x14000158b  mov     rax, cs:WPP_GLOBAL_Control
0x140001592  mov     ecx, edi
0x140001594  mov     rbx, [rax+40h]
0x140001598  call    NtStatusTxt
0x14000159d  mov     [rsp+78h+DeviceObject], rax
0x1400015a2  mov     r9d, 11h
0x1400015a8  mov     rax, [rsp+78h+SourceDevice]
0x1400015b0  mov     rcx, rbx
0x1400015b3  mov     qword ptr [rsp+78h+Exclusive], rax
0x1400015b8  mov     qword ptr [rsp+78h+DeviceCharacteristics], r13
0x1400015bd  lea     r8d, [r9-0Dh]
0x1400015c1  call    WPP_RECORDER_SF_qs
0x1400015c6  mov     eax, edi
0x1400015c8  add     rsp, 48h
0x1400015cc  pop     r13
0x1400015ce  pop     r12
0x1400015d0  pop     rdi
0x1400015d1  pop     rsi
0x1400015d2  pop     rbp
0x1400015d3  pop     rbx
0x1400015d4  retn
0x1400015d6  mov     dword ptr [rbx+10h], 204F4446h
0x1400015dd  lea     rcx, [rbx+18h]; SpinLock
0x1400015e1  mov     [rbx+48h], rbp
0x1400015e5  mov     rax, [rsp+78h+SourceDevice]
0x1400015ed  mov     [rbx+50h], rax
0x1400015f1  lea     rax, [rbx+110h]
0x1400015f8  mov     [rax+8], rax
0x1400015fc  mov     [rax], rax
0x1400015ff  lea     rax, [rbx+120h]
0x140001606  mov     [rax+8], rax
0x14000160a  mov     [rax], rax
0x14000160d  mov     [rbx+60h], rsi
0x140001611  mov     qword ptr [rbx+130h], 0
0x14000161c  mov     dword ptr [rbx+70h], 0
0x140001623  call    cs:__imp_KeInitializeSpinLock
0x14000162a  nop     dword ptr [rax+rax+00h]
0x14000162f  lea     rax, [rbx+180h]
0x140001636  mov     byte ptr [rbx+109h], 1
0x14000163d  lea     rcx, [rbx+170h]; SpinLock
0x140001644  mov     [rax+8], rax
0x140001648  mov     [rax], rax
0x14000164b  call    cs:__imp_KeInitializeSpinLock
0x140001652  nop     dword ptr [rax+rax+00h]
0x140001657  lea     rax, [rbx+198h]
0x14000165e  mov     dword ptr [rbx+178h], 0
0x140001668  lea     rcx, [rbx+190h]; SpinLock
0x14000166f  mov     [rax+8], rax
0x140001673  mov     [rax], rax
0x140001676  call    cs:__imp_KeInitializeSpinLock
0x14000167d  nop     dword ptr [rax+rax+00h]
0x140001682  mov     rcx, rsi; SpinLock
0x140001685  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000168c  nop     dword ptr [rax+rax+00h]
0x140001691  mov     [rsi+8], al
0x140001694  lea     rax, [rsi+18h]
0x140001698  mov     rcx, [rax]
0x14000169b  cmp     [rcx+8], rax
0x14000169f  jnz     loc_1400017F1
0x1400016a5  mov     [rbx], rcx
0x1400016a8  mov     [rbx+8], rax
0x1400016ac  mov     [rcx+8], rbx
0x1400016b0  mov     rcx, rsi; SpinLock
0x1400016b3  mov     [rax], rbx
0x1400016b6  mov     dl, [rsi+8]; NewIrql
0x1400016b9  call    cs:__imp_KeReleaseSpinLock
0x1400016c0  nop     dword ptr [rax+rax+00h]
0x1400016c5  mov     rcx, rsi; SpinLock
0x1400016c8  call    TdiAddDevice
0x1400016cd  mov     edi, eax
0x1400016cf  test    eax, eax
0x1400016d1  jns     short loc_140001744
0x1400016d3  mov     rcx, rsi; SpinLock
0x1400016d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400016dd  nop     dword ptr [rax+rax+00h]
0x1400016e2  mov     [rsi+8], al
0x1400016e5  mov     rcx, [rbx]
0x1400016e8  cmp     [rcx+8], rbx
0x1400016ec  jnz     loc_1400017F1
0x1400016f2  mov     rax, [rbx+8]
0x1400016f6  cmp     [rax], rbx
0x1400016f9  jnz     loc_1400017F1
0x1400016ff  mov     [rax], rcx
0x140001702  mov     [rcx+8], rax
0x140001706  mov     rcx, rsi; SpinLock
0x140001709  mov     [rbx+8], rbx
0x14000170d  mov     [rbx], rbx
0x140001710  mov     dl, [rsi+8]; NewIrql
0x140001713  call    cs:__imp_KeReleaseSpinLock
0x14000171a  nop     dword ptr [rax+rax+00h]
0x14000171f  mov     rcx, [rsp+78h+SourceDevice]; DeviceObject
0x140001727  call    cs:__imp_IoDeleteDevice
0x14000172e  nop     dword ptr [rax+rax+00h]
0x140001733  mov     [rsp+78h+SourceDevice], 0
0x14000173f  jmp     loc_14000157B
0x140001744  lea     rcx, [rbx+28h]; Lock
0x140001748  mov     [rsp+78h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x140001750  xor     r9d, r9d; HighWatermark
0x140001753  xor     r8d, r8d; MaxLockedMinutes
0x140001756  mov     edx, 42436652h; AllocateTag
0x14000175b  call    cs:__imp_IoInitializeRemoveLockEx
0x140001762  nop     dword ptr [rax+rax+00h]
0x140001767  lea     rcx, [rbx+88h]; Timer
0x14000176e  call    cs:__imp_KeInitializeTimer
0x140001775  nop     dword ptr [rax+rax+00h]
0x14000177a  lea     rcx, [rbx+0C8h]; Dpc
0x140001781  xor     r8d, r8d; DeferredContext
0x140001784  lea     rdx, RfcommIoTimerDpc; DeferredRoutine
0x14000178b  call    cs:__imp_KeInitializeDpc
0x140001792  nop     dword ptr [rax+rax+00h]
0x140001797  mov     byte ptr [rbx+108h], 0
0x14000179e  mov     rdx, rbp; TargetDevice
0x1400017a1  mov     rax, [rsp+78h+SourceDevice]
0x1400017a9  or      dword ptr [rax+30h], 2010h
0x1400017b0  mov     rcx, [rsp+78h+SourceDevice]; SourceDevice
0x1400017b8  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400017bf  nop     dword ptr [rax+rax+00h]
0x1400017c4  mov     [rbx+58h], rax
0x1400017c8  test    rax, rax
0x1400017cb  jnz     short loc_1400017DF
0x1400017cd  mov     rcx, rbx
0x1400017d0  mov     edi, 0C0000001h
0x1400017d5  call    RfcommDeleteDevice
0x1400017da  jmp     loc_14000157B
0x1400017df  mov     rax, [rsp+78h+SourceDevice]
0x1400017e7  btr     dword ptr [rax+30h], 7
0x1400017ec  jmp     loc_14000157B
0x1400017f1  mov     ecx, 3
0x1400017f6  int     29h; Win8: RtlFailFast(ecx)
```
