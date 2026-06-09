# NtfsEncryptDecryptOnline

- ea: `0x1400cc78c`
- end: `0x1400ceb84`
- name: `NtfsEncryptDecryptOnline`
- size: `9208`
- prototype: ``
- caller_count: `1`
- callee_count: `67`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027af08`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000c450`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x14000e220`
- `0x1400100b0`
- `0x140010be0`
- `0x140012e70`
- `0x140015b90`
- `0x14001d8f0`
- `0x14001e2f0`
- `0x14001e810`
- `0x140020524`
- `0x14002066c`
- `0x140020de0`
- `0x140021590`
- `0x140021c30`
- `0x140024070`
- `0x140025bd0`
- `0x140025c10`
- `0x1400286d0`
- `0x14002b680`
- `0x14002bc00`
- `0x140030850`
- `0x140031410`
- `0x14003e5b4`
- `0x14004062c`
- `0x1400410a8`
- `0x14004601c`
- `0x140059370`
- `0x1400596c0`
- `0x1400cc78c`
- `0x1401250b0`
- `0x1401261d0`
- `0x140128d50`
- `0x14012be00`
- `0x14013cde0`
- `0x140140380`
- `0x140158af0`
- `0x140159768`
- `0x14015a570`
- `0x140160be0`
- `0x140160e90`
- `0x1401620c0`
- `0x140162370`
- `0x140163f78`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400cccce`
- `ntoskrnl!IoAllocateMdl` at `0x1400cccce`
- `ntoskrnl!IoFreeMdl` at `0x1400ce915`
- `ntoskrnl!IoFreeMdl` at `0x1402c0ba1`
- `ntoskrnl!IoFreeMdl` at `0x1400ce915`
- `ntoskrnl!IoFreeMdl` at `0x1402c0ba1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ccced`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ccced`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ccd01`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ccd01`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400ccb32`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400cd6fb`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400ccb32`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400cd6fb`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdb55`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdcb7`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdb55`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1400cdcb7`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdb6d`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdccf`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdb6d`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1400cdccf`
- `ntoskrnl!KeClearEvent` at `0x1400cceda`
- `ntoskrnl!KeClearEvent` at `0x1400cceda`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ccf22`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ccf22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccd17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce926`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c0bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ccd17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ce926`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c0bb2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ccc9f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ccc9f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cceb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ccfff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c07ae`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cceb0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ccfff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c07ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ccef9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cd016`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c07c8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ccef9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cd016`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c07c8`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400cdaea`
- `ntoskrnl!FsRtlLookupBaseMcbEntry` at `0x1400cdaea`

## pseudocode

```c
__int64 __fastcall NtfsEncryptDecryptOnline(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v5; // r15
  __int64 v8; // rbx
  __int64 v9; // r13
  __int64 v10; // r8
  char v11; // di
  __int64 v12; // rdx
  unsigned __int64 m; // rcx
  __int64 v14; // r8
  unsigned __int8 v15; // di
  int v16; // r12d
  char v17; // r9
  int v18; // r15d
  __int64 v19; // r9
  __int64 v20; // r11
  unsigned __int16 v21; // ax
  __int64 v22; // r8
  _DWORD *v23; // r12
  __int64 v24; // r8
  char v25; // r15
  int v26; // r10d
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  ULONG v30; // r12d
  PVOID PoolWithTag; // r15
  PVOID v32; // rax
  struct _MDL *v33; // rax
  struct _MDL *v34; // r12
  unsigned int v35; // r12d
  unsigned __int8 v36; // r15
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  char v40; // r15
  __int16 *Scb; // r12
  char v42; // r15
  __int64 v43; // r8
  char v44; // di
  LONGLONG *v45; // rbx
  int v46; // ecx
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // r8
  char v54; // di
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rbx
  int v59; // eax
  int v60; // edx
  __int64 v61; // rbx
  __int64 v62; // r8
  __int64 v63; // r9
  char v64; // r15
  __int64 v65; // rcx
  char v66; // di
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rcx
  char v71; // r15
  __int64 v72; // rax
  char v73; // di
  __int64 v74; // rdx
  bool v75; // zf
  int v76; // eax
  __int64 v77; // rcx
  __int64 v78; // r8
  int v79; // r12d
  int v80; // eax
  unsigned int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rcx
  char v86; // di
  char v87; // cl
  LONGLONG v88; // r12
  LONGLONG v89; // rdx
  int v90; // ebx
  unsigned int v91; // ebx
  int *v92; // rdx
  char v93; // di
  __int16 *v94; // rbx
  int v95; // eax
  char v96; // al
  int v97; // r9d
  int v98; // r8d
  __int64 v99; // rcx
  __int64 v100; // r9
  __int64 v101; // rax
  unsigned int v102; // eax
  __int64 v103; // rdx
  __int64 v104; // r9
  int v105; // eax
  __int64 v106; // r9
  __int64 v107; // rdx
  __int64 v108; // r8
  int v109; // eax
  __int64 v110; // rcx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 v113; // r8
  unsigned int i; // eax
  __int64 v115; // rcx
  char v116; // al
  __int64 v117; // rcx
  unsigned int v118; // r8d
  __int64 v119; // rdx
  __int64 v120; // r9
  unsigned int k; // eax
  __int64 v122; // rax
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  PVOID v126; // r15
  unsigned int v127; // eax
  __int64 v128; // rdx
  __int64 n; // rcx
  int SectorCountFromStartingLbn; // [rsp+C0h] [rbp-2B0h]
  int Index; // [rsp+C8h] [rbp-2A8h]
  int Indexb; // [rsp+C8h] [rbp-2A8h]
  int Indexa; // [rsp+C8h] [rbp-2A8h]
  int Indexc; // [rsp+C8h] [rbp-2A8h]
  size_t Size; // [rsp+D0h] [rbp-2A0h]
  __int64 v137; // [rsp+118h] [rbp-258h] BYREF
  int v138; // [rsp+120h] [rbp-250h]
  int v139; // [rsp+124h] [rbp-24Ch]
  int v140; // [rsp+128h] [rbp-248h]
  char v141; // [rsp+12Ch] [rbp-244h]
  int v142; // [rsp+130h] [rbp-240h]
  PVOID P; // [rsp+138h] [rbp-238h] BYREF
  PMDL Mdl; // [rsp+140h] [rbp-230h] BYREF
  int v145; // [rsp+148h] [rbp-228h]
  __int64 SectorCountFromLbn; // [rsp+150h] [rbp-220h] BYREF
  int v147; // [rsp+158h] [rbp-218h]
  unsigned int v148; // [rsp+15Ch] [rbp-214h]
  int v149; // [rsp+160h] [rbp-210h]
  __int16 *v150; // [rsp+168h] [rbp-208h]
  signed int v151; // [rsp+170h] [rbp-200h]
  __int64 v152; // [rsp+178h] [rbp-1F8h]
  int *v153; // [rsp+180h] [rbp-1F0h]
  __int16 v154; // [rsp+188h] [rbp-1E8h]
  LONGLONG v155; // [rsp+190h] [rbp-1E0h]
  __int64 v156; // [rsp+198h] [rbp-1D8h] BYREF
  _DWORD *v157; // [rsp+1A0h] [rbp-1D0h]
  __int64 v158; // [rsp+1A8h] [rbp-1C8h]
  unsigned int v159; // [rsp+1B0h] [rbp-1C0h]
  __int64 v160[2]; // [rsp+1B8h] [rbp-1B8h] BYREF
  int v161; // [rsp+1C8h] [rbp-1A8h] BYREF
  __int64 Lbn; // [rsp+1D0h] [rbp-1A0h] BYREF
  __int64 v163; // [rsp+1D8h] [rbp-198h] BYREF
  __int64 v164; // [rsp+1E0h] [rbp-190h] BYREF
  __int64 v165; // [rsp+1E8h] [rbp-188h]
  LONGLONG v166; // [rsp+1F0h] [rbp-180h] BYREF
  LONGLONG j; // [rsp+1F8h] [rbp-178h]
  __int64 v168; // [rsp+200h] [rbp-170h]
  __int128 v169; // [rsp+208h] [rbp-168h] BYREF
  __int128 v170; // [rsp+218h] [rbp-158h]
  __int64 v171[12]; // [rsp+228h] [rbp-148h] BYREF
  LONGLONG v172; // [rsp+288h] [rbp-E8h]
  _OWORD v173[3]; // [rsp+298h] [rbp-D8h] BYREF
  __int64 v174; // [rsp+2C8h] [rbp-A8h]
  _DWORD v175[38]; // [rsp+2D8h] [rbp-98h] BYREF

  v5 = a4;
  LODWORD(v8) = 0;
  memset(v171, 0, 0x58u);
  v9 = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 96LL);
  v160[1] = v9;
  Mdl = 0;
  BYTE5(v137) = 0;
  P = 0;
  v139 = 0;
  v145 = 0;
  memset(v175, 0, 0x5Cu);
  v169 = 0;
  v170 = 0;
  v156 = 0;
  v149 = 0;
  SectorCountFromLbn = 0;
  Lbn = 0;
  LOBYTE(v138) = 0;
  v150 = 0;
  LODWORD(v137) = 128;
  *(_QWORD *)(a1 + 16) |= 0x80000000uLL;
  BYTE4(v137) = 1;
  v11 = 0x80;
  if ( *(_QWORD *)(a3 + 16) )
  {
    if ( (a5 & 0x2000000) != 0 || (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
    {
      LOBYTE(v10) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v10);
      v11 = -126;
    }
    else
    {
      LOBYTE(v10) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingShared(a1, a3, v10, 0);
      v11 = -124;
    }
    LOBYTE(v137) = v11;
  }
  NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
  v15 = v11 | 1;
  LOBYTE(v137) = v15;
  v16 = *(_DWORD *)(a3 + 512);
  v17 = 2;
  if ( (v16 & 2) != 0 )
  {
    v12 = 0;
    if ( v5 )
    {
      v18 = *(_DWORD *)(v5 + 4);
      if ( (v18 & 0x8000000) == 0 )
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
        {
          v19 = *(_QWORD *)(a3 + 192);
          v20 = *(_QWORD *)(v19 + 248);
          v21 = *(_WORD *)(v20 + 6);
          if ( v21 > 0x40u || (v21 & 1) != 0 )
          {
            v21 = 0;
            v142 = 0;
          }
          else
          {
            v142 = *(unsigned __int16 *)(v20 + 6);
          }
          LOWORD(j) = v21;
          v168 = v20 + 32;
          McTemplateU0ppwwpipdzdd_EtwWriteTransfer(
            *(_QWORD *)(a3 + 184),
            v21 >> 1,
            (unsigned int)KeGetCurrentThread(),
            v19,
            *(_WORD *)(v19 + 7872) >> 1,
            *(_QWORD *)(v19 + 7880),
            v21 >> 1,
            v20 + 32,
            *(_QWORD *)(a3 + 184),
            *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
            a3,
            *(_DWORD *)(a3 + 256),
            *(_QWORD *)(a3 + 272),
            v16,
            v18);
        }
        LODWORD(v8) = -1073741790;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_276;
        v22 = 809897;
LABEL_19:
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)v8, v22);
        goto LABEL_276;
      }
      v5 = a4;
    }
  }
  if ( (v15 & 4) != 0 )
  {
    v23 = (_DWORD *)(v5 + 8);
    if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 )
    {
      NtfsReleasePagingResourcePriv(m, a3, v14, 2);
      LOBYTE(v137) = v15 & 0xFB;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      LOBYTE(v137) = v15 & 0xFA;
      LOBYTE(v24) = *(_BYTE *)(a1 + 12) & 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v24);
      LOBYTE(v137) = v15 & 0xF8 | 2;
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      v15 = v15 & 0xF8 | 3;
      LOBYTE(v137) = v15;
      v17 = 2;
    }
  }
  else
  {
    v23 = (_DWORD *)(a4 + 8);
  }
  v25 = v15;
  if ( (*v23 & 0x100) == 0 )
  {
    SetFlagInterlocked(v23, 256);
    *(_DWORD *)(a3 + 448) += v26;
  }
  m = a3 + 200;
  v153 = (int *)(a3 + 200);
  if ( (v15 & (unsigned __int8)v17) != 0 )
  {
    if ( (*(_DWORD *)m & 0x2000000) != 0 )
    {
      v153 = (int *)(a3 + 200);
    }
    else
    {
      ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 16));
      v15 = v15 & 0xF9 | 4;
      LOBYTE(v137) = v25 & 0xF9 | 4;
      v25 = v137;
      m = a3 + 200;
    }
  }
  v27 = *(_DWORD *)(a3 + 512);
  if ( (v27 & 0x10000) != 0 )
  {
    LODWORD(v8) = -1073741202;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_276;
    v22 = 809978;
    goto LABEL_19;
  }
  if ( (v27 & 0x4000000) != 0 )
  {
    LODWORD(v8) = -1073741431;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_276;
    v22 = 809988;
    goto LABEL_19;
  }
  if ( (*(_DWORD *)m & 0x20) == 0 )
  {
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *(_QWORD *)(a3 + 184),
                             *(_QWORD *)(a3 + 184) + 8LL,
                             *(unsigned int *)(a3 + 256),
                             a3 + 264,
                             0,
                             0,
                             0,
                             0,
                             v171) )
    {
      LODWORD(v8) = 0;
      goto LABEL_276;
    }
    NtfsUpdateScbFromAttribute(a1, a3, v171[0]);
    NtfsCleanupAttributeContext(v28, v171);
    BYTE4(v137) = 0;
  }
  NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
  v15 = v25 & 0xFE;
  LOBYTE(v137) = v25 & 0xFE;
  NtfsCleanupAttributeContext(v29, v171);
  BYTE4(v137) = 0;
  v30 = *(_DWORD *)(v9 + 356);
  if ( v30 < 0x200000 )
    v30 = 0x200000;
  v151 = v30;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v30, 0x4446744Eu);
  P = PoolWithTag;
  v32 = 0;
  if ( PoolWithTag )
  {
    v33 = IoAllocateMdl(PoolWithTag, v30, 0, 0, 0);
    v34 = v33;
    Mdl = v33;
    if ( v33 )
    {
      MmBuildMdlForNonPagedPool(v33);
      MmMdlPageContentsState(v34, 1);
      v32 = PoolWithTag;
    }
    else
    {
      ExFreePoolWithTag(PoolWithTag, 0);
      v32 = 0;
      P = 0;
    }
  }
  if ( v32 )
  {
    v36 = v15;
  }
  else
  {
    v15 |= 0x40u;
    LOBYTE(v137) = v15;
    if ( (*(_DWORD *)(a3 + 512) & 8) != 0 )
      v35 = *(_DWORD *)(*(_QWORD *)(v9 + 5512) + 144LL);
    else
      v35 = dword_140095988;
    v151 = v35;
    v36 = v15;
    if ( v35 < *(_DWORD *)(v9 + 356) )
      v151 = *(_DWORD *)(v9 + 356);
  }
  NtfsInitializeIoContext(a1, v175, 0);
  if ( (v36 & 6) != 0 )
  {
    NtfsReleasePagingResourcePriv(v37, a3, v38, v39);
    v15 = v36 & 0xF9;
    LOBYTE(v137) = v36 & 0xF9;
  }
  v40 = BYTE1(v137);
  Scb = v150;
  while ( 1 )
  {
    if ( (_BYTE)v138 )
      goto LABEL_246;
    v155 = 0;
    v164 = 0;
    v160[0] = 0;
    NtfsPurgeFileRecordCache(a1);
    if ( (v15 & 0x20) != 0 )
    {
      memset(v173, 0, sizeof(v173));
      v174 = 0;
      BYTE6(v137) = 0;
      v42 = v40 & 0xF7;
      BYTE1(v137) = v42;
      NtfsAcquireCheckpointSynchronization(a1, v9, 18);
      HIBYTE(v137) = 0;
      LOBYTE(v43) = 1;
      NtfsAcquireSharedVcb(a1, v9, v43);
      v44 = v15 & 0xD7 | 8;
      LOBYTE(v137) = v44;
      v45 = (LONGLONG *)(a1 + 104);
      v46 = *(_DWORD *)(*(_QWORD *)(a1 + 104) + 4LL);
      if ( (v46 & 1) == 0 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221226094LL, 810202);
        NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 810202);
LABEL_300:
        v8 = 3221225865LL;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225865LL, 810211);
        NtfsRaiseStatusInternal(a1, -1073741431, 0, 0, 810211);
LABEL_303:
        if ( NtfsStatusDebugFlags
          && (unsigned int)v8 < 0xFFFFFFED
          && (_DWORD)v8 != -1073741802
          && (unsigned int)(v8 + 2147483643) > 1
          && (_DWORD)v8 != -1073741807
          && (_DWORD)v8 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v8, 810996);
        }
        NtfsRaiseStatusInternal(a1, v8, 0, 0, 810996);
LABEL_311:
        NtfsAttachCorruption_BadOrOrphanFRS(
          a1,
          v98 + 2,
          811006,
          v97,
          *(_QWORD *)(v8 + 184) + 8LL,
          *(_QWORD *)(v8 + 184),
          v98);
        NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA9000C5FFELL);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 811006);
        v105 = NtfsRaiseStatusInternal(
                 a1,
                 -1073741566,
                 (unsigned int)*(_QWORD *)(v8 + 184) + 8,
                 *(_QWORD *)(v8 + 184),
                 811006);
LABEL_314:
        if ( NtfsStatusDebugFlags
          && (unsigned int)v105 < 0xFFFFFFED
          && v105 != -1073741802
          && (unsigned int)(v105 + 2147483643) > 1
          && (_DWORD)v8 != -1073741807
          && (_DWORD)v8 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v8, 811172);
        }
        NtfsRaiseStatusInternal(a1, v8, 0, 0, 811172);
        __debugbreak();
        JUMPOUT(0x1400CEB84LL);
      }
      if ( (v46 & 0x20) != 0 )
        goto LABEL_300;
      ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 1064), 1u);
      *(_BYTE *)(v9 + 1281) = 1;
      if ( *(_WORD *)(*(_QWORD *)(v9 + 1272) + 4LL) )
      {
        KeClearEvent((PRKEVENT)(v9 + 1400));
        HIBYTE(v137) = 1;
        v45 = (LONGLONG *)(a1 + 104);
      }
      ExReleaseResourceLite((PERESOURCE)(v9 + 1064));
      if ( HIBYTE(v137) )
        KeWaitForSingleObject((PVOID)(v9 + 1400), Executive, 0, 0, 0);
      else
        v45 = (LONGLONG *)(a1 + 104);
      NtfsCheckpointVolume((_DWORD *)a1, v9, 1, 0, 0, 0, *(_QWORD *)(a1 + 200));
      LfsFlushToLsn(*(_QWORD *)(*v45 + 232), NtfsLargeMax);
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v47, deviosup_c23811, v9);
      }
      NtfsFreeRecentlyDeallocated((int *)a1, *v45, &NtfsLargeMax, 1);
      NtfsMarkUnusedContextPreTrimProcessing(a1, v48, v49, v50);
      NtfsPrepareToWaitForDeallocatedClustersToDrain(a1, v173);
      v40 = v42 | 8;
      BYTE1(v137) = v40;
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v51, deviosup_c23826, v9);
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(v9 + 1064), 1u);
      *(_BYTE *)(v9 + 1281) = 0;
      ExReleaseResourceLite((PERESOURCE)(v9 + 1064));
      NtfsReleaseCheckpointSynchronization(v52, v9, 18);
      BYTE6(v137) = (v44 & 8) != 0;
      NtfsWaitForDeallocatedClustersToDrainAfterPrepare(a1, v173, (char *)&v137 + 6);
      if ( BYTE6(v137) )
        NtfsReleaseVcb(a1, v9);
      v15 = v44 & 0xF7;
      LOBYTE(v137) = v15;
    }
    while ( 1 )
    {
      NtfsReleaseQuotaControlIfOwned(a1);
      LOBYTE(v53) = 1;
      NtfsAcquireSharedVcb(a1, v9, v53);
      v54 = v15 | 8;
      LOBYTE(v137) = v54;
      LOBYTE(v55) = 1;
      if ( (v40 & 4) != 0 )
      {
        NtfsAcquirePagingResourceExclusive(a1, a3, v55);
        v15 = v54 | 2;
      }
      else
      {
        NtfsAcquirePagingShared(a1, a3, v55, 0);
        v15 = v54 | 4;
      }
      LOBYTE(v137) = v15;
      LODWORD(v152) = *(_DWORD *)(a3 + 512);
      if ( (v152 & 0x10000) != 0 )
      {
        LODWORD(v8) = -1073741202;
        if ( NtfsStatusDebugFlags )
        {
          v56 = 810330;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      if ( (v152 & 0x4000000) != 0 )
      {
        LODWORD(v8) = -1073741431;
        if ( NtfsStatusDebugFlags )
        {
          v56 = 810340;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      if ( (v152 & 0x40) != 0 )
      {
        LODWORD(v8) = -1073741533;
        if ( NtfsStatusDebugFlags )
        {
          v56 = 810350;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      if ( (v152 & 2) != 0 )
      {
        if ( a4 )
        {
          v142 = *(_DWORD *)(a4 + 4);
          if ( (v142 & 0x8000000) == 0 )
          {
            if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
            {
              v57 = *(_QWORD *)(a3 + 192);
              v58 = *(_QWORD *)(v57 + 248);
              v59 = *(unsigned __int16 *)(v58 + 6);
              if ( (unsigned __int16)v59 > 0x40u || (v59 & 1) != 0 )
                v59 = 0;
              v149 = v59;
              LOWORD(v157) = v59;
              v158 = v58 + 32;
              McTemplateU0ppwwpipdwdd_EtwWriteTransfer(
                *(unsigned __int16 *)(a3 + 264) >> 1,
                (unsigned int)deviosup_c23931,
                (unsigned int)KeGetCurrentThread(),
                v57,
                *(_WORD *)(v57 + 7872) >> 1,
                *(_QWORD *)(v57 + 7880),
                (unsigned __int16)v59 >> 1,
                v58 + 32,
                *(_QWORD *)(a3 + 184),
                *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
                a3,
                *(_DWORD *)(a3 + 256),
                *(_WORD *)(a3 + 264) >> 1,
                *(_QWORD *)(a3 + 272),
                v152,
                v142,
                v137);
            }
            LODWORD(v8) = -1073741790;
            if ( NtfsStatusDebugFlags )
            {
              v56 = 810381;
              goto LABEL_81;
            }
            goto LABEL_82;
          }
        }
      }
      if ( *(_DWORD *)(a3 + 516) == 3 && *(_DWORD *)(a3 + 256) == 128 )
      {
        LODWORD(v8) = -1073740637;
        if ( NtfsStatusDebugFlags )
        {
          v56 = 810391;
          goto LABEL_81;
        }
        goto LABEL_82;
      }
      v60 = v151;
      v139 = v151;
      v145 = v151;
      if ( *(_QWORD *)(a3 + 632) + v151 >= *(__int64 *)(a3 + 40) )
      {
        v60 = -*(_DWORD *)(*(_QWORD *)(a3 + 192) + 356LL)
            & (*(_DWORD *)(a3 + 40) + *(_DWORD *)(*(_QWORD *)(a3 + 192) + 356LL) + ~*(_DWORD *)(a3 + 632));
        v145 = v60;
        if ( v60 > v151 )
          v60 = v151;
        v139 = v60;
        v145 = v60;
      }
      v61 = v60;
      j = v60;
      if ( (v15 & 4) == 0 )
        break;
      NtfsLockFsRtlHeader(a1, a3);
      v64 = v40 | 2;
      BYTE1(v137) = v64;
      v65 = v61 + *(_QWORD *)(a3 + 632);
      if ( v65 < *(_QWORD *)(a3 + 40) )
      {
        if ( (a5 & 0x2000000) != 0 )
        {
          memset(v171, 0, 0x58u);
          BYTE4(v137) = 1;
          NtfsAcquireSharedFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
          v66 = v15 | 1;
          LOBYTE(v137) = v66;
          LOBYTE(Index) = 0;
          if ( !(unsigned __int8)NtfsLookupInFileRecord(
                                   a1,
                                   *(_QWORD *)(a3 + 184),
                                   *(_QWORD *)(a3 + 184) + 8LL,
                                   128,
                                   &NtfsEfsBackupName,
                                   0,
                                   Index,
                                   0,
                                   0,
                                   v171) )
          {
            NtfsReleasePagingResourcePriv(v67, a3, v68, v69);
            v66 &= ~4u;
            LOBYTE(v137) = v66;
            v64 |= 0x14u;
            BYTE1(v137) = v64;
          }
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          v15 = v66 & 0xFE;
          LOBYTE(v137) = v15;
          NtfsCleanupAttributeContext(v70, v171);
          BYTE4(v137) = 0;
        }
      }
      else
      {
        NtfsReleasePagingResourcePriv(v65, a3, v62, v63);
        v15 &= ~4u;
        LOBYTE(v137) = v15;
        v64 |= 4u;
        BYTE1(v137) = v64;
      }
      NtfsUnlockFsRtlHeader(a1, a3);
      v40 = v64 & 0xFD;
      BYTE1(v137) = v40;
      if ( (v40 & 4) == 0 )
        break;
      if ( (v15 & 8) != 0 )
      {
        NtfsReleaseVcb(a1, v9);
        v15 &= ~8u;
        LOBYTE(v137) = v15;
      }
    }
    v71 = v40 & 0xFB;
    BYTE1(v137) = v71;
    LODWORD(v72) = a5 & 0x2000000;
    v142 = a5 & 0x2000000;
    if ( (a5 & 0x2000000) != 0 )
    {
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      v73 = v15 | 1;
      LOBYTE(v137) = v73;
      Scb = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (const UNICODE_STRING *)&NtfsEfsBackupName, 0, 0, 0);
      v150 = Scb;
      *((_DWORD *)Scb + 128) |= 0x800000u;
      NtfsCreateInternalAttributeStream(a1, (__int64)Scb, 0, 0, 0, 0);
      memset(v171, 0, 0x58u);
      BYTE4(v137) = 1;
      v74 = *((_QWORD *)Scb + 23);
      v157 = Scb + 256;
      LOBYTE(Indexb) = 0;
      v75 = (unsigned __int8)NtfsLookupInFileRecord(
                               a1,
                               v74,
                               v74 + 8,
                               *((unsigned int *)Scb + 64),
                               Scb + 132,
                               0,
                               Indexb,
                               0,
                               0,
                               v171) == 0;
      v76 = *((_DWORD *)Scb + 128);
      if ( v75 )
      {
        *v157 = v76 & 0xFFFFFF7F;
        NtfsCreateAttribute(a1, 0, 0, 0, 1, 0, 0);
        *((_DWORD *)Scb + 128) &= ~0x40u;
      }
      else
      {
        *v157 = v76 | 0x80;
        NtfsUpdateScbFromAttribute(a1, Scb, v171[0]);
        NtfsSnapshotScb(a1, Scb);
        *(_QWORD *)(*((_QWORD *)Scb + 62) + 96LL) = a1;
        if ( *(_BYTE *)(v171[0] + 8) )
          NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 1);
      }
      NtfsCheckpointCurrentTransaction(a1);
      NtfsCleanupAttributeContext(v77, v171);
      BYTE4(v137) = 0;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      v15 = v73 & 0xFE;
      LOBYTE(v137) = v15;
      v72 = NtfsReleaseQuotaControlIfOwned(a1);
    }
    if ( (v71 & 0x10) != 0 )
    {
      v72 = *(_QWORD *)(a3 + 632) + v139;
      if ( v72 < *(_QWORD *)(a3 + 40) )
      {
        ExConvertExclusiveToSharedLite(*(PERESOURCE *)(a3 + 16));
        v15 = v15 & 0xF9 | 4;
        LOBYTE(v137) = v15;
      }
    }
    v40 = v71 & 0xEF;
    BYTE1(v137) = v40;
    v8 = *(_QWORD *)(a3 + 40);
    v152 = v8;
    v78 = *(_QWORD *)(a3 + 632);
    if ( v78 < v8 )
      break;
    v165 = v8;
    LOBYTE(v72) = 1;
    v138 = v72;
    v141 = 1;
LABEL_203:
    NtfsReleaseQuotaControlIfOwned(a1);
    NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
    v15 |= 1u;
    LOBYTE(v137) = v15;
    if ( (_BYTE)v138 )
      v8 = -1;
    v104 = (unsigned __int8)v138;
    if ( !v142 )
      v104 = 0;
    v105 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64))&xmmword_1400957A0 + 1))(
             a1,
             *(_QWORD *)(a3 + 184),
             a3 + 264,
             v104,
             v8);
    LODWORD(v8) = v105;
    v140 = v105;
    if ( v105 < 0 )
      goto LABEL_314;
    LOBYTE(v106) = 1;
    NtfsPersistDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL, v106);
    BYTE5(v137) = 0;
    if ( (_BYTE)v138 )
    {
      v109 = a5;
      if ( (a5 & 0x4000000) != 0 )
      {
        NtfsDeleteEncryptionContext(a3, v107, v108);
        *(_QWORD *)(a3 + 632) = -1;
        v109 = a5;
      }
      else
      {
        *(_QWORD *)(a3 + 632) = 0;
      }
      *v153 &= ~v109;
    }
    else
    {
      *(_QWORD *)(a3 + 632) = v152;
    }
    *(_QWORD *)(a1 + 16) &= ~0x40000uLL;
    if ( (v40 & 2) != 0 )
    {
      NtfsUnlockFsRtlHeader(a1, a3);
      v40 &= ~2u;
      BYTE1(v137) = v40;
    }
    NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
    if ( P && (v15 & 0x40) != 0 )
    {
      NtfsDeleteMdlAndBuffer(v9, Mdl, P);
      v110 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      P = 0;
      Mdl = 0;
    }
    if ( (v40 & 1) != 0 )
    {
      NtfsReleaseRangeInternal(&v169);
      v40 &= ~1u;
      BYTE1(v137) = v40;
    }
    if ( Scb )
    {
      NtfsDeleteInternalAttributeStream(a1, (__int64)Scb, 1, 0);
      Scb = 0;
      v150 = 0;
    }
    if ( (v15 & 6) != 0 )
    {
      NtfsReleasePagingResourcePriv(v110, a3, v111, v112);
      v15 &= 0xF9u;
      LOBYTE(v137) = v15;
    }
    if ( (v15 & 1) != 0 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
      v15 &= ~1u;
      LOBYTE(v137) = v15;
    }
    if ( v142 )
    {
      LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
      if ( !(_BYTE)v138 )
        goto LABEL_243;
      NtfsReleaseQuotaControlIfOwned(a1);
      memset(v171, 0, 0x58u);
      BYTE4(v137) = 1;
      LOBYTE(v113) = 1;
      NtfsAcquirePagingResourceExclusive(a1, a3, v113);
      v159 = 0;
      for ( i = 0; ; ++i )
      {
        v159 = i;
        if ( i >= 2 )
          break;
        v115 = *(_QWORD *)(a1 + 8LL * i + 48);
        if ( !v115 || v115 == *(_QWORD *)(a3 + 184) )
        {
          *(_QWORD *)(a1 + 8LL * i + 48) = *(_QWORD *)(a3 + 184);
          break;
        }
      }
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
      Scb = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (const UNICODE_STRING *)&NtfsEfsBackupName, 0, 0, 0);
      v150 = Scb;
      *((_DWORD *)Scb + 128) |= 0x800000u;
      *((_DWORD *)Scb + 128) |= 0x80u;
      LOBYTE(Indexc) = 0;
      v116 = NtfsLookupInFileRecord(
               a1,
               *(_QWORD *)(a3 + 184),
               *(_QWORD *)(a3 + 184) + 8LL,
               128,
               &NtfsEfsBackupName,
               0,
               Indexc,
               0,
               0,
               v171);
      while ( v116 )
      {
        NtfsDeleteAttributeRecord(a1, *(_QWORD *)(a3 + 184), 7, v171);
        v118 = *((_DWORD *)Scb + 64);
        v119 = *((_QWORD *)Scb + 23);
        if ( v171[5] )
        {
          LODWORD(Size) = 0;
          v116 = NtfsLookupExternalAttribute(
                   a1,
                   v119,
                   v118,
                   (PCUNICODE_STRING)(Scb + 132),
                   0,
                   0,
                   0,
                   Size,
                   (__int64)v171);
        }
        else
        {
          LOBYTE(Index) = 0;
          v116 = NtfsLookupInFileRecord(a1, v119, 0, v118, Scb + 132, 0, Index, 0, 0, v171);
        }
      }
      NtfsCleanupAttributeContext(v117, v171);
      BYTE4(v137) = 0;
      NtfsCheckpointCurrentTransaction(a1);
      *((_DWORD *)Scb + 128) |= 0x40u;
      NtfsTeardownStructures(a1, (int)Scb, 0);
      *(_DWORD *)(a1 + 4) |= 0x40400u;
      NtfsExtendedCompleteRequestInternal(a1, 0, 0, 0, 1);
    }
    if ( (_BYTE)v138 )
      LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
LABEL_243:
    if ( (v15 & 8) != 0 )
    {
      NtfsReleaseVcb(a1, v9);
      v15 &= ~8u;
      LOBYTE(v137) = v15;
    }
  }
  if ( (v15 & 4) != 0 )
  {
    NtfsAcquireRange(a1, a3, v78, j, 0, (__int64)&v169);
    v40 |= 1u;
    BYTE1(v137) = v40;
  }
  if ( (*v153 & a5) == 0 )
    *v153 |= a5;
  *(_QWORD *)(a1 + 16) |= 0x40000uLL;
  v8 = *(_QWORD *)(a3 + 632);
  v152 = v8;
  v165 = v8;
  v79 = v139;
  while ( 2 )
  {
    LOBYTE(v80) = v138;
    while ( 1 )
    {
      if ( (_BYTE)v80 || v79 <= 0 )
      {
        Scb = v150;
        goto LABEL_203;
      }
      if ( (v15 & 4) != 0 && (v40 & 1) == 0 )
      {
        NtfsAcquireRange(a1, a3, *(_QWORD *)(a3 + 632), v79, 0, (__int64)&v169);
        v40 |= 1u;
        BYTE1(v137) = v40;
      }
      if ( (unsigned __int8)NtfsLookupAllocation(a1, (__int64)&v164) && v155 != -1 )
        break;
      v102 = v79;
      if ( v79 >= (unsigned __int64)(v164 << *(_BYTE *)(v9 + 488)) )
        v102 = v164 << *(_BYTE *)(v9 + 488);
      v156 = (__int64)(*(unsigned int *)(v9 + 480) + (unsigned __int64)v102) >> *(_BYTE *)(v9 + 488);
      v103 = v156 << *(_BYTE *)(v9 + 488);
      v8 += v103;
      v152 = v8;
      v165 = v8;
      v79 -= v103;
      v139 = v79;
      v145 = v79;
LABEL_199:
      v80 = (unsigned __int8)v138;
      if ( v8 >= *(_QWORD *)(a3 + 40) )
        v80 = 1;
      v138 = v80;
      v141 = v80;
    }
    v81 = v79;
    if ( v79 >= (unsigned __int64)(v164 << *(_BYTE *)(v9 + 488)) )
      v81 = v164 << *(_BYTE *)(v9 + 488);
    v156 = (__int64)(*(unsigned int *)(v9 + 480) + (unsigned __int64)v81) >> *(_BYTE *)(v9 + 488);
    NtfsPurgeFileRecordCache(a1);
    if ( (unsigned __int8)NtfsAllocateClusters(
                            a1,
                            *(_QWORD *)(a3 + 192),
                            a3,
                            (v8 + *(unsigned int *)(v9 + 480)) >> *(_BYTE *)(v9 + 488),
                            1,
                            v156,
                            0,
                            0,
                            v15 >> 7,
                            1,
                            (__int64)&v156) )
    {
      v149 = 0;
      v154 = 0;
      if ( (v15 & 0x40) != 0 )
      {
        v161 = v156 << *(_BYTE *)(v9 + 488);
        LOWORD(v83) = 2 - ((*(_DWORD *)(a3 + 512) & 8) != 0);
        NtfsCreateMdlAndBuffer(a1, v82, v83, 516, &v161, &Mdl, &P);
      }
      v87 = *(_BYTE *)(v9 + 488);
      v88 = (v8 + *(unsigned int *)(v9 + 480)) >> v87;
      v172 = v88;
      v89 = v88 + v156 - 1;
      for ( j = v89; ; v89 = j )
      {
        if ( v88 > v89 || v88 < 0 )
        {
          if ( (v15 & 0x40) != 0 )
          {
            NtfsDeleteMdlAndBuffer(v9, Mdl, P);
            P = 0;
            Mdl = 0;
          }
          LfsSetDefragLsn(*(_QWORD *)(v9 + 232));
          NtfsPurgeFileRecordCache(a1);
          v79 = v139;
          goto LABEL_199;
        }
        v166 = v88 << v87;
        v157 = (_DWORD *)(v89 - v88 == 0x7FFFFFFFFFFFFFFFLL ? 0x7FFFFFFFFFFFFFFFLL : v89 - v88 + 1);
        if ( !FsRtlLookupBaseMcbEntry(
                (PBASE_MCB)(*(_QWORD *)(a1 + 192) + 40LL),
                v88,
                &Lbn,
                &SectorCountFromLbn,
                0,
                0,
                0) )
          break;
        if ( Lbn == -1 )
        {
          v101 = (__int64)v157;
          if ( SectorCountFromLbn <= (__int64)v157 )
            goto LABEL_192;
          goto LABEL_191;
        }
        v90 = SectorCountFromLbn;
        if ( SectorCountFromLbn > (__int64)v157 )
        {
          v90 = (int)v157;
          SectorCountFromLbn = (__int64)v157;
        }
        v91 = v90 << *(_DWORD *)(v9 + 488);
        v140 = 0;
        *(_QWORD *)(a2 + 8) = Mdl;
        if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
          IoClearFsTrackOffsetState(a2);
        NtfsSingleAsync(
          a1,
          *(_QWORD *)(v9 + 224),
          v9,
          a3,
          v88 << *(_BYTE *)(v9 + 488),
          v155 << *(_BYTE *)(v9 + 488),
          v91,
          a2,
          3,
          0,
          (*v153 & 0x4000000) != 0 ? 8 : 4);
        NtfsWaitOnIo(a1, a2, a3);
        NtfsNormalizeAndCleanupTransaction(a1, a2 + 48);
        *(_QWORD *)(a2 + 56) = 0;
        v92 = v153;
        if ( *(_QWORD *)(a3 + 504) && *v153 >= 0 && (*v153 & 0x4000000) != 0 && xmmword_140095740 )
        {
          xmmword_140095740(P, &v166, v91);
          v92 = v153;
        }
        if ( *(_QWORD *)(a3 + 504) && *v92 >= 0 && (*v92 & 0x2000000) != 0 && *(&xmmword_140095740 + 1) )
          ((void (__fastcall *)(PVOID, PVOID, LONGLONG *, _QWORD, _QWORD))*(&xmmword_140095740 + 1))(
            P,
            P,
            &v166,
            v91,
            *(_QWORD *)(a3 + 504));
        if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
          IoClearFsTrackOffsetState(a2);
        NtfsSingleAsync(
          a1,
          *(_QWORD *)(v9 + 224),
          v9,
          a3,
          v88 << *(_BYTE *)(v9 + 488),
          Lbn << *(_BYTE *)(v9 + 488),
          v91,
          a2,
          4,
          0,
          (*v153 & 0x2000000) != 0 ? 8 : 4);
        NtfsWaitOnIo(a1, a2, a3);
        NtfsNormalizeAndCleanupTransaction(a1, a2 + 48);
        *(_QWORD *)(a2 + 56) = 0;
        *(_QWORD *)(a2 + 8) = 0;
        if ( v142 )
        {
          v163 = SectorCountFromLbn;
          NtfsReleaseQuotaControlIfOwned(a1);
          NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(a3 + 184), a3, 8);
          v93 = v15 | 1;
          LOBYTE(v137) = v93;
          v94 = NtfsCreateScb(a1, *(_QWORD *)(a3 + 184), 128, (const UNICODE_STRING *)&NtfsEfsBackupName, 0, 0, 0);
          v150 = v94;
          NtfsCreateInternalAttributeStream(a1, (__int64)v94, 0, 0, 0, 0);
          NtfsPreloadAllocationInternal(a1, v88 + v163 - 1, 0);
          BYTE5(v137) = 1;
          NtfsAddNtfsMcbEntry((unsigned __int64)(v94 + 200), v160[0], v155, SectorCountFromLbn, 0, 1u);
          NtfsRemoveNtfsMcbEntry(a3 + 400, v88);
          v95 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64))&xmmword_1400957A0 + 1))(
                  a1,
                  *(_QWORD *)(a3 + 184),
                  a3 + 264,
                  0,
                  v152 + (SectorCountFromLbn << *(_BYTE *)(v9 + 488)));
          v8 = (unsigned int)v95;
          v140 = v95;
          if ( v95 < 0 )
            goto LABEL_303;
          memset(v171, 0, 0x58u);
          BYTE4(v137) = 1;
          v8 = (__int64)v150;
          LOBYTE(Indexa) = 0;
          v96 = NtfsLookupInFileRecord(
                  a1,
                  *((_QWORD *)v150 + 23),
                  *((_QWORD *)v150 + 23) + 8LL,
                  *((unsigned int *)v150 + 64),
                  v150 + 132,
                  0,
                  Indexa,
                  0,
                  0,
                  v171);
          v98 = 0;
          if ( !v96 && (*(_DWORD *)(v8 + 512) & 4) == 0 )
            goto LABEL_311;
          NtfsSnapshotScb(a1, v8);
          *(_QWORD *)(*(_QWORD *)(v8 + 496) + 96LL) = a1;
          LOBYTE(SectorCountFromStartingLbn) = 0;
          NtfsAddAttributeAllocation(a1, v8, v171, v160, &v163, SectorCountFromStartingLbn);
          NtfsCleanupAttributeContext(v99, v171);
          BYTE4(v137) = 0;
          v157 = *(_DWORD **)(v8 + 472);
          NtfsUpdateScbFromAttribute(a1, v8, 0);
          if ( *(_BYTE *)(*(_QWORD *)(v8 + 184) + 38LL) && *(_DWORD **)(v8 + 472) != v157 )
          {
            NtfsPurgeFileRecordCache(a1);
            NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(v9 + 72), 0);
            LOBYTE(v137) = v93 | 0x10;
            NtfsAdjustFcbAllocatedClusterCount(
              a1,
              *(_QWORD *)(v8 + 184),
              (__int64)(*(_QWORD *)(v8 + 472) - (_QWORD)v157) >> *(_BYTE *)(v9 + 488));
            NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v9 + 72) + 184LL), 0);
            v93 &= ~0x10u;
            LOBYTE(v137) = v93;
          }
          LOBYTE(v100) = 1;
          NtfsPersistDelayedAllocation(a1, v88, v88 + v163 - 1, v100);
          v8 = v152;
          *(_QWORD *)(a3 + 632) = v152 + (SectorCountFromLbn << *(_BYTE *)(v9 + 488));
          NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
          v15 = v93 & 0xFE;
          LOBYTE(v137) = v15;
          v160[0] += SectorCountFromLbn;
          BYTE5(v137) = 0;
        }
        else
        {
          v8 = v152;
        }
LABEL_192:
        v155 += SectorCountFromLbn;
        v87 = *(_BYTE *)(v9 + 488);
        v8 += SectorCountFromLbn << v87;
        v152 = v8;
        v165 = v8;
        v139 -= SectorCountFromLbn << v87;
        v145 = v139;
        v88 += SectorCountFromLbn;
        v172 = v88;
      }
      v101 = (__int64)v157;
LABEL_191:
      SectorCountFromLbn = v101;
      goto LABEL_192;
    }
    if ( !(_WORD)v149 )
    {
      v85 = 1;
      v149 = 1;
      v154 = 1;
      v86 = v15 | 0x20;
      LOBYTE(v137) = v86;
      if ( (v40 & 1) != 0 )
      {
        NtfsReleaseRangeInternal(&v169);
        v40 &= ~1u;
        BYTE1(v137) = v40;
      }
      NtfsReleasePagingResourcePriv(v85, a3, v83, v84);
      v15 = v86 & 0xF9;
      LOBYTE(v137) = v15;
      continue;
    }
    break;
  }
  LODWORD(v8) = -1073741697;
  if ( NtfsStatusDebugFlags )
  {
    v56 = 810706;
LABEL_81:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v8, v56);
  }
LABEL_82:
  v140 = v8;
LABEL_246:
  *(_QWORD *)(a1 + 16) &= ~0x40000uLL;
  if ( (v15 & 0x10) != 0 )
  {
    NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v9 + 72) + 184LL), 0);
    v15 &= ~0x10u;
    LOBYTE(v137) = v15;
  }
  if ( P && (v15 & 0x40) != 0 )
  {
    NtfsDeleteMdlAndBuffer(v9, Mdl, P);
    *(_QWORD *)(a2 + 8) = 0;
    P = 0;
    Mdl = 0;
  }
  if ( (v40 & 2) != 0 )
  {
    NtfsUnlockFsRtlHeader(a1, a3);
    v40 &= ~2u;
    BYTE1(v137) = v40;
  }
  NtfsReleaseDelayedAllocation(a1, 0, 0x7FFFFFFFFFFFFFFFLL);
  if ( (v40 & 1) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      *(_OWORD *)(a1 + 72) = v169;
      *(_OWORD *)(a1 + 88) = v170;
    }
    else
    {
      NtfsReleaseRangeInternal(&v169);
      *(_QWORD *)(a1 + 80) = 0;
    }
    BYTE1(v137) = v40 & 0xFE;
  }
  if ( (v15 & 6) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      v148 = 0;
      for ( k = 0; ; ++k )
      {
        v148 = k;
        if ( k >= 2 )
          break;
        v12 = k;
        m = *(_QWORD *)(a1 + 8LL * k + 48);
        if ( !m || m == *(_QWORD *)(a3 + 184) )
        {
          *(_QWORD *)(a1 + 8LL * k + 48) = *(_QWORD *)(a3 + 184);
          break;
        }
      }
    }
    else
    {
      NtfsReleasePagingResourcePriv(m, *(_QWORD *)(a3 + 184), v14, v120);
      v147 = 0;
      for ( m = 0; ; m = (unsigned int)(m + 1) )
      {
        v147 = m;
        if ( (unsigned int)m >= 2 )
          break;
        v12 = (unsigned int)m;
        if ( *(_QWORD *)(a1 + 8LL * (unsigned int)m + 48) == *(_QWORD *)(a3 + 184) )
          *(_QWORD *)(a1 + 8LL * (unsigned int)m + 48) = 0;
      }
    }
    v15 &= 0xF9u;
    LOBYTE(v137) = v15;
  }
  if ( (v15 & 1) != 0 )
  {
    NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
    v15 &= ~1u;
    LOBYTE(v137) = v15;
  }
  if ( (v15 & 8) != 0 )
  {
    NtfsReleaseVcb(a1, v9);
    v15 &= ~8u;
    LOBYTE(v137) = v15;
  }
LABEL_276:
  v122 = *(unsigned int *)(a1 + 16);
  LODWORD(v122) = v122 & 0x7FFFFFFF;
  *(_QWORD *)(a1 + 16) = v122;
  if ( BYTE4(v137) )
    NtfsCleanupAttributeContext(m, v171);
  NtfsFreeIoContext(a1, v12, v14);
  v126 = P;
  if ( P )
  {
    *(_QWORD *)(a2 + 8) = 0;
    IoFreeMdl(Mdl);
    ExFreePoolWithTag(v126, 0);
  }
  if ( (v15 & 6) != 0 )
  {
    if ( *(_DWORD *)(a1 + 28) )
    {
      v127 = 0;
      while ( 1 )
      {
        v128 = *(_QWORD *)(a1 + 8LL * v127 + 48);
        if ( !v128 || v128 == *(_QWORD *)(a3 + 184) )
          break;
        if ( ++v127 >= 2 )
          goto LABEL_292;
      }
      *(_QWORD *)(a1 + 8LL * v127 + 48) = *(_QWORD *)(a3 + 184);
    }
    else
    {
      NtfsReleasePagingResourcePriv(v123, *(_QWORD *)(a3 + 184), v124, v125);
      for ( n = 0; n != 2; ++n )
      {
        if ( *(_QWORD *)(a1 + 8 * n + 48) == *(_QWORD *)(a3 + 184) )
          *(_QWORD *)(a1 + 8 * n + 48) = 0;
      }
    }
  }
LABEL_292:
  if ( (v15 & 1) != 0 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(a3 + 184), 0);
  if ( (v15 & 8) != 0 )
    NtfsReleaseVcb(a1, v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400cc78c  mov     rax, rsp
0x1400cc78f  mov     [rax+20h], r9
0x1400cc793  mov     [rax+18h], r8
0x1400cc797  mov     [rax+10h], rdx
0x1400cc79b  mov     [rax+8], rcx
0x1400cc79f  push    rbx
0x1400cc7a0  push    rsi
0x1400cc7a1  push    rdi
0x1400cc7a2  push    r12
0x1400cc7a4  push    r13
0x1400cc7a6  push    r14
0x1400cc7a8  push    r15
0x1400cc7aa  sub     rsp, 2A0h
0x1400cc7b1  mov     r15, r9
0x1400cc7b4  mov     r14, r8
0x1400cc7b7  mov     rsi, rcx
0x1400cc7ba  xor     r12d, r12d
0x1400cc7bd  mov     ebx, r12d
0x1400cc7c0  xor     edx, edx; Val
0x1400cc7c2  lea     r8d, [r12+58h]; Size
0x1400cc7c7  lea     rcx, [rax-148h]; void *
0x1400cc7ce  call    memset
0x1400cc7d3  mov     rax, [r14+0B8h]
0x1400cc7da  mov     r13, [rax+60h]
0x1400cc7de  mov     [rsp+2D8h+var_1B0], r13
0x1400cc7e6  mov     [rsp+2D8h+Mdl], r12
0x1400cc7ee  xor     al, al
0x1400cc7f0  mov     [rsp+2D8h+var_253], al
0x1400cc7f7  mov     [rsp+2D8h+P], r12
0x1400cc7ff  mov     eax, r12d
0x1400cc802  mov     [rsp+2D8h+var_24C], eax
0x1400cc809  mov     [rsp+2D8h+var_228], eax
0x1400cc810  mov     [rsp+2D8h+var_94], eax
0x1400cc817  xor     edx, edx; Val
0x1400cc819  lea     r8d, [r12+5Ch]; Size
0x1400cc81e  lea     rcx, [rsp+2D8h+var_98]; void *
0x1400cc826  call    memset
0x1400cc82b  xorps   xmm0, xmm0
0x1400cc82e  movups  [rsp+2D8h+var_168], xmm0
0x1400cc836  movups  [rsp+2D8h+var_158], xmm0
0x1400cc83e  mov     [rsp+2D8h+var_1D8], r12
0x1400cc846  mov     [rsp+2D8h+var_210], r12d
0x1400cc84e  mov     [rsp+2D8h+SectorCountFromLbn], r12
0x1400cc856  mov     [rsp+2D8h+Lbn], r12
0x1400cc85e  mov     byte ptr [rsp+2D8h+var_250], r12b
0x1400cc866  mov     [rsp+2D8h+var_208], r12
0x1400cc86e  mov     [rsp+2D8h+var_258], r12d
0x1400cc876  mov     byte ptr [rsp+2D8h+var_258], 80h
0x1400cc87e  mov     ecx, 80000000h
0x1400cc883  or      [rsi+10h], rcx
0x1400cc887  lea     ecx, [r12+1]
0x1400cc88c  mov     [rsp+2D8h+var_254], cl
0x1400cc893  mov     dil, 80h
0x1400cc896  cmp     [r14+10h], r12
0x1400cc89a  jz      short loc_1400CC8EA
0x1400cc89c  test    [rsp+2D8h+arg_20], 2000000h
0x1400cc8a7  jnz     short loc_1400CC8CD
0x1400cc8a9  test    dword ptr [r15+8], 100h
0x1400cc8b1  jz      short loc_1400CC8CD
0x1400cc8b3  mov     r8b, [rsi+0Ch]
0x1400cc8b7  and     r8b, cl
0x1400cc8ba  xor     r9d, r9d
0x1400cc8bd  mov     rdx, r14
0x1400cc8c0  mov     rcx, rsi
0x1400cc8c3  call    NtfsAcquirePagingShared
0x1400cc8c8  mov     dil, 84h
0x1400cc8cb  jmp     short loc_1400CC8E2
0x1400cc8cd  mov     r8b, [rsi+0Ch]
0x1400cc8d1  and     r8b, cl
0x1400cc8d4  mov     rdx, r14
0x1400cc8d7  mov     rcx, rsi
0x1400cc8da  call    NtfsAcquirePagingResourceExclusive
0x1400cc8df  mov     dil, 82h
0x1400cc8e2  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cc8ea  mov     r9d, 8
0x1400cc8f0  mov     r8, r14
0x1400cc8f3  mov     rdx, [r14+0B8h]
0x1400cc8fa  mov     rcx, rsi
0x1400cc8fd  call    NtfsAcquireExclusiveFcb
0x1400cc902  mov     r10d, 1
0x1400cc908  or      dil, r10b
0x1400cc90b  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cc913  mov     r12d, [r14+200h]
0x1400cc91a  lea     r9d, [r10+1]
0x1400cc91e  test    r9b, r12b
0x1400cc921  jz      loc_1400CCA49
0x1400cc927  xor     edx, edx
0x1400cc929  test    r15, r15
0x1400cc92c  jz      loc_1400CCA49
0x1400cc932  mov     r15d, [r15+4]
0x1400cc936  bt      r15d, 1Bh
0x1400cc93b  jb      loc_1400CCA41
0x1400cc941  mov     eax, [rsi+10h]
0x1400cc944  bt      rax, 14h
0x1400cc949  jb      loc_1400CCA17
0x1400cc94f  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1400cc956  test    al, 20h
0x1400cc958  jz      loc_1400CCA17
0x1400cc95e  mov     r9, [r14+0C0h]
0x1400cc965  mov     r11, [r9+0F8h]
0x1400cc96c  movzx   eax, word ptr [r11+6]
0x1400cc971  lea     ecx, [rdx+40h]
0x1400cc974  cmp     ax, cx
0x1400cc977  ja      short loc_1400CC987
0x1400cc979  test    r10b, al
0x1400cc97c  jnz     short loc_1400CC987
0x1400cc97e  mov     [rsp+2D8h+var_240], eax
0x1400cc985  jmp     short loc_1400CC990
0x1400cc987  mov     eax, edx
0x1400cc989  mov     [rsp+2D8h+var_240], edx
0x1400cc990  mov     word ptr [rsp+2D8h+var_178], ax
0x1400cc998  add     r11, 20h ; ' '
0x1400cc99c  mov     [rsp+2D8h+var_170], r11
0x1400cc9a4  mov     r8, gs:188h
0x1400cc9ad  mov     rcx, [r14+0B8h]
0x1400cc9b4  movzx   edx, ax
0x1400cc9b7  shr     edx, 1
0x1400cc9b9  movzx   r10d, word ptr [r9+1EC0h]
0x1400cc9c1  shr     r10d, 1
0x1400cc9c4  mov     [rsp+2D8h+var_268], r15d
0x1400cc9c9  mov     dword ptr [rsp+2D8h+var_270], r12d
0x1400cc9ce  mov     rax, [r14+110h]
0x1400cc9d5  mov     [rsp+2D8h+var_278], rax
0x1400cc9da  mov     eax, [r14+100h]
0x1400cc9e1  mov     [rsp+2D8h+var_280], eax
0x1400cc9e5  mov     [rsp+2D8h+var_288], r14
0x1400cc9ea  mov     rax, [rcx+8]
0x1400cc9ee  mov     [rsp+2D8h+var_290], rax
0x1400cc9f3  mov     [rsp+2D8h+var_298], rcx
0x1400cc9f8  mov     [rsp+2D8h+Size], r11
0x1400cc9fd  mov     dword ptr [rsp+2D8h+Index], edx
0x1400cca01  mov     rax, [r9+1EC8h]
0x1400cca08  mov     [rsp+2D8h+SectorCountFromStartingLbn], rax
0x1400cca0d  mov     dword ptr [rsp+2D8h+Irp], r10d
0x1400cca12  call    McTemplateU0ppwwpipdzdd_EtwWriteTransfer
0x1400cca17  mov     al, cs:NtfsStatusDebugFlags
0x1400cca1d  xor     r12d, r12d
0x1400cca20  mov     ebx, 0C0000022h
0x1400cca25  test    al, al
0x1400cca27  jz      loc_1400CE8CA
0x1400cca2d  mov     r8d, 0C5BA9h
0x1400cca33  mov     edx, ebx
0x1400cca35  xor     ecx, ecx
0x1400cca37  call    NtfsStatusTraceAndDebugInternal
0x1400cca3c  jmp     loc_1400CE8CA
0x1400cca41  mov     r15, [rsp+2D8h+arg_18]
0x1400cca49  test    dil, 4
0x1400cca4d  jz      loc_1400CCAE5
0x1400cca53  lea     r12, [r15+8]
0x1400cca57  test    dword ptr [r12], 100h
0x1400cca5f  jnz     loc_1400CCAF1
0x1400cca65  mov     rdx, r14
0x1400cca68  call    NtfsReleasePagingResourcePriv
0x1400cca6d  and     dil, 0FBh
0x1400cca71  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cca79  xor     r8d, r8d
0x1400cca7c  mov     rdx, [r14+0B8h]
0x1400cca83  mov     rcx, rsi
0x1400cca86  call    NtfsReleaseFcbEx
0x1400cca8b  and     dil, 0FEh
0x1400cca8f  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400cca97  mov     r8b, [rsi+0Ch]
0x1400cca9b  and     r8b, 1
0x1400cca9f  mov     rdx, r14
0x1400ccaa2  mov     rcx, rsi
0x1400ccaa5  call    NtfsAcquirePagingResourceExclusive
0x1400ccaaa  or      dil, 2
0x1400ccaae  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccab6  mov     r9d, 8
0x1400ccabc  mov     r8, r14
0x1400ccabf  mov     rdx, [r14+0B8h]
0x1400ccac6  mov     rcx, rsi
0x1400ccac9  call    NtfsAcquireExclusiveFcb
0x1400ccace  mov     r10d, 1
0x1400ccad4  or      dil, r10b
0x1400ccad7  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccadf  lea     r9d, [r10+1]
0x1400ccae3  jmp     short loc_1400CCAF1
0x1400ccae5  mov     r12, [rsp+2D8h+arg_18]
0x1400ccaed  add     r12, 8
0x1400ccaf1  mov     r15b, dil
0x1400ccaf4  test    dword ptr [r12], 100h
0x1400ccafc  jnz     short loc_1400CCB12
0x1400ccafe  mov     edx, 100h
0x1400ccb03  mov     rcx, r12
0x1400ccb06  call    SetFlagInterlocked
0x1400ccb0b  add     [r14+1C0h], r10d
0x1400ccb12  lea     rcx, [r14+0C8h]
0x1400ccb19  mov     [rsp+2D8h+var_1F0], rcx
0x1400ccb21  test    r9b, r15b
0x1400ccb24  jz      short loc_1400CCB6D
0x1400ccb26  test    dword ptr [rcx], 2000000h
0x1400ccb2c  jnz     short loc_1400CCB65
0x1400ccb2e  mov     rcx, [r14+10h]; Resource
0x1400ccb32  call    cs:__imp_ExConvertExclusiveToSharedLite
0x1400ccb39  nop     dword ptr [rax+rax+00h]
0x1400ccb3e  mov     dil, r15b
0x1400ccb41  and     dil, 0FDh
0x1400ccb45  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccb4d  or      dil, 4
0x1400ccb51  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccb59  mov     r15b, dil
0x1400ccb5c  lea     rcx, [r14+0C8h]
0x1400ccb63  jmp     short loc_1400CCB6D
0x1400ccb65  mov     [rsp+2D8h+var_1F0], rcx
0x1400ccb6d  mov     eax, [r14+200h]
0x1400ccb74  xor     r12d, r12d
0x1400ccb77  bt      eax, 10h
0x1400ccb7b  jnb     short loc_1400CCB9B
0x1400ccb7d  mov     al, cs:NtfsStatusDebugFlags
0x1400ccb83  mov     ebx, 0C000026Eh
0x1400ccb88  test    al, al
0x1400ccb8a  jz      loc_1400CE8CA
0x1400ccb90  mov     r8d, 0C5BFAh
0x1400ccb96  jmp     loc_1400CCA33
0x1400ccb9b  bt      eax, 1Ah
0x1400ccb9f  jnb     short loc_1400CCBBF
0x1400ccba1  mov     al, cs:NtfsStatusDebugFlags
0x1400ccba7  mov     ebx, 0C0000189h
0x1400ccbac  test    al, al
0x1400ccbae  jz      loc_1400CE8CA
0x1400ccbb4  mov     r8d, 0C5C04h
0x1400ccbba  jmp     loc_1400CCA33
0x1400ccbbf  mov     eax, [rcx]
0x1400ccbc1  test    al, 20h
0x1400ccbc3  jnz     short loc_1400CCC40
0x1400ccbc5  mov     rdx, [r14+0B8h]
0x1400ccbcc  lea     rax, [r14+108h]
0x1400ccbd3  lea     r8, [rdx+8]
0x1400ccbd7  lea     rcx, [rsp+2D8h+var_148]
0x1400ccbdf  mov     [rsp+2D8h+var_290], rcx
0x1400ccbe4  mov     dword ptr [rsp+2D8h+var_298], r12d
0x1400ccbe9  mov     [rsp+2D8h+Size], r12
0x1400ccbee  mov     byte ptr [rsp+2D8h+Index], r12b
0x1400ccbf3  mov     [rsp+2D8h+SectorCountFromStartingLbn], r12
0x1400ccbf8  mov     [rsp+2D8h+Irp], rax
0x1400ccbfd  mov     r9d, [r14+100h]
0x1400ccc04  mov     rcx, rsi
0x1400ccc07  call    NtfsLookupInFileRecord
0x1400ccc0c  test    al, al
0x1400ccc0e  jnz     short loc_1400CCC18
0x1400ccc10  mov     ebx, r12d
0x1400ccc13  jmp     loc_1400CE8CA
0x1400ccc18  mov     r8, [rsp+2D8h+var_148]
0x1400ccc20  mov     rdx, r14
0x1400ccc23  mov     rcx, rsi
0x1400ccc26  call    NtfsUpdateScbFromAttribute
0x1400ccc2b  lea     rdx, [rsp+2D8h+var_148]
0x1400ccc33  call    NtfsCleanupAttributeContext
0x1400ccc38  mov     [rsp+2D8h+var_254], r12b
0x1400ccc40  xor     r8d, r8d
0x1400ccc43  mov     rdx, [r14+0B8h]
0x1400ccc4a  mov     rcx, rsi
0x1400ccc4d  call    NtfsReleaseFcbEx
0x1400ccc52  mov     dil, r15b
0x1400ccc55  and     dil, 0FEh
0x1400ccc59  mov     byte ptr [rsp+2D8h+var_258], dil
0x1400ccc61  lea     rdx, [rsp+2D8h+var_148]
0x1400ccc69  call    NtfsCleanupAttributeContext
0x1400ccc6e  mov     [rsp+2D8h+var_254], r12b
0x1400ccc76  mov     r12d, [r13+164h]
0x1400ccc7d  mov     eax, 200000h
0x1400ccc82  cmp     r12d, eax
0x1400ccc85  cmovb   r12d, eax
0x1400ccc89  mov     [rsp+2D8h+var_200], r12d
0x1400ccc91  mov     edx, r12d; NumberOfBytes
0x1400ccc94  mov     ecx, 200h; PoolType
0x1400ccc99  mov     r8d, 4446744Eh; Tag
0x1400ccc9f  call    cs:__imp_ExAllocatePoolWithTag
0x1400ccca6  nop     dword ptr [rax+rax+00h]
0x1400cccab  mov     r15, rax
0x1400cccae  mov     [rsp+2D8h+P], rax
0x1400cccb6  xor     eax, eax
0x1400cccb8  test    r15, r15
0x1400cccbb  jz      short loc_1400CCD2D
0x1400cccbd  mov     [rsp+2D8h+Irp], rax; Irp
0x1400cccc2  xor     r9d, r9d; ChargeQuota
0x1400cccc5  xor     r8d, r8d; SecondaryBuffer
0x1400cccc8  mov     edx, r12d; Length
0x1400ccccb  mov     rcx, r15; VirtualAddress
0x1400cccce  call    cs:__imp_IoAllocateMdl
0x1400cccd5  nop     dword ptr [rax+rax+00h]
0x1400cccda  mov     r12, rax
0x1400cccdd  mov     [rsp+2D8h+Mdl], rax
0x1400ccce5  test    rax, rax
0x1400ccce8  jz      short loc_1400CCD12
0x1400cccea  mov     rcx, rax; MemoryDescriptorList
0x1400ccced  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400cccf4  nop     dword ptr [rax+rax+00h]
0x1400cccf9  mov     edx, 1
0x1400cccfe  mov     rcx, r12
0x1400ccd01  call    cs:__imp_MmMdlPageContentsState
0x1400ccd08  nop     dword ptr [rax+rax+00h]
0x1400ccd0d  mov     rax, r15
0x1400ccd10  jmp     short loc_1400CCD2D
0x1400ccd12  xor     edx, edx; Tag
0x1400ccd14  mov     rcx, r15; P
0x1400ccd17  call    cs:__imp_ExFreePoolWithTag
0x1400ccd1e  nop     dword ptr [rax+rax+00h]
0x1400ccd23  xor     eax, eax
  ... truncated ...
```
