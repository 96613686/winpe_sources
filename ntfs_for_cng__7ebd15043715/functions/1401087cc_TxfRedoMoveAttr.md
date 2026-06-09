# TxfRedoMoveAttr

- ea: `0x1401087cc`
- end: `0x1401097c8`
- name: `TxfRedoMoveAttr`
- size: `4092`
- prototype: `void __fastcall(__int64, __int64, __int64, CLFS_LSN *)`
- caller_count: `1`
- callee_count: `27`
- tags: `reparse_path, installer_update`

## callers

- `0x140133f30`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d1e0`
- `0x140010be0`
- `0x140012e70`
- `0x140020de0`
- `0x140021590`
- `0x14002c3d0`
- `0x1400410a8`
- `0x140059250`
- `0x1400596c0`
- `0x1400f957c`
- `0x1401087cc`
- `0x14010a8e8`
- `0x1401250b0`
- `0x1401331f4`
- `0x140140380`
- `0x1401620c0`
- `0x1401913d4`
- `0x14019a718`
- `0x1401aab20`
- `0x1401c00e0`
- `0x1401e0660`
- `0x1401fd820`
- `0x14021d6f8`
- `0x140278d84`
- `0x14029130c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14010978e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c5828`
- `ntoskrnl!ObfDereferenceObject` at `0x14010978e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c5828`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140109760`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402c57f8`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140109760`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402c57f8`
- `ntoskrnl!IoSetInformation` at `0x14010955b`
- `ntoskrnl!IoSetInformation` at `0x14010955b`
- `ntoskrnl!DbgPrintEx` at `0x140108a07`
- `ntoskrnl!DbgPrintEx` at `0x140108b49`
- `ntoskrnl!DbgPrintEx` at `0x140108e32`
- `ntoskrnl!DbgPrintEx` at `0x14010940d`
- `ntoskrnl!DbgPrintEx` at `0x140109652`
- `ntoskrnl!DbgPrintEx` at `0x140108a07`
- `ntoskrnl!DbgPrintEx` at `0x140108b49`
- `ntoskrnl!DbgPrintEx` at `0x140108e32`
- `ntoskrnl!DbgPrintEx` at `0x14010940d`
- `ntoskrnl!DbgPrintEx` at `0x140109652`
- `ntoskrnl!ExRaiseStatus` at `0x140108f02`
- `ntoskrnl!ExRaiseStatus` at `0x1401094f9`
- `ntoskrnl!ExRaiseStatus` at `0x140109606`
- `ntoskrnl!ExRaiseStatus` at `0x140108f02`
- `ntoskrnl!ExRaiseStatus` at `0x1401094f9`
- `ntoskrnl!ExRaiseStatus` at `0x140109606`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401089c6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140108b08`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140108f20`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140108f66`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401091d5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140109239`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401089c6`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140108b08`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140108f20`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140108f66`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x1401091d5`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x140109239`

## pseudocode

```c
void __fastcall TxfRedoMoveAttr(__int64 a1, __int64 a2, __int64 a3, CLFS_LSN *a4)
{
  int v5; // ebx
  __int64 v7; // rsi
  __int64 v8; // r13
  char v9; // r15
  char v10; // r14
  unsigned __int64 v11; // rcx
  int v12; // ebx
  const CLFS_LSN *v13; // r14
  __int64 v14; // rsi
  const CLFS_LSN *v15; // r15
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // r8d
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // r8
  int v29; // esi
  __int64 i; // rax
  const CLFS_LSN *v31; // rcx
  __int64 v32; // r8
  __int64 j; // rax
  const CLFS_LSN *v34; // rcx
  int v35; // ecx
  unsigned __int64 v36; // rax
  __int64 v37; // rdx
  unsigned __int64 v38; // rax
  __int64 v39; // rdx
  int v40; // eax
  CLFS_LSN *v41; // rbx
  char v42; // dl
  __int64 Scb; // rbx
  __int64 v44; // rcx
  int v45; // r9d
  __int64 v46; // rcx
  CLFS_LSN *v47; // r12
  __int64 v48; // rcx
  int v49; // eax
  char v50; // al
  __int64 v51; // rcx
  __int64 k; // rax
  __int64 v53; // rcx
  unsigned int m; // eax
  int v55; // eax
  unsigned int v56; // ebx
  unsigned __int64 v57; // rax
  __int64 v58; // rdx
  unsigned __int64 v59; // rax
  __int64 v60; // rdx
  int v61; // eax
  struct _FILE_OBJECT *v62; // rbx
  _QWORD *FsContext; // r14
  __int64 v64; // rdx
  unsigned int v65; // ebx
  __int64 v66; // rax
  __int64 v67; // rdx
  unsigned __int64 v68; // rax
  __int64 v69; // rdx
  unsigned __int64 v70; // rax
  __int64 v71; // rdx
  int v72; // eax
  __int64 v73; // rax
  int v74; // [rsp+20h] [rbp-168h]
  int v75; // [rsp+20h] [rbp-168h]
  int v76; // [rsp+30h] [rbp-158h]
  int v77; // [rsp+30h] [rbp-158h]
  char v78; // [rsp+70h] [rbp-118h]
  char v79; // [rsp+71h] [rbp-117h]
  __int64 v80; // [rsp+78h] [rbp-110h]
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-108h] BYREF
  int v82; // [rsp+88h] [rbp-100h]
  int v83; // [rsp+8Ch] [rbp-FCh]
  int v84; // [rsp+90h] [rbp-F8h]
  unsigned int v85; // [rsp+94h] [rbp-F4h]
  CLFS_LSN *plsn2; // [rsp+98h] [rbp-F0h]
  __int64 FileInformation; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v88; // [rsp+A8h] [rbp-E0h] BYREF
  __int64 v89; // [rsp+B0h] [rbp-D8h]
  __int64 v90; // [rsp+B8h] [rbp-D0h] BYREF
  __int128 v91; // [rsp+C0h] [rbp-C8h] BYREF
  _QWORD v92[2]; // [rsp+D0h] [rbp-B8h] BYREF
  __int128 v93; // [rsp+E0h] [rbp-A8h] BYREF
  int v94[24]; // [rsp+F0h] [rbp-98h] BYREF

  plsn2 = a4;
  v5 = a2;
  v89 = a2;
  v7 = *(_QWORD *)(a2 + 208);
  v80 = v7;
  v92[1] = v7;
  v8 = 0;
  v90 = 0;
  v92[0] = 0;
  FileObject = 0;
  FileInformation = 0;
  v93 = 0;
  v9 = 0;
  v79 = 0;
  memset(v94, 0, 0x58u);
  v10 = 0;
  v78 = 0;
  v91 = 0;
  v88 = 0;
  if ( *(_DWORD *)(a3 + 64) < 0x70u )
    TxfRaiseBoundsCheckFailure();
  if ( (unsigned int)TxfOpenFileCheckId(
                       a1,
                       v5,
                       a3,
                       (int)a3 + 88,
                       0,
                       2,
                       *(_BYTE *)(a3 + 74) & 8,
                       0,
                       (__int64)&v90,
                       (__int64)&FileObject) != -1072103368 )
  {
    v93 = 0;
    *(_QWORD *)&v93 = *(_QWORD *)(a3 + 80);
    v12 = TxfOpenFileCheckId(
            a1,
            v5,
            a3,
            (unsigned int)&v93,
            0,
            2,
            *(_BYTE *)(a3 + 74) & 8,
            0,
            (__int64)v92,
            (__int64)&FileInformation);
    v11 = (unsigned __int64)FileObject;
    if ( FileObject )
    {
      v13 = (const CLFS_LSN *)*((_QWORD *)FileObject->FsContext + 23);
      v11 = (unsigned __int64)FileObject;
    }
    else
    {
      v13 = 0;
    }
    v14 = FileInformation;
    if ( FileInformation )
      v15 = *(const CLFS_LSN **)(*(_QWORD *)(FileInformation + 24) + 184LL);
    else
      v15 = 0;
    if ( v11 )
    {
      if ( !FileInformation )
      {
        if ( ClfsLsnLess(v13 + 30, plsn2) )
        {
          DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19531, "Status", v12);
          if ( v12 == -1073741801
            || (v16 = (unsigned int)(v12 + 1073741697), (unsigned int)v16 <= 0x22)
            && (v17 = 0x408000001LL, _bittest64(&v17, v16)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( v12 == -1072037845
                 || v12 == -1073741202
                 || v12 == -1073741435
                 || v12 == -1073741496
                 || (v18 = (unsigned int)(v12 + 1073741667), (unsigned int)v18 <= 0x23)
                 && (v19 = 0x800000041LL, _bittest64(&v19, v18))
                 || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
                 && (v20 = 2097219, _bittest(&v20, v11))
                 || v12 == -2147483626
                 || v12 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          if ( !NtfsStatusDebugFlags )
            goto LABEL_197;
          v21 = 3230796;
          goto LABEL_30;
        }
        v11 = (unsigned __int64)FileObject;
      }
      if ( v11 )
        goto LABEL_54;
    }
    if ( v14 )
    {
      if ( ClfsLsnLess(v15 + 30, plsn2) )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19545, "Status", v12);
        if ( v12 == -1073741801
          || (v22 = (unsigned int)(v12 + 1073741697), (unsigned int)v22 <= 0x22)
          && (v23 = 0x408000001LL, _bittest64(&v23, v22)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( v12 == -1072037845
               || v12 == -1073741202
               || v12 == -1073741435
               || v12 == -1073741496
               || (v24 = (unsigned int)(v12 + 1073741667), (unsigned int)v24 <= 0x23)
               && (v25 = 0x800000041LL, _bittest64(&v25, v24))
               || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
               && (v26 = 2097219, _bittest(&v26, v11))
               || v12 == -2147483626
               || v12 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_197;
        v21 = 3230810;
        goto LABEL_30;
      }
      v11 = (unsigned __int64)FileObject;
    }
    if ( v11 )
    {
LABEL_54:
      if ( v14 )
      {
        WORD1(v91) = 2 * *(_WORD *)(a3 + 104);
        LOWORD(v91) = WORD1(v91);
        if ( WORD1(v91) )
          v27 = a3 + *(unsigned __int16 *)(a3 + 106);
        else
          v27 = 0;
        *((_QWORD *)&v91 + 1) = v27;
        NtfsAcquireSharedVcb(a1, *(_QWORD *)(v80 + 16), 0);
        v29 = 1;
        v79 = 1;
        if ( (*(_DWORD *)(*(_QWORD *)(v80 + 16) + 4LL) & 1) == 0 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC000026E, 0x314C88u);
          NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 3230856);
        }
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( !v13[14].ullOffset )
          {
            NtfsAcquireExclusiveFcb(a1, (__int64)v13, 0, 0);
            NtfsAddPagingIoToFcb(a1, v13, 0);
            NtfsReleaseFcbEx(a1, (__int64)v13, 0);
          }
          LOBYTE(v28) = 1;
          if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v13, v28) )
          {
            v82 = 0;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v82 = i;
              if ( (unsigned int)i >= 2 )
                break;
              v31 = *(const CLFS_LSN **)(a1 + 8 * i + 48);
              if ( !v31 || v31 == v13 )
              {
                *(_QWORD *)(a1 + 8 * i + 48) = v13;
                break;
              }
            }
          }
        }
        NtfsAcquireExclusiveFcb(a1, (__int64)v13, 0, 0);
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( !v15[14].ullOffset )
          {
            NtfsAcquireExclusiveFcb(a1, (__int64)v15, 0, 0);
            NtfsAddPagingIoToFcb(a1, v15, 0);
            NtfsReleaseFcbEx(a1, (__int64)v15, 0);
          }
          LOBYTE(v32) = 1;
          NtfsAcquirePagingResourceExclusive(0, v15, v32);
          v83 = 0;
          for ( j = 0; ; j = (unsigned int)(j + 1) )
          {
            v83 = j;
            if ( (unsigned int)j >= 2 )
              break;
            v34 = *(const CLFS_LSN **)(a1 + 8 * j + 48);
            if ( !v34 || v34 == v15 )
            {
              *(_QWORD *)(a1 + 8 * j + 48) = v15;
              break;
            }
          }
        }
        NtfsAcquireExclusiveFcb(a1, (__int64)v15, 0, 0);
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( ClfsLsnLess(v13 + 30, plsn2) )
          {
            memset(v94, 0, 0x58u);
            v78 = 1;
            LOBYTE(v76) = 0;
            v42 = NtfsLookupInFileRecord(a1, v15, &v15[1], *(unsigned int *)(a3 + 108), &v91, 0, v76, 0, 0, v94);
            if ( v42 )
            {
              if ( *(_BYTE *)(*(_QWORD *)v94 + 8LL) )
              {
                v42 &= -(*(_QWORD *)(*(_QWORD *)v94 + 40LL) != 0);
              }
              else if ( !*(_DWORD *)(*(_QWORD *)v94 + 16LL) )
              {
                v42 = 0;
              }
            }
            if ( !v42 )
            {
              Scb = NtfsCreateScb(a1, (_DWORD)v13, *(_DWORD *)(a3 + 108), (unsigned int)&v91, 0, 0, 0);
              NtfsCleanupAttributeContext(v44, v94);
              memset(v94, 0, 0x58u);
              LOBYTE(v77) = 0;
              if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                       a1,
                                       *(_QWORD *)(Scb + 184),
                                       *(_QWORD *)(Scb + 184) + 8LL,
                                       *(unsigned int *)(Scb + 256),
                                       Scb + 264,
                                       0,
                                       v77,
                                       0,
                                       0,
                                       v94)
                && (*(_DWORD *)(Scb + 512) & 4) == 0 )
              {
                NtfsAttachCorruption_BadOrOrphanFRS(
                  a1,
                  2,
                  3231004,
                  v45,
                  *(_QWORD *)(Scb + 184) + 8LL,
                  *(_QWORD *)(Scb + 184),
                  0);
                NtfsAttachRepairInfoPriv(a1, 512, 0, (struct _LIST_ENTRY *)0xA900314D1CLL);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0x314D1Cu);
                NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(Scb + 184) + 8, *(_QWORD *)(Scb + 184), 3231004);
              }
              NtfsFlushFcb(a1, (_DWORD)v13);
              v46 = *(_QWORD *)(Scb + 528);
              if ( v46 )
                *(_DWORD *)(v46 + 24) = *(_DWORD *)(v46 + 24);
              TxfPrepareToMoveAttribute(a1, (int)v13, (int)v15, v94, 0);
              TxfMoveAttrInternal(a1, (_DWORD)v13, v94, 0, (__int64)&v88);
              NtfsConditionallyFixupQuota(a1, (__int64)v15);
              NtfsConditionallyFixupQuota(a1, (__int64)v13);
              v47 = plsn2;
              v48 = (unsigned __int64)v47 & -(__int64)(ClfsLsnLess(v15 + 32, plsn2) != 0);
              if ( !v47 || (v49 = 1, (v15->offset.cidContainer & 0x100000) != 0) )
                v49 = 0;
              TxfUpdateTxfDataAttributeMembers(a1, (int)v15, v74, 0, v49, (__int64)v47, v48, 0, 0, 0, 0);
              v50 = -ClfsLsnLess(v13 + 32, v47);
              if ( !v47 || (v13->offset.cidContainer & 0x100000) != 0 )
                v29 = 0;
              TxfUpdateTxfDataAttributeMembers(
                a1,
                (int)v13,
                v75,
                0,
                v29,
                (__int64)v47,
                (unsigned __int64)v47 & -(__int64)(v50 != 0),
                0,
                0,
                0,
                0);
              NtfsCheckpointCurrentTransaction(a1);
              v11 = *(_QWORD *)(Scb + 528);
              v7 = v80;
              if ( v11 )
              {
                *(_QWORD *)(v11 + 96) = *(_QWORD *)(Scb + 40);
                *(_QWORD *)(*(_QWORD *)(Scb + 528) + 104LL) = *(_QWORD *)(Scb + 32);
                v11 = *(_QWORD *)(Scb + 528);
                *(_DWORD *)(v11 + 24) = *(_DWORD *)(v11 + 24);
              }
              v8 = v88;
              v9 = 1;
              goto LABEL_199;
            }
            FileInformation = 0;
            NtfsReleaseFcbEx(a1, (__int64)v13, 0);
            NtfsReleasePagingResourcePriv(v51, (__int64)v13);
            if ( a1 )
            {
              v84 = 0;
              for ( k = 0; ; k = (unsigned int)(k + 1) )
              {
                v84 = k;
                if ( (unsigned int)k >= 2 )
                  break;
                if ( *(const CLFS_LSN **)(a1 + 8 * k + 48) == v13 )
                  *(_QWORD *)(a1 + 8 * k + 48) = 0;
              }
            }
            NtfsReleaseFcbEx(a1, (__int64)v15, 0);
            if ( a1 )
            {
              v85 = 0;
              for ( m = 0; ; ++m )
              {
                v85 = m;
                if ( m >= 2 )
                  break;
                v53 = m;
                if ( *(const CLFS_LSN **)(a1 + 8LL * m + 48) == v15 )
                  *(_QWORD *)(a1 + 8LL * m + 48) = 0;
              }
            }
            NtfsReleasePagingResourcePriv(v53, (__int64)v15);
            NtfsReleaseVcb(a1, *(_QWORD *)(v80 + 16));
            v9 = 0;
            v55 = TxfOpenFileCheckId(
                    a1,
                    v89,
                    a3,
                    (int)a3 + 88,
                    a3 + 104,
                    2,
                    *(_BYTE *)(a3 + 74) & 8,
                    0,
                    (__int64)&v90,
                    (__int64)&FileObject);
            v56 = v55;
            if ( v55 < 0 )
            {
              DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19878, "Status", v55);
              if ( v56 == -1073741801
                || (v57 = v56 + 1073741697, (unsigned int)v57 <= 0x22) && (v58 = 0x408000001LL, _bittest64(&v58, v57)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( v56 == -1072037845
                     || v56 == -1073741202
                     || v56 == -1073741435
                     || v56 == -1073741496
                     || (v59 = v56 + 1073741667, (unsigned int)v59 <= 0x23)
                     && (v60 = 0x800000041LL, _bittest64(&v60, v59))
                     || v56 + 1073741811 <= 0x15 && (v61 = 2097219, _bittest(&v61, v56 + 1073741811))
                     || v56 == -2147483626
                     || v56 == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              if ( NtfsStatusDebugFlags
                && v56 < 0xFFFFFFED
                && v56 != -1073741802
                && v56 != -1073741807
                && v56 + 2147483643 > 1
                && v56 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, v56, 0x314DA7u);
              }
              ExRaiseStatus(v56);
            }
            v62 = FileObject;
            FsContext = FileObject->FsContext;
            if ( FsContext[4] )
            {
              FileInformation = 0;
              v64 = FsContext[66];
              if ( v64 )
                *(_DWORD *)(v64 + 24) = *(_DWORD *)(v64 + 24);
              NtfsPurgeFileRecordCache(a1);
              *(_DWORD *)(a1 + 4) |= 0x200u;
              v65 = IoSetInformation(v62, FileEndOfFileInformation, 8u, &FileInformation);
              *(_DWORD *)(a1 + 4) &= ~0x200u;
              v66 = FsContext[66];
              if ( v66 )
              {
                *(_QWORD *)(v66 + 96) = FsContext[5];
                *(_QWORD *)(FsContext[66] + 104LL) = FsContext[4];
                v67 = FsContext[66];
                v11 = *(unsigned int *)(v67 + 24);
                *(_DWORD *)(v67 + 24) = v11;
              }
              if ( v65 )
              {
                if ( NtfsStatusDebugFlags
                  && (((v65 - 294) & 0xFFFFFFFA) != 0 || v65 == 295)
                  && v65 < 0xFFFFFFED
                  && v65 != -1073741608
                  && v65 != -1073741802
                  && v65 != -1073741807
                  && v65 + 2147483643 > 1
                  && v65 != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(a1, v65, 0x314DDAu);
                }
                ExRaiseStatus(v65);
              }
            }
LABEL_198:
            v7 = v80;
LABEL_199:
            v10 = v78;
            goto LABEL_200;
          }
        }
        else
        {
          if ( *(_DWORD *)(a3 + 108) != 192 )
          {
            DbgPrintEx(
              0x82u,
              0,
              "%s:%d -- TxF corruption detected, %s == 0x%x",
              "txftrans.c",
              19967,
              "Status",
              *(_DWORD *)(a3 + 108));
            v35 = *(_DWORD *)(a3 + 108);
            if ( v35 == -1073741801
              || (v36 = (unsigned int)(v35 + 1073741697), (unsigned int)v36 <= 0x22)
              && (v37 = 0x408000001LL, _bittest64(&v37, v36)) )
            {
              ++HIDWORD((*TxfData)[1]);
            }
            else if ( v35 == -1072037845
                   || v35 == -1073741202
                   || v35 == -1073741435
                   || v35 == -1073741496
                   || (v38 = (unsigned int)(v35 + 1073741667), (unsigned int)v38 <= 0x23)
                   && (v39 = 0x800000041LL, _bittest64(&v39, v38))
                   || (unsigned int)(v35 + 1073741811) <= 0x15 && (v40 = 2097219, _bittest(&v40, v35 + 1073741811))
                   || v35 == -2147483626
                   || v35 == -1072037841 )
            {
              ++LODWORD((*TxfData)[2]);
            }
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 0xC0190030, 0x314E00u);
            ExRaiseStatus(-1072103376);
          }
          v41 = plsn2;
          if ( ClfsLsnLess(v13 + 30, plsn2) )
            TxfRedoUndoMoveReparsePoint(a1, v41->ullOffset);
        }
LABEL_197:
        v9 = v79;
        goto LABEL_198;
      }
    }
    if ( (*(_DWORD *)(v89 + 16) & 0x10) == 0 )
      goto LABEL_197;
    DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19562, "Status", v12);
    if ( v12 == -1073741801
      || (v68 = (unsigned int)(v12 + 1073741697), (unsigned int)v68 <= 0x22)
      && (v69 = 0x408000001LL, _bittest64(&v69, v68)) )
    {
      ++HIDWORD((*TxfData)[1]);
    }
    else if ( v12 == -1072037845
           || v12 == -1073741202
           || v12 == -1073741435
           || v12 == -1073741496
           || (v70 = (unsigned int)(v12 + 1073741667), (unsigned int)v70 <= 0x23)
           && (v71 = 0x800000041LL, _bittest64(&v71, v70))
           || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
           && (v72 = 2097219, _bittest(&v72, v11))
           || v12 == -2147483626
           || v12 == -1072037841 )
    {
      ++LODWORD((*TxfData)[2]);
    }
    if ( !NtfsStatusDebugFlags )
      goto LABEL_197;
    v21 = 3230827;
LABEL_30:
    NtfsStatusTraceAndDebugInternal(0, 0xC0000102, v21);
    goto LABEL_197;
  }
LABEL_200:
  if ( v9 )
    NtfsReleaseVcb(a1, *(_QWORD *)(v7 + 16));
  if ( v10 )
    NtfsCleanupAttributeContext(v11, v94);
  if ( v8 )
  {
    if ( *(_QWORD *)(v8 + 48) )
      CcUninitializeCacheMap((PFILE_OBJECT)v8, 0, 0);
    v73 = *(_QWORD *)(v8 + 24);
    if ( v73 )
    {
      if ( (*(_DWORD *)(v73 + 200) & 0x4000) == 0 )
      {
        *(_DWORD *)(v8 + 88) = 0;
        *(_QWORD *)(v8 + 96) = 0;
      }
    }
    ObfDereferenceObject((PVOID)v8);
  }
}

```

## disassembly

```asm
0x1401087cc  mov     r11, rsp
0x1401087cf  mov     [r11+10h], rbx
0x1401087d3  mov     [r11+18h], rsi
0x1401087d7  mov     [r11+8], rcx
0x1401087db  push    rdi
0x1401087dc  push    r12
0x1401087de  push    r13
0x1401087e0  push    r14
0x1401087e2  push    r15
0x1401087e4  sub     rsp, 160h
0x1401087eb  mov     rax, cs:__security_cookie
0x1401087f2  xor     rax, rsp
0x1401087f5  mov     [rsp+188h+var_38], rax
0x1401087fd  mov     [rsp+188h+plsn2], r9
0x140108805  mov     r12, r8
0x140108808  mov     rbx, rdx
0x14010880b  mov     [rsp+188h+var_D8], rdx
0x140108813  mov     rdi, rcx
0x140108816  mov     rsi, [rdx+0D0h]
0x14010881d  mov     [rsp+188h+var_110], rsi
0x140108822  mov     [rsp+188h+var_B0], rsi
0x14010882a  xor     r13d, r13d
0x14010882d  mov     [r11-0D0h], r13
0x140108834  mov     [r11-0B8h], r13
0x14010883b  mov     [r11-108h], r13
0x140108842  mov     [r11-0E8h], r13
0x140108849  xorps   xmm0, xmm0
0x14010884c  movups  [rsp+188h+var_A8], xmm0
0x140108854  mov     r15b, r13b
0x140108857  mov     [rsp+188h+var_117], r13b
0x14010885c  xor     edx, edx; Val
0x14010885e  lea     r8d, [r13+58h]; Size
0x140108862  lea     rcx, [r11-98h]; void *
0x140108869  call    memset
0x14010886e  mov     r14b, r13b
0x140108871  mov     [rsp+188h+var_118], r13b
0x140108876  xorps   xmm0, xmm0
0x140108879  movups  [rsp+188h+var_C8], xmm0
0x140108881  mov     [rsp+188h+var_E0], r13
0x140108889  cmp     dword ptr [r12+40h], 70h ; 'p'
0x14010888f  jnb     short loc_140108897
0x140108891  call    TxfRaiseBoundsCheckFailure
0x140108897  lea     r9, [r12+58h]
0x14010889c  mov     al, [r12+4Ah]
0x1401088a1  and     al, 8
0x1401088a3  lea     rdx, [rsp+188h+FileObject]
0x1401088ab  mov     [rsp+188h+var_140], rdx
0x1401088b0  lea     rdx, [rsp+188h+var_D0]
0x1401088b8  mov     [rsp+188h+var_148], rdx
0x1401088bd  mov     [rsp+188h+var_150], 0
0x1401088c6  mov     byte ptr [rsp+188h+var_158], al
0x1401088ca  mov     [rsp+188h+var_160], 2
0x1401088d2  mov     qword ptr [rsp+188h+var_168], 0
0x1401088db  mov     r8, r12
0x1401088de  mov     rdx, rbx
0x1401088e1  mov     rcx, rdi
0x1401088e4  call    TxfOpenFileCheckId
0x1401088e9  cmp     eax, 0C0190038h
0x1401088ee  jz      loc_140109729
0x1401088f4  xorps   xmm0, xmm0
0x1401088f7  movups  [rsp+188h+var_A8], xmm0
0x1401088ff  mov     rax, [r12+50h]
0x140108904  mov     qword ptr [rsp+188h+var_A8], rax
0x14010890c  mov     al, [r12+4Ah]
0x140108911  and     al, 8
0x140108913  lea     rcx, [rsp+188h+FileInformation]
0x14010891b  mov     [rsp+188h+var_140], rcx
0x140108920  lea     rcx, [rsp+188h+var_B8]
0x140108928  mov     [rsp+188h+var_148], rcx
0x14010892d  mov     [rsp+188h+var_150], 0
0x140108936  mov     byte ptr [rsp+188h+var_158], al
0x14010893a  mov     [rsp+188h+var_160], 2
0x140108942  mov     qword ptr [rsp+188h+var_168], 0
0x14010894b  lea     r9, [rsp+188h+var_A8]
0x140108953  mov     r8, r12
0x140108956  mov     rdx, rbx
0x140108959  mov     rcx, rdi
0x14010895c  call    TxfOpenFileCheckId
0x140108961  mov     ebx, eax
0x140108963  mov     rcx, [rsp+188h+FileObject]
0x14010896b  test    rcx, rcx
0x14010896e  jz      short loc_140108985
0x140108970  mov     rcx, [rcx+18h]
0x140108974  mov     r14, [rcx+0B8h]
0x14010897b  mov     rcx, [rsp+188h+FileObject]
0x140108983  jmp     short loc_140108988
0x140108985  xor     r14d, r14d
0x140108988  mov     rsi, [rsp+188h+FileInformation]
0x140108990  test    rsi, rsi
0x140108993  jz      short loc_1401089A2
0x140108995  mov     rax, [rsi+18h]
0x140108999  mov     r15, [rax+0B8h]
0x1401089a0  jmp     short loc_1401089A5
0x1401089a2  xor     r15d, r15d
0x1401089a5  test    rcx, rcx
0x1401089a8  jz      loc_140108AF0
0x1401089ae  test    rsi, rsi
0x1401089b1  jnz     loc_140108AE7
0x1401089b7  lea     rcx, [r14+0F0h]; plsn1
0x1401089be  mov     rdx, [rsp+188h+plsn2]; plsn2
0x1401089c6  call    cs:__imp_ClfsLsnLess
0x1401089cd  nop     dword ptr [rax+rax+00h]
0x1401089d2  test    al, al
0x1401089d4  jz      loc_140108ADF
0x1401089da  mov     [rsp+188h+var_158], ebx
0x1401089de  lea     rax, aStatus; "Status"
0x1401089e5  mov     qword ptr [rsp+188h+var_160], rax
0x1401089ea  mov     [rsp+188h+var_168], 4C4Bh
0x1401089f2  lea     r9, aTxftransC; "txftrans.c"
0x1401089f9  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x140108a00  xor     edx, edx; Level
0x140108a02  mov     ecx, 82h; ComponentId
0x140108a07  call    cs:__imp_DbgPrintEx
0x140108a0e  nop     dword ptr [rax+rax+00h]
0x140108a13  cmp     ebx, 0C0000017h
0x140108a19  jz      loc_140108AAB
0x140108a1f  lea     eax, [rbx+3FFFFF81h]
0x140108a25  cmp     eax, 22h ; '"'
0x140108a28  ja      short loc_140108A3A
0x140108a2a  mov     rdx, 408000001h
0x140108a34  bt      rdx, rax
0x140108a38  jb      short loc_140108AAB
0x140108a3a  cmp     ebx, 0C01A002Bh
0x140108a40  jz      short loc_140108A9A
0x140108a42  cmp     ebx, 0C000026Eh
0x140108a48  jz      short loc_140108A9A
0x140108a4a  cmp     ebx, 0C0000185h
0x140108a50  jz      short loc_140108A9A
0x140108a52  cmp     ebx, 0C0000148h
0x140108a58  jz      short loc_140108A9A
0x140108a5a  lea     eax, [rbx+3FFFFF63h]
0x140108a60  cmp     eax, 23h ; '#'
0x140108a63  ja      short loc_140108A75
0x140108a65  mov     rdx, 800000041h
0x140108a6f  bt      rdx, rax
0x140108a73  jb      short loc_140108A9A
0x140108a75  lea     ecx, [rbx+3FFFFFF3h]
0x140108a7b  cmp     ecx, 15h
0x140108a7e  ja      short loc_140108A8A
0x140108a80  mov     eax, 200043h
0x140108a85  bt      eax, ecx
0x140108a88  jb      short loc_140108A9A
0x140108a8a  cmp     ebx, 80000016h
0x140108a90  jz      short loc_140108A9A
0x140108a92  cmp     ebx, 0C01A002Fh
0x140108a98  jnz     short loc_140108ABA
0x140108a9a  mov     rax, cs:TxfData
0x140108aa1  mov     esi, 1
0x140108aa6  add     [rax+10h], esi
0x140108aa9  jmp     short loc_140108ABA
0x140108aab  mov     rax, cs:TxfData
0x140108ab2  mov     esi, 1
0x140108ab7  add     [rax+0Ch], esi
0x140108aba  mov     al, cs:NtfsStatusDebugFlags
0x140108ac0  test    al, al
0x140108ac2  jz      loc_14010971A
0x140108ac8  mov     r8d, 314C4Ch
0x140108ace  mov     edx, 0C0000102h
0x140108ad3  xor     ecx, ecx
0x140108ad5  call    NtfsStatusTraceAndDebugInternal
0x140108ada  jmp     loc_14010971A
0x140108adf  mov     rcx, [rsp+188h+FileObject]
0x140108ae7  test    rcx, rcx
0x140108aea  jnz     loc_140108C26
0x140108af0  test    rsi, rsi
0x140108af3  jz      loc_140108C1D
0x140108af9  lea     rcx, [r15+0F0h]; plsn1
0x140108b00  mov     rdx, [rsp+188h+plsn2]; plsn2
0x140108b08  call    cs:__imp_ClfsLsnLess
0x140108b0f  nop     dword ptr [rax+rax+00h]
0x140108b14  test    al, al
0x140108b16  jz      loc_140108C15
0x140108b1c  mov     [rsp+188h+var_158], ebx
0x140108b20  lea     rax, aStatus; "Status"
0x140108b27  mov     qword ptr [rsp+188h+var_160], rax
0x140108b2c  mov     [rsp+188h+var_168], 4C59h
0x140108b34  lea     r9, aTxftransC; "txftrans.c"
0x140108b3b  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x140108b42  xor     edx, edx; Level
0x140108b44  mov     ecx, 82h; ComponentId
0x140108b49  call    cs:__imp_DbgPrintEx
0x140108b50  nop     dword ptr [rax+rax+00h]
0x140108b55  cmp     ebx, 0C0000017h
0x140108b5b  jz      loc_140108BED
0x140108b61  lea     eax, [rbx+3FFFFF81h]
0x140108b67  cmp     eax, 22h ; '"'
0x140108b6a  ja      short loc_140108B7C
0x140108b6c  mov     rdx, 408000001h
0x140108b76  bt      rdx, rax
0x140108b7a  jb      short loc_140108BED
0x140108b7c  cmp     ebx, 0C01A002Bh
0x140108b82  jz      short loc_140108BDC
0x140108b84  cmp     ebx, 0C000026Eh
0x140108b8a  jz      short loc_140108BDC
0x140108b8c  cmp     ebx, 0C0000185h
0x140108b92  jz      short loc_140108BDC
0x140108b94  cmp     ebx, 0C0000148h
0x140108b9a  jz      short loc_140108BDC
0x140108b9c  lea     eax, [rbx+3FFFFF63h]
0x140108ba2  cmp     eax, 23h ; '#'
0x140108ba5  ja      short loc_140108BB7
0x140108ba7  mov     rdx, 800000041h
0x140108bb1  bt      rdx, rax
0x140108bb5  jb      short loc_140108BDC
0x140108bb7  lea     ecx, [rbx+3FFFFFF3h]
0x140108bbd  cmp     ecx, 15h
0x140108bc0  ja      short loc_140108BCC
0x140108bc2  mov     eax, 200043h
0x140108bc7  bt      eax, ecx
0x140108bca  jb      short loc_140108BDC
0x140108bcc  cmp     ebx, 80000016h
0x140108bd2  jz      short loc_140108BDC
0x140108bd4  cmp     ebx, 0C01A002Fh
0x140108bda  jnz     short loc_140108BFC
0x140108bdc  mov     rax, cs:TxfData
0x140108be3  mov     esi, 1
0x140108be8  add     [rax+10h], esi
0x140108beb  jmp     short loc_140108BFC
0x140108bed  mov     rax, cs:TxfData
0x140108bf4  mov     esi, 1
0x140108bf9  add     [rax+0Ch], esi
0x140108bfc  mov     al, cs:NtfsStatusDebugFlags
0x140108c02  test    al, al
0x140108c04  jz      loc_14010971A
0x140108c0a  mov     r8d, 314C5Ah
0x140108c10  jmp     loc_140108ACE
0x140108c15  mov     rcx, [rsp+188h+FileObject]
0x140108c1d  test    rcx, rcx
0x140108c20  jz      loc_140109612
0x140108c26  test    rsi, rsi
0x140108c29  jz      loc_140109612
0x140108c2f  lea     rbx, [r12+68h]
0x140108c34  movzx   eax, word ptr [rbx]
0x140108c37  add     ax, ax
0x140108c3a  mov     word ptr [rsp+188h+var_C8+2], ax
0x140108c42  mov     word ptr [rsp+188h+var_C8], ax
0x140108c4a  jz      short loc_140108C57
0x140108c4c  movzx   eax, word ptr [r12+6Ah]
0x140108c52  add     rax, r12
0x140108c55  jmp     short loc_140108C59
0x140108c57  xor     eax, eax
0x140108c59  mov     qword ptr [rsp+188h+var_C8+8], rax
0x140108c61  xor     r8d, r8d
0x140108c64  mov     rdx, [rsp+188h+var_110]
0x140108c69  mov     rdx, [rdx+10h]
0x140108c6d  mov     rcx, rdi
0x140108c70  call    NtfsAcquireSharedVcb
0x140108c75  mov     esi, 1
0x140108c7a  mov     [rsp+188h+var_117], sil
0x140108c7f  mov     rax, [rsp+188h+var_110]
0x140108c84  mov     rax, [rax+10h]
0x140108c88  mov     ecx, [rax+4]
0x140108c8b  test    sil, cl
0x140108c8e  jnz     short loc_140108CC9
0x140108c90  mov     al, cs:NtfsStatusDebugFlags
0x140108c96  test    al, al
0x140108c98  jz      short loc_140108CAD
0x140108c9a  mov     edx, 0C000026Eh
0x140108c9f  mov     r8d, 314C88h
0x140108ca5  mov     rcx, rdi
0x140108ca8  call    NtfsStatusTraceAndDebugInternal
0x140108cad  mov     qword ptr [rsp+188h+var_168], 314C88h
0x140108cb6  xor     r9d, r9d
0x140108cb9  xor     r8d, r8d
0x140108cbc  mov     edx, 0C000026Eh
0x140108cc1  mov     rcx, rdi
0x140108cc4  call    NtfsRaiseStatusInternal
0x140108cc9  cmp     dword ptr [r12+6Ch], 80h
0x140108cd2  jnz     short loc_140108D4B
0x140108cd4  cmp     qword ptr [r14+70h], 0
0x140108cd9  jnz     short loc_140108D08
0x140108cdb  xor     r9d, r9d
0x140108cde  xor     r8d, r8d
0x140108ce1  mov     rdx, r14
0x140108ce4  mov     rcx, rdi
0x140108ce7  call    NtfsAcquireExclusiveFcb
0x140108cec  xor     r8d, r8d
0x140108cef  mov     rdx, r14
0x140108cf2  mov     rcx, rdi
0x140108cf5  call    NtfsAddPagingIoToFcb
0x140108cfa  xor     r8d, r8d
0x140108cfd  mov     rdx, r14
0x140108d00  mov     rcx, rdi
0x140108d03  call    NtfsReleaseFcbEx
0x140108d08  mov     r8b, sil
0x140108d0b  mov     rdx, r14
0x140108d0e  mov     rcx, rdi
0x140108d11  call    NtfsAcquirePagingResourceExclusive
0x140108d16  test    al, al
0x140108d18  jz      short loc_140108D4B
0x140108d1a  mov     [rsp+188h+var_100], 0
0x140108d25  xor     eax, eax
0x140108d27  mov     [rsp+188h+var_100], eax
0x140108d2e  cmp     eax, 2
0x140108d31  jnb     short loc_140108D4B
0x140108d33  mov     rcx, [rdi+rax*8+30h]
0x140108d38  test    rcx, rcx
0x140108d3b  jz      short loc_140108D46
0x140108d3d  cmp     rcx, r14
0x140108d40  jz      short loc_140108D46
  ... truncated ...
```
