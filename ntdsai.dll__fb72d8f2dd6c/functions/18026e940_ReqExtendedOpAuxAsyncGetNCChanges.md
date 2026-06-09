# ReqExtendedOpAuxAsyncGetNCChanges

- ea: `0x18026e940`
- end: `0x18026fc81`
- name: `ReqExtendedOpAuxAsyncGetNCChanges`
- size: `4929`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18026e268`
- `0x18026fc90`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x180030af8`
- `0x18003e2e0`
- `0x18007cf4c`
- `0x180151c24`
- `0x180173984`
- `0x180243cf0`
- `0x18026e940`
- `0x18027c87c`
- `0x18027c90c`
- `0x180302138`
- `0x1803072c4`
- `0x18030eb20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18026f93c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18026f93c`
- `RPCRT4!RpcAsyncCancelCall` at `0x18026f641`
- `RPCRT4!RpcAsyncCancelCall` at `0x18026f641`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18026e985`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18026e985`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18026f741`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18026f741`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18026ef8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18026f54a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18026f922`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18026ef8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18026f54a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18026f922`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18026eb34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18026f338`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18026f836`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18026eb34`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18026f338`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18026f836`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18026e9bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18026e9bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18026fa42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18026fa42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18026e9a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18026e9a8`

## pseudocode

```c
__int64 __fastcall ReqExtendedOpAuxAsyncGetNCChanges(int a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // r12
  int v5; // eax
  struct _TP_WAIT *ThreadpoolWait; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  BOOL v14; // r14d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // edi
  _DWORD *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  BOOL v25; // r15d
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rax
  int v29; // edx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // r9
  BOOL v36; // r15d
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // edx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // r8
  __int64 v46; // r9
  BOOL v47; // r15d
  bool v48; // zf
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // r8
  __int64 v55; // r9
  BOOL v56; // r12d
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r8
  __int64 v63; // r9
  BOOL v64; // r15d
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // r8
  __int64 v71; // r9
  BOOL v72; // r15d
  int v73; // eax
  int v74; // edx
  int v75; // r12d
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // r8
  __int64 v83; // r9
  BOOL v84; // r15d
  int v85; // eax
  __int64 v86; // r13
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  __int64 v90; // r9
  __int64 v91; // r8
  __int64 v92; // r9
  BOOL v93; // r15d
  int v94; // eax
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // r8
  __int64 v102; // r9
  BOOL v103; // r15d
  int v104; // eax
  __int64 v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 v111; // r8
  __int64 v112; // r9
  BOOL v113; // r15d
  int v114; // eax
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // r8
  __int64 v122; // r9
  BOOL v123; // r15d
  int v124; // eax
  int v125; // ecx
  RTL_SRWLOCK *v126; // r12
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // rdx
  __int64 v130; // rcx
  __int64 v131; // r8
  __int64 v132; // r9
  __int64 v133; // r8
  __int64 v134; // r9
  BOOL v135; // r15d
  int v136; // eax
  __int64 v137; // rdx
  __int64 v138; // rax
  int v139; // edx
  int v140; // r8d
  int v141; // r9d
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v148; // r8
  __int64 v149; // r9
  BOOL v150; // r14d
  int v151; // r9d
  __int64 v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // r8
  __int64 v157; // r9
  __int64 v158; // r8
  __int64 v159; // r9
  BOOL v160; // r15d
  struct _TP_WAIT *v161; // rcx
  int v163; // [rsp+30h] [rbp-A8h]
  int v164; // [rsp+38h] [rbp-A0h]
  DWORD Reply; // [rsp+60h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-70h]
  PTP_WAIT pwa; // [rsp+70h] [rbp-68h]
  struct _TP_WAIT *v168; // [rsp+78h] [rbp-60h]
  _DWORD *v169; // [rsp+80h] [rbp-58h]
  _DWORD *v170; // [rsp+88h] [rbp-50h]
  struct _TP_WAIT *v171; // [rsp+90h] [rbp-48h]
  struct _TP_WAIT *v174; // [rsp+F0h] [rbp+18h]
  _DWORD *v175; // [rsp+F8h] [rbp+20h]

  v4 = a2;
  v5 = a1;
  Reply = 0;
  ThreadpoolWait = 0;
  pwa = 0;
  if ( gfTPShuttingDown )
  {
    v168 = 0;
  }
  else
  {
    if ( TryAcquireSRWLockShared(&gTPSRWLock) )
    {
      if ( !gfTPShuttingDown )
      {
        ThreadpoolWait = CreateThreadpoolWait(ReqExtendedOpAuxAsyncNotify, (PVOID)v4, gpAsyncRPCTP);
        pwa = ThreadpoolWait;
      }
      ReleaseSRWLockShared(&gTPSRWLock);
    }
    v168 = ThreadpoolWait;
    v5 = a1;
  }
  v174 = ThreadpoolWait;
  v171 = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    Reply = 8;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v8, v7)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 5) )
    {
      goto LABEL_17;
    }
    if ( !gfTraceToSecondProvider )
      goto LABEL_272;
    if ( (unsigned int)THStateCheckForTraceOverride(v8, v7) )
    {
LABEL_17:
      v11 = 1;
LABEL_18:
      v14 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v8, v7)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v8, v7, v12, v13)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 5));
      if ( !(unsigned int)THStateCheckForTraceOverride(v8, v7)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 5) )
      {
        v11 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17311146,
        2,
        5,
        v11,
        v14,
        118,
        &WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
      goto LABEL_272;
    }
    if ( (unsigned int)ThStateCheckIfTraceToSecondProvier(v8, v7, v9, v10) )
    {
      v11 = 1;
      if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 5) )
        goto LABEL_18;
    }
LABEL_272:
    v161 = v174;
    goto LABEL_273;
  }
  drsPrepareAsyncRpcState(v5, *(_QWORD *)(v4 + 264), 0, a4, v4);
  v170 = (_DWORD *)(v4 + 220);
  *(_DWORD *)(v4 + 220) |= 2u;
  SRWLock = (PSRWLOCK)(v4 + 224);
  AcquireSRWLockExclusive((PSRWLOCK)(v4 + 224));
  if ( (unsigned int)THStateCheckForTraceOverride(v16, v15)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) )
  {
    goto LABEL_37;
  }
  if ( !gfTraceToSecondProvider )
  {
LABEL_35:
    v21 = 1;
LABEL_36:
    v22 = (_DWORD *)(v4 + 232);
    v175 = (_DWORD *)(v4 + 232);
    goto LABEL_48;
  }
  if ( (unsigned int)THStateCheckForTraceOverride(v18, v17) )
  {
LABEL_37:
    v21 = 1;
    goto LABEL_38;
  }
  if ( !(unsigned int)ThStateCheckIfTraceToSecondProvier(v18, v17, v19, v20) )
    goto LABEL_35;
  v21 = 1;
  if ( !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5) )
    goto LABEL_36;
LABEL_38:
  v25 = gfTraceToSecondProvider
     && ((unsigned int)THStateCheckForTraceOverride(v18, v17)
      || (unsigned int)ThStateCheckIfTraceToSecondProvier(v18, v17, v23, v24)
      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
  if ( (unsigned int)THStateCheckForTraceOverride(v18, v17)
    || (v26 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 5), v27 = 0, v26) )
  {
    v27 = 1;
  }
  v175 = (_DWORD *)(v4 + 232);
  v28 = DRSACSToSz(*(unsigned int *)(v4 + 232), v27);
  WPP_SF_qs(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    17311201,
    4,
    5,
    v29,
    v25,
    120,
    &WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids,
    v4,
    v28);
  v22 = (_DWORD *)(v4 + 232);
LABEL_48:
  v169 = v22;
  if ( !*v22 || *v22 == 3 )
  {
    if ( *(_DWORD *)(v4 + 236) )
    {
      Reply = 1818;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v51, v50)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 5)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v51, v50, v52, v53)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 5)) )
      {
        v56 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v51, v50)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v51, v50, v54, v55)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 5));
        if ( (unsigned int)THStateCheckForTraceOverride(v51, v50)
          || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 5) == 0, v57 = 0, !v48) )
        {
          v57 = 1;
        }
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17311223,
          3,
          5,
          v57,
          v56,
          122,
          (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
        v4 = a2;
      }
    }
    else
    {
      Reply = 0;
      *v22 = 1;
      if ( (unsigned int)THStateCheckForTraceOverride(v18, v17)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v42, v41, v43, v44)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
      {
        v47 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v42, v41)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v42, v41, v45, v46)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
        if ( (unsigned int)THStateCheckForTraceOverride(v42, v41)
          || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5) == 0, v49 = 0, !v48) )
        {
          v49 = 1;
        }
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17311216,
          5,
          5,
          v49,
          v47,
          121,
          (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
      }
    }
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v31, v30)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v31, v30, v32, v33)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 5)) )
    {
      v36 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v31, v30)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v31, v30, v34, v35)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v31, v30)
        || (v37 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 5), v38 = 0, v37) )
      {
        v38 = 1;
      }
      v39 = DRSACSToSz(*(unsigned int *)(v4 + 232), v38);
      WPP_SF_qs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17311233,
        2,
        5,
        v40,
        v36,
        123,
        &WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids,
        v4,
        v39);
    }
    Reply = 1359;
  }
  ReleaseSRWLockExclusive(SRWLock);
  if ( Reply )
    goto LABEL_272;
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
    || (unsigned int)THStateCheckForTraceOverride(v59, v58)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v59, v58, v60, v61)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
  {
    v64 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v59, v58, v62, v63)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
    if ( (unsigned int)THStateCheckForTraceOverride(v59, v58)
      || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) == 0, v65 = 0, !v48) )
    {
      v65 = 1;
    }
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17311252,
      4,
      5,
      v65,
      v64,
      124,
      (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
  }
  Reply = I_DRSGetNCChanges(a1, *(_QWORD *)(v4 + 264), 0, *(_QWORD *)(v4 + 256), v4 + 272, v4 + 432, v4 + 600, v4, 0);
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
    || (unsigned int)THStateCheckForTraceOverride(v67, v66)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v67, v66, v68, v69)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
  {
    v72 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v67, v66)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v67, v66, v70, v71)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
    if ( (unsigned int)THStateCheckForTraceOverride(v67, v66)
      || (v73 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 5), v74 = 0, v73) )
    {
      v74 = 1;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17311269,
      4,
      5,
      v74,
      v72,
      125,
      (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
  }
  v75 = 0;
  AcquireSRWLockExclusive(SRWLock);
  if ( Reply )
  {
    v86 = a2;
  }
  else
  {
    *v175 = 2;
    *v170 |= 1u;
    if ( (unsigned int)THStateCheckForTraceOverride(v77, v76)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v79, v78)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v79, v78, v80, v81)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
    {
      v84 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v79, v78)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v79, v78, v82, v83)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v79, v78)
        || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) == 0, v85 = 0, !v48) )
      {
        v85 = 1;
      }
      v86 = a2;
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17311289,
        4,
        5,
        v85,
        v84,
        127,
        (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
    }
    else
    {
      v86 = a2;
    }
    if ( *(_DWORD *)(v86 + 236) )
    {
      v75 = 1;
      if ( (unsigned int)THStateCheckForTraceOverride(v79, v78)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v88, v87)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v88, v87, v89, v90)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
      {
        v93 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v88, v87)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v88, v87, v91, v92)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
        if ( (unsigned int)THStateCheckForTraceOverride(v88, v87)
          || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) == 0, v94 = 0, !v48) )
        {
          v94 = 1;
        }
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17311298,
          4,
          5,
          v94,
          v93,
          128,
          (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
      }
    }
  }
  ReleaseSRWLockExclusive(SRWLock);
  if ( v75 )
  {
    if ( (unsigned int)THStateCheckForTraceOverride(v96, v95)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v98, v97)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v98, v97, v99, v100)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
    {
      v103 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v98, v97)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v98, v97, v101, v102)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v98, v97)
        || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) == 0, v104 = 0, !v48) )
      {
        v104 = 1;
      }
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17311315,
        4,
        5,
        v104,
        v103,
        129,
        (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
    }
    RpcAsyncCancelCall((PRPC_ASYNC_STATE)(v86 + 24), 1);
    if ( (unsigned int)THStateCheckForTraceOverride(v106, v105)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v108, v107)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v108, v107, v109, v110)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
    {
      v113 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v108, v107)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v108, v107, v111, v112)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v108, v107)
        || (v48 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) == 0, v114 = 0, !v48) )
      {
        v114 = 1;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17311326,
        4,
        5,
        v114,
        v113,
        130,
        (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
    }
    Reply = WaitForSingleObject(*(HANDLE *)(v86 + 72), 0xFFFFFFFF);
    if ( (unsigned int)THStateCheckForTraceOverride(v116, v115)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v118, v117)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v118, v117, v119, v120)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
    {
      v123 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v118, v117)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v118, v117, v121, v122)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v118, v117)
        || (v124 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 5), v125 = 0, v124) )
      {
        v125 = 1;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17311340,
        4,
        5,
        v125,
        v123,
        131,
        (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
    }
    v126 = SRWLock;
    AcquireSRWLockExclusive(SRWLock);
    if ( (unsigned int)THStateCheckForTraceOverride(v128, v127)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v130, v129)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v130, v129, v131, v132)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5)) )
    {
      v135 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v130, v129)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v130, v129, v133, v134)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v130, v129)
        || (v136 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 5), v137 = 0, v136) )
      {
        v137 = 1;
      }
      v138 = DRSACSToSz((unsigned int)*v175, v137);
      WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v139, v140, v141, v139, v135, v163, v164, v138, v86);
    }
    *v175 = 4;
    ReleaseSRWLockExclusive(v126);
    *v170 &= ~1u;
    RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(v86 + 24), &Reply);
    if ( (unsigned int)THStateCheckForTraceOverride(v143, v142)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v145, v144)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v145, v144, v146, v147)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
    {
      v150 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v145, v144)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v145, v144, v148, v149)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
      if ( !(unsigned int)THStateCheckForTraceOverride(v145, v144)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5) )
      {
        v21 = 0;
      }
      WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17311365, 5, v151, v21, v150, 133);
    }
    Reply = 1818;
    goto LABEL_272;
  }
  if ( Reply )
    goto LABEL_272;
  SetThreadpoolWait(pwa, *(HANDLE *)(v86 + 72), 0);
  v174 = 0;
  if ( !(unsigned int)THStateCheckForTraceOverride(v153, v152)
    && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5)
    && (!gfTraceToSecondProvider
     || !(unsigned int)THStateCheckForTraceOverride(v155, v154)
     && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v155, v154, v156, v157)
      || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5))) )
  {
    goto LABEL_272;
  }
  v160 = gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v155, v154)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v155, v154, v158, v159)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 5));
  if ( !(unsigned int)THStateCheckForTraceOverride(v155, v154)
    && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 5) )
  {
    v21 = 0;
  }
  WPP_SF_q(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    17311390,
    4,
    5,
    v21,
    v160,
    134,
    (__int64)&WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids);
  v161 = 0;
LABEL_273:
  if ( v161 )
    DSCloseThreadpoolWait();
  return Reply;
}

```

## disassembly

```asm
0x18026e940  mov     [rsp+arg_8], rdx
0x18026e945  mov     [rsp+arg_0], rcx
0x18026e94a  push    rbx
0x18026e94b  push    rsi
0x18026e94c  push    rdi
0x18026e94d  push    r12
0x18026e94f  push    r13
0x18026e951  push    r14
0x18026e953  push    r15
0x18026e955  sub     rsp, 0A0h
0x18026e95c  mov     r12, rdx
0x18026e95f  mov     rax, rcx
0x18026e962  xor     ebx, ebx
0x18026e964  mov     [rsp+0D8h+Reply], ebx
0x18026e968  mov     edi, ebx
0x18026e96a  mov     [rsp+0D8h+pwa], rbx
0x18026e96f  cmp     cs:gfTPShuttingDown, ebx
0x18026e975  jz      short loc_18026E97E
0x18026e977  mov     [rsp+0D8h+var_60], rbx
0x18026e97c  jmp     short loc_18026E9D0
0x18026e97e  lea     rcx, gTPSRWLock; SRWLock
0x18026e985  call    cs:__imp_TryAcquireSRWLockShared
0x18026e98b  test    al, al
0x18026e98d  jz      short loc_18026E9C3
0x18026e98f  cmp     cs:gfTPShuttingDown, ebx
0x18026e995  jnz     short loc_18026E9B6
0x18026e997  mov     r8, cs:gpAsyncRPCTP; pcbe
0x18026e99e  mov     rdx, r12; pv
0x18026e9a1  lea     rcx, ReqExtendedOpAuxAsyncNotify; pfnwa
0x18026e9a8  call    cs:__imp_CreateThreadpoolWait
0x18026e9ae  mov     rdi, rax
0x18026e9b1  mov     [rsp+0D8h+pwa], rax
0x18026e9b6  lea     rcx, gTPSRWLock; SRWLock
0x18026e9bd  call    cs:__imp_ReleaseSRWLockShared
0x18026e9c3  mov     [rsp+0D8h+var_60], rdi
0x18026e9c8  mov     rax, [rsp+0D8h+arg_0]
0x18026e9d0  mov     [rsp+0D8h+arg_10], rdi
0x18026e9d8  mov     [rsp+0D8h+var_48], rdi
0x18026e9e0  test    rdi, rdi
0x18026e9e3  jnz     loc_18026EAF3
0x18026e9e9  mov     [rsp+0D8h+Reply], 8
0x18026e9f1  lea     r13d, [rdi+2]
0x18026e9f5  mov     ecx, r13d
0x18026e9f8  call    IncrementWPPPerfCountersForLevel
0x18026e9fd  test    eax, eax
0x18026e9ff  jnz     short loc_18026EA5C
0x18026ea01  call    THStateCheckForTraceOverride
0x18026ea06  test    eax, eax
0x18026ea08  jnz     short loc_18026EA5C
0x18026ea0a  lea     esi, [rdi+5]
0x18026ea0d  mov     r8d, esi
0x18026ea10  mov     edx, r13d
0x18026ea13  xor     ecx, ecx
0x18026ea15  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ea1a  test    eax, eax
0x18026ea1c  jnz     short loc_18026EA61
0x18026ea1e  mov     eax, cs:gfTraceToSecondProvider
0x18026ea24  test    eax, eax
0x18026ea26  jz      loc_18026FC58
0x18026ea2c  call    THStateCheckForTraceOverride
0x18026ea31  test    eax, eax
0x18026ea33  jnz     short loc_18026EA61
0x18026ea35  call    ThStateCheckIfTraceToSecondProvier
0x18026ea3a  test    eax, eax
0x18026ea3c  jz      loc_18026FC58
0x18026ea42  mov     r8d, esi
0x18026ea45  mov     edx, r13d
0x18026ea48  lea     edi, [rsi-4]
0x18026ea4b  mov     ecx, edi
0x18026ea4d  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ea52  test    eax, eax
0x18026ea54  jz      loc_18026FC58
0x18026ea5a  jmp     short loc_18026EA66
0x18026ea5c  mov     esi, 5
0x18026ea61  mov     edi, 1
0x18026ea66  mov     eax, cs:gfTraceToSecondProvider
0x18026ea6c  test    eax, eax
0x18026ea6e  jz      short loc_18026EA98
0x18026ea70  call    THStateCheckForTraceOverride
0x18026ea75  test    eax, eax
0x18026ea77  jnz     short loc_18026EA93
0x18026ea79  call    ThStateCheckIfTraceToSecondProvier
0x18026ea7e  test    eax, eax
0x18026ea80  jz      short loc_18026EA98
0x18026ea82  mov     r8d, esi
0x18026ea85  mov     edx, r13d
0x18026ea88  mov     ecx, edi
0x18026ea8a  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ea8f  test    eax, eax
0x18026ea91  jz      short loc_18026EA98
0x18026ea93  mov     r14d, edi
0x18026ea96  jmp     short loc_18026EA9B
0x18026ea98  mov     r14d, ebx
0x18026ea9b  call    THStateCheckForTraceOverride
0x18026eaa0  test    eax, eax
0x18026eaa2  jnz     short loc_18026EAB7
0x18026eaa4  mov     r8d, esi
0x18026eaa7  mov     edx, r13d
0x18026eaaa  xor     ecx, ecx
0x18026eaac  call    CheckWPPLevelFlagsEnabledForProvider
0x18026eab1  test    eax, eax
0x18026eab3  jnz     short loc_18026EAB7
0x18026eab5  mov     edi, ebx
0x18026eab7  lea     rax, WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids
0x18026eabe  mov     [rsp+0D8h+var_A0], rax; LPCGUID
0x18026eac3  mov     [rsp+0D8h+var_A8], 76h ; 'v'; __int16
0x18026eaca  mov     [rsp+0D8h+var_B0], r14d; int
0x18026eacf  mov     [rsp+0D8h+var_B8], edi; int
0x18026ead3  mov     r9d, esi; int
0x18026ead6  mov     r8d, r13d; int
0x18026ead9  mov     edx, 10825AAh; int
0x18026eade  mov     rcx, cs:WPP_GLOBAL_Control
0x18026eae5  mov     rcx, [rcx+10h]; int
0x18026eae9  call    WPP_SF_
0x18026eaee  jmp     loc_18026FC58
0x18026eaf3  mov     qword ptr [rsp+0D8h+var_B8], r12
0x18026eaf8  xor     r8d, r8d
0x18026eafb  mov     rdx, [r12+108h]
0x18026eb03  mov     rcx, rax
0x18026eb06  call    drsPrepareAsyncRpcState
0x18026eb0b  lea     rax, [r12+0DCh]
0x18026eb13  mov     [rsp+0D8h+var_50], rax
0x18026eb1b  mov     r13d, 2
0x18026eb21  or      [rax], r13d
0x18026eb24  lea     rax, [r12+0E0h]
0x18026eb2c  mov     [rsp+0D8h+SRWLock], rax
0x18026eb31  mov     rcx, rax; SRWLock
0x18026eb34  call    cs:__imp_AcquireSRWLockExclusive
0x18026eb3a  call    THStateCheckForTraceOverride
0x18026eb3f  mov     esi, 5
0x18026eb44  lea     r14d, [rsi-1]
0x18026eb48  test    eax, eax
0x18026eb4a  jnz     short loc_18026EBA9
0x18026eb4c  mov     r8d, esi
0x18026eb4f  mov     edx, r14d
0x18026eb52  xor     ecx, ecx
0x18026eb54  call    CheckWPPLevelFlagsEnabledForProvider
0x18026eb59  test    eax, eax
0x18026eb5b  jnz     short loc_18026EBA9
0x18026eb5d  mov     eax, cs:gfTraceToSecondProvider
0x18026eb63  test    eax, eax
0x18026eb65  jz      short loc_18026EB8F
0x18026eb67  call    THStateCheckForTraceOverride
0x18026eb6c  test    eax, eax
0x18026eb6e  jnz     short loc_18026EBA9
0x18026eb70  call    ThStateCheckIfTraceToSecondProvier
0x18026eb75  test    eax, eax
0x18026eb77  jz      short loc_18026EB8F
0x18026eb79  mov     r8d, esi
0x18026eb7c  mov     edx, r14d
0x18026eb7f  lea     edi, [rsi-4]
0x18026eb82  mov     ecx, edi
0x18026eb84  call    CheckWPPLevelFlagsEnabledForProvider
0x18026eb89  test    eax, eax
0x18026eb8b  jnz     short loc_18026EBAE
0x18026eb8d  jmp     short loc_18026EB94
0x18026eb8f  mov     edi, 1
0x18026eb94  lea     rax, [r12+0E8h]
0x18026eb9c  mov     [rsp+0D8h+arg_18], rax
0x18026eba4  jmp     loc_18026EC61
0x18026eba9  mov     edi, 1
0x18026ebae  mov     eax, cs:gfTraceToSecondProvider
0x18026ebb4  test    eax, eax
0x18026ebb6  jz      short loc_18026EBE0
0x18026ebb8  call    THStateCheckForTraceOverride
0x18026ebbd  test    eax, eax
0x18026ebbf  jnz     short loc_18026EBDB
0x18026ebc1  call    ThStateCheckIfTraceToSecondProvier
0x18026ebc6  test    eax, eax
0x18026ebc8  jz      short loc_18026EBE0
0x18026ebca  mov     r8d, esi
0x18026ebcd  mov     edx, r14d
0x18026ebd0  mov     ecx, edi
0x18026ebd2  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ebd7  test    eax, eax
0x18026ebd9  jz      short loc_18026EBE0
0x18026ebdb  mov     r15d, edi
0x18026ebde  jmp     short loc_18026EBE3
0x18026ebe0  mov     r15d, ebx
0x18026ebe3  call    THStateCheckForTraceOverride
0x18026ebe8  test    eax, eax
0x18026ebea  jnz     short loc_18026EBFF
0x18026ebec  mov     r8d, esi
0x18026ebef  mov     edx, r14d
0x18026ebf2  xor     ecx, ecx
0x18026ebf4  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ebf9  test    eax, eax
0x18026ebfb  mov     edx, ebx
0x18026ebfd  jz      short loc_18026EC01
0x18026ebff  mov     edx, edi
0x18026ec01  lea     rax, [r12+0E8h]
0x18026ec09  mov     [rsp+0D8h+arg_18], rax
0x18026ec11  mov     ecx, [rax]
0x18026ec13  call    DRSACSToSz
0x18026ec18  mov     [rsp+0D8h+var_90], rax; __int64
0x18026ec1d  mov     qword ptr [rsp+0D8h+var_98], r12; char
0x18026ec22  lea     rax, WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids
0x18026ec29  mov     [rsp+0D8h+var_A0], rax; LPCGUID
0x18026ec2e  mov     [rsp+0D8h+var_A8], 78h ; 'x'; __int16
0x18026ec35  mov     [rsp+0D8h+var_B0], r15d; int
0x18026ec3a  mov     [rsp+0D8h+var_B8], edx; int
0x18026ec3e  mov     r9d, esi; int
0x18026ec41  mov     r8d, r14d; int
0x18026ec44  mov     edx, 10825E1h; int
0x18026ec49  mov     rcx, cs:WPP_GLOBAL_Control
0x18026ec50  mov     rcx, [rcx+10h]; int
0x18026ec54  call    WPP_SF_qs
0x18026ec59  lea     rax, [r12+0E8h]
0x18026ec61  mov     [rsp+0D8h+var_58], rax
0x18026ec69  mov     r15d, 3
0x18026ec6f  cmp     [rax], ebx
0x18026ec71  jz      loc_18026ED8D
0x18026ec77  cmp     [rax], r15d
0x18026ec7a  jz      loc_18026ED8D
0x18026ec80  mov     ecx, r13d
0x18026ec83  call    IncrementWPPPerfCountersForLevel
0x18026ec88  test    eax, eax
0x18026ec8a  jnz     short loc_18026ECDF
0x18026ec8c  call    THStateCheckForTraceOverride
0x18026ec91  test    eax, eax
0x18026ec93  jnz     short loc_18026ECDF
0x18026ec95  mov     r8d, esi
0x18026ec98  mov     edx, r13d
0x18026ec9b  xor     ecx, ecx
0x18026ec9d  call    CheckWPPLevelFlagsEnabledForProvider
0x18026eca2  test    eax, eax
0x18026eca4  jnz     short loc_18026ECDF
0x18026eca6  mov     eax, cs:gfTraceToSecondProvider
0x18026ecac  test    eax, eax
0x18026ecae  jz      loc_18026ED80
0x18026ecb4  call    THStateCheckForTraceOverride
0x18026ecb9  test    eax, eax
0x18026ecbb  jnz     short loc_18026ECDF
0x18026ecbd  call    ThStateCheckIfTraceToSecondProvier
0x18026ecc2  test    eax, eax
0x18026ecc4  jz      loc_18026ED80
0x18026ecca  mov     r8d, esi
0x18026eccd  mov     edx, r13d
0x18026ecd0  mov     ecx, edi
0x18026ecd2  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ecd7  test    eax, eax
0x18026ecd9  jz      loc_18026ED80
0x18026ecdf  mov     eax, cs:gfTraceToSecondProvider
0x18026ece5  test    eax, eax
0x18026ece7  jz      short loc_18026ED11
0x18026ece9  call    THStateCheckForTraceOverride
0x18026ecee  test    eax, eax
0x18026ecf0  jnz     short loc_18026ED0C
0x18026ecf2  call    ThStateCheckIfTraceToSecondProvier
0x18026ecf7  test    eax, eax
0x18026ecf9  jz      short loc_18026ED11
0x18026ecfb  mov     r8d, esi
0x18026ecfe  mov     edx, r13d
0x18026ed01  mov     ecx, edi
0x18026ed03  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ed08  test    eax, eax
0x18026ed0a  jz      short loc_18026ED11
0x18026ed0c  mov     r15d, edi
0x18026ed0f  jmp     short loc_18026ED14
0x18026ed11  mov     r15d, ebx
0x18026ed14  call    THStateCheckForTraceOverride
0x18026ed19  test    eax, eax
0x18026ed1b  jnz     short loc_18026ED30
0x18026ed1d  mov     r8d, esi
0x18026ed20  mov     edx, r13d
0x18026ed23  xor     ecx, ecx
0x18026ed25  call    CheckWPPLevelFlagsEnabledForProvider
0x18026ed2a  test    eax, eax
0x18026ed2c  mov     edx, ebx
0x18026ed2e  jz      short loc_18026ED32
0x18026ed30  mov     edx, edi
0x18026ed32  mov     ecx, [r12+0E8h]
0x18026ed3a  call    DRSACSToSz
0x18026ed3f  mov     [rsp+0D8h+var_90], rax; __int64
0x18026ed44  mov     qword ptr [rsp+0D8h+var_98], r12; char
0x18026ed49  lea     rax, WPP_ae6f0ee96de73b859e9bc6049b1bf686_Traceguids
0x18026ed50  mov     [rsp+0D8h+var_A0], rax; LPCGUID
0x18026ed55  mov     [rsp+0D8h+var_A8], 7Bh ; '{'; __int16
0x18026ed5c  mov     [rsp+0D8h+var_B0], r15d; int
0x18026ed61  mov     [rsp+0D8h+var_B8], edx; int
0x18026ed65  mov     r9d, esi; int
0x18026ed68  mov     r8d, r13d; int
0x18026ed6b  mov     edx, 1082601h; int
0x18026ed70  mov     rcx, cs:WPP_GLOBAL_Control
0x18026ed77  mov     rcx, [rcx+10h]; int
0x18026ed7b  call    WPP_SF_qs
0x18026ed80  mov     [rsp+0D8h+Reply], 54Fh
0x18026ed88  jmp     loc_18026EF8A
0x18026ed8d  cmp     [r12+0ECh], ebx
0x18026ed95  jnz     loc_18026EE84
0x18026ed9b  mov     [rsp+0D8h+Reply], ebx
0x18026ed9f  mov     [rax], edi
0x18026eda1  call    THStateCheckForTraceOverride
0x18026eda6  test    eax, eax
0x18026eda8  jnz     short loc_18026EDF2
0x18026edaa  mov     r8d, esi
0x18026edad  mov     edx, esi
0x18026edaf  xor     ecx, ecx
0x18026edb1  call    CheckWPPLevelFlagsEnabledForProvider
0x18026edb6  test    eax, eax
  ... truncated ...
```
