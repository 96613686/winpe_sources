# I8xAddDevice

- ea: `0x14001c590`
- end: `0x14001c802`
- name: `I8xAddDevice`
- size: `626`
- prototype: `__int64 __fastcall(PVOID IoObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x140007b10`
- `0x14000cbe0`
- `0x14000de80`
- `0x14001c590`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14001c65a`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14001c65a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001c6d9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001c6d9`
- `ntoskrnl!KeInitializeTimer` at `0x14001c6e9`
- `ntoskrnl!KeInitializeTimer` at `0x14001c6e9`
- `ntoskrnl!KeInitializeDpc` at `0x14001c707`
- `ntoskrnl!KeInitializeDpc` at `0x14001c725`
- `ntoskrnl!KeInitializeDpc` at `0x14001c743`
- `ntoskrnl!KeInitializeDpc` at `0x14001c761`
- `ntoskrnl!KeInitializeDpc` at `0x14001c707`
- `ntoskrnl!KeInitializeDpc` at `0x14001c725`
- `ntoskrnl!KeInitializeDpc` at `0x14001c743`
- `ntoskrnl!KeInitializeDpc` at `0x14001c761`
- `ntoskrnl!IoSetStartIoAttributes` at `0x14001c799`
- `ntoskrnl!IoSetStartIoAttributes` at `0x14001c799`
- `ntoskrnl!IoDeleteDevice` at `0x14001c69d`
- `ntoskrnl!IoDeleteDevice` at `0x14001c69d`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14001c784`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x14001c784`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14001c640`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x14001c640`
- `ntoskrnl!IoCreateDevice` at `0x14001c60d`
- `ntoskrnl!IoCreateDevice` at `0x14001c60d`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14001c688`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14001c688`

## pseudocode

```c
__int64 __fastcall I8xAddDevice(struct _DRIVER_OBJECT *IoObject, PDEVICE_OBJECT TargetDevice)
{
  NTSTATUS v4; // ebx
  char *DeviceExtension; // rdi
  PDEVICE_OBJECT v6; // rax
  _DWORD *ErrorLogEntry; // rax
  int v8; // edx
  PDEVICE_OBJECT SourceDevice; // [rsp+90h] [rbp+48h] BYREF

  SourceDevice = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)TargetDevice,
      15,
      10,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
  v4 = IoCreateDevice(IoObject, 0x458u, 0, 0x27u, 0, 0, &SourceDevice);
  if ( v4 >= 0 )
  {
    memset(SourceDevice->DeviceExtension, 0, 0x458u);
    DeviceExtension = (char *)SourceDevice->DeviceExtension;
    v6 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
    *((_QWORD *)DeviceExtension + 3) = v6;
    if ( v6 )
    {
      *(_QWORD *)DeviceExtension = SourceDevice;
      *((_QWORD *)DeviceExtension + 4) = TargetDevice;
      *((_DWORD *)DeviceExtension + 20) = 1;
      *((_QWORD *)DeviceExtension + 71) = 0;
      *((_DWORD *)DeviceExtension + 144) = 0;
      KeInitializeSpinLock((PKSPIN_LOCK)DeviceExtension + 2);
      KeInitializeTimer((PKTIMER)(DeviceExtension + 104));
      KeInitializeDpc((PRKDPC)(DeviceExtension + 232), I8042ErrorLogDpc, SourceDevice);
      KeInitializeDpc((PRKDPC)(DeviceExtension + 168), I8042RetriesExceededDpc, SourceDevice);
      KeInitializeDpc((PRKDPC)(DeviceExtension + 296), I8042TimeOutDpc, SourceDevice);
      KeInitializeDpc(&SourceDevice->Dpc, I8042CompletionDpc, SourceDevice);
      IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), 0x32343038u, 0, 0, 0x20u);
      IoSetStartIoAttributes(SourceDevice, 1u, 0);
      SourceDevice->Flags |= 4u;
      SourceDevice->Flags |= 0x2000u;
      SourceDevice->Flags &= ~0x80u;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          15,
          11,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
          v4);
    }
    else
    {
      ErrorLogEntry = IoAllocateErrorLogEntry(IoObject, 0x30u);
      v4 = -1073741667;
      if ( ErrorLogEntry )
      {
        ErrorLogEntry[3] = -1073414089;
        *ErrorLogEntry = 0;
        *((_QWORD *)ErrorLogEntry + 3) = 0;
        ErrorLogEntry[4] = 0;
        ErrorLogEntry[5] = -1073741667;
        IoWriteErrorLogEntry(ErrorLogEntry);
      }
      TraceLoggingAttachDeviceFailed();
      IoDeleteDevice(SourceDevice);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001c590  push    rbp
0x14001c592  push    rbx
0x14001c593  push    rsi
0x14001c594  push    rdi
0x14001c595  push    r13
0x14001c597  push    r14
0x14001c599  mov     rbp, rsp
0x14001c59c  sub     rsp, 48h
0x14001c5a0  mov     r14, rdx
0x14001c5a3  mov     [rbp+SourceDevice], 0
0x14001c5ab  mov     rsi, rcx
0x14001c5ae  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c5b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c5bc  lea     r13, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14001c5c3  jz      short loc_14001C5E4
0x14001c5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c5cc  mov     r9d, 0Ah
0x14001c5d2  mov     qword ptr [rsp+48h+DeviceCharacteristics], r13
0x14001c5d7  mov     rcx, [rcx+40h]
0x14001c5db  lea     r8d, [r9+5]
0x14001c5df  call    WPP_RECORDER_SF_
0x14001c5e4  lea     rax, [rbp+SourceDevice]
0x14001c5e8  mov     edi, 458h
0x14001c5ed  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x14001c5f2  mov     r9d, 27h ; '''; DeviceType
0x14001c5f8  mov     [rsp+48h+Exclusive], 0; Exclusive
0x14001c5fd  xor     r8d, r8d; DeviceName
0x14001c600  mov     edx, edi; DeviceExtensionSize
0x14001c602  mov     [rsp+48h+DeviceCharacteristics], 0; DeviceCharacteristics
0x14001c60a  mov     rcx, rsi; DriverObject
0x14001c60d  call    cs:__imp_IoCreateDevice
0x14001c614  nop     dword ptr [rax+rax+00h]
0x14001c619  mov     ebx, eax
0x14001c61b  test    eax, eax
0x14001c61d  js      loc_14001C7F2
0x14001c623  mov     rcx, [rbp+SourceDevice]
0x14001c627  mov     r8d, edi; Size
0x14001c62a  xor     edx, edx; Val
0x14001c62c  mov     rcx, [rcx+40h]; void *
0x14001c630  call    memset
0x14001c635  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x14001c639  mov     rdx, r14; TargetDevice
0x14001c63c  mov     rdi, [rcx+40h]
0x14001c640  call    cs:__imp_IoAttachDeviceToDeviceStack
0x14001c647  nop     dword ptr [rax+rax+00h]
0x14001c64c  mov     [rdi+18h], rax
0x14001c650  test    rax, rax
0x14001c653  jnz     short loc_14001C6AE
0x14001c655  mov     dl, 30h ; '0'; EntrySize
0x14001c657  mov     rcx, rsi; IoObject
0x14001c65a  call    cs:__imp_IoAllocateErrorLogEntry
0x14001c661  nop     dword ptr [rax+rax+00h]
0x14001c666  mov     ebx, 0C000009Dh
0x14001c66b  test    rax, rax
0x14001c66e  jz      short loc_14001C694
0x14001c670  xor     ecx, ecx
0x14001c672  mov     dword ptr [rax+0Ch], 0C0050037h
0x14001c679  mov     [rax], ecx
0x14001c67b  mov     [rax+18h], rcx
0x14001c67f  mov     [rax+10h], ecx
0x14001c682  mov     rcx, rax; ElEntry
0x14001c685  mov     [rax+14h], ebx
0x14001c688  call    cs:__imp_IoWriteErrorLogEntry
0x14001c68f  nop     dword ptr [rax+rax+00h]
0x14001c694  call    TraceLoggingAttachDeviceFailed
0x14001c699  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14001c69d  call    cs:__imp_IoDeleteDevice
0x14001c6a4  nop     dword ptr [rax+rax+00h]
0x14001c6a9  jmp     loc_14001C7F2
0x14001c6ae  mov     rax, [rbp+SourceDevice]
0x14001c6b2  lea     rcx, [rdi+10h]; SpinLock
0x14001c6b6  mov     [rdi], rax
0x14001c6b9  mov     [rdi+20h], r14
0x14001c6bd  mov     dword ptr [rdi+50h], 1
0x14001c6c4  mov     qword ptr [rdi+238h], 0
0x14001c6cf  mov     dword ptr [rdi+240h], 0
0x14001c6d9  call    cs:__imp_KeInitializeSpinLock
0x14001c6e0  nop     dword ptr [rax+rax+00h]
0x14001c6e5  lea     rcx, [rdi+68h]; Timer
0x14001c6e9  call    cs:__imp_KeInitializeTimer
0x14001c6f0  nop     dword ptr [rax+rax+00h]
0x14001c6f5  mov     r8, [rbp+SourceDevice]; DeferredContext
0x14001c6f9  lea     rcx, [rdi+0E8h]; Dpc
0x14001c700  lea     rdx, I8042ErrorLogDpc; DeferredRoutine
0x14001c707  call    cs:__imp_KeInitializeDpc
0x14001c70e  nop     dword ptr [rax+rax+00h]
0x14001c713  mov     r8, [rbp+SourceDevice]; DeferredContext
0x14001c717  lea     rcx, [rdi+0A8h]; Dpc
0x14001c71e  lea     rdx, I8042RetriesExceededDpc; DeferredRoutine
0x14001c725  call    cs:__imp_KeInitializeDpc
0x14001c72c  nop     dword ptr [rax+rax+00h]
0x14001c731  mov     r8, [rbp+SourceDevice]; DeferredContext
0x14001c735  lea     rcx, [rdi+128h]; Dpc
0x14001c73c  lea     rdx, I8042TimeOutDpc; DeferredRoutine
0x14001c743  call    cs:__imp_KeInitializeDpc
0x14001c74a  nop     dword ptr [rax+rax+00h]
0x14001c74f  mov     r8, [rbp+SourceDevice]; DeferredContext
0x14001c753  lea     rdx, I8042CompletionDpc; DeferredRoutine
0x14001c75a  lea     rcx, [r8+0C8h]; Dpc
0x14001c761  call    cs:__imp_KeInitializeDpc
0x14001c768  nop     dword ptr [rax+rax+00h]
0x14001c76d  lea     rcx, [rdi+28h]; Lock
0x14001c771  mov     [rsp+48h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x14001c779  xor     r9d, r9d; HighWatermark
0x14001c77c  xor     r8d, r8d; MaxLockedMinutes
0x14001c77f  mov     edx, 32343038h; AllocateTag
0x14001c784  call    cs:__imp_IoInitializeRemoveLockEx
0x14001c78b  nop     dword ptr [rax+rax+00h]
0x14001c790  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x14001c794  xor     r8d, r8d; NonCancelable
0x14001c797  mov     dl, 1; DeferredStartIo
0x14001c799  call    cs:__imp_IoSetStartIoAttributes
0x14001c7a0  nop     dword ptr [rax+rax+00h]
0x14001c7a5  mov     rax, [rbp+SourceDevice]
0x14001c7a9  or      dword ptr [rax+30h], 4
0x14001c7ad  mov     rax, [rbp+SourceDevice]
0x14001c7b1  bts     dword ptr [rax+30h], 0Dh
0x14001c7b6  mov     rax, [rbp+SourceDevice]
0x14001c7ba  btr     dword ptr [rax+30h], 7
0x14001c7bf  lea     rax, WPP_RECORDER_INITIALIZED
0x14001c7c6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001c7cd  jz      short loc_14001C7F2
0x14001c7cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7d6  mov     r9d, 0Bh
0x14001c7dc  mov     dword ptr [rsp+48h+Exclusive], ebx
0x14001c7e0  mov     qword ptr [rsp+48h+DeviceCharacteristics], r13
0x14001c7e5  mov     rcx, [rcx+40h]
0x14001c7e9  lea     r8d, [r9+4]
0x14001c7ed  call    WPP_RECORDER_SF_D
0x14001c7f2  mov     eax, ebx
0x14001c7f4  add     rsp, 48h
0x14001c7f8  pop     r14
0x14001c7fa  pop     r13
0x14001c7fc  pop     rdi
0x14001c7fd  pop     rsi
0x14001c7fe  pop     rbx
0x14001c7ff  pop     rbp
0x14001c800  retn
```
