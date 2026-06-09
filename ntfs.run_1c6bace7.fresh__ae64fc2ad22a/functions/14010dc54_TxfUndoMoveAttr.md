# TxfUndoMoveAttr

- ea: `0x14010dc54`
- end: `0x14010f049`
- name: `TxfUndoMoveAttr`
- size: `5109`
- prototype: ``
- caller_count: `3`
- callee_count: `36`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140106348`
- `0x140133f30`
- `0x1401d8340`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d1e0`
- `0x14000ea70`
- `0x140012e70`
- `0x140020de0`
- `0x140021590`
- `0x14002c3d0`
- `0x1400388bc`
- `0x1400410a8`
- `0x1400527fc`
- `0x1400596c0`
- `0x1400f957c`
- `0x140106838`
- `0x14010a8e8`
- `0x14010d044`
- `0x14010dc54`
- `0x1401250b0`
- `0x1401331f4`
- `0x140140380`
- `0x1401419ec`
- `0x140159768`
- `0x1401620c0`
- `0x1401913d4`
- `0x1401952d4`
- `0x14019a718`
- `0x1401aab20`
- `0x1401c00e0`
- `0x1401db164`
- `0x1401e0660`
- `0x1401fd820`
- `0x14021d6f8`
- `0x14022bcc4`
- `0x140278d84`
- `0x14029130c`
- `0x14029c058`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14010efe4`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c61cc`
- `ntoskrnl!ObfDereferenceObject` at `0x14010efe4`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c61cc`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14010efb5`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402c619c`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14010efb5`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402c619c`
- `ntoskrnl!DbgPrintEx` at `0x14010de74`
- `ntoskrnl!DbgPrintEx` at `0x14010dfaa`
- `ntoskrnl!DbgPrintEx` at `0x14010e3cd`
- `ntoskrnl!DbgPrintEx` at `0x14010e525`
- `ntoskrnl!DbgPrintEx` at `0x14010ee87`
- `ntoskrnl!DbgPrintEx` at `0x14010f029`
- `ntoskrnl!DbgPrintEx` at `0x14010de74`
- `ntoskrnl!DbgPrintEx` at `0x14010dfaa`
- `ntoskrnl!DbgPrintEx` at `0x14010e3cd`
- `ntoskrnl!DbgPrintEx` at `0x14010e525`
- `ntoskrnl!DbgPrintEx` at `0x14010ee87`
- `ntoskrnl!DbgPrintEx` at `0x14010f029`
- `ntoskrnl!ExRaiseStatus` at `0x14010e3fb`
- `ntoskrnl!ExRaiseStatus` at `0x14010e5f4`
- `ntoskrnl!ExRaiseStatus` at `0x14010e3fb`
- `ntoskrnl!ExRaiseStatus` at `0x14010e5f4`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010de31`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010df67`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010e258`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eab7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010ead3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb3d`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010de31`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010df67`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010e258`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eab7`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010ead3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnLess` at `0x14010eb3d`

## pseudocode

```c
char __fastcall TxfUndoMoveAttr(__int64 a1, CLFS_LSN *a2, __int64 a3, const CLFS_LSN *a4, CLFS_LSN *a5, int a6)
{
  CLFS_LSN *v7; // r15
  const CLFS_LSN *v9; // rsi
  __int64 n; // rax
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // r12
  const CLFS_LSN *v14; // r14
  __int64 v15; // r15
  BOOLEAN v16; // al
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r8
  BOOLEAN v23; // al
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  unsigned __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // eax
  WCHAR *v29; // rax
  CLFS_LSN v30; // rbx
  __int64 v31; // r8
  unsigned int v32; // eax
  const CLFS_LSN *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  char v36; // r14
  __int64 v37; // r9
  const CLFS_LSN *v38; // rcx
  CLFS_LSN *v39; // rbx
  BOOLEAN ShouldProcessRedoCancelBasedOnLsn; // al
  __int64 v41; // r8
  __int64 v42; // r8
  unsigned int i; // eax
  const CLFS_LSN *v44; // rcx
  unsigned int j; // eax
  const CLFS_LSN *v46; // rcx
  __int64 v47; // rcx
  int v48; // ecx
  unsigned __int64 v49; // rax
  __int64 v50; // rdx
  unsigned __int64 v51; // rax
  __int64 v52; // rdx
  int v53; // eax
  char v54; // bl
  char v55; // dl
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  unsigned int k; // eax
  __int64 v60; // r8
  unsigned int m; // eax
  const CLFS_LSN *v62; // rcx
  __int16 *v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rax
  __int16 *v66; // r12
  __int64 v67; // rcx
  int v68; // r9d
  __int64 v69; // rcx
  CLFS_RECORD_INDEX idxRecord; // r12d
  unsigned int v71; // eax
  CLFS_RECORD_INDEX v72; // eax
  BOOLEAN v73; // al
  BOOLEAN v74; // al
  CLFS_LSN v75; // rdx
  __int64 v76; // r14
  __int16 *v77; // rax
  int v78; // ecx
  __int64 v79; // rdx
  int v80; // ecx
  __int64 v81; // rdx
  __int64 v82; // rsi
  __int16 *v83; // r14
  unsigned __int64 v84; // rax
  __int64 v85; // rdx
  unsigned __int64 v86; // rax
  __int64 v87; // rdx
  int v88; // eax
  PFILE_OBJECT v89; // rbx
  _DWORD *FsContext; // rax
  int v92; // [rsp+20h] [rbp-188h]
  int v93; // [rsp+20h] [rbp-188h]
  int v94; // [rsp+30h] [rbp-178h]
  int v95; // [rsp+30h] [rbp-178h]
  char v96; // [rsp+70h] [rbp-138h]
  char v97; // [rsp+71h] [rbp-137h] BYREF
  char v98; // [rsp+72h] [rbp-136h] BYREF
  char v99; // [rsp+73h] [rbp-135h]
  char v100; // [rsp+74h] [rbp-134h]
  char v101; // [rsp+75h] [rbp-133h]
  char v102; // [rsp+76h] [rbp-132h]
  CLFS_LSN v103; // [rsp+78h] [rbp-130h] BYREF
  UNICODE_STRING v104; // [rsp+80h] [rbp-128h] BYREF
  unsigned int v105; // [rsp+90h] [rbp-118h]
  unsigned int v106; // [rsp+94h] [rbp-114h]
  unsigned int v107; // [rsp+98h] [rbp-110h]
  unsigned int v108; // [rsp+9Ch] [rbp-10Ch]
  unsigned int v109; // [rsp+A0h] [rbp-108h]
  CLFS_RECORD_INDEX v110; // [rsp+A4h] [rbp-104h]
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-100h] BYREF
  __int16 *v112; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v113; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v114; // [rsp+C0h] [rbp-E8h] BYREF
  __int64 v115; // [rsp+C8h] [rbp-E0h]
  __int64 v116; // [rsp+D0h] [rbp-D8h]
  CLFS_LSN v117; // [rsp+D8h] [rbp-D0h]
  const CLFS_LSN *v118; // [rsp+E0h] [rbp-C8h]
  _QWORD v119[2]; // [rsp+E8h] [rbp-C0h] BYREF
  __int128 v120; // [rsp+F8h] [rbp-B0h] BYREF
  _QWORD v121[19]; // [rsp+110h] [rbp-98h] BYREF

  v7 = a2;
  v117 = a2[26];
  v119[1] = v117.ullOffset;
  v9 = 0;
  v118 = 0;
  v119[0] = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  memset(v121, 0, 0x58u);
  v96 = 0;
  v104 = 0;
  FileObject = 0;
  v101 = 0;
  v97 = 0;
  v100 = 0;
  v98 = 0;
  v120 = 0;
  v103.ullOffset = 0;
  v102 = 0;
  v110 = 0;
  if ( *(_DWORD *)(a3 + 64) < 0x70u )
    TxfRaiseBoundsCheckFailure();
  *(_QWORD *)&v120 = *(_QWORD *)(a3 + 80);
  TxfOpenFileCheckId(
    a1,
    (PRTL_AVL_TABLE *)v7,
    a3,
    (unsigned __int64 *)&v120,
    0,
    2,
    *(_BYTE *)(a3 + 74) & 8,
    0,
    v119,
    &v113);
  LODWORD(n) = TxfOpenFileCheckId(
                 a1,
                 (PRTL_AVL_TABLE *)v7,
                 a3,
                 (unsigned __int64 *)(a3 + 88),
                 0,
                 2,
                 *(_BYTE *)(a3 + 74) & 8,
                 0,
                 &v112,
                 &v114);
  v12 = n;
  if ( (_DWORD)n == -1072103368 )
    goto LABEL_242;
  v13 = v113;
  if ( v113 )
    v14 = *(const CLFS_LSN **)(*(_QWORD *)(v113 + 24) + 184LL);
  else
    v14 = 0;
  v15 = v114;
  if ( v114 )
    v9 = *(const CLFS_LSN **)(*(_QWORD *)(v114 + 24) + 184LL);
  v118 = v9;
  v11 = 0;
  if ( !v113 )
    goto LABEL_51;
  if ( !v114 )
  {
    v16 = ClfsLsnLess(v14 + 30, a4);
    v11 = 0;
    if ( v16 )
    {
      DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 20172, "Status", v12);
      if ( v12 == -1073741801
        || (v17 = (unsigned int)(v12 + 1073741697), (unsigned int)v17 <= 0x22)
        && (v18 = 0x408000001LL, _bittest64(&v18, v17)) )
      {
        ++HIDWORD((*TxfData)[1]);
      }
      else if ( v12 == -1072037845
             || v12 == -1073741202
             || v12 == -1073741435
             || v12 == -1073741496
             || (v19 = (unsigned int)(v12 + 1073741667), (unsigned int)v19 <= 0x23)
             && (v20 = 0x800000041LL, _bittest64(&v20, v19))
             || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
             && (v21 = 2097219, _bittest(&v21, v11))
             || v12 == -2147483626
             || v12 == -1072037841 )
      {
        ++LODWORD((*TxfData)[2]);
      }
      LOBYTE(n) = NtfsStatusDebugFlags;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_30;
      v22 = 3231437;
LABEL_29:
      LOBYTE(n) = NtfsStatusTraceAndDebugInternal(0, 3221225730LL, v22);
LABEL_30:
      v7 = a2;
LABEL_242:
      v36 = 0;
      goto LABEL_243;
    }
  }
  if ( !v13 )
  {
LABEL_51:
    if ( v15 )
    {
      v23 = ClfsLsnLess(v9 + 30, a4);
      v11 = 0;
      if ( v23 )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 20186, "Status", v12);
        if ( v12 == -1073741801
          || (v24 = (unsigned int)(v12 + 1073741697), (unsigned int)v24 <= 0x22)
          && (v25 = 0x408000001LL, _bittest64(&v25, v24)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( v12 == -1072037845
               || v12 == -1073741202
               || v12 == -1073741435
               || v12 == -1073741496
               || (v26 = (unsigned int)(v12 + 1073741667), (unsigned int)v26 <= 0x23)
               && (v27 = 0x800000041LL, _bittest64(&v27, v26))
               || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
               && (v28 = 2097219, _bittest(&v28, v11))
               || v12 == -2147483626
               || v12 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        LOBYTE(n) = NtfsStatusDebugFlags;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_30;
        v22 = 3231451;
        goto LABEL_29;
      }
    }
    if ( !v13 )
      goto LABEL_224;
  }
  if ( !v15 )
  {
LABEL_224:
    v7 = a2;
    LODWORD(n) = a2[2].offset.idxRecord;
    if ( (n & 0x10) == 0 )
      goto LABEL_242;
    DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 20203, "Status", v12);
    if ( v12 == -1073741801
      || (v84 = (unsigned int)(v12 + 1073741697), (unsigned int)v84 <= 0x22)
      && (v85 = 0x408000001LL, _bittest64(&v85, v84)) )
    {
      ++HIDWORD((*TxfData)[1]);
    }
    else if ( v12 == -1072037845
           || v12 == -1073741202
           || v12 == -1073741435
           || v12 == -1073741496
           || (v86 = (unsigned int)(v12 + 1073741667), (unsigned int)v86 <= 0x23)
           && (v87 = 0x800000041LL, _bittest64(&v87, v86))
           || (v11 = (unsigned int)(v12 + 1073741811), (unsigned int)v11 <= 0x15)
           && (v88 = 2097219, _bittest(&v88, v11))
           || v12 == -2147483626
           || v12 == -1072037841 )
    {
      ++LODWORD((*TxfData)[2]);
    }
    LOBYTE(n) = NtfsStatusDebugFlags;
    if ( NtfsStatusDebugFlags )
      LOBYTE(n) = NtfsStatusTraceAndDebugInternal(0, 3221225730LL, 3231468);
    goto LABEL_133;
  }
  v104.MaximumLength = 2 * *(_WORD *)(a3 + 104);
  v104.Length = v104.MaximumLength;
  if ( v104.MaximumLength )
    v29 = (WCHAR *)(a3 + *(unsigned __int16 *)(a3 + 106));
  else
    v29 = 0;
  v104.Buffer = v29;
  v30 = v117;
  NtfsAcquireSharedVcb(a1, *(_QWORD *)(v117.ullOffset + 16), 0);
  v101 = 1;
  if ( (*(_DWORD *)(*(_QWORD *)(v30.ullOffset + 16) + 4LL) & 1) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 3231500);
    NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 3231500);
  }
  if ( *(_DWORD *)(a3 + 108) == 128 )
  {
    if ( !v9[14].ullOffset )
    {
      NtfsAcquireExclusiveFcb(a1, v9, 0, 0);
      NtfsAddPagingIoToFcb(a1, v9, 0);
      NtfsReleaseFcbEx(a1, v9, 0);
    }
    LOBYTE(v31) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v9, v31) )
    {
      v32 = 0;
      v105 = 0;
      while ( v32 < 2 )
      {
        v33 = *(const CLFS_LSN **)(a1 + 8LL * v32 + 48);
        if ( !v33 || v33 == v9 )
        {
          *(_QWORD *)(a1 + 8LL * v32 + 48) = v9;
          break;
        }
        v105 = ++v32;
      }
    }
  }
  NtfsAcquireExclusiveFcb(a1, v9, 0, 0);
  if ( (a2[2].offset.idxRecord & 0x1000) == 0 )
  {
    if ( a6 )
    {
      LOBYTE(v35) = 1;
      v7 = a2;
      if ( !(unsigned __int8)TxfAlreadyWroteClr(a1, a2, 15, v35) )
      {
        memset(v121, 0, 0x58u);
        v96 = 1;
        if ( *(_DWORD *)(a3 + 108) == 128 )
        {
          if ( !v14[14].ullOffset )
          {
            NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
            NtfsAddPagingIoToFcb(a1, v14, 0);
            NtfsReleaseFcbEx(a1, v14, 0);
          }
          LOBYTE(v42) = 1;
          NtfsAcquirePagingResourceExclusive(0, v14, v42);
          v106 = 0;
          for ( i = 0; ; ++i )
          {
            v106 = i;
            if ( i >= 2 )
              break;
            v44 = *(const CLFS_LSN **)(a1 + 8LL * i + 48);
            if ( !v44 || v44 == v14 )
            {
              *(_QWORD *)(a1 + 8LL * i + 48) = v14;
              break;
            }
          }
          v100 = 1;
          v97 = 1;
        }
        NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
        v97 = 1;
        v98 = 1;
        LOBYTE(v94) = 0;
        v99 = NtfsLookupInFileRecord(a1, v14, &v14[1], *(unsigned int *)(a3 + 108), &v104, 0, v94, 0, 0, v121);
        if ( !v99 )
        {
          DbgPrintEx(
            0x82u,
            0,
            "%s:%d -- TxF corruption detected, %s == 0x%x",
            "txftrans.c",
            20404,
            "Status",
            -1073741566);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3231674);
          ExRaiseStatus(-1073741566);
        }
        TxfWriteMoveAttrLogRecord(a1, (_DWORD)a2, 0, 0, 0, a3);
      }
      v103 = a2[37];
    }
    else
    {
      v38 = v14 + 30;
      v39 = a5;
      if ( a5 )
      {
        ShouldProcessRedoCancelBasedOnLsn = TxfShouldProcessRedoCancelBasedOnLsn(v38, v34, &v14[30], a4, a5);
      }
      else
      {
        v39 = (CLFS_LSN *)a4;
        ShouldProcessRedoCancelBasedOnLsn = ClfsLsnLess(v38, a4);
      }
      if ( !ShouldProcessRedoCancelBasedOnLsn )
      {
        LOBYTE(n) = v98;
        v7 = a2;
        goto LABEL_97;
      }
      v103 = *v39;
      v7 = a2;
    }
    LOBYTE(n) = 1;
LABEL_97:
    if ( !(_BYTE)n )
    {
LABEL_133:
      v36 = 0;
      goto LABEL_243;
    }
    if ( !v97 )
    {
      if ( *(_DWORD *)(a3 + 108) == 128 )
      {
        if ( !v14[14].ullOffset )
        {
          NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
          NtfsAddPagingIoToFcb(a1, v14, 0);
          NtfsReleaseFcbEx(a1, v14, 0);
        }
        LOBYTE(v41) = 1;
        NtfsAcquirePagingResourceExclusive(0, v14, v41);
        v107 = 0;
        for ( j = 0; ; ++j )
        {
          v107 = j;
          if ( j >= 2 )
            break;
          v46 = *(const CLFS_LSN **)(a1 + 8LL * j + 48);
          if ( !v46 || v46 == v14 )
          {
            *(_QWORD *)(a1 + 8LL * j + 48) = v14;
            break;
          }
        }
        v100 = 1;
        v97 = 1;
      }
      NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
      v98 = 1;
    }
    v47 = *(unsigned int *)(a3 + 108);
    if ( *(_DWORD *)(a3 + 108) != 128 )
    {
      if ( *(_DWORD *)(a3 + 108) != 192 )
      {
        DbgPrintEx(0x82u, 0, "%s:%d -- TxF corruption detected, %s == 0x%x", "txftrans.c", 21038, "Status", v47);
        v48 = *(_DWORD *)(a3 + 108);
        if ( v48 == -1073741801
          || (v49 = (unsigned int)(v48 + 1073741697), (unsigned int)v49 <= 0x22)
          && (v50 = 0x408000001LL, _bittest64(&v50, v49)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( v48 == -1072037845
               || v48 == -1073741202
               || v48 == -1073741435
               || v48 == -1073741496
               || (v51 = (unsigned int)(v48 + 1073741667), (unsigned int)v51 <= 0x23)
               && (v52 = 0x800000041LL, _bittest64(&v52, v51))
               || (unsigned int)(v48 + 1073741811) <= 0x15 && (v53 = 2097219, _bittest(&v53, v48 + 1073741811))
               || v48 == -2147483626
               || v48 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3222863920LL, 3232303);
        ExRaiseStatus(-1072103376);
      }
      if ( v96 )
      {
        NtfsCleanupAttributeContext(v47, v121);
        v96 = 0;
      }
      LOBYTE(n) = TxfRedoUndoMoveReparsePoint(a1, v103.ullOffset);
      goto LABEL_133;
    }
    if ( v96 )
      NtfsCleanupAttributeContext(v47, v121);
    memset(v121, 0, 0x58u);
    v54 = 1;
    LOBYTE(v94) = 0;
    LOBYTE(n) = NtfsLookupInFileRecord(a1, v14, &v14[1], *(unsigned int *)(a3 + 108), &v104, 0, v94, 0, 0, v121);
    v55 = n;
    v99 = n;
    if ( (_BYTE)n && !v104.Length )
    {
      LOBYTE(n) = v121[0];
      if ( *(_BYTE *)(v121[0] + 8LL) )
      {
        n = -*(_QWORD *)(v121[0] + 40LL);
        LOBYTE(v11) = *(_QWORD *)(v121[0] + 40LL) != 0 ? v55 : 0;
        v55 = v11;
        v99 = v11;
      }
      else if ( !*(_DWORD *)(v121[0] + 16LL) )
      {
        v55 = 0;
        v99 = 0;
      }
    }
    if ( !v55 )
    {
      v36 = 0;
      goto LABEL_244;
    }
    NtfsReleaseFcbEx(a1, v14, 0);
    v98 = 0;
    if ( v100 )
    {
      if ( a1 )
      {
        v108 = 0;
        for ( k = 0; ; ++k )
        {
          v108 = k;
          if ( k >= 2 )
            break;
          v56 = k;
          if ( *(const CLFS_LSN **)(a1 + 8LL * k + 48) == v14 )
            *(_QWORD *)(a1 + 8LL * k + 48) = 0;
        }
      }
      NtfsReleasePagingResourcePriv(v56, v14, v57, v58);
      v97 = 0;
    }
    NtfsFlushFcb(a1, (_DWORD)v9);
    if ( v14[14].ullOffset )
    {
      LOBYTE(v60) = 1;
      NtfsAcquirePagingResourceExclusive(0, v14, v60);
      v109 = 0;
      for ( m = 0; ; ++m )
      {
        v109 = m;
        if ( m >= 2 )
          break;
        v62 = *(const CLFS_LSN **)(a1 + 8LL * m + 48);
        if ( !v62 || v62 == v14 )
        {
          *(_QWORD *)(a1 + 8LL * m + 48) = v14;
          break;
        }
      }
      v97 = 1;
    }
    NtfsAcquireExclusiveFcb(a1, v14, 0, 0);
    v98 = 1;
    v63 = NtfsCreateScb(a1, (__int64)v9, *(_DWORD *)(a3 + 108), &v104, 1, 0, 0);
    v64 = (__int64)v63;
    v115 = (__int64)v63;
    if ( v63 )
    {
      v65 = *((_QWORD *)v63 + 66);
      if ( v65 )
        *(_DWORD *)(v65 + 24) = *(_DWORD *)(v65 + 24);
    }
    v66 = NtfsCreateScb(a1, (__int64)v14, *(_DWORD *)(a3 + 108), &v104, 0, 0, 0);
    v112 = v66;
    NtfsCleanupAttributeContext(v67, v121);
    memset(v121, 0, 0x58u);
    v96 = 1;
    LOBYTE(v95) = 0;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *((_QWORD *)v66 + 23),
                             *((_QWORD *)v66 + 23) + 8LL,
                             *((unsigned int *)v66 + 64),
                             v66 + 132,
                             0,
                             v95,
                             0,
                             0,
                             v121)
      && (*((_DWORD *)v66 + 128) & 4) == 0 )
    {
      v64 = 0xA9003150A6LL;
      NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 3231910, v68, *((_QWORD *)v66 + 23) + 8LL, *((_QWORD *)v66 + 23), 0);
      NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA9003150A6LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 3231910);
      NtfsRaiseStatusInternal(a1, -1073741566, *((_QWORD *)v66 + 23) + 8, *((_QWORD *)v66 + 23), 3231910);
    }
    TxfPrepareToMoveAttribute(a1, (int)v14, (int)v9, v121, 0);
    TxfMoveAttrInternal(a1, (_DWORD)v14, v121, 0, (__int64)&FileObject);
    NtfsConditionallyFixupQuota(a1, v9);
    NtfsConditionallyFixupQuota(a1, v14);
    if ( !v64 )
    {
      v64 = (__int64)NtfsCreateScb(a1, (__int64)v9, *(_DWORD *)(a3 + 108), &v104, 1, 0, 0);
      v115 = v64;
    }
    idxRecord = v9[22].offset.idxRecord;
    v110 = idxRecord;
    v102 = 1;
    if ( !v104.Length )
    {
      if ( *(_BYTE *)(v64 + 460) )
        v71 = idxRecord | 0x800;
      else
        v71 = idxRecord & 0xFFFFF7FF;
      v9[22].offset.idxRecord = v71;
      v9[23].offset.idxRecord |= 4u;
    }
    v72 = v9[22].offset.idxRecord;
    if ( *(__int16 *)(v64 + 460) >= 0 )
    {
      if ( (v72 & 0x200) == 0 )
        goto LABEL_180;
      NtfsCleanupAttributeContext(v69, v121);
      v96 = 0;
      if ( (unsigned __int8)NtfsIsSparseStreamRemaining(a1, (int)v9) )
        goto LABEL_180;
      v9[22].offset.idxRecord &= ~0x200u;
    }
    else
    {
      v9[22].offset.idxRecord = v72 | 0x200;
    }
    v9[23].offset.idxRecord |= 4u;
LABEL_180:
    if ( v9[22].offset.idxRecord != idxRecord )
      NtfsUpdateStandardInformation(a1, (_DWORD)v9);
    if ( ClfsLsnLess(v9 + 30, &v103) )
    {
      v73 = ClfsLsnLess(v9 + 30, &v103);
      TxfUpdateTxfDataAttributeMembers(
        a1,
        (int)v9,
        v92,
        0,
        (v9->offset.cidContainer & 0x100000) == 0,
        (__int64)&v103,
        (unsigned __int64)&v103 & -(__int64)(v73 != 0),
        0,
        0,
        0,
        0);
      v74 = ClfsLsnLess(v14 + 30, &v103);
      TxfUpdateTxfDataAttributeMembers(
        a1,
        (int)v14,
        v93,
        0,
        (v14->offset.cidContainer & 0x100000) == 0,
        (__int64)&v103,
        (unsigned __int64)&v103 & -(__int64)(v74 != 0),
        0,
        0,
        0,
        0);
    }
    LOBYTE(n) = NtfsCheckpointCurrentTransaction(a1);
    v75 = v9[41];
    if ( v75.ullOffset )
    {
      v116 = 0;
      n = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))TxfCreateTxfScb)(
            (const CLFS_LSN)v9[12].ullOffset,
            (CLFS_LSN)v75.ullOffset,
            *(unsigned int *)(a3 + 108),
            &v104,
            1,
            1);
      v76 = n;
      v116 = n;
      if ( n )
      {
        v77 = NtfsCreateScb(a1, (__int64)v9, *(_DWORD *)(a3 + 108), &v104, 1, n, 0);
        if ( v77 )
        {
          if ( v77 != (__int16 *)v64 )
          {
            *(_QWORD *)(v64 + 464) = 0;
            *(_QWORD *)(v64 + 24) = 0;
            if ( (*(_DWORD *)(v64 + 200) & 0x20000) != 0 && *(__int64 *)(v64 + 32) < 0 && *(__int64 *)(v64 + 40) < 0 )
            {
              v78 = *(_DWORD *)(v64 + 200);
              if ( (v78 & 0x20000) != 0 )
              {
                v79 = *(_QWORD *)(v64 + 464);
                if ( v79 < 0 || *(__int64 *)(v64 + 40) > 0 && (!*(_QWORD *)(*(_QWORD *)(v64 + 288) + 16LL) || v79 > 0) )
                  *(_QWORD *)(v64 + 464) = 0;
              }
              *(_QWORD *)(v64 + 40) = 0;
            }
            *(_QWORD *)(v64 + 32) = 0;
            v80 = *(_DWORD *)(v64 + 200);
            if ( (v80 & 0x20000) != 0 )
            {
              v81 = *(_QWORD *)(v64 + 464);
              if ( v81 < 0 || *(__int64 *)(v64 + 40) > 0 && (!*(_QWORD *)(*(_QWORD *)(v64 + 288) + 16LL) || v81 > 0) )
                *(_QWORD *)(v64 + 464) = 0;
            }
            *(_QWORD *)(v64 + 40) = 0;
            *(_DWORD *)(v64 + 256) = 0;
            *(_DWORD *)(v64 + 512) |= 0x40u;
          }
          v64 = (__int64)v77;
          v115 = (__int64)v77;
          *((_DWORD *)v77 + 64) = 128;
          *((_DWORD *)v77 + 128) &= ~0x200000u;
          *(_DWORD *)(v76 + 24) &= 0xFFFFFFF9;
        }
        LOBYTE(n) = TxfDereferenceTxfScb((PVOID)v76);
        if ( v64 )
        {
          ClearFlagInterlocked(v64 + 200, 268960303);
          *(_DWORD *)(v64 + 512) &= 0xFFFEFFBF;
          LOBYTE(n) = NtfsUpdateScbFromAttribute(a1, v64, 0);
        }
      }
      else
      {
        v76 = *(_QWORD *)(v64 + 528);
        v116 = v76;
      }
      if ( v76 )
      {
        v82 = *(_QWORD *)(v76 + 56);
        v83 = v112;
        while ( v82 )
        {
          LODWORD(n) = *(_DWORD *)(v82 + 8);
          if ( (n & 1) != 0 )
            break;
          if ( *(_QWORD *)(v82 + 120) && *(__int16 **)(v82 + 112) == v83 )
          {
            TxfDetachBackupAttributeFromTxfVscb(v82);
            for ( n = *(_QWORD *)(v82 + 40); n; n = *(_QWORD *)(n + 40) )
              _InterlockedOr((volatile signed __int32 *)(n + 8), 0x800u);
          }
          v82 = *(_QWORD *)(v82 + 32);
        }
      }
    }
    if ( v64 )
    {
      v11 = *(_QWORD *)(v64 + 528);
      if ( v11 )
      {
        *(_QWORD *)(v11 + 96) = *(_QWORD *)(v64 + 40);
        *(_QWORD *)(*(_QWORD *)(v64 + 528) + 104LL) = *(_QWORD *)(v64 + 32);
        v11 = *(_QWORD *)(v64 + 528);
        LODWORD(n) = *(_DWORD *)(v11 + 24);
        *(_DWORD *)(v11 + 24) = n;
      }
    }
    v7 = a2;
    goto LABEL_133;
  }
  v36 = 1;
  v37 = *(_QWORD *)(v15 + 24);
  v7 = a2;
  LOBYTE(n) = TxfRebuildMoveAttrIsolationDuringRecovery(
                a1,
                (_DWORD)a2,
                *(_QWORD *)(v13 + 24),
                v37,
                (__int64)&v104,
                (__int64)&v97,
                (__int64)&v98);
LABEL_243:
  v54 = v96;
LABEL_244:
  if ( v101 )
    LOBYTE(n) = NtfsReleaseVcb(a1, *(_QWORD *)(v117.ullOffset + 16));
  if ( v54 )
    LOBYTE(n) = NtfsCleanupAttributeContext(v11, v121);
  v89 = FileObject;
  if ( FileObject )
  {
    if ( FileObject->PrivateCacheMap )
      CcUninitializeCacheMap(FileObject, 0, 0);
    FsContext = v89->FsContext;
    if ( FsContext && (FsContext[50] & 0x4000) == 0 )
    {
      *(_DWORD *)&v89->FileName.Length = 0;
      v89->FileName.Buffer = 0;
    }
    LOBYTE(n) = ObfDereferenceObject(v89);
  }
  if ( (v7[2].offset.idxRecord & 0x1000) != 0 && !v36 )
    LOBYTE(n) = DbgPrintEx(
                  0x82u,
                  0,
                  "%s:%d -- TxF corruption detected, %s == 0x%x",
                  "txftrans.c",
                  21102,
                  "Status",
                  -1073741823);
  return n;
}

```

## disassembly

```asm
0x14010dc54  mov     r11, rsp
0x14010dc57  mov     [r11+20h], r9
0x14010dc5b  mov     [r11+10h], rdx
0x14010dc5f  mov     [r11+8], rcx
0x14010dc63  push    rbx
0x14010dc64  push    rsi
0x14010dc65  push    rdi
0x14010dc66  push    r12
0x14010dc68  push    r13
0x14010dc6a  push    r14
0x14010dc6c  push    r15
0x14010dc6e  sub     rsp, 170h
0x14010dc75  mov     r13, r8
0x14010dc78  mov     r15, rdx
0x14010dc7b  mov     rdi, rcx
0x14010dc7e  mov     rax, [rdx+0D0h]
0x14010dc85  mov     [rsp+1A8h+var_D0], rax
0x14010dc8d  mov     [rsp+1A8h+var_B8], rax
0x14010dc95  xor     esi, esi
0x14010dc97  mov     [r11-0C8h], rsi
0x14010dc9e  mov     [r11-0C0h], rsi
0x14010dca5  mov     [r11-0F8h], rsi
0x14010dcac  mov     [r11-0F0h], rsi
0x14010dcb3  mov     [r11-0E8h], rsi
0x14010dcba  xor     edx, edx; Val
0x14010dcbc  lea     r8d, [rsi+58h]; Size
0x14010dcc0  lea     rcx, [r11-98h]; void *
0x14010dcc7  call    memset
0x14010dccc  mov     [rsp+1A8h+var_138], sil
0x14010dcd1  xorps   xmm0, xmm0
0x14010dcd4  movups  [rsp+1A8h+var_128], xmm0
0x14010dcdc  mov     [rsp+1A8h+FileObject], rsi
0x14010dce4  mov     [rsp+1A8h+var_133], sil
0x14010dce9  mov     [rsp+1A8h+var_137], sil
0x14010dcee  mov     [rsp+1A8h+var_134], sil
0x14010dcf3  mov     [rsp+1A8h+var_136], sil
0x14010dcf8  mov     [rsp+1A8h+arg_10], sil
0x14010dd00  movups  [rsp+1A8h+var_B0], xmm0
0x14010dd08  mov     qword ptr [rsp+1A8h+var_130], rsi
0x14010dd0d  mov     [rsp+1A8h+var_132], sil
0x14010dd12  mov     [rsp+1A8h+var_104], esi
0x14010dd19  cmp     dword ptr [r13+40h], 70h ; 'p'
0x14010dd1e  jnb     short loc_14010DD26
0x14010dd20  call    TxfRaiseBoundsCheckFailure
0x14010dd26  mov     rax, [r13+50h]
0x14010dd2a  mov     qword ptr [rsp+1A8h+var_B0], rax
0x14010dd32  mov     al, [r13+4Ah]
0x14010dd36  and     al, 8
0x14010dd38  lea     rcx, [rsp+1A8h+var_F0]
0x14010dd40  mov     [rsp+1A8h+var_160], rcx
0x14010dd45  lea     rcx, [rsp+1A8h+var_C0]
0x14010dd4d  mov     [rsp+1A8h+var_168], rcx
0x14010dd52  mov     [rsp+1A8h+var_170], rsi
0x14010dd57  mov     byte ptr [rsp+1A8h+var_178], al
0x14010dd5b  mov     ebx, 2
0x14010dd60  mov     [rsp+1A8h+var_180], ebx
0x14010dd64  mov     qword ptr [rsp+1A8h+var_188], rsi
0x14010dd69  lea     r9, [rsp+1A8h+var_B0]
0x14010dd71  mov     r8, r13
0x14010dd74  mov     rdx, r15
0x14010dd77  mov     rcx, rdi
0x14010dd7a  call    TxfOpenFileCheckId
0x14010dd7f  mov     al, [r13+4Ah]
0x14010dd83  and     al, 8
0x14010dd85  lea     r9, [r13+58h]
0x14010dd89  lea     rcx, [rsp+1A8h+var_E8]
0x14010dd91  mov     [rsp+1A8h+var_160], rcx
0x14010dd96  lea     rcx, [rsp+1A8h+var_F8]
0x14010dd9e  mov     [rsp+1A8h+var_168], rcx
0x14010dda3  mov     [rsp+1A8h+var_170], rsi
0x14010dda8  mov     byte ptr [rsp+1A8h+var_178], al
0x14010ddac  mov     [rsp+1A8h+var_180], ebx
0x14010ddb0  mov     qword ptr [rsp+1A8h+var_188], rsi
0x14010ddb5  mov     r8, r13
0x14010ddb8  mov     rdx, r15
0x14010ddbb  mov     rcx, rdi
0x14010ddbe  call    TxfOpenFileCheckId
0x14010ddc3  mov     ebx, eax
0x14010ddc5  cmp     eax, 0C0190038h
0x14010ddca  jz      loc_14010EF58
0x14010ddd0  mov     r12, [rsp+1A8h+var_F0]
0x14010ddd8  test    r12, r12
0x14010dddb  jz      short loc_14010DDEB
0x14010dddd  mov     rcx, [r12+18h]
0x14010dde2  mov     r14, [rcx+0B8h]
0x14010dde9  jmp     short loc_14010DDEE
0x14010ddeb  mov     r14, rsi
0x14010ddee  mov     r15, [rsp+1A8h+var_E8]
0x14010ddf6  test    r15, r15
0x14010ddf9  jz      short loc_14010DE06
0x14010ddfb  mov     rax, [r15+18h]
0x14010ddff  mov     rsi, [rax+0B8h]
0x14010de06  mov     [rsp+1A8h+var_C8], rsi
0x14010de0e  xor     ecx, ecx
0x14010de10  test    r12, r12
0x14010de13  jz      loc_14010DF4F
0x14010de19  test    r15, r15
0x14010de1c  jnz     loc_14010DF46
0x14010de22  lea     rcx, [r14+0F0h]; plsn1
0x14010de29  mov     rdx, [rsp+1A8h+plsn2]; plsn2
0x14010de31  call    cs:__imp_ClfsLsnLess
0x14010de38  nop     dword ptr [rax+rax+00h]
0x14010de3d  xor     ecx, ecx
0x14010de3f  test    al, al
0x14010de41  jz      loc_14010DF46
0x14010de47  mov     [rsp+1A8h+var_178], ebx
0x14010de4b  lea     rsi, aStatus; "Status"
0x14010de52  mov     qword ptr [rsp+1A8h+var_180], rsi
0x14010de57  mov     [rsp+1A8h+var_188], 4ECCh
0x14010de5f  lea     r9, aTxftransC; "txftrans.c"
0x14010de66  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14010de6d  xor     edx, edx; Level
0x14010de6f  mov     ecx, 82h; ComponentId
0x14010de74  call    cs:__imp_DbgPrintEx
0x14010de7b  nop     dword ptr [rax+rax+00h]
0x14010de80  cmp     ebx, 0C0000017h
0x14010de86  jz      loc_14010DF13
0x14010de8c  lea     eax, [rbx+3FFFFF81h]
0x14010de92  cmp     eax, 22h ; '"'
0x14010de95  ja      short loc_14010DEA7
0x14010de97  mov     rdx, 408000001h
0x14010dea1  bt      rdx, rax
0x14010dea5  jb      short loc_14010DF13
0x14010dea7  cmp     ebx, 0C01A002Bh
0x14010dead  jz      short loc_14010DF07
0x14010deaf  cmp     ebx, 0C000026Eh
0x14010deb5  jz      short loc_14010DF07
0x14010deb7  cmp     ebx, 0C0000185h
0x14010debd  jz      short loc_14010DF07
0x14010debf  cmp     ebx, 0C0000148h
0x14010dec5  jz      short loc_14010DF07
0x14010dec7  lea     eax, [rbx+3FFFFF63h]
0x14010decd  cmp     eax, 23h ; '#'
0x14010ded0  ja      short loc_14010DEE2
0x14010ded2  mov     rdx, 800000041h
0x14010dedc  bt      rdx, rax
0x14010dee0  jb      short loc_14010DF07
0x14010dee2  lea     ecx, [rbx+3FFFFFF3h]
0x14010dee8  cmp     ecx, 15h
0x14010deeb  ja      short loc_14010DEF7
0x14010deed  mov     eax, 200043h
0x14010def2  bt      eax, ecx
0x14010def5  jb      short loc_14010DF07
0x14010def7  cmp     ebx, 80000016h
0x14010defd  jz      short loc_14010DF07
0x14010deff  cmp     ebx, 0C01A002Fh
0x14010df05  jnz     short loc_14010DF1D
0x14010df07  mov     rax, cs:TxfData
0x14010df0e  inc     dword ptr [rax+10h]
0x14010df11  jmp     short loc_14010DF1D
0x14010df13  mov     rax, cs:TxfData
0x14010df1a  inc     dword ptr [rax+0Ch]
0x14010df1d  mov     al, cs:NtfsStatusDebugFlags
0x14010df23  test    al, al
0x14010df25  jz      short loc_14010DF39
0x14010df27  mov     r8d, 314ECDh
0x14010df2d  xor     ecx, ecx
0x14010df2f  mov     edx, 0C0000102h
0x14010df34  call    NtfsStatusTraceAndDebugInternal
0x14010df39  mov     r15, [rsp+1A8h+arg_8]
0x14010df41  jmp     loc_14010EF5F
0x14010df46  test    r12, r12
0x14010df49  jnz     loc_14010E075
0x14010df4f  test    r15, r15
0x14010df52  jz      loc_14010E06C
0x14010df58  lea     rcx, [rsi+0F0h]; plsn1
0x14010df5f  mov     rdx, [rsp+1A8h+plsn2]; plsn2
0x14010df67  call    cs:__imp_ClfsLsnLess
0x14010df6e  nop     dword ptr [rax+rax+00h]
0x14010df73  xor     ecx, ecx
0x14010df75  test    al, al
0x14010df77  jz      loc_14010E06C
0x14010df7d  mov     [rsp+1A8h+var_178], ebx
0x14010df81  lea     rsi, aStatus; "Status"
0x14010df88  mov     qword ptr [rsp+1A8h+var_180], rsi
0x14010df8d  mov     [rsp+1A8h+var_188], 4EDAh
0x14010df95  lea     r9, aTxftransC; "txftrans.c"
0x14010df9c  lea     r8, aSDTxfCorruptio; "%s:%d -- TxF corruption detected, %s =="...
0x14010dfa3  xor     edx, edx; Level
0x14010dfa5  mov     ecx, 82h; ComponentId
0x14010dfaa  call    cs:__imp_DbgPrintEx
0x14010dfb1  nop     dword ptr [rax+rax+00h]
0x14010dfb6  cmp     ebx, 0C0000017h
0x14010dfbc  jz      loc_14010E049
0x14010dfc2  lea     eax, [rbx+3FFFFF81h]
0x14010dfc8  cmp     eax, 22h ; '"'
0x14010dfcb  ja      short loc_14010DFDD
0x14010dfcd  mov     rdx, 408000001h
0x14010dfd7  bt      rdx, rax
0x14010dfdb  jb      short loc_14010E049
0x14010dfdd  cmp     ebx, 0C01A002Bh
0x14010dfe3  jz      short loc_14010E03D
0x14010dfe5  cmp     ebx, 0C000026Eh
0x14010dfeb  jz      short loc_14010E03D
0x14010dfed  cmp     ebx, 0C0000185h
0x14010dff3  jz      short loc_14010E03D
0x14010dff5  cmp     ebx, 0C0000148h
0x14010dffb  jz      short loc_14010E03D
0x14010dffd  lea     eax, [rbx+3FFFFF63h]
0x14010e003  cmp     eax, 23h ; '#'
0x14010e006  ja      short loc_14010E018
0x14010e008  mov     rdx, 800000041h
0x14010e012  bt      rdx, rax
0x14010e016  jb      short loc_14010E03D
0x14010e018  lea     ecx, [rbx+3FFFFFF3h]
0x14010e01e  cmp     ecx, 15h
0x14010e021  ja      short loc_14010E02D
0x14010e023  mov     eax, 200043h
0x14010e028  bt      eax, ecx
0x14010e02b  jb      short loc_14010E03D
0x14010e02d  cmp     ebx, 80000016h
0x14010e033  jz      short loc_14010E03D
0x14010e035  cmp     ebx, 0C01A002Fh
0x14010e03b  jnz     short loc_14010E053
0x14010e03d  mov     rax, cs:TxfData
0x14010e044  inc     dword ptr [rax+10h]
0x14010e047  jmp     short loc_14010E053
0x14010e049  mov     rax, cs:TxfData
0x14010e050  inc     dword ptr [rax+0Ch]
0x14010e053  mov     al, cs:NtfsStatusDebugFlags
0x14010e059  test    al, al
0x14010e05b  jz      loc_14010DF39
0x14010e061  mov     r8d, 314EDBh
0x14010e067  jmp     loc_14010DF2D
0x14010e06c  test    r12, r12
0x14010e06f  jz      loc_14010EE46
0x14010e075  test    r15, r15
0x14010e078  jz      loc_14010EE46
0x14010e07e  movzx   eax, word ptr [r13+68h]
0x14010e083  add     ax, ax
0x14010e086  mov     word ptr [rsp+1A8h+var_128+2], ax
0x14010e08e  mov     word ptr [rsp+1A8h+var_128], ax
0x14010e096  jz      short loc_14010E0A2
0x14010e098  movzx   eax, word ptr [r13+6Ah]
0x14010e09d  add     rax, r13
0x14010e0a0  jmp     short loc_14010E0A5
0x14010e0a2  mov     rax, rcx
0x14010e0a5  mov     qword ptr [rsp+1A8h+var_128+8], rax
0x14010e0ad  xor     r8d, r8d
0x14010e0b0  mov     rbx, [rsp+1A8h+var_D0]
0x14010e0b8  mov     rdx, [rbx+10h]
0x14010e0bc  mov     rcx, rdi
0x14010e0bf  call    NtfsAcquireSharedVcb
0x14010e0c4  mov     [rsp+1A8h+var_133], 1
0x14010e0c9  mov     rax, [rbx+10h]
0x14010e0cd  mov     ecx, [rax+4]
0x14010e0d0  test    cl, 1
0x14010e0d3  jnz     short loc_14010E10E
0x14010e0d5  mov     al, cs:NtfsStatusDebugFlags
0x14010e0db  test    al, al
0x14010e0dd  jz      short loc_14010E0F2
0x14010e0df  mov     edx, 0C000026Eh
0x14010e0e4  mov     r8d, 314F0Ch
0x14010e0ea  mov     rcx, rdi
0x14010e0ed  call    NtfsStatusTraceAndDebugInternal
0x14010e0f2  mov     qword ptr [rsp+1A8h+var_188], 314F0Ch
0x14010e0fb  xor     r9d, r9d
0x14010e0fe  xor     r8d, r8d
0x14010e101  mov     edx, 0C000026Eh
0x14010e106  mov     rcx, rdi
0x14010e109  call    NtfsRaiseStatusInternal
0x14010e10e  cmp     dword ptr [r13+6Ch], 80h
0x14010e116  jnz     short loc_14010E195
0x14010e118  xor     ebx, ebx
0x14010e11a  cmp     [rsi+70h], rbx
0x14010e11e  jnz     short loc_14010E14D
0x14010e120  xor     r9d, r9d
0x14010e123  xor     r8d, r8d
0x14010e126  mov     rdx, rsi
0x14010e129  mov     rcx, rdi
0x14010e12c  call    NtfsAcquireExclusiveFcb
0x14010e131  xor     r8d, r8d
0x14010e134  mov     rdx, rsi
0x14010e137  mov     rcx, rdi
0x14010e13a  call    NtfsAddPagingIoToFcb
0x14010e13f  xor     r8d, r8d
0x14010e142  mov     rdx, rsi
0x14010e145  mov     rcx, rdi
0x14010e148  call    NtfsReleaseFcbEx
0x14010e14d  mov     r8b, 1
0x14010e150  mov     rdx, rsi
0x14010e153  mov     rcx, rdi
0x14010e156  call    NtfsAcquirePagingResourceExclusive
0x14010e15b  test    al, al
0x14010e15d  jz      short loc_14010E195
0x14010e15f  mov     [rsp+1A8h+var_118], ebx
0x14010e166  mov     eax, ebx
0x14010e168  mov     [rsp+1A8h+var_118], ebx
0x14010e16f  cmp     eax, 2
0x14010e172  jnb     short loc_14010E195
0x14010e174  mov     edx, eax
0x14010e176  mov     rcx, [rdi+rdx*8+30h]
0x14010e17b  test    rcx, rcx
0x14010e17e  jz      short loc_14010E190
0x14010e180  cmp     rcx, rsi
0x14010e183  jz      short loc_14010E190
0x14010e185  inc     eax
0x14010e187  mov     [rsp+1A8h+var_118], eax
0x14010e18e  jmp     short loc_14010E16F
0x14010e190  mov     [rdi+rdx*8+30h], rsi
  ... truncated ...
```
