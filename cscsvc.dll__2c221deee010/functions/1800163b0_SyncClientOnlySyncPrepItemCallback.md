# SyncClientOnlySyncPrepItemCallback

- ea: `0x1800163b0`
- end: `0x180016efe`
- name: `SyncClientOnlySyncPrepItemCallback`
- size: `2894`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x180015230`
- `0x180015cf0`
- `0x1800163b0`
- `0x180016f10`
- `0x18001855c`
- `0x18001dea0`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x18004ff34`
- `0x18005fa04`
- `0x1800715d8`
- `0x1800743dc`
- `0x180074984`
- `0x1800772e4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180016869`
- `ntdll!RtlNtStatusToDosError` at `0x180016869`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016710`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016710`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800166ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800168b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800168b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800168c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800168c9`

## string_xrefs

- `0x180016c69`: `SyncTreeNewTempNode: Node: 0x%p ParentNode: 0x%p Size: %d`
- `0x180016cb5`: `SyncTreeNewTempNode: 0x%x`
- `0x1800167c8`: `SyncEnumNewTreeTempNode: Ctx: 0x%p NewItem: 0x%p FileNameLength: %d`
- `0x180016cfd`: `SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned %x`
- `0x180016d44`: `SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned a NULL ptr for NewItem!!!`
- `0x180016d99`: `SyncEnumNewTreeTempNode: 0x%x`
- `0x180016a27`: `SyncClientOnlySyncPrepItemCallback: SyncEnumNewTreeTempNode failed with %x`

## pseudocode

```c
__int64 __fastcall SyncClientOnlySyncPrepItemCallback(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  CObjectMonitor *v10; // rax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r8d
  unsigned __int64 v15; // r10
  int v16; // r8d
  int v17; // esi
  unsigned int v18; // edx
  __int64 v19; // r14
  __int64 v20; // r15
  __int64 v21; // r13
  int v22; // r9d
  int v23; // r11d
  int v24; // ecx
  int v25; // ecx
  unsigned int v26; // ebx
  unsigned int v28; // r13d
  int v29; // esi
  __int64 v30; // r15
  SIZE_T v31; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v33; // rax
  _DWORD *v34; // rcx
  unsigned int v35; // r14d
  _DWORD *v36; // rdi
  CObjectMonitor *v37; // rcx
  __int64 v38; // r14
  __int64 v39; // rsi
  __int64 v40; // rbx
  __int64 v41; // rax
  int v42; // r10d
  int v43; // r10d
  __int64 v44; // rdx
  __int64 v45; // r9
  __int64 v46; // [rsp+20h] [rbp-E0h]
  _BYTE v47[8]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v48; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v49[6]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v50; // [rsp+68h] [rbp-98h]
  __int128 v51; // [rsp+80h] [rbp-80h] BYREF
  __int128 v52; // [rsp+90h] [rbp-70h]
  _BYTE v53[96]; // [rsp+A0h] [rbp-60h] BYREF

  v48 = 0;
  v49[0] = 0;
  v47[0] = 0;
  v51 = 0;
  v52 = 0;
  memset(v53, 0, 92);
  v50 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncClientOnlySyncPrepItemCallback: Ctx: 0x%p LocalHdl: 0x%p DummyHdl: 0x%p LocalItem: 0x%p DummyItem: 0x%p ",
      a1,
      a2,
      a3,
      a4,
      a6);
    WPP_SF_qqqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      16,
      WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids,
      a1,
      a2,
      a3,
      a4,
      a6);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepItemCallback: LocalItem should never be NULL!");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    v26 = -1073741811;
    goto LABEL_45;
  }
  v11 = ((unsigned int)(*(_DWORD *)(a4 + 60) + 94) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
  if ( *(_DWORD *)(v11 + a4) != 1542600881 )
  {
    if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepItemCallback: LocalItem does not have a valid cookie");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    v26 = -1073740768;
    goto LABEL_45;
  }
  v12 = *(_QWORD *)(a4 + 24);
  v13 = *(_QWORD *)(a4 + 32);
  v14 = *(_DWORD *)(a4 + 56);
  *((_QWORD *)&v51 + 1) = *(_QWORD *)(a4 + 40);
  *(_DWORD *)&v53[4] = HIDWORD(v50);
  *(_QWORD *)&v51 = 589824;
  *(_QWORD *)&v52 = v13;
  *((_QWORD *)&v52 + 1) = v12;
  *(_DWORD *)v53 = v14;
  memset(&v53[8], 0, 88);
  v15 = v11 + a4 + 8;
  if ( !v15 )
  {
    SyncItemAddOriginalEnumInfo(0, 0, 0, 0, (__int64)&v51);
    goto LABEL_40;
  }
  v16 = *(_DWORD *)v15;
  v17 = *(_DWORD *)(v15 + 64);
  v18 = 0x4000;
  v19 = *(_QWORD *)(v15 + 32);
  v20 = *(_QWORD *)(v15 + 40);
  v21 = *(_QWORD *)(v15 + 56);
  *(_DWORD *)&v53[48] = 0x4000;
  if ( (v16 & 0x20) != 0 )
  {
    v18 = 2113536;
    v22 = 3162112;
    *(_DWORD *)&v53[48] = 2113536;
  }
  else
  {
    v22 = 1064960;
  }
  v23 = v18;
  if ( (v16 & 0x4000) != 0 )
  {
    v18 = v22;
    v23 = v22;
    *(_DWORD *)&v53[48] = v22;
  }
  else
  {
    v22 = v18;
  }
  if ( (v16 & 0x400) != 0 )
  {
    v18 = v22 | 2;
    *(_DWORD *)&v53[48] = v22 | 2;
    v23 = v22 | 2;
  }
  if ( (v16 & 0x10) != 0 )
  {
    v18 = v23 | 0x80;
    *(_DWORD *)&v53[48] = v23 | 0x80;
  }
  if ( (v16 & 1) != 0 )
  {
    v18 |= 8u;
    *(_DWORD *)&v53[48] = v18;
  }
  if ( (v16 & 0x20000) != 0 )
  {
    v18 |= 0x2000000u;
    *(_DWORD *)&v53[48] = v18;
  }
  if ( (v16 & 0x100000) != 0 )
  {
    v18 |= 0x4000000u;
    *(_DWORD *)&v53[48] = v18;
  }
  if ( (v16 & 2) != 0 || (v16 & 4) != 0 )
  {
    v18 |= 4u;
    *(_DWORD *)&v53[48] = v18;
  }
  if ( (v16 & 0x10000) != 0 )
  {
    v18 |= 0x8000000u;
    *(_DWORD *)&v53[48] = v18;
  }
  v24 = *(_DWORD *)&v53[92];
  if ( (v16 & 1) != 0 )
  {
    v24 = *(_DWORD *)&v53[92] | 2;
    *(_DWORD *)&v53[92] |= 2u;
  }
  if ( (v16 & 2) != 0 )
  {
    v24 |= 8u;
    *(_DWORD *)&v53[92] = v24;
  }
  if ( (v16 & 4) != 0 )
    *(_DWORD *)&v53[92] = v24 | 1;
  if ( v15 != -72 )
  {
    if ( (*(_BYTE *)(v15 + 73) & 0x3F) != 0 )
    {
      v18 |= 0x400000u;
      *(_DWORD *)&v53[48] = v18;
    }
    if ( (*(_BYTE *)(v15 + 72) & 0xF) != 0 )
    {
      v18 |= 0x800000u;
      *(_DWORD *)&v53[48] = v18;
    }
    *(_DWORD *)&v53[88] |= 1u;
    if ( v15 != -4 && (v18 & 0x200000) != 0 )
    {
      v42 = *(_DWORD *)(v15 + 8);
      if ( v42 && (v43 = v42 - 1) != 0 )
      {
        if ( (unsigned int)(v43 - 1) > 1 || (v16 & 0x10000) == 0 || (v18 & 0xC00000) != 0 )
          goto LABEL_38;
      }
      else if ( (v18 & 0xC00000) != 0 )
      {
        goto LABEL_38;
      }
      v18 = v18 & 0xFEDFFFFF | 0x1000000;
      *(_DWORD *)&v53[48] = v18;
    }
  }
LABEL_38:
  if ( (v16 & 0x40000) != 0 )
  {
    *(_QWORD *)&v53[56] = v21;
    *(_DWORD *)&v53[48] = v18 | 0x20000;
    *(_QWORD *)&v53[64] = v20;
    *(_QWORD *)&v53[72] = v19;
    *(_DWORD *)&v53[80] = v17;
    *(_DWORD *)&v53[84] = HIDWORD(v50);
  }
LABEL_40:
  SyncItemDetermineSyncState(&v51, v49, v47);
  v25 = *(_DWORD *)(*a1 + 8LL);
  if ( ((v25 & 1) != 0 && (v49[0] & 0x200002) != 0 && !v47[0] || (v25 & 2) != 0 && (v49[0] & 0x8E) != 0)
    && ((v49[0] & 0x100000) == 0 || (v25 & 0x1000) == 0) )
  {
    v26 = SyncEnumNewTreeFullItem((__int64)a1, (void **)&v48, *(_DWORD *)(a4 + 60) + 2);
    if ( v26 || !v48 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
        return v26;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        goto LABEL_45;
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepItemCallback: SyncEnumNewTreeFullItem failed with %x", v26);
      v44 = 19;
      v45 = v26;
      goto LABEL_116;
    }
LABEL_84:
    SyncItemAddStateToItem(a4 + 94, *(unsigned int *)(a4 + 60), &v51);
    v36 = v48;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      LODWORD(v46) = v26;
      SyncTraceOutputInternal(
        L"SyncEnumDefaultItemCallback: Ctx: 0x%p NewItem: 0x%p SyncStatus: 0x%x ItemStatus: 0x%x",
        a1,
        v48,
        0,
        v46);
      WPP_SF_qqDD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        38,
        WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids,
        a1,
        v36,
        0,
        v26);
    }
    v36[1] = RtlNtStatusToDosError(v26);
    SyncItemValidateAndTraceItem(L"SyncEnumDefaultItemCallback: ");
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumAddDirSubnode: DirContext: 0x%p NewSubNode: 0x%p", a1, v36);
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, a1, v36);
      v37 = WPP_GLOBAL_Control;
    }
    v38 = a1[2];
    v39 = a1[1];
    v40 = *(_QWORD *)(*a1 + 16LL);
    if ( v37 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v37 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncTreeAddChildNode: Context: 0x%p Parent: 0x%p LastChild: 0x%p NewChild: 0x%p",
        v40,
        v39,
        a1[2],
        v36);
      WPP_SF_qqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        14,
        WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids,
        v40,
        v39,
        v38,
        v36);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 32));
    v41 = *(_QWORD *)(v39 + 8);
    if ( v41 )
    {
      if ( v38 )
      {
        *(_QWORD *)(v38 + 16) = v36;
      }
      else
      {
        for ( ; *(_QWORD *)(v41 + 16); v41 = *(_QWORD *)(v41 + 16) )
          ;
        *(_QWORD *)(v41 + 16) = v36;
      }
    }
    else
    {
      *(_QWORD *)(v39 + 8) = v36;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v40 + 32));
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncTreeAddChildNode");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids);
    }
    a1[2] = v36;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumAddDirSubnode");
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncEnumDefaultItemCallback: 0x%x", 0);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, 0);
        v10 = WPP_GLOBAL_Control;
      }
    }
    v26 = 0;
    goto LABEL_45;
  }
  if ( !v47[0] )
  {
    v26 = 0;
    if ( (v49[0] & 0x100000) == 0 )
      goto LABEL_44;
  }
  v28 = *(_DWORD *)(a4 + 60) + 2;
  v29 = *(_DWORD *)(*(_QWORD *)(*a1 + 16LL) + 8LL) & 0x400;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: Ctx: 0x%p NewItem: 0x%p FileNameLength: %d", a1, &v48, v28);
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, a1, &v48, v28);
    v10 = WPP_GLOBAL_Control;
  }
  v30 = a1[1];
  v31 = v28 + 216;
  if ( !v29 )
    v31 = v28 + 152;
  if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncTreeNewTempNode: Node: 0x%p ParentNode: 0x%p Size: %d",
      &v48,
      a1[1],
      (unsigned int)v31);
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      16,
      WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids,
      &v48,
      v30,
      v31);
    v10 = WPP_GLOBAL_Control;
  }
  v48 = 0;
  if ( (unsigned int)v31 < 0x98 )
  {
    v26 = -1073741811;
LABEL_80:
    if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned %x", v26);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, v26);
      v10 = WPP_GLOBAL_Control;
    }
    v35 = v26;
    goto LABEL_113;
  }
  TotalAlloc += v31;
  ++NumAlloc;
  ProcessHeap = GetProcessHeap();
  v33 = HeapAlloc(ProcessHeap, 8u, v31);
  v48 = v33;
  v34 = v33;
  v35 = -1073741670;
  if ( v33 )
  {
    v33[17] = v30;
    v26 = 0;
    *v48 |= 0x20000000u;
    *v48 |= 0x80000000;
    v34 = v48;
  }
  else
  {
    v26 = -1073741670;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncTreeNewTempNode: 0x%x", v26);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_423b4d92c1c83c8cb080e269378a479c_Traceguids, v26);
    v34 = v48;
    v10 = WPP_GLOBAL_Control;
  }
  if ( v26 )
    goto LABEL_80;
  if ( v34 )
  {
    if ( v29 )
    {
      SyncItemTraceInitialize(v34, v28 >> 1);
      v34 = v48;
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: 0x%x", 0);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids, 0);
      v34 = v48;
      v10 = WPP_GLOBAL_Control;
    }
    v35 = 0;
    v26 = 0;
    if ( v34 )
    {
      *v34 |= 0x80000000;
      goto LABEL_84;
    }
  }
  else
  {
    if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncEnumNewTreeTempNode: SyncTreeNewTempNode returned a NULL ptr for NewItem!!!");
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    v26 = -1073741670;
  }
LABEL_113:
  if ( v10 == (CObjectMonitor *)&WPP_GLOBAL_Control )
    return v26;
  if ( (*((_BYTE *)v10 + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncClientOnlySyncPrepItemCallback: SyncEnumNewTreeTempNode failed with %x", v35);
    v44 = 20;
    v45 = v35;
LABEL_116:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v44, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, v45);
LABEL_44:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_45:
  if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncClientOnlySyncPrepItemCallback: 0x%x", v26);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 21, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, v26);
  }
  return v26;
}

```

## disassembly

```asm
0x1800163b0  push    rbp
0x1800163b2  push    rbx
0x1800163b3  push    rsi
0x1800163b4  push    rdi
0x1800163b5  push    r12
0x1800163b7  push    r13
0x1800163b9  push    r14
0x1800163bb  push    r15
0x1800163bd  lea     rbp, [rsp-18h]
0x1800163c2  sub     rsp, 118h
0x1800163c9  mov     rax, cs:__security_cookie
0x1800163d0  xor     rax, rsp
0x1800163d3  mov     [rbp+50h+var_50], rax
0x1800163d7  mov     r14, [rbp+50h+arg_28]
0x1800163de  xorps   xmm0, xmm0
0x1800163e1  xor     r13d, r13d
0x1800163e4  mov     rdi, r9
0x1800163e7  movups  [rbp+50h+var_70], xmm0
0x1800163eb  mov     rsi, r8
0x1800163ee  mov     rbx, rdx
0x1800163f1  movups  [rbp+50h+var_70+0Ch], xmm0
0x1800163f5  mov     r12, rcx
0x1800163f8  mov     [rsp+150h+var_108], r13
0x1800163fd  mov     [rsp+150h+var_100], r13d
0x180016402  xor     eax, eax
0x180016404  mov     [rsp+150h+var_110], r13b
0x180016409  movups  [rbp+50h+var_D0], xmm0
0x18001640d  movups  [rbp+50h+var_C0], xmm0
0x180016411  movups  [rbp+50h+var_B0], xmm0
0x180016415  movups  [rbp+50h+var_A0], xmm0
0x180016419  movups  [rbp+50h+var_90], xmm0
0x18001641d  movups  [rbp+50h+var_80], xmm0
0x180016421  movups  [rsp+150h+var_E8], xmm0
0x180016426  mov     rax, cs:WPP_GLOBAL_Control
0x18001642d  lea     r15, WPP_GLOBAL_Control
0x180016434  cmp     rax, r15
0x180016437  jz      short loc_180016443
0x180016439  test    byte ptr [rax+6Ch], 4
0x18001643d  jnz     loc_180016A57
0x180016443  test    rdi, rdi
0x180016446  jz      loc_1800167A0
0x18001644c  mov     r9d, [rdi+3Ch]
0x180016450  add     r9d, 5Eh ; '^'
0x180016454  add     r9, 7
0x180016458  and     r9, 0FFFFFFFFFFFFFFF8h
0x18001645c  cmp     dword ptr [r9+rdi], 5BF238B1h
0x180016464  jnz     loc_18001666D
0x18001646a  mov     rdx, [rdi+18h]
0x18001646e  lea     r10, [rdi+8]
0x180016472  mov     rcx, [rdi+20h]
0x180016476  xorps   xmm0, xmm0
0x180016479  mov     r8d, [rdi+38h]
0x18001647d  xor     eax, eax
0x18001647f  mov     [rbp+50h+var_58], rax
0x180016483  mov     rax, [rdi+28h]
0x180016487  mov     qword ptr [rbp+50h+var_D0+8], rax
0x18001648b  mov     eax, dword ptr [rsp+150h+var_E8+0Ch]
0x18001648f  mov     dword ptr [rbp+50h+var_B0+4], eax
0x180016492  mov     qword ptr [rbp+50h+var_D0], 90000h
0x18001649a  mov     qword ptr [rbp+50h+var_C0], rcx
0x18001649e  mov     qword ptr [rbp+50h+var_C0+8], rdx
0x1800164a2  mov     dword ptr [rbp+50h+var_B0], r8d
0x1800164a6  movups  [rbp+50h+var_B0+8], xmm0
0x1800164aa  movups  [rbp+50h+var_A0+8], xmm0
0x1800164ae  movups  [rbp+50h+var_90+8], xmm0
0x1800164b2  movups  [rbp+50h+var_80+8], xmm0
0x1800164b6  movups  [rbp+50h+var_70+8], xmm0
0x1800164ba  add     r10, r9
0x1800164bd  jz      loc_180016BCB
0x1800164c3  mov     r8d, [r10]
0x1800164c6  lea     rbx, [r10+48h]
0x1800164ca  mov     esi, [r10+40h]
0x1800164ce  mov     edx, 4000h
0x1800164d3  mov     r14, [r10+20h]
0x1800164d7  mov     r15, [r10+28h]
0x1800164db  mov     r13, [r10+38h]
0x1800164df  mov     dword ptr [rbp+50h+var_80], edx
0x1800164e2  test    r8b, 20h
0x1800164e6  jz      loc_180016662
0x1800164ec  mov     edx, 204000h
0x1800164f1  mov     r9d, 304000h
0x1800164f7  mov     dword ptr [rbp+50h+var_80], edx
0x1800164fa  mov     r11d, edx
0x1800164fd  mov     ecx, edx
0x1800164ff  bt      r8d, 0Eh
0x180016504  jb      loc_180016B31
0x18001650a  mov     r9d, edx
0x18001650d  bt      r8d, 0Ah
0x180016512  jb      loc_180016B3F
0x180016518  test    r8b, 10h
0x18001651c  jnz     loc_180016B50
0x180016522  mov     ecx, r8d
0x180016525  and     ecx, 1
0x180016528  jz      short loc_180016530
0x18001652a  or      edx, 8
0x18001652d  mov     dword ptr [rbp+50h+var_80], edx
0x180016530  bt      r8d, 11h
0x180016535  jb      loc_180016B5F
0x18001653b  bt      r8d, 14h
0x180016540  jb      loc_180016B6B
0x180016546  mov     r9d, r8d
0x180016549  and     r9d, 2
0x18001654d  jnz     loc_180016B77
0x180016553  test    r8b, 4
0x180016557  jnz     loc_180016B77
0x18001655d  mov     r11d, r8d
0x180016560  and     r11d, 10000h
0x180016567  jz      short loc_180016570
0x180016569  bts     edx, 1Bh
0x18001656d  mov     dword ptr [rbp+50h+var_80], edx
0x180016570  test    ecx, ecx
0x180016572  mov     ecx, dword ptr [rbp+50h+var_58+4]
0x180016575  jnz     loc_180016B82
0x18001657b  test    r9d, r9d
0x18001657e  jnz     loc_180016B8D
0x180016584  test    r8b, 4
0x180016588  jnz     loc_180016B98
0x18001658e  test    rbx, rbx
0x180016591  jz      short loc_1800165C0
0x180016593  test    byte ptr [rbx+1], 3Fh
0x180016597  lea     r9, [r10+4]
0x18001659b  jz      short loc_1800165A4
0x18001659d  bts     edx, 16h
0x1800165a1  mov     dword ptr [rbp+50h+var_80], edx
0x1800165a4  test    byte ptr [rbx], 0Fh
0x1800165a7  jnz     loc_180016BA3
0x1800165ad  or      dword ptr [rbp+50h+var_58], 1
0x1800165b1  test    r9, r9
0x1800165b4  jz      short loc_1800165C0
0x1800165b6  bt      edx, 15h
0x1800165ba  jb      loc_1800169D0
0x1800165c0  bt      r8d, 12h
0x1800165c5  jnb     short loc_1800165E0
0x1800165c7  bts     edx, 11h
0x1800165cb  mov     qword ptr [rbp+50h+var_80+8], r13
0x1800165cf  mov     dword ptr [rbp+50h+var_80], edx
0x1800165d2  mov     qword ptr [rbp+50h+var_70], r15
0x1800165d6  mov     qword ptr [rbp+50h+var_70+8], r14
0x1800165da  mov     [rbp+50h+var_60], esi
0x1800165dd  mov     [rbp+50h+var_5C], eax
0x1800165e0  xor     r13d, r13d
0x1800165e3  lea     r15, WPP_GLOBAL_Control
0x1800165ea  lea     r8, [rsp+150h+var_110]
0x1800165ef  lea     rdx, [rsp+150h+var_100]
0x1800165f4  lea     rcx, [rbp+50h+var_D0]
0x1800165f8  call    SyncItemDetermineSyncState
0x1800165fd  mov     rdx, [r12]
0x180016601  mov     eax, [rsp+150h+var_100]
0x180016605  movzx   r8d, [rsp+150h+var_110]
0x18001660b  mov     ecx, [rdx+8]
0x18001660e  test    cl, 1
0x180016611  jnz     short loc_18001667D
0x180016613  test    cl, 2
0x180016616  jnz     loc_180016BE8
0x18001661c  test    r8b, r8b
0x18001661f  jnz     short loc_18001668F
0x180016621  mov     ebx, r13d
0x180016624  bt      eax, 14h
0x180016628  jb      short loc_18001668F
0x18001662a  mov     rax, cs:WPP_GLOBAL_Control
0x180016631  cmp     rax, r15
0x180016634  jz      short loc_180016640
0x180016636  test    byte ptr [rax+6Ch], 8
0x18001663a  jnz     loc_180016ECC
0x180016640  mov     eax, ebx
0x180016642  mov     rcx, [rbp+50h+var_50]
0x180016646  xor     rcx, rsp; StackCookie
0x180016649  call    __security_check_cookie
0x18001664e  add     rsp, 118h
0x180016655  pop     r15
0x180016657  pop     r14
0x180016659  pop     r13
0x18001665b  pop     r12
0x18001665d  pop     rdi
0x18001665e  pop     rsi
0x18001665f  pop     rbx
0x180016660  pop     rbp
0x180016661  retn
0x180016662  mov     r9d, 104000h
0x180016668  jmp     loc_1800164FA
0x18001666d  cmp     rax, r15
0x180016670  jnz     loc_180016AF3
0x180016676  mov     ebx, 0C0000420h
0x18001667b  jmp     short loc_180016631
0x18001667d  test    eax, 200002h
0x180016682  jz      short loc_180016613
0x180016684  test    r8b, r8b
0x180016687  jz      loc_180016BF0
0x18001668d  jmp     short loc_180016613
0x18001668f  mov     rax, [rdx+10h]
0x180016693  mov     r13d, [rdi+3Ch]
0x180016697  add     r13d, 2
0x18001669b  mov     esi, [rax+8]
0x18001669e  and     esi, 400h
0x1800166a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800166ab  cmp     rax, r15
0x1800166ae  jnz     loc_1800167B3
0x1800166b4  mov     r15, [r12+8]
0x1800166b9  lea     ecx, [r13+98h]
0x1800166c0  test    esi, esi
0x1800166c2  lea     ebx, [rcx+40h]
0x1800166c5  cmovz   ebx, ecx
0x1800166c8  lea     rcx, WPP_GLOBAL_Control
0x1800166cf  cmp     rax, rcx
0x1800166d2  jz      short loc_1800166DE
0x1800166d4  test    byte ptr [rax+6Ch], 4
0x1800166d8  jnz     loc_180016C5E
0x1800166de  xor     ecx, ecx
0x1800166e0  mov     [rsp+150h+var_108], rcx
0x1800166e5  cmp     ebx, 98h
0x1800166eb  jb      loc_18001680E
0x1800166f1  add     cs:TotalAlloc, rbx
0x1800166f8  inc     cs:NumAlloc
0x1800166ff  call    cs:__imp_GetProcessHeap
0x180016705  mov     r8, rbx; dwBytes
0x180016708  mov     edx, 8; dwFlags
0x18001670d  mov     rcx, rax; hHeap
0x180016710  call    cs:__imp_HeapAlloc
0x180016716  mov     [rsp+150h+var_108], rax
0x18001671b  mov     rcx, rax
0x18001671e  mov     r14d, 0C000009Ah
0x180016724  test    rax, rax
0x180016727  jz      loc_180016CAB
0x18001672d  mov     [rax+88h], r15
0x180016734  xor     ebx, ebx
0x180016736  mov     rax, [rsp+150h+var_108]
0x18001673b  or      dword ptr [rax], 20000000h
0x180016741  mov     rcx, [rsp+150h+var_108]
0x180016746  or      dword ptr [rcx], 80000000h
0x18001674c  mov     rcx, [rsp+150h+var_108]
0x180016751  mov     rax, cs:WPP_GLOBAL_Control
0x180016758  lea     r15, WPP_GLOBAL_Control
0x18001675f  cmp     rax, r15
0x180016762  jz      short loc_18001676E
0x180016764  test    byte ptr [rax+6Ch], 8
0x180016768  jnz     loc_180016CB3
0x18001676e  test    ebx, ebx
0x180016770  jnz     loc_18001681A
0x180016776  test    rcx, rcx
0x180016779  jz      loc_180016D39
0x18001677f  test    esi, esi
0x180016781  jnz     loc_180016D7B
0x180016787  cmp     rax, r15
0x18001678a  jz      short loc_180016796
0x18001678c  test    byte ptr [rax+6Ch], 8
0x180016790  jnz     loc_180016D97
0x180016796  xor     r14d, r14d
0x180016799  xor     ebx, ebx
0x18001679b  jmp     loc_18001682E
0x1800167a0  cmp     rax, r15
0x1800167a3  jnz     loc_180016AB5
0x1800167a9  mov     ebx, 0C000000Dh
0x1800167ae  jmp     loc_180016631
0x1800167b3  test    byte ptr [rax+6Ch], 4
0x1800167b7  jz      loc_1800166B4
0x1800167bd  mov     r9d, r13d
0x1800167c0  lea     r8, [rsp+150h+var_108]
0x1800167c5  mov     rdx, r12
0x1800167c8  lea     rcx, aSyncenumnewtre_0; "SyncEnumNewTreeTempNode: Ctx: 0x%p NewI"...
0x1800167cf  call    SyncTraceOutputInternal
0x1800167d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167db  lea     rax, [rsp+150h+var_108]
0x1800167e0  mov     edx, 12h
0x1800167e5  mov     dword ptr [rsp+150h+var_128], r13d
0x1800167ea  mov     r9, r12
0x1800167ed  mov     [rsp+150h+var_130], rax
0x1800167f2  lea     r8, WPP_eda74469f99236469b6cd48e578a9b4d_Traceguids
0x1800167f9  mov     rcx, [rcx+60h]
0x1800167fd  call    WPP_SF_qqD
0x180016802  mov     rax, cs:WPP_GLOBAL_Control
0x180016809  jmp     loc_1800166B4
0x18001680e  mov     ebx, 0C000000Dh
0x180016813  lea     r15, WPP_GLOBAL_Control
0x18001681a  cmp     rax, r15
0x18001681d  jnz     loc_180016CF1
0x180016823  mov     r14d, ebx
0x180016826  test    ebx, ebx
0x180016828  jnz     loc_180016A11
0x18001682e  test    rcx, rcx
0x180016831  jz      loc_180016A11
0x180016837  or      dword ptr [rcx], 80000000h
0x18001683d  mov     r9, [rsp+150h+var_108]
0x180016842  mov     edx, [rdi+3Ch]
0x180016845  lea     rcx, [rdi+5Eh]
0x180016849  lea     r8, [rbp+50h+var_D0]
0x18001684d  call    SyncItemAddStateToItem
0x180016852  mov     rdi, [rsp+150h+var_108]
0x180016857  mov     rax, cs:WPP_GLOBAL_Control
0x18001685e  cmp     rax, r15
0x180016861  jnz     loc_180016978
0x180016867  mov     ecx, ebx; Status
0x180016869  call    cs:__imp_RtlNtStatusToDosError
0x18001686f  mov     rdx, rdi
0x180016872  lea     rcx, aSyncenumdefaul_3; "SyncEnumDefaultItemCallback: "
0x180016879  mov     [rdi+4], eax
0x18001687c  call    SyncItemValidateAndTraceItem
0x180016881  mov     rcx, cs:WPP_GLOBAL_Control
0x180016888  cmp     rcx, r15
0x18001688b  jz      short loc_180016897
0x18001688d  test    byte ptr [rcx+6Ch], 4
  ... truncated ...
```
