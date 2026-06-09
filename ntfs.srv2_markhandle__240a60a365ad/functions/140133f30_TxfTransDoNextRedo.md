# TxfTransDoNextRedo

- ea: `0x140133f30`
- end: `0x140134a51`
- name: `TxfTransDoNextRedo`
- size: `2849`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401d6948`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140010e5c`
- `0x1400291f0`
- `0x140029d80`
- `0x140103260`
- `0x140106348`
- `0x14010778c`
- `0x14010788c`
- `0x140107fdc`
- `0x1401085c0`
- `0x140108668`
- `0x1401087cc`
- `0x1401097d0`
- `0x140109e58`
- `0x14010adfc`
- `0x14010bca0`
- `0x14010be3c`
- `0x14010d734`
- `0x14010dc54`
- `0x140132718`
- `0x1401336c8`
- `0x140133bd4`
- `0x140133f30`
- `0x140134a58`
- `0x140135818`
- `0x14013ad80`
- `0x140140f5c`
- `0x140188ce4`
- `0x1401d7d5c`
- `0x1401d973c`
- `0x1401daa68`
- `0x1401db344`
- `0x14026d0c4`
- `0x140279e48`
- `0x140291978`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140134378`
- `ntoskrnl!ZwClose` at `0x14013438e`
- `ntoskrnl!ZwClose` at `0x140134378`
- `ntoskrnl!ZwClose` at `0x14013438e`
- `ntoskrnl!KeReleaseMutex` at `0x140134873`
- `ntoskrnl!KeReleaseMutex` at `0x1402c7d45`
- `ntoskrnl!KeReleaseMutex` at `0x140134873`
- `ntoskrnl!KeReleaseMutex` at `0x1402c7d45`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013494e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c7d68`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14013494e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c7d68`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013484d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140134a01`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013484d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140134a01`
- `ntoskrnl!CcUnpinData` at `0x140134128`
- `ntoskrnl!CcUnpinData` at `0x140134128`
- `ntoskrnl!ExAcquireFastMutex` at `0x140133f9a`
- `ntoskrnl!ExAcquireFastMutex` at `0x140133f9a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140133fd0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140133fd0`
- `ntoskrnl!ExRaiseStatus` at `0x1401342bc`
- `ntoskrnl!ExRaiseStatus` at `0x1401342bc`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134051`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134634`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401347b3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c7d9d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134051`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x140134634`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401347b3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1402c7d9d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140133fb5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134019`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134031`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401346f9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c7db9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140133fb5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134019`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x140134031`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1401346f9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnGreater` at `0x1402c7db9`

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
0x140133f30  mov     qword ptr [rsp+plsn2], r9
0x140133f35  mov     qword ptr [rsp+plsn1], r8
0x140133f3a  mov     [rsp+arg_8], rdx
0x140133f3f  mov     [rsp+arg_0], rcx
0x140133f44  push    rbx
0x140133f45  push    rsi
0x140133f46  push    rdi
0x140133f47  push    r12
0x140133f49  push    r13
0x140133f4b  push    r14
0x140133f4d  push    r15
0x140133f4f  sub     rsp, 60h
0x140133f53  mov     r14, rdx
0x140133f56  mov     rbx, rcx
0x140133f59  mov     rdi, [rdx+0D0h]
0x140133f60  test    dword ptr [rdi+88h], 8000h
0x140133f6a  jnz     loc_14013488C
0x140133f70  mov     [rdx+28h], r8
0x140133f74  mov     rcx, rdi
0x140133f77  call    TxfRmInForcedRecovery
0x140133f7c  test    al, al
0x140133f7e  jnz     loc_1401346EA
0x140133f84  mov     rax, qword ptr [rsp+98h+plsn1]
0x140133f8c  mov     [rdi+1C0h], rax
0x140133f93  mov     rcx, [rdi+1D8h]; FastMutex
0x140133f9a  call    cs:__imp_ExAcquireFastMutex
0x140133fa1  nop     dword ptr [rax+rax+00h]
0x140133fa6  lea     rdx, [rdi+1D0h]; plsn2
0x140133fad  lea     rcx, [rsp+98h+plsn1]; plsn1
0x140133fb5  call    cs:__imp_ClfsLsnGreater
0x140133fbc  nop     dword ptr [rax+rax+00h]
0x140133fc1  test    al, al
0x140133fc3  jnz     loc_14013498F
0x140133fc9  mov     rcx, [rdi+1D8h]; FastMutex
0x140133fd0  call    cs:__imp_ExReleaseFastMutex
0x140133fd7  nop     dword ptr [rax+rax+00h]
0x140133fdc  mov     r13, [rsp+98h+arg_20]
0x140133fe4  movzx   eax, word ptr [r13+0]
0x140133fe9  test    al, 2
0x140133feb  jz      loc_1401347AB
0x140133ff1  mov     rax, qword ptr [rsp+98h+plsn1]
0x140133ff9  mov     [r14+30h], rax
0x140133ffd  mov     rcx, rdi
0x140134000  call    TxfRmInForcedRecovery
0x140134005  test    al, al
0x140134007  jz      short loc_140134045
0x140134009  lea     rdx, [rsp+98h+plsn2]; plsn2
0x140134011  lea     rcx, [rsp+98h+plsn1]; plsn1
0x140134019  call    cs:__imp_ClfsLsnGreater
0x140134020  nop     dword ptr [rax+rax+00h]
0x140134025  test    al, al
0x140134027  jz      short loc_14013404D
0x140134029  lea     rdx, [r13+30h]; plsn2
0x14013402d  lea     rcx, [r14+48h]; plsn1
0x140134031  call    cs:__imp_ClfsLsnGreater
0x140134038  nop     dword ptr [rax+rax+00h]
0x14013403d  test    al, al
0x14013403f  jnz     loc_1401349DB
0x140134045  mov     rax, [r13+30h]
0x140134049  mov     [r14+48h], rax
0x14013404d  lea     rcx, [r14+20h]; plsn
0x140134051  call    cs:__imp_ClfsLsnNull
0x140134058  nop     dword ptr [rax+rax+00h]
0x14013405d  test    al, al
0x14013405f  jnz     short loc_1401340A9
0x140134061  movzx   eax, word ptr [r13+0]
0x140134066  movzx   ecx, ax
0x140134069  and     cx, 10h
0x14013406d  jnz     loc_14013472C
0x140134073  test    al, 8
0x140134075  jnz     loc_14013472C
0x14013407b  test    al, 4
0x14013407d  jnz     loc_1401348BF
0x140134083  test    al, 1
0x140134085  jnz     loc_1401346CB
0x14013408b  xor     esi, esi
0x14013408d  mov     edi, esi
0x14013408f  test    byte ptr [r13+0], 1
0x140134094  jnz     short loc_1401340D7
0x140134096  mov     eax, edi
0x140134098  add     rsp, 60h
0x14013409c  pop     r15
0x14013409e  pop     r14
0x1401340a0  pop     r13
0x1401340a2  pop     r12
0x1401340a4  pop     rdi
0x1401340a5  pop     rsi
0x1401340a6  pop     rbx
0x1401340a7  retn
0x1401340a9  test    byte ptr [r13+48h], 4
0x1401340ae  jnz     short loc_140134061
0x1401340b0  mov     rax, qword ptr [rsp+98h+plsn1]
0x1401340b8  mov     [r14+20h], rax
0x1401340bc  lea     rcx, [rdi+0A8h]
0x1401340c3  mov     rdx, [rcx]
0x1401340c6  cmp     [rdx+8], rcx
0x1401340ca  jz      loc_1401347D4
0x1401340d0  mov     ecx, 3
0x1401340d5  int     29h; Win8: RtlFailFast(ecx)
0x1401340d7  mov     r15, r13
0x1401340da  mov     r12d, esi
0x1401340dd  mov     [rsp+98h+var_54], esi
0x1401340e1  mov     [rsp+98h+Handle], rsi
0x1401340e6  mov     [rsp+98h+var_48], rsi
0x1401340eb  mov     edi, 0C00000D8h
0x1401340f0  cmp     edi, 0C0190030h
0x1401340f6  jz      short loc_140134096
0x1401340f8  cmp     edi, 0C0000188h
0x1401340fe  jz      loc_140134349
0x140134104  mov     eax, [rbx+128h]
0x14013410a  test    eax, eax
0x14013410c  jz      short loc_140134147
0x14013410e  dec     eax
0x140134110  mov     [rbx+128h], eax
0x140134116  mov     ecx, eax
0x140134118  add     rcx, rcx
0x14013411b  mov     rcx, [rbx+rcx*8+138h]; Bcb
0x140134123  test    rcx, rcx
0x140134126  jz      short loc_140134145
0x140134128  call    cs:__imp_CcUnpinData
0x14013412f  nop     dword ptr [rax+rax+00h]
0x140134134  mov     eax, [rbx+128h]
0x14013413a  add     rax, rax
0x14013413d  mov     [rbx+rax*8+138h], rsi
0x140134145  jmp     short loc_140134104
0x140134147  or      dword ptr [rbx+4], 200h
0x14013414e  mov     rcx, [rsp+98h+Handle]; Handle
0x140134153  test    rcx, rcx
0x140134156  jnz     loc_140134378
0x14013415c  mov     rcx, [rsp+98h+var_48]; Handle
0x140134161  test    rcx, rcx
0x140134164  jnz     loc_14013438E
0x14013416a  and     dword ptr [rbx+4], 0FFFFFDFFh
0x140134171  test    dword ptr [r14+10h], 4000000h
0x140134179  jnz     loc_1401343A4
0x14013417f  mov     edx, [rbx+18h]
0x140134182  test    edx, edx
0x140134184  jnz     loc_14013425F
0x14013418a  cmp     edi, 0C00000D8h
0x140134190  jnz     loc_14013425A
0x140134196  mov     edi, esi
0x140134198  mov     [rsp+98h+var_58], esi
0x14013419c  mov     eax, [r13+4]
0x1401341a0  cmp     eax, 12h
0x1401341a3  jnz     short loc_1401341D3
0x1401341a5  lea     r9, [rsp+98h+plsn1]
0x1401341ad  mov     r8, r13
0x1401341b0  mov     rdx, r14
0x1401341b3  mov     rcx, rbx; int
0x1401341b6  test    byte ptr [r15], 40h
0x1401341ba  jz      loc_140134676
0x1401341c0  mov     dword ptr [rsp+98h+var_70], esi; int
0x1401341c4  mov     [rsp+98h+Timeout], rsi; plsn2
0x1401341c9  call    TxfUndoRenameStream
0x1401341ce  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x1401341d3  cmp     eax, 11h
0x1401341d6  jnz     short loc_14013420A
0x1401341d8  mov     r8, r13; int
0x1401341db  mov     rdx, r14; int
0x1401341de  mov     rcx, rbx; int
0x1401341e1  test    byte ptr [r15], 40h
0x1401341e5  jz      loc_14013465D
0x1401341eb  mov     [rsp+98h+var_70], rsi; __int64
0x1401341f0  lea     rax, [rsp+98h+plsn1]
0x1401341f8  mov     [rsp+98h+Timeout], rax; plsn1
0x1401341fd  xor     r9d, r9d; int
0x140134200  call    TxfUndoCreateAttr
0x140134205  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x14013420a  dec     eax; switch 24 cases
0x14013420c  cmp     eax, 17h
0x14013420f  ja      def_140134229; jumptable 0000000140134229 default case, cases 8,12,17,18,22
0x140134215  cdqe
0x140134217  lea     r8, cs:140000000h
0x14013421e  mov     ecx, ds:(jpt_140134229 - 140000000h)[r8+rax*4]
0x140134226  add     rcx, r8
0x140134229  jmp     rcx; switch jump
0x14013422f  lea     rax, [rsp+98h+Handle]; jumptable 0000000140134229 case 11
0x140134234  mov     [rsp+98h+Timeout], rax
0x140134239  lea     r9, [rsp+98h+plsn1]
0x140134241  mov     r8, r13
0x140134244  mov     rdx, r14
0x140134247  mov     rcx, rbx
0x14013424a  call    TxfRedoAddTxfFileId
0x14013424f  mov     edi, eax
0x140134251  mov     [rsp+98h+var_58], eax
0x140134255  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x14013425a  jmp     loc_140134096
0x14013425f  movzx   eax, cs:NtfsStatusDebugFlags
0x140134266  test    al, al
0x140134268  jz      short loc_1401342B9
0x14013426a  lea     eax, [rdx-126h]
0x140134270  test    eax, 0FFFFFFFAh
0x140134275  jz      loc_1401343B7
0x14013427b  cmp     edx, 0FFFFFFEDh
0x14013427e  jnb     short loc_1401342B9
0x140134280  cmp     edx, 0C00000D8h
0x140134286  jz      short loc_1401342B9
0x140134288  cmp     edx, 0C0000016h
0x14013428e  jz      short loc_1401342B9
0x140134290  cmp     edx, 0C0000011h
0x140134296  jz      short loc_1401342B9
0x140134298  lea     eax, [rdx+7FFFFFFBh]
0x14013429e  cmp     eax, 1
0x1401342a1  jbe     short loc_1401342B9
0x1401342a3  cmp     edx, 103h
0x1401342a9  jz      short loc_1401342B9
0x1401342ab  mov     r8d, 313A08h
0x1401342b1  mov     rcx, rbx
0x1401342b4  call    NtfsStatusTraceAndDebugInternal
0x1401342b9  mov     ecx, [rbx+18h]; Status
0x1401342bc  call    cs:__imp_ExRaiseStatus
0x1401342c8  movzx   eax, cs:NtfsStatusDebugFlags
0x1401342cf  test    al, al
0x1401342d1  jz      short loc_14013433B
0x1401342d3  mov     edx, 0C0190030h
0x1401342d8  xor     ecx, ecx
0x1401342da  mov     r8d, 313AE0h
0x1401342e0  call    NtfsStatusTraceAndDebugInternal
0x1401342e5  mov     edi, 0C0190030h
0x1401342ea  mov     [rsp+98h+var_58], edi
0x1401342ee  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x1401342f3  movzx   eax, cs:NtfsStatusDebugFlags
0x1401342fa  test    al, al
0x1401342fc  jz      short loc_14013433B
0x1401342fe  mov     edx, 0C0190030h
0x140134303  xor     ecx, ecx
0x140134305  mov     r8d, 313B39h
0x14013430b  call    NtfsStatusTraceAndDebugInternal
0x140134310  mov     edi, 0C0190030h
0x140134315  mov     [rsp+98h+var_58], edi
0x140134319  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x14013431e  movzx   eax, cs:NtfsStatusDebugFlags; jumptable 0000000140134229 default case, cases 8,12,17,18,22
0x140134325  test    al, al
0x140134327  jz      short loc_14013433B
0x140134329  mov     edx, 0C0190030h
0x14013432e  xor     ecx, ecx
0x140134330  mov     r8d, 313B44h
0x140134336  call    NtfsStatusTraceAndDebugInternal
0x14013433b  mov     edi, 0C0190030h
0x140134340  mov     [rsp+98h+var_58], edi
0x140134344  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x140134349  mov     rcx, rbx
0x14013434c  call    NtfsCheckpointForLogFileFull
0x140134351  inc     r12d
0x140134354  mov     [rsp+98h+var_54], r12d
0x140134359  cmp     r12d, 2
0x14013435d  jb      short loc_140134363
0x14013435f  or      dword ptr [rbx+4], 10h
0x140134363  movzx   eax, cs:NtfsStatusDebugFlags
0x14013436a  mov     edi, 0C00000D8h
0x14013436f  mov     [rsp+98h+var_58], edi
0x140134373  jmp     loc_140134104
0x140134378  call    cs:__imp_ZwClose
0x14013437f  nop     dword ptr [rax+rax+00h]
0x140134384  mov     [rsp+98h+Handle], rsi
0x140134389  jmp     loc_14013415C
0x14013438e  call    cs:__imp_ZwClose
0x140134395  nop     dword ptr [rax+rax+00h]
0x14013439a  mov     [rsp+98h+var_48], rsi
0x14013439f  jmp     loc_14013416A
0x1401343a4  xor     r8d, r8d
0x1401343a7  mov     rdx, r14
0x1401343aa  mov     rcx, rbx
0x1401343ad  call    TxfCloseHandlesForTransaction
0x1401343b2  jmp     loc_14013417F
0x1401343b7  cmp     edx, 127h
0x1401343bd  jnz     loc_1401342B9
0x1401343c3  jmp     loc_14013427B
0x1401343c8  mov     dword ptr [rsp+98h+var_68], esi; jumptable 0000000140134229 case 9
0x1401343cc  lea     rax, [rsp+98h+plsn1]
0x1401343d4  mov     [rsp+98h+var_70], rax; __int64
0x1401343d9  mov     rax, [r13+80h]
0x1401343e0  mov     [rsp+98h+Timeout], rax; __int64
0x1401343e5  mov     r9, [r13+88h]
0x1401343ec  mov     r8, r13
0x1401343ef  mov     rdx, r14
0x1401343f2  mov     rcx, rbx; int
0x1401343f5  call    TxfTransSetAttrSizes
0x1401343fa  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x1401343ff  lea     rax, [rsp+98h+var_48]; jumptable 0000000140134229 cases 2,5
0x140134404  mov     [rsp+98h+var_70], rax
0x140134409  lea     rax, [rsp+98h+Handle]
0x14013440e  mov     [rsp+98h+Timeout], rax
0x140134413  lea     r9, [rsp+98h+plsn1]
0x14013441b  mov     r8, r13
0x14013441e  mov     rdx, r14
0x140134421  mov     rcx, rbx
0x140134424  call    TxfRedoAddFileName
0x140134429  jmp     loc_14013467B; jumptable 0000000140134229 cases 19,24
0x14013442e  lea     rax, [rsp+98h+var_48]; jumptable 0000000140134229 case 4
0x140134433  mov     [rsp+98h+var_60], rax; __int64
0x140134438  lea     rax, [rsp+98h+Handle]
0x14013443d  mov     [rsp+98h+var_68], rax; __int64
0x140134442  mov     [rsp+98h+var_70], rsi; __int64
0x140134447  lea     rax, [rsp+98h+plsn1]
0x14013444f  mov     [rsp+98h+Timeout], rax; __int64
0x140134454  mov     r9, r13
0x140134457  xor     r8d, r8d
0x14013445a  mov     rdx, r14
0x14013445d  mov     rcx, rbx; int
  ... truncated ...
```
