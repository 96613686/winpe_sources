# NtfsChangeVolumeSize

- ea: `0x14027e3c8`
- end: `0x140280cc3`
- name: `NtfsChangeVolumeSize`
- size: `10491`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401f5890`

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
- `0x140047c74`
- `0x140047fac`
- `0x140059250`
- `0x1400596c0`
- `0x1400c3090`
- `0x1400cc568`
- `0x1400d1da8`
- `0x1400f70d4`
- `0x1401250b0`
- `0x14012c1ec`
- `0x140137a5c`
- `0x14013c2d0`
- `0x14013cde0`
- `0x140140380`
- `0x14014dde0`
- `0x140150bc0`
- `0x140150c80`
- `0x14015ec38`
- `0x140160be0`
- `0x1401620c0`
- `0x140162370`
- `0x14016da60`
- `0x140174520`
- `0x140174afc`
- `0x14017517c`
- `0x1401aab20`
- `0x1401c00e0`
- `0x1401cb2c4`
- `0x1401d24d8`
- `0x1401d2c34`
- `0x1401d2cec`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14027e4e5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14027e4e5`
- `ntoskrnl!RtlSetBit` at `0x14027fb9c`
- `ntoskrnl!RtlSetBit` at `0x14027fbc5`
- `ntoskrnl!RtlSetBit` at `0x14027fb9c`
- `ntoskrnl!RtlSetBit` at `0x14027fbc5`
- `ntoskrnl!RtlSetBits` at `0x14027fd50`
- `ntoskrnl!RtlSetBits` at `0x14027fd50`
- `ntoskrnl!RtlNumberOfClearBitsInRange` at `0x14027fcd2`
- `ntoskrnl!RtlNumberOfClearBitsInRange` at `0x14027fcd2`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140280044`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140280044`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e4aa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e9d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027f062`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140280087`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402bba14`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e4aa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e9d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027f062`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140280087`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402bba14`
- `ntoskrnl!RtlClearBit` at `0x14027f9bb`
- `ntoskrnl!RtlClearBit` at `0x14027f9bb`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x14027fa19`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x14027fa19`
- `ntoskrnl!RtlExtractBitMap` at `0x14027fb4a`
- `ntoskrnl!RtlExtractBitMap` at `0x14027fb4a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14028079d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc1de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc36a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3aa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14028079d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc1de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc36a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3aa`
- `ntoskrnl!IoGetActivityIdThread` at `0x14027e576`
- `ntoskrnl!IoGetActivityIdThread` at `0x14027e576`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027e785`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027e785`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14027f1e8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14027f1e8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14027f1d5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14027f1d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14027fb5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc204`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc24e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14027fb5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc204`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc24e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14027fb1e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14027fb1e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f832`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f913`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f832`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f913`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14027f0ec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14027f0ec`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027f0d9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027f0d9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14027ebc3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14027ebc3`
- `ntoskrnl!CcFlushCache` at `0x14027f25c`
- `ntoskrnl!CcFlushCache` at `0x14027f25c`

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
  __int64 v43; // r15
  __int64 v44; // rax
  signed __int64 v45; // r15
  char v46; // cl
  __int64 v47; // r9
  _QWORD *v48; // r11
  __int64 v49; // r8
  LONGLONG v50; // rdx
  LONGLONG v51; // r9
  char v52; // al
  int v53; // r9d
  int v54; // r8d
  signed __int64 v55; // r8
  signed __int64 v56; // rcx
  signed __int64 v57; // rcx
  int v58; // edx
  signed __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // r8
  __int64 v62; // rcx
  unsigned __int64 v63; // r15
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rcx
  __int64 v66; // rax
  SIZE_T v67; // rbx
  __int64 v68; // rax
  struct _RTL_BITMAP *v69; // r15
  unsigned int v70; // r13d
  ULONG v71; // ebx
  ULONG *v72; // r10
  ULONG v73; // r9d
  __int64 v74; // rdx
  __int64 v75; // r9
  __int64 v76; // rax
  unsigned __int64 v77; // rax
  unsigned __int64 v78; // r8
  ULONG v79; // r15d
  unsigned __int64 v80; // rax
  unsigned int v81; // ebx
  __int64 v82; // r9
  __int64 v83; // rdx
  __int64 v84; // rax
  __int64 v85; // rdx
  signed __int64 v86; // rcx
  __int64 v87; // rax
  int v88; // edx
  signed __int64 v89; // r9
  signed __int64 v90; // r8
  __int64 v91; // rax
  int v92; // edx
  signed __int64 v93; // rcx
  signed __int64 v94; // r8
  __int64 v95; // rcx
  unsigned __int64 v96; // rax
  __int64 v97; // r10
  char v98; // r12
  ULONGLONG v99; // rbx
  char v100; // al
  int v101; // r8d
  ULONGLONG v102; // r13
  __int64 v103; // r8
  __int64 v104; // r9
  unsigned __int64 v105; // r13
  __int16 v106; // r15
  const WCHAR *v107; // r11
  const WCHAR *v108; // rcx
  int v109; // r12d
  int v110; // edx
  const WCHAR *v111; // rcx
  const WCHAR *v112; // rcx
  const WCHAR *v113; // rcx
  const WCHAR *v114; // rcx
  __int64 v115; // rax
  __int64 v116; // rbx
  int v117; // ebx
  __int128 v118; // rax
  unsigned __int64 v119; // r13
  __int16 v120; // r15
  const WCHAR *v121; // r11
  const WCHAR *v122; // rcx
  int v123; // r12d
  int v124; // edx
  const WCHAR *v125; // rcx
  const WCHAR *v126; // rcx
  const WCHAR *v127; // rcx
  const WCHAR *v128; // rcx
  __int64 v129; // rax
  __int64 v130; // rbx
  int v131; // ebx
  __int128 v132; // rax
  PVOID v133; // rcx
  __int64 v134; // rcx
  __int64 v135; // r9
  __int16 v137; // r10
  __int64 v138; // rax
  unsigned __int16 v139; // cx
  unsigned int v140; // eax
  __int64 v141; // rcx
  int v142; // [rsp+120h] [rbp-2D0h]
  int v143; // [rsp+120h] [rbp-2D0h]
  int v144; // [rsp+128h] [rbp-2C8h]
  char v145; // [rsp+1D8h] [rbp-218h]
  char v146; // [rsp+1D9h] [rbp-217h] BYREF
  char v147; // [rsp+1DAh] [rbp-216h]
  char v148; // [rsp+1DBh] [rbp-215h]
  int v149; // [rsp+1DCh] [rbp-214h]
  char v150; // [rsp+1E0h] [rbp-210h]
  char v151; // [rsp+1E1h] [rbp-20Fh]
  char v152; // [rsp+1E2h] [rbp-20Eh]
  int v153; // [rsp+1E4h] [rbp-20Ch]
  __int16 v154; // [rsp+1ECh] [rbp-204h]
  __int16 *v155; // [rsp+1F0h] [rbp-200h]
  int v156; // [rsp+1F8h] [rbp-1F8h]
  int v157[2]; // [rsp+200h] [rbp-1F0h] BYREF
  unsigned __int64 v158; // [rsp+208h] [rbp-1E8h]
  __int64 v159; // [rsp+210h] [rbp-1E0h]
  int v160[2]; // [rsp+218h] [rbp-1D8h] BYREF
  unsigned __int64 v161; // [rsp+220h] [rbp-1D0h] BYREF
  __int16 v162; // [rsp+228h] [rbp-1C8h]
  int v163[2]; // [rsp+230h] [rbp-1C0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+238h] [rbp-1B8h] BYREF
  __int64 v165; // [rsp+248h] [rbp-1A8h]
  ULONGLONG UnbiasedInterruptTime; // [rsp+250h] [rbp-1A0h]
  ULONG SizeOfBitMap[2]; // [rsp+258h] [rbp-198h]
  unsigned __int64 v168; // [rsp+260h] [rbp-190h]
  __int64 v169; // [rsp+268h] [rbp-188h]
  PULONG BitMapBuffer; // [rsp+270h] [rbp-180h]
  __int64 v171; // [rsp+278h] [rbp-178h] BYREF
  __int64 v172; // [rsp+280h] [rbp-170h]
  __int64 v173; // [rsp+288h] [rbp-168h]
  LONGLONG v174; // [rsp+290h] [rbp-160h]
  struct _UNICODE_STRING UnicodeString; // [rsp+298h] [rbp-158h] BYREF
  __int64 v176; // [rsp+2A8h] [rbp-148h]
  PVOID P; // [rsp+2B0h] [rbp-140h]
  ULONG v178; // [rsp+2B8h] [rbp-138h]
  int v179; // [rsp+2BCh] [rbp-134h]
  __int64 v180; // [rsp+2C0h] [rbp-130h]
  __int64 v181; // [rsp+2C8h] [rbp-128h]
  __int64 v182; // [rsp+2D0h] [rbp-120h] BYREF
  LONGLONG v183; // [rsp+2D8h] [rbp-118h]
  __int64 v184; // [rsp+2E0h] [rbp-110h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+2E8h] [rbp-108h] BYREF
  _QWORD v186[11]; // [rsp+2F8h] [rbp-F8h] BYREF
  __int128 v187; // [rsp+358h] [rbp-98h] BYREF
  __int64 v188; // [rsp+368h] [rbp-88h]
  _OWORD v189[2]; // [rsp+370h] [rbp-80h] BYREF
  __int128 v190; // [rsp+390h] [rbp-60h] BYREF
  __int128 v191; // [rsp+3A0h] [rbp-50h]

  v181 = a2;
  v159 = a1;
  IsClearOrSet = 0;
  v149 = 0;
  *(_QWORD *)v160 = 0;
  v161 = 0;
  v172 = 0;
  v176 = 0;
  IoStatus = 0;
  memset(v186, 0, sizeof(v186));
  memset(v189, 0, 28);
  *(_QWORD *)v157 = 0;
  UnicodeString = 0;
  v146 = 0;
  v187 = 0;
  v188 = 0;
  v190 = 0;
  v191 = 0;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  *(_QWORD *)&v190 = UnbiasedInterruptTime;
  v154 = 1;
  if ( a2 )
  {
    if ( (int)IoGetActivityIdIrp(a2, (char *)&v187 + 8) < 0 )
    {
LABEL_3:
      *(_QWORD *)&v187 = 0;
      goto LABEL_4;
    }
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v7);
    if ( !ActivityIdThread )
      goto LABEL_3;
    *((_QWORD *)&v187 + 1) = *ActivityIdThread;
    v188 = ActivityIdThread[1];
  }
  *(_QWORD *)&v187 = (char *)&v187 + 8;
LABEL_4:
  v9 = *(_QWORD *)(a2 + 184);
  v173 = v9;
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
    v156 = *v13;
    v162 = v156;
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
    v156 = 0;
    v162 = 0;
    v14 = **(_QWORD **)(a2 + 24);
  }
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = v14;
  v158 = (unsigned __int64)v13;
  v155 = (__int16 *)v13;
  if ( (unsigned int)NtfsDecodeFileObject(
                       a1,
                       *(_QWORD *)(v9 + 48),
                       (unsigned int)v160,
                       (unsigned int)&v182,
                       (__int64)&v171,
                       (__int64)&v161,
                       1) != 4 )
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
  if ( !v161 || !_bittest16((const signed __int16 *)(v161 + 104), 9u) )
  {
    if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      if ( v161 )
        v137 = *(_WORD *)(v161 + 104);
      else
        LOBYTE(v137) = 0;
      v138 = *(_QWORD *)(*(_QWORD *)v160 + 248LL);
      v139 = *(_WORD *)(v138 + 6);
      if ( v139 > 0x40u || (v139 & 1) != 0 )
        v139 = 0;
      McTemplateU0ppwwd_EtwWriteTransfer(
        v139 >> 1,
        (unsigned int)fsctrl_c23405,
        (unsigned int)KeGetCurrentThread(),
        v160[0],
        *(_WORD *)(*(_QWORD *)v160 + 7872LL) >> 1,
        *(_QWORD *)(*(_QWORD *)v160 + 7880LL),
        v139 >> 1,
        v138 + 32,
        v137);
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
  v16 = *(_QWORD *)v160;
  if ( (*(_DWORD *)(*(_QWORD *)v160 + 4LL) & 0x2000000) == 0 )
  {
    KeWaitForSingleObject((PVOID)(*(_QWORD *)v160 + 6632LL), Executive, 0, 0, 0);
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
      v172 = v21;
      v176 = v21;
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
    v180 = 0;
    v169 = 0;
    v174 = 0;
    P = 0;
    v150 = 0;
    v148 = 0;
    v152 = 0;
    v145 = 0;
    v151 = 0;
    BitMapBuffer = 0;
    *(_QWORD *)SizeOfBitMap = 0;
    *(_DWORD *)(a1 + 12) |= 1u;
    memset(v186, 0, sizeof(v186));
    LOBYTE(v22) = 1;
    if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
      NtfsAcquireExclusiveVcb(a1, v16, v22);
    else
      NtfsAcquireSharedVcb(a1, v16, v22);
    v147 = 1;
    v23 = *(_QWORD *)(v16 + 88);
    v165 = v23;
    v171 = v23;
    v168 = *(_QWORD *)(v16 + 424);
    v161 = v168;
    v182 = *(_QWORD *)(v16 + 432);
    *((_QWORD *)&v190 + 1) = KeQueryUnbiasedInterruptTime();
    v153 = 2;
    v154 = 2;
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
      if ( *(_DWORD *)v155 == 1 )
      {
        v33 = v173;
        if ( *(_QWORD *)(v16 + 5368) == 0x7FFFFFFFFFFFFFFFLL || *(_QWORD *)(v173 + 48) == *(_QWORD *)(v16 + 1480) )
        {
          if ( *(_QWORD *)(v16 + 296) > v20 )
          {
            *(_QWORD *)(v16 + 5368) = v20;
            *(_QWORD *)(v16 + 5376) = v14;
            *(_QWORD *)(v16 + 1480) = *(_QWORD *)(v33 + 48);
            NtfsRemoveCachedRun(a1, v16, *(_QWORD *)(v16 + 5368), *(_QWORD *)(v16 + 296) - *(_QWORD *)(v16 + 5368));
            v34 = v155;
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
      if ( *(_DWORD *)v155 != 2 )
      {
        if ( *(_DWORD *)v155 != 3 )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v24 = 1203411;
            goto LABEL_258;
          }
LABEL_259:
          v149 = IsClearOrSet;
          goto LABEL_260;
        }
        if ( *(_QWORD *)(v173 + 48) != *(_QWORD *)(v16 + 1480) )
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
        v34 = v155;
LABEL_261:
        v98 = a3;
LABEL_262:
        v99 = KeQueryUnbiasedInterruptTime();
        *((_QWORD *)&v191 + 1) = v99;
        NtfsTelemetryFillVcbVolumeState(v16);
        v100 = NtfsTelemetryGuard(2048);
        v102 = UnbiasedInterruptTime;
        if ( v100 )
          NtfsTelemetryVolumeSizeChange(
            (unsigned int)&v187,
            v16,
            IsClearOrSet,
            (unsigned __int16)v156,
            v99 - UnbiasedInterruptTime,
            v142,
            (__int64)&v190);
        LOBYTE(v101) = 1;
        NtfsRepairGetVolumeId(a1, v16, v101, (unsigned int)&UnicodeString, (__int64)&v146);
        if ( (IsClearOrSet & 0x80000000) != 0 )
        {
          if ( (Microsoft_Windows_NtfsEnableBits & 0x10000) != 0 )
          {
            if ( *((_QWORD *)&v191 + 1) && (_QWORD)v191 )
              v161 = (unsigned __int64)(1000 * (*((_QWORD *)&v191 + 1) - v191)) / NtfsPerformanceFrequency.QuadPart;
            else
              v161 = 0;
            if ( (_QWORD)v191 && *((_QWORD *)&v190 + 1) )
              v158 = (unsigned __int64)(1000 * (v191 - *((_QWORD *)&v190 + 1))) / NtfsPerformanceFrequency.QuadPart;
            else
              v158 = 0;
            if ( *((_QWORD *)&v190 + 1) && (_QWORD)v190 )
              *(_QWORD *)&BitMapHeader.SizeOfBitMap = (unsigned __int64)(1000 * (*((_QWORD *)&v190 + 1) - v190))
                                                    / NtfsPerformanceFrequency.QuadPart;
            else
              *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
            if ( v99 && v102 )
              v119 = 1000 * (v99 - v102) / NtfsPerformanceFrequency.QuadPart;
            else
              LOBYTE(v119) = 0;
            if ( v98 )
              v120 = *v34;
            else
              LOBYTE(v120) = 0;
            v121 = &word_140064400;
            v122 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6736) )
              v122 = *(const WCHAR **)(v16 + 6736);
            v171 = (__int64)v122;
            v123 = (*(_DWORD *)(v16 + 28) >> 2) & 1;
            v124 = *(_DWORD *)(v16 + 6660);
            if ( (unsigned int)(v124 - 1) > 0x13 )
              v124 = 0;
            v163[0] = v124;
            v125 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6720) )
              v125 = *(const WCHAR **)(v16 + 6720);
            v159 = (__int64)v125;
            v126 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6704) )
              v126 = *(const WCHAR **)(v16 + 6704);
            *(_QWORD *)v157 = v126;
            v127 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6688) )
              v127 = *(const WCHAR **)(v16 + 6688);
            *(_QWORD *)v160 = v127;
            v128 = &word_140064400;
            if ( *(_QWORD *)(v16 + 6672) )
              v128 = *(const WCHAR **)(v16 + 6672);
            UnbiasedInterruptTime = (ULONGLONG)v128;
            if ( *(_QWORD *)(v16 + 7864) )
              v121 = *(const WCHAR **)(v16 + 7864);
            if ( (*(_DWORD *)(v16 + 4) & 0xC00) != 0x800
              && (v129 = *(_QWORD *)(v16 + 248)) != 0
              && (v130 = *(_QWORD *)(v129 + 16)) != 0 )
            {
              v131 = (*(_DWORD *)(v130 + 48) >> 8) & 1;
            }
            else
            {
              LOBYTE(v131) = 0;
            }
            v132 = (__int64)(v168 * *(unsigned int *)(v16 + 364));
            McTemplateK0jmztzzzzzqjqtzxxhhxxxxhqd_EtwWriteTransfer(
              v16 + 7808,
              v16 + 8528,
              v172 / 0x100000,
              v16 + 7824,
              v16 + 8528,
              (__int64)UnicodeString.Buffer,
              v131,
              (__int64)v121,
              UnbiasedInterruptTime,
              *(__int64 *)v160,
              *(__int64 *)v157,
              v159,
              v163[0],
              v16 + 7808,
              *(_DWORD *)(v16 + 6792),
              v123,
              v171,
              ((*((_QWORD *)&v132 + 1) & 0xFFFFFLL) + (__int64)v132) >> 20,
              v172 / 0x100000,
              a3 != 0,
              v120,
              v119,
              BitMapHeader.SizeOfBitMap,
              v158,
              v161,
              v153,
              IsClearOrSet,
              IsClearOrSet);
          }
        }
        else if ( (Microsoft_Windows_NtfsEnableBits & 0x800) != 0 )
        {
          if ( *((_QWORD *)&v191 + 1) && (_QWORD)v191 )
            v161 = (unsigned __int64)(1000 * (*((_QWORD *)&v191 + 1) - v191)) / NtfsPerformanceFrequency.QuadPart;
          else
            v161 = 0;
          if ( (_QWORD)v191 && *((_QWORD *)&v190 + 1) )
            v158 = (unsigned __int64)(1000 * (v191 - *((_QWORD *)&v190 + 1))) / NtfsPerformanceFrequency.QuadPart;
          else
            v158 = 0;
          if ( *((_QWORD *)&v190 + 1) && (_QWORD)v190 )
            *(_QWORD *)&BitMapHeader.SizeOfBitMap = (unsigned __int64)(1000 * (*((_QWORD *)&v190 + 1) - v190))
                                                  / NtfsPerformanceFrequency.QuadPart;
          else
            *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
          if ( v99 && v102 )
            v105 = 1000 * (v99 - v102) / NtfsPerformanceFrequency.QuadPart;
          else
            LOBYTE(v105) = 0;
          if ( v98 )
            v106 = *v34;
          else
            LOBYTE(v106) = 0;
          v107 = &word_140064400;
          v108 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6736) )
            v108 = *(const WCHAR **)(v16 + 6736);
          v171 = (__int64)v108;
          v109 = (*(_DWORD *)(v16 + 28) >> 2) & 1;
          v110 = *(_DWORD *)(v16 + 6660);
          if ( (unsigned int)(v110 - 1) > 0x13 )
            v110 = 0;
          v163[0] = v110;
          v111 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6720) )
            v111 = *(const WCHAR **)(v16 + 6720);
          v159 = (__int64)v111;
          v112 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6704) )
            v112 = *(const WCHAR **)(v16 + 6704);
          *(_QWORD *)v157 = v112;
          v113 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6688) )
            v113 = *(const WCHAR **)(v16 + 6688);
          *(_QWORD *)v160 = v113;
          v114 = &word_140064400;
          if ( *(_QWORD *)(v16 + 6672) )
            v114 = *(const WCHAR **)(v16 + 6672);
          UnbiasedInterruptTime = (ULONGLONG)v114;
          if ( *(_QWORD *)(v16 + 7864) )
            v107 = *(const WCHAR **)(v16 + 7864);
          if ( (*(_DWORD *)(v16 + 4) & 0xC00) != 0x800
            && (v115 = *(_QWORD *)(v16 + 248)) != 0
            && (v116 = *(_QWORD *)(v115 + 16)) != 0 )
          {
            v117 = (*(_DWORD *)(v116 + 48) >> 8) & 1;
          }
          else
          {
            LOBYTE(v117) = 0;
          }
          v118 = (__int64)(v168 * *(unsigned int *)(v16 + 364));
          McTemplateK0jmztzzzzzqjqtzxxhhxxxx_EtwWriteTransfer(
            v16 + 7808,
            v16 + 8528,
            v172 / 0x100000,
            v16 + 7824,
            v16 + 8528,
            (__int64)UnicodeString.Buffer,
            v117,
            (__int64)v107,
            UnbiasedInterruptTime,
            *(__int64 *)v160,
            *(__int64 *)v157,
            v159,
            v163[0],
            v16 + 7808,
            *(_DWORD *)(v16 + 6792),
            v109,
            v171,
            ((*((_QWORD *)&v118 + 1) & 0xFFFFFLL) + (__int64)v118) >> 20,
            v172 / 0x100000,
            a3 != 0,
            v106,
            v105,
            BitMapHeader.SizeOfBitMap,
            v158,
            v161);
        }
        if ( v146 )
          RtlFreeUnicodeString(&UnicodeString);
        if ( BitMapBuffer )
          ExFreePoolWithTag(BitMapBuffer, 0);
        v133 = P;
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v152 )
          NtfsReleasePagingResourcePriv(v133, *(_QWORD *)(v16 + 72), v103, v104);
        if ( v145 )
          NtfsReleaseFcbEx(a1, *(_QWORD *)(v165 + 184), 0);
        if ( v151 )
        {
          NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 48) + 184LL), 0);
          NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 192) + 184LL), 0);
        }
        NtfsReleaseVcb(a1, v16);
        NtfsCleanupAttributeContext(v134, v186);
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
        LOBYTE(v135) = v181 != 0;
        NtfsExtendedCompleteRequestInternal(a1, v181, IsClearOrSet, v135, (IsClearOrSet & 0x80000000) == 0);
        return IsClearOrSet;
      }
      if ( *(_QWORD *)(v173 + 48) != *(_QWORD *)(v16 + 1480) )
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
      v172 = (*(_QWORD *)&BitMapHeader.SizeOfBitMap - 1LL) * *(unsigned int *)(v16 + 364);
      v176 = v172;
      IsClearOrSet = NtfsRunIsClearOrSet(a1, v16, v20, (unsigned int)*(_QWORD *)(v16 + 296) - (unsigned int)v20, 0, 0);
      v149 = IsClearOrSet;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0);
      if ( IsClearOrSet == -1073741791 || IsClearOrSet == -1073741267 )
      {
        if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v16 + 2160)) )
        {
          NtfsReleaseVcb(a1, v16);
          LOBYTE(v26) = 1;
          NtfsAcquireExclusiveVcb(a1, v16, v26);
          v147 = 1;
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
        v148 = 1;
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
        v148 = 0;
        NtfsMarkUnusedContextPreTrimProcessing(a1, v29, v30, v31);
        LOBYTE(v32) = 1;
        NtfsWaitForDeallocatedClustersToDrain(*(_QWORD *)(a1 + 104), v32);
        NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0, 9);
        IsClearOrSet = NtfsRunIsClearOrSet(a1, v16, v20, (unsigned int)*(_QWORD *)(v16 + 296) - (unsigned int)v20, 0, 0);
        v149 = IsClearOrSet;
        NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v16 + 72) + 184LL), 0);
        v23 = v165;
      }
      v147 = 1;
      if ( (IsClearOrSet & 0x80000000) != 0 )
      {
        v147 = 1;
        goto LABEL_260;
      }
    }
    NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 192) + 184LL), 0, 1);
    if ( a3 )
    {
      NtfsAcquireExclusiveScbEx(a1, v23, 0);
      v145 = 1;
      if ( (unsigned __int64)(v20 << *(_BYTE *)(v16 + 488)) >= *(_QWORD *)(v23 + 24) )
      {
        NtfsReleaseFcbEx(a1, *(_QWORD *)(v23 + 184), 0);
        v145 = 0;
      }
      else
      {
        NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 0);
      }
LABEL_117:
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v16 + 48) + 184LL), 0, 1);
      v151 = 1;
      *(_QWORD *)&v191 = KeQueryUnbiasedInterruptTime();
      v153 = 3;
      v154 = 3;
      v41 = *(_QWORD *)(v16 + 72);
      v180 = v41;
      LOBYTE(v42) = 1;
      NtfsAcquirePagingResourceExclusive(a1, v41, v42);
      v152 = 1;
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(v41 + 184), 0, 9);
      if ( a3 )
      {
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v16 + 720));
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v16 + 6376));
        v43 = *(_QWORD *)(v16 + 296) - v20;
        *(_QWORD *)v163 = *(_QWORD *)(v16 + 328) + (*(__int64 *)(v16 + 328) >> 8) + *(_QWORD *)(v16 + 6368);
        if ( v43 > *(_QWORD *)(v16 + 304) )
        {
          NtfsAllocateDiskFullContext(a1, v43 << *(_BYTE *)(v16 + 488), 0x27700125DDDLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225599LL, 1203678);
          IsClearOrSet = -1073741697;
          v149 = -1073741697;
        }
        if ( *(__int64 *)v163 >= *(_QWORD *)(v16 + 304) - v43 )
        {
          NtfsAllocateDiskFullContext(a1, v43 << *(_BYTE *)(v16 + 488), 0x27800125DE5LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225599LL, 1203686);
          IsClearOrSet = -1073741697;
          v149 = -1073741697;
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
      NtfsGetDiskGeometry(a1, *(_QWORD *)(v16 + 224), v189, v157);
      v44 = *(unsigned int *)(v16 + 364);
      if ( (_DWORD)v44 != LODWORD(v189[0]) || v172 + v44 > *(__int64 *)v157 )
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
        v45 = (((v20 + 7) >> 3) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        v46 = *(_BYTE *)(v16 + 488);
        v47 = (v45 + *(unsigned int *)(v16 + 480)) >> v46 << v46;
        v48 = (_QWORD *)(v41 + 24);
        v49 = *(_QWORD *)(v41 + 24);
        *(_QWORD *)v157 = v49;
        if ( v47 <= v49 )
        {
          *(_QWORD *)(v16 + 296) = 8 * v45;
          if ( v47 >= v49 )
            goto LABEL_151;
          NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 0);
LABEL_150:
          v48 = (_QWORD *)(v41 + 24);
LABEL_151:
          if ( (*(_DWORD *)(v41 + 200) & 0x20000) != 0 )
          {
            v55 = *(_QWORD *)(v41 + 464);
            if ( v55 >= v45 )
            {
              if ( *(_QWORD *)(v41 + 40) > v45 )
              {
                if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) )
                {
                  v56 = (v45 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                  if ( v56 < v55 )
                    *(_QWORD *)(v41 + 464) = v56;
                }
                else
                {
                  *(_QWORD *)(v41 + 464) = v45;
                }
              }
            }
            else
            {
              *(_QWORD *)(v41 + 464) = v45;
            }
          }
          *(_QWORD *)(v41 + 40) = v45;
          if ( (*(_DWORD *)(v41 + 200) & 0x20000) == 0 || *(_QWORD *)(v41 + 32) >= v45 )
            goto LABEL_173;
          v57 = *(_QWORD *)(v41 + 464);
          if ( v45 < v57 )
            v57 = (((v20 + 7) >> 3) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          if ( v57 <= v45 )
          {
LABEL_173:
            *(_QWORD *)(v41 + 32) = v45;
            *(_QWORD *)(v41 + 472) = *v48;
            LOBYTE(v47) = 1;
            NtfsWriteFileSizes(a1, v41, 0, v47, 1, 1);
            NtfsSetCcFileSizes(*(_QWORD *)(v41 + 280), v41, v41 + 24);
            if ( !a3 )
            {
              v60 = 8LL * *(_QWORD *)v157;
              if ( *(_QWORD *)(v16 + 296) < 8LL * *(_QWORD *)v157 )
                v60 = *(_QWORD *)(v16 + 296);
              v61 = *(_QWORD *)(v16 + 336);
              if ( v60 != v61 )
                NtfsModifyBitsInBitmap(a1, v16, v61, 22, 21);
              if ( v169 )
                NtfsModifyBitsInBitmap(a1, v16, v174, 21, 22);
            }
            if ( 8 * v45 != v20 )
              NtfsModifyBitsInBitmap(a1, v16, v20, 21, 0);
            P = ExAllocatePoolWithTag(
                  (POOL_TYPE)528,
                  (unsigned int)(*(_DWORD *)(v16 + 364) + *(_DWORD *)(*(_QWORD *)(v16 + 224) + 152LL)),
                  0x6646744Eu);
            v62 = *(int *)(*(_QWORD *)(v16 + 224) + 152LL);
            v63 = ~(_DWORD)v62 & ((unsigned __int64)P + v62);
            NtfsReadBootSector(a1, a2, v16, v63, v153);
            if ( (unsigned __int8)NtfsIsBootSectorNtfs(v63, v16) )
            {
              if ( *(_QWORD *)(v16 + 8144) )
              {
                v64 = v20 << *(_BYTE *)(v16 + 488);
                v65 = *(_QWORD *)(v16 + 8176);
                v66 = v64 < v65 ? 1LL : (v65 != 0) + 1 + (unsigned int)((v64 - v65) / *(_QWORD *)(v16 + 8152));
                v179 = v66;
                *(_QWORD *)SizeOfBitMap = v66;
                if ( (_DWORD)v66 != *(_DWORD *)(v16 + 8136) )
                {
                  v67 = (v153 + ((unsigned int)(v66 + 7) >> 3)) & 0xFFFFFFFC;
                  BitMapBuffer = (PULONG)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v67, 0x6646744Eu);
                  memset(BitMapBuffer, 0, v67);
                }
              }
              *(_QWORD *)(v16 + 296) = v20;
              v68 = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
              *(_QWORD *)(v16 + 432) = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
              *(_QWORD *)(v16 + 424) = --v68;
              *(_QWORD *)(v63 + 40) = v68;
              NtfsWriteBootSector(a1, a2, v16, v63, v153);
              NtfsCheckpointCurrentTransaction(a1);
              if ( !*(_QWORD *)(v16 + 8144) )
              {
LABEL_225:
                NtfsUpdateTieringInfo(a1);
                NtfsScanEntireBitmap(a1, v16, 10, 5);
                LfsFlushToLsn(*(_QWORD *)(v16 + 232), NtfsLargeMax);
                *(_QWORD *)(v16 + 336) = *(_QWORD *)(v16 + 296);
                v83 = *(_QWORD *)(v16 + 296) << *(_BYTE *)(v16 + 488);
                v84 = *(_QWORD *)(v16 + 192);
                if ( (*(_DWORD *)(v84 + 200) & 0x20000) != 0
                  && *(_QWORD *)(v84 + 24) > v83
                  && *(_QWORD *)(v84 + 464) > v83 )
                {
                  *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = v83;
                }
                *(_QWORD *)(*(_QWORD *)(v16 + 192) + 24LL) = v83;
                v85 = *(_QWORD *)(v16 + 192);
                if ( (*(_DWORD *)(v85 + 200) & 0x20000) == 0 )
                  goto LABEL_244;
                v86 = *(_QWORD *)(v85 + 24);
                if ( *(_QWORD *)(v85 + 32) >= v86 )
                  goto LABEL_244;
                if ( v86 >= *(_QWORD *)(v85 + 464) )
                  v86 = *(_QWORD *)(v85 + 464);
                if ( v86 <= *(_QWORD *)(v85 + 40) )
                {
LABEL_244:
                  *(_QWORD *)(*(_QWORD *)(v16 + 192) + 32LL) = *(_QWORD *)(*(_QWORD *)(v16 + 192) + 24LL);
                  v91 = *(_QWORD *)(v16 + 192);
                  v92 = *(_DWORD *)(v91 + 200);
                  if ( (v92 & 0x20000) != 0 )
                  {
                    v93 = *(_QWORD *)(v91 + 32);
                    v94 = *(_QWORD *)(v91 + 464);
                    if ( v94 < v93 )
                      goto LABEL_251;
                    if ( *(_QWORD *)(v91 + 40) <= v93 )
                      goto LABEL_253;
                    if ( !*(_QWORD *)(*(_QWORD *)(v91 + 288) + 16LL) || v93 == 0x7FFFFFFFFFFFFFFFLL )
                    {
LABEL_251:
                      v95 = *(_QWORD *)(v16 + 192);
                      v96 = *(_QWORD *)(v95 + 32);
                      goto LABEL_252;
                    }
                    if ( (__int64)((v93 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v94 )
                    {
                      v95 = *(_QWORD *)(v16 + 192);
                      v96 = (*(_QWORD *)(v95 + 32) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_252:
                      *(_QWORD *)(v95 + 464) = v96;
                    }
                  }
LABEL_253:
                  *(_QWORD *)(*(_QWORD *)(v16 + 192) + 40LL) = *(_QWORD *)(*(_QWORD *)(v16 + 192) + 32LL);
                  SetFlagInterlocked(v16 + 4, 128);
                  v98 = a3;
                  v34 = v155;
                  if ( !a3
                    || (*(_QWORD *)(v16 + 5368) = v97,
                        *(_QWORD *)(v16 + 5376) = 0,
                        *(_QWORD *)(v16 + 1480) = 0,
                        *(_DWORD *)v34 == 2) )
                  {
                    FsRtlNotifyVolumeEvent(*(PFILE_OBJECT *)(v173 + 48), 0xDu);
                  }
                  goto LABEL_262;
                }
                v87 = *(_QWORD *)(v16 + 192);
                v88 = *(_DWORD *)(v87 + 200);
                if ( (v88 & 0x20000) != 0 )
                {
                  v89 = *(_QWORD *)(v87 + 464);
                  if ( v89 < v86 )
                  {
LABEL_242:
                    *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = v86;
                    goto LABEL_243;
                  }
                  if ( *(_QWORD *)(v87 + 40) > v86 )
                  {
                    if ( *(_QWORD *)(*(_QWORD *)(v87 + 288) + 16LL) )
                    {
                      if ( v86 == 0x7FFFFFFFFFFFFFFFLL )
                      {
                        *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = 0x7FFFFFFFFFFFFFFFLL;
                      }
                      else
                      {
                        v90 = (v86 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                        if ( v90 < v89 )
                          *(_QWORD *)(*(_QWORD *)(v16 + 192) + 464LL) = v90;
                      }
                      goto LABEL_243;
                    }
                    goto LABEL_242;
                  }
                }
LABEL_243:
                *(_QWORD *)(*(_QWORD *)(v16 + 192) + 40LL) = v86;
                goto LABEL_244;
              }
              v69 = (struct _RTL_BITMAP *)(v16 + 8136);
              v70 = *(_DWORD *)(v16 + 8136);
              v71 = 0;
              v178 = 0;
              if ( _bittest64(*(const signed __int64 **)(v16 + 8144), v70 - 1) && v70 > 1 )
              {
                RtlClearBit((PRTL_BITMAP)(v16 + 8136), v70 - 1);
                *(_QWORD *)(v16 + 288) -= (__int64)(*(unsigned int *)(v16 + 480) + *(_QWORD *)(v16 + 0x2000)) >> *(_BYTE *)(v16 + 488);
                v71 = v69->SizeOfBitMap - 1;
                v178 = v71;
              }
              v72 = BitMapBuffer;
              v73 = SizeOfBitMap[0];
              if ( BitMapBuffer && v70 > SizeOfBitMap[0] )
              {
                *(_QWORD *)(v16 + 288) -= *(_DWORD *)(v16 + 8160)
                                        * (unsigned int)RtlNumberOfSetBitsInRange(
                                                          v16 + 8136,
                                                          SizeOfBitMap[0],
                                                          v70 - SizeOfBitMap[0]);
                v73 = SizeOfBitMap[0];
                v72 = BitMapBuffer;
              }
              if ( v73 <= 1 )
              {
                *(_QWORD *)(v16 + 0x2000) = 0;
                *(_QWORD *)(v16 + 288) = *(_QWORD *)(v16 + 296);
                *(_QWORD *)(v16 + 8184) = *(_QWORD *)(v16 + 296) << *(_BYTE *)(v16 + 488);
              }
              else
              {
                v74 = *(_QWORD *)(v16 + 8184);
                if ( v74 != *(_QWORD *)(v16 + 8176) )
                {
                  *(_QWORD *)(v16 + 288) -= (v74 + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
                  *(_QWORD *)(v16 + 288) += (__int64)(*(_QWORD *)(v16 + 8176) + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
                  v74 = *(_QWORD *)(v16 + 8176);
                  *(_QWORD *)(v16 + 8184) = v74;
                }
                *(_QWORD *)(v16 + 0x2000) = (unsigned __int64)((v20 << *(_BYTE *)(v16 + 488)) - v74)
                                          % *(_QWORD *)(v16 + 8152);
              }
              if ( v72 )
              {
                LODWORD(BitMapHeader.Buffer) = 0;
                *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
                RtlInitializeBitMap(&BitMapHeader, v72, v73);
                v75 = SizeOfBitMap[0];
                if ( v70 < SizeOfBitMap[0] )
                  v75 = v70;
                RtlExtractBitMap(v16 + 8136, &BitMapHeader, 0, v75);
                ExFreePoolWithTag(*(PVOID *)(v16 + 8144), 0);
                *v69 = BitMapHeader;
                BitMapBuffer = 0;
                v73 = SizeOfBitMap[0];
              }
              if ( v71 )
              {
                if ( v71 < v73 - 1 )
                {
                  RtlSetBit((PRTL_BITMAP)(v16 + 8136), v71);
                  v76 = *(unsigned int *)(v16 + 8160);
LABEL_210:
                  *(_QWORD *)(v16 + 288) += v76;
LABEL_214:
                  if ( v169 )
                  {
                    v77 = v174 << *(_BYTE *)(v16 + 488);
                    v78 = *(_QWORD *)(v16 + 8184);
                    if ( v77 < v78 )
                      v79 = 0;
                    else
                      v79 = (v78 != 0) + (unsigned int)((v77 - v78) / *(_QWORD *)(v16 + 8152));
                    v80 = (v174 + v169 - 1) << *(_BYTE *)(v16 + 488);
                    if ( v80 < v78 )
                      v81 = 0;
                    else
                      v81 = (v78 != 0) + (unsigned int)((v80 - v78) / *(_QWORD *)(v16 + 8152));
                    *(_QWORD *)(v16 + 288) += *(_DWORD *)(v16 + 8160)
                                            * (unsigned int)RtlNumberOfClearBitsInRange(v16 + 8136, v79, v81 - v79 + 1);
                    if ( v81 == SizeOfBitMap[0] - 1 && !_bittest64(*(const signed __int64 **)(v16 + 8144), v81) )
                    {
                      v82 = *(_QWORD *)(v16 + 288) - *(unsigned int *)(v16 + 8160);
                      *(_QWORD *)(v16 + 288) = v82;
                      *(_QWORD *)(v16 + 288) = v82
                                             + *(_QWORD *)(v16 + 0x2000)
                                             / (unsigned __int64)*(unsigned int *)(v16 + 356);
                    }
                    RtlSetBits((PRTL_BITMAP)(v16 + 8136), v79, v81 - v79 + 1);
                  }
                  goto LABEL_225;
                }
                if ( v71 == v73 - 1 )
                {
                  RtlSetBit((PRTL_BITMAP)(v16 + 8136), v71);
                  v76 = (__int64)(*(_QWORD *)(v16 + 0x2000) + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
                  goto LABEL_210;
                }
              }
              if ( _bittest64(*(const signed __int64 **)(v16 + 8144), v73 - 1) && v73 > 1 )
              {
                *(_QWORD *)(v16 + 288) -= *(unsigned int *)(v16 + 8160);
                *(_QWORD *)(v16 + 288) += (__int64)(*(_QWORD *)(v16 + 0x2000) + *(unsigned int *)(v16 + 480)) >> *(_BYTE *)(v16 + 488);
              }
              goto LABEL_214;
            }
LABEL_419:
            v181 = 0xDD00125F5BLL;
            NtfsAttachCorruptionSimple(a1, 1, 2050, 1204059, 0, v142);
            NtfsAttachRepairInfoPriv(a1, 0, 0, 0xDD00125F5BLL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3221225522LL, 1204059);
            NtfsRaiseStatusInternal(a1, -1073741774, 0, 0, 1204059);
            __debugbreak();
            JUMPOUT(0x140280CC3LL);
          }
          v58 = *(_DWORD *)(v41 + 200);
          if ( (v58 & 0x20000) != 0 )
          {
            v47 = *(_QWORD *)(v41 + 464);
            if ( v47 < v57 )
            {
LABEL_171:
              *(_QWORD *)(v41 + 464) = v57;
              goto LABEL_172;
            }
            if ( *(_QWORD *)(v41 + 40) > v57 )
            {
              if ( *(_QWORD *)(*(_QWORD *)(v41 + 288) + 16LL) && v57 != 0x7FFFFFFFFFFFFFFFLL )
              {
                v59 = (v57 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                if ( v59 < v47 )
                  *(_QWORD *)(v41 + 464) = v59;
                goto LABEL_172;
              }
              goto LABEL_171;
            }
          }
LABEL_172:
          *(_QWORD *)(v41 + 40) = v57;
          goto LABEL_173;
        }
        v163[0] = v47 - v49;
        v169 = (v47 - v49) >> v46;
        v184 = v169;
        v50 = *(_QWORD *)(v16 + 336);
        v51 = v50 + 1;
        v183 = v50 + 1;
        if ( v50 + 1 + v169 > v20 )
          v51 = v50;
        v174 = v51;
        v183 = v51;
        NtfsPreloadAllocationInternal(a1, v49 >> v46, 0);
        if ( (*(_DWORD *)(a1 + 12) & 0x20000) == 0 )
        {
          NtfsAddAllocation(a1, v169, 0, 0);
          *(_QWORD *)(v16 + 296) = 8 * v45;
          v169 = 0;
          v184 = 0;
LABEL_147:
          NtfsSetCcFileSizes(*(_QWORD *)(v41 + 280), v41, v41 + 24);
          goto LABEL_150;
        }
        if ( !*(_QWORD *)(v16 + 8144)
          || (IsClearOrSet = NtfsSetTPMap(a1, v174, v169, v153), v149 = IsClearOrSet, (IsClearOrSet & 0x80000000) == 0) )
        {
          if ( NtfsAddNtfsMcbEntry(v41 + 400, *(__int64 *)v157 >> *(_BYTE *)(v16 + 488), v174, v169, 0, 1u) )
          {
            v150 = 1;
            NtfsWriteBytes(a1, v16, v41, v157[0], 0, v163[0], ((unsigned int)dword_1400956B8 >> 19) & 4);
            *(_QWORD *)(v16 + 296) = 8 * v45;
            LOBYTE(v144) = 0;
            v52 = NtfsLookupInFileRecord(
                    a1,
                    *(_QWORD *)(v41 + 184),
                    *(_QWORD *)(v41 + 184) + 8LL,
                    *(unsigned int *)(v41 + 256),
                    v41 + 264,
                    0,
                    v144,
                    0,
                    0,
                    v186);
            v54 = 0;
            if ( v52 || (*(_DWORD *)(v41 + 512) & 4) != 0 )
            {
              LOBYTE(v143) = 0;
              NtfsAddAttributeAllocation(a1, v41, v186, 0, 0, v143);
              v150 = 0;
              goto LABEL_147;
            }
LABEL_416:
            NtfsAttachCorruption_BadOrOrphanFRS(
              a1,
              v54 + 2,
              1203920,
              v53,
              *(_QWORD *)(v41 + 184) + 8LL,
              *(_QWORD *)(v41 + 184),
              v54);
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
        v140 = NtfsRaiseStatusInternal(a1, -1073741797, 0, 0, 1203751);
        if ( NtfsStatusDebugFlags
          && v140
          && v140 != 294
          && v140 - 298 > 1
          && v140 < 0xFFFFFFED
          && v140 != -1073741802
          && v140 + 2147483643 > 1
          && v140 != -1073741807
          && v140 != 259
          && v140 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(0, v140, 1203849);
        }
        v141 = v159;
        *(_DWORD *)(v159 + 4) &= ~0x100u;
        *(_DWORD *)(v141 + 24) = 0;
        *(_DWORD *)(v141 + 12) |= 0x20000u;
        NtfsRaiseStatusInternal(v141, -1073741608, 0, 0, 1203858);
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
    v36 = v165;
    NtfsAcquireExclusiveScbEx(a1, v165, 0);
    v145 = 1;
    v37 = *(_QWORD *)(v36 + 24);
    if ( v35 <= v37 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v36 + 184), 0);
      v145 = 0;
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
0x14027e3c8  mov     r11, rsp
0x14027e3cb  mov     [r11+18h], r8b
0x14027e3cf  push    rbx
0x14027e3d0  push    rsi
0x14027e3d1  push    rdi
0x14027e3d2  push    r12
0x14027e3d4  push    r13
0x14027e3d6  push    r14
0x14027e3d8  push    r15
0x14027e3da  sub     rsp, 2C0h
0x14027e3e1  mov     rax, cs:__security_cookie
0x14027e3e8  xor     rax, rsp
0x14027e3eb  mov     [rsp+2F8h+var_40], rax
0x14027e3f3  mov     r12b, r8b
0x14027e3f6  mov     r13, rdx
0x14027e3f9  mov     [rsp+2F8h+var_128], rdx
0x14027e401  mov     r14, rcx
0x14027e404  mov     [rsp+2F8h+var_1E0], rcx
0x14027e40c  xor     edi, edi
0x14027e40e  mov     esi, edi
0x14027e410  mov     [rsp+2F8h+var_214], edi
0x14027e417  mov     [r11-1D8h], rdi
0x14027e41e  mov     [r11-1D0h], rdi
0x14027e425  mov     eax, edi
0x14027e427  mov     [r11-170h], rax
0x14027e42e  mov     [r11-148h], rax
0x14027e435  xorps   xmm0, xmm0
0x14027e438  movups  xmmword ptr [rsp+2F8h+IoStatus], xmm0
0x14027e440  xor     edx, edx; Val
0x14027e442  lea     r8d, [rdi+58h]; Size
0x14027e446  lea     rcx, [r11-0F8h]; void *
0x14027e44d  call    memset
0x14027e452  xorps   xmm0, xmm0
0x14027e455  xor     eax, eax
0x14027e457  movups  [rsp+2F8h+var_80], xmm0
0x14027e45f  movups  [rsp+2F8h+var_80+0Ch], xmm0
0x14027e467  mov     qword ptr [rsp+2F8h+var_1F0], rdi
0x14027e46f  movups  xmmword ptr [rsp+2F8h+UnicodeString.Length], xmm0
0x14027e477  mov     [rsp+2F8h+var_217], dil
0x14027e47f  xorps   xmm1, xmm1
0x14027e482  movups  [rsp+2F8h+var_98], xmm1
0x14027e48a  mov     [rsp+2F8h+var_88], rax
0x14027e492  mov     [rsp+2F8h+var_204], di
0x14027e49a  movups  [rsp+2F8h+var_60], xmm0
0x14027e4a2  movups  [rsp+2F8h+var_50], xmm0
0x14027e4aa  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14027e4b1  nop     dword ptr [rax+rax+00h]
0x14027e4b6  mov     [rsp+2F8h+var_1A0], rax
0x14027e4be  mov     qword ptr [rsp+2F8h+var_60], rax
0x14027e4c6  lea     eax, [rdi+1]
0x14027e4c9  mov     [rsp+2F8h+var_204], ax
0x14027e4d1  test    r13, r13
0x14027e4d4  jz      loc_14027E576
0x14027e4da  lea     rdx, [rsp+2F8h+var_98+8]
0x14027e4e2  mov     rcx, r13
0x14027e4e5  call    cs:__imp_IoGetActivityIdIrp
0x14027e4ec  nop     dword ptr [rax+rax+00h]
0x14027e4f1  test    eax, eax
0x14027e4f3  jns     loc_14027E5A5
0x14027e4f9  mov     qword ptr [rsp+2F8h+var_98], rdi
0x14027e501  mov     rcx, [r13+0B8h]
0x14027e508  mov     [rsp+2F8h+var_168], rcx
0x14027e510  mov     eax, [rcx+10h]
0x14027e513  test    r12b, r12b
0x14027e516  jz      loc_14027E5D8
0x14027e51c  cmp     eax, 18h
0x14027e51f  jnb     loc_14027E5BA
0x14027e525  mov     al, cs:NtfsStatusDebugFlags
0x14027e52b  mov     esi, 0C000000Dh
0x14027e530  test    al, al
0x14027e532  jz      short loc_14027E544
0x14027e534  mov     r8d, 125B3Fh
0x14027e53a  mov     edx, esi
0x14027e53c  mov     rcx, r14
0x14027e53f  call    NtfsStatusTraceAndDebugInternal
0x14027e544  test    r13, r13
0x14027e547  setnz   r9b
0x14027e54b  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e54f  mov     r8d, esi
0x14027e552  mov     rdx, r13
0x14027e555  mov     rcx, r14
0x14027e558  call    NtfsExtendedCompleteRequestInternal
0x14027e55d  mov     al, cs:NtfsStatusDebugFlags
0x14027e563  test    al, al
0x14027e565  jz      loc_140280944
0x14027e56b  mov     r8d, 125B40h
0x14027e571  jmp     loc_14028093B
0x14027e576  call    cs:__imp_IoGetActivityIdThread
0x14027e57d  nop     dword ptr [rax+rax+00h]
0x14027e582  mov     rcx, rax
0x14027e585  test    rax, rax
0x14027e588  jz      loc_14027E4F9
0x14027e58e  mov     rax, [rax]
0x14027e591  mov     qword ptr [rsp+2F8h+var_98+8], rax
0x14027e599  mov     rax, [rcx+8]
0x14027e59d  mov     [rsp+2F8h+var_88], rax
0x14027e5a5  lea     rax, [rsp+2F8h+var_98+8]
0x14027e5ad  mov     qword ptr [rsp+2F8h+var_98], rax
0x14027e5b5  jmp     loc_14027E501
0x14027e5ba  mov     rbx, [r13+18h]
0x14027e5be  mov     r15, [rbx+10h]
0x14027e5c2  movzx   edi, word ptr [rbx]
0x14027e5c5  mov     [rsp+2F8h+var_1F8], edi
0x14027e5cc  mov     [rsp+2F8h+var_1C8], di
0x14027e5d4  xor     edi, edi
0x14027e5d6  jmp     short loc_14027E649
0x14027e5d8  cmp     eax, 8
0x14027e5db  jnb     short loc_14027E62E
0x14027e5dd  mov     al, cs:NtfsStatusDebugFlags
0x14027e5e3  mov     esi, 0C000000Dh
0x14027e5e8  test    al, al
0x14027e5ea  jz      short loc_14027E5FC
0x14027e5ec  mov     r8d, 125B4Ch
0x14027e5f2  mov     edx, esi
0x14027e5f4  mov     rcx, r14
0x14027e5f7  call    NtfsStatusTraceAndDebugInternal
0x14027e5fc  test    r13, r13
0x14027e5ff  setnz   r9b
0x14027e603  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e607  mov     r8d, esi
0x14027e60a  mov     rdx, r13
0x14027e60d  mov     rcx, r14
0x14027e610  call    NtfsExtendedCompleteRequestInternal
0x14027e615  mov     al, cs:NtfsStatusDebugFlags
0x14027e61b  test    al, al
0x14027e61d  jz      loc_140280944
0x14027e623  mov     r8d, 125B4Dh
0x14027e629  jmp     loc_14028093B
0x14027e62e  mov     rbx, rdi
0x14027e631  mov     eax, edi
0x14027e633  mov     [rsp+2F8h+var_1F8], eax
0x14027e63a  mov     [rsp+2F8h+var_1C8], ax
0x14027e642  mov     rax, [r13+18h]
0x14027e646  mov     r15, [rax]
0x14027e649  mov     qword ptr [rsp+2F8h+BitMapHeader.SizeOfBitMap], r15
0x14027e651  mov     [rsp+2F8h+var_1E8], rbx
0x14027e659  mov     [rsp+2F8h+var_200], rbx
0x14027e661  mov     byte ptr [rsp+2F8h+var_2C8], 1
0x14027e666  lea     rax, [rsp+2F8h+var_1D0]
0x14027e66e  mov     qword ptr [rsp+2F8h+var_2D0], rax
0x14027e673  lea     rax, [rsp+2F8h+var_178]
0x14027e67b  mov     [rsp+2F8h+Timeout], rax
0x14027e680  lea     r9, [rsp+2F8h+var_120]
0x14027e688  lea     r8, [rsp+2F8h+var_1D8]
0x14027e690  mov     rdx, [rcx+30h]
0x14027e694  mov     rcx, r14
0x14027e697  call    NtfsDecodeFileObject
0x14027e69c  cmp     eax, 4
0x14027e69f  jz      short loc_14027E6F2
0x14027e6a1  mov     al, cs:NtfsStatusDebugFlags
0x14027e6a7  mov     esi, 0C000000Dh
0x14027e6ac  test    al, al
0x14027e6ae  jz      short loc_14027E6C0
0x14027e6b0  mov     r8d, 125B61h
0x14027e6b6  mov     edx, esi
0x14027e6b8  mov     rcx, r14
0x14027e6bb  call    NtfsStatusTraceAndDebugInternal
0x14027e6c0  test    r13, r13
0x14027e6c3  setnz   r9b
0x14027e6c7  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e6cb  mov     r8d, esi
0x14027e6ce  mov     rdx, r13
0x14027e6d1  mov     rcx, r14
0x14027e6d4  call    NtfsExtendedCompleteRequestInternal
0x14027e6d9  mov     al, cs:NtfsStatusDebugFlags
0x14027e6df  test    al, al
0x14027e6e1  jz      loc_140280944
0x14027e6e7  mov     r8d, 125B62h
0x14027e6ed  jmp     loc_14028093B
0x14027e6f2  mov     rcx, [rsp+2F8h+var_1D0]
0x14027e6fa  test    rcx, rcx
0x14027e6fd  jz      loc_14028094B
0x14027e703  bt      word ptr [rcx+68h], 9
0x14027e709  jnb     loc_14028094B
0x14027e70f  mov     rdi, qword ptr [rsp+2F8h+var_1D8]
0x14027e717  test    dword ptr [rdi+4], 2000000h
0x14027e71e  jz      short loc_14027E771
0x14027e720  mov     al, cs:NtfsStatusDebugFlags
0x14027e726  mov     ebx, 0C00000A2h
0x14027e72b  test    al, al
0x14027e72d  jz      short loc_14027E73F
0x14027e72f  mov     r8d, 125B82h
0x14027e735  mov     edx, ebx
0x14027e737  mov     rcx, r14
0x14027e73a  call    NtfsStatusTraceAndDebugInternal
0x14027e73f  test    r13, r13
0x14027e742  setnz   r9b
0x14027e746  mov     dword ptr [rsp+2F8h+Timeout], esi
0x14027e74a  mov     r8d, ebx
0x14027e74d  mov     rdx, r13
0x14027e750  mov     rcx, r14
0x14027e753  call    NtfsExtendedCompleteRequestInternal
0x14027e758  mov     al, cs:NtfsStatusDebugFlags
0x14027e75e  test    al, al
0x14027e760  jz      loc_140280A30
0x14027e766  mov     r8d, 125B83h
0x14027e76c  jmp     loc_140280A27
0x14027e771  lea     rcx, [rdi+19E8h]; Object
0x14027e778  mov     [rsp+2F8h+Timeout], rsi; Timeout
0x14027e77d  xor     r9d, r9d; Alertable
0x14027e780  xor     r8d, r8d; WaitMode
0x14027e783  xor     edx, edx; WaitReason
0x14027e785  call    cs:__imp_KeWaitForSingleObject
0x14027e78c  nop     dword ptr [rax+rax+00h]
0x14027e791  xor     r8d, r8d
0x14027e794  test    r12b, r12b
0x14027e797  jz      loc_14027E864
0x14027e79d  cmp     [rbx+8], r8
0x14027e7a1  jz      short loc_14027E7F8
0x14027e7a3  mov     al, cs:NtfsStatusDebugFlags
0x14027e7a9  mov     esi, 0C000000Dh
0x14027e7ae  test    al, al
0x14027e7b0  jz      short loc_14027E7C5
0x14027e7b2  mov     r8d, 125B9Ah
0x14027e7b8  mov     edx, esi
0x14027e7ba  mov     rcx, r14
0x14027e7bd  call    NtfsStatusTraceAndDebugInternal
0x14027e7c2  xor     r8d, r8d
0x14027e7c5  test    r13, r13
0x14027e7c8  setnz   r9b
0x14027e7cc  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e7d1  mov     r8d, esi
0x14027e7d4  mov     rdx, r13
0x14027e7d7  mov     rcx, r14
0x14027e7da  call    NtfsExtendedCompleteRequestInternal
0x14027e7df  mov     al, cs:NtfsStatusDebugFlags
0x14027e7e5  test    al, al
0x14027e7e7  jz      loc_140280944
0x14027e7ed  mov     r8d, 125B9Bh
0x14027e7f3  jmp     loc_14028093B
0x14027e7f8  test    r12b, r12b
0x14027e7fb  jz      short loc_14027E864
0x14027e7fd  cmp     dword ptr [rbx], 1
0x14027e800  jz      short loc_14027E864
0x14027e802  test    r15, r15
0x14027e805  jz      short loc_14027E85C
0x14027e807  mov     al, cs:NtfsStatusDebugFlags
0x14027e80d  mov     esi, 0C000000Dh
0x14027e812  test    al, al
0x14027e814  jz      short loc_14027E829
0x14027e816  mov     r8d, 125BC6h
0x14027e81c  mov     edx, esi
0x14027e81e  mov     rcx, r14
0x14027e821  call    NtfsStatusTraceAndDebugInternal
0x14027e826  xor     r8d, r8d
0x14027e829  test    r13, r13
0x14027e82c  setnz   r9b
0x14027e830  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e835  mov     r8d, esi
0x14027e838  mov     rdx, r13
0x14027e83b  mov     rcx, r14
0x14027e83e  call    NtfsExtendedCompleteRequestInternal
0x14027e843  mov     al, cs:NtfsStatusDebugFlags
0x14027e849  test    al, al
0x14027e84b  jz      loc_140280944
0x14027e851  mov     r8d, 125BC7h
0x14027e857  jmp     loc_14028093B
0x14027e85c  mov     r12, r8
0x14027e85f  jmp     loc_14027E8FF
0x14027e864  test    r15, r15
0x14027e867  jg      short loc_14027E8BE
0x14027e869  mov     al, cs:NtfsStatusDebugFlags
0x14027e86f  mov     esi, 0C000000Dh
0x14027e874  test    al, al
0x14027e876  jz      short loc_14027E88B
0x14027e878  mov     r8d, 125BACh
0x14027e87e  mov     edx, esi
0x14027e880  mov     rcx, r14
0x14027e883  call    NtfsStatusTraceAndDebugInternal
0x14027e888  xor     r8d, r8d
0x14027e88b  test    r13, r13
0x14027e88e  setnz   r9b
0x14027e892  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e897  mov     r8d, esi
0x14027e89a  mov     rdx, r13
0x14027e89d  mov     rcx, r14
0x14027e8a0  call    NtfsExtendedCompleteRequestInternal
0x14027e8a5  mov     al, cs:NtfsStatusDebugFlags
0x14027e8ab  test    al, al
0x14027e8ad  jz      loc_140280944
0x14027e8b3  mov     r8d, 125BADh
0x14027e8b9  jmp     loc_14028093B
0x14027e8be  mov     edx, [rdi+16Ch]
0x14027e8c4  lea     rax, [r15-1]
0x14027e8c8  imul    rdx, rax
0x14027e8cc  mov     [rsp+2F8h+var_170], rdx
0x14027e8d4  mov     [rsp+2F8h+var_148], rdx
0x14027e8dc  cmp     rdx, r15
0x14027e8df  jl      loc_1402808EF
0x14027e8e5  mov     cl, [rdi+1E8h]
0x14027e8eb  mov     r12, rdx
0x14027e8ee  sar     r12, cl
0x14027e8f1  mov     eax, 0FFFFFFFEh
0x14027e8f6  cmp     r12, rax
0x14027e8f9  jg      loc_1402808EF
0x14027e8ff  mov     [rsp+2F8h+var_130], r8
0x14027e907  mov     [rsp+2F8h+var_188], r8
0x14027e90f  mov     [rsp+2F8h+var_160], r8
0x14027e917  mov     [rsp+2F8h+P], r8
0x14027e91f  mov     [rsp+2F8h+var_210], r8b
  ... truncated ...
```
