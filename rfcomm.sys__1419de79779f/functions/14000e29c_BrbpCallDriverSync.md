# BrbpCallDriverSync

- ea: `0x14000e29c`
- end: `0x14000e4da`
- name: `BrbpCallDriverSync`
- size: `574`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002ec8`
- `0x14000d740`
- `0x14000d83c`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004e58`
- `0x14000e29c`
- `0x14000f4ec`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e490`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e490`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000e2d9`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000e2d9`
- `ntoskrnl!IofCallDriver` at `0x14000e3a8`
- `ntoskrnl!IofCallDriver` at `0x14000e3a8`
- `ntoskrnl!KeInitializeEvent` at `0x14000e307`
- `ntoskrnl!KeInitializeEvent` at `0x14000e307`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e3cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e404`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e3cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e404`
- `ntoskrnl!IoFreeIrp` at `0x14000e477`
- `ntoskrnl!IoFreeIrp` at `0x14000e477`
- `ntoskrnl!IoAllocateIrp` at `0x14000e31c`
- `ntoskrnl!IoAllocateIrp` at `0x14000e31c`
- `ntoskrnl!IoCancelIrp` at `0x14000e3e2`
- `ntoskrnl!IoCancelIrp` at `0x14000e3e2`

## string_xrefs

- `0x14000e2b9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbpCallDriverSync(__int64 a1, unsigned __int64 a2)
{
  int v4; // edx
  NTSTATUS v5; // edi
  PIRP Irp; // rax
  int v7; // edx
  IRP *v8; // rbx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v10; // rax
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int Status; // edx
  int RemlockSize; // [rsp+20h] [rbp-88h]
  struct _KEVENT Event; // [rsp+50h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  v5 = IoAcquireRemoveLockEx(
         (PIO_REMOVE_LOCK)(a1 + 40),
         (PVOID)a2,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c",
         0x163u,
         0x20u);
  if ( v5 >= 0 )
  {
    KeInitializeEvent(&Event, NotificationEvent, 0);
    Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 88) + 76LL), 0);
    v8 = Irp;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        3,
        21,
        (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
        a2,
        (char)Irp);
    if ( v8 )
    {
      CurrentStackLocation = v8->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].MajorFunction = 15;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 4259843;
      CurrentStackLocation[-1].Parameters.WMI.ProviderId = a2;
      v10 = v8->Tail.Overlay.CurrentStackLocation;
      v10[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ForwardAndWaitComplete;
      v10[-1].Context = &Event;
      v10[-1].Control = -32;
      IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 88), v8);
      if ( KeWaitForSingleObject(&Event, Suspended, 0, 0, 0) == 258 )
      {
        IoCancelIrp(v8);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            2,
            22,
            (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
      }
      Status = v8->IoStatus.Status;
      if ( Status && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qddh(
          WPP_GLOBAL_Control->DeviceExtension,
          Status,
          v11,
          v12,
          RemlockSize,
          (char)v8,
          Status,
          *(_DWORD *)(a2 + 28),
          *(_BYTE *)(a2 + 32));
      v5 = v8->IoStatus.Status;
      IoFreeIrp(v8);
    }
    else
    {
      v5 = -1073741670;
    }
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 40), (PVOID)a2, 0x20u);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      3,
      24,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000e29c  push    rbx
0x14000e29e  push    rbp
0x14000e29f  push    rsi
0x14000e2a0  push    rdi
0x14000e2a1  push    r12
0x14000e2a3  push    r14
0x14000e2a5  push    r15
0x14000e2a7  sub     rsp, 70h
0x14000e2ab  mov     rbp, rcx
0x14000e2ae  mov     [rsp+0A8h+RemlockSize], 20h ; ' '; RemlockSize
0x14000e2b6  xorps   xmm0, xmm0
0x14000e2b9  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000e2c0  xor     eax, eax
0x14000e2c2  add     rcx, 28h ; '('; RemoveLock
0x14000e2c6  mov     r9d, 163h; Line
0x14000e2cc  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14000e2d1  movups  xmmword ptr [rsp+0A8h+Event.Header.___u0], xmm0
0x14000e2d6  mov     rsi, rdx
0x14000e2d9  call    cs:__imp_IoAcquireRemoveLockEx
0x14000e2e0  nop     dword ptr [rax+rax+00h]
0x14000e2e5  lea     r15, WPP_RECORDER_INITIALIZED
0x14000e2ec  mov     edi, eax
0x14000e2ee  lea     r12, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000e2f5  test    eax, eax
0x14000e2f7  js      loc_14000E49C
0x14000e2fd  xor     r8d, r8d; State
0x14000e300  lea     rcx, [rsp+0A8h+Event]; Event
0x14000e305  xor     edx, edx; Type
0x14000e307  call    cs:__imp_KeInitializeEvent
0x14000e30e  nop     dword ptr [rax+rax+00h]
0x14000e313  mov     rcx, [rbp+58h]
0x14000e317  xor     edx, edx; ChargeQuota
0x14000e319  mov     cl, [rcx+4Ch]; StackSize
0x14000e31c  call    cs:__imp_IoAllocateIrp
0x14000e323  nop     dword ptr [rax+rax+00h]
0x14000e328  mov     rbx, rax
0x14000e32b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e332  jz      short loc_14000E35D
0x14000e334  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e33b  mov     r9d, 15h
0x14000e341  mov     [rsp+0A8h+var_78], rax
0x14000e346  mov     [rsp+0A8h+var_80], rsi
0x14000e34b  mov     qword ptr [rsp+0A8h+RemlockSize], r12
0x14000e350  mov     rcx, [rcx+40h]
0x14000e354  lea     r8d, [r9-12h]
0x14000e358  call    WPP_RECORDER_SF_qq
0x14000e35d  test    rbx, rbx
0x14000e360  jnz     short loc_14000E36C
0x14000e362  mov     edi, 0C000009Ah
0x14000e367  jmp     loc_14000E483
0x14000e36c  mov     rax, [rbx+0B8h]
0x14000e373  lea     rcx, ForwardAndWaitComplete
0x14000e37a  mov     rdx, rbx; Irp
0x14000e37d  mov     byte ptr [rax-48h], 0Fh
0x14000e381  mov     dword ptr [rax-30h], 410003h
0x14000e388  mov     [rax-40h], rsi
0x14000e38c  mov     rax, [rbx+0B8h]
0x14000e393  mov     [rax-10h], rcx
0x14000e397  lea     rcx, [rsp+0A8h+Event]
0x14000e39c  mov     [rax-8], rcx
0x14000e3a0  mov     byte ptr [rax-45h], 0E0h
0x14000e3a4  mov     rcx, [rbp+58h]; DeviceObject
0x14000e3a8  call    cs:__imp_IofCallDriver
0x14000e3af  nop     dword ptr [rax+rax+00h]
0x14000e3b4  xor     r9d, r9d; Alertable
0x14000e3b7  mov     qword ptr [rsp+0A8h+RemlockSize], 0; Timeout
0x14000e3c0  xor     r8d, r8d; WaitMode
0x14000e3c3  lea     rcx, [rsp+0A8h+Event]; Object
0x14000e3c8  lea     edx, [r9+5]; WaitReason
0x14000e3cc  call    cs:__imp_KeWaitForSingleObject
0x14000e3d3  nop     dword ptr [rax+rax+00h]
0x14000e3d8  cmp     eax, 102h
0x14000e3dd  jnz     short loc_14000E438
0x14000e3df  mov     rcx, rbx; Irp
0x14000e3e2  call    cs:__imp_IoCancelIrp
0x14000e3e9  nop     dword ptr [rax+rax+00h]
0x14000e3ee  xor     r9d, r9d; Alertable
0x14000e3f1  mov     qword ptr [rsp+0A8h+RemlockSize], 0; Timeout
0x14000e3fa  xor     r8d, r8d; WaitMode
0x14000e3fd  lea     rcx, [rsp+0A8h+Event]; Object
0x14000e402  xor     edx, edx; WaitReason
0x14000e404  call    cs:__imp_KeWaitForSingleObject
0x14000e40b  nop     dword ptr [rax+rax+00h]
0x14000e410  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e417  jz      short loc_14000E438
0x14000e419  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e420  mov     r9d, 16h
0x14000e426  mov     qword ptr [rsp+0A8h+RemlockSize], r12
0x14000e42b  mov     rcx, [rcx+40h]
0x14000e42f  lea     r8d, [r9-14h]
0x14000e433  call    WPP_RECORDER_SF_
0x14000e438  mov     edx, [rbx+30h]
0x14000e43b  test    edx, edx
0x14000e43d  jz      short loc_14000E471
0x14000e43f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e446  jz      short loc_14000E471
0x14000e448  movzx   eax, byte ptr [rsi+20h]
0x14000e44c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e453  mov     [rsp+0A8h+var_68], ax
0x14000e458  mov     eax, [rsi+1Ch]
0x14000e45b  mov     [rsp+0A8h+var_70], eax
0x14000e45f  mov     rcx, [rcx+40h]
0x14000e463  mov     dword ptr [rsp+0A8h+var_78], edx
0x14000e467  mov     [rsp+0A8h+var_80], rbx
0x14000e46c  call    WPP_RECORDER_SF_qddh
0x14000e471  mov     edi, [rbx+30h]
0x14000e474  mov     rcx, rbx; Irp
0x14000e477  call    cs:__imp_IoFreeIrp
0x14000e47e  nop     dword ptr [rax+rax+00h]
0x14000e483  mov     r8d, 20h ; ' '; RemlockSize
0x14000e489  lea     rcx, [rbp+28h]; RemoveLock
0x14000e48d  mov     rdx, rsi; Tag
0x14000e490  call    cs:__imp_IoReleaseRemoveLockEx
0x14000e497  nop     dword ptr [rax+rax+00h]
0x14000e49c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e4a3  jz      short loc_14000E4C8
0x14000e4a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4ac  mov     r9d, 18h
0x14000e4b2  mov     dword ptr [rsp+0A8h+var_80], edi
0x14000e4b6  mov     qword ptr [rsp+0A8h+RemlockSize], r12
0x14000e4bb  mov     rcx, [rcx+40h]
0x14000e4bf  lea     r8d, [r9-15h]
0x14000e4c3  call    WPP_RECORDER_SF_d
0x14000e4c8  mov     eax, edi
0x14000e4ca  add     rsp, 70h
0x14000e4ce  pop     r15
0x14000e4d0  pop     r14
0x14000e4d2  pop     r12
0x14000e4d4  pop     rdi
0x14000e4d5  pop     rsi
0x14000e4d6  pop     rbp
0x14000e4d7  pop     rbx
0x14000e4d8  retn
```
