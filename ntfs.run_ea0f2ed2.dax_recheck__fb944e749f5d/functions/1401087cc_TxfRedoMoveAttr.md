# TxfRedoMoveAttr

- ea: `0x1401087cc`
- end: `0x1401097c8`
- name: `TxfRedoMoveAttr`
- size: `4092`
- prototype: ``
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
char __fastcall TxfRedoMoveAttr(__int64 a1, __int64 a2, __int64 a3, CLFS_LSN *a4)
{
  __int64 v7; // rsi
  __int64 v8; // r13
  char v9; // r15
  char v10; // r14
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  int v13; // ebx
  const CLFS_LSN *v14; // r14
  __int64 v15; // rsi
  const CLFS_LSN *v16; // r15
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r8
  unsigned __int64 v23; // rax
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  WCHAR *v28; // rax
  __int64 v29; // r8
  int v30; // esi
  __int64 i; // rax
  const CLFS_LSN *v32; // rcx
  __int64 v33; // r8
  __int64 j; // rax
  const CLFS_LSN *v35; // rcx
  int v36; // ecx
  unsigned __int64 v37; // rax
  __int64 v38; // rdx
  unsigned __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  CLFS_LSN *v42; // rbx
  char v43; // dl
  __int16 *v44; // rbx
  __int64 v45; // rcx
  int v46; // r9d
  __int64 v47; // rcx
  CLFS_LSN *v48; // r12
  __int64 v49; // rcx
  int v50; // eax
  char v51; // al
  __int64 v52; // rcx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 k; // rax
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  unsigned int m; // eax
  unsigned int v60; // ebx
  unsigned __int64 v61; // rax
  __int64 v62; // rdx
  unsigned __int64 v63; // rax
  __int64 v64; // rdx
  int v65; // eax
  struct _FILE_OBJECT *v66; // rbx
  _QWORD *FsContext; // r14
  __int64 v68; // rdx
  unsigned int v69; // ebx
  __int64 v70; // rdx
  unsigned __int64 v71; // rax
  __int64 v72; // rdx
  unsigned __int64 v73; // rax
  __int64 v74; // rdx
  int v75; // eax
  __int64 v76; // rax
  int v78; // [rsp+20h] [rbp-168h]
  int v79; // [rsp+20h] [rbp-168h]
  int v80; // [rsp+30h] [rbp-158h]
  int v81; // [rsp+30h] [rbp-158h]
  char v82; // [rsp+70h] [rbp-118h]
  char v83; // [rsp+71h] [rbp-117h]
  __int64 v84; // [rsp+78h] [rbp-110h]
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-108h] BYREF
  int v86; // [rsp+88h] [rbp-100h]
  int v87; // [rsp+8Ch] [rbp-FCh]
  int v88; // [rsp+90h] [rbp-F8h]
  unsigned int v89; // [rsp+94h] [rbp-F4h]
  CLFS_LSN *plsn2; // [rsp+98h] [rbp-F0h]
  __int64 FileInformation; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v92; // [rsp+A8h] [rbp-E0h] BYREF
  PRTL_AVL_TABLE *v93; // [rsp+B0h] [rbp-D8h]
  __int64 v94; // [rsp+B8h] [rbp-D0h] BYREF
  UNICODE_STRING v95; // [rsp+C0h] [rbp-C8h] BYREF
  _QWORD v96[2]; // [rsp+D0h] [rbp-B8h] BYREF
  __int128 v97; // [rsp+E0h] [rbp-A8h] BYREF
  int v98[24]; // [rsp+F0h] [rbp-98h] BYREF

  plsn2 = a4;
  v93 = (PRTL_AVL_TABLE *)a2;
  v7 = *(_QWORD *)(a2 + 208);
  v84 = v7;
  v96[1] = v7;
  v8 = 0;
  v94 = 0;
  v96[0] = 0;
  FileObject = 0;
  FileInformation = 0;
  v97 = 0;
  v9 = 0;
  v83 = 0;
  memset(v98, 0, 0x58u);
  v10 = 0;
  v82 = 0;
  v95 = 0;
  v92 = 0;
  if ( *(_DWORD *)(a3 + 64) < 0x70u )
    TxfRaiseBoundsCheckFailure();
  LODWORD(v11) = TxfOpenFileCheckId(
                   a1,
                   (PRTL_AVL_TABLE *)a2,
                   a3,
                   (unsigned __int64 *)(a3 + 88),
                   0,
                   2,
                   *(_BYTE *)(a3 + 74) & 8,
                   0,
                   &v94,
                   &FileObject);
  if ( (_DWORD)v11 != -1072103368 )
  {
    v97 = 0;
    *(_QWORD *)&v97 = *(_QWORD *)(a3 + 80);
    v13 = TxfOpenFileCheckId(
            a1,
            (PRTL_AVL_TABLE *)a2,
            a3,
            (unsigned __int64 *)&v97,
            0,
            2,
            *(_BYTE *)(a3 + 74) & 8,
            0,
            v96,
            &FileInformation);
    v12 = (unsigned __int64)FileObject;
    if ( FileObject )
    {
      v14 = (const CLFS_LSN *)*((_QWORD *)FileObject->FsContext + 23);
      v12 = (unsigned __int64)FileObject;
    }
    else
    {
      v14 = 0;
    }
    v15 = FileInformation;
    if ( FileInformation )
      v16 = *(const CLFS_LSN **)(*(_QWORD *)(FileInformation + 24) + 184LL);
    else
      v16 = 0;
    if ( v12 )
    {
      if ( !FileInformation )
      {
        if ( ClfsLsnLess(v14 + 30, plsn2) )
        {
          DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19531, "Status", v13);
          if ( v13 == -1073741801
            || (v17 = (unsigned int)(v13 + 1073741697), (unsigned int)v17 <= 0x22)
            && (v18 = 0x408000001LL, _bittest64(&v18, v17)) )
          {
            ++HIDWORD((*TxfData)[1]);
          }
          else if ( v13 == -1072037845
                 || v13 == -1073741202
                 || v13 == -1073741435
                 || v13 == -1073741496
                 || (v19 = (unsigned int)(v13 + 1073741667), (unsigned int)v19 <= 0x23)
                 && (v20 = 0x800000041LL, _bittest64(&v20, v19))
                 || (v12 = (unsigned int)(v13 + 1073741811), (unsigned int)v12 <= 0x15)
                 && (v21 = 2097219, _bittest(&v21, v12))
                 || v13 == -2147483626
                 || v13 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          LOBYTE(v11) = NtfsStatusDebugFlags;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_197;
          v22 = 3230796;
          goto LABEL_30;
        }
        v12 = (unsigned __int64)FileObject;
      }
      if ( v12 )
        goto LABEL_54;
    }
    if ( v15 )
    {
      if ( ClfsLsnLess(v16 + 30, plsn2) )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19545, "Status", v13);
        if ( v13 == -1073741801
          || (v23 = (unsigned int)(v13 + 1073741697), (unsigned int)v23 <= 0x22)
          && (v24 = 0x408000001LL, _bittest64(&v24, v23)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( v13 == -1072037845
               || v13 == -1073741202
               || v13 == -1073741435
               || v13 == -1073741496
               || (v25 = (unsigned int)(v13 + 1073741667), (unsigned int)v25 <= 0x23)
               && (v26 = 0x800000041LL, _bittest64(&v26, v25))
               || (v12 = (unsigned int)(v13 + 1073741811), (unsigned int)v12 <= 0x15)
               && (v27 = 2097219, _bittest(&v27, v12))
               || v13 == -2147483626
               || v13 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        LOBYTE(v11) = NtfsStatusDebugFlags;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_197;
        v22 = 3230810;
        goto LABEL_30;
      }
      v12 = (unsigned __int64)FileObject;
    }
    if ( v12 )
    {
LABEL_54:
      if ( v15 )
      {
        v95.MaximumLength = 2 * *(_WORD *)(a3 + 104);
        v95.Length = v95.MaximumLength;
        if ( v95.MaximumLength )
          v28 = (WCHAR *)(a3 + *(unsigned __int16 *)(a3 + 106));
        else
          v28 = 0;
        v95.Buffer = v28;
        NtfsAcquireSharedVcb(a1, *(_QWORD *)(v84 + 16), 0);
        v30 = 1;
        v83 = 1;
        if ( (*(_DWORD *)(*(_QWORD *)(v84 + 16) + 4LL) & 1) == 0 )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 3230856);
          NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 3230856);
        }
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( !v14[14].ullOffset )
          {
            NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
            NtfsAddPagingIoToFcb(a1, v14, 0);
            NtfsReleaseFcbEx(a1, v14, 0);
          }
          LOBYTE(v29) = 1;
          if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v14, v29) )
          {
            v86 = 0;
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v86 = i;
              if ( (unsigned int)i >= 2 )
                break;
              v32 = *(const CLFS_LSN **)(a1 + 8 * i + 48);
              if ( !v32 || v32 == v14 )
              {
                *(_QWORD *)(a1 + 8 * i + 48) = v14;
                break;
              }
            }
          }
        }
        NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( !v16[14].ullOffset )
          {
            NtfsAcquireExclusiveFcb(a1, v16, 0, 0);
            NtfsAddPagingIoToFcb(a1, v16, 0);
            NtfsReleaseFcbEx(a1, v16, 0);
          }
          LOBYTE(v33) = 1;
          NtfsAcquirePagingResourceExclusive(0, v16, v33);
          v87 = 0;
          for ( j = 0; ; j = (unsigned int)(j + 1) )
          {
            v87 = j;
            if ( (unsigned int)j >= 2 )
              break;
            v35 = *(const CLFS_LSN **)(a1 + 8 * j + 48);
            if ( !v35 || v35 == v16 )
            {
              *(_QWORD *)(a1 + 8 * j + 48) = v16;
              break;
            }
          }
        }
        NtfsAcquireExclusiveFcb(a1, v16, 0, 0);
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          LOBYTE(v11) = ClfsLsnLess(v14 + 30, plsn2);
          if ( (_BYTE)v11 )
          {
            memset(v98, 0, 0x58u);
            v82 = 1;
            LOBYTE(v80) = 0;
            v43 = NtfsLookupInFileRecord(a1, v16, &v16[1], *(unsigned int *)(a3 + 108), &v95, 0, v80, 0, 0, v98);
            if ( v43 )
            {
              if ( *(_BYTE *)(*(_QWORD *)v98 + 8LL) )
              {
                v43 &= -(*(_QWORD *)(*(_QWORD *)v98 + 40LL) != 0);
              }
              else if ( !*(_DWORD *)(*(_QWORD *)v98 + 16LL) )
              {
                v43 = 0;
              }
            }
            if ( !v43 )
            {
              v44 = NtfsCreateScb(a1, (__int64)v14, *(_DWORD *)(a3 + 108), &v95, 0, 0, 0);
              NtfsCleanupAttributeContext(v45, v98);
              memset(v98, 0, 0x58u);
              LOBYTE(v81) = 0;
              if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                       a1,
                                       *((_QWORD *)v44 + 23),
                                       *((_QWORD *)v44 + 23) + 8LL,
                                       *((unsigned int *)v44 + 64),
                                       v44 + 132,
                                       0,
                                       v81,
                                       0,
                                       0,
                                       v98)
                && (*((_DWORD *)v44 + 128) & 4) == 0 )
              {
                v30 = 3231004;
                NtfsAttachCorruption_BadOrOrphanFRS(
                  a1,
                  2,
                  3231004,
                  v46,
                  *((_QWORD *)v44 + 23) + 8LL,
                  *((_QWORD *)v44 + 23),
                  0);
                NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA900314D1CLL);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3231004);
                NtfsRaiseStatusInternal(a1, -1073741566, *((_QWORD *)v44 + 23) + 8, *((_QWORD *)v44 + 23), 3231004);
              }
              NtfsFlushFcb(a1, (_DWORD)v14);
              v47 = *((_QWORD *)v44 + 66);
              if ( v47 )
                *(_DWORD *)(v47 + 24) = *(_DWORD *)(v47 + 24);
              TxfPrepareToMoveAttribute(a1, (int)v14, (int)v16, v98, 0);
              TxfMoveAttrInternal(a1, (_DWORD)v14, v98, 0, (__int64)&v92);
              NtfsConditionallyFixupQuota(a1, v16);
              NtfsConditionallyFixupQuota(a1, v14);
              v48 = plsn2;
              v49 = (unsigned __int64)v48 & -(__int64)(ClfsLsnLess(v16 + 32, plsn2) != 0);
              if ( !v48 || (v50 = v30, (v16->offset.cidContainer & 0x100000) != 0) )
                v50 = 0;
              TxfUpdateTxfDataAttributeMembers(a1, (int)v16, v78, 0, v50, (__int64)v48, v49, 0, 0, 0, 0);
              v51 = -ClfsLsnLess(v14 + 32, v48);
              if ( !v48 || (v14->offset.cidContainer & 0x100000) != 0 )
                v30 = 0;
              TxfUpdateTxfDataAttributeMembers(
                a1,
                (int)v14,
                v79,
                0,
                v30,
                (__int64)v48,
                (unsigned __int64)v48 & -(__int64)(v51 != 0),
                0,
                0,
                0,
                0);
              LOBYTE(v11) = NtfsCheckpointCurrentTransaction(a1);
              v12 = *((_QWORD *)v44 + 66);
              v7 = v84;
              if ( v12 )
              {
                *(_QWORD *)(v12 + 96) = *((_QWORD *)v44 + 5);
                *(_QWORD *)(*((_QWORD *)v44 + 66) + 104LL) = *((_QWORD *)v44 + 4);
                v12 = *((_QWORD *)v44 + 66);
                LODWORD(v11) = *(_DWORD *)(v12 + 24);
                *(_DWORD *)(v12 + 24) = v11;
              }
              v8 = v92;
              v9 = 1;
              goto LABEL_199;
            }
            FileInformation = 0;
            NtfsReleaseFcbEx(a1, v14, 0);
            NtfsReleasePagingResourcePriv(v52, v14, v53, v54);
            if ( a1 )
            {
              v88 = 0;
              for ( k = 0; ; k = (unsigned int)(k + 1) )
              {
                v88 = k;
                if ( (unsigned int)k >= 2 )
                  break;
                if ( *(const CLFS_LSN **)(a1 + 8 * k + 48) == v14 )
                  *(_QWORD *)(a1 + 8 * k + 48) = 0;
              }
            }
            NtfsReleaseFcbEx(a1, v16, 0);
            if ( a1 )
            {
              v89 = 0;
              for ( m = 0; ; ++m )
              {
                v89 = m;
                if ( m >= 2 )
                  break;
                v56 = m;
                if ( *(const CLFS_LSN **)(a1 + 8LL * m + 48) == v16 )
                  *(_QWORD *)(a1 + 8LL * m + 48) = 0;
              }
            }
            NtfsReleasePagingResourcePriv(v56, v16, v57, v58);
            NtfsReleaseVcb(a1, *(_QWORD *)(v84 + 16));
            v9 = 0;
            LODWORD(v11) = TxfOpenFileCheckId(
                             a1,
                             v93,
                             a3,
                             (unsigned __int64 *)(a3 + 88),
                             (unsigned __int16 *)(a3 + 104),
                             2,
                             *(_BYTE *)(a3 + 74) & 8,
                             0,
                             &v94,
                             &FileObject);
            v60 = v11;
            if ( (int)v11 < 0 )
            {
              DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19878, "Status", v11);
              if ( v60 == -1073741801
                || (v61 = v60 + 1073741697, (unsigned int)v61 <= 0x22) && (v62 = 0x408000001LL, _bittest64(&v62, v61)) )
              {
                ++HIDWORD((*TxfData)[1]);
              }
              else if ( v60 == -1072037845
                     || v60 == -1073741202
                     || v60 == -1073741435
                     || v60 == -1073741496
                     || (v63 = v60 + 1073741667, (unsigned int)v63 <= 0x23)
                     && (v64 = 0x800000041LL, _bittest64(&v64, v63))
                     || v60 + 1073741811 <= 0x15 && (v65 = 2097219, _bittest(&v65, v60 + 1073741811))
                     || v60 == -2147483626
                     || v60 == -1072037841 )
              {
                ++LODWORD((*TxfData)[2]);
              }
              if ( NtfsStatusDebugFlags
                && v60 < 0xFFFFFFED
                && v60 != -1073741802
                && v60 != -1073741807
                && v60 + 2147483643 > 1
                && v60 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, v60, 3231143);
              }
              ExRaiseStatus(v60);
            }
            v66 = FileObject;
            FsContext = FileObject->FsContext;
            if ( FsContext[4] )
            {
              FileInformation = 0;
              v68 = FsContext[66];
              if ( v68 )
                *(_DWORD *)(v68 + 24) = *(_DWORD *)(v68 + 24);
              NtfsPurgeFileRecordCache(a1);
              *(_DWORD *)(a1 + 4) |= 0x200u;
              v69 = IoSetInformation(v66, FileEndOfFileInformation, 8u, &FileInformation);
              *(_DWORD *)(a1 + 4) &= ~0x200u;
              v11 = FsContext[66];
              if ( v11 )
              {
                *(_QWORD *)(v11 + 96) = FsContext[5];
                *(_QWORD *)(FsContext[66] + 104LL) = FsContext[4];
                v70 = FsContext[66];
                v12 = *(unsigned int *)(v70 + 24);
                *(_DWORD *)(v70 + 24) = v12;
              }
              if ( v69 )
              {
                if ( NtfsStatusDebugFlags
                  && (((v69 - 294) & 0xFFFFFFFA) != 0 || v69 == 295)
                  && v69 < 0xFFFFFFED
                  && v69 != -1073741608
                  && v69 != -1073741802
                  && v69 != -1073741807
                  && v69 + 2147483643 > 1
                  && v69 != 259 )
                {
                  NtfsStatusTraceAndDebugInternal(a1, v69, 3231194);
                }
                ExRaiseStatus(v69);
              }
            }
LABEL_198:
            v7 = v84;
LABEL_199:
            v10 = v82;
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
            v36 = *(_DWORD *)(a3 + 108);
            if ( v36 == -1073741801
              || (v37 = (unsigned int)(v36 + 1073741697), (unsigned int)v37 <= 0x22)
              && (v38 = 0x408000001LL, _bittest64(&v38, v37)) )
            {
              ++HIDWORD((*TxfData)[1]);
            }
            else if ( v36 == -1072037845
                   || v36 == -1073741202
                   || v36 == -1073741435
                   || v36 == -1073741496
                   || (v39 = (unsigned int)(v36 + 1073741667), (unsigned int)v39 <= 0x23)
                   && (v40 = 0x800000041LL, _bittest64(&v40, v39))
                   || (unsigned int)(v36 + 1073741811) <= 0x15 && (v41 = 2097219, _bittest(&v41, v36 + 1073741811))
                   || v36 == -2147483626
                   || v36 == -1072037841 )
            {
              ++LODWORD((*TxfData)[2]);
            }
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3222863920LL, 3231232);
            ExRaiseStatus(-1072103376);
          }
          v42 = plsn2;
          LOBYTE(v11) = ClfsLsnLess(v14 + 30, plsn2);
          if ( (_BYTE)v11 )
            LOBYTE(v11) = TxfRedoUndoMoveReparsePoint(a1, v42->ullOffset);
        }
LABEL_197:
        v9 = v83;
        goto LABEL_198;
      }
    }
    LODWORD(v11) = *((_DWORD *)v93 + 4);
    if ( (v11 & 0x10) == 0 )
      goto LABEL_197;
    DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 19562, "Status", v13);
    if ( v13 == -1073741801
      || (v71 = (unsigned int)(v13 + 1073741697), (unsigned int)v71 <= 0x22)
      && (v72 = 0x408000001LL, _bittest64(&v72, v71)) )
    {
      ++HIDWORD((*TxfData)[1]);
    }
    else if ( v13 == -1072037845
           || v13 == -1073741202
           || v13 == -1073741435
           || v13 == -1073741496
           || (v73 = (unsigned int)(v13 + 1073741667), (unsigned int)v73 <= 0x23)
           && (v74 = 0x800000041LL, _bittest64(&v74, v73))
           || (v12 = (unsigned int)(v13 + 1073741811), (unsigned int)v12 <= 0x15)
           && (v75 = 2097219, _bittest(&v75, v12))
           || v13 == -2147483626
           || v13 == -1072037841 )
    {
      ++LODWORD((*TxfData)[2]);
    }
    LOBYTE(v11) = NtfsStatusDebugFlags;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_197;
    v22 = 3230827;
LABEL_30:
    LOBYTE(v11) = NtfsStatusTraceAndDebugInternal(0, 3221225730LL, v22);
    goto LABEL_197;
  }
LABEL_200:
  if ( v9 )
    LOBYTE(v11) = NtfsReleaseVcb(a1, *(_QWORD *)(v7 + 16));
  if ( v10 )
    LOBYTE(v11) = NtfsCleanupAttributeContext(v12, v98);
  if ( v8 )
  {
    if ( *(_QWORD *)(v8 + 48) )
      CcUninitializeCacheMap((PFILE_OBJECT)v8, 0, 0);
    v76 = *(_QWORD *)(v8 + 24);
    if ( v76 && (*(_DWORD *)(v76 + 200) & 0x4000) == 0 )
    {
      *(_DWORD *)(v8 + 88) = 0;
      *(_QWORD *)(v8 + 96) = 0;
    }
    LOBYTE(v11) = ObfDereferenceObject((PVOID)v8);
  }
  return v11;
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
