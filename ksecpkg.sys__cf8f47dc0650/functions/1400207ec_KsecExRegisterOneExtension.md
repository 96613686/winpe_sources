# KsecExRegisterOneExtension

- ea: `0x1400207ec`
- end: `0x140020909`
- name: `KsecExRegisterOneExtension`
- size: `285`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID InputBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400206f8`

## callees

- `0x140007008`
- `0x1400207ec`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400208c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400208c4`
- `ntoskrnl!IofCallDriver` at `0x140020899`
- `ntoskrnl!IofCallDriver` at `0x140020899`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140020864`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140020864`
- `ntoskrnl!KeInitializeEvent` at `0x14002081d`
- `ntoskrnl!KeInitializeEvent` at `0x14002081d`

## string_xrefs

- `0x14002087d`: `KsecExRegisterOneExtension: IoBuildDeviceIoControlRequest failed\n`
- `0x1400208e4`: `KsecExRegisterOneExtension: IoCallDriver failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall KsecExRegisterOneExtension(PDEVICE_OBJECT DeviceObject, PVOID InputBuffer)
{
  IRP *v4; // rax
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-28h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v4 = IoBuildDeviceIoControlRequest(0x390038u, DeviceObject, InputBuffer, 0x10u, 0, 0, 0, &Event, &IoStatusBlock);
  if ( v4 )
  {
    Status = IofCallDriver(DeviceObject, v4);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status < 0 && KsecInfoLevel )
      KsecDebugOut(1, "KsecExRegisterOneExtension: IoCallDriver failed: 0x%lx\n", Status);
    return (unsigned int)Status;
  }
  else
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "KsecExRegisterOneExtension: IoBuildDeviceIoControlRequest failed\n");
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x1400207ec  mov     [rsp+arg_0], rbx
0x1400207f1  push    rdi
0x1400207f2  sub     rsp, 80h
0x1400207f9  xorps   xmm0, xmm0
0x1400207fc  mov     rbx, rdx
0x1400207ff  mov     rdi, rcx
0x140020802  xor     eax, eax
0x140020804  xor     edx, edx; Type
0x140020806  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x14002080b  lea     rcx, [rsp+88h+Event]; Event
0x140020810  xor     r8d, r8d; State
0x140020813  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x140020818  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x14002081d  call    cs:__imp_KeInitializeEvent
0x140020824  nop     dword ptr [rax+rax+00h]
0x140020829  lea     rax, [rsp+88h+var_38]
0x14002082e  mov     r9d, 10h; InputBufferLength
0x140020834  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x140020839  mov     r8, rbx; InputBuffer
0x14002083c  lea     rax, [rsp+88h+Event]
0x140020841  mov     rdx, rdi; DeviceObject
0x140020844  mov     [rsp+88h+var_50], rax; Event
0x140020849  mov     ecx, 390038h; IoControlCode
0x14002084e  mov     [rsp+88h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x140020853  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x14002085b  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x140020864  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14002086b  nop     dword ptr [rax+rax+00h]
0x140020870  test    rax, rax
0x140020873  jnz     short loc_140020893
0x140020875  cmp     cs:KsecInfoLevel, eax
0x14002087b  jz      short loc_14002088C
0x14002087d  lea     rdx, aKsecexregister_2; "KsecExRegisterOneExtension: IoBuildDevi"...
0x140020884  lea     ecx, [rax+1]
0x140020887  call    KsecDebugOut
0x14002088c  mov     eax, 0C0000001h
0x140020891  jmp     short loc_1400208F7
0x140020893  mov     rdx, rax; Irp
0x140020896  mov     rcx, rdi; DeviceObject
0x140020899  call    cs:__imp_IofCallDriver
0x1400208a0  nop     dword ptr [rax+rax+00h]
0x1400208a5  mov     ebx, eax
0x1400208a7  cmp     eax, 103h
0x1400208ac  jnz     short loc_1400208D4
0x1400208ae  xor     r9d, r9d; Alertable
0x1400208b1  mov     [rsp+88h+OutputBuffer], 0; Timeout
0x1400208ba  xor     r8d, r8d; WaitMode
0x1400208bd  lea     rcx, [rsp+88h+Event]; Object
0x1400208c2  xor     edx, edx; WaitReason
0x1400208c4  call    cs:__imp_KeWaitForSingleObject
0x1400208cb  nop     dword ptr [rax+rax+00h]
0x1400208d0  mov     ebx, dword ptr [rsp+88h+var_38]
0x1400208d4  test    ebx, ebx
0x1400208d6  jns     short loc_1400208F5
0x1400208d8  cmp     cs:KsecInfoLevel, 0
0x1400208df  jz      short loc_1400208F5
0x1400208e1  mov     r8d, ebx
0x1400208e4  lea     rdx, aKsecexregister_1; "KsecExRegisterOneExtension: IoCallDrive"...
0x1400208eb  mov     ecx, 1
0x1400208f0  call    KsecDebugOut
0x1400208f5  mov     eax, ebx
0x1400208f7  mov     rbx, [rsp+88h+arg_0]
0x1400208ff  add     rsp, 80h
0x140020906  pop     rdi
0x140020907  retn
```
