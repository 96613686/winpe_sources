# NtfsChangeVolumeSize

- ea: `0x14027e418`
- end: `0x140280d13`
- name: `NtfsChangeVolumeSize`
- size: `10491`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401f58e0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x140012e70`
- `0x14001c910`
- `0x14001e810`
- `0x140020de0`
- `0x140021590`
- `0x140021c30`
- `0x140021e60`
- `0x14002b680`
- `0x14002bc00`
- `0x140031410`
- `0x14003e734`
- `0x14004062c`
- `0x1400410a8`
- `0x140047ce4`
- `0x14004801c`
- `0x1400592c0`
- `0x140059740`
- `0x1400c3090`
- `0x1400cc568`
- `0x1400d1da8`
- `0x1400f7124`
- `0x140125100`
- `0x14012c23c`
- `0x140137aac`
- `0x14013c320`
- `0x14013ce30`
- `0x1401403d0`
- `0x14014de30`
- `0x140150c10`
- `0x140150cd0`
- `0x14015ec88`
- `0x140160c30`
- `0x140162110`
- `0x1401623c0`
- `0x14016dab0`
- `0x140174570`
- `0x140174b4c`
- `0x1401751cc`
- `0x1401aab70`
- `0x1401c0130`
- `0x1401cb314`
- `0x1401d2528`
- `0x1401d2c84`
- `0x1401d2d3c`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14027e535`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14027e535`
- `ntoskrnl!RtlSetBit` at `0x14027fbec`
- `ntoskrnl!RtlSetBit` at `0x14027fc15`
- `ntoskrnl!RtlSetBit` at `0x14027fbec`
- `ntoskrnl!RtlSetBit` at `0x14027fc15`
- `ntoskrnl!RtlSetBits` at `0x14027fda0`
- `ntoskrnl!RtlSetBits` at `0x14027fda0`
- `ntoskrnl!RtlNumberOfClearBitsInRange` at `0x14027fd22`
- `ntoskrnl!RtlNumberOfClearBitsInRange` at `0x14027fd22`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140280094`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140280094`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e4fa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027ea23`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027f0b2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402800d7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402bba64`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e4fa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027ea23`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027f0b2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402800d7`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402bba64`
- `ntoskrnl!RtlClearBit` at `0x14027fa0b`
- `ntoskrnl!RtlClearBit` at `0x14027fa0b`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x14027fa69`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x14027fa69`
- `ntoskrnl!RtlExtractBitMap` at `0x14027fb9a`
- `ntoskrnl!RtlExtractBitMap` at `0x14027fb9a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402807ed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc22e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3ba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3fa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402807ed`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc22e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3ba`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3fa`
- `ntoskrnl!IoGetActivityIdThread` at `0x14027e5c6`
- `ntoskrnl!IoGetActivityIdThread` at `0x14027e5c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027e7d5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027e7d5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14027f238`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14027f238`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14027f225`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14027f225`
- `ntoskrnl!ExFreePoolWithTag` at `0x14027fbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280823`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc254`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc29e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14027fbaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140280823`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc254`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc29e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14027fb6e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14027fb6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f882`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f963`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f882`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f963`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14027f13c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14027f13c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027f129`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027f129`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14027ec13`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14027ec13`
- `ntoskrnl!CcFlushCache` at `0x14027f2ac`
- `ntoskrnl!CcFlushCache` at `0x14027f2ac`

## pseudocode

```c
__int64 __fastcall NtfsChangeVolumeSize(__int64 a1, __int64 a2, char a3)
{
  unsigned int IsClearOrSet; // esi
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // r8
  _QWORD *ActivityIdThread; // rax
  unsigned __int16 *v13; // rbx
  __int64 v14; // r15
  __int64 v15; // r9
  __int64 v16; // rdi
  unsigned int v17; // ebx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r12
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rbx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int16 *v34; // r15
  __int64 v35; // rbx
  __int64 v36; // r15
  __int64 v37; // r9
  __int64 v38; // rcx
  signed __int64 v39; // r9
  signed __int64 v40; // r8
  __int64 v41; // rbx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // r15
  __int64 v45; // rax
  signed __int64 v46; // r15
  char v47; // cl
  __int64 v48; // r9
  _QWORD *v49; // r11
  __int64 v50; // r8
  LONGLONG v51; // rdx
  LONGLONG v52; // r9
  char v53; // al
  int v54; // r9d
  int v55; // r8d
  signed __int64 v56; // r8
  signed __int64 v57; // rcx
  signed __int64 v58; // rcx
  int v59; // edx
  signed __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r8
  __int64 v63; // rcx
  unsigned __int64 v64; // r15
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // rcx
  __int64 v67; // rax
  SIZE_T v68; // rbx
  __int64 v69; // rax
  struct _RTL_BITMAP *v70; // r15
  unsigned int v71; // r13d
  ULONG v72; // ebx
  ULONG *v73; // r10
  ULONG v74; // r9d
  __int64 v75; // rdx
  __int64 v76; // r9
  __int64 v77; // rax
  unsigned __int64 v78; // rax
  unsigned __int64 v79; // r8
  ULONG v80; // r15d
  unsigned __int64 v81; // rax
  unsigned int v82; // ebx
  __int64 v83; // r9
  __int64 v84; // rdx
  __int64 v85; // rax
  __int64 v86; // rdx
  signed __int64 v87; // rcx
  __int64 v88; // rax
  int v89; // edx
  signed __int64 v90; // r9
  signed __int64 v91; // r8
  __int64 v92; // rax
  int v93; // edx
  signed __int64 v94; // rcx
  signed __int64 v95; // r8
  __int64 v96; // rcx
  unsigned __int64 v97; // rax
  __int64 v98; // r10
  char v99; // r12
  ULONGLONG v100; // rbx
  char v101; // al
  int v102; // r8d
  ULONGLONG v103; // r13
  unsigned __int64 v104; // r13
  __int16 v105; // r15
  const WCHAR *v106; // r11
  const WCHAR *v107; // rcx
  int v108; // r12d
  int v109; // edx
  const WCHAR *v110; // rcx
  const WCHAR *v111; // rcx
  const WCHAR *v112; // rcx
  const WCHAR *v113; // rcx
  __int64 v114; // rax
  __int64 v115; // rbx
  int v116; // ebx
  __int128 v117; // rax
  unsigned __int64 v118; // r13
  __int16 v119; // r15
  const WCHAR *v120; // r11
  const WCHAR *v121; // rcx
  int v122; // r12d
  int v123; // edx
  const WCHAR *v124; // rcx
  const WCHAR *v125; // rcx
  const WCHAR *v126; // rcx
  const WCHAR *v127; // rcx
  __int64 v128; // rax
  __int64 v129; // rbx
  int v130; // ebx
  __int128 v131; // rax
  PVOID v132; // rcx
  __int64 v133; // rcx
  __int64 v134; // r9
  __int16 v136; // r10
  __int64 v137; // rax
  unsigned __int16 v138; // cx
  unsigned int v139; // eax
  __int64 v140; // rcx
  int v141; // [rsp+120h] [rbp-2D0h]
  int v142; // [rsp+120h] [rbp-2D0h]
  int v143; // [rsp+128h] [rbp-2C8h]
  char v144; // [rsp+1D8h] [rbp-218h]
  char v145; // [rsp+1D9h] [rbp-217h] BYREF
  char v146; // [rsp+1DAh] [rbp-216h]
  char v147; // [rsp+1DBh] [rbp-215h]
  int v148; // [rsp+1DCh] [rbp-214h]
  char v149; // [rsp+1E0h] [rbp-210h]
  char v150; // [rsp+1E1h] [rbp-20Fh]
  char v151; // [rsp+1E2h] [rbp-20Eh]
  int v152; // [rsp+1E4h] [rbp-20Ch]
  __int16 v153; // [rsp+1ECh] [rbp-204h]
  __int16 *v154; // [rsp+1F0h] [rbp-200h]
  int v155; // [rsp+1F8h] [rbp-1F8h]
  int v156[2]; // [rsp+200h] [rbp-1F0h] BYREF
  unsigned __int64 v157; // [rsp+208h] [rbp-1E8h]
  __int64 v158; // [rsp+210h] [rbp-1E0h]
  int v159[2]; // [rsp+218h] [rbp-1D8h] BYREF
  unsigned __int64 v160; // [rsp+220h] [rbp-1D0h] BYREF
  __int16 v161; // [rsp+228h] [rbp-1C8h]
  int v162[2]; // [rsp+230h] [rbp-1C0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+238h] [rbp-1B8h] BYREF
  __int64 v164; // [rsp+248h] [rbp-1A8h]
  ULONGLONG UnbiasedInterruptTime; // [rsp+250h] [rbp-1A0h]
  ULONG SizeOfBitMap[2]; // [rsp+258h] [rbp-198h]
  unsigned __int64 v167; // [rsp+260h] [rbp-190h]
  __int64 v168; // [rsp+268h] [rbp-188h]
  PULONG BitMapBuffer; // [rsp+270h] [rbp-180h]
  __int64 v170; // [rsp+278h] [rbp-178h] BYREF
  __int64 v171; // [rsp+280h] [rbp-170h]
  __int64 v172; // [rsp+288h] [rbp-168h]
  LONGLONG v173; // [rsp+290h] [rbp-160h]
  struct _UNICODE_STRING UnicodeString; // [rsp+298h] [rbp-158h] BYREF
  __int64 v175; // [rsp+2A8h] [rbp-148h]
  PVOID P; // [rsp+2B0h] [rbp-140h]
  ULONG v177; // [rsp+2B8h] [rbp-138h]
  int v178; // [rsp+2BCh] [rbp-134h]
  __int64 v179; // [rsp+2C0h] [rbp-130h]
  __int64 v180; // [rsp+2C8h] [rbp-128h]
  __int64 v181; // [rsp+2D0h] [rbp-120h] BYREF
  LONGLONG v182; // [rsp+2D8h] [rbp-118h]
  __int64 v183; // [rsp+2E0h] [rbp-110h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+2E8h] [rbp-108h] BYREF
  _QWORD v185[11]; // [rsp+2F8h] [rbp-F8h] BYREF
  __int128 v186; // [rsp+358h] [rbp-98h] BYREF
  __int64 v187; // [rsp+368h] [rbp-88h]
  _OWORD v188[2]; // [rsp+370h] [rbp-80h] BYREF
  __int128 v189; // [rsp+390h] [rbp-60h] BYREF
  __int128 v190; // [rsp+3A0h] [rbp-50h]

  v180 = a2;
  v158 = a1;
  IsClearOrSet = 0;
  v148 = 0;
  *(_QWORD *)v159 = 0;
  v160 = 0;
  v171 = 0;
  v175 = 0;
  IoStatus = 0;
  memset(v185, 0, sizeof(v185));
  memset(v188, 0, 28);
  *(_QWORD *)v156 = 0;
  UnicodeString = 0;
  v145 = 0;
  v186 = 0;
  v187 = 0;
  v189 = 0;
  v190 = 0;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  *(_QWORD *)&v189 = UnbiasedInterruptTime;
  v153 = 1;
  if ( a2 )
  {
    if ( (int)IoGetActivityIdIrp(a2, (char *)&v186 + 8) < 0 )
    {
LABEL_3:
      *(_QWORD *)&v186 = 0;
      goto LABEL_4;
    }
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v7);
    if ( !ActivityIdThread )
      goto LABEL_3;
    *((_QWORD *)&v186 + 1) = *ActivityIdThread;
    v187 = ActivityIdThread[1];
  }
  *(_QWORD *)&v186 = (char *)&v186 + 8;
LABEL_4:
  v9 = *(_QWORD *)(a2 + 184);
  v172 = v9;
  v10 = *(_DWORD *)(v9 + 16);
  if ( a3 )
  {
    if ( v10 < 0x18 )
    {
      IsClearOrSet = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203007);
      LOBYTE(v8) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v8, 0);
      if ( !NtfsStatusDebugFlags )
        return IsClearOrSet;
      v11 = 1203008;
LABEL_373:
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, v11);
      return IsClearOrSet;
    }
    v13 = *(unsigned __int16 **)(a2 + 24);
    v14 = *((_QWORD *)v13 + 2);
    v155 = *v13;
    v161 = v155;
  }
  else
  {
    if ( v10 < 8 )
    {
      IsClearOrSet = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203020);
      LOBYTE(v8) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v8, 0);
      if ( !NtfsStatusDebugFlags )
        return IsClearOrSet;
      v11 = 1203021;
      goto LABEL_373;
    }
    v13 = 0;
    v155 = 0;
    v161 = 0;
    v14 = **(_QWORD **)(a2 + 24);
  }
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = v14;
  v157 = (unsigned __int64)v13;
  v154 = (__int16 *)v13;
  if ( (unsigned int)NtfsDecodeFileObject(a1, *(_QWORD *)(v9 + 48), v159, &v181, &v170, &v160, 1) != 4 )
  {
    IsClearOrSet = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203041);
    LOBYTE(v15) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v15, 0);
    if ( !NtfsStatusDebugFlags )
      return IsClearOrSet;
    v11 = 1203042;
    goto LABEL_373;
  }
  if ( !v160 || !_bittest16((const signed __int16 *)(v160 + 104), 9u) )
  {
    if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( v160 )
        v136 = *(_WORD *)(v160 + 104);
      else
        LOBYTE(v136) = 0;
      v137 = *(_QWORD *)(*(_QWORD *)v159 + 248LL);
      v138 = *(_WORD *)(v137 + 6);
      if ( v138 > 0x40u || (v138 & 1) != 0 )
        v138 = 0;
      McTemplateU0ppwwd_EtwWriteTransfer(
        v138 >> 1,
        (unsigned int)fsctrl_c23405,
        (unsigned int)KeGetCurrentThread(),
        v159[0],
        *(_WORD *)(*(_QWORD *)v159 + 7872LL) >> 1,
        *(_QWORD *)(*(_QWORD *)v159 + 7880LL),
        v138 >> 1,
        v137 + 32,
        v136);
    }
    v17 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 1203064);
    LOBYTE(v15) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225506LL, v15, 0);
    if ( !NtfsStatusDebugFlags )
      return v17;
    v18 = 1203065;
    goto LABEL_389;
  }
  v16 = *(_QWORD *)v159;
  if ( (*(_DWORD *)(*(_QWORD *)v159 + 4LL) & 0x2000000) == 0 )
  {
    KeWaitForSingleObject((PVOID)(*(_QWORD *)v159 + 6632LL), Executive, 0, 0, 0);
    if ( !a3 )
      goto LABEL_45;
    if ( *((_QWORD *)v13 + 1) )
    {
      IsClearOrSet = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203098);
      LOBYTE(v19) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v19, 0);
      if ( !NtfsStatusDebugFlags )
        return IsClearOrSet;
      v11 = 1203099;
      goto LABEL_373;
    }
    if ( *(_DWORD *)v13 == 1 )
    {
LABEL_45:
      if ( v14 <= 0 )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203116);
        LOBYTE(v19) = a2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v19, 0);
        if ( !NtfsStatusDebugFlags )
          return IsClearOrSet;
        v11 = 1203117;
        goto LABEL_373;
      }
      v21 = (v14 - 1) * *(unsigned int *)(v16 + 364);
      v171 = v21;
      v175 = v21;
      if ( v21 < v14 || (v20 = v21 >> *(_BYTE *)(v16 + 488), v20 > 4294967294LL) )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203134);
        LOBYTE(v19) = a2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v19, 0);
        if ( !NtfsStatusDebugFlags )
          return IsClearOrSet;
        v11 = 1203135;
        goto LABEL_373;
      }
    }
    else
    {
      if ( v14 )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1203142);
        LOBYTE(v19) = a2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v19, 0);
        if ( !NtfsStatusDebugFlags )
          return IsClearOrSet;
        v11 = 1203143;
        goto LABEL_373;
      }
      v20 = 0;
    }
    v179 = 0;
    v168 = 0;
    v173 = 0;
    P = 0;
    v149 = 0;
    v147 = 0;
    v151 = 0;
    v144 = 0;
    v150 = 0;
    BitMapBuffer = 0;
    *(_QWORD *)SizeOfBitMap = 0;
    *(_DWORD *)(a1 + 12) |= 1u;
    memset(v185, 0, sizeof(v185));
    LOBYTE(v22) = 1;
    if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
      NtfsAcquireExclusiveVcb(a1, v16, v22);
    else
      NtfsAcquireSharedVcb(a1, v16, v22);
    v146 = 1;
    v23 = *(_QWORD *)(v16 + 88);
    v164 = v23;
    v170 = v23;
    v167 = *(_QWORD *)(v16 + 424);
    v160 = v167;
    v181 = *(_QWORD *)(v16 + 432);
    *((_QWORD *)&v189 + 1) = KeQueryUnbiasedInterruptTime();
    v152 = 2;
    v153 = 2;
    if ( (*(_DWORD *)(v16 + 4) & 1) == 0 )
    {
      IsClearOrSet = -1073741202;
      if ( NtfsStatusDebugFlags )
      {
        v24 = 1203192;
LABEL_258:
        NtfsStatusTraceAndDebugInternal(0, IsClearOrSet, v24);
        goto LABEL_259;
      }
      goto LABEL_259;
    }
    if ( a3 )
    {
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0, 9);
      if ( *(_DWORD *)v154 == 1 )
      {
        v33 = v172;
        if ( *(_QWORD *)(v16 + 5368) == 0x7FFFFFFFFFFFFFFFLL || *(_QWORD *)(v172 + 48) == *(_QWORD *)(v16 + 1480) )
        {
          if ( *(_QWORD *)(v16 + 296) > v20 )
          {
            *(_QWORD *)(v16 + 5368) = v20;
            *(_QWORD *)(v16 + 5376) = v14;
            *(_QWORD *)(v16 + 1480) = *(_QWORD *)(v33 + 48);
            NtfsRemoveCachedRun(a1, v16, *(_QWORD *)(v16 + 5368), *(_QWORD *)(v16 + 296) - *(_QWORD *)(v16 + 5368));
            v34 = v154;
            if ( *(_QWORD *)(v16 + 4960) >= *(_QWORD *)(v16 + 5368) )
              *(_QWORD *)(v16 + 4960) = 0;
            goto LABEL_261;
          }
          IsClearOrSet = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_259;
          v24 = 1203264;
          goto LABEL_258;
        }
        IsClearOrSet = -2147483631;
        if ( NtfsStatusDebugFlags )
        {
          v24 = 1203243;
          goto LABEL_258;
        }
        goto LABEL_259;
      }
      if ( *(_DWORD *)v154 != 2 )
      {
        if ( *(_DWORD *)v154 != 3 )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v24 = 1203411;
            goto LABEL_258;
          }
LABEL_259:
          v148 = IsClearOrSet;
          goto LABEL_260;
        }
        if ( *(_QWORD *)(v172 + 48) != *(_QWORD *)(v16 + 1480) )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v24 = 1203372;
            goto LABEL_258;
          }
          goto LABEL_259;
        }
        *(_QWORD *)(v16 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
        *(_QWORD *)(v16 + 5376) = 0;
        *(_QWORD *)(v16 + 1480) = 0;
        NtfsScanEntireBitmap(a1, v16, 10, 5);
LABEL_260:
        v34 = v154;
LABEL_261:
        v99 = a3;
LABEL_262:
        v100 = KeQueryUnbiasedInterruptTime();
        *((_QWORD *)&v190 + 1) = v100;
        NtfsTelemetryFillVcbVolumeState(v16);
        v101 = NtfsTelemetryGuard(2048);
        v103 = UnbiasedInterruptTime;
        if ( v101 )
          NtfsTelemetryVolumeSizeChange(
            (unsigned int)&v186,
            v16,
            IsClearOrSet,
            (unsigned __int16)v155,
            v100 - UnbiasedInterruptTime,
            v141,
            (__int64)&v189);
        LOBYTE(v102) = 1;
        NtfsRepairGetVolumeId(a1, v16, v102, (unsigned int)&UnicodeString, (__int64)&v145);
        if ( (IsClearOrSet & 0x80000000) != 0 )
        {
          if ( (Microsoft_Windows_NtfsEnableBits & 0x10000) != 0 )
          {
            if ( *((_QWORD *)&v190 + 1) && (_QWORD)v190 )
              v160 = (unsigned __int64)(1000 * (*((_QWORD *)&v190 + 1) - v190)) / NtfsPerformanceFrequency.QuadPart;
            else
              v160 = 0;
            if ( (_QWORD)v190 && *((_QWORD *)&v189 + 1) )
              v157 = (unsigned __int64)(1000 * (v190 - *((_QWORD *)&v189 + 1))) / NtfsPerformanceFrequency.QuadPart;
            else
              v157 = 0;
            if ( *((_QWORD *)&v189 + 1) && (_QWORD)v189 )
              *(_QWORD *)&BitMapHeader.SizeOfBitMap = (unsigned __int64)(1000 * (*((_QWORD *)&v189 + 1) - v189))
                                                    / NtfsPerformanceFrequency.QuadPart;
            else
              *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
            if ( v100 && v103 )
              v118 = 1000 * (v100 - v103) / NtfsPerformanceFrequency.QuadPart;
            else
              LOBYTE(v118) = 0;
            if ( v99 )
              v119 = *v34;
            else
              LOBYTE(v119) = 0;
            v120 = &word_140064400;
            v121 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6736) )
              v121 = *(const WCHAR **)(v16 + 6736);
            v170 = (__int64)v121;
            v122 = (*(_DWORD *)(v16 + 28) >> 2) & 1;
            v123 = *(_DWORD *)(v16 + 6660);
            if ( (unsigned int)(v123 - 1) > 0x13 )
              v123 = 0;
            v162[0] = v123;
            v124 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6720) )
              v124 = *(const WCHAR **)(v16 + 6720);
            v158 = (__int64)v124;
            v125 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6704) )
              v125 = *(const WCHAR **)(v16 + 6704);
            *(_QWORD *)v156 = v125;
            v126 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6688) )
              v126 = *(const WCHAR **)(v16 + 6688);
            *(_QWORD *)v159 = v126;
            v127 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6672) )
              v127 = *(const WCHAR **)(v16 + 6672);
            UnbiasedInterruptTime = (ULONGLONG)v127;
            if ( *(_QWORD *)(v16 + 7864) )
              v120 = *(const WCHAR **)(v16 + 7864);
            if ( (*(_DWORD *)(v16 + 4) & 0xC00) != 0x800
              && (v128 = *(_QWORD *)(v16 + 248)) != 0
              && (v129 = *(_QWORD *)(v128 + 16)) != 0 )
            {
              v130 = (*(_DWORD *)(v129 + 48) >> 8) & 1;
            }
            else
            {
              LOBYTE(v130) = 0;
            }
            v131 = (__int64)(v167 * *(unsigned int *)(v16 + 364));
            McTemplateK0jmztzzzzzqjqtzxxhhxxxxhqd_EtwWriteTransfer(
              v16 + 7808,
              v16 + 8528,
              v171 / 0x100000,
              v16 + 7824,
              v16 + 8528,
              (__int64)UnicodeString.Buffer,
              v130,
              (__int64)v120,
              UnbiasedInterruptTime,
              *(__int64 *)v159,
              *(__int64 *)v156,
              v158,
              v162[0],
              v16 + 7808,
              *(_DWORD *)(v16 + 6792),
              v122,
              v170,
              ((*((_QWORD *)&v131 + 1) & 0xFFFFFLL) + (__int64)v131) >> 20,
              v171 / 0x100000,
              a3 != 0,
              v119,
              v118,
              BitMapHeader.SizeOfBitMap,
              v157,
              v160,
              v152,
              IsClearOrSet,
              IsClearOrSet);
          }
        }
        else if ( (Microsoft_Windows_NtfsEnableBits & 0x800) != 0 )
        {
          if ( *((_QWORD *)&v190 + 1) && (_QWORD)v190 )
            v160 = (unsigned __int64)(1000 * (*((_QWORD *)&v190 + 1) - v190)) / NtfsPerformanceFrequency.QuadPart;
          else
            v160 = 0;
          if ( (_QWORD)v190 && *((_QWORD *)&v189 + 1) )
            v157 = (unsigned __int64)(1000 * (v190 - *((_QWORD *)&v189 + 1))) / NtfsPerformanceFrequency.QuadPart;
          else
            v157 = 0;
          if ( *((_QWORD *)&v189 + 1) && (_QWORD)v189 )
            *(_QWORD *)&BitMapHeader.SizeOfBitMap = (unsigned __int64)(1000 * (*((_QWORD *)&v189 + 1) - v189))
                                                  / NtfsPerformanceFrequency.QuadPart;
          else
            *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
          if ( v100 && v103 )
            v104 = 1000 * (v100 - v103) / NtfsPerformanceFrequency.QuadPart;
          else
            LOBYTE(v104) = 0;
          if ( v99 )
            v105 = *v34;
          else
            LOBYTE(v105) = 0;
          v106 = &word_140064400;
          v107 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6736) )
            v107 = *(const WCHAR **)(v16 + 6736);
          v170 = (__int64)v107;
          v108 = (*(_DWORD *)(v16 + 28) >> 2) & 1;
          v109 = *(_DWORD *)(v16 + 6660);
          if ( (unsigned int)(v109 - 1) > 0x13 )
            v109 = 0;
          v162[0] = v109;
          v110 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6720) )
            v110 = *(const WCHAR **)(v16 + 6720);
          v158 = (__int64)v110;
          v111 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6704) )
            v111 = *(const WCHAR **)(v16 + 6704);
          *(_QWORD *)v156 = v111;
          v112 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6688) )
            v112 = *(const WCHAR **)(v16 + 6688);
          *(_QWORD *)v159 = v112;
          v113 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6672) )
            v113 = *(const WCHAR **)(v16 + 6672);
          UnbiasedInterruptTime = (ULONGLONG)v113;
          if ( *(_QWORD *)(v16 + 7864) )
            v106 = *(const WCHAR **)(v16 + 7864);
          if ( (*(_DWORD *)(v16 + 4) & 0xC00) != 0x800
            && (v114 = *(_QWORD *)(v16 + 248)) != 0
            && (v115 = *(_QWORD *)(v114 + 16)) != 0 )
          {
            v116 = (*(_DWORD *)(v115 + 48) >> 8) & 1;
          }
          else
          {
            LOBYTE(v116) = 0;
          }
          v117 = (__int64)(v167 * *(unsigned int *)(v16 + 364));
          McTemplateK0jmztzzzzzqjqtzxxhhxxxx_EtwWriteTransfer(
            v16 + 7808,
            v16 + 8528,
            v171 / 0x100000,
            v16 + 7824,
            v16 + 8528,
            (__int64)UnicodeString.Buffer,
            v116,
            (__int64)v106,
            UnbiasedInterruptTime,
            *(__int64 *)v159,
            *(__int64 *)v156,
            v158,
            v162[0],
            v16 + 7808,
            *(_DWORD *)(v16 + 6792),
            v108,
            v170,
            ((*((_QWORD *)&v117 + 1) & 0xFFFFFLL) + (__int64)v117) >> 20,
            v171 / 0x100000,
            a3 != 0,
            v105,
            v104,
            BitMapHeader.SizeOfBitMap,
            v157,
            v160);
        }
        if ( v145 )
          RtlFreeUnicodeString(&UnicodeString);
        if ( BitMapBuffer )
          ExFreePoolWithTag(BitMapBuffer, 0);
        v132 = P;
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v151 )
          NtfsReleasePagingResourcePriv(v132, *(_QWORD *)(v16 + 72));
        if ( v144 )
          NtfsReleaseFcbEx(a1, *(_QWORD *)(v164 + 184), 0);
        if ( v150 )
        {
          NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 48) + 184LL), 0);
          NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 192) + 184LL), 0);
        }
        NtfsReleaseVcb(a1, v16);
        NtfsCleanupAttributeContext(v133, v185);
        if ( NtfsStatusDebugFlags
          && IsClearOrSet
          && IsClearOrSet != 294
          && IsClearOrSet - 298 > 1
          && IsClearOrSet < 0xFFFFFFED
          && IsClearOrSet != -1073741802
          && IsClearOrSet + 2147483643 > 1
          && IsClearOrSet != -1073741807
          && IsClearOrSet != 259
          && IsClearOrSet != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, IsClearOrSet, 1204522);
        }
        LOBYTE(v134) = v180 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v180, IsClearOrSet, v134, (IsClearOrSet & 0x80000000) == 0);
        return IsClearOrSet;
      }
      if ( *(_QWORD *)(v172 + 48) != *(_QWORD *)(v16 + 1480) )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v24 = 1203332;
          goto LABEL_258;
        }
        goto LABEL_259;
      }
      v20 = *(_QWORD *)(v16 + 5368);
      *(_QWORD *)&BitMapHeader.SizeOfBitMap = *(_QWORD *)(v16 + 5376);
      v171 = (*(_QWORD *)&BitMapHeader.SizeOfBitMap - 1LL) * *(unsigned int *)(v16 + 364);
      v175 = v171;
      IsClearOrSet = NtfsRunIsClearOrSet(a1, v16, v20, (unsigned int)*(_QWORD *)(v16 + 296) - (unsigned int)v20, 0, 0);
      v148 = IsClearOrSet;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0);
      if ( IsClearOrSet == -1073741791 || IsClearOrSet == -1073741267 )
      {
        if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v16 + 2160)) )
        {
          NtfsReleaseVcb(a1, v16);
          LOBYTE(v26) = 1;
          NtfsAcquireExclusiveVcb(a1, v16, v26);
          v146 = 1;
        }
        if ( (*(_DWORD *)(v16 + 4) & 1) == 0 )
        {
          IsClearOrSet = -1073741202;
          if ( NtfsStatusDebugFlags )
          {
            v24 = 1203458;
            goto LABEL_258;
          }
          goto LABEL_259;
        }
        NtfsAcquireAllFiles(a1, v16, 6, v25);
        v147 = 1;
        LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v27, fsctrl_c23834, v16);
        }
        NtfsFreeRecentlyDeallocated((int *)a1, *(_QWORD *)(a1 + 104), &NtfsLargeMax, 1);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v28, fsctrl_c23843, v16);
        }
        NtfsReleaseAllFiles(a1, v16, 6);
        v147 = 0;
        NtfsMarkUnusedContextPreTrimProcessing(a1, v29, v30, v31);
        LOBYTE(v32) = 1;
        NtfsWaitForDeallocatedClustersToDrain(*(_QWORD *)(a1 + 104), v32);
        NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0, 9);
        IsClearOrSet = NtfsRunIsClearOrSet(a1, v16, v20, (unsigned int)*(_QWORD *)(v16 + 296) - (unsigned int)v20, 0, 0);
        v148 = IsClearOrSet;
        NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0);
        v23 = v164;
      }
      v146 = 1;
      if ( (IsClearOrSet & 0x80000000) != 0 )
      {
        v146 = 1;
        goto LABEL_260;
      }
    }
    NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 192) + 184LL), 0, 1);
    if ( a3 )
    {
      NtfsAcquireExclusiveScbEx(a1, v23, 0);
      v144 = 1;
      if ( (unsigned __int64)(v20 << *(_BYTE *)(v16 + 488)) >= *(_QWORD *)(v23 + 24) )
      {
        NtfsReleaseFcbEx(a1, *(_QWORD *)(v23 + 184), 0);
        v144 = 0;
      }
      else
      {
        NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 0);
      }
LABEL_117:
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 48) + 184LL), 0, 1);
      v150 = 1;
      *(_QWORD *)&v190 = KeQueryUnbiasedInterruptTime();
      v152 = 3;
      v153 = 3;
      v41 = *(_QWORD *)(v16 + 72);
      v179 = v41;
      LOBYTE(v42) = 1;
      NtfsAcquirePagingResourceExclusive(a1, v41, v42, v43);
      v151 = 1;
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(v41 + 184), 0, 9);
      if ( a3 )
      {
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v16 + 720));
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v16 + 6376));
        v44 = *(_QWORD *)(v16 + 296) - v20;
        *(_QWORD *)v162 = *(_QWORD *)(v16 + 328) + (*(__int64 *)(v16 + 328) >> 8) + *(_QWORD *)(v16 + 6368);
        if ( v44 > *(_QWORD *)(v16 + 304) )
        {
          NtfsAllocateDiskFullContext(a1, v44 << *(_BYTE *)(v16 + 488), 0x27700125DDDLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225599LL, 1203678);
          IsClearOrSet = -1073741697;
          v148 = -1073741697;
        }
        if ( *(__int64 *)v162 >= *(_QWORD *)(v16 + 304) - v44 )
        {
          NtfsAllocateDiskFullContext(a1, v44 << *(_BYTE *)(v16 + 488), 0x27800125DE5LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225599LL, 1203686);
          IsClearOrSet = -1073741697;
          v148 = -1073741697;
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v16 + 6376));
        KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v16 + 720));
        if ( (IsClearOrSet & 0x80000000) != 0 )
          goto LABEL_260;
      }
      else
      {
        if ( *(_QWORD *)(v16 + 296) > v20 )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v24 = 1203705;
            goto LABEL_258;
          }
          goto LABEL_259;
        }
        if ( *(_QWORD *)(v16 + 296) == v20 )
        {
          IsClearOrSet = 0;
          goto LABEL_259;
        }
      }
      NtfsGetDiskGeometry(a1, *(_QWORD *)(v16 + 224), v188, v156);
      v45 = *(unsigned int *)(v16 + 364);
      if ( (_DWORD)v45 != LODWORD(v188[0]) || v171 + v45 > *(__int64 *)v156 )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v24 = 1203729;
          goto LABEL_258;
        }
        goto LABEL_259;
      }
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v41 + 288) + 16LL), 0, 0, &IoStatus);
      NtfsNormalizeAndCleanupTransaction(a1, &IoStatus);
      if ( (unsigned __int8)NtfsPurgeCacheSection(a1, v41, 0, 0, 0) )
      {
        NtfsSnapshotScb(a1, v41);
        *(_QWORD *)(*(_QWORD *)(v41 + 496) + 64LL) = 0;
        *(_QWORD *)(*(_QWORD *)(v41 + 496) + 72LL) = 0x7FFFFFFFFFFFFFFFLL;
        v46 = (((v20 + 7) >> 3) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        v47 = *(_BYTE *)(v16 + 488);
        v48 = (v46 + *(unsigned int *)(v16 + 480)) >> v47 << v47;
        v49 = (_QWORD *)(v41 + 24);
        v50 = *(_QWORD *)(v41 + 24);
        *(_QWORD *)v156 = v50;
        if ( v48 <= v50 )
        {
          *(_QWORD *)(v16 + 296) = 8 * v46;
          if ( v48 >= v50 )
            goto LABEL_151;
          NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 0);
LABEL_150:
          v49 = (_QWORD *)(v41 + 24);
LABEL_151:
          if ( (*(_DWORD *)(v41 + 200) & 0x20000) != 0 )
          {
            v56 = *(_QWORD *)(v41 + 464);
            if ( v56 >= v46 )
            {
              if ( *(_QWORD *)(v41 + 40) > v46 )
              {
                if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) )
                {
                  v57 = (v46 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                  if ( v57 < v56 )
                    *(_QWORD *)(v41 + 464) = v57;
                }
                else
                {
                  *(_QWORD *)(v41 + 464) = v46;
                }
              }
            }
            else
            {
              *(_QWORD *)(v41 + 464) = v46;
            }
          }
          *(_QWORD *)(v41 + 40) = v46;
          if ( (*(_DWORD *)(v41 + 200) & 0x20000) == 0 || *(_QWORD *)(v41 + 32) >= v46 )
            goto LABEL_173;
          v58 = *(_QWORD *)(v41 + 464);
          if ( v46 < v58 )
            v58 = (((v20 + 7) >> 3) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v58 <= v46 )
          {
LABEL_173:
            *(_QWORD *)(v41 + 32) = v46;
            *(_QWORD *)(v41 + 472) = *v49;
            LOBYTE(v48) = 1;
            NtfsWriteFileSizes(a1, v41, 0, v48, 1, 1);
            NtfsSetCcFileSizes(*(_QWORD *)(v41 + 280), v41, v41 + 24);
            if ( !a3 )
            {
              v61 = 8LL * *(_QWORD *)v156;
              if ( *(_QWORD *)(v16 + 296) < 8LL * *(_QWORD *)v156 )
                v61 = *(_QWORD *)(v16 + 296);
              v62 = *(_QWORD *)(v16 + 336);
              if ( v61 != v62 )
                NtfsModifyBitsInBitmap(a1, v16, v62, 22, 21);
              if ( v168 )
                NtfsModifyBitsInBitmap(a1, v16, v173, 21, 22);
            }
            if ( 8 * v46 != v20 )
              NtfsModifyBitsInBitmap(a1, v16, v20, 21, 0);
            P = ExAllocatePoolWithTag(
                  (POOL_TYPE)528,
                  (unsigned int)(*(_DWORD *)(v16 + 364) + *(_DWORD *)(*(_QWORD *)(v16 + 224) + 152LL)),
                  0x6646744Eu);
            v63 = *(int *)(*(_QWORD *)(v16 + 224) + 152LL);
            v64 = ~(_DWORD)v63 & ((unsigned __int64)P + v63);
            NtfsReadBootSector(a1, a2, v16, v64, v152);
            if ( (unsigned __int8)NtfsIsBootSectorNtfs(v64, v16) )
            {
              if ( *(_QWORD *)(v16 + 8144) )
              {
                v65 = v20 << *(_BYTE *)(v16 + 488);
                v66 = *(_QWORD *)(v16 + 8176);
                v67 = v65 < v66 ? 1LL : (v66 != 0) + 1 + (unsigned int)((v65 - v66) / *(_QWORD *)(v16 + 8152));
                v178 = v67;
                *(_QWORD *)SizeOfBitMap = v67;
                if ( (_DWORD)v67 != *(_DWORD *)(v16 + 8136) )
                {
                  v68 = (v152 + ((unsigned int)(v67 + 7) >> 3)) & 0xFFFFFFFC;
                  BitMapBuffer = (PULONG)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v68, 0x6646744Eu);
                  memset(BitMapBuffer, 0, v68);
                }
              }
              *(_QWORD *)(v16 + 296) = v20;
              v69 = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
              *(_QWORD *)(v16 + 432) = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
              *(_QWORD *)(v16 + 424) = --v69;
              *(_QWORD *)(v64 + 40) = v69;
              NtfsWriteBootSector(a1, a2, v16, v64, v152);
              NtfsCheckpointCurrentTransaction(a1);
              if ( !*(_QWORD *)(v16 + 8144) )
              {
LABEL_225:
                NtfsUpdateTieringInfo(a1);
                NtfsScanEntireBitmap(a1, v16, 10, 5);
                LfsFlushToLsn(*(_QWORD *)(v16 + 232), NtfsLargeMax);
                *(_QWORD *)(v16 + 336) = *(_QWORD *)(v16 + 296);
                v84 = *(_QWORD *)(v16 + 296) << *(_BYTE *)(v16 + 488);
                v85 = *(_QWORD *)(v16 + 192);
                if ( (*(_DWORD *)(v85 + 200) & 0x20000) != 0
                  && *(_QWORD *)(v85 + 24) > v84
                  && *(_QWORD *)(v85 + 464) > v84 )
                {
                  *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = v84;
                }
                *(_QWORD *)(*(_QWORD *)(v16 + 192) + 24LL) = v84;
                v86 = *(_QWORD *)(v16 + 192);
                if ( (*(_DWORD *)(v86 + 200) & 0x20000) == 0 )
                  goto LABEL_244;
                v87 = *(_QWORD *)(v86 + 24);
                if ( *(_QWORD *)(v86 + 32) >= v87 )
                  goto LABEL_244;
                if ( v87 >= *(_QWORD *)(v86 + 464) )
                  v87 = *(_QWORD *)(v86 + 464);
                if ( v87 <= *(_QWORD *)(v86 + 40) )
                {
LABEL_244:
                  *(_QWORD *)(*(_QWORD *)(v16 + 192) + 32LL) = *(_QWORD *)(*(_QWORD *)(v16 + 192) + 24LL);
                  v92 = *(_QWORD *)(v16 + 192);
                  v93 = *(_DWORD *)(v92 + 200);
                  if ( (v93 & 0x20000) != 0 )
                  {
                    v94 = *(_QWORD *)(v92 + 32);
                    v95 = *(_QWORD *)(v92 + 464);
                    if ( v95 < v94 )
                      goto LABEL_251;
                    if ( *(_QWORD *)(v92 + 40) <= v94 )
                      goto LABEL_253;
                    if ( !*(_QWORD *)(*(_QWORD *)(v92 + 288) + 16LL) || v94 == 0x7FFFFFFFFFFFFFFFLL )
                    {
LABEL_251:
                      v96 = *(_QWORD *)(v16 + 192);
                      v97 = *(_QWORD *)(v96 + 32);
                      goto LABEL_252;
                    }
                    if ( (__int64)((v94 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v95 )
                    {
                      v96 = *(_QWORD *)(v16 + 192);
                      v97 = (*(_QWORD *)(v96 + 32) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_252:
                      *(_QWORD *)(v96 + 464) = v97;
                    }
                  }
LABEL_253:
                  *(_QWORD *)(*(_QWORD *)(v16 + 192) + 40LL) = *(_QWORD *)(*(_QWORD *)(v16 + 192) + 32LL);
                  SetFlagInterlocked(v16 + 4, 128);
                  v99 = a3;
                  v34 = v154;
                  if ( !a3
                    || (*(_QWORD *)(v16 + 5368) = v98,
                        *(_QWORD *)(v16 + 5376) = 0,
                        *(_QWORD *)(v16 + 1480) = 0,
                        *(_DWORD *)v34 == 2) )
                  {
                    FsRtlNotifyVolumeEvent(*(PFILE_OBJECT *)(v172 + 48), 0xDu);
                  }
                  goto LABEL_262;
                }
                v88 = *(_QWORD *)(v16 + 192);
                v89 = *(_DWORD *)(v88 + 200);
                if ( (v89 & 0x20000) != 0 )
                {
                  v90 = *(_QWORD *)(v88 + 464);
                  if ( v90 < v87 )
                  {
LABEL_242:
                    *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = v87;
                    goto LABEL_243;
                  }
                  if ( *(_QWORD *)(v88 + 40) > v87 )
                  {
                    if ( *(_QWORD *)(*(_QWORD *)(v88 + 288) + 16LL) )
                    {
                      if ( v87 == 0x7FFFFFFFFFFFFFFFLL )
                      {
                        *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = 0x7FFFFFFFFFFFFFFFLL;
                      }
                      else
                      {
                        v91 = (v87 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                        if ( v91 < v90 )
                          *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = v91;
                      }
                      goto LABEL_243;
                    }
                    goto LABEL_242;
                  }
                }
LABEL_243:
                *(_QWORD *)(*(_QWORD *)(v16 + 192) + 40LL) = v87;
                goto LABEL_244;
              }
              v70 = (struct _RTL_BITMAP *)(v16 + 8136);
              v71 = *(_DWORD *)(v16 + 8136);
              v72 = 0;
              v177 = 0;
              if ( _bittest64(*(const signed __int64 **)(v16 + 8144), v71 - 1) && v71 > 1 )
              {
                RtlClearBit((PRTL_BITMAP)(v16 + 8136), v71 - 1);
                *(_QWORD *)(v16 + 288) -= (__int64)(*(unsigned int *)(v16 + 480) + *(_QWORD *)(v16 + 0x2000)) >> *(_BYTE *)(v16 + 488);
                v72 = v70->SizeOfBitMap - 1;
                v177 = v72;
              }
              v73 = BitMapBuffer;
              v74 = SizeOfBitMap[0];
              if ( BitMapBuffer && v71 > SizeOfBitMap[0] )
              {
                *(_QWORD *)(v16 + 288) -= *(_DWORD *)(v16 + 8160)
                                        * (unsigned int)RtlNumberOfSetBitsInRange(
                                                          v16 + 8136,
                                                          SizeOfBitMap[0],
                                                          v71 - SizeOfBitMap[0]);
                v74 = SizeOfBitMap[0];
                v73 = BitMapBuffer;
              }
              if ( v74 <= 1 )
              {
                *(_QWORD *)(v16 + 0x2000) = 0;
                *(_QWORD *)(v16 + 288) = *(_QWORD *)(v16 + 296);
                *(_QWORD *)(v16 + 8184) = *(_QWORD *)(v16 + 296) << *(_BYTE *)(v16 + 488);
              }
              else
              {
                v75 = *(_QWORD *)(v16 + 8184);
                if ( v75 != *(_QWORD *)(v16 + 8176) )
                {
                  *(_QWORD *)(v16 + 288) -= (v75 + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
                  *(_QWORD *)(v16 + 288) += (__int64)(*(_QWORD *)(v16 + 8176) + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
                  v75 = *(_QWORD *)(v16 + 8176);
                  *(_QWORD *)(v16 + 8184) = v75;
                }
                *(_QWORD *)(v16 + 0x2000) = (unsigned __int64)((v20 << *(_BYTE *)(v16 + 488)) - v75)
                                          % *(_QWORD *)(v16 + 8152);
              }
              if ( v73 )
              {
                LODWORD(BitMapHeader.Buffer) = 0;
                *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
                RtlInitializeBitMap(&BitMapHeader, v73, v74);
                v76 = SizeOfBitMap[0];
                if ( v71 < SizeOfBitMap[0] )
                  v76 = v71;
                RtlExtractBitMap(v16 + 8136, &BitMapHeader, 0, v76);
                ExFreePoolWithTag(*(PVOID *)(v16 + 8144), 0);
                *v70 = BitMapHeader;
                BitMapBuffer = 0;
                v74 = SizeOfBitMap[0];
              }
              if ( v72 )
              {
                if ( v72 < v74 - 1 )
                {
                  RtlSetBit((PRTL_BITMAP)(v16 + 8136), v72);
                  v77 = *(unsigned int *)(v16 + 8160);
LABEL_210:
                  *(_QWORD *)(v16 + 288) += v77;
LABEL_214:
                  if ( v168 )
                  {
                    v78 = v173 << *(_BYTE *)(v16 + 488);
                    v79 = *(_QWORD *)(v16 + 8184);
                    if ( v78 < v79 )
                      v80 = 0;
                    else
                      v80 = (v79 != 0) + (unsigned int)((v78 - v79) / *(_QWORD *)(v16 + 8152));
                    v81 = (v173 + v168 - 1) << *(_BYTE *)(v16 + 488);
                    if ( v81 < v79 )
                      v82 = 0;
                    else
                      v82 = (v79 != 0) + (unsigned int)((v81 - v79) / *(_QWORD *)(v16 + 8152));
                    *(_QWORD *)(v16 + 288) += *(_DWORD *)(v16 + 8160)
                                            * (unsigned int)RtlNumberOfClearBitsInRange(v16 + 8136, v80, v82 - v80 + 1);
                    if ( v82 == SizeOfBitMap[0] - 1 && !_bittest64(*(const signed __int64 **)(v16 + 8144), v82) )
                    {
                      v83 = *(_QWORD *)(v16 + 288) - *(unsigned int *)(v16 + 8160);
                      *(_QWORD *)(v16 + 288) = v83;
                      *(_QWORD *)(v16 + 288) = v83
                                             + *(_QWORD *)(v16 + 0x2000)
                                             / (unsigned __int64)*(unsigned int *)(v16 + 356);
                    }
                    RtlSetBits((PRTL_BITMAP)(v16 + 8136), v80, v82 - v80 + 1);
                  }
                  goto LABEL_225;
                }
                if ( v72 == v74 - 1 )
                {
                  RtlSetBit((PRTL_BITMAP)(v16 + 8136), v72);
                  v77 = (__int64)(*(_QWORD *)(v16 + 0x2000) + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
                  goto LABEL_210;
                }
              }
              if ( _bittest64(*(const signed __int64 **)(v16 + 8144), v74 - 1) && v74 > 1 )
              {
                *(_QWORD *)(v16 + 288) -= *(unsigned int *)(v16 + 8160);
                *(_QWORD *)(v16 + 288) += (__int64)(*(_QWORD *)(v16 + 0x2000) + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
              }
              goto LABEL_214;
            }
LABEL_419:
            v180 = 0xDD00125F5BLL;
            NtfsAttachCorruptionSimple(a1, 1, 2050, 1204059, 0, v141);
            NtfsAttachRepairInfoPriv(a1, 0, 0, 0xDD00125F5BLL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3221225522LL, 1204059);
            NtfsRaiseStatusInternal(a1, -1073741774, 0, 0, 1204059);
            __debugbreak();
            JUMPOUT(0x140280D13LL);
          }
          v59 = *(_DWORD *)(v41 + 200);
          if ( (v59 & 0x20000) != 0 )
          {
            v48 = *(_QWORD *)(v41 + 464);
            if ( v48 < v58 )
            {
LABEL_171:
              *(_QWORD *)(v41 + 464) = v58;
              goto LABEL_172;
            }
            if ( *(_QWORD *)(v41 + 40) > v58 )
            {
              if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) && v58 != 0x7FFFFFFFFFFFFFFFLL )
              {
                v60 = (v58 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                if ( v60 < v48 )
                  *(_QWORD *)(v41 + 464) = v60;
                goto LABEL_172;
              }
              goto LABEL_171;
            }
          }
LABEL_172:
          *(_QWORD *)(v41 + 40) = v58;
          goto LABEL_173;
        }
        v162[0] = v48 - v50;
        v168 = (v48 - v50) >> v47;
        v183 = v168;
        v51 = *(_QWORD *)(v16 + 336);
        v52 = v51 + 1;
        v182 = v51 + 1;
        if ( v51 + 1 + v168 > v20 )
          v52 = v51;
        v173 = v52;
        v182 = v52;
        NtfsPreloadAllocationInternal(a1, v50 >> v47, 0);
        if ( (*(_DWORD *)(a1 + 12) & 0x20000) == 0 )
        {
          NtfsAddAllocation(a1, v168, 0, 0);
          *(_QWORD *)(v16 + 296) = 8 * v46;
          v168 = 0;
          v183 = 0;
LABEL_147:
          NtfsSetCcFileSizes(*(_QWORD *)(v41 + 280), v41, v41 + 24);
          goto LABEL_150;
        }
        if ( !*(_QWORD *)(v16 + 8144)
          || (IsClearOrSet = NtfsSetTPMap(a1, v173, v168, v152), v148 = IsClearOrSet, (IsClearOrSet & 0x80000000) == 0) )
        {
          if ( NtfsAddNtfsMcbEntry(v41 + 400, *(__int64 *)v156 >> *(_BYTE *)(v16 + 488), v173, v168, 0, 1u) )
          {
            v149 = 1;
            NtfsWriteBytes(a1, v16, v41, v156[0], 0, v162[0], ((unsigned int)dword_1400956B8 >> 19) & 4);
            *(_QWORD *)(v16 + 296) = 8 * v46;
            LOBYTE(v143) = 0;
            v53 = NtfsLookupInFileRecord(
                    a1,
                    *(_QWORD *)(v41 + 184),
                    *(_QWORD *)(v41 + 184) + 8LL,
                    *(unsigned int *)(v41 + 256),
                    v41 + 264,
                    0,
                    v143,
                    0,
                    0,
                    v185);
            v55 = 0;
            if ( v53 || (*(_DWORD *)(v41 + 512) & 4) != 0 )
            {
              LOBYTE(v142) = 0;
              NtfsAddAttributeAllocation(a1, v41, v185, 0, 0, v142);
              v149 = 0;
              goto LABEL_147;
            }
LABEL_416:
            NtfsAttachCorruption_BadOrOrphanFRS(
              a1,
              v55 + 2,
              1203920,
              v54,
              *(_QWORD *)(v41 + 184) + 8LL,
              *(_QWORD *)(v41 + 184),
              v55);
            NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA900125ED0LL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 1203920);
            NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v41 + 184) + 8, *(_QWORD *)(v41 + 184), 1203920);
            goto LABEL_419;
          }
LABEL_413:
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225626LL, 1203886);
          NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 1203886);
          goto LABEL_416;
        }
      }
      else
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225499LL, 1203751);
        v139 = NtfsRaiseStatusInternal(a1, -1073741797, 0, 0, 1203751);
        if ( NtfsStatusDebugFlags
          && v139
          && v139 != 294
          && v139 - 298 > 1
          && v139 < 0xFFFFFFED
          && v139 != -1073741802
          && v139 + 2147483643 > 1
          && v139 != -1073741807
          && v139 != 259
          && v139 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(0, v139, 1203849);
        }
        v140 = v158;
        *(_DWORD *)(v158 + 4) &= ~0x100u;
        *(_DWORD *)(v140 + 24) = 0;
        *(_DWORD *)(v140 + 12) |= 0x20000u;
        NtfsRaiseStatusInternal(v140, -1073741608, 0, 0, 1203858);
      }
      if ( NtfsStatusDebugFlags
        && IsClearOrSet < 0xFFFFFFED
        && IsClearOrSet != -1073741802
        && IsClearOrSet + 2147483643 > 1
        && IsClearOrSet != -1073741807
        && IsClearOrSet != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, IsClearOrSet, 1203875);
      }
      NtfsRaiseStatusInternal(a1, IsClearOrSet, 0, 0, 1203875);
      goto LABEL_413;
    }
    v35 = v20 << *(_BYTE *)(v16 + 488);
    v36 = v164;
    NtfsAcquireExclusiveScbEx(a1, v164, 0);
    v144 = 1;
    v37 = *(_QWORD *)(v36 + 24);
    if ( v35 <= v37 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v36 + 184), 0);
      v144 = 0;
      goto LABEL_117;
    }
    NtfsAddSparseAllocation(a1, v35 - v37);
    if ( (*(_DWORD *)(v36 + 200) & 0x20000) == 0 || *(_QWORD *)(v36 + 32) >= v35 )
      goto LABEL_115;
    v38 = *(_QWORD *)(v36 + 464);
    if ( v35 < v38 )
      v38 = v35;
    if ( v38 <= *(_QWORD *)(v36 + 40) )
    {
LABEL_115:
      *(_QWORD *)(v36 + 32) = v35;
      NtfsWriteFileSizes(a1, v36, 0, 0, 1, 1);
      goto LABEL_117;
    }
    if ( (*(_DWORD *)(v36 + 200) & 0x20000) != 0 )
    {
      v39 = *(_QWORD *)(v36 + 464);
      if ( v39 < v38 )
      {
LABEL_113:
        *(_QWORD *)(v36 + 464) = v38;
        goto LABEL_114;
      }
      if ( *(_QWORD *)(v36 + 40) > v38 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v36 + 288) + 16LL) && v38 != 0x7FFFFFFFFFFFFFFFLL )
        {
          v40 = (v38 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v40 < v39 )
            *(_QWORD *)(v36 + 464) = v40;
          goto LABEL_114;
        }
        goto LABEL_113;
      }
    }
LABEL_114:
    *(_QWORD *)(v36 + 40) = v38;
    goto LABEL_115;
  }
  v17 = -1073741662;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221225634LL, 1203074);
  LOBYTE(v15) = a2 != 0;
  NtfsExtendedCompleteRequestInternal(a1, a2, 3221225634LL, v15, 0);
  if ( !NtfsStatusDebugFlags )
    return v17;
  v18 = 1203075;
LABEL_389:
  NtfsStatusTraceAndDebugInternal(0, v17, v18);
  return v17;
}

```

## disassembly

```asm
0x14027e418  mov     r11, rsp
0x14027e41b  mov     [r11+18h], r8b
0x14027e41f  push    rbx
0x14027e420  push    rsi
0x14027e421  push    rdi
0x14027e422  push    r12
0x14027e424  push    r13
0x14027e426  push    r14
0x14027e428  push    r15
0x14027e42a  sub     rsp, 2C0h
0x14027e431  mov     rax, cs:__security_cookie
0x14027e438  xor     rax, rsp
0x14027e43b  mov     [rsp+2F8h+var_40], rax
0x14027e443  mov     r12b, r8b
0x14027e446  mov     r13, rdx
0x14027e449  mov     [rsp+2F8h+var_128], rdx
0x14027e451  mov     r14, rcx
0x14027e454  mov     [rsp+2F8h+var_1E0], rcx
0x14027e45c  xor     edi, edi
0x14027e45e  mov     esi, edi
0x14027e460  mov     [rsp+2F8h+var_214], edi
0x14027e467  mov     [r11-1D8h], rdi
0x14027e46e  mov     [r11-1D0h], rdi
0x14027e475  mov     eax, edi
0x14027e477  mov     [r11-170h], rax
0x14027e47e  mov     [r11-148h], rax
0x14027e485  xorps   xmm0, xmm0
0x14027e488  movups  xmmword ptr [rsp+2F8h+IoStatus], xmm0
0x14027e490  xor     edx, edx; Val
0x14027e492  lea     r8d, [rdi+58h]; Size
0x14027e496  lea     rcx, [r11-0F8h]; void *
0x14027e49d  call    memset
0x14027e4a2  xorps   xmm0, xmm0
0x14027e4a5  xor     eax, eax
0x14027e4a7  movups  [rsp+2F8h+var_80], xmm0
0x14027e4af  movups  [rsp+2F8h+var_80+0Ch], xmm0
0x14027e4b7  mov     qword ptr [rsp+2F8h+var_1F0], rdi
0x14027e4bf  movups  xmmword ptr [rsp+2F8h+UnicodeString.Length], xmm0
0x14027e4c7  mov     [rsp+2F8h+var_217], dil
0x14027e4cf  xorps   xmm1, xmm1
0x14027e4d2  movups  [rsp+2F8h+var_98], xmm1
0x14027e4da  mov     [rsp+2F8h+var_88], rax
0x14027e4e2  mov     [rsp+2F8h+var_204], di
0x14027e4ea  movups  [rsp+2F8h+var_60], xmm0
0x14027e4f2  movups  [rsp+2F8h+var_50], xmm0
0x14027e4fa  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14027e501  nop     dword ptr [rax+rax+00h]
0x14027e506  mov     [rsp+2F8h+var_1A0], rax
0x14027e50e  mov     qword ptr [rsp+2F8h+var_60], rax
0x14027e516  lea     eax, [rdi+1]
0x14027e519  mov     [rsp+2F8h+var_204], ax
0x14027e521  test    r13, r13
0x14027e524  jz      loc_14027E5C6
0x14027e52a  lea     rdx, [rsp+2F8h+var_98+8]
0x14027e532  mov     rcx, r13
0x14027e535  call    cs:__imp_IoGetActivityIdIrp
0x14027e53c  nop     dword ptr [rax+rax+00h]
0x14027e541  test    eax, eax
0x14027e543  jns     loc_14027E5F5
0x14027e549  mov     qword ptr [rsp+2F8h+var_98], rdi
0x14027e551  mov     rcx, [r13+0B8h]
0x14027e558  mov     [rsp+2F8h+var_168], rcx
0x14027e560  mov     eax, [rcx+10h]
0x14027e563  test    r12b, r12b
0x14027e566  jz      loc_14027E628
0x14027e56c  cmp     eax, 18h
0x14027e56f  jnb     loc_14027E60A
0x14027e575  mov     al, cs:NtfsStatusDebugFlags
0x14027e57b  mov     esi, 0C000000Dh
0x14027e580  test    al, al
0x14027e582  jz      short loc_14027E594
0x14027e584  mov     r8d, 125B3Fh
0x14027e58a  mov     edx, esi
0x14027e58c  mov     rcx, r14
0x14027e58f  call    NtfsStatusTraceAndDebugInternal
0x14027e594  test    r13, r13
0x14027e597  setnz   r9b
0x14027e59b  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e59f  mov     r8d, esi
0x14027e5a2  mov     rdx, r13
0x14027e5a5  mov     rcx, r14
0x14027e5a8  call    NtfsExtendedCompleteRequestInternal
0x14027e5ad  mov     al, cs:NtfsStatusDebugFlags
0x14027e5b3  test    al, al
0x14027e5b5  jz      loc_140280994
0x14027e5bb  mov     r8d, 125B40h
0x14027e5c1  jmp     loc_14028098B
0x14027e5c6  call    cs:__imp_IoGetActivityIdThread
0x14027e5cd  nop     dword ptr [rax+rax+00h]
0x14027e5d2  mov     rcx, rax
0x14027e5d5  test    rax, rax
0x14027e5d8  jz      loc_14027E549
0x14027e5de  mov     rax, [rax]
0x14027e5e1  mov     qword ptr [rsp+2F8h+var_98+8], rax
0x14027e5e9  mov     rax, [rcx+8]
0x14027e5ed  mov     [rsp+2F8h+var_88], rax
0x14027e5f5  lea     rax, [rsp+2F8h+var_98+8]
0x14027e5fd  mov     qword ptr [rsp+2F8h+var_98], rax
0x14027e605  jmp     loc_14027E551
0x14027e60a  mov     rbx, [r13+18h]
0x14027e60e  mov     r15, [rbx+10h]
0x14027e612  movzx   edi, word ptr [rbx]
0x14027e615  mov     [rsp+2F8h+var_1F8], edi
0x14027e61c  mov     [rsp+2F8h+var_1C8], di
0x14027e624  xor     edi, edi
0x14027e626  jmp     short loc_14027E699
0x14027e628  cmp     eax, 8
0x14027e62b  jnb     short loc_14027E67E
0x14027e62d  mov     al, cs:NtfsStatusDebugFlags
0x14027e633  mov     esi, 0C000000Dh
0x14027e638  test    al, al
0x14027e63a  jz      short loc_14027E64C
0x14027e63c  mov     r8d, 125B4Ch
0x14027e642  mov     edx, esi
0x14027e644  mov     rcx, r14
0x14027e647  call    NtfsStatusTraceAndDebugInternal
0x14027e64c  test    r13, r13
0x14027e64f  setnz   r9b
0x14027e653  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e657  mov     r8d, esi
0x14027e65a  mov     rdx, r13
0x14027e65d  mov     rcx, r14
0x14027e660  call    NtfsExtendedCompleteRequestInternal
0x14027e665  mov     al, cs:NtfsStatusDebugFlags
0x14027e66b  test    al, al
0x14027e66d  jz      loc_140280994
0x14027e673  mov     r8d, 125B4Dh
0x14027e679  jmp     loc_14028098B
0x14027e67e  mov     rbx, rdi
0x14027e681  mov     eax, edi
0x14027e683  mov     [rsp+2F8h+var_1F8], eax
0x14027e68a  mov     [rsp+2F8h+var_1C8], ax
0x14027e692  mov     rax, [r13+18h]
0x14027e696  mov     r15, [rax]
0x14027e699  mov     qword ptr [rsp+2F8h+BitMapHeader.SizeOfBitMap], r15
0x14027e6a1  mov     [rsp+2F8h+var_1E8], rbx
0x14027e6a9  mov     [rsp+2F8h+var_200], rbx
0x14027e6b1  mov     byte ptr [rsp+2F8h+var_2C8], 1
0x14027e6b6  lea     rax, [rsp+2F8h+var_1D0]
0x14027e6be  mov     qword ptr [rsp+2F8h+var_2D0], rax
0x14027e6c3  lea     rax, [rsp+2F8h+var_178]
0x14027e6cb  mov     [rsp+2F8h+Timeout], rax
0x14027e6d0  lea     r9, [rsp+2F8h+var_120]
0x14027e6d8  lea     r8, [rsp+2F8h+var_1D8]
0x14027e6e0  mov     rdx, [rcx+30h]
0x14027e6e4  mov     rcx, r14
0x14027e6e7  call    NtfsDecodeFileObject
0x14027e6ec  cmp     eax, 4
0x14027e6ef  jz      short loc_14027E742
0x14027e6f1  mov     al, cs:NtfsStatusDebugFlags
0x14027e6f7  mov     esi, 0C000000Dh
0x14027e6fc  test    al, al
0x14027e6fe  jz      short loc_14027E710
0x14027e700  mov     r8d, 125B61h
0x14027e706  mov     edx, esi
0x14027e708  mov     rcx, r14
0x14027e70b  call    NtfsStatusTraceAndDebugInternal
0x14027e710  test    r13, r13
0x14027e713  setnz   r9b
0x14027e717  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e71b  mov     r8d, esi
0x14027e71e  mov     rdx, r13
0x14027e721  mov     rcx, r14
0x14027e724  call    NtfsExtendedCompleteRequestInternal
0x14027e729  mov     al, cs:NtfsStatusDebugFlags
0x14027e72f  test    al, al
0x14027e731  jz      loc_140280994
0x14027e737  mov     r8d, 125B62h
0x14027e73d  jmp     loc_14028098B
0x14027e742  mov     rcx, [rsp+2F8h+var_1D0]
0x14027e74a  test    rcx, rcx
0x14027e74d  jz      loc_14028099B
0x14027e753  bt      word ptr [rcx+68h], 9
0x14027e759  jnb     loc_14028099B
0x14027e75f  mov     rdi, qword ptr [rsp+2F8h+var_1D8]
0x14027e767  test    dword ptr [rdi+4], 2000000h
0x14027e76e  jz      short loc_14027E7C1
0x14027e770  mov     al, cs:NtfsStatusDebugFlags
0x14027e776  mov     ebx, 0C00000A2h
0x14027e77b  test    al, al
0x14027e77d  jz      short loc_14027E78F
0x14027e77f  mov     r8d, 125B82h
0x14027e785  mov     edx, ebx
0x14027e787  mov     rcx, r14
0x14027e78a  call    NtfsStatusTraceAndDebugInternal
0x14027e78f  test    r13, r13
0x14027e792  setnz   r9b
0x14027e796  mov     dword ptr [rsp+2F8h+Timeout], esi
0x14027e79a  mov     r8d, ebx
0x14027e79d  mov     rdx, r13
0x14027e7a0  mov     rcx, r14
0x14027e7a3  call    NtfsExtendedCompleteRequestInternal
0x14027e7a8  mov     al, cs:NtfsStatusDebugFlags
0x14027e7ae  test    al, al
0x14027e7b0  jz      loc_140280A80
0x14027e7b6  mov     r8d, 125B83h
0x14027e7bc  jmp     loc_140280A77
0x14027e7c1  lea     rcx, [rdi+19E8h]; Object
0x14027e7c8  mov     [rsp+2F8h+Timeout], rsi; Timeout
0x14027e7cd  xor     r9d, r9d; Alertable
0x14027e7d0  xor     r8d, r8d; WaitMode
0x14027e7d3  xor     edx, edx; WaitReason
0x14027e7d5  call    cs:__imp_KeWaitForSingleObject
0x14027e7dc  nop     dword ptr [rax+rax+00h]
0x14027e7e1  xor     r8d, r8d
0x14027e7e4  test    r12b, r12b
0x14027e7e7  jz      loc_14027E8B4
0x14027e7ed  cmp     [rbx+8], r8
0x14027e7f1  jz      short loc_14027E848
0x14027e7f3  mov     al, cs:NtfsStatusDebugFlags
0x14027e7f9  mov     esi, 0C000000Dh
0x14027e7fe  test    al, al
0x14027e800  jz      short loc_14027E815
0x14027e802  mov     r8d, 125B9Ah
0x14027e808  mov     edx, esi
0x14027e80a  mov     rcx, r14
0x14027e80d  call    NtfsStatusTraceAndDebugInternal
0x14027e812  xor     r8d, r8d
0x14027e815  test    r13, r13
0x14027e818  setnz   r9b
0x14027e81c  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e821  mov     r8d, esi
0x14027e824  mov     rdx, r13
0x14027e827  mov     rcx, r14
0x14027e82a  call    NtfsExtendedCompleteRequestInternal
0x14027e82f  mov     al, cs:NtfsStatusDebugFlags
0x14027e835  test    al, al
0x14027e837  jz      loc_140280994
0x14027e83d  mov     r8d, 125B9Bh
0x14027e843  jmp     loc_14028098B
0x14027e848  test    r12b, r12b
0x14027e84b  jz      short loc_14027E8B4
0x14027e84d  cmp     dword ptr [rbx], 1
0x14027e850  jz      short loc_14027E8B4
0x14027e852  test    r15, r15
0x14027e855  jz      short loc_14027E8AC
0x14027e857  mov     al, cs:NtfsStatusDebugFlags
0x14027e85d  mov     esi, 0C000000Dh
0x14027e862  test    al, al
0x14027e864  jz      short loc_14027E879
0x14027e866  mov     r8d, 125BC6h
0x14027e86c  mov     edx, esi
0x14027e86e  mov     rcx, r14
0x14027e871  call    NtfsStatusTraceAndDebugInternal
0x14027e876  xor     r8d, r8d
0x14027e879  test    r13, r13
0x14027e87c  setnz   r9b
0x14027e880  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e885  mov     r8d, esi
0x14027e888  mov     rdx, r13
0x14027e88b  mov     rcx, r14
0x14027e88e  call    NtfsExtendedCompleteRequestInternal
0x14027e893  mov     al, cs:NtfsStatusDebugFlags
0x14027e899  test    al, al
0x14027e89b  jz      loc_140280994
0x14027e8a1  mov     r8d, 125BC7h
0x14027e8a7  jmp     loc_14028098B
0x14027e8ac  mov     r12, r8
0x14027e8af  jmp     loc_14027E94F
0x14027e8b4  test    r15, r15
0x14027e8b7  jg      short loc_14027E90E
0x14027e8b9  mov     al, cs:NtfsStatusDebugFlags
0x14027e8bf  mov     esi, 0C000000Dh
0x14027e8c4  test    al, al
0x14027e8c6  jz      short loc_14027E8DB
0x14027e8c8  mov     r8d, 125BACh
0x14027e8ce  mov     edx, esi
0x14027e8d0  mov     rcx, r14
0x14027e8d3  call    NtfsStatusTraceAndDebugInternal
0x14027e8d8  xor     r8d, r8d
0x14027e8db  test    r13, r13
0x14027e8de  setnz   r9b
0x14027e8e2  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e8e7  mov     r8d, esi
0x14027e8ea  mov     rdx, r13
0x14027e8ed  mov     rcx, r14
0x14027e8f0  call    NtfsExtendedCompleteRequestInternal
0x14027e8f5  mov     al, cs:NtfsStatusDebugFlags
0x14027e8fb  test    al, al
0x14027e8fd  jz      loc_140280994
0x14027e903  mov     r8d, 125BADh
0x14027e909  jmp     loc_14028098B
0x14027e90e  mov     edx, [rdi+16Ch]
0x14027e914  lea     rax, [r15-1]
0x14027e918  imul    rdx, rax
0x14027e91c  mov     [rsp+2F8h+var_170], rdx
0x14027e924  mov     [rsp+2F8h+var_148], rdx
0x14027e92c  cmp     rdx, r15
0x14027e92f  jl      loc_14028093F
0x14027e935  mov     cl, [rdi+1E8h]
0x14027e93b  mov     r12, rdx
0x14027e93e  sar     r12, cl
0x14027e941  mov     eax, 0FFFFFFFEh
0x14027e946  cmp     r12, rax
0x14027e949  jg      loc_14028093F
0x14027e94f  mov     [rsp+2F8h+var_130], r8
0x14027e957  mov     [rsp+2F8h+var_188], r8
0x14027e95f  mov     [rsp+2F8h+var_160], r8
0x14027e967  mov     [rsp+2F8h+P], r8
0x14027e96f  mov     [rsp+2F8h+var_210], r8b
  ... truncated ...
```
