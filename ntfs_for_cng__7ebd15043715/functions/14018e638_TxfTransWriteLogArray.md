# TxfTransWriteLogArray

- ea: `0x14018e638`
- end: `0x14018f3c1`
- name: `TxfTransWriteLogArray`
- size: `3465`
- prototype: `CLFS_LSN __fastcall(__int64, CLFS_WRITE_ENTRY *, ULONG, ULONG, CLFS_LSN *, int, int, unsigned int, NTSTATUS *)`
- caller_count: `31`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400108f0`
- `0x140035e70`
- `0x14003879c`
- `0x1400f8c7c`
- `0x1400f97bc`
- `0x14010046c`
- `0x140101a78`
- `0x140103260`
- `0x140104a70`
- `0x14010d148`
- `0x14012e970`
- `0x140132718`
- `0x140134a58`
- `0x140135818`
- `0x14018bf40`
- `0x14018e07c`
- `0x14018e23c`
- `0x14018f740`
- `0x140190410`
- `0x1401922f0`
- `0x1401941c0`
- `0x1401952d4`
- `0x1401d5488`
- `0x1401d60b8`
- `0x1401da21c`
- `0x140249d88`
- `0x14026d0c4`
- `0x140276d40`
- `0x14027ad70`
- `0x140291978`
- `0x140296da4`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x140010be0`
- `0x140010c54`
- `0x1400414f4`
- `0x14004173c`
- `0x140053bb4`
- `0x140059250`
- `0x14010c050`
- `0x140129fb0`
- `0x14012e4f0`
- `0x14018dc4c`
- `0x14018e638`
- `0x1401d9420`
- `0x1401d9484`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x14018f31a`
- `ntoskrnl!ExQueueWorkItem` at `0x14018f31a`
- `ntoskrnl!IoWithinStackLimits` at `0x14018eab5`
- `ntoskrnl!IoWithinStackLimits` at `0x14018eab5`
- `ntoskrnl!KeReleaseMutex` at `0x14018e7db`
- `ntoskrnl!KeReleaseMutex` at `0x14018ebdf`
- `ntoskrnl!KeReleaseMutex` at `0x14018f0c2`
- `ntoskrnl!KeReleaseMutex` at `0x14018f19b`
- `ntoskrnl!KeReleaseMutex` at `0x14018f1d3`
- `ntoskrnl!KeReleaseMutex` at `0x14018f32f`
- `ntoskrnl!KeReleaseMutex` at `0x1402ab4c2`
- `ntoskrnl!KeReleaseMutex` at `0x1402ab52e`
- `ntoskrnl!KeReleaseMutex` at `0x14018e7db`
- `ntoskrnl!KeReleaseMutex` at `0x14018ebdf`
- `ntoskrnl!KeReleaseMutex` at `0x14018f0c2`
- `ntoskrnl!KeReleaseMutex` at `0x14018f19b`
- `ntoskrnl!KeReleaseMutex` at `0x14018f1d3`
- `ntoskrnl!KeReleaseMutex` at `0x14018f32f`
- `ntoskrnl!KeReleaseMutex` at `0x1402ab4c2`
- `ntoskrnl!KeReleaseMutex` at `0x1402ab52e`
- `ntoskrnl!KeResetEvent` at `0x14018f26a`
- `ntoskrnl!KeResetEvent` at `0x14018f26a`
- `ntoskrnl!IoGetActivityIdThread` at `0x14018f2b0`
- `ntoskrnl!IoGetActivityIdThread` at `0x14018f2b0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14018f17f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ab498`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14018f17f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ab498`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14018e940`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14018e940`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018e75d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018eaf6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018f246`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018e75d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018eaf6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018f246`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018e778`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018e778`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018e7b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018f09e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018f1b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ab4e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ab50b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018e7b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018f09e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018f1b4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ab4e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ab50b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14018edae`
- `ntoskrnl!ExAcquireFastMutex` at `0x14018edae`
- `ntoskrnl!ExReleaseFastMutex` at `0x14018ee03`
- `ntoskrnl!ExReleaseFastMutex` at `0x14018ee03`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14018ea96`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14018ea96`
- `ntoskrnl!ExRaiseStatus` at `0x14018f3b4`
- `ntoskrnl!ExRaiseStatus` at `0x14018f3b4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14018e735`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14018e796`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14018efb1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14018e735`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14018e796`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14018efb1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14018e8b0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14018edc9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14018e8b0`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x14018edc9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x14018eb6c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x14018eb6c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsFreeReservedLog` at `0x14018f043`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsFreeReservedLog` at `0x14018f043`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAlignReservedLog` at `0x14018eefb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsAlignReservedLog` at `0x14018eefb`

## string_xrefs

- `0x14018ed8f`: `TxfTransWriteLogArray`

## pseudocode

```c
CLFS_LSN __fastcall TxfTransWriteLogArray(
        __int64 a1,
        CLFS_WRITE_ENTRY *a2,
        ULONG a3,
        ULONG a4,
        CLFS_LSN *a5,
        int a6,
        int a7,
        unsigned int a8,
        NTSTATUS *a9)
{
  __int64 v12; // rbx
  ULONG cReserveRecords; // edi
  _QWORD *Buffer; // r15
  ULONG ByteLength; // edx
  unsigned int i; // ecx
  __int64 v17; // rdx
  int v18; // r9d
  int v19; // ecx
  ULONG v20; // edi
  int v21; // r9d
  int v22; // r10d
  __int64 v23; // r13
  _WORD *v24; // rax
  char v25; // r13
  PIRP TopLevelIrp; // r13
  NTSTATUS appended; // edi
  char v28; // r13
  CLFS_LSN *v29; // rax
  NTSTATUS *v30; // r15
  _DWORD *v31; // rax
  __int64 v32; // rcx
  int v33; // r8d
  unsigned int v34; // r9d
  volatile signed __int64 *v35; // r12
  signed __int64 v36; // rdx
  __int64 v37; // rax
  char v38; // r12
  NTSTATUS v39; // eax
  CLFS_LSN v40; // rax
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  NTSTATUS v43; // eax
  char v44; // dl
  __int64 v45; // rcx
  __int64 v46; // rsi
  _OWORD *ActivityIdThread; // rax
  __int64 v48; // r9
  __int64 v49; // rcx
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-118h]
  char v52; // [rsp+51h] [rbp-E7h]
  char v53; // [rsp+52h] [rbp-E6h]
  char v54; // [rsp+53h] [rbp-E5h]
  char v55; // [rsp+54h] [rbp-E4h]
  char v56; // [rsp+55h] [rbp-E3h]
  CLFS_LSN *Entry; // [rsp+58h] [rbp-E0h]
  CLFS_LSN plsn1; // [rsp+78h] [rbp-C0h] BYREF
  char v60; // [rsp+80h] [rbp-B8h]
  int v61; // [rsp+84h] [rbp-B4h]
  __int64 v62[2]; // [rsp+88h] [rbp-B0h] BYREF
  unsigned int v63; // [rsp+98h] [rbp-A0h]
  ULONG cWriteEntries; // [rsp+9Ch] [rbp-9Ch]
  PIRP v65; // [rsp+A0h] [rbp-98h]
  LONGLONG v66; // [rsp+A8h] [rbp-90h] BYREF
  __int64 pcbAlignReservation[2]; // [rsp+B0h] [rbp-88h] BYREF
  PCLFS_WRITE_ENTRY rgWriteEntries; // [rsp+C0h] [rbp-78h]
  __int64 rgcbReservation[2]; // [rsp+C8h] [rbp-70h] BYREF
  __int128 v70; // [rsp+D8h] [rbp-60h]
  __int64 v71; // [rsp+E8h] [rbp-50h]

  cWriteEntries = a3;
  rgWriteEntries = a2;
  pcbAlignReservation[1] = a1;
  Entry = 0;
  plsn1.ullOffset = CLFS_LSN_NULL_EXT;
  v53 = 0;
  v54 = 0;
  v65 = 0;
  v12 = *(_QWORD *)(a1 + 208);
  v62[1] = v12;
  v55 = 0;
  v56 = 0;
  *(_OWORD *)rgcbReservation = 0;
  v70 = 0;
  v71 = 0;
  cReserveRecords = 0;
  v61 = -1;
  v66 = 0;
  pcbAlignReservation[0] = 0;
  v62[0] = 0;
  v52 = 0;
  Buffer = a2->Buffer;
  if ( a9 )
    *a9 = 0;
  while ( 1 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x4000000) == 0 && ClfsLsnNull((const CLFS_LSN *)(a1 + 32)) )
    {
      KeWaitForSingleObject(*(PVOID *)(v12 + 184), Executive, 0, 0, 0);
      v53 = 1;
    }
    ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(a1 + 24) + 80LL), 1u);
    if ( (*(_DWORD *)(a1 + 16) & 0x4000000) != 0 || !ClfsLsnNull((const CLFS_LSN *)(a1 + 32)) )
      break;
    if ( v53 )
      goto LABEL_12;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 24) + 80LL));
  }
  if ( v53 )
  {
    KeReleaseMutex(*(PRKMUTEX *)(v12 + 184), 0);
    v53 = 0;
  }
LABEL_12:
  Buffer[3] = LfsQueryLastLsn(*(_QWORD *)(*(_QWORD *)(v12 + 16) + 232LL));
  *((_OWORD *)Buffer + 2) = *(_OWORD *)(a1 + 256);
  ByteLength = a2->ByteLength;
  *((_DWORD *)Buffer + 16) = ByteLength;
  for ( i = 1; ; ++i )
  {
    v63 = i;
    if ( i >= a3 )
      break;
    ByteLength += a2[i].ByteLength;
    *((_DWORD *)Buffer + 16) = ByteLength;
  }
  *((_WORD *)Buffer + 36) = HIBYTE(*(_DWORD *)(a1 + 16)) & 6
                          | (*(_DWORD *)(a1 + 16) >> 14) & 0x10
                          | ((*(_DWORD *)(a1 + 16) & 0x9000000) != 0)
                          | (unsigned __int16)(8 * (*(_DWORD *)(a1 + 16) & 1));
  Buffer[6] = *(_QWORD *)(a1 + 72);
  Buffer[7] = MEMORY[0xFFFFF78000000014];
  *((_WORD *)Buffer + 37) &= 8u;
  v17 = *(_QWORD *)(a1 + 320);
  if ( v17 != a1 + 320
    && !ClfsLsnGreater((const CLFS_LSN *)(a1 + 48), (const CLFS_LSN *)(v17 - 24))
    && (*(_BYTE *)Buffer & 2) != 0 )
  {
    *((_WORD *)Buffer + 37) |= 1u;
  }
  if ( (*(_BYTE *)Buffer & 1) != 0 && (*(_DWORD *)(a1 + 16) & 0x808) == 0x800 )
  {
    *((_WORD *)Buffer + 37) |= 2u;
    _InterlockedAnd((volatile signed __int32 *)(a1 + 16), 0xFFFFF7FF);
  }
  if ( (*(_BYTE *)Buffer & 0x40) != 0 && (*(_DWORD *)(a1 + 16) & 8) != 0 )
    *((_WORD *)Buffer + 37) |= 4u;
  v18 = a6;
  if ( a6 || a7 )
  {
    Entry = (CLFS_LSN *)ExAllocateFromLookasideListEx(&TxfCancelLsnLookasideList);
    v18 = a6;
  }
  if ( a8 )
  {
    rgcbReservation[0] = a8;
    v61 = 0;
    cReserveRecords = 1;
    *((_DWORD *)Buffer + 17) = a8;
  }
  else
  {
    *((_DWORD *)Buffer + 17) = 0;
  }
  v19 = *(_DWORD *)(a1 + 16);
  if ( (v19 & 0x4000040) == 0 )
  {
    rgcbReservation[cReserveRecords] = 96;
    v20 = cReserveRecords + 1;
    rgcbReservation[v20] = 96;
    cReserveRecords = v20 + 1;
  }
  if ( *(_DWORD *)(v12 + 504) < 2u && (v19 & 0x20) == 0 && (a4 & 4) == 0 )
  {
    v55 = 1;
    rgcbReservation[cReserveRecords++] = 112;
  }
  if ( v18 )
    rgcbReservation[cReserveRecords++] = 88;
  if ( (*(_BYTE *)Buffer & 2) != 0 )
  {
    TxfGetRequiredAbortReservation(Buffer, v62);
    v23 = v62[0];
    if ( v62[0] )
    {
      if ( v21 )
      {
        v24 = NtfsAddStructToRollbackList((__int64)a5, 1829, a1, v22);
        *((_QWORD *)v24 + 4) += v23;
        *((_DWORD *)v24 + 1) |= 1u;
        TxfReserveSpaceForAbortPriv((__int64)a5, *(_QWORD *)(a1 + 208), a1, v23);
      }
      else
      {
        TxfReserveSpaceForAbortPriv((__int64)a5, v12, a1, v62[0]);
        v52 = 1;
      }
    }
  }
  if ( a5 || (*(_WORD *)Buffer & 0xC) != 0 || (*(_WORD *)Buffer & 0x10) != 0 )
  {
    TopLevelIrp = IoGetTopLevelIrp();
    v65 = TopLevelIrp;
    IoWithinStackLimits((ULONG_PTR)TopLevelIrp, 0x28u);
    HIDWORD(TopLevelIrp->ThreadListEntry.Flink[27].Flink) |= 0x80u;
    v25 = 1;
  }
  else
  {
    v25 = 0;
  }
  if ( (*(_WORD *)Buffer & 0xC) != 0 || (*(_WORD *)Buffer & 0x10) != 0 )
  {
    KeWaitForSingleObject(*(PVOID *)(v12 + 544), Executive, 0, 0, 0);
    v54 = 1;
    Buffer[10] = *(_QWORD *)(v12 + 536);
  }
  if ( a5 )
  {
    NtfsPurgeFileRecordCache((__int64)a5);
    a5->offset.cidContainer |= 0x200u;
  }
  appended = ClfsReserveAndAppendLog(
               *(PVOID *)(v12 + 512),
               rgWriteEntries,
               cWriteEntries,
               (PCLFS_LSN)(a1 + 48),
               (PCLFS_LSN)(a1 + 40),
               cReserveRecords,
               rgcbReservation,
               a4,
               &plsn1);
  if ( a5 )
    a5->offset.cidContainer &= ~0x200u;
  if ( appended < 0
    && (a4 & 4) != 0
    && ((*(_WORD *)Buffer & 0x10) != 0 && (*(_BYTE *)(a1 + 16) & 1) != 0
     || appended != -1073741670 && appended != -1073741801) )
  {
    TxfHardErrorFcn((__int64)a5, v12, appended, 0x313007u);
  }
  if ( v54 )
    KeReleaseMutex(*(PRKMUTEX *)(v12 + 544), 0);
  if ( v25 )
    HIDWORD(v65->ThreadListEntry.Flink[27].Flink) &= ~0x80u;
  v28 = 0;
  if ( appended < 0 )
  {
    if ( appended == -1072037859 )
    {
      if ( (a4 & 4) == 0 )
      {
        v56 = 1;
        v60 = 1;
        v30 = a9;
        if ( a9 )
        {
          appended = -30;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xFFFFFFE2, 0x31306Eu);
        }
        else
        {
          if ( a5 && _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(a1 + 208) + 132LL), 4, 4) == 2 )
          {
            v31 = TxfSearchAddTxfFcbCleanupList(a5[18].ullOffset, 0, 5, 0, 1);
            v31[4] |= 0x200u;
            *(_DWORD *)(a5[18].ullOffset + 436) |= 0x20u;
            v32 = *(_QWORD *)(a1 + 208);
            *((_QWORD *)v31 + 4) = v32;
            _InterlockedAdd((volatile signed __int32 *)(v32 + 64), 1u);
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)v31 + 4) + 48LL), 1u);
          }
          appended = -1073741608;
        }
        v29 = Entry;
        v28 = 1;
        goto LABEL_143;
      }
      TxfHardErrorFcn((__int64)a5, v12, -1072037859, 0x313032u);
      appended = -1072103419;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0190005, 0x313039u);
      goto LABEL_70;
    }
    v33 = -1072037845;
    if ( appended != -1072037845 )
    {
      if ( (!a5 || (a5[2].offset.idxRecord & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
      {
        McTemplateU0sdpjpj_EtwWriteTransfer(
          a1 + 256,
          (const EVENT_DESCRIPTOR *)txftrans_c12362,
          "TxfTransWriteLogArray",
          appended,
          v12,
          v12 + 672,
          a1,
          a1 + 256);
      }
      goto LABEL_70;
    }
    v34 = 3223617;
LABEL_81:
    TxfHardErrorFcn((__int64)a5, v12, v33, v34);
LABEL_70:
    v29 = Entry;
    v28 = 1;
LABEL_142:
    v30 = a9;
LABEL_143:
    v38 = v52;
    goto LABEL_144;
  }
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v12 + 472));
  v35 = (volatile signed __int64 *)(v12 + 464);
  if ( ClfsLsnGreater(&plsn1, (const CLFS_LSN *)(v12 + 464)) )
  {
    do
      v36 = _InterlockedCompareExchange64(v35, NtfsLarge0.QuadPart, NtfsLarge0.QuadPart);
    while ( v36 != _InterlockedCompareExchange64(v35, plsn1.ullOffset, v36) );
  }
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v12 + 472));
  ++*(_DWORD *)(v12 + 484);
  if ( *(_DWORD *)(v12 + 484) == 7000 * (*(_DWORD *)(v12 + 484) / 0x1B58u) && (*(_DWORD *)(v12 + 136) & 0x10) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v12 + 136), 0x10u);
    TxfQueueDelayedRmWorkItem(v12);
  }
  if ( (a4 & 2) != 0 )
    TxfUpdateHighestFlushedLsn(v12, &plsn1);
  if ( v55 )
    _InterlockedAdd((volatile signed __int32 *)(v12 + 504), 1u);
  v37 = v61;
  if ( v61 >= 0 )
  {
    ++*(_DWORD *)(a1 + 288);
    *(_QWORD *)(a1 + 280) += rgcbReservation[v37];
    *(_QWORD *)(a1 + 272) += a8;
  }
  v38 = 0;
  v52 = 0;
  if ( (*(_BYTE *)Buffer & 0x40) == 0 || (*(_DWORD *)(a1 + 16) & 0x20) != 0 )
  {
LABEL_109:
    v40 = plsn1;
    *(CLFS_LSN *)(a1 + 40) = plsn1;
    if ( (*(_BYTE *)Buffer & 2) != 0 )
    {
      if ( *((_DWORD *)Buffer + 1) == 13 )
        *(CLFS_LSN *)(a1 + 72) = v40;
      if ( (*(_BYTE *)Buffer & 2) != 0 )
        *(CLFS_LSN *)(a1 + 48) = v40;
    }
    if ( (*(_BYTE *)Buffer & 1) != 0 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 16), 0x400000u);
    if ( (*(_DWORD *)(a1 + 16) & 0x4000000) == 0 && ClfsLsnNull((const CLFS_LSN *)(a1 + 32)) )
    {
      *(CLFS_LSN *)(a1 + 32) = plsn1;
      v41 = (_QWORD *)(v12 + 168);
      v42 = *(_QWORD *)(v12 + 168);
      if ( *(_QWORD *)(v42 + 8) != v12 + 168 )
        __fastfail(3u);
      *(_QWORD *)(a1 + 120) = v42;
      *(_QWORD *)(a1 + 128) = v41;
      *(_QWORD *)(v42 + 8) = a1 + 120;
      *v41 = a1 + 120;
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 236));
    }
    _InterlockedOr((volatile signed __int32 *)(a1 + 16), 0x40u);
    if ( (*(_BYTE *)Buffer & 0x10) != 0 && *(_DWORD *)(a1 + 288) )
    {
      *(_QWORD *)(a1 + 280) = -*(_QWORD *)(a1 + 280);
      if ( a5 )
      {
        NtfsPurgeFileRecordCache((__int64)a5);
        a5->offset.cidContainer |= 0x200u;
      }
      v43 = ClfsFreeReservedLog(*(PVOID *)(v12 + 512), *(_DWORD *)(a1 + 288), (PLONGLONG)(a1 + 280));
      appended = v43;
      if ( a5 )
        a5->offset.cidContainer &= ~0x200u;
      if ( v43 < 0 )
      {
        v34 = 3223900;
        v33 = v43;
        goto LABEL_81;
      }
      *(_DWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 280) = 0;
      *(_QWORD *)(a1 + 272) = 0;
    }
    if ( (*(_BYTE *)Buffer & 0x40) != 0 )
      *(CLFS_LSN *)(a1 + 296) = plsn1;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 24) + 80LL));
    if ( v53 )
    {
      KeReleaseMutex(*(PRKMUTEX *)(v12 + 184), 0);
      v53 = 0;
    }
    if ( a6 || a7 )
    {
      v44 = (a6 != 0 ? 2 : 0) | 1;
      if ( !a7 )
        v44 = a6 != 0 ? 2 : 0;
      *(_OWORD *)&Entry->offset.idxRecord = 0;
      *(_OWORD *)&Entry[2].offset.idxRecord = 0;
      *Entry = plsn1;
      Entry[1].ullOffset = a1;
      WORD2(Entry[3].ullOffset) = *(_WORD *)Buffer;
      Entry[3].offset.idxRecord = *((_DWORD *)Buffer + 1);
      BYTE6(Entry[3].ullOffset) = v44;
      Entry[2] = a5[52];
      a5[52].ullOffset = (ULONGLONG)Entry;
      if ( (v44 & 1) != 0 )
        a5[54].offset.cidContainer |= 0x400u;
      v29 = 0;
    }
    else
    {
      v29 = Entry;
    }
    goto LABEL_142;
  }
  v66 = *((unsigned int *)Buffer + 16);
  if ( a5 )
  {
    NtfsPurgeFileRecordCache((__int64)a5);
    a5->offset.cidContainer |= 0x200u;
  }
  v39 = ClfsAlignReservedLog(*(PVOID *)(v12 + 512), 1u, &v66, pcbAlignReservation);
  appended = v39;
  if ( a5 )
    a5->offset.cidContainer &= ~0x200u;
  if ( v39 >= 0 )
  {
    *(_QWORD *)(a1 + 272) -= *((unsigned int *)Buffer + 16);
    *(_QWORD *)(a1 + 280) -= pcbAlignReservation[0];
    --*(_DWORD *)(a1 + 288);
    goto LABEL_109;
  }
  if ( v39 != -1073741670 && v39 != -1073741801 )
    TxfHardErrorFcn((__int64)a5, v12, v39, 0x3130EDu);
  v29 = Entry;
  v30 = a9;
  v28 = 1;
LABEL_144:
  if ( v29 )
    ExFreeToLookasideListEx(&TxfCancelLsnLookasideList, v29);
  if ( v28 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 24) + 80LL));
  if ( v53 )
    KeReleaseMutex(*(PRKMUTEX *)(v12 + 184), 0);
  if ( v38 )
    TxfReleaseSpaceForAbortPriv(v12, a1, v62[0]);
  if ( !v56 )
  {
LABEL_166:
    if ( appended >= 0 )
      return plsn1;
    goto LABEL_167;
  }
  if ( (*(_DWORD *)(v12 + 128) & 2) == 0 )
  {
    KeWaitForSingleObject(*(PVOID *)(v12 + 184), Executive, 0, 0, 0);
    if ( !*(_BYTE *)(v12 + 480) )
    {
      KeResetEvent((PRKEVENT)(*(_QWORD *)(v12 + 24) + 448LL));
      *(_BYTE *)(v12 + 480) = 1;
      _InterlockedOr((volatile signed __int32 *)(v12 + 136), 8u);
      _m_prefetchw((const void *)(v12 + 136));
      v45 = *(_DWORD *)(v12 + 136) | 1u;
      if ( (_InterlockedOr((volatile signed __int32 *)(v12 + 136), 1u) & 1) == 0 )
      {
        v46 = *(_QWORD *)(v12 + 24);
        ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v45);
        if ( ActivityIdThread )
        {
          v49 = v46 + 1160;
          *(_OWORD *)(v46 + 1160) = *ActivityIdThread;
        }
        else
        {
          v49 = 0;
        }
        *(_QWORD *)(v46 + 1152) = v49;
        if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        {
          LODWORD(Timeout) = 10;
          McTemplateK0pq_EtwWriteTransfer(
            v49,
            (const EVENT_DESCRIPTOR *)WORKITEM_QUEUE,
            *(const GUID **)(*(_QWORD *)(v12 + 24) + 1152LL),
            v48,
            (__int64)Timeout);
        }
        _InterlockedAdd((volatile signed __int32 *)(v12 + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(v12 + 56), 1u);
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(*(_QWORD *)(v12 + 24) + 1120LL), CriticalWorkQueue);
      }
    }
    KeReleaseMutex(*(PRKMUTEX *)(v12 + 184), 0);
    goto LABEL_166;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC01A001D, 0x31321Au);
  appended = -1072037859;
LABEL_167:
  if ( !v30 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)appended < 0xFFFFFFED
      && appended != -1073741802
      && appended != -1073741807
      && (unsigned int)(appended + 2147483643) > 1
      && appended != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal((__int64)a5, appended, 0x31325Bu);
    }
    ExRaiseStatus(appended);
  }
  *v30 = appended;
  return plsn1;
}

```

## disassembly

```asm
0x14018e638  mov     r11, rsp
0x14018e63b  push    rbx
0x14018e63c  push    rsi
0x14018e63d  push    rdi
0x14018e63e  push    r12
0x14018e640  push    r13
0x14018e642  push    r14
0x14018e644  push    r15
0x14018e646  sub     rsp, 100h
0x14018e64d  mov     rax, cs:__security_cookie
0x14018e654  xor     rax, rsp
0x14018e657  mov     [rsp+138h+var_48], rax
0x14018e65f  mov     [rsp+138h+var_D8], r9d
0x14018e664  mov     r13d, r8d
0x14018e667  mov     [rsp+138h+cWriteEntries], r8d
0x14018e66f  mov     r12, rdx
0x14018e672  mov     [rsp+138h+rgWriteEntries], rdx
0x14018e67a  mov     rsi, rcx
0x14018e67d  mov     [rsp+138h+var_80], rcx
0x14018e685  mov     r14, [rsp+138h+arg_20]
0x14018e68d  mov     rdx, [rsp+138h+arg_40]
0x14018e695  mov     [rsp+138h+var_D0], rdx
0x14018e69a  xor     r8d, r8d
0x14018e69d  mov     [rsp+138h+Entry], r8
0x14018e6a2  mov     rax, cs:CLFS_LSN_NULL_EXT
0x14018e6a9  mov     qword ptr [rsp+138h+plsn1], rax
0x14018e6ae  mov     [rsp+138h+var_E8], r8b
0x14018e6b3  mov     [rsp+138h+var_E2], r8b
0x14018e6b8  mov     [rsp+138h+var_E6], r8b
0x14018e6bd  mov     [rsp+138h+var_E5], r8b
0x14018e6c2  mov     [r11-98h], r8
0x14018e6c9  mov     rbx, [rcx+0D0h]
0x14018e6d0  mov     [rsp+138h+var_A8], rbx
0x14018e6d8  mov     [rsp+138h+var_E4], r8b
0x14018e6dd  mov     [rsp+138h+var_E3], r8b
0x14018e6e2  xorps   xmm0, xmm0
0x14018e6e5  xor     eax, eax
0x14018e6e7  movups  xmmword ptr [r11-70h], xmm0
0x14018e6ec  movups  xmmword ptr [r11-60h], xmm0
0x14018e6f1  mov     [r11-50h], rax
0x14018e6f5  mov     edi, r8d
0x14018e6f8  or      ecx, 0FFFFFFFFh
0x14018e6fb  mov     [rsp+138h+var_B4], ecx
0x14018e702  mov     [r11-90h], r8
0x14018e709  mov     [r11-88h], r8
0x14018e710  mov     [r11-0B0h], r8
0x14018e717  mov     [rsp+138h+var_E7], r8b
0x14018e71c  mov     r15, [r12]
0x14018e720  test    rdx, rdx
0x14018e723  jz      short loc_14018E728
0x14018e725  mov     [rdx], r8d
0x14018e728  lea     rcx, [rsi+20h]; plsn
0x14018e72c  test    dword ptr [rsi+10h], 4000000h
0x14018e733  jnz     short loc_14018E76E
0x14018e735  call    cs:__imp_ClfsLsnNull
0x14018e73c  nop     dword ptr [rax+rax+00h]
0x14018e741  test    al, al
0x14018e743  jz      short loc_14018E76E
0x14018e745  mov     [rsp+138h+Timeout], 0; Timeout
0x14018e74e  xor     r9d, r9d; Alertable
0x14018e751  xor     r8d, r8d; WaitMode
0x14018e754  xor     edx, edx; WaitReason
0x14018e756  mov     rcx, [rbx+0B8h]; Object
0x14018e75d  call    cs:__imp_KeWaitForSingleObject
0x14018e764  nop     dword ptr [rax+rax+00h]
0x14018e769  mov     [rsp+138h+var_E6], 1
0x14018e76e  mov     rcx, [rsi+18h]
0x14018e772  add     rcx, 50h ; 'P'; Resource
0x14018e776  mov     dl, 1; Wait
0x14018e778  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018e77f  nop     dword ptr [rax+rax+00h]
0x14018e784  mov     [rsp+138h+var_E8], 1
0x14018e789  test    dword ptr [rsi+10h], 4000000h
0x14018e790  jnz     short loc_14018E7CB
0x14018e792  lea     rcx, [rsi+20h]; plsn
0x14018e796  call    cs:__imp_ClfsLsnNull
0x14018e79d  nop     dword ptr [rax+rax+00h]
0x14018e7a2  test    al, al
0x14018e7a4  jz      short loc_14018E7CB
0x14018e7a6  cmp     [rsp+138h+var_E6], 0
0x14018e7ab  jnz     short loc_14018E7EC
0x14018e7ad  mov     rcx, [rsi+18h]
0x14018e7b1  add     rcx, 50h ; 'P'; Resource
0x14018e7b5  call    cs:__imp_ExReleaseResourceLite
0x14018e7bc  nop     dword ptr [rax+rax+00h]
0x14018e7c1  mov     [rsp+138h+var_E8], 0
0x14018e7c6  jmp     loc_14018E728
0x14018e7cb  cmp     [rsp+138h+var_E6], 0
0x14018e7d0  jz      short loc_14018E7EC
0x14018e7d2  xor     edx, edx; Wait
0x14018e7d4  mov     rcx, [rbx+0B8h]; Mutex
0x14018e7db  call    cs:__imp_KeReleaseMutex
0x14018e7e2  nop     dword ptr [rax+rax+00h]
0x14018e7e7  mov     [rsp+138h+var_E6], 0
0x14018e7ec  mov     rcx, [rbx+10h]
0x14018e7f0  mov     rcx, [rcx+0E8h]
0x14018e7f7  call    LfsQueryLastLsn
0x14018e7fc  mov     [r15+18h], rax
0x14018e800  movups  xmm0, xmmword ptr [rsi+100h]
0x14018e807  movdqu  xmmword ptr [r15+20h], xmm0
0x14018e80d  mov     edx, [r12+8]
0x14018e812  mov     [r15+40h], edx
0x14018e816  mov     r8d, 1
0x14018e81c  mov     ecx, r8d
0x14018e81f  mov     [rsp+138h+var_A0], ecx
0x14018e826  cmp     ecx, r13d
0x14018e829  jnb     short loc_14018E83F
0x14018e82b  mov     eax, ecx
0x14018e82d  shl     rax, 4
0x14018e831  add     edx, [rax+r12+8]
0x14018e836  mov     [r15+40h], edx
0x14018e83a  add     ecx, r8d
0x14018e83d  jmp     short loc_14018E81F
0x14018e83f  mov     edx, [rsi+10h]
0x14018e842  mov     ecx, edx
0x14018e844  and     cx, r8w
0x14018e848  shl     cx, 3
0x14018e84c  test    edx, 9000000h
0x14018e852  mov     eax, 0
0x14018e857  setnz   al
0x14018e85a  or      cx, ax
0x14018e85d  mov     eax, edx
0x14018e85f  shr     eax, 0Eh
0x14018e862  and     ax, 10h
0x14018e866  or      cx, ax
0x14018e869  shr     edx, 18h
0x14018e86c  and     dx, 6
0x14018e870  or      cx, dx
0x14018e873  mov     [r15+48h], cx
0x14018e878  mov     rax, [rsi+48h]
0x14018e87c  mov     [r15+30h], rax
0x14018e880  mov     rax, ds:0FFFFF78000000014h
0x14018e88a  mov     [r15+38h], rax
0x14018e88e  mov     r12d, 8
0x14018e894  and     [r15+4Ah], r12w
0x14018e899  lea     rax, [rsi+140h]
0x14018e8a0  mov     rdx, [rax]
0x14018e8a3  cmp     rdx, rax
0x14018e8a6  jz      short loc_14018E8D6
0x14018e8a8  add     rdx, 0FFFFFFFFFFFFFFE8h; plsn2
0x14018e8ac  lea     rcx, [rsi+30h]; plsn1
0x14018e8b0  call    cs:__imp_ClfsLsnGreater
0x14018e8b7  nop     dword ptr [rax+rax+00h]
0x14018e8bc  test    al, al
0x14018e8be  jnz     short loc_14018E8D6
0x14018e8c0  lea     r13d, [r12-6]
0x14018e8c5  lea     r10d, [r12-7]
0x14018e8ca  test    [r15], r13b
0x14018e8cd  jz      short loc_14018E8E0
0x14018e8cf  or      [r15+4Ah], r10w
0x14018e8d4  jmp     short loc_14018E8E0
0x14018e8d6  mov     r13d, 2
0x14018e8dc  lea     r10d, [r13-1]
0x14018e8e0  test    [r15], r10b
0x14018e8e3  jz      short loc_14018E901
0x14018e8e5  mov     eax, [rsi+10h]
0x14018e8e8  and     eax, 808h
0x14018e8ed  cmp     eax, 800h
0x14018e8f2  jnz     short loc_14018E901
0x14018e8f4  or      [r15+4Ah], r13w
0x14018e8f9  lock and dword ptr [rsi+10h], 0FFFFF7FFh
0x14018e901  test    byte ptr [r15], 40h
0x14018e905  jz      short loc_14018E91C
0x14018e907  mov     eax, [rsi+10h]
0x14018e90a  test    r12b, al
0x14018e90d  jz      short loc_14018E91C
0x14018e90f  mov     r12d, 4
0x14018e915  or      [r15+4Ah], r12w
0x14018e91a  jmp     short loc_14018E922
0x14018e91c  mov     r12d, 4
0x14018e922  mov     r9d, [rsp+138h+arg_28]
0x14018e92a  test    r9d, r9d
0x14018e92d  jnz     short loc_14018E939
0x14018e92f  cmp     [rsp+138h+arg_30], r9d
0x14018e937  jz      short loc_14018E95F
0x14018e939  lea     rcx, TxfCancelLsnLookasideList; Lookaside
0x14018e940  call    cs:__imp_ExAllocateFromLookasideListEx
0x14018e947  nop     dword ptr [rax+rax+00h]
0x14018e94c  mov     [rsp+138h+Entry], rax
0x14018e951  mov     r9d, [rsp+138h+arg_28]
0x14018e959  mov     r10d, 1
0x14018e95f  mov     eax, [rsp+138h+arg_38]
0x14018e966  test    eax, eax
0x14018e968  jz      short loc_14018E989
0x14018e96a  mov     [rsp+138h+var_70], rax
0x14018e972  xor     ecx, ecx
0x14018e974  mov     [rsp+138h+var_B4], ecx
0x14018e97b  mov     edi, r10d
0x14018e97e  mov     [rsp+138h+var_C8], r10d
0x14018e983  mov     [r15+44h], eax
0x14018e987  jmp     short loc_14018E991
0x14018e989  mov     dword ptr [r15+44h], 0
0x14018e991  mov     ecx, [rsi+10h]
0x14018e994  test    ecx, 4000040h
0x14018e99a  jnz     short loc_14018E9C5
0x14018e99c  movsxd  rax, edi
0x14018e99f  mov     edx, 60h ; '`'
0x14018e9a4  mov     [rsp+rax*8+138h+var_70], rdx
0x14018e9ac  add     edi, r10d
0x14018e9af  mov     [rsp+138h+var_C8], edi
0x14018e9b3  movsxd  rax, edi
0x14018e9b6  mov     [rsp+rax*8+138h+var_70], rdx
0x14018e9be  add     edi, r10d
0x14018e9c1  mov     [rsp+138h+var_C8], edi
0x14018e9c5  cmp     [rbx+1F8h], r13d
0x14018e9cc  jnb     short loc_14018E9FB
0x14018e9ce  test    cl, 20h
0x14018e9d1  setz    cl
0x14018e9d4  test    byte ptr [rsp+138h+var_D8], r12b
0x14018e9d9  setz    al
0x14018e9dc  test    al, cl
0x14018e9de  jz      short loc_14018E9FB
0x14018e9e0  mov     [rsp+138h+var_E4], r10b
0x14018e9e5  movsxd  rax, edi
0x14018e9e8  mov     [rsp+rax*8+138h+var_70], 70h ; 'p'
0x14018e9f4  add     edi, r10d
0x14018e9f7  mov     [rsp+138h+var_C8], edi
0x14018e9fb  test    r9d, r9d
0x14018e9fe  jz      short loc_14018EA16
0x14018ea00  movsxd  rax, edi
0x14018ea03  mov     [rsp+rax*8+138h+var_70], 58h ; 'X'
0x14018ea0f  add     edi, r10d
0x14018ea12  mov     [rsp+138h+var_C8], edi
0x14018ea16  test    [r15], r13b
0x14018ea19  jz      short loc_14018EA80
0x14018ea1b  lea     rdx, [rsp+138h+var_B0]
0x14018ea23  mov     rcx, r15
0x14018ea26  call    TxfGetRequiredAbortReservation
0x14018ea2b  mov     r13, [rsp+138h+var_B0]
0x14018ea33  test    r13, r13
0x14018ea36  jz      short loc_14018EA80
0x14018ea38  mov     r8, rsi
0x14018ea3b  mov     rcx, r14
0x14018ea3e  test    r9d, r9d
0x14018ea41  jz      short loc_14018EA6F
0x14018ea43  mov     edx, 725h
0x14018ea48  mov     r9d, r10d
0x14018ea4b  call    NtfsAddStructToRollbackList
0x14018ea50  add     [rax+20h], r13
0x14018ea54  or      dword ptr [rax+4], 1
0x14018ea58  mov     r9, r13
0x14018ea5b  mov     r8, rsi
0x14018ea5e  mov     rdx, [rsi+0D0h]
0x14018ea65  mov     rcx, r14
0x14018ea68  call    TxfReserveSpaceForAbortPriv
0x14018ea6d  jmp     short loc_14018EA80
0x14018ea6f  mov     r9, r13
0x14018ea72  mov     rdx, rbx
0x14018ea75  call    TxfReserveSpaceForAbortPriv
0x14018ea7a  mov     al, 1
0x14018ea7c  mov     [rsp+138h+var_E7], al
0x14018ea80  test    r14, r14
0x14018ea83  jnz     short loc_14018EA96
0x14018ea85  movzx   eax, word ptr [r15]
0x14018ea89  test    al, 0Ch
0x14018ea8b  jnz     short loc_14018EA96
0x14018ea8d  test    al, 10h
0x14018ea8f  jnz     short loc_14018EA96
0x14018ea91  xor     r13b, r13b
0x14018ea94  jmp     short loc_14018EAD0
0x14018ea96  call    cs:__imp_IoGetTopLevelIrp
0x14018ea9d  nop     dword ptr [rax+rax+00h]
0x14018eaa2  mov     r13, rax
0x14018eaa5  mov     [rsp+138h+var_98], rax
0x14018eaad  mov     edx, 28h ; '('; RegionSize
0x14018eab2  mov     rcx, rax; RegionStart
0x14018eab5  call    cs:__imp_IoWithinStackLimits
0x14018eabc  nop     dword ptr [rax+rax+00h]
0x14018eac1  mov     rcx, [r13+20h]
0x14018eac5  bts     dword ptr [rcx+1B4h], 7
0x14018eacd  mov     r13b, 1
0x14018ead0  movzx   ecx, word ptr [r15]
0x14018ead4  test    cl, 0Ch
0x14018ead7  jnz     short loc_14018EADE
0x14018ead9  test    cl, 10h
0x14018eadc  jz      short loc_14018EB12
0x14018eade  mov     [rsp+138h+Timeout], 0; Timeout
0x14018eae7  xor     r9d, r9d; Alertable
0x14018eaea  xor     r8d, r8d; WaitMode
0x14018eaed  xor     edx, edx; WaitReason
0x14018eaef  mov     rcx, [rbx+220h]; Object
0x14018eaf6  call    cs:__imp_KeWaitForSingleObject
0x14018eafd  nop     dword ptr [rax+rax+00h]
0x14018eb02  mov     [rsp+138h+var_E5], 1
0x14018eb07  mov     rax, [rbx+218h]
0x14018eb0e  mov     [r15+50h], rax
0x14018eb12  test    r14, r14
0x14018eb15  jz      short loc_14018EB25
0x14018eb17  mov     rcx, r14
0x14018eb1a  call    NtfsPurgeFileRecordCache
0x14018eb1f  bts     dword ptr [r14+4], 9
0x14018eb25  lea     rax, [rsi+28h]
0x14018eb29  lea     r9, [rsi+30h]; plsnUndoNext
0x14018eb2d  lea     rcx, [rsp+138h+plsn1]
0x14018eb32  mov     [rsp+138h+plsn], rcx; plsn
0x14018eb37  mov     ecx, [rsp+138h+var_D8]
0x14018eb3b  mov     [rsp+138h+fFlags], ecx; fFlags
0x14018eb3f  lea     rcx, [rsp+138h+var_70]
0x14018eb47  mov     [rsp+138h+rgcbReservation], rcx; rgcbReservation
0x14018eb4c  mov     [rsp+138h+cReserveRecords], edi; cReserveRecords
  ... truncated ...
```
