# DiskSendFailurePredictIoctl

- ea: `0x140014520`
- end: `0x140014623`
- name: `DiskSendFailurePredictIoctl`
- size: `259`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140011ee0`
- `0x140014200`

## callees

- `0x140014520`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400145e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400145e9`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140014564`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140014564`
- `ntoskrnl!KeInitializeEvent` at `0x140014554`
- `ntoskrnl!KeInitializeEvent` at `0x140014554`
- `ntoskrnl!IofCallDriver` at `0x1400145be`
- `ntoskrnl!IofCallDriver` at `0x1400145be`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400145a7`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400145a7`
- `ntoskrnl!ObfDereferenceObject` at `0x140014603`
- `ntoskrnl!ObfDereferenceObject` at `0x140014603`

## pseudocode

```c
__int64 __fastcall DiskSendFailurePredictIoctl(__int64 a1, void *a2)
{
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rbx
  IRP *v5; // rax
  unsigned int Status; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  AttachedDeviceReference = IoGetAttachedDeviceReference(*(PDEVICE_OBJECT *)(a1 + 8));
  v5 = IoBuildDeviceIoControlRequest(0x2D1100u, AttachedDeviceReference, 0, 0, a2, 0x204u, 0, &Event, &IoStatusBlock);
  if ( v5 )
  {
    Status = IofCallDriver(AttachedDeviceReference, v5);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
  }
  else
  {
    Status = -1073741670;
  }
  ObfDereferenceObject(AttachedDeviceReference);
  return Status;
}

```

## disassembly

```asm
0x140014520  mov     [rsp+arg_0], rbx
0x140014525  push    rdi
0x140014526  sub     rsp, 80h
0x14001452d  xorps   xmm0, xmm0
0x140014530  mov     rdi, rdx
0x140014533  mov     rbx, rcx
0x140014536  xor     eax, eax
0x140014538  mov     edx, 1; Type
0x14001453d  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x140014542  lea     rcx, [rsp+88h+Event]; Event
0x140014547  xor     r8d, r8d; State
0x14001454a  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x14001454f  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x140014554  call    cs:__imp_KeInitializeEvent
0x14001455b  nop     dword ptr [rax+rax+00h]
0x140014560  mov     rcx, [rbx+8]; DeviceObject
0x140014564  call    cs:__imp_IoGetAttachedDeviceReference
0x14001456b  nop     dword ptr [rax+rax+00h]
0x140014570  xor     r9d, r9d; InputBufferLength
0x140014573  xor     r8d, r8d; InputBuffer
0x140014576  mov     rbx, rax
0x140014579  mov     ecx, 2D1100h; IoControlCode
0x14001457e  lea     rax, [rsp+88h+var_38]
0x140014583  mov     rdx, rbx; DeviceObject
0x140014586  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x14001458b  lea     rax, [rsp+88h+Event]
0x140014590  mov     [rsp+88h+var_50], rax; Event
0x140014595  mov     [rsp+88h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14001459a  mov     [rsp+88h+OutputBufferLength], 204h; OutputBufferLength
0x1400145a2  mov     [rsp+88h+OutputBuffer], rdi; OutputBuffer
0x1400145a7  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400145ae  nop     dword ptr [rax+rax+00h]
0x1400145b3  test    rax, rax
0x1400145b6  jz      short loc_1400145FB
0x1400145b8  mov     rdx, rax; Irp
0x1400145bb  mov     rcx, rbx; DeviceObject
0x1400145be  call    cs:__imp_IofCallDriver
0x1400145c5  nop     dword ptr [rax+rax+00h]
0x1400145ca  mov     edi, eax
0x1400145cc  cmp     eax, 103h
0x1400145d1  jnz     short loc_140014600
0x1400145d3  xor     r9d, r9d; Alertable
0x1400145d6  mov     [rsp+88h+OutputBuffer], 0; Timeout
0x1400145df  xor     r8d, r8d; WaitMode
0x1400145e2  lea     rcx, [rsp+88h+Event]; Object
0x1400145e7  xor     edx, edx; WaitReason
0x1400145e9  call    cs:__imp_KeWaitForSingleObject
0x1400145f0  nop     dword ptr [rax+rax+00h]
0x1400145f5  mov     edi, dword ptr [rsp+88h+var_38]
0x1400145f9  jmp     short loc_140014600
0x1400145fb  mov     edi, 0C000009Ah
0x140014600  mov     rcx, rbx; Object
0x140014603  call    cs:__imp_ObfDereferenceObject
0x14001460a  nop     dword ptr [rax+rax+00h]
0x14001460f  mov     rbx, [rsp+88h+arg_0]
0x140014617  mov     eax, edi
0x140014619  add     rsp, 80h
0x140014620  pop     rdi
0x140014621  retn
```
