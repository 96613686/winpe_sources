# TxfRollforwardRedo

- ea: `0x1401d6948`
- end: `0x1401d7d55`
- name: `TxfRollforwardRedo`
- size: `5133`
- prototype: `__int64 __fastcall(__int64, CLFS_LSN *, _QWORD *)`
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400fd904`
- `0x1401f4220`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x14000cb00`
- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x140010e98`
- `0x1400291f0`
- `0x140029d80`
- `0x1400414f4`
- `0x140059250`
- `0x1400596c0`
- `0x1400ffd34`
- `0x140133f30`
- `0x14013ad80`
- `0x140140380`
- `0x140188028`
- `0x140188ce4`
- `0x1401d432c`
- `0x1401d5488`
- `0x1401d5ad0`
- `0x1401d6024`
- `0x1401d6948`
- `0x1401d90dc`
- `0x14020a724`
- `0x14020b5f4`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1401d7c17`
- `ntoskrnl!KeReleaseMutex` at `0x1401d7c17`
- `ntoskrnl!DbgPrintEx` at `0x1401d6fb3`
- `ntoskrnl!DbgPrintEx` at `0x1401d70f6`
- `ntoskrnl!DbgPrintEx` at `0x1401d7340`
- `ntoskrnl!DbgPrintEx` at `0x1401d749b`
- `ntoskrnl!DbgPrintEx` at `0x1401d75c6`
- `ntoskrnl!DbgPrintEx` at `0x1401d7773`
- `ntoskrnl!DbgPrintEx` at `0x1401d78ff`
- `ntoskrnl!DbgPrintEx` at `0x1401d7ab7`
- `ntoskrnl!DbgPrintEx` at `0x1402cc802`
- `ntoskrnl!DbgPrintEx` at `0x1401d6fb3`
- `ntoskrnl!DbgPrintEx` at `0x1401d70f6`
- `ntoskrnl!DbgPrintEx` at `0x1401d7340`
- `ntoskrnl!DbgPrintEx` at `0x1401d749b`
- `ntoskrnl!DbgPrintEx` at `0x1401d75c6`
- `ntoskrnl!DbgPrintEx` at `0x1401d7773`
- `ntoskrnl!DbgPrintEx` at `0x1401d78ff`
- `ntoskrnl!DbgPrintEx` at `0x1401d7ab7`
- `ntoskrnl!DbgPrintEx` at `0x1402cc802`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d7bf5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d7bf5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d702c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d702c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d7065`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d7065`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6add`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6d48`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6add`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6d48`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d704a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d751a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d704a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d751a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f16`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f46`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f16`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d6f46`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d6e70`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d6e70`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d6b8a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1401d6b8a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d7986`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402b0775`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d7986`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1402b0775`

## pseudocode

```c
__int64 __fastcall TxfRollforwardRedo(__int64 a1, CLFS_LSN *a2, _QWORD *a3)
{
  CLFS_LSN *v6; // r12
  int v7; // eax
  int IrpContextForRecovery; // ecx
  __int64 v9; // rbx
  int Redo; // edi
  unsigned int v11; // r9d
  __int64 v12; // r8
  int v13; // r15d
  __int16 v14; // cx
  int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // r8d
  unsigned int v18; // r9d
  volatile signed __int64 *v19; // rdi
  PVOID v20; // r15
  signed int v21; // edi
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // ecx
  unsigned __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  unsigned __int64 v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // ecx
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  unsigned __int64 v38; // rax
  __int64 v39; // rcx
  int v40; // ecx
  signed __int64 v41; // rdx
  unsigned __int64 v42; // rax
  __int64 v43; // rcx
  unsigned __int64 v44; // rax
  __int64 v45; // rcx
  int v46; // ecx
  int v48; // edi
  CLFS_LSN *v49; // rax
  CLFS_RECORD_INDEX idxRecord; // eax
  unsigned int v51; // eax
  __int64 v52; // r8
  unsigned __int64 v53; // rax
  __int64 v54; // rcx
  unsigned __int64 v55; // rax
  __int64 v56; // rcx
  CLS_RECORD_TYPE peRecordType; // [rsp+94h] [rbp-3A4h] BYREF
  char v58; // [rsp+95h] [rbp-3A3h]
  char v59; // [rsp+96h] [rbp-3A2h]
  char v60; // [rsp+97h] [rbp-3A1h]
  PVOID ppvReadBuffer; // [rsp+98h] [rbp-3A0h] BYREF
  int v62[2]; // [rsp+A0h] [rbp-398h] BYREF
  ULONG pcbBuffer; // [rsp+A8h] [rbp-390h] BYREF
  CLFS_LSN plsnRecord; // [rsp+B0h] [rbp-388h] BYREF
  PVOID pvReadContext; // [rsp+B8h] [rbp-380h] BYREF
  CLFS_LSN plsn1; // [rsp+C0h] [rbp-378h] BYREF
  int *v67; // [rsp+C8h] [rbp-370h]
  CLFS_LSN plsnFirst; // [rsp+D0h] [rbp-368h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-360h]
  CLFS_LSN *v70; // [rsp+E0h] [rbp-358h]
  CLFS_LSN plsnUndoNext; // [rsp+E8h] [rbp-350h] BYREF
  unsigned int *v72; // [rsp+F0h] [rbp-348h]
  CLFS_LSN *plsn2; // [rsp+F8h] [rbp-340h]
  _QWORD *v74; // [rsp+100h] [rbp-338h]
  _QWORD *v75; // [rsp+108h] [rbp-330h]
  CLFS_LSN plsnPrevious; // [rsp+110h] [rbp-328h] BYREF
  __int64 v77; // [rsp+118h] [rbp-320h]
  CLFS_LSN v78; // [rsp+120h] [rbp-318h] BYREF
  CLFS_LSN v79; // [rsp+128h] [rbp-310h] BYREF
  _OWORD v80[2]; // [rsp+130h] [rbp-308h] BYREF
  __int64 v81; // [rsp+150h] [rbp-2E8h]
  int v82[164]; // [rsp+160h] [rbp-2D8h] BYREF

  v75 = a3;
  plsn2 = a2;
  v67 = (int *)a3;
  v69 = a1;
  v70 = a2;
  v74 = a3;
  memset(v80, 0, sizeof(v80));
  v81 = 0;
  memset(v82, 0, sizeof(v82));
  pvReadContext = 0;
  ppvReadBuffer = 0;
  pcbBuffer = 0;
  plsnFirst.ullOffset = CLFS_LSN_NULL_EXT;
  plsnUndoNext.ullOffset = CLFS_LSN_NULL_EXT;
  plsnPrevious.ullOffset = CLFS_LSN_NULL_EXT;
  plsnRecord.ullOffset = CLFS_LSN_NULL_EXT;
  v78.ullOffset = CLFS_LSN_NULL_EXT;
  v79.ullOffset = CLFS_LSN_NULL_EXT;
  plsn1.ullOffset = CLFS_LSN_NULL_EXT;
  peRecordType = 0;
  *(_QWORD *)v62 = 0;
  v6 = (CLFS_LSN *)(a1 + 128);
  v72 = (unsigned int *)(a1 + 128);
  v7 = *(_DWORD *)(a1 + 128);
  if ( (v7 & 4) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x3000E4u);
    return 3221225485LL;
  }
  if ( (v7 & 2) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0x40190034u, 0x3000ECu);
    return 1075380276;
  }
  IrpContextForRecovery = TxfCreateIrpContextForRecovery(a1, (__int64)v82, (__int64)v80);
  if ( a2 || a3 )
  {
    if ( IrpContextForRecovery == -1073741432 )
      NtfsCheckpointForLogFileFull((__int64)v82);
    NtfsAcquireExclusiveScbEx((__int64)v82, *(_QWORD *)(a1 + 288), 0);
    TxfUpdateTopsMetadataStream((int)v82, 0, 0, (__int64)a3, a2, 0, 0, 0, 0, 0, 0, 0, 0, 0);
    NtfsCheckpointCurrentTransaction((__int64)v82);
    NtfsCleanupIrpContext((__int64)v82, 0, v52);
    IrpContextForRecovery = 0;
    *(_DWORD *)(*(_QWORD *)&v82[36] + 24LL) = 0;
    v6 = (CLFS_LSN *)v72;
    if ( a2 )
      *(CLFS_LSN *)(a1 + 432) = *a2;
    else
      *(_QWORD *)(a1 + 440) = *a3;
  }
  v70 = v6;
  v67 = v82;
  v59 = 0;
  v58 = 0;
  v9 = 0;
  v77 = 0;
  v6->offset.idxRecord |= 4u;
  if ( IrpContextForRecovery < 0 )
    return (unsigned int)IrpContextForRecovery;
  if ( ClfsLsnNull((const CLFS_LSN *)(a1 + 448)) )
  {
    plsnFirst = *(CLFS_LSN *)(a1 + 408);
  }
  else
  {
    plsnFirst = *(CLFS_LSN *)(a1 + 448);
    v58 = 1;
    v60 = 1;
  }
  v82[109] |= 0x10u;
  NtfsPurgeFileRecordCache((__int64)v82);
  v82[1] |= 0x200u;
  peRecordType = 3;
  Redo = ClfsReadLogRecord(
           *(PVOID *)(a1 + 512),
           &plsnFirst,
           ClfsContextForward,
           &ppvReadBuffer,
           &pcbBuffer,
           &peRecordType,
           &plsnUndoNext,
           &plsnPrevious,
           &pvReadContext);
  v82[1] &= ~0x200u;
  v82[109] &= ~0x10u;
  if ( Redo < 0 && TxfRmInForcedRecovery(a1) )
  {
    if ( Redo == -1073741801
      || (v27 = (unsigned int)(Redo + 1073741697), (unsigned int)v27 <= 0x22)
      && (v28 = 0x408000001LL, _bittest64(&v28, v27)) )
    {
      ++HIDWORD((*TxfData)[1]);
      v13 = 2097219;
      goto LABEL_124;
    }
    if ( Redo == -1072037845
      || Redo == -1073741202
      || Redo == -1073741435
      || Redo == -1073741496
      || (v29 = (unsigned int)(Redo + 1073741667), (unsigned int)v29 <= 0x23)
      && (v30 = 0x800000041LL, _bittest64(&v30, v29)) )
    {
      v13 = 2097219;
    }
    else
    {
      v13 = 2097219;
      if ( ((unsigned int)(Redo + 1073741811) > 0x15 || !_bittest(&v13, Redo + 1073741811))
        && Redo != -2147483626
        && Redo != -1072037841 )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 388, "Status", Redo);
LABEL_124:
        Redo = TxfHandleRecoveryError((__int64)v82, a1, 2u, Redo, 0);
        goto LABEL_190;
      }
    }
    ++LODWORD((*TxfData)[2]);
    goto LABEL_124;
  }
  if ( Redo < 0 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)Redo < 0xFFFFFFED
      && Redo != -1073741802
      && Redo != -1073741807
      && (unsigned int)(Redo + 2147483643) > 1
      && Redo != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(0, Redo, 0x300191u);
    }
    v11 = 3146130;
LABEL_12:
    TxfHardErrorFcn((__int64)v82, a1, Redo, v11);
    goto LABEL_13;
  }
  _InterlockedAdd((volatile signed __int32 *)(a1 + 528), 1u);
  plsnRecord = plsnFirst;
  if ( !(unsigned __int8)TxfValidateLogRecord(ppvReadBuffer, pcbBuffer) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0190030, 0x30019Cu);
    v11 = 3146141;
LABEL_85:
    Redo = -1072103376;
    goto LABEL_12;
  }
  while ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 132), 4, 4) != 3 )
  {
    if ( v58 )
    {
      v58 = 0;
      v60 = 0;
    }
    else
    {
      if ( plsn2 && ClfsLsnGreater(&plsnRecord, plsn2)
        || (v14 = *(_WORD *)ppvReadBuffer, ((*(_WORD *)ppvReadBuffer - 4) & 0xFFF3) == 0)
        && v14 != 12
        && v74
        && *((_QWORD *)ppvReadBuffer + 10) > *v75 )
      {
        if ( ClfsLsnLess(&plsn1, (const CLFS_LSN *)(a1 + 432)) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x3001D3u);
          Redo = -1073741811;
          if ( !TxfRmInForcedRecovery(a1) )
            goto LABEL_13;
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            471,
            "Status",
            -1073741811);
          goto LABEL_50;
        }
        if ( v9 < *(_QWORD *)(a1 + 440) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x3001E1u);
          Redo = -1073741811;
          if ( !TxfRmInForcedRecovery(a1) )
            goto LABEL_13;
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            485,
            "Status",
            -1073741811);
          v17 = 0x2000;
        }
        else
        {
          if ( !ClfsLsnLess(&plsn1, (const CLFS_LSN *)(a1 + 408)) || !TxfRmInForcedRecovery(a1) )
          {
            v59 = 1;
            *(CLFS_LSN *)(a1 + 456) = plsn1;
LABEL_54:
            Redo = 0;
            goto LABEL_13;
          }
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x3001F8u);
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            506,
            "Status",
            -1073741811);
LABEL_50:
          v17 = 128;
        }
        ++LODWORD((*TxfData)[2]);
        v18 = -1073741811;
LABEL_52:
        TxfHandleRecoveryError((__int64)v82, a1, v17, v18, (__int64)ppvReadBuffer);
        goto LABEL_35;
      }
      if ( v14 == 32 || (v15 = *((_DWORD *)ppvReadBuffer + 1), v15 == 24) )
      {
        *(CLFS_LSN *)(a1 + 448) = plsnRecord;
        ExAcquireFastMutex(*(PFAST_MUTEX *)(a1 + 472));
        v19 = (volatile signed __int64 *)(a1 + 464);
        if ( ClfsLsnGreater(&plsnRecord, (const CLFS_LSN *)(a1 + 464)) )
        {
          do
            v41 = _InterlockedCompareExchange64(v19, NtfsLarge0.QuadPart, NtfsLarge0.QuadPart);
          while ( v41 != _InterlockedCompareExchange64(v19, plsnRecord.ullOffset, v41) );
        }
        ExReleaseFastMutex(*(PFAST_MUTEX *)(a1 + 472));
        v20 = ppvReadBuffer;
        if ( *(_WORD *)ppvReadBuffer == 32 )
        {
          v21 = TxfActOnAllDirtyFilesInRm((__int64)v82, a1, 6, (CLFS_LSN *)ppvReadBuffer + 10, 0, 0);
          if ( v21 < 0 )
          {
            if ( TxfRmInForcedRecovery(a1) )
            {
              DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 563, "Status", v21);
              if ( v21 == -1073741801
                || (v22 = (unsigned int)(v21 + 1073741697), (unsigned int)v22 <= 0x22)
                && (v23 = 0x408000001LL, _bittest64(&v23, v22)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( v21 == -1072037845
                     || v21 == -1073741202
                     || v21 == -1073741435
                     || v21 == -1073741496
                     || (v24 = (unsigned int)(v21 + 1073741667), (unsigned int)v24 <= 0x23)
                     && (v25 = 0x800000041LL, _bittest64(&v25, v24))
                     || (unsigned int)(v21 + 1073741811) <= 0x15 && (v26 = 2097219, _bittest(&v26, v21 + 1073741811))
                     || v21 == -2147483626
                     || v21 == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              TxfHandleRecoveryError((__int64)v82, a1, 0x40u, v21, (__int64)v20);
            }
          }
        }
      }
      else if ( v14 == 1 && v15 == 22 )
      {
        Redo = TxfProcessTransactionSummaryRecord((__int64)v82, a1, (unsigned __int16 *)ppvReadBuffer, &plsnRecord);
        if ( Redo )
          goto LABEL_13;
      }
      else
      {
        Redo = TxfTransMgrSearchAddTrans(a1, (_OWORD *)ppvReadBuffer + 2, 0, 19, 0, (__int64 *)v62);
        if ( (Redo < 0 || !*(_QWORD *)v62) && TxfRmInForcedRecovery(a1) )
        {
          DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 602, "Status", Redo);
          if ( Redo == -1073741801
            || (v31 = (unsigned int)(Redo + 1073741697), (unsigned int)v31 <= 0x22)
            && (v32 = 0x408000001LL, _bittest64(&v32, v31)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( Redo == -1072037845
                 || Redo == -1073741202
                 || Redo == -1073741435
                 || Redo == -1073741496
                 || (v33 = (unsigned int)(Redo + 1073741667), (unsigned int)v33 <= 0x23)
                 && (v34 = 0x800000041LL, _bittest64(&v34, v33))
                 || (unsigned int)(Redo + 1073741811) <= 0x15 && (v35 = 2097219, _bittest(&v35, Redo + 1073741811))
                 || Redo == -2147483626
                 || Redo == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          v18 = Redo;
          v17 = 256;
          goto LABEL_52;
        }
        if ( Redo )
        {
          v11 = 3146338;
          goto LABEL_12;
        }
        v16 = ((*((_WORD *)ppvReadBuffer + 36) & 1) << 24) | ((*((_WORD *)ppvReadBuffer + 36) & 2) << 24);
        if ( (*((_WORD *)ppvReadBuffer + 36) & 0x10) != 0 )
          _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v62 + 16LL), 0x40000u);
        ClfsLsnNull((const CLFS_LSN *)(*(_QWORD *)v62 + 40LL));
        _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)v62 + 16LL), 0xFCFFFFFF);
        _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v62 + 16LL), v16);
        Redo = TxfTransDoNextRedo((__int64)v82, *(CLFS_LSN **)v62, plsnRecord, plsnUndoNext.ullOffset, ppvReadBuffer);
        if ( Redo < 0 && TxfRmInForcedRecovery(a1) )
        {
          if ( Redo == -1073741801
            || (v36 = (unsigned int)(Redo + 1073741697), (unsigned int)v36 <= 0x22)
            && (v37 = 0x408000001LL, _bittest64(&v37, v36)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( Redo == -1072037845
                 || Redo == -1073741202
                 || Redo == -1073741435
                 || Redo == -1073741496
                 || (v38 = (unsigned int)(Redo + 1073741667), (unsigned int)v38 <= 0x23)
                 && (v39 = 0x800000041LL, _bittest64(&v39, v38))
                 || (unsigned int)(Redo + 1073741811) <= 0x15 && (v40 = 2097219, _bittest(&v40, Redo + 1073741811))
                 || Redo == -2147483626
                 || Redo == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          else
          {
            DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 724, "Status", Redo);
          }
          Redo = TxfHandleRecoveryError((__int64)v82, a1, 0x1000u, Redo, (__int64)ppvReadBuffer);
        }
        if ( Redo < 0 )
        {
          v11 = 3146467;
          goto LABEL_12;
        }
        TxfDereferenceTransaction((__int64 *)v62, 1);
      }
      plsn1 = plsnRecord;
      if ( ((*(_WORD *)ppvReadBuffer - 4) & 0xFFF3) == 0 && *(_WORD *)ppvReadBuffer != 12 )
      {
        if ( *((_QWORD *)ppvReadBuffer + 10) > v9 )
          v9 = *((_QWORD *)ppvReadBuffer + 10);
        v77 = v9;
      }
    }
LABEL_35:
    v82[109] |= 0x10u;
    NtfsPurgeFileRecordCache((__int64)v82);
    v82[1] |= 0x200u;
    peRecordType = 3;
    Redo = ClfsReadNextLogRecord(
             pvReadContext,
             &ppvReadBuffer,
             &pcbBuffer,
             &peRecordType,
             0,
             &plsnUndoNext,
             &plsnPrevious,
             &plsnRecord);
    v82[1] &= ~0x200u;
    v82[109] &= ~0x10u;
    if ( (int)(Redo + 0x80000000) >= 0 )
    {
      if ( Redo == -1073741807 )
        goto LABEL_54;
      if ( TxfRmInForcedRecovery(a1) )
      {
        if ( Redo == -1073741801
          || (v42 = (unsigned int)(Redo + 1073741697), (unsigned int)v42 <= 0x22)
          && (v43 = 0x408000001LL, _bittest64(&v43, v42)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( Redo == -1072037845
               || Redo == -1073741202
               || Redo == -1073741435
               || Redo == -1073741496
               || (v44 = (unsigned int)(Redo + 1073741667), (unsigned int)v44 <= 0x23)
               && (v45 = 0x800000041LL, _bittest64(&v45, v44))
               || (unsigned int)(Redo + 1073741811) <= 0x15 && (v46 = 2097219, _bittest(&v46, Redo + 1073741811))
               || Redo == -2147483626
               || Redo == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        else
        {
          DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 802, "Status", Redo);
        }
        Redo = TxfHandleRecoveryError((__int64)v82, a1, 0x200u, Redo, 0);
      }
    }
    if ( Redo == -1073741807 )
      goto LABEL_54;
    if ( Redo < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)Redo < 0xFFFFFFED
        && Redo != -1073741802
        && (unsigned int)(Redo + 2147483643) > 1
        && Redo != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(0, Redo, 0x300334u);
      }
      v11 = 3146549;
      goto LABEL_12;
    }
    if ( !(unsigned __int8)TxfValidateLogRecord(ppvReadBuffer, pcbBuffer) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0190030, 0x30033Du);
      v11 = 3146558;
      goto LABEL_85;
    }
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC0190005, 0x3001AFu);
  Redo = -1072103419;
LABEL_13:
  v13 = 2097219;
LABEL_190:
  v82[109] &= ~0x10u;
  if ( *(_QWORD *)v62 )
    TxfDereferenceTransaction((__int64 *)v62, 1);
  if ( pvReadContext )
  {
    NtfsPurgeFileRecordCache((__int64)v82);
    v82[1] |= 0x200u;
    ClfsTerminateReadLog(pvReadContext);
    v82[1] &= ~0x200u;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 528));
  }
  if ( Redo >= 0 )
  {
    TxfUpdateHighestFlushedLsn(a1, &plsn1);
    v48 = TxfActOnAllDirtyFilesInRm((__int64)v82, a1, 6, 0, &plsn1, 0);
    if ( v48 < 0 && TxfRmInForcedRecovery(a1) )
    {
      DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "TxfRecovery.c", 926, "Status", v48);
      if ( v48 == -1073741801
        || (v53 = (unsigned int)(v48 + 1073741697), (unsigned int)v53 <= 0x22)
        && (v54 = 0x408000001LL, _bittest64(&v54, v53)) )
      {
        ++HIDWORD((*TxfData)[1]);
      }
      else if ( v48 == -1072037845
             || v48 == -1073741202
             || v48 == -1073741435
             || v48 == -1073741496
             || (v55 = (unsigned int)(v48 + 1073741667), (unsigned int)v55 <= 0x23)
             && (v56 = 0x800000041LL, _bittest64(&v56, v55))
             || (unsigned int)(v48 + 1073741811) <= 0x15 && _bittest(&v13, v48 + 1073741811)
             || v48 == -2147483626
             || v48 == -1072037841 )
      {
        ++LODWORD((*TxfData)[2]);
      }
      v48 = TxfHandleRecoveryError((__int64)v82, a1, 0x400u, v48, 0);
    }
    if ( v48 < 0 )
    {
      TxfHardErrorFcn((__int64)v82, a1, v48, 0x3003ACu);
      v49 = v70;
    }
    else
    {
      v49 = v70;
      v70->offset.idxRecord &= ~4u;
    }
    idxRecord = v49->offset.idxRecord;
    if ( v59 )
      v51 = idxRecord | 0x200;
    else
      v51 = idxRecord & 0xFFFFFDFF;
    *v72 = v51;
    TxfComputeTargetLsnsForCheckpoint(a1, 1, &v78, &v79);
    KeWaitForSingleObject(*(PVOID *)(a1 + 544), Executive, 0, 0, 0);
    if ( v9 > *(_QWORD *)(a1 + 536) )
      *(_QWORD *)(a1 + 536) = v9;
    KeReleaseMutex(*(PRKMUTEX *)(a1 + 544), 0);
    Redo = TxfTransMgrCheckpoint((int)v82, a1 + 448, 0, 0, 0, 0, 0);
    if ( Redo < 0 && TxfRmInForcedRecovery(a1) )
      Redo = TxfHandleRecoveryError((__int64)v82, a1, 0x800u, Redo, 0);
    *(_QWORD *)(a1 + 440) = v9;
    TxfDeleteLinks(a1, 0, 0, 0);
  }
  else if ( Redo != -1072103419 )
  {
    TxfHardErrorFcn((__int64)v82, a1, Redo, 0x30040Au);
  }
  v82[3] &= ~0x10000u;
  NtfsCleanupIrpContext((__int64)v82, 0, v12);
  return (unsigned int)Redo;
}

```

## disassembly

```asm
0x1401d6948  push    rbx
0x1401d694a  push    rsi
0x1401d694b  push    rdi
0x1401d694c  push    r12
0x1401d694e  push    r13
0x1401d6950  push    r14
0x1401d6952  push    r15
0x1401d6954  sub     rsp, 400h
0x1401d695b  mov     rax, cs:__security_cookie
0x1401d6962  xor     rax, rsp
0x1401d6965  mov     [rsp+438h+var_48], rax
0x1401d696d  mov     [rsp+438h+var_330], r8
0x1401d6975  mov     rbx, rdx
0x1401d6978  mov     [rsp+438h+plsn2], rdx
0x1401d6980  mov     r14, rcx
0x1401d6983  mov     [rsp+438h+var_370], r8
0x1401d698b  mov     [rsp+438h+var_360], rcx
0x1401d6993  mov     [rsp+438h+var_358], rdx
0x1401d699b  mov     rdi, r8
0x1401d699e  mov     [rsp+438h+var_338], r8
0x1401d69a6  xorps   xmm0, xmm0
0x1401d69a9  xor     eax, eax
0x1401d69ab  movups  [rsp+438h+var_308], xmm0
0x1401d69b3  movups  [rsp+438h+var_2F8], xmm0
0x1401d69bb  mov     [rsp+438h+var_2E8], rax
0x1401d69c3  xor     edx, edx; Val
0x1401d69c5  mov     r8d, 290h; Size
0x1401d69cb  lea     rcx, [rsp+438h+var_2D8]; void *
0x1401d69d3  call    memset
0x1401d69d8  xor     esi, esi
0x1401d69da  mov     [rsp+438h+pvReadContext], rsi
0x1401d69e2  mov     [rsp+438h+ppvReadBuffer], rsi
0x1401d69ea  mov     [rsp+438h+pcbBuffer], esi
0x1401d69f1  mov     rax, cs:CLFS_LSN_NULL_EXT
0x1401d69f8  mov     qword ptr [rsp+438h+plsnFirst], rax
0x1401d6a00  mov     qword ptr [rsp+438h+var_350], rax
0x1401d6a08  mov     qword ptr [rsp+438h+var_328], rax
0x1401d6a10  mov     qword ptr [rsp+438h+plsnRecord], rax
0x1401d6a18  mov     [rsp+438h+var_318], rax
0x1401d6a20  mov     [rsp+438h+var_310], rax
0x1401d6a28  mov     qword ptr [rsp+438h+plsn1], rax
0x1401d6a30  mov     [rsp+438h+var_3A4], sil
0x1401d6a38  mov     qword ptr [rsp+438h+var_398], rsi
0x1401d6a40  lea     r12, [r14+80h]
0x1401d6a47  mov     [rsp+438h+var_348], r12
0x1401d6a4f  mov     eax, [r12]
0x1401d6a53  lea     r15d, [rsi+4]
0x1401d6a57  test    r15b, al
0x1401d6a5a  jnz     loc_1401D7CAD
0x1401d6a60  test    al, 2
0x1401d6a62  jz      loc_1401D7CD3
0x1401d6a68  lea     r8, [rsp+438h+var_308]
0x1401d6a70  lea     rdx, [rsp+438h+var_2D8]
0x1401d6a78  mov     rcx, r14
0x1401d6a7b  call    TxfCreateIrpContextForRecovery
0x1401d6a80  mov     ecx, eax
0x1401d6a82  test    rbx, rbx
0x1401d6a85  jnz     loc_1402CC67A
0x1401d6a8b  test    rdi, rdi
0x1401d6a8e  jnz     loc_1402CC67A
0x1401d6a94  mov     [rsp+438h+var_358], r12
0x1401d6a9c  lea     r13, [rsp+438h+var_2D8]
0x1401d6aa4  mov     [rsp+438h+var_370], r13
0x1401d6aac  mov     [rsp+438h+var_3A2], sil
0x1401d6ab4  mov     [rsp+438h+var_3A3], sil
0x1401d6abc  mov     rbx, rsi
0x1401d6abf  mov     [rsp+438h+var_320], rbx
0x1401d6ac7  or      [r12], r15d
0x1401d6acb  test    ecx, ecx
0x1401d6acd  js      loc_1401D7CF9
0x1401d6ad3  lea     rdi, [r14+1C0h]
0x1401d6ada  mov     rcx, rdi; plsn
0x1401d6add  call    cs:__imp_ClfsLsnNull
0x1401d6ae4  nop     dword ptr [rax+rax+00h]
0x1401d6ae9  mov     r12d, 1
0x1401d6aef  test    al, al
0x1401d6af1  jz      loc_1401D722C
0x1401d6af7  mov     rax, [r14+198h]
0x1401d6afe  mov     qword ptr [rsp+438h+plsnFirst], rax
0x1401d6b06  or      [rsp+438h+var_124], 10h
0x1401d6b0e  lea     rcx, [rsp+438h+var_2D8]
0x1401d6b16  call    NtfsPurgeFileRecordCache
0x1401d6b1b  bts     [rsp+438h+var_2D4], 9
0x1401d6b24  mov     [rsp+438h+var_3A4], 3
0x1401d6b2c  lea     rax, [rsp+438h+pvReadContext]
0x1401d6b34  mov     [rsp+438h+ppvReadContext], rax; ppvReadContext
0x1401d6b39  lea     rax, [rsp+438h+var_328]
0x1401d6b41  mov     [rsp+438h+plsnPrevious], rax; plsnPrevious
0x1401d6b46  lea     rax, [rsp+438h+var_350]
0x1401d6b4e  mov     [rsp+438h+plsnUndoNext], rax; plsnUndoNext
0x1401d6b53  lea     rax, [rsp+438h+var_3A4]
0x1401d6b5b  mov     [rsp+438h+peRecordType], rax; peRecordType
0x1401d6b60  lea     rax, [rsp+438h+pcbBuffer]
0x1401d6b68  mov     [rsp+438h+pcbReadBuffer], rax; pcbReadBuffer
0x1401d6b6d  lea     r9, [rsp+438h+ppvReadBuffer]; ppvReadBuffer
0x1401d6b75  mov     r8d, 3; peContextMode
0x1401d6b7b  lea     rdx, [rsp+438h+plsnFirst]; plsnFirst
0x1401d6b83  mov     rcx, [r14+200h]; pvMarshalContext
0x1401d6b8a  call    cs:__imp_ClfsReadLogRecord
0x1401d6b91  nop     dword ptr [rax+rax+00h]
0x1401d6b96  mov     edi, eax
0x1401d6b98  mov     [rsp+438h+var_3A8], eax
0x1401d6b9f  btr     [rsp+438h+var_2D4], 9
0x1401d6ba8  and     [rsp+438h+var_124], 0FFFFFFEFh
0x1401d6bb0  test    eax, eax
0x1401d6bb2  js      loc_1401D73C5
0x1401d6bb8  test    edi, edi
0x1401d6bba  jns     short loc_1401D6C10
0x1401d6bbc  mov     al, cs:NtfsStatusDebugFlags
0x1401d6bc2  test    al, al
0x1401d6bc4  jnz     loc_1401D71A1
0x1401d6bca  mov     r9d, 300192h
0x1401d6bd0  lea     rcx, [rsp+438h+var_2D8]
0x1401d6bd8  mov     r8d, edi
0x1401d6bdb  mov     rdx, r14
0x1401d6bde  call    TxfHardErrorFcn
0x1401d6be3  mov     r15d, 200043h
0x1401d6be9  jmp     loc_1401D7951
0x1401d6bee  cmp     cx, 0Ch
0x1401d6bf2  jz      loc_1401D6DF8
0x1401d6bf8  mov     rax, [r15+50h]
0x1401d6bfc  cmp     rax, rbx
0x1401d6bff  cmovg   rbx, rax
0x1401d6c03  mov     [rsp+438h+var_320], rbx
0x1401d6c0b  jmp     loc_1401D6DF8
0x1401d6c10  lock add [r14+210h], r12d
0x1401d6c18  mov     rax, qword ptr [rsp+438h+plsnFirst]
0x1401d6c20  mov     qword ptr [rsp+438h+plsnRecord], rax
0x1401d6c28  mov     edx, [rsp+438h+pcbBuffer]
0x1401d6c2f  mov     rcx, [rsp+438h+ppvReadBuffer]
0x1401d6c37  call    TxfValidateLogRecord
0x1401d6c3c  test    al, al
0x1401d6c3e  jz      loc_1401D726C
0x1401d6c44  mov     r15d, 0C000000Dh
0x1401d6c4a  lea     rdi, aStatus; "Status"
0x1401d6c51  mov     ecx, 4
0x1401d6c56  mov     eax, ecx
0x1401d6c58  lock cmpxchg [r14+84h], ecx
0x1401d6c61  cmp     eax, 3
0x1401d6c64  jz      loc_1401D71FF
0x1401d6c6a  cmp     [rsp+438h+var_3A3], sil
0x1401d6c72  jnz     loc_1401D74F9
0x1401d6c78  mov     rax, [rsp+438h+plsn2]
0x1401d6c80  test    rax, rax
0x1401d6c83  jnz     loc_1401D750F
0x1401d6c89  mov     rdx, [rsp+438h+ppvReadBuffer]
0x1401d6c91  movzx   ecx, word ptr [rdx]
0x1401d6c94  lea     eax, [rcx-4]
0x1401d6c97  mov     r8d, 0FFF3h
0x1401d6c9d  test    r8w, ax
0x1401d6ca1  jz      loc_1401D6EDA
0x1401d6ca7  cmp     cx, 20h ; ' '
0x1401d6cab  jz      loc_1401D7016
0x1401d6cb1  mov     eax, [rdx+4]
0x1401d6cb4  cmp     eax, 18h
0x1401d6cb7  jz      loc_1401D7016
0x1401d6cbd  cmp     cx, r12w
0x1401d6cc1  jz      loc_1401D754F
0x1401d6cc7  add     rdx, 20h ; ' '
0x1401d6ccb  lea     rax, [rsp+438h+var_398]
0x1401d6cd3  mov     [rsp+438h+peRecordType], rax
0x1401d6cd8  mov     [rsp+438h+pcbReadBuffer], rsi
0x1401d6cdd  mov     r9d, 13h
0x1401d6ce3  xor     r8d, r8d
0x1401d6ce6  mov     rcx, r14
0x1401d6ce9  call    TxfTransMgrSearchAddTrans
0x1401d6cee  mov     edi, eax
0x1401d6cf0  mov     [rsp+438h+var_3A8], eax
0x1401d6cf7  test    eax, eax
0x1401d6cf9  js      loc_1401D7589
0x1401d6cff  cmp     qword ptr [rsp+438h+var_398], rsi
0x1401d6d07  jz      loc_1401D7589
0x1401d6d0d  test    edi, edi
0x1401d6d0f  jnz     loc_1401D767F
0x1401d6d15  mov     rax, [rsp+438h+ppvReadBuffer]
0x1401d6d1d  movzx   ecx, word ptr [rax+48h]
0x1401d6d21  mov     edi, ecx
0x1401d6d23  and     edi, 2
0x1401d6d26  shl     edi, 18h
0x1401d6d29  mov     eax, ecx
0x1401d6d2b  and     eax, r12d
0x1401d6d2e  shl     eax, 18h
0x1401d6d31  or      edi, eax
0x1401d6d33  test    cl, 10h
0x1401d6d36  jnz     loc_1401D768A
0x1401d6d3c  mov     rcx, qword ptr [rsp+438h+var_398]
0x1401d6d44  add     rcx, 28h ; '('; plsn
0x1401d6d48  call    cs:__imp_ClfsLsnNull
0x1401d6d4f  nop     dword ptr [rax+rax+00h]
0x1401d6d54  mov     rax, qword ptr [rsp+438h+var_398]
0x1401d6d5c  lock and dword ptr [rax+10h], 0FCFFFFFFh
0x1401d6d64  mov     rax, qword ptr [rsp+438h+var_398]
0x1401d6d6c  lock or [rax+10h], edi
0x1401d6d70  mov     rax, [rsp+438h+ppvReadBuffer]
0x1401d6d78  mov     [rsp+438h+pcbReadBuffer], rax; int
0x1401d6d7d  mov     r9, qword ptr [rsp+438h+var_350]
0x1401d6d85  mov     r8, qword ptr [rsp+438h+plsnRecord]
0x1401d6d8d  mov     rdx, qword ptr [rsp+438h+var_398]; int
0x1401d6d95  lea     rcx, [rsp+438h+var_2D8]; int
0x1401d6d9d  call    TxfTransDoNextRedo
0x1401d6da2  mov     edi, eax
0x1401d6da4  mov     [rsp+438h+var_3A8], eax
0x1401d6dab  test    eax, eax
0x1401d6dad  js      loc_1401D769F
0x1401d6db3  test    edi, edi
0x1401d6db5  js      loc_1401D71F1
0x1401d6dbb  mov     dl, r12b
0x1401d6dbe  lea     rcx, [rsp+438h+var_398]
0x1401d6dc6  call    TxfDereferenceTransaction
0x1401d6dcb  mov     rax, qword ptr [rsp+438h+plsnRecord]
0x1401d6dd3  mov     qword ptr [rsp+438h+plsn1], rax
0x1401d6ddb  mov     r15, [rsp+438h+ppvReadBuffer]
0x1401d6de3  movzx   ecx, word ptr [r15]
0x1401d6de7  lea     eax, [rcx-4]
0x1401d6dea  mov     edx, 0FFF3h
0x1401d6def  test    dx, ax
0x1401d6df2  jz      loc_1401D6BEE
0x1401d6df8  mov     r15d, 0C000000Dh
0x1401d6dfe  or      [rsp+438h+var_124], 10h
0x1401d6e06  lea     rcx, [rsp+438h+var_2D8]
0x1401d6e0e  call    NtfsPurgeFileRecordCache
0x1401d6e13  bts     [rsp+438h+var_2D4], 9
0x1401d6e1c  mov     [rsp+438h+var_3A4], 3
0x1401d6e24  lea     rax, [rsp+438h+plsnRecord]
0x1401d6e2c  mov     [rsp+438h+plsnPrevious], rax; plsnRecord
0x1401d6e31  lea     rax, [rsp+438h+var_328]
0x1401d6e39  mov     [rsp+438h+plsnUndoNext], rax; plsnPrevious
0x1401d6e3e  lea     rax, [rsp+438h+var_350]
0x1401d6e46  mov     [rsp+438h+peRecordType], rax; plsnUndoNext
0x1401d6e4b  mov     [rsp+438h+pcbReadBuffer], rsi; plsnUser
0x1401d6e50  lea     r9, [rsp+438h+var_3A4]; peRecordType
0x1401d6e58  lea     r8, [rsp+438h+pcbBuffer]; pcbBuffer
0x1401d6e60  lea     rdx, [rsp+438h+ppvReadBuffer]; ppvBuffer
0x1401d6e68  mov     rcx, [rsp+438h+pvReadContext]; pvReadContext
0x1401d6e70  call    cs:__imp_ClfsReadNextLogRecord
0x1401d6e77  nop     dword ptr [rax+rax+00h]
0x1401d6e7c  mov     edi, eax
0x1401d6e7e  mov     [rsp+438h+var_3A8], eax
0x1401d6e85  btr     [rsp+438h+var_2D4], 9
0x1401d6e8e  and     [rsp+438h+var_124], 0FFFFFFEFh
0x1401d6e96  mov     ecx, 80000000h
0x1401d6e9b  add     eax, ecx
0x1401d6e9d  test    ecx, eax
0x1401d6e9f  jz      loc_1401D6FFC
0x1401d6ea5  cmp     edi, 0C0000011h
0x1401d6eab  jz      loc_1401D7008
0x1401d6eb1  test    edi, edi
0x1401d6eb3  js      loc_1401D7357
0x1401d6eb9  mov     edx, [rsp+438h+pcbBuffer]
0x1401d6ec0  mov     rcx, [rsp+438h+ppvReadBuffer]
0x1401d6ec8  call    TxfValidateLogRecord
0x1401d6ecd  test    al, al
0x1401d6ecf  jz      loc_1401D739B
0x1401d6ed5  jmp     loc_1401D6C4A
0x1401d6eda  cmp     cx, 0Ch
0x1401d6ede  jz      loc_1401D6CA7
0x1401d6ee4  cmp     [rsp+438h+var_338], rsi
0x1401d6eec  jz      loc_1401D6CA7
0x1401d6ef2  mov     rax, [rsp+438h+var_330]
0x1401d6efa  mov     rax, [rax]
0x1401d6efd  cmp     [rdx+50h], rax
0x1401d6f01  jle     loc_1401D6CA7
0x1401d6f07  lea     rdx, [r14+1B0h]; plsn2
0x1401d6f0e  lea     rcx, [rsp+438h+plsn1]; plsn1
0x1401d6f16  call    cs:__imp_ClfsLsnLess
0x1401d6f1d  nop     dword ptr [rax+rax+00h]
0x1401d6f22  test    al, al
0x1401d6f24  jnz     loc_1401D728A
0x1401d6f2a  cmp     rbx, [r14+1B8h]
0x1401d6f31  jl      loc_1401D72DD
0x1401d6f37  lea     rdx, [r14+198h]; plsn2
0x1401d6f3e  lea     rcx, [rsp+438h+plsn1]; plsn1
0x1401d6f46  call    cs:__imp_ClfsLsnLess
0x1401d6f4d  nop     dword ptr [rax+rax+00h]
0x1401d6f52  test    al, al
0x1401d6f54  jz      loc_1401D7533
0x1401d6f5a  mov     rcx, r14
0x1401d6f5d  call    TxfRmInForcedRecovery
0x1401d6f62  test    al, al
0x1401d6f64  jz      loc_1401D7533
0x1401d6f6a  mov     al, cs:NtfsStatusDebugFlags
0x1401d6f70  test    al, al
0x1401d6f72  jz      short loc_1401D6F84
0x1401d6f74  mov     r8d, 3001F8h
0x1401d6f7a  mov     edx, r15d
0x1401d6f7d  xor     ecx, ecx
0x1401d6f7f  call    NtfsStatusTraceAndDebugInternal
0x1401d6f84  mov     [rsp+438h+var_3A8], r15d
0x1401d6f8c  mov     dword ptr [rsp+438h+plsnUndoNext], r15d
0x1401d6f91  mov     [rsp+438h+peRecordType], rdi
0x1401d6f96  mov     dword ptr [rsp+438h+pcbReadBuffer], 1FAh
0x1401d6f9e  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x1401d6fa5  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x1401d6fac  xor     edx, edx; Level
0x1401d6fae  mov     ecx, 82h; ComponentId
0x1401d6fb3  call    cs:__imp_DbgPrintEx
0x1401d6fba  nop     dword ptr [rax+rax+00h]
0x1401d6fbf  mov     r8d, 80h
0x1401d6fc5  mov     rax, cs:TxfData
0x1401d6fcc  add     [rax+10h], r12d
  ... truncated ...
```
