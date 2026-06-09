# TxfRollforwardUndo

- ea: `0x1402670c0`
- end: `0x14026800c`
- name: `TxfRollforwardUndo`
- size: `3916`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400fdbb4`
- `0x1401f4220`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140010be0`
- `0x140010c54`
- `0x140010e5c`
- `0x140010e98`
- `0x1400291f0`
- `0x140029d80`
- `0x1400414f4`
- `0x140049c90`
- `0x140059250`
- `0x1400596c0`
- `0x1400fa3d8`
- `0x140188ce4`
- `0x1401ac080`
- `0x1401d4f40`
- `0x1401d5ad0`
- `0x1401d6024`
- `0x1401d60b8`
- `0x140214de8`
- `0x1402670c0`
- `0x140268014`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140267213`
- `ntoskrnl!DbgPrintEx` at `0x1402673e1`
- `ntoskrnl!DbgPrintEx` at `0x140267565`
- `ntoskrnl!DbgPrintEx` at `0x14026769f`
- `ntoskrnl!DbgPrintEx` at `0x140267a12`
- `ntoskrnl!DbgPrintEx` at `0x140267b30`
- `ntoskrnl!DbgPrintEx` at `0x140267dd2`
- `ntoskrnl!DbgPrintEx` at `0x140267f06`
- `ntoskrnl!DbgPrintEx` at `0x140267213`
- `ntoskrnl!DbgPrintEx` at `0x1402673e1`
- `ntoskrnl!DbgPrintEx` at `0x140267565`
- `ntoskrnl!DbgPrintEx` at `0x14026769f`
- `ntoskrnl!DbgPrintEx` at `0x140267a12`
- `ntoskrnl!DbgPrintEx` at `0x140267b30`
- `ntoskrnl!DbgPrintEx` at `0x140267dd2`
- `ntoskrnl!DbgPrintEx` at `0x140267f06`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14026779d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267849`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14026789c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267c55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14026779d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267849`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14026789c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140267c55`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402677b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402678ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267c71`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267cdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ba170`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402677b8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402678ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267c71`
- `ntoskrnl!ExReleaseResourceLite` at `0x140267cdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ba170`
- `ntoskrnl!ExAcquireFastMutex` at `0x140267d11`
- `ntoskrnl!ExAcquireFastMutex` at `0x140267d11`
- `ntoskrnl!ExReleaseFastMutex` at `0x140267d3c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140267d3c`
- `ntoskrnl!ExRaiseStatus` at `0x140267966`
- `ntoskrnl!ExRaiseStatus` at `0x140267c3a`
- `ntoskrnl!ExRaiseStatus` at `0x140267966`
- `ntoskrnl!ExRaiseStatus` at `0x140267c3a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsSetEndOfLog` at `0x140267381`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsSetEndOfLog` at `0x140267381`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1402674c9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1402674c9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x140267505`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCreateMarshallingArea` at `0x140267505`

## pseudocode

```c
__int64 __fastcall TxfRollforwardUndo(__int64 a1)
{
  int v2; // eax
  __int64 result; // rax
  int MarshallingArea; // ebx
  __int64 v5; // r13
  __int64 v6; // r15
  int v7; // r14d
  unsigned int v8; // r9d
  __int64 v9; // r8
  _QWORD *v10; // r14
  __int64 v11; // rbx
  unsigned int v12; // r9d
  int v13; // r8d
  char v14; // dl
  int KtmResourceManagerObject; // eax
  __int64 v16; // r14
  __int64 v17; // rcx
  __int64 v18; // r13
  __int64 v19; // rax
  __int64 j; // rcx
  char v21; // r15
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // ecx
  int v28; // eax
  unsigned int v29; // r9d
  int v30; // r8d
  unsigned __int64 v31; // rax
  __int64 v32; // rcx
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // eax
  unsigned __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // ecx
  __int64 i; // [rsp+50h] [rbp-328h] BYREF
  CLFS_LSN v41[3]; // [rsp+58h] [rbp-320h] BYREF
  __int64 v42; // [rsp+70h] [rbp-308h] BYREF
  _OWORD v43[2]; // [rsp+78h] [rbp-300h] BYREF
  __int64 v44; // [rsp+98h] [rbp-2E0h]
  _QWORD v45[82]; // [rsp+A0h] [rbp-2D8h] BYREF

  v41[1].ullOffset = a1;
  memset(v43, 0, sizeof(v43));
  v44 = 0;
  memset(v45, 0, sizeof(v45));
  v41[0].ullOffset = CLFS_LSN_NULL_EXT;
  v2 = *(_DWORD *)(a1 + 128);
  if ( (v2 & 4) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0x300511u);
    return 3221225485LL;
  }
  if ( (v2 & 2) != 0 )
  {
    v41[2].ullOffset = (ULONGLONG)v45;
    result = TxfCreateIrpContextForRecovery(a1, (__int64)v45, (__int64)v43);
    if ( (int)result < 0 )
      return result;
    *(_DWORD *)(a1 + 128) |= 4u;
    MarshallingArea = TxfScanForHighestTxfFileId((unsigned int)v45);
    if ( MarshallingArea >= 0 || !TxfRmInForcedRecovery(a1) )
    {
      v5 = 0x408000001LL;
      v6 = 0x800000041LL;
      v7 = 2097219;
LABEL_32:
      if ( MarshallingArea >= 0 )
      {
        if ( (*(_DWORD *)(a1 + 128) & 0x200) != 0 )
        {
          NtfsPurgeFileRecordCache((__int64)v45);
          HIDWORD(v45[0]) |= 0x200u;
          MarshallingArea = ClfsSetEndOfLog(*(PLOG_FILE_OBJECT *)(a1 + 496), (PCLFS_LSN)(a1 + 456));
          HIDWORD(v45[0]) &= ~0x200u;
          if ( MarshallingArea < 0 && TxfRmInForcedRecovery(a1) )
          {
            DbgPrintEx(
              0x82u,
              0,
              "%s:%d -- TxF corruption detected, %s == 0x%x",
              "TxfRecovery.c",
              1370,
              "Status",
              MarshallingArea);
            if ( MarshallingArea == -1073741801
              || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
            {
              ++HIDWORD((*TxfData)[1]);
            }
            else if ( MarshallingArea == -1072037845
                   || MarshallingArea == -1073741202
                   || MarshallingArea == -1073741435
                   || MarshallingArea == -1073741496
                   || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                   && _bittest64(&v6, MarshallingArea + 1073741667)
                   || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                   && _bittest(&v7, MarshallingArea + 1073741811)
                   || MarshallingArea == -2147483626
                   || MarshallingArea == -1072037841 )
            {
              ++LODWORD((*TxfData)[2]);
            }
            MarshallingArea = TxfHandleRecoveryError((__int64)v45, a1, 2u, MarshallingArea, 0);
          }
          if ( MarshallingArea < 0 )
          {
            v8 = 3147104;
            goto LABEL_34;
          }
          NtfsPurgeFileRecordCache((__int64)v45);
          HIDWORD(v45[0]) |= 0x200u;
          ClfsDeleteMarshallingArea(*(PVOID *)(a1 + 512));
          MarshallingArea = ClfsCreateMarshallingArea(
                              *(PLOG_FILE_OBJECT *)(a1 + 496),
                              PoolType,
                              0,
                              0,
                              0x40000u,
                              0xAu,
                              0x14u,
                              (PVOID *)(a1 + 512));
          HIDWORD(v45[0]) &= ~0x200u;
          if ( MarshallingArea < 0 && TxfRmInForcedRecovery(a1) )
          {
            DbgPrintEx(
              0x82u,
              0,
              "%s:%d -- TxF corruption detected, %s == 0x%x",
              "TxfRecovery.c",
              1402,
              "Status",
              MarshallingArea);
            if ( MarshallingArea == -1073741801
              || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
            {
              ++HIDWORD((*TxfData)[1]);
            }
            else if ( MarshallingArea == -1072037845
                   || MarshallingArea == -1073741202
                   || MarshallingArea == -1073741435
                   || MarshallingArea == -1073741496
                   || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                   && _bittest64(&v6, MarshallingArea + 1073741667)
                   || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                   && _bittest(&v7, MarshallingArea + 1073741811)
                   || MarshallingArea == -2147483626
                   || MarshallingArea == -1072037841 )
            {
              ++LODWORD((*TxfData)[2]);
            }
            MarshallingArea = TxfHandleRecoveryError((__int64)v45, a1, 2u, MarshallingArea, 0);
          }
          if ( MarshallingArea < 0 )
          {
            v8 = 3147136;
            goto LABEL_34;
          }
          *(_DWORD *)(a1 + 128) &= ~0x200u;
        }
        MarshallingArea = NtfsFlushUserStream((__int64)v45, *(_QWORD *)(a1 + 280), 0, 0, 0);
        if ( MarshallingArea < 0 && TxfRmInForcedRecovery(a1) )
        {
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "TxfRecovery.c",
            1429,
            "Status",
            MarshallingArea);
          if ( MarshallingArea == -1073741801
            || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( MarshallingArea == -1072037845
                 || MarshallingArea == -1073741202
                 || MarshallingArea == -1073741435
                 || MarshallingArea == -1073741496
                 || (unsigned int)(MarshallingArea + 1073741667) <= 0x23
                 && _bittest64(&v6, MarshallingArea + 1073741667)
                 || (unsigned int)(MarshallingArea + 1073741811) <= 0x15 && _bittest(&v7, MarshallingArea + 1073741811)
                 || MarshallingArea == -2147483626
                 || MarshallingArea == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          MarshallingArea = TxfHandleRecoveryError((__int64)v45, a1, 4u, MarshallingArea, 0);
        }
        if ( MarshallingArea >= 0 )
        {
          v10 = *(_QWORD **)(a1 + 168);
          while ( v10 != (_QWORD *)(a1 + 168) )
          {
            v11 = (__int64)(v10 - 15);
            i = v11;
            v10 = (_QWORD *)*v10;
            if ( (*(_DWORD *)(v11 + 16) & 9) != 1 )
            {
              ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v11 + 24) + 80LL), 1u);
              *(_DWORD *)(v11 + 436) |= 1u;
              ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v11 + 24) + 80LL));
              MarshallingArea = TxfTransMgrAbort((__int64)v45, v11);
              TxfDereferenceTransaction(&i, 0);
              if ( MarshallingArea < 0 && !TxfRmInForcedRecovery(a1) )
              {
                v12 = 3147221;
                v13 = MarshallingArea;
LABEL_103:
                TxfHardErrorFcn((__int64)v45, a1, v13, v12);
                v14 = 0;
                goto LABEL_178;
              }
            }
          }
          TxfProcessTxfVscbDereferencesForEOT(a1);
          KtmResourceManagerObject = TxfCreateKtmResourceManagerObject((__int64)v45, a1);
          MarshallingArea = KtmResourceManagerObject;
          if ( KtmResourceManagerObject < 0 )
          {
            v12 = 3147242;
            v13 = KtmResourceManagerObject;
            goto LABEL_103;
          }
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 160), 1u);
          v14 = 1;
          v16 = *(_QWORD *)(a1 + 152);
          for ( i = v16; ; i = *(_QWORD *)(v17 + 104) )
          {
            v17 = v16;
            if ( !v16 || (*(_DWORD *)(v16 + 16) & 0x2000) == 0 )
              break;
            v16 = *(_QWORD *)(v16 + 104);
          }
          while ( v16 )
          {
            if ( !v14 )
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 160), 1u);
            v18 = v16;
            v42 = v16;
            v19 = *(_QWORD *)(v16 + 104);
            v16 = v19;
            i = v19;
            for ( j = v19; v19 && (*(_DWORD *)(j + 16) & 0x2000) != 0; j = v16 )
            {
              v16 = *(_QWORD *)(j + 104);
              i = v16;
              v19 = v16;
            }
            ExReleaseResourceLite(*(PERESOURCE *)(a1 + 160));
            v21 = 1;
            if ( (*(_DWORD *)(v18 + 16) & 0x4001) != 0 && *(_QWORD *)(v18 + 240) )
            {
              if ( (*(_DWORD *)(v18 + 16) & 0x4001) == 0x4001 )
              {
                v21 = 0;
              }
              else
              {
                if ( !TxfRmInForcedRecovery(a1) )
                {
                  if ( (v45[2] & 0x100000LL) == 0
                    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
                  {
                    McTemplateU0spj_EtwWriteTransfer(
                      v22,
                      (const EVENT_DESCRIPTOR *)txfrecovery_c1622,
                      "TxfRollforwardUndo",
                      a1,
                      a1 + 672);
                  }
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 0xC0190006, 0x30065Eu);
                  MarshallingArea = -1072103418;
                  goto LABEL_134;
                }
                DbgPrintEx(
                  0x82u,
                  0,
                  "%s:%d -- TxF corruption detected, %s == 0x%x",
                  "TxfRecovery.c",
                  1634,
                  "Status",
                  MarshallingArea);
                if ( MarshallingArea == -1073741801
                  || (v23 = (unsigned int)(MarshallingArea + 1073741697), (unsigned int)v23 <= 0x22)
                  && (v24 = 0x408000001LL, _bittest64(&v24, v23)) )
                {
                  ++HIDWORD((*TxfData)[1]);
                }
                else if ( MarshallingArea == -1072037845
                       || MarshallingArea == -1073741202
                       || MarshallingArea == -1073741435
                       || MarshallingArea == -1073741496
                       || (v25 = (unsigned int)(MarshallingArea + 1073741667), (unsigned int)v25 <= 0x23)
                       && (v26 = 0x800000041LL, _bittest64(&v26, v25))
                       || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                       && (v27 = 2097219, _bittest(&v27, MarshallingArea + 1073741811))
                       || MarshallingArea == -2147483626
                       || MarshallingArea == -1072037841 )
                {
                  ++LODWORD((*TxfData)[2]);
                }
                v28 = TxfHandleRecoveryError((__int64)v45, a1, 8u, 0xC0190006, v18);
                MarshallingArea = v28;
                if ( v28 < 0 )
                {
                  v29 = 3147371;
                  v30 = v28;
                  goto LABEL_152;
                }
              }
            }
            if ( *(_QWORD *)(v18 + 88) != v18 + 88 )
            {
              if ( !TxfRmInForcedRecovery(a1) )
              {
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal((__int64)v45, 0xC0190030, 0x300691u);
                ExRaiseStatus(-1072103376);
              }
              DbgPrintEx(
                0x82u,
                0,
                "%s:%d -- TxF corruption detected, %s == 0x%x",
                "TxfRecovery.c",
                1684,
                "Status",
                MarshallingArea);
              if ( MarshallingArea == -1073741801
                || (v31 = (unsigned int)(MarshallingArea + 1073741697), (unsigned int)v31 <= 0x22)
                && (v32 = 0x408000001LL, _bittest64(&v32, v31)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( MarshallingArea == -1072037845
                     || MarshallingArea == -1073741202
                     || MarshallingArea == -1073741435
                     || MarshallingArea == -1073741496
                     || (v33 = (unsigned int)(MarshallingArea + 1073741667), (unsigned int)v33 <= 0x23)
                     && (v34 = 0x800000041LL, _bittest64(&v34, v33))
                     || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                     && (v35 = 2097219, _bittest(&v35, MarshallingArea + 1073741811))
                     || MarshallingArea == -2147483626
                     || MarshallingArea == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              v36 = TxfHandleRecoveryError((__int64)v45, a1, 0x10u, 0xC0190030, v18);
              MarshallingArea = v36;
              if ( v36 < 0 )
              {
                TxfHardErrorFcn((__int64)v45, a1, v36, 0x30069Du);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal((__int64)v45, 0xC0190030, 0x30069Eu);
                ExRaiseStatus(-1072103376);
              }
            }
            if ( v21 )
            {
              ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v18 + 24) + 80LL), 1u);
              *(_DWORD *)(v18 + 436) |= 1u;
              ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v18 + 24) + 80LL));
              MarshallingArea = TxfTransMgrAbort((__int64)v45, v18);
              TxfDereferenceTransaction(&v42, 0);
              if ( MarshallingArea < 0 && !TxfRmInForcedRecovery(a1) )
              {
                v29 = 3147461;
                v30 = MarshallingArea;
LABEL_152:
                TxfHardErrorFcn((__int64)v45, a1, v30, v29);
LABEL_134:
                v14 = 0;
                break;
              }
            }
            v14 = 0;
          }
          v5 = 0x408000001LL;
LABEL_178:
          if ( v14 )
            ExReleaseResourceLite(*(PERESOURCE *)(a1 + 160));
          if ( MarshallingArea >= 0 || TxfRmInForcedRecovery(a1) )
          {
            ExAcquireFastMutex(*(PFAST_MUTEX *)(a1 + 472));
            v41[0].ullOffset = _InterlockedCompareExchange64(
                                 (volatile signed __int64 *)(a1 + 464),
                                 NtfsLarge0.QuadPart,
                                 NtfsLarge0.QuadPart);
            ExReleaseFastMutex(*(PFAST_MUTEX *)(a1 + 472));
            TxfFlushToLsn(a1, v41[0].ullOffset);
            TxfUpdateHighestFlushedLsn(a1, v41);
            MarshallingArea = TxfActOnAllDirtyFilesInRm((__int64)v45, a1, 6, 0, v41, 0);
            if ( MarshallingArea < 0 && TxfRmInForcedRecovery(a1) )
            {
              DbgPrintEx(
                0x82u,
                0,
                "%s:%d -- TxF corruption detected, %s == 0x%x",
                "TxfRecovery.c",
                1783,
                "Status",
                MarshallingArea);
              if ( MarshallingArea == -1073741801
                || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( MarshallingArea == -1072037845
                     || MarshallingArea == -1073741202
                     || MarshallingArea == -1073741435
                     || MarshallingArea == -1073741496
                     || (v37 = (unsigned int)(MarshallingArea + 1073741667), (unsigned int)v37 <= 0x23)
                     && (v38 = 0x800000041LL, _bittest64(&v38, v37))
                     || (unsigned int)(MarshallingArea + 1073741811) <= 0x15
                     && (v39 = 2097219, _bittest(&v39, MarshallingArea + 1073741811))
                     || MarshallingArea == -2147483626
                     || MarshallingArea == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              MarshallingArea = TxfHandleRecoveryError((__int64)v45, a1, 0x20u, MarshallingArea, 0);
            }
            if ( MarshallingArea >= 0 )
            {
              *(_DWORD *)(a1 + 128) &= ~4u;
              goto LABEL_204;
            }
            v8 = 3147517;
          }
          else
          {
            v8 = 3147480;
          }
        }
        else
        {
          v8 = 3147163;
        }
      }
      else
      {
        v8 = 3147078;
      }
LABEL_34:
      TxfHardErrorFcn((__int64)v45, a1, MarshallingArea, v8);
LABEL_204:
      HIDWORD(v45[1]) &= ~0x10000u;
      NtfsCleanupIrpContext((__int64)v45, 0, v9);
      return (unsigned int)MarshallingArea;
    }
    DbgPrintEx(
      0x82u,
      0,
      "%s:%d -- TxF corruption detected, %s == 0x%x",
      "TxfRecovery.c",
      1344,
      "Status",
      MarshallingArea);
    v5 = 0x408000001LL;
    if ( MarshallingArea == -1073741801
      || (unsigned int)(MarshallingArea + 1073741697) <= 0x22 && _bittest64(&v5, MarshallingArea + 1073741697) )
    {
      ++HIDWORD((*TxfData)[1]);
      v6 = 0x800000041LL;
      v7 = 2097219;
      goto LABEL_30;
    }
    if ( MarshallingArea == -1072037845
      || MarshallingArea == -1073741202
      || MarshallingArea == -1073741435
      || MarshallingArea == -1073741496 )
    {
      v6 = 0x800000041LL;
    }
    else
    {
      v6 = 0x800000041LL;
      if ( (unsigned int)(MarshallingArea + 1073741667) > 0x23 || !_bittest64(&v6, MarshallingArea + 1073741667) )
      {
        v7 = 2097219;
        if ( ((unsigned int)(MarshallingArea + 1073741811) > 0x15 || !_bittest(&v7, MarshallingArea + 1073741811))
          && MarshallingArea != -2147483626
          && MarshallingArea != -1072037841 )
        {
          goto LABEL_30;
        }
        goto LABEL_28;
      }
    }
    v7 = 2097219;
LABEL_28:
    ++LODWORD((*TxfData)[2]);
LABEL_30:
    MarshallingArea = TxfHandleRecoveryError((__int64)v45, a1, 1u, MarshallingArea, 0);
    goto LABEL_32;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0x40190034u, 0x30051Au);
  return 1075380276;
}

```

## disassembly

```asm
0x1402670c0  push    rbx
0x1402670c2  push    rdi
0x1402670c3  push    r12
0x1402670c5  push    r13
0x1402670c7  push    r14
0x1402670c9  push    r15
0x1402670cb  sub     rsp, 348h
0x1402670d2  mov     rax, cs:__security_cookie
0x1402670d9  xor     rax, rsp
0x1402670dc  mov     [rsp+378h+var_48], rax
0x1402670e4  mov     rdi, rcx
0x1402670e7  mov     [rsp+378h+var_318], rcx
0x1402670ec  xorps   xmm0, xmm0
0x1402670ef  xor     eax, eax
0x1402670f1  movups  [rsp+378h+var_300], xmm0
0x1402670f6  movups  [rsp+378h+var_2F0], xmm0
0x1402670fe  mov     [rsp+378h+var_2E0], rax
0x140267106  xor     edx, edx; Val
0x140267108  mov     r8d, 290h; Size
0x14026710e  lea     rcx, [rsp+378h+var_2D8]; void *
0x140267116  call    memset
0x14026711b  mov     rax, cs:CLFS_LSN_NULL_EXT
0x140267122  mov     [rsp+378h+var_320], rax
0x140267127  mov     eax, [rdi+80h]
0x14026712d  test    al, 4
0x14026712f  jz      short loc_140267157
0x140267131  mov     al, cs:NtfsStatusDebugFlags
0x140267137  test    al, al
0x140267139  jz      short loc_14026714D
0x14026713b  mov     edx, 0C000000Dh
0x140267140  xor     ecx, ecx
0x140267142  mov     r8d, 300511h
0x140267148  call    NtfsStatusTraceAndDebugInternal
0x14026714d  mov     eax, 0C000000Dh
0x140267152  jmp     loc_140267FE9
0x140267157  test    al, 2
0x140267159  jnz     short loc_140267181
0x14026715b  mov     al, cs:NtfsStatusDebugFlags
0x140267161  test    al, al
0x140267163  jz      short loc_140267177
0x140267165  mov     edx, 40190034h
0x14026716a  xor     ecx, ecx
0x14026716c  mov     r8d, 30051Ah
0x140267172  call    NtfsStatusTraceAndDebugInternal
0x140267177  mov     eax, 40190034h
0x14026717c  jmp     loc_140267FE9
0x140267181  xor     al, al
0x140267183  mov     [rsp+378h+var_338], al
0x140267187  lea     r12, [rsp+378h+var_2D8]
0x14026718f  mov     [rsp+378h+var_310], r12
0x140267194  lea     r8, [rsp+378h+var_300]
0x140267199  lea     rdx, [rsp+378h+var_2D8]
0x1402671a1  mov     rcx, rdi
0x1402671a4  call    TxfCreateIrpContextForRecovery
0x1402671a9  test    eax, eax
0x1402671ab  js      loc_140267FE9
0x1402671b1  or      dword ptr [rdi+80h], 4
0x1402671b8  mov     rdx, rdi
0x1402671bb  lea     rcx, [rsp+378h+var_2D8]
0x1402671c3  call    TxfScanForHighestTxfFileId
0x1402671c8  mov     ebx, eax
0x1402671ca  mov     [rsp+378h+var_334], eax
0x1402671ce  test    eax, eax
0x1402671d0  jns     loc_140267312
0x1402671d6  mov     rcx, rdi
0x1402671d9  call    TxfRmInForcedRecovery
0x1402671de  test    al, al
0x1402671e0  jz      loc_140267312
0x1402671e6  mov     [rsp+378h+cMaxReadBuffers], ebx
0x1402671ea  lea     rax, aStatus; "Status"
0x1402671f1  mov     qword ptr [rsp+378h+cMaxWriteBuffers], rax
0x1402671f6  mov     [rsp+378h+cbMarshallingBuffer], 540h
0x1402671fe  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x140267205  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14026720c  xor     edx, edx; Level
0x14026720e  mov     ecx, 82h; ComponentId
0x140267213  call    cs:__imp_DbgPrintEx
0x14026721a  nop     dword ptr [rax+rax+00h]
0x14026721f  mov     r13, 408000001h
0x140267229  cmp     ebx, 0C0000017h
0x14026722f  jz      loc_1402672CE
0x140267235  lea     eax, [rbx+3FFFFF81h]
0x14026723b  cmp     eax, 22h ; '"'
0x14026723e  ja      short loc_14026724C
0x140267240  cdqe
0x140267242  bt      r13, rax
0x140267246  jb      loc_1402672CE
0x14026724c  cmp     ebx, 0C01A002Bh
0x140267252  jz      short loc_1402672B2
0x140267254  cmp     ebx, 0C000026Eh
0x14026725a  jz      short loc_1402672B2
0x14026725c  cmp     ebx, 0C0000185h
0x140267262  jz      short loc_1402672B2
0x140267264  cmp     ebx, 0C0000148h
0x14026726a  jz      short loc_1402672B2
0x14026726c  lea     eax, [rbx+3FFFFF63h]
0x140267272  mov     r15, 800000041h
0x14026727c  cmp     eax, 23h ; '#'
0x14026727f  ja      short loc_140267289
0x140267281  cdqe
0x140267283  bt      r15, rax
0x140267287  jb      short loc_1402672BC
0x140267289  lea     eax, [rbx+3FFFFFF3h]
0x14026728f  mov     r14d, 200043h
0x140267295  cmp     eax, 15h
0x140267298  ja      short loc_1402672A0
0x14026729a  bt      r14d, eax
0x14026729e  jb      short loc_1402672C2
0x1402672a0  cmp     ebx, 80000016h
0x1402672a6  jz      short loc_1402672C2
0x1402672a8  cmp     ebx, 0C01A002Fh
0x1402672ae  jnz     short loc_1402672E8
0x1402672b0  jmp     short loc_1402672C2
0x1402672b2  mov     r15, 800000041h
0x1402672bc  mov     r14d, 200043h
0x1402672c2  mov     rax, cs:TxfData
0x1402672c9  inc     dword ptr [rax+10h]
0x1402672cc  jmp     short loc_1402672E8
0x1402672ce  mov     rax, cs:TxfData
0x1402672d5  inc     dword ptr [rax+0Ch]
0x1402672d8  mov     r15, 800000041h
0x1402672e2  mov     r14d, 200043h
0x1402672e8  mov     qword ptr [rsp+378h+cbMarshallingBuffer], 0
0x1402672f1  mov     r9d, ebx
0x1402672f4  mov     r8d, 1
0x1402672fa  mov     rdx, rdi
0x1402672fd  lea     rcx, [rsp+378h+var_2D8]
0x140267305  call    TxfHandleRecoveryError
0x14026730a  mov     ebx, eax
0x14026730c  mov     [rsp+378h+var_334], eax
0x140267310  jmp     short loc_14026732C
0x140267312  mov     r13, 408000001h
0x14026731c  mov     r15, 800000041h
0x140267326  mov     r14d, 200043h
0x14026732c  test    ebx, ebx
0x14026732e  jns     short loc_14026734E
0x140267330  mov     r9d, 300546h
0x140267336  lea     rcx, [rsp+378h+var_2D8]
0x14026733e  mov     r8d, ebx
0x140267341  mov     rdx, rdi
0x140267344  call    TxfHardErrorFcn
0x140267349  jmp     loc_140267EA8
0x14026734e  mov     ebx, 200h
0x140267353  test    [rdi+80h], ebx
0x140267359  jz      loc_140267635
0x14026735f  lea     rcx, [rsp+378h+var_2D8]
0x140267367  call    NtfsPurgeFileRecordCache
0x14026736c  or      [rsp+378h+var_2D4], ebx
0x140267373  lea     rdx, [rdi+1C8h]; plsnEnd
0x14026737a  mov     rcx, [rdi+1F0h]; plfoLog
0x140267381  call    cs:__imp_ClfsSetEndOfLog
0x140267388  nop     dword ptr [rax+rax+00h]
0x14026738d  mov     ebx, eax
0x14026738f  mov     [rsp+378h+var_334], eax
0x140267393  btr     [rsp+378h+var_2D4], 9
0x14026739c  test    eax, eax
0x14026739e  jns     loc_14026749A
0x1402673a4  mov     rcx, rdi
0x1402673a7  call    TxfRmInForcedRecovery
0x1402673ac  test    al, al
0x1402673ae  jz      loc_14026749A
0x1402673b4  mov     [rsp+378h+cMaxReadBuffers], ebx
0x1402673b8  lea     rax, aStatus; "Status"
0x1402673bf  mov     qword ptr [rsp+378h+cMaxWriteBuffers], rax
0x1402673c4  mov     [rsp+378h+cbMarshallingBuffer], 55Ah
0x1402673cc  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x1402673d3  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x1402673da  xor     edx, edx; Level
0x1402673dc  mov     ecx, 82h; ComponentId
0x1402673e1  call    cs:__imp_DbgPrintEx
0x1402673e8  nop     dword ptr [rax+rax+00h]
0x1402673ed  cmp     ebx, 0C0000017h
0x1402673f3  jz      short loc_140267468
0x1402673f5  lea     eax, [rbx+3FFFFF81h]
0x1402673fb  cmp     eax, 22h ; '"'
0x1402673fe  ja      short loc_140267408
0x140267400  cdqe
0x140267402  bt      r13, rax
0x140267406  jb      short loc_140267468
0x140267408  cmp     ebx, 0C01A002Bh
0x14026740e  jz      short loc_14026745C
0x140267410  cmp     ebx, 0C000026Eh
0x140267416  jz      short loc_14026745C
0x140267418  cmp     ebx, 0C0000185h
0x14026741e  jz      short loc_14026745C
0x140267420  cmp     ebx, 0C0000148h
0x140267426  jz      short loc_14026745C
0x140267428  lea     eax, [rbx+3FFFFF63h]
0x14026742e  cmp     eax, 23h ; '#'
0x140267431  ja      short loc_14026743B
0x140267433  cdqe
0x140267435  bt      r15, rax
0x140267439  jb      short loc_14026745C
0x14026743b  lea     eax, [rbx+3FFFFFF3h]
0x140267441  cmp     eax, 15h
0x140267444  ja      short loc_14026744C
0x140267446  bt      r14d, eax
0x14026744a  jb      short loc_14026745C
0x14026744c  cmp     ebx, 80000016h
0x140267452  jz      short loc_14026745C
0x140267454  cmp     ebx, 0C01A002Fh
0x14026745a  jnz     short loc_140267472
0x14026745c  mov     rax, cs:TxfData
0x140267463  inc     dword ptr [rax+10h]
0x140267466  jmp     short loc_140267472
0x140267468  mov     rax, cs:TxfData
0x14026746f  inc     dword ptr [rax+0Ch]
0x140267472  mov     qword ptr [rsp+378h+cbMarshallingBuffer], 0
0x14026747b  mov     r9d, ebx
0x14026747e  mov     r8d, 2
0x140267484  mov     rdx, rdi
0x140267487  lea     rcx, [rsp+378h+var_2D8]
0x14026748f  call    TxfHandleRecoveryError
0x140267494  mov     ebx, eax
0x140267496  mov     [rsp+378h+var_334], eax
0x14026749a  lea     rcx, [rsp+378h+var_2D8]
0x1402674a2  test    ebx, ebx
0x1402674a4  jns     short loc_1402674B1
0x1402674a6  mov     r9d, 300560h
0x1402674ac  jmp     loc_14026733E
0x1402674b1  call    NtfsPurgeFileRecordCache
0x1402674b6  bts     [rsp+378h+var_2D4], 9
0x1402674bf  lea     rbx, [rdi+200h]
0x1402674c6  mov     rcx, [rbx]; pvMarshalContext
0x1402674c9  call    cs:__imp_ClfsDeleteMarshallingArea
0x1402674d0  nop     dword ptr [rax+rax+00h]
0x1402674d5  mov     [rsp+378h+ppvMarshalContext], rbx; ppvMarshalContext
0x1402674da  mov     [rsp+378h+cMaxReadBuffers], 14h; cMaxReadBuffers
0x1402674e2  mov     [rsp+378h+cMaxWriteBuffers], 0Ah; cMaxWriteBuffers
0x1402674ea  mov     [rsp+378h+cbMarshallingBuffer], 40000h; cbMarshallingBuffer
0x1402674f2  xor     r9d, r9d; pfnFreeBuffer
0x1402674f5  xor     r8d, r8d; pfnAllocBuffer
0x1402674f8  mov     edx, cs:PoolType; ePoolType
0x1402674fe  mov     rcx, [rdi+1F0h]; plfoLog
0x140267505  call    cs:__imp_ClfsCreateMarshallingArea
0x14026750c  nop     dword ptr [rax+rax+00h]
0x140267511  mov     ebx, eax
0x140267513  mov     [rsp+378h+var_334], eax
0x140267517  btr     [rsp+378h+var_2D4], 9
0x140267520  test    eax, eax
0x140267522  jns     loc_14026761E
0x140267528  mov     rcx, rdi
0x14026752b  call    TxfRmInForcedRecovery
0x140267530  test    al, al
0x140267532  jz      loc_14026761E
0x140267538  mov     [rsp+378h+cMaxReadBuffers], ebx
0x14026753c  lea     rax, aStatus; "Status"
0x140267543  mov     qword ptr [rsp+378h+cMaxWriteBuffers], rax
0x140267548  mov     [rsp+378h+cbMarshallingBuffer], 57Ah
0x140267550  lea     r9, aTxfrecoveryC; "TxfRecovery.c"
0x140267557  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14026755e  xor     edx, edx; Level
0x140267560  mov     ecx, 82h; ComponentId
0x140267565  call    cs:__imp_DbgPrintEx
0x14026756c  nop     dword ptr [rax+rax+00h]
0x140267571  cmp     ebx, 0C0000017h
0x140267577  jz      short loc_1402675EC
0x140267579  lea     eax, [rbx+3FFFFF81h]
0x14026757f  cmp     eax, 22h ; '"'
0x140267582  ja      short loc_14026758C
0x140267584  cdqe
0x140267586  bt      r13, rax
0x14026758a  jb      short loc_1402675EC
0x14026758c  cmp     ebx, 0C01A002Bh
0x140267592  jz      short loc_1402675E0
0x140267594  cmp     ebx, 0C000026Eh
0x14026759a  jz      short loc_1402675E0
0x14026759c  cmp     ebx, 0C0000185h
0x1402675a2  jz      short loc_1402675E0
0x1402675a4  cmp     ebx, 0C0000148h
0x1402675aa  jz      short loc_1402675E0
0x1402675ac  lea     eax, [rbx+3FFFFF63h]
0x1402675b2  cmp     eax, 23h ; '#'
0x1402675b5  ja      short loc_1402675BF
0x1402675b7  cdqe
0x1402675b9  bt      r15, rax
0x1402675bd  jb      short loc_1402675E0
0x1402675bf  lea     eax, [rbx+3FFFFFF3h]
0x1402675c5  cmp     eax, 15h
0x1402675c8  ja      short loc_1402675D0
0x1402675ca  bt      r14d, eax
0x1402675ce  jb      short loc_1402675E0
0x1402675d0  cmp     ebx, 80000016h
0x1402675d6  jz      short loc_1402675E0
0x1402675d8  cmp     ebx, 0C01A002Fh
0x1402675de  jnz     short loc_1402675F6
0x1402675e0  mov     rax, cs:TxfData
0x1402675e7  inc     dword ptr [rax+10h]
0x1402675ea  jmp     short loc_1402675F6
0x1402675ec  mov     rax, cs:TxfData
0x1402675f3  inc     dword ptr [rax+0Ch]
0x1402675f6  mov     qword ptr [rsp+378h+cbMarshallingBuffer], 0
0x1402675ff  mov     r9d, ebx
0x140267602  mov     r8d, 2
0x140267608  mov     rdx, rdi
0x14026760b  lea     rcx, [rsp+378h+var_2D8]
0x140267613  call    TxfHandleRecoveryError
0x140267618  mov     ebx, eax
0x14026761a  mov     [rsp+378h+var_334], eax
0x14026761e  test    ebx, ebx
  ... truncated ...
```
