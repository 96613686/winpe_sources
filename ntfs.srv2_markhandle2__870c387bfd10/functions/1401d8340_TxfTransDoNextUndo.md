# TxfTransDoNextUndo

- ea: `0x1401d8340`
- end: `0x1401d90d3`
- name: `TxfTransDoNextUndo`
- size: `3475`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `3`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400bbf04`
- `0x14010c7d0`
- `0x1401d60b8`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x140010e98`
- `0x140017480`
- `0x1400291f0`
- `0x140029d80`
- `0x140038908`
- `0x140038a30`
- `0x140038f8c`
- `0x140054044`
- `0x1400b62e4`
- `0x1400ff4f8`
- `0x14010229c`
- `0x140103260`
- `0x14010c050`
- `0x14010d5e8`
- `0x14010d734`
- `0x14010d9c8`
- `0x14010dad0`
- `0x14010dc54`
- `0x14010f050`
- `0x140132718`
- `0x1401336c8`
- `0x140134a58`
- `0x140135818`
- `0x14013ad80`
- `0x1401d8340`
- `0x1401d90dc`
- `0x1401d9420`
- `0x1401d9484`
- `0x1401d973c`
- `0x14026d0c4`
- `0x140291978`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d90c2`
- `ntoskrnl!KeSetEvent` at `0x1402ccfd1`
- `ntoskrnl!KeSetEvent` at `0x1401d90c2`
- `ntoskrnl!KeSetEvent` at `0x1402ccfd1`
- `ntoskrnl!ZwClose` at `0x1401d88bd`
- `ntoskrnl!ZwClose` at `0x1401d88d6`
- `ntoskrnl!ZwClose` at `0x1401d88bd`
- `ntoskrnl!ZwClose` at `0x1401d88d6`
- `ntoskrnl!KeResetEvent` at `0x1401d8c0e`
- `ntoskrnl!KeResetEvent` at `0x1401d8c0e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401d882f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401d882f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402cd03d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402cd03d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402ccaf9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402ccaf9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d8b03`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401d8b03`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1401d84d2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1401d84d2`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d83f8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401d83f8`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x1402cce26`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x1402cce26`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAlignReservedLog` at `0x1402ccd97`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAlignReservedLog` at `0x1402ccef7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAlignReservedLog` at `0x1402ccd97`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAlignReservedLog` at `0x1402ccef7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d8478`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d8ce4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d8478`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1401d8ce4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1402ccb79`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1402ccb79`

## pseudocode

```c
__int64 __fastcall TxfTransDoNextUndo(__int64 a1, CLFS_LSN *a2, CLFS_LSN *a3)
{
  CLFS_LSN v5; // r15
  PVOID *ppvReadContext; // rdi
  const CLFS_LSN *v7; // rcx
  _DWORD *v8; // r12
  __int64 ullOffset; // rbx
  PCLFS_LSN v10; // rdx
  NTSTATUS appended; // edi
  _DWORD *v12; // r8
  CLFS_LSN *v13; // r8
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  CLFS_LSN *v16; // rdx
  volatile signed __int32 *v17; // rax
  CLFS_LSN v18; // rax
  int v20; // r9d
  CLFS_LSN *v21; // r8
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  CLFS_LSN *v31; // rdx
  _QWORD *p_ullOffset; // rax
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  _DWORD *v40; // r8
  __int64 v41; // r8
  __int64 v42; // r8
  signed __int32 v43; // eax
  struct _KEVENT *v44; // rcx
  _DWORD *v45; // r8
  __int64 v46; // r9
  __int64 v47; // rcx
  int v48; // r9d
  PCLFS_LSN v49; // r8
  PCLFS_LSN v50; // r14
  PVOID v51; // rcx
  CLFS_LSN v52; // rcx
  int plsnUser; // [rsp+20h] [rbp-108h]
  int plsnUndoNext; // [rsp+28h] [rbp-100h]
  CLS_RECORD_TYPE peRecordType[8]; // [rsp+50h] [rbp-D8h] BYREF
  PVOID ppvBuffer; // [rsp+58h] [rbp-D0h] BYREF
  CLFS_LSN plsn2; // [rsp+60h] [rbp-C8h] BYREF
  ULONG pcbBuffer; // [rsp+68h] [rbp-C0h] BYREF
  PCLFS_LSN v59; // [rsp+70h] [rbp-B8h]
  _DWORD *v60; // [rsp+78h] [rbp-B0h]
  int v61; // [rsp+80h] [rbp-A8h]
  HANDLE Handle; // [rsp+88h] [rbp-A0h] BYREF
  HANDLE v63; // [rsp+90h] [rbp-98h] BYREF
  _DWORD *v64; // [rsp+98h] [rbp-90h]
  __int64 pcbAlignReservation; // [rsp+A0h] [rbp-88h] BYREF
  int v66; // [rsp+A8h] [rbp-80h]
  CLFS_LSN *v67; // [rsp+B0h] [rbp-78h] BYREF
  CLFS_LSN v68; // [rsp+B8h] [rbp-70h]
  __int64 v69; // [rsp+C0h] [rbp-68h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+C8h] [rbp-60h] BYREF
  LONGLONG v71; // [rsp+D0h] [rbp-58h] BYREF
  CLFS_LSN *v72; // [rsp+D8h] [rbp-50h]
  volatile signed __int32 *v73; // [rsp+E0h] [rbp-48h]
  __int64 v74; // [rsp+E8h] [rbp-40h]
  LONGLONG rgcbReservation; // [rsp+138h] [rbp+10h] BYREF
  PCLFS_LSN v76; // [rsp+140h] [rbp+18h]
  CLFS_LSN v77; // [rsp+148h] [rbp+20h] BYREF

  v76 = a3;
  rgcbReservation = (LONGLONG)a2;
  peRecordType[0] = 0;
  plsnPrevious.ullOffset = 0;
  plsn2.ullOffset = 0;
  ppvBuffer = 0;
  pcbBuffer = 0;
  v68 = a2[26];
  v5 = v68;
  v69 = 0;
  if ( (*(_DWORD *)(v68.ullOffset + 136) & 0x8000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3222863877LL, 3224286);
    return 3222863877LL;
  }
  v66 = 0;
  ppvReadContext = (PVOID *)&a2[28];
  v7 = a2 + 6;
  v59 = a2 + 6;
  v60 = (_DWORD *)(a1 + 436);
  v8 = (_DWORD *)(a1 + 4);
  v64 = (_DWORD *)(a1 + 4);
  if ( a2[28].ullOffset )
  {
    v64 = (_DWORD *)(a1 + 4);
    ullOffset = CLFS_LSN_NULL_EXT;
    pcbAlignReservation = CLFS_LSN_NULL_EXT;
    v77.ullOffset = 0;
    if ( ClfsLsnLess(v7, a2 + 10) )
    {
      NtfsPurgeFileRecordCache(a1);
      *v8 |= 0x200u;
      *v60 |= 0x10u;
      appended = ClfsReadNextLogRecord(
                   *ppvReadContext,
                   &ppvBuffer,
                   &pcbBuffer,
                   peRecordType,
                   (PCLFS_LSN)ppvBuffer + 6,
                   &v77,
                   &plsnPrevious,
                   &plsn2);
      v40 = v60;
      *v60 &= ~0x10u;
      *v8 &= ~0x200u;
      if ( appended < 0
        && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
      {
        appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 512, appended, (__int64)a2);
        if ( appended == -1073741807 )
          goto LABEL_86;
        v40 = v60;
      }
      if ( appended < 0 )
      {
        if ( (*v40 & 0x40) != 0 )
          TxfSetupForDeferredAbortPriv(
            (_DWORD)a2,
            appended,
            (unsigned int)"TxfTransDoNextUndo",
            (unsigned int)"txftrans.c",
            13291);
        else
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
            a1,
            (CLFS_LSN)v5.ullOffset,
            (unsigned int)appended,
            3224559);
        if ( !NtfsStatusDebugFlags
          || (unsigned int)appended >= 0xFFFFFFED
          || appended == -1073741802
          || appended == -1073741807
          || (unsigned int)(appended + 2147483643) <= 1
          || appended == -1073741608 )
        {
          return (unsigned int)appended;
        }
        v42 = 3224562;
        goto LABEL_105;
      }
      if ( !(unsigned __int8)TxfValidateLogRecord(ppvBuffer, pcbBuffer, v40) )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
          a1,
          (CLFS_LSN)v5.ullOffset,
          3222863920LL,
          3224567);
        if ( !NtfsStatusDebugFlags )
          return 3222863920LL;
        v41 = 3224568;
        goto LABEL_95;
      }
      v15 = ppvBuffer;
      if ( (*(_BYTE *)ppvBuffer & 2) != 0 && *((_DWORD *)ppvBuffer + 1) == 13 )
      {
        v13 = v59;
        goto LABEL_10;
      }
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
        a1,
        (CLFS_LSN)v5.ullOffset,
        3222863920LL,
        3224578);
      if ( NtfsStatusDebugFlags )
      {
        v41 = 3224579;
LABEL_95:
        NtfsStatusTraceAndDebugInternal(0, 3222863920LL, v41);
      }
    }
    else
    {
      v10 = v59;
      *v76 = *v59;
      *v60 |= 0x10u;
      ullOffset = v10->ullOffset;
      NtfsPurgeFileRecordCache(a1);
      *v8 |= 0x200u;
      appended = ClfsReadNextLogRecord(
                   *ppvReadContext,
                   &ppvBuffer,
                   &pcbBuffer,
                   peRecordType,
                   v76,
                   v59,
                   &plsnPrevious,
                   &plsn2);
      v12 = v60;
      *v60 &= ~0x10u;
      *v8 &= ~0x200u;
      if ( appended < 0
        && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
      {
        appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 512, appended, (__int64)a2);
        if ( appended == -1073741807 )
        {
LABEL_86:
          v76->ullOffset = CLFS_LSN_NULL_EXT;
          return 0;
        }
        v12 = v60;
      }
      if ( appended < 0 )
      {
        if ( (*v12 & 0x40) != 0 )
        {
          v59->ullOffset = ullOffset;
          TxfSetupForDeferredAbortPriv(
            (_DWORD)a2,
            appended,
            (unsigned int)"TxfTransDoNextUndo",
            (unsigned int)"txftrans.c",
            13390);
        }
        else
        {
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
            a1,
            (CLFS_LSN)v5.ullOffset,
            (unsigned int)appended,
            3224658);
        }
        if ( !NtfsStatusDebugFlags
          || (unsigned int)appended >= 0xFFFFFFED
          || appended == -1073741802
          || appended == -1073741807
          || (unsigned int)(appended + 2147483643) <= 1
          || appended == -1073741608 )
        {
          return (unsigned int)appended;
        }
        v42 = 3224661;
        goto LABEL_105;
      }
      if ( !(unsigned __int8)TxfValidateLogRecord(ppvBuffer, pcbBuffer, v12) )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
          a1,
          (CLFS_LSN)v5.ullOffset,
          3222863920LL,
          3224665);
        if ( !NtfsStatusDebugFlags )
          return 3222863920LL;
        v41 = 3224666;
        goto LABEL_95;
      }
      if ( (*(_BYTE *)ppvBuffer & 2) != 0 && ClfsLsnEqual(a2 + 8, &plsn2) )
      {
        pcbAlignReservation = ullOffset;
        v13 = v59;
        a2[8] = *v59;
        v14 = ((*((_WORD *)ppvBuffer + 36) & 1) << 24) | ((*((_WORD *)ppvBuffer + 36) & 2) << 24);
        _InterlockedAnd((volatile signed __int32 *)&a2[2], 0xFCFFFFFF);
        _InterlockedOr((volatile signed __int32 *)&a2[2], v14);
        v64 = (_DWORD *)(a1 + 4);
        v15 = ppvBuffer;
LABEL_10:
        v16 = a2 + 10;
        goto LABEL_11;
      }
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
        a1,
        (CLFS_LSN)v5.ullOffset,
        3222863920LL,
        3224677);
      if ( NtfsStatusDebugFlags )
      {
        v41 = 3224678;
        goto LABEL_95;
      }
    }
    return 3222863920LL;
  }
  *(_DWORD *)(a1 + 436) |= 0x10u;
  plsn2 = *(CLFS_LSN *)((char *)a2 + (-(__int64)(ClfsLsnNull(v7) != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 48);
  ullOffset = v59->ullOffset;
  a2[8] = *v59;
  NtfsPurgeFileRecordCache(a1);
  *v8 |= 0x200u;
  appended = ClfsReadLogRecord(
               *(PVOID *)(v5.ullOffset + 512),
               &plsn2,
               ClfsContextUndoNext,
               &ppvBuffer,
               &pcbBuffer,
               peRecordType,
               v59,
               &plsnPrevious,
               ppvReadContext);
  v45 = v60;
  *v60 &= ~0x10u;
  *v8 &= ~0x200u;
  if ( appended < 0 && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
  {
    appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 512, appended, (__int64)a2);
    if ( appended == -1073741807 )
      goto LABEL_86;
    v45 = v60;
  }
  if ( appended < 0 )
  {
    if ( (*v45 & 0x40) == 0 )
    {
      v46 = 3224395;
LABEL_157:
      v47 = a1;
LABEL_159:
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
        v47,
        (CLFS_LSN)v5.ullOffset,
        (unsigned int)appended,
        v46);
      return (unsigned int)appended;
    }
    plsnUser = 13127;
LABEL_154:
    v59->ullOffset = ullOffset;
    TxfSetupForDeferredAbortPriv(
      (_DWORD)a2,
      appended,
      (unsigned int)"TxfTransDoNextUndo",
      (unsigned int)"txftrans.c",
      plsnUser);
    return (unsigned int)appended;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v5.ullOffset + 528));
  if ( !(unsigned __int8)TxfValidateLogRecord(ppvBuffer, pcbBuffer, v45) )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
      a1,
      (CLFS_LSN)v5.ullOffset,
      3222863920LL,
      3224405);
    if ( !NtfsStatusDebugFlags )
      return 3222863920LL;
    v41 = 3224406;
    goto LABEL_95;
  }
  _InterlockedAnd((volatile signed __int32 *)&a2[2], 0xFCFFFFFF);
  _InterlockedOr((volatile signed __int32 *)&a2[2], (*((_WORD *)ppvBuffer + 36) & 1) << 24);
  v48 = 2;
  _InterlockedOr((volatile signed __int32 *)&a2[2], (*((_WORD *)ppvBuffer + 36) & 2) << 24);
  _InterlockedOr((volatile signed __int32 *)&a2[2], (*((_WORD *)ppvBuffer + 36) & 4) << 24);
  v16 = a2 + 10;
  v15 = ppvBuffer;
  if ( (*(_BYTE *)ppvBuffer & 2) == 0 )
  {
    *v16 = a2[9];
    v49 = v76;
    v50 = v59;
    do
    {
      *v49 = *v50;
      --v48;
    }
    while ( v48 );
    if ( (*(_DWORD *)(rgcbReservation + 16) & 0x9000000) != 0 )
      _InterlockedOr((volatile signed __int32 *)(rgcbReservation + 16), 0x8000000u);
    return 0;
  }
  pcbAlignReservation = ullOffset;
  v13 = v59;
  a2[8] = *v59;
  *v16 = (CLFS_LSN)v15[6];
LABEL_11:
  v74 = a1 + 4;
  LOBYTE(v77.offset.idxRecord) = 0;
  v72 = a2 + 2;
  if ( (a2[2].offset.idxRecord & 0x9000000) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)&a2[2], 0x8000000u);
    v15 = ppvBuffer;
  }
  *v76 = *v13;
  *v16 = (CLFS_LSN)v15[6];
  if ( (unsigned __int8)TxfFindRecordInCancelList(a2, &plsn2) )
  {
    if ( (*v60 & 0x40) == 0 || !*((_DWORD *)ppvBuffer + 17) )
      goto LABEL_26;
    rgcbReservation = *((unsigned int *)ppvBuffer + 17);
    pcbAlignReservation = 0;
    NtfsPurgeFileRecordCache(a1);
    *v8 |= 0x200u;
    appended = ClfsAlignReservedLog(*(PVOID *)(v5.ullOffset + 512), 1u, &rgcbReservation, &pcbAlignReservation);
    *v8 &= ~0x200u;
    if ( appended < 0
      && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
    {
      appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 0x8000, appended, (__int64)a2);
    }
    v47 = a1;
    if ( appended < 0 )
    {
      v46 = 3224818;
      goto LABEL_159;
    }
    rgcbReservation = -rgcbReservation;
    NtfsPurgeFileRecordCache(a1);
    *v8 |= 0x200u;
    appended = ClfsReserveAndAppendLog(*(PVOID *)(v5.ullOffset + 512), 0, 0, 0, 0, 1u, &rgcbReservation, 0, 0);
    *v8 &= ~0x200u;
    if ( appended < 0
      && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
    {
      appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 0x10000, appended, (__int64)a2);
    }
    if ( appended >= 0 )
    {
      a2[34].ullOffset -= *((unsigned int *)ppvBuffer + 17);
      a2[35].ullOffset -= pcbAlignReservation;
      --a2[36].offset.idxRecord;
      goto LABEL_26;
    }
    if ( (*v60 & 0x40) == 0 )
    {
      v46 = 3224877;
      goto LABEL_157;
    }
    plsnUser = 13609;
    goto LABEL_154;
  }
  v17 = (volatile signed __int32 *)v72;
  v73 = (volatile signed __int32 *)v72;
  Handle = 0;
  v63 = 0;
  _InterlockedOr((volatile signed __int32 *)v72, 0x10u);
  if ( (*v17 & 0x1000) != 0 )
  {
    v51 = ppvBuffer;
    if ( !*((_DWORD *)ppvBuffer + 17) )
      goto LABEL_187;
    v71 = *((unsigned int *)ppvBuffer + 17);
    v67 = 0;
    NtfsPurgeFileRecordCache(a1);
    *v8 |= 0x200u;
    appended = ClfsAlignReservedLog(*(PVOID *)(v5.ullOffset + 512), 1u, &v71, (PLONGLONG)&v67);
    *v8 &= ~0x200u;
    if ( appended < 0
      && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
    {
      appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 0x8000, appended, (__int64)a2);
    }
    if ( appended >= 0 )
    {
      v51 = ppvBuffer;
      a2[34].ullOffset += *((unsigned int *)ppvBuffer + 17);
      a2[35].ullOffset += (ULONGLONG)v67;
      ++a2[36].offset.idxRecord;
LABEL_187:
      TxfGetRequiredAbortReservation(v51, &v69);
      if ( v69 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfReserveSpaceForAbortPriv)(
          a1,
          (CLFS_LSN)v5.ullOffset,
          a2,
          v69);
      goto LABEL_15;
    }
    v46 = 3224948;
    goto LABEL_157;
  }
LABEL_15:
  v67 = v59;
  v71 = (LONGLONG)v59;
  appended = -1073741608;
  while ( appended != -1072103376 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
    NtfsPurgeFileRecordCache(a1);
    *v64 |= 0x200u;
    if ( Handle )
    {
      ZwClose(Handle);
      Handle = 0;
    }
    if ( v63 )
    {
      ZwClose(v63);
      v63 = 0;
    }
    *v64 &= ~0x200u;
    if ( (*v73 & 0x4000000) != 0 )
      TxfCloseHandlesForTransaction(a1, a2, 0);
    if ( appended != -1073741608 )
      break;
    NtfsPreRequestProcessingExtend(a1);
    appended = 0;
    v61 = 0;
    v21 = (CLFS_LSN *)ppvBuffer;
    v22 = *((_DWORD *)ppvBuffer + 1);
    if ( v22 <= 10 )
    {
      if ( v22 == 10 )
      {
        TxfUndoModifySecurityFile(a1, 0, 1);
        goto LABEL_81;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        TxfUndoCreateNewFile(a1, (_DWORD)a2, 0, plsnUndoNext, (__int64)&Handle, (__int64)&v63);
        goto LABEL_81;
      }
      v24 = v23 - 1;
      if ( !v24 )
        goto LABEL_63;
      v25 = v24 - 1;
      if ( !v25 )
      {
        TxfUndoDeleteFile(a1, (_DWORD)a2, 0, (__int64)&Handle, (__int64)&v63);
        goto LABEL_81;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        TxfRedoUndoFileRename(a1, (__int64)&plsn2, 0, (__int64)&Handle, (__int64)&v63);
        goto LABEL_81;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
LABEL_63:
        TxfUndoAddFileName(a1, 0, plsnUndoNext, (__int64)&Handle, (__int64)&v63);
        goto LABEL_81;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        TxfCLRAndUndoWriteFile(a1, (_DWORD)a2, (_DWORD)ppvBuffer, (unsigned int)&plsn2, 0);
        goto LABEL_81;
      }
      v29 = v28 - 1;
      if ( !v29 )
      {
        TxfRedoUndoFcbInfoUpdateFile(a1);
        goto LABEL_81;
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
        TxfUndoTempBitChangeFile(a1, a2);
        goto LABEL_81;
      }
      if ( v30 == 1 )
      {
        TxfTransSetAttrSizes(a1, *((_QWORD *)ppvBuffer + 14), (__int64)&plsn2, 1);
        goto LABEL_81;
      }
LABEL_51:
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3225313);
      appended = -1072103376;
      v61 = -1072103376;
      goto LABEL_81;
    }
    v33 = v22 - 11;
    if ( !v33 )
    {
      TxfUndoAddTxfFileId(a1, 0, (__int64)&Handle);
      goto LABEL_81;
    }
    v34 = v33 - 2;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        LOBYTE(v20) = 1;
        TxfUndoCreateBackupFile(a1, (_DWORD)a2, (_DWORD)ppvBuffer, v20, (__int64)&Handle);
        goto LABEL_81;
      }
      v36 = v35 - 1;
      if ( !v36 )
      {
        TxfUndoMoveAttr(a1, 0, 1);
        goto LABEL_81;
      }
      v37 = v36 - 2;
      if ( !v37 )
      {
        LOBYTE(v20) = 1;
        TxfUndoCreateAttr(a1, (int)a2, (int)ppvBuffer, v20, &plsn2, 0);
        goto LABEL_81;
      }
      v38 = v37 - 1;
      if ( !v38 )
      {
        TxfUndoRenameStream(a1, 0, 1);
        goto LABEL_81;
      }
      v39 = v38 - 1;
      if ( v39 && v39 != 5 )
        goto LABEL_51;
    }
    else if ( !ClfsLsnGreater((const CLFS_LSN *)ppvBuffer + 10, v67) )
    {
      v31 = (CLFS_LSN *)ExAllocateFromLookasideListEx(&TxfTransCancelListLookasideList);
      p_ullOffset = &a2[11].ullOffset;
      v21 = (CLFS_LSN *)a2[11].ullOffset;
      if ( v21 == &a2[11] )
        a2[9] = plsn2;
      if ( (_QWORD *)v21[1].ullOffset != p_ullOffset )
        __fastfail(3u);
      v31->ullOffset = (ULONGLONG)v21;
      v31[1].ullOffset = (ULONGLONG)p_ullOffset;
      v21[1].ullOffset = (ULONGLONG)v31;
      *p_ullOffset = v31;
      v31[3] = plsn2;
      v31[2] = *(CLFS_LSN *)((char *)ppvBuffer + 80);
    }
LABEL_81:
    NtfsCleanupIrpContext(a1, 0, (__int64)v21);
  }
  _InterlockedAnd((volatile signed __int32 *)v72, 0xFFFFFFEF);
  *(_DWORD *)(a1 + 12) &= ~0x100u;
  if ( appended < 0 && (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset) )
    appended = TxfHandleRecoveryError(a1, v5.offset.idxRecord, 0x4000, appended, (__int64)ppvBuffer);
  v18 = a2[42];
  if ( appended < 0 )
  {
    if ( v18.ullOffset )
      ((void (__fastcall *)(_QWORD))TxfMarkTempTxLockAsDoomed)((CLFS_LSN)a2[42].ullOffset);
    v52 = a2[43];
    if ( v52.ullOffset )
      ((void (__fastcall *)(_QWORD))TxfMarkTempTxLockAsDoomed)((CLFS_LSN)v52.ullOffset);
    if ( LOBYTE(v77.offset.idxRecord)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(v5.ullOffset + 592), 0xFFFFFFFF) == 1 )
    {
      KeSetEvent((PRKEVENT)(*(_QWORD *)(v5.ullOffset + 24) + 424LL), 0, 0);
    }
    if ( (*v60 & 0x40) != 0 )
    {
      v59->ullOffset = ullOffset;
      TxfSetupForDeferredAbortPriv(
        (_DWORD)a2,
        appended,
        (unsigned int)"TxfTransDoNextUndo",
        (unsigned int)"txftrans.c",
        14204);
    }
    else
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))TxfHardErrorFcn)(
        a1,
        (CLFS_LSN)v5.ullOffset,
        (unsigned int)appended,
        3225472);
    }
    if ( !NtfsStatusDebugFlags
      || (unsigned int)appended >= 0xFFFFFFED
      || appended == -1073741802
      || appended == -1073741807
      || (unsigned int)(appended + 2147483643) <= 1
      || appended == -1073741608 )
    {
      return (unsigned int)appended;
    }
    v42 = 3225479;
LABEL_105:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)appended, v42);
    return (unsigned int)appended;
  }
  if ( v18.ullOffset )
    TxfReleaseTempTxLock();
  if ( a2[43].ullOffset )
    TxfReleaseTempTxLock();
  if ( (*v73 & 0x1000) == 0 && (*(_BYTE *)v60 & 0x40) != 0 )
  {
    TxfGetRequiredAbortReservation(ppvBuffer, &v69);
    if ( v69 )
      ((void (__fastcall *)(_QWORD, _QWORD))TxfReleaseSpaceForAbortPriv)((CLFS_LSN)v5.ullOffset, a2);
  }
LABEL_26:
  if ( LOBYTE(v77.offset.idxRecord) )
  {
    v43 = _InterlockedExchangeAdd((volatile signed __int32 *)(v5.ullOffset + 592), 0xFFFFFFFF);
    v44 = (struct _KEVENT *)(*(_QWORD *)(v5.ullOffset + 24) + 424LL);
    if ( v43 == 1 )
      KeSetEvent(v44, 0, 0);
    else
      KeWaitForSingleObject(v44, Executive, 0, 0, 0);
  }
  a2[37].ullOffset = CLFS_LSN_NULL_EXT;
  ProcessSavepointListForCurrentLogRec(a2);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1401d8340  mov     r11, rsp
0x1401d8343  mov     [r11+18h], r8
0x1401d8347  mov     [r11+10h], rdx
0x1401d834b  mov     [r11+8], rcx
0x1401d834f  push    rbx
0x1401d8350  push    rsi
0x1401d8351  push    rdi
0x1401d8352  push    r12
0x1401d8354  push    r13
0x1401d8356  push    r14
0x1401d8358  push    r15
0x1401d835a  sub     rsp, 0F0h
0x1401d8361  mov     r14, rdx
0x1401d8364  mov     r13, rcx
0x1401d8367  xor     esi, esi
0x1401d8369  mov     [rsp+128h+peRecordType], sil
0x1401d836e  mov     [r11-60h], rsi
0x1401d8372  mov     qword ptr [rsp+128h+plsn2], rsi
0x1401d8377  mov     [rsp+128h+ppvBuffer], rsi
0x1401d837c  mov     [rsp+128h+pcbBuffer], esi
0x1401d8380  mov     r15, [rdx+0D0h]
0x1401d8387  mov     [rsp+128h+var_70], r15
0x1401d838f  mov     [r11-68h], rsi
0x1401d8393  test    dword ptr [r15+88h], 8000h
0x1401d839e  jnz     loc_1401D8DF3
0x1401d83a4  mov     [r11-80h], esi
0x1401d83a8  lea     rdi, [rdx+0E0h]
0x1401d83af  lea     rcx, [rdx+30h]; plsn
0x1401d83b3  mov     [rsp+128h+var_B8], rcx
0x1401d83b8  lea     rax, [r13+1B4h]
0x1401d83bf  mov     [rsp+128h+var_B0], rax
0x1401d83c4  lea     r12, [r13+4]
0x1401d83c8  mov     [rsp+128h+var_90], r12
0x1401d83d0  cmp     [rdi], rsi
0x1401d83d3  jz      loc_1402CCAF6
0x1401d83d9  mov     [rsp+128h+var_90], r12
0x1401d83e1  mov     rbx, cs:CLFS_LSN_NULL_EXT
0x1401d83e8  mov     [rsp+128h+pcbAlignReservation], rbx
0x1401d83f0  mov     [r11+20h], rsi
0x1401d83f4  add     rdx, 50h ; 'P'; plsn2
0x1401d83f8  call    cs:__imp_ClfsLsnLess
0x1401d83ff  nop     dword ptr [rax+rax+00h]
0x1401d8404  test    al, al
0x1401d8406  jnz     loc_1401D8C8A
0x1401d840c  mov     rdx, [rsp+128h+var_B8]
0x1401d8411  mov     rax, [rdx]
0x1401d8414  mov     r8, [rsp+128h+arg_10]
0x1401d841c  mov     [r8], rax
0x1401d841f  mov     rcx, [rsp+128h+var_B0]
0x1401d8424  or      dword ptr [rcx], 10h
0x1401d8427  mov     rbx, [rdx]
0x1401d842a  mov     rcx, r13
0x1401d842d  call    NtfsPurgeFileRecordCache
0x1401d8432  bts     dword ptr [r12], 9
0x1401d8438  lea     rax, [rsp+128h+plsn2]
0x1401d843d  mov     [rsp+128h+plsnRecord], rax; plsnRecord
0x1401d8442  lea     rax, [rsp+128h+var_60]
0x1401d844a  mov     [rsp+128h+plsnPrevious], rax; plsnPrevious
0x1401d844f  mov     rax, [rsp+128h+var_B8]
0x1401d8454  mov     [rsp+128h+plsnUndoNext], rax; plsnUndoNext
0x1401d8459  mov     rax, [rsp+128h+arg_10]
0x1401d8461  mov     [rsp+128h+plsnUser], rax; plsnUser
0x1401d8466  lea     r9, [rsp+128h+peRecordType]; peRecordType
0x1401d846b  lea     r8, [rsp+128h+pcbBuffer]; pcbBuffer
0x1401d8470  lea     rdx, [rsp+128h+ppvBuffer]; ppvBuffer
0x1401d8475  mov     rcx, [rdi]; pvReadContext
0x1401d8478  call    cs:__imp_ClfsReadNextLogRecord
0x1401d847f  nop     dword ptr [rax+rax+00h]
0x1401d8484  mov     edi, eax
0x1401d8486  mov     r8, [rsp+128h+var_B0]
0x1401d848b  and     dword ptr [r8], 0FFFFFFEFh
0x1401d848f  btr     dword ptr [r12], 9
0x1401d8495  test    eax, eax
0x1401d8497  js      loc_1401D8C3B
0x1401d849d  test    edi, edi
0x1401d849f  js      loc_1401D8FF3
0x1401d84a5  mov     edx, [rsp+128h+pcbBuffer]
0x1401d84a9  mov     rcx, [rsp+128h+ppvBuffer]
0x1401d84ae  call    TxfValidateLogRecord
0x1401d84b3  test    al, al
0x1401d84b5  jz      loc_1401D8EE7
0x1401d84bb  mov     rax, [rsp+128h+ppvBuffer]
0x1401d84c0  test    byte ptr [rax], 2
0x1401d84c3  jz      loc_1401D8D77
0x1401d84c9  lea     rcx, [r14+40h]; plsn1
0x1401d84cd  lea     rdx, [rsp+128h+plsn2]; plsn2
0x1401d84d2  call    cs:__imp_ClfsLsnEqual
0x1401d84d9  nop     dword ptr [rax+rax+00h]
0x1401d84de  test    al, al
0x1401d84e0  jz      loc_1401D8D77
0x1401d84e6  mov     [rsp+128h+pcbAlignReservation], rbx
0x1401d84ee  mov     r8, [rsp+128h+var_B8]
0x1401d84f3  mov     rax, [r8]
0x1401d84f6  mov     [r14+40h], rax
0x1401d84fa  mov     rax, [rsp+128h+ppvBuffer]
0x1401d84ff  movzx   ecx, word ptr [rax+48h]
0x1401d8503  mov     eax, ecx
0x1401d8505  and     eax, 2
0x1401d8508  shl     eax, 18h
0x1401d850b  and     ecx, 1
0x1401d850e  shl     ecx, 18h
0x1401d8511  or      eax, ecx
0x1401d8513  lock and dword ptr [r14+10h], 0FCFFFFFFh
0x1401d851c  lock or [r14+10h], eax
0x1401d8521  mov     [rsp+128h+var_90], r12
0x1401d8529  mov     rcx, [rsp+128h+ppvBuffer]
0x1401d852e  lea     rdx, [r14+50h]
0x1401d8532  mov     [rsp+128h+var_40], r12
0x1401d853a  mov     byte ptr [rsp+128h+arg_18], sil
0x1401d8542  lea     r9, [r14+10h]
0x1401d8546  mov     [rsp+128h+var_50], r9
0x1401d854e  test    dword ptr [r9], 9000000h
0x1401d8555  jnz     loc_1401D902B
0x1401d855b  mov     rax, [r8]
0x1401d855e  mov     r8, [rsp+128h+arg_10]
0x1401d8566  mov     [r8], rax
0x1401d8569  mov     rax, [rcx+30h]
0x1401d856d  mov     [rdx], rax
0x1401d8570  lea     rdx, [rsp+128h+plsn2]
0x1401d8575  mov     rcx, r14
0x1401d8578  call    TxfFindRecordInCancelList
0x1401d857d  test    al, al
0x1401d857f  jnz     loc_1401D8C27
0x1401d8585  mov     rax, [rsp+128h+var_50]
0x1401d858d  mov     [rsp+128h+var_48], rax
0x1401d8595  mov     [rsp+128h+Handle], rsi
0x1401d859d  mov     [rsp+128h+var_98], rsi
0x1401d85a5  lock or dword ptr [rax], 10h
0x1401d85a9  test    dword ptr [rax], 1000h
0x1401d85af  jnz     loc_1402CCEAD
0x1401d85b5  mov     rax, [rsp+128h+var_B8]
0x1401d85ba  mov     [rsp+128h+var_78], rax
0x1401d85c2  mov     [rsp+128h+var_58], rax
0x1401d85ca  mov     edi, 0C00000D8h
0x1401d85cf  mov     r12d, 0C0190030h
0x1401d85d5  cmp     edi, r12d
0x1401d85d8  jnz     loc_1401D86A7
0x1401d85de  mov     rax, [rsp+128h+var_50]
0x1401d85e6  lock and dword ptr [rax], 0FFFFFFEFh
0x1401d85ea  btr     dword ptr [r13+0Ch], 8
0x1401d85f0  test    edi, edi
0x1401d85f2  js      loc_1401D903D
0x1401d85f8  lea     rcx, [r14+150h]
0x1401d85ff  mov     rax, [rcx]
0x1401d8602  test    edi, edi
0x1401d8604  js      loc_1401D9072
0x1401d860a  test    rax, rax
0x1401d860d  jnz     loc_1401D9089
0x1401d8613  lea     rcx, [r14+158h]
0x1401d861a  cmp     [rcx], rsi
0x1401d861d  jnz     loc_1401D9093
0x1401d8623  mov     rax, [rsp+128h+var_48]
0x1401d862b  test    dword ptr [rax], 1000h
0x1401d8631  setz    cl
0x1401d8634  mov     rax, [rsp+128h+var_B0]
0x1401d8639  test    byte ptr [rax], 40h
0x1401d863c  setnz   al
0x1401d863f  test    al, cl
0x1401d8641  jz      short loc_1401D866D
0x1401d8643  lea     rdx, [rsp+128h+var_68]
0x1401d864b  mov     rcx, [rsp+128h+ppvBuffer]
0x1401d8650  call    TxfGetRequiredAbortReservation
0x1401d8655  mov     r8, [rsp+128h+var_68]
0x1401d865d  test    r8, r8
0x1401d8660  jz      short loc_1401D866D
0x1401d8662  mov     rdx, r14
0x1401d8665  mov     rcx, r15
0x1401d8668  call    TxfReleaseSpaceForAbortPriv
0x1401d866d  cmp     byte ptr [rsp+128h+arg_18], sil
0x1401d8675  jnz     loc_1401D909D
0x1401d867b  mov     rax, cs:CLFS_LSN_NULL_EXT
0x1401d8682  mov     [r14+128h], rax
0x1401d8689  mov     rcx, r14
0x1401d868c  call    ProcessSavepointListForCurrentLogRec
0x1401d8691  mov     eax, edi
0x1401d8693  add     rsp, 0F0h
0x1401d869a  pop     r15
0x1401d869c  pop     r14
0x1401d869e  pop     r13
0x1401d86a0  pop     r12
0x1401d86a2  pop     rdi
0x1401d86a3  pop     rsi
0x1401d86a4  pop     rbx
0x1401d86a5  retn
0x1401d86a7  mov     rax, [r13+90h]
0x1401d86ae  mov     [rax+18h], esi
0x1401d86b1  cmp     edi, 0C0000188h
0x1401d86b7  jz      loc_1401D8884
0x1401d86bd  mov     rcx, r13
0x1401d86c0  call    NtfsPurgeFileRecordCache
0x1401d86c5  mov     rax, [rsp+128h+var_90]
0x1401d86cd  bts     dword ptr [rax], 9
0x1401d86d1  mov     rcx, [rsp+128h+Handle]; Handle
0x1401d86d9  test    rcx, rcx
0x1401d86dc  jnz     loc_1401D88BD
0x1401d86e2  mov     rcx, [rsp+128h+var_98]; Handle
0x1401d86ea  test    rcx, rcx
0x1401d86ed  jnz     loc_1401D88D6
0x1401d86f3  mov     rax, [rsp+128h+var_90]
0x1401d86fb  btr     dword ptr [rax], 9
0x1401d86ff  mov     rax, [rsp+128h+var_48]
0x1401d8707  test    dword ptr [rax], 4000000h
0x1401d870d  jnz     loc_1401D88EF
0x1401d8713  cmp     edi, 0C01A001Dh
0x1401d8719  jz      loc_1401D8902
0x1401d871f  cmp     edi, 0C00000D8h
0x1401d8725  jnz     short loc_1401D8770
0x1401d8727  mov     edx, 0C00000D8h
0x1401d872c  mov     rcx, r13
0x1401d872f  call    NtfsPreRequestProcessingExtend
0x1401d8734  mov     edi, esi
0x1401d8736  mov     [rsp+128h+var_A8], esi
0x1401d873d  mov     r8, [rsp+128h+ppvBuffer]; int
0x1401d8742  mov     ecx, [r8+4]
0x1401d8746  cmp     ecx, 0Ah
0x1401d8749  jg      loc_1401D8A33
0x1401d874f  jnz     short loc_1401D8775
0x1401d8751  mov     byte ptr [rsp+128h+plsnUndoNext], 1
0x1401d8756  mov     [rsp+128h+plsnUser], rsi
0x1401d875b  lea     r9, [rsp+128h+plsn2]
0x1401d8760  mov     rdx, r14
0x1401d8763  mov     rcx, r13
0x1401d8766  call    TxfUndoModifySecurityFile
0x1401d876b  jmp     loc_1401D8B48
0x1401d8770  jmp     loc_1401D85DE
0x1401d8775  sub     ecx, 1
0x1401d8778  jz      loc_1401D89FF
0x1401d877e  sub     ecx, 1
0x1401d8781  jz      loc_1401D89CB
0x1401d8787  sub     ecx, 1
0x1401d878a  jz      loc_1401D8997
0x1401d8790  sub     ecx, 1
0x1401d8793  jz      loc_1401D8958
0x1401d8799  sub     ecx, 1
0x1401d879c  jz      loc_1401D89CB
0x1401d87a2  sub     ecx, 1
0x1401d87a5  jz      loc_1401D893F
0x1401d87ab  sub     ecx, 1
0x1401d87ae  jnz     short loc_1401D87C5
0x1401d87b0  lea     r9, [rsp+128h+plsn2]
0x1401d87b5  mov     rdx, r14
0x1401d87b8  mov     rcx, r13; int
0x1401d87bb  call    TxfRedoUndoFcbInfoUpdateFile
0x1401d87c0  jmp     loc_1401D8B48
0x1401d87c5  sub     ecx, 1
0x1401d87c8  jz      loc_1401D892F
0x1401d87ce  cmp     ecx, 1
0x1401d87d1  jnz     short loc_1401D87FE
0x1401d87d3  mov     dword ptr [rsp+128h+plsnPrevious], ecx; int
0x1401d87d7  lea     rax, [rsp+128h+plsn2]
0x1401d87dc  mov     [rsp+128h+plsnUndoNext], rax; __int64
0x1401d87e1  mov     rax, [r8+70h]
0x1401d87e5  mov     [rsp+128h+plsnUser], rax; __int64
0x1401d87ea  mov     r9, [r8+78h]
0x1401d87ee  mov     rdx, r14
0x1401d87f1  mov     rcx, r13; int
0x1401d87f4  call    TxfTransSetAttrSizes
0x1401d87f9  jmp     loc_1401D8B48
0x1401d87fe  mov     al, cs:NtfsStatusDebugFlags
0x1401d8804  test    al, al
0x1401d8806  jz      short loc_1401D8818
0x1401d8808  mov     r8d, 3136E1h
0x1401d880e  mov     edx, r12d
0x1401d8811  xor     ecx, ecx
0x1401d8813  call    NtfsStatusTraceAndDebugInternal
0x1401d8818  mov     edi, r12d
0x1401d881b  mov     [rsp+128h+var_A8], r12d
0x1401d8823  jmp     loc_1401D8B48
0x1401d8828  lea     rcx, TxfTransCancelListLookasideList; Lookaside
0x1401d882f  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401d8836  nop     dword ptr [rax+rax+00h]
0x1401d883b  mov     rdx, rax
0x1401d883e  lea     rax, [r14+58h]
0x1401d8842  mov     r8, [rax]
0x1401d8845  cmp     r8, rax
0x1401d8848  jz      loc_1401D8B18
0x1401d884e  cmp     [r8+8], rax
0x1401d8852  jz      short loc_1401D885B
0x1401d8854  mov     ecx, 3
0x1401d8859  int     29h; Win8: RtlFailFast(ecx)
0x1401d885b  mov     [rdx], r8
0x1401d885e  mov     [rdx+8], rax
0x1401d8862  mov     [r8+8], rdx
0x1401d8866  mov     [rax], rdx
0x1401d8869  mov     rax, qword ptr [rsp+128h+plsn2]
0x1401d886e  mov     [rdx+18h], rax
0x1401d8872  mov     rax, [rsp+128h+ppvBuffer]
0x1401d8877  mov     rcx, [rax+50h]
0x1401d887b  mov     [rdx+10h], rcx
0x1401d887f  jmp     loc_1401D8B48
0x1401d8884  mov     rcx, r13
0x1401d8887  call    NtfsCheckpointForLogFileFull
0x1401d888c  mov     eax, [rsp+128h+var_80]
0x1401d8893  inc     eax
0x1401d8895  mov     [rsp+128h+var_80], eax
0x1401d889c  cmp     eax, 2
0x1401d889f  jb      short loc_1401D88AC
0x1401d88a1  mov     rax, [rsp+128h+var_90]
0x1401d88a9  or      dword ptr [rax], 10h
0x1401d88ac  mov     edi, 0C00000D8h
  ... truncated ...
```
