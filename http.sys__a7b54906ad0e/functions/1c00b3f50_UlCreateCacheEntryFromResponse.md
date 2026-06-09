# UlCreateCacheEntryFromResponse

- ea: `0x1c00b3f50`
- end: `0x1c00b481c`
- name: `UlCreateCacheEntryFromResponse`
- size: `2252`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1c00b3c58`
- `0x1c0127578`

## callees

- `0x1c000a9c0`
- `0x1c000b280`
- `0x1c0011380`
- `0x1c001b640`
- `0x1c001b900`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f680`
- `0x1c00903a4`
- `0x1c0090c60`
- `0x1c0093264`
- `0x1c009a448`
- `0x1c00b3f50`
- `0x1c00b4824`
- `0x1c00b4938`
- `0x1c00ce4f4`
- `0x1c010e41c`
- `0x1c01162ac`
- `0x1c011e3fc`
- `0x1c011e93c`
- `0x1c0142738`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00b46d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1c00b46d0`
- `ntoskrnl!_strnicmp` at `0x1c00b4669`
- `ntoskrnl!_strnicmp` at `0x1c00b4669`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b474f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b474f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b4597`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b4597`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b475b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b475b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b4582`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b4582`

## pseudocode

```c
__int64 __fastcall UlCreateCacheEntryFromResponse(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 a4,
        __int64 a5,
        PVOID *a6)
{
  __int64 v6; // r15
  __int64 v9; // r13
  int v10; // r14d
  __int64 v11; // rax
  int v12; // esi
  __int64 v13; // r12
  __int64 v14; // rax
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // r9
  int v17; // r9d
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  char *v21; // rsi
  __int64 v22; // r14
  int v23; // eax
  __int64 v24; // rcx
  char *v25; // r15
  unsigned int v26; // eax
  bool v27; // al
  char v28; // al
  char *v29; // r14
  __int128 *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  volatile signed __int32 *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  _OWORD *v41; // rax
  __int64 v42; // rcx
  __int128 v43; // xmm0
  char v44; // bl
  __int64 v45; // r14
  __int64 v46; // rcx
  char *v47; // rax
  unsigned int v48; // ebx
  char *v49; // r15
  __int64 v50; // r13
  __int64 v51; // r14
  __int64 v52; // rdx
  __int64 v53; // r8
  char *v54; // rcx
  unsigned __int64 v55; // r9
  __int64 *v56; // rsi
  __int64 *v57; // rdx
  __int64 **v58; // r8
  char *v59; // rdx
  char *v60; // r8
  __int64 v61; // rax
  int v62; // eax
  int v63; // ecx
  __int64 v64; // rax
  volatile signed __int32 *v65; // rax
  PVOID v66; // r8
  unsigned int v68; // eax
  __int64 v69; // rdx
  char v70; // bl
  char v71; // bl
  int v72; // ecx
  int v73; // eax
  __int64 v74; // rcx
  PVOID v75; // rbx
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-60h]
  int LogDataCacheBufferSize; // [rsp+40h] [rbp-40h]
  unsigned int v78; // [rsp+40h] [rbp-40h]
  _WORD *v79; // [rsp+40h] [rbp-40h]
  PVOID P; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v81; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v82; // [rsp+54h] [rbp-2Ch]
  __int64 v83; // [rsp+58h] [rbp-28h]
  _QWORD v84[2]; // [rsp+60h] [rbp-20h] BYREF
  char *v85; // [rsp+70h] [rbp-10h]
  __int64 v86; // [rsp+78h] [rbp-8h]
  unsigned __int16 v87; // [rsp+C0h] [rbp+40h] BYREF
  char v88; // [rsp+D8h] [rbp+58h]

  v88 = a4;
  v6 = *(_QWORD *)(a1 + 24);
  P = 0;
  v83 = v6;
  v86 = 0;
  v87 = 0;
  v82 = 0;
  v9 = (unsigned int)a2;
  v10 = a5;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qLLlqq(a6, a2, a1, (unsigned int)a2, a3, a4, a5, a6);
  v11 = *(_QWORD *)(a1 + 320);
  v12 = *(_DWORD *)(v6 + 2048);
  v13 = *(unsigned int *)(a1 + 500);
  if ( v11 )
  {
    v86 = *(_QWORD *)(a1 + 320);
    LogDataCacheBufferSize = UlGetLogDataCacheBufferSize(v11, &v87);
    v17 = LogDataCacheBufferSize;
    if ( LogDataCacheBufferSize < 0 )
      goto LABEL_101;
  }
  if ( (unsigned int)(*(_DWORD *)(v6 + 1432) - 2) <= 1 )
  {
    LogDataCacheBufferSize = UlGenerateRoutingToken(v6, 2);
    v17 = LogDataCacheBufferSize;
    if ( LogDataCacheBufferSize < 0 )
      goto LABEL_101;
    v12 += *(unsigned __int16 *)(v6 + 2082) - 2 * ((__int64)(*(_QWORD *)(v6 + 2032) - *(_QWORD *)(v6 + 2016)) >> 1);
  }
  v14 = *(unsigned int *)(a1 + 188);
  v15 = v87 + (unsigned __int64)*(unsigned int *)(a1 + 152);
  v85 = (char *)v87;
  v16 = *(unsigned int *)(a1 + 168) + 1LL + v14 + 24 * v13 + v15;
  if ( v16 > 0xFFFFFFFF )
  {
    v17 = -1073741675;
    LogDataCacheBufferSize = -1073741675;
    goto LABEL_101;
  }
  if ( (int)v9 + *(_DWORD *)(a1 + 76) < (unsigned int)v9 )
  {
    v17 = -1073741675;
    LogDataCacheBufferSize = -1073741675;
    goto LABEL_101;
  }
  BugCheckOnFailure[0] = v9 + *(_DWORD *)(a1 + 76);
  LogDataCacheBufferSize = UlAllocateCacheEntry(
                             *(_QWORD *)(*(_QWORD *)(v6 + 24) + 960LL),
                             v10,
                             v12 + 2,
                             v16,
                             *(size_t *)BugCheckOnFailure,
                             (__int64)&P);
  v17 = LogDataCacheBufferSize;
  if ( LogDataCacheBufferSize < 0 )
  {
    v21 = (char *)P;
    goto LABEL_130;
  }
  v18 = v83;
  v19 = *(unsigned int *)(v83 + 1968);
  v20 = *(unsigned int *)(v83 + 1432);
  v78 = *(_DWORD *)(v83 + 1968);
  v81 = *(_DWORD *)(v83 + 1432);
  v21 = (char *)P;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
  {
    WPP_SF_qlqLLq(134, v19, P, 0, v83 + 2016, v20, v19, a1 + 200);
    v19 = v78;
    v20 = v81;
    v18 = v83;
  }
  v22 = *((_QWORD *)v21 + 1);
  *((_QWORD *)v21 + 5) = 0;
  *((_QWORD *)v21 + 6) = 0;
  *((_DWORD *)v21 + 30) = 0;
  v21[553] = 0;
  *((_QWORD *)v21 + 8) = 0;
  *((_QWORD *)v21 + 10) = 0;
  *((_QWORD *)v21 + 12) = 0;
  *((_QWORD *)v21 + 78) = v21 + 616;
  *((_QWORD *)v21 + 77) = v21 + 616;
  *((_DWORD *)v21 + 8) = 1;
  *((_WORD *)v21 + 56) = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
  {
    WPP_SF_qlqLLq(132, v19, v22, 0, v18 + 2016, v20, v19, a1 + 200);
    LODWORD(v19) = v78;
    v20 = v81;
  }
  v23 = *(_DWORD *)(v22 + 96);
  v24 = v83 + 2016;
  *(_DWORD *)(v22 + 104) = v19;
  *(_WORD *)(v22 + 100) = 0;
  LogDataCacheBufferSize = UlpBuildUriKeyFromCookedUrl(v24, 0, v20, v22 + 224, v23, v22 + 40);
  v17 = LogDataCacheBufferSize;
  if ( LogDataCacheBufferSize >= 0 && a1 != -200 )
  {
    *(_OWORD *)(v22 + 108) = *(_OWORD *)(a1 + 200);
    *(_OWORD *)(v22 + 124) = *(_OWORD *)(a1 + 216);
    *(_OWORD *)(v22 + 140) = *(_OWORD *)(a1 + 232);
    *(_OWORD *)(v22 + 156) = *(_OWORD *)(a1 + 248);
    *(_OWORD *)(v22 + 172) = *(_OWORD *)(a1 + 264);
    *(_OWORD *)(v22 + 188) = *(_OWORD *)(a1 + 280);
    *(_QWORD *)(v22 + 204) = *(_QWORD *)(a1 + 296);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
  {
    WPP_SF_D(133, WPP_ede9639403cc3db159114586db5b30dd_Traceguids);
    v17 = LogDataCacheBufferSize;
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
    {
      WPP_SF_D(135, WPP_ede9639403cc3db159114586db5b30dd_Traceguids);
      v17 = LogDataCacheBufferSize;
    }
  }
  if ( v17 >= 0 )
  {
    v25 = v21 + 672;
    v21[555] = *(_BYTE *)(a1 + 49);
    v26 = *(_DWORD *)(a1 + 152);
    if ( v26 )
    {
      memmove(v21 + 672, *(const void **)(a1 + 160), v26);
      *((_QWORD *)v21 + 20) = v25;
      *((_DWORD *)v21 + 38) = *(_DWORD *)(a1 + 152);
      v25 += *(unsigned int *)(a1 + 152);
    }
    else
    {
      *((_QWORD *)v21 + 20) = &qword_1C005D868;
    }
    if ( *(_DWORD *)(a1 + 168) )
    {
      memmove(v25, *(const void **)(a1 + 176), *(unsigned int *)(a1 + 168));
      *((_QWORD *)v21 + 22) = v25;
      *((_DWORD *)v21 + 42) = *(_DWORD *)(a1 + 168);
      v25 += *(unsigned int *)(a1 + 168);
    }
    else
    {
      *((_QWORD *)v21 + 22) = &qword_1C005D868;
    }
    *((_DWORD *)v21 + 46) = *(_DWORD *)(a1 + 184);
    if ( *(_DWORD *)(a1 + 188) )
    {
      memmove(v25, *(const void **)(a1 + 192), *(unsigned int *)(a1 + 188));
      *((_QWORD *)v21 + 24) = v25;
      v68 = *(_DWORD *)(a1 + 188);
      *((_DWORD *)v21 + 47) = v68;
      *(_BYTE *)(v68 + *((_QWORD *)v21 + 24)) = 0;
      v25 += *(unsigned int *)(a1 + 188) + 1;
    }
    else
    {
      *((_QWORD *)v21 + 24) = &qword_1C005D868;
    }
    *((_QWORD *)v21 + 18) = *(_QWORD *)(a1 + 144);
    v27 = *(_BYTE *)(a1 + 40) || *(_BYTE *)(a1 + 43);
    v21[114] = v27;
    *((_WORD *)v21 + 58) = *(_WORD *)(a1 + 60);
    v28 = v88;
    *(_QWORD *)(v21 + 124) = a3;
    v21[554] = v28;
    v79 = v21 + 116;
    if ( (_DWORD)a3 == 2 )
    {
      v69 = MEMORY[0xFFFFF78000000014];
      v21 = (char *)P;
      *((_QWORD *)P + 17) = MEMORY[0xFFFFF78000000014];
      *((_QWORD *)v21 + 17) = v69 + 10000000LL * *((unsigned int *)v21 + 32);
    }
    v29 = v21 + 200;
    v30 = (__int128 *)(v83 + 1280);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
      WPP_SF_qq(166, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, v83 + 1280, v21 + 200);
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 8) != 0 )
      WPP_SF_qq(167, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, v30, v21 + 200);
    v31 = *((_QWORD *)v30 + 3);
    if ( v31 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v31 + 4));
      v21 = (char *)P;
    }
    v32 = *((_QWORD *)v30 + 4);
    if ( v32 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v32 + 4));
      v21 = (char *)P;
    }
    v33 = (volatile signed __int32 *)*((_QWORD *)v30 + 6);
    if ( v33 )
    {
      _InterlockedIncrement(v33);
      _InterlockedIncrement(*((volatile signed __int32 **)v30 + 6));
      v21 = (char *)P;
    }
    v34 = *((_QWORD *)v30 + 8);
    if ( v34 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v34 + 4));
      v21 = (char *)P;
    }
    v35 = *((_QWORD *)v30 + 9);
    if ( v35 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v35 + 4));
      v21 = (char *)P;
    }
    v36 = *((_QWORD *)v30 + 10);
    if ( v36 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v36 + 4));
      v21 = (char *)P;
    }
    v37 = *((_QWORD *)v30 + 12);
    if ( v37 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v37 + 4));
      v21 = (char *)P;
    }
    v38 = *((_QWORD *)v30 + 15);
    if ( v38 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v38 + 4));
      v21 = (char *)P;
    }
    v39 = *((_QWORD *)v30 + 13);
    if ( v39 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v39 + 4));
      v21 = (char *)P;
    }
    v40 = *((_QWORD *)v30 + 11);
    if ( v40 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v40 + 4));
      v21 = (char *)P;
    }
    v41 = v29;
    v42 = 2;
    do
    {
      v41 += 8;
      v43 = *v30;
      v30 += 8;
      *(v41 - 8) = v43;
      *(v41 - 7) = *(v30 - 7);
      *(v41 - 6) = *(v30 - 6);
      *(v41 - 5) = *(v30 - 5);
      *(v41 - 4) = *(v30 - 4);
      *(v41 - 3) = *(v30 - 3);
      *(v41 - 2) = *(v30 - 2);
      *(v41 - 1) = *(v30 - 1);
      --v42;
    }
    while ( v42 );
    *v41 = *v30;
    v41[1] = v30[1];
    v41[2] = v30[2];
    *((_QWORD *)v29 + 1) = *((_QWORD *)v29 + 6);
    memset(v29 + 160, 0, 0x50u);
    *((_DWORD *)v29 + 64) &= ~1u;
    *((_QWORD *)v29 + 31) = 0;
    *(_QWORD *)(v29 + 260) = 0;
    *((_QWORD *)v29 + 34) = 0;
    *((_WORD *)v29 + 140) = 0;
    *((_QWORD *)v29 + 36) = 0;
    *((_QWORD *)v29 + 7) = 0;
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
      WPP_SF_(168, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
    *((_DWORD *)v21 + 128) = *(_DWORD *)(a1 + 76);
    *((_DWORD *)v21 + 134) = *(_DWORD *)(a1 + 116);
    *((_DWORD *)v21 + 135) = *(_DWORD *)(a1 + 120);
    *((_DWORD *)v21 + 136) = *(_DWORD *)(a1 + 124);
    *((_DWORD *)v21 + 137) = *(_DWORD *)(a1 + 128);
    v21[552] = *(_BYTE *)(a1 + 112);
    if ( (*(_DWORD *)(a1 + 56) & 0x20) != 0 && *(_WORD *)(a1 + 60) == 206 && (_DWORD)v9 )
    {
      if ( *(_DWORD *)(a1 + 120) < 6u )
      {
        v17 = -1073741811;
        LogDataCacheBufferSize = -1073741811;
        goto LABEL_130;
      }
      v70 = UlLargeMemSetData(
              *((_QWORD *)v21 + 65),
              *(_QWORD *)(a1 + 88),
              *(unsigned int *)(a1 + 116),
              (unsigned int)v9);
      v71 = UlLargeMemSetData(*((_QWORD *)v21 + 65), "200 OK", 6, (unsigned int)(v9 + *(_DWORD *)(a1 + 116))) | v70;
      v44 = UlLargeMemSetData(
              *((_QWORD *)v21 + 65),
              *(_QWORD *)(a1 + 88) + *(unsigned int *)(a1 + 116) + (unsigned __int64)*(unsigned int *)(a1 + 120),
              (unsigned int)(*(_DWORD *)(a1 + 76) - *(_DWORD *)(a1 + 120) - *(_DWORD *)(a1 + 116)),
              (unsigned int)(*(_DWORD *)(a1 + 116) + v9 + 6))
          | v71;
      v72 = *(_DWORD *)(a1 + 120) - 6;
      v73 = *(_DWORD *)(a1 + 76) - v72;
      v82 = v72;
      *((_DWORD *)v21 + 128) = v73;
      *((_DWORD *)v21 + 134) = *(_DWORD *)(a1 + 116);
      *((_DWORD *)v21 + 135) = 6;
      *((_DWORD *)v21 + 136) = *(_DWORD *)(a1 + 124) - v72;
      *((_DWORD *)v21 + 137) = *(_DWORD *)(a1 + 128);
      *v79 = 200;
    }
    else
    {
      v44 = UlLargeMemSetData(*((_QWORD *)v21 + 65), *(_QWORD *)(a1 + 88), *(unsigned int *)(a1 + 76), (unsigned int)v9);
    }
    if ( v44 )
    {
      v45 = v83;
      *((_DWORD *)v21 + 129) = v9;
      LogDataCacheBufferSize = 0;
      if ( *(_QWORD *)(v45 + 2464) )
        UlFlCopyFlowRateParamsToCache(v21);
      if ( v86 )
      {
        LogDataCacheBufferSize = UlCopyLogDataToCache(v21, v86, v25, v87, &v81);
        v17 = LogDataCacheBufferSize;
        if ( LogDataCacheBufferSize < 0 )
          goto LABEL_130;
        v25 = &v25[(_QWORD)v85];
      }
      UlInitializeParsedHeaders(v21 + 632, v25, (unsigned int)v13);
      v46 = *((_QWORD *)v21 + 65);
      if ( (*(_BYTE *)(v46 + 10) & 5) != 0 )
        v47 = *(char **)(v46 + 24);
      else
        v47 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v46, 0, MmCached, 0, 0, 0x40000000u);
      v48 = 0;
      v49 = &v47[v9];
      if ( (_DWORD)v13 )
      {
        v50 = v82;
        v51 = 0;
        do
        {
          if ( *(_DWORD *)(a1 + 504) == v48 )
          {
            v59 = v21 + 632;
            v60 = &v49[*((unsigned int *)v21 + 134)];
            v17 = 0;
            v85 = v60;
            LogDataCacheBufferSize = 0;
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
            {
              WPP_SF_qqLqL(75, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids, v21 + 632, ":status", 7, v60, 3);
              v60 = v85;
              v59 = v21 + 632;
              v17 = 0;
            }
            if ( v59 )
            {
              v61 = *((unsigned int *)v59 + 2);
              if ( (unsigned int)v61 >= *((_DWORD *)v59 + 4) )
              {
                v17 = -1073741670;
                LogDataCacheBufferSize = -1073741670;
              }
              else
              {
                LogDataCacheBufferSize = 0;
                *(_QWORD *)(*(_QWORD *)v59 + 24 * v61) = ":status";
                *(_DWORD *)(*(_QWORD *)v59 + 24LL * *((unsigned int *)v59 + 2) + 16) = 7;
                *(_QWORD *)(*(_QWORD *)v59 + 24LL * *((unsigned int *)v59 + 2) + 8) = v60;
                *(_DWORD *)(*(_QWORD *)v59 + 24LL * *((unsigned int *)v59 + 2) + 20) = 3;
                v62 = _strnicmp(":status", ":status", 7u);
                v63 = *((_DWORD *)v21 + 160);
                if ( !v62 )
                  *((_DWORD *)v21 + 164) = v63;
                v17 = 0;
                *((_DWORD *)v21 + 160) = v63 + 1;
              }
            }
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
            {
              WPP_SF_D(76, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
              v17 = LogDataCacheBufferSize;
            }
            if ( v17 < 0 )
              goto LABEL_130;
          }
          else
          {
            v52 = v51 + *(_QWORD *)(a1 + 480);
            v53 = v51 + *((_QWORD *)v21 + 79);
            *(_DWORD *)(v53 + 16) = *(_DWORD *)(v52 + 16);
            v54 = *(char **)v52;
            v55 = *(_QWORD *)(a1 + 88);
            if ( *(_QWORD *)v52 >= v55 && (unsigned __int64)v54 < v55 + *(unsigned int *)(a1 + 76) )
              v54 = &v49[(unsigned int)((_DWORD)v54 - v55) - v50];
            *(_QWORD *)v53 = v54;
            *(_DWORD *)(v53 + 20) = *(_DWORD *)(v52 + 20);
            *(_QWORD *)(v53 + 8) = &v49[(unsigned int)(*(_DWORD *)(v52 + 8) - *(_DWORD *)(a1 + 88)) - v50];
            ++*((_DWORD *)v21 + 160);
          }
          ++v48;
          v51 += 24;
        }
        while ( v48 < (unsigned int)v13 );
        v45 = v83;
      }
      *((_DWORD *)v21 + 163) = v13;
      *((_DWORD *)v21 + 165) = *(_DWORD *)(a1 + 508);
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_qqq(42, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v45, *(_QWORD *)(v45 + 64), v21);
      v84[1] = v84;
      v84[0] = v84;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v45 + 2784, 0);
      v56 = (__int64 *)(v21 + 616);
      v57 = (__int64 *)(v45 + 2768);
      v58 = (__int64 **)v56[1];
      if ( *(__int64 **)(*v56 + 8) != v56
        || *v58 != v56
        || *(__int64 **)(*v57 + 8) != v57
        || **(__int64 ***)(v45 + 2776) != v57
        || (*v58 = v57,
            v56[1] = *(_QWORD *)(v45 + 2776),
            **(_QWORD **)(v45 + 2776) = v56,
            v64 = *v57,
            *(_QWORD *)(v45 + 2776) = v58,
            *(__int64 **)(v64 + 8) != v57)
        || *v58 != v57 )
      {
LABEL_76:
        __fastfail(3u);
      }
      *v58 = (__int64 *)v64;
      *(_QWORD *)(v64 + 8) = v58;
      *(_QWORD *)(v45 + 2776) = v45 + 2768;
      *v57 = (__int64)v57;
      *(_BYTE *)(v45 + 2792) = 1;
      ExReleasePushLockExclusiveEx(v45 + 2784, 0);
      KeLeaveCriticalRegion();
      while ( 1 )
      {
        v65 = (volatile signed __int32 *)v84[0];
        if ( (_QWORD *)v84[0] == v84 )
          break;
        if ( *(_QWORD **)(v84[0] + 8LL) != v84 )
          goto LABEL_76;
        v74 = *(_QWORD *)v84[0];
        if ( *(_QWORD *)(*(_QWORD *)v84[0] + 8LL) != v84[0] )
          goto LABEL_76;
        v84[0] = *(_QWORD *)v84[0];
        *(_QWORD *)(v74 + 8) = v84;
        *(_QWORD *)v65 = 0;
        *((_QWORD *)v65 + 1) = 0;
        if ( _InterlockedExchangeAdd(v65 - 6, 0xFFFFFFFF) == 1 )
          UxDuoFreeDeclarePushParameters((PVOID)(v65 - 6));
      }
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_(43, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
      v66 = P;
      *a6 = P;
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
        WPP_SF_q(137, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids, v66);
      goto LABEL_100;
    }
    v17 = -1073741670;
    LogDataCacheBufferSize = -1073741670;
  }
LABEL_130:
  if ( v21 && _InterlockedExchangeAdd((volatile signed __int32 *)v21 + 1, 0xFFFFFFFF) == 1 )
  {
    v75 = P;
    if ( *((_BYTE *)P + 113) )
      UlpRemoveEntryStats(P);
    UlDestroyUriCacheEntry(v75);
LABEL_100:
    v17 = LogDataCacheBufferSize;
  }
LABEL_101:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    WPP_SF_D(138, WPP_7cbf0d8611643fc15970b65376ef98c5_Traceguids);
    return (unsigned int)LogDataCacheBufferSize;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1c00b3f50  mov     [rsp-38h+arg_8], rbx
0x1c00b3f55  mov     [rsp-38h+arg_18], r9b
0x1c00b3f5a  push    rbp
0x1c00b3f5b  push    rsi
0x1c00b3f5c  push    rdi
0x1c00b3f5d  push    r12
0x1c00b3f5f  push    r13
0x1c00b3f61  push    r14
0x1c00b3f63  push    r15
0x1c00b3f65  mov     rbp, rsp
0x1c00b3f68  sub     rsp, 80h
0x1c00b3f6f  mov     r15, [rcx+18h]
0x1c00b3f73  xor     eax, eax
0x1c00b3f75  mov     [rbp+P], rax
0x1c00b3f79  mov     rbx, r8
0x1c00b3f7c  mov     [rbp+var_28], r15
0x1c00b3f80  mov     rdi, rcx
0x1c00b3f83  mov     [rbp+var_8], rax
0x1c00b3f87  mov     [rbp+arg_0], ax
0x1c00b3f8b  mov     [rbp+var_2C], eax
0x1c00b3f8e  mov     r13d, edx
0x1c00b3f91  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b3f9b  mov     rcx, [rbp+arg_28]
0x1c00b3f9f  mov     r14, [rbp+arg_20]
0x1c00b3fa3  jnz     loc_1C00E8808
0x1c00b3fa9  mov     rax, [rdi+140h]
0x1c00b3fb0  mov     esi, [r15+800h]
0x1c00b3fb7  mov     r12d, [rdi+1F4h]
0x1c00b3fbe  test    rax, rax
0x1c00b3fc1  jnz     loc_1C00E882F
0x1c00b3fc7  mov     eax, [r15+598h]
0x1c00b3fce  sub     eax, 2
0x1c00b3fd1  cmp     eax, 1
0x1c00b3fd4  jbe     loc_1C00E8852
0x1c00b3fda  mov     eax, [rdi+0BCh]
0x1c00b3fe0  lea     rcx, [r12+r12*2]
0x1c00b3fe4  movzx   r8d, [rbp+arg_0]
0x1c00b3fe9  mov     r9d, [rdi+98h]
0x1c00b3ff0  add     r9, r8
0x1c00b3ff3  mov     [rbp+var_10], r8
0x1c00b3ff7  lea     rdx, [rax+rcx*8]
0x1c00b3ffb  mov     eax, [rdi+0A8h]
0x1c00b4001  inc     rax
0x1c00b4004  add     r9, rdx
0x1c00b4007  add     r9, rax; int
0x1c00b400a  mov     eax, 0FFFFFFFFh
0x1c00b400f  cmp     r9, rax
0x1c00b4012  ja      loc_1C00E8891
0x1c00b4018  mov     edx, [rdi+4Ch]
0x1c00b401b  add     edx, r13d
0x1c00b401e  cmp     edx, r13d
0x1c00b4021  jb      loc_1C00E88A0
0x1c00b4027  mov     rcx, [r15+18h]
0x1c00b402b  lea     rax, [rbp+P]
0x1c00b402f  mov     qword ptr [rsp+80h+Priority], rax; __int64
0x1c00b4034  lea     r8d, [rsi+2]; int
0x1c00b4038  mov     [rsp+80h+BugCheckOnFailure], edx; Size
0x1c00b403c  mov     rdx, r14; int
0x1c00b403f  mov     rcx, [rcx+3C0h]; int
0x1c00b4046  call    UlAllocateCacheEntry
0x1c00b404b  mov     dword ptr [rbp+var_40], eax
0x1c00b404e  mov     r9d, eax
0x1c00b4051  test    eax, eax
0x1c00b4053  js      loc_1C00E8C99
0x1c00b4059  mov     r9, [rbp+var_28]
0x1c00b405d  lea     r15, [rdi+0C8h]
0x1c00b4064  mov     edx, [r9+7B0h]
0x1c00b406b  mov     r8d, [r9+598h]
0x1c00b4072  mov     dword ptr [rbp+var_40], edx
0x1c00b4075  mov     [rbp+var_30], r8d
0x1c00b4079  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00b4083  mov     rsi, [rbp+P]
0x1c00b4087  jnz     loc_1C00E88AF
0x1c00b408d  mov     r14, [rsi+8]
0x1c00b4091  xor     eax, eax
0x1c00b4093  mov     [rsi+28h], rax
0x1c00b4097  mov     [rsi+30h], rax
0x1c00b409b  mov     [rsi+78h], eax
0x1c00b409e  mov     [rsi+229h], al
0x1c00b40a4  mov     [rsi+40h], rax
0x1c00b40a8  mov     [rsi+50h], rax
0x1c00b40ac  mov     [rsi+60h], rax
0x1c00b40b0  lea     rax, [rsi+268h]
0x1c00b40b7  mov     [rax+8], rax
0x1c00b40bb  mov     [rax], rax
0x1c00b40be  mov     dword ptr [rsi+20h], 1
0x1c00b40c5  mov     word ptr [rsi+70h], 0
0x1c00b40cb  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00b40d5  jnz     loc_1C00E88E9
0x1c00b40db  mov     rcx, [rbp+var_28]
0x1c00b40df  lea     rax, [r14+28h]
0x1c00b40e3  mov     qword ptr [rsp+80h+Priority], rax
0x1c00b40e8  lea     r9, [r14+0E0h]
0x1c00b40ef  mov     eax, [r14+60h]
0x1c00b40f3  add     rcx, 7E0h
0x1c00b40fa  mov     [r14+68h], edx
0x1c00b40fe  xor     edx, edx
0x1c00b4100  mov     [rsp+80h+BugCheckOnFailure], eax
0x1c00b4104  mov     word ptr [r14+64h], 0
0x1c00b410b  call    UlpBuildUriKeyFromCookedUrl
0x1c00b4110  mov     dword ptr [rbp+var_40], eax
0x1c00b4113  mov     r9d, eax
0x1c00b4116  test    eax, eax
0x1c00b4118  js      short loc_1C00B4175
0x1c00b411a  test    r15, r15
0x1c00b411d  jz      short loc_1C00B4175
0x1c00b411f  movups  xmm0, xmmword ptr [r15]
0x1c00b4123  movups  xmmword ptr [r14+6Ch], xmm0
0x1c00b4128  movups  xmm1, xmmword ptr [r15+10h]
0x1c00b412d  movups  xmmword ptr [r14+7Ch], xmm1
0x1c00b4132  movups  xmm0, xmmword ptr [r15+20h]
0x1c00b4137  movups  xmmword ptr [r14+8Ch], xmm0
0x1c00b413f  movups  xmm1, xmmword ptr [r15+30h]
0x1c00b4144  movups  xmmword ptr [r14+9Ch], xmm1
0x1c00b414c  movups  xmm0, xmmword ptr [r15+40h]
0x1c00b4151  movups  xmmword ptr [r14+0ACh], xmm0
0x1c00b4159  movups  xmm1, xmmword ptr [r15+50h]
0x1c00b415e  movups  xmmword ptr [r14+0BCh], xmm1
0x1c00b4166  movsd   xmm0, qword ptr [r15+60h]
0x1c00b416c  movsd   qword ptr [r14+0CCh], xmm0
0x1c00b4175  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00b417f  jnz     loc_1C00E891F
0x1c00b4185  test    r9d, r9d
0x1c00b4188  js      loc_1C00E8C9D
0x1c00b418e  movzx   eax, byte ptr [rdi+31h]
0x1c00b4192  lea     r15, [rsi+2A0h]
0x1c00b4199  mov     [rsi+22Bh], al
0x1c00b419f  lea     r14, qword_1C005D868
0x1c00b41a6  mov     eax, [rdi+98h]
0x1c00b41ac  test    eax, eax
0x1c00b41ae  jz      loc_1C00E8964
0x1c00b41b4  mov     rdx, [rdi+0A0h]; Src
0x1c00b41bb  mov     r8d, eax; Size
0x1c00b41be  mov     rcx, r15; void *
0x1c00b41c1  call    memmove
0x1c00b41c6  mov     [rsi+0A0h], r15
0x1c00b41cd  mov     eax, [rdi+98h]
0x1c00b41d3  mov     [rsi+98h], eax
0x1c00b41d9  mov     eax, [rdi+98h]
0x1c00b41df  add     r15, rax
0x1c00b41e2  mov     eax, [rdi+0A8h]
0x1c00b41e8  test    eax, eax
0x1c00b41ea  jnz     loc_1C00E8970
0x1c00b41f0  mov     [rsi+0B0h], r14
0x1c00b41f7  mov     eax, [rdi+0B8h]
0x1c00b41fd  mov     [rsi+0B8h], eax
0x1c00b4203  mov     eax, [rdi+0BCh]
0x1c00b4209  test    eax, eax
0x1c00b420b  jnz     loc_1C00B47D9
0x1c00b4211  mov     [rsi+0C0h], r14
0x1c00b4218  mov     rax, [rdi+90h]
0x1c00b421f  mov     [rsi+90h], rax
0x1c00b4226  cmp     byte ptr [rdi+28h], 0
0x1c00b422a  jnz     loc_1C00E89A3
0x1c00b4230  cmp     byte ptr [rdi+2Bh], 0
0x1c00b4234  jnz     loc_1C00E89A3
0x1c00b423a  xor     al, al
0x1c00b423c  mov     [rsi+72h], al
0x1c00b423f  lea     rcx, [rsi+74h]
0x1c00b4243  movzx   eax, word ptr [rdi+3Ch]
0x1c00b4247  mov     [rcx], ax
0x1c00b424a  movzx   eax, [rbp+arg_18]
0x1c00b424e  mov     [rsi+7Ch], rbx
0x1c00b4252  mov     [rsi+22Ah], al
0x1c00b4258  mov     [rbp+var_40], rcx
0x1c00b425c  cmp     ebx, 2
0x1c00b425f  jz      loc_1C00E89AA
0x1c00b4265  mov     rbx, [rbp+var_28]
0x1c00b4269  lea     r14, [rsi+0C8h]
0x1c00b4270  add     rbx, 500h
0x1c00b4277  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00b427d  test    al, 8
0x1c00b427f  jnz     loc_1C00E89DE
0x1c00b4285  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00b428b  test    al, 8
0x1c00b428d  jnz     loc_1C00E89FB
0x1c00b4293  mov     rax, [rbx+18h]
0x1c00b4297  test    rax, rax
0x1c00b429a  jz      short loc_1C00B42A4
0x1c00b429c  lock inc dword ptr [rax+4]
0x1c00b42a0  mov     rsi, [rbp+P]
0x1c00b42a4  mov     rax, [rbx+20h]
0x1c00b42a8  test    rax, rax
0x1c00b42ab  jz      short loc_1C00B42B5
0x1c00b42ad  lock inc dword ptr [rax+4]
0x1c00b42b1  mov     rsi, [rbp+P]
0x1c00b42b5  mov     rax, [rbx+30h]
0x1c00b42b9  test    rax, rax
0x1c00b42bc  jz      short loc_1C00B42CC
0x1c00b42be  lock inc dword ptr [rax]
0x1c00b42c1  mov     rax, [rbx+30h]
0x1c00b42c5  lock inc dword ptr [rax]
0x1c00b42c8  mov     rsi, [rbp+P]
0x1c00b42cc  mov     rax, [rbx+40h]
0x1c00b42d0  test    rax, rax
0x1c00b42d3  jnz     loc_1C00E8A18
0x1c00b42d9  mov     rax, [rbx+48h]
0x1c00b42dd  test    rax, rax
0x1c00b42e0  jz      short loc_1C00B42EA
0x1c00b42e2  lock inc dword ptr [rax+4]
0x1c00b42e6  mov     rsi, [rbp+P]
0x1c00b42ea  mov     rax, [rbx+50h]
0x1c00b42ee  test    rax, rax
0x1c00b42f1  jz      short loc_1C00B42FB
0x1c00b42f3  lock inc dword ptr [rax+4]
0x1c00b42f7  mov     rsi, [rbp+P]
0x1c00b42fb  mov     rax, [rbx+60h]
0x1c00b42ff  test    rax, rax
0x1c00b4302  jnz     loc_1C00E8A25
0x1c00b4308  mov     rax, [rbx+78h]
0x1c00b430c  test    rax, rax
0x1c00b430f  jz      short loc_1C00B4319
0x1c00b4311  lock inc dword ptr [rax+4]
0x1c00b4315  mov     rsi, [rbp+P]
0x1c00b4319  mov     rax, [rbx+68h]
0x1c00b431d  test    rax, rax
0x1c00b4320  jz      short loc_1C00B432A
0x1c00b4322  lock inc dword ptr [rax+4]
0x1c00b4326  mov     rsi, [rbp+P]
0x1c00b432a  mov     rax, [rbx+58h]
0x1c00b432e  test    rax, rax
0x1c00b4331  jz      short loc_1C00B433B
0x1c00b4333  lock inc dword ptr [rax+4]
0x1c00b4337  mov     rsi, [rbp+P]
0x1c00b433b  mov     rax, r14
0x1c00b433e  mov     ecx, 2
0x1c00b4343  lea     rax, [rax+80h]
0x1c00b434a  movups  xmm0, xmmword ptr [rbx]
0x1c00b434d  lea     rbx, [rbx+80h]
0x1c00b4354  movups  xmmword ptr [rax-80h], xmm0
0x1c00b4358  movups  xmm1, xmmword ptr [rbx-70h]
0x1c00b435c  movups  xmmword ptr [rax-70h], xmm1
0x1c00b4360  movups  xmm0, xmmword ptr [rbx-60h]
0x1c00b4364  movups  xmmword ptr [rax-60h], xmm0
0x1c00b4368  movups  xmm1, xmmword ptr [rbx-50h]
0x1c00b436c  movups  xmmword ptr [rax-50h], xmm1
0x1c00b4370  movups  xmm0, xmmword ptr [rbx-40h]
0x1c00b4374  movups  xmmword ptr [rax-40h], xmm0
0x1c00b4378  movups  xmm1, xmmword ptr [rbx-30h]
0x1c00b437c  movups  xmmword ptr [rax-30h], xmm1
0x1c00b4380  movups  xmm0, xmmword ptr [rbx-20h]
0x1c00b4384  movups  xmmword ptr [rax-20h], xmm0
0x1c00b4388  movups  xmm1, xmmword ptr [rbx-10h]
0x1c00b438c  movups  xmmword ptr [rax-10h], xmm1
0x1c00b4390  sub     rcx, 1
0x1c00b4394  jnz     short loc_1C00B4343
0x1c00b4396  movups  xmm0, xmmword ptr [rbx]
0x1c00b4399  xor     edx, edx; Val
0x1c00b439b  lea     rcx, [r14+0A0h]; void *
0x1c00b43a2  movups  xmmword ptr [rax], xmm0
0x1c00b43a5  movups  xmm1, xmmword ptr [rbx+10h]
0x1c00b43a9  lea     r8d, [rdx+50h]; Size
0x1c00b43ad  movups  xmmword ptr [rax+10h], xmm1
0x1c00b43b1  movups  xmm0, xmmword ptr [rbx+20h]
0x1c00b43b5  movups  xmmword ptr [rax+20h], xmm0
0x1c00b43b9  mov     rax, [r14+30h]
0x1c00b43bd  mov     [r14+8], rax
0x1c00b43c1  call    memset
0x1c00b43c6  xor     eax, eax
0x1c00b43c8  and     dword ptr [r14+100h], 0FFFFFFFEh
0x1c00b43d0  mov     [r14+0F8h], rax
0x1c00b43d7  mov     [r14+104h], rax
0x1c00b43de  mov     [r14+110h], rax
0x1c00b43e5  mov     [r14+118h], ax
0x1c00b43ed  mov     [r14+120h], rax
0x1c00b43f4  mov     [r14+38h], rax
0x1c00b43f8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00b43fe  test    al, 8
0x1c00b4400  jnz     loc_1C00E8A32
0x1c00b4406  mov     eax, [rdi+4Ch]
0x1c00b4409  mov     [rsi+200h], eax
0x1c00b440f  mov     eax, [rdi+74h]
0x1c00b4412  mov     [rsi+218h], eax
0x1c00b4418  mov     eax, [rdi+78h]
0x1c00b441b  mov     [rsi+21Ch], eax
0x1c00b4421  mov     eax, [rdi+7Ch]
0x1c00b4424  mov     [rsi+220h], eax
0x1c00b442a  mov     eax, [rdi+80h]
0x1c00b4430  mov     [rsi+224h], eax
0x1c00b4436  movzx   eax, byte ptr [rdi+70h]
0x1c00b443a  mov     [rsi+228h], al
0x1c00b4440  mov     eax, [rdi+38h]
0x1c00b4443  test    al, 20h
0x1c00b4445  jnz     loc_1C00E8A49
0x1c00b444b  mov     r8d, [rdi+4Ch]
0x1c00b444f  mov     r9d, r13d
0x1c00b4452  mov     rdx, [rdi+58h]
0x1c00b4456  mov     rcx, [rsi+208h]
0x1c00b445d  call    UlLargeMemSetData
0x1c00b4462  movzx   ebx, al
0x1c00b4465  test    bl, bl
0x1c00b4467  jz      loc_1C00E8B2D
0x1c00b446d  mov     r14, [rbp+var_28]
0x1c00b4471  xor     ecx, ecx
0x1c00b4473  mov     [rsi+204h], r13d
0x1c00b447a  mov     dword ptr [rbp+var_40], ecx
0x1c00b447d  mov     rdx, [r14+9A0h]
0x1c00b4484  test    rdx, rdx
0x1c00b4487  jnz     loc_1C00E8B3C
0x1c00b448d  mov     rdx, [rbp+var_8]
  ... truncated ...
```
