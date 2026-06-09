# NtfsRestoreCachedRunsOnKsr

- ea: `0x1402956a8`
- end: `0x140296412`
- name: `NtfsRestoreCachedRunsOnKsr`
- size: `3434`
- prototype: `char __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401fda90`

## callees

- `0x140007ea0`
- `0x140008278`
- `0x140042e10`
- `0x140042edc`
- `0x140059250`
- `0x1400593c0`
- `0x14016a900`
- `0x1401cbe1c`
- `0x1402956a8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1402957ca`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1402957ca`
- `ntoskrnl!IoGetActivityIdThread` at `0x140295876`
- `ntoskrnl!IoGetActivityIdThread` at `0x140295876`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295e32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295e81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295ed2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402961d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402961fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296234`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdcc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295e32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295e81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295ed2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f24`
- `ntoskrnl!ExFreePoolWithTag` at `0x140295f79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402961d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402961fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296219`
- `ntoskrnl!ExFreePoolWithTag` at `0x140296234`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdcc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bdd26`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295984`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295aaf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295c9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295cda`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d16`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d48`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d7a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295984`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295aaf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295c9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295cda`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d16`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d48`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140295d7a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140295bda`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140295bda`
- `HAL!KeQueryPerformanceCounter` at `0x1402957e8`
- `HAL!KeQueryPerformanceCounter` at `0x140296291`
- `HAL!KeQueryPerformanceCounter` at `0x1402bdda7`
- `HAL!KeQueryPerformanceCounter` at `0x1402957e8`
- `HAL!KeQueryPerformanceCounter` at `0x140296291`
- `HAL!KeQueryPerformanceCounter` at `0x1402bdda7`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x140295852`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x14029626a`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402bdd6a`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x140295852`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x14029626a`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrEnumeratePersistedMemory` at `0x1402bdd6a`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x14029591e`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x140295a15`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x14029591e`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrClaimPersistedMemory` at `0x140295a15`

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
  LARGE_INTEGER v65; // r9
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
      NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x41002u);
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
          MicrosoftTelemetryAssertTriggeredMsgKM((__int64)"!\"Vcb's TotalClusters did not match with KSRData's TotalClusters\"");
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
                  NtfsInsertCachedRun((int)v76, a2, *(_QWORD *)&v56[16 * m + 16], *(_QWORD *)&v56[16 * m + 24], 0);
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
          MicrosoftTelemetryAssertTriggeredMsgKM((__int64)"!\"Vcb's TotalClusters did not match with KSRData's TotalClusters\"");
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
        NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x41026u);
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
        (const EVENT_DESCRIPTOR *)NTFS_ETW_KSR_RESTORE_SUCCEEDED,
        (const GUID *)v98,
        v65.QuadPart,
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
            (const EVENT_DESCRIPTOR *)NTFS_ETW_KSR_RESTORE_FAILED,
            (const GUID *)v98,
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
0x1402956a8  mov     r11, rsp
0x1402956ab  push    rbx
0x1402956ac  push    rsi
0x1402956ad  push    rdi
0x1402956ae  push    r12
0x1402956b0  push    r13
0x1402956b2  push    r14
0x1402956b4  push    r15
0x1402956b6  sub     rsp, 1D0h
0x1402956bd  mov     rax, cs:__security_cookie
0x1402956c4  xor     rax, rsp
0x1402956c7  mov     [rsp+208h+var_48], rax
0x1402956cf  mov     [rsp+208h+var_128], r8
0x1402956d7  mov     r13, rdx
0x1402956da  mov     rdx, rcx
0x1402956dd  mov     [rsp+208h+var_170], rcx
0x1402956e5  mov     [rsp+208h+var_118], r13
0x1402956ed  xor     ebx, ebx
0x1402956ef  mov     [r11-158h], rbx
0x1402956f6  mov     [rsp+208h+var_180], ebx
0x1402956fd  xorps   xmm0, xmm0
0x140295700  xor     ecx, ecx
0x140295702  movups  xmmword ptr [rsp+208h+var_F8], xmm0
0x14029570a  movups  [rsp+208h+var_E8], xmm0
0x140295712  mov     [r11-0D8h], rcx
0x140295719  xorps   xmm1, xmm1
0x14029571c  movups  xmmword ptr [rsp+208h+var_D0], xmm1
0x140295724  movups  [rsp+208h+var_C0], xmm1
0x14029572c  mov     [r11-0B0h], rcx
0x140295733  movups  [rsp+208h+var_A8], xmm0
0x14029573b  mov     [r11-98h], rcx
0x140295742  mov     r15d, 40FACh
0x140295748  mov     [r11-178h], r15
0x14029574f  mov     [r8], rbx
0x140295752  mov     rax, [r13+0F8h]
0x140295759  mov     rcx, [rax+10h]
0x14029575d  test    dword ptr [rcx+30h], 400000h
0x140295764  jz      loc_1402963EC
0x14029576a  mov     eax, cs:dword_140095BE8
0x140295770  test    al, 1
0x140295772  jz      loc_1402963EC
0x140295778  test    al, 6
0x14029577a  jnz     loc_1402963EC
0x140295780  mov     [rsp+208h+P], rbx
0x140295785  mov     r14d, ebx
0x140295788  mov     [r11-150h], rbx
0x14029578f  mov     edi, ebx
0x140295791  mov     [rsp+208h+var_1A4], ebx
0x140295795  mov     r12d, ebx
0x140295798  mov     [rsp+208h+var_184], ebx
0x14029579f  mov     [rsp+208h+var_1A8], bl
0x1402957a3  mov     [rsp+208h+var_168], ebx
0x1402957aa  mov     [rsp+208h+var_18C], bx
0x1402957af  mov     [rsp+208h+var_188], ebx
0x1402957b6  mov     rcx, [rdx+70h]
0x1402957ba  test    rcx, rcx
0x1402957bd  jz      loc_140295876
0x1402957c3  lea     rdx, [r11-0A0h]
0x1402957ca  call    cs:__imp_IoGetActivityIdIrp
0x1402957d1  nop     dword ptr [rax+rax+00h]
0x1402957d6  test    eax, eax
0x1402957d8  jns     loc_1402958A2
0x1402957de  mov     qword ptr [rsp+208h+var_A8], rbx
0x1402957e6  xor     ecx, ecx; PerformanceFrequency
0x1402957e8  call    cs:__imp_KeQueryPerformanceCounter
0x1402957ef  nop     dword ptr [rax+rax+00h]
0x1402957f4  mov     rbx, rax
0x1402957f7  mov     [rsp+208h+var_100], rax
0x1402957ff  mov     esi, 2
0x140295804  mov     eax, 0C0000001h
0x140295809  lea     rcx, NTFS_KSR_GUID_ARRAY
0x140295810  mov     [rsp+208h+var_164], esi
0x140295817  cmp     esi, 1
0x14029581a  jb      loc_1402958B7
0x140295820  dec     esi
0x140295822  mov     r14d, esi
0x140295825  shl     r14, 4
0x140295829  add     r14, rcx
0x14029582c  mov     [rsp+208h+var_108], r14
0x140295834  mov     [rsp+208h+var_158], 0
0x140295840  lea     r8, [rsp+208h+var_158]
0x140295848  lea     rdx, NtfsGetBlockIdForKSR
0x14029584f  mov     rcx, r14
0x140295852  call    cs:__imp_KsrEnumeratePersistedMemory
0x140295859  nop     dword ptr [rax+rax+00h]
0x14029585e  mov     [rsp+208h+var_17C], eax
0x140295865  test    eax, eax
0x140295867  js      short loc_140295874
0x140295869  cmp     [rsp+208h+var_158], 0
0x140295872  jnz     short loc_1402958B7
0x140295874  jmp     short loc_140295809
0x140295876  call    cs:__imp_IoGetActivityIdThread
0x14029587d  nop     dword ptr [rax+rax+00h]
0x140295882  test    rax, rax
0x140295885  jz      loc_1402957DE
0x14029588b  mov     rcx, [rax]
0x14029588e  mov     qword ptr [rsp+208h+var_A8+8], rcx
0x140295896  mov     rax, [rax+8]
0x14029589a  mov     [rsp+208h+var_98], rax
0x1402958a2  lea     rax, [rsp+208h+var_A8+8]
0x1402958aa  mov     qword ptr [rsp+208h+var_A8], rax
0x1402958b2  jmp     loc_1402957E6
0x1402958b7  test    eax, eax
0x1402958b9  js      loc_14029619B
0x1402958bf  cmp     [rsp+208h+var_158], 0
0x1402958c8  jz      loc_14029619B
0x1402958ce  cmp     qword ptr [r13+1FD0h], 0
0x1402958d6  jz      short loc_1402958F0
0x1402958d8  mov     edi, 6AA3h
0x1402958dd  mov     [rsp+208h+var_1A4], edi
0x1402958e1  mov     r15, 24E00040FEAh
0x1402958eb  jmp     loc_1402961B8
0x1402958f0  lea     rax, [rsp+208h+var_180]
0x1402958f8  mov     qword ptr [rsp+208h+Priority], rax
0x1402958fd  mov     [rsp+208h+BugCheckOnFailure], 0
0x140295905  mov     r9d, 8
0x14029590b  lea     r8, [rsp+208h+var_88]
0x140295913  mov     rdx, [rsp+208h+var_158]
0x14029591b  mov     rcx, r14
0x14029591e  call    cs:__imp_KsrClaimPersistedMemory
0x140295925  nop     dword ptr [rax+rax+00h]
0x14029592a  mov     [rsp+208h+var_17C], eax
0x140295931  mov     edx, 80000000h
0x140295936  lea     ecx, [rax+rdx]
0x140295939  test    edx, ecx
0x14029593b  jnz     short loc_140295958
0x14029593d  cmp     eax, 0C0000023h
0x140295942  jz      short loc_140295958
0x140295944  mov     edi, 6AA4h
0x140295949  mov     r15, 24F00040FF4h
0x140295953  jmp     loc_1402961AA
0x140295958  mov     r8d, [rsp+208h+var_180]
0x140295960  cmp     r8d, 8
0x140295964  jbe     loc_140295A5A
0x14029596a  mov     dword ptr [rsp+208h+var_1A0], 0
0x140295972  mov     edx, r8d
0x140295975  shl     rdx, 3; NumberOfBytes
0x140295979  mov     ecx, 200h; PoolType
0x14029597e  mov     r8d, 524B744Eh; Tag
0x140295984  call    cs:__imp_ExAllocatePoolWithTag
0x14029598b  nop     dword ptr [rax+rax+00h]
0x140295990  mov     rsi, rax
0x140295993  mov     [rsp+208h+P], rax
0x140295998  test    rax, rax
0x14029599b  jnz     short loc_1402959ED
0x14029599d  mov     al, cs:NtfsStatusDebugFlags
0x1402959a3  mov     r12d, 0C000009Ah
0x1402959a9  test    al, al
0x1402959ab  jz      short loc_1402959BD
0x1402959ad  mov     r8d, 41002h
0x1402959b3  mov     edx, r12d
0x1402959b6  xor     ecx, ecx
0x1402959b8  call    NtfsStatusTraceAndDebugInternal
0x1402959bd  mov     [rsp+208h+var_17C], r12d
0x1402959c5  mov     edi, 6AA5h
0x1402959ca  mov     [rsp+208h+var_1A4], edi
0x1402959ce  mov     [rsp+208h+var_184], r12d
0x1402959d6  mov     r15, 25000041005h
0x1402959e0  mov     [rsp+208h+var_178], r15
0x1402959e8  jmp     loc_1402961C5
0x1402959ed  lea     rax, [rsp+208h+var_1A0]
0x1402959f2  mov     qword ptr [rsp+208h+Priority], rax
0x1402959f7  mov     [rsp+208h+BugCheckOnFailure], 0
0x1402959ff  mov     r9d, [rsp+208h+var_180]
0x140295a07  mov     r8, rsi
0x140295a0a  mov     rdx, [rsp+208h+var_158]
0x140295a12  mov     rcx, r14
0x140295a15  call    cs:__imp_KsrClaimPersistedMemory
0x140295a1c  nop     dword ptr [rax+rax+00h]
0x140295a21  mov     [rsp+208h+var_17C], eax
0x140295a28  test    eax, eax
0x140295a2a  jns     short loc_140295A4B
0x140295a2c  mov     edi, 6AA4h
0x140295a31  mov     [rsp+208h+var_1A4], edi
0x140295a35  mov     r12d, eax
0x140295a38  mov     [rsp+208h+var_184], eax
0x140295a3f  mov     r15, 25100041010h
0x140295a49  jmp     short loc_1402959E0
0x140295a4b  mov     r8d, dword ptr [rsp+208h+var_1A0]
0x140295a50  mov     [rsp+208h+var_180], r8d
0x140295a58  jmp     short loc_140295A67
0x140295a5a  lea     rsi, [rsp+208h+var_88]
0x140295a62  mov     [rsp+208h+P], rsi
0x140295a67  xor     r9d, r9d
0x140295a6a  mov     [rsp+208h+var_148], r9d
0x140295a72  xor     edx, edx
0x140295a74  lea     r14d, [r9+1]
0x140295a78  mov     [rsp+208h+var_190], edx
0x140295a7c  cmp     edx, r8d
0x140295a7f  jnb     short loc_140295A99
0x140295a81  mov     rcx, [rsi+rdx*8]
0x140295a85  shr     rcx, 28h
0x140295a89  add     r9d, ecx
0x140295a8c  mov     [rsp+208h+var_148], r9d
0x140295a94  add     edx, r14d
0x140295a97  jmp     short loc_140295A78
0x140295a99  mov     esi, r9d
0x140295a9c  lea     rdx, ds:30h[r9*8]; NumberOfBytes
0x140295aa4  mov     ecx, 200h; PoolType
0x140295aa9  mov     r8d, 4D4B744Eh; Tag
0x140295aaf  call    cs:__imp_ExAllocatePoolWithTag
0x140295ab6  nop     dword ptr [rax+rax+00h]
0x140295abb  mov     rcx, rax
0x140295abe  mov     [rsp+208h+MemoryDescriptorList], rax
0x140295ac6  test    rax, rax
0x140295ac9  jnz     short loc_140295B11
0x140295acb  mov     al, cs:NtfsStatusDebugFlags
0x140295ad1  mov     r12d, 0C000009Ah
0x140295ad7  test    al, al
0x140295ad9  jz      short loc_140295AE9
0x140295adb  mov     r8d, 41026h
0x140295ae1  mov     edx, r12d
0x140295ae4  call    NtfsStatusTraceAndDebugInternal
0x140295ae9  mov     [rsp+208h+var_17C], r12d
0x140295af1  mov     edi, 6AA5h
0x140295af6  mov     [rsp+208h+var_1A4], edi
0x140295afa  mov     [rsp+208h+var_184], r12d
0x140295b02  mov     r15, 25200041029h
0x140295b0c  jmp     loc_1402961B8
0x140295b11  xorps   xmm0, xmm0
0x140295b14  movups  xmmword ptr [rax], xmm0
0x140295b17  movups  xmmword ptr [rax+10h], xmm0
0x140295b1b  movups  xmmword ptr [rax+20h], xmm0
0x140295b1f  shl     rsi, 0Ch
0x140295b23  lea     rax, [rsi+0FFFh]
0x140295b2a  shr     rax, 0Ch
0x140295b2e  add     ax, 6
0x140295b32  shl     ax, 3
0x140295b36  mov     [rcx+8], ax
0x140295b3a  mov     [rcx+28h], esi
0x140295b3d  mov     eax, 2002h
0x140295b42  mov     [rcx+0Ah], ax
0x140295b46  lea     r8, [rcx+30h]
0x140295b4a  mov     [rsp+208h+var_110], r8
0x140295b52  xor     edx, edx
0x140295b54  mov     [rsp+208h+var_190], edx
0x140295b58  mov     r11, [rsp+208h+P]
0x140295b5d  cmp     edx, [rsp+208h+var_180]
0x140295b64  jnb     short loc_140295BAE
0x140295b66  mov     r9, [r11+rdx*8]
0x140295b6a  mov     rax, 0FFFFFFFFFFh
0x140295b74  and     r9, rax
0x140295b77  xor     ecx, ecx
0x140295b79  mov     [rsp+208h+var_144], ecx
0x140295b80  mov     rax, [r11+rdx*8]
0x140295b84  shr     rax, 28h
0x140295b88  cmp     ecx, eax
0x140295b8a  jnb     short loc_140295BA5
0x140295b8c  mov     eax, ecx
0x140295b8e  add     rax, r9
0x140295b91  mov     [r8], rax
0x140295b94  add     r8, 8
0x140295b98  mov     [rsp+208h+var_110], r8
0x140295ba0  add     ecx, r14d
0x140295ba3  jmp     short loc_140295B79
0x140295ba5  add     edx, r14d
0x140295ba8  mov     [rsp+208h+var_190], edx
0x140295bac  jmp     short loc_140295B5D
0x140295bae  mov     rcx, [rsp+208h+MemoryDescriptorList]; MemoryDescriptorList
0x140295bb6  test    byte ptr [rcx+0Ah], 5
0x140295bba  jz      short loc_140295BC2
0x140295bbc  mov     rsi, [rcx+18h]
0x140295bc0  jmp     short loc_140295BE9
0x140295bc2  mov     [rsp+208h+Priority], 40000010h; Priority
0x140295bca  mov     [rsp+208h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140295bd2  xor     r9d, r9d; RequestedAddress
0x140295bd5  mov     r8d, r14d; CacheType
0x140295bd8  xor     edx, edx; AccessMode
0x140295bda  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140295be1  nop     dword ptr [rax+rax+00h]
0x140295be6  mov     rsi, rax
0x140295be9  test    rsi, rsi
0x140295bec  jnz     short loc_140295C06
0x140295bee  mov     edi, 6AA6h
0x140295bf3  mov     [rsp+208h+var_1A4], edi
0x140295bf7  mov     r15, 2530004104Ch
0x140295c01  jmp     loc_1402961B8
0x140295c06  mov     eax, [rsi]
0x140295c08  cmp     eax, 2
0x140295c0b  jnz     loc_14029605E
0x140295c11  mov     [rsp+208h+var_160], 0
0x140295c1d  mov     rax, [rsi+10h]
0x140295c21  cmp     [r13+128h], rax
0x140295c28  jz      short loc_140295C4E
0x140295c2a  lea     rcx, aVcbSTotalclust; "!\"Vcb's TotalClusters did not match wi"...
0x140295c31  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140295c36  mov     edi, 6AA8h
0x140295c3b  mov     [rsp+208h+var_1A4], edi
0x140295c3f  mov     r15, 2540004105Ah
0x140295c49  jmp     loc_1402961B8
0x140295c4e  lea     r14, [rsi+38h]
0x140295c52  mov     rcx, r14
0x140295c55  mov     [rsp+208h+var_160], rcx
0x140295c5d  mov     eax, [rcx]
0x140295c5f  cmp     eax, 1
0x140295c62  jnz     short loc_140295C6E
0x140295c64  lea     rax, [rsp+208h+var_F8]
0x140295c6c  jmp     short loc_140295C7F
0x140295c6e  cmp     eax, 2
0x140295c71  jnz     loc_1402961C0
  ... truncated ...
```
