# SCSchemaUpdateThread

- ea: `0x1800dbca0`
- end: `0x1800dcb6b`
- name: `SCSchemaUpdateThread`
- size: `3787`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x180030b60`
- `0x1800dbca0`
- `0x1800dcce4`
- `0x1800dcec0`
- `0x18017079c`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dbd05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dc99c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dbd05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dc99c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800dbd11`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800dc9a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800dbd11`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800dc9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcb42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dcb42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800dbd6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800dbd6c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800dbd83`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800dc432`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800dbd83`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800dc432`

## pseudocode

```c
DWORD SCSchemaUpdateThread()
{
  HANDLE CurrentThread; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // r14d
  int v4; // ebx
  DWORD v5; // esi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // r9
  BOOL v10; // edi
  bool v11; // zf
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // r9
  BOOL v19; // edi
  int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // r8
  __int64 v30; // r9
  BOOL v31; // edi
  int v32; // eax
  LPOVERLAPPED v33; // rdi
  __int64 *v34; // rcx
  LPOVERLAPPED v35; // rdi
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // r9
  BOOL v42; // edi
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // r9
  BOOL v52; // edi
  int v53; // eax
  int v54; // ecx
  DWORD v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // r9
  __int64 v60; // r8
  __int64 v61; // r9
  BOOL v62; // edi
  int v63; // eax
  int v64; // ecx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // r8
  __int64 v70; // r9
  BOOL v71; // edi
  int v72; // eax
  unsigned int v73; // eax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // r8
  __int64 v81; // r9
  BOOL v82; // edi
  int v83; // eax
  LPOVERLAPPED v84; // rdi
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // r8
  __int64 v90; // r9
  BOOL v91; // edi
  int v92; // eax
  LPOVERLAPPED v93; // rdi
  HANDLE v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // r9
  __int64 v99; // r8
  __int64 v100; // r9
  BOOL v101; // edi
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r9
  __int64 v107; // r8
  __int64 v108; // r9
  BOOL v109; // edi
  DWORD dwMilliseconds[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v111; // [rsp+60h] [rbp-A0h] BYREF
  int v112; // [rsp+68h] [rbp-98h]
  int v113; // [rsp+6Ch] [rbp-94h]
  __int64 v114; // [rsp+70h] [rbp-90h]
  int v115; // [rsp+78h] [rbp-88h]
  int v116; // [rsp+7Ch] [rbp-84h]
  __int64 v117; // [rsp+80h] [rbp-80h]
  __int64 v118; // [rsp+88h] [rbp-78h]
  __int64 v119; // [rsp+90h] [rbp-70h]
  __int64 v120; // [rsp+98h] [rbp-68h]
  __int64 v121; // [rsp+A0h] [rbp-60h]
  int v122; // [rsp+A8h] [rbp-58h]
  __int64 v123; // [rsp+ACh] [rbp-54h]
  int v124; // [rsp+B4h] [rbp-4Ch]
  int *v125; // [rsp+B8h] [rbp-48h]
  __int64 v126; // [rsp+C0h] [rbp-40h] BYREF
  int v127; // [rsp+C8h] [rbp-38h]
  int Internal; // [rsp+CCh] [rbp-34h]
  __int64 v129; // [rsp+D0h] [rbp-30h]
  int v130; // [rsp+D8h] [rbp-28h]
  int v131; // [rsp+DCh] [rbp-24h]
  __int64 v132; // [rsp+E0h] [rbp-20h]
  __int64 v133; // [rsp+E8h] [rbp-18h]
  __int64 v134; // [rsp+F0h] [rbp-10h]
  __int64 v135; // [rsp+F8h] [rbp-8h]
  __int64 v136; // [rsp+100h] [rbp+0h]
  int v137; // [rsp+108h] [rbp+8h]
  __int64 v138; // [rsp+10Ch] [rbp+Ch]
  int v139; // [rsp+114h] [rbp+14h]
  int *v140; // [rsp+118h] [rbp+18h]
  __int64 v141; // [rsp+120h] [rbp+20h] BYREF
  int v142; // [rsp+128h] [rbp+28h]
  int v143; // [rsp+12Ch] [rbp+2Ch]
  __int64 v144; // [rsp+130h] [rbp+30h]
  int v145; // [rsp+138h] [rbp+38h]
  int v146; // [rsp+13Ch] [rbp+3Ch]
  __int64 v147; // [rsp+140h] [rbp+40h]
  __int64 v148; // [rsp+148h] [rbp+48h]
  __int64 v149; // [rsp+150h] [rbp+50h]
  __int64 v150; // [rsp+158h] [rbp+58h]
  __int64 v151; // [rsp+160h] [rbp+60h]
  int v152; // [rsp+168h] [rbp+68h]
  __int64 v153; // [rsp+16Ch] [rbp+6Ch]
  int v154; // [rsp+174h] [rbp+74h]
  int *v155; // [rsp+178h] [rbp+78h]
  HANDLE v156[2]; // [rsp+180h] [rbp+80h] BYREF
  HANDLE Handles[4]; // [rsp+190h] [rbp+90h] BYREF
  int v158; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 *v159; // [rsp+1B8h] [rbp+B8h]
  __int64 v160; // [rsp+1C8h] [rbp+C8h] BYREF
  int v161; // [rsp+1D0h] [rbp+D0h]
  __int64 *v162; // [rsp+1D8h] [rbp+D8h]
  __int64 v163; // [rsp+1E8h] [rbp+E8h] BYREF
  int v164; // [rsp+1F0h] [rbp+F0h]
  __int64 *v165; // [rsp+1F8h] [rbp+F8h]
  __int64 v166; // [rsp+208h] [rbp+108h] BYREF
  int v167; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 *v168; // [rsp+3D8h] [rbp+2D8h]
  __int64 v169; // [rsp+3E8h] [rbp+2E8h] BYREF
  int v170; // [rsp+3F0h] [rbp+2F0h]
  __int64 *v171; // [rsp+3F8h] [rbp+2F8h]
  __int64 v172; // [rsp+408h] [rbp+308h] BYREF
  int v173; // [rsp+410h] [rbp+310h]
  __int64 *v174; // [rsp+418h] [rbp+318h]
  __int64 v175; // [rsp+428h] [rbp+328h] BYREF
  int v176; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 *v177; // [rsp+5F8h] [rbp+4F8h]
  __int64 v178; // [rsp+608h] [rbp+508h] BYREF

  Handles[0] = evSchema;
  Handles[2] = hServDoneEvent;
  v156[1] = hServDoneEvent;
  Handles[1] = evUpdNow;
  v156[0] = evUpdNow;
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  if ( !evSchema )
    return GetLastError();
  if ( !evUpdNow )
    return GetLastError();
  v3 = 0;
  if ( !evUpdRepl )
    return GetLastError();
  v4 = 1;
  while ( !eServiceShutdown )
  {
    SetEvent(evUpdRepl);
    v5 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
    if ( v5 )
    {
      v2 = v5 - 1;
      if ( v5 == 1 )
      {
        if ( !eServiceShutdown )
        {
          if ( (unsigned int)THStateCheckForTraceOverride(v2, v1)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v14, v13, v15, v16)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v19 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v14, v13)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v14, v13, v17, v18)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v14, v13)
              || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v20 = 0, !v11) )
            {
              v20 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51848419,
              4,
              3,
              v20,
              v19,
              72,
              &WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
          }
          v21 = SCUpdateSchema();
          v24 = v21;
          if ( v21 )
          {
            ++v3;
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
              || (unsigned int)THStateCheckForTraceOverride(v26, v25)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v26, v25)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v26, v25, v27, v28)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
            {
              v31 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v26, v25)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier(v26, v25, v29, v30)
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
              if ( (unsigned int)THStateCheckForTraceOverride(v26, v25)
                || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) == 0, v32 = 0, !v11) )
              {
                v32 = 1;
              }
              WPP_SF__ATTRTYP_LOG_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51848436,
                3,
                3,
                v32,
                v31,
                73,
                (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
            }
            if ( v3 > 4 )
              goto LABEL_71;
            v33 = gpDsEventConfig;
            if ( !gpDsEventConfig )
              goto LABEL_70;
            if ( (gpDsEventConfig[12].Internal & 0x8000000000000000uLL) != 0LL
              && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(791, 0)) )
            {
              if ( !(unsigned int)DoLogMsgOverride(3221226679LL) )
                goto LABEL_70;
              v33 = gpDsEventConfig;
            }
            v127 = -1073740617;
            v129 = 0;
            v135 = 0;
            v138 = 0;
            v139 = 0;
            Internal = v33[12].Internal;
            v140 = &v158;
            v159 = &v160;
            v162 = &v163;
            v166 = v3;
            v161 = 5;
            v164 = 5;
            v34 = &v126;
            v165 = &v166;
            v130 = 0;
            v131 = 1;
            v158 = 4;
            v160 = v24;
            v163 = 4;
            v126 = 3;
            v134 = 0;
            v133 = 791;
            v132 = 1;
            v136 = 0;
            v137 = 0;
            goto LABEL_69;
          }
          if ( (unsigned int)THStateCheckForTraceOverride(v23, v22)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v38, v39)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v42 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v37, v36)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v37, v36, v40, v41)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v37, v36)
              || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v43 = 0, !v11) )
            {
              v43 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51848469,
              4,
              3,
              v43,
              v42,
              74,
              (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
          }
          goto LABEL_187;
        }
      }
      else
      {
        if ( v5 == 2 )
        {
          if ( (unsigned int)THStateCheckForTraceOverride(v2, v1)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v96, v95)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v96, v95, v97, v98)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
          {
            v101 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v96, v95)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v96, v95, v99, v100)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( !(unsigned int)THStateCheckForTraceOverride(v96, v95)
              && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
            {
              v4 = 0;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51848495,
              4,
              3,
              v4,
              v101,
              75,
              &WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
          }
          return 0;
        }
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v2, v1)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v2, v1)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v2, v1, v6, v7)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3)) )
        {
          v10 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v2, v1)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v2, v1, v8, v9)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v2, v1)
            || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 3) == 0, v12 = 0, !v11) )
          {
            v12 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51848505,
            2,
            3,
            v12,
            v10,
            76,
            (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
        }
      }
    }
    else
    {
      dwMilliseconds[0] = 0;
      GetTestHookConfigParam((__int64)"DbgTestHookRecalcSchemaDelayInMs", (LPBYTE)dwMilliseconds);
      if ( (unsigned int)THStateCheckForTraceOverride(v45, v44)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v48, v49)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
      {
        v52 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v50, v51)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
        if ( (unsigned int)THStateCheckForTraceOverride(v47, v46)
          || (v53 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3), v54 = 0, v53) )
        {
          v54 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51848313,
          4,
          3,
          v54,
          v52,
          67,
          (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
      }
      v55 = WaitForMultipleObjects(2u, v156, 0, dwMilliseconds[0]);
      v2 = (unsigned int)eServiceShutdown;
      if ( !eServiceShutdown )
      {
        if ( v55 )
        {
          if ( v55 == 258
            && ((unsigned int)THStateCheckForTraceOverride((unsigned int)eServiceShutdown, v1)
             || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
             || gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v57, v56, v58, v59)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3))) )
          {
            v62 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v57, v56)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v57, v56, v60, v61)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v57, v56)
              || (v63 = CheckWPPLevelFlagsEnabledForProvider(0, 4, 3), v64 = 0, v63) )
            {
              v64 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51848339,
              4,
              3,
              v64,
              v62,
              69,
              (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
          }
        }
        else if ( (unsigned int)THStateCheckForTraceOverride((unsigned int)eServiceShutdown, v1)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
               || gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v66, v65, v67, v68)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
        {
          v71 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v66, v65, v69, v70)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v66, v65)
            || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v72 = 0, !v11) )
          {
            v72 = 1;
          }
          WPP_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51848330,
            4,
            3,
            v72,
            v71,
            68,
            &WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
        }
        v73 = SCUpdateSchema();
        v24 = v73;
        if ( v73 )
        {
          ++v3;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
            || (unsigned int)THStateCheckForTraceOverride(v77, v76)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v77, v76)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v77, v76, v78, v79)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
          {
            v82 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v77, v76)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v77, v76, v80, v81)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
            if ( (unsigned int)THStateCheckForTraceOverride(v77, v76)
              || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) == 0, v83 = 0, !v11) )
            {
              v83 = 1;
            }
            WPP_SF__ATTRTYP_LOG_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51848358,
              3,
              3,
              v83,
              v82,
              70,
              (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
          }
          if ( v3 > 4 )
            goto LABEL_71;
          v84 = gpDsEventConfig;
          if ( !gpDsEventConfig )
            goto LABEL_70;
          if ( (gpDsEventConfig[12].Internal & 0x8000000000000000uLL) != 0LL
            && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(791, 0)) )
          {
            if ( (unsigned int)DoLogMsgOverride(3221226679LL) )
            {
              v84 = gpDsEventConfig;
              goto LABEL_170;
            }
LABEL_70:
            if ( (unsigned int)SCSignalSchemaUpdateLazy() )
              goto LABEL_195;
LABEL_71:
            v35 = gpDsEventConfig;
            v3 = 0;
            if ( !gpDsEventConfig )
              goto LABEL_195;
            if ( (gpDsEventConfig[12].Internal & 0x8000000000000000uLL) != 0LL
              && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(791, 0)) )
            {
              if ( !(unsigned int)DoLogMsgOverride(3221226680LL) )
                goto LABEL_195;
              v35 = gpDsEventConfig;
            }
            v112 = -1073740616;
            v114 = 0;
            v120 = 0;
            v123 = 0;
            v124 = 0;
            v113 = v35[12].Internal;
            v125 = &v176;
            v177 = &v178;
            v176 = 4;
            v178 = v24;
            v111 = 1;
            goto LABEL_194;
          }
LABEL_170:
          v142 = -1073740617;
          v144 = 0;
          v150 = 0;
          v153 = 0;
          v154 = 0;
          v143 = v84[12].Internal;
          v155 = &v167;
          v168 = &v169;
          v171 = &v172;
          v175 = v3;
          v170 = 5;
          v173 = 5;
          v34 = &v141;
          v174 = &v175;
          v145 = 0;
          v146 = 1;
          v167 = 4;
          v169 = v24;
          v172 = 4;
          v141 = 3;
          v149 = 0;
          v148 = 791;
          v147 = 1;
          v151 = 0;
          v152 = 0;
LABEL_69:
          DoLogEventAndTrace(v34);
          goto LABEL_70;
        }
        if ( (unsigned int)THStateCheckForTraceOverride(v75, v74)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v86, v85)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v86, v85, v87, v88)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
        {
          v91 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v86, v85)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier(v86, v85, v89, v90)
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
          if ( (unsigned int)THStateCheckForTraceOverride(v86, v85)
            || (v11 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) == 0, v92 = 0, !v11) )
          {
            v92 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51848388,
            4,
            3,
            v92,
            v91,
            71,
            (__int64)&WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
        }
LABEL_187:
        v93 = gpDsEventConfig;
        v3 = 0;
        if ( !gpDsEventConfig )
          goto LABEL_195;
        if ( SHIDWORD(gpDsEventConfig[12].Internal) < 1
          && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(791, 1)) )
        {
          if ( !(unsigned int)DoLogMsgOverride(1073743406) )
            goto LABEL_195;
          v93 = gpDsEventConfig;
        }
        v114 = 1;
        v120 = 0;
        v123 = 0;
        v124 = 0;
        v113 = v93[12].Internal;
        v125 = &v176;
        v111 = 0;
        v112 = 1073743406;
LABEL_194:
        v115 = 0;
        v116 = 1;
        v119 = 0;
        v118 = 791;
        v117 = 1;
        v121 = 0;
        v122 = 0;
        DoLogEventAndTrace(&v111);
LABEL_195:
        v94 = GetCurrentThread();
        SetThreadPriority(v94, -1);
      }
    }
  }
  if ( (unsigned int)THStateCheckForTraceOverride(v2, v1)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v104, v103)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v104, v103, v105, v106)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v109 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v104, v103)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v104, v103, v107, v108)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride(v104, v103)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
    {
      v4 = 0;
    }
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51848517,
      4,
      3,
      v4,
      v109,
      77,
      &WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dbca0  push    rbp
0x1800dbca2  push    rbx
0x1800dbca3  push    rsi
0x1800dbca4  push    rdi
0x1800dbca5  push    r12
0x1800dbca7  push    r13
0x1800dbca9  push    r14
0x1800dbcab  push    r15
0x1800dbcad  lea     rbp, [rsp-728h]
0x1800dbcb5  sub     rsp, 828h
0x1800dbcbc  mov     rax, cs:__security_cookie
0x1800dbcc3  xor     rax, rsp
0x1800dbcc6  mov     [rbp+760h+var_50], rax
0x1800dbccd  mov     rax, cs:evSchema
0x1800dbcd4  mov     rcx, cs:evUpdNow
0x1800dbcdb  mov     [rbp+760h+Handles], rax
0x1800dbce2  mov     rax, cs:hServDoneEvent
0x1800dbce9  mov     [rbp+760h+var_6C0], rax
0x1800dbcf0  mov     [rbp+760h+var_6D8], rax
0x1800dbcf7  mov     [rbp+760h+var_6C8], rcx
0x1800dbcfe  mov     [rbp+760h+var_6E0], rcx
0x1800dbd05  call    cs:__imp_GetCurrentThread
0x1800dbd0b  mov     rcx, rax; hThread
0x1800dbd0e  or      edx, 0FFFFFFFFh; nPriority
0x1800dbd11  call    cs:__imp_SetThreadPriority
0x1800dbd17  xor     r15d, r15d
0x1800dbd1a  cmp     cs:evSchema, r15
0x1800dbd21  jz      loc_1800DCB42
0x1800dbd27  cmp     cs:evUpdNow, r15
0x1800dbd2e  jz      loc_1800DCB42
0x1800dbd34  cmp     cs:evUpdRepl, r15
0x1800dbd3b  mov     r14d, r15d
0x1800dbd3e  jz      loc_1800DCB42
0x1800dbd44  lea     ebx, [r15+1]
0x1800dbd48  lea     r12d, [r15+3]
0x1800dbd4c  lea     r13d, [r15+4]
0x1800dbd50  lea     rsi, WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids
0x1800dbd57  mov     eax, cs:eServiceShutdown
0x1800dbd5d  test    eax, eax
0x1800dbd5f  jnz     loc_1800DCA94
0x1800dbd65  mov     rcx, cs:evUpdRepl; hEvent
0x1800dbd6c  call    cs:__imp_SetEvent
0x1800dbd72  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800dbd76  lea     rdx, [rbp+760h+Handles]; lpHandles
0x1800dbd7d  xor     r8d, r8d; bWaitAll
0x1800dbd80  mov     ecx, r12d; nCount
0x1800dbd83  call    cs:__imp_WaitForMultipleObjects
0x1800dbd89  mov     esi, eax
0x1800dbd8b  mov     ecx, eax
0x1800dbd8d  test    eax, eax
0x1800dbd8f  jz      loc_1800DC30B
0x1800dbd95  sub     ecx, ebx
0x1800dbd97  jz      loc_1800DBE9F
0x1800dbd9d  cmp     ecx, ebx
0x1800dbd9f  jz      loc_1800DC9B3
0x1800dbda5  mov     ecx, 2
0x1800dbdaa  call    IncrementWPPPerfCountersForLevel
0x1800dbdaf  test    eax, eax
0x1800dbdb1  jnz     short loc_1800DBE08
0x1800dbdb3  call    THStateCheckForTraceOverride
0x1800dbdb8  test    eax, eax
0x1800dbdba  jnz     short loc_1800DBE08
0x1800dbdbc  mov     r8d, r12d
0x1800dbdbf  lea     edx, [rax+2]
0x1800dbdc2  xor     ecx, ecx
0x1800dbdc4  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbdc9  test    eax, eax
0x1800dbdcb  jnz     short loc_1800DBE08
0x1800dbdcd  mov     eax, cs:gfTraceToSecondProvider
0x1800dbdd3  test    eax, eax
0x1800dbdd5  jz      loc_1800DBD50
0x1800dbddb  call    THStateCheckForTraceOverride
0x1800dbde0  test    eax, eax
0x1800dbde2  jnz     short loc_1800DBE08
0x1800dbde4  call    ThStateCheckIfTraceToSecondProvier
0x1800dbde9  test    eax, eax
0x1800dbdeb  jz      loc_1800DBD50
0x1800dbdf1  mov     r8d, r12d
0x1800dbdf4  mov     edx, 2
0x1800dbdf9  mov     ecx, ebx
0x1800dbdfb  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbe00  test    eax, eax
0x1800dbe02  jz      loc_1800DBD50
0x1800dbe08  mov     eax, cs:gfTraceToSecondProvider
0x1800dbe0e  test    eax, eax
0x1800dbe10  jz      short loc_1800DBE3B
0x1800dbe12  call    THStateCheckForTraceOverride
0x1800dbe17  test    eax, eax
0x1800dbe19  jnz     short loc_1800DBE37
0x1800dbe1b  call    ThStateCheckIfTraceToSecondProvier
0x1800dbe20  test    eax, eax
0x1800dbe22  jz      short loc_1800DBE3B
0x1800dbe24  mov     r8d, r12d
0x1800dbe27  mov     edx, 2
0x1800dbe2c  mov     ecx, ebx
0x1800dbe2e  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbe33  test    eax, eax
0x1800dbe35  jz      short loc_1800DBE3B
0x1800dbe37  mov     edi, ebx
0x1800dbe39  jmp     short loc_1800DBE3E
0x1800dbe3b  mov     edi, r15d
0x1800dbe3e  call    THStateCheckForTraceOverride
0x1800dbe43  test    eax, eax
0x1800dbe45  jnz     short loc_1800DBE5B
0x1800dbe47  mov     r8d, r12d
0x1800dbe4a  lea     edx, [rax+2]
0x1800dbe4d  xor     ecx, ecx
0x1800dbe4f  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbe54  test    eax, eax
0x1800dbe56  mov     eax, r15d
0x1800dbe59  jz      short loc_1800DBE5D
0x1800dbe5b  mov     eax, ebx
0x1800dbe5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbe64  mov     r9d, r12d
0x1800dbe67  mov     [rsp+860h+var_820], esi
0x1800dbe6b  mov     edx, 3172539h
0x1800dbe70  lea     rsi, WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids
0x1800dbe77  mov     r8d, 2
0x1800dbe7d  mov     [rsp+860h+var_828], rsi
0x1800dbe82  mov     rcx, [rcx+10h]
0x1800dbe86  mov     [rsp+860h+var_830], 4Ch ; 'L'
0x1800dbe8d  mov     [rsp+860h+var_838], edi
0x1800dbe91  mov     dword ptr [rsp+860h+lpData], eax
0x1800dbe95  call    WPP_SF__ATTRTYP_LOG_
0x1800dbe9a  jmp     loc_1800DBD57
0x1800dbe9f  mov     eax, cs:eServiceShutdown
0x1800dbea5  lea     rsi, WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids
0x1800dbeac  test    eax, eax
0x1800dbeae  jnz     loc_1800DBD57
0x1800dbeb4  call    THStateCheckForTraceOverride
0x1800dbeb9  test    eax, eax
0x1800dbebb  jnz     short loc_1800DBF07
0x1800dbebd  mov     r8d, r12d
0x1800dbec0  mov     edx, r13d
0x1800dbec3  xor     ecx, ecx
0x1800dbec5  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbeca  test    eax, eax
0x1800dbecc  jnz     short loc_1800DBF07
0x1800dbece  mov     eax, cs:gfTraceToSecondProvider
0x1800dbed4  test    eax, eax
0x1800dbed6  jz      loc_1800DBF90
0x1800dbedc  call    THStateCheckForTraceOverride
0x1800dbee1  test    eax, eax
0x1800dbee3  jnz     short loc_1800DBF07
0x1800dbee5  call    ThStateCheckIfTraceToSecondProvier
0x1800dbeea  test    eax, eax
0x1800dbeec  jz      loc_1800DBF90
0x1800dbef2  mov     r8d, r12d
0x1800dbef5  mov     edx, r13d
0x1800dbef8  mov     ecx, ebx
0x1800dbefa  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbeff  test    eax, eax
0x1800dbf01  jz      loc_1800DBF90
0x1800dbf07  mov     eax, cs:gfTraceToSecondProvider
0x1800dbf0d  test    eax, eax
0x1800dbf0f  jz      short loc_1800DBF38
0x1800dbf11  call    THStateCheckForTraceOverride
0x1800dbf16  test    eax, eax
0x1800dbf18  jnz     short loc_1800DBF34
0x1800dbf1a  call    ThStateCheckIfTraceToSecondProvier
0x1800dbf1f  test    eax, eax
0x1800dbf21  jz      short loc_1800DBF38
0x1800dbf23  mov     r8d, r12d
0x1800dbf26  mov     edx, r13d
0x1800dbf29  mov     ecx, ebx
0x1800dbf2b  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbf30  test    eax, eax
0x1800dbf32  jz      short loc_1800DBF38
0x1800dbf34  mov     edi, ebx
0x1800dbf36  jmp     short loc_1800DBF3B
0x1800dbf38  mov     edi, r15d
0x1800dbf3b  call    THStateCheckForTraceOverride
0x1800dbf40  test    eax, eax
0x1800dbf42  jnz     short loc_1800DBF58
0x1800dbf44  mov     r8d, r12d
0x1800dbf47  mov     edx, r13d
0x1800dbf4a  xor     ecx, ecx
0x1800dbf4c  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbf51  test    eax, eax
0x1800dbf53  mov     eax, r15d
0x1800dbf56  jz      short loc_1800DBF5A
0x1800dbf58  mov     eax, ebx
0x1800dbf5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dbf61  lea     rdx, WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids
0x1800dbf68  mov     [rsp+860h+var_828], rdx; LPCGUID
0x1800dbf6d  mov     r9d, r12d; int
0x1800dbf70  mov     [rsp+860h+var_830], 48h ; 'H'; __int16
0x1800dbf77  mov     r8d, r13d; int
0x1800dbf7a  mov     [rsp+860h+var_838], edi; int
0x1800dbf7e  mov     edx, 31724E3h; int
0x1800dbf83  mov     rcx, [rcx+10h]; int
0x1800dbf87  mov     dword ptr [rsp+860h+lpData], eax; int
0x1800dbf8b  call    WPP_SF_
0x1800dbf90  call    SCUpdateSchema
0x1800dbf95  mov     esi, eax
0x1800dbf97  test    eax, eax
0x1800dbf99  jz      loc_1800DC243
0x1800dbf9f  inc     r14d
0x1800dbfa2  mov     ecx, r12d
0x1800dbfa5  call    IncrementWPPPerfCountersForLevel
0x1800dbfaa  test    eax, eax
0x1800dbfac  jnz     short loc_1800DC001
0x1800dbfae  call    THStateCheckForTraceOverride
0x1800dbfb3  test    eax, eax
0x1800dbfb5  jnz     short loc_1800DC001
0x1800dbfb7  mov     r8d, r12d
0x1800dbfba  mov     edx, r12d
0x1800dbfbd  xor     ecx, ecx
0x1800dbfbf  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbfc4  test    eax, eax
0x1800dbfc6  jnz     short loc_1800DC001
0x1800dbfc8  mov     eax, cs:gfTraceToSecondProvider
0x1800dbfce  test    eax, eax
0x1800dbfd0  jz      loc_1800DC093
0x1800dbfd6  call    THStateCheckForTraceOverride
0x1800dbfdb  test    eax, eax
0x1800dbfdd  jnz     short loc_1800DC001
0x1800dbfdf  call    ThStateCheckIfTraceToSecondProvier
0x1800dbfe4  test    eax, eax
0x1800dbfe6  jz      loc_1800DC093
0x1800dbfec  mov     r8d, r12d
0x1800dbfef  mov     edx, r12d
0x1800dbff2  mov     ecx, ebx
0x1800dbff4  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dbff9  test    eax, eax
0x1800dbffb  jz      loc_1800DC093
0x1800dc001  mov     eax, cs:gfTraceToSecondProvider
0x1800dc007  test    eax, eax
0x1800dc009  jz      short loc_1800DC032
0x1800dc00b  call    THStateCheckForTraceOverride
0x1800dc010  test    eax, eax
0x1800dc012  jnz     short loc_1800DC02E
0x1800dc014  call    ThStateCheckIfTraceToSecondProvier
0x1800dc019  test    eax, eax
0x1800dc01b  jz      short loc_1800DC032
0x1800dc01d  mov     r8d, r12d
0x1800dc020  mov     edx, r12d
0x1800dc023  mov     ecx, ebx
0x1800dc025  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dc02a  test    eax, eax
0x1800dc02c  jz      short loc_1800DC032
0x1800dc02e  mov     edi, ebx
0x1800dc030  jmp     short loc_1800DC035
0x1800dc032  mov     edi, r15d
0x1800dc035  call    THStateCheckForTraceOverride
0x1800dc03a  test    eax, eax
0x1800dc03c  jnz     short loc_1800DC052
0x1800dc03e  mov     r8d, r12d
0x1800dc041  mov     edx, r12d
0x1800dc044  xor     ecx, ecx
0x1800dc046  call    CheckWPPLevelFlagsEnabledForProvider
0x1800dc04b  test    eax, eax
0x1800dc04d  mov     eax, r15d
0x1800dc050  jz      short loc_1800DC054
0x1800dc052  mov     eax, ebx
0x1800dc054  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc05b  lea     rdx, WPP_f3135c97770f3f7499c4450b7dd77e3d_Traceguids
0x1800dc062  mov     [rsp+860h+var_818], esi
0x1800dc066  mov     r9d, r12d
0x1800dc069  mov     [rsp+860h+var_820], r14d
0x1800dc06e  mov     r8d, r12d
0x1800dc071  mov     [rsp+860h+var_828], rdx
0x1800dc076  mov     edx, 31724F4h
0x1800dc07b  mov     rcx, [rcx+10h]
0x1800dc07f  mov     [rsp+860h+var_830], 49h ; 'I'
0x1800dc086  mov     [rsp+860h+var_838], edi
0x1800dc08a  mov     dword ptr [rsp+860h+lpData], eax
0x1800dc08e  call    WPP_SF__ATTRTYP_LOG_d
0x1800dc093  cmp     r14d, r13d
0x1800dc096  ja      loc_1800DC1A3
0x1800dc09c  mov     rdi, cs:gpDsEventConfig
0x1800dc0a3  test    rdi, rdi
0x1800dc0a6  jz      loc_1800DC196
0x1800dc0ac  cmp     [rdi+184h], r15d
0x1800dc0b3  jge     short loc_1800DC0E4
0x1800dc0b5  cmp     [rdi+4], r15d
0x1800dc0b9  jz      short loc_1800DC0CB
0x1800dc0bb  xor     edx, edx
0x1800dc0bd  mov     ecx, 317h
0x1800dc0c2  call    DoLogOverride
0x1800dc0c7  test    eax, eax
0x1800dc0c9  jnz     short loc_1800DC0E4
0x1800dc0cb  mov     ecx, 0C00004B7h
0x1800dc0d0  call    DoLogMsgOverride
0x1800dc0d5  test    eax, eax
0x1800dc0d7  jz      loc_1800DC196
0x1800dc0dd  mov     rdi, cs:gpDsEventConfig
0x1800dc0e4  xor     eax, eax
0x1800dc0e6  mov     [rbp+760h+var_798], 0C00004B7h
0x1800dc0ed  mov     [rbp+760h+var_790], rax
0x1800dc0f1  mov     ecx, 5
0x1800dc0f6  mov     [rbp+760h+var_768], rax
0x1800dc0fa  mov     [rbp+760h+var_754], rax
0x1800dc0fe  mov     [rbp+760h+var_74C], eax
0x1800dc101  mov     eax, [rdi+180h]
0x1800dc107  mov     [rbp+760h+var_794], eax
0x1800dc10a  lea     rax, [rbp+760h+var_6B0]
0x1800dc111  mov     [rbp+760h+var_748], rax
0x1800dc115  lea     rax, [rbp+760h+var_698]
0x1800dc11c  mov     [rbp+760h+var_6A8], rax
  ... truncated ...
```
