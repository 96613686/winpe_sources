# UlSendHttpResponseIoctl

- ea: `0x1c00b4cf0`
- end: `0x1c00b6a50`
- name: `UlSendHttpResponseIoctl`
- size: `7520`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `45`
- tags: `broker_com_uri`

## callees

- `0x1c0001ae0`
- `0x1c000aca8`
- `0x1c000ad10`
- `0x1c000b018`
- `0x1c000b0a0`
- `0x1c000b184`
- `0x1c000cb50`
- `0x1c000e148`
- `0x1c000fc68`
- `0x1c00102d0`
- `0x1c0010ce8`
- `0x1c0014720`
- `0x1c0017104`
- `0x1c001a4b0`
- `0x1c001a548`
- `0x1c001a8ac`
- `0x1c001aff4`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c002cb04`
- `0x1c0032300`
- `0x1c008f21c`
- `0x1c008f30c`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f4f0`
- `0x1c008f570`
- `0x1c008fd84`
- `0x1c00903a4`
- `0x1c0097cfc`
- `0x1c0097d58`
- `0x1c0097dec`
- `0x1c009c1e4`
- `0x1c00b3674`
- `0x1c00b4cf0`
- `0x1c00b6a60`
- `0x1c00b8300`
- `0x1c00b89b4`
- `0x1c00bbfe0`
- `0x1c00c0360`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c0108768`
- `0x1c010e41c`
- `0x1c0116320`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1c00b5339`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b538c`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b61b4`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b5339`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b538c`
- `ntoskrnl!KeReadStateEvent` at `0x1c00b61b4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1c00b59a7`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1c00b59a7`
- `ntoskrnl!MmUserProbeAddress` at `0x1c00b4f8b`
- `ntoskrnl!ExRaiseStatus` at `0x1c00b59c9`
- `ntoskrnl!ExRaiseStatus` at `0x1c00b59c9`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b4e45`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b4f41`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b502f`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b5da5`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b4e45`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b4f41`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b502f`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00b5da5`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00b4ed9`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00b4ed9`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e93c9`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e93c9`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00b5a8b`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00b5a8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e916e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e918a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e916e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00e918a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b6521`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b684f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b6521`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00b684f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b649c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b67a9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b649c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00b67a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b652d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b685b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b652d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00b685b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b6486`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b6794`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b6486`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00b6794`

## pseudocode

```c
__int64 __fastcall UlSendHttpResponseIoctl(PIRP Irp, __int64 a2)
{
  __int64 v4; // r15
  __int64 v5; // r9
  _QWORD *v6; // rbx
  NTSTATUS ChunkInfo; // esi
  __int64 v8; // rbx
  __int64 v9; // rax
  unsigned int v10; // r12d
  unsigned __int64 v11; // rbx
  unsigned __int8 RequestorMode; // di
  __int64 v13; // rdx
  _WORD *v14; // rdi
  __int64 v15; // rbx
  unsigned __int8 v16; // r12
  BOOLEAN v17; // al
  unsigned __int16 v18; // cx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // r8d
  KPROCESSOR_MODE v22; // al
  int *v23; // rbx
  __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rbx
  __int64 ObjectFromOpaqueId; // rax
  __int64 v28; // rdi
  char v29; // r12
  __int64 v30; // r10
  int v31; // ebx
  __int64 v32; // rsi
  LONG StateEvent; // eax
  unsigned int v34; // ecx
  unsigned int v35; // r12d
  unsigned int v36; // edx
  LONG v37; // eax
  unsigned int v38; // ecx
  bool v39; // r9
  __int64 v40; // rdx
  unsigned __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  int v45; // ebx
  bool v46; // zf
  _OWORD *v47; // r10
  __int64 v48; // r12
  __int64 v49; // rbx
  __int64 v50; // rcx
  _QWORD *v51; // rbx
  char v52; // di
  int v53; // eax
  unsigned __int16 v54; // si
  _WORD *PoolWithTagPriority; // rax
  _WORD *v56; // rbx
  __int64 v57; // rdx
  __int64 v58; // rcx
  unsigned __int16 v59; // r8
  char *v60; // rcx
  __int64 v61; // rdx
  char *v62; // rdx
  char *v63; // r8
  __int64 v64; // rcx
  unsigned int v65; // eax
  unsigned __int64 v66; // rdi
  __int64 v67; // r9
  unsigned __int64 v68; // r12
  unsigned __int16 v69; // cx
  BOOLEAN v70; // al
  __int64 v71; // r9
  int v72; // ecx
  __int64 v73; // r9
  __int16 v74; // cx
  int v75; // eax
  __int64 v76; // r8
  __int64 v77; // r8
  UCHAR v78; // al
  char v79; // r10
  char v80; // r11
  const char *v81; // rcx
  char v82; // r9
  __int64 v83; // rbx
  int v84; // edx
  int v85; // ecx
  volatile signed __int32 **v86; // rcx
  volatile signed __int32 ***v87; // rdx
  volatile signed __int32 *v88; // rax
  volatile signed __int32 *v89; // rax
  _QWORD *v90; // rdx
  __int64 v92; // rbx
  volatile signed __int32 *v93; // rcx
  __int64 v94; // r8
  _QWORD *v95; // rdi
  __int64 v96; // rcx
  __int64 v97; // rax
  __int64 *v98; // [rsp+20h] [rbp-448h]
  PVOID v99; // [rsp+28h] [rbp-440h]
  bool v100; // [rsp+80h] [rbp-3E8h]
  int v101; // [rsp+84h] [rbp-3E4h]
  unsigned __int8 v102; // [rsp+88h] [rbp-3E0h]
  char v103; // [rsp+89h] [rbp-3DFh] BYREF
  char v104; // [rsp+8Ah] [rbp-3DEh]
  char v105; // [rsp+8Bh] [rbp-3DDh]
  char v106[2]; // [rsp+8Ch] [rbp-3DCh] BYREF
  unsigned __int16 v107; // [rsp+8Eh] [rbp-3DAh]
  __int16 v108; // [rsp+90h] [rbp-3D8h]
  unsigned __int16 v109; // [rsp+94h] [rbp-3D4h]
  char v110; // [rsp+98h] [rbp-3D0h]
  char v111; // [rsp+99h] [rbp-3CFh] BYREF
  BOOLEAN v112; // [rsp+9Ah] [rbp-3CEh]
  _DWORD v113[3]; // [rsp+9Ch] [rbp-3CCh] BYREF
  __int64 v114; // [rsp+A8h] [rbp-3C0h]
  __int64 v115; // [rsp+B0h] [rbp-3B8h] BYREF
  PVOID v116; // [rsp+B8h] [rbp-3B0h]
  int v117; // [rsp+C0h] [rbp-3A8h]
  size_t Size; // [rsp+C8h] [rbp-3A0h]
  __int64 v119; // [rsp+D0h] [rbp-398h]
  __int128 v120; // [rsp+D8h] [rbp-390h]
  __int128 v121; // [rsp+E8h] [rbp-380h]
  __int128 v122; // [rsp+F8h] [rbp-370h]
  _OWORD *v123; // [rsp+108h] [rbp-360h]
  int v124; // [rsp+110h] [rbp-358h]
  int v125; // [rsp+114h] [rbp-354h]
  int v126; // [rsp+118h] [rbp-350h]
  volatile signed __int32 *v127; // [rsp+120h] [rbp-348h] BYREF
  volatile signed __int32 ***v128; // [rsp+128h] [rbp-340h]
  unsigned int v129; // [rsp+130h] [rbp-338h]
  PVOID P; // [rsp+138h] [rbp-330h] BYREF
  __int64 v131; // [rsp+140h] [rbp-328h]
  int v132; // [rsp+148h] [rbp-320h]
  int v133; // [rsp+14Ch] [rbp-31Ch]
  __int64 v134; // [rsp+150h] [rbp-318h]
  char *v135; // [rsp+158h] [rbp-310h]
  unsigned __int64 v136; // [rsp+160h] [rbp-308h]
  unsigned __int64 v137; // [rsp+168h] [rbp-300h]
  int v138; // [rsp+170h] [rbp-2F8h]
  char *v139; // [rsp+178h] [rbp-2F0h]
  char *v140; // [rsp+180h] [rbp-2E8h]
  PIRP v141; // [rsp+188h] [rbp-2E0h]
  _OWORD v142[9]; // [rsp+190h] [rbp-2D8h] BYREF
  __int128 v143; // [rsp+220h] [rbp-248h]
  __int128 v144; // [rsp+230h] [rbp-238h]
  __int128 v145; // [rsp+240h] [rbp-228h] BYREF
  __int128 v146; // [rsp+250h] [rbp-218h] BYREF
  __int128 v147; // [rsp+260h] [rbp-208h] BYREF
  __int128 v148; // [rsp+270h] [rbp-1F8h] BYREF
  _QWORD v149[3]; // [rsp+280h] [rbp-1E8h] BYREF
  char v150; // [rsp+298h] [rbp-1D0h]
  int v151; // [rsp+299h] [rbp-1CFh]
  __int16 v152; // [rsp+29Dh] [rbp-1CBh]
  char v153; // [rsp+29Fh] [rbp-1C9h]
  _QWORD v154[2]; // [rsp+2A0h] [rbp-1C8h] BYREF
  __int128 v155; // [rsp+2B0h] [rbp-1B8h]
  _OWORD v156[2]; // [rsp+2C0h] [rbp-1A8h] BYREF
  __int128 v157; // [rsp+2E0h] [rbp-188h] BYREF
  int v158; // [rsp+2F0h] [rbp-178h] BYREF
  __int128 v159; // [rsp+2F8h] [rbp-170h]
  __int64 v160; // [rsp+308h] [rbp-160h]
  _BYTE v161[288]; // [rsp+310h] [rbp-158h] BYREF

  v141 = Irp;
  *(_QWORD *)&v113[1] = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  v119 = 0;
  v116 = 0;
  v4 = 0;
  v114 = 0;
  v106[0] = 0;
  v105 = 0;
  v117 = 0;
  v110 = 0;
  v104 = 0;
  v111 = 0;
  v115 = 0;
  v131 = 0;
  v102 = 0;
  v158 = 0;
  v159 = 0;
  v160 = 0;
  memset(v161, 0, sizeof(v161));
  P = 0;
  LOWORD(v113[0]) = 0;
  memset(v142, 0, sizeof(v142));
  v109 = 0;
  v157 = 0;
  v132 = 0;
  v103 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qq(67, WPP_18ca8755388c316524f95a91261e2540_Traceguids, Irp, a2);
  v112 = IoIs32bitProcess(Irp);
  v6 = *(_QWORD **)(a2 + 48);
  ChunkInfo = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    v98 = &v115;
    WPP_SF_qdP(12, WPP_18ca8755388c316524f95a91261e2540_Traceguids, v6, 1);
  }
  v115 = 0;
  if ( *(PDEVICE_OBJECT *)(v6[1] + 8LL) == UxDriverObject && v6[4] == 1347440705 )
  {
    v8 = v6[3];
    if ( v8
      && *(_DWORD *)(v8 + 24) == 1346464853
      && (v9 = *(_QWORD *)(v8 + 8)) != 0
      && *(_DWORD *)(v9 + 120) == 1329687637 )
    {
      if ( (*(_DWORD *)(v8 + 40) & 1) != 0 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v8 + 8) + 320LL) == PsGetCurrentServerSilo() )
          v115 = v8;
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
    WPP_SF_qD(13, WPP_18ca8755388c316524f95a91261e2540_Traceguids, v115, (unsigned int)ChunkInfo);
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    v52 = 0;
    goto LABEL_247;
  }
  v10 = *(_DWORD *)(a2 + 16);
  v11 = *(_QWORD *)(a2 + 32);
  RequestorMode = Irp->RequestorMode;
  ChunkInfo = 0;
  v124 = 0;
  if ( !v11 )
  {
    ChunkInfo = -1073741811;
    v124 = -1073741811;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(11, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
    goto LABEL_27;
  }
  if ( !IoIs32bitProcess(Irp) )
  {
    if ( v10 < 0x38 )
    {
      ChunkInfo = -1073741789;
      v124 = -1073741789;
      if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
        WPP_SF_D(13, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
    }
    else
    {
      if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x100) != 0 )
      {
        LODWORD(v98) = 8;
        WPP_SF_PqLc(10, v13, 56, v11);
      }
      if ( RequestorMode )
      {
        if ( (v11 & 7) != 0 )
          ExRaiseDatatypeMisalignment();
        if ( v11 + 56 > MmUserProbeAddress || v11 + 56 < v11 )
          *(_BYTE *)MmUserProbeAddress = 0;
      }
      else if ( (v11 & 7) != 0 )
      {
        ExRaiseStatus(-1073741115);
      }
      v120 = *(_OWORD *)v11;
      v121 = *(_OWORD *)(v11 + 16);
      v122 = *(_OWORD *)(v11 + 32);
      v123 = *(_OWORD **)(v11 + 48);
      *(_QWORD *)&v113[1] = v123;
    }
LABEL_27:
    v14 = (_WORD *)v120;
    goto LABEL_28;
  }
  if ( v10 < 0x28 )
  {
    ChunkInfo = -1073741789;
    v124 = -1073741789;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(12, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
    goto LABEL_27;
  }
  UlProbeForRead(v11, 40, 4, RequestorMode);
  v14 = (_WORD *)*(unsigned int *)v11;
  *(_QWORD *)&v120 = v14;
  *(_QWORD *)&v121 = *(unsigned int *)(v11 + 8);
  WORD4(v120) = *(_WORD *)(v11 + 4);
  *((_QWORD *)&v121 + 1) = *(_QWORD *)(v11 + 12);
  *(_QWORD *)&v122 = *(_QWORD *)(v11 + 24);
  DWORD2(v122) = *(_DWORD *)(v11 + 32);
  *(_QWORD *)&v113[1] = *(unsigned int *)(v11 + 36);
  v123 = *(_OWORD **)&v113[1];
LABEL_28:
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    v52 = 0;
    goto LABEL_247;
  }
  v15 = *(_QWORD *)(v115 + 8);
  v16 = Irp->RequestorMode;
  ChunkInfo = 0;
  v125 = 0;
  v102 = 0;
  if ( v14 )
  {
    v17 = IoIs32bitProcess(Irp);
    v18 = *(_WORD *)(v15 + 276);
    if ( v17 )
    {
      v54 = 0;
      if ( v18 < 2u )
      {
        UlProbeForRead(v14, 280, 4, v16);
      }
      else
      {
        UlProbeForRead(v14, 288, 4, v16);
        v54 = v14[140];
      }
      v107 = v14[8];
      Size = ((24LL * v107 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 568 + 16LL * v54;
      PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, Size, 0x53486C55u, LowPoolPriority);
      v56 = PoolWithTagPriority;
      if ( PoolWithTagPriority )
      {
        v116 = PoolWithTagPriority;
        v102 = 1;
        memset(PoolWithTagPriority, 0, Size);
        v57 = v107;
        v56[12] = v107;
        v56[276] = v54;
        ChunkInfo = 0;
        v138 = 0;
        v108 = 0;
        v134 = 0;
        v135 = 0;
        v139 = 0;
        v140 = 0;
        v137 = 0;
        v136 = 0;
        *(_DWORD *)v56 = *(_DWORD *)v14;
        *((_DWORD *)v56 + 1) = *((_DWORD *)v14 + 1);
        v56[4] = v14[4];
        v56[5] = v14[5];
        *((_QWORD *)v56 + 2) = *((unsigned int *)v14 + 3);
        v56[268] = v14[136];
        *((_QWORD *)v56 + 68) = *((unsigned int *)v14 + 69);
        if ( v14[12] || *((_DWORD *)v14 + 7) )
        {
          ChunkInfo = -1073741811;
          v138 = -1073741811;
          if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
            WPP_SF_D(15, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
        }
        else
        {
          v58 = *((unsigned int *)v14 + 5);
          v134 = v58;
          v135 = (char *)(v56 + 284);
          *((_QWORD *)v56 + 4) = v56 + 284;
          UlProbeForRead(v58, 12 * v57, 4, v16);
          v59 = 0;
          v108 = 0;
          v60 = v135;
          v61 = v134;
          while ( v59 < v56[12] )
          {
            *(_WORD *)v60 = *(_WORD *)v61;
            *((_QWORD *)v60 + 1) = *(unsigned int *)(v61 + 4);
            *((_WORD *)v60 + 1) = *(_WORD *)(v61 + 2);
            *((_QWORD *)v60 + 2) = *(unsigned int *)(v61 + 8);
            v108 = ++v59;
            v61 += 12;
            v134 = v61;
            v60 += 24;
            v135 = v60;
          }
          v62 = (char *)(v14 + 16);
          v63 = (char *)(v56 + 28);
          v5 = 0;
          v108 = 0;
          while ( 1 )
          {
            v140 = v63;
            v139 = v62;
            if ( (unsigned __int16)v5 >= 0x1Eu )
              break;
            *(_WORD *)v63 = *(_WORD *)v62;
            *((_QWORD *)v63 + 1) = *((unsigned int *)v62 + 1);
            LOWORD(v5) = v5 + 1;
            v108 = v5;
            v62 += 8;
            v63 += 16;
          }
          v136 = (unsigned __int64)(v60 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          v64 = (unsigned __int16)v56[276];
          if ( (_WORD)v64 )
          {
            v65 = *((_DWORD *)v14 + 71);
            v137 = v65;
            v66 = v136;
            *((_QWORD *)v56 + 70) = v136;
            v67 = v16;
            v68 = v65;
            UlProbeForRead(v65, 12 * v64, 4, v67);
            v69 = 0;
            while ( 1 )
            {
              v108 = v69;
              if ( v69 >= v56[276] )
                break;
              *(_DWORD *)v66 = *(_DWORD *)v68;
              *(_DWORD *)(v66 + 4) = *(_DWORD *)(v68 + 4);
              *(_QWORD *)(v66 + 8) = *(unsigned int *)(v68 + 8);
              ++v69;
              v66 += 16LL;
              v136 = v66;
              v68 += 12LL;
              v137 = v68;
            }
          }
        }
        v125 = ChunkInfo;
      }
      else
      {
        ChunkInfo = -1073741801;
        v125 = -1073741801;
        if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
          WPP_SF_D(17, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
      }
    }
    else
    {
      if ( v18 < 2u )
        v19 = 552;
      else
        v19 = 568;
      UlProbeForRead(v14, v19, 8, v16);
      v116 = v14;
    }
  }
  else
  {
    ChunkInfo = -1073741811;
    v125 = -1073741811;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(16, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
  }
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    v52 = 0;
    goto LABEL_247;
  }
  ChunkInfo = UlpGetChunkInfo(Irp, (int)v98, &v158, (__int64)&P, (__int64)v113);
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(68, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v52 = 0;
    goto LABEL_247;
  }
  v22 = Irp->RequestorMode;
  ChunkInfo = 0;
  v133 = 0;
  v23 = *(int **)&v113[1];
  if ( *(_QWORD *)&v113[1] && v22 == 1 )
  {
    v70 = IoIs32bitProcess(Irp);
    LOBYTE(v71) = 1;
    if ( v70 )
    {
      UlProbeForRead(v23, 92, 4, v71);
      v72 = *v23;
      v142[0] = *(_OWORD *)v23;
      *(_QWORD *)&v142[1] = *((_QWORD *)v23 + 2);
      DWORD2(v142[1]) = v23[6];
      *(_QWORD *)&v142[2] = (unsigned int)v23[7];
      *((_QWORD *)&v142[2] + 1) = (unsigned int)v23[8];
      *(_QWORD *)&v142[3] = (unsigned int)v23[9];
      *((_QWORD *)&v142[3] + 1) = (unsigned int)v23[10];
      *(_QWORD *)&v142[4] = (unsigned int)v23[11];
      *((_QWORD *)&v142[4] + 1) = (unsigned int)v23[12];
      *(_QWORD *)&v142[5] = (unsigned int)v23[13];
      *((_QWORD *)&v142[5] + 1) = (unsigned int)v23[14];
      *(_QWORD *)&v142[6] = (unsigned int)v23[15];
      *((_QWORD *)&v142[6] + 1) = (unsigned int)v23[16];
      *(_QWORD *)&v142[7] = (unsigned int)v23[17];
      *((_QWORD *)&v142[7] + 1) = (unsigned int)v23[18];
      LODWORD(v142[8]) = v23[19];
      *(_QWORD *)((char *)&v142[8] + 4) = *((_QWORD *)v23 + 10);
      WORD6(v142[8]) = *((_WORD *)v23 + 44);
    }
    else
    {
      UlProbeForRead(v23, 144, 8, v71);
      v142[0] = *(_OWORD *)v23;
      v142[1] = *((_OWORD *)v23 + 1);
      v142[2] = *((_OWORD *)v23 + 2);
      v142[3] = *((_OWORD *)v23 + 3);
      v142[4] = *((_OWORD *)v23 + 4);
      v142[5] = *((_OWORD *)v23 + 5);
      v142[6] = *((_OWORD *)v23 + 6);
      v142[7] = *((_OWORD *)v23 + 7);
      v142[8] = *((_OWORD *)v23 + 8);
      v72 = v142[0];
    }
    if ( v72 )
    {
      ChunkInfo = -1073741811;
      v133 = -1073741811;
      if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
        WPP_SF_D(14, WPP_56fa5037e0a538d8b1a5dc606b0258f3_Traceguids);
    }
    else
    {
      *(_QWORD *)&v113[1] = v142;
      v123 = v142;
    }
  }
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    v52 = 0;
    goto LABEL_247;
  }
  LODWORD(Size) = BYTE8(v122) & 2;
  BYTE1(v113[0]) = (BYTE8(v122) & 2) == 0;
  if ( (BYTE8(v122) & 2) == 0 )
  {
    LODWORD(v5) = v122;
    v131 = v122;
    *((_QWORD *)&v157 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
    *(_QWORD *)&v157 = v122;
    v24 = *(_QWORD *)(v115 + 8);
    v25 = *(_QWORD *)(v24 + 328);
    if ( *(_BYTE *)(v25 + 1568) )
    {
      v155 = v25;
      v154[0] = &v157;
      v154[1] = 0;
      McTemplateK0p_UlEtwWriteEventWrapper(v24, HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY, v154);
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
    WPP_SF_iD(69, v20, v131, DWORD2(v122));
  v26 = v115;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qq(10, WPP_113f5b8b44003c935cfae087381f34ee_Traceguids, v122, v115);
  ObjectFromOpaqueId = UxGetObjectFromOpaqueIdEx(v122, v20, v21, v5, (_DWORD)v98, v26);
  v28 = ObjectFromOpaqueId;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    if ( ObjectFromOpaqueId )
      v73 = *(_QWORD *)(ObjectFromOpaqueId + 64);
    else
      v73 = 0;
    WPP_SF_qq(11, WPP_113f5b8b44003c935cfae087381f34ee_Traceguids, ObjectFromOpaqueId, v73);
  }
  v4 = v28;
  v114 = v28;
  if ( !v28 )
  {
    ChunkInfo = -1073741254;
    v101 = -1073741254;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(70, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v52 = 0;
    goto LABEL_247;
  }
  v29 = BYTE8(v121);
  if ( SDWORD2(v121) >= 3 )
  {
    ChunkInfo = -1073741811;
    v101 = -1073741811;
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(71, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v52 = 0;
    goto LABEL_247;
  }
  if ( DWORD2(v121) )
  {
    v53 = *(_DWORD *)(v28 + 2184) >> 1;
    LOBYTE(v53) = (*(_DWORD *)(v28 + 2184) & 2) != 0;
    v117 = v53;
    v105 = v53;
    v110 = v53;
  }
  v30 = *(_QWORD *)(v115 + 8);
  v31 = *(_DWORD *)(v30 + 276);
  v132 = v31;
  if ( (unsigned __int16)v31 >= 2u )
  {
    ChunkInfo = UlFlCaptureFlowRateInfo(*(_QWORD *)(v30 + 328), (_DWORD)v116, 0, 0, v102, v112, (__int64)&v103);
    v101 = ChunkInfo;
    if ( ChunkInfo < 0 )
    {
      v52 = 0;
      goto LABEL_247;
    }
  }
  if ( *(_QWORD *)(v28 + 2472) )
  {
    if ( (BYTE8(v122) & 0x10) != 0 )
    {
      v100 = 0;
    }
    else if ( (BYTE8(v122) & 0x40) != 0 )
    {
      v100 = 0;
    }
    else if ( (unsigned __int16)v31 >= 2u && *((_WORD *)v116 + 276) )
    {
      v100 = 0;
    }
    else
    {
      v74 = *((_WORD *)v116 + 4);
      v100 = (v74 == 200 || v74 == 206) && *(_DWORD *)(v28 + 2660) <= 1u;
    }
  }
  else
  {
    v100 = 0;
  }
  if ( (_BYTE)v117 )
  {
LABEL_116:
    if ( v100 )
      goto LABEL_78;
    goto LABEL_56;
  }
  if ( v100 )
  {
    v75 = *(_DWORD *)(v28 + 2184) >> 2;
    LOBYTE(v75) = (*(_DWORD *)(v28 + 2184) & 4) != 0;
    v117 = v75;
    v110 = v75;
    goto LABEL_116;
  }
LABEL_56:
  if ( !v105 && !v103 && (BYTE8(v122) & 4) == 0 && (BYTE8(v122) & 0x20) == 0 )
  {
    v32 = *(_QWORD *)(v28 + 24);
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v32 + 848) + 960LL) + 4172LL) == -1 )
    {
      StateEvent = KeReadStateEvent(UxHighNonPagedPoolEvent);
      v34 = *(_DWORD *)(v32 + 856);
      v35 = 0x10000;
      if ( StateEvent )
      {
        v36 = 2 * v34;
      }
      else
      {
        v36 = 0x10000;
        if ( v34 < 0x10000 )
          v36 = *(_DWORD *)(v32 + 856);
      }
      v129 = v36;
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v32 + 848) + 960LL) + 4176LL) <= v36 )
      {
        v35 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v32 + 848) + 960LL) + 4176LL);
      }
      else
      {
        v37 = KeReadStateEvent(UxHighNonPagedPoolEvent);
        v38 = *(_DWORD *)(v32 + 856);
        if ( v37 )
        {
          v35 = 2 * v38;
        }
        else if ( v38 < 0x10000 )
        {
          v35 = *(_DWORD *)(v32 + 856);
        }
      }
    }
    else if ( KeReadStateEvent(UxHighNonPagedPoolEvent) )
    {
      v35 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v32 + 848) + 960LL) + 4172LL);
    }
    else
    {
      v35 = 0x10000;
    }
    v39 = (unsigned int)(*(_DWORD *)(v32 + 872) + *(_DWORD *)(v32 + 896)) < 0x40
       && *(_QWORD *)(v32 + 864) + *(_QWORD *)(v32 + 904) < (unsigned __int64)v35;
    LOBYTE(v107) = v39;
    if ( (HIDWORD(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x1000000) != 0 )
    {
      v76 = *(_QWORD *)(v32 + 848);
      v143 = (unsigned __int64)(v76 + 316);
      WORD4(v143) = SOCKADDR_SIZE(*(_WORD *)(v76 + 316));
      v148 = v143;
      v144 = (unsigned __int64)(v77 + 288);
      v78 = SOCKADDR_SIZE(*(_WORD *)(v77 + 288));
      WORD4(v144) = v78;
      v147 = v144;
      v81 = "ok";
      if ( !v82 )
        v81 = "no";
      WPP_SF__SOCKADDR__SOCKADDR_sLLIIL(
        (_DWORD)v81,
        v78,
        (unsigned int)&v147,
        (unsigned int)&v148,
        (__int64)v81,
        v80,
        v79,
        *(_QWORD *)(v32 + 864),
        *(_QWORD *)(v32 + 904),
        v35);
      v39 = v107;
    }
    if ( v39 && WORD4(v120) == 1 && !*(_DWORD *)P && (unsigned int)(*((_DWORD *)P + 4) - 1) <= 0xFFFF )
    {
      if ( (unsigned __int16)v31 < 2u || !*((_WORD *)v116 + 276) )
        goto LABEL_114;
      ChunkInfo = UlExtractAndAppendAuthenticationResponseInfo(v28, (__int64)v116, 0, Irp->RequestorMode, 0, &v111);
      v101 = ChunkInfo;
      if ( ChunkInfo < 0 )
      {
        if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
          WPP_SF_D(72, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
        v52 = 0;
        goto LABEL_247;
      }
      if ( !v111 )
      {
LABEL_114:
        v104 = 1;
        goto LABEL_83;
      }
    }
    v29 = BYTE8(v121);
  }
LABEL_78:
  HIDWORD(v99) = HIDWORD(P);
  LOWORD(v98) = WORD4(v120);
  ChunkInfo = UlCaptureHttpResponse(v115, v116, v28, Irp);
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(73, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v52 = 0;
    goto LABEL_247;
  }
  v41 = *(_QWORD *)(*(_QWORD *)(v28 + 24) + 960LL);
  if ( *(_BYTE *)(v41 + 1568) )
  {
    v156[1] = v41;
    v156[0] = (unsigned __int64)(v28 + 72);
    v42 = UlVerbToString(*(unsigned int *)(v119 + 64));
    McTemplateK0xxhsqhq_UlEtwWriteEventWrapper(
      *(_DWORD *)(v43 + 76),
      (unsigned int)HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE,
      (unsigned int)v156,
      *(_QWORD *)(v28 + 56),
      *(_QWORD *)(v44 + 24),
      *(_WORD *)(v43 + 60),
      v42,
      *(_DWORD *)(v43 + 76),
      SBYTE8(v120),
      v29);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
  {
    LOWORD(v98) = *(_WORD *)(v119 + 60);
    WPP_SF_iiHLLHL(v119, v40, *(_QWORD *)(v28 + 56), *(_QWORD *)(*(_QWORD *)(v28 + 24) + 24LL));
  }
LABEL_83:
  v5 = v109;
  v45 = Size;
  if ( (DWORD2(v122) & 0xFFFFFE10) != 0 )
  {
    v47 = *(_OWORD **)&v113[1];
  }
  else if ( _InterlockedCompareExchange((volatile signed __int32 *)(v28 + 2200), 1, 0) == 1 )
  {
    v47 = v123;
    *(_QWORD *)&v113[1] = v123;
    v4 = v114;
  }
  else
  {
    *(_WORD *)(v28 + 1674) = v5;
    if ( v45 )
      v46 = *(_DWORD *)(v28 + 2204) == 1;
    else
      v46 = _InterlockedCompareExchange((volatile signed __int32 *)(v28 + 2204), 1, 0) == 1;
    if ( v46 )
    {
      v47 = v123;
      *(_QWORD *)&v113[1] = v123;
      v4 = v114;
    }
    else
    {
      if ( (unsigned __int8)UlCheckOpaqueSendFlags(v28, DWORD2(v122), 0)
        && ((WORD4(v122) & 0x100) == 0 || (BYTE8(v122) & 1) != 0) )
      {
        ChunkInfo = 0;
        v47 = v123;
        *(_QWORD *)&v113[1] = v123;
        v4 = v114;
        goto LABEL_91;
      }
      v47 = v123;
      *(_QWORD *)&v113[1] = v123;
      v4 = v114;
    }
  }
  ChunkInfo = -1073741811;
LABEL_91:
  v101 = ChunkInfo;
  if ( ChunkInfo < 0 )
  {
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(75, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v52 = 0;
  }
  else
  {
    LOBYTE(v107) = Irp->RequestorMode;
    v48 = *(_QWORD *)(v28 + 24);
    ChunkInfo = 0;
    v126 = 0;
    if ( v45 )
    {
      if ( *(_DWORD *)(v48 + 416) )
      {
        ChunkInfo = -1073741254;
        v126 = -1073741254;
      }
    }
    else
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(v28 + 2208), 1, 0) == 1 )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v48 + 464, 0);
        if ( *(_DWORD *)(v48 + 416) )
        {
          v46 = _InterlockedCompareExchange((volatile signed __int32 *)(v48 + 448), 1, 0) == 1;
          *(_QWORD *)&v113[1] = v123;
          if ( v46 )
          {
            ChunkInfo = -1073741254;
            v126 = -1073741254;
          }
          else
          {
            ChunkInfo = UlLogZombieConnection(v28, v48, v123, (unsigned __int8)v107);
            v126 = ChunkInfo;
          }
        }
        else
        {
          *(_QWORD *)&v113[1] = v123;
        }
        ExReleasePushLockExclusiveEx(v48 + 464, 0);
        KeLeaveCriticalRegion();
        v47 = *(_OWORD **)&v113[1];
      }
      else
      {
        v47 = v123;
        *(_QWORD *)&v113[1] = v123;
      }
      v4 = v114;
    }
    v101 = ChunkInfo;
    if ( ChunkInfo >= 0 )
    {
      if ( v119 && v47 && *(_DWORD *)(v28 + 2204) == 1 )
      {
        ChunkInfo = UlCaptureUserLogData(v47, v28, v119 + 320);
        v101 = ChunkInfo;
        if ( ChunkInfo < 0 )
        {
          if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
            WPP_SF_D(77, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
          v52 = 0;
          goto LABEL_247;
        }
        LODWORD(v47) = v113[1];
      }
      if ( v103 )
      {
        v49 = *(_QWORD *)(v28 + 2464);
        if ( v49 )
        {
          v50 = *(_QWORD *)(*(_QWORD *)(v28 + 24) + 952LL);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v49 + 24), 0xFFFFFFFF) == 1 )
          {
            v51 = (_QWORD *)(v49 + 32);
            v145 = 0;
            if ( *v51 || v51[2] || v51[4] )
              UlBugCheckEx(1u, (ULONG_PTR)v51, (ULONG_PTR)"minio\\http\\sys\\flowrate.h", 0x69u);
            if ( KeGetCurrentIrql() )
            {
              LODWORD(v99) = -1;
              LOBYTE(v5) = 1;
              UlThreadPoolEnqueueWorkItem(0, v51, UlpFlCleanupFlowRateInfoWorker, v5, v50, v99);
            }
            else
            {
              UxPodAttachThread(v50, &v145);
              UlpFlCleanupFlowRateInfoWorker(v51);
              UxPodDetachThread(&v145);
            }
          }
          *(_QWORD *)(v28 + 2464) = 0;
          *(_QWORD *)&v113[1] = v123;
          v4 = v114;
        }
        ChunkInfo = UlFlCaptureFlowRateInfo(
                      *(_QWORD *)(*(_QWORD *)(v28 + 24) + 960LL),
                      (_DWORD)v116,
                      (int)v28 + 2464,
                      (int)v28 + 72,
                      v102,
                      v112,
                      0);
        v101 = ChunkInfo;
        if ( ChunkInfo < 0 )
        {
          v52 = 0;
          goto LABEL_247;
        }
        LODWORD(v47) = v113[1];
      }
      v52 = 0;
      if ( (WORD4(v122) & 0x100) != 0 )
      {
        v92 = *(_QWORD *)(v4 + 24);
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
          WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v92 + 384, 47, 0, 0, 0, 0);
        HIDWORD(v99) = 0;
        v98 = 0;
        ChunkInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(v92 + 392) + 120LL))(
                      *(_QWORD *)(v92 + 384),
                      47,
                      0);
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
          WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
        v101 = ChunkInfo;
        if ( ChunkInfo < 0 )
        {
          v52 = 1;
          goto LABEL_247;
        }
        LODWORD(v47) = v113[1];
      }
      if ( v104 )
      {
        ChunkInfo = UlFastSendHttpResponse(
                      (_DWORD)v116,
                      (_DWORD)v47,
                      (_DWORD)P,
                      1,
                      *((_DWORD *)P + 4),
                      0,
                      0,
                      DWORD2(v122),
                      v4,
                      *(_DWORD *)(*(_QWORD *)(v115 + 8) + 276LL),
                      (__int64)Irp,
                      Irp->RequestorMode,
                      0);
        v101 = ChunkInfo;
        goto LABEL_247;
      }
      if ( !(unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(v4 + 24), Irp) )
      {
        ChunkInfo = -1073741536;
        v101 = -1073741536;
        goto LABEL_247;
      }
      *(_QWORD *)(v119 + 400) = Irp;
      v83 = v119;
      v119 = 0;
      if ( v100 )
        *(_BYTE *)(v83 + 50) = UlpSetResponseCacheClassification(v4, v83, *((_QWORD *)&v121 + 1));
      v84 = v83;
      v85 = v4;
      if ( v105 )
      {
        ChunkInfo = UlCacheAndSendResponse(v4, v83, v115, DWORD2(v121), (_DWORD)v98, v83, (__int64)v106);
        v101 = ChunkInfo;
        if ( ChunkInfo < 0 || v106[0] )
        {
LABEL_245:
          if ( ChunkInfo != 259 )
          {
            UlpRestartSendHttpResponseIoctl(v83, (unsigned int)ChunkInfo, 0);
            v52 = 1;
            ChunkInfo = 259;
            v101 = 259;
          }
          goto LABEL_247;
        }
        v84 = v83;
        v85 = v4;
      }
      v101 = UlSendHttpResponse(v85, v84, (unsigned int)UlpRestartSendHttpResponseIoctl, v83, 0);
      ChunkInfo = v101;
      goto LABEL_245;
    }
    if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
      WPP_SF_D(76, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
    v52 = 0;
  }
LABEL_247:
  if ( LOBYTE(v113[0]) )
    ExFreePoolWithTag(P, 0);
  if ( v102 )
    ExFreePoolWithTag(v116, 0);
  if ( v4 )
  {
    if ( !v106[0] && ChunkInfo != -1073741766 )
    {
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_qqq(42, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v4, *(_QWORD *)(v4 + 64), 0);
      v128 = (volatile signed __int32 ***)&v127;
      v127 = (volatile signed __int32 *)&v127;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v4 + 2784, 0);
      v86 = (volatile signed __int32 **)(v4 + 2768);
      v87 = v128;
      if ( *((volatile signed __int32 ***)v127 + 1) != &v127
        || *v128 != &v127
        || *((volatile signed __int32 ***)*v86 + 1) != v86
        || **(volatile signed __int32 ****)(v4 + 2776) != v86
        || (*v128 = v86,
            v128 = *(volatile signed __int32 ****)(v4 + 2776),
            **(_QWORD **)(v4 + 2776) = &v127,
            *(_QWORD *)(v4 + 2776) = v87,
            v88 = *v86,
            *((volatile signed __int32 ***)*v86 + 1) != v86)
        || *v87 != v86 )
      {
LABEL_257:
        __fastfail(3u);
      }
      *v87 = (volatile signed __int32 **)v88;
      *((_QWORD *)v88 + 1) = v87;
      *(_QWORD *)(v4 + 2776) = v4 + 2768;
      *v86 = (volatile signed __int32 *)v86;
      *(_BYTE *)(v4 + 2792) = 1;
      ExReleasePushLockExclusiveEx(v4 + 2784, 0);
      KeLeaveCriticalRegion();
      while ( 1 )
      {
        v89 = v127;
        if ( v127 == (volatile signed __int32 *)&v127 )
          break;
        v93 = *(volatile signed __int32 **)v127;
        if ( *((volatile signed __int32 ***)v127 + 1) != &v127 || *((volatile signed __int32 **)v93 + 1) != v127 )
          goto LABEL_257;
        v127 = *(volatile signed __int32 **)v127;
        *((_QWORD *)v93 + 1) = &v127;
        *(_QWORD *)v89 = 0;
        *((_QWORD *)v89 + 1) = 0;
        if ( _InterlockedExchangeAdd(v89 - 6, 0xFFFFFFFF) == 1 )
          UxDuoFreeDeclarePushParameters((PVOID)(v89 - 6));
      }
      if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
        WPP_SF_(43, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
      ChunkInfo = v101;
      v4 = v114;
    }
    if ( (int)(ChunkInfo + 0x80000000) >= 0 && ChunkInfo != -1073741766 || v52 )
      UlCloseConnection(*(_QWORD *)(v4 + 24));
    if ( !v109 )
      v109 = *(_WORD *)(v4 + 1674);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 48), 0xFFFFFFFF) == 1 )
      UlpQueueFreeHttpRequest(v114);
    ChunkInfo = v101;
  }
  v90 = (_QWORD *)v119;
  if ( v119 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v119 + 20), 0xFFFFFFFF) == 1 )
    {
      v94 = *(_QWORD *)(*(_QWORD *)(v90[3] + 24LL) + 952LL);
      v95 = v90 + 52;
      v146 = 0;
      if ( v90[52] || v90[54] || v90[56] )
        UlBugCheckEx(1u, (ULONG_PTR)(v90 + 52), (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x317u);
      if ( KeGetCurrentIrql() )
      {
        LODWORD(v99) = -1;
        LOBYTE(v5) = 1;
        UlThreadPoolEnqueueWorkItem(0, v90 + 52, UlDestroyCapturedResponse, v5, v94, v99);
      }
      else
      {
        UxPodAttachThread(v94, &v146);
        UlDestroyCapturedResponse(v95);
        UxPodDetachThread(&v146);
      }
    }
    ChunkInfo = v101;
  }
  if ( BYTE1(v113[0]) && ((ChunkInfo + 0x80000000) & 0x80000000) == 0 && ChunkInfo != -1073741766 )
  {
    v96 = *(_QWORD *)(v115 + 8);
    v97 = *(_QWORD *)(v96 + 328);
    if ( *(_BYTE *)(v97 + 1568) )
    {
      v151 = 0;
      v152 = 0;
      v153 = 0;
      v149[2] = v97;
      v149[0] = &v157;
      v149[1] = 0;
      v150 = 0;
      LOWORD(v98) = v109;
      McTemplateK0xh_UlEtwWriteEventWrapper(v96, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, v149, v131, v98);
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000) != 0 )
    {
      LOWORD(v98) = v109;
      WPP_SF_diH(78, v90, (unsigned int)ChunkInfo, v131, v98);
    }
  }
  if ( ChunkInfo != 259 )
  {
    Irp->IoStatus.Status = ChunkInfo;
    IofCompleteRequest(Irp, 0);
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(79, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
  return (unsigned int)ChunkInfo;
}

```

## disassembly

```asm
0x1c00b4cf0  mov     r11, rsp
0x1c00b4cf3  mov     [r11+18h], rbx
0x1c00b4cf7  mov     [r11+20h], rsi
0x1c00b4cfb  push    rdi
0x1c00b4cfc  push    r12
0x1c00b4cfe  push    r13
0x1c00b4d00  push    r14
0x1c00b4d02  push    r15
0x1c00b4d04  sub     rsp, 440h
0x1c00b4d0b  mov     rax, cs:__security_cookie
0x1c00b4d12  xor     rax, rsp
0x1c00b4d15  mov     [rsp+468h+var_38], rax
0x1c00b4d1d  mov     rdi, rdx
0x1c00b4d20  mov     r13, rcx
0x1c00b4d23  mov     [rsp+468h+var_2E0], rcx
0x1c00b4d2b  xorps   xmm0, xmm0
0x1c00b4d2e  xor     eax, eax
0x1c00b4d30  mov     [r11-3C8h], rax
0x1c00b4d37  movups  [rsp+468h+var_390], xmm0
0x1c00b4d3f  movups  [rsp+468h+var_380], xmm0
0x1c00b4d47  movups  [rsp+468h+var_370], xmm0
0x1c00b4d4f  mov     [r11-360h], rax
0x1c00b4d56  xor     r14d, r14d
0x1c00b4d59  mov     [r11-398h], r14
0x1c00b4d60  mov     [r11-3B0h], r14
0x1c00b4d67  mov     r15d, r14d
0x1c00b4d6a  mov     [r11-3C0h], r14
0x1c00b4d71  mov     [rsp+468h+var_3DC], al
0x1c00b4d78  mov     [rsp+468h+var_3DD], al
0x1c00b4d7f  mov     [rsp+468h+var_3A8], eax
0x1c00b4d86  mov     [rsp+468h+var_3D0], al
0x1c00b4d8d  mov     [r11-3DEh], r14b
0x1c00b4d94  mov     [r11-3CFh], r14b
0x1c00b4d9b  mov     [r11-3B8h], r14
0x1c00b4da2  mov     [r11-3CBh], r14b
0x1c00b4da9  mov     [r11-328h], r14
0x1c00b4db0  mov     [r11-3E0h], r14b
0x1c00b4db7  mov     [r11-178h], r14d
0x1c00b4dbe  movups  [rsp+468h+var_170], xmm0
0x1c00b4dc6  mov     [r11-160h], rax
0x1c00b4dcd  xor     edx, edx; Val
0x1c00b4dcf  mov     r8d, 120h; Size
0x1c00b4dd5  lea     rcx, [r11-158h]; void *
0x1c00b4ddc  call    memset
0x1c00b4de1  mov     [rsp+468h+P], r14
0x1c00b4de9  mov     [rsp+468h+var_3CC], r14b
0x1c00b4df1  xor     edx, edx; Val
0x1c00b4df3  mov     r8d, 90h; Size
0x1c00b4df9  lea     rcx, [rsp+468h+var_2D8]; void *
0x1c00b4e01  call    memset
0x1c00b4e06  mov     [rsp+468h+var_3D4], r14w
0x1c00b4e0f  xorps   xmm0, xmm0
0x1c00b4e12  movups  [rsp+468h+var_188], xmm0
0x1c00b4e1a  mov     [rsp+468h+var_320], r14d
0x1c00b4e22  mov     [rsp+468h+var_3DF], r14b
0x1c00b4e2a  mov     [rsp+468h+var_3E8], r14b
0x1c00b4e32  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b4e3c  jnz     loc_1C00E8FB8
0x1c00b4e42  mov     rcx, r13; Irp
0x1c00b4e45  call    cs:__imp_IoIs32bitProcess
0x1c00b4e4c  nop     dword ptr [rax+rax+00h]
0x1c00b4e51  mov     [rsp+468h+var_3CE], al
0x1c00b4e58  mov     rbx, [rdi+30h]
0x1c00b4e5c  mov     esi, r14d
0x1c00b4e5f  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b4e69  jnz     loc_1C00E8FD5
0x1c00b4e6f  mov     [rsp+468h+var_3B8], r14
0x1c00b4e77  mov     rcx, [rbx+8]
0x1c00b4e7b  mov     rax, cs:UxDriverObject
0x1c00b4e82  cmp     [rcx+8], rax
0x1c00b4e86  jnz     loc_1C00E901E
0x1c00b4e8c  cmp     qword ptr [rbx+20h], 50505041h
0x1c00b4e94  jnz     loc_1C00E901E
0x1c00b4e9a  mov     rbx, [rbx+18h]
0x1c00b4e9e  test    rbx, rbx
0x1c00b4ea1  jz      loc_1C00E9014
0x1c00b4ea7  cmp     dword ptr [rbx+18h], 50416C55h
0x1c00b4eae  jnz     loc_1C00E9014
0x1c00b4eb4  mov     rax, [rbx+8]
0x1c00b4eb8  test    rax, rax
0x1c00b4ebb  jz      loc_1C00E9014
0x1c00b4ec1  cmp     dword ptr [rax+78h], 4F416C55h
0x1c00b4ec8  jnz     loc_1C00E9014
0x1c00b4ece  mov     eax, [rbx+28h]
0x1c00b4ed1  test    al, 1
0x1c00b4ed3  jz      loc_1C00E9000
0x1c00b4ed9  call    cs:__imp_PsGetCurrentServerSilo
0x1c00b4ee0  nop     dword ptr [rax+rax+00h]
0x1c00b4ee5  mov     rcx, [rbx+8]
0x1c00b4ee9  cmp     [rcx+140h], rax
0x1c00b4ef0  jnz     loc_1C00E900A
0x1c00b4ef6  mov     [rsp+468h+var_3B8], rbx
0x1c00b4efe  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b4f08  jnz     loc_1C00E9028
0x1c00b4f0e  mov     [rsp+468h+var_3E4], esi
0x1c00b4f15  test    esi, esi
0x1c00b4f17  js      loc_1C00E9156
0x1c00b4f1d  mov     r12d, [rdi+10h]
0x1c00b4f21  mov     rbx, [rdi+20h]
0x1c00b4f25  movzx   edi, byte ptr [r13+40h]
0x1c00b4f2a  mov     esi, r14d
0x1c00b4f2d  mov     [rsp+468h+var_358], r14d
0x1c00b4f35  test    rbx, rbx
0x1c00b4f38  jz      loc_1C00B5863
0x1c00b4f3e  mov     rcx, r13; Irp
0x1c00b4f41  call    cs:__imp_IoIs32bitProcess
0x1c00b4f48  nop     dword ptr [rax+rax+00h]
0x1c00b4f4d  test    al, al
0x1c00b4f4f  jnz     loc_1C00B5896
0x1c00b4f55  cmp     r12d, 38h ; '8'
0x1c00b4f59  jb      loc_1C00B593F
0x1c00b4f5f  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 100h
0x1c00b4f69  jnz     loc_1C00B5972
0x1c00b4f6f  mov     rax, rbx
0x1c00b4f72  and     eax, 7
0x1c00b4f75  test    dil, dil
0x1c00b4f78  jz      loc_1C00B59BB
0x1c00b4f7e  test    rax, rax
0x1c00b4f81  jnz     loc_1C00B59A7
0x1c00b4f87  lea     rcx, [rbx+38h]
0x1c00b4f8b  mov     rax, cs:MmUserProbeAddress
0x1c00b4f92  mov     rdx, [rax]
0x1c00b4f95  cmp     rcx, rdx
0x1c00b4f98  ja      loc_1C00B59B3
0x1c00b4f9e  cmp     rcx, rbx
0x1c00b4fa1  jb      loc_1C00B59B3
0x1c00b4fa7  movups  xmm0, xmmword ptr [rbx]
0x1c00b4faa  movups  [rsp+468h+var_390], xmm0
0x1c00b4fb2  movups  xmm1, xmmword ptr [rbx+10h]
0x1c00b4fb6  movups  [rsp+468h+var_380], xmm1
0x1c00b4fbe  movups  xmm0, xmmword ptr [rbx+20h]
0x1c00b4fc2  movups  [rsp+468h+var_370], xmm0
0x1c00b4fca  movsd   xmm1, qword ptr [rbx+30h]
0x1c00b4fcf  movsd   [rsp+468h+var_360], xmm1
0x1c00b4fd8  mov     rax, [rsp+468h+var_360]
0x1c00b4fe0  mov     qword ptr [rsp+468h+var_3CC+4], rax
0x1c00b4fe8  mov     rdi, qword ptr [rsp+468h+var_390]
0x1c00b4ff0  mov     [rsp+468h+var_3E4], esi
0x1c00b4ff7  test    esi, esi
0x1c00b4ff9  js      loc_1C00B59D5
0x1c00b4fff  mov     rax, [rsp+468h+var_3B8]
0x1c00b5007  mov     rbx, [rax+8]
0x1c00b500b  movzx   r12d, byte ptr [r13+40h]
0x1c00b5010  mov     esi, r14d
0x1c00b5013  mov     [rsp+468h+var_354], r14d
0x1c00b501b  mov     [rsp+468h+var_3E0], sil
0x1c00b5023  test    rdi, rdi
0x1c00b5026  jz      loc_1C00B59E3
0x1c00b502c  mov     rcx, r13; Irp
0x1c00b502f  call    cs:__imp_IoIs32bitProcess
0x1c00b5036  nop     dword ptr [rax+rax+00h]
0x1c00b503b  movzx   ecx, word ptr [rbx+114h]
0x1c00b5042  movzx   r9d, r12b
0x1c00b5046  test    al, al
0x1c00b5048  jnz     loc_1C00B5A16
0x1c00b504e  mov     r8d, 8
0x1c00b5054  cmp     cx, 2
0x1c00b5058  mov     rcx, rdi
0x1c00b505b  jb      loc_1C00B5859
0x1c00b5061  mov     edx, 238h
0x1c00b5066  call    UlProbeForRead
0x1c00b506b  mov     [rsp+468h+var_3B0], rdi
0x1c00b5073  mov     [rsp+468h+var_3E4], esi
0x1c00b507a  test    esi, esi
0x1c00b507c  js      loc_1C00B5D5F
0x1c00b5082  lea     rax, [rsp+468h+var_3CC]
0x1c00b508a  mov     [rsp+468h+var_430], rax; __int64
0x1c00b508f  lea     rax, [rsp+468h+P]
0x1c00b5097  mov     [rsp+468h+var_438], rax; __int64
0x1c00b509c  lea     rax, [rsp+468h+var_178]
0x1c00b50a4  mov     [rsp+468h+var_440], rax; P
0x1c00b50a9  mov     r9, qword ptr [rsp+468h+var_380]
0x1c00b50b1  movzx   r8d, word ptr [rsp+468h+var_390+8]
0x1c00b50ba  movzx   edx, byte ptr [r13+40h]
0x1c00b50bf  mov     rcx, r13; Irp
0x1c00b50c2  call    UlpGetChunkInfo
0x1c00b50c7  mov     esi, eax
0x1c00b50c9  mov     [rsp+468h+var_3E4], eax
0x1c00b50d0  test    eax, eax
0x1c00b50d2  js      loc_1C00B5D6D
0x1c00b50d8  movzx   eax, byte ptr [r13+40h]
0x1c00b50dd  mov     esi, r14d
0x1c00b50e0  mov     [rsp+468h+var_31C], r14d
0x1c00b50e8  mov     rbx, qword ptr [rsp+468h+var_3CC+4]
0x1c00b50f0  test    rbx, rbx
0x1c00b50f3  jnz     loc_1C00B5D9A
0x1c00b50f9  mov     [rsp+468h+var_3E4], esi
0x1c00b5100  test    esi, esi
0x1c00b5102  js      loc_1C00B6000
0x1c00b5108  mov     eax, dword ptr [rsp+468h+var_370+8]
0x1c00b510f  and     eax, 2
0x1c00b5112  mov     dword ptr [rsp+468h+Size], eax
0x1c00b5119  jnz     loc_1C00B600E
0x1c00b511f  mov     al, 1
0x1c00b5121  mov     [rsp+468h+var_3CC+1], al
0x1c00b5128  test    al, al
0x1c00b512a  jz      loc_1C00B51C2
0x1c00b5130  mov     r9, qword ptr [rsp+468h+var_370]
0x1c00b5138  mov     [rsp+468h+var_328], r9
0x1c00b5140  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1c00b5147  movups  [rsp+468h+var_188], xmm0
0x1c00b514f  mov     qword ptr [rsp+468h+var_188], r9
0x1c00b5157  mov     rax, [rsp+468h+var_3B8]
0x1c00b515f  mov     rcx, [rax+8]
0x1c00b5163  mov     rax, [rcx+148h]
0x1c00b516a  cmp     byte ptr [rax+620h], 0
0x1c00b5171  jz      short loc_1C00B51C2
0x1c00b5173  xorps   xmm0, xmm0
0x1c00b5176  movups  [rsp+468h+var_1C8], xmm0
0x1c00b517e  movups  [rsp+468h+var_1B8], xmm0
0x1c00b5186  mov     qword ptr [rsp+468h+var_1B8], rax
0x1c00b518e  lea     rax, [rsp+468h+var_188]
0x1c00b5196  mov     qword ptr [rsp+468h+var_1C8], rax
0x1c00b519e  mov     qword ptr [rsp+468h+var_1C8+8], r14
0x1c00b51a6  mov     byte ptr [rsp+468h+var_1B8+8], 0
0x1c00b51ae  lea     r8, [rsp+468h+var_1C8]
0x1c00b51b6  lea     rdx, HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY
0x1c00b51bd  call    McTemplateK0p_UlEtwWriteEventWrapper
0x1c00b51c2  test    dword ptr cs:WPP_MAIN_CB.Queue, 8000h
0x1c00b51cc  jnz     loc_1C00B6015
0x1c00b51d2  mov     rbx, [rsp+468h+var_3B8]
0x1c00b51da  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b51e4  jnz     loc_1C00B6034
0x1c00b51ea  mov     [rsp+468h+var_440], rbx
0x1c00b51ef  mov     rcx, qword ptr [rsp+468h+var_370]
0x1c00b51f7  call    UxGetObjectFromOpaqueIdEx
0x1c00b51fc  mov     rdi, rax
0x1c00b51ff  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00b5209  jnz     loc_1C00B6055
0x1c00b520f  mov     r15, rdi
0x1c00b5212  mov     [rsp+468h+var_3C0], rdi
0x1c00b521a  test    rdi, rdi
0x1c00b521d  jz      loc_1C00B607C
0x1c00b5223  mov     r12d, dword ptr [rsp+468h+var_380+8]
0x1c00b522b  cmp     r12d, 3
0x1c00b522f  jge     loc_1C00B60B4
0x1c00b5235  test    r12d, r12d
0x1c00b5238  jnz     loc_1C00B5822
0x1c00b523e  mov     rax, [rsp+468h+var_3B8]
0x1c00b5246  mov     r10, [rax+8]
0x1c00b524a  mov     ebx, [r10+114h]
0x1c00b5251  mov     [rsp+468h+var_320], ebx
0x1c00b5258  cmp     bx, 2
0x1c00b525c  jb      short loc_1C00B52AE
0x1c00b525e  movzx   eax, [rsp+468h+var_3CE]
0x1c00b5266  movzx   ecx, [rsp+468h+var_3E0]
0x1c00b526e  lea     rdx, [rsp+468h+var_3DF]
0x1c00b5276  mov     [rsp+468h+var_438], rdx
0x1c00b527b  mov     dword ptr [rsp+468h+var_440], eax
0x1c00b527f  mov     dword ptr [rsp+468h+var_448], ecx
0x1c00b5283  xor     r9d, r9d
0x1c00b5286  xor     r8d, r8d
0x1c00b5289  mov     rdx, [rsp+468h+var_3B0]
0x1c00b5291  mov     rcx, [r10+148h]
0x1c00b5298  call    UlFlCaptureFlowRateInfo
0x1c00b529d  mov     esi, eax
0x1c00b529f  mov     [rsp+468h+var_3E4], eax
0x1c00b52a6  test    eax, eax
0x1c00b52a8  js      loc_1C00B60EC
0x1c00b52ae  cmp     qword ptr [rdi+9A8h], 0
0x1c00b52b6  jnz     loc_1C00B60FA
0x1c00b52bc  mov     [rsp+468h+var_3E8], 0
0x1c00b52c4  cmp     byte ptr [rsp+468h+var_3A8], 0
0x1c00b52cc  jnz     loc_1C00B5846
0x1c00b52d2  cmp     [rsp+468h+var_3E8], 0
0x1c00b52da  jnz     loc_1C00B618E
0x1c00b52e0  cmp     [rsp+468h+var_3DD], 0
0x1c00b52e8  jnz     loc_1C00B5429
0x1c00b52ee  cmp     [rsp+468h+var_3DF], 0
0x1c00b52f6  jnz     loc_1C00B5429
0x1c00b52fc  mov     eax, dword ptr [rsp+468h+var_370+8]
0x1c00b5303  test    al, 4
0x1c00b5305  jnz     loc_1C00B5429
0x1c00b530b  test    al, 20h
0x1c00b530d  jnz     loc_1C00B5429
0x1c00b5313  mov     rsi, [rdi+18h]
0x1c00b5317  mov     rax, [rsi+350h]
0x1c00b531e  mov     rcx, [rax+3C0h]
0x1c00b5325  cmp     dword ptr [rcx+104Ch], 0FFFFFFFFh
0x1c00b532c  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x1c00b5333  jnz     loc_1C00B61B4
0x1c00b5339  call    cs:__imp_KeReadStateEvent
0x1c00b5340  nop     dword ptr [rax+rax+00h]
0x1c00b5345  mov     ecx, [rsi+358h]
0x1c00b534b  mov     r12d, 10000h
0x1c00b5351  test    eax, eax
0x1c00b5353  jnz     loc_1C00B581A
0x1c00b5359  mov     edx, r12d
0x1c00b535c  cmp     ecx, r12d
0x1c00b535f  cmovb   edx, ecx
0x1c00b5362  mov     [rsp+468h+var_338], edx
0x1c00b5369  mov     rax, [rsi+350h]
0x1c00b5370  mov     rcx, [rax+3C0h]
0x1c00b5377  mov     eax, [rcx+1050h]
0x1c00b537d  cmp     eax, edx
0x1c00b537f  jbe     loc_1C00B61AC
0x1c00b5385  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x1c00b538c  call    cs:__imp_KeReadStateEvent
0x1c00b5393  nop     dword ptr [rax+rax+00h]
0x1c00b5398  mov     ecx, [rsi+358h]
  ... truncated ...
```
