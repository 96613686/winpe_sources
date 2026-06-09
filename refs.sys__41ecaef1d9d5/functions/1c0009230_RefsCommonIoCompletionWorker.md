# RefsCommonIoCompletionWorker

- ea: `0x1c0009230`
- end: `0x1c00098dc`
- name: `RefsCommonIoCompletionWorker`
- size: `1708`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0008060`

## callees

- `0x1c000384c`
- `0x1c0008a50`
- `0x1c0009230`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0014110`
- `0x1c0014450`
- `0x1c003aa60`
- `0x1c003de50`
- `0x1c004d17c`
- `0x1c00582b0`
- `0x1c0059038`
- `0x1c005bb10`
- `0x1c005f020`
- `0x1c005f0a0`
- `0x1c0062e40`
- `0x1c0062e8c`
- `0x1c0063db0`
- `0x1c0064c64`
- `0x1c0068168`
- `0x1c006ab80`
- `0x1c006ac80`
- `0x1c0093ddc`
- `0x1c00b1c78`
- `0x1c00b2610`
- `0x1c00b3400`
- `0x1c00b3dc8`
- `0x1c00fd504`
- `0x1c01630d0`
- `0x1c01632d4`
- `0x1c01634c8`
- `0x1c01cd240`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x1c00702bc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00702e1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00702bc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c00702e1`
- `ntoskrnl!KeSetEvent` at `0x1c000954d`
- `ntoskrnl!KeSetEvent` at `0x1c000954d`
- `ntoskrnl!DbgPrintEx` at `0x1c0070257`
- `ntoskrnl!DbgPrintEx` at `0x1c0070257`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00097c1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c00097c1`
- `ntoskrnl!ExQueryDepthSList` at `0x1c00097a4`
- `ntoskrnl!ExQueryDepthSList` at `0x1c00097a4`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1c007027a`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1c007027a`
- `ntoskrnl!_strnicmp` at `0x1c007030c`
- `ntoskrnl!_strnicmp` at `0x1c007030c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c00702f0`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1c00702f0`
- `ntoskrnl!IoFreeMdl` at `0x1c0070088`
- `ntoskrnl!IoFreeMdl` at `0x1c00700e2`
- `ntoskrnl!IoFreeMdl` at `0x1c0070131`
- `ntoskrnl!IoFreeMdl` at `0x1c0070088`
- `ntoskrnl!IoFreeMdl` at `0x1c00700e2`
- `ntoskrnl!IoFreeMdl` at `0x1c0070131`
- `ntoskrnl!MmUnlockPages` at `0x1c0070075`
- `ntoskrnl!MmUnlockPages` at `0x1c00700ca`
- `ntoskrnl!MmUnlockPages` at `0x1c0070119`
- `ntoskrnl!MmUnlockPages` at `0x1c0070075`
- `ntoskrnl!MmUnlockPages` at `0x1c00700ca`
- `ntoskrnl!MmUnlockPages` at `0x1c0070119`
- `ntoskrnl!CcUnpinData` at `0x1c00700fa`
- `ntoskrnl!CcUnpinData` at `0x1c0070149`
- `ntoskrnl!CcUnpinData` at `0x1c00700fa`
- `ntoskrnl!CcUnpinData` at `0x1c0070149`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1c006b8e2`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1c00701a9`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1c006b8e2`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1c00701a9`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x1c0009824`
- `ntoskrnl!ExReleaseDisownedFastResource` at `0x1c0009824`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c000964e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c006ffca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c000964e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c006ffca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c000968b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c000968b`

## pseudocode

```c
__int64 __fastcall RefsCommonIoCompletionWorker(__int64 a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // r12
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  char v16; // cl
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rdi
  __int64 v21; // r11
  __int64 v22; // r10
  __int64 v23; // r8
  char v24; // cl
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rbx
  _QWORD *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rax
  struct _MDL *v31; // rcx
  void *v32; // rcx
  struct _MDL *v33; // rcx
  void *v34; // rcx
  __int64 v35; // rcx
  unsigned int v36; // eax
  unsigned __int64 v37; // rdi
  __int64 v38; // rcx
  __int64 v39; // r8
  int v40; // eax
  int v41; // eax
  int v42; // ecx
  __int64 v43; // r9
  NTSTATUS v44; // ebx
  struct _KTHREAD *CurrentThread; // rdi
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // r8
  _QWORD *v50; // r8
  _QWORD *v51; // rcx
  int v52; // r12d
  __int64 v53; // rcx
  __int64 v54; // rdx
  struct _MDL *v55; // rcx
  struct _MDL *Next; // rdi
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v59; // rax
  __int64 v60; // [rsp+38h] [rbp-D8h] BYREF
  char v61; // [rsp+78h] [rbp-98h]
  _QWORD v62[2]; // [rsp+80h] [rbp-90h] BYREF
  ERESOURCE_THREAD ResourceThreadId; // [rsp+90h] [rbp-80h]
  __int64 v64; // [rsp+98h] [rbp-78h]
  __int64 v65; // [rsp+A0h] [rbp-70h]
  struct _ERESOURCE *v66; // [rsp+A8h] [rbp-68h]
  ERESOURCE_THREAD v67; // [rsp+B0h] [rbp-60h]
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-58h] BYREF
  __int64 *v69; // [rsp+D0h] [rbp-40h]
  struct _ERESOURCE *Resource; // [rsp+130h] [rbp+20h]

  v69 = &v60;
  v4 = *(_QWORD *)(a1 + 144);
  v65 = v4;
  v64 = *(_QWORD *)(v4 + 200);
  v5 = v64;
  v6 = *(_QWORD *)(a2 + 184);
  v7 = *(_QWORD *)(*(_QWORD *)(v6 + 48) + 24LL);
  v8 = *(_QWORD *)(v7 + 128);
  Resource = *(struct _ERESOURCE **)(v4 + 48);
  v66 = Resource;
  ResourceThreadId = *(_QWORD *)(v4 + 56);
  v67 = ResourceThreadId;
  v9 = *(_QWORD *)(v64 + 296);
  *(_QWORD *)(a1 + 24) = v9;
  if ( v9 )
  {
    MsReacquireTransactionContextThread();
    if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
    {
      v9 = 0x80000000LL;
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) |= 0x80000000uLL;
    }
  }
  if ( (*(_DWORD *)v4 & 0x80u) != 0 )
  {
    v15 = *(unsigned int *)(a2 + 48);
    if ( (int)v15 >= 0 )
      RefsIncReadCopyCounts(v8, v15, 0);
  }
  v10 = *(_DWORD *)(a2 + 48);
  if ( (unsigned int)v10 <= 0x40000009 || v10 >= 1073741836 )
  {
    *(_QWORD *)(a2 + 56) = *(unsigned int *)(v4 + 192);
    if ( *(_BYTE *)(v4 + 196) )
    {
      v9 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 190, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids, 303);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(303);
      *(_DWORD *)(a2 + 48) = 303;
    }
    if ( (*(_DWORD *)v4 & 2) == 0 )
    {
      v9 = *(_QWORD *)(v6 + 48);
      if ( v9 )
      {
        v11 = *(_DWORD *)(v9 + 80);
        if ( *(_BYTE *)v6 == 3 )
          v12 = v11 | 0x80000;
        else
          v12 = v11 | 0x1000;
        *(_DWORD *)(v9 + 80) = v12;
      }
    }
  }
  if ( *(int *)(a2 + 48) >= 0 && *(_BYTE *)(v5 + 281) )
  {
    if ( (*(_DWORD *)(a1 + 4) & 0x8000000) == 0 )
      goto LABEL_16;
    v61 = 0;
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) |= 0x40000000uLL;
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v7 + 360) + 16LL) + 64LL))(
            *(_QWORD *)(*(_QWORD *)(v7 + 360) + 16LL),
            *(_QWORD *)(a1 + 24),
            0);
    v61 = v16;
    if ( v16 && *(_BYTE *)(a1 + 40) == 4 )
    {
      v16 = MsEnterGlobalTables(*(_QWORD *)(a1 + 24));
      v61 = v16;
    }
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) &= ~0x40000000uLL;
    if ( v16 )
    {
LABEL_16:
      v13 = RefsFinishBuffers(a1, a2, v7, v5);
      if ( v13 >= 0 )
        goto LABEL_17;
    }
    else
    {
      v13 = -1073741608;
      v9 = 3221225556LL;
      if ( (*(_BYTE *)(a2 + 16) & 2) != 0 )
        v13 = -1073741740;
    }
    *(_DWORD *)(a2 + 48) = v13;
  }
LABEL_17:
  v14 = *(_DWORD *)(a2 + 48);
  if ( v14 < 0 )
  {
    if ( *(_BYTE *)(a1 + 40) == 4 && *(_BYTE *)(v5 + 282) && (v14 == -1073741391 || v14 == -1073741435) )
    {
      if ( (unsigned __int8)MsIsWPOutOfSync(*(_QWORD *)(a1 + 24)) )
      {
        *(_DWORD *)(a2 + 48) = -1073741608;
        if ( (*(_DWORD *)(a1 + 4) & 0x8000000) == 0 )
          MsSetOkayToResyncSMRBands(*(_QWORD *)(a1 + 24));
      }
    }
    RefsIsTriagePending(a1);
    LOBYTE(v17) = 1;
    RefsRestoreScbSnapshots(a1, v17);
    RefsAbortTransaction(a1);
    RefsRestoreScbSnapshots(a1, 0);
  }
  if ( (*(_DWORD *)v4 & 0x40) != 0 )
  {
    KeSetEvent((PRKEVENT)(v4 + 8), 0, 0);
    local_unwind_0(v69, &loc_1C000989D);
  }
  else if ( *(int *)(a2 + 48) >= 0 )
  {
    RefsCheckpointCurrentTransaction(a1);
    if ( *(_BYTE *)(a1 + 40) == 4 )
      RefsFlushForWriteThrough(a1, v7);
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x8000) != 0 )
  {
    v18 = *(_QWORD *)(a1 + 144);
    if ( *(_QWORD *)(v18 + 224) != v18 + 224 || *(_DWORD *)(v18 + 268) || (*(_BYTE *)(v18 + 240) & 0x40) != 0 )
    {
      MsUpdateCacheFromCacheContext(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 104LL), v18 + 216);
      MsFreeCacheContextResources(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 104LL), *(_QWORD *)(a1 + 144) + 216LL);
    }
  }
  v19 = *(_QWORD *)(v5 + 256);
  if ( v19 )
  {
    v20 = v5 + 72;
    v21 = *(_QWORD *)(v5 + 272);
    v22 = *(_QWORD *)(v5 + 264);
    v23 = *(_QWORD *)(v19 + 56);
    if ( !*(_BYTE *)(v5 + 280) )
    {
      v47 = *(_DWORD *)(v23 + 464);
      v48 = -4096;
      if ( v47 != 12 )
        v48 = -16384;
      v49 = 4095;
      if ( v47 != 12 )
        v49 = 0x3FFF;
      FsLibUnlockRangeShared(v19 + 64, v22 & v48, (v48 & (v21 + v22 + v49)) - (v22 & v48), v5 + 72);
      goto LABEL_63;
    }
    v24 = *(_BYTE *)(v23 + 464);
    v25 = v22 >> v24 << v24;
    v26 = (v21 + v22 + *(unsigned int *)(v23 + 456)) >> v24 << v24;
    v9 = 0;
    memset(&LockHandle, 0, sizeof(LockHandle));
    v27 = *(_QWORD *)(v19 + 64);
    if ( !*(_QWORD *)(v27 + 16) )
    {
LABEL_63:
      *(_QWORD *)(v5 + 256) = 0;
      goto LABEL_64;
    }
    v62[0] = v25;
    v62[1] = v26 - 1;
    if ( v5 == -72 || !*(_QWORD *)(v5 + 80) )
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v27, &LockHandle);
      v52 = FsLibPrivateUnlockRange(*(PVOID *)(v27 + 16));
      if ( v52 == -1073741698 && *(_QWORD *)(v27 + 24) )
        FsLibPrivateCheckWaitingRangeLocks(v27, v27, v62);
      if ( v52 < 0 )
        goto LABEL_61;
    }
    else
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v27, &LockHandle);
      v28 = *(_QWORD **)(v27 + 16);
      *(_QWORD *)(*(_QWORD *)(v5 + 72) + 8LL) &= ~*(_QWORD *)(v5 + 80);
      if ( *(_QWORD **)v20 != v28 && !*(_QWORD *)(*(_QWORD *)v20 + 8LL) )
      {
        v50 = v28;
        v51 = v28;
        if ( v28 )
        {
          while ( v51[1] || v51 == v28 )
          {
            v50 = v51;
            v51 = (_QWORD *)*v51;
            if ( !v51 )
              goto LABEL_59;
          }
          *v50 = *v51;
          ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v51);
        }
      }
    }
LABEL_59:
    if ( *(_QWORD *)(v27 + 24) )
      FsLibPrivateCheckWaitingRangeLocks(v27, v27, v62);
LABEL_61:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v5 != -72 )
      *(_QWORD *)(v5 + 80) = 0;
    goto LABEL_63;
  }
LABEL_64:
  if ( *(_QWORD *)(v5 + 16) )
  {
    v53 = *(_QWORD *)(a2 + 8);
    *(_DWORD *)(v53 + 40) = *(_DWORD *)(v5 + 8);
    v54 = *(_QWORD *)(a2 + 8);
    if ( *(_QWORD *)(v5 + 32) == v54 )
    {
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      *(_DWORD *)(v5 + 48) = 0;
      v54 = *(_QWORD *)(a2 + 8);
    }
    RefsDeleteMdlAndBuffer(v53, v54);
  }
  else
  {
    v29 = *(_QWORD *)(v5 + 32);
    if ( v29 )
    {
      RefsDeleteMdlAndBuffer(v9, v29);
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 0;
      *(_DWORD *)(v5 + 48) = 0;
    }
  }
  if ( *(_QWORD *)(v5 + 168) )
  {
    do
    {
      v55 = *(struct _MDL **)(v5 + 168);
      Next = v55->Next;
      MmUnlockPages(v55);
      IoFreeMdl(*(PMDL *)(v5 + 168));
      *(_QWORD *)(v5 + 168) = Next;
    }
    while ( Next );
  }
  v30 = *(_QWORD *)(v5 + 16);
  if ( v30 )
  {
    *(_QWORD *)(a2 + 8) = v30;
    *(_QWORD *)(a2 + 112) = *(_QWORD *)(v5 + 24);
  }
  if ( *(_QWORD *)(v5 + 184) )
    RefsDeleteMdlAndBuffer(v9, 0);
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  *(_QWORD *)v5 = 0;
  *(_QWORD *)(v5 + 184) = 0;
  *(_DWORD *)(v5 + 8) = 0;
  if ( *(_BYTE *)(v5 + 216) )
  {
    MmUnlockPages(*(PMDL *)(v5 + 192));
    *(_BYTE *)(v5 + 216) = 0;
  }
  v31 = *(struct _MDL **)(v5 + 192);
  if ( v31 )
  {
    IoFreeMdl(v31);
    *(_QWORD *)(v5 + 192) = 0;
  }
  v32 = *(void **)(v5 + 208);
  if ( v32 )
  {
    CcUnpinData(v32);
    *(_QWORD *)(v5 + 208) = 0;
  }
  *(_QWORD *)(v5 + 200) = 0;
  if ( *(_BYTE *)(v5 + 248) )
  {
    MmUnlockPages(*(PMDL *)(v5 + 224));
    *(_BYTE *)(v5 + 248) = 0;
  }
  v33 = *(struct _MDL **)(v5 + 224);
  if ( v33 )
  {
    IoFreeMdl(v33);
    *(_QWORD *)(v5 + 224) = 0;
  }
  v34 = *(void **)(v5 + 240);
  if ( v34 )
  {
    CcUnpinData(v34);
    *(_QWORD *)(v5 + 240) = 0;
  }
  *(_QWORD *)(v5 + 232) = 0;
  v35 = *(_QWORD *)(v5 + 304);
  if ( v35 )
    RefsCleanupIrpContext(v35, 0);
  v36 = *(_DWORD *)(v5 - 8);
  if ( v36 >= RefsNumberProcessors )
    v36 %= (unsigned int)RefsNumberProcessors;
  v37 = RefsCompressCtxLookasideList + ((unsigned __int64)v36 << 7);
  ++*(_DWORD *)(v37 + 28);
  if ( ExQueryDepthSList((PSLIST_HEADER)v37) >= *(_WORD *)(v37 + 16) )
  {
    ++*(_DWORD *)(v37 + 32);
    (*(void (__fastcall **)(__int64))(v37 + 56))(v5 - 8);
  }
  else
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)v37, (PSLIST_ENTRY)(v5 - 8));
  }
  *(_QWORD *)(v4 + 200) = 0;
  v38 = *(_QWORD *)(v4 + 168);
  if ( v38 )
  {
    RefsReleaseRangeLock(v38, *(_QWORD *)(v4 + 176), *(_DWORD *)(v4 + 184), 0, v4 + 32);
    *(_QWORD *)(v4 + 168) = 0;
  }
  if ( Resource )
    ExReleaseResourceForThreadLite(Resource, ResourceThreadId);
  v39 = *(_QWORD *)(v4 + 64);
  if ( v39 )
  {
    v40 = *(_DWORD *)(v4 + 152);
    if ( !v40 )
      __fastfail(5u);
    v41 = v40 - 1;
    *(_DWORD *)(v4 + 152) = v41;
    v42 = *(_DWORD *)(v4 + 156);
    if ( !v41 )
      v42 &= ~2u;
    *(_DWORD *)(v4 + 156) = v42 & 0xFFFFFFFB;
    ExReleaseDisownedFastResource(v39);
  }
  v43 = *(unsigned int *)(a2 + 48);
  if ( (int)v43 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 191, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids, v43);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(*(_DWORD *)(a2 + 48));
    RefsRaiseStatusInternal(a1, *(unsigned int *)(a2 + 48));
    __debugbreak();
  }
  if ( RefsStatusDebugEnabled )
  {
    v44 = *(_DWORD *)(a2 + 48);
    CurrentThread = KeGetCurrentThread();
    if ( RefsStatusDisplayStatus && RefsStatusDisplayStatus == v44 )
      DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", CurrentThread, v44, "DevIoSup.c", 19561);
    if ( (RefsStatusBreakOnStatus && RefsStatusBreakOnStatus == v44
       || RefsStatusBreakOnWin32Error && RefsStatusBreakOnWin32Error == RtlNtStatusToDosErrorNoTeb(v44))
      && (!RefsStatusBreakForThread || (struct _KTHREAD *)RefsStatusBreakForThread == CurrentThread)
      && (!RefsStatusBreakForProcess || (PEPROCESS)RefsStatusBreakForProcess == IoGetCurrentProcess()) )
    {
      if ( !RefsStatusBreakForImage
        || (CurrentProcess = IoGetCurrentProcess(),
            ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
            !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu)) )
      {
        __int2c();
      }
    }
    if ( v44 )
    {
      v59 = 4LL * (_InterlockedIncrement(&RefsStatusNextQueueEntry) % (unsigned int)RefsStatusDebugQueueMax);
      RefsStatusQueue[v59] = (__int64)CurrentThread;
      LODWORD(RefsStatusQueue[v59 + 1]) = v44;
      RefsStatusQueue[v59 + 2] = (__int64)"DevIoSup.c";
      LODWORD(RefsStatusQueue[v59 + 3]) = 19561;
    }
  }
  return RefsExtendedCompleteRequestInternal(a1, a2, *(unsigned int *)(a2 + 48));
}

```

## disassembly

```asm
0x1c0009230  mov     r11, rsp
0x1c0009233  mov     [r11+10h], rdx
0x1c0009237  mov     [r11+8], rcx
0x1c000923b  push    rbx
0x1c000923c  push    rsi
0x1c000923d  push    rdi
0x1c000923e  push    r12
0x1c0009240  push    r13
0x1c0009242  push    r14
0x1c0009244  push    r15
0x1c0009246  sub     rsp, 0A0h
0x1c000924d  mov     [rsp+0D8h+var_40], rsp
0x1c0009255  mov     r13, rdx
0x1c0009258  mov     r15, rcx
0x1c000925b  mov     r14, [rcx+90h]
0x1c0009262  mov     [r11-70h], r14
0x1c0009266  mov     rsi, [r14+0C8h]
0x1c000926d  mov     [r11-78h], rsi
0x1c0009271  mov     rbx, [rdx+0B8h]
0x1c0009278  mov     rax, [rbx+30h]
0x1c000927c  mov     rdi, [rax+18h]
0x1c0009280  mov     r12, [rdi+80h]
0x1c0009287  mov     rax, [r14+30h]
0x1c000928b  mov     [r11+20h], rax
0x1c000928f  mov     [r11-68h], rax
0x1c0009293  mov     rax, [r14+38h]
0x1c0009297  mov     [r11-80h], rax
0x1c000929b  mov     [r11-60h], rax
0x1c000929f  mov     rcx, [rsi+128h]
0x1c00092a6  mov     [r15+18h], rcx
0x1c00092aa  test    rcx, rcx
0x1c00092ad  jz      short loc_1C00092CB
0x1c00092af  call    MsReacquireTransactionContextThread
0x1c00092b4  test    dword ptr [r15+0Ch], 100h
0x1c00092bc  jz      short loc_1C00092CB
0x1c00092be  mov     rax, [r15+18h]
0x1c00092c2  mov     ecx, 80000000h
0x1c00092c7  or      [rax+10h], rcx
0x1c00092cb  mov     eax, [r14]
0x1c00092ce  test    al, al
0x1c00092d0  js      loc_1C00093B2
0x1c00092d6  mov     eax, [r13+30h]
0x1c00092da  cmp     eax, 40000009h
0x1c00092df  jbe     short loc_1C00092EC
0x1c00092e1  cmp     eax, 4000000Ch
0x1c00092e6  jl      loc_1C00093CE
0x1c00092ec  mov     eax, [r14+0C0h]
0x1c00092f3  mov     [r13+38h], rax
0x1c00092f7  cmp     byte ptr [r14+0C4h], 0
0x1c00092ff  jnz     loc_1C00093DA
0x1c0009305  lea     r12, WPP_GLOBAL_Control
0x1c000930c  mov     eax, [r14]
0x1c000930f  test    al, 2
0x1c0009311  jnz     short loc_1C000932F
0x1c0009313  mov     rcx, [rbx+30h]
0x1c0009317  test    rcx, rcx
0x1c000931a  jz      short loc_1C000932F
0x1c000931c  mov     eax, [rcx+50h]
0x1c000931f  cmp     byte ptr [rbx], 3
0x1c0009322  jz      loc_1C0009444
0x1c0009328  bts     eax, 0Ch
0x1c000932c  mov     [rcx+50h], eax
0x1c000932f  cmp     dword ptr [r13+30h], 0
0x1c0009334  jl      short loc_1C000936D
0x1c0009336  cmp     byte ptr [rsi+119h], 0
0x1c000933d  jz      short loc_1C000936D
0x1c000933f  test    dword ptr [r15+4], 8000000h
0x1c0009347  jnz     loc_1C000944D
0x1c000934d  mov     r9, rsi
0x1c0009350  mov     r8, rdi
0x1c0009353  mov     rdx, r13
0x1c0009356  mov     rcx, r15
0x1c0009359  call    RefsFinishBuffers
0x1c000935e  mov     [rsp+0D8h+arg_10], eax
0x1c0009365  test    eax, eax
0x1c0009367  js      loc_1C00094CC
0x1c000936d  mov     eax, [r13+30h]
0x1c0009371  test    eax, eax
0x1c0009373  js      loc_1C00094D5
0x1c0009379  mov     eax, [r14]
0x1c000937c  test    al, 40h
0x1c000937e  jnz     loc_1C0009544
0x1c0009384  cmp     dword ptr [r13+30h], 0
0x1c0009389  jl      loc_1C000956E
0x1c000938f  mov     rcx, r15
0x1c0009392  call    RefsCheckpointCurrentTransaction
0x1c0009397  cmp     byte ptr [r15+28h], 4
0x1c000939c  jnz     loc_1C000956E
0x1c00093a2  mov     rdx, rdi
0x1c00093a5  mov     rcx, r15
0x1c00093a8  call    RefsFlushForWriteThrough
0x1c00093ad  jmp     loc_1C000956E
0x1c00093b2  mov     edx, [r13+30h]
0x1c00093b6  test    edx, edx
0x1c00093b8  js      loc_1C00092D6
0x1c00093be  xor     r8d, r8d
0x1c00093c1  mov     rcx, r12
0x1c00093c4  call    RefsIncReadCopyCounts
0x1c00093c9  jmp     loc_1C00092D6
0x1c00093ce  lea     r12, WPP_GLOBAL_Control
0x1c00093d5  jmp     loc_1C000932F
0x1c00093da  lea     r12, WPP_GLOBAL_Control
0x1c00093e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00093e8  cmp     rcx, r12
0x1c00093eb  jz      short loc_1C0009415
0x1c00093ed  test    dword ptr [rcx+2Ch], 100h
0x1c00093f4  jz      short loc_1C0009415
0x1c00093f6  cmp     byte ptr [rcx+29h], 5
0x1c00093fa  jb      short loc_1C0009415
0x1c00093fc  mov     edx, 0BEh
0x1c0009401  lea     r9d, [rdx+71h]
0x1c0009405  lea     r8, WPP_a1f0ec5c527f3c4dda14189a8c4d4f39_Traceguids
0x1c000940c  mov     rcx, [rcx+18h]
0x1c0009410  call    WPP_SF_D
0x1c0009415  movzx   eax, cs:RefsStatusDebugEnabled
0x1c000941c  test    al, al
0x1c000941e  jz      short loc_1C0009437
0x1c0009420  mov     r8d, 4B51h
0x1c0009426  lea     rdx, aDeviosupC; "DevIoSup.c"
0x1c000942d  mov     ecx, 12Fh; Status
0x1c0009432  call    RefsStatusDebug
0x1c0009437  mov     dword ptr [r13+30h], 12Fh
0x1c000943f  jmp     loc_1C000930C
0x1c0009444  bts     eax, 13h
0x1c0009448  jmp     loc_1C000932C
0x1c000944d  mov     [rsp+0D8h+var_98], 0
0x1c0009452  mov     rax, [r15+18h]
0x1c0009456  or      qword ptr [rax+10h], 40000000h
0x1c000945e  mov     rdx, [r15+18h]
0x1c0009462  mov     rax, [rdi+168h]
0x1c0009469  mov     rcx, [rax+10h]
0x1c000946d  mov     rax, [rcx]
0x1c0009470  mov     rax, [rax+40h]
0x1c0009474  xor     r8d, r8d
0x1c0009477  call    cs:__guard_dispatch_icall_fptr
0x1c000947d  movzx   ecx, al
0x1c0009480  mov     [rsp+0D8h+var_98], al
0x1c0009484  test    al, al
0x1c0009486  jz      short loc_1C000949F
0x1c0009488  cmp     byte ptr [r15+28h], 4
0x1c000948d  jnz     short loc_1C000949F
0x1c000948f  mov     rcx, [r15+18h]
0x1c0009493  call    MsEnterGlobalTables
0x1c0009498  movzx   ecx, al
0x1c000949b  mov     [rsp+0D8h+var_98], al
0x1c000949f  mov     rax, [r15+18h]
0x1c00094a3  and     qword ptr [rax+10h], 0FFFFFFFFBFFFFFFFh
0x1c00094ab  test    cl, cl
0x1c00094ad  jnz     loc_1C000934D
0x1c00094b3  test    byte ptr [r13+10h], 2
0x1c00094b8  mov     eax, 0C00000D8h
0x1c00094bd  mov     ecx, 0C0000054h
0x1c00094c2  cmovnz  eax, ecx
0x1c00094c5  mov     [rsp+0D8h+arg_10], eax
0x1c00094cc  mov     [r13+30h], eax
0x1c00094d0  jmp     loc_1C000936D
0x1c00094d5  cmp     byte ptr [r15+28h], 4
0x1c00094da  jnz     short loc_1C000951B
0x1c00094dc  cmp     byte ptr [rsi+11Ah], 0
0x1c00094e3  jz      short loc_1C000951B
0x1c00094e5  cmp     eax, 0C00001B1h
0x1c00094ea  jz      short loc_1C00094F3
0x1c00094ec  cmp     eax, 0C0000185h
0x1c00094f1  jnz     short loc_1C000951B
0x1c00094f3  mov     rcx, [r15+18h]
0x1c00094f7  call    MsIsWPOutOfSync
0x1c00094fc  test    al, al
0x1c00094fe  jz      short loc_1C000951B
0x1c0009500  mov     dword ptr [r13+30h], 0C00000D8h
0x1c0009508  test    dword ptr [r15+4], 8000000h
0x1c0009510  jnz     short loc_1C000951B
0x1c0009512  mov     rcx, [r15+18h]
0x1c0009516  call    MsSetOkayToResyncSMRBands
0x1c000951b  mov     rcx, r15
0x1c000951e  call    RefsIsTriagePending
0x1c0009523  mov     dl, 1
0x1c0009525  mov     rcx, r15
0x1c0009528  call    RefsRestoreScbSnapshots
0x1c000952d  mov     rcx, r15
0x1c0009530  call    RefsAbortTransaction
0x1c0009535  xor     edx, edx
0x1c0009537  mov     rcx, r15
0x1c000953a  call    RefsRestoreScbSnapshots
0x1c000953f  jmp     loc_1C0009379
0x1c0009544  lea     rcx, [r14+8]; Event
0x1c0009548  xor     r8d, r8d; Wait
0x1c000954b  xor     edx, edx; Increment
0x1c000954d  call    cs:__imp_KeSetEvent
0x1c0009554  nop     dword ptr [rax+rax+00h]
0x1c0009559  lea     rdx, loc_1C000989D
0x1c0009560  mov     rcx, [rsp+0D8h+var_40]
0x1c0009568  call    _local_unwind_0
0x1c000956d  nop
0x1c000956e  test    dword ptr [r15+8], 8000h
0x1c0009576  jz      short loc_1C00095A9
0x1c0009578  mov     rdx, [r15+90h]
0x1c000957f  lea     rax, [rdx+0E0h]
0x1c0009586  cmp     [rax], rax
0x1c0009589  jnz     loc_1C006FEE6
0x1c000958f  cmp     dword ptr [rdx+10Ch], 0
0x1c0009596  ja      loc_1C006FEE6
0x1c000959c  test    byte ptr [rdx+0F0h], 40h
0x1c00095a3  jnz     loc_1C006FEE6
0x1c00095a9  mov     r9, [rsi+100h]
0x1c00095b0  test    r9, r9
0x1c00095b3  jz      loc_1C007001A
0x1c00095b9  lea     rdi, [rsi+48h]
0x1c00095bd  mov     r11, [rsi+110h]
0x1c00095c4  mov     r10, [rsi+108h]
0x1c00095cb  mov     r8, [r9+38h]
0x1c00095cf  cmp     byte ptr [rsi+118h], 0
0x1c00095d6  jz      loc_1C006FF1B
0x1c00095dc  movsx   ecx, byte ptr [r8+1D0h]
0x1c00095e4  mov     rdx, r10
0x1c00095e7  sar     rdx, cl
0x1c00095ea  shl     rdx, cl
0x1c00095ed  mov     eax, [r8+1C8h]
0x1c00095f4  add     rax, r10
0x1c00095f7  add     rax, r11
0x1c00095fa  sar     rax, cl
0x1c00095fd  shl     rax, cl
0x1c0009600  xorps   xmm0, xmm0
0x1c0009603  xor     ecx, ecx
0x1c0009605  movups  xmmword ptr [rsp+0D8h+LockHandle.LockQueue.Next], xmm0
0x1c000960d  mov     qword ptr [rsp+0D8h+LockHandle.OldIrql], rcx
0x1c0009615  mov     rbx, [r9+40h]
0x1c0009619  cmp     [rbx+10h], rcx
0x1c000961d  jz      loc_1C006FF67
0x1c0009623  mov     [rsp+0D8h+var_90], rdx
0x1c0009628  dec     rax
0x1c000962b  mov     [rsp+0D8h+var_88], rax
0x1c0009630  test    rdi, rdi
0x1c0009633  jz      loc_1C006FFBF
0x1c0009639  cmp     [rdi+8], rcx
0x1c000963d  jz      loc_1C006FFBF
0x1c0009643  lea     rdx, [rsp+0D8h+LockHandle]; LockHandle
0x1c000964b  mov     rcx, rbx; SpinLock
0x1c000964e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c0009655  nop     dword ptr [rax+rax+00h]
0x1c000965a  mov     rdx, [rbx+10h]
0x1c000965e  mov     rcx, [rdi]
0x1c0009661  mov     rax, [rdi+8]
0x1c0009665  not     rax
0x1c0009668  and     [rcx+8], rax
0x1c000966c  mov     rax, [rdi]
0x1c000966f  cmp     rax, rdx
0x1c0009672  jnz     loc_1C006FF6E
0x1c0009678  cmp     qword ptr [rbx+18h], 0
0x1c000967d  jnz     loc_1C00098C7
0x1c0009683  lea     rcx, [rsp+0D8h+LockHandle]; LockHandle
0x1c000968b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c0009692  nop     dword ptr [rax+rax+00h]
0x1c0009697  test    rdi, rdi
0x1c000969a  jz      loc_1C006FF67
0x1c00096a0  xor     ebx, ebx
0x1c00096a2  mov     [rdi+8], rbx
0x1c00096a6  mov     [rsi+100h], rbx
0x1c00096ad  cmp     qword ptr [rsi+10h], 0
0x1c00096b2  jnz     loc_1C0070021
0x1c00096b8  mov     rdx, [rsi+20h]
0x1c00096bc  test    rdx, rdx
0x1c00096bf  jnz     loc_1C0070052
0x1c00096c5  cmp     qword ptr [rsi+0A8h], 0
0x1c00096cd  jnz     loc_1C007006B
0x1c00096d3  mov     rax, [rsi+10h]
0x1c00096d7  test    rax, rax
0x1c00096da  jnz     loc_1C00700A5
0x1c00096e0  mov     r8, [rsi+0B8h]
0x1c00096e7  test    r8, r8
0x1c00096ea  jnz     loc_1C00700B6
0x1c00096f0  mov     [rsi+10h], rbx
0x1c00096f4  mov     [rsi+18h], rbx
0x1c00096f8  mov     [rsi], rbx
0x1c00096fb  mov     [rsi+0B8h], rbx
0x1c0009702  mov     [rsi+8], ebx
0x1c0009705  cmp     byte ptr [rsi+0D8h], 0
0x1c000970c  jnz     loc_1C00700C3
0x1c0009712  mov     rcx, [rsi+0C0h]; Mdl
0x1c0009719  test    rcx, rcx
0x1c000971c  jnz     loc_1C00700E2
0x1c0009722  mov     rcx, [rsi+0D0h]; Bcb
0x1c0009729  test    rcx, rcx
0x1c000972c  jnz     loc_1C00700FA
0x1c0009732  mov     [rsi+0C8h], rbx
0x1c0009739  cmp     byte ptr [rsi+0F8h], 0
0x1c0009740  jnz     loc_1C0070112
0x1c0009746  mov     rcx, [rsi+0E0h]; Mdl
0x1c000974d  test    rcx, rcx
0x1c0009750  jnz     loc_1C0070131
0x1c0009756  mov     rcx, [rsi+0F0h]; Bcb
0x1c000975d  test    rcx, rcx
0x1c0009760  jnz     loc_1C0070149
0x1c0009766  mov     [rsi+0E8h], rbx
0x1c000976d  mov     rcx, [rsi+130h]
0x1c0009774  test    rcx, rcx
0x1c0009777  jnz     loc_1C0070161
0x1c000977d  mov     r8, cs:RefsCompressCtxLookasideList
0x1c0009784  mov     eax, [rsi-8]
0x1c0009787  mov     ecx, cs:RefsNumberProcessors
0x1c000978d  cmp     eax, ecx
  ... truncated ...
```
