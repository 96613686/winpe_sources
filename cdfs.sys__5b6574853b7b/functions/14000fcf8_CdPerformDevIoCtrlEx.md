# CdPerformDevIoCtrlEx

- ea: `0x14000fcf8`
- end: `0x14000fe0b`
- name: `CdPerformDevIoCtrlEx`
- size: `275`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fcb0`
- `0x1400142d8`
- `0x140019280`
- `0x14001a400`

## callees

- `0x14000fcf8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000fd4c`
- `ntoskrnl!KeInitializeEvent` at `0x14000fd4c`
- `ntoskrnl!IofCallDriver` at `0x14000fdc7`
- `ntoskrnl!IofCallDriver` at `0x14000fdc7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fdf0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fdf0`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000fd94`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000fd94`

## pseudocode

```c
NTSTATUS __fastcall CdPerformDevIoCtrlEx(
        __int64 a1,
        ULONG a2,
        struct _DEVICE_OBJECT *a3,
        void *a4,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        __int64 a8,
        char a9,
        PIO_STATUS_BLOCK a10)
{
  struct _IO_STATUS_BLOCK *IoStatusBlock; // rsi
  PIRP v14; // rax
  NTSTATUS result; // eax
  __int128 v16; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  IoStatusBlock = (struct _IO_STATUS_BLOCK *)&v16;
  Event.Header.WaitListHead.Blink = 0;
  v16 = 0;
  if ( a10 )
    IoStatusBlock = a10;
  *(_OWORD *)&Event.Header.Lock = 0;
  IoStatusBlock->Status = 0;
  IoStatusBlock->Information = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v14 = IoBuildDeviceIoControlRequest(
          a2,
          a3,
          a4,
          InputBufferLength,
          OutputBuffer,
          OutputBufferLength,
          0,
          &Event,
          IoStatusBlock);
  if ( !v14 )
    return -1073741670;
  if ( a9 )
    v14->Tail.Overlay.CurrentStackLocation[-1].Flags |= 2u;
  result = IofCallDriver(a3, v14);
  if ( result == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    return IoStatusBlock->Status;
  }
  return result;
}

```

## disassembly

```asm
0x14000fcf8  push    rbx
0x14000fcfa  push    rbp
0x14000fcfb  push    rsi
0x14000fcfc  push    rdi
0x14000fcfd  sub     rsp, 88h
0x14000fd04  xor     eax, eax
0x14000fd06  lea     rsi, [rsp+0A8h+var_58]
0x14000fd0b  xorps   xmm0, xmm0
0x14000fd0e  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14000fd13  mov     rax, [rsp+0A8h+arg_48]
0x14000fd1b  lea     rcx, [rsp+0A8h+Event]; Event
0x14000fd20  movups  [rsp+0A8h+var_58], xmm0
0x14000fd25  test    rax, rax
0x14000fd28  mov     rbp, r8
0x14000fd2b  mov     edi, edx
0x14000fd2d  mov     rbx, r9
0x14000fd30  cmovnz  rsi, rax
0x14000fd34  xor     r8d, r8d; State
0x14000fd37  xor     edx, edx; Type
0x14000fd39  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14000fd3e  mov     dword ptr [rsi], 0
0x14000fd44  mov     qword ptr [rsi+8], 0
0x14000fd4c  call    cs:__imp_KeInitializeEvent
0x14000fd53  nop     dword ptr [rax+rax+00h]
0x14000fd58  mov     r9d, [rsp+0A8h+InputBufferLength]; InputBufferLength
0x14000fd60  lea     rax, [rsp+0A8h+Event]
0x14000fd65  mov     [rsp+0A8h+IoStatusBlock], rsi; IoStatusBlock
0x14000fd6a  mov     r8, rbx; InputBuffer
0x14000fd6d  mov     [rsp+0A8h+var_70], rax; Event
0x14000fd72  mov     rdx, rbp; DeviceObject
0x14000fd75  mov     eax, [rsp+0A8h+arg_30]
0x14000fd7c  mov     ecx, edi; IoControlCode
0x14000fd7e  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14000fd83  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x14000fd87  mov     rax, [rsp+0A8h+arg_28]
0x14000fd8f  mov     [rsp+0A8h+OutputBuffer], rax; OutputBuffer
0x14000fd94  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000fd9b  nop     dword ptr [rax+rax+00h]
0x14000fda0  mov     rdx, rax; Irp
0x14000fda3  test    rax, rax
0x14000fda6  jnz     short loc_14000FDAF
0x14000fda8  mov     eax, 0C000009Ah
0x14000fdad  jmp     short loc_14000FDFE
0x14000fdaf  cmp     [rsp+0A8h+arg_40], 0
0x14000fdb7  jz      short loc_14000FDC4
0x14000fdb9  mov     rax, [rax+0B8h]
0x14000fdc0  or      byte ptr [rax-46h], 2
0x14000fdc4  mov     rcx, rbp; DeviceObject
0x14000fdc7  call    cs:__imp_IofCallDriver
0x14000fdce  nop     dword ptr [rax+rax+00h]
0x14000fdd3  cmp     eax, 103h
0x14000fdd8  jnz     short loc_14000FDFE
0x14000fdda  xor     r9d, r9d; Alertable
0x14000fddd  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x14000fde6  xor     r8d, r8d; WaitMode
0x14000fde9  lea     rcx, [rsp+0A8h+Event]; Object
0x14000fdee  xor     edx, edx; WaitReason
0x14000fdf0  call    cs:__imp_KeWaitForSingleObject
0x14000fdf7  nop     dword ptr [rax+rax+00h]
0x14000fdfc  mov     eax, [rsi]
0x14000fdfe  add     rsp, 88h
0x14000fe05  pop     rdi
0x14000fe06  pop     rsi
0x14000fe07  pop     rbp
0x14000fe08  pop     rbx
0x14000fe09  retn
```
