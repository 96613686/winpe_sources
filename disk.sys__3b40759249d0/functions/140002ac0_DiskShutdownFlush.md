# DiskShutdownFlush

- ea: `0x140002ac0`
- end: `0x140003193`
- name: `DiskShutdownFlush`
- size: `1747`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001150`
- `0x1400022b0`
- `0x140002ac0`
- `0x140004078`
- `0x1400041c0`
- `0x1400042c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002c6f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002c6f`
- `ntoskrnl!IofCallDriver` at `0x140003169`
- `ntoskrnl!IofCallDriver` at `0x140003169`
- `ntoskrnl!IoAllocateIrp` at `0x140002d6d`
- `ntoskrnl!IoAllocateIrp` at `0x140002d6d`
- `ntoskrnl!ExAllocatePool2` at `0x140002e27`
- `ntoskrnl!ExAllocatePool2` at `0x140002e27`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002be6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002d31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002d96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002be6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002d31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002d96`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002eab`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002eab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002cae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002b48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002cae`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140002b16`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140002e48`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140002f6f`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140002b16`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140002e48`
- `CLASSPNP!ClassReleaseRemoveLock` at `0x140002f6f`
- `CLASSPNP!ClassCompleteRequest` at `0x140002b2b`
- `CLASSPNP!ClassCompleteRequest` at `0x140002e5d`
- `CLASSPNP!ClassCompleteRequest` at `0x140002f84`
- `CLASSPNP!ClassCompleteRequest` at `0x140002b2b`
- `CLASSPNP!ClassCompleteRequest` at `0x140002e5d`
- `CLASSPNP!ClassCompleteRequest` at `0x140002f84`
- `CLASSPNP!ClassIoComplete` at `0x140003135`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000300f`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x1400030ab`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000300f`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x1400030ab`

## pseudocode

```c
__int64 __fastcall DiskShutdownFlush(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  _QWORD *DeviceExtension; // rax
  __int64 v6; // r14
  __int64 v7; // rsi
  KSPIN_LOCK *v9; // r14
  __int64 v10; // r8
  KIRQL v11; // r12
  struct _LIST_ENTRY *v12; // rsi
  struct _LIST_ENTRY *Blink; // rcx
  bool v14; // bl
  KIRQL v15; // r8
  __int64 v16; // rbx
  _QWORD **v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  bool v21; // zf
  PIRP v22; // rax
  __int64 v23; // rax
  unsigned int v24; // esi
  bool v25; // r13
  __int64 Pool2; // rbx
  __int16 IoPriorityHint; // ax
  __int64 v28; // rax
  _BYTE *v29; // r12
  __int64 v30; // rax
  __int64 v31; // rsi
  _BYTE *v32; // rcx
  unsigned int v33; // eax
  __int64 v34; // r8
  unsigned int v35; // eax
  __int64 v36; // r8
  struct _IO_STACK_LOCATION *v37; // rdx
  struct _IO_STACK_LOCATION *v38; // rax
  _BYTE *v39; // [rsp+70h] [rbp+8h]
  struct _IO_STACK_LOCATION *v40; // [rsp+78h] [rbp+10h]
  _QWORD *v41; // [rsp+80h] [rbp+18h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = DeviceObject->DeviceExtension;
  v41 = DeviceExtension;
  v40 = CurrentStackLocation;
  v6 = DeviceExtension[3];
  if ( CurrentStackLocation->MajorFunction != 9 )
  {
    v23 = *(_QWORD *)(v6 + 528);
    if ( *(_BYTE *)(v23 + 30) == 1 )
    {
      v24 = 308;
      if ( *(_BYTE *)(v23 + 31) != 1 )
        v24 = 184;
      v25 = *(_BYTE *)(v23 + 31) == 1;
    }
    else
    {
      v25 = 0;
      v24 = 88;
    }
    Pool2 = ExAllocatePool2(64, v24, 1396990803);
    if ( !Pool2 )
      goto LABEL_43;
    if ( *(_BYTE *)(*(_QWORD *)(v6 + 528) + 30LL) != 1 )
    {
      *(_WORD *)Pool2 = 88;
      v32 = (_BYTE *)(Pool2 + 72);
      v31 = 0;
      v29 = 0;
      *(_DWORD *)(Pool2 + 20) = 4 * *(_DWORD *)(v6 + 584);
      *(_WORD *)(Pool2 + 8) = 8447;
      *(_DWORD *)(Pool2 + 12) = *(_DWORD *)(v6 + 592);
      *(_BYTE *)(Pool2 + 2) = 0;
LABEL_52:
      v39 = v32;
      if ( (*(_WORD *)(v6 + 640) & 1) != 0 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v6 + 528) + 30LL) == 1 )
          v29[10] = 10;
        else
          *(_BYTE *)(Pool2 + 10) = 10;
        *v32 = 53;
        v33 = ClassSendSrbSynchronous(DeviceObject, (PSCSI_REQUEST_BLOCK)Pool2, 0, 0, 1u);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 23, v34, v33);
        }
      }
      if ( (DeviceObject->Characteristics & 1) != 0 )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v6 + 528) + 30LL) == 1 )
        {
          *(_BYTE *)(v31 + 3) = 0;
          v29[8] = 0;
          v29[10] = 6;
          *(_DWORD *)(v31 + 40) = *(_DWORD *)(v6 + 584);
        }
        else
        {
          *(_WORD *)(Pool2 + 3) = 0;
          *(_BYTE *)(Pool2 + 10) = 6;
          *(_DWORD *)(Pool2 + 20) = *(_DWORD *)(v6 + 584);
        }
        v39[4] &= ~1u;
        *v39 = 30;
        v35 = ClassSendSrbSynchronous(DeviceObject, (PSCSI_REQUEST_BLOCK)Pool2, 0, 0, 1u);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 24, v36, v35);
        }
      }
      if ( *(_BYTE *)(*(_QWORD *)(v6 + 528) + 30LL) == 1 )
      {
        *(_DWORD *)(v31 + 56) = 0;
        *(_DWORD *)(v31 + 120) = 0;
        *(_DWORD *)(v31 + 20) = 7;
        *(_QWORD *)(v31 + 80) = Irp;
        *(_DWORD *)(v31 + 16) = 144;
        *(_BYTE *)(v31 + 3) = 0;
      }
      else
      {
        *(_BYTE *)(Pool2 + 10) = 0;
        *(_WORD *)(Pool2 + 2) = 7;
        *(_QWORD *)(Pool2 + 48) = Irp;
      }
      v40->Parameters.CreatePipe.Parameters = 0;
      v37 = Irp->Tail.Overlay.CurrentStackLocation;
      v37[-1].CompletionRoutine = ClassIoComplete;
      v37[-1].Context = (PVOID)Pool2;
      v37[-1].Control = -32;
      v38 = Irp->Tail.Overlay.CurrentStackLocation;
      v38[-1].MajorFunction = 15;
      v38[-1].Parameters.WMI.ProviderId = Pool2;
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      IofCallDriver((PDEVICE_OBJECT)v41[2], Irp);
      return 259;
    }
    *(_WORD *)Pool2 = 8;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_BYTE *)(Pool2 + 2) = 40;
    *(_DWORD *)(Pool2 + 8) = 1397899864;
    *(_DWORD *)(Pool2 + 16) = v24;
    *(_DWORD *)(Pool2 + 20) = 0;
    IoPriorityHint = IoGetIoPriorityHint(Irp);
    *(_DWORD *)(Pool2 + 52) = 128;
    *(_WORD *)(Pool2 + 36) = IoPriorityHint;
    *(_DWORD *)(Pool2 + 56) = 1;
    *(_DWORD *)(Pool2 + 40) = 4 * *(_DWORD *)(v6 + 584);
    *(_DWORD *)(Pool2 + 32) = 255;
    *(_WORD *)(Pool2 + 38) = 32;
    *(_DWORD *)(Pool2 + 24) = *(_DWORD *)(v6 + 592);
    *(_WORD *)(Pool2 + 128) = 1;
    *(_DWORD *)(Pool2 + 132) = 4;
    v28 = 4 * (unsigned int)v25 + 144;
    *(_DWORD *)(Pool2 + 120) = v28;
    if ( v28 + 40 <= (unsigned __int64)*(unsigned int *)(Pool2 + 16) )
    {
      *(_DWORD *)(v28 + Pool2) = 64;
      v29 = (_BYTE *)(v28 + Pool2);
      *(_DWORD *)(v28 + Pool2 + 4) = 32;
      if ( !v25 )
      {
LABEL_49:
        v31 = Pool2;
        v32 = v29 + 24;
        goto LABEL_52;
      }
      v30 = (unsigned int)(*(_DWORD *)(Pool2 + 120) + 40);
      *(_DWORD *)(Pool2 + 124) = v30;
      if ( v30 + 112 <= (unsigned __int64)*(unsigned int *)(Pool2 + 16) )
      {
        *(_DWORD *)((unsigned int)v30 + Pool2) = 67;
        *(_DWORD *)((unsigned int)v30 + Pool2 + 4) = 100;
        goto LABEL_49;
      }
    }
    Irp->IoStatus.Status = -1073741595;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    return 3221225701LL;
  }
  v7 = DeviceExtension[12];
  if ( (*(_WORD *)(v6 + 640) & 0x10) != 0 )
  {
    Irp->IoStatus.Status = 0;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    return 0;
  }
  v9 = (KSPIN_LOCK *)(v7 + 472);
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 472));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 20, v10, Irp, CurrentStackLocation->Flags);
  }
  if ( *(_QWORD *)(v7 + 128) )
  {
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    if ( *(_QWORD *)(v7 + 152) )
    {
      v12 = (struct _LIST_ENTRY *)(v7 + 136);
      Blink = v12->Blink;
      if ( Blink->Flink != v12 )
LABEL_27:
        __fastfail(3u);
      Irp->Tail.Overlay.ListEntry.Blink = Blink;
      Irp->Tail.Overlay.ListEntry.Flink = v12;
      Blink->Flink = &Irp->Tail.Overlay.ListEntry;
      v12->Blink = &Irp->Tail.Overlay.ListEntry;
      KeReleaseSpinLock(v9, v11);
    }
    else
    {
      *(_QWORD *)(v7 + 152) = Irp;
      v14 = (CurrentStackLocation->Flags & 1) == 0;
      *(_BYTE *)(v7 + 512) = v14;
      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 472), v11);
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
        }
        KeWaitForSingleObject((PVOID)(v7 + 480), Executive, 0, 0, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
        }
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 472));
        v16 = v7 + 112;
        v17 = (_QWORD **)(v7 + 136);
        while ( 1 )
        {
          v18 = *v17;
          if ( *v17 == v17 )
            break;
          if ( (_QWORD **)v18[1] != v17 )
            goto LABEL_27;
          v19 = (_QWORD *)*v18;
          if ( *(_QWORD **)(*v18 + 8LL) != v18 )
            goto LABEL_27;
          *v17 = v19;
          v19[1] = v17;
          v20 = *(_QWORD **)(v7 + 120);
          if ( *v20 != v16 )
            goto LABEL_27;
          *v18 = v16;
          v18[1] = v20;
          *v20 = v18;
          *(_QWORD *)(v7 + 120) = v18;
        }
        *(_QWORD *)(v7 + 128) = *(_QWORD *)(v7 + 152);
        *(_QWORD *)(v7 + 152) = 0;
        *(_BYTE *)(v7 + 512) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 472), v15);
        DiskFlushDispatch(DeviceObject);
      }
    }
    return 259;
  }
  v21 = *(_QWORD *)(v7 + 504) == 0;
  *(_QWORD *)(v7 + 128) = Irp;
  if ( v21 && (CurrentStackLocation->Flags & 1) != 0 )
  {
    v22 = IoAllocateIrp(DeviceObject->StackSize + 3, 0);
    *(_QWORD *)(v7 + 504) = v22;
    if ( !v22 )
      *(_QWORD *)(v7 + 128) = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 472), v11);
  if ( (CurrentStackLocation->Flags & 1) == 0 )
  {
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    DiskFlushDispatch(DeviceObject);
    return 259;
  }
  if ( !*(_QWORD *)(v7 + 504) )
  {
LABEL_43:
    Irp->IoStatus.Status = -1073741670;
    ClassReleaseRemoveLock(DeviceObject, Irp);
    ClassCompleteRequest(DeviceObject, Irp, 0);
    return 3221225626LL;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  DiskFlushDispatchAsync(DeviceObject);
  return 259;
}

```

## disassembly

```asm
0x140002ac0  mov     [rsp+arg_18], rbx
0x140002ac5  push    rbp
0x140002ac6  push    rsi
0x140002ac7  push    rdi
0x140002ac8  push    r12
0x140002aca  push    r13
0x140002acc  push    r14
0x140002ace  push    r15
0x140002ad0  sub     rsp, 30h
0x140002ad4  mov     rbx, [rdx+0B8h]
0x140002adb  mov     rdi, rdx
0x140002ade  mov     rax, [rcx+40h]
0x140002ae2  mov     rbp, rcx
0x140002ae5  mov     [rsp+68h+arg_10], rax
0x140002aed  mov     [rsp+68h+arg_8], rbx
0x140002af2  cmp     byte ptr [rbx], 9
0x140002af5  mov     r14, [rax+18h]
0x140002af9  jnz     loc_140002DEE
0x140002aff  mov     rsi, [rax+60h]
0x140002b03  movzx   eax, word ptr [r14+280h]
0x140002b0b  test    al, 10h
0x140002b0d  jz      short loc_140002B3E
0x140002b0f  xor     r15d, r15d
0x140002b12  mov     [rdx+30h], r15d
0x140002b16  call    cs:__imp_ClassReleaseRemoveLock
0x140002b1d  nop     dword ptr [rax+rax+00h]
0x140002b22  xor     r8d, r8d; PriorityBoost
0x140002b25  mov     rdx, rdi; Irp
0x140002b28  mov     rcx, rbp; DeviceObject
0x140002b2b  call    cs:__imp_ClassCompleteRequest
0x140002b32  nop     dword ptr [rax+rax+00h]
0x140002b37  xor     eax, eax
0x140002b39  jmp     loc_14000317A
0x140002b3e  lea     r14, [rsi+1D8h]
0x140002b45  mov     rcx, r14; SpinLock
0x140002b48  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002b4f  nop     dword ptr [rax+rax+00h]
0x140002b54  movzx   r12d, al
0x140002b58  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b5f  lea     r13, WPP_GLOBAL_Control
0x140002b66  cmp     rcx, r13
0x140002b69  jz      short loc_140002B93
0x140002b6b  test    dword ptr [rcx+2Ch], 20000h
0x140002b72  jz      short loc_140002B93
0x140002b74  cmp     byte ptr [rcx+29h], 5
0x140002b78  jb      short loc_140002B93
0x140002b7a  movzx   eax, byte ptr [rbx+2]
0x140002b7e  mov     edx, 14h
0x140002b83  mov     rcx, [rcx+18h]
0x140002b87  mov     r9, rdi
0x140002b8a  mov     dword ptr [rsp+68h+Timeout], eax
0x140002b8e  call    WPP_SF_qD
0x140002b93  cmp     qword ptr [rsi+80h], 0
0x140002b9b  jz      loc_140002D4D
0x140002ba1  mov     rax, [rdi+0B8h]
0x140002ba8  or      byte ptr [rax+3], 1
0x140002bac  cmp     qword ptr [rsi+98h], 0
0x140002bb4  jz      short loc_140002BF7
0x140002bb6  add     rsi, 88h
0x140002bbd  mov     rcx, [rsi+8]
0x140002bc1  cmp     [rcx], rsi
0x140002bc4  jnz     loc_140002D07
0x140002bca  lea     rax, [rdi+0A8h]
0x140002bd1  movzx   edx, r12b; NewIrql
0x140002bd5  mov     [rax+8], rcx
0x140002bd9  mov     [rax], rsi
0x140002bdc  mov     [rcx], rax
0x140002bdf  mov     rcx, r14; SpinLock
0x140002be2  mov     [rsi+8], rax
0x140002be6  call    cs:__imp_KeReleaseSpinLock
0x140002bed  nop     dword ptr [rax+rax+00h]
0x140002bf2  jmp     loc_140003175
0x140002bf7  mov     [rsi+98h], rdi
0x140002bfe  movzx   edx, r12b; NewIrql
0x140002c02  movzx   ebx, byte ptr [rbx+2]
0x140002c06  mov     rcx, r14; SpinLock
0x140002c09  not     bl
0x140002c0b  and     bl, 1
0x140002c0e  mov     [rsi+200h], bl
0x140002c14  call    cs:__imp_KeReleaseSpinLock
0x140002c1b  nop     dword ptr [rax+rax+00h]
0x140002c20  test    bl, bl
0x140002c22  jz      loc_140003175
0x140002c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c2f  cmp     rcx, r13
0x140002c32  jz      short loc_140002C58
0x140002c34  test    dword ptr [rcx+2Ch], 20000h
0x140002c3b  jz      short loc_140002C58
0x140002c3d  cmp     byte ptr [rcx+29h], 5
0x140002c41  jb      short loc_140002C58
0x140002c43  mov     rcx, [rcx+18h]
0x140002c47  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140002c4e  mov     edx, 15h
0x140002c53  call    WPP_SF_
0x140002c58  xor     r15d, r15d
0x140002c5b  lea     rcx, [rsi+1E0h]; Object
0x140002c62  xor     r9d, r9d; Alertable
0x140002c65  mov     [rsp+68h+Timeout], r15; Timeout
0x140002c6a  xor     r8d, r8d; WaitMode
0x140002c6d  xor     edx, edx; WaitReason
0x140002c6f  call    cs:__imp_KeWaitForSingleObject
0x140002c76  nop     dword ptr [rax+rax+00h]
0x140002c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c82  cmp     rcx, r13
0x140002c85  jz      short loc_140002CAB
0x140002c87  test    dword ptr [rcx+2Ch], 20000h
0x140002c8e  jz      short loc_140002CAB
0x140002c90  cmp     byte ptr [rcx+29h], 5
0x140002c94  jb      short loc_140002CAB
0x140002c96  mov     rcx, [rcx+18h]
0x140002c9a  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140002ca1  mov     edx, 16h
0x140002ca6  call    WPP_SF_
0x140002cab  mov     rcx, r14; SpinLock
0x140002cae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002cb5  nop     dword ptr [rax+rax+00h]
0x140002cba  movzx   r8d, al
0x140002cbe  lea     rbx, [rsi+70h]
0x140002cc2  lea     rdx, [rsi+88h]
0x140002cc9  nop     dword ptr [rax+00000000h]
0x140002cd0  mov     rcx, [rdx]
0x140002cd3  cmp     rcx, rdx
0x140002cd6  jz      short loc_140002D0E
0x140002cd8  cmp     [rcx+8], rdx
0x140002cdc  jnz     short loc_140002D07
0x140002cde  mov     rax, [rcx]
0x140002ce1  cmp     [rax+8], rcx
0x140002ce5  jnz     short loc_140002D07
0x140002ce7  mov     [rdx], rax
0x140002cea  mov     [rax+8], rdx
0x140002cee  mov     rax, [rbx+8]
0x140002cf2  cmp     [rax], rbx
0x140002cf5  jnz     short loc_140002D07
0x140002cf7  mov     [rcx], rbx
0x140002cfa  mov     [rcx+8], rax
0x140002cfe  mov     [rax], rcx
0x140002d01  mov     [rbx+8], rcx
0x140002d05  jmp     short loc_140002CD0
0x140002d07  mov     ecx, 3
0x140002d0c  int     29h; Win8: RtlFailFast(ecx)
0x140002d0e  mov     rax, [rsi+98h]
0x140002d15  movzx   edx, r8b; NewIrql
0x140002d19  mov     rcx, r14; SpinLock
0x140002d1c  mov     [rsi+80h], rax
0x140002d23  mov     [rsi+98h], r15
0x140002d2a  mov     [rsi+200h], r15b
0x140002d31  call    cs:__imp_KeReleaseSpinLock
0x140002d38  nop     dword ptr [rax+rax+00h]
0x140002d3d  mov     rdx, rbx
0x140002d40  mov     rcx, rbp; DeviceObject
0x140002d43  call    DiskFlushDispatch
0x140002d48  jmp     loc_140003175
0x140002d4d  cmp     qword ptr [rsi+1F8h], 0
0x140002d55  mov     [rsi+80h], rdi
0x140002d5c  jnz     short loc_140002D8F
0x140002d5e  test    byte ptr [rbx+2], 1
0x140002d62  jz      short loc_140002D8F
0x140002d64  movzx   ecx, byte ptr [rbp+4Ch]
0x140002d68  xor     edx, edx; ChargeQuota
0x140002d6a  add     cl, 3; StackSize
0x140002d6d  call    cs:__imp_IoAllocateIrp
0x140002d74  nop     dword ptr [rax+rax+00h]
0x140002d79  mov     [rsi+1F8h], rax
0x140002d80  test    rax, rax
0x140002d83  jnz     short loc_140002D8F
0x140002d85  xor     r15d, r15d
0x140002d88  mov     [rsi+80h], r15
0x140002d8f  movzx   edx, r12b; NewIrql
0x140002d93  mov     rcx, r14; SpinLock
0x140002d96  call    cs:__imp_KeReleaseSpinLock
0x140002d9d  nop     dword ptr [rax+rax+00h]
0x140002da2  test    byte ptr [rbx+2], 1
0x140002da6  jz      short loc_140002DD2
0x140002da8  cmp     qword ptr [rsi+1F8h], 0
0x140002db0  jz      loc_140002E3B
0x140002db6  mov     rax, [rdi+0B8h]
0x140002dbd  lea     rdx, [rsi+70h]
0x140002dc1  mov     rcx, rbp; DeviceObject
0x140002dc4  or      byte ptr [rax+3], 1
0x140002dc8  call    DiskFlushDispatchAsync
0x140002dcd  jmp     loc_140003175
0x140002dd2  mov     rax, [rdi+0B8h]
0x140002dd9  lea     rdx, [rsi+70h]
0x140002ddd  mov     rcx, rbp; DeviceObject
0x140002de0  or      byte ptr [rax+3], 1
0x140002de4  call    DiskFlushDispatch
0x140002de9  jmp     loc_140003175
0x140002dee  mov     rax, [r14+210h]
0x140002df5  cmp     byte ptr [rax+1Eh], 1
0x140002df9  jnz     short loc_140002E12
0x140002dfb  cmp     byte ptr [rax+1Fh], 1
0x140002dff  mov     esi, 134h
0x140002e04  mov     ecx, 0B8h
0x140002e09  cmovnz  esi, ecx
0x140002e0c  setz    r13b
0x140002e10  jmp     short loc_140002E1A
0x140002e12  xor     r13b, r13b
0x140002e15  mov     esi, 58h ; 'X'
0x140002e1a  mov     edx, esi
0x140002e1c  mov     ecx, 40h ; '@'
0x140002e21  mov     r8d, 53446353h
0x140002e27  call    cs:__imp_ExAllocatePool2
0x140002e2e  nop     dword ptr [rax+rax+00h]
0x140002e33  mov     rbx, rax
0x140002e36  test    rax, rax
0x140002e39  jnz     short loc_140002E73
0x140002e3b  mov     rdx, rdi; Tag
0x140002e3e  mov     dword ptr [rdi+30h], 0C000009Ah
0x140002e45  mov     rcx, rbp; DeviceObject
0x140002e48  call    cs:__imp_ClassReleaseRemoveLock
0x140002e4f  nop     dword ptr [rax+rax+00h]
0x140002e54  xor     r8d, r8d; PriorityBoost
0x140002e57  mov     rdx, rdi; Irp
0x140002e5a  mov     rcx, rbp; DeviceObject
0x140002e5d  call    cs:__imp_ClassCompleteRequest
0x140002e64  nop     dword ptr [rax+rax+00h]
0x140002e69  mov     eax, 0C000009Ah
0x140002e6e  jmp     loc_14000317A
0x140002e73  mov     rax, [r14+210h]
0x140002e7a  xor     r15d, r15d
0x140002e7d  cmp     byte ptr [rax+1Eh], 1
0x140002e81  jnz     loc_140002F9A
0x140002e87  mov     r12d, 1
0x140002e8d  mov     word ptr [rbx], 8
0x140002e92  mov     rcx, rdi; Irp
0x140002e95  mov     [rbx+0Ch], r12d
0x140002e99  mov     byte ptr [rbx+2], 28h ; '('
0x140002e9d  mov     dword ptr [rbx+8], 53524258h
0x140002ea4  mov     [rbx+10h], esi
0x140002ea7  mov     [rbx+14h], r15d
0x140002eab  call    cs:__imp_IoGetIoPriorityHint
0x140002eb2  nop     dword ptr [rax+rax+00h]
0x140002eb7  mov     dword ptr [rbx+34h], 80h
0x140002ebe  mov     r8d, 20h ; ' '
0x140002ec4  mov     [rbx+24h], ax
0x140002ec8  mov     [rbx+38h], r12d
0x140002ecc  mov     eax, [r14+248h]
0x140002ed3  shl     eax, 2
0x140002ed6  mov     [rbx+28h], eax
0x140002ed9  mov     dword ptr [rbx+20h], 0FFh
0x140002ee0  mov     [rbx+26h], r8w
0x140002ee5  mov     eax, [r14+250h]
0x140002eec  mov     [rbx+18h], eax
0x140002eef  movzx   eax, r13b
0x140002ef3  mov     [rbx+80h], r12w
0x140002efb  mov     dword ptr [rbx+84h], 4
0x140002f05  lea     eax, ds:90h[rax*4]
0x140002f0c  lea     rcx, [rax+28h]
0x140002f10  mov     [rbx+78h], eax
0x140002f13  mov     edx, eax
0x140002f15  mov     eax, [rbx+10h]
0x140002f18  cmp     rcx, rax
0x140002f1b  ja      short loc_140002F62
0x140002f1d  mov     dword ptr [rdx+rbx], 40h ; '@'
0x140002f24  lea     r12, [rdx+rbx]
0x140002f28  mov     [r12+4], r8d
0x140002f2d  test    r13b, r13b
0x140002f30  jz      short loc_140002F58
0x140002f32  mov     eax, [rbx+78h]
0x140002f35  add     eax, 28h ; '('
0x140002f38  mov     [rbx+7Ch], eax
0x140002f3b  mov     edx, eax
0x140002f3d  lea     rcx, [rax+70h]
0x140002f41  mov     eax, [rbx+10h]
0x140002f44  cmp     rcx, rax
0x140002f47  ja      short loc_140002F62
0x140002f49  mov     dword ptr [rdx+rbx], 43h ; 'C'
0x140002f50  mov     dword ptr [rdx+rbx+4], 64h ; 'd'
0x140002f58  mov     rsi, rbx
0x140002f5b  lea     rcx, [r12+18h]
0x140002f60  jmp     short loc_140002FCA
0x140002f62  mov     rdx, rdi; Tag
0x140002f65  mov     dword ptr [rdi+30h], 0C00000E5h
0x140002f6c  mov     rcx, rbp; DeviceObject
0x140002f6f  call    cs:__imp_ClassReleaseRemoveLock
0x140002f76  nop     dword ptr [rax+rax+00h]
0x140002f7b  xor     r8d, r8d; PriorityBoost
0x140002f7e  mov     rdx, rdi; Irp
0x140002f81  mov     rcx, rbp; DeviceObject
0x140002f84  call    cs:__imp_ClassCompleteRequest
0x140002f8b  nop     dword ptr [rax+rax+00h]
0x140002f90  mov     eax, 0C00000E5h
0x140002f95  jmp     loc_14000317A
0x140002f9a  mov     word ptr [rbx], 58h ; 'X'
0x140002f9f  lea     rcx, [rbx+48h]
0x140002fa3  mov     eax, [r14+248h]
0x140002faa  mov     rsi, r15
0x140002fad  shl     eax, 2
0x140002fb0  mov     r12, r15
0x140002fb3  mov     [rbx+14h], eax
0x140002fb6  mov     word ptr [rbx+8], 20FFh
0x140002fbc  mov     eax, [r14+250h]
0x140002fc3  mov     [rbx+0Ch], eax
0x140002fc6  mov     [rbx+2], sil
0x140002fca  movzx   eax, word ptr [r14+280h]
0x140002fd2  lea     r13, WPP_GLOBAL_Control
0x140002fd9  mov     [rsp+68h+arg_0], rcx
0x140002fde  test    al, 1
0x140002fe0  jz      short loc_140003046
0x140002fe2  mov     rax, [r14+210h]
  ... truncated ...
```
