# NtfsPerformDismountOnVcb

- ea: `0x140138c20`
- end: `0x140139dc7`
- name: `NtfsPerformDismountOnVcb`
- size: `4519`
- prototype: `void __fastcall(char *Context1, __int64, char, char, int, __int64)`
- caller_count: `7`
- callee_count: `33`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020240`
- `0x1400d4804`
- `0x1400dc204`
- `0x1400e2aa0`
- `0x1401c3700`
- `0x1401f63f8`
- `0x14029dd30`

## callees

- `0x140004068`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140010be0`
- `0x140012e70`
- `0x14001ca10`
- `0x14001ebf0`
- `0x140021c30`
- `0x140023250`
- `0x14002c130`
- `0x140034770`
- `0x14003fe78`
- `0x14004062c`
- `0x140059250`
- `0x14012be00`
- `0x140137c60`
- `0x140138b18`
- `0x140138b60`
- `0x140138ba0`
- `0x140138c20`
- `0x140139dd0`
- `0x140139e3c`
- `0x14013af10`
- `0x140140660`
- `0x14018dc4c`
- `0x1401cb2c4`
- `0x1401cfc18`
- `0x1401d295c`
- `0x140244130`
- `0x140246bc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14013927e`
- `ntoskrnl!KeSetEvent` at `0x14013927e`
- `ntoskrnl!ObfDereferenceObject` at `0x140139b88`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a6e82`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c8431`
- `ntoskrnl!ObfDereferenceObject` at `0x140139b88`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a6e82`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c8431`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140139b4d`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140139b4d`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402a6c35`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402c8209`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402a6c35`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1402c8209`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x140139d8e`
- `ntoskrnl!IoUnregisterPlugPlayNotification` at `0x140139d8e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140139750`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140139750`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401396f1`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401396f1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140138e90`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140138e90`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a6e69`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c8414`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a6e69`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c8414`
- `ntoskrnl!IoGetActivityIdThread` at `0x140139ca4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402a6a56`
- `ntoskrnl!IoGetActivityIdThread` at `0x140139ca4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402a6a56`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a69ae`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402a69ae`
- `ntoskrnl!ExReleasePushLockEx` at `0x140138ecf`
- `ntoskrnl!ExReleasePushLockEx` at `0x14013907d`
- `ntoskrnl!ExReleasePushLockEx` at `0x140138ecf`
- `ntoskrnl!ExReleasePushLockEx` at `0x14013907d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402a6c4c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402c8221`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402a6c4c`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402c8221`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013948a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013948a`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140139456`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140139456`
- `ntoskrnl!KeWaitForSingleObject` at `0x140139593`
- `ntoskrnl!KeWaitForSingleObject` at `0x140139b6e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140139593`
- `ntoskrnl!KeWaitForSingleObject` at `0x140139b6e`
- `ntoskrnl!KeInitializeEvent` at `0x140139538`
- `ntoskrnl!KeInitializeEvent` at `0x140139af5`
- `ntoskrnl!KeInitializeEvent` at `0x140139538`
- `ntoskrnl!KeInitializeEvent` at `0x140139af5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140138df5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013943c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140138df5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14013943c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140139cff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c8022`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140139cff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c8022`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139237`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139815`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139237`
- `ntoskrnl!ExFreePoolWithTag` at `0x140139815`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140139ce4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140139ce4`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140138dbd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401393a2`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140138dbd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401393a2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013985e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14013985e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140139883`
- `ntoskrnl!ExReleaseFastMutex` at `0x140139883`
- `ntoskrnl!CcFlushCache` at `0x140139b2b`
- `ntoskrnl!CcFlushCache` at `0x140139b2b`

## pseudocode

```c
void __fastcall NtfsPerformDismountOnVcb(char *Context1, __int64 a2, char a3, char a4, int a5, __int64 a6)
{
  char v6; // r14
  unsigned int *v9; // r13
  char v10; // r12
  void *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r13
  _QWORD *v15; // rax
  _QWORD *v16; // r12
  __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // r12
  __int64 v20; // r13
  __int64 NextFcbTableEntry; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  char v24; // r14
  _DWORD *v25; // r9
  __int64 v26; // r14
  _QWORD *v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rax
  char v30; // r12
  _QWORD *v31; // rcx
  PVOID *v32; // rax
  PVOID v33; // r14
  PVOID v34; // rax
  __int64 v35; // rcx
  _QWORD *v36; // rax
  __int64 v37; // rdx
  _QWORD *v38; // rcx
  __int64 *v39; // rax
  __int64 v40; // rcx
  _QWORD *i; // rax
  __int64 **v42; // rdx
  _QWORD *v43; // rcx
  PVOID *v44; // rax
  __int64 v45; // rcx
  signed __int64 v46; // rdx
  _QWORD *Pointer; // r8
  signed __int64 v48; // rcx
  signed __int64 v49; // rax
  signed __int64 v50; // rcx
  signed __int64 v51; // rax
  char *v52; // r12
  char *v53; // rcx
  __int64 v54; // rcx
  _QWORD *v55; // r14
  IRP *v56; // r13
  _QWORD **v57; // r8
  SECTION_OBJECT_POINTERS *v58; // rcx
  __int64 v59; // rdx
  const char *ProcessImageFileName; // r12
  _OWORD *v61; // rax
  _OWORD *ActivityIdThread; // rax
  struct _FAST_MUTEX *v63; // r14
  char v64; // al
  __int64 v65; // rax
  __int64 v66; // rax
  unsigned __int16 v67; // dx
  __int64 v68; // rcx
  const wchar_t *v69; // r14
  const WCHAR *v70; // rax
  int v71; // r13d
  int v72; // ecx
  const wchar_t *v73; // rcx
  WCHAR *v74; // rcx
  unsigned int *v75; // rcx
  WCHAR *v76; // rcx
  __int64 v77; // rax
  __int64 v78; // r11
  int v79; // r11d
  signed __int32 v80[8]; // [rsp+C8h] [rbp-1E8h] BYREF
  PLARGE_INTEGER Timeout; // [rsp+E8h] [rbp-1C8h]
  __int64 v82; // [rsp+F8h] [rbp-1B8h]
  __int64 v83; // [rsp+100h] [rbp-1B0h]
  int v84; // [rsp+150h] [rbp-160h]
  char v85; // [rsp+178h] [rbp-138h] BYREF
  char v86; // [rsp+179h] [rbp-137h] BYREF
  char v87; // [rsp+17Ah] [rbp-136h]
  char v88; // [rsp+17Bh] [rbp-135h]
  __int64 v89; // [rsp+180h] [rbp-130h]
  __int64 v90; // [rsp+188h] [rbp-128h]
  char *v91; // [rsp+190h] [rbp-120h]
  PEPROCESS Process; // [rsp+198h] [rbp-118h] BYREF
  _DWORD *v93; // [rsp+1A0h] [rbp-110h]
  int v94; // [rsp+1A8h] [rbp-108h]
  unsigned int *v95; // [rsp+1B0h] [rbp-100h]
  unsigned int *v96; // [rsp+1B8h] [rbp-F8h]
  PVOID Entry; // [rsp+1C0h] [rbp-F0h]
  unsigned int *v98; // [rsp+1C8h] [rbp-E8h] BYREF
  __int128 v99; // [rsp+1D0h] [rbp-E0h]
  __int64 v100; // [rsp+1E0h] [rbp-D0h]
  int v101; // [rsp+1E8h] [rbp-C8h]
  __int64 v102; // [rsp+1F0h] [rbp-C0h]
  PVOID P; // [rsp+1F8h] [rbp-B8h]
  const wchar_t *v104; // [rsp+200h] [rbp-B0h]
  struct _UNICODE_STRING UnicodeString; // [rsp+208h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+218h] [rbp-98h] BYREF
  __int64 v107; // [rsp+228h] [rbp-88h]
  _QWORD Event[7]; // [rsp+230h] [rbp-80h] BYREF

  v6 = a4;
  v91 = Context1;
  v89 = a2;
  v94 = a5;
  *(_QWORD *)&v99 = a6;
  v85 = 0;
  v9 = (unsigned int *)(a2 + 4);
  v93 = (_DWORD *)(a2 + 4);
  v10 = *(_BYTE *)(a2 + 4) & 1;
  if ( (*(_DWORD *)(a2 + 6436) & 2) != 0 )
  {
    v63 = (struct _FAST_MUTEX *)(a2 + 6256);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 6256));
    if ( *(_DWORD *)(a2 + 6432) )
    {
      v65 = TxfSearchAddTxfFcbCleanupList(*((_QWORD *)Context1 + 18), 0, 5, 0, 1);
      *(_DWORD *)(v65 + 16) |= 0x100000u;
      ExReleaseFastMutexUnsafe(v63);
      NtfsRaiseStatusInternal((__int64)Context1, -1073741608, 0, 0, 2295238);
    }
    ExReleaseFastMutexUnsafe(v63);
    v6 = a4;
  }
  IoStatus.Pointer = (PVOID)a2;
  v95 = v9;
  v98 = v9;
  v90 = 0;
  P = 0;
  v96 = v9;
  v87 = v10;
  v11 = *(void **)(a2 + 7992);
  if ( v11 )
  {
    IoUnregisterPlugPlayNotification(v11);
    *(_QWORD *)(a2 + 7992) = 0;
  }
  NtfsFspCloseInternal(0, a2, 1, 0, 0);
  NtfsCommitCurrentTransaction(Context1);
  if ( v6 )
  {
    v59 = *(_QWORD *)(a2 + 128);
    if ( v59 )
    {
      v86 = 0;
      NtfsAcquireExclusiveFcb((__int64)Context1, *(_QWORD *)(v59 + 184), v59, 4);
      NtfsDecrementCloseCounts((int)Context1, *(_QWORD *)(a2 + 128), 0, 1, 0, 0, &v86);
      *(_QWORD *)(a2 + 128) = 0;
    }
  }
  *(_BYTE *)(a2 + 5521) = 1;
  v104 = (const wchar_t *)(Context1 + 24);
  if ( !*((_DWORD *)Context1 + 6) && (*v9 & 0x10001000) == 0x10001000 && (*v9 & 0x8000000) == 0 )
    NtfsCheckpointVolume(Context1, 0, 5, NtfsLarge0.QuadPart);
  NtOfsCloseIndexSafe(Context1, a2 + 160);
  NtOfsCloseIndexSafe(Context1, a2 + 152);
  NtOfsCloseIndexSafe(Context1, a2 + 144);
  NtOfsCloseIndexSafe(Context1, a2 + 136);
  NtOfsCloseIndexSafe(Context1, a2 + 112);
  NtOfsCloseIndexSafe(Context1, a2 + 120);
  v12 = *(_QWORD *)(a2 + 104);
  if ( v12 )
  {
    NtfsAcquireExclusiveFcb((__int64)Context1, *(_QWORD *)(v12 + 184), *(_QWORD *)(a2 + 104), 4);
    NtfsDecrementCloseCounts((int)Context1, *(_QWORD *)(a2 + 104), 0, 1, 0, 1, 0);
  }
  v13 = *(_QWORD *)(a2 + 80);
  if ( v13 )
  {
    NtfsAcquireExclusiveFcb((__int64)Context1, *(_QWORD *)(v13 + 184), *(_QWORD *)(a2 + 80), 4);
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL) + 304LL) = &v85;
    v85 = 0;
    NtfsDecrementCloseCounts((int)Context1, *(_QWORD *)(a2 + 80), 0, 1, 0, 1, 0);
    if ( !v85 )
    {
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL) + 304LL) = 0;
      NtfsReleaseFcbEx((__int64)Context1, *(_QWORD *)(*(_QWORD *)(a2 + 80) + 184LL), 0);
    }
    *(_QWORD *)(a2 + 80) = 0;
  }
  v14 = *(_QWORD *)(a2 + 40);
  if ( v14 )
  {
    NtfsAcquireExclusiveFcb((__int64)Context1, *(_QWORD *)(v14 + 184), *(_QWORD *)(a2 + 40), 4);
    v107 = v14 + 160;
    Entry = (PVOID)(v14 + 120);
    FsRtlAcquireHeaderMutex(v14 + 120, v14 + 160);
    v34 = (PVOID)(v14 + 592);
    v33 = *(PVOID *)(v14 + 592);
    while ( v33 != v34 )
    {
      P = *(PVOID *)v33;
      if ( NtfsClearCancelRoutine(*((_QWORD *)v33 + 6)) )
      {
        if ( (*((_DWORD *)v33 + 17) & 1) != 0 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v14 + 212));
          v31 = *(_QWORD **)v33;
          if ( *(PVOID *)(*(_QWORD *)v33 + 8LL) != v33 || (v32 = (PVOID *)*((_QWORD *)v33 + 1), *v32 != v33) )
LABEL_53:
            __fastfail(3u);
          *v32 = v31;
          v31[1] = v32;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000026E, 0x230674u);
          NtfsExtendedCompleteRequestInternal(0, *((IRP **)v33 + 6), -1073741202, *((_QWORD *)v33 + 6) != 0, 0);
          if ( Context1 && *((_QWORD *)Context1 + 14) == *((_QWORD *)v33 + 6) )
            *((_QWORD *)Context1 + 14) = 0;
          *((_QWORD *)v33 + 6) = 0;
          ExFreePoolWithTag(v33, 0);
        }
        else
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000026E, 0x23067Eu);
          *((_DWORD *)v33 + 16) = -1073741202;
          KeSetEvent((PRKEVENT)v33 + 1, 0, 0);
        }
      }
      v33 = P;
      v34 = (PVOID)(v14 + 592);
    }
    FsRtlReleaseHeaderMutex(Entry, v107);
  }
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
  v15 = (_QWORD *)(a2 + 1960);
  v16 = *(_QWORD **)(a2 + 1960);
  while ( v16 != v15 )
  {
    v55 = v16;
    v56 = (IRP *)(v16 - 21);
    v16 = (_QWORD *)*v16;
    if ( NtfsClearCancelRoutine((__int64)v56) )
    {
      v35 = *v55;
      if ( *(_QWORD **)(*v55 + 8LL) != v55 )
        goto LABEL_53;
      v36 = (_QWORD *)v55[1];
      if ( (_QWORD *)*v36 != v55 )
        goto LABEL_53;
      *v36 = v35;
      *(_QWORD *)(v35 + 8) = v36;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000026E, 0x2306A9u);
      NtfsExtendedCompleteRequestInternal(0, v56, -1073741202, v56 != 0, 0);
      if ( Context1 && *((IRP **)Context1 + 14) == v56 )
        *((_QWORD *)Context1 + 14) = 0;
    }
    v15 = (_QWORD *)(a2 + 1960);
  }
  ClearFlagInterlocked(v98, 0x80000);
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
  NtOfsCloseAttributeSafe((int)Context1, *(_QWORD *)(a2 + 40));
  v17 = *(_QWORD *)(a2 + 168);
  if ( v17 )
  {
    NtfsAcquireExclusiveFcb((__int64)Context1, *(_QWORD *)(v17 + 184), *(_QWORD *)(a2 + 168), 4);
    NtfsDeleteInternalAttributeStream((__int64)Context1, *(_QWORD *)(a2 + 168), 1, 0);
    NtfsDecrementCleanupCounts((__int64)Context1, *(_QWORD *)(a2 + 168), 0, 0, 0);
    NtfsDecrementCloseCounts((int)Context1, *(_QWORD *)(a2 + 168), 0, 1, 0, 1, 0);
    NtfsReleaseFcbEx((__int64)Context1, *(_QWORD *)(*(_QWORD *)(a2 + 168) + 184LL), 0);
    *(_QWORD *)(a2 + 168) = 0;
  }
  NtfsCloseCorruptLog(Context1, a2 + 184);
  NtfsCloseCorruptLog(Context1, a2 + 176);
  v18 = *(void **)(a2 + 4696);
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0);
    *(_QWORD *)(a2 + 4696) = 0;
  }
  NtfsStopLogFile((__int64)Context1, a2);
  if ( (*v93 & 1) != 0 )
  {
    ClearFlagInterlocked(v96, 1);
    _InterlockedOr(v80, 0);
    NtfsUpdateCorruptionHandlingVolumeSetting(Context1, a2, 0);
  }
  v98 = 0;
  v19 = v90;
  do
  {
    v20 = v19;
    v100 = v19;
    ExAcquirePushLockSharedEx(a2 + 656, 0);
    NextFcbTableEntry = NtfsGetNextFcbTableEntry(a2, (unsigned __int64 *)&v98);
    v19 = NextFcbTableEntry;
    v90 = NextFcbTableEntry;
    if ( NextFcbTableEntry )
      _InterlockedAdd((volatile signed __int32 *)(NextFcbTableEntry + 28), 1u);
    v22 = a2 + 656;
    if ( !v20 )
    {
      ExReleasePushLockEx(v22, 0);
      continue;
    }
    _InterlockedDecrement((volatile signed __int32 *)(v20 + 28));
    ExReleasePushLockEx(v22, 0);
    v26 = 0;
    v102 = 0;
    while ( v20 )
    {
      v27 = (_QWORD *)(v20 + 64);
      if ( v26 )
        v28 = *(_QWORD **)(v26 + 168);
      else
        v28 = (_QWORD *)*v27;
      v26 = (__int64)(v28 - 21);
      if ( v28 == v27 )
        v26 = 0;
      v102 = v26;
      if ( !v26 )
        break;
      v29 = *(_QWORD *)(v26 + 280);
      if ( v29 )
      {
        v30 = 1;
        v88 = 1;
        if ( v26 == *(_QWORD *)(a2 + 192) || v26 == *(_QWORD *)(a2 + 88) )
        {
          NtfsAcquireExclusiveFcb((__int64)Context1, v20, v26, 1);
          *(_QWORD *)(v26 + 280) = 0;
          *(_QWORD *)(v20 + 304) = &v85;
          v85 = 0;
          NtfsDecrementCloseCounts((int)Context1, v26, 0, 1, 0, 0, 0);
          if ( v85 )
          {
            v20 = 0;
            v100 = 0;
            goto LABEL_49;
          }
LABEL_48:
          NtfsReleaseFcbEx((__int64)Context1, v20, 0);
          *(_QWORD *)(v20 + 304) = 0;
          goto LABEL_49;
        }
        if ( v29 == *(_QWORD *)(a2 + 216) )
        {
          NtfsDecrementCloseCounts((int)Context1, *(_QWORD *)(a2 + 64), 0, 1, 0, 1, 0);
          *(_QWORD *)(v26 + 280) = 0;
          goto LABEL_49;
        }
        if ( v26 == *(_QWORD *)(a2 + 40) )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(a2 + 1992));
          v57 = (_QWORD **)(a2 + 1976);
          for ( i = *(_QWORD **)(a2 + 1976); i != v57; i = *v57 )
          {
            v37 = *i;
            if ( *(_QWORD **)(*i + 8LL) != i )
              goto LABEL_53;
            v38 = (_QWORD *)i[1];
            if ( (_QWORD *)*v38 != i )
              goto LABEL_53;
            *v38 = v37;
            *(_QWORD *)(v37 + 8) = v38;
            *i = 0;
            v39 = i - 2;
            v40 = *v39;
            if ( *v39 )
            {
              if ( *(__int64 **)(v40 + 8) != v39 )
                goto LABEL_53;
              v42 = (__int64 **)v39[1];
              if ( *v42 != v39 )
                goto LABEL_53;
              *v42 = (__int64 *)v40;
              *(_QWORD *)(v40 + 8) = v42;
            }
          }
          ExReleaseFastMutex((PFAST_MUTEX)(a2 + 1992));
        }
        NtfsAcquireExclusiveFcb((__int64)Context1, v20, v26, 1);
        if ( v26 == *(_QWORD *)(a2 + 72) )
        {
          v53 = (char *)(a2 + 1608);
          v52 = *(char **)(a2 + 1608);
          if ( *(_QWORD *)(a2 + 1480) )
          {
            *(_QWORD *)(a2 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
            *(_QWORD *)(a2 + 5376) = 0;
            *(_QWORD *)(a2 + 1480) = 0;
          }
          if ( (!Context1 || (*((_DWORD *)Context1 + 4) & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          {
            McTemplateU0p_EtwWriteTransfer((__int64)v53, (const EVENT_DESCRIPTOR *)verfysup_c2003, a2);
            goto LABEL_102;
          }
          while ( v52 != v53 )
          {
            if ( (*((_DWORD *)v52 + 14) & 1) != 0 )
            {
              if ( (!Context1 || (*((_DWORD *)Context1 + 4) & 0x100000) == 0)
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
              {
                McTemplateU0p_EtwWriteTransfer((__int64)v53, (const EVENT_DESCRIPTOR *)verfysup_c2017, a2);
                v53 = (char *)(a2 + 1608);
              }
              break;
            }
            v43 = *(_QWORD **)v52;
            Entry = v43;
            if ( (char *)v43[1] != v52 )
              goto LABEL_53;
            v44 = (PVOID *)*((_QWORD *)v52 + 1);
            if ( *v44 != v52 )
              goto LABEL_53;
            *v44 = v43;
            v43[1] = v44;
            *(_QWORD *)(a2 + 312) -= *((_QWORD *)v52 + 6);
            if ( (*((_DWORD *)v52 + 14) & 0x20) != 0 )
            {
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
              *(_QWORD *)(a2 + 328) -= *((_QWORD *)v52 + 6);
              v45 = *(_QWORD *)(a2 + 328);
              if ( v45 < *(_QWORD *)(a2 + 8312) )
                *(_QWORD *)(a2 + 8312) = v45;
              v46 = *(_QWORD *)(a2 + 304) - (v45 >> 8) - *(_QWORD *)(a2 + 6368) - v45;
              if ( v46 <= 0 )
                v46 = 0;
              Pointer = IoStatus.Pointer;
              do
              {
                v48 = Pointer[1043];
                v49 = v48;
                if ( v46 < v48 )
                  v49 = _InterlockedCompareExchange64(Pointer + 1043, v46, v48);
              }
              while ( v49 != v48 );
              do
              {
                v50 = Pointer[1044];
                v51 = v50;
                if ( v46 > v50 )
                  v51 = _InterlockedCompareExchange64(Pointer + 1044, v46, v50);
              }
              while ( v51 != v50 );
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
            }
            if ( (*((_DWORD *)v52 + 14) & 2) == 0 )
            {
              FsRtlUninitializeBaseMcb((PBASE_MCB)(v52 + 16));
              *((_DWORD *)v52 + 14) |= 2u;
            }
            if ( v52 != (char *)(a2 + 1688) && v52 != (char *)(a2 + 1624) )
              ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v52);
            v52 = (char *)Entry;
LABEL_102:
            v53 = (char *)(a2 + 1608);
          }
          if ( *(char **)v53 != v53 )
          {
            NtfsIncrementCloseCounts((__int64)v53, v26, 1, 1);
            *(_DWORD *)(v26 + 512) |= 0x8000000u;
            NtfsWakeupDeallocatedClustersWaiters(a2, 0);
            NtfsReleaseFcbEx((__int64)Context1, v20, 0);
            NtfsMarkUnusedContextPreTrimProcessing((__int64)Context1);
            KeInitializeEvent((PRKEVENT)(a2 + 1552), SynchronizationEvent, 0);
            _InterlockedAdd((volatile signed __int32 *)(a2 + 1540), 1u);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 1536), 0) )
            {
              if ( (!Context1 || (*((_DWORD *)Context1 + 4) & 0x100000) == 0)
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
              {
                McTemplateU0p_EtwWriteTransfer(v54, (const EVENT_DESCRIPTOR *)verfysup_c2118, a2);
              }
              KeWaitForSingleObject((PVOID)(a2 + 1552), Executive, 0, 0, 0);
            }
            if ( (!Context1 || (*((_DWORD *)Context1 + 4) & 0x100000) == 0)
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
            {
              McTemplateU0p_EtwWriteTransfer(v54, (const EVENT_DESCRIPTOR *)verfysup_c2135, a2);
            }
            *(_BYTE *)(a2 + 1544) = 1;
            NtfsAcquireExclusiveFcb((__int64)Context1, v20, v26, 1);
            *(_BYTE *)(a2 + 1544) = 0;
          }
        }
        *(_QWORD *)(v20 + 304) = &v85;
        v85 = 0;
        if ( !*(_DWORD *)(*(_QWORD *)(v26 + 184) + 8LL) )
          NtfsPurgeFileRecordCache((__int64)Context1);
        v30 = NtfsDeleteInternalAttributeStream((__int64)Context1, v26, 1, 0);
        v88 = v30;
        if ( !v85 )
          goto LABEL_48;
        v20 = 0;
        v100 = 0;
        if ( v26 == *(_QWORD *)(a2 + 72) )
          *(_QWORD *)(a2 + 1576) = 0;
LABEL_49:
        if ( v30 )
        {
          if ( v26 == *(_QWORD *)(a2 + 48) )
          {
            *(_QWORD *)(a2 + 48) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 56) )
          {
            *(_QWORD *)(a2 + 56) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 64) )
          {
            *(_QWORD *)(a2 + 64) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 192) )
          {
            *(_QWORD *)(a2 + 192) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 80) )
          {
            *(_QWORD *)(a2 + 80) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 128) )
          {
            *(_QWORD *)(a2 + 128) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 32) )
          {
            *(_QWORD *)(a2 + 32) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 72) )
          {
            *(_QWORD *)(a2 + 72) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 88) )
          {
            *(_QWORD *)(a2 + 88) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 136) )
          {
            *(_QWORD *)(a2 + 136) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 208) )
          {
            *(_QWORD *)(a2 + 208) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 112) )
          {
            *(_QWORD *)(a2 + 112) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 120) )
          {
            *(_QWORD *)(a2 + 120) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 104) )
          {
            *(_QWORD *)(a2 + 104) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 96) )
          {
            *(_QWORD *)(a2 + 96) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 40) )
          {
            *(_QWORD *)(a2 + 40) = 0;
          }
          else if ( v26 == *(_QWORD *)(a2 + 200) )
          {
            *(_QWORD *)(a2 + 200) = 0;
          }
          v26 = 0;
          v102 = 0;
        }
      }
    }
    v19 = v90;
  }
  while ( v19 );
  *(_QWORD *)(a2 + 32) = 0;
  NtfsFspCloseInternal(0, a2, 1, 0, 0);
  v23 = *(unsigned int *)(a2 + 4904);
  if ( *(_DWORD *)(a2 + 260) == (_DWORD)v23 && *(_QWORD *)(a2 + 216) && (*(_DWORD *)(a2 + 572) & 8) == 0 )
  {
    memset(Event, 0, 32);
    IoStatus = 0;
    KeInitializeEvent((PRKEVENT)&Event[1], SynchronizationEvent, 0);
    v24 = a4;
    if ( a4 )
    {
      v58 = *(SECTION_OBJECT_POINTERS **)(*(_QWORD *)(a2 + 216) + 40LL);
      if ( v58 )
        CcFlushCache(v58, 0, 0, &IoStatus);
    }
    CcUninitializeCacheMap(*(PFILE_OBJECT *)(a2 + 216), &NtfsLarge0, (PCACHE_UNINITIALIZE_EVENT)Event);
    KeWaitForSingleObject(&Event[1], Executive, 0, 0, 0);
    *(_DWORD *)(a2 + 572) |= 8u;
    ObfDereferenceObject(*(PVOID *)(a2 + 216));
  }
  else
  {
    v24 = a4;
  }
  v25 = v93;
  if ( (*v93 & 0x8010000) == 0x10000 )
  {
    v86 = 0;
    v101 = *(_DWORD *)v104;
    v86 = 0;
    NtfsDeviceIoControl((__int64)Context1, *(struct _DEVICE_OBJECT **)(a2 + 224), 0x74804u, 0, &v86, 1u, 0, 0, 0);
    ClearFlagInterlocked(v96, 0x10000);
  }
  if ( a3 && (*v25 & 0x800) == 0 )
    NtfsPerformDismountOnVcbNonpaged(v23, a2, (_QWORD *)v99);
  if ( dword_140092174 )
  {
    if ( (unsigned __int8)(byte_140092178 - 1) <= 2u
      || (qword_140092160 & 0x8000000) == 0
      || (v64 = 1, (qword_140092168 & 0x8000000) != qword_140092168) )
    {
      v64 = 0;
    }
    if ( v64 && (!Context1 || (*((_DWORD *)Context1 + 4) & 0x100000LL) == 0) )
    {
      v99 = 0;
      v66 = *(_QWORD *)(a2 + 248);
      v67 = 0;
      if ( v66 )
      {
        v67 = *(_WORD *)(v66 + 6);
        if ( v67 > 0x40u || (v67 & 1) != 0 )
          v67 = 0;
        if ( v67 )
          *((_QWORD *)&v99 + 1) = v66 + 32;
      }
      if ( (!Context1 || (*((_DWORD *)Context1 + 4) & 0x100000LL) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000000) != 0 )
      {
        v68 = *(unsigned __int16 *)(a2 + 7856) >> 1;
        v83 = *(_QWORD *)(a2 + 7864);
        LODWORD(v82) = v68;
        LODWORD(Timeout) = v67 >> 1;
        McTemplateU0ppww_EtwWriteTransfer(
          v68,
          (const EVENT_DESCRIPTOR *)verfysup_c2474,
          Context1,
          a2,
          Timeout,
          *((_QWORD *)&v99 + 1),
          v82,
          v83);
      }
    }
  }
  if ( v87 && !v24 )
  {
    memset(&Event[4], 0, 24);
    UnicodeString = 0;
    v86 = 0;
    Process = 0;
    ProcessImageFileName = byte_140064C38;
    if ( Context1 && (v61 = (_OWORD *)*((_QWORD *)Context1 + 15)) != 0 )
    {
      *(_OWORD *)&Event[5] = *v61;
      Event[4] = &Event[5];
    }
    else
    {
      ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v23);
      if ( ActivityIdThread )
      {
        *(_OWORD *)&Event[5] = *ActivityIdThread;
        Event[4] = &Event[5];
      }
      else
      {
        Event[4] = 0;
      }
    }
    NtfsFillVcbVolumeGuid(Context1);
    NtfsRepairGetVolumeId((_DWORD)Context1, a2, 0, (unsigned int)&UnicodeString, (__int64)&v86);
    if ( PsLookupProcessByProcessId(*((HANDLE *)Context1 + 64), &Process) >= 0 )
      ProcessImageFileName = (const char *)PsGetProcessImageFileName(Process);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x40000) != 0 )
    {
      v69 = &word_140064400;
      v70 = &word_140064400;
      if ( *(_QWORD *)(a2 + 6736) )
        v70 = *(const WCHAR **)(a2 + 6736);
      *(_QWORD *)&v99 = v70;
      v71 = (*(_DWORD *)(a2 + 28) >> 2) & 1;
      v72 = *(_DWORD *)(a2 + 6660);
      if ( (unsigned int)(v72 - 1) > 0x13 )
        v72 = 0;
      LODWORD(v89) = v72;
      v73 = &word_140064400;
      if ( *(_QWORD *)(a2 + 6720) )
        v73 = *(const wchar_t **)(a2 + 6720);
      v104 = v73;
      v74 = (WCHAR *)&word_140064400;
      if ( *(_QWORD *)(a2 + 6704) )
        v74 = *(WCHAR **)(a2 + 6704);
      IoStatus.Pointer = v74;
      v75 = (unsigned int *)&word_140064400;
      if ( *(_QWORD *)(a2 + 6688) )
        v75 = *(unsigned int **)(a2 + 6688);
      v98 = v75;
      v76 = (WCHAR *)&word_140064400;
      if ( *(_QWORD *)(a2 + 6672) )
        v76 = *(WCHAR **)(a2 + 6672);
      Entry = v76;
      if ( *(_QWORD *)(a2 + 7864) )
        v69 = *(const wchar_t **)(a2 + 7864);
      if ( (*v93 & 0xC00) != 0x800 && (v77 = *(_QWORD *)(a2 + 248)) != 0 && (v78 = *(_QWORD *)(v77 + 16)) != 0 )
        v79 = (*(_DWORD *)(v78 + 48) >> 8) & 1;
      else
        LOBYTE(v79) = 0;
      McTemplateK0jmztzzzzzqjqtzpqss_EtwWriteTransfer(
        *((unsigned int *)Context1 + 128),
        (const EVENT_DESCRIPTOR *)NTFS_ETW_VOLUME_DISMOUNT_COMPLETE,
        (const GUID *)Event[4],
        a2 + 7824,
        a2 + 8528,
        UnicodeString.Buffer,
        v79,
        v69,
        (const wchar_t *)Entry,
        (const wchar_t *)v98,
        (const wchar_t *)IoStatus.Pointer,
        v104,
        v89,
        a2 + 7808,
        *(_DWORD *)(a2 + 6792),
        v71,
        (const wchar_t *)v99,
        v84,
        *((_DWORD *)Context1 + 128),
        ProcessImageFileName,
        NtfsDismountReasonMapping[v94]);
    }
    if ( v86 )
      RtlFreeUnicodeString(&UnicodeString);
    if ( Process )
      ObfDereferenceObject(Process);
  }
}

```

## disassembly

```asm
0x140138c20  mov     [rsp+arg_18], r9b
0x140138c25  mov     [rsp+arg_10], r8b
0x140138c2a  push    rbx
0x140138c2b  push    rsi
0x140138c2c  push    rdi
0x140138c2d  push    r12
0x140138c2f  push    r13
0x140138c31  push    r14
0x140138c33  push    r15
0x140138c35  sub     rsp, 1B0h
0x140138c3c  mov     rax, cs:__security_cookie
0x140138c43  xor     rax, rsp
0x140138c46  mov     [rsp+1E8h+var_48], rax
0x140138c4e  mov     r14b, r9b
0x140138c51  mov     rdi, rdx
0x140138c54  mov     rsi, rcx
0x140138c57  mov     [rsp+1E8h+var_120], rcx
0x140138c5f  mov     [rsp+1E8h+var_130], rdx
0x140138c67  mov     eax, [rsp+1E8h+arg_20]
0x140138c6e  mov     [rsp+1E8h+var_108], eax
0x140138c75  mov     rax, [rsp+1E8h+arg_28]
0x140138c7d  mov     qword ptr [rsp+1E8h+var_E0], rax
0x140138c85  xor     ebx, ebx
0x140138c87  mov     [rsp+1E8h+var_138], bl
0x140138c8e  lea     r13, [rdx+4]
0x140138c92  mov     [rsp+1E8h+var_110], r13
0x140138c9a  mov     r12b, [r13+0]
0x140138c9e  lea     r15d, [rbx+1]
0x140138ca2  and     r12b, r15b
0x140138ca5  mov     eax, [rdx+1924h]
0x140138cab  test    al, 2
0x140138cad  jnz     loc_140139CDA
0x140138cb3  mov     qword ptr [rsp+1E8h+IoStatus], rdi
0x140138cbb  mov     [rsp+1E8h+var_100], r13
0x140138cc3  mov     [rsp+1E8h+var_E8], r13
0x140138ccb  mov     [rsp+1E8h+var_128], rbx
0x140138cd3  mov     [rsp+1E8h+P], rbx
0x140138cdb  mov     [rsp+1E8h+var_F8], r13
0x140138ce3  mov     [rsp+1E8h+var_136], r12b
0x140138ceb  mov     rcx, [rdi+1F38h]; NotificationEntry
0x140138cf2  test    rcx, rcx
0x140138cf5  jnz     loc_140139D8E
0x140138cfb  mov     byte ptr [rsp+1E8h+Timeout], bl
0x140138cff  xor     r9d, r9d
0x140138d02  mov     r8b, r15b
0x140138d05  mov     rdx, rdi
0x140138d08  xor     ecx, ecx
0x140138d0a  call    NtfsFspCloseInternal
0x140138d0f  mov     rcx, rsi
0x140138d12  call    NtfsCommitCurrentTransaction
0x140138d17  test    r14b, r14b
0x140138d1a  jnz     loc_140139BD7
0x140138d20  mov     [rdi+1591h], r15b
0x140138d27  lea     rax, [rsi+18h]
0x140138d2b  mov     [rsp+1E8h+var_B0], rax
0x140138d33  cmp     [rax], ebx
0x140138d35  jz      loc_140139C3C
0x140138d3b  lea     rdx, [rdi+0A0h]
0x140138d42  mov     rcx, rsi
0x140138d45  call    NtOfsCloseIndexSafe
0x140138d4a  lea     rdx, [rdi+98h]
0x140138d51  mov     rcx, rsi
0x140138d54  call    NtOfsCloseIndexSafe
0x140138d59  lea     rdx, [rdi+90h]
0x140138d60  mov     rcx, rsi
0x140138d63  call    NtOfsCloseIndexSafe
0x140138d68  lea     rdx, [rdi+88h]
0x140138d6f  mov     rcx, rsi
0x140138d72  call    NtOfsCloseIndexSafe
0x140138d77  lea     rdx, [rdi+70h]
0x140138d7b  mov     rcx, rsi
0x140138d7e  call    NtOfsCloseIndexSafe
0x140138d83  lea     rdx, [rdi+78h]
0x140138d87  mov     rcx, rsi
0x140138d8a  call    NtOfsCloseIndexSafe
0x140138d8f  mov     rdx, [rdi+68h]
0x140138d93  test    rdx, rdx
0x140138d96  jnz     loc_1401395EB
0x140138d9c  mov     rdx, [rdi+50h]
0x140138da0  test    rdx, rdx
0x140138da3  jnz     loc_140139628
0x140138da9  mov     r13, [rdi+28h]
0x140138dad  test    r13, r13
0x140138db0  jnz     loc_1401396BB
0x140138db6  lea     rcx, [rdi+240h]; Mutex
0x140138dbd  call    cs:__imp_KeAcquireGuardedMutex
0x140138dc4  nop     dword ptr [rax+rax+00h]
0x140138dc9  lea     rax, [rdi+7A8h]
0x140138dd0  mov     r12, [rax]
0x140138dd3  cmp     r12, rax
0x140138dd6  jnz     loc_140139761
0x140138ddc  mov     edx, 80000h
0x140138de1  mov     rcx, [rsp+1E8h+var_E8]
0x140138de9  call    ClearFlagInterlocked
0x140138dee  lea     rcx, [rdi+240h]; Mutex
0x140138df5  call    cs:__imp_KeReleaseGuardedMutex
0x140138dfc  nop     dword ptr [rax+rax+00h]
0x140138e01  mov     rdx, [rdi+28h]
0x140138e05  mov     rcx, rsi
0x140138e08  call    NtOfsCloseAttributeSafe
0x140138e0d  mov     rdx, [rdi+0A8h]
0x140138e14  test    rdx, rdx
0x140138e17  jnz     loc_140139785
0x140138e1d  lea     rdx, [rdi+0B8h]
0x140138e24  mov     rcx, rsi
0x140138e27  call    NtfsCloseCorruptLog
0x140138e2c  lea     rdx, [rdi+0B0h]
0x140138e33  mov     rcx, rsi
0x140138e36  call    NtfsCloseCorruptLog
0x140138e3b  mov     rcx, [rdi+1258h]; P
0x140138e42  test    rcx, rcx
0x140138e45  jnz     loc_140139813
0x140138e4b  mov     rdx, rdi
0x140138e4e  mov     rcx, rsi
0x140138e51  call    NtfsStopLogFile
0x140138e56  mov     rcx, [rsp+1E8h+var_110]
0x140138e5e  mov     eax, [rcx]
0x140138e60  test    r15b, al
0x140138e63  jnz     loc_14013982D
0x140138e69  mov     [rsp+1E8h+var_E8], rbx
0x140138e71  mov     r12, [rsp+1E8h+var_128]
0x140138e79  mov     r13, r12
0x140138e7c  mov     [rsp+1E8h+var_D0], r12
0x140138e84  lea     r14, [rdi+290h]
0x140138e8b  xor     edx, edx
0x140138e8d  mov     rcx, r14
0x140138e90  call    cs:__imp_ExAcquirePushLockSharedEx
0x140138e97  nop     dword ptr [rax+rax+00h]
0x140138e9c  lea     rdx, [rsp+1E8h+var_E8]
0x140138ea4  mov     rcx, rdi
0x140138ea7  call    NtfsGetNextFcbTableEntry
0x140138eac  mov     r12, rax
0x140138eaf  mov     [rsp+1E8h+var_128], rax
0x140138eb7  test    rax, rax
0x140138eba  jz      short loc_140138EC1
0x140138ebc  lock add [rax+1Ch], r15d
0x140138ec1  xor     edx, edx
0x140138ec3  mov     rcx, r14
0x140138ec6  test    r13, r13
0x140138ec9  jnz     loc_140139078
0x140138ecf  call    cs:__imp_ExReleasePushLockEx
0x140138ed6  nop     dword ptr [rax+rax+00h]
0x140138edb  test    r12, r12
0x140138ede  jnz     short loc_140138E79
0x140138ee0  mov     [rdi+20h], rbx
0x140138ee4  mov     byte ptr [rsp+1E8h+Timeout], bl
0x140138ee8  xor     r9d, r9d
0x140138eeb  mov     r8b, r15b
0x140138eee  mov     rdx, rdi
0x140138ef1  xor     ecx, ecx
0x140138ef3  call    NtfsFspCloseInternal
0x140138ef8  mov     ecx, [rdi+1328h]
0x140138efe  cmp     [rdi+104h], ecx
0x140138f04  jnz     short loc_140138F13
0x140138f06  cmp     [rdi+0D8h], rbx
0x140138f0d  jnz     loc_140139ABE
0x140138f13  mov     r14b, [rsp+1E8h+arg_18]
0x140138f1b  mov     r9, [rsp+1E8h+var_110]
0x140138f23  mov     eax, [r9]
0x140138f26  and     eax, 8010000h
0x140138f2b  cmp     eax, 10000h
0x140138f30  jnz     loc_140139049
0x140138f36  mov     [rsp+1E8h+var_137], bl
0x140138f3d  mov     rax, [rsp+1E8h+var_B0]
0x140138f45  mov     eax, [rax]
0x140138f47  mov     [rsp+1E8h+var_C8], eax
0x140138f4e  mov     [rsp+1E8h+var_137], bl
0x140138f55  mov     [rsp+1E8h+var_1A8], rbx
0x140138f5a  mov     dword ptr [rsp+1E8h+var_1B0], ebx
0x140138f5e  mov     [rsp+1E8h+var_1B8], rbx
0x140138f63  mov     [rsp+1E8h+var_1C0], r15d
0x140138f68  lea     rax, [rsp+1E8h+var_137]
0x140138f70  mov     [rsp+1E8h+Timeout], rax
0x140138f75  xor     r9d, r9d
0x140138f78  mov     r8d, 74804h
0x140138f7e  mov     rdx, [rdi+0E0h]
0x140138f85  mov     rcx, rsi
0x140138f88  call    NtfsDeviceIoControl
0x140138f8d  mov     r9, [rsp+1E8h+var_110]
0x140138f95  jmp     loc_140139037
0x140138f9a  mov     edx, eax
0x140138f9c  mov     cl, cs:NtfsStatusDebugFlags
0x140138fa2  test    cl, cl
0x140138fa4  jz      short loc_140138FF5
0x140138fa6  test    eax, eax
0x140138fa8  jz      short loc_140138FF5
0x140138faa  cmp     eax, 126h
0x140138faf  jz      short loc_140138FF5
0x140138fb1  lea     ecx, [rax-12Ah]
0x140138fb7  cmp     ecx, 1
0x140138fba  jbe     short loc_140138FF5
0x140138fbc  cmp     eax, 0FFFFFFEDh
0x140138fbf  jnb     short loc_140138FF5
0x140138fc1  cmp     eax, 0C00000D8h
0x140138fc6  jz      short loc_140138FF5
0x140138fc8  cmp     eax, 0C0000016h
0x140138fcd  jz      short loc_140138FF5
0x140138fcf  cmp     eax, 0C0000011h
0x140138fd4  jz      short loc_140138FF5
0x140138fd6  add     eax, 7FFFFFFBh
0x140138fdb  cmp     eax, 1
0x140138fde  jbe     short loc_140138FF5
0x140138fe0  cmp     edx, 103h
0x140138fe6  jz      short loc_140138FF5
0x140138fe8  xor     ecx, ecx
0x140138fea  mov     r8d, 230960h
0x140138ff0  call    NtfsStatusTraceAndDebugInternal
0x140138ff5  mov     rsi, [rsp+1E8h+var_120]
0x140138ffd  mov     eax, [rsi+4]
0x140139000  btr     eax, 8
0x140139004  mov     [rsi+4], eax
0x140139007  mov     eax, [rsp+1E8h+var_C8]
0x14013900e  mov     [rsi+18h], eax
0x140139011  xor     ebx, ebx
0x140139013  lea     r15d, [rbx+1]
0x140139017  mov     rdi, [rsp+1E8h+var_130]
0x14013901f  mov     r9, [rsp+1E8h+var_100]
0x140139027  mov     [rsp+1E8h+var_110], r9
0x14013902f  mov     r14b, [rsp+1E8h+arg_18]
0x140139037  mov     edx, 10000h
0x14013903c  mov     rcx, [rsp+1E8h+var_F8]
0x140139044  call    ClearFlagInterlocked
0x140139049  cmp     [rsp+1E8h+arg_10], bl
0x140139050  jz      loc_140139B99
0x140139056  test    dword ptr [r9], 800h
0x14013905d  jnz     loc_140139B99
0x140139063  mov     r8, qword ptr [rsp+1E8h+var_E0]
0x14013906b  mov     rdx, rdi
0x14013906e  call    NtfsPerformDismountOnVcbNonpaged
0x140139073  jmp     loc_140139B99
0x140139078  lock dec dword ptr [r13+1Ch]
0x14013907d  call    cs:__imp_ExReleasePushLockEx
0x140139084  nop     dword ptr [rax+rax+00h]
0x140139089  mov     r14, rbx
0x14013908c  mov     [rsp+1E8h+var_C0], rbx
0x140139094  test    r13, r13
0x140139097  jz      loc_1401391A9
0x14013909d  lea     rax, [r13+40h]
0x1401390a1  test    r14, r14
0x1401390a4  jz      loc_1401391A1
0x1401390aa  mov     rcx, [r14+0A8h]
0x1401390b1  lea     r14, [rcx-0A8h]
0x1401390b8  cmp     rcx, rax
0x1401390bb  cmovz   r14, rbx
0x1401390bf  mov     [rsp+1E8h+var_C0], r14
0x1401390c7  test    r14, r14
0x1401390ca  jz      loc_1401391A9
0x1401390d0  mov     rax, [r14+118h]
0x1401390d7  test    rax, rax
0x1401390da  jz      loc_14013919C
0x1401390e0  mov     r12b, r15b
0x1401390e3  mov     [rsp+1E8h+var_135], r15b
0x1401390eb  cmp     r14, [rdi+0C0h]
0x1401390f2  jz      loc_140139949
0x1401390f8  cmp     r14, [rdi+58h]
0x1401390fc  jz      loc_140139949
0x140139102  cmp     rax, [rdi+0D8h]
0x140139109  jz      loc_14013991D
0x14013910f  cmp     r14, [rdi+28h]
0x140139113  jz      loc_140139854
0x140139119  mov     r9d, r15d
0x14013911c  mov     r8, r14
0x14013911f  mov     rdx, r13
0x140139122  mov     rcx, rsi
0x140139125  call    NtfsAcquireExclusiveFcb
0x14013912a  cmp     r14, [rdi+48h]
0x14013912e  jz      loc_140139894
0x140139134  lea     rax, [rsp+1E8h+var_138]
0x14013913c  mov     [r13+130h], rax
0x140139143  mov     [rsp+1E8h+var_138], bl
0x14013914a  mov     rax, [r14+0B8h]
0x140139151  cmp     [rax+8], ebx
0x140139154  jz      short loc_1401391B6
0x140139156  xor     r9d, r9d
0x140139159  mov     r8b, r15b
0x14013915c  mov     rdx, r14
0x14013915f  mov     rcx, rsi
0x140139162  call    NtfsDeleteInternalAttributeStream
0x140139167  mov     r12b, al
0x14013916a  mov     [rsp+1E8h+var_135], al
0x140139171  cmp     [rsp+1E8h+var_138], bl
0x140139178  jnz     loc_1401398FC
0x14013917e  xor     r8d, r8d
0x140139181  mov     rdx, r13
0x140139184  mov     rcx, rsi
0x140139187  call    NtfsReleaseFcbEx
0x14013918c  mov     [r13+130h], rbx
0x140139193  test    r12b, r12b
0x140139196  jnz     loc_1401399B2
0x14013919c  jmp     loc_140139094
0x1401391a1  mov     rcx, [rax]
0x1401391a4  jmp     loc_1401390B1
0x1401391a9  mov     r12, [rsp+1E8h+var_128]
0x1401391b1  jmp     loc_140138EDB
0x1401391b6  mov     rcx, rsi
0x1401391b9  call    NtfsPurgeFileRecordCache
0x1401391be  jmp     short loc_140139156
0x1401391c0  mov     ecx, 3
0x1401391c5  int     29h; Win8: RtlFailFast(ecx)
0x1401391c7  lock dec dword ptr [r13+0D4h]
  ... truncated ...
```
