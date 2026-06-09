# I8xPowerUpToD0Complete

- ea: `0x1400080e0`
- end: `0x1400089fe`
- name: `I8xPowerUpToD0Complete`
- size: `2334`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400043e0`
- `0x140004530`
- `0x140007b10`
- `0x1400080e0`
- `0x14000c0a4`
- `0x14000cf48`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008179`
- `ntoskrnl!ExAllocatePool2` at `0x140008179`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000879d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400081a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000879d`
- `ntoskrnl!IofCompleteRequest` at `0x140008869`
- `ntoskrnl!IofCompleteRequest` at `0x1400088ec`
- `ntoskrnl!IofCompleteRequest` at `0x140008971`
- `ntoskrnl!IofCompleteRequest` at `0x140008869`
- `ntoskrnl!IofCompleteRequest` at `0x1400088ec`
- `ntoskrnl!IofCompleteRequest` at `0x140008971`
- `ntoskrnl!IoFreeWorkItem` at `0x14000878c`
- `ntoskrnl!IoFreeWorkItem` at `0x14000878c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140008858`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400088db`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140008960`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400089d6`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140008858`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400088db`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140008960`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400089d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400081c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400081c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008687`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000873b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400087c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008687`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000873b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400087c2`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008190`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008190`
- `ntoskrnl!IoQueueWorkItem` at `0x1400086df`
- `ntoskrnl!IoQueueWorkItem` at `0x1400086df`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008889`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000890c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008991`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008889`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000890c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140008991`

## pseudocode

```c
__int64 __fastcall I8xPowerUpToD0Complete(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3, __int64 a4)
{
  _BYTE *DeviceExtension; // r15
  IRP *v5; // r14
  IRP *v6; // rbp
  const char *v9; // rcx
  PIO_WORKITEM *Pool2; // rbx
  PIO_WORKITEM WorkItem; // rax
  KIRQL v12; // al
  int v13; // r8d
  int v14; // edx
  char v15; // al
  unsigned int v16; // r12d
  int v17; // eax
  unsigned __int8 v18; // si
  unsigned __int8 v19; // cl
  int v20; // r15d
  int v21; // edi
  char v22; // di
  char v23; // si
  unsigned int v24; // eax
  int v25; // edx
  struct _IO_WORKITEM *v26; // rcx
  int v28; // [rsp+20h] [rbp-68h]
  KIRQL v29; // [rsp+90h] [rbp+8h]
  char v30; // [rsp+98h] [rbp+10h]
  unsigned __int8 v31; // [rsp+A8h] [rbp+20h]

  DeviceExtension = DeviceObject->DeviceExtension;
  v5 = 0;
  v6 = 0;
  v30 = 0;
  v31 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = "kb";
    if ( !DeviceExtension[565] )
      v9 = "mouse";
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)"mouse",
      23,
      52,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      (__int64)v9);
  }
  Pool2 = (PIO_WORKITEM *)ExAllocatePool2(64, 32, 842281016, a4);
  if ( Pool2 )
  {
    WorkItem = IoAllocateWorkItem(DeviceObject);
    *Pool2 = WorkItem;
    if ( !WorkItem )
    {
      ExFreePoolWithTag(Pool2, 0);
      Pool2 = 0;
    }
  }
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 192LL));
  v14 = v12;
  v29 = v12;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      23,
      53,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
      *((char *)&WPP_MAIN_CB.DeviceQueue.Size + 2));
    v14 = v29;
  }
  v15 = DeviceExtension[565];
  if ( Irp->IoStatus.Status < 0 )
  {
    v16 = 0;
    if ( v15 )
      v17 = *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) | 0x200;
    else
      v17 = *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) | 0x2000;
  }
  else
  {
    *((_QWORD *)DeviceExtension + 9) = Irp;
    v16 = -1073741802;
    if ( v15 )
      v17 = *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) | 0x100;
    else
      v17 = *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) | 0x1000;
  }
  *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) = v17;
  if ( (v17 & 2) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        22,
        54,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v14 = v29;
    }
    v18 = 1;
  }
  else
  {
    v18 = 0;
  }
  if ( (*(_BYTE *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x20) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        22,
        55,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v14 = v29;
    }
    ++v18;
  }
  if ( (*(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x100) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        22,
        56,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v14 = v29;
    }
    v19 = 1;
    v30 = 1;
  }
  else
  {
    v19 = 0;
  }
  if ( (*(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x1000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        22,
        57,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v14 = v29;
      v19 = v30;
    }
    v30 = ++v19;
  }
  if ( (*(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x200) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        25,
        58,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v14 = v29;
      v19 = v30;
    }
    LOBYTE(v13) = 1;
    v31 = 1;
  }
  else
  {
    LOBYTE(v13) = 0;
  }
  if ( (*(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x2000) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        25,
        59,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
      v14 = v29;
      v19 = v30;
      v13 = v31;
    }
    LOBYTE(v13) = v13 + 1;
    v31 = v13;
  }
  v20 = (unsigned __int8)v13;
  v21 = v19;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_dddD(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      v13,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      v28,
      v19,
      v18,
      v13,
      *((char *)&WPP_MAIN_CB.DeviceQueue.Size + 2));
    v14 = v29;
    v19 = v30;
    LOBYTE(v13) = v31;
  }
  if ( v21 + v20 == v18 )
  {
    if ( v19 )
    {
      if ( !(_BYTE)v13 || (*(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x200) == 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            24,
            61,
            (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
          v14 = v29;
        }
        v23 = 1;
        v22 = 0;
LABEL_60:
        if ( (*(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0x1000) != 0 )
        {
          v5 = (IRP *)*((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 9);
          *((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 9) = 0;
          v24 = *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0xFFFFEFCF;
        }
        else
        {
          v24 = *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) & 0xFFFFDFFF;
        }
        *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) = v24;
        if ( (v24 & 0x100) != 0 )
        {
          v6 = (IRP *)*((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceContext + 9);
          *((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceContext + 9) = 0;
          *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) &= 0xFFFFFEFC;
        }
        else
        {
          *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) = v24 & 0xFFFFFDFF;
        }
        if ( Pool2 && v23 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              24,
              64,
              (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
            LOBYTE(v14) = v29;
          }
          *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) |= 0x10000000u;
          KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 192LL), v14);
          goto LABEL_71;
        }
        goto LABEL_81;
      }
      v5 = (IRP *)*((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 9);
      *((_QWORD *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 9) = 0;
      *(_DWORD *)(&WPP_MAIN_CB.DeviceQueue.Size + 1) &= 0xFFFFEFCF;
      if ( v5 != Irp )
      {
        v22 = 1;
LABEL_59:
        v23 = 0;
        goto LABEL_60;
      }
      v16 = -1073741823;
      v5->IoStatus.Status = -1073741823;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        24,
        62,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
        *((char *)&WPP_MAIN_CB.DeviceQueue.Size + 2));
      v14 = v29;
    }
    v22 = 0;
    goto LABEL_59;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      24,
      63,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 192LL), v29);
    v22 = 0;
    goto LABEL_76;
  }
  v22 = 0;
  v23 = 0;
LABEL_81:
  KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 192LL), v14);
  if ( !v23 )
  {
LABEL_76:
    if ( Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          22,
          69,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
          (char)Pool2);
      IoFreeWorkItem(*Pool2);
      ExFreePoolWithTag(Pool2, 0);
    }
    goto LABEL_94;
  }
  if ( Pool2 )
  {
LABEL_71:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        24,
        68,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
    v26 = *Pool2;
    Pool2[2] = (PIO_WORKITEM)v6;
    Pool2[1] = (PIO_WORKITEM)v5;
    IoQueueWorkItem(v26, I8xReinitializeHardware, DelayedWorkQueue, Pool2);
LABEL_94:
    if ( v22 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          25,
          70,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
          (char)v5);
      PoStartNextPowerIrp(v5);
      IofCompleteRequest(v5, 0);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 40), v5, 0x20u);
    }
    if ( Irp->IoStatus.Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          25,
          71,
          (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
          (char)Irp);
      PoStartNextPowerIrp(Irp);
    }
    return v16;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v25,
      25,
      65,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
  if ( v5 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        25,
        66,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
        (char)v5);
    v5->IoStatus.Status = -1073741670;
    v5->IoStatus.Information = 0;
    PoStartNextPowerIrp(v5);
    IofCompleteRequest(v5, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine + 40), v5, 0x20u);
  }
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v25,
        25,
        67,
        (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids,
        (char)v6);
    v6->IoStatus.Status = -1073741670;
    v6->IoStatus.Information = 0;
    PoStartNextPowerIrp(v6);
    IofCompleteRequest(v6, 0);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)WPP_MAIN_CB.Queue.Wcb.DeviceContext + 40), v6, 0x20u);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400080e0  mov     [rsp+arg_10], rbx
0x1400080e5  push    rbp
0x1400080e6  push    rsi
0x1400080e7  push    rdi
0x1400080e8  push    r12
0x1400080ea  push    r13
0x1400080ec  push    r14
0x1400080ee  push    r15
0x1400080f0  sub     rsp, 50h
0x1400080f4  mov     r15, [rcx+40h]
0x1400080f8  xor     r14d, r14d
0x1400080fb  xor     ebp, ebp
0x1400080fd  mov     [rsp+88h+arg_8], 0
0x140008105  mov     r13, rdx
0x140008108  mov     [rsp+88h+arg_18], 0
0x140008110  mov     rsi, rcx
0x140008113  lea     r12, WPP_RECORDER_INITIALIZED
0x14000811a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140008121  lea     r8, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x140008128  jz      short loc_140008169
0x14000812a  cmp     [r15+235h], bpl
0x140008131  lea     rdx, aMouse_0; "mouse"
0x140008138  lea     rcx, aKb; "kb"
0x14000813f  mov     r9d, 34h ; '4'
0x140008145  cmovz   rcx, rdx
0x140008149  mov     [rsp+88h+var_60], rcx
0x14000814e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008155  mov     [rsp+88h+var_68], r8
0x14000815a  mov     r8d, 17h
0x140008160  mov     rcx, [rcx+40h]
0x140008164  call    WPP_RECORDER_SF_s
0x140008169  mov     edx, 20h ; ' '
0x14000816e  mov     ecx, 40h ; '@'
0x140008173  mov     r8d, 32343038h
0x140008179  call    cs:__imp_ExAllocatePool2
0x140008180  nop     dword ptr [rax+rax+00h]
0x140008185  mov     rbx, rax
0x140008188  test    rax, rax
0x14000818b  jz      short loc_1400081B7
0x14000818d  mov     rcx, rsi; DeviceObject
0x140008190  call    cs:__imp_IoAllocateWorkItem
0x140008197  nop     dword ptr [rax+rax+00h]
0x14000819c  mov     [rbx], rax
0x14000819f  test    rax, rax
0x1400081a2  jnz     short loc_1400081B7
0x1400081a4  xor     edx, edx; Tag
0x1400081a6  mov     rcx, rbx; P
0x1400081a9  call    cs:__imp_ExFreePoolWithTag
0x1400081b0  nop     dword ptr [rax+rax+00h]
0x1400081b5  xor     ebx, ebx
0x1400081b7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400081be  add     rcx, 0C0h; SpinLock
0x1400081c5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400081cc  nop     dword ptr [rax+rax+00h]
0x1400081d1  movzx   edx, al
0x1400081d4  mov     [rsp+88h+arg_0], al
0x1400081db  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400081e2  jz      short loc_14000821E
0x1400081e4  mov     ecx, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x1400081ea  lea     rax, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x1400081f1  mov     dword ptr [rsp+88h+var_60], ecx
0x1400081f5  mov     r9d, 35h ; '5'
0x1400081fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008202  mov     r8d, 17h
0x140008208  mov     [rsp+88h+var_68], rax
0x14000820d  mov     rcx, [rcx+40h]
0x140008211  call    WPP_RECORDER_SF_D
0x140008216  movzx   edx, [rsp+88h+arg_0]
0x14000821e  movzx   eax, byte ptr [r15+235h]
0x140008226  cmp     [r13+30h], ebp
0x14000822a  jl      short loc_14000824C
0x14000822c  mov     [r15+48h], r13
0x140008230  test    al, al
0x140008232  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x140008238  mov     r12d, 0C0000016h
0x14000823e  jz      short loc_140008246
0x140008240  bts     eax, 8
0x140008244  jmp     short loc_140008263
0x140008246  bts     eax, 0Ch
0x14000824a  jmp     short loc_140008263
0x14000824c  xor     r12d, r12d
0x14000824f  test    al, al
0x140008251  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x140008257  jz      short loc_14000825F
0x140008259  bts     eax, 9
0x14000825d  jmp     short loc_140008263
0x14000825f  bts     eax, 0Dh
0x140008263  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, eax
0x140008269  test    al, 2
0x14000826b  jz      short loc_1400082B9
0x14000826d  lea     r9, WPP_RECORDER_INITIALIZED
0x140008274  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14000827b  lea     rdi, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x140008282  jz      short loc_1400082B4
0x140008284  mov     rcx, cs:WPP_GLOBAL_Control
0x14000828b  mov     r9d, 36h ; '6'
0x140008291  mov     r8d, 16h
0x140008297  mov     [rsp+88h+var_68], rdi
0x14000829c  mov     rcx, [rcx+40h]
0x1400082a0  call    WPP_RECORDER_SF_
0x1400082a5  movzx   edx, [rsp+88h+arg_0]
0x1400082ad  lea     r9, WPP_RECORDER_INITIALIZED
0x1400082b4  mov     sil, 1
0x1400082b7  jmp     short loc_1400082CA
0x1400082b9  xor     sil, sil
0x1400082bc  lea     r9, WPP_RECORDER_INITIALIZED
0x1400082c3  lea     rdi, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x1400082ca  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x1400082d0  test    al, 20h
0x1400082d2  jz      short loc_140008310
0x1400082d4  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400082db  jz      short loc_14000830D
0x1400082dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400082e4  mov     r9d, 37h ; '7'
0x1400082ea  mov     r8d, 16h
0x1400082f0  mov     [rsp+88h+var_68], rdi
0x1400082f5  mov     rcx, [rcx+40h]
0x1400082f9  call    WPP_RECORDER_SF_
0x1400082fe  movzx   edx, [rsp+88h+arg_0]
0x140008306  lea     r9, WPP_RECORDER_INITIALIZED
0x14000830d  inc     sil
0x140008310  test    dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 100h
0x14000831a  jz      short loc_140008360
0x14000831c  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140008323  jz      short loc_140008355
0x140008325  mov     rcx, cs:WPP_GLOBAL_Control
0x14000832c  mov     r9d, 38h ; '8'
0x140008332  mov     r8d, 16h
0x140008338  mov     [rsp+88h+var_68], rdi
0x14000833d  mov     rcx, [rcx+40h]
0x140008341  call    WPP_RECORDER_SF_
0x140008346  movzx   edx, [rsp+88h+arg_0]
0x14000834e  lea     r9, WPP_RECORDER_INITIALIZED
0x140008355  mov     cl, 1
0x140008357  mov     [rsp+88h+arg_8], cl
0x14000835e  jmp     short loc_140008362
0x140008360  xor     cl, cl
0x140008362  test    dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 1000h
0x14000836c  jz      short loc_1400083B8
0x14000836e  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140008375  jz      short loc_1400083AF
0x140008377  mov     rcx, cs:WPP_GLOBAL_Control
0x14000837e  mov     r9d, 39h ; '9'
0x140008384  mov     r8d, 16h
0x14000838a  mov     [rsp+88h+var_68], rdi
0x14000838f  mov     rcx, [rcx+40h]
0x140008393  call    WPP_RECORDER_SF_
0x140008398  movzx   edx, [rsp+88h+arg_0]
0x1400083a0  lea     r9, WPP_RECORDER_INITIALIZED
0x1400083a7  movzx   ecx, [rsp+88h+arg_8]
0x1400083af  inc     cl
0x1400083b1  mov     [rsp+88h+arg_8], cl
0x1400083b8  test    dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 200h
0x1400083c2  jz      short loc_140008412
0x1400083c4  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x1400083cb  jz      short loc_140008405
0x1400083cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083d4  mov     r9d, 3Ah ; ':'
0x1400083da  mov     r8d, 19h
0x1400083e0  mov     [rsp+88h+var_68], rdi
0x1400083e5  mov     rcx, [rcx+40h]
0x1400083e9  call    WPP_RECORDER_SF_
0x1400083ee  movzx   edx, [rsp+88h+arg_0]
0x1400083f6  lea     r9, WPP_RECORDER_INITIALIZED
0x1400083fd  movzx   ecx, [rsp+88h+arg_8]
0x140008405  mov     r8b, 1
0x140008408  mov     [rsp+88h+arg_18], r8b
0x140008410  jmp     short loc_140008415
0x140008412  xor     r8b, r8b
0x140008415  test    dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 2000h
0x14000841f  jz      short loc_140008476
0x140008421  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140008428  jz      short loc_14000846B
0x14000842a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008431  mov     r9d, 3Bh ; ';'
0x140008437  mov     r8d, 19h
0x14000843d  mov     [rsp+88h+var_68], rdi
0x140008442  mov     rcx, [rcx+40h]
0x140008446  call    WPP_RECORDER_SF_
0x14000844b  movzx   edx, [rsp+88h+arg_0]
0x140008453  lea     r9, WPP_RECORDER_INITIALIZED
0x14000845a  movzx   ecx, [rsp+88h+arg_8]
0x140008462  movzx   r8d, [rsp+88h+arg_18]
0x14000846b  inc     r8b
0x14000846e  mov     [rsp+88h+arg_18], r8b
0x140008476  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x14000847d  movzx   r15d, r8b
0x140008481  movzx   edi, cl
0x140008484  movzx   esi, sil
0x140008488  jz      short loc_1400084D1
0x14000848a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008491  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x140008497  mov     [rsp+88h+var_48], eax
0x14000849b  mov     [rsp+88h+var_50], r15d
0x1400084a0  mov     rcx, [rcx+40h]
0x1400084a4  mov     [rsp+88h+var_58], esi
0x1400084a8  mov     dword ptr [rsp+88h+var_60], edi
0x1400084ac  call    WPP_RECORDER_SF_dddD
0x1400084b1  movzx   edx, [rsp+88h+arg_0]; NewIrql
0x1400084b9  lea     r9, WPP_RECORDER_INITIALIZED
0x1400084c0  movzx   ecx, [rsp+88h+arg_8]
0x1400084c8  movzx   r8d, [rsp+88h+arg_18]
0x1400084d1  lea     eax, [rdi+r15]
0x1400084d5  cmp     eax, esi
0x1400084d7  jnz     loc_1400086F0
0x1400084dd  test    cl, cl
0x1400084df  jz      loc_14000857A
0x1400084e5  test    r8b, r8b
0x1400084e8  jz      short loc_140008532
0x1400084ea  test    dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 200h
0x1400084f4  jz      short loc_140008532
0x1400084f6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400084fd  lea     r15, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x140008504  mov     r14, [rax+48h]
0x140008508  mov     [rax+48h], rbp
0x14000850c  and     dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 0FFFFEFCFh
0x140008516  cmp     r14, r13
0x140008519  jz      short loc_140008523
0x14000851b  mov     dil, 1
0x14000851e  jmp     loc_1400085C7
0x140008523  mov     r12d, 0C0000001h
0x140008529  mov     [r14+30h], r12d
0x14000852d  jmp     loc_1400085C4
0x140008532  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140008539  lea     r15, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x140008540  jz      short loc_140008572
0x140008542  mov     rcx, cs:WPP_GLOBAL_Control
0x140008549  mov     r9d, 3Dh ; '='
0x14000854f  mov     r8d, 18h
0x140008555  mov     [rsp+88h+var_68], r15
0x14000855a  mov     rcx, [rcx+40h]
0x14000855e  call    WPP_RECORDER_SF_
0x140008563  movzx   edx, [rsp+88h+arg_0]
0x14000856b  lea     r9, WPP_RECORDER_INITIALIZED
0x140008572  mov     sil, 1
0x140008575  xor     dil, dil
0x140008578  jmp     short loc_1400085CA
0x14000857a  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140008581  lea     r15, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x140008588  jz      short loc_1400085C4
0x14000858a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008591  mov     r9d, 3Eh ; '>'
0x140008597  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x14000859d  mov     r8d, 18h
0x1400085a3  mov     dword ptr [rsp+88h+var_60], eax
0x1400085a7  mov     [rsp+88h+var_68], r15
0x1400085ac  mov     rcx, [rcx+40h]
0x1400085b0  call    WPP_RECORDER_SF_D
0x1400085b5  movzx   edx, [rsp+88h+arg_0]
0x1400085bd  lea     r9, WPP_RECORDER_INITIALIZED
0x1400085c4  xor     dil, dil
0x1400085c7  xor     sil, sil
0x1400085ca  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x1400085d0  bt      eax, 0Ch
0x1400085d4  jnb     short loc_1400085F2
0x1400085d6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400085dd  mov     r14, [rax+48h]
0x1400085e1  mov     [rax+48h], rbp
0x1400085e5  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue+4
0x1400085eb  and     eax, 0FFFFEFCFh
0x1400085f0  jmp     short loc_1400085F6
0x1400085f2  btr     eax, 0Dh
0x1400085f6  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, eax
0x1400085fc  bt      eax, 8
0x140008600  jnb     short loc_140008621
0x140008602  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x140008609  mov     rbp, [rax+48h]
0x14000860d  mov     qword ptr [rax+48h], 0
0x140008615  and     dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 0FFFFFEFCh
0x14000861f  jmp     short loc_14000862B
0x140008621  btr     eax, 9
0x140008625  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, eax
0x14000862b  test    rbx, rbx
0x14000862e  jz      loc_1400087B4
0x140008634  test    sil, sil
0x140008637  jz      loc_1400087B4
0x14000863d  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140008644  jz      short loc_14000866F
0x140008646  mov     rcx, cs:WPP_GLOBAL_Control
0x14000864d  mov     r9d, 40h ; '@'
0x140008653  mov     r8d, 18h
0x140008659  mov     [rsp+88h+var_68], r15
0x14000865e  mov     rcx, [rcx+40h]
0x140008662  call    WPP_RECORDER_SF_
0x140008667  movzx   edx, [rsp+88h+arg_0]; NewIrql
0x14000866f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140008676  or      dword ptr cs:WPP_MAIN_CB.DeviceQueue+4, 10000000h
0x140008680  add     rcx, 0C0h; SpinLock
0x140008687  call    cs:__imp_KeReleaseSpinLock
0x14000868e  nop     dword ptr [rax+rax+00h]
0x140008693  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000869a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400086a1  jz      short loc_1400086C4
0x1400086a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400086aa  mov     r9d, 44h ; 'D'
0x1400086b0  mov     r8d, 18h
0x1400086b6  mov     [rsp+88h+var_68], r15
0x1400086bb  mov     rcx, [rcx+40h]
0x1400086bf  call    WPP_RECORDER_SF_
0x1400086c4  mov     rcx, [rbx]; IoWorkItem
  ... truncated ...
```
