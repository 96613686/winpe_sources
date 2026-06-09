# VIDMM_RECYCLE_MULTIRANGE::MergeRanges(VIDMM_RECYCLE_RANGE *,VIDMM_RECYCLE_RANGE *)

- ea: `0x1400f8600`
- end: `0x1400f9013`
- name: `?MergeRanges@VIDMM_RECYCLE_MULTIRANGE@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@0@Z`
- size: `2579`
- prototype: `void(VIDMM_RECYCLE_MULTIRANGE *__hidden this, struct VIDMM_RECYCLE_RANGE *, struct VIDMM_RECYCLE_RANGE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400f84a0`

## callees

- `0x1400120fc`
- `0x14002e458`
- `0x14002e6c0`
- `0x14002f4a0`
- `0x140032f00`
- `0x140033f20`
- `0x140034c00`
- `0x1400f8600`
- `0x1401212d0`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400f8ec8`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400f8ec8`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f8bcf`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x1400f8bcf`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f8d55`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f8d55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f88ab`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f88ab`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f8e83`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f9002`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f8e83`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400f9002`
- `watchdog!WdLogSingleEntry5` at `0x1400f8955`
- `watchdog!WdLogSingleEntry5` at `0x1400f89c0`
- `watchdog!WdLogSingleEntry5` at `0x1400f8af8`
- `watchdog!WdLogSingleEntry5` at `0x1400f8f43`
- `watchdog!WdLogSingleEntry5` at `0x1400f8fa0`
- `watchdog!WdLogSingleEntry5` at `0x1400f8955`
- `watchdog!WdLogSingleEntry5` at `0x1400f89c0`
- `watchdog!WdLogSingleEntry5` at `0x1400f8af8`
- `watchdog!WdLogSingleEntry5` at `0x1400f8f43`
- `watchdog!WdLogSingleEntry5` at `0x1400f8fa0`
- `watchdog!WdLogSingleEntry1` at `0x1400f8789`
- `watchdog!WdLogSingleEntry1` at `0x1400f8789`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f892a`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f8997`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f8acd`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f8f18`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f8f75`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f891a`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f8988`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f8abd`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f8f08`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f8f65`

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
      WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
      WdLogGlobalForLineNumber = 227;
LABEL_40:
      if ( (_DWORD)v24 )
        break;
      if ( !dword_1400874D0 || !v13 || !g_IsInternalRelease )
        goto LABEL_16;
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(v24, 270, 9, 0, 0, 0);
      WdLogGlobalForLineNumber = 227;
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
      if ( !dword_1400874D0 || v13 || !g_IsInternalRelease )
      {
        if ( v13 == 1 )
          v57 = 2;
        goto LABEL_16;
      }
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
      WdLogGlobalForLineNumber = 227;
    }
    v27 = v24 - 1;
    if ( !v27 )
    {
      if ( !dword_1400874D0 || v13 || !g_IsInternalRelease )
        goto LABEL_16;
      g_DxgMmsBugcheckExportIndex = 1;
      v8 = WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
      WdLogGlobalForLineNumber = 227;
LABEL_61:
      v67 = v8;
      continue;
    }
    break;
  }
  if ( v27 != 2 )
    goto LABEL_16;
  if ( dword_1400874D0 && !v13 && g_IsInternalRelease )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9, 0, 0, 0);
    WdLogGlobalForLineNumber = 227;
    goto LABEL_107;
  }
  if ( v13 == 1 || v13 == 2 )
    v57 = 3;
LABEL_16:
  v16 = *(_QWORD *)(*((_QWORD *)v5 + 10) + 32LL);
  v17 = *(_QWORD *)(v16 + 8);
  if ( (byte_140087202 & 0x40) != 0 )
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
      v35[12] = *(_QWORD *)(v44 + 1576) + (unsigned int)dword_1400874C0;
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
  v35[12] = *(_QWORD *)(v28 + 1576) + (unsigned int)dword_1400874BC;
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
  if ( (byte_140087202 & 0x40) != 0 )
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
0x1400f8600  mov     [rsp+arg_0], rcx
0x1400f8605  push    rbx
0x1400f8606  push    rbp
0x1400f8607  push    rsi
0x1400f8608  push    rdi
0x1400f8609  push    r13
0x1400f860b  push    r14
0x1400f860d  push    r15
0x1400f860f  sub     rsp, 0B0h
0x1400f8616  mov     rbx, rdx
0x1400f8619  mov     r14, r8
0x1400f861c  mov     rdx, rcx
0x1400f861f  mov     rax, [rbx+20h]
0x1400f8623  mov     r15, [rbx+88h]
0x1400f862a  mov     esi, [rbx+40h]
0x1400f862d  mov     [rsp+0E8h+var_78], rax
0x1400f8632  mov     rax, [r8+28h]
0x1400f8636  mov     [rsp+0E8h+var_70], rax
0x1400f863b  mov     eax, [rbx+5Ch]
0x1400f863e  mov     [rsp+0E8h+var_7C], eax
0x1400f8642  xor     al, al
0x1400f8644  mov     [rsp+0E8h+arg_10], al
0x1400f864b  mov     [rsp+0E8h+var_86], al
0x1400f864f  test    r15, r15
0x1400f8652  jz      short loc_1400F8671
0x1400f8654  cmp     [r15+40h], rbx
0x1400f8658  setz    al
0x1400f865b  mov     [rsp+0E8h+arg_10], al
0x1400f8662  cmp     [r15+48h], r8
0x1400f8666  jnz     loc_1400F8B0E
0x1400f866c  mov     [rsp+0E8h+var_86], 1
0x1400f8671  mov     r13, [rbx+90h]
0x1400f8678  xor     cl, cl
0x1400f867a  mov     [rsp+0E8h+arg_18], cl
0x1400f8681  mov     [rsp+0E8h+var_85], cl
0x1400f8685  test    r13, r13
0x1400f8688  jnz     loc_1400F88BC
0x1400f868e  mov     rax, [rbx+98h]
0x1400f8695  xor     cl, cl
0x1400f8697  mov     [rsp+0E8h+var_68], rax
0x1400f869f  mov     [rsp+0E8h+var_88], cl
0x1400f86a3  mov     [rsp+0E8h+var_84], cl
0x1400f86a7  test    rax, rax
0x1400f86aa  jnz     loc_1400F88DE
0x1400f86b0  mov     rax, [rbx+0A0h]
0x1400f86b7  xor     cl, cl
0x1400f86b9  mov     [rsp+0E8h+var_60], rax
0x1400f86c1  mov     [rsp+0E8h+var_87], cl
0x1400f86c5  mov     [rsp+0E8h+var_83], cl
0x1400f86c9  test    rax, rax
0x1400f86cc  jnz     loc_1400F8A54
0x1400f86d2  mov     rax, [rbx+80h]
0x1400f86d9  xor     bpl, bpl
0x1400f86dc  mov     [rsp+0E8h+var_58], rax
0x1400f86e4  mov     rax, [r8+78h]
0x1400f86e8  mov     [rsp+0E8h+var_50], rax
0x1400f86f0  mov     rax, [rdx+50h]
0x1400f86f4  mov     [rsp+0E8h+var_40], r12
0x1400f86fc  inc     qword ptr [rax]
0x1400f86ff  mov     r9d, [rbx+50h]
0x1400f8703  xor     r8b, r8b
0x1400f8706  mov     [rsp+0E8h+arg_8], r8b
0x1400f870e  mov     [rsp+0E8h+var_80], r9d
0x1400f8713  mov     rax, [rbx+48h]
0x1400f8717  mov     edi, 1
0x1400f871c  mov     rcx, [rbx+78h]
0x1400f8720  add     rax, 48h ; 'H'
0x1400f8724  cmp     rcx, rax
0x1400f8727  jnz     loc_1400F8FB6
0x1400f872d  xor     r12d, r12d
0x1400f8730  mov     ecx, esi
0x1400f8732  sub     ecx, 3
0x1400f8735  jz      loc_1400F880A
0x1400f873b  sub     ecx, 1
0x1400f873e  jz      loc_1400F880A
0x1400f8744  cmp     ecx, 1
0x1400f8747  jz      loc_1400F880A
0x1400f874d  cmp     rbx, r14
0x1400f8750  movzx   ebp, bpl
0x1400f8754  cmovz   ebp, edi
0x1400f8757  test    r8b, r8b
0x1400f875a  jnz     loc_1400F886C
0x1400f8760  mov     [rsp+0E8h+arg_8], 1
0x1400f8768  test    cs:byte_140087202, 40h
0x1400f876f  mov     rax, [rdx+50h]
0x1400f8773  mov     rcx, [rax+20h]
0x1400f8777  mov     rdi, [rcx+8]
0x1400f877b  jnz     loc_1400F89FE
0x1400f8781  mov     rdx, rbx
0x1400f8784  mov     ecx, 4
0x1400f8789  call    cs:__imp_WdLogSingleEntry1
0x1400f8790  nop     dword ptr [rax+rax+00h]
0x1400f8795  mov     cs:WdLogGlobalForLineNumber, 456h
0x1400f879f  mov     r8, rbx
0x1400f87a2  mov     rcx, [rbx+48h]
0x1400f87a6  mov     edx, 1
0x1400f87ab  call    ?NotifyRangeEvent@VIDMM_RECYCLE_BLOCK@@QEAAXW4RangeOp@1@PEAX@Z; VIDMM_RECYCLE_BLOCK::NotifyRangeEvent(VIDMM_RECYCLE_BLOCK::RangeOp,void *)
0x1400f87b0  mov     rcx, [rbx+48h]; this
0x1400f87b4  call    ?ReleaseReference@VIDMM_RECYCLE_BLOCK@@QEAAXXZ; VIDMM_RECYCLE_BLOCK::ReleaseReference(void)
0x1400f87b9  mov     byte ptr [rbx+0A8h], 1
0x1400f87c0  mov     eax, [rdi+650h]
0x1400f87c6  cmp     eax, 4
0x1400f87c9  jnb     loc_1400F88A1
0x1400f87cf  mov     [rdi+rax*8+658h], rbx
0x1400f87d7  inc     dword ptr [rdi+650h]
0x1400f87dd  dec     dword ptr [rdi+698h]
0x1400f87e3  test    bpl, bpl
0x1400f87e6  jnz     loc_1400F8B51
0x1400f87ec  movzx   r8d, [rsp+0E8h+arg_8]
0x1400f87f5  mov     rbx, r12
0x1400f87f8  mov     rdx, [rsp+0E8h+arg_0]
0x1400f8800  mov     r9d, [rsp+0E8h+var_80]
0x1400f8805  jmp     loc_1400F8713
0x1400f880a  mov     rdx, [rbx+68h]
0x1400f880e  lea     rax, [rbx+68h]
0x1400f8812  cmp     [rdx+8], rax
0x1400f8816  jnz     loc_1400F8AA0
0x1400f881c  mov     rcx, [rbx+70h]
0x1400f8820  cmp     [rcx], rax
0x1400f8823  jnz     loc_1400F8AA0
0x1400f8829  mov     [rcx], rdx
0x1400f882c  mov     [rdx+8], rcx
0x1400f8830  mov     qword ptr [rax], 0
0x1400f8837  mov     eax, [rbx+40h]
0x1400f883a  mov     qword ptr [rbx+70h], 0
0x1400f8842  mov     qword ptr [rbx+60h], 0
0x1400f884a  cmp     eax, 5
0x1400f884d  jz      loc_1400F89D6
0x1400f8853  add     eax, 0FFFFFFFDh
0x1400f8856  cmp     eax, 1
0x1400f8859  jbe     loc_1400F88FD
0x1400f885f  mov     rdx, [rsp+0E8h+arg_0]
0x1400f8867  jmp     loc_1400F874D
0x1400f886c  mov     ecx, [rbx+50h]
0x1400f886f  cmp     ecx, 2
0x1400f8872  jnz     loc_1400F896B
0x1400f8878  cmp     cs:dword_1400874D0, 0
0x1400f887f  jz      short loc_1400F888A
0x1400f8881  test    r9d, r9d
0x1400f8884  jz      loc_1400F8F65
0x1400f888a  cmp     r9d, 1
0x1400f888e  jnz     loc_1400F8768
0x1400f8894  mov     [rsp+0E8h+var_80], 2
0x1400f889c  jmp     loc_1400F8768
0x1400f88a1  mov     rcx, [rdi+520h]; Lookaside
0x1400f88a8  mov     rdx, rbx; Entry
0x1400f88ab  call    cs:__imp_ExFreeToLookasideListEx
0x1400f88b2  nop     dword ptr [rax+rax+00h]
0x1400f88b7  jmp     loc_1400F87DD
0x1400f88bc  cmp     [r13+40h], rbx
0x1400f88c0  setz    cl
0x1400f88c3  mov     [rsp+0E8h+arg_18], cl
0x1400f88ca  cmp     [r13+48h], r14
0x1400f88ce  jnz     loc_1400F8F59
0x1400f88d4  mov     [rsp+0E8h+var_85], 1
0x1400f88d9  jmp     loc_1400F868E
0x1400f88de  cmp     [rax+40h], rbx
0x1400f88e2  setz    cl
0x1400f88e5  mov     [rsp+0E8h+var_88], cl
0x1400f88e9  cmp     [rax+48h], r14
0x1400f88ed  jnz     loc_1400F8FBF
0x1400f88f3  mov     [rsp+0E8h+var_84], 1
0x1400f88f8  jmp     loc_1400F86B0
0x1400f88fd  mov     rcx, [rbx+20h]
0x1400f8901  sub     rcx, [rbx+28h]
0x1400f8905  mov     rax, rcx
0x1400f8908  lock xadd cs:?_GlobalOutstandingDebouncedUnlock@VIDMM_RECYCLE_HEAP_MGR@@0_JA, rax; __int64 VIDMM_RECYCLE_HEAP_MGR::_GlobalOutstandingDebouncedUnlock
0x1400f8911  add     rax, rcx
0x1400f8914  jns     loc_1400F885F
0x1400f891a  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f8921  cmp     byte ptr [rax], 0
0x1400f8924  jz      loc_1400F885F
0x1400f892a  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f8931  mov     [rax], edi
0x1400f8933  mov     [rsp+0E8h+var_C0], 0
0x1400f893c  xor     r9d, r9d
0x1400f893f  mov     edx, 10Eh
0x1400f8944  mov     [rsp+0E8h+Dpc], 0
0x1400f894d  xor     ecx, ecx
0x1400f894f  mov     r8d, 9
0x1400f8955  call    cs:__imp_WdLogSingleEntry5
0x1400f895c  nop     dword ptr [rax+rax+00h]
0x1400f8961  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400f896b  test    ecx, ecx
0x1400f896d  jnz     loc_1400F8A12
0x1400f8973  cmp     cs:dword_1400874D0, ecx
0x1400f8979  jz      loc_1400F8768
0x1400f897f  test    r9d, r9d
0x1400f8982  jz      loc_1400F8768
0x1400f8988  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f898f  cmp     [rax], cl
0x1400f8991  jz      loc_1400F8768
0x1400f8997  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f899e  mov     [rax], edi
0x1400f89a0  mov     [rsp+0E8h+var_C0], 0
0x1400f89a9  xor     r9d, r9d
0x1400f89ac  mov     edx, 10Eh
0x1400f89b1  mov     [rsp+0E8h+Dpc], 0
0x1400f89ba  mov     r8d, 9
0x1400f89c0  call    cs:__imp_WdLogSingleEntry5
0x1400f89c7  nop     dword ptr [rax+rax+00h]
0x1400f89cc  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400f89d6  mov     rcx, [rbx+20h]
0x1400f89da  sub     rcx, [rbx+28h]; __int64
0x1400f89de  call    ?UpdateOutstandingDecommit@VIDMM_RECYCLE_HEAP_MGR@@SAX_JPEAVVIDMM_RECYCLE_BLOCK@@@Z; VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingDecommit(__int64,VIDMM_RECYCLE_BLOCK *)
0x1400f89e3  movzx   r8d, [rsp+0E8h+arg_8]
0x1400f89ec  mov     r9d, [rsp+0E8h+var_80]
0x1400f89f1  mov     rdx, [rsp+0E8h+arg_0]
0x1400f89f9  jmp     loc_1400F874D
0x1400f89fe  mov     r9, rbx
0x1400f8a01  lea     rdx, EventRecycleRangeDestroy
0x1400f8a08  call    McTemplateK0x_EtwWriteTransfer
0x1400f8a0d  jmp     loc_1400F8781
0x1400f8a12  sub     ecx, 1
0x1400f8a15  jz      loc_1400F8AA7
0x1400f8a1b  cmp     ecx, 2
0x1400f8a1e  jnz     loc_1400F8768
0x1400f8a24  cmp     cs:dword_1400874D0, 0
0x1400f8a2b  jz      short loc_1400F8A36
0x1400f8a2d  test    r9d, r9d
0x1400f8a30  jz      loc_1400F8F08
0x1400f8a36  mov     ecx, r9d
0x1400f8a39  sub     ecx, 1
0x1400f8a3c  jz      short loc_1400F8A47
0x1400f8a3e  cmp     ecx, 1
0x1400f8a41  jnz     loc_1400F8768
0x1400f8a47  mov     [rsp+0E8h+var_80], 3
0x1400f8a4f  jmp     loc_1400F8768
0x1400f8a54  cmp     [rax+40h], rbx
0x1400f8a58  setz    cl
0x1400f8a5b  mov     [rsp+0E8h+var_87], cl
0x1400f8a5f  cmp     [rax+48h], r14
0x1400f8a63  jnz     loc_1400F8FC8
0x1400f8a69  mov     [rsp+0E8h+var_83], 1
0x1400f8a6e  jmp     loc_1400F86D2
0x1400f8a73  mov     rax, [r14+50h]
0x1400f8a77  mov     rcx, [rax+20h]
0x1400f8a7b  mov     eax, cs:dword_1400874BC
0x1400f8a81  mov     rcx, [rcx+8]
0x1400f8a85  add     rax, [rcx+628h]
0x1400f8a8c  lea     rdx, [rcx+608h]; struct VIDMM_RECYCLE_BLOCK *
0x1400f8a93  mov     [rbx+60h], rax
0x1400f8a97  mov     r8, [rdx+8]
0x1400f8a9b  cmp     [r8], rdx
0x1400f8a9e  jz      short loc_1400F8B1A
0x1400f8aa0  mov     ecx, 3
0x1400f8aa5  int     29h; Win8: RtlFailFast(ecx)
0x1400f8aa7  cmp     cs:dword_1400874D0, 0
0x1400f8aae  jz      loc_1400F8768
0x1400f8ab4  test    r9d, r9d
0x1400f8ab7  jnz     loc_1400F8768
0x1400f8abd  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f8ac4  cmp     [rax], r9b
0x1400f8ac7  jz      loc_1400F8768
0x1400f8acd  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f8ad4  mov     [rax], edi
0x1400f8ad6  mov     [rsp+0E8h+var_C0], 0
0x1400f8adf  xor     r9d, r9d
0x1400f8ae2  mov     edx, 10Eh
0x1400f8ae7  mov     [rsp+0E8h+Dpc], 0
0x1400f8af0  xor     ecx, ecx
0x1400f8af2  mov     r8d, 9
0x1400f8af8  call    cs:__imp_WdLogSingleEntry5
0x1400f8aff  nop     dword ptr [rax+rax+00h]
0x1400f8b04  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400f8b0e  mov     [rsp+0E8h+arg_10], al
0x1400f8b15  jmp     loc_1400F8671
0x1400f8b1a  lea     rax, [rbx+68h]
0x1400f8b1e  mov     [rax], rdx
0x1400f8b21  mov     [rax+8], r8
0x1400f8b25  mov     [r8], rax
0x1400f8b28  mov     [rdx+8], rax
0x1400f8b2c  mov     eax, 1
0x1400f8b31  xchg    eax, [rcx+600h]
0x1400f8b37  test    eax, eax
0x1400f8b39  jz      loc_1400F8E52
0x1400f8b3f  mov     rcx, [rbx+28h]
0x1400f8b43  sub     rcx, [rbx+20h]; __int64
0x1400f8b47  call    ?UpdateOutstandingUnlock@VIDMM_RECYCLE_HEAP_MGR@@SAX_JPEAVVIDMM_RECYCLE_BLOCK@@@Z; VIDMM_RECYCLE_HEAP_MGR::UpdateOutstandingUnlock(__int64,VIDMM_RECYCLE_BLOCK *)
0x1400f8b4c  jmp     loc_1400F8D26
0x1400f8b51  mov     r14, [rsp+0E8h+arg_0]
0x1400f8b59  mov     rbp, [r14+50h]
0x1400f8b5d  mov     rax, [rbp+20h]
0x1400f8b61  mov     rdi, [rax+8]
0x1400f8b65  mov     eax, [rdi+650h]
0x1400f8b6b  test    eax, eax
0x1400f8b6d  jz      loc_1400F8D4E
0x1400f8b73  dec     eax
0x1400f8b75  xor     r12d, r12d
0x1400f8b78  mov     rbx, [rdi+rax*8+658h]
0x1400f8b80  mov     [rdi+rax*8+658h], r12
0x1400f8b88  dec     dword ptr [rdi+650h]
0x1400f8b8e  test    rbx, rbx
0x1400f8b91  jz      loc_1400F8C44
0x1400f8b97  inc     dword ptr [rdi+698h]
0x1400f8b9d  mov     rax, [rsp+0E8h+var_78]
0x1400f8ba2  mov     [rbx+20h], rax
0x1400f8ba6  mov     rax, [rsp+0E8h+var_70]
0x1400f8bab  mov     [rbx+28h], rax
0x1400f8baf  mov     [rbx+18h], r12d
  ... truncated ...
```
