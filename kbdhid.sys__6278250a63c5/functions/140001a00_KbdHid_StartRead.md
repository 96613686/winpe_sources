# KbdHid_StartRead

- ea: `0x140001a00`
- end: `0x140001d22`
- name: `KbdHid_StartRead`
- size: `802`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001300`
- `0x1400026a0`
- `0x140006870`

## callees

- `0x140001a00`
- `0x140005a0c`
- `0x140005d88`
- `0x1400068bc`
- `0x140006978`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140001ac2`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140001ac2`
- `ntoskrnl!IofCallDriver` at `0x140001b05`
- `ntoskrnl!IofCallDriver` at `0x140001b05`
- `ntoskrnl!KeSetEvent` at `0x140001b1c`
- `ntoskrnl!KeSetEvent` at `0x140001c78`
- `ntoskrnl!KeSetEvent` at `0x140001c8d`
- `ntoskrnl!KeSetEvent` at `0x140001cf4`
- `ntoskrnl!KeSetEvent` at `0x140001b1c`
- `ntoskrnl!KeSetEvent` at `0x140001c78`
- `ntoskrnl!KeSetEvent` at `0x140001c8d`
- `ntoskrnl!KeSetEvent` at `0x140001cf4`
- `ntoskrnl!IoReuseIrp` at `0x140001a63`
- `ntoskrnl!IoReuseIrp` at `0x140001a63`
- `ntoskrnl!KeResetEvent` at `0x140001ada`
- `ntoskrnl!KeResetEvent` at `0x140001ada`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001c26`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001d11`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001c26`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001d11`

## pseudocode

```c
__int64 __fastcall KbdHid_StartRead(char *Context)
{
  IRP *v1; // rsi
  NTSTATUS Status; // edi
  __int64 *v4; // rdx
  __int64 v5; // r15
  _BYTE *v6; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  int v8; // r8d
  struct _IO_STACK_LOCATION *v10; // rax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  int InvokeOnSuccess; // [rsp+20h] [rbp-68h]

  v1 = (IRP *)*((_QWORD *)Context + 13);
  Status = v1->IoStatus.Status;
  v4 = WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v4,
      2,
      15,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  }
  v5 = *((_QWORD *)Context + 14);
  v6 = Context + 89;
  while ( _InterlockedExchange((volatile __int32 *)Context + 8, 1) == 2 )
  {
    if ( Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 3;
        WPP_RECORDER_SF_qqd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v4,
          2,
          18,
          (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
          *(_QWORD *)Context,
          (char)v1,
          Status);
      }
      KeSetEvent((PRKEVENT)(Context + 40), 0, 0);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), *((PVOID *)Context + 13), 0x20u);
      break;
    }
    IoReuseIrp(v1, 0);
    CurrentStackLocation = v1->Tail.Overlay.CurrentStackLocation;
    v1->MdlAddress = *(PMDL *)(v5 + 144);
    CurrentStackLocation[-1].Parameters.Read.Length = *(unsigned __int16 *)(v5 + 12);
    CurrentStackLocation[-1].Parameters.Create.Options = 0;
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = 0;
    CurrentStackLocation[-1].MajorFunction = 3;
    CurrentStackLocation[-1].FileObject = (PFILE_OBJECT)*((_QWORD *)Context + 16);
    if ( IoSetCompletionRoutineEx(*(PDEVICE_OBJECT *)Context, v1, KbdHid_ReadComplete, Context, 1u, 1u, 1u) < 0 )
    {
      v10 = v1->Tail.Overlay.CurrentStackLocation;
      v6 = Context + 89;
      v10[-1].CompletionRoutine = KbdHid_ReadComplete;
      v10[-1].Context = Context;
      v10[-1].Control = -32;
    }
    KeResetEvent((PRKEVENT)(Context + 64));
    if ( !*((_DWORD *)Context + 7) || (v6 = Context + 89, Context[89] == 1) )
    {
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), *((PVOID *)Context + 13), 0x20u);
      Status = -1073741738;
      if ( !*v6 )
        Status = -1073741823;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v12,
          v13,
          InvokeOnSuccess,
          *(_QWORD *)Context,
          *((_DWORD *)Context + 7),
          Status);
      KeSetEvent((PRKEVENT)(Context + 64), 0, 0);
      KeSetEvent((PRKEVENT)(Context + 40), 0, 0);
      break;
    }
    Status = IofCallDriver(*((PDEVICE_OBJECT *)Context + 1), v1);
    KeSetEvent((PRKEVENT)(Context + 64), 0, 0);
    if ( _InterlockedExchange((volatile __int32 *)Context + 8, 2) != 3 )
      break;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v4) = 5;
      WPP_RECORDER_SF_q(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v4, v8, 17, InvokeOnSuccess, *(_QWORD *)Context);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v4,
      2,
      19,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140001a00  push    rbx
0x140001a02  push    rbp
0x140001a03  push    rsi
0x140001a04  push    rdi
0x140001a05  push    r12
0x140001a07  push    r13
0x140001a09  push    r14
0x140001a0b  push    r15
0x140001a0d  sub     rsp, 48h
0x140001a11  mov     rsi, [rcx+68h]
0x140001a15  mov     rbx, rcx
0x140001a18  mov     edi, [rsi+30h]
0x140001a1b  lea     r13, WPP_RECORDER_INITIALIZED
0x140001a22  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140001a29  lea     rdx, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140001a30  jnz     loc_140001B5D
0x140001a36  mov     r15, [rbx+70h]
0x140001a3a  lea     r14, [rbx+59h]
0x140001a3e  mov     eax, 1
0x140001a43  lea     r12, KbdHid_ReadComplete
0x140001a4a  xchg    eax, [rbx+20h]
0x140001a4d  cmp     eax, 2
0x140001a50  jnz     loc_140001B39
0x140001a56  test    edi, edi
0x140001a58  js      loc_140001C9E
0x140001a5e  xor     edx, edx; Iostatus
0x140001a60  mov     rcx, rsi; Irp
0x140001a63  call    cs:__imp_IoReuseIrp
0x140001a6a  nop     dword ptr [rax+rax+00h]
0x140001a6f  mov     rax, [r15+90h]
0x140001a76  mov     r9, rbx; Context
0x140001a79  mov     rcx, [rsi+0B8h]
0x140001a80  mov     r8, r12; CompletionRoutine
0x140001a83  mov     [rsi+8], rax
0x140001a87  mov     rdx, rsi; Irp
0x140001a8a  movzx   eax, word ptr [r15+0Ch]
0x140001a8f  mov     [rsp+88h+InvokeOnCancel], 1; InvokeOnCancel
0x140001a94  mov     [rcx-40h], eax
0x140001a97  mov     dword ptr [rcx-38h], 0
0x140001a9e  mov     qword ptr [rcx-30h], 0
0x140001aa6  mov     byte ptr [rcx-48h], 3
0x140001aaa  mov     rax, [rbx+80h]
0x140001ab1  mov     [rcx-18h], rax
0x140001ab5  mov     rcx, [rbx]; DeviceObject
0x140001ab8  mov     [rsp+88h+InvokeOnError], 1; InvokeOnError
0x140001abd  mov     [rsp+88h+InvokeOnSuccess], 1; InvokeOnSuccess
0x140001ac2  call    cs:__imp_IoSetCompletionRoutineEx
0x140001ac9  nop     dword ptr [rax+rax+00h]
0x140001ace  test    eax, eax
0x140001ad0  js      loc_140001BBC
0x140001ad6  lea     rcx, [rbx+40h]; Event
0x140001ada  call    cs:__imp_KeResetEvent
0x140001ae1  nop     dword ptr [rax+rax+00h]
0x140001ae6  cmp     dword ptr [rbx+1Ch], 0
0x140001aea  jz      loc_140001C15
0x140001af0  cmp     byte ptr [rbx+59h], 1
0x140001af4  lea     r14, [rbx+59h]
0x140001af8  jz      loc_140001C15
0x140001afe  mov     rcx, [rbx+8]; DeviceObject
0x140001b02  mov     rdx, rsi; Irp
0x140001b05  call    cs:__imp_IofCallDriver
0x140001b0c  nop     dword ptr [rax+rax+00h]
0x140001b11  xor     r8d, r8d; Wait
0x140001b14  lea     rcx, [rbx+40h]; Event
0x140001b18  xor     edx, edx; Increment
0x140001b1a  mov     edi, eax
0x140001b1c  call    cs:__imp_KeSetEvent
0x140001b23  nop     dword ptr [rax+rax+00h]
0x140001b28  mov     ecx, 2
0x140001b2d  xchg    ecx, [rbx+20h]
0x140001b30  cmp     ecx, 3
0x140001b33  jz      loc_140001BD8
0x140001b39  lea     rsi, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140001b40  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140001b47  jnz     short loc_140001B90
0x140001b49  mov     eax, edi
0x140001b4b  add     rsp, 48h
0x140001b4f  pop     r15
0x140001b51  pop     r14
0x140001b53  pop     r13
0x140001b55  pop     r12
0x140001b57  pop     rdi
0x140001b58  pop     rsi
0x140001b59  pop     rbp
0x140001b5a  pop     rbx
0x140001b5b  retn
0x140001b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b64  cmp     word ptr [rcx+48h], 0
0x140001b69  jz      loc_140001A36
0x140001b6f  mov     rcx, [rcx+40h]
0x140001b73  mov     r9d, 0Fh
0x140001b79  mov     qword ptr [rsp+88h+InvokeOnSuccess], rdx
0x140001b7e  mov     r8d, 2
0x140001b84  mov     dl, 5
0x140001b86  call    WPP_RECORDER_SF_
0x140001b8b  jmp     loc_140001A36
0x140001b90  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b97  cmp     word ptr [rcx+48h], 0
0x140001b9c  jz      short loc_140001B49
0x140001b9e  mov     rcx, [rcx+40h]
0x140001ba2  mov     r9d, 13h
0x140001ba8  mov     r8d, 2
0x140001bae  mov     qword ptr [rsp+88h+InvokeOnSuccess], rsi
0x140001bb3  mov     dl, 5
0x140001bb5  call    WPP_RECORDER_SF_
0x140001bba  jmp     short loc_140001B49
0x140001bbc  mov     rax, [rsi+0B8h]
0x140001bc3  lea     r14, [rbx+59h]
0x140001bc7  mov     [rax-10h], r12
0x140001bcb  mov     [rax-8], rbx
0x140001bcf  mov     byte ptr [rax-45h], 0E0h
0x140001bd3  jmp     loc_140001AD6
0x140001bd8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140001bdf  jz      loc_140001A3E
0x140001be5  mov     rcx, cs:WPP_GLOBAL_Control
0x140001bec  cmp     word ptr [rcx+48h], 0
0x140001bf1  jz      loc_140001A3E
0x140001bf7  mov     rax, [rbx]
0x140001bfa  mov     r9d, 11h
0x140001c00  mov     rcx, [rcx+40h]
0x140001c04  mov     dl, 5
0x140001c06  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x140001c0b  call    WPP_RECORDER_SF_q
0x140001c10  jmp     loc_140001A3E
0x140001c15  mov     rdx, [rbx+68h]; Tag
0x140001c19  lea     rcx, [rbx+98h]; RemoveLock
0x140001c20  mov     r8d, 20h ; ' '; RemlockSize
0x140001c26  call    cs:__imp_IoReleaseRemoveLockEx
0x140001c2d  nop     dword ptr [rax+rax+00h]
0x140001c32  cmp     byte ptr [r14], 0
0x140001c36  mov     edi, 0C0000056h
0x140001c3b  mov     eax, 0C0000001h
0x140001c40  cmovz   edi, eax
0x140001c43  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140001c4a  jz      short loc_140001C6F
0x140001c4c  mov     eax, [rbx+1Ch]
0x140001c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c56  mov     [rsp+88h+var_50], edi
0x140001c5a  mov     dword ptr [rsp+88h+InvokeOnCancel], eax
0x140001c5e  mov     rax, [rbx]
0x140001c61  mov     rcx, [rcx+40h]
0x140001c65  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x140001c6a  call    WPP_RECORDER_SF_qDd
0x140001c6f  xor     r8d, r8d; Wait
0x140001c72  lea     rcx, [rbx+40h]; Event
0x140001c76  xor     edx, edx; Increment
0x140001c78  call    cs:__imp_KeSetEvent
0x140001c7f  nop     dword ptr [rax+rax+00h]
0x140001c84  lea     rcx, [rbx+28h]; Event
0x140001c88  xor     r8d, r8d; Wait
0x140001c8b  xor     edx, edx; Increment
0x140001c8d  call    cs:__imp_KeSetEvent
0x140001c94  nop     dword ptr [rax+rax+00h]
0x140001c99  jmp     loc_140001B39
0x140001c9e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140001ca5  jz      short loc_140001CE4
0x140001ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cae  mov     r9d, 12h
0x140001cb4  mov     rax, [rbx]
0x140001cb7  mov     r8d, 2
0x140001cbd  mov     [rsp+88h+var_50], edi
0x140001cc1  mov     dl, 3
0x140001cc3  mov     qword ptr [rsp+88h+InvokeOnCancel], rsi
0x140001cc8  lea     rsi, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140001ccf  mov     rcx, [rcx+40h]
0x140001cd3  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x140001cd8  mov     qword ptr [rsp+88h+InvokeOnSuccess], rsi
0x140001cdd  call    WPP_RECORDER_SF_qqd
0x140001ce2  jmp     short loc_140001CEB
0x140001ce4  lea     rsi, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140001ceb  lea     rcx, [rbx+28h]; Event
0x140001cef  xor     r8d, r8d; Wait
0x140001cf2  xor     edx, edx; Increment
0x140001cf4  call    cs:__imp_KeSetEvent
0x140001cfb  nop     dword ptr [rax+rax+00h]
0x140001d00  mov     rdx, [rbx+68h]; Tag
0x140001d04  lea     rcx, [rbx+98h]; RemoveLock
0x140001d0b  mov     r8d, 20h ; ' '; RemlockSize
0x140001d11  call    cs:__imp_IoReleaseRemoveLockEx
0x140001d18  nop     dword ptr [rax+rax+00h]
0x140001d1d  jmp     loc_140001B40
```
