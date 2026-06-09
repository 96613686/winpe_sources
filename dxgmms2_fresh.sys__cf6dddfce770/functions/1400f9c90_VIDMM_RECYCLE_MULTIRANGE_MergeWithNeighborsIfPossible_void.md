# VIDMM_RECYCLE_MULTIRANGE::MergeWithNeighborsIfPossible(void)

- ea: `0x1400f9c90`
- end: `0x1400fa925`
- name: `?MergeWithNeighborsIfPossible@VIDMM_RECYCLE_MULTIRANGE@@QEAAPEAV1@XZ`
- size: `3221`
- prototype: `struct VIDMM_RECYCLE_MULTIRANGE *__fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f70ec`

## callees

- `0x14002f2cc`
- `0x1400f5650`
- `0x1400f6fdc`
- `0x1400f9c90`
- `0x1400fa930`
- `0x1400fa96c`
- `0x1400faa38`
- `0x1400fabc0`
- `0x1400fb7fc`

## import_xrefs

- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f9fac`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400fa46a`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f9fac`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400fa46a`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400fa120`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400fa120`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400fa1ee`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400fa609`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400fa1ee`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400fa609`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa1bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa1d6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa5bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa5d6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa5f1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa1bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa1d6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa5bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa5d6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400fa5f1`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f9df1`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f9e47`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400fa25d`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400fa2b3`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400fa309`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f9df1`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f9e47`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400fa25d`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400fa2b3`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400fa309`
- `watchdog!WdLogSingleEntry2` at `0x1400f9dc1`
- `watchdog!WdLogSingleEntry2` at `0x1400f9e17`
- `watchdog!WdLogSingleEntry2` at `0x1400fa06d`
- `watchdog!WdLogSingleEntry2` at `0x1400fa22d`
- `watchdog!WdLogSingleEntry2` at `0x1400fa283`
- `watchdog!WdLogSingleEntry2` at `0x1400fa2d9`
- `watchdog!WdLogSingleEntry2` at `0x1400f9dc1`
- `watchdog!WdLogSingleEntry2` at `0x1400f9e17`
- `watchdog!WdLogSingleEntry2` at `0x1400fa06d`
- `watchdog!WdLogSingleEntry2` at `0x1400fa22d`
- `watchdog!WdLogSingleEntry2` at `0x1400fa283`
- `watchdog!WdLogSingleEntry2` at `0x1400fa2d9`
- `watchdog!WdLogSingleEntry5` at `0x1400fa689`
- `watchdog!WdLogSingleEntry5` at `0x1400fa6c9`
- `watchdog!WdLogSingleEntry5` at `0x1400fa709`
- `watchdog!WdLogSingleEntry5` at `0x1400fa749`
- `watchdog!WdLogSingleEntry5` at `0x1400fa789`
- `watchdog!WdLogSingleEntry5` at `0x1400fa7d1`
- `watchdog!WdLogSingleEntry5` at `0x1400fa811`
- `watchdog!WdLogSingleEntry5` at `0x1400fa87b`
- `watchdog!WdLogSingleEntry5` at `0x1400fa8bb`
- `watchdog!WdLogSingleEntry5` at `0x1400fa689`
- `watchdog!WdLogSingleEntry5` at `0x1400fa6c9`
- `watchdog!WdLogSingleEntry5` at `0x1400fa709`
- `watchdog!WdLogSingleEntry5` at `0x1400fa749`
- `watchdog!WdLogSingleEntry5` at `0x1400fa789`
- `watchdog!WdLogSingleEntry5` at `0x1400fa7d1`
- `watchdog!WdLogSingleEntry5` at `0x1400fa811`
- `watchdog!WdLogSingleEntry5` at `0x1400fa87b`
- `watchdog!WdLogSingleEntry5` at `0x1400fa8bb`
- `watchdog!WdLogSingleEntry1` at `0x1400f9f5d`
- `watchdog!WdLogSingleEntry1` at `0x1400fa415`
- `watchdog!WdLogSingleEntry1` at `0x1400f9f5d`
- `watchdog!WdLogSingleEntry1` at `0x1400fa415`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa65f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa69f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa6df`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa71f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa75f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa7a7`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa7e7`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa854`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400fa891`

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
          WdLogSingleEntry5(0, 270, 52, 10, 0, 0);
          WdLogGlobalForLineNumber = 227;
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
      WdLogSingleEntry5(0, 270, 52, 10, 0, 0);
      WdLogGlobalForLineNumber = 227;
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
    WdLogSingleEntry5(0, 270, 52, 16, v2, 0);
    WdLogGlobalForLineNumber = 227;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52, 16, v2, 0);
    WdLogGlobalForLineNumber = 227;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52, 16, v2, 0);
    WdLogGlobalForLineNumber = 227;
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
      WdLogSingleEntry5(0, 270, 52, 16, v14, 0);
      WdLogGlobalForLineNumber = 227;
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 52, 16, v14, 0);
      WdLogGlobalForLineNumber = 227;
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
          WdLogSingleEntry5(0, 270, 52, 10, 0, 0);
          WdLogGlobalForLineNumber = 227;
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
      WdLogSingleEntry5(0, 270, 52, 15, v14, 0);
      WdLogGlobalForLineNumber = 227;
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
0x1400f9c90  push    rbp
0x1400f9c92  push    rsi
0x1400f9c93  push    rdi
0x1400f9c94  push    r15
0x1400f9c96  sub     rsp, 88h
0x1400f9c9d  mov     rax, [rcx+40h]
0x1400f9ca1  xor     ebp, ebp
0x1400f9ca3  mov     r15d, [rcx+90h]
0x1400f9caa  mov     rsi, rcx
0x1400f9cad  mov     edi, ebp
0x1400f9caf  mov     rdx, [rax+48h]
0x1400f9cb3  mov     rcx, [rax+80h]
0x1400f9cba  add     rdx, 48h ; 'H'
0x1400f9cbe  cmp     rcx, rdx
0x1400f9cc1  jz      short loc_1400F9CEB
0x1400f9cc3  lea     rax, [rcx-78h]
0x1400f9cc7  test    rax, rax
0x1400f9cca  jz      short loc_1400F9CEB
0x1400f9ccc  cmp     r15d, 1
0x1400f9cd0  jz      short loc_1400F9CE4
0x1400f9cd2  test    r15d, r15d
0x1400f9cd5  jnz     loc_1400F9D87
0x1400f9cdb  mov     rdi, [rax+88h]
0x1400f9ce2  jmp     short loc_1400F9CEB
0x1400f9ce4  mov     rdi, [rax+90h]
0x1400f9ceb  mov     rax, [rsi+48h]
0x1400f9cef  mov     [rsp+0A8h+var_28], rbx
0x1400f9cf7  mov     rbx, rbp
0x1400f9cfa  mov     rcx, [rax+48h]
0x1400f9cfe  mov     rdx, [rax+78h]
0x1400f9d02  add     rcx, 48h ; 'H'
0x1400f9d06  cmp     rdx, rcx
0x1400f9d09  jz      short loc_1400F9D2F
0x1400f9d0b  lea     rax, [rdx-78h]
0x1400f9d0f  test    rax, rax
0x1400f9d12  jz      short loc_1400F9D2F
0x1400f9d14  cmp     r15d, 1
0x1400f9d18  jz      short loc_1400F9D28
0x1400f9d1a  test    r15d, r15d
0x1400f9d1d  jnz     short loc_1400F9D74
0x1400f9d1f  mov     rbx, [rax+88h]
0x1400f9d26  jmp     short loc_1400F9D2F
0x1400f9d28  mov     rbx, [rax+90h]
0x1400f9d2f  mov     [rsp+0A8h+var_30], r12
0x1400f9d34  mov     [rsp+0A8h+var_38], r13
0x1400f9d39  mov     [rsp+0A8h+var_40], r14
0x1400f9d3e  mov     r14, [rsi+50h]
0x1400f9d42  test    rdi, rdi
0x1400f9d45  jnz     short loc_1400F9DA2
0x1400f9d47  test    rbx, rbx
0x1400f9d4a  jnz     short loc_1400F9D9D
0x1400f9d4c  mov     rax, rsi
0x1400f9d4f  mov     r13, [rsp+0A8h+var_38]
0x1400f9d54  mov     r12, [rsp+0A8h+var_30]
0x1400f9d59  mov     r14, [rsp+0A8h+var_40]
0x1400f9d5e  mov     rbx, [rsp+0A8h+var_28]
0x1400f9d66  add     rsp, 88h
0x1400f9d6d  pop     r15
0x1400f9d6f  pop     rdi
0x1400f9d70  pop     rsi
0x1400f9d71  pop     rbp
0x1400f9d72  retn
0x1400f9d74  cmp     r15d, 2
0x1400f9d78  jnz     loc_1400FA69F
0x1400f9d7e  mov     rbx, [rax+98h]
0x1400f9d85  jmp     short loc_1400F9D2F
0x1400f9d87  cmp     r15d, 2
0x1400f9d8b  jnz     loc_1400FA65F
0x1400f9d91  mov     rdi, [rax+98h]
0x1400f9d98  jmp     loc_1400F9CEB
0x1400f9d9d  mov     rdi, rsi
0x1400f9da0  jmp     short loc_1400F9DAE
0x1400f9da2  test    rbx, rbx
0x1400f9da5  jnz     loc_1400FA202
0x1400f9dab  mov     rbx, rsi
0x1400f9dae  movsxd  r12, dword ptr [rsi+58h]
0x1400f9db2  mov     r13, [r14+20h]
0x1400f9db6  mov     r8, r12
0x1400f9db9  mov     rdx, rdi
0x1400f9dbc  mov     ecx, 4
0x1400f9dc1  call    cs:__imp_WdLogSingleEntry2
0x1400f9dc8  nop     dword ptr [rax+rax+00h]
0x1400f9dcd  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f9dd7  cmp     r12d, 2
0x1400f9ddb  jz      loc_1400FA142
0x1400f9de1  test    r12d, r12d
0x1400f9de4  jnz     loc_1400FA570
0x1400f9dea  lea     rcx, [r13+30h]
0x1400f9dee  mov     rdx, rdi
0x1400f9df1  call    cs:__imp_RtlAvlRemoveNode
0x1400f9df8  nop     dword ptr [rax+rax+00h]
0x1400f9dfd  mov     dword ptr [rdi+58h], 3
0x1400f9e04  mov     rax, [rsi+50h]
0x1400f9e08  mov     rsi, [rax+20h]
0x1400f9e0c  mov     r8, r12
0x1400f9e0f  mov     rdx, rbx
0x1400f9e12  mov     ecx, 4
0x1400f9e17  call    cs:__imp_WdLogSingleEntry2
0x1400f9e1e  nop     dword ptr [rax+rax+00h]
0x1400f9e23  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f9e2d  cmp     r12d, 2
0x1400f9e31  jz      loc_1400FA14B
0x1400f9e37  test    r12d, r12d
0x1400f9e3a  jnz     loc_1400FA583
0x1400f9e40  lea     rcx, [rsi+30h]
0x1400f9e44  mov     rdx, rbx
0x1400f9e47  call    cs:__imp_RtlAvlRemoveNode
0x1400f9e4e  nop     dword ptr [rax+rax+00h]
0x1400f9e53  mov     dword ptr [rbx+58h], 3
0x1400f9e5a  mov     rcx, rdi; this
0x1400f9e5d  mov     rax, [rdi+20h]
0x1400f9e61  mov     rsi, [rdi+40h]
0x1400f9e65  mov     [rsp+0A8h+var_78], rax
0x1400f9e6a  mov     rax, [rbx+28h]
0x1400f9e6e  mov     [rsp+0A8h+var_70], rax
0x1400f9e73  mov     rax, [rbx+48h]
0x1400f9e77  mov     [rsp+0A8h+var_68], rax
0x1400f9e7c  mov     rax, [r14+20h]
0x1400f9e80  mov     r13, [rax+8]
0x1400f9e84  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f9e89  mov     eax, [r13+654h]
0x1400f9e90  cmp     eax, 4
0x1400f9e93  jnb     loc_1400FA1B1
0x1400f9e99  mov     [r13+rax*8+678h], rdi
0x1400f9ea1  inc     dword ptr [r13+654h]
0x1400f9ea8  dec     dword ptr [r13+698h]
0x1400f9eaf  mov     rcx, rbx; this
0x1400f9eb2  mov     rax, [r14+20h]
0x1400f9eb6  mov     rdi, [rax+8]
0x1400f9eba  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f9ebf  mov     eax, [rdi+654h]
0x1400f9ec5  cmp     eax, 4
0x1400f9ec8  jnb     loc_1400FA1CC
0x1400f9ece  mov     [rdi+rax*8+678h], rbx
0x1400f9ed6  inc     dword ptr [rdi+654h]
0x1400f9edc  dec     dword ptr [rdi+698h]
0x1400f9ee2  mov     rax, [r14+20h]
0x1400f9ee6  mov     rdi, [rax+8]
0x1400f9eea  mov     eax, [rdi+654h]
0x1400f9ef0  test    eax, eax
0x1400f9ef2  jz      loc_1400FA1E7
0x1400f9ef8  dec     eax
0x1400f9efa  mov     rbx, [rdi+rax*8+678h]
0x1400f9f02  mov     [rdi+rax*8+678h], rbp
0x1400f9f0a  dec     dword ptr [rdi+654h]
0x1400f9f10  lea     r9, [rbx+40h]
0x1400f9f14  mov     r8d, 1
0x1400f9f1a  mov     [rsp+0A8h+arg_18], r9
0x1400f9f22  lea     rdx, [rbx+28h]
0x1400f9f26  mov     [rsp+0A8h+arg_8], rdx
0x1400f9f2e  lea     rax, [rbx+38h]
0x1400f9f32  mov     [rsp+0A8h+arg_10], rax
0x1400f9f3a  lea     rcx, [rbx+20h]
0x1400f9f3e  mov     [rsp+0A8h+arg_0], rcx
0x1400f9f46  test    rbx, rbx
0x1400f9f49  jz      loc_1400FA82F
0x1400f9f4f  inc     dword ptr [rdi+698h]
0x1400f9f55  mov     rdx, rbx
0x1400f9f58  mov     ecx, 4
0x1400f9f5d  call    cs:__imp_WdLogSingleEntry1
0x1400f9f64  nop     dword ptr [rax+rax+00h]
0x1400f9f69  mov     rax, [rsp+0A8h+var_78]
0x1400f9f6e  mov     edi, 1
0x1400f9f73  mov     rcx, [rsp+0A8h+var_70]
0x1400f9f78  mov     cs:WdLogGlobalForLineNumber, 8EFh
0x1400f9f82  mov     [rbx+20h], rax
0x1400f9f86  mov     [rbx+28h], rcx
0x1400f9f8a  mov     [rbx+30h], rax
0x1400f9f8e  mov     [rbx+18h], edi
0x1400f9f91  mov     [rbx+40h], rbp
0x1400f9f95  mov     [rbx+48h], rbp
0x1400f9f99  mov     [rbx+50h], r14
0x1400f9f9d  mov     [rbx+90h], r15d
0x1400f9fa4  inc     qword ptr [r14+8]
0x1400f9fa8  mov     rcx, [rbx+20h]; Set
0x1400f9fac  call    cs:__imp_RtlFindLeastSignificantBit
0x1400f9fb3  nop     dword ptr [rax+rax+00h]
0x1400f9fb8  test    al, al
0x1400f9fba  js      loc_1400FA827
0x1400f9fc0  movzx   ecx, al
0x1400f9fc3  mov     eax, edi
0x1400f9fc5  shl     rax, cl
0x1400f9fc8  mov     [rbx+38h], rax
0x1400f9fcc  mov     r8, rbx
0x1400f9fcf  mov     qword ptr [rbx+58h], 3
0x1400f9fd7  xor     edx, edx
0x1400f9fd9  mov     [rbx+60h], ebp
0x1400f9fdc  mov     [rbx+78h], rbp
0x1400f9fe0  mov     word ptr [rbx+64h], 0
0x1400f9fe6  mov     [rbx+68h], rbp
0x1400f9fea  mov     [rbx+70h], rbp
0x1400f9fee  mov     [rbx+80h], rbp
0x1400f9ff5  mov     [rbx+88h], rbp
0x1400f9ffc  mov     rcx, [rbx+50h]
0x1400fa000  mov     byte ptr [rbx+94h], 0
0x1400fa007  call    ?NotifyMultirangeEvent@VIDMM_RECYCLE_BLOCK@@QEAAXW4RangeOp@1@PEAX@Z; VIDMM_RECYCLE_BLOCK::NotifyMultirangeEvent(VIDMM_RECYCLE_BLOCK::RangeOp,void *)
0x1400fa00c  mov     r8, rdi
0x1400fa00f  lea     r9, [rbx+40h]
0x1400fa013  mov     rax, [rsp+0A8h+var_68]
0x1400fa018  xor     cl, cl
0x1400fa01a  mov     [rbx+48h], rax
0x1400fa01e  mov     [r9], rsi
0x1400fa021  test    cl, cl
0x1400fa023  jnz     short loc_1400FA05E
0x1400fa025  mov     edx, [rbx+90h]
0x1400fa02b  test    edx, edx
0x1400fa02d  jnz     loc_1400FA0FC
0x1400fa033  mov     [rsi+88h], rbx
0x1400fa03a  cmp     rsi, [rbx+48h]
0x1400fa03e  jz      loc_1400FA10D
0x1400fa044  mov     rax, [rsi+48h]
0x1400fa048  mov     rdx, [rsi+78h]
0x1400fa04c  add     rax, 48h ; 'H'
0x1400fa050  cmp     rdx, rax
0x1400fa053  jnz     loc_1400FA656
0x1400fa059  mov     rsi, rbp
0x1400fa05c  jmp     short loc_1400FA021
0x1400fa05e  mov     rdi, [r14+20h]
0x1400fa062  mov     r8, r12
0x1400fa065  mov     rdx, rbx
0x1400fa068  mov     ecx, 4
0x1400fa06d  call    cs:__imp_WdLogSingleEntry2
0x1400fa074  nop     dword ptr [rax+rax+00h]
0x1400fa079  mov     rax, [rsp+0A8h+arg_0]
0x1400fa081  mov     rcx, [rsp+0A8h+arg_8]
0x1400fa089  mov     cs:WdLogGlobalForLineNumber, 20E5h
0x1400fa093  mov     [rsp+0A8h+var_50], 0
0x1400fa098  mov     rcx, [rcx]
0x1400fa09b  sub     rcx, [rax]
0x1400fa09e  mov     rax, [rsp+0A8h+arg_10]
0x1400fa0a6  mov     [rsp+0A8h+var_60], rcx
0x1400fa0ab  mov     rax, [rax]
0x1400fa0ae  mov     [rsp+0A8h+var_58], rax
0x1400fa0b3  cmp     r12d, 2
0x1400fa0b7  jnz     loc_1400FA169
0x1400fa0bd  lea     rsi, [rdi+40h]
0x1400fa0c1  xor     r8b, r8b
0x1400fa0c4  mov     rdi, [rsi]
0x1400fa0c7  test    rdi, rdi
0x1400fa0ca  jz      short loc_1400FA117
0x1400fa0cc  nop     dword ptr [rax+00h]
0x1400fa0d0  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x1400fa0d3  lea     rcx, [rsp+0A8h+var_60]; void *
0x1400fa0d8  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400fa0dd  test    eax, eax
0x1400fa0df  js      short loc_1400FA0EF
0x1400fa0e1  mov     rax, [rdi+8]
0x1400fa0e5  test    rax, rax
0x1400fa0e8  jz      short loc_1400FA114
0x1400fa0ea  mov     rdi, rax
0x1400fa0ed  jmp     short loc_1400FA0D0
0x1400fa0ef  mov     rax, [rdi]
0x1400fa0f2  test    rax, rax
0x1400fa0f5  jnz     short loc_1400FA0EA
0x1400fa0f7  xor     r8b, r8b
0x1400fa0fa  jmp     short loc_1400FA117
0x1400fa0fc  sub     edx, 1
0x1400fa0ff  jnz     short loc_1400FA154
0x1400fa101  mov     [rsi+90h], rbx
0x1400fa108  jmp     loc_1400FA03A
0x1400fa10d  mov     cl, 1
0x1400fa10f  jmp     loc_1400FA021
0x1400fa114  mov     r8b, 1
0x1400fa117  mov     r9, rbx
0x1400fa11a  mov     rdx, rdi
0x1400fa11d  mov     rcx, rsi
0x1400fa120  call    cs:__imp_RtlAvlInsertNodeEx
0x1400fa127  nop     dword ptr [rax+rax+00h]
0x1400fa12c  mov     [rbx+58h], r12d
0x1400fa130  cmp     qword ptr [r14], 1
0x1400fa134  jz      loc_1400FA8D1
0x1400fa13a  mov     rax, rbx
0x1400fa13d  jmp     loc_1400F9D4F
0x1400fa142  lea     rcx, [r13+40h]
0x1400fa146  jmp     loc_1400F9DEE
0x1400fa14b  lea     rcx, [rsi+40h]
0x1400fa14f  jmp     loc_1400F9E44
0x1400fa154  cmp     edx, 1
0x1400fa157  jnz     loc_1400FA854
0x1400fa15d  mov     [rsi+98h], rbx
0x1400fa164  jmp     loc_1400FA03A
0x1400fa169  test    r12d, r12d
0x1400fa16c  jnz     loc_1400FA51D
0x1400fa172  lea     rsi, [rdi+30h]
0x1400fa176  xor     r8b, r8b
0x1400fa179  mov     rdi, [rsi]
0x1400fa17c  test    rdi, rdi
0x1400fa17f  jz      short loc_1400FA117
0x1400fa181  mov     rdx, rdi; struct _RTL_BALANCED_NODE *
0x1400fa184  lea     rcx, [rsp+0A8h+var_60]; void *
0x1400fa189  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400fa18e  test    eax, eax
0x1400fa190  js      short loc_1400FA1A4
0x1400fa192  mov     rax, [rdi+8]
0x1400fa196  test    rax, rax
0x1400fa199  jz      loc_1400FA114
0x1400fa19f  mov     rdi, rax
0x1400fa1a2  jmp     short loc_1400FA181
0x1400fa1a4  mov     rax, [rdi]
0x1400fa1a7  test    rax, rax
  ... truncated ...
```
