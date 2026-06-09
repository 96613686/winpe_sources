# KbdHid_SendS0IdleStopResumeIrp

- ea: `0x14000fd50`
- end: `0x14000ff5e`
- name: `KbdHid_SendS0IdleStopResumeIrp`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140004d30`

## callees

- `0x140004e50`
- `0x1400052a0`
- `0x140005a0c`
- `0x14000fd50`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000fe76`
- `ntoskrnl!IofCallDriver` at `0x14000fe76`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fed2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000fed2`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000fe13`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14000fe13`
- `ntoskrnl!KeInitializeEvent` at `0x14000fdc5`
- `ntoskrnl!KeInitializeEvent` at `0x14000fdc5`

## pseudocode

```c
__int64 __fastcall KbdHid_SendS0IdleStopResumeIrp(__int64 a1, int a2)
{
  ULONG v4; // ebp
  IRP *v5; // rax
  char v6; // si
  unsigned int Status; // ebx
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int OutputBuffer; // [rsp+20h] [rbp-98h]
  int OutputBuffera; // [rsp+20h] [rbp-98h]
  __int64 InternalDeviceIoControl; // [rsp+30h] [rbp-88h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-68h] BYREF
  struct _KEVENT Event; // [rsp+60h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      2u,
      0x16u,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v4 = 721499;
  if ( a2 != 1 )
    v4 = 721503;
  v5 = IoBuildDeviceIoControlRequest(v4, *(PDEVICE_OBJECT *)(a1 + 8), 0, 0, 0, 0, 0, &Event, &IoStatusBlock);
  v6 = (char)v5;
  if ( v5 )
  {
    v8 = IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 8), v5);
    Status = v8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qLqd(WPP_GLOBAL_Control->DeviceExtension, v9, v10, 24, OutputBuffer, *(_QWORD *)a1, v4, v6, v8);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = IoStatusBlock.Status;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return Status;
      WPP_RECORDER_SF_qLqd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        25,
        OutputBuffera,
        *(_QWORD *)a1,
        v4,
        v6,
        IoStatusBlock.Status);
    }
  }
  else
  {
    Status = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return Status;
    LODWORD(InternalDeviceIoControl) = -1073741670;
    WPP_RECORDER_SF_qd(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      2u,
      2u,
      0x17u,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
      *(_QWORD *)a1,
      InternalDeviceIoControl);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      2u,
      0x1Au,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  return Status;
}

```

## disassembly

```asm
0x14000fd50  push    rbx
0x14000fd52  push    rbp
0x14000fd53  push    rsi
0x14000fd54  push    rdi
0x14000fd55  push    r12
0x14000fd57  push    r14
0x14000fd59  push    r15
0x14000fd5b  sub     rsp, 80h
0x14000fd62  xorps   xmm0, xmm0
0x14000fd65  xor     eax, eax
0x14000fd67  movups  xmmword ptr [rsp+0B8h+Event.Header], xmm0
0x14000fd6c  mov     [rsp+0B8h+Event.Header.WaitListHead.Blink], rax
0x14000fd71  mov     ebx, edx
0x14000fd73  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x14000fd78  mov     rdi, rcx
0x14000fd7b  lea     r14, WPP_RECORDER_INITIALIZED
0x14000fd82  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000fd89  lea     r12, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x14000fd90  jz      short loc_14000FDBB
0x14000fd92  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd99  cmp     [rcx+48h], ax
0x14000fd9d  jz      short loc_14000FDBB
0x14000fd9f  mov     rcx, [rcx+40h]
0x14000fda3  mov     r9d, 16h
0x14000fda9  mov     r8d, 2
0x14000fdaf  mov     [rsp+0B8h+OutputBuffer], r12
0x14000fdb4  mov     dl, 5
0x14000fdb6  call    WPP_RECORDER_SF_
0x14000fdbb  xor     r8d, r8d; State
0x14000fdbe  lea     rcx, [rsp+0B8h+Event]; Event
0x14000fdc3  xor     edx, edx; Type
0x14000fdc5  call    cs:__imp_KeInitializeEvent
0x14000fdcc  nop     dword ptr [rax+rax+00h]
0x14000fdd1  mov     rdx, [rdi+8]; DeviceObject
0x14000fdd5  mov     eax, 0B025Fh
0x14000fdda  cmp     ebx, 1
0x14000fddd  mov     ebp, 0B025Bh
0x14000fde2  cmovnz  ebp, eax
0x14000fde5  lea     rax, [rsp+0B8h+var_68]
0x14000fdea  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x14000fdef  xor     r15d, r15d
0x14000fdf2  lea     rax, [rsp+0B8h+Event]
0x14000fdf7  xor     r9d, r9d; InputBufferLength
0x14000fdfa  mov     [rsp+0B8h+var_80], rax; Event
0x14000fdff  xor     r8d, r8d; InputBuffer
0x14000fe02  mov     [rsp+0B8h+InternalDeviceIoControl], 0; InternalDeviceIoControl
0x14000fe07  mov     ecx, ebp; IoControlCode
0x14000fe09  mov     [rsp+0B8h+OutputBufferLength], r15d; OutputBufferLength
0x14000fe0e  mov     [rsp+0B8h+OutputBuffer], r15; OutputBuffer
0x14000fe13  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14000fe1a  nop     dword ptr [rax+rax+00h]
0x14000fe1f  mov     rsi, rax
0x14000fe22  test    rax, rax
0x14000fe25  jnz     short loc_14000FE6F
0x14000fe27  mov     ebx, 0C000009Ah
0x14000fe2c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000fe33  jz      loc_14000FF49
0x14000fe39  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe40  mov     r8d, 2
0x14000fe46  mov     rax, [rdi]
0x14000fe49  mov     r9d, 17h
0x14000fe4f  mov     dword ptr [rsp+0B8h+InternalDeviceIoControl], ebx
0x14000fe53  movzx   edx, r8b
0x14000fe57  mov     qword ptr [rsp+0B8h+OutputBufferLength], rax
0x14000fe5c  mov     rcx, [rcx+40h]
0x14000fe60  mov     [rsp+0B8h+OutputBuffer], r12
0x14000fe65  call    WPP_RECORDER_SF_qd
0x14000fe6a  jmp     loc_14000FF16
0x14000fe6f  mov     rcx, [rdi+8]; DeviceObject
0x14000fe73  mov     rdx, rsi; Irp
0x14000fe76  call    cs:__imp_IofCallDriver
0x14000fe7d  nop     dword ptr [rax+rax+00h]
0x14000fe82  mov     ebx, eax
0x14000fe84  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000fe8b  jz      short loc_14000FEB8
0x14000fe8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe94  mov     r9d, 18h
0x14000fe9a  mov     dword ptr [rsp+0B8h+IoStatusBlock], eax
0x14000fe9e  mov     rax, [rdi]
0x14000fea1  mov     [rsp+0B8h+var_80], rsi
0x14000fea6  mov     rcx, [rcx+40h]
0x14000feaa  mov     dword ptr [rsp+0B8h+InternalDeviceIoControl], ebp
0x14000feae  mov     qword ptr [rsp+0B8h+OutputBufferLength], rax
0x14000feb3  call    WPP_RECORDER_SF_qLqd
0x14000feb8  cmp     ebx, 103h
0x14000febe  jnz     short loc_14000FF16
0x14000fec0  xor     r9d, r9d; Alertable
0x14000fec3  mov     [rsp+0B8h+OutputBuffer], r15; Timeout
0x14000fec8  xor     r8d, r8d; WaitMode
0x14000fecb  lea     rcx, [rsp+0B8h+Event]; Object
0x14000fed0  xor     edx, edx; WaitReason
0x14000fed2  call    cs:__imp_KeWaitForSingleObject
0x14000fed9  nop     dword ptr [rax+rax+00h]
0x14000fede  mov     ebx, dword ptr [rsp+0B8h+var_68]
0x14000fee2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14000fee9  jz      short loc_14000FF49
0x14000feeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fef2  mov     r9d, 19h
0x14000fef8  mov     rax, [rdi]
0x14000fefb  mov     dword ptr [rsp+0B8h+IoStatusBlock], ebx
0x14000feff  mov     [rsp+0B8h+var_80], rsi
0x14000ff04  mov     rcx, [rcx+40h]
0x14000ff08  mov     dword ptr [rsp+0B8h+InternalDeviceIoControl], ebp
0x14000ff0c  mov     qword ptr [rsp+0B8h+OutputBufferLength], rax
0x14000ff11  call    WPP_RECORDER_SF_qLqd
0x14000ff16  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000ff1d  jz      short loc_14000FF49
0x14000ff1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff26  cmp     [rcx+48h], r15w
0x14000ff2b  jz      short loc_14000FF49
0x14000ff2d  mov     rcx, [rcx+40h]
0x14000ff31  mov     r9d, 1Ah
0x14000ff37  mov     r8d, 2
0x14000ff3d  mov     [rsp+0B8h+OutputBuffer], r12
0x14000ff42  mov     dl, 5
0x14000ff44  call    WPP_RECORDER_SF_
0x14000ff49  mov     eax, ebx
0x14000ff4b  add     rsp, 80h
0x14000ff52  pop     r15
0x14000ff54  pop     r14
0x14000ff56  pop     r12
0x14000ff58  pop     rdi
0x14000ff59  pop     rsi
0x14000ff5a  pop     rbp
0x14000ff5b  pop     rbx
0x14000ff5c  retn
```
