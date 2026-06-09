# RtlpCreateHeap

- ea: `0x180086bd4`
- end: `0x180087eb0`
- name: `RtlpCreateHeap`
- size: `4828`
- prototype: ``
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e1b4`
- `0x180081f38`
- `0x180085b60`
- `0x180086838`
- `0x180086ba0`
- `0x180087f40`
- `0x180108fb0`
- `0x180110cac`

## callees

- `0x18000416c`
- `0x180007060`
- `0x180007cb0`
- `0x180017e90`
- `0x1800183a0`
- `0x18001b984`
- `0x180058fb0`
- `0x180059b1c`
- `0x18005a1e0`
- `0x18005a7a0`
- `0x18006f0d0`
- `0x180086bd4`
- `0x1800881d0`
- `0x180088294`
- `0x1800e6c4c`
- `0x1800e82e4`
- `0x1800fb940`
- `0x1800fba70`
- `0x1800ff0c8`
- `0x1800ff1f8`
- `0x180101588`
- `0x180103f20`
- `0x18010eedc`
- `0x180110b54`
- `0x180110cac`
- `0x18011f220`
- `0x18015ede0`
- `0x18015ef40`
- `0x18015f1a0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x180087b80`: `!(CheckedFlags & ~HEAP_CREATE_VALID_MASK)`

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
          if ( (dword_1801C68B8 & 1) != 0 && (dword_1801C68B8 & 2) != 0 )
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
  v21 = qword_1801C66F0;
  if ( !qword_1801C66F0 )
  {
    qword_1801C66F8 = 0x10000;
    if ( NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0) < 0 )
    {
LABEL_110:
      v8 = v82;
      goto LABEL_92;
    }
    v21 = v108;
    qword_1801C66F0 = v108;
  }
  if ( !*((_QWORD *)&v102 + 1) )
    *((_QWORD *)&v102 + 1) = v21 - qword_1801C66F8 - 4096;
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
0x180086bd4  push    rbx
0x180086bd6  push    rsi
0x180086bd7  push    rdi
0x180086bd8  push    r12
0x180086bda  push    r13
0x180086bdc  push    r14
0x180086bde  push    r15
0x180086be0  sub     rsp, 220h
0x180086be7  mov     rax, cs:__security_cookie
0x180086bee  xor     rax, rsp
0x180086bf1  mov     [rsp+258h+var_48], rax
0x180086bf9  mov     r12, r9
0x180086bfc  mov     [rsp+258h+var_1D0], r9
0x180086c04  mov     [rsp+258h+var_1E0], r8
0x180086c09  mov     r14, rdx
0x180086c0c  mov     [rsp+258h+var_208], rdx
0x180086c11  mov     r15d, ecx
0x180086c14  mov     rax, [rsp+258h+arg_20]
0x180086c1c  mov     [rsp+258h+var_210], rax
0x180086c21  mov     [rsp+258h+var_1B8], rdx
0x180086c29  mov     [rsp+258h+var_1C8], rax
0x180086c31  mov     rsi, [rsp+258h+arg_28]
0x180086c39  mov     ebx, [rsp+258h+arg_30]
0x180086c40  mov     [rsp+258h+var_1C0], ebx
0x180086c47  xor     edi, edi
0x180086c49  mov     [rsp+258h+var_1D8], rdi
0x180086c51  mov     rax, gs:60h
0x180086c5a  mov     eax, [rax+0BCh]
0x180086c60  mov     [rsp+258h+var_1F0], eax
0x180086c64  xorps   xmm0, xmm0
0x180086c67  movups  xmmword ptr [rsp+258h+var_198], xmm0
0x180086c6f  movups  [rsp+258h+var_188], xmm0
0x180086c77  movups  [rsp+258h+var_178], xmm0
0x180086c7f  xorps   xmm1, xmm1
0x180086c82  movups  [rsp+258h+var_168], xmm1
0x180086c8a  movups  [rsp+258h+var_158], xmm1
0x180086c92  movups  [rsp+258h+var_148], xmm1
0x180086c9a  xor     eax, eax
0x180086c9c  mov     dword ptr [rsp+258h+var_138+4], eax
0x180086ca3  xor     edx, edx; Val
0x180086ca5  lea     r8d, [rdi+5Ch]; Size
0x180086ca9  lea     rcx, [rsp+258h+var_138]; void *
0x180086cb1  call    memset$thunk$772440563353939046
0x180086cb6  mov     [rsp+258h+var_1E8], rdi
0x180086cbb  mov     [rsp+258h+var_1F8], rdi
0x180086cc0  xor     edx, edx; Val
0x180086cc2  lea     r8d, [rdi+40h]; Size
0x180086cc6  lea     rcx, [rsp+258h+SystemInformation]; void *
0x180086cce  call    memset$thunk$772440563353939046
0x180086cd3  xor     edx, edx; Val
0x180086cd5  lea     r8d, [rdi+50h]; Size
0x180086cd9  lea     rcx, [rsp+258h+var_D8]; void *
0x180086ce1  call    memset$thunk$772440563353939046
0x180086ce6  mov     r13d, edi
0x180086ce9  test    ebx, ebx
0x180086ceb  setnz   r13b
0x180086cef  mov     [rsp+258h+var_218], rdi
0x180086cf4  mov     [rsp+258h+var_200], rdi
0x180086cf9  bt      r15d, 0Ah
0x180086cfe  jb      loc_18008747F
0x180086d04  mov     bl, dil
0x180086d07  cmp     cs:dword_1801C4588, edi
0x180086d0d  jnz     loc_180087A90
0x180086d13  mov     r12d, 1
0x180086d19  and     r15d, 0F1FFFFFFh
0x180086d20  bt      r15d, 8
0x180086d25  jb      loc_180087684
0x180086d2b  mov     r14, rdi
0x180086d2e  test    cs:RtlpHpHeapFeatures, r12b
0x180086d35  jnz     loc_1800878D1
0x180086d3b  test    r14, r14
0x180086d3e  jnz     loc_180087453
0x180086d44  bt      r15d, 1Ch
0x180086d49  jb      short loc_180086D65
0x180086d4b  cmp     cs:RtlpHeapErrorHandlerThreshold, 2
0x180086d52  jge     loc_180087B35
0x180086d58  test    r15d, 0FFF80800h
0x180086d5f  jnz     loc_180087B9B
0x180086d65  xor     edx, edx; Val
0x180086d67  lea     r8d, [rdx+60h]; Size
0x180086d6b  lea     rcx, [rsp+258h+var_138]; void *
0x180086d73  call    memset$thunk$772440563353939046
0x180086d78  test    rsi, rsi
0x180086d7b  jnz     loc_1800875A2
0x180086d81  mov     r8d, [rsp+258h+var_1F0]
0x180086d86  test    r8b, 10h
0x180086d8a  jnz     loc_180087BA7
0x180086d90  mov     ecx, r15d
0x180086d93  or      ecx, 40h
0x180086d96  test    r8b, 20h
0x180086d9a  cmovz   ecx, r15d
0x180086d9e  mov     edx, ecx
0x180086da0  mov     r9d, 80h
0x180086da6  or      edx, r9d
0x180086da9  bt      r8d, 15h
0x180086dae  cmovnb  edx, ecx
0x180086db1  mov     ecx, edx
0x180086db3  bts     ecx, 1Eh
0x180086db7  test    r8b, 40h
0x180086dbb  cmovz   ecx, edx
0x180086dbe  mov     edx, ecx
0x180086dc0  bts     edx, 1Dh
0x180086dc4  test    r9b, r8b
0x180086dc7  cmovz   edx, ecx
0x180086dca  mov     r10d, 1000h
0x180086dd0  mov     esi, edx
0x180086dd2  bts     esi, 1Bh
0x180086dd6  test    [rsp+258h+var_1F0], r10d
0x180086ddb  cmovz   esi, edx
0x180086dde  mov     rcx, gs:60h
0x180086de7  cmp     qword ptr [rsp+258h+var_138+8], rdi
0x180086def  jnz     short loc_180086E00
0x180086df1  mov     rax, [rcx+0C8h]
0x180086df8  mov     qword ptr [rsp+258h+var_138+8], rax
0x180086e00  cmp     qword ptr [rsp+258h+var_128], rdi
0x180086e08  jnz     short loc_180086E19
0x180086e0a  mov     rax, [rcx+0D0h]
0x180086e11  mov     qword ptr [rsp+258h+var_128], rax
0x180086e19  cmp     qword ptr [rsp+258h+var_128+8], rdi
0x180086e21  jz      loc_1800874D8
0x180086e27  cmp     qword ptr [rsp+258h+var_118], rdi
0x180086e2f  jz      loc_18008758E
0x180086e35  mov     rax, cs:qword_1801C66F0
0x180086e3c  test    rax, rax
0x180086e3f  jz      loc_1800874FF
0x180086e45  cmp     qword ptr [rsp+258h+var_118+8], rdi
0x180086e4d  jz      loc_180087999
0x180086e53  mov     rcx, qword ptr [rsp+258h+var_108]
0x180086e5b  lea     rax, [rcx-1]
0x180086e5f  mov     edx, 0FF000h
0x180086e64  cmp     rax, 0FEFFFh
0x180086e6a  cmova   rcx, rdx
0x180086e6e  mov     qword ptr [rsp+258h+var_108], rcx
0x180086e76  mov     r9, [rsp+258h+var_1D0]
0x180086e7e  test    r9, r9
0x180086e81  jnz     loc_1800874EC
0x180086e87  mov     r9d, 2000h
0x180086e8d  mov     [rsp+258h+var_1E8], r9
0x180086e92  mov     rax, [rsp+258h+var_1E0]
0x180086e97  test    rax, rax
0x180086e9a  jnz     loc_1800874C5
0x180086ea0  lea     r8, [r9+0FFFFh]
0x180086ea7  and     r8, 0FFFFFFFFFFFF0000h
0x180086eae  mov     [rsp+258h+var_1F8], r8
0x180086eb3  cmp     r9, r8
0x180086eb6  ja      loc_180087BB0
0x180086ebc  mov     rcx, r9
0x180086ebf  mov     r14, [rsp+258h+var_208]
0x180086ec4  test    sil, 2
0x180086ec8  jz      short loc_180086ED3
0x180086eca  test    r14, r14
0x180086ecd  jz      loc_180087905
0x180086ed3  mov     r15d, edi
0x180086ed6  mov     [rsp+258h+var_1F0], edi
0x180086eda  mov     [rsp+258h+var_1A8], rdi
0x180086ee2  mov     rax, r8
0x180086ee5  test    rcx, rcx
0x180086ee8  jz      loc_18008747F
0x180086eee  test    rax, rax
0x180086ef1  jz      loc_18008747F
0x180086ef7  test    esi, 61000000h
0x180086efd  jnz     loc_180087BC0
0x180086f03  mov     rdx, [rsp+258h+var_210]
0x180086f08  test    r12b, sil
0x180086f0b  jz      loc_180087542
0x180086f11  test    rdx, rdx
0x180086f14  jnz     loc_180087586
0x180086f1a  mov     dword ptr [rsp+258h+var_1C8], 2C8h
0x180086f25  test    r14, r14
0x180086f28  jnz     loc_180087789
0x180086f2e  mov     [rsp+258h+var_1D0], rdi
0x180086f36  mov     [rsp+258h+var_1E0], rdi
0x180086f3b  mov     [rsp+258h+var_1B8], rdi
0x180086f43  cmp     qword ptr [rsp+258h+var_F8+8], rdi
0x180086f4b  jnz     loc_180087579
0x180086f51  mov     rax, cs:qword_1801C5F00
0x180086f58  mov     rcx, rax
0x180086f5b  shr     rcx, 0Ch
0x180086f5f  xor     rcx, rax
0x180086f62  mov     rdx, rcx
0x180086f65  shl     rdx, 19h
0x180086f69  xor     rdx, rcx
0x180086f6c  mov     rcx, rdx
0x180086f6f  shr     rcx, 1Bh
0x180086f73  xor     rcx, rdx
0x180086f76  lock cmpxchg cs:qword_1801C5F00, rcx
0x180086f7f  jnz     short loc_180086F58
0x180086f81  imul    rax, rcx, -3
0x180086f85  and     eax, 1Fh
0x180086f88  shl     rax, 10h
0x180086f8c  mov     [rsp+258h+var_1B8], rax
0x180086f94  mov     rcx, [rsp+258h+var_1F8]
0x180086f99  add     rax, rcx
0x180086f9c  mov     [rsp+258h+var_1E0], rax
0x180086fa1  cmp     rax, rcx
0x180086fa4  jb      loc_180087C93
0x180086faa  mov     eax, esi
0x180086fac  and     eax, 40000h
0x180086fb1  neg     eax
0x180086fb3  sbb     ecx, ecx
0x180086fb5  and     ecx, 3Ch
0x180086fb8  add     ecx, 4
0x180086fbb  mov     dword ptr [rsp+258h+var_230], ecx
0x180086fbf  mov     dword ptr [rsp+258h+var_238], 2000h
0x180086fc7  lea     r9, [rsp+258h+var_1E0]
0x180086fcc  xor     r8d, r8d
0x180086fcf  lea     rdx, [rsp+258h+var_1D0]
0x180086fd7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180086fdb  call    ZwAllocateVirtualMemory
0x180086fe0  test    eax, eax
0x180086fe2  js      loc_180087C81
0x180086fe8  mov     r14, [rsp+258h+var_1D0]
0x180086ff0  mov     rbx, r14
0x180086ff3  mov     [rsp+258h+var_218], rbx
0x180086ff8  mov     rax, [rsp+258h+var_1E0]
0x180086ffd  mov     [rsp+258h+var_1F8], rax
0x180087002  cmp     [rsp+258h+var_1B8], rdi
0x18008700a  jz      short loc_180087051
0x18008700c  mov     r9d, 8000h
0x180087012  lea     r8, [rsp+258h+var_1B8]
0x18008701a  lea     rdx, [rsp+258h+var_1D0]
0x180087022  call    RtlpSecMemFreeVirtualMemory
0x180087027  mov     r14, [rsp+258h+var_1D0]
0x18008702f  add     r14, [rsp+258h+var_1B8]
0x180087037  mov     rbx, r14
0x18008703a  mov     [rsp+258h+var_218], rbx
0x18008703f  mov     rax, [rsp+258h+var_1E0]
0x180087044  sub     rax, [rsp+258h+var_1B8]
0x18008704c  mov     [rsp+258h+var_1F8], rax
0x180087051  mov     rcx, rbx
0x180087054  mov     [rsp+258h+var_1D8], rbx
0x18008705c  mov     r13d, 3
0x180087062  cmp     rcx, r14
0x180087065  jz      loc_180087618
0x18008706b  mov     r15d, 7FFE0380h
0x180087071  add     rbx, 2C8h
0x180087078  mov     rax, gs:60h
0x180087081  test    dword ptr [rax+0BCh], 800h
0x18008708b  jnz     loc_180087CF6
0x180087091  mov     eax, dword ptr [rsp+258h+var_1C8]
0x180087098  add     eax, 0Fh
0x18008709b  and     eax, 0FFFFFFF0h
0x18008709e  mov     dword ptr [rsp+258h+var_1C8], eax
0x1800870a5  mov     ecx, eax
0x1800870a7  shr     ecx, 4
0x1800870aa  mov     rax, [rsp+258h+var_218]
0x1800870af  mov     [rax+8], cx
0x1800870b3  mov     rax, [rsp+258h+var_218]
0x1800870b8  mov     [rax+0Ah], r12b
0x1800870bc  mov     rax, [rsp+258h+var_218]
0x1800870c1  mov     [rax+0Fh], r12b
0x1800870c5  mov     rax, [rsp+258h+var_218]
0x1800870ca  mov     dword ptr [rax+98h], 0EEFFEEFFh
0x1800870d4  mov     ecx, esi
0x1800870d6  btr     ecx, 1Ch
0x1800870da  mov     rax, [rsp+258h+var_218]
0x1800870df  mov     [rax+70h], ecx
0x1800870e2  mov     rax, [rsp+258h+var_218]
0x1800870e7  mov     [rax+90h], edi
0x1800870ed  mov     rcx, [rsp+258h+var_218]
0x1800870f2  add     rcx, 238h; void *
0x1800870f9  xor     edx, edx; Val
0x1800870fb  mov     r8d, 80h; Size
0x180087101  call    memset$thunk$772440563353939046
0x180087106  mov     rcx, [rsp+258h+var_218]
0x18008710b  call    RtlpCreateHeapEncoding
0x180087110  mov     r10, [rsp+258h+var_218]
0x180087115  mov     [r10+290h], r12d
0x18008711c  mov     r9, [rsp+258h+var_218]
0x180087121  test    dword ptr [r9+70h], 8000000h
0x180087129  jnz     loc_180087D24
0x18008712f  mov     eax, esi
0x180087131  and     eax, 6001007Dh
0x180087136  mov     [r9+74h], eax
0x18008713a  movzx   ecx, bx
0x18008713d  mov     rax, [rsp+258h+var_218]
0x180087142  sub     cx, ax
0x180087145  mov     [rax+0D2h], cx
0x18008714c  mov     rax, [rsp+258h+var_218]
0x180087151  mov     [rax+0D8h], rdi
0x180087158  mov     rax, [rsp+258h+var_218]
0x18008715d  add     rax, 150h
0x180087163  mov     [rax+8], rax
0x180087167  mov     [rax], rax
0x18008716a  mov     rax, [rsp+258h+var_218]
0x18008716f  add     rax, 110h
0x180087175  mov     [rax+8], rax
0x180087179  mov     [rax], rax
0x18008717c  mov     rax, [rsp+258h+var_218]
0x180087181  add     rax, 120h
0x180087187  mov     [rax+8], rax
0x18008718b  mov     [rax], rax
0x18008718e  mov     rax, [rsp+258h+var_218]
0x180087193  add     rax, 0F0h
0x180087199  mov     [rax+8], rax
0x18008719d  mov     [rax], rax
0x1800871a0  cmp     [rsp+258h+var_200], rdi
0x1800871a5  jnz     short loc_1800871B0
0x1800871a7  test    r12b, sil
0x1800871aa  jz      loc_1800878AB
  ... truncated ...
```
