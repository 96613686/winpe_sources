# NtfsRestoreCachedRunsOnKsr

- ea: `0x1402956f8`
- end: `0x140296462`
- name: `NtfsRestoreCachedRunsOnKsr`
- size: `3434`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401fdae0`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x140042e10`
- `0x140042edc`
- `0x1400592c0`
- `0x140059440`
- `0x14016a950`
- `0x1401cbe6c`
- `0x1402956f8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14029581a`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14029581a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402958c6`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402958c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295ed1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296229`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029624c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296269`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296284`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd15`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295e82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295ed1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f74`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295fc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296229`
- `ntoskrnl!ExFreePoolWithTag` at `0x14029624c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296269`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296284`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd15`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd39`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd76`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402959d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295aff`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295cef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d66`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d98`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295dca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402959d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295aff`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295cef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d66`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d98`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295dca`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140295c2a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140295c2a`
- `HAL!KeQueryPerformanceCounter` at `0x140295838`
- `HAL!KeQueryPerformanceCounter` at `0x1402962e1`
- `HAL!KeQueryPerformanceCounter` at `0x1402bddf7`
- `HAL!KeQueryPerformanceCounter` at `0x140295838`
- `HAL!KeQueryPerformanceCounter` at `0x1402962e1`
- `HAL!KeQueryPerformanceCounter` at `0x1402bddf7`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402958a2`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402962ba`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402bddba`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402958a2`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402962ba`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402bddba`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x14029596e`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x140295a65`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x14029596e`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x140295a65`

## pseudocode

```c
char __fastcall NtfsRestoreCachedRunsOnKsr(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // r15
  __int64 *v5; // r14
  ULONG v6; // edi
  char v7; // r12
  __int64 v8; // rcx
  LARGE_INTEGER PerformanceCounter; // rbx
  int v10; // esi
  int v11; // eax
  _QWORD *ActivityIdThread; // rax
  unsigned int v13; // r8d
  _BYTE *PoolWithTag; // rsi
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  char v18; // r14
  __int64 v19; // rsi
  struct _MDL *v20; // rax
  __int64 v21; // rsi
  struct _MDL *v22; // r8
  __int64 v23; // rdx
  _QWORD *v24; // r11
  __int64 v25; // r9
  unsigned int i; // ecx
  _QWORD *MappedSystemVa; // rsi
  char *v28; // r14
  char *v29; // rcx
  PVOID *v30; // rax
  PVOID v31; // rax
  PVOID v32; // rax
  PVOID v33; // rax
  PVOID v34; // rax
  PVOID v35; // rax
  __int64 v36; // rax
  PVOID *v37; // rax
  PVOID v38; // rcx
  PVOID v39; // rcx
  PVOID *v40; // r9
  PVOID v41; // rcx
  PVOID *v42; // r9
  PVOID v43; // rcx
  PVOID *v44; // r9
  PVOID v45; // rcx
  PVOID *v46; // r9
  PVOID *v47; // rdx
  PVOID v48; // rcx
  PVOID *v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rax
  __int64 v55; // rax
  char *v56; // rsi
  unsigned int k; // ecx
  unsigned int m; // r14d
  unsigned int v59; // eax
  __int64 n; // rsi
  PVOID v61; // rcx
  PVOID v62; // rcx
  int v63; // esi
  LARGE_INTEGER v64; // rax
  int v65; // r9d
  PVOID *v67; // [rsp+68h] [rbp-1A0h] BYREF
  PVOID P; // [rsp+70h] [rbp-198h]
  unsigned int v69; // [rsp+78h] [rbp-190h]
  __int16 v70; // [rsp+7Ch] [rbp-18Ch]
  int v71; // [rsp+80h] [rbp-188h]
  int v72; // [rsp+84h] [rbp-184h]
  unsigned int v73; // [rsp+88h] [rbp-180h] BYREF
  int v74; // [rsp+8Ch] [rbp-17Ch]
  __int64 v75; // [rsp+90h] [rbp-178h]
  PVOID *v76; // [rsp+98h] [rbp-170h]
  int v77; // [rsp+A0h] [rbp-168h]
  int v78; // [rsp+A4h] [rbp-164h]
  char *j; // [rsp+A8h] [rbp-160h]
  __int64 v80; // [rsp+B0h] [rbp-158h] BYREF
  PMDL MemoryDescriptorList; // [rsp+B8h] [rbp-150h]
  int v82; // [rsp+C0h] [rbp-148h]
  unsigned int v83; // [rsp+C4h] [rbp-144h]
  unsigned int v84; // [rsp+C8h] [rbp-140h]
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-138h] BYREF
  _QWORD *v86; // [rsp+E0h] [rbp-128h]
  char *v87; // [rsp+E8h] [rbp-120h]
  __int64 v88; // [rsp+F0h] [rbp-118h]
  struct _MDL *v89; // [rsp+F8h] [rbp-110h]
  __int64 *v90; // [rsp+100h] [rbp-108h]
  LARGE_INTEGER v91; // [rsp+108h] [rbp-100h]
  PVOID v92[2]; // [rsp+110h] [rbp-F8h] BYREF
  __int128 v93; // [rsp+120h] [rbp-E8h]
  __int64 v94; // [rsp+130h] [rbp-D8h]
  PVOID v95[2]; // [rsp+138h] [rbp-D0h] BYREF
  __int128 v96; // [rsp+148h] [rbp-C0h]
  __int64 v97; // [rsp+158h] [rbp-B0h]
  __int128 v98; // [rsp+160h] [rbp-A8h] BYREF
  __int64 v99; // [rsp+170h] [rbp-98h]
  _BYTE v100[48]; // [rsp+180h] [rbp-88h] BYREF

  v86 = a3;
  v76 = (PVOID *)a1;
  v88 = a2;
  v80 = 0;
  v73 = 0;
  *(_OWORD *)v92 = 0;
  v93 = 0;
  v94 = 0;
  *(_OWORD *)v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  LOBYTE(v4) = -84;
  v75 = 266156;
  *a3 = 0;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 248) + 16LL) + 48LL) & 0x400000) == 0
    || (dword_140095BE8 & 1) == 0
    || (dword_140095BE8 & 6) != 0 )
  {
    return 0;
  }
  P = 0;
  v5 = 0;
  MemoryDescriptorList = 0;
  v6 = 0;
  v7 = 0;
  v72 = 0;
  v77 = 0;
  v70 = 0;
  v71 = 0;
  v8 = *(_QWORD *)(a1 + 112);
  if ( !v8 )
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(0);
    if ( !ActivityIdThread )
      goto LABEL_6;
    *((_QWORD *)&v98 + 1) = *ActivityIdThread;
    v99 = ActivityIdThread[1];
LABEL_14:
    *(_QWORD *)&v98 = (char *)&v98 + 8;
    goto LABEL_7;
  }
  if ( (int)IoGetActivityIdIrp(v8, (char *)&v98 + 8) >= 0 )
    goto LABEL_14;
LABEL_6:
  *(_QWORD *)&v98 = 0;
LABEL_7:
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v91 = PerformanceCounter;
  v10 = 2;
  v11 = -1073741823;
  while ( 1 )
  {
    v78 = v10;
    if ( !v10 )
      break;
    v5 = &NTFS_KSR_GUID_ARRAY[2 * (unsigned int)--v10];
    v90 = v5;
    v80 = 0;
    v11 = KsrEnumeratePersistedMemory(v5, NtfsGetBlockIdForKSR, &v80);
    v74 = v11;
    if ( v11 >= 0 )
    {
      if ( v80 )
        break;
    }
  }
  if ( v11 < 0 || !v80 )
  {
    v6 = 27298;
    v4 = 0x24D00040FE3LL;
    goto LABEL_109;
  }
  if ( *(_QWORD *)(a2 + 8144) )
  {
    v6 = 27299;
    v4 = 0x24E00040FEALL;
    goto LABEL_110;
  }
  v11 = KsrClaimPersistedMemory(v5, v80, v100, 8, 0, &v73);
  v74 = v11;
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -1073741789 )
  {
    v6 = 27300;
    v4 = 0x24F00040FF4LL;
LABEL_109:
    v72 = v11;
    v7 = v11;
    goto LABEL_110;
  }
  v13 = v73;
  if ( v73 <= 8 )
  {
    PoolWithTag = v100;
    P = v100;
    goto LABEL_32;
  }
  LODWORD(v67) = 0;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 8LL * v73, 0x524B744Eu);
  P = PoolWithTag;
  if ( !PoolWithTag )
  {
    v7 = -102;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 266242);
    v74 = -1073741670;
    v6 = 27301;
    v72 = -1073741670;
    v4 = 0x25000041005LL;
    goto LABEL_27;
  }
  v15 = KsrClaimPersistedMemory(v5, v80, PoolWithTag, v73, 0, &v67);
  v74 = v15;
  if ( v15 >= 0 )
  {
    v13 = (unsigned int)v67;
    v73 = (unsigned int)v67;
LABEL_32:
    v16 = 0;
    v82 = 0;
    v17 = 0;
    v18 = 1;
    while ( 1 )
    {
      v69 = v17;
      if ( (unsigned int)v17 >= v13 )
        break;
      v16 = (unsigned int)(*(_QWORD *)&PoolWithTag[8 * v17] >> 40) + (unsigned int)v16;
      v82 = v16;
      v17 = (unsigned int)(v17 + 1);
    }
    v19 = (unsigned int)v16;
    v20 = (struct _MDL *)ExAllocatePoolWithTag((POOL_TYPE)512, 8 * v16 + 48, 0x4D4B744Eu);
    MemoryDescriptorList = v20;
    if ( v20 )
    {
      *(_OWORD *)&v20->Next = 0;
      *(_OWORD *)&v20->Process = 0;
      *(_OWORD *)&v20->StartVa = 0;
      v21 = v19 << 12;
      v20->Size = 8 * (((unsigned __int64)(v21 + 4095) >> 12) + 6);
      v20->ByteCount = v21;
      v20->MdlFlags = 8194;
      v22 = v20 + 1;
      v89 = v20 + 1;
      v23 = 0;
      v69 = 0;
      v24 = P;
      while ( (unsigned int)v23 < v73 )
      {
        v25 = v24[v23] & 0xFFFFFFFFFFLL;
        for ( i = 0; ; ++i )
        {
          v83 = i;
          if ( i >= (unsigned int)(v24[v23] >> 40) )
            break;
          v22->Next = (struct _MDL *)(v25 + i);
          v22 = (struct _MDL *)((char *)v22 + 8);
          v89 = v22;
        }
        v23 = (unsigned int)(v23 + 1);
        v69 = v23;
      }
      if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
        MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
      if ( MappedSystemVa )
      {
        if ( *(_DWORD *)MappedSystemVa == 2 )
        {
          j = 0;
          if ( *(_QWORD *)(a2 + 296) == MappedSystemVa[2] )
          {
            v28 = (char *)(MappedSystemVa + 7);
            v29 = (char *)(MappedSystemVa + 7);
            for ( j = (char *)(MappedSystemVa + 7); ; j += v36 )
            {
              if ( *(_DWORD *)v29 == 1 )
              {
                v30 = v92;
              }
              else
              {
                if ( *(_DWORD *)v29 != 2 )
                  goto LABEL_111;
                v30 = v95;
              }
              v67 = v30;
              v31 = ExAllocatePoolWithTag(
                      (POOL_TYPE)(PoolType | 0x10),
                      24LL * *((unsigned __int16 *)v29 + 4),
                      0x414C744Eu);
              *v67 = v31;
              if ( !v31 )
                break;
              v32 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 2LL * *((unsigned __int16 *)j + 4), 0x614C744Eu);
              v67[1] = v32;
              if ( !v32 )
                break;
              v33 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 2LL * *((unsigned __int16 *)j + 6), 0x4142744Eu);
              v67[2] = v33;
              if ( !v33 )
                break;
              v34 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x100u, 0x444C744Eu);
              v67[3] = v34;
              if ( !v34 )
                break;
              v35 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x100u, 0x644C744Eu);
              v67[4] = v35;
              if ( !v35 )
                break;
              v36 = *((unsigned int *)j + 1);
              if ( !(_DWORD)v36 )
              {
                for ( j = (char *)(MappedSystemVa + 7); ; j = v28 )
                {
                  if ( *(_DWORD *)v28 == 1 )
                  {
                    v37 = *(PVOID **)(a2 + 528);
                    v76 = v92;
                    v38 = v92[0];
                  }
                  else
                  {
                    if ( *(_DWORD *)v28 != 2 )
                      goto LABEL_111;
                    v37 = *(PVOID **)(a2 + 536);
                    v76 = v95;
                    v38 = v95[0];
                  }
                  v67 = v37;
                  memmove(v38, &v28[*((unsigned int *)v28 + 5)], 24LL * *((unsigned __int16 *)v28 + 4));
                  v39 = v67[12];
                  if ( v39 )
                    ExFreePoolWithTag(v39, 0);
                  v40 = v76;
                  v67[12] = *v76;
                  *v40 = 0;
                  memmove(v40[1], &v28[*((unsigned int *)v28 + 6)], 2LL * *((unsigned __int16 *)v28 + 4));
                  v41 = v67[13];
                  if ( v41 )
                    ExFreePoolWithTag(v41, 0);
                  v42 = v76;
                  v67[13] = v76[1];
                  v42[1] = 0;
                  memmove(v42[2], &v28[*((unsigned int *)v28 + 7)], 2LL * *((unsigned __int16 *)v28 + 6));
                  v43 = v67[14];
                  if ( v43 )
                    ExFreePoolWithTag(v43, 0);
                  v44 = v76;
                  v67[14] = v76[2];
                  v44[2] = 0;
                  memmove(v44[3], &v28[*((unsigned int *)v28 + 8)], 4LL * *((unsigned __int16 *)v28 + 7));
                  v45 = v67[15];
                  if ( v45 )
                    ExFreePoolWithTag(v45, 0);
                  v46 = v76;
                  v67[15] = v76[3];
                  v46[3] = 0;
                  memmove(v46[4], &v28[*((unsigned int *)v28 + 9)], 4LL * *((unsigned __int16 *)v28 + 8));
                  v47 = v67;
                  v48 = v67[16];
                  if ( v48 )
                  {
                    ExFreePoolWithTag(v48, 0);
                    v47 = v67;
                  }
                  v49 = v76;
                  v47[16] = v76[4];
                  v49[4] = 0;
                  *((_WORD *)v47 + 74) = *((_WORD *)v28 + 4);
                  LODWORD(v49) = *((unsigned __int16 *)v28 + 5);
                  *((_WORD *)v47 + 75) = (_WORD)v49;
                  *((_WORD *)v47 + 76) = *((_WORD *)v28 + 7);
                  *((_WORD *)v47 + 77) = *((_WORD *)v28 + 8);
                  *((_WORD *)v47 + 78) = *((_WORD *)v28 + 6);
                  v71 += (int)v49;
                  v50 = *((unsigned int *)v28 + 1);
                  if ( !(_DWORD)v50 )
                    break;
                  v28 += v50;
                }
                *v86 = MappedSystemVa[3];
                v51 = MappedSystemVa[6];
                if ( v51 )
                  *(_QWORD *)(a2 + 4960) = v51;
                v52 = MappedSystemVa[4];
                if ( v52 && MappedSystemVa[5] )
                {
                  *(_QWORD *)(a2 + 1488) = v52;
                  *(_QWORD *)(a2 + 1496) = MappedSystemVa[5];
                }
                v18 = 1;
                v53 = 2;
                goto LABEL_106;
              }
              v29 = &j[v36];
            }
            goto LABEL_111;
          }
          MicrosoftTelemetryAssertTriggeredMsgKM("!\"Vcb's TotalClusters did not match with KSRData's TotalClusters\"");
          v6 = 27304;
          v4 = 0x2540004105ALL;
        }
        else if ( *(_DWORD *)MappedSystemVa == 1 )
        {
          v87 = 0;
          if ( *(_QWORD *)(a2 + 296) == MappedSystemVa[1] )
          {
            *v86 = MappedSystemVa[2];
            v54 = MappedSystemVa[5];
            if ( v54 )
              *(_QWORD *)(a2 + 4960) = v54;
            v55 = MappedSystemVa[3];
            if ( v55 && MappedSystemVa[4] )
            {
              *(_QWORD *)(a2 + 1488) = v55;
              *(_QWORD *)(a2 + 1496) = MappedSystemVa[4];
            }
            v56 = (char *)(MappedSystemVa + 6);
            v87 = v56;
            for ( k = 0; ; ++k )
            {
              v69 = k;
              if ( k >= 2 )
                break;
              if ( (v56[6] & 1) != 0 )
              {
                for ( m = 0; ; ++m )
                {
                  v84 = m;
                  v59 = *((unsigned __int16 *)v56 + 2);
                  if ( m >= v59 )
                    break;
                  NtfsInsertCachedRun((_DWORD)v76, a2, *(_QWORD *)&v56[16 * m + 16], *(_QWORD *)&v56[16 * m + 24], 0);
                }
                v71 += v59;
                k = v69;
                v18 = 1;
              }
              if ( !*(_DWORD *)v56 )
                break;
              v56 += *((unsigned int *)v56 + 2);
              v87 = v56;
            }
            v53 = 1;
LABEL_106:
            v77 = v53;
            v70 = v53;
            PoolWithTag = P;
            goto LABEL_113;
          }
          MicrosoftTelemetryAssertTriggeredMsgKM("!\"Vcb's TotalClusters did not match with KSRData's TotalClusters\"");
          v6 = 27304;
          v4 = 0x2550004114CLL;
        }
        else
        {
          v6 = 27303;
          v4 = 0x25600041199LL;
        }
      }
      else
      {
        v6 = 27302;
        v4 = 0x2530004104CLL;
      }
    }
    else
    {
      v7 = -102;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 266278);
      v74 = -1073741670;
      v6 = 27301;
      v72 = -1073741670;
      v4 = 0x25200041029LL;
    }
LABEL_110:
    v75 = v4;
LABEL_111:
    PoolWithTag = P;
    goto LABEL_112;
  }
  v6 = 27300;
  v7 = v15;
  v72 = v15;
  v4 = 0x25100041010LL;
LABEL_27:
  v75 = v4;
LABEL_112:
  v18 = 0;
LABEL_113:
  if ( MemoryDescriptorList )
    ExFreePoolWithTag(MemoryDescriptorList, 0);
  if ( PoolWithTag && PoolWithTag != v100 )
    ExFreePoolWithTag(PoolWithTag, 0);
  for ( n = 0; n != 5; ++n )
  {
    v61 = v92[n];
    if ( v61 )
      ExFreePoolWithTag(v61, 0);
    v62 = v95[n];
    if ( v62 )
      ExFreePoolWithTag(v62, 0);
  }
  v63 = 2;
  do
    KsrEnumeratePersistedMemory(&NTFS_KSR_GUID_ARRAY[2 * (unsigned int)--v63], NtfsFreeBlockIdForKSR, 0);
  while ( v63 );
  if ( v18 )
  {
    dword_140095BE8 |= 2u;
    v64 = KeQueryPerformanceCounter(0);
    word_140095BF4 = v77;
    dword_140095BF8 = v71;
    qword_140095C00 = 1000 * (v64.QuadPart - PerformanceCounter.QuadPart) / NtfsPerformanceFrequency.QuadPart;
    if ( (Microsoft_Windows_NtfsEnableBits & 0x200) != 0 )
      McTemplateK0phzr1jhqq_EtwWriteTransfer(
        a2 + 7792,
        (unsigned int)NTFS_ETW_KSR_RESTORE_SUCCEEDED,
        v98,
        v65,
        *(_WORD *)(a2 + 7856) >> 1,
        *(_QWORD *)(a2 + 7864),
        a2 + 7792,
        word_140095BF4,
        dword_140095BF8,
        qword_140095C00);
  }
  else
  {
    dword_140095BE8 |= 4u;
    if ( (Microsoft_Windows_NtfsEnableBits & 0x400) != 0 )
    {
      if ( v6 )
      {
        DestinationString = 0;
        NtfsGetStrippedMessageText(v6, &DestinationString);
        if ( (Microsoft_Windows_NtfsEnableBits & 0x400) != 0 )
          McTemplateK0phzr1jhzr4dq_EtwWriteTransfer(
            *(_QWORD *)(a2 + 7864),
            (unsigned int)NTFS_ETW_KSR_RESTORE_FAILED,
            v98,
            DestinationString.Length >> 1,
            *(_WORD *)(a2 + 7856) >> 1,
            *(_QWORD *)(a2 + 7864),
            a2 + 7792,
            DestinationString.Length >> 1,
            (__int64)DestinationString.Buffer,
            v7,
            v4);
      }
    }
  }
  return v18;
}

```

## disassembly

```asm
0x1402956f8  mov     r11, rsp
0x1402956fb  push    rbx
0x1402956fc  push    rsi
0x1402956fd  push    rdi
0x1402956fe  push    r12
0x140295700  push    r13
0x140295702  push    r14
0x140295704  push    r15
0x140295706  sub     rsp, 1D0h
0x14029570d  mov     rax, cs:__security_cookie
0x140295714  xor     rax, rsp
0x140295717  mov     [rsp+208h+var_48], rax
0x14029571f  mov     [rsp+208h+var_128], r8
0x140295727  mov     r13, rdx
0x14029572a  mov     rdx, rcx
0x14029572d  mov     [rsp+208h+var_170], rcx
0x140295735  mov     [rsp+208h+var_118], r13
0x14029573d  xor     ebx, ebx
0x14029573f  mov     [r11-158h], rbx
0x140295746  mov     [rsp+208h+var_180], ebx
0x14029574d  xorps   xmm0, xmm0
0x140295750  xor     ecx, ecx
0x140295752  movups  xmmword ptr [rsp+208h+var_F8], xmm0
0x14029575a  movups  [rsp+208h+var_E8], xmm0
0x140295762  mov     [r11-0D8h], rcx
0x140295769  xorps   xmm1, xmm1
0x14029576c  movups  xmmword ptr [rsp+208h+var_D0], xmm1
0x140295774  movups  [rsp+208h+var_C0], xmm1
0x14029577c  mov     [r11-0B0h], rcx
0x140295783  movups  [rsp+208h+var_A8], xmm0
0x14029578b  mov     [r11-98h], rcx
0x140295792  mov     r15d, 40FACh
0x140295798  mov     [r11-178h], r15
0x14029579f  mov     [r8], rbx
0x1402957a2  mov     rax, [r13+0F8h]
0x1402957a9  mov     rcx, [rax+10h]
0x1402957ad  test    dword ptr [rcx+30h], 400000h
0x1402957b4  jz      loc_14029643C
0x1402957ba  mov     eax, cs:dword_140095BE8
0x1402957c0  test    al, 1
0x1402957c2  jz      loc_14029643C
0x1402957c8  test    al, 6
0x1402957ca  jnz     loc_14029643C
0x1402957d0  mov     [rsp+208h+P], rbx
0x1402957d5  mov     r14d, ebx
0x1402957d8  mov     [r11-150h], rbx
0x1402957df  mov     edi, ebx
0x1402957e1  mov     [rsp+208h+var_1A4], ebx
0x1402957e5  mov     r12d, ebx
0x1402957e8  mov     [rsp+208h+var_184], ebx
0x1402957ef  mov     [rsp+208h+var_1A8], bl
0x1402957f3  mov     [rsp+208h+var_168], ebx
0x1402957fa  mov     [rsp+208h+var_18C], bx
0x1402957ff  mov     [rsp+208h+var_188], ebx
0x140295806  mov     rcx, [rdx+70h]
0x14029580a  test    rcx, rcx
0x14029580d  jz      loc_1402958C6
0x140295813  lea     rdx, [r11-0A0h]
0x14029581a  call    cs:__imp_IoGetActivityIdIrp
0x140295821  nop     dword ptr [rax+rax+00h]
0x140295826  test    eax, eax
0x140295828  jns     loc_1402958F2
0x14029582e  mov     qword ptr [rsp+208h+var_A8], rbx
0x140295836  xor     ecx, ecx; PerformanceFrequency
0x140295838  call    cs:__imp_KeQueryPerformanceCounter
0x14029583f  nop     dword ptr [rax+rax+00h]
0x140295844  mov     rbx, rax
0x140295847  mov     [rsp+208h+var_100], rax
0x14029584f  mov     esi, 2
0x140295854  mov     eax, 0C0000001h
0x140295859  lea     rcx, NTFS_KSR_GUID_ARRAY
0x140295860  mov     [rsp+208h+var_164], esi
0x140295867  cmp     esi, 1
0x14029586a  jb      loc_140295907
0x140295870  dec     esi
0x140295872  mov     r14d, esi
0x140295875  shl     r14, 4
0x140295879  add     r14, rcx
0x14029587c  mov     [rsp+208h+var_108], r14
0x140295884  mov     [rsp+208h+var_158], 0
0x140295890  lea     r8, [rsp+208h+var_158]
0x140295898  lea     rdx, NtfsGetBlockIdForKSR
0x14029589f  mov     rcx, r14
0x1402958a2  call    cs:__imp_KsrEnumeratePersistedMemory
0x1402958a9  nop     dword ptr [rax+rax+00h]
0x1402958ae  mov     [rsp+208h+var_17C], eax
0x1402958b5  test    eax, eax
0x1402958b7  js      short loc_1402958C4
0x1402958b9  cmp     [rsp+208h+var_158], 0
0x1402958c2  jnz     short loc_140295907
0x1402958c4  jmp     short loc_140295859
0x1402958c6  call    cs:__imp_IoGetActivityIdThread
0x1402958cd  nop     dword ptr [rax+rax+00h]
0x1402958d2  test    rax, rax
0x1402958d5  jz      loc_14029582E
0x1402958db  mov     rcx, [rax]
0x1402958de  mov     qword ptr [rsp+208h+var_A8+8], rcx
0x1402958e6  mov     rax, [rax+8]
0x1402958ea  mov     [rsp+208h+var_98], rax
0x1402958f2  lea     rax, [rsp+208h+var_A8+8]
0x1402958fa  mov     qword ptr [rsp+208h+var_A8], rax
0x140295902  jmp     loc_140295836
0x140295907  test    eax, eax
0x140295909  js      loc_1402961EB
0x14029590f  cmp     [rsp+208h+var_158], 0
0x140295918  jz      loc_1402961EB
0x14029591e  cmp     qword ptr [r13+1FD0h], 0
0x140295926  jz      short loc_140295940
0x140295928  mov     edi, 6AA3h
0x14029592d  mov     [rsp+208h+var_1A4], edi
0x140295931  mov     r15, 24E00040FEAh
0x14029593b  jmp     loc_140296208
0x140295940  lea     rax, [rsp+208h+var_180]
0x140295948  mov     qword ptr [rsp+208h+Priority], rax
0x14029594d  mov     [rsp+208h+BugCheckOnFailure], 0
0x140295955  mov     r9d, 8
0x14029595b  lea     r8, [rsp+208h+var_88]
0x140295963  mov     rdx, [rsp+208h+var_158]
0x14029596b  mov     rcx, r14
0x14029596e  call    cs:__imp_KsrClaimPersistedMemory
0x140295975  nop     dword ptr [rax+rax+00h]
0x14029597a  mov     [rsp+208h+var_17C], eax
0x140295981  mov     edx, 80000000h
0x140295986  lea     ecx, [rax+rdx]
0x140295989  test    edx, ecx
0x14029598b  jnz     short loc_1402959A8
0x14029598d  cmp     eax, 0C0000023h
0x140295992  jz      short loc_1402959A8
0x140295994  mov     edi, 6AA4h
0x140295999  mov     r15, 24F00040FF4h
0x1402959a3  jmp     loc_1402961FA
0x1402959a8  mov     r8d, [rsp+208h+var_180]
0x1402959b0  cmp     r8d, 8
0x1402959b4  jbe     loc_140295AAA
0x1402959ba  mov     dword ptr [rsp+208h+var_1A0], 0
0x1402959c2  mov     edx, r8d
0x1402959c5  shl     rdx, 3; NumberOfBytes
0x1402959c9  mov     ecx, 200h; PoolType
0x1402959ce  mov     r8d, 524B744Eh; Tag
0x1402959d4  call    cs:__imp_ExAllocatePoolWithTag
0x1402959db  nop     dword ptr [rax+rax+00h]
0x1402959e0  mov     rsi, rax
0x1402959e3  mov     [rsp+208h+P], rax
0x1402959e8  test    rax, rax
0x1402959eb  jnz     short loc_140295A3D
0x1402959ed  mov     al, cs:NtfsStatusDebugFlags
0x1402959f3  mov     r12d, 0C000009Ah
0x1402959f9  test    al, al
0x1402959fb  jz      short loc_140295A0D
0x1402959fd  mov     r8d, 41002h
0x140295a03  mov     edx, r12d
0x140295a06  xor     ecx, ecx
0x140295a08  call    NtfsStatusTraceAndDebugInternal
0x140295a0d  mov     [rsp+208h+var_17C], r12d
0x140295a15  mov     edi, 6AA5h
0x140295a1a  mov     [rsp+208h+var_1A4], edi
0x140295a1e  mov     [rsp+208h+var_184], r12d
0x140295a26  mov     r15, 25000041005h
0x140295a30  mov     [rsp+208h+var_178], r15
0x140295a38  jmp     loc_140296215
0x140295a3d  lea     rax, [rsp+208h+var_1A0]
0x140295a42  mov     qword ptr [rsp+208h+Priority], rax
0x140295a47  mov     [rsp+208h+BugCheckOnFailure], 0
0x140295a4f  mov     r9d, [rsp+208h+var_180]
0x140295a57  mov     r8, rsi
0x140295a5a  mov     rdx, [rsp+208h+var_158]
0x140295a62  mov     rcx, r14
0x140295a65  call    cs:__imp_KsrClaimPersistedMemory
0x140295a6c  nop     dword ptr [rax+rax+00h]
0x140295a71  mov     [rsp+208h+var_17C], eax
0x140295a78  test    eax, eax
0x140295a7a  jns     short loc_140295A9B
0x140295a7c  mov     edi, 6AA4h
0x140295a81  mov     [rsp+208h+var_1A4], edi
0x140295a85  mov     r12d, eax
0x140295a88  mov     [rsp+208h+var_184], eax
0x140295a8f  mov     r15, 25100041010h
0x140295a99  jmp     short loc_140295A30
0x140295a9b  mov     r8d, dword ptr [rsp+208h+var_1A0]
0x140295aa0  mov     [rsp+208h+var_180], r8d
0x140295aa8  jmp     short loc_140295AB7
0x140295aaa  lea     rsi, [rsp+208h+var_88]
0x140295ab2  mov     [rsp+208h+P], rsi
0x140295ab7  xor     r9d, r9d
0x140295aba  mov     [rsp+208h+var_148], r9d
0x140295ac2  xor     edx, edx
0x140295ac4  lea     r14d, [r9+1]
0x140295ac8  mov     [rsp+208h+var_190], edx
0x140295acc  cmp     edx, r8d
0x140295acf  jnb     short loc_140295AE9
0x140295ad1  mov     rcx, [rsi+rdx*8]
0x140295ad5  shr     rcx, 28h
0x140295ad9  add     r9d, ecx
0x140295adc  mov     [rsp+208h+var_148], r9d
0x140295ae4  add     edx, r14d
0x140295ae7  jmp     short loc_140295AC8
0x140295ae9  mov     esi, r9d
0x140295aec  lea     rdx, ds:30h[r9*8]; NumberOfBytes
0x140295af4  mov     ecx, 200h; PoolType
0x140295af9  mov     r8d, 4D4B744Eh; Tag
0x140295aff  call    cs:__imp_ExAllocatePoolWithTag
0x140295b06  nop     dword ptr [rax+rax+00h]
0x140295b0b  mov     rcx, rax
0x140295b0e  mov     [rsp+208h+MemoryDescriptorList], rax
0x140295b16  test    rax, rax
0x140295b19  jnz     short loc_140295B61
0x140295b1b  mov     al, cs:NtfsStatusDebugFlags
0x140295b21  mov     r12d, 0C000009Ah
0x140295b27  test    al, al
0x140295b29  jz      short loc_140295B39
0x140295b2b  mov     r8d, 41026h
0x140295b31  mov     edx, r12d
0x140295b34  call    NtfsStatusTraceAndDebugInternal
0x140295b39  mov     [rsp+208h+var_17C], r12d
0x140295b41  mov     edi, 6AA5h
0x140295b46  mov     [rsp+208h+var_1A4], edi
0x140295b4a  mov     [rsp+208h+var_184], r12d
0x140295b52  mov     r15, 25200041029h
0x140295b5c  jmp     loc_140296208
0x140295b61  xorps   xmm0, xmm0
0x140295b64  movups  xmmword ptr [rax], xmm0
0x140295b67  movups  xmmword ptr [rax+10h], xmm0
0x140295b6b  movups  xmmword ptr [rax+20h], xmm0
0x140295b6f  shl     rsi, 0Ch
0x140295b73  lea     rax, [rsi+0FFFh]
0x140295b7a  shr     rax, 0Ch
0x140295b7e  add     ax, 6
0x140295b82  shl     ax, 3
0x140295b86  mov     [rcx+8], ax
0x140295b8a  mov     [rcx+28h], esi
0x140295b8d  mov     eax, 2002h
0x140295b92  mov     [rcx+0Ah], ax
0x140295b96  lea     r8, [rcx+30h]
0x140295b9a  mov     [rsp+208h+var_110], r8
0x140295ba2  xor     edx, edx
0x140295ba4  mov     [rsp+208h+var_190], edx
0x140295ba8  mov     r11, [rsp+208h+P]
0x140295bad  cmp     edx, [rsp+208h+var_180]
0x140295bb4  jnb     short loc_140295BFE
0x140295bb6  mov     r9, [r11+rdx*8]
0x140295bba  mov     rax, 0FFFFFFFFFFh
0x140295bc4  and     r9, rax
0x140295bc7  xor     ecx, ecx
0x140295bc9  mov     [rsp+208h+var_144], ecx
0x140295bd0  mov     rax, [r11+rdx*8]
0x140295bd4  shr     rax, 28h
0x140295bd8  cmp     ecx, eax
0x140295bda  jnb     short loc_140295BF5
0x140295bdc  mov     eax, ecx
0x140295bde  add     rax, r9
0x140295be1  mov     [r8], rax
0x140295be4  add     r8, 8
0x140295be8  mov     [rsp+208h+var_110], r8
0x140295bf0  add     ecx, r14d
0x140295bf3  jmp     short loc_140295BC9
0x140295bf5  add     edx, r14d
0x140295bf8  mov     [rsp+208h+var_190], edx
0x140295bfc  jmp     short loc_140295BAD
0x140295bfe  mov     rcx, [rsp+208h+MemoryDescriptorList]; MemoryDescriptorList
0x140295c06  test    byte ptr [rcx+0Ah], 5
0x140295c0a  jz      short loc_140295C12
0x140295c0c  mov     rsi, [rcx+18h]
0x140295c10  jmp     short loc_140295C39
0x140295c12  mov     [rsp+208h+Priority], 40000010h; Priority
0x140295c1a  mov     [rsp+208h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140295c22  xor     r9d, r9d; RequestedAddress
0x140295c25  mov     r8d, r14d; CacheType
0x140295c28  xor     edx, edx; AccessMode
0x140295c2a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140295c31  nop     dword ptr [rax+rax+00h]
0x140295c36  mov     rsi, rax
0x140295c39  test    rsi, rsi
0x140295c3c  jnz     short loc_140295C56
0x140295c3e  mov     edi, 6AA6h
0x140295c43  mov     [rsp+208h+var_1A4], edi
0x140295c47  mov     r15, 2530004104Ch
0x140295c51  jmp     loc_140296208
0x140295c56  mov     eax, [rsi]
0x140295c58  cmp     eax, 2
0x140295c5b  jnz     loc_1402960AE
0x140295c61  mov     [rsp+208h+var_160], 0
0x140295c6d  mov     rax, [rsi+10h]
0x140295c71  cmp     [r13+128h], rax
0x140295c78  jz      short loc_140295C9E
0x140295c7a  lea     rcx, aVcbSTotalclust; "!\"Vcb's TotalClusters did not match wi"...
0x140295c81  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140295c86  mov     edi, 6AA8h
0x140295c8b  mov     [rsp+208h+var_1A4], edi
0x140295c8f  mov     r15, 2540004105Ah
0x140295c99  jmp     loc_140296208
0x140295c9e  lea     r14, [rsi+38h]
0x140295ca2  mov     rcx, r14
0x140295ca5  mov     [rsp+208h+var_160], rcx
0x140295cad  mov     eax, [rcx]
0x140295caf  cmp     eax, 1
0x140295cb2  jnz     short loc_140295CBE
0x140295cb4  lea     rax, [rsp+208h+var_F8]
0x140295cbc  jmp     short loc_140295CCF
0x140295cbe  cmp     eax, 2
0x140295cc1  jnz     loc_140296210
  ... truncated ...
```
