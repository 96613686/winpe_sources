# CreatePrintPortInterface

- ea: `0x14002bca0`
- end: `0x14002be36`
- name: `CreatePrintPortInterface`
- size: `406`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004cd8`

## callees

- `0x14002bca0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002bcc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bcc9`
- `ntoskrnl!KeInitializeEvent` at `0x14002bd4e`
- `ntoskrnl!KeInitializeEvent` at `0x14002bd4e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bdee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bdee`
- `ntoskrnl!ObfDereferenceObject` at `0x14002be14`
- `ntoskrnl!ObfDereferenceObject` at `0x14002be14`
- `ntoskrnl!IofCallDriver` at `0x14002bdc4`
- `ntoskrnl!IofCallDriver` at `0x14002bdc4`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002bda1`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002bda1`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002bd2b`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14002bd2b`

## pseudocode

```c
__int64 __fastcall CreatePrintPortInterface(__int64 a1, __int64 a2)
{
  NTSTATUS DeviceObjectPointer; // ebx
  IRP *v5; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-58h] BYREF
  __int128 InputBuffer; // [rsp+70h] [rbp-48h] BYREF
  __int64 v10; // [rsp+80h] [rbp-38h]
  struct _KEVENT Event; // [rsp+88h] [rbp-30h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+D0h] [rbp+18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+D8h] [rbp+20h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\RdpBus");
  v10 = 0;
  DeviceObject = 0;
  FileObject = 0;
  IoStatusBlock = 0;
  memset(&Event, 0, sizeof(Event));
  InputBuffer = 0;
  DeviceObjectPointer = IoGetDeviceObjectPointer(&DestinationString, 0x1F01FFu, &FileObject, &DeviceObject);
  if ( DeviceObjectPointer >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    *(_QWORD *)&InputBuffer = a1;
    *((_QWORD *)&InputBuffer + 1) = a2;
    v5 = IoBuildDeviceIoControlRequest(0x220804u, DeviceObject, &InputBuffer, 0x18u, 0, 0, 0, &Event, &IoStatusBlock);
    if ( v5 )
    {
      DeviceObjectPointer = IofCallDriver(DeviceObject, v5);
      if ( DeviceObjectPointer == 259 )
        DeviceObjectPointer = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( DeviceObjectPointer >= 0 )
        DeviceObjectPointer = v10;
    }
    else
    {
      DeviceObjectPointer = -1073741801;
    }
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)DeviceObjectPointer;
}

```

## disassembly

```asm
0x14002bca0  mov     [rsp+arg_0], rbx
0x14002bca5  push    rbp
0x14002bca6  push    rsi
0x14002bca7  push    rdi
0x14002bca8  sub     rsp, 0A0h
0x14002bcaf  mov     rdi, rdx
0x14002bcb2  mov     rsi, rcx
0x14002bcb5  xorps   xmm0, xmm0
0x14002bcb8  lea     rdx, aDeviceRdpbus; "\\Device\\RdpBus"
0x14002bcbf  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14002bcc4  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14002bcc9  call    cs:__imp_RtlInitUnicodeString
0x14002bcd0  nop     dword ptr [rax+rax+00h]
0x14002bcd5  xorps   xmm0, xmm0
0x14002bcd8  lea     r9, [rsp+0B8h+DeviceObject]; DeviceObject
0x14002bce0  xor     eax, eax
0x14002bce2  lea     r8, [rsp+0B8h+FileObject]; FileObject
0x14002bcea  xorps   xmm1, xmm1
0x14002bced  mov     [rsp+0B8h+Event.Header.WaitListHead.Blink], rax
0x14002bcf5  xor     ebp, ebp
0x14002bcf7  mov     [rsp+0B8h+var_38], rax
0x14002bcff  mov     edx, 1F01FFh; DesiredAccess
0x14002bd04  mov     [rsp+0B8h+DeviceObject], rbp
0x14002bd0c  lea     rcx, [rsp+0B8h+DestinationString]; ObjectName
0x14002bd11  mov     [rsp+0B8h+FileObject], rbp
0x14002bd19  movups  xmmword ptr [rsp+0B8h+var_58], xmm0
0x14002bd1e  movups  xmmword ptr [rsp+0B8h+Event.Header], xmm1
0x14002bd26  movups  [rsp+0B8h+InputBuffer], xmm0
0x14002bd2b  call    cs:__imp_IoGetDeviceObjectPointer
0x14002bd32  nop     dword ptr [rax+rax+00h]
0x14002bd37  mov     ebx, eax
0x14002bd39  test    eax, eax
0x14002bd3b  js      loc_14002BE07
0x14002bd41  xor     r8d, r8d; State
0x14002bd44  lea     rcx, [rsp+0B8h+Event]; Event
0x14002bd4c  xor     edx, edx; Type
0x14002bd4e  call    cs:__imp_KeInitializeEvent
0x14002bd55  nop     dword ptr [rax+rax+00h]
0x14002bd5a  mov     rdx, [rsp+0B8h+DeviceObject]; DeviceObject
0x14002bd62  lea     rax, [rsp+0B8h+var_58]
0x14002bd67  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x14002bd6c  lea     r8, [rsp+0B8h+InputBuffer]; InputBuffer
0x14002bd71  lea     rax, [rsp+0B8h+Event]
0x14002bd79  mov     qword ptr [rsp+0B8h+InputBuffer], rsi
0x14002bd7e  mov     [rsp+0B8h+var_80], rax; Event
0x14002bd83  mov     r9d, 18h; InputBufferLength
0x14002bd89  mov     [rsp+0B8h+InternalDeviceIoControl], bpl; InternalDeviceIoControl
0x14002bd8e  mov     ecx, 220804h; IoControlCode
0x14002bd93  mov     [rsp+0B8h+OutputBufferLength], ebp; OutputBufferLength
0x14002bd97  mov     [rsp+0B8h+OutputBuffer], rbp; OutputBuffer
0x14002bd9c  mov     qword ptr [rsp+0B8h+InputBuffer+8], rdi
0x14002bda1  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14002bda8  nop     dword ptr [rax+rax+00h]
0x14002bdad  test    rax, rax
0x14002bdb0  jnz     short loc_14002BDB9
0x14002bdb2  mov     ebx, 0C0000017h
0x14002bdb7  jmp     short loc_14002BE07
0x14002bdb9  mov     rcx, [rsp+0B8h+DeviceObject]; DeviceObject
0x14002bdc1  mov     rdx, rax; Irp
0x14002bdc4  call    cs:__imp_IofCallDriver
0x14002bdcb  nop     dword ptr [rax+rax+00h]
0x14002bdd0  mov     ebx, eax
0x14002bdd2  cmp     eax, 103h
0x14002bdd7  jnz     short loc_14002BDFC
0x14002bdd9  xor     r9d, r9d; Alertable
0x14002bddc  mov     [rsp+0B8h+OutputBuffer], rbp; Timeout
0x14002bde1  xor     r8d, r8d; WaitMode
0x14002bde4  lea     rcx, [rsp+0B8h+Event]; Object
0x14002bdec  xor     edx, edx; WaitReason
0x14002bdee  call    cs:__imp_KeWaitForSingleObject
0x14002bdf5  nop     dword ptr [rax+rax+00h]
0x14002bdfa  mov     ebx, eax
0x14002bdfc  test    ebx, ebx
0x14002bdfe  js      short loc_14002BE07
0x14002be00  mov     ebx, dword ptr [rsp+0B8h+var_38]
0x14002be07  mov     rcx, [rsp+0B8h+FileObject]; Object
0x14002be0f  test    rcx, rcx
0x14002be12  jz      short loc_14002BE20
0x14002be14  call    cs:__imp_ObfDereferenceObject
0x14002be1b  nop     dword ptr [rax+rax+00h]
0x14002be20  mov     eax, ebx
0x14002be22  mov     rbx, [rsp+0B8h+arg_0]
0x14002be2a  add     rsp, 0A0h
0x14002be31  pop     rdi
0x14002be32  pop     rsi
0x14002be33  pop     rbp
0x14002be34  retn
```
