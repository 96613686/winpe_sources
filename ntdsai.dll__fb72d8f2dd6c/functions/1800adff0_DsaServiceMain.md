# DsaServiceMain

- ea: `0x1800adff0`
- end: `0x1800af38b`
- name: `DsaServiceMain`
- size: `5019`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x18007cf4c`
- `0x1800a504c`
- `0x1800a94a0`
- `0x1800aae40`
- `0x1800acc30`
- `0x1800adff0`
- `0x1800b700c`
- `0x180173260`
- `0x180187e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ae370`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ae370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aedbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aefdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18045a54c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aedbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aefdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18045a54c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae1f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae53e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aed76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aefb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae1f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ae53e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aed76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aefb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae854`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800aeeb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af178`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ae854`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800aeeb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800af178`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aed44`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aed44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aefc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aefc7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800ae20a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800ae20a`
- `ntdll!RtlGetNtProductType` at `0x1800ae4bd`
- `ntdll!RtlGetNtProductType` at `0x1800ae4bd`
- `WS2_32!__imp_WSAStartup` at `0x1800ae495`
- `WS2_32!__imp_WSAStartup` at `0x1800ae495`
- `WS2_32!__imp_WSACleanup` at `0x1800af29d`
- `WS2_32!__imp_WSACleanup` at `0x18045a591`
- `WS2_32!__imp_WSACleanup` at `0x1800af29d`
- `WS2_32!__imp_WSACleanup` at `0x18045a591`
- `LSASRV!LsaISafeMode` at `0x1800ae4cb`
- `LSASRV!LsaISafeMode` at `0x1800ae4cb`
- `SAMSRV!SampUsingDsData` at `0x1800ae4f1`
- `SAMSRV!SampUsingDsData` at `0x1800ae4f1`

## string_xrefs

- `0x1800af00d`: `StartNTDSDependentServices`

## pseudocode

```c
__int64 __fastcall DsaServiceMain(DWORD a1, void *a2, unsigned int a3, _DWORD *a4)
{
  DWORD v5; // r12d
  int v6; // edi
  int v7; // r13d
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  BOOL v16; // r12d
  bool v17; // zf
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // r8
  __int64 v27; // r9
  BOOL v28; // ebx
  int v29; // eax
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // r9
  BOOL v37; // ebx
  int v38; // eax
  int v39; // ecx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // r8
  __int64 v45; // r9
  BOOL v46; // ebx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // r8
  __int64 v52; // r9
  BOOL v53; // ebx
  int v54; // eax
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // r8
  __int64 v61; // r9
  BOOL v62; // ebx
  int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // r8
  __int64 v69; // r9
  BOOL v70; // ebx
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 v77; // r9
  BOOL v78; // ebx
  int v79; // eax
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // r8
  __int64 v83; // r9
  __int64 v84; // r8
  __int64 v85; // r9
  BOOL v86; // ebx
  int v87; // eax
  int v88; // ecx
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // r8
  __int64 v94; // r9
  BOOL v95; // ebx
  int v96; // eax
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // r8
  __int64 v102; // r9
  BOOL v103; // ebx
  int v104; // eax
  int v105; // ecx
  BOOL v106; // ebx
  __int64 v107; // rdx
  __int64 v108; // rcx
  __int64 v109; // r8
  __int64 v110; // r9
  __int64 v111; // r8
  __int64 v112; // r9
  BOOL v113; // ebx
  int v114; // eax
  __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // r8
  __int64 v120; // r9
  BOOL v121; // ebx
  int v122; // eax
  int v123; // ecx
  int v124; // eax
  __int64 v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // r8
  __int64 v128; // r9
  __int64 v129; // r8
  __int64 v130; // r9
  BOOL v131; // ebx
  int v132; // eax
  __int64 v133; // rdx
  __int64 v134; // rcx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // r8
  __int64 v138; // r9
  BOOL v139; // ebx
  int v140; // eax
  _DWORD *v141; // rbx
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v148; // r8
  __int64 v149; // r9
  BOOL v150; // ebx
  int v151; // [rsp+50h] [rbp-218h]
  DWORD ThreadId; // [rsp+54h] [rbp-214h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+58h] [rbp-210h] BYREF
  void *v154; // [rsp+60h] [rbp-208h]
  _DWORD *v155; // [rsp+68h] [rbp-200h]
  _DWORD *v156; // [rsp+70h] [rbp-1F8h]
  WSAData WSAData; // [rsp+80h] [rbp-1E8h] BYREF

  v155 = a4;
  v154 = a2;
  v5 = a1;
  ThreadId = a1;
  v156 = a4;
  v6 = 0;
  v7 = 0;
  ProductType = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( (unsigned int)THStateCheckForTraceOverride(v9, v8)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v11, v10)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v11, v10, v12, v13)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v16 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v11, v10)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v11, v10, v14, v15)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( (unsigned int)THStateCheckForTraceOverride(v11, v10)
      || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v18 = 0, !v17) )
    {
      v18 = 1;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50335209,
      4,
      3,
      v18,
      v16,
      54,
      &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
    v5 = ThreadId;
  }
  *(_DWORD *)gfADAM = (a3 & 2) != 0;
  gfRunningAsExe = a3 & 1;
  if ( (a3 & 2) != 0 || (v19 = 1, (a3 & 1) != 0) )
    v19 = 0;
  gfRequireSchemaUpgrade = v19;
  if ( (a3 & 1) != 0 || (v20 = 1, (a3 & 2) != 0) )
    v20 = 0;
  gfRunningInsideLsa = v20;
  gfDoSamChecks = (a3 >> 3) & 1;
  gfFirstStartup = (a3 >> 2) & 1;
  if ( (a3 & 1) != 0 )
  {
    gfDitIsReadOnly = 1;
    gfAllowAdminAccessOnly = 1;
    gfGenerateReferrals = 0;
  }
  else
  {
    EnterCriticalSection(&gcsDsServiceStatus);
    DsServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"NTDS", DsaServiceCtrlHandler, 0);
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
      || (unsigned int)THStateCheckForTraceOverride(v23, v22)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v23, v22)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v23, v22, v24, v25)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
    {
      v28 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v23, v22)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v23, v22, v26, v27)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
      if ( (unsigned int)THStateCheckForTraceOverride(v23, v22)
        || (v29 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3), v30 = 0, v29) )
      {
        v30 = 1;
      }
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50335234,
        4,
        3,
        v30,
        v28,
        55,
        (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
    }
    if ( DsServiceStatusHandle )
    {
      DsServiceStatus.dwServiceType = 16;
      *(_QWORD *)&DsServiceStatus.dwCurrentState = 2;
      *(_QWORD *)&DsServiceStatus.dwWin32ExitCode = 0;
      DsServiceStatus.dwCheckPoint = 0;
      if ( !ghPingSCMThread )
      {
        ThreadId = 0;
        ghPingSCMThread = CreateThread(0, 0, PingSCMThread, 0, 0, &ThreadId);
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
          || (unsigned int)THStateCheckForTraceOverride(v32, v31)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v32, v31)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v31, v33, v34)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
        {
          v37 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v32, v31)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v32, v31, v35, v36)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v32, v31)
            || (v38 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3), v39 = 0, v38) )
          {
            v39 = 1;
          }
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50335260,
            4,
            3,
            v39,
            v37,
            56,
            (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
        }
      }
    }
    else
    {
      v7 = -1073741801;
    }
    LeaveCriticalSection(&gcsDsServiceStatus);
  }
  v151 = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( !WSAStartup(2u, &WSAData) )
  {
    v151 = 1;
    if ( *(_DWORD *)gfADAM || gfRunningAsExe )
      goto LABEL_76;
    if ( RtlGetNtProductType(&ProductType) )
    {
      if ( (unsigned __int8)LsaISafeMode() || ProductType != NtProductLanManNt )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v48, v47)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v48, v47, v49, v50)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v53 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v48, v47)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v48, v47, v51, v52)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v48, v47)
            || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) == 0, v54 = 0, !v17) )
          {
            v54 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50335292,
            2,
            3,
            v54,
            v53,
            57,
            &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
        }
        goto LABEL_302;
      }
      if ( (unsigned __int8)DsWaitForSamService() && (unsigned __int8)SampUsingDsData() )
      {
LABEL_76:
        if ( !gfFirstStartup || !gfRunningInsideLsa )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v73, v72)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v74, v75)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v78 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v73, v72)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v73, v72, v76, v77)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v73, v72)
              || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v79 = 0, !v17) )
            {
              v79 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335354,
              4,
              3,
              v79,
              v78,
              61,
              &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
          gdwStartupPhase1Return = DsStartupPhase1(v5, v154, 0, gfFirstStartup, 0, 0);
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v81, v80)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v81, v80)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v81, v80, v82, v83)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v86 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v81, v80)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v81, v80, v84, v85)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v81, v80)
              || (v87 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3), v88 = 0, v87) )
            {
              v88 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335356,
              4,
              3,
              v88,
              v86,
              62,
              (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
          if ( gdwStartupPhase1Return )
            goto LABEL_302;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v90, v89)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v90, v89)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v90, v89, v91, v92)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v95 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v90, v89)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v90, v89, v93, v94)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v90, v89)
              || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v96 = 0, !v17) )
            {
              v96 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335364,
              4,
              3,
              v96,
              v95,
              63,
              &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
          gdwStartupPhase2Return = DsStartupPhase2((unsigned int)gfFirstStartup, v89);
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v98, v97)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v98, v97)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v98, v97, v99, v100)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v103 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v98, v97)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v98, v97, v101, v102)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v98, v97)
              || (v104 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3), v105 = 0, v104) )
            {
              v105 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335366,
              4,
              3,
              v105,
              v103,
              64,
              (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
          SetEvent(hevDelayedStartupDone);
          goto LABEL_217;
        }
        WaitForSingleObject(hevBaseStartupDone, 0xFFFFFFFF);
        if ( !gdwStartupPhase1Return )
        {
          EnterCriticalSection(&gcsDsServiceStatus);
          if ( DsServiceStatus.dwCurrentState == 2 )
          {
            *(_QWORD *)&DsServiceStatus.dwControlsAccepted = 5;
            DsServiceStatus.dwCurrentState = 4;
            *(_QWORD *)&DsServiceStatus.dwCheckPoint = 0;
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
              || (unsigned int)THStateCheckForTraceOverride(v41, v40)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v41, v40)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v41, v40, v42, v43)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
            {
              v46 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v41, v40)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v41, v40, v44, v45)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
              if ( (unsigned int)THStateCheckForTraceOverride(v41, v40)
                || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v55 = 0, !v17) )
              {
                v55 = 1;
              }
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50335343,
                4,
                3,
                v55,
                v46,
                58,
                &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
            }
          }
          LeaveCriticalSection(&gcsDsServiceStatus);
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v57, v56)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v57, v56, v58, v59)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v62 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v57, v56, v60, v61)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v57, v56)
              || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v63 = 0, !v17) )
            {
              v63 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335348,
              4,
              3,
              v63,
              v62,
              59,
              &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
          WaitForSingleObject(hevDelayedStartupDone, 0xFFFFFFFF);
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v65, v64)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v65, v64, v66, v67)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v70 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v65, v64)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v65, v64, v68, v69)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v65, v64)
              || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v71 = 0, !v17) )
            {
              v71 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335350,
              4,
              3,
              v71,
              v70,
              60,
              (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
LABEL_217:
          if ( !DsServiceStatus.dwWin32ExitCode && !gfRunningAsExe )
          {
            EnterCriticalSection(&gcsDsServiceStatus);
            if ( (!gfFirstStartup || *(_DWORD *)gfADAM) && DsServiceStatus.dwCurrentState == 2 )
            {
              *(_QWORD *)&DsServiceStatus.dwControlsAccepted = 5;
              DsServiceStatus.dwCurrentState = 4;
              *(_QWORD *)&DsServiceStatus.dwCheckPoint = 0;
            }
            v106 = DsServiceStatus.dwCurrentState == 4;
            LeaveCriticalSection(&gcsDsServiceStatus);
            if ( v106 )
            {
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
                || (unsigned int)THStateCheckForTraceOverride(v108, v107)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v108, v107)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v108, v107, v109, v110)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
              {
                v113 = gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride(v108, v107)
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v108, v107, v111, v112)
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
                if ( (unsigned int)THStateCheckForTraceOverride(v108, v107)
                  || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v114 = 0, !v17) )
                {
                  v114 = 1;
                }
                WPP_SF_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  50335401,
                  4,
                  3,
                  v114,
                  v113,
                  65,
                  &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
              }
              WaitForSingleObject(ghPingSCMThread, 0xFFFFFFFF);
              if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
                || (unsigned int)THStateCheckForTraceOverride(v116, v115)
                || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
                || gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v116, v115)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v116, v115, v117, v118)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
              {
                v121 = gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride(v116, v115)
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v116, v115, v119, v120)
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
                if ( (unsigned int)THStateCheckForTraceOverride(v116, v115)
                  || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v122 = 0, !v17) )
                {
                  v122 = 1;
                }
                WPP_SF__ATTRTYP_LOG_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  50335403,
                  4,
                  3,
                  v122,
                  v121,
                  66,
                  (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
              }
              EnterCriticalSection(&gcsDsServiceStatus);
              if ( ghPingSCMThread )
              {
                CloseHandle(ghPingSCMThread);
                ghPingSCMThread = 0;
              }
              LeaveCriticalSection(&gcsDsServiceStatus);
            }
          }
          serviceStateCallback(1);
          v124 = *(_DWORD *)gfADAM;
          if ( !*(_DWORD *)gfADAM && !gfFirstStartup )
          {
            DsTqpDoInsertInTaskQueueDamped(
              v123,
              (unsigned int)StartNTDSDependentServices,
              0,
              0,
              0,
              (__int64)"StartNTDSDependentServices",
              -1,
              0,
              0);
            v124 = *(_DWORD *)gfADAM;
          }
          if ( !gfRunningAsExe && (v124 || gfFirstStartup) )
            DsTqpDoInsertInTaskQueueDamped(v123, (unsigned int)StartADWS, 0, 60, 0, (__int64)"StartADWS", -1, 0, 0);
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v126, v125)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v126, v125)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v126, v125, v127, v128)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v131 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v126, v125)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v126, v125, v129, v130)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v126, v125)
              || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v132 = 0, !v17) )
            {
              v132 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335437,
              4,
              3,
              v132,
              v131,
              67,
              &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
          WaitForSingleObject(hStartDsUninitialize, 0xFFFFFFFF);
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(4)
            || (unsigned int)THStateCheckForTraceOverride(v134, v133)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v134, v133)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v134, v133, v135, v136)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v139 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v134, v133)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v134, v133, v137, v138)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v134, v133)
              || (v17 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v140 = 0, !v17) )
            {
              v140 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50335439,
              4,
              3,
              v140,
              v139,
              68,
              (__int64)&WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
          }
        }
      }
    }
  }
LABEL_302:
  v141 = v155;
  DsUninitialize(0);
  if ( v151 )
    WSACleanup();
  serviceStateCallback(3);
  *v141 = gdwStopControl;
  if ( (unsigned int)THStateCheckForTraceOverride(v143, v142)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v145, v144)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v145, v144, v146, v147)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v150 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v145, v144)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v145, v144, v148, v149)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( (unsigned int)THStateCheckForTraceOverride(v145, v144)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
    {
      v6 = 1;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50335456,
      4,
      3,
      v6,
      v150,
      69,
      &WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids);
  }
  return (unsigned int)gdwShutdownFatalError;
}

```

## disassembly

```asm
0x1800adff0  push    rbx
0x1800adff2  push    rsi
0x1800adff3  push    rdi
0x1800adff4  push    r12
0x1800adff6  push    r13
0x1800adff8  push    r14
0x1800adffa  push    r15
0x1800adffc  sub     rsp, 230h
0x1800ae003  mov     rax, cs:__security_cookie
0x1800ae00a  xor     rax, rsp
0x1800ae00d  mov     [rsp+268h+var_48], rax
0x1800ae015  mov     rax, r9
0x1800ae018  mov     [rsp+268h+var_200], rax
0x1800ae01d  mov     ebx, r8d
0x1800ae020  mov     [rsp+268h+var_208], rdx
0x1800ae025  mov     r12d, ecx
0x1800ae028  mov     [rsp+268h+ThreadId], ecx
0x1800ae02c  mov     [rsp+268h+var_1F8], rax
0x1800ae031  xor     edi, edi
0x1800ae033  mov     r13d, edi
0x1800ae036  mov     [rsp+268h+ProductType], edi
0x1800ae03a  xor     edx, edx; Val
0x1800ae03c  mov     r8d, 198h; Size
0x1800ae042  lea     rcx, [rsp+268h+WSAData]; void *
0x1800ae04a  call    memset_0
0x1800ae04f  call    THStateCheckForTraceOverride
0x1800ae054  lea     r15d, [rdi+3]
0x1800ae058  lea     esi, [rdi+4]
0x1800ae05b  test    eax, eax
0x1800ae05d  jnz     short loc_1800AE0B0
0x1800ae05f  mov     r8d, r15d
0x1800ae062  mov     edx, esi
0x1800ae064  xor     ecx, ecx
0x1800ae066  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae06b  test    eax, eax
0x1800ae06d  jnz     short loc_1800AE0B0
0x1800ae06f  mov     eax, cs:gfTraceToSecondProvider
0x1800ae075  test    eax, eax
0x1800ae077  jz      short loc_1800AE0A5
0x1800ae079  call    THStateCheckForTraceOverride
0x1800ae07e  test    eax, eax
0x1800ae080  jnz     short loc_1800AE0B0
0x1800ae082  call    ThStateCheckIfTraceToSecondProvier
0x1800ae087  test    eax, eax
0x1800ae089  jz      short loc_1800AE0A5
0x1800ae08b  mov     r8d, r15d
0x1800ae08e  mov     edx, esi
0x1800ae090  lea     r14d, [rdi+1]
0x1800ae094  mov     ecx, r14d
0x1800ae097  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae09c  test    eax, eax
0x1800ae09e  jnz     short loc_1800AE0B6
0x1800ae0a0  jmp     loc_1800AE145
0x1800ae0a5  mov     r14d, 1
0x1800ae0ab  jmp     loc_1800AE145
0x1800ae0b0  mov     r14d, 1
0x1800ae0b6  mov     eax, cs:gfTraceToSecondProvider
0x1800ae0bc  test    eax, eax
0x1800ae0be  jz      short loc_1800AE0E8
0x1800ae0c0  call    THStateCheckForTraceOverride
0x1800ae0c5  test    eax, eax
0x1800ae0c7  jnz     short loc_1800AE0E3
0x1800ae0c9  call    ThStateCheckIfTraceToSecondProvier
0x1800ae0ce  test    eax, eax
0x1800ae0d0  jz      short loc_1800AE0E8
0x1800ae0d2  mov     r8d, r15d
0x1800ae0d5  mov     edx, esi
0x1800ae0d7  mov     ecx, r14d
0x1800ae0da  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae0df  test    eax, eax
0x1800ae0e1  jz      short loc_1800AE0E8
0x1800ae0e3  mov     r12d, r14d
0x1800ae0e6  jmp     short loc_1800AE0EB
0x1800ae0e8  mov     r12d, edi
0x1800ae0eb  call    THStateCheckForTraceOverride
0x1800ae0f0  test    eax, eax
0x1800ae0f2  jnz     short loc_1800AE106
0x1800ae0f4  mov     r8d, r15d
0x1800ae0f7  mov     edx, esi
0x1800ae0f9  xor     ecx, ecx
0x1800ae0fb  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae100  test    eax, eax
0x1800ae102  mov     eax, edi
0x1800ae104  jz      short loc_1800AE109
0x1800ae106  mov     eax, r14d
0x1800ae109  lea     rcx, WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids
0x1800ae110  mov     [rsp+268h+var_230], rcx; LPCGUID
0x1800ae115  mov     [rsp+268h+var_238], 36h ; '6'; __int16
0x1800ae11c  mov     dword ptr [rsp+268h+lpThreadId], r12d; int
0x1800ae121  mov     [rsp+268h+dwCreationFlags], eax; int
0x1800ae125  mov     r9d, r15d; int
0x1800ae128  mov     r8d, esi; int
0x1800ae12b  mov     edx, 3000DE9h; int
0x1800ae130  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae137  mov     rcx, [rcx+10h]; int
0x1800ae13b  call    WPP_SF_
0x1800ae140  mov     r12d, [rsp+268h+ThreadId]
0x1800ae145  mov     edx, ebx
0x1800ae147  and     edx, 2
0x1800ae14a  mov     eax, edi
0x1800ae14c  setnz   al
0x1800ae14f  mov     cs:gfADAM, eax
0x1800ae155  mov     ecx, ebx
0x1800ae157  and     ecx, r14d
0x1800ae15a  mov     cs:gfRunningAsExe, ecx
0x1800ae160  test    edx, edx
0x1800ae162  jnz     short loc_1800AE16B
0x1800ae164  test    ecx, ecx
0x1800ae166  mov     eax, r14d
0x1800ae169  jz      short loc_1800AE16D
0x1800ae16b  mov     eax, edi
0x1800ae16d  mov     cs:gfRequireSchemaUpgrade, eax
0x1800ae173  test    ecx, ecx
0x1800ae175  jnz     short loc_1800AE17E
0x1800ae177  test    edx, edx
0x1800ae179  mov     eax, r14d
0x1800ae17c  jz      short loc_1800AE180
0x1800ae17e  mov     eax, edi
0x1800ae180  mov     cs:gfRunningInsideLsa, eax
0x1800ae186  mov     eax, ebx
0x1800ae188  shr     eax, 3
0x1800ae18b  and     eax, r14d
0x1800ae18e  mov     cs:gfDoSamChecks, eax
0x1800ae194  shr     ebx, 2
0x1800ae197  and     ebx, r14d
0x1800ae19a  mov     cs:gfFirstStartup, ebx
0x1800ae1a0  test    ecx, ecx
0x1800ae1a2  jz      short loc_1800AE1EB
0x1800ae1a4  mov     cs:gfDitIsReadOnly, r14d
0x1800ae1ab  mov     cs:gfAllowAdminAccessOnly, r14d
0x1800ae1b2  mov     cs:gfGenerateReferrals, edi
0x1800ae1b8  mov     [rsp+268h+var_218], edi
0x1800ae1bc  test    r13d, r13d
0x1800ae1bf  jns     loc_1800AE484
0x1800ae1c5  mov     eax, r13d
0x1800ae1c8  mov     rcx, [rsp+268h+var_48]
0x1800ae1d0  xor     rcx, rsp; StackCookie
0x1800ae1d3  call    __security_check_cookie
0x1800ae1d8  add     rsp, 230h
0x1800ae1df  pop     r15
0x1800ae1e1  pop     r14
0x1800ae1e3  pop     r13
0x1800ae1e5  pop     r12
0x1800ae1e7  pop     rdi
0x1800ae1e8  pop     rsi
0x1800ae1e9  pop     rbx
0x1800ae1ea  retn
0x1800ae1eb  lea     rcx, gcsDsServiceStatus; lpCriticalSection
0x1800ae1f2  call    cs:__imp_EnterCriticalSection
0x1800ae1f8  nop
0x1800ae1f9  xor     r8d, r8d; lpContext
0x1800ae1fc  lea     rdx, DsaServiceCtrlHandler; lpHandlerProc
0x1800ae203  lea     rcx, aNtds_2; "NTDS"
0x1800ae20a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800ae210  mov     cs:DsServiceStatusHandle, rax
0x1800ae217  mov     ecx, esi
0x1800ae219  call    IncrementWPPPerfCountersForLevel
0x1800ae21e  test    eax, eax
0x1800ae220  jnz     short loc_1800AE274
0x1800ae222  call    THStateCheckForTraceOverride
0x1800ae227  test    eax, eax
0x1800ae229  jnz     short loc_1800AE274
0x1800ae22b  mov     r8d, r15d
0x1800ae22e  mov     edx, esi
0x1800ae230  xor     ecx, ecx
0x1800ae232  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae237  test    eax, eax
0x1800ae239  jnz     short loc_1800AE274
0x1800ae23b  mov     eax, cs:gfTraceToSecondProvider
0x1800ae241  test    eax, eax
0x1800ae243  jz      loc_1800AE30D
0x1800ae249  call    THStateCheckForTraceOverride
0x1800ae24e  test    eax, eax
0x1800ae250  jnz     short loc_1800AE274
0x1800ae252  call    ThStateCheckIfTraceToSecondProvier
0x1800ae257  test    eax, eax
0x1800ae259  jz      loc_1800AE30D
0x1800ae25f  mov     r8d, r15d
0x1800ae262  mov     edx, esi
0x1800ae264  mov     ecx, r14d
0x1800ae267  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae26c  test    eax, eax
0x1800ae26e  jz      loc_1800AE30D
0x1800ae274  mov     eax, cs:gfTraceToSecondProvider
0x1800ae27a  test    eax, eax
0x1800ae27c  jz      short loc_1800AE2A6
0x1800ae27e  call    THStateCheckForTraceOverride
0x1800ae283  test    eax, eax
0x1800ae285  jnz     short loc_1800AE2A1
0x1800ae287  call    ThStateCheckIfTraceToSecondProvier
0x1800ae28c  test    eax, eax
0x1800ae28e  jz      short loc_1800AE2A6
0x1800ae290  mov     r8d, r15d
0x1800ae293  mov     edx, esi
0x1800ae295  mov     ecx, r14d
0x1800ae298  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae29d  test    eax, eax
0x1800ae29f  jz      short loc_1800AE2A6
0x1800ae2a1  mov     ebx, r14d
0x1800ae2a4  jmp     short loc_1800AE2A8
0x1800ae2a6  mov     ebx, edi
0x1800ae2a8  call    THStateCheckForTraceOverride
0x1800ae2ad  test    eax, eax
0x1800ae2af  jnz     short loc_1800AE2C3
0x1800ae2b1  mov     r8d, r15d
0x1800ae2b4  mov     edx, esi
0x1800ae2b6  xor     ecx, ecx
0x1800ae2b8  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae2bd  test    eax, eax
0x1800ae2bf  mov     ecx, edi
0x1800ae2c1  jz      short loc_1800AE2C6
0x1800ae2c3  mov     ecx, r14d
0x1800ae2c6  mov     r8d, 37h ; '7'
0x1800ae2cc  mov     rax, cs:DsServiceStatusHandle
0x1800ae2d3  mov     [rsp+268h+var_228], rax
0x1800ae2d8  lea     rdx, WPP_666bc6dd173a39f543577e7fb362cee5_Traceguids
0x1800ae2df  mov     [rsp+268h+var_230], rdx
0x1800ae2e4  mov     [rsp+268h+var_238], r8w
0x1800ae2ea  mov     dword ptr [rsp+268h+lpThreadId], ebx
0x1800ae2ee  mov     [rsp+268h+dwCreationFlags], ecx
0x1800ae2f2  mov     r9d, r15d
0x1800ae2f5  mov     r8d, esi
0x1800ae2f8  mov     edx, 3000E02h
0x1800ae2fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae304  mov     rcx, [rcx+10h]
0x1800ae308  call    WPP_SF_q
0x1800ae30d  cmp     cs:DsServiceStatusHandle, rdi
0x1800ae314  jnz     short loc_1800AE321
0x1800ae316  mov     r13d, 0C0000017h
0x1800ae31c  jmp     loc_1800AE472
0x1800ae321  mov     cs:DsServiceStatus.dwServiceType, 10h
0x1800ae32b  mov     qword ptr cs:DsServiceStatus.dwCurrentState, 2
0x1800ae336  mov     qword ptr cs:DsServiceStatus.dwWin32ExitCode, rdi
0x1800ae33d  mov     cs:DsServiceStatus.dwCheckPoint, edi
0x1800ae343  cmp     cs:ghPingSCMThread, rdi
0x1800ae34a  jnz     loc_1800AE472
0x1800ae350  mov     [rsp+268h+ThreadId], edi
0x1800ae354  lea     rax, [rsp+268h+ThreadId]
0x1800ae359  mov     [rsp+268h+lpThreadId], rax; lpThreadId
0x1800ae35e  mov     [rsp+268h+dwCreationFlags], edi; dwCreationFlags
0x1800ae362  xor     r9d, r9d; lpParameter
0x1800ae365  lea     r8, PingSCMThread; lpStartAddress
0x1800ae36c  xor     edx, edx; dwStackSize
0x1800ae36e  xor     ecx, ecx; lpThreadAttributes
0x1800ae370  call    cs:__imp_CreateThread
0x1800ae376  mov     cs:ghPingSCMThread, rax
0x1800ae37d  mov     ecx, esi
0x1800ae37f  call    IncrementWPPPerfCountersForLevel
0x1800ae384  test    eax, eax
0x1800ae386  jnz     short loc_1800AE3DA
0x1800ae388  call    THStateCheckForTraceOverride
0x1800ae38d  test    eax, eax
0x1800ae38f  jnz     short loc_1800AE3DA
0x1800ae391  mov     r8d, r15d
0x1800ae394  mov     edx, esi
0x1800ae396  xor     ecx, ecx
0x1800ae398  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae39d  test    eax, eax
0x1800ae39f  jnz     short loc_1800AE3DA
0x1800ae3a1  mov     eax, cs:gfTraceToSecondProvider
0x1800ae3a7  test    eax, eax
0x1800ae3a9  jz      loc_1800AE472
0x1800ae3af  call    THStateCheckForTraceOverride
0x1800ae3b4  test    eax, eax
0x1800ae3b6  jnz     short loc_1800AE3DA
0x1800ae3b8  call    ThStateCheckIfTraceToSecondProvier
0x1800ae3bd  test    eax, eax
0x1800ae3bf  jz      loc_1800AE472
0x1800ae3c5  mov     r8d, r15d
0x1800ae3c8  mov     edx, esi
0x1800ae3ca  mov     ecx, r14d
0x1800ae3cd  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae3d2  test    eax, eax
0x1800ae3d4  jz      loc_1800AE472
0x1800ae3da  mov     eax, cs:gfTraceToSecondProvider
0x1800ae3e0  test    eax, eax
0x1800ae3e2  jz      short loc_1800AE40C
0x1800ae3e4  call    THStateCheckForTraceOverride
0x1800ae3e9  test    eax, eax
0x1800ae3eb  jnz     short loc_1800AE407
0x1800ae3ed  call    ThStateCheckIfTraceToSecondProvier
0x1800ae3f2  test    eax, eax
0x1800ae3f4  jz      short loc_1800AE40C
0x1800ae3f6  mov     r8d, r15d
0x1800ae3f9  mov     edx, esi
0x1800ae3fb  mov     ecx, r14d
0x1800ae3fe  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae403  test    eax, eax
0x1800ae405  jz      short loc_1800AE40C
0x1800ae407  mov     ebx, r14d
0x1800ae40a  jmp     short loc_1800AE40E
0x1800ae40c  mov     ebx, edi
0x1800ae40e  call    THStateCheckForTraceOverride
0x1800ae413  test    eax, eax
0x1800ae415  jnz     short loc_1800AE429
0x1800ae417  mov     r8d, r15d
0x1800ae41a  mov     edx, esi
0x1800ae41c  xor     ecx, ecx
0x1800ae41e  call    CheckWPPLevelFlagsEnabledForProvider
0x1800ae423  test    eax, eax
  ... truncated ...
```
