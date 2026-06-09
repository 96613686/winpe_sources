# RefsPerformDismountOnVcb(_IRP_CONTEXT *,_VCB *,uchar,uchar,_REFS_DISMOUNT_REASON,_VPB * *)

- ea: `0x1402e6f54`
- end: `0x1402e7bd1`
- name: `?RefsPerformDismountOnVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@EEW4_REFS_DISMOUNT_REASON@@PEAPEAU_VPB@@@Z`
- size: `3197`
- prototype: ``
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b2b60`
- `0x140287c68`
- `0x1402ab528`
- `0x1402b0e80`
- `0x1402c1868`
- `0x1402c7540`
- `0x140314de0`
- `0x140321a64`

## callees

- `0x14000bcc0`
- `0x1400548b0`
- `0x140080680`
- `0x14008faf0`
- `0x14008fc50`
- `0x1400913a0`
- `0x14009bb80`
- `0x1400a23e0`
- `0x1400afb00`
- `0x1400b00b0`
- `0x1400b0128`
- `0x1400b11b4`
- `0x1400f130c`
- `0x140104eb8`
- `0x14010525c`
- `0x140113ee0`
- `0x1401143a4`
- `0x140115584`
- `0x140115dec`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x1402864ec`
- `0x140289be8`
- `0x1402e593c`
- `0x1402e6f54`
- `0x1402fed30`
- `0x1403012f0`
- `0x14031b640`
- `0x140327ba0`
- `0x140331020`
- `0x140337e0c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1402e7ba1`
- `ntoskrnl!ObfDereferenceObject` at `0x140346d66`
- `ntoskrnl!ObfDereferenceObject` at `0x1402e7ba1`
- `ntoskrnl!ObfDereferenceObject` at `0x140346d66`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402e77c1`
- `ntoskrnl!IoGetActivityIdThread` at `0x1403469b3`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402e77c1`
- `ntoskrnl!IoGetActivityIdThread` at `0x1403469b3`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402e73b8`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402e7448`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402e73b8`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402e7448`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402e792e`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140346afc`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402e792e`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140346afc`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402e7175`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402e7175`
- `ntoskrnl!FsRtlDedupChangeUninit` at `0x1402e702f`
- `ntoskrnl!FsRtlDedupChangeUninit` at `0x1402e702f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402e7801`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1403469f3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402e7801`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1403469f3`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402e7916`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140346ae5`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402e7916`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140346ae5`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e75fb`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402e75fb`
- `ntoskrnl!PcwCloseInstance` at `0x1402e7099`
- `ntoskrnl!PcwCloseInstance` at `0x1402e7099`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1402e704c`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1402e704c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e760b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402e760b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140346935`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140346935`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e7641`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402e7641`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e764d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402e764d`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e71d7`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e71ed`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e73d6`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e7466`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e71d7`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e71ed`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e73d6`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e7466`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e7196`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e7196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402e78a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346a89`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402e78a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140346a89`

## pseudocode

```c
void __fastcall RefsPerformDismountOnVcb(__int64 a1, __int64 a2, char a3, __int64 a4, int a5, struct _VPB **a6)
{
  struct _FCB *v8; // r13
  __int64 v9; // rdx
  __int64 VolumeUniqueGuid; // rax
  void *v11; // rcx
  struct _PCW_INSTANCE *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  struct _FCB *v18; // r14
  __int64 v19; // r8
  struct _FCB *NextFcbTableEntry; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  char v24; // r13
  PFAST_MUTEX *v25; // rbx
  PFAST_MUTEX *p_FastMutex; // rax
  PFAST_MUTEX *v27; // rcx
  _QWORD *i; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // r8
  __int128 *v39; // rdx
  __int64 v40; // rdx
  struct _IRP_CONTEXT *v41; // rcx
  char v42; // r14
  struct _VPB **v43; // r8
  unsigned int j; // ebx
  __int64 v45; // r13
  _OWORD *ActivityIdThread; // rax
  ULONGLONG UnbiasedInterruptTime; // rax
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // r14
  char v50; // r13
  __int64 v51; // rdx
  const CHAR *v52; // r8
  char v53; // r15
  __int64 v54; // r8
  char v55; // r10
  __int64 v56; // r11
  __int64 v57; // rdx
  __int64 v58; // rdx
  int v59; // edx
  int v60; // [rsp+20h] [rbp-328h]
  char v61; // [rsp+100h] [rbp-248h] BYREF
  char v62; // [rsp+101h] [rbp-247h] BYREF
  char v63; // [rsp+102h] [rbp-246h]
  char v64; // [rsp+103h] [rbp-245h]
  char v65; // [rsp+104h] [rbp-244h]
  char v66; // [rsp+105h] [rbp-243h]
  int v67; // [rsp+108h] [rbp-240h]
  __int64 v68; // [rsp+110h] [rbp-238h]
  PEPROCESS Process; // [rsp+118h] [rbp-230h] BYREF
  const char *const near *v70; // [rsp+120h] [rbp-228h]
  struct _VPB **v71; // [rsp+128h] [rbp-220h]
  struct _FCB *v72; // [rsp+130h] [rbp-218h]
  __int64 DirtyPagesAccumulator; // [rsp+138h] [rbp-210h]
  void *v74; // [rsp+140h] [rbp-208h] BYREF
  struct _FCB *v75; // [rsp+148h] [rbp-200h]
  __int64 v76; // [rsp+150h] [rbp-1F8h]
  struct _FCB *v77; // [rsp+158h] [rbp-1F0h]
  struct _FCB *v78; // [rsp+160h] [rbp-1E8h]
  int v79; // [rsp+168h] [rbp-1E0h]
  unsigned int v80; // [rsp+16Ch] [rbp-1DCh]
  __int64 v81; // [rsp+170h] [rbp-1D8h]
  __int64 v82; // [rsp+178h] [rbp-1D0h]
  _QWORD *v83; // [rsp+180h] [rbp-1C8h]
  PFAST_MUTEX *v84; // [rsp+188h] [rbp-1C0h]
  _QWORD v85[13]; // [rsp+190h] [rbp-1B8h] BYREF
  __int128 v86; // [rsp+1F8h] [rbp-150h] BYREF
  __int128 v87; // [rsp+208h] [rbp-140h]
  __int64 v88; // [rsp+220h] [rbp-128h] BYREF
  int v89; // [rsp+290h] [rbp-B8h] BYREF

  v68 = a1;
  v76 = a2;
  v67 = a5;
  v71 = a6;
  v70 = (const char *const near *)a6;
  v8 = 0;
  DirtyPagesAccumulator = -1;
  v81 = -1;
  memset(v85, 0, 0x48u);
  v62 = 0;
  v61 = 0;
  v64 = *(_BYTE *)(a2 + 24) & 1;
  RefsUninitializePerfCountersTelemetry((struct _VCB *)a2);
  if ( (*(_DWORD *)(a2 + 28) & 0x80u) != 0 )
  {
    VolumeUniqueGuid = MsGetVolumeUniqueGuid(*(_QWORD *)(a2 + 112));
    FsRtlDedupChangeUninit(a2 + 6572, a2 + 6588, VolumeUniqueGuid);
    *(_DWORD *)(a2 + 28) &= ~0x80u;
  }
  v11 = *(void **)(a2 + 6272);
  if ( v11 )
  {
    IoUnregisterPlugPlayNotification(v11);
    *(_QWORD *)(a2 + 6272) = 0;
  }
  LOBYTE(v9) = 1;
  RefsProcessAsyncCloses(a2, v9, 4);
  RefsCommitCurrentTransaction((struct _IRP_CONTEXT *)a1, 1u);
  if ( RefsPcwCmsCounterSet )
  {
    if ( *(_QWORD *)(a2 + 6688) )
    {
      v12 = *(struct _PCW_INSTANCE **)(a2 + 6696);
      if ( v12 )
      {
        PcwCloseInstance(v12);
        *(_QWORD *)(a2 + 6688) = 0;
        *(_QWORD *)(a2 + 6696) = 0;
      }
    }
  }
  v13 = *(_QWORD *)(a2 + 176);
  if ( v13 )
  {
    MsUninitializeCachingTableObject(*(_QWORD *)(a1 + 24), *(_QWORD *)(a2 + 176));
    MsCloseDurableTableObject(v14, v13);
    *(_QWORD *)(a2 + 176) = 0;
  }
  v15 = *(_QWORD *)(a2 + 184);
  if ( v15 )
  {
    MsUninitializeCachingTableObject(*(_QWORD *)(a1 + 24), v15);
    MsCloseDurableTableObject(v16, *(_QWORD *)(a2 + 184));
    *(_QWORD *)(a2 + 184) = 0;
  }
  v17 = *(_QWORD *)(a2 + 40);
  if ( v17 )
  {
    RefsAcquireExclusiveFcb(a1, *(_QWORD *)(v17 + 136), *(_QWORD *)(a2 + 40), 4);
    RefsUsnCleanupAllReadWaiters((struct _VCB *)a2, -1073741202);
    RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(v17 + 136));
  }
  RefsUsnNotifyDeletion((struct _VCB *)a2, -1073741202);
  *(_DWORD *)(a2 + 24) &= ~0x80000u;
  *(_DWORD *)(a2 + 24) &= ~1u;
  v74 = 0;
  do
  {
    v18 = v8;
    v75 = v8;
    ExInitializeFastOwnerEntry(v85);
    LOBYTE(v19) = 1;
    ExAcquireFastResourceShared(a2 + 624, v85, v19);
    NextFcbTableEntry = RefsGetNextFcbTableEntry((struct _VCB *)a2, &v74);
    v8 = NextFcbTableEntry;
    v72 = NextFcbTableEntry;
    if ( NextFcbTableEntry )
      _InterlockedAdd((volatile signed __int32 *)&NextFcbTableEntry->Header.AllocationSize, 1u);
    v21 = a2 + 624;
    if ( v18 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&v18->Header.AllocationSize);
      ExReleaseFastResource(v21, v85);
      RefsAcquireExclusiveFcb(a1, v18, 0, 1);
      v63 = 1;
      v24 = 1;
      v65 = 1;
      v25 = 0;
      while ( v18 )
      {
        p_FastMutex = &v18->Header.FastMutex;
        v25 = (PFAST_MUTEX *)(v24 ? *p_FastMutex : *v25);
        v24 = 0;
        v65 = 0;
        if ( v25 == p_FastMutex )
          break;
        v27 = v25 - 15;
        v84 = v25 - 15;
        if ( v25[15] )
        {
          v18->FcbTableEntry.HashLinks.Flink = (struct _LIST_ENTRY *)&v62;
          v62 = 0;
          RefsDeleteInternalAttributeStream((struct _IRP_CONTEXT *)a1, (struct _SCB *)(v25 - 15), 1u, v23);
          v24 = 1;
          v65 = 1;
          v27 = v25 - 15;
          if ( v62 )
          {
            v18 = 0;
            v75 = 0;
            v63 = 0;
          }
          else
          {
            v18->FcbTableEntry.HashLinks.Flink = 0;
          }
        }
        if ( v27 == *(PFAST_MUTEX **)(a2 + 40) )
        {
          RefsUsnRemoveAllModifiedOpenFiles((struct _VCB *)a2);
          v27 = v25 - 15;
        }
        if ( v27 == *(PFAST_MUTEX **)(a2 + 72) && *(_QWORD *)(a2 + 880) )
        {
          *(_QWORD *)(a2 + 5856) = 0x7FFFFFFFFFFFFFFFLL;
          *(_QWORD *)(a2 + 5864) = 0;
          *(_QWORD *)(a2 + 880) = 0;
        }
        for ( i = (_QWORD *)(a2 + 32); ; ++i )
        {
          v83 = i;
          if ( i == (_QWORD *)(a2 + 96) )
            break;
          if ( (PFAST_MUTEX *)*i == v27 )
          {
            *i = 0;
            v18->Header.Resource = (PERESOURCE)((unsigned __int64)v18->Header.Resource & ~0x100uLL);
            v18->FcbTableEntry.HashLinks.Flink = (struct _LIST_ENTRY *)&v62;
            v62 = 0;
            LOBYTE(v60) = 0;
            LOBYTE(v23) = 1;
            RefsDecrementCloseCounts(a1, v27, 0, v23, v60, 0);
            if ( v62 )
            {
              v18 = 0;
              v75 = 0;
              v63 = 0;
            }
            else
            {
              v18->FcbTableEntry.HashLinks.Flink = 0;
            }
            v24 = 1;
            v65 = 1;
            break;
          }
        }
        if ( v24 && v18 && !v61 )
        {
          LOBYTE(v22) = 1;
          ExAcquireFastResourceExclusive(v18->Header.FileContextSupportPointer + 78, 0, v22);
          _InterlockedAdd((volatile signed __int32 *)&v18->Header.AllocationSize, 1u);
          ExReleaseFastResource(v18->Header.FileContextSupportPointer + 78, 0);
          RefsReleaseFcb((struct _IRP_CONTEXT *)a1, v18);
          v63 = 0;
          if ( v18->Context )
          {
            v78 = v18;
            LOBYTE(v30) = 1;
            RefsAcquirePagingResourceExclusive(v29, v18, v30);
            v61 = 1;
            v66 = 1;
          }
          RefsAcquireExclusiveFcb(a1, v18, 0, 1);
          v63 = 1;
          LOBYTE(v31) = 1;
          ExAcquireFastResourceExclusive(v18->Header.FileContextSupportPointer + 78, 0, v31);
          _InterlockedDecrement((volatile signed __int32 *)&v18->Header.AllocationSize);
          ExReleaseFastResource(v18->Header.FileContextSupportPointer + 78, 0);
        }
      }
      if ( v63 )
      {
        if ( v61 )
        {
          v77 = v18;
          RefsReleasePagingResource(a1, v18);
          v61 = 0;
          v66 = 0;
        }
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, v18);
        v63 = 0;
      }
      else
      {
        v61 = 0;
        v66 = 0;
      }
      v8 = v72;
    }
    else
    {
      ExReleaseFastResource(v21, v85);
    }
  }
  while ( v8 );
  RefsBindMinstoreTransactionNoRaise((struct _IRP_CONTEXT *)a1);
  *(_QWORD *)(a2 + 32) = 0;
  v32 = *(_QWORD *)(a2 + 104);
  if ( v32 )
  {
    v33 = *(_QWORD *)(a1 + 24);
    if ( v33 )
    {
      MsUpdateTree(v33, v32, 2, 0, 0);
      RefsCommitCurrentTransaction((struct _IRP_CONTEXT *)a1, 1u);
    }
    MsUninitializeCachingTableObject(*(_QWORD *)(a1 + 24), *(_QWORD *)(a2 + 104));
    MsCloseDurableTableObject(v34, *(_QWORD *)(a2 + 104));
    *(_QWORD *)(a2 + 104) = 0;
  }
  RefsCommitCurrentTransaction((struct _IRP_CONTEXT *)a1, 0);
  LOBYTE(v35) = 1;
  RefsProcessAsyncCloses(a2, v35, 4);
  v36 = *(_QWORD *)(a2 + 112);
  if ( v36 )
  {
    v37 = *(_DWORD *)(a2 + 24);
    if ( (v37 & 0x4000) != 0 )
    {
      MsReleaseLogSpace();
      *(_DWORD *)(a2 + 24) &= ~0x4000u;
      v37 = *(_DWORD *)(a2 + 24);
      v36 = *(_QWORD *)(a2 + 112);
    }
    if ( *(_DWORD *)(a1 + 16) || (v37 & 0x10000000) == 0 || (v37 & 0x100000) != 0 || (v37 & 0x8000000) != 0 )
    {
      v38 = 0;
      v39 = 0;
    }
    else
    {
      v86 = 0;
      v87 = 0;
      v86 = *(_OWORD *)(a2 + 920);
      v87 = *(_OWORD *)(a2 + 968);
      v38 = 32;
      v39 = &v86;
    }
    MsShutdownVolume(v36, v39, v38);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 120));
    DirtyPagesAccumulator = MsGetDirtyPagesAccumulator(*(_QWORD *)(a2 + 112));
    v81 = DirtyPagesAccumulator;
    MsReleaseTable(*(_QWORD *)(a2 + 112));
    *(_QWORD *)(a2 + 112) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 120));
    KeLeaveGuardedRegion();
  }
  v40 = *(unsigned int *)(a2 + 24);
  v41 = (struct _IRP_CONTEXT *)(*(_DWORD *)(a2 + 24) & 0x8010000);
  if ( (_DWORD)v41 == 0x10000 )
  {
    v61 = 0;
    v79 = *(_DWORD *)(a1 + 16);
    v61 = 0;
    RefsDeviceIoControl((struct _IRP_CONTEXT *)a1, *(PDEVICE_OBJECT *)(a2 + 192), 0x74804u, 0, &v61, 1u, 0, 0, 0);
    v42 = v64;
    v43 = v71;
    *(_DWORD *)(a2 + 24) &= ~0x10000u;
    v40 = *(unsigned int *)(a2 + 24);
  }
  else
  {
    v42 = v64;
    v43 = v71;
  }
  if ( a3 && (v40 & 0x800) == 0 )
  {
    RefsPerformDismountOnVcbNonpaged(v41, (struct _VCB *)a2, v43);
    *(_DWORD *)(a2 + 24) |= 0x800u;
    for ( j = 0; ; ++j )
    {
      v80 = j;
      if ( j >= *(_DWORD *)(a2 + 10448) )
        break;
      IoPerfFreeEntityData((struct _IO_PERF_ENTITY_DATA *)(a2 + 192LL * j + 10496));
    }
  }
  if ( v42 )
  {
    memset(&v85[10], 0, 24);
    Process = 0;
    v45 = *(_QWORD *)(a1 + 712);
    ActivityIdThread = *(_OWORD **)(a1 + 80);
    if ( ActivityIdThread || (ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v41, v40)) != 0 )
    {
      *(_OWORD *)&v85[11] = *ActivityIdThread;
      v85[10] = &v85[11];
    }
    else
    {
      v85[10] = 0;
    }
    if ( v45 )
    {
      UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
      *(_QWORD *)(v45 + 24) = UnbiasedInterruptTime;
      v48 = (UnbiasedInterruptTime - *(_QWORD *)v45) / 0xA / 0x3E8;
      v49 = (*(_QWORD *)(v45 + 16) - *(_QWORD *)(v45 + 8)) / 0xAuLL / 0x3E8;
      DirtyPagesAccumulator -= *(_QWORD *)(v45 + 48);
      v70 = *(const char *const near **)(v45 + 32);
      LODWORD(v68) = *(_DWORD *)(v45 + 40);
      ExFreePoolWithTag(*(PVOID *)(a1 + 712), 0);
      *(_QWORD *)(a1 + 712) = 0;
      v50 = (char)v70;
    }
    else
    {
      LODWORD(v68) = 0;
      v48 = 0;
      v49 = 0;
      DirtyPagesAccumulator = 0;
      v50 = 0;
    }
    IoPerfPrintTimeInterval(v48, 2, &v88);
    IoPerfPrintTimeInterval(v49, 2, &v89);
    if ( PsLookupProcessByProcessId(*(HANDLE *)(a1 + 704), &Process) >= 0 )
      PsGetProcessImageFileName(Process);
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      v70 = (&RefsDismountReasonMapping)[v67];
      v67 = *(_DWORD *)(a1 + 704);
      v52 = &File;
      if ( *(_QWORD *)(a2 + 10480) )
        v52 = *(const CHAR **)(a2 + 10480);
      LODWORD(v71) = *(_DWORD *)(a2 + 6372);
      v53 = 0;
      if ( (unsigned int)(*(_DWORD *)(a2 + 6288) - 1) <= 0x13 )
        v53 = *(_DWORD *)(a2 + 6288);
      v74 = *(void **)(a2 + 6352);
      v76 = *(_QWORD *)(a2 + 6336);
      v82 = *(_QWORD *)(a2 + 6320);
      v77 = *(struct _FCB **)(a2 + 6304);
      v78 = *(struct _FCB **)(a2 + 824);
      LODWORD(v72) = RefsGetDeveloperVolumeState(a2, v51, v52);
      v57 = *(_QWORD *)(a2 + 208);
      if ( v57 && (v58 = *(_QWORD *)(v57 + 16)) != 0 )
        v59 = (*(_DWORD *)(v58 + 48) >> 8) & 1;
      else
        v59 = 0;
      McTemplateK0jmzuuhtqzzzzzqjqtjsqsszxzxidi_EtwWriteTransfer(
        a2 + 6704,
        v59,
        v85[10],
        a2 + 6064,
        a2 + 6704,
        *(_QWORD *)(a2 + 6160),
        *(_BYTE *)(a2 + 792),
        *(_BYTE *)(a2 + 793),
        *(_WORD *)(a2 + 6728),
        v59,
        (char)v72,
        (__int64)v78,
        (__int64)v77,
        v82,
        v76,
        (__int64)v74,
        v53,
        a2 + 6376,
        (char)v71,
        v55,
        a2 + 13280,
        v54,
        v67,
        v56,
        (__int64)v70,
        (__int64)&v89,
        v49,
        (__int64)&v88,
        v48,
        v50,
        v68,
        DirtyPagesAccumulator);
    }
    if ( Process )
      ObfDereferenceObject(Process);
  }
}

```

## disassembly

```asm
0x1402e6f54  mov     [rsp+arg_10], r8b
0x1402e6f59  push    rbx
0x1402e6f5a  push    rsi
0x1402e6f5b  push    rdi
0x1402e6f5c  push    r12
0x1402e6f5e  push    r13
0x1402e6f60  push    r14
0x1402e6f62  push    r15
0x1402e6f64  sub     rsp, 310h
0x1402e6f6b  mov     rax, cs:__security_cookie
0x1402e6f72  xor     rax, rsp
0x1402e6f75  mov     [rsp+348h+var_48], rax
0x1402e6f7d  mov     rsi, rdx
0x1402e6f80  mov     r15, rcx
0x1402e6f83  mov     [rsp+348h+var_238], rcx
0x1402e6f8b  mov     [rsp+348h+var_1F8], rdx
0x1402e6f93  mov     eax, [rsp+348h+arg_20]
0x1402e6f9a  mov     [rsp+348h+var_240], eax
0x1402e6fa1  mov     rax, [rsp+348h+arg_28]
0x1402e6fa9  mov     [rsp+348h+var_220], rax
0x1402e6fb1  mov     [rsp+348h+var_228], rax
0x1402e6fb9  xor     edi, edi
0x1402e6fbb  mov     r13d, edi
0x1402e6fbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x1402e6fc2  mov     [rsp+348h+var_210], rax
0x1402e6fca  mov     [rsp+348h+var_1D8], rax
0x1402e6fd2  xor     edx, edx; Val
0x1402e6fd4  lea     r8d, [rdi+48h]; Size
0x1402e6fd8  lea     rcx, [rsp+348h+var_1B8]; void *
0x1402e6fe0  call    memset
0x1402e6fe5  mov     [rsp+348h+var_247], dil
0x1402e6fed  mov     [rsp+348h+var_248], dil
0x1402e6ff5  mov     al, [rsi+18h]
0x1402e6ff8  lea     r12d, [rdi+1]
0x1402e6ffc  and     al, r12b
0x1402e6fff  mov     [rsp+348h+var_245], al
0x1402e7006  mov     rcx, rsi; struct _VCB *
0x1402e7009  call    ?RefsUninitializePerfCountersTelemetry@@YAXPEAU_VCB@@@Z; RefsUninitializePerfCountersTelemetry(_VCB *)
0x1402e700e  mov     eax, [rsi+1Ch]
0x1402e7011  test    al, al
0x1402e7013  jns     short loc_1402E7040
0x1402e7015  mov     rcx, [rsi+70h]
0x1402e7019  call    MsGetVolumeUniqueGuid
0x1402e701e  mov     r8, rax
0x1402e7021  lea     rdx, [rsi+19BCh]
0x1402e7028  lea     rcx, [rsi+19ACh]
0x1402e702f  call    cs:__imp_FsRtlDedupChangeUninit
0x1402e7036  nop     dword ptr [rax+rax+00h]
0x1402e703b  btr     dword ptr [rsi+1Ch], 7
0x1402e7040  mov     rcx, [rsi+1880h]; NotificationEntry
0x1402e7047  test    rcx, rcx
0x1402e704a  jz      short loc_1402E705F
0x1402e704c  call    cs:__imp_IoUnregisterPlugPlayNotification
0x1402e7053  nop     dword ptr [rax+rax+00h]
0x1402e7058  mov     [rsi+1880h], rdi
0x1402e705f  mov     r8d, 4
0x1402e7065  mov     dl, r12b
0x1402e7068  mov     rcx, rsi
0x1402e706b  call    ?RefsProcessAsyncCloses@@YAXAEAU_VCB@@W4DrainAll@CLOSE_QUEUE@@W4AsyncCloseFlags@@@Z; RefsProcessAsyncCloses(_VCB &,CLOSE_QUEUE::DrainAll,AsyncCloseFlags)
0x1402e7070  mov     dl, r12b; unsigned __int8
0x1402e7073  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402e7076  call    ?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)
0x1402e707b  cmp     cs:RefsPcwCmsCounterSet, rdi
0x1402e7082  jz      short loc_1402E70B3
0x1402e7084  cmp     [rsi+1A20h], rdi
0x1402e708b  jz      short loc_1402E70B3
0x1402e708d  mov     rcx, [rsi+1A28h]; Instance
0x1402e7094  test    rcx, rcx
0x1402e7097  jz      short loc_1402E70B3
0x1402e7099  call    cs:__imp_PcwCloseInstance
0x1402e70a0  nop     dword ptr [rax+rax+00h]
0x1402e70a5  mov     [rsi+1A20h], rdi
0x1402e70ac  mov     [rsi+1A28h], rdi
0x1402e70b3  mov     rbx, [rsi+0B0h]
0x1402e70ba  test    rbx, rbx
0x1402e70bd  jz      short loc_1402E70DA
0x1402e70bf  mov     rdx, rbx
0x1402e70c2  mov     rcx, [r15+18h]
0x1402e70c6  call    MsUninitializeCachingTableObject
0x1402e70cb  mov     rdx, rbx
0x1402e70ce  call    MsCloseDurableTableObject
0x1402e70d3  mov     [rsi+0B0h], rdi
0x1402e70da  mov     rdx, [rsi+0B8h]
0x1402e70e1  test    rdx, rdx
0x1402e70e4  jz      short loc_1402E7102
0x1402e70e6  mov     rcx, [r15+18h]
0x1402e70ea  call    MsUninitializeCachingTableObject
0x1402e70ef  mov     rdx, [rsi+0B8h]
0x1402e70f6  call    MsCloseDurableTableObject
0x1402e70fb  mov     [rsi+0B8h], rdi
0x1402e7102  mov     rbx, [rsi+28h]
0x1402e7106  test    rbx, rbx
0x1402e7109  jz      short loc_1402E713F
0x1402e710b  mov     r9d, 4
0x1402e7111  mov     r8, rbx
0x1402e7114  mov     rdx, [rbx+88h]
0x1402e711b  mov     rcx, r15
0x1402e711e  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402e7123  mov     edx, 0C000026Eh; int
0x1402e7128  mov     rcx, rsi; struct _VCB *
0x1402e712b  call    ?RefsUsnCleanupAllReadWaiters@@YAXAEAU_VCB@@J@Z; RefsUsnCleanupAllReadWaiters(_VCB &,long)
0x1402e7130  mov     rdx, [rbx+88h]; struct _FCB *
0x1402e7137  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402e713a  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x1402e713f  mov     edx, 0C000026Eh; int
0x1402e7144  mov     rcx, rsi; struct _VCB *
0x1402e7147  call    ?RefsUsnNotifyDeletion@@YAXAEAU_VCB@@J@Z; RefsUsnNotifyDeletion(_VCB &,long)
0x1402e714c  btr     dword ptr [rsi+18h], 13h
0x1402e7151  mov     eax, [rsi+18h]
0x1402e7154  and     eax, 0FFFFFFFEh
0x1402e7157  mov     [rsi+18h], eax
0x1402e715a  mov     [rsp+348h+var_208], rdi
0x1402e7162  mov     r14, r13
0x1402e7165  mov     [rsp+348h+var_200], r13
0x1402e716d  lea     rcx, [rsp+348h+var_1B8]
0x1402e7175  call    cs:__imp_ExInitializeFastOwnerEntry
0x1402e717c  nop     dword ptr [rax+rax+00h]
0x1402e7181  lea     rbx, [rsi+270h]
0x1402e7188  mov     r8b, r12b
0x1402e718b  lea     rdx, [rsp+348h+var_1B8]
0x1402e7193  mov     rcx, rbx
0x1402e7196  call    cs:__imp_ExAcquireFastResourceShared
0x1402e719d  nop     dword ptr [rax+rax+00h]
0x1402e71a2  lea     rdx, [rsp+348h+var_208]; void **
0x1402e71aa  mov     rcx, rsi; struct _VCB *
0x1402e71ad  call    ?RefsGetNextFcbTableEntry@@YAPEAU_FCB@@PEAU_VCB@@PEAPEAX@Z; RefsGetNextFcbTableEntry(_VCB *,void * *)
0x1402e71b2  mov     r13, rax
0x1402e71b5  mov     [rsp+348h+var_218], rax
0x1402e71bd  test    rax, rax
0x1402e71c0  jz      short loc_1402E71C7
0x1402e71c2  lock add [rax+18h], r12d
0x1402e71c7  lea     rdx, [rsp+348h+var_1B8]
0x1402e71cf  mov     rcx, rbx
0x1402e71d2  test    r14, r14
0x1402e71d5  jnz     short loc_1402E71E8
0x1402e71d7  call    cs:__imp_ExReleaseFastResource
0x1402e71de  nop     dword ptr [rax+rax+00h]
0x1402e71e3  jmp     loc_1402E74DB
0x1402e71e8  lock dec dword ptr [r14+18h]
0x1402e71ed  call    cs:__imp_ExReleaseFastResource
0x1402e71f4  nop     dword ptr [rax+rax+00h]
0x1402e71f9  mov     r9d, r12d
0x1402e71fc  xor     r8d, r8d
0x1402e71ff  mov     rdx, r14
0x1402e7202  mov     rcx, r15
0x1402e7205  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402e720a  mov     [rsp+348h+var_246], r12b
0x1402e7212  mov     r13b, r12b
0x1402e7215  mov     [rsp+348h+var_244], r12b
0x1402e721d  mov     rbx, rdi
0x1402e7220  test    r14, r14
0x1402e7223  jz      loc_1402E7477
0x1402e7229  lea     rax, [r14+30h]
0x1402e722d  test    r13b, r13b
0x1402e7230  jz      short loc_1402E7237
0x1402e7232  mov     rbx, [rax]
0x1402e7235  jmp     short loc_1402E723A
0x1402e7237  mov     rbx, [rbx]
0x1402e723a  mov     r13b, dil
0x1402e723d  mov     [rsp+348h+var_244], dil
0x1402e7245  cmp     rbx, rax
0x1402e7248  jz      loc_1402E7477
0x1402e724e  lea     rcx, [rbx-78h]
0x1402e7252  mov     [rsp+348h+var_1C0], rcx
0x1402e725a  cmp     [rcx+0F0h], rdi
0x1402e7261  jz      short loc_1402E72B4
0x1402e7263  lea     rax, [rsp+348h+var_247]
0x1402e726b  mov     [r14+0F8h], rax
0x1402e7272  mov     [rsp+348h+var_247], dil
0x1402e727a  mov     r8d, r12d; unsigned int
0x1402e727d  mov     rdx, rcx; struct _SCB *
0x1402e7280  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402e7283  call    ?RefsDeleteInternalAttributeStream@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@KE@Z; RefsDeleteInternalAttributeStream(_IRP_CONTEXT *,_SCB *,ulong,uchar)
0x1402e7288  mov     r13b, r12b
0x1402e728b  mov     [rsp+348h+var_244], r12b
0x1402e7293  lea     rcx, [rbx-78h]
0x1402e7297  cmp     [rsp+348h+var_247], dil
0x1402e729f  jz      short loc_1402E7314
0x1402e72a1  mov     r14, rdi
0x1402e72a4  mov     [rsp+348h+var_200], rdi
0x1402e72ac  mov     [rsp+348h+var_246], dil
0x1402e72b4  cmp     rcx, [rsi+28h]
0x1402e72b8  jnz     short loc_1402E72C6
0x1402e72ba  mov     rcx, rsi; struct _VCB *
0x1402e72bd  call    ?RefsUsnRemoveAllModifiedOpenFiles@@YAXAEAU_VCB@@@Z; RefsUsnRemoveAllModifiedOpenFiles(_VCB &)
0x1402e72c2  lea     rcx, [rbx-78h]
0x1402e72c6  cmp     rcx, [rsi+48h]
0x1402e72ca  jnz     short loc_1402E72F4
0x1402e72cc  cmp     [rsi+370h], rdi
0x1402e72d3  jz      short loc_1402E72F4
0x1402e72d5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1402e72df  mov     [rsi+16E0h], rax
0x1402e72e6  mov     [rsi+16E8h], rdi
0x1402e72ed  mov     [rsi+370h], rdi
0x1402e72f4  lea     rax, [rsi+20h]
0x1402e72f8  lea     rdx, [rax+40h]
0x1402e72fc  mov     [rsp+348h+var_1C8], rax
0x1402e7304  cmp     rax, rdx
0x1402e7307  jz      short loc_1402E7388
0x1402e7309  cmp     [rax], rcx
0x1402e730c  jz      short loc_1402E731D
0x1402e730e  add     rax, 8
0x1402e7312  jmp     short loc_1402E72FC
0x1402e7314  mov     [r14+0F8h], rdi
0x1402e731b  jmp     short loc_1402E72B4
0x1402e731d  mov     [rax], rdi
0x1402e7320  btr     qword ptr [r14+8], 8
0x1402e7326  lea     rax, [rsp+348h+var_247]
0x1402e732e  mov     [r14+0F8h], rax
0x1402e7335  mov     [rsp+348h+var_247], dil
0x1402e733d  mov     [rsp+348h+var_320], edi
0x1402e7341  mov     byte ptr [rsp+348h+var_328], dil
0x1402e7346  mov     r9b, r12b
0x1402e7349  xor     r8d, r8d
0x1402e734c  mov     rdx, rcx
0x1402e734f  mov     rcx, r15
0x1402e7352  call    ?RefsDecrementCloseCounts@@YA_NPEAU_IRP_CONTEXT@@AEAU_SCB@@PEAU_LCB@@EEW4CloseCountFlags@@@Z; RefsDecrementCloseCounts(_IRP_CONTEXT *,_SCB &,_LCB *,uchar,uchar,CloseCountFlags)
0x1402e7357  cmp     [rsp+348h+var_247], dil
0x1402e735f  jz      short loc_1402E7376
0x1402e7361  mov     r14, rdi
0x1402e7364  mov     [rsp+348h+var_200], rdi
0x1402e736c  mov     [rsp+348h+var_246], dil
0x1402e7374  jmp     short loc_1402E737D
0x1402e7376  mov     [r14+0F8h], rdi
0x1402e737d  mov     r13b, r12b
0x1402e7380  mov     [rsp+348h+var_244], r12b
0x1402e7388  test    r13b, r13b
0x1402e738b  jz      loc_1402E7472
0x1402e7391  test    r14, r14
0x1402e7394  jz      loc_1402E7472
0x1402e739a  cmp     [rsp+348h+var_248], dil
0x1402e73a2  jnz     loc_1402E7472
0x1402e73a8  mov     rcx, [r14+50h]
0x1402e73ac  add     rcx, 270h
0x1402e73b3  mov     r8b, r12b
0x1402e73b6  xor     edx, edx
0x1402e73b8  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402e73bf  nop     dword ptr [rax+rax+00h]
0x1402e73c4  lock add [r14+18h], r12d
0x1402e73c9  mov     rcx, [r14+50h]
0x1402e73cd  add     rcx, 270h
0x1402e73d4  xor     edx, edx
0x1402e73d6  call    cs:__imp_ExReleaseFastResource
0x1402e73dd  nop     dword ptr [rax+rax+00h]
0x1402e73e2  mov     rdx, r14; struct _FCB *
0x1402e73e5  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402e73e8  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x1402e73ed  mov     [rsp+348h+var_246], dil
0x1402e73f5  cmp     [r14+60h], rdi
0x1402e73f9  jz      short loc_1402E741F
0x1402e73fb  mov     [rsp+348h+var_1E8], r14
0x1402e7403  mov     r8b, r12b
0x1402e7406  mov     rdx, r14
0x1402e7409  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x1402e740e  mov     al, r12b
0x1402e7411  mov     [rsp+348h+var_248], al
0x1402e7418  mov     [rsp+348h+var_243], al
0x1402e741f  mov     r9d, r12d
0x1402e7422  xor     r8d, r8d
0x1402e7425  mov     rdx, r14
0x1402e7428  mov     rcx, r15
0x1402e742b  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402e7430  mov     [rsp+348h+var_246], r12b
0x1402e7438  mov     rcx, [r14+50h]
0x1402e743c  add     rcx, 270h
0x1402e7443  mov     r8b, r12b
0x1402e7446  xor     edx, edx
0x1402e7448  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402e744f  nop     dword ptr [rax+rax+00h]
0x1402e7454  lock dec dword ptr [r14+18h]
0x1402e7459  mov     rcx, [r14+50h]
0x1402e745d  add     rcx, 270h
0x1402e7464  xor     edx, edx
0x1402e7466  call    cs:__imp_ExReleaseFastResource
0x1402e746d  nop     dword ptr [rax+rax+00h]
0x1402e7472  jmp     loc_1402E7220
0x1402e7477  cmp     [rsp+348h+var_246], 0
0x1402e747f  jz      short loc_1402E74C3
0x1402e7481  cmp     [rsp+348h+var_248], dil
0x1402e7489  jz      short loc_1402E74AE
0x1402e748b  mov     [rsp+348h+var_1F0], r14
0x1402e7493  mov     rdx, r14
0x1402e7496  mov     rcx, r15
0x1402e7499  call    ?RefsReleasePagingResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleasePagingResource(_IRP_CONTEXT *,PFCBOrSCB)
0x1402e749e  mov     [rsp+348h+var_248], dil
0x1402e74a6  mov     [rsp+348h+var_243], dil
0x1402e74ae  mov     rdx, r14; struct _FCB *
0x1402e74b1  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402e74b4  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x1402e74b9  mov     [rsp+348h+var_246], dil
0x1402e74c1  jmp     short loc_1402E74D3
0x1402e74c3  mov     [rsp+348h+var_248], dil
0x1402e74cb  mov     [rsp+348h+var_243], dil
0x1402e74d3  mov     r13, [rsp+348h+var_218]
0x1402e74db  test    r13, r13
0x1402e74de  jnz     loc_1402E7162
0x1402e74e4  mov     rcx, r15; struct _IRP_CONTEXT *
0x1402e74e7  call    ?RefsBindMinstoreTransactionNoRaise@@YAJPEAU_IRP_CONTEXT@@@Z; RefsBindMinstoreTransactionNoRaise(_IRP_CONTEXT *)
0x1402e74ec  mov     [rsi+20h], rdi
0x1402e74f0  mov     rdx, [rsi+68h]
  ... truncated ...
```
