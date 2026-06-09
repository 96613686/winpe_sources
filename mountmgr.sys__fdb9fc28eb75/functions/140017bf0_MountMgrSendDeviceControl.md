# MountMgrSendDeviceControl

- ea: `0x140017bf0`
- end: `0x140017cf6`
- name: `MountMgrSendDeviceControl`
- size: `262`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, struct _FILE_OBJECT *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140017540`
- `0x140017a20`
- `0x140017d00`
- `0x140018060`
- `0x140018450`
- `0x140018890`
- `0x140018a20`
- `0x14001a8a0`

## callees

- `0x140017bf0`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140017c6d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140017c6d`
- `ntoskrnl!IofCallDriver` at `0x140017c9c`
- `ntoskrnl!IofCallDriver` at `0x140017c9c`
- `ntoskrnl!KeInitializeEvent` at `0x140017c25`
- `ntoskrnl!KeInitializeEvent` at `0x140017c25`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017cd2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017cd2`

## pseudocode

```c
NTSTATUS __fastcall MountMgrSendDeviceControl(
        PDEVICE_OBJECT DeviceObject,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        struct _FILE_OBJECT *a7)
{
  PIRP v11; // rax
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
          0,
          &Event,
          &IoStatusBlock);
  if ( !v11 )
    return -1073741670;
  if ( a7 )
    v11->Tail.Overlay.CurrentStackLocation[-1].FileObject = a7;
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
0x140017bf0  push    rbx
0x140017bf2  push    rbp
0x140017bf3  push    rsi
0x140017bf4  push    rdi
0x140017bf5  sub     rsp, 88h
0x140017bfc  xorps   xmm0, xmm0
0x140017bff  mov     rdi, r8
0x140017c02  mov     esi, edx
0x140017c04  mov     rbp, rcx
0x140017c07  xor     eax, eax
0x140017c09  lea     rcx, [rsp+0A8h+Event]; Event
0x140017c0e  xor     r8d, r8d; State
0x140017c11  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x140017c16  xor     edx, edx; Type
0x140017c18  mov     ebx, r9d
0x140017c1b  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x140017c20  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140017c25  call    cs:__imp_KeInitializeEvent
0x140017c2c  nop     dword ptr [rax+rax+00h]
0x140017c31  lea     rax, [rsp+0A8h+var_58]
0x140017c36  mov     r9d, ebx; InputBufferLength
0x140017c39  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x140017c3e  mov     r8, rdi; InputBuffer
0x140017c41  lea     rax, [rsp+0A8h+Event]
0x140017c46  mov     rdx, rbp; DeviceObject
0x140017c49  mov     [rsp+0A8h+var_70], rax; Event
0x140017c4e  mov     ecx, esi; IoControlCode
0x140017c50  mov     eax, [rsp+0A8h+arg_28]
0x140017c57  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140017c5c  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x140017c60  mov     rax, [rsp+0A8h+arg_20]
0x140017c68  mov     [rsp+0A8h+OutputBuffer], rax; OutputBuffer
0x140017c6d  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140017c74  nop     dword ptr [rax+rax+00h]
0x140017c79  test    rax, rax
0x140017c7c  jz      short loc_140017CEF
0x140017c7e  mov     rcx, [rsp+0A8h+arg_30]
0x140017c86  test    rcx, rcx
0x140017c89  jz      short loc_140017C96
0x140017c8b  mov     rdx, [rax+0B8h]
0x140017c92  mov     [rdx-18h], rcx
0x140017c96  mov     rdx, rax; Irp
0x140017c99  mov     rcx, rbp; DeviceObject
0x140017c9c  call    cs:__imp_IofCallDriver
0x140017ca3  nop     dword ptr [rax+rax+00h]
0x140017ca8  cmp     eax, 103h
0x140017cad  jz      short loc_140017CBC
0x140017caf  add     rsp, 88h
0x140017cb6  pop     rdi
0x140017cb7  pop     rsi
0x140017cb8  pop     rbp
0x140017cb9  pop     rbx
0x140017cba  retn
0x140017cbc  xor     r9d, r9d; Alertable
0x140017cbf  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x140017cc8  xor     r8d, r8d; WaitMode
0x140017ccb  lea     rcx, [rsp+0A8h+Event]; Object
0x140017cd0  xor     edx, edx; WaitReason
0x140017cd2  call    cs:__imp_KeWaitForSingleObject
0x140017cd9  nop     dword ptr [rax+rax+00h]
0x140017cde  mov     eax, dword ptr [rsp+0A8h+var_58]
0x140017ce2  add     rsp, 88h
0x140017ce9  pop     rdi
0x140017cea  pop     rsi
0x140017ceb  pop     rbp
0x140017cec  pop     rbx
0x140017ced  retn
0x140017cef  mov     eax, 0C000009Ah
0x140017cf4  jmp     short loc_140017CAF
```
