# VIDMM_RECYCLE_MULTIRANGE::MergeWithNeighborsIfPossible(void)

- ea: `0x1400f4cb0`
- end: `0x1400f5945`
- name: `?MergeWithNeighborsIfPossible@VIDMM_RECYCLE_MULTIRANGE@@QEAAPEAV1@XZ`
- size: `3221`
- prototype: `struct VIDMM_RECYCLE_MULTIRANGE *__fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f210c`

## callees

- `0x140031450`
- `0x1400f0670`
- `0x1400f1ffc`
- `0x1400f4cb0`
- `0x1400f5950`
- `0x1400f598c`
- `0x1400f5a58`
- `0x1400f5be0`
- `0x1400f681c`

## import_xrefs

- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f4fcc`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f548a`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f4fcc`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f548a`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400f5140`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400f5140`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f4e11`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f4e67`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f527d`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f52d3`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f5329`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f4e11`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f4e67`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f527d`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f52d3`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f5329`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f520e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f5629`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f520e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f5629`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f51db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f51f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f55db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f55f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f5611`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f51db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f51f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f55db`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f55f6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f5611`
- `watchdog!WdLogSingleEntry2` at `0x1400f4de1`
- `watchdog!WdLogSingleEntry2` at `0x1400f4e37`
- `watchdog!WdLogSingleEntry2` at `0x1400f508d`
- `watchdog!WdLogSingleEntry2` at `0x1400f524d`
- `watchdog!WdLogSingleEntry2` at `0x1400f52a3`
- `watchdog!WdLogSingleEntry2` at `0x1400f52f9`
- `watchdog!WdLogSingleEntry2` at `0x1400f4de1`
- `watchdog!WdLogSingleEntry2` at `0x1400f4e37`
- `watchdog!WdLogSingleEntry2` at `0x1400f508d`
- `watchdog!WdLogSingleEntry2` at `0x1400f524d`
- `watchdog!WdLogSingleEntry2` at `0x1400f52a3`
- `watchdog!WdLogSingleEntry2` at `0x1400f52f9`
- `watchdog!WdLogSingleEntry5` at `0x1400f56a9`
- `watchdog!WdLogSingleEntry5` at `0x1400f56e9`
- `watchdog!WdLogSingleEntry5` at `0x1400f5729`
- `watchdog!WdLogSingleEntry5` at `0x1400f5769`
- `watchdog!WdLogSingleEntry5` at `0x1400f57a9`
- `watchdog!WdLogSingleEntry5` at `0x1400f57f1`
- `watchdog!WdLogSingleEntry5` at `0x1400f5831`
- `watchdog!WdLogSingleEntry5` at `0x1400f589b`
- `watchdog!WdLogSingleEntry5` at `0x1400f58db`
- `watchdog!WdLogSingleEntry5` at `0x1400f56a9`
- `watchdog!WdLogSingleEntry5` at `0x1400f56e9`
- `watchdog!WdLogSingleEntry5` at `0x1400f5729`
- `watchdog!WdLogSingleEntry5` at `0x1400f5769`
- `watchdog!WdLogSingleEntry5` at `0x1400f57a9`
- `watchdog!WdLogSingleEntry5` at `0x1400f57f1`
- `watchdog!WdLogSingleEntry5` at `0x1400f5831`
- `watchdog!WdLogSingleEntry5` at `0x1400f589b`
- `watchdog!WdLogSingleEntry5` at `0x1400f58db`
- `watchdog!WdLogSingleEntry1` at `0x1400f4f7d`
- `watchdog!WdLogSingleEntry1` at `0x1400f5435`
- `watchdog!WdLogSingleEntry1` at `0x1400f4f7d`
- `watchdog!WdLogSingleEntry1` at `0x1400f5435`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f567f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f56bf`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f56ff`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f573f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f577f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f57c7`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f5807`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f5874`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f58b1`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
struct VIDMM_RECYCLE_MULTIRANGE *__fastcall VIDMM_RECYCLE_MULTIRANGE::MergeWithNeighborsIfPossible(_QWORD *Entry)
{
  _QWORD *v1; // rbx
  __int64 v2; // r12
  _QWORD *v3; // r14
  __int64 v4; // rax
  int v5; // r15d
  _QWORD *v6; // rsi
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rax
  __int64 v14; // r12
  __int64 v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rdi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  _QWORD *v25; // r9
  unsigned int v26; // r8d
  CCHAR v27; // al
  __int64 v28; // rax
  __int64 v29; // rcx
  char v30; // cl
  int v31; // edx
  __int64 v32; // rdx
  _QWORD *v33; // rdi
  __int64 v34; // r8
  _QWORD *v35; // rsi
  struct _RTL_BALANCED_NODE *v36; // rdi
  struct _RTL_BALANCED_NODE *v37; // rax
  int v38; // edx
  struct _RTL_BALANCED_NODE *v39; // rax
  __int64 v40; // r13
  __int64 v41; // rcx
  __int64 v42; // r13
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // r13
  __int64 v46; // rcx
  __int64 v47; // r13
  __int64 v48; // rax
  __int64 v49; // rdi
  __int64 v50; // rax
  __int64 v51; // rdi
  __int64 v52; // rax
  __int64 v53; // rdi
  int v54; // eax
  __int64 v55; // rax
  CCHAR LeastSignificantBit; // al
  __int64 v57; // rdi
  __int64 v58; // rcx
  struct VIDMM_RECYCLE_RANGE *v59; // rdi
  struct _RTL_BALANCED_NODE *v60; // rax
  __int64 v61; // [rsp+30h] [rbp-78h]
  __int64 v62; // [rsp+38h] [rbp-70h]
  __int64 v63; // [rsp+40h] [rbp-68h]
  _QWORD v64[2]; // [rsp+48h] [rbp-60h] BYREF
  char v65; // [rsp+58h] [rbp-50h]
  _QWORD *v66; // [rsp+68h] [rbp-40h]
  __int64 v67; // [rsp+78h] [rbp-30h]
  _QWORD *v68; // [rsp+80h] [rbp-28h]
  _QWORD *v69; // [rsp+B0h] [rbp+8h]
  __int64 v70; // [rsp+B0h] [rbp+8h]
  __int64 v71; // [rsp+B8h] [rbp+10h]
  __int64 v72; // [rsp+B8h] [rbp+10h]
  _QWORD *v73; // [rsp+C0h] [rbp+18h]
  __int64 v74; // [rsp+C8h] [rbp+20h]

  v4 = Entry[8];
  v5 = *((_DWORD *)Entry + 36);
  v6 = Entry;
  v7 = 0;
  v8 = *(_QWORD *)(v4 + 128);
  if ( v8 != *(_QWORD *)(v4 + 72) + 72LL )
  {
    v9 = (_QWORD *)(v8 - 120);
    if ( v8 != 120 )
    {
      if ( v5 == 1 )
      {
        v7 = (_QWORD *)v9[18];
      }
      else if ( v5 )
      {
        if ( v5 != 2 )
        {
          g_DxgMmsBugcheckExportIndex = 1;
          WdLogSingleEntry5(0, 270, 52);
          WdLogGlobalForLineNumber = 222;
          goto LABEL_121;
        }
        v7 = (_QWORD *)v9[19];
      }
      else
      {
        v7 = (_QWORD *)v9[17];
      }
    }
  }
  v10 = v6[9];
  v68 = v1;
  v1 = 0;
  v11 = *(_QWORD *)(v10 + 120);
  if ( v11 != *(_QWORD *)(v10 + 72) + 72LL )
  {
    v12 = (_QWORD *)(v11 - 120);
    if ( v11 != 120 )
    {
      switch ( v5 )
      {
        case 1:
          v1 = (_QWORD *)v12[18];
          goto LABEL_13;
        case 0:
          v1 = (_QWORD *)v12[17];
          goto LABEL_13;
        case 2:
          v1 = (_QWORD *)v12[19];
          goto LABEL_13;
      }
LABEL_121:
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 52);
      WdLogGlobalForLineNumber = 222;
      goto LABEL_122;
    }
  }
LABEL_13:
  v67 = v2;
  v66 = v3;
  v3 = (_QWORD *)v6[10];
  if ( v7 )
  {
    if ( !v1 )
    {
      v1 = v6;
      goto LABEL_23;
    }
    v2 = *((int *)v6 + 22);
    v40 = v3[4];
    v73 = (_QWORD *)v7[8];
    v74 = v1[9];
    WdLogSingleEntry2(4, v7, v2);
    WdLogGlobalForLineNumber = 8471;
    switch ( (_DWORD)v2 )
    {
      case 2:
        v41 = v40 + 64;
        goto LABEL_76;
      case 0:
        v41 = v40 + 48;
        goto LABEL_76;
      case 1:
        v41 = v40 + 56;
LABEL_76:
        RtlAvlRemoveNode(v41, v7);
        *((_DWORD *)v7 + 22) = 3;
        v42 = *(_QWORD *)(v6[10] + 32LL);
        WdLogSingleEntry2(4, v6, v2);
        WdLogGlobalForLineNumber = 8471;
        if ( (_DWORD)v2 == 2 )
        {
          v43 = v42 + 64;
        }
        else if ( (_DWORD)v2 )
        {
          v43 = v42 + 56;
        }
        else
        {
          v43 = v42 + 48;
        }
        RtlAvlRemoveNode(v43, v6);
        v44 = v6[10];
        *((_DWORD *)v6 + 22) = 3;
        v45 = *(_QWORD *)(v44 + 32);
        WdLogSingleEntry2(4, v1, v2);
        WdLogGlobalForLineNumber = 8471;
        if ( (_DWORD)v2 == 2 )
        {
          v46 = v45 + 64;
        }
        else if ( (_DWORD)v2 )
        {
          v46 = v45 + 56;
        }
        else
        {
          v46 = v45 + 48;
        }
        RtlAvlRemoveNode(v46, v1);
        *((_DWORD *)v1 + 22) = 3;
        v70 = v7[4];
        v72 = v1[5];
        v47 = *(_QWORD *)(v3[4] + 8LL);
        VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v7);
        v48 = *(unsigned int *)(v47 + 1620);
        if ( (unsigned int)v48 >= 4 )
        {
          ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v47 + 1320), v7);
        }
        else
        {
          *(_QWORD *)(v47 + 8 * v48 + 1656) = v7;
          ++*(_DWORD *)(v47 + 1620);
        }
        --*(_DWORD *)(v47 + 1688);
        v49 = *(_QWORD *)(v3[4] + 8LL);
        VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v6);
        v50 = *(unsigned int *)(v49 + 1620);
        if ( (unsigned int)v50 >= 4 )
        {
          ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v49 + 1320), v6);
        }
        else
        {
          *(_QWORD *)(v49 + 8 * v50 + 1656) = v6;
          ++*(_DWORD *)(v49 + 1620);
        }
        --*(_DWORD *)(v49 + 1688);
        v51 = *(_QWORD *)(v3[4] + 8LL);
        VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v1);
        v52 = *(unsigned int *)(v51 + 1620);
        if ( (unsigned int)v52 >= 4 )
        {
          ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v51 + 1320), v1);
        }
        else
        {
          *(_QWORD *)(v51 + 8 * v52 + 1656) = v1;
          ++*(_DWORD *)(v51 + 1620);
        }
        --*(_DWORD *)(v51 + 1688);
        v53 = *(_QWORD *)(v3[4] + 8LL);
        v54 = *(_DWORD *)(v53 + 1620);
        if ( v54 )
        {
          v55 = (unsigned int)(v54 - 1);
          v1 = *(_QWORD **)(v53 + 8 * v55 + 1656);
          *(_QWORD *)(v53 + 8 * v55 + 1656) = 0;
          --*(_DWORD *)(v53 + 1620);
        }
        else
        {
          v1 = ExAllocateFromLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v53 + 1320));
        }
        if ( !v1 )
        {
LABEL_94:
          v1[8] = v73;
          v1[9] = v74;
          VIDMM_RECYCLE_MULTIRANGE::MarkAllRangesWithNewOwner((VIDMM_RECYCLE_MULTIRANGE *)v1);
          VIDMM_RECYCLE_HEAP::AddMultirangeToTree(v3[4], (unsigned int)v2, v1);
          if ( *v3 != 1 )
            return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
          if ( v5 )
            return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
          v59 = (struct VIDMM_RECYCLE_RANGE *)v1[8];
          if ( *((_DWORD *)v59 + 16) )
            return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
          goto LABEL_131;
        }
        ++*(_DWORD *)(v53 + 1688);
        WdLogSingleEntry1(4, v1);
        WdLogGlobalForLineNumber = 2287;
        v1[4] = v70;
        v1[5] = v72;
        v1[6] = v70;
        *((_DWORD *)v1 + 6) = 1;
        v1[8] = 0;
        v1[9] = 0;
        v1[10] = v3;
        *((_DWORD *)v1 + 36) = v5;
        ++v3[1];
        LeastSignificantBit = RtlFindLeastSignificantBit(v1[4]);
        if ( LeastSignificantBit >= 0 )
        {
          v57 = 1LL << LeastSignificantBit;
LABEL_93:
          v1[7] = v57;
          v1[11] = 3;
          *((_DWORD *)v1 + 24) = 0;
          v1[15] = 0;
          *((_WORD *)v1 + 50) = 0;
          v1[13] = 0;
          v1[14] = 0;
          v1[16] = 0;
          v1[17] = 0;
          v58 = v1[10];
          *((_BYTE *)v1 + 148) = 0;
          VIDMM_RECYCLE_BLOCK::NotifyMultirangeEvent(v58, 0, v1);
          goto LABEL_94;
        }
LABEL_123:
        v57 = 0;
        goto LABEL_93;
    }
LABEL_122:
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52);
    WdLogGlobalForLineNumber = 222;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52);
    WdLogGlobalForLineNumber = 222;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52);
    WdLogGlobalForLineNumber = 222;
    goto LABEL_123;
  }
  if ( !v1 )
    return (struct VIDMM_RECYCLE_MULTIRANGE *)v6;
  v7 = v6;
LABEL_23:
  v14 = *((int *)v6 + 22);
  v15 = v3[4];
  WdLogSingleEntry2(4, v7, v14);
  WdLogGlobalForLineNumber = 8471;
  if ( (_DWORD)v14 == 2 )
  {
    v16 = v15 + 64;
  }
  else if ( (_DWORD)v14 )
  {
    if ( (_DWORD)v14 != 1 )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 52);
      WdLogGlobalForLineNumber = 222;
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 52);
      WdLogGlobalForLineNumber = 222;
LABEL_125:
      v28 = 0;
      goto LABEL_38;
    }
    v16 = v15 + 56;
  }
  else
  {
    v16 = v15 + 48;
  }
  RtlAvlRemoveNode(v16, v7);
  *((_DWORD *)v7 + 22) = 3;
  v17 = *(_QWORD *)(v6[10] + 32LL);
  WdLogSingleEntry2(4, v1, v14);
  WdLogGlobalForLineNumber = 8471;
  if ( (_DWORD)v14 == 2 )
  {
    v18 = v17 + 64;
  }
  else if ( (_DWORD)v14 )
  {
    v18 = v17 + 56;
  }
  else
  {
    v18 = v17 + 48;
  }
  RtlAvlRemoveNode(v18, v1);
  *((_DWORD *)v1 + 22) = 3;
  v6 = (_QWORD *)v7[8];
  v61 = v7[4];
  v62 = v1[5];
  v63 = v1[9];
  v19 = *(_QWORD *)(v3[4] + 8LL);
  VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v7);
  v20 = *(unsigned int *)(v19 + 1620);
  if ( (unsigned int)v20 >= 4 )
  {
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v19 + 1320), v7);
  }
  else
  {
    *(_QWORD *)(v19 + 8 * v20 + 1656) = v7;
    ++*(_DWORD *)(v19 + 1620);
  }
  --*(_DWORD *)(v19 + 1688);
  v21 = *(_QWORD *)(v3[4] + 8LL);
  VIDMM_RECYCLE_MULTIRANGE::Destroy((VIDMM_RECYCLE_MULTIRANGE *)v1);
  v22 = *(unsigned int *)(v21 + 1620);
  if ( (unsigned int)v22 >= 4 )
  {
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v21 + 1320), v1);
  }
  else
  {
    *(_QWORD *)(v21 + 8 * v22 + 1656) = v1;
    ++*(_DWORD *)(v21 + 1620);
  }
  --*(_DWORD *)(v21 + 1688);
  v7 = *(_QWORD **)(v3[4] + 8LL);
  v23 = *((_DWORD *)v7 + 405);
  if ( v23 )
  {
    v24 = (unsigned int)(v23 - 1);
    v1 = (_QWORD *)v7[v24 + 207];
    v7[v24 + 207] = 0;
    --*((_DWORD *)v7 + 405);
  }
  else
  {
    v1 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)v7[165]);
  }
  v25 = v1 + 8;
  v26 = 1;
  v74 = (__int64)(v1 + 8);
  v71 = (__int64)(v1 + 5);
  v73 = v1 + 7;
  v69 = v1 + 4;
  if ( !v1 )
  {
    v74 = 64;
    v71 = 40;
    v69 = v1 + 4;
    v73 = v1 + 7;
    goto LABEL_39;
  }
  ++*((_DWORD *)v7 + 422);
  WdLogSingleEntry1(4, v1);
  LODWORD(v7) = 1;
  WdLogGlobalForLineNumber = 2287;
  v1[4] = v61;
  v1[5] = v62;
  v1[6] = v61;
  *((_DWORD *)v1 + 6) = 1;
  v1[8] = 0;
  v1[9] = 0;
  v1[10] = v3;
  *((_DWORD *)v1 + 36) = v5;
  ++v3[1];
  v27 = RtlFindLeastSignificantBit(v1[4]);
  if ( v27 < 0 )
    goto LABEL_125;
  v28 = 1LL << v27;
LABEL_38:
  v1[7] = v28;
  v1[11] = 3;
  *((_DWORD *)v1 + 24) = 0;
  v1[15] = 0;
  *((_WORD *)v1 + 50) = 0;
  v1[13] = 0;
  v1[14] = 0;
  v1[16] = 0;
  v1[17] = 0;
  v29 = v1[10];
  *((_BYTE *)v1 + 148) = 0;
  VIDMM_RECYCLE_BLOCK::NotifyMultirangeEvent(v29, 0, v1);
  v26 = (unsigned int)v7;
  v25 = v1 + 8;
LABEL_39:
  v30 = 0;
  v1[9] = v63;
  *v25 = v6;
  while ( !v30 )
  {
    v31 = *((_DWORD *)v1 + 36);
    if ( v31 )
    {
      v38 = v31 - 1;
      if ( v38 )
      {
        if ( v38 != 1 )
        {
          g_DxgMmsBugcheckExportIndex = v26;
          WdLogSingleEntry5(0, 270, 52);
          WdLogGlobalForLineNumber = 222;
          goto LABEL_128;
        }
        v6[19] = v1;
      }
      else
      {
        v6[18] = v1;
      }
    }
    else
    {
      v6[17] = v1;
    }
    if ( v6 == (_QWORD *)v1[9] )
    {
      v30 = 1;
    }
    else
    {
      v32 = v6[15];
      if ( v32 == v6[9] + 72LL )
        v6 = 0;
      else
        v6 = (_QWORD *)(v32 - 120);
    }
  }
  v33 = (_QWORD *)v3[4];
  WdLogSingleEntry2(4, v1, v14);
  WdLogGlobalForLineNumber = 8421;
  v65 = 0;
  v64[0] = *(_QWORD *)v71 - *v69;
  v64[1] = *v73;
  if ( (_DWORD)v14 == 2 )
  {
    v35 = v33 + 8;
    LOBYTE(v34) = 0;
    v36 = (struct _RTL_BALANCED_NODE *)v33[8];
    if ( v36 )
    {
      while ( 1 )
      {
        if ( (int)VidMmCompareForInsertAlignedRange(v64, v36) < 0 )
        {
          v37 = v36->Children[0];
          if ( !v36->Children[0] )
            goto LABEL_52;
        }
        else
        {
          v37 = v36->Children[1];
          if ( !v37 )
            goto LABEL_56;
        }
        v36 = v37;
      }
    }
  }
  else if ( (_DWORD)v14 )
  {
    if ( (_DWORD)v14 != 1 )
    {
LABEL_128:
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 52);
      WdLogGlobalForLineNumber = 222;
      goto LABEL_129;
    }
    v35 = v33 + 7;
    LOBYTE(v34) = 0;
    v36 = (struct _RTL_BALANCED_NODE *)v33[7];
    if ( v36 )
    {
      while ( 1 )
      {
        if ( (int)VidMmCompareForInsertAlignedRange(v64, v36) < 0 )
        {
          v60 = v36->Children[0];
          if ( !v36->Children[0] )
          {
LABEL_52:
            LOBYTE(v34) = 0;
            break;
          }
        }
        else
        {
          v60 = v36->Children[1];
          if ( !v60 )
          {
LABEL_56:
            LOBYTE(v34) = 1;
            break;
          }
        }
        v36 = v60;
      }
    }
  }
  else
  {
    v35 = v33 + 6;
    LOBYTE(v34) = 0;
    v36 = (struct _RTL_BALANCED_NODE *)v33[6];
    if ( v36 )
    {
      while ( 1 )
      {
        if ( (int)VidMmCompareForInsertAlignedRange(v64, v36) < 0 )
        {
          v39 = v36->Children[0];
          if ( !v36->Children[0] )
            goto LABEL_52;
        }
        else
        {
          v39 = v36->Children[1];
          if ( !v39 )
            goto LABEL_56;
        }
        v36 = v39;
      }
    }
  }
  RtlAvlInsertNodeEx(v35, v36, v34, v1);
  *((_DWORD *)v1 + 22) = v14;
  if ( *v3 != 1 )
    return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
LABEL_129:
  if ( v5 )
    return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
  v59 = *(struct VIDMM_RECYCLE_RANGE **)v74;
  if ( *(_DWORD *)(*(_QWORD *)v74 + 64LL) )
    return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
LABEL_131:
  VIDMM_RECYCLE_HEAP::RemoveMultirangeFromTree(v3[4], 2, v1);
  VIDMM_RECYCLE_HEAP_MGR::DestroyMultirange(
    *(VIDMM_RECYCLE_HEAP_MGR **)(v3[4] + 8LL),
    (struct VIDMM_RECYCLE_MULTIRANGE *)v1);
  VIDMM_RECYCLE_HEAP_MGR::DestroyRange(*(VIDMM_RECYCLE_HEAP_MGR **)(v3[4] + 8LL), v59);
  return (struct VIDMM_RECYCLE_MULTIRANGE *)v1;
}

```

## disassembly

```asm
0x1400f4cb0  push    rbp
0x1400f4cb2  push    rsi
0x1400f4cb3  push    rdi
0x1400f4cb4  push    r15
0x1400f4cb6  sub     rsp, 88h
0x1400f4cbd  mov     rax, [rcx+40h]
0x1400f4cc1  xor     ebp, ebp
0x1400f4cc3  mov     r15d, [rcx+90h]
0x1400f4cca  mov     rsi, rcx
0x1400f4ccd  mov     edi, ebp
0x1400f4ccf  mov     rdx, [rax+48h]
0x1400f4cd3  mov     rcx, [rax+80h]
0x1400f4cda  add     rdx, 48h ; 'H'
0x1400f4cde  cmp     rcx, rdx
0x1400f4ce1  jz      short loc_1400F4D0B
0x1400f4ce3  lea     rax, [rcx-78h]
0x1400f4ce7  test    rax, rax
0x1400f4cea  jz      short loc_1400F4D0B
0x1400f4cec  cmp     r15d, 1
0x1400f4cf0  jz      short loc_1400F4D04
0x1400f4cf2  test    r15d, r15d
0x1400f4cf5  jnz     loc_1400F4DA7
0x1400f4cfb  mov     rdi, [rax+88h]
0x1400f4d02  jmp     short loc_1400F4D0B
0x1400f4d04  mov     rdi, [rax+90h]
0x1400f4d0b  mov     rax, [rsi+48h]
0x1400f4d0f  mov     [rsp+0A8h+var_28], rbx
0x1400f4d17  mov     rbx, rbp
0x1400f4d1a  mov     rcx, [rax+48h]
0x1400f4d1e  mov     rdx, [rax+78h]
0x1400f4d22  add     rcx, 48h ; 'H'
0x1400f4d26  cmp     rdx, rcx
0x1400f4d29  jz      short loc_1400F4D4F
0x1400f4d2b  lea     rax, [rdx-78h]
0x1400f4d2f  test    rax, rax
0x1400f4d32  jz      short loc_1400F4D4F
0x1400f4d34  cmp     r15d, 1
0x1400f4d38  jz      short loc_1400F4D48
0x1400f4d3a  test    r15d, r15d
0x1400f4d3d  jnz     short loc_1400F4D94
0x1400f4d3f  mov     rbx, [rax+88h]
0x1400f4d46  jmp     short loc_1400F4D4F
0x1400f4d48  mov     rbx, [rax+90h]
0x1400f4d4f  mov     [rsp+0A8h+var_30], r12
0x1400f4d54  mov     [rsp+0A8h+var_38], r13
0x1400f4d59  mov     [rsp+0A8h+var_40], r14
0x1400f4d5e  mov     r14, [rsi+50h]
0x1400f4d62  test    rdi, rdi
0x1400f4d65  jnz     short loc_1400F4DC2
0x1400f4d67  test    rbx, rbx
0x1400f4d6a  jnz     short loc_1400F4DBD
0x1400f4d6c  mov     rax, rsi
0x1400f4d6f  mov     r13, [rsp+0A8h+var_38]
0x1400f4d74  mov     r12, [rsp+0A8h+var_30]
0x1400f4d79  mov     r14, [rsp+0A8h+var_40]
0x1400f4d7e  mov     rbx, [rsp+0A8h+var_28]
0x1400f4d86  add     rsp, 88h
0x1400f4d8d  pop     r15
0x1400f4d8f  pop     rdi
0x1400f4d90  pop     rsi
0x1400f4d91  pop     rbp
0x1400f4d92  retn
0x1400f4d94  cmp     r15d, 2
0x1400f4d98  jnz     loc_1400F56BF
0x1400f4d9e  mov     rbx, [rax+98h]
0x1400f4da5  jmp     short loc_1400F4D4F
0x1400f4da7  cmp     r15d, 2
0x1400f4dab  jnz     loc_1400F567F
0x1400f4db1  mov     rdi, [rax+98h]
0x1400f4db8  jmp     loc_1400F4D0B
0x1400f4dbd  mov     rdi, rsi
0x1400f4dc0  jmp     short loc_1400F4DCE
0x1400f4dc2  test    rbx, rbx
0x1400f4dc5  jnz     loc_1400F5222
0x1400f4dcb  mov     rbx, rsi
0x1400f4dce  movsxd  r12, dword ptr [rsi+58h]
0x1400f4dd2  mov     r13, [r14+20h]
0x1400f4dd6  mov     r8, r12
0x1400f4dd9  mov     rdx, rdi
0x1400f4ddc  mov     ecx, 4
0x1400f4de1  call    cs:__imp_WdLogSingleEntry2
0x1400f4de8  nop     dword ptr [rax+rax+00h]
0x1400f4ded  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f4df7  cmp     r12d, 2
0x1400f4dfb  jz      loc_1400F5162
0x1400f4e01  test    r12d, r12d
0x1400f4e04  jnz     loc_1400F5590
0x1400f4e0a  lea     rcx, [r13+30h]
0x1400f4e0e  mov     rdx, rdi
0x1400f4e11  call    cs:__imp_RtlAvlRemoveNode
0x1400f4e18  nop     dword ptr [rax+rax+00h]
0x1400f4e1d  mov     dword ptr [rdi+58h], 3
0x1400f4e24  mov     rax, [rsi+50h]
0x1400f4e28  mov     rsi, [rax+20h]
0x1400f4e2c  mov     r8, r12
0x1400f4e2f  mov     rdx, rbx
0x1400f4e32  mov     ecx, 4
0x1400f4e37  call    cs:__imp_WdLogSingleEntry2
0x1400f4e3e  nop     dword ptr [rax+rax+00h]
0x1400f4e43  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f4e4d  cmp     r12d, 2
0x1400f4e51  jz      loc_1400F516B
0x1400f4e57  test    r12d, r12d
0x1400f4e5a  jnz     loc_1400F55A3
0x1400f4e60  lea     rcx, [rsi+30h]
0x1400f4e64  mov     rdx, rbx
0x1400f4e67  call    cs:__imp_RtlAvlRemoveNode
0x1400f4e6e  nop     dword ptr [rax+rax+00h]
0x1400f4e73  mov     dword ptr [rbx+58h], 3
0x1400f4e7a  mov     rcx, rdi; this
0x1400f4e7d  mov     rax, [rdi+20h]
0x1400f4e81  mov     rsi, [rdi+40h]
0x1400f4e85  mov     [rsp+0A8h+var_78], rax
0x1400f4e8a  mov     rax, [rbx+28h]
0x1400f4e8e  mov     [rsp+0A8h+var_70], rax
0x1400f4e93  mov     rax, [rbx+48h]
0x1400f4e97  mov     [rsp+0A8h+var_68], rax
0x1400f4e9c  mov     rax, [r14+20h]
0x1400f4ea0  mov     r13, [rax+8]
0x1400f4ea4  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f4ea9  mov     eax, [r13+654h]
0x1400f4eb0  cmp     eax, 4
0x1400f4eb3  jnb     loc_1400F51D1
0x1400f4eb9  mov     [r13+rax*8+678h], rdi
0x1400f4ec1  inc     dword ptr [r13+654h]
0x1400f4ec8  dec     dword ptr [r13+698h]
0x1400f4ecf  mov     rcx, rbx; this
0x1400f4ed2  mov     rax, [r14+20h]
0x1400f4ed6  mov     rdi, [rax+8]
0x1400f4eda  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f4edf  mov     eax, [rdi+654h]
0x1400f4ee5  cmp     eax, 4
0x1400f4ee8  jnb     loc_1400F51EC
0x1400f4eee  mov     [rdi+rax*8+678h], rbx
0x1400f4ef6  inc     dword ptr [rdi+654h]
0x1400f4efc  dec     dword ptr [rdi+698h]
0x1400f4f02  mov     rax, [r14+20h]
0x1400f4f06  mov     rdi, [rax+8]
0x1400f4f0a  mov     eax, [rdi+654h]
0x1400f4f10  test    eax, eax
0x1400f4f12  jz      loc_1400F5207
0x1400f4f18  dec     eax
0x1400f4f1a  mov     rbx, [rdi+rax*8+678h]
0x1400f4f22  mov     [rdi+rax*8+678h], rbp
0x1400f4f2a  dec     dword ptr [rdi+654h]
0x1400f4f30  lea     r9, [rbx+40h]
0x1400f4f34  mov     r8d, 1
0x1400f4f3a  mov     [rsp+0A8h+arg_18], r9
0x1400f4f42  lea     rdx, [rbx+28h]
0x1400f4f46  mov     [rsp+0A8h+arg_8], rdx
0x1400f4f4e  lea     rax, [rbx+38h]
0x1400f4f52  mov     [rsp+0A8h+arg_10], rax
0x1400f4f5a  lea     rcx, [rbx+20h]
0x1400f4f5e  mov     [rsp+0A8h+arg_0], rcx
0x1400f4f66  test    rbx, rbx
0x1400f4f69  jz      loc_1400F584F
0x1400f4f6f  inc     dword ptr [rdi+698h]
0x1400f4f75  mov     rdx, rbx
0x1400f4f78  mov     ecx, 4
0x1400f4f7d  call    cs:__imp_WdLogSingleEntry1
0x1400f4f84  nop     dword ptr [rax+rax+00h]
0x1400f4f89  mov     rax, [rsp+0A8h+var_78]
0x1400f4f8e  mov     edi, 1
0x1400f4f93  mov     rcx, [rsp+0A8h+var_70]
0x1400f4f98  mov     cs:WdLogGlobalForLineNumber, 8EFh
0x1400f4fa2  mov     [rbx+20h], rax
0x1400f4fa6  mov     [rbx+28h], rcx
0x1400f4faa  mov     [rbx+30h], rax
0x1400f4fae  mov     [rbx+18h], edi
0x1400f4fb1  mov     [rbx+40h], rbp
0x1400f4fb5  mov     [rbx+48h], rbp
0x1400f4fb9  mov     [rbx+50h], r14
0x1400f4fbd  mov     [rbx+90h], r15d
0x1400f4fc4  inc     qword ptr [r14+8]
0x1400f4fc8  mov     rcx, [rbx+20h]; Set
0x1400f4fcc  call    cs:__imp_RtlFindLeastSignificantBit
0x1400f4fd3  nop     dword ptr [rax+rax+00h]
0x1400f4fd8  test    al, al
0x1400f4fda  js      loc_1400F5847
0x1400f4fe0  movzx   ecx, al
0x1400f4fe3  mov     eax, edi
0x1400f4fe5  shl     rax, cl
0x1400f4fe8  mov     [rbx+38h], rax
0x1400f4fec  mov     r8, rbx
0x1400f4fef  mov     qword ptr [rbx+58h], 3
0x1400f4ff7  xor     edx, edx
0x1400f4ff9  mov     [rbx+60h], ebp
0x1400f4ffc  mov     [rbx+78h], rbp
0x1400f5000  mov     word ptr [rbx+64h], 0
0x1400f5006  mov     [rbx+68h], rbp
0x1400f500a  mov     [rbx+70h], rbp
0x1400f500e  mov     [rbx+80h], rbp
0x1400f5015  mov     [rbx+88h], rbp
0x1400f501c  mov     rcx, [rbx+50h]
0x1400f5020  mov     byte ptr [rbx+94h], 0
0x1400f5027  call    ?NotifyMultirangeEvent@VIDMM_RECYCLE_BLOCK@@QEAAXW4RangeOp@1@PEAX@Z; VIDMM_RECYCLE_BLOCK::NotifyMultirangeEvent(VIDMM_RECYCLE_BLOCK::RangeOp,void *)
0x1400f502c  mov     r8, rdi
0x1400f502f  lea     r9, [rbx+40h]
0x1400f5033  mov     rax, [rsp+0A8h+var_68]
0x1400f5038  xor     cl, cl
0x1400f503a  mov     [rbx+48h], rax
0x1400f503e  mov     [r9], rsi
0x1400f5041  test    cl, cl
0x1400f5043  jnz     short loc_1400F507E
0x1400f5045  mov     edx, [rbx+90h]
0x1400f504b  test    edx, edx
0x1400f504d  jnz     loc_1400F511C
0x1400f5053  mov     [rsi+88h], rbx
0x1400f505a  cmp     rsi, [rbx+48h]
0x1400f505e  jz      loc_1400F512D
0x1400f5064  mov     rax, [rsi+48h]
0x1400f5068  mov     rdx, [rsi+78h]
0x1400f506c  add     rax, 48h ; 'H'
0x1400f5070  cmp     rdx, rax
0x1400f5073  jnz     loc_1400F5676
0x1400f5079  mov     rsi, rbp
0x1400f507c  jmp     short loc_1400F5041
0x1400f507e  mov     rdi, [r14+20h]
0x1400f5082  mov     r8, r12
0x1400f5085  mov     rdx, rbx
0x1400f5088  mov     ecx, 4
0x1400f508d  call    cs:__imp_WdLogSingleEntry2
0x1400f5094  nop     dword ptr [rax+rax+00h]
0x1400f5099  mov     rax, [rsp+0A8h+arg_0]
0x1400f50a1  mov     rcx, [rsp+0A8h+arg_8]
0x1400f50a9  mov     cs:WdLogGlobalForLineNumber, 20E5h
0x1400f50b3  mov     [rsp+0A8h+var_50], 0
0x1400f50b8  mov     rcx, [rcx]
0x1400f50bb  sub     rcx, [rax]
0x1400f50be  mov     rax, [rsp+0A8h+arg_10]
0x1400f50c6  mov     [rsp+0A8h+var_60], rcx
0x1400f50cb  mov     rax, [rax]
0x1400f50ce  mov     [rsp+0A8h+var_58], rax
0x1400f50d3  cmp     r12d, 2
0x1400f50d7  jnz     loc_1400F5189
0x1400f50dd  lea     rsi, [rdi+40h]
0x1400f50e1  xor     r8b, r8b
0x1400f50e4  mov     rdi, [rsi]
0x1400f50e7  test    rdi, rdi
0x1400f50ea  jz      short loc_1400F5137
0x1400f50ec  nop     dword ptr [rax+00h]
0x1400f50f0  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x1400f50f3  lea     rcx, [rsp+0A8h+var_60]; void *
0x1400f50f8  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f50fd  test    eax, eax
0x1400f50ff  js      short loc_1400F510F
0x1400f5101  mov     rax, [rdi+8]
0x1400f5105  test    rax, rax
0x1400f5108  jz      short loc_1400F5134
0x1400f510a  mov     rdi, rax
0x1400f510d  jmp     short loc_1400F50F0
0x1400f510f  mov     rax, [rdi]
0x1400f5112  test    rax, rax
0x1400f5115  jnz     short loc_1400F510A
0x1400f5117  xor     r8b, r8b
0x1400f511a  jmp     short loc_1400F5137
0x1400f511c  sub     edx, 1
0x1400f511f  jnz     short loc_1400F5174
0x1400f5121  mov     [rsi+90h], rbx
0x1400f5128  jmp     loc_1400F505A
0x1400f512d  mov     cl, 1
0x1400f512f  jmp     loc_1400F5041
0x1400f5134  mov     r8b, 1
0x1400f5137  mov     r9, rbx
0x1400f513a  mov     rdx, rdi
0x1400f513d  mov     rcx, rsi
0x1400f5140  call    cs:__imp_RtlAvlInsertNodeEx
0x1400f5147  nop     dword ptr [rax+rax+00h]
0x1400f514c  mov     [rbx+58h], r12d
0x1400f5150  cmp     qword ptr [r14], 1
0x1400f5154  jz      loc_1400F58F1
0x1400f515a  mov     rax, rbx
0x1400f515d  jmp     loc_1400F4D6F
0x1400f5162  lea     rcx, [r13+40h]
0x1400f5166  jmp     loc_1400F4E0E
0x1400f516b  lea     rcx, [rsi+40h]
0x1400f516f  jmp     loc_1400F4E64
0x1400f5174  cmp     edx, 1
0x1400f5177  jnz     loc_1400F5874
0x1400f517d  mov     [rsi+98h], rbx
0x1400f5184  jmp     loc_1400F505A
0x1400f5189  test    r12d, r12d
0x1400f518c  jnz     loc_1400F553D
0x1400f5192  lea     rsi, [rdi+30h]
0x1400f5196  xor     r8b, r8b
0x1400f5199  mov     rdi, [rsi]
0x1400f519c  test    rdi, rdi
0x1400f519f  jz      short loc_1400F5137
0x1400f51a1  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x1400f51a4  lea     rcx, [rsp+0A8h+var_60]; void *
0x1400f51a9  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f51ae  test    eax, eax
0x1400f51b0  js      short loc_1400F51C4
0x1400f51b2  mov     rax, [rdi+8]
0x1400f51b6  test    rax, rax
0x1400f51b9  jz      loc_1400F5134
0x1400f51bf  mov     rdi, rax
0x1400f51c2  jmp     short loc_1400F51A1
0x1400f51c4  mov     rax, [rdi]
0x1400f51c7  test    rax, rax
  ... truncated ...
```
