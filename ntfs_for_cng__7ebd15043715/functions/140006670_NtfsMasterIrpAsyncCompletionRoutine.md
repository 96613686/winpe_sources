# NtfsMasterIrpAsyncCompletionRoutine

- ea: `0x140006670`
- end: `0x140007664`
- name: `NtfsMasterIrpAsyncCompletionRoutine`
- size: `4084`
- prototype: `__int64 __fastcall(__int64, IRP *, unsigned int *)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400054e8`
- `0x140005768`
- `0x140005aec`
- `0x140005f00`
- `0x140006670`
- `0x140007900`
- `0x140007ea0`
- `0x1400082b0`
- `0x140008740`
- `0x140009710`
- `0x1400105d4`
- `0x140010670`
- `0x14001072c`
- `0x140010788`
- `0x140017030`
- `0x1400281ac`
- `0x14002c240`
- `0x14002f558`
- `0x1400346b4`
- `0x140038e9c`
- `0x14003c2f0`
- `0x140040f4c`
- `0x140045208`
- `0x140059250`
- `0x1400596c0`
- `0x140188ce4`
- `0x1401e72e8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14000706d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000706d`
- `ntoskrnl!KeSetEvent` at `0x1400069e0`
- `ntoskrnl!KeSetEvent` at `0x14005ce1c`
- `ntoskrnl!KeSetEvent` at `0x14005ceab`
- `ntoskrnl!KeSetEvent` at `0x1400069e0`
- `ntoskrnl!KeSetEvent` at `0x14005ce1c`
- `ntoskrnl!KeSetEvent` at `0x14005ceab`
- `ntoskrnl!ZwClose` at `0x1400070f0`
- `ntoskrnl!ZwClose` at `0x1400070f0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006f20`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006f20`
- `ntoskrnl!PsCreateSystemThread` at `0x1400070d5`
- `ntoskrnl!PsCreateSystemThread` at `0x1400070d5`
- `ntoskrnl!IoBuildPartialMdl` at `0x140006c9b`
- `ntoskrnl!IoBuildPartialMdl` at `0x140006c9b`
- `ntoskrnl!MmUnmapLockedPages` at `0x140006ce1`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000721e`
- `ntoskrnl!MmUnmapLockedPages` at `0x140006ce1`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000721e`
- `ntoskrnl!IoFreeMdl` at `0x14000722d`
- `ntoskrnl!IoFreeMdl` at `0x14000722d`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140007595`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140007595`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140006edf`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140006edf`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000725d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000725d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006a41`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006e68`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006a41`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140006e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000680b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006de3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000680b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006de3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140006f02`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140006f02`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007336`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007336`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000690e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006b40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000690e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006b40`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000689e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006ad0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000689e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006ad0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006e15`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400073f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140006e15`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400073f5`

## pseudocode

```c
__int64 __fastcall NtfsMasterIrpAsyncCompletionRoutine(__int64 a1, IRP *a2, unsigned int *a3)
{
  struct _ERESOURCE *v3; // r12
  __int64 v4; // r10
  __int64 v5; // rcx
  ERESOURCE_THREAD v6; // rax
  char v7; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  NTSTATUS v11; // ecx
  unsigned int v12; // r11d
  PFILE_OBJECT FileObject; // r9
  __int64 v14; // r10
  unsigned int v15; // ecx
  KSPIN_LOCK *v16; // rdi
  __int64 p_Flags; // r14
  void *v18; // rcx
  struct _MDL *v19; // rax
  void *v20; // rcx
  __int64 v21; // rdx
  bool v22; // zf
  int v23; // ecx
  KSPIN_LOCK **v24; // rax
  KSPIN_LOCK *v25; // r15
  KSPIN_LOCK v26; // r14
  KSPIN_LOCK *v27; // rcx
  __int64 v28; // r12
  KSPIN_LOCK v29; // r12
  _QWORD *v30; // rdx
  _QWORD *v31; // r10
  unsigned __int64 i; // r9
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rcx
  KSPIN_LOCK v37; // r12
  int v38; // r14d
  KSPIN_LOCK *v39; // r13
  __int64 v40; // rdx
  unsigned __int8 v41; // r9
  unsigned __int16 v42; // r8
  unsigned __int16 v43; // dx
  __int64 v45; // rax
  KSPIN_LOCK **v46; // rax
  KSPIN_LOCK *v47; // r15
  KSPIN_LOCK v48; // r14
  __int64 v49; // r12
  KSPIN_LOCK v50; // r12
  _QWORD *v51; // rdx
  _QWORD *v52; // r10
  unsigned __int64 j; // r9
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // rax
  __int64 v57; // rcx
  KSPIN_LOCK v58; // r12
  KSPIN_LOCK *v59; // r15
  KSPIN_LOCK *v60; // r13
  __int64 v61; // rdx
  unsigned __int8 v62; // r9
  PMDL v63; // r15
  void *v64; // r12
  __int64 v65; // rcx
  struct _IO_STACK_LOCATION *v66; // rax
  unsigned int v67; // edx
  unsigned int v68; // r14d
  struct _MDL *MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  KSPIN_LOCK Lock; // rdx
  _QWORD *v72; // r14
  bool v73; // sf
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // rdx
  int v77; // eax
  ERESOURCE_THREAD v78; // rdx
  struct _ERESOURCE *v79; // rcx
  __int64 v80; // r8
  __int64 v81; // rax
  unsigned int v82; // eax
  int Status; // eax
  unsigned __int64 v84; // r12
  KSPIN_LOCK v85; // r15
  int v86; // r12d
  char v87; // al
  __int64 v88; // r8
  int inserted; // eax
  char v90; // al
  __int64 v91; // r8
  int v92; // eax
  KSPIN_LOCK *v93; // r9
  __int64 v94; // [rsp+48h] [rbp-B8h]
  KSPIN_LOCK *v95; // [rsp+48h] [rbp-B8h]
  void *ThreadHandle; // [rsp+50h] [rbp-B0h]
  int v97; // [rsp+58h] [rbp-A8h]
  __int64 v98; // [rsp+60h] [rbp-A0h]
  __int128 v99; // [rsp+68h] [rbp-98h] BYREF
  __int64 v100; // [rsp+78h] [rbp-88h]
  PERESOURCE Resource; // [rsp+80h] [rbp-80h]
  KSPIN_LOCK *v102; // [rsp+88h] [rbp-78h]
  ERESOURCE_THREAD ResourceThreadId; // [rsp+90h] [rbp-70h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+C8h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v105; // [rsp+E0h] [rbp-20h] BYREF
  _MDL TargetMdl[4]; // [rsp+100h] [rbp+0h] BYREF

  v3 = (struct _ERESOURCE *)*((_QWORD *)a3 + 5);
  v4 = a1 + 384;
  v5 = *((_QWORD *)a3 + 4);
  v6 = *((_QWORD *)a3 + 6);
  v7 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v98 = v4;
  v100 = 0;
  LOBYTE(v97) = 0;
  Resource = v3;
  ResourceThreadId = v6;
  if ( v5 )
  {
    v7 = 1;
    if ( CurrentStackLocation->MajorFunction == 3 )
    {
      Status = a2->IoStatus.Status;
      if ( (unsigned int)Status <= 0x40000009 || Status >= 1073741836 )
      {
        v86 = NtfsCopyAlignedMdlDataForRead();
        if ( v86 < 0 )
        {
          if ( NtfsStatusDebugFlags
            && (unsigned int)v86 < 0xFFFFFFED
            && v86 != -1073741802
            && v86 != -1073741807
            && (unsigned int)(v86 + 2147483643) > 1
            && v86 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)v86, 801843);
          }
          a2->IoStatus.Status = v86;
        }
        v3 = Resource;
      }
    }
    a2->MdlAddress = *(PMDL *)(*((_QWORD *)a3 + 4) + 16LL);
    a2->UserBuffer = *(PVOID *)(*((_QWORD *)a3 + 4) + 24LL);
    NtfsCleanupAlignedMdlContext((_QWORD **)a3 + 4);
    LODWORD(v4) = v98;
  }
  v11 = a2->IoStatus.Status;
  if ( (unsigned int)v11 > 0x40000009 && v11 < 1073741836 )
  {
    v82 = *a3;
    if ( (*a3 & 0x42) == 0 )
    {
      if ( v11 == -2147483626 )
      {
LABEL_155:
        if ( !a2->AssociatedIrp.IrpCount )
          NtfsIoFailurePostFileObjectError(v4, (_DWORD)a2, *((_QWORD *)a3 + 11), 0, 0, a2->IoStatus.Status);
        NtfsInitializeIrpContextInternal(a2);
        v100 = 0;
        goto LABEL_13;
      }
      if ( !FsRtlIsTotalDeviceFailure(v11) )
      {
        LODWORD(v4) = v98;
        goto LABEL_155;
      }
      v82 = *a3;
    }
    if ( (v82 & 2) != 0 && a2->IoStatus.Status == -1073741670 && CurrentStackLocation->MajorFunction == 3 )
      ++NtfsFailedHandedOffPagingReads;
    goto LABEL_13;
  }
  if ( v7
    || (memset(TargetMdl, 0, 0xB8u), v66 = a2->Tail.Overlay.CurrentStackLocation, v66->MajorFunction != 3)
    || (v67 = a3[14],
        v68 = -*(_DWORD *)&v66->DeviceObject[2].StackSize & (*(_DWORD *)&v66->DeviceObject[2].StackSize + v67 - 1),
        v68 <= v67) )
  {
LABEL_5:
    a2->IoStatus.Information = a3[14];
    v12 = *a3;
    if ( (*a3 & 2) == 0 )
    {
      FileObject = CurrentStackLocation->FileObject;
      if ( FileObject )
      {
        v14 = *((_QWORD *)a3 + 9);
        if ( CurrentStackLocation->MajorFunction == 3 )
        {
          if ( (v12 & 0x800) != 0 && v14 && (*(_WORD *)(v14 + 4) & 1) == 0 )
            _InterlockedOr16((volatile signed __int16 *)(v14 + 4), 1u);
          FileObject->Flags |= 0x80000u;
        }
        else
        {
          if ( v14 )
          {
            v42 = (v12 >> 11) & 1 | 2;
            if ( (v12 & 0x200) == 0 )
              v42 = (v12 >> 11) & 1;
            v43 = v42 | 4;
            if ( (v12 & 0x400) == 0 )
              v43 = v42;
            SetFlagInterlocked16((void *)(v14 + 4), v43);
          }
          FileObject->Flags |= 0x1000u;
        }
      }
    }
    goto LABEL_13;
  }
  MdlAddress = a2->MdlAddress;
  *(_DWORD *)&TargetMdl[0].Size = 176;
  TargetMdl[0].StartVa = 0;
  *(_QWORD *)&TargetMdl[0].ByteCount = 0x10000;
  IoBuildPartialMdl(MdlAddress, TargetMdl, (char *)MdlAddress->StartVa + v67 + MdlAddress->ByteOffset, v68 - v67);
  if ( (TargetMdl[0].MdlFlags & 5) != 0 )
    MappedSystemVa = TargetMdl[0].MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(TargetMdl, 0, MmCached, 0, 0, 0x40000010u);
  if ( MappedSystemVa )
  {
    memset(MappedSystemVa, 0, v68 - a3[14]);
    if ( (TargetMdl[0].MdlFlags & 0x20) != 0 )
      MmUnmapLockedPages(TargetMdl[0].MappedSystemVa, TargetMdl);
    goto LABEL_5;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 787323);
  a2->IoStatus.Status = -1073741670;
LABEL_13:
  v15 = *a3;
  if ( (*a3 & 0x40) != 0 )
  {
    KeSetEvent((PRKEVENT)(a3 + 2), 1, 0);
    return 3221225494LL;
  }
  v16 = (KSPIN_LOCK *)*((_QWORD *)a3 + 8);
  v102 = v16;
  if ( v16 )
  {
    p_Flags = (__int64)&a2->Tail.Overlay.CurrentStackLocation->DeviceObject[1].Flags;
    if ( !v16[6] )
    {
      v18 = (void *)v16[4];
      if ( !v18 )
        goto LABEL_17;
      if ( v18 != (void *)qword_140095978 && v18 != (void *)qword_140095990 && v18 != (void *)qword_1400959C0 )
      {
        Lock = a2->Tail.Overlay.CurrentStackLocation->DeviceObject[17].DeviceQueue.Lock;
        if ( v18 == *(void **)(Lock + 128) )
          _InterlockedExchange64((volatile __int64 *)(Lock + 8), 0);
        else
          ExFreePoolWithTag(v18, 0);
        goto LABEL_17;
      }
      if ( --dword_140095938 )
        goto LABEL_17;
LABEL_141:
      _InterlockedExchange64(&qword_1400958C0, 0);
      goto LABEL_17;
    }
    a2->MdlAddress->ByteCount = *((_DWORD *)v16 + 10);
    v63 = a2->MdlAddress;
    v64 = (void *)v16[4];
    if ( v63 )
    {
      if ( v63 != (PMDL)qword_140095980
        && v63 != (PMDL)qword_140095998
        && v63 != (PMDL)qword_1400959B0
        && v63 != (PMDL)qword_1400959C8 )
      {
        v81 = *(_QWORD *)(p_Flags + 5512);
        if ( v63 != *(PMDL *)(v81 + 136) || v81 == -128 )
        {
          if ( (v63->MdlFlags & 1) != 0 )
            MmUnmapLockedPages(v63->MappedSystemVa, a2->MdlAddress);
          IoFreeMdl(v63);
        }
      }
    }
    if ( v64 )
    {
      if ( v64 == (void *)qword_140095978 || v64 == (void *)qword_140095990 || v64 == (void *)qword_1400959C0 )
      {
        if ( --dword_140095938 )
          goto LABEL_17;
        goto LABEL_141;
      }
      v65 = *(_QWORD *)(p_Flags + 5512);
      if ( v64 == *(void **)(v65 + 128) )
        _InterlockedExchange64((volatile __int64 *)(v65 + 8), 0);
      else
        ExFreePoolWithTag(v64, 0);
    }
LABEL_17:
    v19 = (struct _MDL *)v16[6];
    if ( v19 )
    {
      a2->MdlAddress = v19;
      a2->UserBuffer = (PVOID)v16[7];
    }
    v20 = (void *)v16[12];
    if ( v20 )
    {
      if ( v20 == (void *)qword_140095978 || v20 == (void *)qword_140095990 || v20 == (void *)qword_1400959C0 )
      {
        if ( !--dword_140095938 )
          _InterlockedExchange64(&qword_1400958C0, 0);
      }
      else
      {
        v21 = *(_QWORD *)(p_Flags + 5512);
        if ( v20 == *(void **)(v21 + 128) )
          _InterlockedExchange64((volatile __int64 *)(v21 + 8), 0);
        else
          ExFreePoolWithTag(v20, 0);
      }
    }
    v22 = *((_DWORD *)v16 + 22) == 8;
    v16[6] = 0;
    v16[7] = 0;
    v16[4] = 0;
    v16[12] = 0;
    *((_DWORD *)v16 + 10) = 0;
    if ( !v22 )
      ExFreePoolWithTag((PVOID)v16[10], 0);
    v23 = *((_DWORD *)v16 + 28);
    if ( (v23 & 3) == 0 )
      goto LABEL_118;
    if ( (v16[14] & 3) == 3 )
    {
      v72 = (_QWORD *)v16[15];
      if ( *v72 )
      {
        v84 = v16[16];
        v85 = v16[17];
        if ( v84 + v85 - 1 < v84 && v85 )
        {
          v38 = -1073741407;
        }
        else if ( (unsigned int)FsLibUnlockRangeShared(v16[15], v16[16], v16[17]) )
        {
          v38 = FsLibUnlockRangeExclusive(v72, v84, v85);
        }
        else
        {
          v38 = 0;
        }
      }
      else
      {
        v38 = -1073741698;
      }
      if ( NtfsStatusDebugFlags )
      {
        v73 = v38 < 0;
        if ( !v38 )
          goto LABEL_116;
        if ( v38 != 294
          && (unsigned int)(v38 - 298) > 1
          && (unsigned int)v38 < 0xFFFFFFED
          && v38 != -1073741608
          && v38 != -1073741802
          && v38 != -1073741807
          && (unsigned int)(v38 + 2147483643) > 1
          && v38 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)v38, 1903345);
        }
      }
    }
    else
    {
      if ( (v23 & 1) != 0 )
      {
        v24 = (KSPIN_LOCK **)v16[15];
        memset(&LockHandle, 0, sizeof(LockHandle));
        v99 = 0;
        v25 = *v24;
        if ( (*v24)[1] )
        {
          v26 = v16[16];
          v27 = *v24;
          v28 = v16[17] - 1;
          *(_QWORD *)&v99 = v26;
          v29 = v26 + v28;
          *((_QWORD *)&v99 + 1) = v29;
          KeAcquireInStackQueuedSpinLock(v27, &LockHandle);
          v30 = (_QWORD *)v25[1];
          v31 = 0;
LABEL_32:
          if ( v30 )
          {
            for ( i = v30[1]; ; i &= ~(1LL << v34) )
            {
              v22 = !_BitScanForward64((unsigned __int64 *)&v33, i);
              if ( v22 )
              {
                v31 = v30;
                v30 = (_QWORD *)*v30;
                goto LABEL_32;
              }
              v34 = (unsigned int)v33;
              v35 = 2 * v33;
              if ( v30[v35 + 2] == v26 && v30[v35 + 3] == v29 )
                break;
            }
            v36 = v30[1] & ~(1LL << v34);
            v30[1] = v36;
            if ( !v36 && v31 )
            {
              *v31 = *v30;
              *v30 = 0;
              ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v30);
            }
            v37 = v25[3];
            v38 = 0;
            if ( v37 )
            {
              v39 = v25 + 3;
              do
              {
                v94 = *(_QWORD *)(v37 + 40);
                if ( (unsigned __int8)AreRangeLocksOverlapping(&v99, v94, v34)
                  && ((v41 = *(_BYTE *)(v37 + 36), (v41 & 2) != 0)
                   || v25[3] == v37
                   || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v25, v40, v41))
                  && ((v41 & 1) == 0
                    ? (v87 = FsLibPrivateSearchArrayForRange(v25[2], v40))
                    : (v87 = FsLibPrivateCheckForExclusiveRangeLockAccess(v25, v40)),
                      v87) )
                {
                  v88 = *(_QWORD *)(v37 + 48);
                  if ( (*(_BYTE *)(v37 + 36) & 1) != 0 )
                    inserted = FsLibPrivateInsertRangeLockExclusive(v25, v94, v88);
                  else
                    inserted = FsLibPrivateInsertRangeLockShared(v25, v94, v88);
                  *(_DWORD *)(v37 + 32) = inserted;
                  *v39 = *(_QWORD *)v37;
                  if ( v37 == v25[4] )
                    v25[4] = (KSPIN_LOCK)v39;
                  KeSetEvent((PRKEVENT)(v37 + 8), 0, 0);
                }
                else
                {
                  v39 = (KSPIN_LOCK *)v37;
                }
                v37 = *v39;
              }
              while ( *v39 );
              v16 = v102;
            }
          }
          else
          {
            v38 = -1073741698;
            if ( v25[3] )
              FsLibPrivateCheckWaitingRangeLocks(v25, v25, &v99);
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        else
        {
          v38 = -1073741698;
        }
        if ( !NtfsStatusDebugFlags || !v38 )
          goto LABEL_115;
        v80 = 1903353;
      }
      else
      {
        if ( (v23 & 2) == 0 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225598LL, 1903365);
          goto LABEL_118;
        }
        v46 = (KSPIN_LOCK **)v16[15];
        memset(&v105, 0, sizeof(v105));
        v99 = 0;
        v47 = *v46;
        v102 = v47;
        if ( v47[2] )
        {
          v48 = v16[16];
          v49 = v16[17] - 1;
          *(_QWORD *)&v99 = v48;
          v50 = v48 + v49;
          *((_QWORD *)&v99 + 1) = v50;
          KeAcquireInStackQueuedSpinLock(v47, &v105);
          v51 = (_QWORD *)v47[2];
          v52 = 0;
LABEL_64:
          if ( v51 )
          {
            for ( j = v51[1]; ; j &= ~(1LL << v55) )
            {
              v22 = !_BitScanForward64((unsigned __int64 *)&v54, j);
              if ( v22 )
              {
                v52 = v51;
                v51 = (_QWORD *)*v51;
                goto LABEL_64;
              }
              v55 = (unsigned int)v54;
              v56 = 2 * v54;
              if ( v51[v56 + 2] == v48 && v51[v56 + 3] == v50 )
                break;
            }
            v57 = v51[1] & ~(1LL << v55);
            v51[1] = v57;
            if ( !v57 && v52 )
            {
              *v52 = *v51;
              *v51 = 0;
              ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v51);
            }
            v58 = v47[3];
            v59 = v47 + 3;
            v38 = 0;
            if ( v58 )
            {
              v60 = v102;
              v95 = v59;
              do
              {
                ThreadHandle = *(void **)(v58 + 40);
                if ( (unsigned __int8)AreRangeLocksOverlapping(&v99, ThreadHandle, v55)
                  && ((v62 = *(_BYTE *)(v58 + 36), (v62 & 2) != 0)
                   || *v59 == v58
                   || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v60, v61, v62))
                  && ((v62 & 1) == 0
                    ? (v90 = FsLibPrivateSearchArrayForRange(v60[2], v61))
                    : (v90 = FsLibPrivateCheckForExclusiveRangeLockAccess(v60, v61)),
                      v90) )
                {
                  v91 = *(_QWORD *)(v58 + 48);
                  if ( (*(_BYTE *)(v58 + 36) & 1) != 0 )
                    v92 = FsLibPrivateInsertRangeLockExclusive(v60, ThreadHandle, v91);
                  else
                    v92 = FsLibPrivateInsertRangeLockShared(v60, ThreadHandle, v91);
                  *(_DWORD *)(v58 + 32) = v92;
                  *v95 = *(_QWORD *)v58;
                  if ( v58 == v60[4] )
                    v60[4] = (KSPIN_LOCK)v95;
                  KeSetEvent((PRKEVENT)(v58 + 8), 0, 0);
                  v93 = v95;
                }
                else
                {
                  v95 = (KSPIN_LOCK *)v58;
                  v93 = (KSPIN_LOCK *)v58;
                }
                v58 = *v93;
              }
              while ( *v93 );
            }
          }
          else
          {
            v38 = -1073741698;
            if ( v47[3] )
              FsLibPrivateCheckWaitingRangeLocks(v47, v47, &v99);
          }
          KeReleaseInStackQueuedSpinLock(&v105);
        }
        else
        {
          v38 = -1073741698;
        }
        if ( !NtfsStatusDebugFlags || !v38 )
          goto LABEL_115;
        v80 = 1903361;
      }
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)v38, v80);
    }
LABEL_115:
    v73 = v38 < 0;
LABEL_116:
    if ( !v73 )
      *((_DWORD *)v16 + 28) &= 0xFFFFFFFC;
LABEL_118:
    v74 = *((_QWORD *)a3 + 8);
    v75 = *(unsigned int *)(v74 - 8);
    if ( (unsigned int)v75 >= NtfsNumberProcessors )
      v75 = (unsigned int)v75 % NtfsNumberProcessors;
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(NtfsCompressCtxLookasideList + 96 * v75), (PVOID)(v74 - 8));
    v15 = *a3;
    v3 = Resource;
    *((_QWORD *)a3 + 8) = 0;
  }
  if ( v3 )
  {
    if ( (v15 & 0x10000) != 0 )
    {
      v76 = *((_QWORD *)a3 + 9);
      *a3 = v15 & 0xFFFEFFFF;
      if ( _InterlockedDecrement((volatile signed __int32 *)(v76 + 384)) != 0x80000000
        || _InterlockedCompareExchange((volatile signed __int32 *)(v76 + 384), 0, 0x80000000) != 0x80000000 )
      {
        goto LABEL_124;
      }
      v79 = (struct _ERESOURCE *)(v76 + 280);
      v78 = (v76 + 280) | 3;
    }
    else
    {
      v78 = ResourceThreadId;
      v79 = v3;
    }
    ExReleaseResourceForThreadLite(v79, v78);
  }
LABEL_124:
  if ( (*a3 & 0x1000) != 0 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)(*(_QWORD *)(v98 + 11784) + 32LL));
  v77 = a2->IoStatus.Status;
  if ( (v77 >= 1073741836 || (unsigned int)v77 <= 0x40000009) && *(_BYTE *)(v98 + 10496) )
    NtfsIoPerfCollectReadWriteData(v98, a2, a3);
  v45 = *(a3 - 2);
  if ( (unsigned int)v45 >= NtfsNumberProcessors )
    v45 = (unsigned int)v45 % NtfsNumberProcessors;
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(NtfsIoContextLookasideList + 96 * v45), a3 - 2);
  return 0;
}

```

## disassembly

```asm
0x140006670  mov     [rsp-8+arg_18], rbx
0x140006675  push    rbp
0x140006676  push    rsi
0x140006677  push    rdi
0x140006678  push    r12
0x14000667a  push    r13
0x14000667c  push    r14
0x14000667e  push    r15
0x140006680  lea     rbp, [rsp-0D0h]
0x140006688  sub     rsp, 1D0h
0x14000668f  mov     rax, cs:__security_cookie
0x140006696  xor     rax, rsp
0x140006699  mov     [rbp+100h+var_40], rax
0x1400066a0  mov     r12, [r8+28h]
0x1400066a4  lea     r10, [rcx+180h]
0x1400066ab  mov     rcx, [r8+20h]
0x1400066af  xor     r13d, r13d
0x1400066b2  mov     rax, [r8+30h]
0x1400066b6  xor     r15b, r15b
0x1400066b9  mov     rdi, [rdx+0B8h]
0x1400066c0  mov     rbx, r8
0x1400066c3  mov     [rsp+200h+var_1A0], r10
0x1400066c8  mov     rsi, rdx
0x1400066cb  mov     [rsp+200h+var_188], r13
0x1400066d0  mov     [rsp+200h+var_1B8], r13
0x1400066d5  mov     [rsp+200h+var_1C0], 1
0x1400066da  mov     byte ptr [rsp+200h+var_1A8], r13b
0x1400066df  mov     [rbp+100h+Resource], r12
0x1400066e3  mov     [rbp+100h+ResourceThreadId], rax
0x1400066e7  test    rcx, rcx
0x1400066ea  jnz     loc_140007477
0x1400066f0  mov     ecx, [rsi+30h]; Status
0x1400066f3  cmp     ecx, 40000009h
0x1400066f9  jbe     short loc_140006707
0x1400066fb  cmp     ecx, 4000000Ch
0x140006701  jl      loc_14000726E
0x140006707  test    r15b, r15b
0x14000670a  jz      loc_140006C2C
0x140006710  mov     eax, [rbx+38h]
0x140006713  mov     [rsi+38h], rax
0x140006717  mov     r11d, [rbx]
0x14000671a  test    r11b, 2
0x14000671e  jnz     short loc_14000675E
0x140006720  mov     r9, [rdi+30h]
0x140006724  test    r9, r9
0x140006727  jz      short loc_14000675E
0x140006729  cmp     byte ptr [rdi], 3
0x14000672c  mov     r10, [rbx+48h]
0x140006730  jnz     loc_140006986
0x140006736  bt      r11d, 0Bh
0x14000673b  jnb     short loc_140006752
0x14000673d  test    r10, r10
0x140006740  jz      short loc_140006752
0x140006742  movzx   eax, word ptr [r10+4]
0x140006747  test    al, 1
0x140006749  jnz     short loc_140006752
0x14000674b  lock or word ptr [r10+4], 1
0x140006752  mov     eax, [r9+50h]
0x140006756  bts     eax, 13h
0x14000675a  mov     [r9+50h], eax
0x14000675e  mov     ecx, [rbx]
0x140006760  test    cl, 40h
0x140006763  jnz     loc_1400069D4
0x140006769  mov     rdi, [rbx+40h]
0x14000676d  mov     [rbp+100h+var_178], rdi
0x140006771  test    rdi, rdi
0x140006774  jz      loc_1400073C4
0x14000677a  test    r13, r13
0x14000677d  jnz     loc_14000697D
0x140006783  mov     rax, [rsi+0B8h]
0x14000678a  mov     r14, [rax+28h]
0x14000678e  add     r14, 180h
0x140006795  cmp     qword ptr [rdi+30h], 0
0x14000679a  jnz     loc_140006BB7
0x1400067a0  mov     rcx, [rdi+20h]; P
0x1400067a4  test    rcx, rcx
0x1400067a7  jnz     loc_140006CF2
0x1400067ad  xor     r15d, r15d
0x1400067b0  mov     rax, [rdi+30h]
0x1400067b4  test    rax, rax
0x1400067b7  jz      short loc_1400067C5
0x1400067b9  mov     [rsi+8], rax
0x1400067bd  mov     rax, [rdi+38h]
0x1400067c1  mov     [rsi+70h], rax
0x1400067c5  mov     rcx, [rdi+60h]; P
0x1400067c9  test    rcx, rcx
0x1400067cc  jz      short loc_140006817
0x1400067ce  cmp     rcx, cs:qword_140095978
0x1400067d5  jz      loc_14000715F
0x1400067db  cmp     rcx, cs:qword_140095990
0x1400067e2  jz      loc_14000715F
0x1400067e8  cmp     rcx, cs:qword_1400959C0
0x1400067ef  jz      loc_14000715F
0x1400067f5  mov     rdx, [r14+1588h]
0x1400067fc  cmp     rcx, [rdx+80h]
0x140006803  jz      loc_14000744D
0x140006809  xor     edx, edx; Tag
0x14000680b  call    cs:__imp_ExFreePoolWithTag
0x140006812  nop     dword ptr [rax+rax+00h]
0x140006817  cmp     dword ptr [rdi+58h], 8
0x14000681b  mov     [rdi+30h], r15
0x14000681f  mov     [rdi+38h], r15
0x140006823  mov     [rdi+20h], r15
0x140006827  mov     [rdi+60h], r15
0x14000682b  mov     [rdi+28h], r15d
0x14000682f  jnz     loc_140006DDD
0x140006835  mov     ecx, [rdi+70h]
0x140006838  mov     eax, ecx
0x14000683a  and     eax, 3
0x14000683d  jz      loc_140006E3C
0x140006843  cmp     eax, 3
0x140006846  jz      loc_140006D40
0x14000684c  test    cl, 1
0x14000684f  jz      loc_140006A7A
0x140006855  xor     eax, eax
0x140006857  xorps   xmm0, xmm0
0x14000685a  mov     qword ptr [rbp+100h+LockHandle.OldIrql], rax
0x14000685e  mov     rax, [rdi+78h]
0x140006862  movups  xmmword ptr [rbp+100h+LockHandle.LockQueue.Next], xmm0
0x140006866  movups  [rsp+200h+var_198], xmm0
0x14000686b  mov     r15, [rax]
0x14000686e  cmp     qword ptr [r15+8], 0
0x140006873  jz      loc_140007347
0x140006879  mov     r14, [rdi+80h]
0x140006880  lea     rdx, [rbp+100h+LockHandle]; LockHandle
0x140006884  mov     r12, [rdi+88h]
0x14000688b  mov     rcx, r15; SpinLock
0x14000688e  dec     r12
0x140006891  mov     qword ptr [rsp+200h+var_198], r14
0x140006896  add     r12, r14
0x140006899  mov     qword ptr [rsp+200h+var_198+8], r12
0x14000689e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400068a5  nop     dword ptr [rax+rax+00h]
0x1400068aa  mov     rdx, [r15+8]; Entry
0x1400068ae  xor     r10d, r10d
0x1400068b1  mov     dword ptr [rsp+200h+var_1B8], r10d
0x1400068b6  test    rdx, rdx
0x1400068b9  jz      loc_140006DF4
0x1400068bf  mov     rcx, [rdx+8]
0x1400068c3  mov     r9, rcx
0x1400068c6  bsf     rax, r9
0x1400068ca  jz      loc_14000710F
0x1400068d0  mov     r8d, eax
0x1400068d3  add     rax, rax
0x1400068d6  cmp     [rdx+rax*8+10h], r14
0x1400068db  jnz     loc_14000723E
0x1400068e1  cmp     [rdx+rax*8+18h], r12
0x1400068e6  jnz     loc_14000723E
0x1400068ec  btr     rcx, r8
0x1400068f0  mov     [rdx+8], rcx
0x1400068f4  test    rcx, rcx
0x1400068f7  jnz     short loc_14000691A
0x1400068f9  test    r10, r10
0x1400068fc  jz      short loc_14000691A
0x1400068fe  mov     rax, [rdx]
0x140006901  mov     [r10], rax
0x140006904  mov     [rdx], rcx
0x140006907  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x14000690e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006915  nop     dword ptr [rax+rax+00h]
0x14000691a  mov     r12, [r15+18h]
0x14000691e  xor     r14d, r14d
0x140006921  test    r12, r12
0x140006924  jz      loc_140006E11
0x14000692a  lea     r13, [r15+18h]
0x14000692e  mov     rdx, [r12+28h]
0x140006933  lea     rcx, [rsp+200h+var_198]
0x140006938  mov     [rsp+200h+var_1B8], rdx
0x14000693d  call    AreRangeLocksOverlapping
0x140006942  test    al, al
0x140006944  jz      loc_14005CE2A
0x14000694a  movzx   r9d, byte ptr [r12+24h]
0x140006950  test    r9b, 2
0x140006954  jnz     loc_14005CDBD
0x14000695a  cmp     [r15+18h], r12
0x14000695e  jz      loc_14005CDBD
0x140006964  movzx   r8d, r9b
0x140006968  mov     rcx, r15
0x14000696b  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140006970  test    al, al
0x140006972  jnz     loc_14005CDBD
0x140006978  jmp     loc_14005CE2A
0x14000697d  mov     r14, [r13+68h]
0x140006981  jmp     loc_140006795
0x140006986  test    r10, r10
0x140006989  jz      short loc_1400069C3
0x14000698b  mov     ecx, r11d
0x14000698e  shr     ecx, 0Bh
0x140006991  and     cx, 1
0x140006995  movzx   r8d, cx
0x140006999  or      r8w, 2
0x14000699e  bt      r11d, 9
0x1400069a3  cmovnb  r8w, cx
0x1400069a8  lea     rcx, [r10+4]
0x1400069ac  movzx   edx, r8w
0x1400069b0  or      dx, 4
0x1400069b4  bt      r11d, 0Ah
0x1400069b9  cmovnb  dx, r8w
0x1400069be  call    SetFlagInterlocked16
0x1400069c3  mov     ecx, [r9+50h]
0x1400069c7  bts     ecx, 0Ch
0x1400069cb  mov     [r9+50h], ecx
0x1400069cf  jmp     loc_14000675E
0x1400069d4  lea     rcx, [rbx+8]; Event
0x1400069d8  xor     r8d, r8d; Wait
0x1400069db  mov     edx, 1; Increment
0x1400069e0  call    cs:__imp_KeSetEvent
0x1400069e7  nop     dword ptr [rax+rax+00h]
0x1400069ec  movzx   ecx, cs:NtfsStatusDebugFlags
0x1400069f3  mov     eax, 0C0000016h
0x1400069f8  jmp     short loc_140006A4F
0x1400069fa  cmp     eax, 40000009h
0x1400069ff  ja      short loc_140006A1A
0x140006a01  movzx   eax, byte ptr [rdi+2900h]
0x140006a08  test    al, al
0x140006a0a  jz      short loc_140006A1A
0x140006a0c  mov     r8, rbx
0x140006a0f  mov     rdx, rsi
0x140006a12  mov     rcx, rdi
0x140006a15  call    NtfsIoPerfCollectReadWriteData
0x140006a1a  mov     eax, [rbx-8]
0x140006a1d  mov     ecx, cs:NtfsNumberProcessors
0x140006a23  mov     r8, cs:NtfsIoContextLookasideList
0x140006a2a  cmp     eax, ecx
0x140006a2c  jnb     loc_1400071B5
0x140006a32  lea     rcx, [rax+rax*2]
0x140006a36  shl     rcx, 5
0x140006a3a  lea     rdx, [rbx-8]; Entry
0x140006a3e  add     rcx, r8; Lookaside
0x140006a41  call    cs:__imp_ExFreeToLookasideListEx
0x140006a48  nop     dword ptr [rax+rax+00h]
0x140006a4d  xor     eax, eax
0x140006a4f  mov     rcx, [rbp+100h+var_40]
0x140006a56  xor     rcx, rsp; StackCookie
0x140006a59  call    __security_check_cookie
0x140006a5e  mov     rbx, [rsp+200h+arg_18]
0x140006a66  add     rsp, 1D0h
0x140006a6d  pop     r15
0x140006a6f  pop     r14
0x140006a71  pop     r13
0x140006a73  pop     r12
0x140006a75  pop     rdi
0x140006a76  pop     rsi
0x140006a77  pop     rbp
0x140006a78  retn
0x140006a7a  test    cl, 2
0x140006a7d  jz      loc_140007139
0x140006a83  xor     eax, eax
0x140006a85  xorps   xmm0, xmm0
0x140006a88  mov     qword ptr [rbp+100h+var_120.OldIrql], rax
0x140006a8c  mov     rax, [rdi+78h]
0x140006a90  movups  xmmword ptr [rbp+100h+var_120.LockQueue.Next], xmm0
0x140006a94  movups  [rsp+200h+var_198], xmm0
0x140006a99  mov     r15, [rax]
0x140006a9c  mov     [rbp+100h+var_178], r15
0x140006aa0  cmp     qword ptr [r15+10h], 0
0x140006aa5  jz      loc_1400073CC
0x140006aab  mov     r14, [rdi+80h]
0x140006ab2  lea     rdx, [rbp+100h+var_120]; LockHandle
0x140006ab6  mov     r12, [rdi+88h]
0x140006abd  mov     rcx, r15; SpinLock
0x140006ac0  dec     r12
0x140006ac3  mov     qword ptr [rsp+200h+var_198], r14
0x140006ac8  add     r12, r14
0x140006acb  mov     qword ptr [rsp+200h+var_198+8], r12
0x140006ad0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140006ad7  nop     dword ptr [rax+rax+00h]
0x140006adc  mov     rdx, [r15+10h]; Entry
0x140006ae0  xor     r10d, r10d
0x140006ae3  mov     dword ptr [rsp+200h+var_1B8], r10d
0x140006ae8  test    rdx, rdx
0x140006aeb  jz      loc_1400073D4
0x140006af1  mov     rcx, [rdx+8]
0x140006af5  mov     r9, rcx
0x140006af8  bsf     rax, r9
0x140006afc  jz      loc_140007247
0x140006b02  mov     r8d, eax
0x140006b05  add     rax, rax
0x140006b08  cmp     [rdx+rax*8+10h], r14
0x140006b0d  jnz     loc_140007311
0x140006b13  cmp     [rdx+rax*8+18h], r12
0x140006b18  jnz     loc_140007311
0x140006b1e  btr     rcx, r8
0x140006b22  mov     [rdx+8], rcx
0x140006b26  test    rcx, rcx
0x140006b29  jnz     short loc_140006B4C
0x140006b2b  test    r10, r10
0x140006b2e  jz      short loc_140006B4C
0x140006b30  mov     rax, [rdx]
0x140006b33  mov     [r10], rax
0x140006b36  mov     [rdx], rcx
0x140006b39  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140006b40  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006b47  nop     dword ptr [rax+rax+00h]
0x140006b4c  mov     r12, [r15+18h]
0x140006b50  add     r15, 18h
0x140006b54  xor     r14d, r14d
0x140006b57  test    r12, r12
0x140006b5a  jz      loc_1400073F1
0x140006b60  mov     r13, [rbp+100h+var_178]
  ... truncated ...
```
