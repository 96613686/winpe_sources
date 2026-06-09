# TxfTransDoNextRedo

- ea: `0x140133f80`
- end: `0x140134aa1`
- name: `TxfTransDoNextRedo`
- size: `2849`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401d6998`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140010e5c`
- `0x1400291f0`
- `0x140029d80`
- `0x1401032b0`
- `0x140106398`
- `0x1401077dc`
- `0x1401078dc`
- `0x14010802c`
- `0x140108610`
- `0x1401086b8`
- `0x14010881c`
- `0x140109820`
- `0x140109ea8`
- `0x14010ae4c`
- `0x14010bcf0`
- `0x14010be8c`
- `0x14010d784`
- `0x14010dca4`
- `0x140132768`
- `0x140133718`
- `0x140133c24`
- `0x140133f80`
- `0x140134aa8`
- `0x140135868`
- `0x14013add0`
- `0x140140fac`
- `0x140188d34`
- `0x1401d7dac`
- `0x1401d978c`
- `0x1401daab8`
- `0x1401db394`
- `0x14026d114`
- `0x140279e98`
- `0x1402919c8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401343c8`
- `ntoskrnl!ZwClose` at `0x1401343de`
- `ntoskrnl!ZwClose` at `0x1401343c8`
- `ntoskrnl!ZwClose` at `0x1401343de`
- `ntoskrnl!KeReleaseMutex` at `0x1401348c3`
- `ntoskrnl!KeReleaseMutex` at `0x1402c7d95`
- `ntoskrnl!KeReleaseMutex` at `0x1401348c3`
- `ntoskrnl!KeReleaseMutex` at `0x1402c7d95`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013499e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c7db8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013499e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c7db8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013489d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140134a51`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013489d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140134a51`
- `ntoskrnl!CcUnpinData` at `0x140134178`
- `ntoskrnl!CcUnpinData` at `0x140134178`
- `ntoskrnl!ExAcquireFastMutex` at `0x140133fea`
- `ntoskrnl!ExAcquireFastMutex` at `0x140133fea`
- `ntoskrnl!ExReleaseFastMutex` at `0x140134020`
- `ntoskrnl!ExReleaseFastMutex` at `0x140134020`
- `ntoskrnl!ExRaiseStatus` at `0x14013430c`
- `ntoskrnl!ExRaiseStatus` at `0x14013430c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401340a1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134684`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134803`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c7ded`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401340a1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134684`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134803`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c7ded`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134005`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134069`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134081`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134749`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c7e09`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134005`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134069`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134081`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134749`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c7e09`

## pseudocode

```c
__int64 TxfTransDoNextRedo(__int64 a1, CLFS_LSN *a2, CLFS_LSN a3, ...)
{
  __int64 v3; // r14
  CLFS_LSN v5; // rdi
  __int64 v6; // r13
  CLFS_LSN v7; // rax
  __int64 v8; // r8
  __int16 v9; // ax
  unsigned int v10; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int v14; // r12d
  int v15; // eax
  unsigned int v16; // eax
  void *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // kr00_8
  CLFS_LSN **v22; // rsi
  __int64 v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rdi
  __int64 v26; // rcx
  void *v27; // rcx
  CLFS_LSN *v28; // rcx
  CLFS_LSN **v29; // rax
  void *ullOffset; // rcx
  signed __int64 v31; // rcx
  __int64 v32; // rax
  CLFS_LSN **v33; // r12
  CLFS_LSN *v34; // rdi
  CLFS_LSN ***v35; // r14
  HANDLE *Timeout; // [rsp+20h] [rbp-78h]
  HANDLE Handle; // [rsp+48h] [rbp-50h] BYREF
  HANDLE v38[9]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v39; // [rsp+A8h] [rbp+10h] BYREF
  CLFS_LSN plsn1; // [rsp+B0h] [rbp+18h] BYREF
  CLFS_LSN plsn2; // [rsp+B8h] [rbp+20h] BYREF
  va_list plsn2a; // [rsp+B8h] [rbp+20h]
  _WORD *v43; // [rsp+C0h] [rbp+28h]
  va_list va1; // [rsp+C8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(plsn2a, a3);
  plsn2.ullOffset = va_arg(va1, _QWORD);
  v43 = va_arg(va1, _WORD *);
  plsn1 = a3;
  v39 = (__int64)a2;
  v3 = (__int64)a2;
  v5 = a2[26];
  if ( (*(_DWORD *)(v5.ullOffset + 136) & 0x8000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3222863877LL, 3225675);
    return 3222863877LL;
  }
  a2[5] = a3;
  if ( (unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset)
    && !ClfsLsnGreater(&plsn1, (const CLFS_LSN *)(v5.ullOffset + 448)) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3225704);
    return 3221225730LL;
  }
  *(CLFS_LSN *)(v5.ullOffset + 448) = plsn1;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v5.ullOffset + 472));
  if ( ClfsLsnGreater(&plsn1, (const CLFS_LSN *)(v5.ullOffset + 464)) )
  {
    do
      v31 = _InterlockedCompareExchange64(
              (volatile signed __int64 *)(v5.ullOffset + 464),
              NtfsLarge0.QuadPart,
              NtfsLarge0.QuadPart);
    while ( v31 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5.ullOffset + 464), plsn1.ullOffset, v31) );
  }
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v5.ullOffset + 472));
  v6 = (__int64)v43;
  if ( (*v43 & 2) != 0 )
  {
    v7 = plsn1;
  }
  else
  {
    if ( (*v43 & 0x40) == 0
      && !ClfsLsnNull((const CLFS_LSN *)(v3 + 48))
      && (*(_BYTE *)v6 & 0x18) == 0
      && (*(_BYTE *)(v6 + 74) & 2) == 0 )
    {
      goto LABEL_7;
    }
    v7 = plsn2;
  }
  *(CLFS_LSN *)(v3 + 48) = v7;
LABEL_7:
  if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD))TxfRmInForcedRecovery)((CLFS_LSN)v5.ullOffset)
    || ClfsLsnGreater(&plsn1, (const CLFS_LSN *)plsn2a)
    && (!ClfsLsnGreater((const CLFS_LSN *)(v3 + 72), (const CLFS_LSN *)(v6 + 48)) || (*(_BYTE *)v6 & 0x40) != 0) )
  {
    *(_QWORD *)(v3 + 72) = *(_QWORD *)(v6 + 48);
  }
  if ( ClfsLsnNull((const CLFS_LSN *)(v3 + 32)) && (*(_BYTE *)(v6 + 72) & 4) == 0 )
  {
    *(CLFS_LSN *)(v3 + 32) = plsn1;
    v12 = (_QWORD *)(v5.ullOffset + 168);
    v13 = *(_QWORD *)(v5.ullOffset + 168);
    if ( *(_QWORD *)(v13 + 8) != v5.ullOffset + 168 )
LABEL_20:
      __fastfail(3u);
    *(_QWORD *)(v3 + 120) = v13;
    *(_QWORD *)(v3 + 128) = v12;
    *(_QWORD *)(v13 + 8) = v3 + 120;
    *v12 = v3 + 120;
    _InterlockedIncrement((volatile signed __int32 *)(v5.ullOffset + 236));
  }
  v9 = *(_WORD *)v6;
  if ( (*(_WORD *)v6 & 0x10) != 0 || (v9 & 8) != 0 )
  {
    if ( *(_QWORD *)(v3 + 88) != v3 + 88 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3225825);
      return 3221225730LL;
    }
    if ( (*(_WORD *)v6 & 0x10) != 0 )
    {
      *(_QWORD *)(v3 + 384) = *(_QWORD *)(v6 + 88);
      TxfWriteUsnRecordsAtCommit(a1, v3);
    }
    TxfTransCleanupOnTransEnd(a1, v3, *(_WORD *)v6 & 0x10, 0, 1);
    _InterlockedAnd((volatile signed __int32 *)(v3 + 16), 0xFFFFFFFE);
    TxfRemoveTransactionFromList(v3);
    TxfDereferenceTransaction(&v39, 0);
    KeWaitForSingleObject(*(PVOID *)(v5.ullOffset + 544), Executive, 0, 0, 0);
    v23 = *(_QWORD *)(v6 + 80);
    if ( v23 > *(_QWORD *)(v5.ullOffset + 536) )
      *(_QWORD *)(v5.ullOffset + 536) = v23;
    KeReleaseMutex(*(PRKMUTEX *)(v5.ullOffset + 544), 0);
    v3 = v39;
  }
  else if ( (v9 & 4) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(v3 + 16), 1u);
    *(_QWORD *)(v3 + 384) = *(_QWORD *)(v6 + 88);
    if ( *(_QWORD *)(v3 + 88) != v3 + 88 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3225905);
      return 3221225730LL;
    }
    KeWaitForSingleObject(*(PVOID *)(v5.ullOffset + 544), Executive, 0, 0, 0);
    v32 = *(_QWORD *)(v6 + 80);
    if ( v32 > *(_QWORD *)(v5.ullOffset + 536) )
      *(_QWORD *)(v5.ullOffset + 536) = v32;
    KeReleaseMutex(*(PRKMUTEX *)(v5.ullOffset + 544), 0);
  }
  else if ( (v9 & 1) != 0 )
  {
    if ( (v9 & 0x40) != 0 && (*(_DWORD *)(v3 + 16) & 8) == 0 && (*(_BYTE *)(v6 + 74) & 4) != 0 )
    {
      _InterlockedOr((volatile signed __int32 *)(v3 + 16), 8u);
      if ( *(_QWORD *)(v3 + 88) != v3 + 88 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3225955);
        return 3221225730LL;
      }
      while ( 1 )
      {
        v24 = (_QWORD *)(v3 + 176);
        v25 = *(_QWORD **)(v3 + 176);
        if ( v25 == (_QWORD *)(v3 + 176) )
          break;
        if ( (_QWORD *)v25[1] != v24 )
          goto LABEL_20;
        v26 = *v25;
        if ( *(_QWORD **)(*v25 + 8LL) != v25 )
          goto LABEL_20;
        *v24 = v26;
        *(_QWORD *)(v26 + 8) = v24;
        v27 = (void *)v25[4];
        if ( v27 )
          TxfDereferenceTxfFcb(v27);
        ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v25);
      }
    }
    if ( (*(_BYTE *)(v6 + 74) & 2) != 0 )
    {
      v22 = *(CLFS_LSN ***)(v3 + 184);
      while ( v22 != (CLFS_LSN **)(v3 + 176) )
      {
        v33 = v22;
        v34 = (CLFS_LSN *)v22;
        v35 = (CLFS_LSN ***)(v22 + 1);
        v22 = (CLFS_LSN **)v22[1];
        if ( !ClfsLsnNull(v34 + 2) )
        {
          if ( !ClfsLsnGreater(v34 + 2, (const CLFS_LSN *)plsn2a) )
          {
            v3 = v39;
            break;
          }
          v28 = *v33;
          if ( (CLFS_LSN *)(*v33)[1].ullOffset != v34 )
            goto LABEL_20;
          v29 = *v35;
          if ( **v35 != v34 )
            goto LABEL_20;
          *v29 = v28;
          v28[1].ullOffset = (ULONGLONG)v29;
          ullOffset = (void *)v34[4].ullOffset;
          if ( ullOffset )
            TxfDereferenceTxfFcb(ullOffset);
          ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v34);
        }
        v3 = v39;
      }
    }
  }
  v10 = 0;
  if ( (*(_BYTE *)v6 & 1) != 0 )
  {
    v14 = 0;
    Handle = 0;
    v38[0] = 0;
    v10 = -1073741608;
    while ( v10 != -1072103376 )
    {
      if ( v10 == -1073741432 )
      {
        NtfsCheckpointForLogFileFull(a1);
        if ( (unsigned int)++v14 >= 2 )
          *(_DWORD *)(a1 + 4) |= 0x10u;
        v10 = -1073741608;
      }
      while ( 1 )
      {
        v15 = *(_DWORD *)(a1 + 296);
        if ( !v15 )
          break;
        v16 = v15 - 1;
        *(_DWORD *)(a1 + 296) = v16;
        v17 = *(void **)(a1 + 16LL * v16 + 312);
        if ( v17 )
        {
          CcUnpinData(v17);
          *(_QWORD *)(a1 + 16LL * *(unsigned int *)(a1 + 296) + 312) = 0;
        }
      }
      *(_DWORD *)(a1 + 4) |= 0x200u;
      if ( Handle )
      {
        ZwClose(Handle);
        Handle = 0;
      }
      if ( v38[0] )
      {
        ZwClose(v38[0]);
        v38[0] = 0;
      }
      *(_DWORD *)(a1 + 4) &= ~0x200u;
      if ( (*(_DWORD *)(v3 + 16) & 0x4000000) != 0 )
        TxfCloseHandlesForTransaction(a1, v3, 0);
      v18 = *(unsigned int *)(a1 + 24);
      if ( (_DWORD)v18 )
      {
        if ( NtfsStatusDebugFlags
          && ((((_DWORD)v18 - 294) & 0xFFFFFFFA) != 0 || (_DWORD)v18 == 295)
          && (unsigned int)v18 < 0xFFFFFFED
          && (_DWORD)v18 != -1073741608
          && (_DWORD)v18 != -1073741802
          && (_DWORD)v18 != -1073741807
          && (unsigned int)(v18 + 2147483643) > 1
          && (_DWORD)v18 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v18, 3226120);
        }
        ExRaiseStatus(*(_DWORD *)(a1 + 24));
      }
      if ( v10 != -1073741608 )
        break;
      v10 = 0;
      v19 = *(_DWORD *)(v6 + 4);
      if ( v19 == 18 )
      {
        if ( (*(_BYTE *)v6 & 0x40) != 0 )
          TxfUndoRenameStream(a1, 0, 0);
        else
          TxfRedoRenameStream(a1);
      }
      else if ( v19 == 17 )
      {
        if ( (*(_BYTE *)v6 & 0x40) != 0 )
          TxfUndoCreateAttr(a1, v3, v6, 0, &plsn1, 0);
        else
          TxfRedoCreateAttr(a1, &Handle);
      }
      else
      {
        v21 = v8;
        v20 = 0x140000000uLL;
        switch ( v19 )
        {
          case 1:
            TxfRedoCreateNewFile(a1, &Handle);
            break;
          case 2:
          case 5:
            Timeout = &Handle;
            TxfRedoAddFileName(a1, v3, v6, &plsn1);
            break;
          case 3:
            TxfRedoDeleteFile(a1, v3, v6, (unsigned int)&plsn1, (_DWORD)Timeout, (__int64)&Handle, (__int64)v38);
            break;
          case 4:
            TxfRedoUndoFileRename(a1, (__int64)&plsn1, 0, (__int64)&Handle, (__int64)v38);
            break;
          case 6:
            if ( (*(_BYTE *)v6 & 0x40) != 0 )
              TxfCLRAndUndoWriteFile(a1, v3, v6, (unsigned int)&plsn1, 0);
            else
              TxfRedoWriteFile(a1, v3, v6, &plsn1);
            break;
          case 7:
            TxfRedoUndoFcbInfoUpdateFile(a1);
            break;
          case 9:
            TxfTransSetAttrSizes(a1, *(_QWORD *)(v6 + 128), (__int64)&plsn1, 0);
            break;
          case 10:
            if ( (*(_BYTE *)v6 & 0x40) != 0 )
              TxfUndoModifySecurityFile(a1, 0, 0);
            else
              TxfRedoModifySecurityFile(a1);
            break;
          case 11:
            v10 = TxfRedoAddTxfFileId(a1, (__int64)&Handle);
            break;
          case 13:
            v10 = TxfProcessRedoCancelRecord(
                    a1,
                    v3,
                    (CLFS_LSN *)v6,
                    &plsn1,
                    (ULONG)Timeout,
                    (__int64)&Handle,
                    (__int64)v38);
            break;
          case 14:
            if ( (*(_BYTE *)v6 & 0x40) != 0 )
              TxfUndoCreateBackupFile(a1, v3, v6, 0, (__int64)&Handle);
            else
              TxfRedoCreateBackupFile(a1, v3, v6, (__int64)&plsn1);
            break;
          case 15:
            if ( (*(_BYTE *)v6 & 0x40) != 0 )
              TxfUndoMoveAttr(a1, (CLFS_LSN *)v3, v6, &plsn1, 0, 0);
            else
              TxfRedoMoveAttr(a1, v3, v6, &plsn1);
            break;
          case 16:
            if ( (*(_BYTE *)v6 & 0x40) != 0 )
            {
              if ( !NtfsStatusDebugFlags )
                goto LABEL_61;
              NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3226336);
              v10 = -1072103376;
            }
            else
            {
              TxfRedoRemoveAttr(a1);
            }
            break;
          case 19:
          case 24:
            break;
          case 20:
            TxfRedoZeroUserRange((PVOID)a1);
            break;
          case 21:
            TxfRedoZeroFlushTops(a1);
            break;
          case 23:
            if ( ClfsLsnNull((const CLFS_LSN *)(v6 + 80)) && *(_WORD *)(v3 + 414) )
            {
              if ( !NtfsStatusDebugFlags )
                goto LABEL_61;
              NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3226425);
              v10 = -1072103376;
            }
            else
            {
              ++*(_WORD *)(v3 + 414);
            }
            break;
          default:
            v20 = v21;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3222863920LL, 3226436);
LABEL_61:
            v10 = -1072103376;
            break;
        }
      }
      NtfsCleanupIrpContext(a1, 0, v20);
      *(_DWORD *)(*(_QWORD *)(a1 + 144) + 24LL) = 0;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140133f80  mov     qword ptr [rsp+plsn2], r9
0x140133f85  mov     qword ptr [rsp+plsn1], r8
0x140133f8a  mov     [rsp+arg_8], rdx
0x140133f8f  mov     [rsp+arg_0], rcx
0x140133f94  push    rbx
0x140133f95  push    rsi
0x140133f96  push    rdi
0x140133f97  push    r12
0x140133f99  push    r13
0x140133f9b  push    r14
0x140133f9d  push    r15
0x140133f9f  sub     rsp, 60h
0x140133fa3  mov     r14, rdx
0x140133fa6  mov     rbx, rcx
0x140133fa9  mov     rdi, [rdx+0D0h]
0x140133fb0  test    dword ptr [rdi+88h], 8000h
0x140133fba  jnz     loc_1401348DC
0x140133fc0  mov     [rdx+28h], r8
0x140133fc4  mov     rcx, rdi
0x140133fc7  call    TxfRmInForcedRecovery
0x140133fcc  test    al, al
0x140133fce  jnz     loc_14013473A
0x140133fd4  mov     rax, qword ptr [rsp+98h+plsn1]
0x140133fdc  mov     [rdi+1C0h], rax
0x140133fe3  mov     rcx, [rdi+1D8h]; FastMutex
0x140133fea  call    cs:__imp_ExAcquireFastMutex
0x140133ff1  nop     dword ptr [rax+rax+00h]
0x140133ff6  lea     rdx, [rdi+1D0h]; plsn2
0x140133ffd  lea     rcx, [rsp+98h+plsn1]; plsn1
0x140134005  call    cs:__imp_ClfsLsnGreater
0x14013400c  nop     dword ptr [rax+rax+00h]
0x140134011  test    al, al
0x140134013  jnz     loc_1401349DF
0x140134019  mov     rcx, [rdi+1D8h]; FastMutex
0x140134020  call    cs:__imp_ExReleaseFastMutex
0x140134027  nop     dword ptr [rax+rax+00h]
0x14013402c  mov     r13, [rsp+98h+arg_20]
0x140134034  movzx   eax, word ptr [r13+0]
0x140134039  test    al, 2
0x14013403b  jz      loc_1401347FB
0x140134041  mov     rax, qword ptr [rsp+98h+plsn1]
0x140134049  mov     [r14+30h], rax
0x14013404d  mov     rcx, rdi
0x140134050  call    TxfRmInForcedRecovery
0x140134055  test    al, al
0x140134057  jz      short loc_140134095
0x140134059  lea     rdx, [rsp+98h+plsn2]; plsn2
0x140134061  lea     rcx, [rsp+98h+plsn1]; plsn1
0x140134069  call    cs:__imp_ClfsLsnGreater
0x140134070  nop     dword ptr [rax+rax+00h]
0x140134075  test    al, al
0x140134077  jz      short loc_14013409D
0x140134079  lea     rdx, [r13+30h]; plsn2
0x14013407d  lea     rcx, [r14+48h]; plsn1
0x140134081  call    cs:__imp_ClfsLsnGreater
0x140134088  nop     dword ptr [rax+rax+00h]
0x14013408d  test    al, al
0x14013408f  jnz     loc_140134A2B
0x140134095  mov     rax, [r13+30h]
0x140134099  mov     [r14+48h], rax
0x14013409d  lea     rcx, [r14+20h]; plsn
0x1401340a1  call    cs:__imp_ClfsLsnNull
0x1401340a8  nop     dword ptr [rax+rax+00h]
0x1401340ad  test    al, al
0x1401340af  jnz     short loc_1401340F9
0x1401340b1  movzx   eax, word ptr [r13+0]
0x1401340b6  movzx   ecx, ax
0x1401340b9  and     cx, 10h
0x1401340bd  jnz     loc_14013477C
0x1401340c3  test    al, 8
0x1401340c5  jnz     loc_14013477C
0x1401340cb  test    al, 4
0x1401340cd  jnz     loc_14013490F
0x1401340d3  test    al, 1
0x1401340d5  jnz     loc_14013471B
0x1401340db  xor     esi, esi
0x1401340dd  mov     edi, esi
0x1401340df  test    byte ptr [r13+0], 1
0x1401340e4  jnz     short loc_140134127
0x1401340e6  mov     eax, edi
0x1401340e8  add     rsp, 60h
0x1401340ec  pop     r15
0x1401340ee  pop     r14
0x1401340f0  pop     r13
0x1401340f2  pop     r12
0x1401340f4  pop     rdi
0x1401340f5  pop     rsi
0x1401340f6  pop     rbx
0x1401340f7  retn
0x1401340f9  test    byte ptr [r13+48h], 4
0x1401340fe  jnz     short loc_1401340B1
0x140134100  mov     rax, qword ptr [rsp+98h+plsn1]
0x140134108  mov     [r14+20h], rax
0x14013410c  lea     rcx, [rdi+0A8h]
0x140134113  mov     rdx, [rcx]
0x140134116  cmp     [rdx+8], rcx
0x14013411a  jz      loc_140134824
0x140134120  mov     ecx, 3
0x140134125  int     29h; Win8: RtlFailFast(ecx)
0x140134127  mov     r15, r13
0x14013412a  mov     r12d, esi
0x14013412d  mov     [rsp+98h+var_54], esi
0x140134131  mov     [rsp+98h+Handle], rsi
0x140134136  mov     [rsp+98h+var_48], rsi
0x14013413b  mov     edi, 0C00000D8h
0x140134140  cmp     edi, 0C0190030h
0x140134146  jz      short loc_1401340E6
0x140134148  cmp     edi, 0C0000188h
0x14013414e  jz      loc_140134399
0x140134154  mov     eax, [rbx+128h]
0x14013415a  test    eax, eax
0x14013415c  jz      short loc_140134197
0x14013415e  dec     eax
0x140134160  mov     [rbx+128h], eax
0x140134166  mov     ecx, eax
0x140134168  add     rcx, rcx
0x14013416b  mov     rcx, [rbx+rcx*8+138h]; Bcb
0x140134173  test    rcx, rcx
0x140134176  jz      short loc_140134195
0x140134178  call    cs:__imp_CcUnpinData
0x14013417f  nop     dword ptr [rax+rax+00h]
0x140134184  mov     eax, [rbx+128h]
0x14013418a  add     rax, rax
0x14013418d  mov     [rbx+rax*8+138h], rsi
0x140134195  jmp     short loc_140134154
0x140134197  or      dword ptr [rbx+4], 200h
0x14013419e  mov     rcx, [rsp+98h+Handle]; Handle
0x1401341a3  test    rcx, rcx
0x1401341a6  jnz     loc_1401343C8
0x1401341ac  mov     rcx, [rsp+98h+var_48]; Handle
0x1401341b1  test    rcx, rcx
0x1401341b4  jnz     loc_1401343DE
0x1401341ba  and     dword ptr [rbx+4], 0FFFFFDFFh
0x1401341c1  test    dword ptr [r14+10h], 4000000h
0x1401341c9  jnz     loc_1401343F4
0x1401341cf  mov     edx, [rbx+18h]
0x1401341d2  test    edx, edx
0x1401341d4  jnz     loc_1401342AF
0x1401341da  cmp     edi, 0C00000D8h
0x1401341e0  jnz     loc_1401342AA
0x1401341e6  mov     edi, esi
0x1401341e8  mov     [rsp+98h+var_58], esi
0x1401341ec  mov     eax, [r13+4]
0x1401341f0  cmp     eax, 12h
0x1401341f3  jnz     short loc_140134223
0x1401341f5  lea     r9, [rsp+98h+plsn1]
0x1401341fd  mov     r8, r13
0x140134200  mov     rdx, r14
0x140134203  mov     rcx, rbx; int
0x140134206  test    byte ptr [r15], 40h
0x14013420a  jz      loc_1401346C6
0x140134210  mov     dword ptr [rsp+98h+var_70], esi; int
0x140134214  mov     [rsp+98h+Timeout], rsi; plsn2
0x140134219  call    TxfUndoRenameStream
0x14013421e  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x140134223  cmp     eax, 11h
0x140134226  jnz     short loc_14013425A
0x140134228  mov     r8, r13; int
0x14013422b  mov     rdx, r14; int
0x14013422e  mov     rcx, rbx; int
0x140134231  test    byte ptr [r15], 40h
0x140134235  jz      loc_1401346AD
0x14013423b  mov     [rsp+98h+var_70], rsi; __int64
0x140134240  lea     rax, [rsp+98h+plsn1]
0x140134248  mov     [rsp+98h+Timeout], rax; plsn1
0x14013424d  xor     r9d, r9d; int
0x140134250  call    TxfUndoCreateAttr
0x140134255  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x14013425a  dec     eax; switch 24 cases
0x14013425c  cmp     eax, 17h
0x14013425f  ja      def_140134279; jumptable 0000000140134279 default case, cases 8,12,17,18,22
0x140134265  cdqe
0x140134267  lea     r8, cs:140000000h
0x14013426e  mov     ecx, ds:(jpt_140134279 - 140000000h)[r8+rax*4]
0x140134276  add     rcx, r8
0x140134279  jmp     rcx; switch jump
0x14013427f  lea     rax, [rsp+98h+Handle]; jumptable 0000000140134279 case 11
0x140134284  mov     [rsp+98h+Timeout], rax
0x140134289  lea     r9, [rsp+98h+plsn1]
0x140134291  mov     r8, r13
0x140134294  mov     rdx, r14
0x140134297  mov     rcx, rbx
0x14013429a  call    TxfRedoAddTxfFileId
0x14013429f  mov     edi, eax
0x1401342a1  mov     [rsp+98h+var_58], eax
0x1401342a5  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x1401342aa  jmp     loc_1401340E6
0x1401342af  movzx   eax, cs:NtfsStatusDebugFlags
0x1401342b6  test    al, al
0x1401342b8  jz      short loc_140134309
0x1401342ba  lea     eax, [rdx-126h]
0x1401342c0  test    eax, 0FFFFFFFAh
0x1401342c5  jz      loc_140134407
0x1401342cb  cmp     edx, 0FFFFFFEDh
0x1401342ce  jnb     short loc_140134309
0x1401342d0  cmp     edx, 0C00000D8h
0x1401342d6  jz      short loc_140134309
0x1401342d8  cmp     edx, 0C0000016h
0x1401342de  jz      short loc_140134309
0x1401342e0  cmp     edx, 0C0000011h
0x1401342e6  jz      short loc_140134309
0x1401342e8  lea     eax, [rdx+7FFFFFFBh]
0x1401342ee  cmp     eax, 1
0x1401342f1  jbe     short loc_140134309
0x1401342f3  cmp     edx, 103h
0x1401342f9  jz      short loc_140134309
0x1401342fb  mov     r8d, 313A08h
0x140134301  mov     rcx, rbx
0x140134304  call    NtfsStatusTraceAndDebugInternal
0x140134309  mov     ecx, [rbx+18h]; Status
0x14013430c  call    cs:__imp_ExRaiseStatus
0x140134318  movzx   eax, cs:NtfsStatusDebugFlags
0x14013431f  test    al, al
0x140134321  jz      short loc_14013438B
0x140134323  mov     edx, 0C0190030h
0x140134328  xor     ecx, ecx
0x14013432a  mov     r8d, 313AE0h
0x140134330  call    NtfsStatusTraceAndDebugInternal
0x140134335  mov     edi, 0C0190030h
0x14013433a  mov     [rsp+98h+var_58], edi
0x14013433e  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x140134343  movzx   eax, cs:NtfsStatusDebugFlags
0x14013434a  test    al, al
0x14013434c  jz      short loc_14013438B
0x14013434e  mov     edx, 0C0190030h
0x140134353  xor     ecx, ecx
0x140134355  mov     r8d, 313B39h
0x14013435b  call    NtfsStatusTraceAndDebugInternal
0x140134360  mov     edi, 0C0190030h
0x140134365  mov     [rsp+98h+var_58], edi
0x140134369  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x14013436e  movzx   eax, cs:NtfsStatusDebugFlags; jumptable 0000000140134279 default case, cases 8,12,17,18,22
0x140134375  test    al, al
0x140134377  jz      short loc_14013438B
0x140134379  mov     edx, 0C0190030h
0x14013437e  xor     ecx, ecx
0x140134380  mov     r8d, 313B44h
0x140134386  call    NtfsStatusTraceAndDebugInternal
0x14013438b  mov     edi, 0C0190030h
0x140134390  mov     [rsp+98h+var_58], edi
0x140134394  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x140134399  mov     rcx, rbx
0x14013439c  call    NtfsCheckpointForLogFileFull
0x1401343a1  inc     r12d
0x1401343a4  mov     [rsp+98h+var_54], r12d
0x1401343a9  cmp     r12d, 2
0x1401343ad  jb      short loc_1401343B3
0x1401343af  or      dword ptr [rbx+4], 10h
0x1401343b3  movzx   eax, cs:NtfsStatusDebugFlags
0x1401343ba  mov     edi, 0C00000D8h
0x1401343bf  mov     [rsp+98h+var_58], edi
0x1401343c3  jmp     loc_140134154
0x1401343c8  call    cs:__imp_ZwClose
0x1401343cf  nop     dword ptr [rax+rax+00h]
0x1401343d4  mov     [rsp+98h+Handle], rsi
0x1401343d9  jmp     loc_1401341AC
0x1401343de  call    cs:__imp_ZwClose
0x1401343e5  nop     dword ptr [rax+rax+00h]
0x1401343ea  mov     [rsp+98h+var_48], rsi
0x1401343ef  jmp     loc_1401341BA
0x1401343f4  xor     r8d, r8d
0x1401343f7  mov     rdx, r14
0x1401343fa  mov     rcx, rbx
0x1401343fd  call    TxfCloseHandlesForTransaction
0x140134402  jmp     loc_1401341CF
0x140134407  cmp     edx, 127h
0x14013440d  jnz     loc_140134309
0x140134413  jmp     loc_1401342CB
0x140134418  mov     dword ptr [rsp+98h+var_68], esi; jumptable 0000000140134279 case 9
0x14013441c  lea     rax, [rsp+98h+plsn1]
0x140134424  mov     [rsp+98h+var_70], rax; __int64
0x140134429  mov     rax, [r13+80h]
0x140134430  mov     [rsp+98h+Timeout], rax; __int64
0x140134435  mov     r9, [r13+88h]
0x14013443c  mov     r8, r13
0x14013443f  mov     rdx, r14
0x140134442  mov     rcx, rbx; int
0x140134445  call    TxfTransSetAttrSizes
0x14013444a  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x14013444f  lea     rax, [rsp+98h+var_48]; jumptable 0000000140134279 cases 2,5
0x140134454  mov     [rsp+98h+var_70], rax
0x140134459  lea     rax, [rsp+98h+Handle]
0x14013445e  mov     [rsp+98h+Timeout], rax
0x140134463  lea     r9, [rsp+98h+plsn1]
0x14013446b  mov     r8, r13
0x14013446e  mov     rdx, r14
0x140134471  mov     rcx, rbx
0x140134474  call    TxfRedoAddFileName
0x140134479  jmp     loc_1401346CB; jumptable 0000000140134279 cases 19,24
0x14013447e  lea     rax, [rsp+98h+var_48]; jumptable 0000000140134279 case 4
0x140134483  mov     [rsp+98h+var_60], rax; __int64
0x140134488  lea     rax, [rsp+98h+Handle]
0x14013448d  mov     [rsp+98h+var_68], rax; __int64
0x140134492  mov     [rsp+98h+var_70], rsi; __int64
0x140134497  lea     rax, [rsp+98h+plsn1]
0x14013449f  mov     [rsp+98h+Timeout], rax; __int64
0x1401344a4  mov     r9, r13
0x1401344a7  xor     r8d, r8d
0x1401344aa  mov     rdx, r14
0x1401344ad  mov     rcx, rbx; int
  ... truncated ...
```
