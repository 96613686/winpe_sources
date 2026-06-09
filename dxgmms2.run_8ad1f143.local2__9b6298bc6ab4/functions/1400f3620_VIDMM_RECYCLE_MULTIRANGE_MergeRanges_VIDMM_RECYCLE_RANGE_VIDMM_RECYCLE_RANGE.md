# VIDMM_RECYCLE_MULTIRANGE::MergeRanges(VIDMM_RECYCLE_RANGE *,VIDMM_RECYCLE_RANGE *)

- ea: `0x1400f3620`
- end: `0x1400f4033`
- name: `?MergeRanges@VIDMM_RECYCLE_MULTIRANGE@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@0@Z`
- size: `2579`
- prototype: `void(VIDMM_RECYCLE_MULTIRANGE *__hidden this, struct VIDMM_RECYCLE_RANGE *, struct VIDMM_RECYCLE_RANGE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400f34c0`

## callees

- `0x14001265c`
- `0x140030870`
- `0x140030ae0`
- `0x140031624`
- `0x140034610`
- `0x140035630`
- `0x140035e08`
- `0x1400f3620`
- `0x14011daf0`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400f3ee8`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400f3ee8`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f3bef`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f3bef`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f3d75`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f3d75`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f38cb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f38cb`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f3ea3`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f4022`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f3ea3`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f4022`
- `watchdog!WdLogSingleEntry5` at `0x1400f3975`
- `watchdog!WdLogSingleEntry5` at `0x1400f39e0`
- `watchdog!WdLogSingleEntry5` at `0x1400f3b18`
- `watchdog!WdLogSingleEntry5` at `0x1400f3f63`
- `watchdog!WdLogSingleEntry5` at `0x1400f3fc0`
- `watchdog!WdLogSingleEntry5` at `0x1400f3975`
- `watchdog!WdLogSingleEntry5` at `0x1400f39e0`
- `watchdog!WdLogSingleEntry5` at `0x1400f3b18`
- `watchdog!WdLogSingleEntry5` at `0x1400f3f63`
- `watchdog!WdLogSingleEntry5` at `0x1400f3fc0`
- `watchdog!WdLogSingleEntry1` at `0x1400f37a9`
- `watchdog!WdLogSingleEntry1` at `0x1400f37a9`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f394a`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f39b7`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f3aed`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f3f38`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f3f95`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f393a`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f39a8`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f3add`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f3f28`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f3f85`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_RECYCLE_MULTIRANGE::MergeRanges(
        VIDMM_RECYCLE_BLOCK **this,
        struct VIDMM_RECYCLE_RANGE *a2,
        unsigned __int64 a3)
{
  struct VIDMM_RECYCLE_RANGE *v4; // r14
  VIDMM_RECYCLE_MULTIRANGE *v5; // rdx
  __int64 v6; // r15
  int v7; // esi
  char v8; // al
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // rax
  char v12; // bp
  int v13; // r9d
  __int64 v14; // rcx
  struct VIDMM_RECYCLE_RANGE *v15; // r12
  __int64 v16; // rcx
  __int64 v17; // rdi
  int v18; // r8d
  __int64 v19; // rax
  struct VIDMM_RECYCLE_RANGE **v20; // rdx
  _QWORD *v21; // rax
  struct VIDMM_RECYCLE_RANGE *v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  bool v25; // cl
  unsigned __int64 v26; // rcx
  int v27; // ecx
  __int64 v28; // rcx
  struct VIDMM_RECYCLE_BLOCK *v29; // rdx
  _QWORD *v30; // r8
  VIDMM_RECYCLE_BLOCK *v31; // rbp
  __int64 v32; // rdi
  int v33; // eax
  __int64 v34; // rax
  _QWORD *v35; // rbx
  CCHAR LeastSignificantBit; // al
  __int64 v37; // rax
  __int64 v38; // rdi
  __int64 *v39; // rdx
  VIDMM_RECYCLE_BLOCK *v40; // rdi
  bool v41; // zf
  int v42; // esi
  int v43; // esi
  __int64 v44; // rcx
  struct VIDMM_RECYCLE_BLOCK *v45; // rdx
  _QWORD *v46; // r8
  VIDMM_RECYCLE_BLOCK *v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rcx
  bool v51; // [rsp+60h] [rbp-88h]
  bool v52; // [rsp+61h] [rbp-87h]
  char v53; // [rsp+62h] [rbp-86h]
  char v54; // [rsp+63h] [rbp-85h]
  char v55; // [rsp+64h] [rbp-84h]
  char v56; // [rsp+65h] [rbp-83h]
  int v57; // [rsp+68h] [rbp-80h]
  int v58; // [rsp+6Ch] [rbp-7Ch]
  __int64 v59; // [rsp+70h] [rbp-78h]
  __int64 v60; // [rsp+78h] [rbp-70h]
  __int64 v61; // [rsp+80h] [rbp-68h]
  __int64 v62; // [rsp+88h] [rbp-60h]
  _QWORD *v63; // [rsp+90h] [rbp-58h]
  __int64 v64; // [rsp+98h] [rbp-50h]
  unsigned __int8 v66; // [rsp+F8h] [rbp+10h]
  char v67; // [rsp+100h] [rbp+18h]
  bool v68; // [rsp+108h] [rbp+20h]

  v4 = (struct VIDMM_RECYCLE_RANGE *)a3;
  v5 = (VIDMM_RECYCLE_MULTIRANGE *)this;
  v6 = *((_QWORD *)a2 + 17);
  v7 = *((_DWORD *)a2 + 16);
  v59 = *((_QWORD *)a2 + 4);
  v60 = *(_QWORD *)(a3 + 40);
  v58 = *((_DWORD *)a2 + 23);
  v67 = 0;
  v53 = 0;
  if ( v6 )
  {
    v8 = *(_QWORD *)(v6 + 64) == (_QWORD)a2;
    v67 = v8;
    if ( *(_QWORD *)(v6 + 72) != a3 )
      goto LABEL_61;
    v53 = 1;
  }
  while ( 2 )
  {
    v9 = *((_QWORD *)a2 + 18);
    v68 = 0;
    v54 = 0;
    if ( v9 )
    {
      v25 = *(_QWORD *)(v9 + 64) == (_QWORD)a2;
      v68 = v25;
      if ( *(struct VIDMM_RECYCLE_RANGE **)(v9 + 72) == v4 )
        v54 = 1;
      else
LABEL_107:
        v68 = v25;
    }
    v10 = *((_QWORD *)a2 + 19);
    v61 = v10;
    v51 = 0;
    v55 = 0;
    if ( v10 )
    {
      v51 = *(_QWORD *)(v10 + 64) == (_QWORD)a2;
      if ( *(struct VIDMM_RECYCLE_RANGE **)(v10 + 72) == v4 )
        v55 = 1;
      else
        v51 = *(_QWORD *)(v10 + 64) == (_QWORD)a2;
    }
    v11 = *((_QWORD *)a2 + 20);
    v62 = v11;
    v52 = 0;
    v56 = 0;
    if ( v11 )
    {
      v52 = *(_QWORD *)(v11 + 64) == (_QWORD)a2;
      if ( *(struct VIDMM_RECYCLE_RANGE **)(v11 + 72) == v4 )
        v56 = 1;
      else
        v52 = *(_QWORD *)(v11 + 64) == (_QWORD)a2;
    }
    v12 = 0;
    v63 = (_QWORD *)*((_QWORD *)a2 + 16);
    v64 = *(_QWORD *)(a3 + 120);
    ++**((_QWORD **)v5 + 10);
    v13 = *((_DWORD *)a2 + 20);
    LOBYTE(a3) = 0;
    v66 = 0;
    v57 = v13;
LABEL_8:
    v14 = *((_QWORD *)a2 + 15);
    if ( v14 == *((_QWORD *)a2 + 9) + 72LL )
    {
      v15 = 0;
      goto LABEL_10;
    }
    while ( 1 )
    {
      v15 = (struct VIDMM_RECYCLE_RANGE *)(v14 - 120);
LABEL_10:
      if ( v7 != 3 && (unsigned int)(v7 - 4) >= 2 )
        goto LABEL_12;
      v20 = (struct VIDMM_RECYCLE_RANGE **)*((_QWORD *)a2 + 13);
      v21 = (_QWORD *)((char *)a2 + 104);
      if ( v20[1] != (struct VIDMM_RECYCLE_RANGE *)((char *)a2 + 104) )
        goto LABEL_56;
      v22 = (struct VIDMM_RECYCLE_RANGE *)*((_QWORD *)a2 + 14);
      if ( *(_QWORD **)v22 != v21 )
        goto LABEL_56;
      *(_QWORD *)v22 = v20;
      v20[1] = v22;
      *v21 = 0;
      v23 = *((_DWORD *)a2 + 16);
      *((_QWORD *)a2 + 14) = 0;
      *((_QWORD *)a2 + 12) = 0;
      if ( v23 == 5 )
        goto LABEL_45;
      if ( (unsigned int)(v23 - 3) > 1
        || (v26 = *((_QWORD *)a2 + 4) - *((_QWORD *)a2 + 5),
            (__int64)(v26 + _InterlockedExchangeAdd64(&VIDMM_RECYCLE_HEAP_MGR::_GlobalOutstandingDebouncedUnlock, v26)) >= 0)
        || !g_IsInternalRelease )
      {
        v5 = (VIDMM_RECYCLE_MULTIRANGE *)this;
        goto LABEL_12;
      }
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 9);
      WdLogGlobalForLineNumber = 222;
LABEL_40:
      if ( (_DWORD)v24 )
        break;
      if ( !dword_140086500 || !v13 || !g_IsInternalRelease )
        goto LABEL_16;
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(v24, 270, 9);
      WdLogGlobalForLineNumber = 222;
LABEL_45:
      VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingDecommit(
        *((_QWORD *)a2 + 4) - *((_QWORD *)a2 + 5),
        (struct VIDMM_RECYCLE_BLOCK *)v20);
      a3 = v66;
      v13 = v57;
      v5 = (VIDMM_RECYCLE_MULTIRANGE *)this;
LABEL_12:
      if ( a2 == v4 )
        v12 = 1;
      if ( !(_BYTE)a3 )
      {
        v66 = 1;
        goto LABEL_16;
      }
      v24 = *((unsigned int *)a2 + 20);
      if ( (_DWORD)v24 != 2 )
        goto LABEL_40;
      if ( !dword_140086500 || v13 || !g_IsInternalRelease )
      {
        if ( v13 == 1 )
          v57 = 2;
        goto LABEL_16;
      }
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 9);
      WdLogGlobalForLineNumber = 222;
    }
    v27 = v24 - 1;
    if ( !v27 )
    {
      if ( !dword_140086500 || v13 || !g_IsInternalRelease )
        goto LABEL_16;
      g_DxgMmsBugcheckExportIndex = 1;
      v8 = WdLogSingleEntry5(0, 270, 9);
      WdLogGlobalForLineNumber = 222;
LABEL_61:
      v67 = v8;
      continue;
    }
    break;
  }
  if ( v27 != 2 )
    goto LABEL_16;
  if ( dword_140086500 && !v13 && g_IsInternalRelease )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9);
    WdLogGlobalForLineNumber = 222;
    goto LABEL_107;
  }
  if ( v13 == 1 || v13 == 2 )
    v57 = 3;
LABEL_16:
  v16 = *(_QWORD *)(*((_QWORD *)v5 + 10) + 32LL);
  v17 = *(_QWORD *)(v16 + 8);
  if ( (byte_140086202 & 0x40) != 0 )
    McTemplateK0x_EtwWriteTransfer(v16, EventRecycleRangeDestroy, a3, a2);
  WdLogSingleEntry1(4, a2);
  WdLogGlobalForLineNumber = 1110;
  VIDMM_RECYCLE_BLOCK::NotifyRangeEvent(*((_QWORD *)a2 + 9), 1, a2);
  VIDMM_RECYCLE_BLOCK::ReleaseReference(*((VIDMM_RECYCLE_BLOCK **)a2 + 9));
  *((_BYTE *)a2 + 168) = 1;
  v19 = *(unsigned int *)(v17 + 1616);
  if ( (unsigned int)v19 >= 4 )
  {
    ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v17 + 1312), a2);
  }
  else
  {
    *(_QWORD *)(v17 + 8 * v19 + 1624) = a2;
    ++*(_DWORD *)(v17 + 1616);
  }
  --*(_DWORD *)(v17 + 1688);
  if ( !v12 )
  {
    a3 = v66;
    a2 = v15;
    v5 = (VIDMM_RECYCLE_MULTIRANGE *)this;
    v13 = v57;
    goto LABEL_8;
  }
  v31 = this[10];
  v32 = *(_QWORD *)(*((_QWORD *)v31 + 4) + 8LL);
  v33 = *(_DWORD *)(v32 + 1616);
  if ( v33 )
  {
    v34 = (unsigned int)(v33 - 1);
    v35 = *(_QWORD **)(v32 + 8 * v34 + 1624);
    *(_QWORD *)(v32 + 8 * v34 + 1624) = 0;
    --*(_DWORD *)(v32 + 1616);
  }
  else
  {
    v35 = ExAllocateFromLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v32 + 1312));
  }
  if ( v35 )
  {
    ++*(_DWORD *)(v32 + 1688);
    v35[4] = v59;
    v35[5] = v60;
    *((_DWORD *)v35 + 6) = 0;
    v35[9] = v31;
    *((_DWORD *)v35 + 16) = 0;
    v35[11] = 3;
    v35[12] = 0;
    ++*(_QWORD *)v31;
    LeastSignificantBit = RtlFindLeastSignificantBit(v35[4]);
    v37 = LeastSignificantBit < 0 ? 0LL : 1LL << LeastSignificantBit;
    v35[7] = v37;
    v35[6] = 0;
    *((_DWORD *)v35 + 20) = 0;
    v35[13] = 0;
    v35[14] = 0;
    v35[15] = 0;
    v35[16] = 0;
    v38 = v35[9];
    v35[17] = 0;
    v35[18] = 0;
    v35[19] = 0;
    v35[20] = 0;
    *((_BYTE *)v35 + 168) = 0;
    v39 = *(__int64 **)(v38 + 152);
    if ( v39 )
    {
      v48 = *v39;
      v49 = 144 * v39[1];
      *(_DWORD *)(v49 + v48) = 0;
      *(_QWORD *)(v49 + v48 + 8) = v35;
      RtlCaptureStackBackTrace(1u, 0x10u, (PVOID *)(v49 + v48 + 16), 0);
      ++*(_QWORD *)(*(_QWORD *)(v38 + 152) + 8LL);
      v50 = *(_QWORD *)(v38 + 152);
      if ( *(_QWORD *)(v50 + 8) == *(_QWORD *)(v50 + 48) )
      {
        *(_QWORD *)(v50 + 8) = 0;
        *(_BYTE *)(*(_QWORD *)(v38 + 152) + 16LL) = 1;
      }
    }
  }
  v40 = this[10];
  v41 = (*(_QWORD *)v40)-- == 1;
  if ( v41 && !*((_QWORD *)v40 + 1) && v40 )
  {
    VIDMM_RECYCLE_BLOCK::~VIDMM_RECYCLE_BLOCK(v40);
    operator delete(v40);
  }
  *((_DWORD *)v35 + 23) = v58;
  *((_DWORD *)v35 + 20) = v57;
  v35[19] = v61;
  *((_DWORD *)v35 + 16) = v7;
  v35[17] = v6;
  v35[18] = v9;
  v35[20] = v62;
  if ( v67 )
    *(_QWORD *)(v6 + 64) = v35;
  if ( v53 )
    *(_QWORD *)(v6 + 72) = v35;
  if ( v68 )
    *(_QWORD *)(v9 + 64) = v35;
  if ( v54 )
    *(_QWORD *)(v9 + 72) = v35;
  if ( v51 )
    *(_QWORD *)(v61 + 64) = v35;
  if ( v55 )
    *(_QWORD *)(v61 + 72) = v35;
  if ( v52 )
    *(_QWORD *)(v62 + 64) = v35;
  if ( v56 )
    *(_QWORD *)(v62 + 72) = v35;
  v35[16] = v63;
  *v63 = v35 + 15;
  v35[15] = v64;
  *(_QWORD *)(v64 + 8) = v35 + 15;
  v42 = v7 - 3;
  if ( v42 )
  {
    v43 = v42 - 1;
    if ( v43 )
    {
      if ( v43 != 1 )
        goto LABEL_90;
      v44 = *(_QWORD *)(*((_QWORD *)this[10] + 4) + 8LL);
      v45 = (struct VIDMM_RECYCLE_BLOCK *)(v44 + 1560);
      v35[12] = *(_QWORD *)(v44 + 1576) + (unsigned int)dword_1400864F0;
      v46 = *(_QWORD **)(v44 + 1568);
      if ( *v46 == v44 + 1560 )
      {
        v35[13] = v45;
        v35[14] = v46;
        *v46 = v35 + 13;
        *(_QWORD *)(v44 + 1568) = v35 + 13;
        if ( !_InterlockedExchange((volatile __int32 *)(v44 + 1536), 1) && !*(_DWORD *)(v44 + 1584) )
          KeSetCoalescableTimer((PKTIMER)(v44 + 1376), (LARGE_INTEGER)-2000000LL, 0, 0x28u, (PKDPC)(v44 + 1440));
        VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingDecommit(v35[5] - v35[4], v45);
        goto LABEL_90;
      }
LABEL_56:
      __fastfail(3u);
    }
  }
  v28 = *(_QWORD *)(*((_QWORD *)this[10] + 4) + 8LL);
  v29 = (struct VIDMM_RECYCLE_BLOCK *)(v28 + 1544);
  v35[12] = *(_QWORD *)(v28 + 1576) + (unsigned int)dword_1400864EC;
  v30 = *(_QWORD **)(v28 + 1552);
  if ( *v30 != v28 + 1544 )
    goto LABEL_56;
  v35[13] = v29;
  v35[14] = v30;
  *v30 = v35 + 13;
  *(_QWORD *)(v28 + 1552) = v35 + 13;
  if ( !_InterlockedExchange((volatile __int32 *)(v28 + 1536), 1) && !*(_DWORD *)(v28 + 1584) )
    KeSetCoalescableTimer((PKTIMER)(v28 + 1376), (LARGE_INTEGER)-2000000LL, 0, 0x28u, (PKDPC)(v28 + 1440));
  VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingUnlock(v35[5] - v35[4], v29);
LABEL_90:
  if ( (byte_140086202 & 0x40) != 0 )
  {
    v47 = this[10];
    McTemplateK0pppppppqq_EtwWriteTransfer(
      *((_QWORD *)v47 + 4),
      (_DWORD)v47,
      v18,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v47 + 4) + 8LL) + 8LL) + 16LL),
      (char)v35,
      (char)v47,
      *((_QWORD *)v47 + 7),
      *((_QWORD *)v47 + 4),
      v35[4],
      v35[5],
      **((_DWORD **)v47 + 4),
      *((_DWORD *)v35 + 16));
  }
}

```

## disassembly

```asm
0x1400f3620  mov     [rsp+arg_0], rcx
0x1400f3625  push    rbx
0x1400f3626  push    rbp
0x1400f3627  push    rsi
0x1400f3628  push    rdi
0x1400f3629  push    r13
0x1400f362b  push    r14
0x1400f362d  push    r15
0x1400f362f  sub     rsp, 0B0h
0x1400f3636  mov     rbx, rdx
0x1400f3639  mov     r14, r8
0x1400f363c  mov     rdx, rcx
0x1400f363f  mov     rax, [rbx+20h]
0x1400f3643  mov     r15, [rbx+88h]
0x1400f364a  mov     esi, [rbx+40h]
0x1400f364d  mov     [rsp+0E8h+var_78], rax
0x1400f3652  mov     rax, [r8+28h]
0x1400f3656  mov     [rsp+0E8h+var_70], rax
0x1400f365b  mov     eax, [rbx+5Ch]
0x1400f365e  mov     [rsp+0E8h+var_7C], eax
0x1400f3662  xor     al, al
0x1400f3664  mov     [rsp+0E8h+arg_10], al
0x1400f366b  mov     [rsp+0E8h+var_86], al
0x1400f366f  test    r15, r15
0x1400f3672  jz      short loc_1400F3691
0x1400f3674  cmp     [r15+40h], rbx
0x1400f3678  setz    al
0x1400f367b  mov     [rsp+0E8h+arg_10], al
0x1400f3682  cmp     [r15+48h], r8
0x1400f3686  jnz     loc_1400F3B2E
0x1400f368c  mov     [rsp+0E8h+var_86], 1
0x1400f3691  mov     r13, [rbx+90h]
0x1400f3698  xor     cl, cl
0x1400f369a  mov     [rsp+0E8h+arg_18], cl
0x1400f36a1  mov     [rsp+0E8h+var_85], cl
0x1400f36a5  test    r13, r13
0x1400f36a8  jnz     loc_1400F38DC
0x1400f36ae  mov     rax, [rbx+98h]
0x1400f36b5  xor     cl, cl
0x1400f36b7  mov     [rsp+0E8h+var_68], rax
0x1400f36bf  mov     [rsp+0E8h+var_88], cl
0x1400f36c3  mov     [rsp+0E8h+var_84], cl
0x1400f36c7  test    rax, rax
0x1400f36ca  jnz     loc_1400F38FE
0x1400f36d0  mov     rax, [rbx+0A0h]
0x1400f36d7  xor     cl, cl
0x1400f36d9  mov     [rsp+0E8h+var_60], rax
0x1400f36e1  mov     [rsp+0E8h+var_87], cl
0x1400f36e5  mov     [rsp+0E8h+var_83], cl
0x1400f36e9  test    rax, rax
0x1400f36ec  jnz     loc_1400F3A74
0x1400f36f2  mov     rax, [rbx+80h]
0x1400f36f9  xor     bpl, bpl
0x1400f36fc  mov     [rsp+0E8h+var_58], rax
0x1400f3704  mov     rax, [r8+78h]
0x1400f3708  mov     [rsp+0E8h+var_50], rax
0x1400f3710  mov     rax, [rdx+50h]
0x1400f3714  mov     [rsp+0E8h+var_40], r12
0x1400f371c  inc     qword ptr [rax]
0x1400f371f  mov     r9d, [rbx+50h]
0x1400f3723  xor     r8b, r8b
0x1400f3726  mov     [rsp+0E8h+arg_8], r8b
0x1400f372e  mov     [rsp+0E8h+var_80], r9d
0x1400f3733  mov     rax, [rbx+48h]
0x1400f3737  mov     edi, 1
0x1400f373c  mov     rcx, [rbx+78h]
0x1400f3740  add     rax, 48h ; 'H'
0x1400f3744  cmp     rcx, rax
0x1400f3747  jnz     loc_1400F3FD6
0x1400f374d  xor     r12d, r12d
0x1400f3750  mov     ecx, esi
0x1400f3752  sub     ecx, 3
0x1400f3755  jz      loc_1400F382A
0x1400f375b  sub     ecx, 1
0x1400f375e  jz      loc_1400F382A
0x1400f3764  cmp     ecx, 1
0x1400f3767  jz      loc_1400F382A
0x1400f376d  cmp     rbx, r14
0x1400f3770  movzx   ebp, bpl
0x1400f3774  cmovz   ebp, edi
0x1400f3777  test    r8b, r8b
0x1400f377a  jnz     loc_1400F388C
0x1400f3780  mov     [rsp+0E8h+arg_8], 1
0x1400f3788  test    cs:byte_140086202, 40h
0x1400f378f  mov     rax, [rdx+50h]
0x1400f3793  mov     rcx, [rax+20h]
0x1400f3797  mov     rdi, [rcx+8]
0x1400f379b  jnz     loc_1400F3A1E
0x1400f37a1  mov     rdx, rbx
0x1400f37a4  mov     ecx, 4
0x1400f37a9  call    cs:__imp_WdLogSingleEntry1
0x1400f37b0  nop     dword ptr [rax+rax+00h]
0x1400f37b5  mov     cs:WdLogGlobalForLineNumber, 456h
0x1400f37bf  mov     r8, rbx
0x1400f37c2  mov     rcx, [rbx+48h]
0x1400f37c6  mov     edx, 1
0x1400f37cb  call    ?NotifyRangeEvent@VIDMM_RECYCLE_BLOCK@@QEAAXW4RangeOp@1@PEAX@Z; VIDMM_RECYCLE_BLOCK::NotifyRangeEvent(VIDMM_RECYCLE_BLOCK::RangeOp,void *)
0x1400f37d0  mov     rcx, [rbx+48h]; this
0x1400f37d4  call    ?ReleaseReference@VIDMM_RECYCLE_BLOCK@@QEAAXXZ; VIDMM_RECYCLE_BLOCK::ReleaseReference(void)
0x1400f37d9  mov     byte ptr [rbx+0A8h], 1
0x1400f37e0  mov     eax, [rdi+650h]
0x1400f37e6  cmp     eax, 4
0x1400f37e9  jnb     loc_1400F38C1
0x1400f37ef  mov     [rdi+rax*8+658h], rbx
0x1400f37f7  inc     dword ptr [rdi+650h]
0x1400f37fd  dec     dword ptr [rdi+698h]
0x1400f3803  test    bpl, bpl
0x1400f3806  jnz     loc_1400F3B71
0x1400f380c  movzx   r8d, [rsp+0E8h+arg_8]
0x1400f3815  mov     rbx, r12
0x1400f3818  mov     rdx, [rsp+0E8h+arg_0]
0x1400f3820  mov     r9d, [rsp+0E8h+var_80]
0x1400f3825  jmp     loc_1400F3733
0x1400f382a  mov     rdx, [rbx+68h]
0x1400f382e  lea     rax, [rbx+68h]
0x1400f3832  cmp     [rdx+8], rax
0x1400f3836  jnz     loc_1400F3AC0
0x1400f383c  mov     rcx, [rbx+70h]
0x1400f3840  cmp     [rcx], rax
0x1400f3843  jnz     loc_1400F3AC0
0x1400f3849  mov     [rcx], rdx
0x1400f384c  mov     [rdx+8], rcx
0x1400f3850  mov     qword ptr [rax], 0
0x1400f3857  mov     eax, [rbx+40h]
0x1400f385a  mov     qword ptr [rbx+70h], 0
0x1400f3862  mov     qword ptr [rbx+60h], 0
0x1400f386a  cmp     eax, 5
0x1400f386d  jz      loc_1400F39F6
0x1400f3873  add     eax, 0FFFFFFFDh
0x1400f3876  cmp     eax, 1
0x1400f3879  jbe     loc_1400F391D
0x1400f387f  mov     rdx, [rsp+0E8h+arg_0]
0x1400f3887  jmp     loc_1400F376D
0x1400f388c  mov     ecx, [rbx+50h]
0x1400f388f  cmp     ecx, 2
0x1400f3892  jnz     loc_1400F398B
0x1400f3898  cmp     cs:dword_140086500, 0
0x1400f389f  jz      short loc_1400F38AA
0x1400f38a1  test    r9d, r9d
0x1400f38a4  jz      loc_1400F3F85
0x1400f38aa  cmp     r9d, 1
0x1400f38ae  jnz     loc_1400F3788
0x1400f38b4  mov     [rsp+0E8h+var_80], 2
0x1400f38bc  jmp     loc_1400F3788
0x1400f38c1  mov     rcx, [rdi+520h]; Lookaside
0x1400f38c8  mov     rdx, rbx; Entry
0x1400f38cb  call    cs:__imp_ExFreeToLookasideListEx
0x1400f38d2  nop     dword ptr [rax+rax+00h]
0x1400f38d7  jmp     loc_1400F37FD
0x1400f38dc  cmp     [r13+40h], rbx
0x1400f38e0  setz    cl
0x1400f38e3  mov     [rsp+0E8h+arg_18], cl
0x1400f38ea  cmp     [r13+48h], r14
0x1400f38ee  jnz     loc_1400F3F79
0x1400f38f4  mov     [rsp+0E8h+var_85], 1
0x1400f38f9  jmp     loc_1400F36AE
0x1400f38fe  cmp     [rax+40h], rbx
0x1400f3902  setz    cl
0x1400f3905  mov     [rsp+0E8h+var_88], cl
0x1400f3909  cmp     [rax+48h], r14
0x1400f390d  jnz     loc_1400F3FDF
0x1400f3913  mov     [rsp+0E8h+var_84], 1
0x1400f3918  jmp     loc_1400F36D0
0x1400f391d  mov     rcx, [rbx+20h]
0x1400f3921  sub     rcx, [rbx+28h]
0x1400f3925  mov     rax, rcx
0x1400f3928  lock xadd cs:?_GlobalOutstandingDebouncedUnlock@VIDMM_RECYCLE_HEAP_MGR@@0_JA, rax; __int64 VIDMM_RECYCLE_HEAP_MGR::_GlobalOutstandingDebouncedUnlock
0x1400f3931  add     rax, rcx
0x1400f3934  jns     loc_1400F387F
0x1400f393a  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f3941  cmp     byte ptr [rax], 0
0x1400f3944  jz      loc_1400F387F
0x1400f394a  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f3951  mov     [rax], edi
0x1400f3953  mov     [rsp+0E8h+var_C0], 0
0x1400f395c  xor     r9d, r9d
0x1400f395f  mov     edx, 10Eh
0x1400f3964  mov     [rsp+0E8h+Dpc], 0
0x1400f396d  xor     ecx, ecx
0x1400f396f  mov     r8d, 9
0x1400f3975  call    cs:__imp_WdLogSingleEntry5
0x1400f397c  nop     dword ptr [rax+rax+00h]
0x1400f3981  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f398b  test    ecx, ecx
0x1400f398d  jnz     loc_1400F3A32
0x1400f3993  cmp     cs:dword_140086500, ecx
0x1400f3999  jz      loc_1400F3788
0x1400f399f  test    r9d, r9d
0x1400f39a2  jz      loc_1400F3788
0x1400f39a8  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f39af  cmp     [rax], cl
0x1400f39b1  jz      loc_1400F3788
0x1400f39b7  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f39be  mov     [rax], edi
0x1400f39c0  mov     [rsp+0E8h+var_C0], 0
0x1400f39c9  xor     r9d, r9d
0x1400f39cc  mov     edx, 10Eh
0x1400f39d1  mov     [rsp+0E8h+Dpc], 0
0x1400f39da  mov     r8d, 9
0x1400f39e0  call    cs:__imp_WdLogSingleEntry5
0x1400f39e7  nop     dword ptr [rax+rax+00h]
0x1400f39ec  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f39f6  mov     rcx, [rbx+20h]
0x1400f39fa  sub     rcx, [rbx+28h]; __int64
0x1400f39fe  call    ?UpdateOutstandingDecommit@VIDMM_RECYCLE_HEAP_MGR@@SAX_JPEAVVIDMM_RECYCLE_BLOCK@@@Z; VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingDecommit(__int64,VIDMM_RECYCLE_BLOCK *)
0x1400f3a03  movzx   r8d, [rsp+0E8h+arg_8]
0x1400f3a0c  mov     r9d, [rsp+0E8h+var_80]
0x1400f3a11  mov     rdx, [rsp+0E8h+arg_0]
0x1400f3a19  jmp     loc_1400F376D
0x1400f3a1e  mov     r9, rbx
0x1400f3a21  lea     rdx, EventRecycleRangeDestroy
0x1400f3a28  call    McTemplateK0x_EtwWriteTransfer
0x1400f3a2d  jmp     loc_1400F37A1
0x1400f3a32  sub     ecx, 1
0x1400f3a35  jz      loc_1400F3AC7
0x1400f3a3b  cmp     ecx, 2
0x1400f3a3e  jnz     loc_1400F3788
0x1400f3a44  cmp     cs:dword_140086500, 0
0x1400f3a4b  jz      short loc_1400F3A56
0x1400f3a4d  test    r9d, r9d
0x1400f3a50  jz      loc_1400F3F28
0x1400f3a56  mov     ecx, r9d
0x1400f3a59  sub     ecx, 1
0x1400f3a5c  jz      short loc_1400F3A67
0x1400f3a5e  cmp     ecx, 1
0x1400f3a61  jnz     loc_1400F3788
0x1400f3a67  mov     [rsp+0E8h+var_80], 3
0x1400f3a6f  jmp     loc_1400F3788
0x1400f3a74  cmp     [rax+40h], rbx
0x1400f3a78  setz    cl
0x1400f3a7b  mov     [rsp+0E8h+var_87], cl
0x1400f3a7f  cmp     [rax+48h], r14
0x1400f3a83  jnz     loc_1400F3FE8
0x1400f3a89  mov     [rsp+0E8h+var_83], 1
0x1400f3a8e  jmp     loc_1400F36F2
0x1400f3a93  mov     rax, [r14+50h]
0x1400f3a97  mov     rcx, [rax+20h]
0x1400f3a9b  mov     eax, cs:dword_1400864EC
0x1400f3aa1  mov     rcx, [rcx+8]
0x1400f3aa5  add     rax, [rcx+628h]
0x1400f3aac  lea     rdx, [rcx+608h]; struct VIDMM_RECYCLE_BLOCK *
0x1400f3ab3  mov     [rbx+60h], rax
0x1400f3ab7  mov     r8, [rdx+8]
0x1400f3abb  cmp     [r8], rdx
0x1400f3abe  jz      short loc_1400F3B3A
0x1400f3ac0  mov     ecx, 3
0x1400f3ac5  int     29h; Win8: RtlFailFast(ecx)
0x1400f3ac7  cmp     cs:dword_140086500, 0
0x1400f3ace  jz      loc_1400F3788
0x1400f3ad4  test    r9d, r9d
0x1400f3ad7  jnz     loc_1400F3788
0x1400f3add  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f3ae4  cmp     [rax], r9b
0x1400f3ae7  jz      loc_1400F3788
0x1400f3aed  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f3af4  mov     [rax], edi
0x1400f3af6  mov     [rsp+0E8h+var_C0], 0
0x1400f3aff  xor     r9d, r9d
0x1400f3b02  mov     edx, 10Eh
0x1400f3b07  mov     [rsp+0E8h+Dpc], 0
0x1400f3b10  xor     ecx, ecx
0x1400f3b12  mov     r8d, 9
0x1400f3b18  call    cs:__imp_WdLogSingleEntry5
0x1400f3b1f  nop     dword ptr [rax+rax+00h]
0x1400f3b24  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f3b2e  mov     [rsp+0E8h+arg_10], al
0x1400f3b35  jmp     loc_1400F3691
0x1400f3b3a  lea     rax, [rbx+68h]
0x1400f3b3e  mov     [rax], rdx
0x1400f3b41  mov     [rax+8], r8
0x1400f3b45  mov     [r8], rax
0x1400f3b48  mov     [rdx+8], rax
0x1400f3b4c  mov     eax, 1
0x1400f3b51  xchg    eax, [rcx+600h]
0x1400f3b57  test    eax, eax
0x1400f3b59  jz      loc_1400F3E72
0x1400f3b5f  mov     rcx, [rbx+28h]
0x1400f3b63  sub     rcx, [rbx+20h]; __int64
0x1400f3b67  call    ?UpdateOutstandingUnlock@VIDMM_RECYCLE_HEAP_MGR@@SAX_JPEAVVIDMM_RECYCLE_BLOCK@@@Z; VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingUnlock(__int64,VIDMM_RECYCLE_BLOCK *)
0x1400f3b6c  jmp     loc_1400F3D46
0x1400f3b71  mov     r14, [rsp+0E8h+arg_0]
0x1400f3b79  mov     rbp, [r14+50h]
0x1400f3b7d  mov     rax, [rbp+20h]
0x1400f3b81  mov     rdi, [rax+8]
0x1400f3b85  mov     eax, [rdi+650h]
0x1400f3b8b  test    eax, eax
0x1400f3b8d  jz      loc_1400F3D6E
0x1400f3b93  dec     eax
0x1400f3b95  xor     r12d, r12d
0x1400f3b98  mov     rbx, [rdi+rax*8+658h]
0x1400f3ba0  mov     [rdi+rax*8+658h], r12
0x1400f3ba8  dec     dword ptr [rdi+650h]
0x1400f3bae  test    rbx, rbx
0x1400f3bb1  jz      loc_1400F3C64
0x1400f3bb7  inc     dword ptr [rdi+698h]
0x1400f3bbd  mov     rax, [rsp+0E8h+var_78]
0x1400f3bc2  mov     [rbx+20h], rax
0x1400f3bc6  mov     rax, [rsp+0E8h+var_70]
0x1400f3bcb  mov     [rbx+28h], rax
0x1400f3bcf  mov     [rbx+18h], r12d
  ... truncated ...
```
