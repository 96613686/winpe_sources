# NatpRedirectCreateHandler

- ea: `0x14001a220`
- end: `0x14001a4b2`
- name: `NatpRedirectCreateHandler`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000218c`
- `0x14001a220`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001a2fa`
- `ntoskrnl!KeSetEvent` at `0x14001a2fa`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001a388`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001a3ee`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001a388`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001a3ee`
- `ntoskrnl!IoQueueWorkItem` at `0x14001a3b3`
- `ntoskrnl!IoQueueWorkItem` at `0x14001a440`
- `ntoskrnl!IoQueueWorkItem` at `0x14001a3b3`
- `ntoskrnl!IoQueueWorkItem` at `0x14001a440`
- `ntoskrnl!IoFreeWorkItem` at `0x14001a44e`
- `ntoskrnl!IoFreeWorkItem` at `0x14001a44e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a2d6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a32c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a2d6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a32c`
- `ntoskrnl!ExAllocatePool2` at `0x14001a410`
- `ntoskrnl!ExAllocatePool2` at `0x14001a410`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a3cd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a466`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a3cd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a466`

## pseudocode

```c
void __fastcall NatpRedirectCreateHandler(__int64 a1, __int64 a2, __int64 a3)
{
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  struct _KEVENT *v7; // rcx
  _QWORD *v8; // rcx
  bool v9; // zf
  struct _IO_WORKITEM *WorkItem; // rax
  struct _IO_WORKITEM *v11; // rdi
  struct _IO_WORKITEM **Pool2; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  if ( a3 )
  {
    KeAcquireSpinLockAtDpcLevel(&RedirectLock);
    v7 = *(struct _KEVENT **)(a3 + 144);
    *(_QWORD *)(a3 + 152) = a1;
    if ( v7 )
      KeSetEvent(v7, 0, 0);
    if ( *(_QWORD *)(a3 + 128) && (*(_DWORD *)(a3 + 112) & 0x10000020) == 0x20 )
    {
      KeAcquireSpinLockAtDpcLevel(&RedirectCompletionLock);
      *(_DWORD *)(a3 + 112) |= 0x40000000u;
      v8 = (_QWORD *)qword_140031FD8;
      if ( *(__int64 **)qword_140031FD8 != &RedirectCompletionList )
        __fastfail(3u);
      v9 = RedirectIoCompletionPending == 0;
      *(_QWORD *)(a3 + 16) = &RedirectCompletionList;
      *(_QWORD *)(a3 + 24) = v8;
      *v8 = a3 + 16;
      qword_140031FD8 = a3 + 16;
      if ( v9 )
      {
        WorkItem = RedirectIoWorkItem;
        if ( RedirectIoWorkItem
          || (WorkItem = IoAllocateWorkItem(NatDeviceObject), (RedirectIoWorkItem = WorkItem) != 0) )
        {
          IoQueueWorkItem(
            WorkItem,
            (PIO_WORKITEM_ROUTINE)NatpRedirectIoCompletionWorkerRoutine,
            DelayedWorkQueue,
            WorkItem);
          RedirectIoCompletionPending = 1;
        }
      }
      KeReleaseSpinLockFromDpcLevel(&RedirectCompletionLock);
    }
    *(_DWORD *)(a3 + 112) &= ~0x20000000u;
    if ( (*(_DWORD *)(a3 + 112) & 0x10000000) != 0 )
    {
      v11 = IoAllocateWorkItem(NatDeviceObject);
      if ( v11 )
      {
        Pool2 = (struct _IO_WORKITEM **)ExAllocatePool2(64, 16, 1383358798);
        if ( Pool2 )
        {
          *(_DWORD *)(a3 + 112) |= 0x8000000u;
          *Pool2 = v11;
          Pool2[1] = (struct _IO_WORKITEM *)a3;
          IoQueueWorkItem(v11, NatpRedirectDelayedCleanupWorkerRoutine, DelayedWorkQueue, Pool2);
        }
        else
        {
          IoFreeWorkItem(v11);
        }
      }
      *(_DWORD *)(a3 + 112) &= ~0x10000000u;
    }
    KeReleaseSpinLockFromDpcLevel(&RedirectLock);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v6 = 99;
      goto LABEL_35;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v6 = 98;
LABEL_35:
      WPP_SF_(v5->AttachedDevice, v6, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14001a220  mov     [rsp+arg_0], rbx
0x14001a225  mov     [rsp+arg_8], rdi
0x14001a22a  push    r14
0x14001a22c  sub     rsp, 20h
0x14001a230  mov     rbx, r8
0x14001a233  mov     rdi, rcx
0x14001a236  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a23d  lea     r14, WPP_GLOBAL_Control
0x14001a244  cmp     rcx, r14
0x14001a247  jz      short loc_14001A26B
0x14001a249  mov     eax, [rcx+2Ch]
0x14001a24c  test    al, 1
0x14001a24e  jz      short loc_14001A26B
0x14001a250  cmp     byte ptr [rcx+29h], 6
0x14001a254  jb      short loc_14001A26B
0x14001a256  mov     rcx, [rcx+18h]
0x14001a25a  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a261  mov     edx, 60h ; '`'
0x14001a266  call    WPP_SF_
0x14001a26b  test    rbx, rbx
0x14001a26e  jnz     short loc_14001A2CF
0x14001a270  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a277  cmp     rcx, r14
0x14001a27a  jz      loc_14001A4A0
0x14001a280  mov     eax, [rcx+2Ch]
0x14001a283  test    al, 1
0x14001a285  jz      short loc_14001A2A0
0x14001a287  cmp     byte ptr [rcx+29h], 2
0x14001a28b  jb      short loc_14001A2A0
0x14001a28d  mov     rcx, [rcx+18h]
0x14001a291  lea     edx, [rbx+61h]
0x14001a294  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a29b  call    WPP_SF_
0x14001a2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2a7  cmp     rcx, r14
0x14001a2aa  jz      loc_14001A4A0
0x14001a2b0  mov     eax, [rcx+2Ch]
0x14001a2b3  test    al, 1
0x14001a2b5  jz      loc_14001A4A0
0x14001a2bb  cmp     byte ptr [rcx+29h], 6
0x14001a2bf  jb      loc_14001A4A0
0x14001a2c5  mov     edx, 62h ; 'b'
0x14001a2ca  jmp     loc_14001A490
0x14001a2cf  lea     rcx, RedirectLock; SpinLock
0x14001a2d6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001a2dd  nop     dword ptr [rax+rax+00h]
0x14001a2e2  mov     rcx, [rbx+90h]; Event
0x14001a2e9  mov     [rbx+98h], rdi
0x14001a2f0  test    rcx, rcx
0x14001a2f3  jz      short loc_14001A306
0x14001a2f5  xor     r8d, r8d; Wait
0x14001a2f8  xor     edx, edx; Increment
0x14001a2fa  call    cs:__imp_KeSetEvent
0x14001a301  nop     dword ptr [rax+rax+00h]
0x14001a306  cmp     qword ptr [rbx+80h], 0
0x14001a30e  jz      loc_14001A3D9
0x14001a314  mov     eax, [rbx+70h]
0x14001a317  and     eax, 10000020h
0x14001a31c  cmp     eax, 20h ; ' '
0x14001a31f  jnz     loc_14001A3D9
0x14001a325  lea     rcx, RedirectCompletionLock; SpinLock
0x14001a32c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001a333  nop     dword ptr [rax+rax+00h]
0x14001a338  bts     dword ptr [rbx+70h], 1Eh
0x14001a33d  lea     rdx, RedirectCompletionList
0x14001a344  mov     rcx, cs:qword_140031FD8
0x14001a34b  cmp     [rcx], rdx
0x14001a34e  jz      short loc_14001A357
0x14001a350  mov     ecx, 3
0x14001a355  int     29h; Win8: RtlFailFast(ecx)
0x14001a357  cmp     cs:RedirectIoCompletionPending, 0
0x14001a35e  lea     rax, [rbx+10h]
0x14001a362  mov     [rax], rdx
0x14001a365  mov     [rax+8], rcx
0x14001a369  mov     [rcx], rax
0x14001a36c  mov     cs:qword_140031FD8, rax
0x14001a373  jnz     short loc_14001A3C6
0x14001a375  mov     rax, cs:RedirectIoWorkItem
0x14001a37c  test    rax, rax
0x14001a37f  jnz     short loc_14001A3A0
0x14001a381  mov     rcx, cs:NatDeviceObject; DeviceObject
0x14001a388  call    cs:__imp_IoAllocateWorkItem
0x14001a38f  nop     dword ptr [rax+rax+00h]
0x14001a394  mov     cs:RedirectIoWorkItem, rax
0x14001a39b  test    rax, rax
0x14001a39e  jz      short loc_14001A3C6
0x14001a3a0  mov     r9, rax; Context
0x14001a3a3  lea     rdx, NatpRedirectIoCompletionWorkerRoutine; WorkerRoutine
0x14001a3aa  mov     r8d, 1; QueueType
0x14001a3b0  mov     rcx, rax; IoWorkItem
0x14001a3b3  call    cs:__imp_IoQueueWorkItem
0x14001a3ba  nop     dword ptr [rax+rax+00h]
0x14001a3bf  mov     cs:RedirectIoCompletionPending, 1
0x14001a3c6  lea     rcx, RedirectCompletionLock; SpinLock
0x14001a3cd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001a3d4  nop     dword ptr [rax+rax+00h]
0x14001a3d9  btr     dword ptr [rbx+70h], 1Dh
0x14001a3de  test    dword ptr [rbx+70h], 10000000h
0x14001a3e5  jz      short loc_14001A45F
0x14001a3e7  mov     rcx, cs:NatDeviceObject; DeviceObject
0x14001a3ee  call    cs:__imp_IoAllocateWorkItem
0x14001a3f5  nop     dword ptr [rax+rax+00h]
0x14001a3fa  mov     rdi, rax
0x14001a3fd  test    rax, rax
0x14001a400  jz      short loc_14001A45A
0x14001a402  mov     edx, 10h
0x14001a407  mov     r8d, 5274614Eh
0x14001a40d  lea     ecx, [rdx+30h]
0x14001a410  call    cs:__imp_ExAllocatePool2
0x14001a417  nop     dword ptr [rax+rax+00h]
0x14001a41c  mov     rcx, rdi; IoWorkItem
0x14001a41f  test    rax, rax
0x14001a422  jz      short loc_14001A44E
0x14001a424  bts     dword ptr [rbx+70h], 1Bh
0x14001a429  lea     rdx, NatpRedirectDelayedCleanupWorkerRoutine; WorkerRoutine
0x14001a430  mov     r9, rax; Context
0x14001a433  mov     [rax], rdi
0x14001a436  mov     r8d, 1; QueueType
0x14001a43c  mov     [rax+8], rbx
0x14001a440  call    cs:__imp_IoQueueWorkItem
0x14001a447  nop     dword ptr [rax+rax+00h]
0x14001a44c  jmp     short loc_14001A45A
0x14001a44e  call    cs:__imp_IoFreeWorkItem
0x14001a455  nop     dword ptr [rax+rax+00h]
0x14001a45a  btr     dword ptr [rbx+70h], 1Ch
0x14001a45f  lea     rcx, RedirectLock; SpinLock
0x14001a466  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001a46d  nop     dword ptr [rax+rax+00h]
0x14001a472  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a479  cmp     rcx, r14
0x14001a47c  jz      short loc_14001A4A0
0x14001a47e  mov     eax, [rcx+2Ch]
0x14001a481  test    al, 1
0x14001a483  jz      short loc_14001A4A0
0x14001a485  cmp     byte ptr [rcx+29h], 6
0x14001a489  jb      short loc_14001A4A0
0x14001a48b  mov     edx, 63h ; 'c'
0x14001a490  mov     rcx, [rcx+18h]
0x14001a494  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a49b  call    WPP_SF_
0x14001a4a0  mov     rbx, [rsp+28h+arg_0]
0x14001a4a5  mov     rdi, [rsp+28h+arg_8]
0x14001a4aa  add     rsp, 20h
0x14001a4ae  pop     r14
0x14001a4b0  retn
```
