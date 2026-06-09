# TdiAddDevice

- ea: `0x1400060c4`
- end: `0x140006464`
- name: `TdiAddDevice`
- size: `928`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140001460`

## callees

- `0x140003bf4`
- `0x140005050`
- `0x1400051b4`
- `0x140005964`
- `0x1400060c4`
- `0x14001bfa8`
- `0x14001e74c`
- `0x14001e8f4`
- `0x14001ea34`
- `0x14001fd40`
- `0x140033b90`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140006236`
- `ntoskrnl!KeInitializeSpinLock` at `0x140006236`
- `ntoskrnl!IoCreateDevice` at `0x140006170`
- `ntoskrnl!IoCreateDevice` at `0x140006170`
- `ntoskrnl!IoDeleteDevice` at `0x1400061a2`
- `ntoskrnl!IoDeleteDevice` at `0x1400061a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400061b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006340`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400061b9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006340`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000628d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006365`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006414`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000628d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006365`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006414`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000613b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000613b`
- `TDI!TdiRegisterDeviceObject` at `0x14000618b`
- `TDI!TdiRegisterDeviceObject` at `0x14000618b`

## string_xrefs

- `0x140006130`: `\Device\BTHMS_RFCOMM`
- `0x14000624c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140006321`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiAddDevice(_BYTE *SpinLock, int a2)
{
  NTSTATUS v3; // r14d
  char *v4; // rdi
  void *v5; // rbx
  const char *v6; // rax
  int v7; // edx
  KSPIN_LOCK v8; // rcx
  KSPIN_LOCK v9; // rbx
  __int64 v10; // rbx
  void *DeviceExtension; // rdi
  const char *v12; // rax
  int v13; // edx
  void *v14; // rbx
  const char *v15; // rax
  int v16; // edx
  int v17; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp+30h] BYREF
  HANDLE RegistrationHandle; // [rsp+88h] [rbp+38h] BYREF

  DeviceObject = 0;
  DestinationString = 0;
  RegistrationHandle = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      20,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"\\Device\\BTHMS_RFCOMM");
  v3 = IoCreateDevice(*((PDRIVER_OBJECT *)SpinLock + 5), 0x288u, &DestinationString, 0x12u, 0x100u, 0, &DeviceObject);
  if ( v3 >= 0 )
  {
    v3 = TdiRegisterDeviceObject(&DestinationString, &RegistrationHandle);
    if ( v3 < 0 )
    {
      IoDeleteDevice(DeviceObject);
      DeviceObject = 0;
    }
  }
  SpinLock[8] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SpinLock);
  if ( v3 < 0 )
  {
    v8 = *((_QWORD *)SpinLock + 2);
    if ( v8 )
    {
      RefObj_AddRefEx(v8 + 24, 542065734, 418, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      v9 = *((_QWORD *)SpinLock + 2);
      *(_BYTE *)(v9 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 48));
      *(_BYTE *)(*((_QWORD *)SpinLock + 2) + 128LL) = 1;
      KeReleaseSpinLock((PKSPIN_LOCK)(*((_QWORD *)SpinLock + 2) + 48LL), *(_BYTE *)(*((_QWORD *)SpinLock + 2) + 56LL));
      v3 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v10 = *(_QWORD *)(*((_QWORD *)SpinLock + 2) + 64LL);
        DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
        v12 = NtStatusTxt(0);
        WPP_RECORDER_SF_qs(
          (_DWORD)DeviceExtension,
          v13,
          15,
          22,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
          v10,
          (__int64)v12);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = WPP_GLOBAL_Control->DeviceExtension;
      v15 = NtStatusTxt(v3);
      WPP_RECORDER_SF_s(
        (_DWORD)v14,
        v16,
        15,
        23,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        (__int64)v15);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, SpinLock[8]);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v17,
        15,
        24,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  }
  else
  {
    v4 = (char *)DeviceObject->DeviceExtension;
    *((_QWORD *)SpinLock + 2) = v4;
    *((_DWORD *)v4 + 4) = 541672532;
    *((_QWORD *)v4 + 8) = DeviceObject;
    *((_QWORD *)v4 + 9) = RegistrationHandle;
    *((_QWORD *)v4 + 13) = v4 + 96;
    *((_QWORD *)v4 + 12) = v4 + 96;
    *((_QWORD *)v4 + 15) = v4 + 112;
    *((_QWORD *)v4 + 14) = v4 + 112;
    *((_QWORD *)v4 + 10) = SpinLock;
    *((_QWORD *)v4 + 1) = v4;
    *(_QWORD *)v4 = v4;
    *((_WORD *)v4 + 64) = 1;
    memset(v4 + 136, 0, 0x200u);
    KeInitializeSpinLock((PKSPIN_LOCK)v4 + 6);
    RefObj_InitEx(
      (_DWORD)v4 + 24,
      (unsigned int)TdiDeleteDevice,
      1414090313,
      385,
      (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    *((_QWORD *)SpinLock + 2) = v4;
    RefObj_AddRefEx(v4 + 24, 542065734, 390, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    KeReleaseSpinLock((PKSPIN_LOCK)SpinLock, SpinLock[8]);
    RefObj_ReleaseEx(v4 + 24, 1414090313, 396, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = WPP_GLOBAL_Control->DeviceExtension;
      v6 = NtStatusTxt(v3);
      WPP_RECORDER_SF_qs(
        (_DWORD)v5,
        v7,
        15,
        21,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        (char)DeviceObject,
        (__int64)v6);
    }
    RFCOMMAddCapabilitySids(DeviceObject);
    TdiNotifyAddDevice();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400060c4  mov     [rsp-28h+arg_10], rbx
0x1400060c9  mov     [rsp-28h+arg_18], rsi
0x1400060ce  push    rbp
0x1400060cf  push    rdi
0x1400060d0  push    r13
0x1400060d2  push    r14
0x1400060d4  push    r15
0x1400060d6  mov     rbp, rsp
0x1400060d9  sub     rsp, 50h
0x1400060dd  xorps   xmm0, xmm0
0x1400060e0  mov     [rbp+arg_0], 0
0x1400060e8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400060ec  mov     rsi, rcx
0x1400060ef  mov     [rbp+RegistrationHandle], 0
0x1400060f7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400060fe  mov     r13d, 0Fh
0x140006104  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000610b  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140006112  jz      short loc_140006130
0x140006114  mov     rcx, cs:WPP_GLOBAL_Control
0x14000611b  lea     r9d, [r13+5]
0x14000611f  mov     r8d, r13d
0x140006122  mov     qword ptr [rsp+50h+DeviceCharacteristics], rdi
0x140006127  mov     rcx, [rcx+40h]
0x14000612b  call    WPP_RECORDER_SF_
0x140006130  lea     rdx, SourceString; "\\Device\\BTHMS_RFCOMM"
0x140006137  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000613b  call    cs:__imp_RtlInitUnicodeString
0x140006142  nop     dword ptr [rax+rax+00h]
0x140006147  mov     rcx, [rsi+28h]; DriverObject
0x14000614b  lea     rax, [rbp+arg_0]
0x14000614f  mov     [rsp+50h+DeviceObject], rax; DeviceObject
0x140006154  lea     r8, [rbp+DestinationString]; DeviceName
0x140006158  mov     [rsp+50h+Exclusive], 0; Exclusive
0x14000615d  mov     r9d, 12h; DeviceType
0x140006163  mov     edx, 288h; DeviceExtensionSize
0x140006168  mov     [rsp+50h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x140006170  call    cs:__imp_IoCreateDevice
0x140006177  nop     dword ptr [rax+rax+00h]
0x14000617c  mov     r14d, eax
0x14000617f  test    eax, eax
0x140006181  js      short loc_1400061B6
0x140006183  lea     rdx, [rbp+RegistrationHandle]; RegistrationHandle
0x140006187  lea     rcx, [rbp+DestinationString]; DeviceName
0x14000618b  call    cs:__imp_TdiRegisterDeviceObject
0x140006192  nop     dword ptr [rax+rax+00h]
0x140006197  mov     r14d, eax
0x14000619a  test    eax, eax
0x14000619c  jns     short loc_1400061B6
0x14000619e  mov     rcx, [rbp+arg_0]; DeviceObject
0x1400061a2  call    cs:__imp_IoDeleteDevice
0x1400061a9  nop     dword ptr [rax+rax+00h]
0x1400061ae  mov     [rbp+arg_0], 0
0x1400061b6  mov     rcx, rsi; SpinLock
0x1400061b9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400061c0  nop     dword ptr [rax+rax+00h]
0x1400061c5  mov     [rsi+8], al
0x1400061c8  test    r14d, r14d
0x1400061cb  js      loc_140006310
0x1400061d1  mov     rax, [rbp+arg_0]
0x1400061d5  mov     rdi, [rax+40h]
0x1400061d9  mov     [rsi+10h], rdi
0x1400061dd  mov     dword ptr [rdi+10h], 20494454h
0x1400061e4  mov     rax, [rbp+arg_0]
0x1400061e8  mov     [rdi+40h], rax
0x1400061ec  mov     rax, [rbp+RegistrationHandle]
0x1400061f0  mov     [rdi+48h], rax
0x1400061f4  lea     rax, [rdi+60h]
0x1400061f8  mov     [rax+8], rax
0x1400061fc  mov     [rax], rax
0x1400061ff  lea     rax, [rdi+70h]
0x140006203  mov     [rax+8], rax
0x140006207  mov     [rax], rax
0x14000620a  mov     [rdi+50h], rsi
0x14000620e  mov     [rdi+8], rdi
0x140006212  mov     [rdi], rdi
0x140006215  lea     rcx, [rdi+88h]; void *
0x14000621c  mov     word ptr [rdi+80h], 1
0x140006225  xor     edx, edx; Val
0x140006227  mov     r8d, 200h; Size
0x14000622d  call    memset
0x140006232  lea     rcx, [rdi+30h]; SpinLock
0x140006236  call    cs:__imp_KeInitializeSpinLock
0x14000623d  nop     dword ptr [rax+rax+00h]
0x140006242  lea     rbx, [rdi+18h]
0x140006246  mov     r9d, 181h
0x14000624c  lea     r15, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006253  mov     rcx, rbx
0x140006256  mov     r8d, 54494E49h
0x14000625c  mov     qword ptr [rsp+50h+DeviceCharacteristics], r15
0x140006261  lea     rdx, TdiDeleteDevice
0x140006268  call    RefObj_InitEx
0x14000626d  mov     r9, r15
0x140006270  mov     [rsi+10h], rdi
0x140006274  mov     edx, 204F4446h
0x140006279  mov     r8d, 186h
0x14000627f  mov     rcx, rbx
0x140006282  call    RefObj_AddRefEx
0x140006287  mov     dl, [rsi+8]; NewIrql
0x14000628a  mov     rcx, rsi; SpinLock
0x14000628d  call    cs:__imp_KeReleaseSpinLock
0x140006294  nop     dword ptr [rax+rax+00h]
0x140006299  mov     r9, r15
0x14000629c  mov     edx, 54494E49h
0x1400062a1  mov     r8d, 18Ch
0x1400062a7  mov     rcx, rbx
0x1400062aa  call    RefObj_ReleaseEx
0x1400062af  lea     r15, WPP_RECORDER_INITIALIZED
0x1400062b6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400062bd  jz      short loc_1400062FD
0x1400062bf  mov     rax, cs:WPP_GLOBAL_Control
0x1400062c6  mov     ecx, r14d
0x1400062c9  mov     rbx, [rax+40h]
0x1400062cd  call    NtStatusTxt
0x1400062d2  mov     [rsp+50h+DeviceObject], rax
0x1400062d7  mov     r9d, 15h
0x1400062dd  mov     rax, [rbp+arg_0]
0x1400062e1  mov     r8d, r13d
0x1400062e4  mov     qword ptr [rsp+50h+Exclusive], rax
0x1400062e9  mov     rcx, rbx
0x1400062ec  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400062f3  mov     qword ptr [rsp+50h+DeviceCharacteristics], rax
0x1400062f8  call    WPP_RECORDER_SF_qs
0x1400062fd  mov     rcx, [rbp+arg_0]
0x140006301  call    RFCOMMAddCapabilitySids
0x140006306  call    TdiNotifyAddDevice
0x14000630b  jmp     loc_140006447
0x140006310  mov     rcx, [rsi+10h]
0x140006314  test    rcx, rcx
0x140006317  jz      loc_1400063D0
0x14000631d  add     rcx, 18h
0x140006321  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006328  mov     edx, 204F4446h
0x14000632d  mov     r8d, 1A2h
0x140006333  call    RefObj_AddRefEx
0x140006338  mov     rbx, [rsi+10h]
0x14000633c  lea     rcx, [rbx+30h]; SpinLock
0x140006340  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006347  nop     dword ptr [rax+rax+00h]
0x14000634c  mov     [rbx+38h], al
0x14000634f  mov     rax, [rsi+10h]
0x140006353  mov     byte ptr [rax+80h], 1
0x14000635a  mov     rdx, [rsi+10h]
0x14000635e  lea     rcx, [rdx+30h]; SpinLock
0x140006362  mov     dl, [rdx+38h]; NewIrql
0x140006365  call    cs:__imp_KeReleaseSpinLock
0x14000636c  nop     dword ptr [rax+rax+00h]
0x140006371  xor     r14d, r14d
0x140006374  lea     r15, WPP_RECORDER_INITIALIZED
0x14000637b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006382  jz      loc_14000640E
0x140006388  mov     rax, [rsi+10h]
0x14000638c  xor     ecx, ecx
0x14000638e  mov     rbx, [rax+40h]
0x140006392  mov     rax, cs:WPP_GLOBAL_Control
0x140006399  mov     rdi, [rax+40h]
0x14000639d  call    NtStatusTxt
0x1400063a2  mov     [rsp+50h+DeviceObject], rax
0x1400063a7  lea     r9d, [r14+16h]
0x1400063ab  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400063b2  mov     qword ptr [rsp+50h+Exclusive], rbx
0x1400063b7  mov     r8d, r13d
0x1400063ba  mov     qword ptr [rsp+50h+DeviceCharacteristics], rax
0x1400063bf  mov     rcx, rdi
0x1400063c2  call    WPP_RECORDER_SF_qs
0x1400063c7  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400063ce  jmp     short loc_14000640E
0x1400063d0  lea     r15, WPP_RECORDER_INITIALIZED
0x1400063d7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400063de  jz      short loc_14000640E
0x1400063e0  mov     rax, cs:WPP_GLOBAL_Control
0x1400063e7  mov     ecx, r14d
0x1400063ea  mov     rbx, [rax+40h]
0x1400063ee  call    NtStatusTxt
0x1400063f3  mov     qword ptr [rsp+50h+Exclusive], rax
0x1400063f8  mov     r9d, 17h
0x1400063fe  mov     r8d, r13d
0x140006401  mov     qword ptr [rsp+50h+DeviceCharacteristics], rdi
0x140006406  mov     rcx, rbx
0x140006409  call    WPP_RECORDER_SF_s
0x14000640e  mov     dl, [rsi+8]; NewIrql
0x140006411  mov     rcx, rsi; SpinLock
0x140006414  call    cs:__imp_KeReleaseSpinLock
0x14000641b  nop     dword ptr [rax+rax+00h]
0x140006420  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006427  jz      short loc_140006447
0x140006429  mov     rcx, cs:WPP_GLOBAL_Control
0x140006430  mov     r9d, 18h
0x140006436  mov     r8d, r13d
0x140006439  mov     qword ptr [rsp+50h+DeviceCharacteristics], rdi
0x14000643e  mov     rcx, [rcx+40h]
0x140006442  call    WPP_RECORDER_SF_
0x140006447  lea     r11, [rsp+50h+var_s0]
0x14000644c  mov     eax, r14d
0x14000644f  mov     rbx, [r11+40h]
0x140006453  mov     rsi, [r11+48h]
0x140006457  mov     rsp, r11
0x14000645a  pop     r15
0x14000645c  pop     r14
0x14000645e  pop     r13
0x140006460  pop     rdi
0x140006461  pop     rbp
0x140006462  retn
```
