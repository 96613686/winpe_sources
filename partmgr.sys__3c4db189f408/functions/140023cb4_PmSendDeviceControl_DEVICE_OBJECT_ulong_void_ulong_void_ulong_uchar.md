# PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)

- ea: `0x140023cb4`
- end: `0x140023da2`
- name: `?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z`
- size: `238`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, BOOLEAN InternalDeviceIoControl)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x140005d78`
- `0x1400079fc`
- `0x14000e398`
- `0x14001d894`
- `0x14001e468`
- `0x14001e6f0`
- `0x14001fa44`
- `0x14001ff00`
- `0x14001ff34`
- `0x14002096c`
- `0x140022040`
- `0x14002366c`
- `0x14002392c`
- `0x140023aa0`
- `0x140023c80`
- `0x1400261fc`
- `0x140026640`

## callees

- `0x140023cb4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140023d85`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023d85`
- `ntoskrnl!IofCallDriver` at `0x140023d5c`
- `ntoskrnl!IofCallDriver` at `0x140023d5c`
- `ntoskrnl!KeInitializeEvent` at `0x140023cf0`
- `ntoskrnl!KeInitializeEvent` at `0x140023cf0`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140023d3e`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140023d3e`

## pseudocode

```c
NTSTATUS __fastcall PmSendDeviceControl(
        PDEVICE_OBJECT DeviceObject,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        BOOLEAN InternalDeviceIoControl)
{
  IRP *v11; // rax
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v11 = IoBuildDeviceIoControlRequest(
          IoControlCode,
          DeviceObject,
          InputBuffer,
          InputBufferLength,
          OutputBuffer,
          OutputBufferLength,
          InternalDeviceIoControl,
          &Event,
          &IoStatusBlock);
  if ( !v11 )
    return -1073741670;
  result = IofCallDriver(DeviceObject, v11);
  if ( result == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    return IoStatusBlock.Status;
  }
  return result;
}

```

## disassembly

```asm
0x140023cb4  push    rbx
0x140023cb6  push    rbp
0x140023cb7  push    rsi
0x140023cb8  push    rdi
0x140023cb9  sub     rsp, 88h
0x140023cc0  xorps   xmm0, xmm0
0x140023cc3  mov     dword ptr [rsp+0A8h+Event.Header], 0
0x140023ccb  mov     rdi, r8
0x140023cce  mov     esi, edx
0x140023cd0  mov     rbp, rcx
0x140023cd3  xor     eax, eax
0x140023cd5  xor     r8d, r8d; State
0x140023cd8  mov     dword ptr [rsp+0A8h+Event.Header.WaitListHead.Blink+4], eax
0x140023cdc  xor     edx, edx; Type
0x140023cde  lea     rcx, [rsp+0A8h+Event]; Event
0x140023ce3  movups  xmmword ptr [rsp+0A8h+Event.Header.SignalState], xmm0
0x140023ce8  mov     ebx, r9d
0x140023ceb  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140023cf0  call    cs:__imp_KeInitializeEvent
0x140023cf7  nop     dword ptr [rax+rax+00h]
0x140023cfc  lea     rax, [rsp+0A8h+var_58]
0x140023d01  mov     r9d, ebx; InputBufferLength
0x140023d04  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x140023d09  mov     r8, rdi; InputBuffer
0x140023d0c  lea     rax, [rsp+0A8h+Event]
0x140023d11  mov     rdx, rbp; DeviceObject
0x140023d14  mov     [rsp+0A8h+var_70], rax; Event
0x140023d19  mov     ecx, esi; IoControlCode
0x140023d1b  mov     al, [rsp+0A8h+arg_30]
0x140023d22  mov     [rsp+0A8h+InternalDeviceIoControl], al; InternalDeviceIoControl
0x140023d26  mov     eax, [rsp+0A8h+arg_28]
0x140023d2d  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x140023d31  mov     rax, [rsp+0A8h+arg_20]
0x140023d39  mov     [rsp+0A8h+OutputBuffer], rax; OutputBuffer
0x140023d3e  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140023d45  nop     dword ptr [rax+rax+00h]
0x140023d4a  test    rax, rax
0x140023d4d  jnz     short loc_140023D56
0x140023d4f  mov     eax, 0C000009Ah
0x140023d54  jmp     short loc_140023D95
0x140023d56  mov     rdx, rax; Irp
0x140023d59  mov     rcx, rbp; DeviceObject
0x140023d5c  call    cs:__imp_IofCallDriver
0x140023d63  nop     dword ptr [rax+rax+00h]
0x140023d68  cmp     eax, 103h
0x140023d6d  jnz     short loc_140023D95
0x140023d6f  xor     r9d, r9d; Alertable
0x140023d72  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x140023d7b  xor     r8d, r8d; WaitMode
0x140023d7e  lea     rcx, [rsp+0A8h+Event]; Object
0x140023d83  xor     edx, edx; WaitReason
0x140023d85  call    cs:__imp_KeWaitForSingleObject
0x140023d8c  nop     dword ptr [rax+rax+00h]
0x140023d91  mov     eax, dword ptr [rsp+0A8h+var_58]
0x140023d95  add     rsp, 88h
0x140023d9c  pop     rdi
0x140023d9d  pop     rsi
0x140023d9e  pop     rbp
0x140023d9f  pop     rbx
0x140023da0  retn
```
