# KbdHid_CallHidClass

- ea: `0x140010510`
- end: `0x140010682`
- name: `KbdHid_CallHidClass`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400042d0`
- `0x14000ff70`

## callees

- `0x140005a0c`
- `0x140010510`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400105fe`
- `ntoskrnl!IofCallDriver` at `0x1400105fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010629`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010629`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400105ca`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400105ca`
- `ntoskrnl!KeInitializeEvent` at `0x140010581`
- `ntoskrnl!KeInitializeEvent` at `0x140010581`

## pseudocode

```c
__int64 __fastcall KbdHid_CallHidClass(
        __int64 a1,
        ULONG a2,
        __int64 a3,
        __int64 a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  PIRP v8; // rax
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-48h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      5u,
      0xAu,
      (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v8 = IoBuildDeviceIoControlRequest(
         a2,
         *(PDEVICE_OBJECT *)(a1 + 8),
         0,
         0,
         OutputBuffer,
         OutputBufferLength,
         0,
         &Event,
         &IoStatusBlock);
  if ( !v8 )
    return 3221225473LL;
  v8->Tail.Overlay.CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(a1 + 128);
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 8), v8);
  if ( Status == 259 )
    Status = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  if ( Status >= 0 )
    Status = IoStatusBlock.Status;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        5u,
        5u,
        0xBu,
        (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140010510  push    rbx
0x140010512  push    rbp
0x140010513  push    rsi
0x140010514  push    rdi
0x140010515  sub     rsp, 88h
0x14001051c  xorps   xmm0, xmm0
0x14001051f  xor     eax, eax
0x140010521  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x140010526  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14001052b  mov     edi, edx
0x14001052d  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140010532  mov     rbx, rcx
0x140010535  lea     rsi, WPP_RECORDER_INITIALIZED
0x14001053c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140010543  lea     rbp, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x14001054a  jz      short loc_140010577
0x14001054c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010553  cmp     [rcx+48h], ax
0x140010557  jz      short loc_140010577
0x140010559  mov     rcx, [rcx+40h]
0x14001055d  mov     r8d, 5
0x140010563  movzx   edx, r8b
0x140010567  mov     [rsp+0A8h+OutputBuffer], rbp
0x14001056c  mov     r9d, 0Ah
0x140010572  call    WPP_RECORDER_SF_
0x140010577  xor     r8d, r8d; State
0x14001057a  lea     rcx, [rsp+0A8h+Event]; Event
0x14001057f  xor     edx, edx; Type
0x140010581  call    cs:__imp_KeInitializeEvent
0x140010588  nop     dword ptr [rax+rax+00h]
0x14001058d  mov     rdx, [rbx+8]; DeviceObject
0x140010591  lea     rax, [rsp+0A8h+var_58]
0x140010596  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x14001059b  xor     r9d, r9d; InputBufferLength
0x14001059e  lea     rax, [rsp+0A8h+Event]
0x1400105a3  xor     r8d, r8d; InputBuffer
0x1400105a6  mov     [rsp+0A8h+var_70], rax; Event
0x1400105ab  mov     ecx, edi; IoControlCode
0x1400105ad  mov     eax, [rsp+0A8h+arg_28]
0x1400105b4  mov     [rsp+0A8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x1400105b9  mov     [rsp+0A8h+OutputBufferLength], eax; OutputBufferLength
0x1400105bd  mov     rax, [rsp+0A8h+arg_20]
0x1400105c5  mov     [rsp+0A8h+OutputBuffer], rax; OutputBuffer
0x1400105ca  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400105d1  nop     dword ptr [rax+rax+00h]
0x1400105d6  mov     rdx, rax; Irp
0x1400105d9  test    rax, rax
0x1400105dc  jnz     short loc_1400105E8
0x1400105de  mov     eax, 0C0000001h
0x1400105e3  jmp     loc_140010675
0x1400105e8  mov     rcx, [rax+0B8h]
0x1400105ef  mov     rax, [rbx+80h]
0x1400105f6  mov     [rcx-18h], rax
0x1400105fa  mov     rcx, [rbx+8]; DeviceObject
0x1400105fe  call    cs:__imp_IofCallDriver
0x140010605  nop     dword ptr [rax+rax+00h]
0x14001060a  mov     ebx, eax
0x14001060c  cmp     eax, 103h
0x140010611  jnz     short loc_140010637
0x140010613  xor     r9d, r9d; Alertable
0x140010616  mov     [rsp+0A8h+OutputBuffer], 0; Timeout
0x14001061f  xor     r8d, r8d; WaitMode
0x140010622  lea     rcx, [rsp+0A8h+Event]; Object
0x140010627  xor     edx, edx; WaitReason
0x140010629  call    cs:__imp_KeWaitForSingleObject
0x140010630  nop     dword ptr [rax+rax+00h]
0x140010635  mov     ebx, eax
0x140010637  test    ebx, ebx
0x140010639  cmovns  ebx, dword ptr [rsp+0A8h+var_58]
0x14001063e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140010645  jz      short loc_140010673
0x140010647  mov     rcx, cs:WPP_GLOBAL_Control
0x14001064e  cmp     word ptr [rcx+48h], 0
0x140010653  jz      short loc_140010673
0x140010655  mov     rcx, [rcx+40h]
0x140010659  mov     r8d, 5
0x14001065f  movzx   edx, r8b
0x140010663  mov     [rsp+0A8h+OutputBuffer], rbp
0x140010668  mov     r9d, 0Bh
0x14001066e  call    WPP_RECORDER_SF_
0x140010673  mov     eax, ebx
0x140010675  add     rsp, 88h
0x14001067c  pop     rdi
0x14001067d  pop     rsi
0x14001067e  pop     rbp
0x14001067f  pop     rbx
0x140010680  retn
```
