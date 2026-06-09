# SyncFullSyncPrepItemCallback

- ea: `0x180017810`
- end: `0x180018553`
- name: `SyncFullSyncPrepItemCallback`
- size: `3395`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180015230`
- `0x180015a50`
- `0x180016f10`
- `0x180017810`
- `0x18001855c`
- `0x18001dea0`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x18003e928`
- `0x18004fef4`
- `0x18005fa04`
- `0x18007263c`
- `0x1800743dc`
- `0x1800772e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800182a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800182a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018291`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018291`

## string_xrefs

- `0x180017b30`: `Local: Attribute = 0x%08x WriteTime = (0x%08x, 0x%08x) ChangeTime = (0x%08x, 0x%08x) Size = %I64x`
- `0x180017da0`: `Original: Attribute = 0x%08x WriteTime = (0x%08x, 0x%08x) ChangeTime = (0x%08x, 0x%08x) Size = %I64x`
- `0x180017c58`: `Remote: Attribute = 0x%08x WriteTime = (0x%08x, 0x%08x) ChangeTime = (0x%08x, 0x%08x) Size = %I64x`
- `0x180018226`: `SyncTreeNewTempNode: Node: 0x%p ParentNode: 0x%p Size: %d`
- `0x1800182ff`: `SyncTreeNewTempNode: 0x%x`
- `0x1800181ad`: `SyncEnumNewTreeTempNode: Ctx: 0x%p NewItem: 0x%p FileNameLength: %d`
- `0x180018352`: `SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned %x`
- `0x18001845e`: `SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned a NULL ptr for NewItem!!!`
- `0x1800184cc`: `SyncEnumNewTreeTempNode: 0x%x`
- `0x180017d15`: `Ignoring item since it is purely transparently-cached`
- `0x1800183a9`: `SyncFullSyncPrepItemCallback: SyncEnumNewTreeTempNode failed with %x`

## pseudocode

```c
__int64 __fastcall SyncFullSyncPrepItemCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 v7; // r10
  __int64 v8; // rsi
  CObjectMonitor *v11; // rax
  unsigned int v12; // ebx
  unsigned int v13; // r8d
  unsigned int v14; // ebx
  unsigned int v15; // r8d
  char v16; // cl
  int v17; // r8d
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // r14d
  __int64 v23; // r15
  unsigned int v24; // r12d
  unsigned int v25; // r13d
  int v26; // r9d
  int *v27; // r14
  int v28; // ecx
  char v29; // r14
  __int64 v30; // r8
  __int64 v31; // rcx
  unsigned int v32; // r15d
  __int64 v33; // r12
  unsigned int v34; // r13d
  unsigned int v35; // edx
  __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // r15
  unsigned int v39; // r13d
  int v40; // r12d
  _BYTE *v41; // r15
  int v42; // edx
  unsigned int v43; // r8d
  char v44; // cl
  unsigned int v45; // r9d
  int v46; // ecx
  int v47; // r12d
  int v48; // r11d
  int v49; // r10d
  int v50; // ecx
  int *v51; // r14
  int v52; // r9d
  int v53; // r9d
  char v54; // dl
  __int64 v55; // r9
  __int64 v56; // r10
  __int64 v57; // r8
  int v58; // ecx
  __int64 v59; // r8
  __int64 v60; // rdx
  __int64 v61; // r9
  __int64 v62; // rcx
  unsigned int v63; // r13d
  int v64; // r14d
  __int64 v65; // r12
  SIZE_T v66; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v68; // rax
  _DWORD *v69; // rcx
  unsigned int v70; // r15d
  __int64 v72; // r8
  __int64 v73; // [rsp+20h] [rbp-E0h]
  __int64 v74; // [rsp+28h] [rbp-D8h]
  char v75[8]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v76; // [rsp+58h] [rbp-A8h] BYREF
  char v77; // [rsp+60h] [rbp-A0h]
  unsigned int v78; // [rsp+64h] [rbp-9Ch]
  unsigned int v79; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v80; // [rsp+70h] [rbp-90h]
  __int64 v81; // [rsp+80h] [rbp-80h]
  __int64 v82; // [rsp+88h] [rbp-78h]
  __int64 v83; // [rsp+90h] [rbp-70h]
  unsigned int v84; // [rsp+98h] [rbp-68h]
  __int64 v85; // [rsp+A0h] [rbp-60h]
  __int128 v86; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v87; // [rsp+C0h] [rbp-40h]
  __int128 v88; // [rsp+D0h] [rbp-30h]
  __int128 v89; // [rsp+E0h] [rbp-20h]
  __int128 v90; // [rsp+F0h] [rbp-10h]
  __int128 v91; // [rsp+100h] [rbp+0h]
  _OWORD v92[2]; // [rsp+110h] [rbp+10h] BYREF

  v7 = a1;
  v80 = (__int64 *)a1;
  v8 = a4;
  memset(v92, 0, 28);
  v76 = 0;
  v79 = 0;
  v75[0] = 0;
  v83 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncFullSyncPrepItemCallback: Ctx: 0x%p RemoteHdl: 0x%p LocalHdl: 0x%p RemoteItem: 0x%p LocalItem: 0x%p",
      a1,
      a2,
      a3,
      a4,
      a6);
    WPP_SF_qqqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      16,
      WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
      v80,
      a2,
      a3,
      v8,
      a6);
    v11 = WPP_GLOBAL_Control;
    v7 = (__int64)v80;
  }
  if ( a6 )
  {
    if ( !v8 )
      goto LABEL_15;
  }
  else if ( !v8 )
  {
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: It should be impossible for both the RemoteItem and LocalItem to be NULL!");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_9160e5fe847e313a31000d654b474c01_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = -1073741811;
    goto LABEL_164;
  }
  v13 = *(_DWORD *)v8;
  v14 = a5;
  if ( !*(_DWORD *)v8 )
  {
    if ( a5 >= 0x60 )
      goto LABEL_14;
LABEL_25:
    if ( v11 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 108) & 1) == 0 )
      goto LABEL_29;
    SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: Invalid remote buffer! (R: %d NE: %d)", a5);
    v18 = *(_DWORD *)v8;
    v19 = 18;
    goto LABEL_28;
  }
  if ( a5 < v13 || v13 < 0x60 )
    goto LABEL_25;
LABEL_14:
  if ( !a6 )
    goto LABEL_18;
LABEL_15:
  v15 = *(_DWORD *)a6;
  v14 = a7;
  if ( !*(_DWORD *)a6 )
  {
    if ( a7 >= 0xB0 )
      goto LABEL_18;
    goto LABEL_31;
  }
  if ( a7 < v15 || v15 < 0xB0 )
  {
LABEL_31:
    if ( v11 == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 108) & 1) == 0 )
      goto LABEL_29;
    SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: Invalid local buffer! (R: %d NE: %d)", a7);
    v18 = *(_DWORD *)a6;
    v19 = 19;
LABEL_28:
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), v19, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, v14, v18);
    v11 = WPP_GLOBAL_Control;
LABEL_29:
    v12 = -1073741595;
    goto LABEL_164;
  }
LABEL_18:
  v16 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  memset(v92, 0, sizeof(v92));
  if ( !a6 )
  {
    LODWORD(v86) = 0x10000;
    goto LABEL_42;
  }
  v17 = *(_DWORD *)(a6 + 60);
  if ( *(_DWORD *)((((unsigned int)(v17 + 94) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + a6) != 1542600881 )
  {
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: LocalItem does not have a valid cookie");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_9160e5fe847e313a31000d654b474c01_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = -1073740768;
    goto LABEL_164;
  }
  v20 = *(_QWORD *)(a6 + 24);
  v21 = *(_QWORD *)(a6 + 32);
  v22 = *(_DWORD *)(a6 + 56);
  v23 = *(_QWORD *)(a6 + 40);
  v82 = v20;
  v81 = v21;
  v24 = v20;
  v25 = v21;
  if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 2) != 0 )
  {
    LODWORD(v73) = HIDWORD(v21);
    LODWORD(v74) = v21;
    SyncTraceOutputInternal(
      L"Local: Attribute = 0x%08x WriteTime = (0x%08x, 0x%08x) ChangeTime = (0x%08x, 0x%08x) Size = %I64x",
      v22,
      HIDWORD(v20),
      (unsigned int)v20,
      v73,
      v74,
      v23);
    WPP_SF_DDDDDi(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      21,
      WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
      v22,
      HIDWORD(v82),
      v24,
      HIDWORD(v81),
      v25,
      v23);
    v17 = *(_DWORD *)(a6 + 60);
    v11 = WPP_GLOBAL_Control;
    v7 = (__int64)v80;
  }
  v26 = v86 | 0x90000;
  *(_QWORD *)&v88 = __PAIR64__(HIDWORD(v83), v22);
  LODWORD(v86) = v86 | 0x90000;
  *((_QWORD *)&v86 + 1) = v23;
  *(_QWORD *)&v87 = __PAIR64__(HIDWORD(v81), v25);
  *((_QWORD *)&v87 + 1) = __PAIR64__(HIDWORD(v82), v24);
  v27 = (int *)(a6 + (((unsigned int)(v17 + 94) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 8);
  if ( !v27 )
  {
    SyncItemAddOriginalEnumInfo(0, 0, 0, 0, (__int64)&v86);
    v11 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v28 = *v27;
  if ( (*v27 & 0x400000) != 0 && (v28 & 0x80417) == 0 )
  {
    LODWORD(v86) = v26 & 0xFFF7FFFF;
LABEL_41:
    v16 = 0;
    goto LABEL_42;
  }
  if ( (*(_BYTE *)(a6 + 56) & 0x10) != 0
    || (v28 & 0x1000000) == 0 && (v28 & 0x800000) == 0
    || (*(_DWORD *)(*(_QWORD *)v7 + 8LL) & 0x4000) != 0 )
  {
    v36 = *((_QWORD *)v27 + 4);
    v37 = *((_QWORD *)v27 + 5);
    v38 = *((_QWORD *)v27 + 7);
    v39 = v27[16];
    v82 = v36;
    v81 = v37;
    v85 = v38;
    v84 = v36;
    v40 = v36;
    v78 = v37;
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 2) != 0 )
    {
      LODWORD(v73) = HIDWORD(v37);
      LODWORD(v74) = v37;
      SyncTraceOutputInternal(
        L"Original: Attribute = 0x%08x WriteTime = (0x%08x, 0x%08x) ChangeTime = (0x%08x, 0x%08x) Size = %I64x",
        v39,
        v36 >> 32,
        (unsigned int)v36,
        v73,
        v74,
        v38);
      WPP_SF_DDDDDi(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        23,
        WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
        v39,
        HIDWORD(v82),
        v40,
        HIDWORD(v81),
        v78,
        v38);
      v11 = WPP_GLOBAL_Control;
    }
    v41 = v27 + 18;
    v42 = *v27;
    v43 = v91 | 0x4000;
    v44 = *v27;
    LODWORD(v91) = v43;
    v45 = v43;
    v46 = v44 & 0x20;
    if ( v46 )
    {
      v43 |= 0x200000u;
      LODWORD(v91) = v43;
    }
    v47 = v45 | 0x200000;
    if ( !v46 )
      v47 = v45;
    v48 = v45 | 0x200000;
    if ( !v46 )
      v48 = v45;
    v49 = v45 | 0x200000;
    if ( !v46 )
      v49 = v45;
    if ( (v42 & 0x4000) != 0 )
    {
      v43 = v49 | 0x100000;
      LODWORD(v91) = v49 | 0x100000;
      v48 = v49 | 0x100000;
      v47 = v49 | 0x100000;
    }
    if ( (v42 & 0x400) != 0 )
    {
      v43 = v48 | 2;
      LODWORD(v91) = v48 | 2;
      v47 = v48 | 2;
    }
    if ( (v42 & 0x10) != 0 )
    {
      v43 = v47 | 0x80;
      LODWORD(v91) = v47 | 0x80;
    }
    if ( (v42 & 1) != 0 )
    {
      v43 |= 8u;
      LODWORD(v91) = v43;
    }
    if ( (v42 & 0x20000) != 0 )
    {
      v43 |= 0x2000000u;
      LODWORD(v91) = v43;
    }
    if ( (v42 & 0x100000) != 0 )
    {
      v43 |= 0x4000000u;
      LODWORD(v91) = v43;
    }
    if ( (v42 & 2) != 0 || (v42 & 4) != 0 )
    {
      v43 |= 4u;
      LODWORD(v91) = v43;
    }
    if ( (v42 & 0x10000) != 0 )
    {
      v43 |= 0x8000000u;
      LODWORD(v91) = v43;
    }
    v50 = HIDWORD(v92[1]);
    if ( (v42 & 1) != 0 )
    {
      v50 = HIDWORD(v92[1]) | 2;
      HIDWORD(v92[1]) |= 2u;
    }
    if ( (v42 & 2) != 0 )
    {
      v50 |= 8u;
      HIDWORD(v92[1]) = v50;
    }
    if ( (v42 & 4) != 0 )
      HIDWORD(v92[1]) = v50 | 1;
    if ( v27 == (int *)-72LL )
      goto LABEL_104;
    v51 = v27 + 1;
    if ( (v41[1] & 0x3F) != 0 )
    {
      v43 |= 0x400000u;
      LODWORD(v91) = v43;
    }
    if ( (*v41 & 0xF) != 0 )
    {
      v43 |= 0x800000u;
      LODWORD(v91) = v43;
    }
    DWORD2(v92[1]) |= 1u;
    if ( !v51 || (v43 & 0x200000) == 0 )
      goto LABEL_104;
    v52 = v51[1];
    if ( v52 && (v53 = v52 - 1) != 0 )
    {
      if ( (unsigned int)(v53 - 1) > 1 || (v42 & 0x10000) == 0 || (v43 & 0xC00000) != 0 )
      {
LABEL_104:
        if ( (v42 & 0x40000) != 0 )
        {
          *((_QWORD *)&v91 + 1) = v85;
          *(_QWORD *)&v92[0] = __PAIR64__(HIDWORD(v81), v78);
          *((_QWORD *)&v92[0] + 1) = __PAIR64__(HIDWORD(v82), v84);
          LODWORD(v91) = v43 | 0x20000;
          *(_QWORD *)&v92[1] = __PAIR64__(HIDWORD(v83), v39);
        }
        goto LABEL_41;
      }
    }
    else if ( (v43 & 0xC00000) != 0 )
    {
      goto LABEL_104;
    }
    v43 = v43 & 0xFEDFFFFF | 0x1000000;
    LODWORD(v91) = v43;
    goto LABEL_104;
  }
  v16 = 1;
  LODWORD(v86) = v26 & 0xFFF7FFFF;
  v77 = 1;
  if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 2) != 0 )
  {
    SyncTraceOutputInternal(L"Ignoring item since it is purely transparently-cached");
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_9160e5fe847e313a31000d654b474c01_Traceguids);
    v11 = WPP_GLOBAL_Control;
    v16 = v77;
  }
LABEL_42:
  v29 = 0;
  if ( v8 )
  {
    if ( !v16 )
    {
      v30 = *(_QWORD *)(v8 + 24);
      v31 = *(_QWORD *)(v8 + 32);
      v32 = *(_DWORD *)(v8 + 56);
      v33 = *(_QWORD *)(v8 + 40);
      v82 = v30;
      v81 = v31;
      v78 = v31;
      v34 = v30;
      v35 = v31;
      if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 2) != 0 )
      {
        LODWORD(v73) = HIDWORD(v31);
        LODWORD(v74) = v31;
        SyncTraceOutputInternal(
          L"Remote: Attribute = 0x%08x WriteTime = (0x%08x, 0x%08x) ChangeTime = (0x%08x, 0x%08x) Size = %I64x",
          v32,
          v30 >> 32,
          (unsigned int)v30,
          v73,
          v74,
          v33);
        WPP_SF_DDDDDi(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          24,
          WPP_9160e5fe847e313a31000d654b474c01_Traceguids,
          v32,
          HIDWORD(v82),
          v34,
          HIDWORD(v81),
          v78,
          v33);
        v35 = v78;
      }
      DWORD2(v88) |= 0x48000u;
      *(_QWORD *)&v89 = v33;
      *((_QWORD *)&v89 + 1) = __PAIR64__(HIDWORD(v81), v35);
      *(_QWORD *)&v90 = __PAIR64__(HIDWORD(v82), v34);
      *((_QWORD *)&v90 + 1) = __PAIR64__(HIDWORD(v83), v32);
    }
  }
  else
  {
    DWORD2(v88) |= 0x8000u;
  }
  SyncItemDetermineSyncState(&v86, &v79, v75);
  v54 = v75[0];
  v55 = v79;
  if ( v75[0] && (v79 & 0xC00000) != 0 && (v79 & 0x8000000) != 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      SyncTraceOutputInternal(L"Clearing cliend valid info for pinned ghost, Ctx: 0x%p", v80);
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, v80);
      v55 = v79;
      v54 = v75[0];
      v11 = WPP_GLOBAL_Control;
    }
    LODWORD(v86) = v86 & 0xFFF7FFFF;
    v29 = 1;
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
  }
  v56 = (__int64)v80;
  v57 = *v80;
  v58 = *(_DWORD *)(*v80 + 8);
  if ( ((v58 & 1) == 0 || ((v55 & 0x200002) == 0 || v54) && !v29)
    && ((v58 & 2) == 0 || (v55 & 0x8E) == 0)
    && ((v58 & 4) == 0 || (v55 & 0x71) == 0 || (v55 & 0x100000) != 0 && (v58 & 0x1000) != 0) )
  {
    if ( !v54 )
    {
      v12 = 0;
      if ( (v55 & 0x100000) == 0 )
        goto LABEL_164;
    }
    v62 = a6;
    if ( v8 )
      v62 = v8;
    v63 = *(_DWORD *)(v62 + 60) + 2;
    v64 = *(_DWORD *)(*(_QWORD *)(v57 + 16) + 8LL) & 0x400;
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: Ctx: 0x%p NewItem: 0x%p FileNameLength: %d", v80, &v76, v63);
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        18,
        WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids,
        v80,
        &v76,
        v63);
      v11 = WPP_GLOBAL_Control;
      v56 = (__int64)v80;
    }
    v65 = *(_QWORD *)(v56 + 8);
    v66 = v63 + 216;
    if ( !v64 )
      v66 = v63 + 152;
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncTreeNewTempNode: Node: 0x%p ParentNode: 0x%p Size: %d",
        &v76,
        *(_QWORD *)(v56 + 8),
        (unsigned int)v66);
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        16,
        WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids,
        &v76,
        v65,
        v66);
      v11 = WPP_GLOBAL_Control;
    }
    v76 = 0;
    if ( (unsigned int)v66 >= 0x98 )
    {
      TotalAlloc += v66;
      ++NumAlloc;
      ProcessHeap = GetProcessHeap();
      v68 = HeapAlloc(ProcessHeap, 8u, v66);
      v76 = v68;
      v69 = v68;
      v70 = -1073741670;
      if ( v68 )
      {
        v68[17] = v65;
        v12 = 0;
        *v76 |= 0x20000000u;
        *v76 |= 0x80000000;
        v69 = v76;
      }
      else
      {
        v12 = -1073741670;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncTreeNewTempNode: 0x%x", v12);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids, v12);
        v69 = v76;
        v11 = WPP_GLOBAL_Control;
      }
      if ( !v12 )
      {
        if ( v69 )
        {
          if ( v64 )
          {
            SyncItemTraceInitialize(v69, v63 >> 1);
            v69 = v76;
            v11 = WPP_GLOBAL_Control;
          }
          if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 8) != 0 )
          {
            SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: 0x%x", 0);
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, 0);
            v69 = v76;
            v11 = WPP_GLOBAL_Control;
          }
          v70 = 0;
          v12 = 0;
          if ( v69 )
          {
            *v69 |= 0x80000000;
LABEL_180:
            if ( !v8 )
              v8 = a6;
            SyncItemAddStateToItem(v8 + 94, *(unsigned int *)(v8 + 60), &v86);
            v12 = SyncEnumDefaultItemCallback(v80, v76, v72, v12);
            goto LABEL_163;
          }
        }
        else
        {
          if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned a NULL ptr for NewItem!!!");
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
          v12 = -1073741670;
        }
LABEL_159:
        if ( v11 == (CObjectMonitor *)&WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)v11 + 108) & 1) == 0 )
          goto LABEL_164;
        SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: SyncEnumNewTreeTempNode failed with %x", v70, v57, v55);
        v60 = 27;
        v61 = v70;
        goto LABEL_162;
      }
    }
    else
    {
      v12 = -1073741811;
    }
    if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned %x", v12, v57, v55);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, v12);
      v11 = WPP_GLOBAL_Control;
    }
    v70 = v12;
    goto LABEL_159;
  }
  v59 = a6;
  if ( v8 )
    v59 = v8;
  v12 = SyncEnumNewTreeFullItem((__int64)v80, (void **)&v76, *(_DWORD *)(v59 + 60) + 2);
  if ( !v12 && v76 )
    goto LABEL_180;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: SyncEnumNewTreeFullItem failed with %x", v12);
    v60 = 26;
    v61 = v12;
LABEL_162:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v60, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, v61);
LABEL_163:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_164:
  if ( v11 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncFullSyncPrepItemCallback: 0x%x", v12);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_9160e5fe847e313a31000d654b474c01_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180017810  push    rbp
0x180017812  push    rbx
0x180017813  push    rsi
0x180017814  push    rdi
0x180017815  push    r14
0x180017817  lea     rbp, [rsp-60h]
0x18001781c  sub     rsp, 160h
0x180017823  mov     rax, cs:__security_cookie
0x18001782a  xor     rax, rsp
0x18001782d  mov     [rbp+80h+var_50], rax
0x180017831  mov     rdi, [rbp+80h+arg_28]
0x180017838  xorps   xmm0, xmm0
0x18001783b  mov     r10, rcx
0x18001783e  mov     [rsp+180h+var_110], rcx
0x180017843  xor     ecx, ecx
0x180017845  mov     rsi, r9
0x180017848  movups  [rbp+80h+var_70], xmm0
0x18001784c  mov     [rsp+180h+var_128], rcx
0x180017851  xor     eax, eax
0x180017853  mov     [rsp+180h+var_118], ecx
0x180017857  mov     r14, r8
0x18001785a  mov     [rsp+180h+var_130], cl
0x18001785e  mov     rbx, rdx
0x180017861  movups  [rbp+80h+var_70+0Ch], xmm0
0x180017865  mov     [rbp+80h+var_F0], rcx
0x180017869  movups  [rbp+80h+var_D0], xmm0
0x18001786d  movups  [rbp+80h+var_C0], xmm0
0x180017871  movups  [rbp+80h+var_B0], xmm0
0x180017875  movups  [rbp+80h+var_A0], xmm0
0x180017879  movups  [rbp+80h+var_90], xmm0
0x18001787d  movups  [rbp+80h+var_80], xmm0
0x180017881  mov     rax, cs:WPP_GLOBAL_Control
0x180017888  lea     r11, WPP_GLOBAL_Control
0x18001788f  cmp     rax, r11
0x180017892  jz      short loc_180017901
0x180017894  test    byte ptr [rax+6Ch], 4
0x180017898  jz      short loc_180017901
0x18001789a  mov     [rsp+180h+var_158], rdi
0x18001789f  lea     rcx, aSyncfullsyncpr_6; "SyncFullSyncPrepItemCallback: Ctx: 0x%p"...
0x1800178a6  mov     [rsp+180h+var_160], r9
0x1800178ab  mov     r9, r8
0x1800178ae  mov     r8, rdx
0x1800178b1  mov     rdx, r10
0x1800178b4  call    SyncTraceOutputInternal
0x1800178b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178c0  lea     r8, WPP_9160e5fe847e313a31000d654b474c01_Traceguids
0x1800178c7  mov     r9, [rsp+180h+var_110]
0x1800178cc  mov     edx, 10h
0x1800178d1  mov     [rsp+180h+var_148], rdi
0x1800178d6  mov     [rsp+180h+var_150], rsi
0x1800178db  mov     rcx, [rcx+60h]
0x1800178df  mov     [rsp+180h+var_158], r14
0x1800178e4  mov     [rsp+180h+var_160], rbx
0x1800178e9  call    WPP_SF_qqqqq
0x1800178ee  mov     rax, cs:WPP_GLOBAL_Control
0x1800178f5  lea     r11, WPP_GLOBAL_Control
0x1800178fc  mov     r10, [rsp+180h+var_110]
0x180017901  mov     [rsp+180h+var_28], r12
0x180017909  mov     [rsp+180h+var_30], r13
0x180017911  mov     [rsp+180h+var_38], r15
0x180017919  test    rdi, rdi
0x18001791c  jnz     short loc_18001796E
0x18001791e  test    rsi, rsi
0x180017921  jnz     short loc_180017973
0x180017923  cmp     rax, r11
0x180017926  jz      short loc_180017964
0x180017928  test    byte ptr [rax+6Ch], 1
0x18001792c  jz      short loc_180017964
0x18001792e  lea     rcx, aSyncfullsyncpr_2; "SyncFullSyncPrepItemCallback: It should"...
0x180017935  call    SyncTraceOutputInternal
0x18001793a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017941  lea     r8, WPP_9160e5fe847e313a31000d654b474c01_Traceguids
0x180017948  mov     edx, 11h
0x18001794d  mov     rcx, [rcx+60h]
0x180017951  call    WPP_SF_
0x180017956  mov     rax, cs:WPP_GLOBAL_Control
0x18001795d  lea     r11, WPP_GLOBAL_Control
0x180017964  mov     ebx, 0C000000Dh
0x180017969  jmp     loc_1800183E2
0x18001796e  test    rsi, rsi
0x180017971  jz      short loc_18001799D
0x180017973  mov     r8d, [rsi]
0x180017976  mov     ebx, [rbp+80h+arg_20]
0x18001797c  test    r8d, r8d
0x18001797f  jz      loc_180017A5E
0x180017985  cmp     ebx, r8d
0x180017988  jb      loc_180017A67
0x18001798e  cmp     r8d, 60h ; '`'
0x180017992  jb      loc_180017A67
0x180017998  test    rdi, rdi
0x18001799b  jz      short loc_1800179C5
0x18001799d  mov     r8d, [rdi]
0x1800179a0  mov     ebx, [rbp+80h+arg_30]
0x1800179a6  test    r8d, r8d
0x1800179a9  jz      loc_180017ABD
0x1800179af  cmp     ebx, r8d
0x1800179b2  jb      loc_180017AC9
0x1800179b8  cmp     r8d, 0B0h
0x1800179bf  jb      loc_180017AC9
0x1800179c5  mov     ebx, dword ptr [rbp+80h+var_F0+4]
0x1800179c8  xorps   xmm0, xmm0
0x1800179cb  xor     cl, cl
0x1800179cd  movups  [rbp+80h+var_D0], xmm0
0x1800179d1  movups  [rbp+80h+var_C0], xmm0
0x1800179d5  movups  [rbp+80h+var_B0], xmm0
0x1800179d9  movups  [rbp+80h+var_A0], xmm0
0x1800179dd  movups  [rbp+80h+var_90], xmm0
0x1800179e1  movups  [rbp+80h+var_80], xmm0
0x1800179e5  movups  [rbp+80h+var_70], xmm0
0x1800179e9  movups  [rbp+80h+var_60], xmm0
0x1800179ed  test    rdi, rdi
0x1800179f0  jz      loc_180017FEB
0x1800179f6  mov     r8d, [rdi+3Ch]
0x1800179fa  lea     edx, [r8+5Eh]
0x1800179fe  add     rdx, 7
0x180017a02  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180017a06  cmp     dword ptr [rdx+rdi], 5BF238B1h
0x180017a0d  jz      loc_180017AEB
0x180017a13  cmp     rax, r11
0x180017a16  jz      short loc_180017A54
0x180017a18  test    byte ptr [rax+6Ch], 1
0x180017a1c  jz      short loc_180017A54
0x180017a1e  lea     rcx, aSyncfullsyncpr_11; "SyncFullSyncPrepItemCallback: LocalItem"...
0x180017a25  call    SyncTraceOutputInternal
0x180017a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a31  lea     r8, WPP_9160e5fe847e313a31000d654b474c01_Traceguids
0x180017a38  mov     edx, 14h
0x180017a3d  mov     rcx, [rcx+60h]
0x180017a41  call    WPP_SF_
0x180017a46  mov     rax, cs:WPP_GLOBAL_Control
0x180017a4d  lea     r11, WPP_GLOBAL_Control
0x180017a54  mov     ebx, 0C0000420h
0x180017a59  jmp     loc_1800183E2
0x180017a5e  cmp     ebx, 60h ; '`'
0x180017a61  jnb     loc_180017998
0x180017a67  cmp     rax, r11
0x180017a6a  jz      short loc_180017AB3
0x180017a6c  test    byte ptr [rax+6Ch], 1
0x180017a70  jz      short loc_180017AB3
0x180017a72  mov     edx, ebx
0x180017a74  lea     rcx, aSyncfullsyncpr_9; "SyncFullSyncPrepItemCallback: Invalid r"...
0x180017a7b  call    SyncTraceOutputInternal
0x180017a80  mov     eax, [rsi]
0x180017a82  mov     edx, 12h
0x180017a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a8e  lea     r8, WPP_9160e5fe847e313a31000d654b474c01_Traceguids
0x180017a95  mov     r9d, ebx
0x180017a98  mov     dword ptr [rsp+180h+var_160], eax
0x180017a9c  mov     rcx, [rcx+60h]
0x180017aa0  call    WPP_SF_dd
0x180017aa5  mov     rax, cs:WPP_GLOBAL_Control
0x180017aac  lea     r11, WPP_GLOBAL_Control
0x180017ab3  mov     ebx, 0C00000E5h
0x180017ab8  jmp     loc_1800183E2
0x180017abd  cmp     ebx, 0B0h
0x180017ac3  jnb     loc_1800179C5
0x180017ac9  cmp     rax, r11
0x180017acc  jz      short loc_180017AB3
0x180017ace  test    byte ptr [rax+6Ch], 1
0x180017ad2  jz      short loc_180017AB3
0x180017ad4  mov     edx, ebx
0x180017ad6  lea     rcx, aSyncfullsyncpr_24; "SyncFullSyncPrepItemCallback: Invalid l"...
0x180017add  call    SyncTraceOutputInternal
0x180017ae2  mov     eax, [rdi]
0x180017ae4  mov     edx, 13h
0x180017ae9  jmp     short loc_180017A87
0x180017aeb  mov     rcx, [rdi+18h]
0x180017aef  mov     rdx, [rdi+20h]
0x180017af3  mov     r14d, [rdi+38h]
0x180017af7  mov     r15, [rdi+28h]
0x180017afb  mov     [rbp+80h+var_F8], rcx
0x180017aff  mov     [rbp+80h+var_100], rdx
0x180017b03  mov     r12d, ecx
0x180017b06  mov     r13d, edx
0x180017b09  cmp     rax, r11
0x180017b0c  jz      loc_180017B96
0x180017b12  test    byte ptr [rax+6Ch], 2
0x180017b16  jz      short loc_180017B96
0x180017b18  sar     rdx, 20h
0x180017b1c  mov     r9d, r12d
0x180017b1f  sar     rcx, 20h
0x180017b23  mov     [rsp+180h+var_150], r15
0x180017b28  mov     r8d, ecx
0x180017b2b  mov     dword ptr [rsp+180h+var_158], r13d
0x180017b30  lea     rcx, aLocalAttribute; "Local: Attribute = 0x%08x WriteTime = ("...
0x180017b37  mov     dword ptr [rsp+180h+var_160], edx
0x180017b3b  mov     edx, r14d
0x180017b3e  call    SyncTraceOutputInternal
0x180017b43  mov     eax, dword ptr [rbp+80h+var_100+4]
0x180017b46  lea     r8, WPP_9160e5fe847e313a31000d654b474c01_Traceguids
0x180017b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b54  mov     edx, 15h
0x180017b59  mov     [rsp+180h+var_140], r15
0x180017b5e  mov     r9d, r14d
0x180017b61  mov     dword ptr [rsp+180h+var_148], r13d
0x180017b66  mov     dword ptr [rsp+180h+var_150], eax
0x180017b6a  mov     eax, dword ptr [rbp+80h+var_F8+4]
0x180017b6d  mov     rcx, [rcx+60h]
0x180017b71  mov     dword ptr [rsp+180h+var_158], r12d
0x180017b76  mov     dword ptr [rsp+180h+var_160], eax
0x180017b7a  call    WPP_SF_DDDDDi
0x180017b7f  mov     r8d, [rdi+3Ch]
0x180017b83  lea     r11, WPP_GLOBAL_Control
0x180017b8a  mov     rax, cs:WPP_GLOBAL_Control
0x180017b91  mov     r10, [rsp+180h+var_110]
0x180017b96  mov     r9d, dword ptr [rbp+80h+var_D0]
0x180017b9a  mov     ecx, dword ptr [rbp+80h+var_100+4]
0x180017b9d  or      r9d, 90000h
0x180017ba4  mov     dword ptr [rbp+80h+var_B0], r14d
0x180017ba8  lea     r14d, [r8+5Eh]
0x180017bac  add     r14, 7
0x180017bb0  mov     dword ptr [rbp+80h+var_C0+4], ecx
0x180017bb3  mov     ecx, dword ptr [rbp+80h+var_F8+4]
0x180017bb6  and     r14, 0FFFFFFFFFFFFFFF8h
0x180017bba  add     r14, 8
0x180017bbe  mov     dword ptr [rbp+80h+var_D0], r9d
0x180017bc2  mov     qword ptr [rbp+80h+var_D0+8], r15
0x180017bc6  mov     dword ptr [rbp+80h+var_C0], r13d
0x180017bca  mov     dword ptr [rbp+80h+var_C0+8], r12d
0x180017bce  mov     dword ptr [rbp+80h+var_C0+0Ch], ecx
0x180017bd1  mov     dword ptr [rbp+80h+var_B0+4], ebx
0x180017bd4  add     r14, rdi
0x180017bd7  jz      loc_180017FC0
0x180017bdd  mov     ecx, [r14]
0x180017be0  bt      ecx, 16h
0x180017be4  jnb     loc_180017CD5
0x180017bea  test    ecx, 80417h
0x180017bf0  jnz     loc_180017CD5
0x180017bf6  btr     r9d, 13h
0x180017bfb  mov     dword ptr [rbp+80h+var_D0], r9d
0x180017bff  xor     cl, cl
0x180017c01  xor     r14b, r14b
0x180017c04  test    rsi, rsi
0x180017c07  jz      loc_180017FF7
0x180017c0d  test    cl, cl
0x180017c0f  jnz     loc_180017FFE
0x180017c15  mov     r8, [rsi+18h]
0x180017c19  mov     rcx, [rsi+20h]
0x180017c1d  mov     r15d, [rsi+38h]
0x180017c21  mov     r12, [rsi+28h]
0x180017c25  mov     [rbp+80h+var_F8], r8
0x180017c29  mov     [rbp+80h+var_100], rcx
0x180017c2d  mov     [rsp+180h+var_11C], ecx
0x180017c31  mov     r13d, r8d
0x180017c34  mov     edx, ecx
0x180017c36  cmp     rax, r11
0x180017c39  jz      short loc_180017CAB
0x180017c3b  test    byte ptr [rax+6Ch], 2
0x180017c3f  jz      short loc_180017CAB
0x180017c41  sar     rcx, 20h
0x180017c45  mov     r9d, r13d
0x180017c48  mov     [rsp+180h+var_150], r12
0x180017c4d  mov     dword ptr [rsp+180h+var_158], edx
0x180017c51  mov     edx, r15d
0x180017c54  mov     dword ptr [rsp+180h+var_160], ecx
0x180017c58  lea     rcx, aRemoteAttribut; "Remote: Attribute = 0x%08x WriteTime = "...
0x180017c5f  sar     r8, 20h
0x180017c63  call    SyncTraceOutputInternal
0x180017c68  mov     eax, [rsp+180h+var_11C]
0x180017c6c  lea     r8, WPP_9160e5fe847e313a31000d654b474c01_Traceguids
0x180017c73  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c7a  mov     edx, 18h
0x180017c7f  mov     [rsp+180h+var_140], r12
0x180017c84  mov     r9d, r15d
0x180017c87  mov     dword ptr [rsp+180h+var_148], eax
0x180017c8b  mov     eax, dword ptr [rbp+80h+var_100+4]
0x180017c8e  mov     rcx, [rcx+60h]
0x180017c92  mov     dword ptr [rsp+180h+var_150], eax
0x180017c96  mov     eax, dword ptr [rbp+80h+var_F8+4]
0x180017c99  mov     dword ptr [rsp+180h+var_158], r13d
0x180017c9e  mov     dword ptr [rsp+180h+var_160], eax
0x180017ca2  call    WPP_SF_DDDDDi
0x180017ca7  mov     edx, [rsp+180h+var_11C]
0x180017cab  mov     eax, dword ptr [rbp+80h+var_100+4]
0x180017cae  or      dword ptr [rbp+80h+var_B0+8], 48000h
0x180017cb5  mov     dword ptr [rbp+80h+var_A0+0Ch], eax
0x180017cb8  mov     eax, dword ptr [rbp+80h+var_F8+4]
0x180017cbb  mov     dword ptr [rbp+80h+var_90+4], eax
0x180017cbe  mov     qword ptr [rbp+80h+var_A0], r12
0x180017cc2  mov     dword ptr [rbp+80h+var_A0+8], edx
0x180017cc5  mov     dword ptr [rbp+80h+var_90], r13d
0x180017cc9  mov     dword ptr [rbp+80h+var_90+8], r15d
0x180017ccd  mov     dword ptr [rbp+80h+var_90+0Ch], ebx
0x180017cd0  jmp     loc_180017FFE
0x180017cd5  test    byte ptr [rdi+38h], 10h
0x180017cd9  jnz     short loc_180017D55
0x180017cdb  bt      ecx, 18h
0x180017cdf  jb      short loc_180017CE7
0x180017ce1  bt      ecx, 17h
0x180017ce5  jnb     short loc_180017D55
0x180017ce7  mov     rcx, [r10]
0x180017cea  test    dword ptr [rcx+8], 4000h
0x180017cf1  jnz     short loc_180017D55
0x180017cf3  btr     r9d, 13h
0x180017cf8  mov     cl, 1
0x180017cfa  mov     dword ptr [rbp+80h+var_D0], r9d
0x180017cfe  mov     [rsp+180h+var_120], cl
0x180017d02  cmp     rax, r11
0x180017d05  jz      loc_180017C01
0x180017d0b  test    byte ptr [rax+6Ch], 2
  ... truncated ...
```
