# RefsPerformDismountOnVcb(_IRP_CONTEXT *,_VCB *,uchar,uchar,_REFS_DISMOUNT_REASON,_VPB * *)

- ea: `0x1402eb144`
- end: `0x1402ebd8d`
- name: `?RefsPerformDismountOnVcb@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@EEW4_REFS_DISMOUNT_REASON@@PEAPEAU_VPB@@@Z`
- size: `3145`
- prototype: ``
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400aeae0`
- `0x14028ec68`
- `0x1402b1d38`
- `0x1402b75e0`
- `0x1402c70f4`
- `0x1402cc560`
- `0x140319010`
- `0x140324914`

## callees

- `0x14002b340`
- `0x140037820`
- `0x140075ae0`
- `0x1400894e0`
- `0x140089640`
- `0x14008ad80`
- `0x140096ed0`
- `0x14009d150`
- `0x1400ab4e8`
- `0x1400abb14`
- `0x1400abb88`
- `0x1400ad194`
- `0x1400f662c`
- `0x140109d18`
- `0x14010a0bc`
- `0x140119294`
- `0x140119804`
- `0x14011aa40`
- `0x14011b268`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x14028d4ec`
- `0x140290b84`
- `0x1402e9b2c`
- `0x1402eb144`
- `0x140302eb0`
- `0x1403053a0`
- `0x14031e740`
- `0x14032ab00`
- `0x140332ce0`
- `0x140339af4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1402ebd5d`
- `ntoskrnl!ObfDereferenceObject` at `0x140349c8c`
- `ntoskrnl!ObfDereferenceObject` at `0x1402ebd5d`
- `ntoskrnl!ObfDereferenceObject` at `0x140349c8c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402eb9d4`
- `ntoskrnl!IoGetActivityIdThread` at `0x140349903`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402eb9d4`
- `ntoskrnl!IoGetActivityIdThread` at `0x140349903`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402eb5b4`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402eb643`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402eb5b4`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402eb643`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402ebb5d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140349a5b`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402ebb5d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140349a5b`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402eb36e`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402eb36e`
- `ntoskrnl!FsRtlDedupChangeUninit` at `0x1402eb224`
- `ntoskrnl!FsRtlDedupChangeUninit` at `0x1402eb224`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402eba14`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140349943`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402eba14`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140349943`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402ebb45`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140349a44`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402ebb45`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140349a44`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402eb7f8`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402eb7f8`
- `ntoskrnl!PcwCloseInstance` at `0x1402eb28f`
- `ntoskrnl!PcwCloseInstance` at `0x1402eb28f`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1402eb242`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x1402eb242`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402eb808`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402eb808`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140349878`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140349878`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402eb83e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402eb83e`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402eb84a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402eb84a`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb3cf`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb3e4`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb5d1`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb660`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb3cf`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb3e4`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb5d1`
- `ntoskrnl!ExReleaseFastResource` at `0x1402eb660`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402eb38f`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402eb38f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ebac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403499e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ebac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403499e5`

## pseudocode

```c
void __fastcall RefsPerformDismountOnVcb(CHAR *a1, unsigned __int64 a2, char a3, __int64 a4, int a5, struct _VPB **a6)
{
  struct _FCB *v8; // r15
  __int64 v9; // rdx
  __int64 VolumeUniqueGuid; // rax
  void *v11; // rcx
  struct _PCW_INSTANCE *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rbx
  struct _FCB *v18; // rdi
  __int64 v19; // r8
  struct _FCB *NextFcbTableEntry; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  char v24; // r15
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
  char v42; // di
  struct _VPB **v43; // r8
  unsigned int j; // ebx
  CHAR *v45; // r15
  __int64 v46; // rsi
  _OWORD *ActivityIdThread; // rax
  ULONGLONG UnbiasedInterruptTime; // rax
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // rdi
  const char *const near *v51; // rsi
  int v52; // r14d
  int v53; // r15d
  unsigned int v54; // ecx
  __int64 v55; // rdx
  int DeveloperVolumeState; // eax
  int v57; // edx
  char v58; // r8
  __int64 v59; // r10
  char v60; // r11
  int v61; // [rsp+20h] [rbp-328h]
  char v62; // [rsp+100h] [rbp-248h] BYREF
  char v63; // [rsp+101h] [rbp-247h] BYREF
  char v64; // [rsp+102h] [rbp-246h]
  char v65; // [rsp+103h] [rbp-245h]
  char v66; // [rsp+104h] [rbp-244h]
  char v67; // [rsp+105h] [rbp-243h]
  int v68; // [rsp+108h] [rbp-240h]
  __int64 DirtyPagesAccumulator; // [rsp+110h] [rbp-238h]
  const CHAR *ProcessImageFileName; // [rsp+118h] [rbp-230h]
  struct _VPB **v71; // [rsp+120h] [rbp-228h]
  struct _VPB **v72; // [rsp+128h] [rbp-220h]
  struct _FCB *v73; // [rsp+130h] [rbp-218h]
  PEPROCESS Process; // [rsp+138h] [rbp-210h] BYREF
  void *v75; // [rsp+140h] [rbp-208h] BYREF
  unsigned __int64 v76; // [rsp+148h] [rbp-200h]
  struct _FCB *v77; // [rsp+150h] [rbp-1F8h]
  int v78; // [rsp+158h] [rbp-1F0h]
  unsigned int v79; // [rsp+15Ch] [rbp-1ECh]
  __int64 v80; // [rsp+160h] [rbp-1E8h]
  struct _FCB *v81; // [rsp+168h] [rbp-1E0h]
  _QWORD *v82; // [rsp+170h] [rbp-1D8h]
  PFAST_MUTEX *v83; // [rsp+178h] [rbp-1D0h]
  struct _FCB *v84; // [rsp+180h] [rbp-1C8h]
  _QWORD v85[13]; // [rsp+190h] [rbp-1B8h] BYREF
  __int128 v86; // [rsp+1F8h] [rbp-150h] BYREF
  __int128 v87; // [rsp+208h] [rbp-140h]
  __int64 v88; // [rsp+220h] [rbp-128h] BYREF
  int v89; // [rsp+290h] [rbp-B8h] BYREF

  ProcessImageFileName = a1;
  v76 = a2;
  v68 = a5;
  v72 = a6;
  v71 = a6;
  v8 = 0;
  DirtyPagesAccumulator = -1;
  v80 = -1;
  memset(v85, 0, 0x48u);
  v63 = 0;
  v62 = 0;
  v65 = *(_BYTE *)(a2 + 24) & 1;
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
    MsUninitializeCachingTableObject(*((_QWORD *)a1 + 3), *(_QWORD *)(a2 + 176));
    MsCloseDurableTableObject(v14, v13);
    *(_QWORD *)(a2 + 176) = 0;
  }
  v15 = *(_QWORD *)(a2 + 184);
  if ( v15 )
  {
    MsUninitializeCachingTableObject(*((_QWORD *)a1 + 3), v15);
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
  v75 = 0;
  do
  {
    v18 = v8;
    v77 = v8;
    ExInitializeFastOwnerEntry(v85);
    LOBYTE(v19) = 1;
    ExAcquireFastResourceShared(a2 + 624, v85, v19);
    NextFcbTableEntry = RefsGetNextFcbTableEntry((struct _VCB *)a2, &v75);
    v8 = NextFcbTableEntry;
    v73 = NextFcbTableEntry;
    if ( NextFcbTableEntry )
      _InterlockedAdd((volatile signed __int32 *)&NextFcbTableEntry->Header.AllocationSize, 1u);
    v21 = a2 + 624;
    if ( v18 )
    {
      _InterlockedDecrement((volatile signed __int32 *)&v18->Header.AllocationSize);
      ExReleaseFastResource(v21, v85);
      RefsAcquireExclusiveFcb(a1, v18, 0, 1);
      v64 = 1;
      v24 = 1;
      v66 = 1;
      v25 = 0;
      while ( v18 )
      {
        p_FastMutex = &v18->Header.FastMutex;
        v25 = (PFAST_MUTEX *)(v24 ? *p_FastMutex : *v25);
        v24 = 0;
        v66 = 0;
        if ( v25 == p_FastMutex )
          break;
        v27 = v25 - 15;
        v83 = v25 - 15;
        if ( v25[15] )
        {
          v18->FcbTableEntry.HashLinks.Flink = (struct _LIST_ENTRY *)&v63;
          v63 = 0;
          RefsDeleteInternalAttributeStream((struct _IRP_CONTEXT *)a1, (struct _SCB *)(v25 - 15), 1u, v23);
          v24 = 1;
          v66 = 1;
          v27 = v25 - 15;
          if ( v63 )
          {
            v18 = 0;
            v77 = 0;
            v64 = 0;
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
          v82 = i;
          if ( i == (_QWORD *)(a2 + 96) )
            break;
          if ( (PFAST_MUTEX *)*i == v27 )
          {
            *i = 0;
            v18->Header.Resource = (PERESOURCE)((unsigned __int64)v18->Header.Resource & ~0x100uLL);
            v18->FcbTableEntry.HashLinks.Flink = (struct _LIST_ENTRY *)&v63;
            v63 = 0;
            LOBYTE(v61) = 0;
            LOBYTE(v23) = 1;
            RefsDecrementCloseCounts(a1, v27, 0, v23, v61, 0);
            if ( v63 )
            {
              v18 = 0;
              v77 = 0;
              v64 = 0;
            }
            else
            {
              v18->FcbTableEntry.HashLinks.Flink = 0;
            }
            v24 = 1;
            v66 = 1;
            break;
          }
        }
        if ( v24 && v18 && !v62 )
        {
          LOBYTE(v22) = 1;
          ExAcquireFastResourceExclusive(v18->Header.FileContextSupportPointer + 78, 0, v22);
          _InterlockedAdd((volatile signed __int32 *)&v18->Header.AllocationSize, 1u);
          ExReleaseFastResource(v18->Header.FileContextSupportPointer + 78, 0);
          RefsReleaseFcb((struct _IRP_CONTEXT *)a1, v18);
          v64 = 0;
          if ( v18->Context )
          {
            v81 = v18;
            LOBYTE(v30) = 1;
            RefsAcquirePagingResourceExclusive(v29, v18, v30);
            v62 = 1;
            v67 = 1;
          }
          RefsAcquireExclusiveFcb(a1, v18, 0, 1);
          v64 = 1;
          LOBYTE(v31) = 1;
          ExAcquireFastResourceExclusive(v18->Header.FileContextSupportPointer + 78, 0, v31);
          _InterlockedDecrement((volatile signed __int32 *)&v18->Header.AllocationSize);
          ExReleaseFastResource(v18->Header.FileContextSupportPointer + 78, 0);
        }
      }
      if ( v64 )
      {
        if ( v62 )
        {
          v84 = v18;
          RefsReleasePagingResource(a1, v18);
          v62 = 0;
          v67 = 0;
        }
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, v18);
        v64 = 0;
      }
      else
      {
        v62 = 0;
        v67 = 0;
      }
      v8 = v73;
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
    v33 = *((_QWORD *)a1 + 3);
    if ( v33 )
    {
      MsUpdateTree(v33, v32, 2, 0, 0);
      RefsCommitCurrentTransaction((struct _IRP_CONTEXT *)a1, 1u);
    }
    MsUninitializeCachingTableObject(*((_QWORD *)a1 + 3), *(_QWORD *)(a2 + 104));
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
    if ( *((_DWORD *)a1 + 4) || (v37 & 0x10000000) == 0 || (v37 & 0x100000) != 0 || (v37 & 0x8000000) != 0 )
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
    v80 = DirtyPagesAccumulator;
    MsReleaseTable(*(_QWORD *)(a2 + 112));
    *(_QWORD *)(a2 + 112) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 120));
    KeLeaveGuardedRegion();
  }
  v40 = *(unsigned int *)(a2 + 24);
  v41 = (struct _IRP_CONTEXT *)(*(_DWORD *)(a2 + 24) & 0x8010000);
  if ( (_DWORD)v41 == 0x10000 )
  {
    v62 = 0;
    v78 = *((_DWORD *)a1 + 4);
    v62 = 0;
    RefsDeviceIoControl((struct _IRP_CONTEXT *)a1, *(PDEVICE_OBJECT *)(a2 + 192), 0x74804u, 0, &v62, 1u, 0, 0, 0);
    v42 = v65;
    v43 = v72;
    *(_DWORD *)(a2 + 24) &= ~0x10000u;
    v40 = *(unsigned int *)(a2 + 24);
  }
  else
  {
    v42 = v65;
    v43 = v72;
  }
  if ( a3 && (v40 & 0x800) == 0 )
  {
    RefsPerformDismountOnVcbNonpaged(v41, (struct _VCB *)a2, v43);
    *(_DWORD *)(a2 + 24) |= 0x800u;
    for ( j = 0; ; ++j )
    {
      v79 = j;
      if ( j >= *(_DWORD *)(a2 + 10208) )
        break;
      IoPerfFreeEntityData((struct _IO_PERF_ENTITY_DATA *)(a2 + 192LL * j + 10304));
    }
  }
  if ( v42 )
  {
    memset(&v85[10], 0, 24);
    Process = 0;
    v45 = (CHAR *)&File;
    ProcessImageFileName = &File;
    v46 = *((_QWORD *)a1 + 89);
    ActivityIdThread = (_OWORD *)*((_QWORD *)a1 + 10);
    if ( ActivityIdThread || (ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v41, v40)) != 0 )
    {
      *(_OWORD *)&v85[11] = *ActivityIdThread;
      v85[10] = &v85[11];
    }
    else
    {
      v85[10] = 0;
    }
    if ( v46 )
    {
      UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
      *(_QWORD *)(v46 + 24) = UnbiasedInterruptTime;
      v49 = (UnbiasedInterruptTime - *(_QWORD *)v46) / 0xA / 0x3E8;
      v72 = (struct _VPB **)v49;
      v50 = (*(_QWORD *)(v46 + 16) - *(_QWORD *)(v46 + 8)) / 0xAuLL / 0x3E8;
      v76 = v50;
      DirtyPagesAccumulator -= *(_QWORD *)(v46 + 48);
      v73 = *(struct _FCB **)(v46 + 32);
      LODWORD(v71) = *(_DWORD *)(v46 + 40);
      ExFreePoolWithTag(*((PVOID *)a1 + 89), 0);
      *((_QWORD *)a1 + 89) = 0;
    }
    else
    {
      LODWORD(v71) = 0;
      v49 = 0;
      v72 = 0;
      v50 = 0;
      v76 = 0;
      DirtyPagesAccumulator = 0;
      v73 = 0;
    }
    IoPerfPrintTimeInterval(v49, 2, &v88);
    IoPerfPrintTimeInterval(v50, 2, &v89);
    if ( PsLookupProcessByProcessId(*((HANDLE *)a1 + 88), &Process) >= 0 )
      ProcessImageFileName = (const CHAR *)PsGetProcessImageFileName(Process);
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      v51 = (&RefsDismountReasonMapping)[v68];
      v52 = *((_DWORD *)a1 + 176);
      if ( *(_QWORD *)(a2 + 10240) )
        v45 = *(CHAR **)(a2 + 10240);
      v75 = v45;
      v53 = *(_DWORD *)(a2 + 28);
      v54 = *(_DWORD *)(a2 + 6288);
      v55 = 0;
      if ( v54 - 1 <= 0x13 )
        v55 = v54;
      DeveloperVolumeState = RefsGetDeveloperVolumeState(a2, v55, *(unsigned int *)(a2 + 6372));
      McTemplateK0jmzuuhtqzzzzzqjqtjsqsszxzxidi_EtwWriteTransfer(
        DeveloperVolumeState,
        v57,
        v85[10],
        a2 + 6064,
        a2 + 6704,
        *(_QWORD *)(a2 + 6160),
        *(_BYTE *)(a2 + 792),
        *(_BYTE *)(a2 + 793),
        *(_WORD *)(a2 + 6728),
        (v53 & 0x1000) != 0,
        DeveloperVolumeState,
        *(_QWORD *)(a2 + 824),
        *(_QWORD *)(a2 + 6304),
        *(_QWORD *)(a2 + 6320),
        *(_QWORD *)(a2 + 6336),
        *(_QWORD *)(a2 + 6352),
        v57,
        v59,
        v58,
        v60,
        a2 + 13080,
        (__int64)v75,
        v52,
        (__int64)ProcessImageFileName,
        (__int64)v51,
        (__int64)&v89,
        v76,
        (__int64)&v88,
        (char)v72,
        (char)v73,
        (char)v71,
        DirtyPagesAccumulator);
    }
    if ( Process )
      ObfDereferenceObject(Process);
  }
}

```

## disassembly

```asm
0x1402eb144  mov     [rsp+arg_10], r8b
0x1402eb149  push    rbx
0x1402eb14a  push    rsi
0x1402eb14b  push    rdi
0x1402eb14c  push    r12
0x1402eb14e  push    r13
0x1402eb150  push    r14
0x1402eb152  push    r15
0x1402eb154  sub     rsp, 310h
0x1402eb15b  mov     rax, cs:__security_cookie
0x1402eb162  xor     rax, rsp
0x1402eb165  mov     [rsp+348h+var_48], rax
0x1402eb16d  mov     r13, rdx
0x1402eb170  mov     r14, rcx
0x1402eb173  mov     [rsp+348h+var_230], rcx
0x1402eb17b  mov     [rsp+348h+var_200], rdx
0x1402eb183  mov     eax, [rsp+348h+arg_20]
0x1402eb18a  mov     [rsp+348h+var_240], eax
0x1402eb191  mov     rax, [rsp+348h+arg_28]
0x1402eb199  mov     [rsp+348h+var_220], rax
0x1402eb1a1  mov     [rsp+348h+var_228], rax
0x1402eb1a9  xor     r12d, r12d
0x1402eb1ac  mov     r15d, r12d
0x1402eb1af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1402eb1b3  mov     [rsp+348h+var_238], rax
0x1402eb1bb  mov     [rsp+348h+var_1E8], rax
0x1402eb1c3  xor     edx, edx; Val
0x1402eb1c5  lea     r8d, [r12+48h]; Size
0x1402eb1ca  lea     rcx, [rsp+348h+var_1B8]; void *
0x1402eb1d2  call    memset
0x1402eb1d7  mov     [rsp+348h+var_247], r12b
0x1402eb1df  mov     [rsp+348h+var_248], r12b
0x1402eb1e7  mov     al, [r13+18h]
0x1402eb1eb  lea     esi, [r12+1]
0x1402eb1f0  and     al, sil
0x1402eb1f3  mov     [rsp+348h+var_245], al
0x1402eb1fa  mov     rcx, r13; struct _VCB *
0x1402eb1fd  call    ?RefsUninitializePerfCountersTelemetry@@YAXPEAU_VCB@@@Z; RefsUninitializePerfCountersTelemetry(_VCB *)
0x1402eb202  mov     eax, [r13+1Ch]
0x1402eb206  test    al, al
0x1402eb208  jns     short loc_1402EB236
0x1402eb20a  mov     rcx, [r13+70h]
0x1402eb20e  call    MsGetVolumeUniqueGuid
0x1402eb213  mov     r8, rax
0x1402eb216  lea     rdx, [r13+19BCh]
0x1402eb21d  lea     rcx, [r13+19ACh]
0x1402eb224  call    cs:__imp_FsRtlDedupChangeUninit
0x1402eb22b  nop     dword ptr [rax+rax+00h]
0x1402eb230  btr     dword ptr [r13+1Ch], 7
0x1402eb236  mov     rcx, [r13+1880h]; NotificationEntry
0x1402eb23d  test    rcx, rcx
0x1402eb240  jz      short loc_1402EB255
0x1402eb242  call    cs:__imp_IoUnregisterPlugPlayNotification
0x1402eb249  nop     dword ptr [rax+rax+00h]
0x1402eb24e  mov     [r13+1880h], r12
0x1402eb255  mov     r8d, 4
0x1402eb25b  mov     dl, sil
0x1402eb25e  mov     rcx, r13
0x1402eb261  call    ?RefsProcessAsyncCloses@@YAXAEAU_VCB@@W4DrainAll@CLOSE_QUEUE@@W4AsyncCloseFlags@@@Z; RefsProcessAsyncCloses(_VCB &,CLOSE_QUEUE::DrainAll,AsyncCloseFlags)
0x1402eb266  mov     dl, sil; unsigned __int8
0x1402eb269  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402eb26c  call    ?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)
0x1402eb271  cmp     cs:RefsPcwCmsCounterSet, r12
0x1402eb278  jz      short loc_1402EB2A9
0x1402eb27a  cmp     [r13+1A20h], r12
0x1402eb281  jz      short loc_1402EB2A9
0x1402eb283  mov     rcx, [r13+1A28h]; Instance
0x1402eb28a  test    rcx, rcx
0x1402eb28d  jz      short loc_1402EB2A9
0x1402eb28f  call    cs:__imp_PcwCloseInstance
0x1402eb296  nop     dword ptr [rax+rax+00h]
0x1402eb29b  mov     [r13+1A20h], r12
0x1402eb2a2  mov     [r13+1A28h], r12
0x1402eb2a9  mov     rbx, [r13+0B0h]
0x1402eb2b0  test    rbx, rbx
0x1402eb2b3  jz      short loc_1402EB2D0
0x1402eb2b5  mov     rdx, rbx
0x1402eb2b8  mov     rcx, [r14+18h]
0x1402eb2bc  call    MsUninitializeCachingTableObject
0x1402eb2c1  mov     rdx, rbx
0x1402eb2c4  call    MsCloseDurableTableObject
0x1402eb2c9  mov     [r13+0B0h], r12
0x1402eb2d0  mov     rdx, [r13+0B8h]
0x1402eb2d7  test    rdx, rdx
0x1402eb2da  jz      short loc_1402EB2F8
0x1402eb2dc  mov     rcx, [r14+18h]
0x1402eb2e0  call    MsUninitializeCachingTableObject
0x1402eb2e5  mov     rdx, [r13+0B8h]
0x1402eb2ec  call    MsCloseDurableTableObject
0x1402eb2f1  mov     [r13+0B8h], r12
0x1402eb2f8  mov     rbx, [r13+28h]
0x1402eb2fc  test    rbx, rbx
0x1402eb2ff  jz      short loc_1402EB335
0x1402eb301  mov     r9d, 4
0x1402eb307  mov     r8, rbx
0x1402eb30a  mov     rdx, [rbx+88h]
0x1402eb311  mov     rcx, r14
0x1402eb314  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402eb319  mov     edx, 0C000026Eh; int
0x1402eb31e  mov     rcx, r13; struct _VCB *
0x1402eb321  call    ?RefsUsnCleanupAllReadWaiters@@YAXAEAU_VCB@@J@Z; RefsUsnCleanupAllReadWaiters(_VCB &,long)
0x1402eb326  mov     rdx, [rbx+88h]; struct _FCB *
0x1402eb32d  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402eb330  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x1402eb335  mov     edx, 0C000026Eh; int
0x1402eb33a  mov     rcx, r13; struct _VCB *
0x1402eb33d  call    ?RefsUsnNotifyDeletion@@YAXAEAU_VCB@@J@Z; RefsUsnNotifyDeletion(_VCB &,long)
0x1402eb342  btr     dword ptr [r13+18h], 13h
0x1402eb348  mov     eax, [r13+18h]
0x1402eb34c  and     eax, 0FFFFFFFEh
0x1402eb34f  mov     [r13+18h], eax
0x1402eb353  mov     [rsp+348h+var_208], r12
0x1402eb35b  mov     rdi, r15
0x1402eb35e  mov     [rsp+348h+var_1F8], r15
0x1402eb366  lea     rcx, [rsp+348h+var_1B8]
0x1402eb36e  call    cs:__imp_ExInitializeFastOwnerEntry
0x1402eb375  nop     dword ptr [rax+rax+00h]
0x1402eb37a  lea     rbx, [r13+270h]
0x1402eb381  mov     r8b, sil
0x1402eb384  lea     rdx, [rsp+348h+var_1B8]
0x1402eb38c  mov     rcx, rbx
0x1402eb38f  call    cs:__imp_ExAcquireFastResourceShared
0x1402eb396  nop     dword ptr [rax+rax+00h]
0x1402eb39b  lea     rdx, [rsp+348h+var_208]; void **
0x1402eb3a3  mov     rcx, r13; struct _VCB *
0x1402eb3a6  call    ?RefsGetNextFcbTableEntry@@YAPEAU_FCB@@PEAU_VCB@@PEAPEAX@Z; RefsGetNextFcbTableEntry(_VCB *,void * *)
0x1402eb3ab  mov     r15, rax
0x1402eb3ae  mov     [rsp+348h+var_218], rax
0x1402eb3b6  test    rax, rax
0x1402eb3b9  jz      short loc_1402EB3BF
0x1402eb3bb  lock add [rax+18h], esi
0x1402eb3bf  lea     rdx, [rsp+348h+var_1B8]
0x1402eb3c7  mov     rcx, rbx
0x1402eb3ca  test    rdi, rdi
0x1402eb3cd  jnz     short loc_1402EB3E0
0x1402eb3cf  call    cs:__imp_ExReleaseFastResource
0x1402eb3d6  nop     dword ptr [rax+rax+00h]
0x1402eb3db  jmp     loc_1402EB6D5
0x1402eb3e0  lock dec dword ptr [rdi+18h]
0x1402eb3e4  call    cs:__imp_ExReleaseFastResource
0x1402eb3eb  nop     dword ptr [rax+rax+00h]
0x1402eb3f0  mov     r9d, esi
0x1402eb3f3  xor     r8d, r8d
0x1402eb3f6  mov     rdx, rdi
0x1402eb3f9  mov     rcx, r14
0x1402eb3fc  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402eb401  mov     [rsp+348h+var_246], sil
0x1402eb409  mov     r15b, sil
0x1402eb40c  mov     [rsp+348h+var_244], sil
0x1402eb414  mov     rbx, r12
0x1402eb417  test    rdi, rdi
0x1402eb41a  jz      loc_1402EB671
0x1402eb420  lea     rax, [rdi+30h]
0x1402eb424  test    r15b, r15b
0x1402eb427  jz      short loc_1402EB42E
0x1402eb429  mov     rbx, [rax]
0x1402eb42c  jmp     short loc_1402EB431
0x1402eb42e  mov     rbx, [rbx]
0x1402eb431  mov     r15b, r12b
0x1402eb434  mov     [rsp+348h+var_244], r12b
0x1402eb43c  cmp     rbx, rax
0x1402eb43f  jz      loc_1402EB671
0x1402eb445  lea     rcx, [rbx-78h]
0x1402eb449  mov     [rsp+348h+var_1D0], rcx
0x1402eb451  cmp     [rcx+0F0h], r12
0x1402eb458  jz      short loc_1402EB4AB
0x1402eb45a  lea     rax, [rsp+348h+var_247]
0x1402eb462  mov     [rdi+0F8h], rax
0x1402eb469  mov     [rsp+348h+var_247], r12b
0x1402eb471  mov     r8d, esi; unsigned int
0x1402eb474  mov     rdx, rcx; struct _SCB *
0x1402eb477  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402eb47a  call    ?RefsDeleteInternalAttributeStream@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@KE@Z; RefsDeleteInternalAttributeStream(_IRP_CONTEXT *,_SCB *,ulong,uchar)
0x1402eb47f  mov     r15b, sil
0x1402eb482  mov     [rsp+348h+var_244], sil
0x1402eb48a  lea     rcx, [rbx-78h]
0x1402eb48e  cmp     [rsp+348h+var_247], r12b
0x1402eb496  jz      short loc_1402EB50F
0x1402eb498  mov     rdi, r12
0x1402eb49b  mov     [rsp+348h+var_1F8], r12
0x1402eb4a3  mov     [rsp+348h+var_246], r12b
0x1402eb4ab  cmp     rcx, [r13+28h]
0x1402eb4af  jnz     short loc_1402EB4BD
0x1402eb4b1  mov     rcx, r13; struct _VCB *
0x1402eb4b4  call    ?RefsUsnRemoveAllModifiedOpenFiles@@YAXAEAU_VCB@@@Z; RefsUsnRemoveAllModifiedOpenFiles(_VCB &)
0x1402eb4b9  lea     rcx, [rbx-78h]
0x1402eb4bd  cmp     rcx, [r13+48h]
0x1402eb4c1  jnz     short loc_1402EB4EB
0x1402eb4c3  cmp     [r13+370h], r12
0x1402eb4ca  jz      short loc_1402EB4EB
0x1402eb4cc  mov     rax, 7FFFFFFFFFFFFFFFh
0x1402eb4d6  mov     [r13+16E0h], rax
0x1402eb4dd  mov     [r13+16E8h], r12
0x1402eb4e4  mov     [r13+370h], r12
0x1402eb4eb  lea     rax, [r13+20h]
0x1402eb4ef  lea     rdx, [rax+40h]
0x1402eb4f3  mov     [rsp+348h+var_1D8], rax
0x1402eb4fb  cmp     rax, rdx
0x1402eb4fe  jz      loc_1402EB584
0x1402eb504  cmp     [rax], rcx
0x1402eb507  jz      short loc_1402EB518
0x1402eb509  add     rax, 8
0x1402eb50d  jmp     short loc_1402EB4F3
0x1402eb50f  mov     [rdi+0F8h], r12
0x1402eb516  jmp     short loc_1402EB4AB
0x1402eb518  mov     [rax], r12
0x1402eb51b  btr     qword ptr [rdi+8], 8
0x1402eb521  lea     rax, [rsp+348h+var_247]
0x1402eb529  mov     [rdi+0F8h], rax
0x1402eb530  mov     [rsp+348h+var_247], r12b
0x1402eb538  mov     [rsp+348h+var_320], r12d
0x1402eb53d  mov     byte ptr [rsp+348h+var_328], r12b
0x1402eb542  mov     r9b, sil
0x1402eb545  xor     r8d, r8d
0x1402eb548  mov     rdx, rcx
0x1402eb54b  mov     rcx, r14
0x1402eb54e  call    ?RefsDecrementCloseCounts@@YA_NPEAU_IRP_CONTEXT@@AEAU_SCB@@PEAU_LCB@@EEW4CloseCountFlags@@@Z; RefsDecrementCloseCounts(_IRP_CONTEXT *,_SCB &,_LCB *,uchar,uchar,CloseCountFlags)
0x1402eb553  cmp     [rsp+348h+var_247], r12b
0x1402eb55b  jz      short loc_1402EB572
0x1402eb55d  mov     rdi, r12
0x1402eb560  mov     [rsp+348h+var_1F8], r12
0x1402eb568  mov     [rsp+348h+var_246], r12b
0x1402eb570  jmp     short loc_1402EB579
0x1402eb572  mov     [rdi+0F8h], r12
0x1402eb579  mov     r15b, sil
0x1402eb57c  mov     [rsp+348h+var_244], sil
0x1402eb584  test    r15b, r15b
0x1402eb587  jz      loc_1402EB66C
0x1402eb58d  test    rdi, rdi
0x1402eb590  jz      loc_1402EB66C
0x1402eb596  cmp     [rsp+348h+var_248], r12b
0x1402eb59e  jnz     loc_1402EB66C
0x1402eb5a4  mov     rcx, [rdi+50h]
0x1402eb5a8  add     rcx, 270h
0x1402eb5af  mov     r8b, sil
0x1402eb5b2  xor     edx, edx
0x1402eb5b4  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402eb5bb  nop     dword ptr [rax+rax+00h]
0x1402eb5c0  lock add [rdi+18h], esi
0x1402eb5c4  mov     rcx, [rdi+50h]
0x1402eb5c8  add     rcx, 270h
0x1402eb5cf  xor     edx, edx
0x1402eb5d1  call    cs:__imp_ExReleaseFastResource
0x1402eb5d8  nop     dword ptr [rax+rax+00h]
0x1402eb5dd  mov     rdx, rdi; struct _FCB *
0x1402eb5e0  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402eb5e3  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x1402eb5e8  mov     [rsp+348h+var_246], r12b
0x1402eb5f0  cmp     [rdi+60h], r12
0x1402eb5f4  jz      short loc_1402EB61A
0x1402eb5f6  mov     [rsp+348h+var_1E0], rdi
0x1402eb5fe  mov     r8b, sil
0x1402eb601  mov     rdx, rdi
0x1402eb604  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x1402eb609  mov     al, sil
0x1402eb60c  mov     [rsp+348h+var_248], al
0x1402eb613  mov     [rsp+348h+var_243], al
0x1402eb61a  mov     r9d, esi
0x1402eb61d  xor     r8d, r8d
0x1402eb620  mov     rdx, rdi
0x1402eb623  mov     rcx, r14
0x1402eb626  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1402eb62b  mov     [rsp+348h+var_246], sil
0x1402eb633  mov     rcx, [rdi+50h]
0x1402eb637  add     rcx, 270h
0x1402eb63e  mov     r8b, sil
0x1402eb641  xor     edx, edx
0x1402eb643  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402eb64a  nop     dword ptr [rax+rax+00h]
0x1402eb64f  lock dec dword ptr [rdi+18h]
0x1402eb653  mov     rcx, [rdi+50h]
0x1402eb657  add     rcx, 270h
0x1402eb65e  xor     edx, edx
0x1402eb660  call    cs:__imp_ExReleaseFastResource
0x1402eb667  nop     dword ptr [rax+rax+00h]
0x1402eb66c  jmp     loc_1402EB417
0x1402eb671  cmp     [rsp+348h+var_246], 0
0x1402eb679  jz      short loc_1402EB6BD
0x1402eb67b  cmp     [rsp+348h+var_248], r12b
0x1402eb683  jz      short loc_1402EB6A8
0x1402eb685  mov     [rsp+348h+var_1C8], rdi
0x1402eb68d  mov     rdx, rdi
0x1402eb690  mov     rcx, r14
0x1402eb693  call    ?RefsReleasePagingResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleasePagingResource(_IRP_CONTEXT *,PFCBOrSCB)
0x1402eb698  mov     [rsp+348h+var_248], r12b
0x1402eb6a0  mov     [rsp+348h+var_243], r12b
0x1402eb6a8  mov     rdx, rdi; struct _FCB *
0x1402eb6ab  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402eb6ae  call    ?RefsReleaseFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsReleaseFcb(_IRP_CONTEXT *,_FCB *)
0x1402eb6b3  mov     [rsp+348h+var_246], r12b
0x1402eb6bb  jmp     short loc_1402EB6CD
0x1402eb6bd  mov     [rsp+348h+var_248], r12b
0x1402eb6c5  mov     [rsp+348h+var_243], r12b
0x1402eb6cd  mov     r15, [rsp+348h+var_218]
0x1402eb6d5  test    r15, r15
0x1402eb6d8  jnz     loc_1402EB35B
0x1402eb6de  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402eb6e1  call    ?RefsBindMinstoreTransactionNoRaise@@YAJPEAU_IRP_CONTEXT@@@Z; RefsBindMinstoreTransactionNoRaise(_IRP_CONTEXT *)
0x1402eb6e6  mov     [r13+20h], r12
0x1402eb6ea  mov     rdx, [r13+68h]
  ... truncated ...
```
