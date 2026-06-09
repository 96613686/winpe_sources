# RefsFspDispatch(void *)

- ea: `0x1400bc440`
- end: `0x1400bcf74`
- name: `?RefsFspDispatch@@YAXPEAX@Z`
- size: `2868`
- prototype: `KSTART_ROUTINE`
- caller_count: `3`
- callee_count: `30`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400b9250`
- `0x1400f3500`
- `0x1402e2d4c`

## callees

- `0x14003a520`
- `0x14003b3f0`
- `0x14003ec10`
- `0x14003fbe0`
- `0x140041a40`
- `0x140041b40`
- `0x14008f8b0`
- `0x1400a648c`
- `0x1400a7f90`
- `0x1400bc440`
- `0x1400e1534`
- `0x1400e4df8`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x14028692c`
- `0x140286acc`
- `0x1402961f4`
- `0x1402c3810`
- `0x140300f70`
- `0x140308620`
- `0x14030a1a0`
- `0x14030cbe0`
- `0x140312090`
- `0x140314de0`
- `0x140319a38`
- `0x140320d80`
- `0x1403286c0`
- `0x1403294a0`
- `0x1403389e4`
- `0x14033e1e0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400bcf3c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bcf3c`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc93f`
- `ntoskrnl!KeBugCheckEx` at `0x1400bc93f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bc611`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bc611`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bc740`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bc740`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bc5c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bc5c5`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bcc91`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bcc91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcc9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcc9d`
- `ntoskrnl!KeSetEvent` at `0x1400bceb8`
- `ntoskrnl!KeSetEvent` at `0x1400bceb8`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bc6e2`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bc6e2`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1400bc6cf`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1400bc6cf`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x1400bc6f9`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x1400bc6f9`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1400bcc78`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1400bcc78`
- `ntoskrnl!ObfReferenceObject` at `0x1400bc576`
- `ntoskrnl!ObfReferenceObject` at `0x1400bc576`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400bc5fa`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400bc5fa`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bc7c3`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bcbbe`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bc7c3`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bcbbe`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400bc7eb`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400bc7eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc856`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bccd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bce3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc856`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bccd6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bce3b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc86c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bce2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bce9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bcf28`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc86c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bce2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bce9a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bcf28`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400bcf63`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400bcf63`
- `ntoskrnl!IoWithinStackLimits` at `0x1400bc628`
- `ntoskrnl!IoWithinStackLimits` at `0x1400bc628`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400bcdf4`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400bcdf4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400bce11`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400bce53`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400bce11`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400bce53`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bc890`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bc890`
- `ntoskrnl!KeInitializeEvent` at `0x1400bca08`
- `ntoskrnl!KeInitializeEvent` at `0x1400bca08`

## pseudocode

```c
void __fastcall RefsFspDispatch(struct _IRP_CONTEXT *StartContext)
{
  struct _IRP_CONTEXT *v1; // r14
  __int64 v2; // rdx
  __int64 v3; // r13
  unsigned int v4; // edi
  __int64 v5; // rbx
  int v6; // ecx
  __int64 v7; // rax
  _OWORD *v8; // rax
  PVOID *v9; // rcx
  bool v10; // r15
  ULONG_PTR TopLevelIrp; // rsi
  IRP *p_Irp; // rax
  IO_PRIORITY_HINT IoPriorityHint; // eax
  char Type; // al
  int v15; // edx
  bool v16; // r8
  __int64 v17; // r12
  __int64 v18; // rsi
  KIRQL v19; // al
  int v20; // eax
  struct REFS_IO_CONTEXT *v21; // rdx
  struct _IRP_CONTEXT *v22; // rcx
  char v23; // r15
  int v24; // esi
  int v25; // eax
  KSPIN_LOCK *v26; // rbx
  KIRQL v27; // dl
  __int64 v28; // rsi
  struct _IO_STATUS_BLOCK *v29; // rcx
  unsigned int v30; // ecx
  __int64 *v31; // r15
  __int64 v32; // rcx
  __int64 *v33; // rax
  char v34; // [rsp+30h] [rbp-108h]
  char v35; // [rsp+31h] [rbp-107h]
  char v36; // [rsp+33h] [rbp-105h]
  KIRQL Irql; // [rsp+34h] [rbp-104h] BYREF
  KIRQL v38; // [rsp+35h] [rbp-103h]
  bool v39; // [rsp+36h] [rbp-102h]
  int v40; // [rsp+38h] [rbp-100h]
  unsigned int v41; // [rsp+3Ch] [rbp-FCh]
  int v42; // [rsp+40h] [rbp-F8h]
  unsigned int v43; // [rsp+44h] [rbp-F4h]
  int v44; // [rsp+48h] [rbp-F0h]
  int v45; // [rsp+4Ch] [rbp-ECh]
  struct _IO_STATUS_BLOCK *v46; // [rsp+50h] [rbp-E8h]
  struct _IRP_CONTEXT *v47; // [rsp+58h] [rbp-E0h]
  IRP Irp; // [rsp+60h] [rbp-D8h] BYREF

  v1 = StartContext;
  memset(&Irp, 0, 40);
  Irp.IoStatus.Pointer = 0;
  v2 = 0;
  v45 = 0;
  v41 = 0;
  v43 = 0;
  v3 = 0;
  v39 = 0;
  v4 = 0;
  v40 = 0;
  memset(&Irp.Overlay.AllocationSize + 1, 0, 40);
  v36 = 0;
  v47 = StartContext;
  *((_QWORD *)StartContext + 15) = (char *)StartContext + 112;
  *((_QWORD *)StartContext + 14) = (char *)StartContext + 112;
  v5 = *((_QWORD *)StartContext + 9);
  *(_QWORD *)&Irp.RequestorMode = v5;
  if ( v5 )
    v2 = *(_QWORD *)(v5 + 184);
  v6 = *((_DWORD *)StartContext + 1);
  v42 = v6 & 0x4000000;
  HIDWORD(Irp.ThreadListEntry.Blink) = v6 & 0x4000000;
  v44 = v6 & 0x100000;
  LODWORD(Irp.ThreadListEntry.Blink) = v6 & 0x100000;
  v7 = *((_QWORD *)v1 + 1);
  v46 = (struct _IO_STATUS_BLOCK *)(v7 & 0x1000);
  Irp.UserIosb = v46;
  v34 = v6 & 1;
  *((_DWORD *)v1 + 1) = v6 & 0xFFFFFFFE;
  *((_QWORD *)v1 + 1) = v7 | 1;
  if ( (v6 & 0x4000000) == 0 && (v6 & 0x100000) == 0 )
  {
    if ( v5 && *(_QWORD *)(v2 + 48) )
    {
      v3 = *(_QWORD *)(v2 + 40);
      Irp.ThreadListEntry.Flink = (struct _LIST_ENTRY *)v3;
      ObfReferenceObject((PVOID)v3);
    }
    else
    {
      Irp.ThreadListEntry.Flink = 0;
    }
    v39 = (*((_DWORD *)v1 + 1) & 0x400000) != 0;
  }
  Irp.UserEvent = (PKEVENT)v3;
  do
  {
    memset(&Irp.Tail.CompletionKey + 2, 0, 24);
    KeEnterCriticalRegion();
    v8 = (_OWORD *)*((_QWORD *)v1 + 10);
    if ( v8 )
    {
      *(_OWORD *)(&Irp.Tail.CompletionKey + 3) = *v8;
      v9 = &Irp.Tail.Overlay.DriverContext[3];
    }
    else
    {
      v9 = 0;
    }
    Irp.Tail.Overlay.DriverContext[2] = v9;
    Irp.Overlay.AllocationSize.QuadPart = IoSetActivityIdThread();
    v10 = 0;
    TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
    if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
      v10 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
    *(_DWORD *)(&Irp.Size + 1) = 0;
    Irp.MdlAddress = (PMDL)TopLevelIrp;
    *(_QWORD *)&Irp.Flags = 0;
    LOBYTE(Irp.Type) = 1;
    if ( v10 )
    {
      HIBYTE(Irp.Type) = 1;
      LOBYTE(Irp.Size) = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(CSHORT *)((char *)&Irp.Type + 1) = 0;
    }
    p_Irp = &Irp;
    Irp.IoStatus.Information = (ULONG_PTR)&Irp;
    if ( v5 )
    {
      LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = 16;
      *(PVOID *)((char *)Irp.Tail.Overlay.DriverContext + 4) = (PVOID)0xFFFF;
      *((_DWORD *)&Irp.Tail.CompletionKey + 3) = 2;
      if ( IoRetrievePriorityInfo(0, 0, KeGetCurrentThread(), (PIO_PRIORITY_INFO)&Irp.Tail) >= 0 )
      {
        IoPriorityHint = IoGetIoPriorityHint((PIRP)v5);
        IoSetIoPriorityHintIntoThread(KeGetCurrentThread(), (unsigned int)IoPriorityHint);
        v36 = 1;
      }
      v4 = 0;
      v40 = 0;
      p_Irp = (IRP *)Irp.IoStatus.Information;
    }
    ++RefsPostRequests;
    do
    {
      if ( !*(_QWORD *)&Irp.Flags )
      {
        *(_DWORD *)(&Irp.Size + 1) = 1397140410;
        *(_QWORD *)&Irp.Flags = v1;
        *((_QWORD *)v1 + 1) |= 0x100000uLL;
        IoSetTopLevelIrp(p_Irp);
      }
      *((_QWORD *)v1 + 13) = *(_QWORD *)&Irp.Flags;
      Type = Irp.Type;
      if ( (*((_DWORD *)v1 + 2) & 0x2000LL) != 0 )
        Type = 0;
      LOBYTE(Irp.Type) = Type;
      v35 = 0;
      *((_DWORD *)v1 + 4) = 0;
      *((_QWORD *)v1 + 1) |= 0x40uLL;
      if ( v46 && !v42 )
        *((_DWORD *)v1 + 1) |= 0x8000000u;
      if ( v4 == -1073741432 || !v5 )
      {
        RefsCheckpointForLogFileFull(v1);
        if ( (unsigned int)++v45 >= 2 )
          *((_DWORD *)v1 + 1) |= 0x10u;
        v4 = 0;
        v40 = 0;
      }
      if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(v4) )
      {
        Irp.AssociatedIrp.IrpCount = 8;
        HIDWORD(Irp.AssociatedIrp.SystemBuffer) = v4;
        CcErrorCallbackRoutine(&Irp.AssociatedIrp);
      }
      RefsPreRequestProcessingExtend(v1, v15);
      if ( v5 )
      {
        switch ( *((_BYTE *)v1 + 40) )
        {
          case 0:
            *((_QWORD *)v1 + 1) &= ~2uLL;
            v17 = *((_QWORD *)v1 + 18);
            if ( (*(_DWORD *)(v17 + 144) & 0x100000) != 0 )
            {
              v18 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 112LL);
              v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 4088));
              KeReleaseSpinLock((PKSPIN_LOCK)(v18 + 4088), v19);
              KeWaitForSingleObject((PVOID)(v18 + 4120), Executive, 0, 0, 0);
            }
            memset((void *)v17, 0, 0xD8u);
            *(_QWORD *)(v17 + 160) = *(_QWORD *)(v5 + 184);
            if ( (*((_DWORD *)v1 + 2) & 0x200LL) != 0 )
              v20 = RefsCommonVolumeOpen(v1, (struct _IRP *)v5, (struct _CREATE_CONTEXT *)v17);
            else
              v20 = RefsCommonCreate(v1, (PIRP)v5, (struct _CREATE_CONTEXT *)v17);
            v4 = v20;
            v40 = v20;
            goto LABEL_72;
          case 2:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1e930544d89f3ce82d53e09c7070df23_Traceguids);
            }
            KeBugCheckEx(0x149u, 0x130184u, 0, 0, 0);
          case 3:
            Irp.IoStatus.Pointer = (char *)v1 + 800;
            v21 = (struct _IRP_CONTEXT *)((char *)v1 + 800);
            v22 = v1;
            if ( (*((_DWORD *)v1 + 2) & 0x1000LL) != 0 )
              goto LABEL_53;
            RefsInitializeIoContext(v1, v21, v16, (*(_DWORD *)(v5 + 16) & 2) != 0);
            RefsCommonRead(v1, (struct _IRP_CONTEXT *)((char *)v1 + 800), (struct _IRP *)v5);
            goto LABEL_72;
          case 4:
            Irp.IoStatus.Pointer = (char *)v1 + 800;
            v21 = (struct _IRP_CONTEXT *)((char *)v1 + 800);
            v22 = v1;
            if ( (*((_DWORD *)v1 + 2) & 0x1000LL) != 0 )
            {
LABEL_53:
              RefsCommonIoCompletionWorker(v22, v21, (struct _IRP *)v5);
            }
            else
            {
              RefsInitializeIoContext(v1, v21, v16, (*(_DWORD *)(v5 + 16) & 2) != 0);
              RefsCommonWrite(v1, (struct _IRP_CONTEXT *)((char *)v1 + 800), (PIRP)v5);
            }
            goto LABEL_72;
          case 5:
            RefsCommonQueryInformation(v1, (PIRP)v5);
            goto LABEL_72;
          case 6:
            KeInitializeEvent((PRKEVENT)(&Irp.Overlay.AllocationSize + 1), NotificationEvent, 0);
            *((_QWORD *)v1 + 19) = &Irp.Overlay.AsynchronousParameters.UserApcContext;
            v4 = RefsCommonSetInformation(v1, (PIRP)v5);
            v40 = v4;
            if ( v4 != 871 )
              goto LABEL_72;
            RefsWaitForOplockCompletionEvent((PIRP)v5, (PRKEVENT)(&Irp.Overlay.AllocationSize + 1));
            v35 = 1;
            v23 = v34;
            v24 = v42;
            break;
          case 9:
            RefsCommonFlushBuffers(v1, (PIRP)v5);
            goto LABEL_72;
          case 0xA:
            RefsCommonQueryVolumeInfo(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0xB:
            RefsCommonSetVolumeInfo(v1, (PIRP)v5);
            goto LABEL_72;
          case 0xC:
            RefsCommonDirectoryControl(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0xD:
            RefsCommonFileSystemControl(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0xE:
            RefsCommonDeviceControl(v1, (PIRP)v5);
            goto LABEL_72;
          case 0x11:
            RefsCommonLockControl(v1, (PIRP)v5);
            goto LABEL_72;
          case 0x12:
            RefsCommonCleanup(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0x14:
            RefsCommonQuerySecurityInfo(v1, (PIRP)v5);
            goto LABEL_72;
          case 0x15:
            RefsCommonSetSecurityInfo(v1, (PIRP)v5);
            goto LABEL_72;
          default:
            RefsCompleteRequest(v1, (PIRP)v5, -1073741808);
            goto LABEL_72;
        }
      }
      else
      {
        RefsCompleteRequest(v1, 0, 0);
        v1 = 0;
        v47 = 0;
LABEL_72:
        v23 = v34;
        v24 = v42;
      }
      p_Irp = (IRP *)Irp.IoStatus.Information;
    }
    while ( v35 );
    if ( v36 )
    {
      IoApplyPriorityInfoThread((PIO_PRIORITY_INFO)&Irp.Tail, 0, KeGetCurrentThread());
      v36 = 0;
    }
    ((void (__fastcall *)(_QWORD))IoClearActivityIdThread)((LARGE_INTEGER)Irp.Overlay.AllocationSize.QuadPart);
    KeLeaveCriticalRegion();
    v25 = v44;
    if ( v24 )
      return;
    if ( v44 )
      continue;
    if ( !Irp.ThreadListEntry.Flink )
    {
      if ( v39 )
        KeReleaseSemaphore(&RefsGlobalPostThrottle, 0, 1, 0);
      return;
    }
    v26 = (KSPIN_LOCK *)(v3 + 6216);
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 6216));
    v38 = v27;
    if ( v23 )
      --*(_DWORD *)(v3 + 6060);
    while ( 1 )
    {
      v28 = 0;
      v29 = v46;
      if ( v46 )
      {
        if ( *(_DWORD *)(v3 + 6208) )
          v28 = v3 + 6168;
      }
      else
      {
        if ( !*(_DWORD *)(v3 + 6160) || *(_DWORD *)(v3 + 6060) )
        {
          v41 = 0;
          v43 = 0;
          v34 = 0;
          if ( !*(_DWORD *)(v3 + 6112) )
            goto LABEL_93;
        }
        else
        {
          v30 = v41 + 1;
          v41 = v30;
          if ( v30 > 0x14 || !*(_DWORD *)(v3 + 6112) )
          {
            v41 = 0;
            v43 = 0;
            v34 = 1;
            v28 = v3 + 6120;
            v29 = v46;
            goto LABEL_93;
          }
          v43 = v30;
          v29 = v46;
          if ( !*(_DWORD *)(v3 + 6112) )
            goto LABEL_93;
          v34 = 0;
        }
        v28 = v3 + 6072;
      }
LABEL_93:
      if ( !v28 )
      {
        if ( v29 )
          --*(_DWORD *)(v3 + 6064);
        else
          --*(_DWORD *)(v3 + 6056);
        KeReleaseSpinLock(v26, v27);
        ObfDereferenceObject(Irp.ThreadListEntry.Flink);
        return;
      }
      v31 = *(__int64 **)(v28 + 24);
      v1 = (struct _IRP_CONTEXT *)(v31 - 14);
      v47 = (struct _IRP_CONTEXT *)(v31 - 14);
      v5 = *(v31 - 5);
      *(_QWORD *)&Irp.RequestorMode = v5;
      if ( v29 )
        goto LABEL_98;
      Irql = 0;
      IoAcquireCancelSpinLock(&Irql);
      if ( _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
        break;
      IoReleaseCancelSpinLock(Irql);
      v26 = (KSPIN_LOCK *)(v3 + 6216);
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 6216), v38);
      v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 6216));
      v38 = v27;
    }
    IoReleaseCancelSpinLock(Irql);
    *(_QWORD *)(v5 + 56) = 0;
    v27 = v38;
LABEL_98:
    --*(_DWORD *)(v28 + 40);
    v32 = *v31;
    v33 = (__int64 *)v31[1];
    *v33 = *v31;
    *(_QWORD *)(v32 + 8) = v33;
    v31[1] = (__int64)v31;
    *v31 = (__int64)v31;
    if ( v34 )
      ++*(_DWORD *)(v3 + 6060);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 6216), v27);
    if ( *(_DWORD *)(v28 + 40) < 0x3E8u )
      KeSetEvent((PRKEVENT)v28, 0, 0);
    v45 = 0;
    *((_QWORD *)v1 + 1) |= 1uLL;
    v24 = v42;
    v25 = v44;
  }
  while ( !v24 && !v25 );
}

```

## disassembly

```asm
0x1400bc440  mov     r11, rsp
0x1400bc443  mov     [r11+10h], rbx
0x1400bc447  mov     [r11+18h], rsi
0x1400bc44b  push    rdi
0x1400bc44c  push    r12
0x1400bc44e  push    r13
0x1400bc450  push    r14
0x1400bc452  push    r15
0x1400bc454  sub     rsp, 110h
0x1400bc45b  mov     rax, cs:__security_cookie
0x1400bc462  xor     rax, rsp
0x1400bc465  mov     qword ptr [rsp+138h+Irp.Tail+28h], rax
0x1400bc46d  mov     r14, rcx
0x1400bc470  xorps   xmm0, xmm0
0x1400bc473  xor     eax, eax
0x1400bc475  movups  xmmword ptr [rsp+138h+Irp.Type], xmm0
0x1400bc47a  mov     qword ptr [rsp+138h+Irp.Flags], rax
0x1400bc47f  xor     r12d, r12d
0x1400bc482  mov     [r11-0A8h], r12
0x1400bc489  mov     edx, r12d
0x1400bc48c  mov     [rsp+138h+var_EC], r12d
0x1400bc491  mov     [rsp+138h+var_FC], eax
0x1400bc495  mov     [rsp+138h+var_F4], eax
0x1400bc499  mov     r13d, r12d
0x1400bc49c  mov     [rsp+138h+Irp.ThreadListEntry.Flink], r12
0x1400bc4a4  mov     [rsp+138h+var_102], al
0x1400bc4a8  mov     edi, r12d
0x1400bc4ab  mov     [rsp+138h+var_100], r12d
0x1400bc4b0  movups  xmmword ptr [r11-78h], xmm0
0x1400bc4b5  mov     [r11-68h], rax
0x1400bc4b9  mov     [rsp+138h+var_105], al
0x1400bc4bd  movups  xmmword ptr [r11-60h], xmm0
0x1400bc4c2  mov     qword ptr [rsp+138h+Irp.AssociatedIrp], r12
0x1400bc4c7  mov     [rsp+138h+var_E0], rcx
0x1400bc4cc  lea     rax, [rcx+70h]
0x1400bc4d0  mov     [rax+8], rax
0x1400bc4d4  mov     [rax], rax
0x1400bc4d7  mov     rbx, [rcx+48h]
0x1400bc4db  mov     qword ptr [rsp+138h+Irp.RequestorMode], rbx
0x1400bc4e3  test    rbx, rbx
0x1400bc4e6  jz      short loc_1400BC4EF
0x1400bc4e8  mov     rdx, [rbx+0B8h]
0x1400bc4ef  mov     ecx, [rcx+4]
0x1400bc4f2  mov     esi, ecx
0x1400bc4f4  and     esi, 4000000h
0x1400bc4fa  mov     [rsp+138h+var_F8], esi
0x1400bc4fe  mov     dword ptr [rsp+138h+Irp.ThreadListEntry.Blink+4], esi
0x1400bc505  mov     r9d, ecx
0x1400bc508  and     r9d, 100000h
0x1400bc50f  mov     [rsp+138h+var_F0], r9d
0x1400bc514  mov     dword ptr [rsp+138h+Irp.ThreadListEntry.Blink], r9d
0x1400bc51c  mov     rax, [r14+8]
0x1400bc520  mov     r8, rax
0x1400bc523  and     r8d, 1000h
0x1400bc52a  mov     [rsp+138h+var_E8], r8
0x1400bc52f  mov     [rsp+138h+Irp.UserIosb], r8
0x1400bc537  movzx   r15d, cl
0x1400bc53b  and     r15b, 1
0x1400bc53f  mov     [rsp+138h+var_108], r15b
0x1400bc544  and     ecx, 0FFFFFFFEh
0x1400bc547  mov     [r14+4], ecx
0x1400bc54b  or      rax, 1
0x1400bc54f  mov     [r14+8], rax
0x1400bc553  test    esi, esi
0x1400bc555  jnz     short loc_1400BC599
0x1400bc557  test    r9d, r9d
0x1400bc55a  jnz     short loc_1400BC599
0x1400bc55c  test    rbx, rbx
0x1400bc55f  jz      short loc_1400BC584
0x1400bc561  cmp     [rdx+30h], rdi
0x1400bc565  jz      short loc_1400BC584
0x1400bc567  mov     r13, [rdx+28h]
0x1400bc56b  mov     [rsp+138h+Irp.ThreadListEntry.Flink], r13
0x1400bc573  mov     rcx, r13; Object
0x1400bc576  call    cs:__imp_ObfReferenceObject
0x1400bc57d  nop     dword ptr [rax+rax+00h]
0x1400bc582  jmp     short loc_1400BC58C
0x1400bc584  mov     [rsp+138h+Irp.ThreadListEntry.Flink], r13
0x1400bc58c  mov     eax, [r14+4]
0x1400bc590  shr     eax, 16h
0x1400bc593  and     al, 1
0x1400bc595  mov     [rsp+138h+var_102], al
0x1400bc599  mov     [rsp+138h+Irp.UserEvent], r13
0x1400bc5a1  mov     [rsp+138h+var_106], r15b
0x1400bc5a6  nop     word ptr [rax+rax+00000000h]
0x1400bc5b0  xorps   xmm0, xmm0
0x1400bc5b3  xor     eax, eax
0x1400bc5b5  movups  xmmword ptr [rsp+138h+Irp.Tail+10h], xmm0
0x1400bc5bd  mov     qword ptr [rsp+138h+Irp.Tail+20h], rax
0x1400bc5c5  call    cs:__imp_KeEnterCriticalRegion
0x1400bc5cc  nop     dword ptr [rax+rax+00h]
0x1400bc5d1  mov     rax, [r14+50h]
0x1400bc5d5  test    rax, rax
0x1400bc5d8  jz      short loc_1400BC5EF
0x1400bc5da  movups  xmm0, xmmword ptr [rax]
0x1400bc5dd  movups  xmmword ptr [rsp+138h+Irp.Tail+18h], xmm0
0x1400bc5e5  lea     rcx, [rsp+138h+Irp.Tail+18h]
0x1400bc5ed  jmp     short loc_1400BC5F2
0x1400bc5ef  mov     rcx, r12
0x1400bc5f2  mov     qword ptr [rsp+138h+Irp.Tail+10h], rcx
0x1400bc5fa  call    cs:__imp_IoSetActivityIdThread
0x1400bc601  nop     dword ptr [rax+rax+00h]
0x1400bc606  mov     qword ptr [rsp+138h+Irp.Overlay], rax
0x1400bc60e  xor     r15b, r15b
0x1400bc611  call    cs:__imp_IoGetTopLevelIrp
0x1400bc618  nop     dword ptr [rax+rax+00h]
0x1400bc61d  mov     rsi, rax
0x1400bc620  mov     edx, 18h; RegionSize
0x1400bc625  mov     rcx, rax; RegionStart
0x1400bc628  call    cs:__imp_IoWithinStackLimits
0x1400bc62f  nop     dword ptr [rax+rax+00h]
0x1400bc634  test    eax, eax
0x1400bc636  jz      short loc_1400BC653
0x1400bc638  test    sil, 3
0x1400bc63c  jnz     short loc_1400BC653
0x1400bc63e  movzx   r15d, r15b
0x1400bc642  cmp     dword ptr [rsi+4], 5346ABBAh
0x1400bc649  mov     r8d, 1
0x1400bc64f  cmovz   r15d, r8d
0x1400bc653  mov     dword ptr [rsp+138h+Irp+4], r12d
0x1400bc658  mov     [rsp+138h+Irp.MdlAddress], rsi
0x1400bc65d  mov     qword ptr [rsp+138h+Irp.Flags], r12
0x1400bc662  mov     byte ptr [rsp+138h+Irp.Type], 1
0x1400bc667  test    r15b, r15b
0x1400bc66a  jz      short loc_1400BC67B
0x1400bc66c  mov     byte ptr [rsp+138h+Irp.Type+1], 1
0x1400bc671  movzx   eax, byte ptr [rsi+2]
0x1400bc675  mov     byte ptr [rsp+138h+Irp.Size], al
0x1400bc679  jmp     short loc_1400BC682
0x1400bc67b  mov     [rsp+138h+Irp.Type+1], 0
0x1400bc682  lea     rax, [rsp+138h+Irp]
0x1400bc687  mov     [rsp+138h+Irp.IoStatus.Information], rax
0x1400bc68f  test    rbx, rbx
0x1400bc692  jz      loc_1400BC71A
0x1400bc698  mov     dword ptr [rsp+138h+Irp.Tail], 10h
0x1400bc6a3  mov     qword ptr [rsp+138h+Irp.Tail+4], 0FFFFh
0x1400bc6af  mov     dword ptr [rsp+138h+Irp.Tail+0Ch], 2
0x1400bc6ba  mov     r8, gs:188h; Thread
0x1400bc6c3  lea     r9, [rsp+138h+Irp.Tail]; PriorityInfo
0x1400bc6cb  xor     edx, edx; FileObject
0x1400bc6cd  xor     ecx, ecx; Irp
0x1400bc6cf  call    cs:__imp_IoRetrievePriorityInfo
0x1400bc6d6  nop     dword ptr [rax+rax+00h]
0x1400bc6db  test    eax, eax
0x1400bc6dd  js      short loc_1400BC70A
0x1400bc6df  mov     rcx, rbx; Irp
0x1400bc6e2  call    cs:__imp_IoGetIoPriorityHint
0x1400bc6e9  nop     dword ptr [rax+rax+00h]
0x1400bc6ee  mov     rcx, gs:188h
0x1400bc6f7  mov     edx, eax
0x1400bc6f9  call    cs:__imp_IoSetIoPriorityHintIntoThread
0x1400bc700  nop     dword ptr [rax+rax+00h]
0x1400bc705  mov     [rsp+138h+var_105], 1
0x1400bc70a  mov     edi, r12d
0x1400bc70d  mov     [rsp+138h+var_100], r12d
0x1400bc712  mov     rax, [rsp+138h+Irp.IoStatus.Information]
0x1400bc71a  inc     cs:?RefsPostRequests@@3KA; ulong RefsPostRequests
0x1400bc720  cmp     qword ptr [rsp+138h+Irp.Flags], 0
0x1400bc726  jnz     short loc_1400BC74C
0x1400bc728  mov     dword ptr [rsp+138h+Irp+4], 5346ABBAh
0x1400bc730  mov     qword ptr [rsp+138h+Irp.Flags], r14
0x1400bc735  or      qword ptr [r14+8], 100000h
0x1400bc73d  mov     rcx, rax; Irp
0x1400bc740  call    cs:__imp_IoSetTopLevelIrp
0x1400bc747  nop     dword ptr [rax+rax+00h]
0x1400bc74c  mov     rax, qword ptr [rsp+138h+Irp.Flags]
0x1400bc751  mov     [r14+68h], rax
0x1400bc755  mov     eax, [r14+8]
0x1400bc759  bt      rax, 0Dh
0x1400bc75e  movzx   eax, byte ptr [rsp+138h+Irp.Type]
0x1400bc763  cmovb   eax, r12d
0x1400bc767  mov     byte ptr [rsp+138h+Irp.Type], al
0x1400bc76b  mov     [rsp+138h+var_107], 0
0x1400bc770  mov     [r14+10h], r12d
0x1400bc774  or      qword ptr [r14+8], 40h
0x1400bc779  cmp     [rsp+138h+var_E8], 0
0x1400bc77f  jz      short loc_1400BC790
0x1400bc781  cmp     [rsp+138h+var_F8], 0
0x1400bc786  jnz     short loc_1400BC790
0x1400bc788  or      dword ptr [r14+4], 8000000h
0x1400bc790  cmp     edi, 0C0000188h
0x1400bc796  jz      short loc_1400BC79D
0x1400bc798  test    rbx, rbx
0x1400bc79b  jnz     short loc_1400BC7C1
0x1400bc79d  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400bc7a0  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x1400bc7a5  mov     eax, [rsp+138h+var_EC]
0x1400bc7a9  inc     eax
0x1400bc7ab  mov     [rsp+138h+var_EC], eax
0x1400bc7af  cmp     eax, 2
0x1400bc7b2  jb      short loc_1400BC7B9
0x1400bc7b4  or      dword ptr [r14+4], 10h
0x1400bc7b9  mov     edi, r12d
0x1400bc7bc  mov     [rsp+138h+var_100], r12d
0x1400bc7c1  mov     ecx, edi
0x1400bc7c3  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x1400bc7ca  nop     dword ptr [rax+rax+00h]
0x1400bc7cf  test    al, al
0x1400bc7d1  jz      short loc_1400BC7F7
0x1400bc7d3  mov     qword ptr [rsp+138h+Irp.AssociatedIrp], r12
0x1400bc7d8  mov     eax, 8
0x1400bc7dd  mov     word ptr [rsp+138h+Irp.AssociatedIrp], ax
0x1400bc7e2  mov     dword ptr [rsp+138h+Irp.AssociatedIrp+4], edi
0x1400bc7e6  lea     rcx, [rsp+138h+Irp.AssociatedIrp]
0x1400bc7eb  call    cs:__imp_CcErrorCallbackRoutine
0x1400bc7f2  nop     dword ptr [rax+rax+00h]
0x1400bc7f7  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400bc7fa  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x1400bc7ff  test    rbx, rbx
0x1400bc802  jz      loc_1400BCB01
0x1400bc808  movzx   eax, byte ptr [r14+28h]
0x1400bc80d  cmp     eax, 15h; switch 22 cases
0x1400bc810  ja      def_1400BC827; jumptable 00000001400BC827 default case, cases 1,7,8,15,16,19
0x1400bc816  lea     rdx, cs:140000000h
0x1400bc81d  mov     ecx, ds:(jpt_1400BC827 - 140000000h)[rdx+rax*4]
0x1400bc824  add     rcx, rdx
0x1400bc827  jmp     rcx; switch jump
0x1400bc82d  and     qword ptr [r14+8], 0FFFFFFFFFFFFFFFDh; jumptable 00000001400BC827 case 0
0x1400bc832  mov     r12, [r14+90h]
0x1400bc839  test    dword ptr [r12+90h], 100000h
0x1400bc845  jz      short loc_1400BC89C
0x1400bc847  mov     rax, [r14+40h]
0x1400bc84b  mov     rsi, [rax+70h]
0x1400bc84f  lea     rcx, [rsi+0FF8h]; SpinLock
0x1400bc856  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bc85d  nop     dword ptr [rax+rax+00h]
0x1400bc862  movzx   edx, al; NewIrql
0x1400bc865  lea     rcx, [rsi+0FF8h]; SpinLock
0x1400bc86c  call    cs:__imp_KeReleaseSpinLock
0x1400bc873  nop     dword ptr [rax+rax+00h]
0x1400bc878  lea     rcx, [rsi+1018h]; Object
0x1400bc87f  mov     [rsp+138h+Timeout], 0; Timeout
0x1400bc888  xor     r9d, r9d; Alertable
0x1400bc88b  xor     r8d, r8d; WaitMode
0x1400bc88e  xor     edx, edx; WaitReason
0x1400bc890  call    cs:__imp_KeWaitForSingleObject
0x1400bc897  nop     dword ptr [rax+rax+00h]
0x1400bc89c  xor     edx, edx; Val
0x1400bc89e  mov     r8d, 0D8h; Size
0x1400bc8a4  mov     rcx, r12; void *
0x1400bc8a7  call    memset
0x1400bc8ac  mov     rax, [rbx+0B8h]
0x1400bc8b3  mov     [r12+0A0h], rax
0x1400bc8bb  mov     eax, [r14+8]
0x1400bc8bf  mov     r8, r12; struct _CREATE_CONTEXT *
0x1400bc8c2  mov     rdx, rbx; Irp
0x1400bc8c5  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400bc8c8  bt      rax, 9
0x1400bc8cd  jnb     short loc_1400BC8E2
0x1400bc8cf  call    ?RefsCommonVolumeOpen@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonVolumeOpen(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x1400bc8d4  mov     edi, eax
0x1400bc8d6  mov     [rsp+138h+var_100], eax
0x1400bc8da  xor     r12d, r12d
0x1400bc8dd  jmp     loc_1400BCB16
0x1400bc8e2  call    ?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonCreate(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x1400bc8e7  mov     edi, eax
0x1400bc8e9  mov     [rsp+138h+var_100], eax
0x1400bc8ed  xor     r12d, r12d
0x1400bc8f0  jmp     loc_1400BCB16
0x1400bc8f5  lea     rax, WPP_GLOBAL_Control; jumptable 00000001400BC827 case 2
0x1400bc8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc903  cmp     rcx, rax
0x1400bc906  jz      short loc_1400BC92A
0x1400bc908  mov     eax, [rcx+2Ch]
0x1400bc90b  test    al, 1
0x1400bc90d  jz      short loc_1400BC92A
0x1400bc90f  cmp     byte ptr [rcx+29h], 2
0x1400bc913  jb      short loc_1400BC92A
0x1400bc915  mov     edx, 0Ah
0x1400bc91a  lea     r8, WPP_1e930544d89f3ce82d53e09c7070df23_Traceguids
0x1400bc921  mov     rcx, [rcx+18h]
0x1400bc925  call    WPP_SF_
0x1400bc92a  mov     [rsp+138h+Timeout], r12; BugCheckParameter4
0x1400bc92f  xor     r9d, r9d; BugCheckParameter3
0x1400bc932  xor     r8d, r8d; BugCheckParameter2
0x1400bc935  mov     edx, 130184h; BugCheckParameter1
0x1400bc93a  mov     ecx, 149h; BugCheckCode
0x1400bc93f  call    cs:__imp_KeBugCheckEx
0x1400bc94b  lea     rsi, [r14+320h]; jumptable 00000001400BC827 case 3
0x1400bc952  mov     qword ptr [rsp+138h+Irp.IoStatus], rsi
0x1400bc95a  mov     eax, [r14+8]
0x1400bc95e  mov     rdx, rsi; struct REFS_IO_CONTEXT *
0x1400bc961  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400bc964  bt      rax, 0Ch
0x1400bc969  jnb     short loc_1400BC978
0x1400bc96b  mov     r8, rbx; struct _IRP *
0x1400bc96e  call    ?RefsCommonIoCompletionWorker@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z; RefsCommonIoCompletionWorker(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)
0x1400bc973  jmp     loc_1400BCB16
0x1400bc978  mov     r9d, [rbx+10h]
0x1400bc97c  shr     r9d, 1
0x1400bc97f  and     r9b, 1; bool
0x1400bc983  call    ?RefsInitializeIoContext@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@_N2@Z; RefsInitializeIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,bool,bool)
0x1400bc988  mov     r8, rbx; struct _IRP *
0x1400bc98b  mov     rdx, rsi; struct REFS_IO_CONTEXT *
0x1400bc98e  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400bc991  call    ?RefsCommonRead@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z; RefsCommonRead(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)
0x1400bc996  jmp     loc_1400BCB16
0x1400bc99b  lea     rsi, [r14+320h]; jumptable 00000001400BC827 case 4
0x1400bc9a2  mov     qword ptr [rsp+138h+Irp.IoStatus], rsi
0x1400bc9aa  mov     eax, [r14+8]
  ... truncated ...
```
