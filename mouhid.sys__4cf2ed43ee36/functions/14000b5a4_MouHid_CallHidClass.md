# MouHid_CallHidClass

- ea: `0x14000b5a4`
- end: `0x14000b720`
- name: `MouHid_CallHidClass`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400044bc`
- `0x14000baf0`

## callees

- `0x140001464`
- `0x14000b5a4`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000b669`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000b669`
- `ntoskrnl!KeInitializeEvent` at `0x14000b620`
- `ntoskrnl!KeInitializeEvent` at `0x14000b620`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b6c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b6c4`
- `ntoskrnl!IofCallDriver` at `0x14000b69d`
- `ntoskrnl!IofCallDriver` at `0x14000b69d`

## pseudocode

```c
__int64 __fastcall MouHid_CallHidClass(
        __int64 a1,
        ULONG a2,
        void *a3,
        ULONG a4,
        PVOID OutputBuffer,
        ULONG OutputBufferLength)
{
  PIRP v10; // rax
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      5u,
      0xAu,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v10 = IoBuildDeviceIoControlRequest(
          a2,
          *(PDEVICE_OBJECT *)(a1 + 8),
          a3,
          a4,
          OutputBuffer,
          OutputBufferLength,
          0,
          &Event,
          &IoStatusBlock);
  if ( !v10 )
    return 3221225473LL;
  v10->Tail.Overlay.CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(a1 + 128);
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 8), v10);
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
        (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000b5a4  push    rbx
0x14000b5a6  push    rbp
0x14000b5a7  push    rsi
0x14000b5a8  push    rdi
0x14000b5a9  push    r12
0x14000b5ab  push    r13
0x14000b5ad  push    r14
0x14000b5af  sub     rsp, 80h
0x14000b5b6  xorps   xmm0, xmm0
0x14000b5b9  xor     eax, eax
0x14000b5bb  movups  xmmword ptr [rsp+0B8h+Event.Header], xmm0
0x14000b5c0  mov     [rsp+0B8h+Event.Header.WaitListHead.Blink], rax
0x14000b5c5  mov     edi, r9d
0x14000b5c8  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x14000b5cd  mov     rsi, r8
0x14000b5d0  mov     ebp, edx
0x14000b5d2  mov     rbx, rcx
0x14000b5d5  lea     r13, WPP_RECORDER_INITIALIZED
0x14000b5dc  xor     r14d, r14d
0x14000b5df  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000b5e6  lea     r12, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000b5ed  jz      short loc_14000B616
0x14000b5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5f6  cmp     [rcx+48h], r14w
0x14000b5fb  jz      short loc_14000B616
0x14000b5fd  mov     rcx, [rcx+40h]
0x14000b601  lea     r8d, [rax+5]
0x14000b605  mov     dl, r8b
0x14000b608  mov     [rsp+0B8h+OutputBuffer], r12
0x14000b60d  lea     r9d, [rax+0Ah]
0x14000b611  call    WPP_RECORDER_SF_
0x14000b616  xor     r8d, r8d; State
0x14000b619  lea     rcx, [rsp+0B8h+Event]; Event
0x14000b61e  xor     edx, edx; Type
0x14000b620  call    cs:__imp_KeInitializeEvent
0x14000b627  nop     dword ptr [rax+rax+00h]
0x14000b62c  mov     rdx, [rbx+8]; DeviceObject
0x14000b630  lea     rax, [rsp+0B8h+var_68]
0x14000b635  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x14000b63a  mov     r9d, edi; InputBufferLength
0x14000b63d  lea     rax, [rsp+0B8h+Event]
0x14000b642  mov     r8, rsi; InputBuffer
0x14000b645  mov     [rsp+0B8h+var_80], rax; Event
0x14000b64a  mov     ecx, ebp; IoControlCode
0x14000b64c  mov     eax, [rsp+0B8h+arg_28]
0x14000b653  mov     [rsp+0B8h+InternalDeviceIoControl], r14b; InternalDeviceIoControl
0x14000b658  mov     [rsp+0B8h+OutputBufferLength], eax; OutputBufferLength
0x14000b65c  mov     rax, [rsp+0B8h+arg_20]
0x14000b664  mov     [rsp+0B8h+OutputBuffer], rax; OutputBuffer
0x14000b669  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000b670  nop     dword ptr [rax+rax+00h]
0x14000b675  mov     rdx, rax; Irp
0x14000b678  test    rax, rax
0x14000b67b  jnz     short loc_14000B687
0x14000b67d  mov     eax, 0C0000001h
0x14000b682  jmp     loc_14000B70D
0x14000b687  mov     rcx, [rax+0B8h]
0x14000b68e  mov     rax, [rbx+80h]
0x14000b695  mov     [rcx-18h], rax
0x14000b699  mov     rcx, [rbx+8]; DeviceObject
0x14000b69d  call    cs:__imp_IofCallDriver
0x14000b6a4  nop     dword ptr [rax+rax+00h]
0x14000b6a9  mov     ebx, eax
0x14000b6ab  cmp     eax, 103h
0x14000b6b0  jnz     short loc_14000B6D2
0x14000b6b2  xor     r9d, r9d; Alertable
0x14000b6b5  mov     [rsp+0B8h+OutputBuffer], r14; Timeout
0x14000b6ba  xor     r8d, r8d; WaitMode
0x14000b6bd  lea     rcx, [rsp+0B8h+Event]; Object
0x14000b6c2  xor     edx, edx; WaitReason
0x14000b6c4  call    cs:__imp_KeWaitForSingleObject
0x14000b6cb  nop     dword ptr [rax+rax+00h]
0x14000b6d0  mov     ebx, eax
0x14000b6d2  test    ebx, ebx
0x14000b6d4  cmovns  ebx, dword ptr [rsp+0B8h+var_68]
0x14000b6d9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000b6e0  jz      short loc_14000B70B
0x14000b6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6e9  cmp     [rcx+48h], r14w
0x14000b6ee  jz      short loc_14000B70B
0x14000b6f0  mov     rcx, [rcx+40h]
0x14000b6f4  mov     r9d, 0Bh
0x14000b6fa  mov     [rsp+0B8h+OutputBuffer], r12
0x14000b6ff  lea     r8d, [r9-6]
0x14000b703  mov     dl, r8b
0x14000b706  call    WPP_RECORDER_SF_
0x14000b70b  mov     eax, ebx
0x14000b70d  add     rsp, 80h
0x14000b714  pop     r14
0x14000b716  pop     r13
0x14000b718  pop     r12
0x14000b71a  pop     rdi
0x14000b71b  pop     rsi
0x14000b71c  pop     rbp
0x14000b71d  pop     rbx
0x14000b71e  retn
```
