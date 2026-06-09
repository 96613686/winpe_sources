# UlpSendResponseOrEntityBodyFastIo

- ea: `0x1c00b6c70`
- end: `0x1c00b82f7`
- name: `UlpSendResponseOrEntityBodyFastIo`
- size: `5767`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x1c00b6c30`
- `0x1c0115d30`

## callees

- `0x1c000aca8`
- `0x1c000ad10`
- `0x1c000f514`
- `0x1c000fc68`
- `0x1c0010ce8`
- `0x1c0017104`
- `0x1c001a4b0`
- `0x1c001a548`
- `0x1c001aff4`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c002cb04`
- `0x1c008f30c`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f4f0`
- `0x1c008f570`
- `0x1c008f680`
- `0x1c008f76c`
- `0x1c008fa08`
- `0x1c008fd84`
- `0x1c0095f3c`
- `0x1c00962b0`
- `0x1c009c1e4`
- `0x1c00b6a60`
- `0x1c00b6c70`
- `0x1c00b8300`
- `0x1c00b89b4`
- `0x1c00c0360`
- `0x1c010623c`
- `0x1c01297ac`
- `0x1c012992c`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1c00b7f34`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b7fbc`
- `ntoskrnl!KeReadStateEvent` at `0x1c00e9653`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b7f34`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b7fbc`
- `ntoskrnl!KeReadStateEvent` at `0x1c00e9653`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1c00b7413`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1c00b7413`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00b6ef2`
- `ntoskrnl!ExRaiseStatus` at `0x1c00b7434`
- `ntoskrnl!ExRaiseStatus` at `0x1c00b7434`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b6dac`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b6e9b`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b717c`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b74ef`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b6dac`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b6e9b`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b717c`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b74ef`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00b6e46`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00b6e46`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00b7973`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00b7973`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e9c66`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e9c8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e9c66`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e9c8b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00e9ab4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00e9ab4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00e9a43`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00e9a43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e9880`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e9ac0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e9880`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e9ac0`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00e9874`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00e9874`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00e9832`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00e9832`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e9819`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e9a2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e9819`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e9a2e`

## pseudocode

```c
__int64 __fastcall UlpSendResponseOrEntityBodyFastIo(
        _QWORD *a1,
        unsigned __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned __int8 a7,
        unsigned __int8 a8)
{
  signed int v11; // edi
  unsigned int v12; // r12d
  _WORD *v13; // r13
  __int64 v14; // rdx
  __int64 v15; // rsi
  unsigned int *v16; // rdx
  unsigned int v17; // r9d
  signed int ChunkInfo; // ebx
  __int64 v19; // r14
  __int64 v20; // rax
  unsigned __int8 v21; // r10
  _OWORD *v22; // r14
  _WORD *v23; // r8
  unsigned int v24; // r14d
  char *v25; // r15
  int v26; // ecx
  __int64 v27; // r15
  signed int *v28; // rcx
  char v29; // r14
  __int64 v30; // r14
  __int64 v31; // r15
  BOOLEAN v32; // al
  unsigned __int16 v33; // cx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  BOOLEAN v37; // al
  __int64 v38; // r9
  int v39; // ecx
  void *v40; // rcx
  unsigned __int16 v41; // bx
  _WORD *PoolWithTagPriority; // rax
  _WORD *v43; // r14
  __int64 v44; // rcx
  unsigned __int16 v45; // r8
  _WORD *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rax
  _DWORD *v49; // rcx
  unsigned __int64 v50; // r15
  _DWORD *v51; // rcx
  unsigned __int8 v52; // r14
  __int64 v54; // rbx
  __int64 ObjectFromOpaqueId; // rax
  _OWORD *v56; // r8
  int v57; // r15d
  __int64 v58; // rcx
  int v59; // ebx
  __int64 v60; // r9
  __int64 v61; // r14
  LONG StateEvent; // eax
  unsigned int v63; // ecx
  unsigned int v64; // r15d
  LONG v65; // eax
  unsigned int v66; // ecx
  bool v67; // r9
  bool v68; // zf
  char v69; // r14
  signed __int32 v70; // eax
  signed __int32 v71; // eax
  __int64 v72; // r14
  __int64 v73; // r9
  __int64 v74; // r8
  __int64 v75; // r8
  UCHAR v76; // al
  char v77; // r10
  char v78; // r11
  const char *v79; // rcx
  char v80; // r9
  __int16 v81; // ax
  bool v82; // r14
  __int64 v83; // rax
  signed __int32 v84; // eax
  signed __int32 v85; // eax
  __int64 v86; // rbx
  __int64 v87; // r8
  __int64 v88; // r8
  UCHAR v89; // al
  unsigned __int8 v90; // r10
  char v91; // r9
  __int64 v92; // rcx
  __int64 *v93; // [rsp+20h] [rbp-488h]
  unsigned int v94; // [rsp+70h] [rbp-438h]
  BOOLEAN v95; // [rsp+74h] [rbp-434h]
  bool v96; // [rsp+74h] [rbp-434h]
  unsigned __int8 v97; // [rsp+7Ch] [rbp-42Ch]
  _OWORD *v98; // [rsp+98h] [rbp-410h]
  unsigned int v99; // [rsp+A0h] [rbp-408h] BYREF
  char v100; // [rsp+A4h] [rbp-404h] BYREF
  char v101; // [rsp+A5h] [rbp-403h] BYREF
  char v102; // [rsp+A6h] [rbp-402h] BYREF
  unsigned int v103; // [rsp+A8h] [rbp-400h]
  __int16 v104; // [rsp+B0h] [rbp-3F8h]
  _WORD *v105; // [rsp+B8h] [rbp-3F0h]
  unsigned __int16 v106; // [rsp+C0h] [rbp-3E8h]
  __int64 v107; // [rsp+C8h] [rbp-3E0h] BYREF
  __int64 v108; // [rsp+D0h] [rbp-3D8h]
  PVOID v109; // [rsp+D8h] [rbp-3D0h] BYREF
  int v110; // [rsp+E0h] [rbp-3C8h]
  int v111; // [rsp+E4h] [rbp-3C4h]
  unsigned int v112; // [rsp+E8h] [rbp-3C0h]
  unsigned int v113; // [rsp+ECh] [rbp-3BCh] BYREF
  int v114; // [rsp+F0h] [rbp-3B8h]
  __int128 v115; // [rsp+F8h] [rbp-3B0h]
  __int128 v116; // [rsp+108h] [rbp-3A0h]
  __int128 v117; // [rsp+118h] [rbp-390h]
  _OWORD *v118; // [rsp+128h] [rbp-380h]
  PVOID P; // [rsp+130h] [rbp-378h] BYREF
  int v120; // [rsp+138h] [rbp-370h]
  __int64 v121; // [rsp+140h] [rbp-368h]
  _WORD *v122; // [rsp+148h] [rbp-360h]
  unsigned __int64 v123; // [rsp+150h] [rbp-358h]
  _DWORD *v124; // [rsp+158h] [rbp-350h]
  __int64 v125; // [rsp+160h] [rbp-348h]
  int v126; // [rsp+168h] [rbp-340h]
  char *v127; // [rsp+170h] [rbp-338h]
  unsigned int *v128; // [rsp+178h] [rbp-330h]
  _WORD *v129; // [rsp+180h] [rbp-328h]
  unsigned int *v130; // [rsp+188h] [rbp-320h]
  _OWORD v131[9]; // [rsp+190h] [rbp-318h] BYREF
  __int64 v132; // [rsp+220h] [rbp-288h]
  size_t Size; // [rsp+228h] [rbp-280h]
  __int64 v134; // [rsp+238h] [rbp-270h]
  __int128 v135; // [rsp+240h] [rbp-268h]
  __int128 v136; // [rsp+250h] [rbp-258h]
  __int128 v137; // [rsp+260h] [rbp-248h]
  __int128 v138; // [rsp+270h] [rbp-238h]
  __int64 v139; // [rsp+280h] [rbp-228h]
  __int128 v140; // [rsp+290h] [rbp-218h] BYREF
  __int128 v141; // [rsp+2A0h] [rbp-208h] BYREF
  __int128 v142; // [rsp+2B0h] [rbp-1F8h] BYREF
  __int128 v143; // [rsp+2C0h] [rbp-1E8h] BYREF
  _QWORD v144[3]; // [rsp+2D0h] [rbp-1D8h] BYREF
  char v145; // [rsp+2E8h] [rbp-1C0h]
  int v146; // [rsp+2E9h] [rbp-1BFh]
  __int16 v147; // [rsp+2EDh] [rbp-1BBh]
  char v148; // [rsp+2EFh] [rbp-1B9h]
  _QWORD v149[3]; // [rsp+2F0h] [rbp-1B8h] BYREF
  char v150; // [rsp+308h] [rbp-1A0h]
  int v151; // [rsp+309h] [rbp-19Fh]
  __int16 v152; // [rsp+30Dh] [rbp-19Bh]
  char v153; // [rsp+30Fh] [rbp-199h]
  __int128 v154; // [rsp+310h] [rbp-198h] BYREF
  char v155[320]; // [rsp+320h] [rbp-188h] BYREF

  v125 = a4;
  LODWORD(v108) = a3;
  v134 = a4;
  v11 = 0;
  v94 = 0;
  v99 = 0;
  v130 = 0;
  v154 = 0;
  v113 = 0;
  v109 = 0;
  v132 = 0;
  P = 0;
  v102 = 0;
  LOBYTE(v12) = 0;
  v103 = 0;
  v13 = 0;
  v105 = 0;
  v97 = 0;
  memset(v131, 0, sizeof(v131));
  LODWORD(v98) = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v107 = 0;
  v15 = 0;
  v104 = 0;
  v101 = 0;
  v114 = 0;
  v100 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    LODWORD(v93) = a3;
    WPP_SF_qqLqLqll((unsigned int)(char)a8, v14, a1, a2);
  }
  v95 = IoIs32bitProcess(0);
  *(_QWORD *)(a6 + 8) = 0;
  ChunkInfo = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    v93 = &v107;
    WPP_SF_qdP(12, WPP_18ca8755388c316524f95a91261e2540_Traceguids, a1, 1);
  }
  v107 = 0;
  if ( *(PDEVICE_OBJECT *)(a1[1] + 8LL) == UxDriverObject && a1[4] == 1347440705 )
  {
    v19 = a1[3];
    if ( v19
      && *(_DWORD *)(v19 + 24) == 1346464853
      && (v20 = *(_QWORD *)(v19 + 8)) != 0
      && *(_DWORD *)(v20 + 120) == 1329687637 )
    {
      if ( (*(_DWORD *)(v19 + 40) & 1) != 0 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v19 + 8) + 320LL) == PsGetCurrentServerSilo() )
          v107 = v19;
        else
          ChunkInfo = -1073740700;
      }
      else
      {
        ChunkInfo = -1073741637;
      }
    }
    else
    {
      ChunkInfo = -1073741811;
    }
  }
  else
  {
    ChunkInfo = -1073741808;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qD(13, WPP_18ca8755388c316524f95a91261e2540_Traceguids, v107, (unsigned int)ChunkInfo);
  if ( ChunkInfo < 0 )
    goto LABEL_226;
  ChunkInfo = 0;
  v110 = 0;
  if ( !a2 )
  {
    ChunkInfo = -1073741811;
    v110 = -1073741811;
    if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
      goto LABEL_71;
    v36 = 11;
    goto LABEL_70;
  }
  if ( IoIs32bitProcess(0) )
  {
    if ( (unsigned int)v108 >= 0x28 )
    {
      UlProbeForRead(a2, 40, 4, a8);
      *(_QWORD *)&v115 = *(unsigned int *)a2;
      *(_QWORD *)&v116 = *(unsigned int *)(a2 + 8);
      WORD4(v115) = *(_WORD *)(a2 + 4);
      *((_QWORD *)&v116 + 1) = *(_QWORD *)(a2 + 12);
      *(_QWORD *)&v117 = *(_QWORD *)(a2 + 24);
      DWORD2(v117) = *(_DWORD *)(a2 + 32);
      v22 = (_OWORD *)*(unsigned int *)(a2 + 36);
      v118 = v22;
      v21 = a8;
LABEL_27:
      LODWORD(v98) = (_DWORD)v22;
      goto LABEL_28;
    }
    ChunkInfo = -1073741789;
    v110 = -1073741789;
    if ( (WPP_MAIN_CB.StackSize & 0x20) == 0 )
      goto LABEL_71;
    v36 = 12;
LABEL_70:
    WPP_SF_D(v36, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
    goto LABEL_71;
  }
  if ( (unsigned int)v108 >= 0x38 )
  {
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
    {
      LODWORD(v93) = 8;
      WPP_SF_PqLc(10, v16, 56, a2);
    }
    v21 = a8;
    if ( a8 )
    {
      if ( (a2 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      LODWORD(v16) = MmUserProbeAddress;
      if ( a2 + 56 > MmUserProbeAddress || a2 + 56 < a2 )
        *(_BYTE *)MmUserProbeAddress = 0;
    }
    else if ( (a2 & 7) != 0 )
    {
      ExRaiseStatus(-1073741115);
    }
    v115 = *(_OWORD *)a2;
    v116 = *(_OWORD *)(a2 + 16);
    v117 = *(_OWORD *)(a2 + 32);
    v118 = *(_OWORD **)(a2 + 48);
    v22 = v118;
    goto LABEL_27;
  }
  ChunkInfo = -1073741789;
  v110 = -1073741789;
  if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
  {
    v36 = 13;
    goto LABEL_70;
  }
LABEL_71:
  v22 = 0;
  v21 = a8;
LABEL_28:
  if ( ChunkInfo < 0 )
  {
    v27 = a6;
    v28 = (signed int *)a6;
    v29 = 0;
    goto LABEL_140;
  }
  v106 = WORD4(v115);
  v12 = DWORD2(v117);
  v103 = DWORD2(v117);
  v139 = v117;
  v132 = *((_QWORD *)&v116 + 1);
  if ( WORD4(v115) >= 0x2710u )
  {
    ChunkInfo = -1073741811;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(37, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids);
    v27 = a6;
    v28 = (signed int *)a6;
    v29 = 0;
  }
  else
  {
    if ( (DWORD2(v117) & 0xFFFFFE00) != 0 || (LODWORD(v16) = a7, (BYTE8(v117) & 0x10) != 0) && !a7 )
    {
      ChunkInfo = -1073741811;
      if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
        WPP_SF_D(38, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids);
      v27 = a6;
      v28 = (signed int *)a6;
      v29 = 0;
      goto LABEL_140;
    }
    ChunkInfo = 0;
    v120 = 0;
    if ( v22 && v21 == 1 )
    {
      v37 = IoIs32bitProcess(0);
      LOBYTE(v38) = 1;
      if ( v37 )
      {
        UlProbeForRead(v22, 92, 4, v38);
        v39 = *(_DWORD *)v22;
        v131[0] = *v22;
        *(_QWORD *)&v131[1] = *((_QWORD *)v22 + 2);
        DWORD2(v131[1]) = *((_DWORD *)v22 + 6);
        *(_QWORD *)&v131[2] = *((unsigned int *)v22 + 7);
        *((_QWORD *)&v131[2] + 1) = *((unsigned int *)v22 + 8);
        *(_QWORD *)&v131[3] = *((unsigned int *)v22 + 9);
        *((_QWORD *)&v131[3] + 1) = *((unsigned int *)v22 + 10);
        *(_QWORD *)&v131[4] = *((unsigned int *)v22 + 11);
        *((_QWORD *)&v131[4] + 1) = *((unsigned int *)v22 + 12);
        *(_QWORD *)&v131[5] = *((unsigned int *)v22 + 13);
        *((_QWORD *)&v131[5] + 1) = *((unsigned int *)v22 + 14);
        *(_QWORD *)&v131[6] = *((unsigned int *)v22 + 15);
        *((_QWORD *)&v131[6] + 1) = *((unsigned int *)v22 + 16);
        *(_QWORD *)&v131[7] = *((unsigned int *)v22 + 17);
        *((_QWORD *)&v131[7] + 1) = *((unsigned int *)v22 + 18);
        LODWORD(v131[8]) = *((_DWORD *)v22 + 19);
        *(_QWORD *)((char *)&v131[8] + 4) = *((_QWORD *)v22 + 10);
        WORD6(v131[8]) = *((_WORD *)v22 + 44);
      }
      else
      {
        UlProbeForRead(v22, 144, 8, v38);
        v131[0] = *v22;
        v131[1] = v22[1];
        v131[2] = v22[2];
        v131[3] = v22[3];
        v131[4] = v22[4];
        v131[5] = v22[5];
        v131[6] = v22[6];
        v131[7] = v22[7];
        v131[8] = v22[8];
        v39 = v131[0];
      }
      if ( v39 )
      {
        ChunkInfo = -1073741811;
        v120 = -1073741811;
        if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
          WPP_SF_D(14, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
      }
      else
      {
        v98 = v131;
        v118 = v131;
      }
      LODWORD(v16) = a7;
      v21 = a8;
    }
    if ( ChunkInfo < 0 )
    {
      v27 = a6;
      v28 = (signed int *)a6;
      v29 = 0;
      goto LABEL_140;
    }
    if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v107 + 8) + 328LL) + 1088LL) && !(_BYTE)v16 && DWORD2(v116)
      || (BYTE8(v117) & 0x20) != 0
      || WORD4(v115) > 0xAu && v21 == 1 )
    {
      ChunkInfo = -1073741822;
      v27 = a6;
      v28 = (signed int *)a6;
      v29 = 0;
      goto LABEL_140;
    }
    LODWORD(v23) = WORD4(v115);
    if ( WORD4(v115) )
    {
      ChunkInfo = UlpGetChunkInfo(0, (int)v93, v155, (__int64)&P, (__int64)&v102);
      if ( ChunkInfo < 0 )
      {
        v27 = a6;
        v28 = (signed int *)a6;
        v29 = 0;
        goto LABEL_140;
      }
      v108 = v107;
      v127 = 0;
      v109 = 0;
      v17 = 0;
      v94 = 0;
      v99 = 0;
      v24 = 0;
      v112 = 0;
      v25 = (char *)P;
      LODWORD(v23) = -1;
      while ( 1 )
      {
        v127 = v25;
        if ( v24 >= v106 )
          break;
        LODWORD(v16) = *((_DWORD *)v25 + 4);
        v26 = *(_DWORD *)v25;
        if ( (unsigned int)(*(_DWORD *)v25 - 2) <= 1 )
        {
          if ( v109 )
          {
            ChunkInfo = -1073741822;
            goto LABEL_46;
          }
          if ( v26 == 2 )
          {
            v40 = (void *)*((_QWORD *)v25 + 2);
            *(_QWORD *)&v154 = 0;
            *((_QWORD *)&v154 + 1) = -1;
          }
          else
          {
            v40 = (void *)*((_QWORD *)v25 + 3);
            v154 = *(_OWORD *)(v25 + 8);
          }
          ChunkInfo = UlCheckoutFragmentCacheEntry(v40, a8, (__int64)&v109);
          if ( ChunkInfo < 0 )
            goto LABEL_46;
          v17 = v94;
          LODWORD(v23) = -1;
        }
        else
        {
          if ( v26 || v17 > ~(_DWORD)v16 )
            goto LABEL_45;
          v17 += (unsigned int)v16;
          v94 = v17;
          v99 = v17;
        }
        v112 = ++v24;
        v25 += 32;
      }
      if ( v17 > 0x800 && ((v12 & 4) == 0 || v109) )
      {
LABEL_45:
        ChunkInfo = -1073741637;
LABEL_46:
        v27 = a6;
        v28 = (signed int *)a6;
        v29 = 0;
        goto LABEL_140;
      }
      LODWORD(v16) = a7;
    }
    if ( (_BYTE)v16 )
    {
      v13 = 0;
      v105 = 0;
      goto LABEL_154;
    }
    v30 = *(_QWORD *)(v107 + 8);
    ChunkInfo = 0;
    v111 = 0;
    v97 = 0;
    v31 = v115;
    if ( (_QWORD)v115 )
    {
      v32 = IoIs32bitProcess(0);
      v33 = *(_WORD *)(v30 + 276);
      if ( v32 )
      {
        v41 = 0;
        if ( v33 < 2u )
        {
          UlProbeForRead(v31, 280, 4, a8);
        }
        else
        {
          UlProbeForRead(v31, 288, 4, a8);
          v41 = *(_WORD *)(v31 + 280);
        }
        LOWORD(v108) = *(_WORD *)(v31 + 16);
        Size = ((24LL * (unsigned __int16)v108 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 568 + 16LL * v41;
        PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, Size, 0x53486C55u, LowPoolPriority);
        v43 = PoolWithTagPriority;
        if ( PoolWithTagPriority )
        {
          v13 = PoolWithTagPriority;
          v105 = PoolWithTagPriority;
          v97 = 1;
          memset(PoolWithTagPriority, 0, Size);
          v16 = (unsigned int *)(unsigned __int16)v108;
          v43[12] = v108;
          v43[276] = v41;
          ChunkInfo = 0;
          v126 = 0;
          v121 = 0;
          v122 = 0;
          v128 = 0;
          v129 = 0;
          v124 = 0;
          v123 = 0;
          *(_DWORD *)v43 = *(_DWORD *)v31;
          *((_DWORD *)v43 + 1) = *(_DWORD *)(v31 + 4);
          v43[4] = *(_WORD *)(v31 + 8);
          v43[5] = *(_WORD *)(v31 + 10);
          *((_QWORD *)v43 + 2) = *(unsigned int *)(v31 + 12);
          v43[268] = *(_WORD *)(v31 + 272);
          *((_QWORD *)v43 + 68) = *(unsigned int *)(v31 + 276);
          if ( *(_WORD *)(v31 + 24) || *(_DWORD *)(v31 + 28) )
          {
            ChunkInfo = -1073741811;
            v126 = -1073741811;
            if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
              WPP_SF_D(15, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
          }
          else
          {
            v44 = *(unsigned int *)(v31 + 20);
            v121 = v44;
            v122 = v43 + 284;
            *((_QWORD *)v43 + 4) = v43 + 284;
            UlProbeForRead(v44, 12LL * (_QWORD)v16, 4, a8);
            v45 = 0;
            v46 = v122;
            v47 = v121;
            while ( v45 < v43[12] )
            {
              *v46 = *(_WORD *)v47;
              *((_QWORD *)v46 + 1) = *(unsigned int *)(v47 + 4);
              v46[1] = *(_WORD *)(v47 + 2);
              *((_QWORD *)v46 + 2) = *(unsigned int *)(v47 + 8);
              ++v45;
              v47 += 12;
              v121 = v47;
              v46 += 12;
              v122 = v46;
            }
            v16 = (unsigned int *)(v31 + 32);
            v23 = v43 + 28;
            v17 = 0;
            while ( 1 )
            {
              v129 = v23;
              v128 = v16;
              if ( (unsigned __int16)v17 >= 0x1Eu )
                break;
              *v23 = *(_WORD *)v16;
              *((_QWORD *)v23 + 1) = v16[1];
              LOWORD(v17) = v17 + 1;
              v16 += 2;
              v23 += 8;
            }
            v123 = ((unsigned __int64)v46 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
            v48 = (unsigned __int16)v43[276];
            if ( (_WORD)v48 )
            {
              v49 = (_DWORD *)*(unsigned int *)(v31 + 284);
              v124 = v49;
              v50 = v123;
              *((_QWORD *)v43 + 70) = v123;
              UlProbeForRead(v49, 12 * v48, 4, a8);
              LODWORD(v16) = 0;
              v51 = v124;
              while ( (unsigned __int16)v16 < v43[276] )
              {
                *(_DWORD *)v50 = *v51;
                *(_DWORD *)(v50 + 4) = v51[1];
                *(_QWORD *)(v50 + 8) = (unsigned int)v51[2];
                LOWORD(v16) = (_WORD)v16 + 1;
                v50 += 16LL;
                v123 = v50;
                v51 += 3;
                v124 = v51;
              }
            }
          }
          v111 = ChunkInfo;
        }
        else
        {
          ChunkInfo = -1073741801;
          v111 = -1073741801;
          if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
            WPP_SF_D(17, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
        }
      }
      else
      {
        if ( v33 < 2u )
          v34 = 552;
        else
          v34 = 568;
        UlProbeForRead(v31, v34, 8, a8);
        v13 = (_WORD *)v31;
        v105 = (_WORD *)v31;
      }
    }
    else
    {
      ChunkInfo = -1073741811;
      v111 = -1073741811;
      if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
        WPP_SF_D(16, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
    }
    if ( ChunkInfo < 0 )
    {
      v27 = a6;
      v28 = (signed int *)a6;
      v29 = 0;
      goto LABEL_140;
    }
    v104 = v13[4];
    v35 = *(_QWORD *)(v107 + 8);
    if ( *(_WORD *)(v35 + 276) < 2u )
      goto LABEL_154;
    ChunkInfo = UlFlCaptureFlowRateInfo(*(_QWORD *)(v35 + 328), (_DWORD)v13, 0, 0, v97, v95, (__int64)&v100);
    if ( ChunkInfo < 0 )
    {
      v27 = a6;
      v28 = (signed int *)a6;
      v29 = 0;
      goto LABEL_140;
    }
    if ( !v100 )
    {
LABEL_154:
      v54 = v107;
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
        WPP_SF_qq(10, WPP_113f5b8b44003c935cfae087381f34ee_Traceguids, v117, v107);
      ObjectFromOpaqueId = UxGetObjectFromOpaqueIdEx(v117, (_DWORD)v16, (_DWORD)v23, v17, (_DWORD)v93, v54);
      v15 = ObjectFromOpaqueId;
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
      {
        if ( ObjectFromOpaqueId )
          v73 = *(_QWORD *)(ObjectFromOpaqueId + 64);
        else
          v73 = 0;
        WPP_SF_qq(11, WPP_113f5b8b44003c935cfae087381f34ee_Traceguids, ObjectFromOpaqueId, v73);
      }
      if ( v15 )
      {
        v57 = v12 & 2;
        LODWORD(v108) = v57;
        if ( (v12 & 2) != 0 )
        {
          v16 = 0;
        }
        else
        {
          v58 = *(_QWORD *)(*(_QWORD *)(v15 + 24) + 960LL);
          if ( *(_BYTE *)(v58 + 1568) )
          {
            v146 = 0;
            v147 = 0;
            v148 = 0;
            v144[2] = v58;
            v144[0] = v15 + 72;
            v144[1] = 0;
            v145 = 0;
            McTemplateK0p_UlEtwWriteEventWrapper(v58, HTTP_EVENT_RECEIVE_FAST_RESPONSE_FROM_USERMODE_LEGACY, v144);
          }
          if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
            WPP_SF_q(40, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids, *(_QWORD *)(v15 + 56));
          v16 = &v99;
          v130 = &v99;
        }
        v59 = *(_DWORD *)(*(_QWORD *)(v107 + 8) + 276LL);
        v114 = v59;
        v60 = v94;
        if ( v94 || v109 )
        {
          v61 = *(_QWORD *)(v15 + 24);
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 848) + 960LL) + 4172LL) == -1 )
          {
            StateEvent = KeReadStateEvent(UxHighNonPagedPoolEvent);
            v63 = *(_DWORD *)(v61 + 856);
            v64 = 0x10000;
            if ( StateEvent )
            {
              LODWORD(v16) = 2 * v63;
            }
            else
            {
              LODWORD(v16) = 0x10000;
              if ( v63 < 0x10000 )
                LODWORD(v16) = *(_DWORD *)(v61 + 856);
            }
            if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 848) + 960LL) + 4176LL) <= (unsigned int)v16 )
            {
              v64 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 848) + 960LL) + 4176LL);
            }
            else
            {
              v65 = KeReadStateEvent(UxHighNonPagedPoolEvent);
              v66 = *(_DWORD *)(v61 + 856);
              if ( v65 )
              {
                v64 = 2 * v66;
              }
              else if ( v66 < 0x10000 )
              {
                v64 = *(_DWORD *)(v61 + 856);
              }
            }
          }
          else if ( KeReadStateEvent(UxHighNonPagedPoolEvent) )
          {
            v64 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v61 + 848) + 960LL) + 4172LL);
          }
          else
          {
            v64 = 0x10000;
          }
          v67 = (unsigned int)(*(_DWORD *)(v61 + 872) + *(_DWORD *)(v61 + 896)) < 0x40
             && *(_QWORD *)(v61 + 864) + *(_QWORD *)(v61 + 904) < (unsigned __int64)v64;
          v96 = v67;
          if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x1000000) != 0 )
          {
            v74 = *(_QWORD *)(v61 + 848);
            v135 = (unsigned __int64)(v74 + 316);
            WORD4(v135) = SOCKADDR_SIZE(*(_WORD *)(v74 + 316));
            v140 = v135;
            v136 = (unsigned __int64)(v75 + 288);
            v76 = SOCKADDR_SIZE(*(_WORD *)(v75 + 288));
            WORD4(v136) = v76;
            v141 = v136;
            v79 = "ok";
            if ( !v80 )
              v79 = "no";
            WPP_SF__SOCKADDR__SOCKADDR_sLLIIL(
              (_DWORD)v79,
              v76,
              (unsigned int)&v141,
              (unsigned int)&v140,
              (__int64)v79,
              v78,
              v77,
              *(_QWORD *)(v61 + 864),
              *(_QWORD *)(v61 + 904),
              v64);
            v67 = v96;
          }
          v68 = !v67;
          v60 = v94;
          if ( v68 )
          {
            ChunkInfo = -1073741756;
            goto LABEL_226;
          }
          v57 = v108;
          v16 = v130;
        }
        if ( *(_DWORD *)(v15 + 2192) != 1 )
        {
          if ( v13 )
          {
            if ( (!v16 || *v16 > 0x800 || (*(_DWORD *)(v15 + 2184) & 0x8000) != 0)
              && *(_QWORD *)(v15 + 2472)
              && (v12 & 0x10) == 0
              && (v12 & 0x40) == 0
              && ((unsigned __int16)v59 < 2u || !v13[276]) )
            {
              v81 = v13[4];
              if ( (v81 == 200 || v81 == 206) && *(_DWORD *)(v15 + 2660) <= 1u )
              {
                ChunkInfo = -1073741822;
                goto LABEL_226;
              }
            }
          }
          else if ( (_DWORD)v60 && *(_QWORD *)(v15 + 2472) )
          {
            v82 = 0;
            KeEnterCriticalRegion();
            ExAcquirePushLockSharedEx(*(_QWORD *)(v15 + 24) + 464LL, 0);
            v83 = *(_QWORD *)(v15 + 2496);
            if ( v83 && !*(_DWORD *)(v83 + 136) )
              v82 = *(_DWORD *)(v83 + 256) == 1;
            ExReleasePushLockSharedEx(*(_QWORD *)(v15 + 24) + 464LL, 0);
            KeLeaveCriticalRegion();
            v60 = v94;
            if ( v82 )
            {
              ChunkInfo = -1073741822;
              goto LABEL_226;
            }
          }
          if ( v13 )
          {
            if ( (unsigned __int16)v59 >= 2u && v13[276] )
            {
              ChunkInfo = UlExtractAndAppendAuthenticationResponseInfo(v15, (__int64)v13, 0, a8, 0, &v101);
              v60 = v94;
              if ( ChunkInfo < 0 )
              {
                v29 = 1;
                goto LABEL_227;
              }
              if ( v101 )
              {
                ChunkInfo = -1073741822;
                goto LABEL_226;
              }
            }
            v69 = 1;
          }
          else
          {
            v69 = 0;
          }
          if ( v69 )
          {
            v70 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 2200), 1, 0);
            v12 = v103;
            v13 = v105;
            LODWORD(v16) = (_DWORD)v118;
            v94 = v99;
            LODWORD(v98) = (_DWORD)v118;
            if ( v70 == 1 )
            {
              ChunkInfo = -1073741436;
              goto LABEL_203;
            }
            *(_WORD *)(v15 + 1674) = v104;
            goto LABEL_196;
          }
          if ( !*(_DWORD *)(v15 + 2200) )
          {
            if ( (v12 & 0x10) != 0 )
            {
              ChunkInfo = UlCheckRawResponseCompatibility(v15, v16, v56, v60);
              if ( ChunkInfo >= 0 )
              {
                v84 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 2200), 1, 0);
                v12 = v103;
                v13 = v105;
                LODWORD(v16) = (_DWORD)v118;
                v94 = v99;
                LODWORD(v98) = (_DWORD)v118;
                if ( v84 == 1 )
                {
                  ChunkInfo = -1073741436;
                  goto LABEL_203;
                }
                goto LABEL_196;
              }
            }
            else
            {
              ChunkInfo = -1073741436;
            }
LABEL_202:
            LODWORD(v16) = (_DWORD)v98;
LABEL_203:
            if ( ChunkInfo < 0 )
            {
              v29 = 1;
              goto LABEL_227;
            }
            v72 = *(_QWORD *)(v15 + 24);
            ChunkInfo = 0;
            if ( v57 )
            {
              ChunkInfo = *(_DWORD *)(v72 + 416) != 0 ? 0xC000023A : 0;
            }
            else
            {
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 2208), 1, 0) == 1 )
              {
                KeEnterCriticalRegion();
                ExAcquirePushLockExclusiveEx(v72 + 464, 0);
                if ( *(_DWORD *)(v72 + 416) )
                {
                  v85 = _InterlockedCompareExchange((volatile signed __int32 *)(v72 + 448), 1, 0);
                  LODWORD(v98) = (_DWORD)v118;
                  if ( v85 == 1 )
                    ChunkInfo = -1073741254;
                  else
                    ChunkInfo = UlLogZombieConnection(v15, v72, v118, a8);
                }
                else
                {
                  LODWORD(v98) = (_DWORD)v118;
                }
                ExReleasePushLockExclusiveEx(v72 + 464, 0);
                KeLeaveCriticalRegion();
                LODWORD(v16) = (_DWORD)v98;
              }
              else
              {
                LODWORD(v16) = (_DWORD)v118;
                LODWORD(v98) = (_DWORD)v118;
              }
              v13 = v105;
              v12 = v103;
              v94 = v99;
            }
            if ( ChunkInfo >= 0 )
            {
              if ( (v12 & 0x100) != 0 )
              {
                v86 = *(_QWORD *)(v15 + 24);
                if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                  WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v86 + 384, 47, 0, 0, 0, 0);
                ChunkInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(v86 + 392) + 120LL))(
                              *(_QWORD *)(v86 + 384),
                              47,
                              0);
                if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
                  WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
                if ( ChunkInfo < 0 )
                {
                  v29 = 1;
                  goto LABEL_227;
                }
                LODWORD(v16) = (_DWORD)v98;
              }
              ChunkInfo = UlFastSendHttpResponse(
                            (_DWORD)v13,
                            (_DWORD)v16,
                            (_DWORD)P,
                            v106,
                            v94,
                            (__int64)v109,
                            (__int64)&v154,
                            v12,
                            v15,
                            *(_DWORD *)(*(_QWORD *)(v107 + 8) + 276LL),
                            0,
                            a8,
                            (__int64)&v113);
              v27 = a6;
              v28 = (signed int *)a6;
              if ( ChunkInfo < 0 )
              {
                v29 = 1;
              }
              else
              {
                *(_QWORD *)(a6 + 8) = v113;
                v109 = 0;
                v29 = 0;
              }
              goto LABEL_140;
            }
            goto LABEL_226;
          }
          LODWORD(v16) = (_DWORD)v98;
LABEL_196:
          if ( v57 )
          {
            if ( *(_DWORD *)(v15 + 2204) == 1 )
            {
              ChunkInfo = -1073741436;
              goto LABEL_203;
            }
          }
          else
          {
            v71 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 2204), 1, 0);
            v12 = v103;
            v13 = v105;
            if ( v71 == 1 )
            {
              ChunkInfo = -1073741436;
              v94 = v99;
              LODWORD(v16) = (_DWORD)v118;
              LODWORD(v98) = (_DWORD)v118;
              goto LABEL_203;
            }
            v94 = v99;
            v56 = v118;
            LODWORD(v98) = (_DWORD)v118;
          }
          LOBYTE(v56) = v69 == 0;
          if ( (unsigned __int8)UlCheckOpaqueSendFlags(v15, v12, v56) )
          {
            if ( (v12 & 0x100) == 0 || (ChunkInfo = -1073741811, (v12 & 1) != 0) )
              ChunkInfo = 0;
          }
          else
          {
            ChunkInfo = -1073741811;
          }
          goto LABEL_202;
        }
        ChunkInfo = -1073741822;
      }
      else
      {
        ChunkInfo = -1073741254;
      }
LABEL_226:
      v29 = 0;
LABEL_227:
      v27 = a6;
      v28 = (signed int *)a6;
      goto LABEL_140;
    }
    ChunkInfo = -1073741822;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(39, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids);
    v27 = a6;
    v28 = (signed int *)a6;
    v29 = 0;
  }
LABEL_140:
  if ( v15 && (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x8000) != 0 )
  {
    v87 = *(_QWORD *)(v15 + 24);
    v137 = (unsigned __int64)(v87 + 316);
    WORD4(v137) = SOCKADDR_SIZE(*(_WORD *)(v87 + 316));
    v142 = v137;
    v138 = (unsigned __int64)(v88 + 288);
    v89 = SOCKADDR_SIZE(*(_WORD *)(v88 + 288));
    WORD4(v138) = v89;
    v143 = v138;
    WPP_SF__SOCKADDR__SOCKADDR_LLLS(
      v90,
      v89,
      (unsigned int)&v143,
      (unsigned int)&v142,
      v90,
      v91,
      v12,
      *(_QWORD *)(v15 + 2016));
    v28 = (signed int *)a6;
  }
  if ( v102 )
  {
    ExFreePoolWithTag(P, 0);
    v28 = (signed int *)a6;
  }
  if ( v97 )
  {
    ExFreePoolWithTag(v13, 0);
    v28 = (signed int *)a6;
  }
  if ( ChunkInfo >= 0 )
  {
    v52 = 1;
  }
  else
  {
    if ( v29 )
    {
      v92 = *(_QWORD *)(*(_QWORD *)(v15 + 24) + 960LL);
      if ( *(_BYTE *)(v92 + 1568) )
      {
        v151 = 0;
        v152 = 0;
        v153 = 0;
        v149[2] = v92;
        v149[0] = v15 + 72;
        v149[1] = 0;
        v150 = 0;
        McTemplateK0xsq_UlEtwWriteEventWrapper(
          v92,
          (_DWORD)v16,
          (unsigned int)v149,
          *(_QWORD *)(v15 + 56),
          (__int64)"FastSendResponseOrEntityBodyFailed",
          ChunkInfo);
      }
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_Dq(42, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids, (unsigned int)ChunkInfo, *(_QWORD *)(v15 + 56));
      UlCloseConnection(*(_QWORD *)(v15 + 24));
      v28 = (signed int *)a6;
    }
    v52 = 0;
    v11 = ChunkInfo;
  }
  *v28 = v11;
  if ( v15 && _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 48), 0xFFFFFFFF) == 1 )
    UlpQueueFreeHttpRequest(v15);
  if ( v109 )
    UlCheckinUriCacheEntry(v109);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qqD(43, WPP_6320283b878d340a10cd9064912a2ecd_Traceguids, v125, v27, v52);
  return v52;
}

```

## disassembly

```asm
0x1c00b6c70  push    rbx
0x1c00b6c72  push    rsi
0x1c00b6c73  push    rdi
0x1c00b6c74  push    r12
0x1c00b6c76  push    r13
0x1c00b6c78  push    r14
0x1c00b6c7a  push    r15
0x1c00b6c7c  sub     rsp, 470h
0x1c00b6c83  mov     rax, cs:__security_cookie
0x1c00b6c8a  xor     rax, rsp
0x1c00b6c8d  mov     [rsp+4A8h+var_48], rax
0x1c00b6c95  mov     [rsp+4A8h+var_348], r9
0x1c00b6c9d  mov     ebx, r8d
0x1c00b6ca0  mov     dword ptr [rsp+4A8h+var_3D8], ebx
0x1c00b6ca7  mov     r15, rdx
0x1c00b6caa  mov     r14, rcx
0x1c00b6cad  mov     rax, [rsp+4A8h+arg_28]
0x1c00b6cb5  mov     [rsp+4A8h+var_428], rax
0x1c00b6cbd  mov     [rsp+4A8h+var_270], r9
0x1c00b6cc5  mov     [rsp+4A8h+var_420], rax
0x1c00b6ccd  xor     edi, edi
0x1c00b6ccf  mov     eax, edi
0x1c00b6cd1  mov     [rsp+4A8h+var_438], eax
0x1c00b6cd5  mov     [rsp+4A8h+var_408], eax
0x1c00b6cdc  mov     [rsp+4A8h+var_320], rdi
0x1c00b6ce4  xorps   xmm0, xmm0
0x1c00b6ce7  movups  [rsp+4A8h+var_198], xmm0
0x1c00b6cef  mov     [rsp+4A8h+var_3BC], edi
0x1c00b6cf6  mov     [rsp+4A8h+var_3D0], rdi
0x1c00b6cfe  mov     [rsp+4A8h+var_288], rdi
0x1c00b6d06  mov     [rsp+4A8h+P], rdi
0x1c00b6d0e  mov     byte ptr [rsp+4A8h+var_402], al
0x1c00b6d15  mov     r12d, edi
0x1c00b6d18  mov     dword ptr [rsp+4A8h+var_402+2], edi
0x1c00b6d1f  mov     r13d, edi
0x1c00b6d22  mov     [rsp+4A8h+var_3F0], rdi
0x1c00b6d2a  mov     [rsp+4A8h+var_42C], al
0x1c00b6d2e  xor     edx, edx; Val
0x1c00b6d30  mov     r8d, 90h; Size
0x1c00b6d36  lea     rcx, [rsp+4A8h+var_318]; void *
0x1c00b6d3e  call    memset
0x1c00b6d43  xorps   xmm0, xmm0
0x1c00b6d46  xor     r8d, r8d
0x1c00b6d49  mov     [rsp+4A8h+var_410], r8
0x1c00b6d51  movups  [rsp+4A8h+var_3B0], xmm0
0x1c00b6d59  movups  [rsp+4A8h+var_3A0], xmm0
0x1c00b6d61  movups  [rsp+4A8h+var_390], xmm0
0x1c00b6d69  mov     [rsp+4A8h+var_380], r8
0x1c00b6d71  mov     [rsp+4A8h+var_3E0], rdi
0x1c00b6d79  mov     esi, edi
0x1c00b6d7b  mov     [rsp+4A8h+var_3F8], di
0x1c00b6d83  mov     [rsp+4A8h+var_403], sil
0x1c00b6d8b  mov     [rsp+4A8h+var_3B8], edi
0x1c00b6d92  mov     [rsp+4A8h+var_404], sil
0x1c00b6d9a  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b6da4  jnz     loc_1C00E94EC
0x1c00b6daa  xor     ecx, ecx; Irp
0x1c00b6dac  call    cs:__imp_IoIs32bitProcess
0x1c00b6db3  nop     dword ptr [rax+rax+00h]
0x1c00b6db8  mov     [rsp+4A8h+var_434], al
0x1c00b6dbc  mov     rax, [rsp+4A8h+var_420]
0x1c00b6dc4  mov     [rax+8], rdi
0x1c00b6dc8  mov     ebx, edi
0x1c00b6dca  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b6dd4  jnz     loc_1C00E953E
0x1c00b6dda  mov     [rsp+4A8h+var_3E0], rdi
0x1c00b6de2  mov     rcx, [r14+8]
0x1c00b6de6  mov     rax, cs:UxDriverObject
0x1c00b6ded  cmp     [rcx+8], rax
0x1c00b6df1  jnz     loc_1C00E9587
0x1c00b6df7  cmp     qword ptr [r14+20h], 50505041h
0x1c00b6dff  jnz     loc_1C00E9587
0x1c00b6e05  mov     r14, [r14+18h]
0x1c00b6e09  test    r14, r14
0x1c00b6e0c  jz      loc_1C00E957D
0x1c00b6e12  cmp     dword ptr [r14+18h], 50416C55h
0x1c00b6e1a  jnz     loc_1C00E957D
0x1c00b6e20  mov     rax, [r14+8]
0x1c00b6e24  test    rax, rax
0x1c00b6e27  jz      loc_1C00E957D
0x1c00b6e2d  cmp     dword ptr [rax+78h], 4F416C55h
0x1c00b6e34  jnz     loc_1C00E957D
0x1c00b6e3a  mov     eax, [r14+28h]
0x1c00b6e3e  test    al, 1
0x1c00b6e40  jz      loc_1C00E9569
0x1c00b6e46  call    cs:__imp_PsGetCurrentServerSilo
0x1c00b6e4d  nop     dword ptr [rax+rax+00h]
0x1c00b6e52  mov     rcx, [r14+8]
0x1c00b6e56  cmp     [rcx+140h], rax
0x1c00b6e5d  jnz     loc_1C00E9573
0x1c00b6e63  mov     [rsp+4A8h+var_3E0], r14
0x1c00b6e6b  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b6e75  jnz     loc_1C00E9591
0x1c00b6e7b  mov     [rsp+4A8h+var_430], ebx
0x1c00b6e7f  test    ebx, ebx
0x1c00b6e81  js      loc_1C00E9606
0x1c00b6e87  mov     ebx, edi
0x1c00b6e89  mov     [rsp+4A8h+var_3C8], ebx
0x1c00b6e90  test    r15, r15
0x1c00b6e93  jz      loc_1C00B72D5
0x1c00b6e99  xor     ecx, ecx; Irp
0x1c00b6e9b  call    cs:__imp_IoIs32bitProcess
0x1c00b6ea2  nop     dword ptr [rax+rax+00h]
0x1c00b6ea7  test    al, al
0x1c00b6ea9  jnz     loc_1C00B731C
0x1c00b6eaf  cmp     dword ptr [rsp+4A8h+var_3D8], 38h ; '8'
0x1c00b6eb7  jb      loc_1C00B73BE
0x1c00b6ebd  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 100h
0x1c00b6ec7  jnz     loc_1C00B73DD
0x1c00b6ecd  mov     rax, r15
0x1c00b6ed0  and     eax, 7
0x1c00b6ed3  movzx   r10d, [rsp+4A8h+arg_38]
0x1c00b6edc  test    r10b, r10b
0x1c00b6edf  jz      loc_1C00B7426
0x1c00b6ee5  test    rax, rax
0x1c00b6ee8  jnz     loc_1C00B7413
0x1c00b6eee  lea     rcx, [r15+38h]
0x1c00b6ef2  mov     rax, cs:MmUserProbeAddress
0x1c00b6ef9  mov     rdx, [rax]
0x1c00b6efc  cmp     rcx, rdx
0x1c00b6eff  ja      loc_1C00B741F
0x1c00b6f05  cmp     rcx, r15
0x1c00b6f08  jb      loc_1C00B741F
0x1c00b6f0e  movups  xmm0, xmmword ptr [r15]
0x1c00b6f12  movups  [rsp+4A8h+var_3B0], xmm0
0x1c00b6f1a  movups  xmm1, xmmword ptr [r15+10h]
0x1c00b6f1f  movups  [rsp+4A8h+var_3A0], xmm1
0x1c00b6f27  movups  xmm0, xmmword ptr [r15+20h]
0x1c00b6f2c  movups  [rsp+4A8h+var_390], xmm0
0x1c00b6f34  movsd   xmm1, qword ptr [r15+30h]
0x1c00b6f3a  movsd   [rsp+4A8h+var_380], xmm1
0x1c00b6f43  mov     r14, [rsp+4A8h+var_380]
0x1c00b6f4b  mov     [rsp+4A8h+var_410], r14
0x1c00b6f53  mov     [rsp+4A8h+var_430], ebx
0x1c00b6f57  test    ebx, ebx
0x1c00b6f59  js      loc_1C00B7440
0x1c00b6f5f  movzx   r8d, word ptr [rsp+4A8h+var_3B0+8]
0x1c00b6f68  mov     [rsp+4A8h+var_3E8], r8w
0x1c00b6f71  mov     r12d, dword ptr [rsp+4A8h+var_390+8]
0x1c00b6f79  mov     dword ptr [rsp+4A8h+var_402+2], r12d
0x1c00b6f81  mov     rax, qword ptr [rsp+4A8h+var_390]
0x1c00b6f89  mov     [rsp+4A8h+var_228], rax
0x1c00b6f91  mov     rax, qword ptr [rsp+4A8h+var_3A0+8]
0x1c00b6f99  mov     [rsp+4A8h+var_288], rax
0x1c00b6fa1  mov     eax, 2710h
0x1c00b6fa6  cmp     r8w, ax
0x1c00b6faa  jnb     loc_1C00B7462
0x1c00b6fb0  mov     eax, r12d
0x1c00b6fb3  test    eax, 0FFFFFE00h
0x1c00b6fb8  jnz     loc_1C00B74B3
0x1c00b6fbe  movzx   edx, [rsp+4A8h+arg_30]
0x1c00b6fc6  test    al, 10h
0x1c00b6fc8  jnz     loc_1C00B74AB
0x1c00b6fce  mov     ebx, edi
0x1c00b6fd0  mov     [rsp+4A8h+var_370], ebx
0x1c00b6fd7  test    r14, r14
0x1c00b6fda  jnz     loc_1C00B74E3
0x1c00b6fe0  mov     [rsp+4A8h+var_430], ebx
0x1c00b6fe4  test    ebx, ebx
0x1c00b6fe6  js      loc_1C00B777B
0x1c00b6fec  mov     rax, [rsp+4A8h+var_3E0]
0x1c00b6ff4  mov     rcx, [rax+8]
0x1c00b6ff8  mov     rax, [rcx+148h]
0x1c00b6fff  cmp     byte ptr [rax+440h], 0
0x1c00b7006  jz      short loc_1C00B701A
0x1c00b7008  test    dl, dl
0x1c00b700a  jnz     short loc_1C00B701A
0x1c00b700c  cmp     dword ptr [rsp+4A8h+var_3A0+8], 0
0x1c00b7014  jnz     loc_1C00B727E
0x1c00b701a  test    byte ptr [rsp+4A8h+var_390+8], 20h
0x1c00b7022  jnz     loc_1C00B779D
0x1c00b7028  cmp     word ptr [rsp+4A8h+var_3B0+8], 0Ah
0x1c00b7031  ja      loc_1C00B77C8
0x1c00b7037  movzx   r8d, word ptr [rsp+4A8h+var_3B0+8]
0x1c00b7040  test    r8w, r8w
0x1c00b7044  jz      loc_1C00B7148
0x1c00b704a  lea     rax, [rsp+4A8h+var_402]
0x1c00b7052  mov     [rsp+4A8h+var_470], rax; __int64
0x1c00b7057  lea     rax, [rsp+4A8h+P]
0x1c00b705f  mov     [rsp+4A8h+var_478], rax; __int64
0x1c00b7064  lea     rax, [rsp+4A8h+var_188]
0x1c00b706c  mov     [rsp+4A8h+var_480], rax; P
0x1c00b7071  mov     r9, qword ptr [rsp+4A8h+var_3A0]
0x1c00b7079  movzx   edx, r10b
0x1c00b707d  xor     ecx, ecx; Irp
0x1c00b707f  call    UlpGetChunkInfo
0x1c00b7084  mov     ebx, eax
0x1c00b7086  mov     [rsp+4A8h+var_430], eax
0x1c00b708a  test    eax, eax
0x1c00b708c  js      loc_1C00B77FD
0x1c00b7092  mov     r10, [rsp+4A8h+var_3E0]
0x1c00b709a  mov     [rsp+4A8h+var_3D8], r10
0x1c00b70a2  mov     [rsp+4A8h+var_338], rdi
0x1c00b70aa  mov     [rsp+4A8h+var_3C0], edi
0x1c00b70b1  mov     [rsp+4A8h+var_3D0], rdi
0x1c00b70b9  mov     r9d, edi
0x1c00b70bc  mov     [rsp+4A8h+var_438], edi
0x1c00b70c0  mov     [rsp+4A8h+var_408], edi
0x1c00b70c7  mov     r14d, edi
0x1c00b70ca  mov     [rsp+4A8h+var_3C0], edi
0x1c00b70d1  mov     r15, [rsp+4A8h+P]
0x1c00b70d9  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1c00b70e0  mov     [rsp+4A8h+var_338], r15
0x1c00b70e8  movzx   eax, [rsp+4A8h+var_3E8]
0x1c00b70f0  cmp     r14d, eax
0x1c00b70f3  jnb     short loc_1C00B712F
0x1c00b70f5  mov     edx, [r15+10h]
0x1c00b70f9  mov     ecx, [r15]
0x1c00b70fc  lea     eax, [rcx-2]
0x1c00b70ff  cmp     eax, 1
0x1c00b7102  jbe     loc_1C00B781F
0x1c00b7108  test    ecx, ecx
0x1c00b710a  jz      loc_1C00B724D
0x1c00b7110  mov     ebx, 0C00000BBh
0x1c00b7115  mov     [rsp+4A8h+var_430], ebx
0x1c00b7119  mov     r15, [rsp+4A8h+var_420]
0x1c00b7121  mov     rcx, r15
0x1c00b7124  xor     r14b, r14b
0x1c00b7127  xor     r10b, r10b
0x1c00b712a  jmp     loc_1C00B7D7B
0x1c00b712f  cmp     r9d, 800h
0x1c00b7136  ja      loc_1C00B72A9
0x1c00b713c  mov     [rsp+4A8h+var_430], edi
0x1c00b7140  movzx   edx, [rsp+4A8h+arg_30]
0x1c00b7148  test    dl, dl
0x1c00b714a  jnz     loc_1C00B7CEA
0x1c00b7150  mov     rax, [rsp+4A8h+var_3E0]
0x1c00b7158  mov     r14, [rax+8]
0x1c00b715c  mov     ebx, edi
0x1c00b715e  mov     [rsp+4A8h+var_3C4], ebx
0x1c00b7165  mov     [rsp+4A8h+var_42C], bl
0x1c00b7169  mov     r15, qword ptr [rsp+4A8h+var_3B0]
0x1c00b7171  test    r15, r15
0x1c00b7174  jz      loc_1C00B78CA
0x1c00b717a  xor     ecx, ecx; Irp
0x1c00b717c  call    cs:__imp_IoIs32bitProcess
0x1c00b7183  nop     dword ptr [rax+rax+00h]
0x1c00b7188  movzx   ecx, word ptr [r14+114h]
0x1c00b7190  movzx   r9d, [rsp+4A8h+arg_38]
0x1c00b7199  test    al, al
0x1c00b719b  jnz     loc_1C00B78FD
0x1c00b71a1  mov     r8d, 8
0x1c00b71a7  cmp     cx, 2
0x1c00b71ab  mov     rcx, r15
0x1c00b71ae  jb      loc_1C00B72CB
0x1c00b71b4  mov     edx, 238h
0x1c00b71b9  call    UlProbeForRead
0x1c00b71be  mov     r13, r15
0x1c00b71c1  mov     [rsp+4A8h+var_3F0], r15
0x1c00b71c9  mov     [rsp+4A8h+var_430], ebx
0x1c00b71cd  test    ebx, ebx
0x1c00b71cf  js      loc_1C00B7C5D
0x1c00b71d5  movzx   eax, word ptr [r13+8]
0x1c00b71da  mov     [rsp+4A8h+var_3F8], ax
0x1c00b71e2  mov     rax, [rsp+4A8h+var_3E0]
0x1c00b71ea  mov     rcx, [rax+8]
0x1c00b71ee  cmp     word ptr [rcx+114h], 2
0x1c00b71f6  jb      short loc_1C00B7248
0x1c00b71f8  movzx   eax, [rsp+4A8h+var_434]
0x1c00b71fd  movzx   edx, [rsp+4A8h+var_42C]
0x1c00b7202  lea     r8, [rsp+4A8h+var_404]
0x1c00b720a  mov     [rsp+4A8h+var_478], r8
0x1c00b720f  mov     dword ptr [rsp+4A8h+var_480], eax
0x1c00b7213  mov     dword ptr [rsp+4A8h+var_488], edx
0x1c00b7217  xor     r9d, r9d
0x1c00b721a  xor     r8d, r8d
0x1c00b721d  mov     rdx, r13
0x1c00b7220  mov     rcx, [rcx+148h]
0x1c00b7227  call    UlFlCaptureFlowRateInfo
0x1c00b722c  mov     ebx, eax
0x1c00b722e  mov     [rsp+4A8h+var_430], eax
0x1c00b7232  test    eax, eax
0x1c00b7234  js      loc_1C00B7C7F
0x1c00b723a  cmp     [rsp+4A8h+var_404], 0
0x1c00b7242  jnz     loc_1C00B7CA1
0x1c00b7248  jmp     loc_1C00B7E07
0x1c00b724d  mov     eax, edx
0x1c00b724f  not     eax
0x1c00b7251  cmp     r9d, eax
0x1c00b7254  ja      loc_1C00B7110
0x1c00b725a  add     r9d, edx
0x1c00b725d  mov     [rsp+4A8h+var_438], r9d
0x1c00b7262  mov     [rsp+4A8h+var_408], r9d
0x1c00b726a  inc     r14d
0x1c00b726d  mov     [rsp+4A8h+var_3C0], r14d
0x1c00b7275  add     r15, 20h ; ' '
0x1c00b7279  jmp     loc_1C00B70E0
0x1c00b727e  mov     ebx, 0C0000002h
0x1c00b7283  mov     [rsp+4A8h+var_430], ebx
0x1c00b7287  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1c00b728e  mov     r9d, [rsp+4A8h+var_438]
0x1c00b7293  mov     r15, [rsp+4A8h+var_420]
0x1c00b729b  mov     rcx, r15
0x1c00b729e  xor     r14b, r14b
0x1c00b72a1  xor     r10b, r10b
0x1c00b72a4  jmp     loc_1C00B7D7B
0x1c00b72a9  mov     eax, r12d
0x1c00b72ac  and     eax, 4
0x1c00b72af  test    al, al
0x1c00b72b1  jz      loc_1C00B7110
  ... truncated ...
```
