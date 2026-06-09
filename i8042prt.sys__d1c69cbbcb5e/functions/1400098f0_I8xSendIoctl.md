# I8xSendIoctl

- ea: `0x1400098f0`
- end: `0x140009a10`
- name: `I8xSendIoctl`
- size: `288`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007090`
- `0x140019490`
- `0x14001b924`

## callees

- `0x140006950`
- `0x1400098f0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140009987`
- `ntoskrnl!IofCallDriver` at `0x140009987`
- `ntoskrnl!KeInitializeEvent` at `0x140009925`
- `ntoskrnl!KeInitializeEvent` at `0x140009925`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400099f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400099f1`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140009966`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140009966`

## pseudocode

```c
__int64 __fastcall I8xSendIoctl(
        PDEVICE_OBJECT DeviceObject,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength)
{
  IRP *v8; // rax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 OutputBufferLength; // [rsp+28h] [rbp-80h]
  __int64 InternalDeviceIoControl; // [rsp+30h] [rbp-78h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v8 = IoBuildDeviceIoControlRequest(
         IoControlCode,
         DeviceObject,
         InputBuffer,
         InputBufferLength,
         0,
         0,
         1u,
         &Event,
         &IoStatusBlock);
  if ( !v8 )
    return 3221225626LL;
  v11 = IofCallDriver(DeviceObject, v8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(InternalDeviceIoControl) = v11;
    LODWORD(OutputBufferLength) = IoControlCode;
    WPP_RECORDER_SF_dD(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v10,
      0xCu,
      0x1Eu,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
      OutputBufferLength,
      InternalDeviceIoControl);
  }
  if ( v11 == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    return (unsigned int)IoStatusBlock.Status;
  }
  return v11;
}

```

## disassembly

```asm
0x1400098f0  push    rbx
0x1400098f2  push    rbp
0x1400098f3  push    rsi
0x1400098f4  push    rdi
0x1400098f5  sub     rsp, 88h
0x1400098fc  xorps   xmm0, xmm0
0x1400098ff  mov     rdi, r8
0x140009902  mov     ebp, edx
0x140009904  mov     rsi, rcx
0x140009907  xor     eax, eax
0x140009909  lea     rcx, [rsp+0A8h+Event]; Event
0x14000990e  xor     r8d, r8d; State
0x140009911  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x140009916  xor     edx, edx; Type
0x140009918  mov     ebx, r9d
0x14000991b  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x140009920  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140009925  call    cs:__imp_KeInitializeEvent
0x14000992c  nop     dword ptr [rax+rax+00h]
0x140009931  lea     rax, [rsp+0A8h+var_58]
0x140009936  mov     r9d, ebx; InputBufferLength
0x140009939  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x14000993e  mov     r8, rdi; InputBuffer
0x140009941  lea     rax, [rsp+0A8h+Event]
0x140009946  mov     rdx, rsi; DeviceObject
0x140009949  mov     [rsp+0A8h+var_70], rax; Event
0x14000994e  mov     ecx, ebp; IoControlCode
0x140009950  mov     [rsp+0A8h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x140009955  mov     dword ptr [rsp+0A8h+OutputBufferLength], 0; OutputBufferLength
0x14000995d  mov     [rsp+0A8h+OutputBuffer], 0; OutputBuffer
0x140009966  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000996d  nop     dword ptr [rax+rax+00h]
0x140009972  test    rax, rax
0x140009975  jnz     short loc_140009981
0x140009977  mov     eax, 0C000009Ah
0x14000997c  jmp     loc_140009A03
0x140009981  mov     rdx, rax; Irp
0x140009984  mov     rcx, rsi; DeviceObject
0x140009987  call    cs:__imp_IofCallDriver
0x14000998e  nop     dword ptr [rax+rax+00h]
0x140009993  mov     ebx, eax
0x140009995  lea     rax, WPP_RECORDER_INITIALIZED
0x14000999c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400099a3  jz      short loc_1400099D3
0x1400099a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099ac  lea     rax, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x1400099b3  mov     r9d, 1Eh
0x1400099b9  mov     dword ptr [rsp+0A8h+InternalDeviceIoControl], ebx
0x1400099bd  mov     dword ptr [rsp+0A8h+OutputBufferLength], ebp
0x1400099c1  mov     [rsp+0A8h+OutputBuffer], rax
0x1400099c6  mov     rcx, [rcx+40h]
0x1400099ca  lea     r8d, [r9-12h]
0x1400099ce  call    WPP_RECORDER_SF_dD
0x1400099d3  cmp     ebx, 103h
0x1400099d9  jnz     short loc_140009A01
0x1400099db  xor     r9d, r9d; Alertable
0x1400099de  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x1400099e7  xor     r8d, r8d; WaitMode
0x1400099ea  lea     rcx, [rsp+0A8h+Event]; Object
0x1400099ef  xor     edx, edx; WaitReason
0x1400099f1  call    cs:__imp_KeWaitForSingleObject
0x1400099f8  nop     dword ptr [rax+rax+00h]
0x1400099fd  mov     ebx, dword ptr [rsp+0A8h+var_58]
0x140009a01  mov     eax, ebx
0x140009a03  add     rsp, 88h
0x140009a0a  pop     rdi
0x140009a0b  pop     rsi
0x140009a0c  pop     rbp
0x140009a0d  pop     rbx
0x140009a0e  retn
```
