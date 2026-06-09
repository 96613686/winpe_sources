# RtlpCreateHeap

- ea: `0x18006a124`
- end: `0x18006b400`
- name: `RtlpCreateHeap`
- size: `4828`
- prototype: ``
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800408d4`
- `0x180065558`
- `0x180069180`
- `0x180069d84`
- `0x18006a0f0`
- `0x18006b490`
- `0x180108240`
- `0x18010f94c`

## callees

- `0x18000416c`
- `0x180007060`
- `0x180007cb0`
- `0x180017e90`
- `0x1800183a0`
- `0x18001b984`
- `0x1800526f0`
- `0x18006a124`
- `0x18006b720`
- `0x18006b7e4`
- `0x180079610`
- `0x18007a17c`
- `0x18007a840`
- `0x18007ae00`
- `0x1800e68cc`
- `0x1800e7c84`
- `0x1800fac08`
- `0x1800fad30`
- `0x1800feaa8`
- `0x1800febd8`
- `0x180100fa8`
- `0x1801032d0`
- `0x18010db8c`
- `0x18010f7f4`
- `0x18010f94c`
- `0x18011e730`
- `0x18015e5d0`
- `0x18015e730`
- `0x18015e990`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x18006b0d0`: `!(CheckedFlags & ~HEAP_CREATE_VALID_MASK)`

## pseudocode

```c
__int64 __fastcall RtlpCreateHeap(
        int a1,
        void *a2,
        unsigned __int64 a3,
        char *a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r12d
  void *v8; // r14
  __int64 v10; // rsi
  unsigned int v11; // r13d
  char v12; // bl
  unsigned int v13; // r15d
  _DWORD *v14; // r14
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  unsigned int v19; // esi
  struct _PEB *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int64 v23; // r9
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // rcx
  int v26; // r15d
  __int64 v27; // rdx
  unsigned __int64 v28; // rax
  signed __int64 v29; // rcx
  unsigned __int64 v30; // rtt
  __int64 v31; // rcx
  char *v32; // r14
  char *v33; // rbx
  char *v34; // rcx
  __int64 v35; // r15
  char *v36; // rbx
  int v37; // eax
  char *v38; // r9
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  _QWORD *v42; // rax
  char v43; // al
  char *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rbx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rbx
  __int64 v60; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 v66; // rcx
  int v67; // r10d
  char v68; // r8
  __int64 v69; // r9
  char *v70; // rsi
  char *v71; // rbx
  unsigned int v72; // eax
  __int64 v73; // rax
  unsigned __int64 v74; // rax
  __int64 v75; // rcx
  int v76; // eax
  unsigned __int64 v77; // rbx
  unsigned __int16 HeapInterceptorIndex; // ax
  __int64 v79; // r9
  char *v80; // [rsp+40h] [rbp-218h] BYREF
  __int64 v81; // [rsp+48h] [rbp-210h]
  void *v82; // [rsp+50h] [rbp-208h]
  __int64 v83; // [rsp+58h] [rbp-200h]
  unsigned __int64 v84; // [rsp+60h] [rbp-1F8h] BYREF
  unsigned int NtGlobalFlag; // [rsp+68h] [rbp-1F0h]
  unsigned __int64 v86; // [rsp+70h] [rbp-1E8h] BYREF
  unsigned __int64 v87; // [rsp+78h] [rbp-1E0h] BYREF
  char *v88; // [rsp+80h] [rbp-1D8h] BYREF
  char *v89; // [rsp+88h] [rbp-1D0h] BYREF
  __int64 v90; // [rsp+90h] [rbp-1C8h]
  unsigned int v91; // [rsp+98h] [rbp-1C0h]
  unsigned __int64 v92; // [rsp+A0h] [rbp-1B8h] BYREF
  _QWORD v93[2]; // [rsp+B0h] [rbp-1A8h] BYREF
  void *v94[2]; // [rsp+C0h] [rbp-198h] BYREF
  __int128 v95; // [rsp+D0h] [rbp-188h]
  __int128 v96; // [rsp+E0h] [rbp-178h]
  __int128 v97; // [rsp+F0h] [rbp-168h] BYREF
  __int128 v98; // [rsp+100h] [rbp-158h]
  __int128 v99; // [rsp+110h] [rbp-148h]
  __int128 v100; // [rsp+120h] [rbp-138h] BYREF
  __int128 v101; // [rsp+130h] [rbp-128h]
  __int128 v102; // [rsp+140h] [rbp-118h]
  __int128 v103; // [rsp+150h] [rbp-108h]
  __int128 v104; // [rsp+160h] [rbp-F8h]
  __int128 v105; // [rsp+170h] [rbp-E8h]
  _BYTE v106[80]; // [rsp+180h] [rbp-D8h] BYREF
  _BYTE SystemInformation[40]; // [rsp+1D0h] [rbp-88h] BYREF
  __int64 v108; // [rsp+1F8h] [rbp-60h]

  v7 = (int)a4;
  v89 = a4;
  v87 = a3;
  v8 = a2;
  v82 = a2;
  v81 = a5;
  v92 = (unsigned __int64)a2;
  v90 = a5;
  v10 = a6;
  v91 = a7;
  v88 = 0;
  NtGlobalFlag = NtCurrentPeb()->NtGlobalFlag;
  *(_OWORD *)v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  DWORD1(v100) = 0;
  memset_thunk_772440563353939046(&v100, 0, 0x5Cu);
  v86 = 0;
  v84 = 0;
  memset_thunk_772440563353939046(SystemInformation, 0, 0x40u);
  memset_thunk_772440563353939046(v106, 0, 0x50u);
  v11 = a7 != 0;
  v80 = 0;
  v83 = 0;
  if ( (a1 & 0x400) != 0 )
    goto LABEL_92;
  v12 = 0;
  if ( dword_1801C4588 && !v8 && !v81 )
  {
    v59 = RtlpDebugPageHeapCreate(a1, 0, v87, v7, 0, a6);
    if ( v59 )
      goto LABEL_93;
    if ( a6 != -1 )
    {
LABEL_92:
      v59 = 0;
LABEL_93:
      v27 = v81;
LABEL_94:
      v60 = 0;
      goto LABEL_95;
    }
    v10 = 0;
    v12 = 1;
  }
  v13 = a1 & 0xF1FFFFFF;
  if ( (v13 & 0x100) != 0 )
  {
    if ( (v13 & 2) == 0 || v8 || v81 )
      goto LABEL_92;
    if ( v10 == -1 && (_DWORD)xmmword_1801C4598 )
    {
      v10 = 0;
      v12 = 1;
    }
    if ( v10 )
    {
      if ( !(unsigned int)RtlpHpParametersVerify(v10) )
        goto LABEL_92;
      v14 = (_DWORD *)v10;
    }
    else
    {
      v14 = v106;
    }
  }
  else
  {
    v14 = 0;
    if ( (RtlpHpHeapFeatures & 1) != 0 && (v13 & 2) != 0 && !v82 )
    {
      if ( !v10 )
        goto LABEL_152;
      if ( *(_QWORD *)(v10 + 8) || *(_QWORD *)(v10 + 16) || *(_QWORD *)(v10 + 48) || (v76 = 1, *(_QWORD *)(v10 + 72)) )
        v76 = 0;
      if ( v76 )
      {
LABEL_152:
        v14 = v106;
        if ( v81 )
          v14 = 0;
      }
    }
  }
  if ( v14 )
  {
    if ( v14 == (_DWORD *)v106 )
    {
      memset_thunk_772440563353939046(v14, 0, 0x50u);
      *v14 = 5242883;
      v14[3] = 1;
      v14[4] = -1;
      if ( v12 )
        v14[1] = 2;
    }
    if ( (v14[1] & 1) == 0 )
    {
      _BitScanReverse((unsigned int *)&v67, v14[3]);
      if ( v14[4] == -1 )
        v68 = BYTE2(RtlpHpEnvHandle);
      else
        v68 = *((_BYTE *)v14 + 16) + 1;
      v69 = *((_QWORD *)v14 + 3);
      v70 = v89;
      v71 = v89;
      if ( v87 )
        v71 = (char *)v87;
      if ( v89 > v71 )
        v70 = v71;
      LOBYTE(v93[0]) = RtlpHpEnvHandle;
      BYTE1(v93[0]) = v67;
      BYTE2(v93[0]) = v68;
      *(_DWORD *)((char *)v93 + 3) = *(_DWORD *)((char *)&RtlpHpEnvHandle + 3);
      HIBYTE(v93[0]) = BYTE7(RtlpHpEnvHandle);
      v93[1] = v69;
      v72 = RtlpHpConvertCreationFlags(v13, NtGlobalFlag, v14);
      v73 = RtlpHpHeapCreate(v72, v71, v70, v93);
      v59 = v73;
      if ( v73 )
      {
        if ( (v13 & 1) != 0 )
          v11 |= 2u;
        if ( (int)RtlpProcessHeapsInsert(v73, v11) < 0 )
        {
          RtlpHpHeapDestroy(v59);
          v59 = 0;
        }
        if ( *(_DWORD *)(v59 + 16) == -571548178 )
        {
          RtlAcquireSRWLockExclusive(&RtlpHpStackTrackingContext);
          if ( (dword_1801C68C8 & 1) != 0 && (dword_1801C68C8 & 2) != 0 )
            _InterlockedOr((volatile signed __int32 *)(v59 + 20), 0x40u);
          RtlReleaseSRWLockExclusive(&RtlpHpStackTrackingContext);
        }
        RtlpHpHeapLoggingStateSync(v59);
      }
      v8 = v82;
      goto LABEL_93;
    }
    v8 = v82;
    if ( (_DWORD)xmmword_1801C4598 )
    {
      v59 = RtlpDebugPageHeapCreate(v13, (int)v82, v87, (int)v89, 0, 0);
      goto LABEL_93;
    }
    goto LABEL_92;
  }
  if ( (v13 & 0x10000000) == 0 )
  {
    if ( RtlpHeapErrorHandlerThreshold >= 2 )
    {
      if ( (v13 & 0xFFF80800) == 0 )
        goto LABEL_10;
      if ( NtCurrentPeb()->Ldr )
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
      else
        DbgPrint("HEAP: ");
      DbgPrint("!(CheckedFlags & ~HEAP_CREATE_VALID_MASK)");
      RtlpHeapHandleError(2);
    }
    if ( (v13 & 0xFFF80800) != 0 )
      v13 &= 0x7F7FFu;
  }
LABEL_10:
  memset_thunk_772440563353939046(&v100, 0, 0x60u);
  if ( v10 && *(_DWORD *)v10 == 96 )
  {
    v100 = *(_OWORD *)v10;
    v101 = *(_OWORD *)(v10 + 16);
    v102 = *(_OWORD *)(v10 + 32);
    v103 = *(_OWORD *)(v10 + 48);
    v104 = *(_OWORD *)(v10 + 64);
    v105 = *(_OWORD *)(v10 + 80);
  }
  if ( (NtGlobalFlag & 0x10) != 0 )
    v13 |= 0x20u;
  v15 = v13 | 0x40;
  if ( (NtGlobalFlag & 0x20) == 0 )
    v15 = v13;
  v16 = v15 | 0x80;
  if ( (NtGlobalFlag & 0x200000) == 0 )
    v16 = v15;
  v17 = v16 | 0x40000000;
  if ( (NtGlobalFlag & 0x40) == 0 )
    v17 = v16;
  v18 = v17 | 0x20000000;
  if ( (NtGlobalFlag & 0x80) == 0 )
    v18 = v17;
  v19 = v18 | 0x8000000;
  if ( (NtGlobalFlag & 0x1000) == 0 )
    v19 = v18;
  v20 = NtCurrentPeb();
  if ( !*((_QWORD *)&v100 + 1) )
    *((_QWORD *)&v100 + 1) = v20->HeapSegmentReserve;
  if ( !(_QWORD)v101 )
    *(_QWORD *)&v101 = v20->HeapSegmentCommit;
  if ( !*((_QWORD *)&v101 + 1) )
    *((_QWORD *)&v101 + 1) = v20->HeapDeCommitFreeBlockThreshold;
  if ( !(_QWORD)v102 )
    *(_QWORD *)&v102 = v20->HeapDeCommitTotalFreeThreshold;
  v21 = qword_1801C6700;
  if ( !qword_1801C6700 )
  {
    qword_1801C6708 = 0x10000;
    if ( NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0) < 0 )
    {
LABEL_110:
      v8 = v82;
      goto LABEL_92;
    }
    v21 = v108;
    qword_1801C6700 = v108;
  }
  if ( !*((_QWORD *)&v102 + 1) )
    *((_QWORD *)&v102 + 1) = v21 - qword_1801C6708 - 4096;
  v22 = v103;
  if ( (unsigned __int64)(v103 - 1) > 0xFEFFF )
    v22 = 1044480;
  *(_QWORD *)&v103 = v22;
  if ( v89 )
    v23 = (unsigned __int64)(v89 + 0x1FFF) & 0xFFFFFFFFFFFFE000uLL;
  else
    v23 = 0x2000;
  v86 = v23;
  if ( v87 )
    v24 = (v87 + 0x1FFF) & 0xFFFFFFFFFFFFE000uLL;
  else
    v24 = (v23 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
  v84 = v24;
  if ( v23 > v24 )
  {
    LODWORD(v23) = v24;
    v86 = v24;
    v25 = v24;
  }
  else
  {
    v25 = v23;
  }
  v8 = v82;
  if ( (v19 & 2) != 0 && !v82 )
  {
    v93[0] = 4096;
    v26 = 2;
    NtGlobalFlag = 2;
    if ( v24 - 4096 < v25 )
    {
      v24 = (v24 + 69631) & 0xFFFFFFFFFFFF0000uLL;
      v84 = v24;
    }
  }
  else
  {
    v26 = 0;
    NtGlobalFlag = 0;
    v93[0] = 0;
  }
  if ( !v25 || !v24 )
    goto LABEL_92;
  if ( (v19 & 0x61000000) != 0 && (v19 & 0x10000000) == 0 )
    return RtlDebugCreateHeap(v19, (_DWORD)v82, v24, v23, v81, (__int64)&v100, v91);
  v27 = v81;
  if ( (v19 & 1) != 0 )
  {
    if ( v81 )
    {
      v59 = 0;
      goto LABEL_94;
    }
    LODWORD(v90) = 712;
  }
  else
  {
    if ( v81 )
      v19 |= 0x80000000;
    LODWORD(v90) = v81 != 0 ? 712 : 752;
    v83 = v81 & -(__int64)(v81 != 0);
  }
  if ( v82 )
  {
    if ( *((_QWORD *)&v104 + 1) )
    {
      if ( !*((_QWORD *)&v103 + 1) || !(_QWORD)v104 || *((_QWORD *)&v103 + 1) > (unsigned __int64)v104 || (v19 & 2) != 0 )
        goto LABEL_105;
      v88 = (char *)v82;
      v32 = (char *)v82 + *((_QWORD *)&v103 + 1);
      v84 = v104;
      memset_thunk_772440563353939046(v82, 0, 0x1000u);
      v34 = (char *)v82;
    }
    else
    {
      if ( (int)ZwQueryVirtualMemory(-1, v82, 0, v94, 48, 0) < 0 )
        goto LABEL_200;
      v32 = (char *)v94[0];
      if ( v94[0] != v82 || (_DWORD)v96 == 0x10000 )
        goto LABEL_199;
      v34 = (char *)v94[0];
      v88 = (char *)v94[0];
      if ( (_DWORD)v96 == 4096 )
      {
        if ( (v19 & 0x40000) != 0 && (BYTE4(v96) & 0x40) == 0 )
          goto LABEL_199;
        memset_thunk_772440563353939046(v94[0], 0, 0x1000u);
        v8 = v82;
        if ( (int)ZwQueryVirtualMemory(-1, v82, 3, &v97, 48, 0) < 0 )
          goto LABEL_200;
        v84 = v98;
        v86 = *((_QWORD *)&v95 + 1);
        v34 = v88;
        v32 = &v88[*((_QWORD *)&v95 + 1)];
      }
      else
      {
        v84 = *((_QWORD *)&v95 + 1);
        v74 = v86;
        if ( v86 > *((_QWORD *)&v95 + 1) )
        {
          v74 = *((_QWORD *)&v95 + 1);
          v86 = *((_QWORD *)&v95 + 1);
        }
        if ( v74 < 0x2000 )
          goto LABEL_199;
      }
    }
    NtGlobalFlag = v26 | 1;
    v33 = (char *)v82;
    v80 = (char *)v82;
    goto LABEL_61;
  }
  v89 = 0;
  v87 = 0;
  v92 = 0;
  if ( *((_QWORD *)&v104 + 1) )
  {
LABEL_105:
    v59 = 0;
    v60 = v83;
    goto LABEL_95;
  }
  v28 = qword_1801C5F00;
  do
  {
    v29 = v28 ^ (v28 >> 12) ^ ((v28 ^ (v28 >> 12)) << 25) ^ ((v28 ^ (v28 >> 12) ^ ((v28 ^ (v28 >> 12)) << 25)) >> 27);
    v30 = v28;
    v28 = _InterlockedCompareExchange64(&qword_1801C5F00, v29, v28);
  }
  while ( v30 != v28 );
  v92 = (unsigned __int64)((-3 * (_BYTE)v29) & 0x1F) << 16;
  v87 = v84 + v92;
  if ( v84 + v92 < v84 )
  {
    v87 = v84;
    v92 = 0;
  }
  if ( (int)ZwAllocateVirtualMemory(-1, &v89, 0, &v87, 0x2000, (v19 & 0x40000) != 0 ? 64 : 4) < 0 )
    goto LABEL_200;
  v32 = v89;
  v33 = v89;
  v80 = v89;
  v84 = v87;
  if ( v92 )
  {
    RtlpSecMemFreeVirtualMemory(v31, &v89, &v92, 0x8000);
    v32 = &v89[v92];
    v33 = &v89[v92];
    v80 = &v89[v92];
    v84 = v87 - v92;
  }
  v34 = v33;
  v88 = v33;
LABEL_61:
  if ( v34 != v32 )
  {
    v35 = 2147353472;
    goto LABEL_63;
  }
  if ( (int)ZwAllocateVirtualMemory(-1, &v88, 0, &v86, 4096, (v19 & 0x40000) != 0 ? 64 : 4) < 0 )
  {
LABEL_199:
    v8 = v82;
    goto LABEL_200;
  }
  v35 = 2147353472;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v63, v62, v64, v65) )
    v66 = (__int64)NtCurrentPeb()->SharedData + 550;
  else
    v66 = 2147353472;
  if ( *(_BYTE *)v66 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
    RtlpLogHeapCommit(v80, v88, v86, 1);
  v32 += v86;
  v33 = v80;
LABEL_63:
  v36 = v33 + 712;
  if ( (NtCurrentPeb()->NtGlobalFlag & 0x800) != 0 )
  {
    v77 = (unsigned __int64)(v36 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    *((_QWORD *)v80 + 41) = v77;
    v37 = v90 + 2064;
    v36 = (char *)(v77 + 2064);
    v19 |= 0x4000000u;
  }
  else
  {
    v37 = v90;
  }
  LODWORD(v90) = (v37 + 15) & 0xFFFFFFF0;
  *((_WORD *)v80 + 4) = (unsigned int)v90 >> 4;
  v80[10] = 1;
  v80[15] = 1;
  *((_DWORD *)v80 + 38) = -285217025;
  *((_DWORD *)v80 + 28) = v19 & 0xEFFFFFFF;
  *((_DWORD *)v80 + 36) = 0;
  memset_thunk_772440563353939046(v80 + 568, 0, 0x80u);
  RtlpCreateHeapEncoding(v80);
  *((_DWORD *)v80 + 164) = 1;
  v38 = v80;
  if ( (*((_DWORD *)v80 + 28) & 0x8000000) != 0 )
  {
    HeapInterceptorIndex = RtlpGetHeapInterceptorIndex(RtlpStackTraceDatabaseLogPrefix);
    *(_DWORD *)(v79 + 144) = HeapInterceptorIndex;
    *((_DWORD *)v80 + 28) &= ~0x40u;
    v38 = v80;
  }
  *((_DWORD *)v38 + 29) = v19 & 0x6001007D;
  *((_WORD *)v80 + 105) = (_WORD)v36 - (_WORD)v80;
  *((_QWORD *)v80 + 27) = 0;
  v39 = v80 + 336;
  *((_QWORD *)v80 + 43) = v80 + 336;
  *v39 = v39;
  v40 = v80 + 272;
  *((_QWORD *)v80 + 35) = v80 + 272;
  *v40 = v40;
  v41 = v80 + 288;
  *((_QWORD *)v80 + 37) = v80 + 288;
  *v41 = v41;
  v42 = v80 + 240;
  *((_QWORD *)v80 + 31) = v80 + 240;
  *v42 = v42;
  if ( !v83 && (v19 & 1) == 0 )
  {
    if ( (int)RtlInitializeCriticalSectionEx(v36, 0, 0x10000000) >= 0 )
    {
      v83 = (__int64)v36;
      v36 += 40;
      goto LABEL_69;
    }
    goto LABEL_110;
  }
LABEL_69:
  *((_QWORD *)v80 + 44) = v83;
  *((_DWORD *)v80 + 30) |= 0x80000000;
  v43 = RtlpInitializeHeapSegment(
          (_DWORD)v80,
          (_DWORD)v80,
          (int)v90 + 1104,
          (_DWORD)v38,
          NtGlobalFlag,
          (__int64)v88,
          (__int64)v32,
          (__int64)&v88[v84 - v93[0]]);
  v8 = v82;
  if ( v43 )
  {
    if ( v82 )
      memset_thunk_772440563353939046(v36, 0, 0x80u);
    *((_DWORD *)v36 + 2) = 128;
    *((_QWORD *)v36 + 5) = v36 + 56;
    *((_QWORD *)v36 + 4) = v80 + 336;
    *((_QWORD *)v36 + 6) = v36 + 72;
    RtlpPopulateListIndex(v80, v36);
    *((_WORD *)v80 + 104) = 0;
    *((_QWORD *)v80 + 20) = *((_QWORD *)&v100 + 1);
    *((_QWORD *)v80 + 21) = v101;
    *((_QWORD *)v80 + 22) = *((_QWORD *)&v101 + 1) >> 4;
    *((_QWORD *)v80 + 23) = (unsigned __int64)v102 >> 4;
    *((_QWORD *)v80 + 25) = *((_QWORD *)&v102 + 1);
    *((_DWORD *)v80 + 37) = (unsigned __int64)(v103 + 15) >> 4;
    *((_QWORD *)v80 + 45) = RtlpHeapKey ^ *((_QWORD *)&v104 + 1);
    *((_DWORD *)v80 + 174) = 4;
    *((_QWORD *)v80 + 88) = 2088960;
    if ( (RtlpDisableHeapLookaside & 1) != 0 )
      *((_DWORD *)v80 + 30) = 1;
    *((_QWORD *)v80 + 32) = 31;
    *((_QWORD *)v80 + 33) = -16;
    v44 = v80;
    if ( (v80[112] & 0x20) != 0 )
    {
      *((_QWORD *)v80 + 32) += 16LL;
      v44 = v80;
    }
    *((_QWORD *)v44 + 51) = 0;
    *((_WORD *)v80 + 208) = 0;
    v80[418] = 0;
    v80[419] = 0;
    *((_QWORD *)v80 + 40) = 0;
    if ( (v19 & 3) != 2 || (RtlpDisableHeapLookaside & 1) != 0 )
    {
LABEL_77:
      v80[563] = 0;
      *((_QWORD *)v80 + 46) = 0;
      if ( (int)RtlpProcessHeapsInsert(v80, v91) >= 0 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v46, v45, v47, v48) )
          v52 = (__int64)NtCurrentPeb()->SharedData + 550;
        else
          v52 = 2147353472;
        if ( *(_BYTE *)v52 && (NtCurrentPeb()->TracingFlags & 1) != 0 )
        {
          if ( (unsigned int)RtlGetCurrentServiceSessionId(v52, v49, v50, v51) )
            v35 = (__int64)NtCurrentPeb()->SharedData + 550;
          RtlpLogHeapCreateEvent((_DWORD)v80, v19, v84, v86, *(unsigned __int8 *)v35);
        }
        v56 = 2147353482;
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v52, v49, v50, v51) )
          v57 = (__int64)NtCurrentPeb()->SharedData + 560;
        else
          v57 = 2147353482;
        if ( *(_BYTE *)v57 )
        {
          if ( (unsigned int)RtlGetCurrentServiceSessionId(v57, v53, v54, v55) )
            v56 = (__int64)NtCurrentPeb()->SharedData + 560;
          RtlpLogHeapCreateEvent((_DWORD)v80, v19, v84, v86, *(unsigned __int8 *)v56);
        }
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v57, v53, v54, v55) )
          v58 = (__int64)NtCurrentPeb()->SharedData + 558;
        else
          v58 = 2147353480;
        if ( *(_BYTE *)v58 )
          RtlpHeapLogRangeCreate(v80, v84, v19);
        *((_DWORD *)v80 + 30) &= ~0x80000000;
        v59 = (__int64)v80;
        v80 = 0;
        goto LABEL_93;
      }
      goto LABEL_200;
    }
    *((_QWORD *)v80 + 53) = RtlAllocateHeap_0(v80, 8388618, 256);
    v75 = *((_QWORD *)v80 + 53);
    if ( v75 )
    {
      *(_BYTE *)(v75 - 1) = 1;
      *((_WORD *)v80 + 216) = 128;
      goto LABEL_77;
    }
  }
LABEL_200:
  v59 = 0;
  v60 = v83;
  v27 = v81;
LABEL_95:
  if ( v60 && v60 != v27 )
    RtlDeleteCriticalSection();
  if ( v80 )
  {
    if ( !v8 )
    {
      v84 = 0;
      RtlpSecMemFreeVirtualMemory(v60, &v80, &v84, 0x8000);
    }
  }
  return v59;
}

```

## disassembly

```asm
0x18006a124  push    rbx
0x18006a126  push    rsi
0x18006a127  push    rdi
0x18006a128  push    r12
0x18006a12a  push    r13
0x18006a12c  push    r14
0x18006a12e  push    r15
0x18006a130  sub     rsp, 220h
0x18006a137  mov     rax, cs:__security_cookie
0x18006a13e  xor     rax, rsp
0x18006a141  mov     [rsp+258h+var_48], rax
0x18006a149  mov     r12, r9
0x18006a14c  mov     [rsp+258h+var_1D0], r9
0x18006a154  mov     [rsp+258h+var_1E0], r8
0x18006a159  mov     r14, rdx
0x18006a15c  mov     [rsp+258h+var_208], rdx
0x18006a161  mov     r15d, ecx
0x18006a164  mov     rax, [rsp+258h+arg_20]
0x18006a16c  mov     [rsp+258h+var_210], rax
0x18006a171  mov     [rsp+258h+var_1B8], rdx
0x18006a179  mov     [rsp+258h+var_1C8], rax
0x18006a181  mov     rsi, [rsp+258h+arg_28]
0x18006a189  mov     ebx, [rsp+258h+arg_30]
0x18006a190  mov     [rsp+258h+var_1C0], ebx
0x18006a197  xor     edi, edi
0x18006a199  mov     [rsp+258h+var_1D8], rdi
0x18006a1a1  mov     rax, gs:60h
0x18006a1aa  mov     eax, [rax+0BCh]
0x18006a1b0  mov     [rsp+258h+var_1F0], eax
0x18006a1b4  xorps   xmm0, xmm0
0x18006a1b7  movups  xmmword ptr [rsp+258h+var_198], xmm0
0x18006a1bf  movups  [rsp+258h+var_188], xmm0
0x18006a1c7  movups  [rsp+258h+var_178], xmm0
0x18006a1cf  xorps   xmm1, xmm1
0x18006a1d2  movups  [rsp+258h+var_168], xmm1
0x18006a1da  movups  [rsp+258h+var_158], xmm1
0x18006a1e2  movups  [rsp+258h+var_148], xmm1
0x18006a1ea  xor     eax, eax
0x18006a1ec  mov     dword ptr [rsp+258h+var_138+4], eax
0x18006a1f3  xor     edx, edx; Val
0x18006a1f5  lea     r8d, [rdi+5Ch]; Size
0x18006a1f9  lea     rcx, [rsp+258h+var_138]; void *
0x18006a201  call    memset$thunk$772440563353939046
0x18006a206  mov     [rsp+258h+var_1E8], rdi
0x18006a20b  mov     [rsp+258h+var_1F8], rdi
0x18006a210  xor     edx, edx; Val
0x18006a212  lea     r8d, [rdi+40h]; Size
0x18006a216  lea     rcx, [rsp+258h+SystemInformation]; void *
0x18006a21e  call    memset$thunk$772440563353939046
0x18006a223  xor     edx, edx; Val
0x18006a225  lea     r8d, [rdi+50h]; Size
0x18006a229  lea     rcx, [rsp+258h+var_D8]; void *
0x18006a231  call    memset$thunk$772440563353939046
0x18006a236  mov     r13d, edi
0x18006a239  test    ebx, ebx
0x18006a23b  setnz   r13b
0x18006a23f  mov     [rsp+258h+var_218], rdi
0x18006a244  mov     [rsp+258h+var_200], rdi
0x18006a249  bt      r15d, 0Ah
0x18006a24e  jb      loc_18006A9CF
0x18006a254  mov     bl, dil
0x18006a257  cmp     cs:dword_1801C4588, edi
0x18006a25d  jnz     loc_18006AFE0
0x18006a263  mov     r12d, 1
0x18006a269  and     r15d, 0F1FFFFFFh
0x18006a270  bt      r15d, 8
0x18006a275  jb      loc_18006ABD4
0x18006a27b  mov     r14, rdi
0x18006a27e  test    cs:RtlpHpHeapFeatures, r12b
0x18006a285  jnz     loc_18006AE21
0x18006a28b  test    r14, r14
0x18006a28e  jnz     loc_18006A9A3
0x18006a294  bt      r15d, 1Ch
0x18006a299  jb      short loc_18006A2B5
0x18006a29b  cmp     cs:RtlpHeapErrorHandlerThreshold, 2
0x18006a2a2  jge     loc_18006B085
0x18006a2a8  test    r15d, 0FFF80800h
0x18006a2af  jnz     loc_18006B0EB
0x18006a2b5  xor     edx, edx; Val
0x18006a2b7  lea     r8d, [rdx+60h]; Size
0x18006a2bb  lea     rcx, [rsp+258h+var_138]; void *
0x18006a2c3  call    memset$thunk$772440563353939046
0x18006a2c8  test    rsi, rsi
0x18006a2cb  jnz     loc_18006AAF2
0x18006a2d1  mov     r8d, [rsp+258h+var_1F0]
0x18006a2d6  test    r8b, 10h
0x18006a2da  jnz     loc_18006B0F7
0x18006a2e0  mov     ecx, r15d
0x18006a2e3  or      ecx, 40h
0x18006a2e6  test    r8b, 20h
0x18006a2ea  cmovz   ecx, r15d
0x18006a2ee  mov     edx, ecx
0x18006a2f0  mov     r9d, 80h
0x18006a2f6  or      edx, r9d
0x18006a2f9  bt      r8d, 15h
0x18006a2fe  cmovnb  edx, ecx
0x18006a301  mov     ecx, edx
0x18006a303  bts     ecx, 1Eh
0x18006a307  test    r8b, 40h
0x18006a30b  cmovz   ecx, edx
0x18006a30e  mov     edx, ecx
0x18006a310  bts     edx, 1Dh
0x18006a314  test    r9b, r8b
0x18006a317  cmovz   edx, ecx
0x18006a31a  mov     r10d, 1000h
0x18006a320  mov     esi, edx
0x18006a322  bts     esi, 1Bh
0x18006a326  test    [rsp+258h+var_1F0], r10d
0x18006a32b  cmovz   esi, edx
0x18006a32e  mov     rcx, gs:60h
0x18006a337  cmp     qword ptr [rsp+258h+var_138+8], rdi
0x18006a33f  jnz     short loc_18006A350
0x18006a341  mov     rax, [rcx+0C8h]
0x18006a348  mov     qword ptr [rsp+258h+var_138+8], rax
0x18006a350  cmp     qword ptr [rsp+258h+var_128], rdi
0x18006a358  jnz     short loc_18006A369
0x18006a35a  mov     rax, [rcx+0D0h]
0x18006a361  mov     qword ptr [rsp+258h+var_128], rax
0x18006a369  cmp     qword ptr [rsp+258h+var_128+8], rdi
0x18006a371  jz      loc_18006AA28
0x18006a377  cmp     qword ptr [rsp+258h+var_118], rdi
0x18006a37f  jz      loc_18006AADE
0x18006a385  mov     rax, cs:qword_1801C6700
0x18006a38c  test    rax, rax
0x18006a38f  jz      loc_18006AA4F
0x18006a395  cmp     qword ptr [rsp+258h+var_118+8], rdi
0x18006a39d  jz      loc_18006AEE9
0x18006a3a3  mov     rcx, qword ptr [rsp+258h+var_108]
0x18006a3ab  lea     rax, [rcx-1]
0x18006a3af  mov     edx, 0FF000h
0x18006a3b4  cmp     rax, 0FEFFFh
0x18006a3ba  cmova   rcx, rdx
0x18006a3be  mov     qword ptr [rsp+258h+var_108], rcx
0x18006a3c6  mov     r9, [rsp+258h+var_1D0]
0x18006a3ce  test    r9, r9
0x18006a3d1  jnz     loc_18006AA3C
0x18006a3d7  mov     r9d, 2000h
0x18006a3dd  mov     [rsp+258h+var_1E8], r9
0x18006a3e2  mov     rax, [rsp+258h+var_1E0]
0x18006a3e7  test    rax, rax
0x18006a3ea  jnz     loc_18006AA15
0x18006a3f0  lea     r8, [r9+0FFFFh]
0x18006a3f7  and     r8, 0FFFFFFFFFFFF0000h
0x18006a3fe  mov     [rsp+258h+var_1F8], r8
0x18006a403  cmp     r9, r8
0x18006a406  ja      loc_18006B100
0x18006a40c  mov     rcx, r9
0x18006a40f  mov     r14, [rsp+258h+var_208]
0x18006a414  test    sil, 2
0x18006a418  jz      short loc_18006A423
0x18006a41a  test    r14, r14
0x18006a41d  jz      loc_18006AE55
0x18006a423  mov     r15d, edi
0x18006a426  mov     [rsp+258h+var_1F0], edi
0x18006a42a  mov     [rsp+258h+var_1A8], rdi
0x18006a432  mov     rax, r8
0x18006a435  test    rcx, rcx
0x18006a438  jz      loc_18006A9CF
0x18006a43e  test    rax, rax
0x18006a441  jz      loc_18006A9CF
0x18006a447  test    esi, 61000000h
0x18006a44d  jnz     loc_18006B110
0x18006a453  mov     rdx, [rsp+258h+var_210]
0x18006a458  test    r12b, sil
0x18006a45b  jz      loc_18006AA92
0x18006a461  test    rdx, rdx
0x18006a464  jnz     loc_18006AAD6
0x18006a46a  mov     dword ptr [rsp+258h+var_1C8], 2C8h
0x18006a475  test    r14, r14
0x18006a478  jnz     loc_18006ACD9
0x18006a47e  mov     [rsp+258h+var_1D0], rdi
0x18006a486  mov     [rsp+258h+var_1E0], rdi
0x18006a48b  mov     [rsp+258h+var_1B8], rdi
0x18006a493  cmp     qword ptr [rsp+258h+var_F8+8], rdi
0x18006a49b  jnz     loc_18006AAC9
0x18006a4a1  mov     rax, cs:qword_1801C5F00
0x18006a4a8  mov     rcx, rax
0x18006a4ab  shr     rcx, 0Ch
0x18006a4af  xor     rcx, rax
0x18006a4b2  mov     rdx, rcx
0x18006a4b5  shl     rdx, 19h
0x18006a4b9  xor     rdx, rcx
0x18006a4bc  mov     rcx, rdx
0x18006a4bf  shr     rcx, 1Bh
0x18006a4c3  xor     rcx, rdx
0x18006a4c6  lock cmpxchg cs:qword_1801C5F00, rcx
0x18006a4cf  jnz     short loc_18006A4A8
0x18006a4d1  imul    rax, rcx, -3
0x18006a4d5  and     eax, 1Fh
0x18006a4d8  shl     rax, 10h
0x18006a4dc  mov     [rsp+258h+var_1B8], rax
0x18006a4e4  mov     rcx, [rsp+258h+var_1F8]
0x18006a4e9  add     rax, rcx
0x18006a4ec  mov     [rsp+258h+var_1E0], rax
0x18006a4f1  cmp     rax, rcx
0x18006a4f4  jb      loc_18006B1E3
0x18006a4fa  mov     eax, esi
0x18006a4fc  and     eax, 40000h
0x18006a501  neg     eax
0x18006a503  sbb     ecx, ecx
0x18006a505  and     ecx, 3Ch
0x18006a508  add     ecx, 4
0x18006a50b  mov     dword ptr [rsp+258h+var_230], ecx
0x18006a50f  mov     dword ptr [rsp+258h+var_238], 2000h
0x18006a517  lea     r9, [rsp+258h+var_1E0]
0x18006a51c  xor     r8d, r8d
0x18006a51f  lea     rdx, [rsp+258h+var_1D0]
0x18006a527  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006a52b  call    ZwAllocateVirtualMemory
0x18006a530  test    eax, eax
0x18006a532  js      loc_18006B1D1
0x18006a538  mov     r14, [rsp+258h+var_1D0]
0x18006a540  mov     rbx, r14
0x18006a543  mov     [rsp+258h+var_218], rbx
0x18006a548  mov     rax, [rsp+258h+var_1E0]
0x18006a54d  mov     [rsp+258h+var_1F8], rax
0x18006a552  cmp     [rsp+258h+var_1B8], rdi
0x18006a55a  jz      short loc_18006A5A1
0x18006a55c  mov     r9d, 8000h
0x18006a562  lea     r8, [rsp+258h+var_1B8]
0x18006a56a  lea     rdx, [rsp+258h+var_1D0]
0x18006a572  call    RtlpSecMemFreeVirtualMemory
0x18006a577  mov     r14, [rsp+258h+var_1D0]
0x18006a57f  add     r14, [rsp+258h+var_1B8]
0x18006a587  mov     rbx, r14
0x18006a58a  mov     [rsp+258h+var_218], rbx
0x18006a58f  mov     rax, [rsp+258h+var_1E0]
0x18006a594  sub     rax, [rsp+258h+var_1B8]
0x18006a59c  mov     [rsp+258h+var_1F8], rax
0x18006a5a1  mov     rcx, rbx
0x18006a5a4  mov     [rsp+258h+var_1D8], rbx
0x18006a5ac  mov     r13d, 3
0x18006a5b2  cmp     rcx, r14
0x18006a5b5  jz      loc_18006AB68
0x18006a5bb  mov     r15d, 7FFE0380h
0x18006a5c1  add     rbx, 2C8h
0x18006a5c8  mov     rax, gs:60h
0x18006a5d1  test    dword ptr [rax+0BCh], 800h
0x18006a5db  jnz     loc_18006B246
0x18006a5e1  mov     eax, dword ptr [rsp+258h+var_1C8]
0x18006a5e8  add     eax, 0Fh
0x18006a5eb  and     eax, 0FFFFFFF0h
0x18006a5ee  mov     dword ptr [rsp+258h+var_1C8], eax
0x18006a5f5  mov     ecx, eax
0x18006a5f7  shr     ecx, 4
0x18006a5fa  mov     rax, [rsp+258h+var_218]
0x18006a5ff  mov     [rax+8], cx
0x18006a603  mov     rax, [rsp+258h+var_218]
0x18006a608  mov     [rax+0Ah], r12b
0x18006a60c  mov     rax, [rsp+258h+var_218]
0x18006a611  mov     [rax+0Fh], r12b
0x18006a615  mov     rax, [rsp+258h+var_218]
0x18006a61a  mov     dword ptr [rax+98h], 0EEFFEEFFh
0x18006a624  mov     ecx, esi
0x18006a626  btr     ecx, 1Ch
0x18006a62a  mov     rax, [rsp+258h+var_218]
0x18006a62f  mov     [rax+70h], ecx
0x18006a632  mov     rax, [rsp+258h+var_218]
0x18006a637  mov     [rax+90h], edi
0x18006a63d  mov     rcx, [rsp+258h+var_218]
0x18006a642  add     rcx, 238h; void *
0x18006a649  xor     edx, edx; Val
0x18006a64b  mov     r8d, 80h; Size
0x18006a651  call    memset$thunk$772440563353939046
0x18006a656  mov     rcx, [rsp+258h+var_218]
0x18006a65b  call    RtlpCreateHeapEncoding
0x18006a660  mov     r10, [rsp+258h+var_218]
0x18006a665  mov     [r10+290h], r12d
0x18006a66c  mov     r9, [rsp+258h+var_218]
0x18006a671  test    dword ptr [r9+70h], 8000000h
0x18006a679  jnz     loc_18006B274
0x18006a67f  mov     eax, esi
0x18006a681  and     eax, 6001007Dh
0x18006a686  mov     [r9+74h], eax
0x18006a68a  movzx   ecx, bx
0x18006a68d  mov     rax, [rsp+258h+var_218]
0x18006a692  sub     cx, ax
0x18006a695  mov     [rax+0D2h], cx
0x18006a69c  mov     rax, [rsp+258h+var_218]
0x18006a6a1  mov     [rax+0D8h], rdi
0x18006a6a8  mov     rax, [rsp+258h+var_218]
0x18006a6ad  add     rax, 150h
0x18006a6b3  mov     [rax+8], rax
0x18006a6b7  mov     [rax], rax
0x18006a6ba  mov     rax, [rsp+258h+var_218]
0x18006a6bf  add     rax, 110h
0x18006a6c5  mov     [rax+8], rax
0x18006a6c9  mov     [rax], rax
0x18006a6cc  mov     rax, [rsp+258h+var_218]
0x18006a6d1  add     rax, 120h
0x18006a6d7  mov     [rax+8], rax
0x18006a6db  mov     [rax], rax
0x18006a6de  mov     rax, [rsp+258h+var_218]
0x18006a6e3  add     rax, 0F0h
0x18006a6e9  mov     [rax+8], rax
0x18006a6ed  mov     [rax], rax
0x18006a6f0  cmp     [rsp+258h+var_200], rdi
0x18006a6f5  jnz     short loc_18006A700
0x18006a6f7  test    r12b, sil
0x18006a6fa  jz      loc_18006ADFB
  ... truncated ...
```
