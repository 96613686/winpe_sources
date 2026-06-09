# UpdateNCValuesHelpMultipleThreads

- ea: `0x1802ec838`
- end: `0x1802ee3fc`
- name: `UpdateNCValuesHelpMultipleThreads`
- size: `7108`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1802eb220`

## callees

- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x180030af8`
- `0x180030b60`
- `0x1800488c4`
- `0x18007cf4c`
- `0x1801737f0`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x180181db0`
- `0x1801c4a34`
- `0x1802523cc`
- `0x180255a38`
- `0x1802e6ae0`
- `0x1802e6b18`
- `0x1802e93fc`
- `0x1802e968c`
- `0x1802ec838`
- `0x1802f7fd8`
- `0x1802f8204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1802ecd2a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1802ecd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ec964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ecb68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ecbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ecd3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ec964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ecb68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ecbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802ecd3b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1802ecb47`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1802ecb9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1802ecb47`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1802ecb9c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802ecb8c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802ecbde`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802ecb8c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1802ecbde`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802ecff5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802ed624`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802ed63b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802edc70`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802eddda`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18046e6ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802ecff5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802ed624`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802ed63b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802edc70`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802eddda`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18046e6ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ee1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ee203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ee21a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046eb57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046eb6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046eb83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ee1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ee203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802ee21a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046eb57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046eb6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18046eb83`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1802edef4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18046e80c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1802edef4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18046e80c`

## pseudocode

```c
__int64 __fastcall UpdateNCValuesHelpMultipleThreads(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        _DWORD *a7,
        __int64 a8,
        __int64 a9,
        _DWORD *a10,
        __int64 a11,
        __int64 *a12)
{
  __int64 v12; // r15
  unsigned int v15; // eax
  unsigned int v16; // ebx
  DWORD LastError; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  BOOL v24; // ebx
  bool v25; // zf
  int v26; // eax
  __int64 v27; // rbx
  unsigned int v28; // r14d
  HANDLE EventA; // rax
  __int64 v30; // rbx
  DWORD v31; // eax
  __int64 v32; // rdi
  HANDLE v33; // rax
  __int64 v34; // r14
  DWORD v35; // eax
  unsigned int v36; // ecx
  unsigned int v37; // edx
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // ebx
  unsigned int v41; // edi
  __int64 v42; // r12
  HANDLE *v43; // r14
  __int64 v44; // rax
  DWORD v45; // eax
  unsigned int v46; // ebx
  unsigned int v47; // eax
  unsigned int v48; // r15d
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // r15
  __int64 v54; // rax
  const __int64 *v55; // r14
  __int64 v56; // r8
  __int64 v57; // r9
  BOOL v58; // edi
  BOOL v59; // ecx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // r8
  __int64 v65; // r9
  BOOL v66; // edi
  int v67; // eax
  int v68; // edx
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r12
  __int64 v73; // rdi
  __int64 v74; // r14
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  __int64 v79; // r8
  __int64 v80; // r9
  BOOL v81; // ebx
  BOOL v82; // ecx
  __int64 v83; // rax
  int v84; // edi
  __int64 v85; // rbx
  __int64 v86; // rax
  int v87; // r13d
  unsigned int v88; // ebx
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // r8
  __int64 v94; // r9
  BOOL v95; // ebx
  int v96; // eax
  unsigned int v97; // eax
  unsigned int i; // edx
  __int64 v99; // rbx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // r8
  __int64 v105; // r9
  BOOL v106; // edi
  int v107; // eax
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // r8
  __int64 v113; // r9
  BOOL v114; // edi
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 v120; // r8
  __int64 v121; // r9
  BOOL v122; // ebx
  __int64 v123; // r8
  __int64 v124; // r9
  __int64 v125; // r8
  __int64 v126; // r9
  BOOL v127; // ebx
  int v128; // eax
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // r8
  __int64 v132; // r9
  BOOL v133; // ebx
  int v134; // eax
  int v135; // eax
  __int64 v136; // r8
  __int64 v137; // r9
  __int64 v138; // r8
  __int64 v139; // r9
  BOOL v140; // ebx
  int v141; // eax
  __int64 v142; // rdx
  __int64 v143; // rcx
  __int64 v144; // r8
  __int64 v145; // r9
  __int64 v146; // r8
  __int64 v147; // r9
  BOOL v148; // ebx
  int v149; // eax
  __int64 v150; // rbx
  __int64 v151; // rbx
  __int64 v152; // r8
  __int64 v153; // r9
  __int64 v154; // r8
  __int64 v155; // r9
  BOOL v156; // ebx
  int v157; // eax
  DWORD v158; // r14d
  __int64 v159; // rbx
  unsigned int v160; // r15d
  HANDLE *j; // rdi
  __int64 v162; // r8
  __int64 v163; // r9
  __int64 v164; // r8
  __int64 v165; // r9
  BOOL v166; // edi
  BOOL v167; // ecx
  __int64 v168; // rdx
  __int64 v169; // rcx
  __int64 v170; // r8
  __int64 v171; // r9
  __int64 v172; // r8
  __int64 v173; // r9
  BOOL v174; // ebx
  int v175; // eax
  __int64 v176; // rdx
  DWORD v177; // edi
  __int64 v178; // rcx
  __int64 v179; // r8
  __int64 v180; // r9
  __int64 v181; // r8
  __int64 v182; // r9
  BOOL v183; // ebx
  int v184; // eax
  __int64 v185; // rdx
  __int64 v186; // rcx
  __int64 v187; // r8
  __int64 v188; // r9
  __int64 v189; // r8
  __int64 v190; // r9
  BOOL v191; // ebx
  int v192; // eax
  __int64 v193; // rdx
  __int64 v194; // rcx
  __int64 v195; // r8
  __int64 v196; // r9
  __int64 v197; // r8
  __int64 v198; // r9
  BOOL v199; // ebx
  int v200; // eax
  unsigned int v201; // r13d
  unsigned int v202; // edi
  __int64 v203; // r15
  unsigned int v204; // eax
  __int64 v205; // rbx
  __int64 v206; // r14
  HANDLE v207; // rcx
  LPOVERLAPPED v208; // rbx
  unsigned int v209; // ebx
  unsigned int v211; // [rsp+60h] [rbp-398h] BYREF
  unsigned int v212; // [rsp+64h] [rbp-394h]
  unsigned int v213; // [rsp+68h] [rbp-390h]
  int v214; // [rsp+6Ch] [rbp-38Ch]
  unsigned int v215; // [rsp+70h] [rbp-388h]
  __int64 v216; // [rsp+78h] [rbp-380h]
  HANDLE *lpHandles; // [rsp+80h] [rbp-378h]
  unsigned int v218; // [rsp+88h] [rbp-370h]
  int v219; // [rsp+8Ch] [rbp-36Ch]
  int v220; // [rsp+90h] [rbp-368h]
  int v221; // [rsp+94h] [rbp-364h]
  unsigned int v222; // [rsp+98h] [rbp-360h]
  int v223; // [rsp+9Ch] [rbp-35Ch]
  __int64 v224; // [rsp+A0h] [rbp-358h]
  DWORD nCount; // [rsp+A8h] [rbp-350h]
  unsigned int v226; // [rsp+B0h] [rbp-348h]
  __int64 v227; // [rsp+B8h] [rbp-340h]
  __int128 v228; // [rsp+C0h] [rbp-338h] BYREF
  HANDLE *v229; // [rsp+D0h] [rbp-328h]
  __int64 v230; // [rsp+D8h] [rbp-320h]
  __int64 v231; // [rsp+E0h] [rbp-318h]
  int v232; // [rsp+E8h] [rbp-310h]
  int v233; // [rsp+ECh] [rbp-30Ch]
  int v234; // [rsp+F0h] [rbp-308h]
  int v235; // [rsp+F4h] [rbp-304h]
  __int64 *v236; // [rsp+F8h] [rbp-300h]
  _DWORD *v237; // [rsp+100h] [rbp-2F8h]
  __int64 v238; // [rsp+108h] [rbp-2F0h]
  __int64 v239; // [rsp+110h] [rbp-2E8h]
  __int64 v240; // [rsp+120h] [rbp-2D8h]
  __int64 v241; // [rsp+130h] [rbp-2C8h] BYREF
  int v242; // [rsp+138h] [rbp-2C0h]
  DWORD Offset; // [rsp+13Ch] [rbp-2BCh]
  __int64 v244; // [rsp+140h] [rbp-2B8h]
  int v245; // [rsp+148h] [rbp-2B0h]
  int v246; // [rsp+14Ch] [rbp-2ACh]
  __int64 v247; // [rsp+150h] [rbp-2A8h]
  __int64 v248; // [rsp+158h] [rbp-2A0h]
  __int64 v249; // [rsp+160h] [rbp-298h]
  __int64 v250; // [rsp+168h] [rbp-290h]
  __int64 v251; // [rsp+170h] [rbp-288h]
  int v252; // [rsp+178h] [rbp-280h]
  __int64 v253; // [rsp+17Ch] [rbp-27Ch]
  int v254; // [rsp+184h] [rbp-274h]
  int *v255; // [rsp+188h] [rbp-270h]
  int v256; // [rsp+190h] [rbp-268h] BYREF
  __int64 v257; // [rsp+198h] [rbp-260h]
  int v258; // [rsp+1B0h] [rbp-248h]
  __int64 *v259; // [rsp+1B8h] [rbp-240h]
  __int64 v260; // [rsp+1C8h] [rbp-230h] BYREF
  int v261; // [rsp+1D0h] [rbp-228h]
  __int64 *v262; // [rsp+1D8h] [rbp-220h]
  __int64 v263; // [rsp+1E8h] [rbp-210h] BYREF
  int v264; // [rsp+1F0h] [rbp-208h]
  __int64 *v265; // [rsp+1F8h] [rbp-200h]
  __int64 v266; // [rsp+208h] [rbp-1F0h] BYREF

  v12 = a4;
  v215 = a4;
  v211 = a3;
  v231 = a2;
  v230 = a1;
  v226 = a4;
  v239 = a5;
  v237 = a10;
  v227 = a11;
  v240 = a11;
  v236 = a12;
  lpHandles = 0;
  v216 = 0;
  v212 = 0;
  v223 = 0;
  v221 = 0;
  v218 = *(_DWORD *)(a5 + 148);
  v224 = *(_QWORD *)(a5 + 152);
  v228 = 0;
  v214 = 0;
  v220 = 0;
  *a12 = 0;
  if ( a3 == -1 )
  {
    BeginDraTransactionEx(0, 0);
    v15 = DBFindDSName(*(_QWORD *)(a1 + 5576), a2);
    if ( v15 )
    {
      v16 = v15;
      LastError = GetLastError();
      DraExcept(LastError, v16, 19271002, 1);
    }
    else
    {
      v211 = *(_DWORD *)(*(_QWORD *)(a1 + 5576) + 24LL);
    }
    EndDraTransaction(0);
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
    || (unsigned int)THStateCheckForTraceOverride(v19, v18)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v19, v18)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v19, v18, v20, v21)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
  {
    v24 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v19, v18)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v19, v18, v22, v23)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
    if ( (unsigned int)THStateCheckForTraceOverride(v19, v18)
      || (v25 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5) == 0, v26 = 0, !v25) )
    {
      v26 = 1;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19271013,
      5,
      5,
      v26,
      v24,
      109,
      (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
  }
  v238 = v12;
  lpHandles = (HANDLE *)THAlloc_(a1, v12, 8, 1, 0, 19271016);
  nCount = v12 + 1;
  v229 = (HANDLE *)THAlloc_(a1, (int)v12 + 1, 8, 1, 0, 19271020);
  *v229 = hServDoneEvent;
  v216 = THAlloc_(a1, v12, 168, 1, 0, 19271024);
  v213 = 0;
  LODWORD(v27) = 0;
  v28 = 0;
  while ( (unsigned int)v27 < (unsigned int)v12 )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    v12 = 168LL * (unsigned int)v27;
    v30 = v216;
    *(_QWORD *)(v12 + v216 + 112) = EventA;
    if ( !EventA )
    {
      v31 = GetLastError();
      DraExcept(v31, 0, 19271030, 1);
    }
    v32 = 168LL * v28;
    ResetEvent(*(HANDLE *)(v32 + v30 + 112));
    v33 = CreateEventA(0, 0, 0, 0);
    v27 = v28 + 1;
    v229[v27] = v33;
    v34 = v216;
    *(_QWORD *)(v32 + v216 + 120) = v33;
    if ( !v33 )
    {
      v35 = GetLastError();
      DraExcept(v35, 0, 19271036, 1);
    }
    ResetEvent(*(HANDLE *)(v32 + v34 + 120));
    *(_DWORD *)(v12 + v34 + 136) = 0;
    *(_DWORD *)(v32 + v34 + 132) = 1;
    *(_QWORD *)(v32 + v34 + 16) = a9;
    *(_DWORD *)(v32 + v34) = v211;
    *(_QWORD *)(v32 + v34 + 8) = v231;
    *(_QWORD *)(v32 + v34 + 24) = a8;
    *(_QWORD *)(v32 + v34 + 48) = a6;
    v36 = (a7[2] << 6) ^ (*(_DWORD *)(v32 + v34 + 56) ^ (a7[2] << 6)) & 0xFFFFFFBF;
    *(_DWORD *)(v32 + v34 + 56) = v36;
    v37 = (32 * *a7) ^ (v36 ^ (32 * *a7)) & 0xFFFFFFDF;
    *(_DWORD *)(v32 + v34 + 56) = v37;
    *(_DWORD *)(v32 + v34 + 56) = (16 * a7[3]) ^ ((16 * a7[3]) ^ v37) & 0xFFFFFFEF;
    v38 = v230;
    *(_OWORD *)(v32 + v34 + 64) = *(_OWORD *)(v230 + 5944);
    *(_QWORD *)(v32 + v34 + 80) = *(_QWORD *)(v38 + 5832);
    *(_DWORD *)(v32 + v34 + 100) = 0;
    v39 = *(_DWORD *)(v227 + 56);
    *(_DWORD *)(v32 + v34 + 152) = v39;
    *(_QWORD *)(v32 + v34 + 160) = THAlloc_(v38, v39, 28, 1, 0, 19271060);
    InitLargeAttributes(v12 + v34 + 144);
    v213 = v27;
    v28 = v27;
    LODWORD(v12) = v215;
  }
  v213 = 0;
  v40 = 0;
  v41 = 0;
  v42 = v216;
  v43 = lpHandles;
  while ( v40 < (unsigned int)v12 )
  {
    v44 = _o__beginthreadex(0, 0, UpdateNCValuesMultipleThreadsHelper, v42 + 168LL * v40, 0, 0);
    v43[v41] = (HANDLE)v44;
    if ( !v44 )
    {
      v45 = GetLastError();
      DraExcept(v45, 0, 19271075, 1);
    }
    v213 = ++v40;
    v41 = v40;
  }
  v211 = 0;
  v46 = 0;
  v213 = 0;
  v47 = 0;
  v48 = v212;
  while ( v47 < v215 && v211 < v218 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
      || (unsigned int)THStateCheckForTraceOverride(v50, v49)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v50, v49)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v50, v49, v51, v52)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
    {
      v53 = 112LL * v211;
      v54 = *(_QWORD *)(v53 + v224);
      v55 = (const __int64 *)(v54 + 8);
      if ( !v54 )
        v55 = &gNullGuid;
      v58 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v50, v49)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v50, v49, v56, v57)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
      v59 = (unsigned int)THStateCheckForTraceOverride(v50, v49)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5);
      WPP_SF__DS_NAME__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v59,
        v58,
        110,
        &WPP_86babf8413563011cdbb63299f85e207_Traceguids,
        *(_QWORD *)(v53 + v224),
        (__int64)v55,
        v46);
      v48 = v212;
    }
    if ( (unsigned int)AssignValueWorkItem((unsigned int)v42 + 168 * v46, v218, v224, (unsigned int)&v211, v48 == 0) )
    {
      v212 = ++v48;
      v219 = v48;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
        || (unsigned int)THStateCheckForTraceOverride(v61, v60)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v61, v60, v62, v63)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
      {
        v66 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v61, v60)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v61, v60, v64, v65)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
        v67 = THStateCheckForTraceOverride(v61, v60);
        v68 = 5;
        if ( v67 || (v69 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
          v69 = 1;
        WPP_SF__ATTRTYP_LOG_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19271095,
          v68,
          v68,
          v69,
          v66,
          111,
          (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
      }
      SetEvent(*(HANDLE *)(v42 + 168LL * v46 + 112));
    }
    v213 = ++v46;
    v47 = v46;
  }
  do
  {
    v212 = WaitForThreads(v229, nCount);
    if ( v212 )
      break;
    v72 = v213;
    v73 = v216;
    v74 = v216 + 168LL * v213;
    v70 = *(unsigned int *)(v74 + 88);
    v212 = v70;
    if ( (_DWORD)v70 )
    {
      if ( (_DWORD)v70 != 8206 && (_DWORD)v70 != 8438 && (_DWORD)v70 != 8527 || v214 )
      {
        v71 = *(_QWORD *)(v74 + 40) + 112LL * *(unsigned int *)(v74 + 92);
        *v236 = v71;
        v223 = 1;
        v233 = 1;
        goto LABEL_109;
      }
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
        || (unsigned int)THStateCheckForTraceOverride(v76, v75)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v76, v75)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v76, v75, v77, v78)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
      {
        v81 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v76, v75)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier(v76, v75, v79, v80)
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
        v82 = (unsigned int)THStateCheckForTraceOverride(v76, v75)
           || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5);
        WPP_SF__ATTRTYP_LOG_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19271129,
          5,
          5,
          v82,
          v81,
          112,
          (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
      }
      v83 = *(unsigned int *)(v74 + 96);
      v84 = *(_DWORD *)(v74 + 32) - v83;
      v85 = *(_QWORD *)(v74 + 40) + 112 * v83;
      v86 = THAlloc_(v230, 1, 24, 1, 0, 19270741);
      v71 = v86;
      *(_QWORD *)(v86 + 16) = 0;
      *(_QWORD *)v86 = v85;
      *(_DWORD *)(v86 + 8) = v84;
      if ( (_QWORD)v228 )
      {
        *(_QWORD *)(*((_QWORD *)&v228 + 1) + 16LL) = v86;
        *((_QWORD *)&v228 + 1) = v86;
      }
      else
      {
        *((_QWORD *)&v228 + 1) = v86;
        *(_QWORD *)&v228 = v86;
      }
      v232 = ++v220;
      v70 = 0;
      v73 = v216;
    }
    else
    {
      v221 += *(_DWORD *)(v74 + 100);
      v234 = v221;
      *v237 = 2;
    }
    v212 = v70;
LABEL_109:
    if ( !(_DWORD)v70 )
    {
      v87 = v214;
      if ( !v214 )
      {
        v88 = v218;
        if ( v211 >= v218 )
        {
          v219 = --v48;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
            || (unsigned int)THStateCheckForTraceOverride(v71, v70)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v129, v130)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
          {
            v133 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v131, v132)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
            if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
              || (v134 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
            {
              v134 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19271189,
              5,
              5,
              v134,
              v133,
              117,
              (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
          }
        }
        else
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
            || (unsigned int)THStateCheckForTraceOverride(v90, v89)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v90, v89)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v90, v89, v91, v92)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
          {
            v95 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v90, v89)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier(v90, v89, v93, v94)
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
            if ( (unsigned int)THStateCheckForTraceOverride(v90, v89)
              || (v96 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
            {
              v96 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19271159,
              5,
              5,
              v96,
              v95,
              113,
              (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
            v88 = v218;
          }
          if ( (unsigned int)AssignValueWorkItem(v74, v88, v224, (unsigned int)&v211, v48 <= 1) )
          {
            if ( v211 < v88 )
            {
              v97 = v215;
              if ( v48 < v215 )
              {
                v222 = 0;
                for ( i = 0; ; ++i )
                {
                  v222 = i;
                  if ( i >= v97 )
                    break;
                  v99 = v73 + 168LL * i;
                  if ( *(_DWORD *)(v99 + 128) == 1 )
                  {
                    *(_DWORD *)(v99 + 132) = 1;
                    *(_DWORD *)(v99 + 128) = 0;
                    goto LABEL_138;
                  }
                  v97 = v215;
                }
                v99 = 0;
LABEL_138:
                if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
                  || (unsigned int)THStateCheckForTraceOverride(v101, v100)
                  || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
                  || gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v101, v100)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier(v101, v100, v102, v103)
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
                {
                  v106 = gfTraceToSecondProvider
                      && ((unsigned int)THStateCheckForTraceOverride(v101, v100)
                       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v101, v100, v104, v105)
                       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
                  if ( (unsigned int)THStateCheckForTraceOverride(v101, v100)
                    || (v107 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
                  {
                    v107 = 1;
                  }
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    19271167,
                    5,
                    5,
                    v107,
                    v106,
                    114,
                    (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
                }
                if ( v99 && (unsigned int)AssignValueWorkItem(v99, v218, v224, (unsigned int)&v211, 0) )
                {
                  v219 = ++v48;
                  if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
                    || (unsigned int)THStateCheckForTraceOverride(v109, v108)
                    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
                    || gfTraceToSecondProvider
                    && ((unsigned int)THStateCheckForTraceOverride(v109, v108)
                     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v109, v108, v110, v111)
                     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
                  {
                    v114 = gfTraceToSecondProvider
                        && ((unsigned int)THStateCheckForTraceOverride(v109, v108)
                         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v109, v108, v112, v113)
                         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
                    if ( (unsigned int)THStateCheckForTraceOverride(v109, v108)
                      || (v115 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
                    {
                      v115 = 1;
                    }
                    WPP_SF__ATTRTYP_LOG_(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      19271170,
                      5,
                      5,
                      v115,
                      v114,
                      115,
                      (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
                  }
                  SetEvent(*(HANDLE *)(v99 + 112));
                }
              }
            }
            SetEvent(*(HANDLE *)(168 * v72 + v216 + 112));
            v87 = v214;
          }
          else
          {
            v219 = --v48;
            if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
              || (unsigned int)THStateCheckForTraceOverride(v71, v70)
              || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
              || gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v123, v124)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
            {
              v127 = gfTraceToSecondProvider
                  && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                   || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v125, v126)
                   && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
              if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
                || (v128 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
              {
                v128 = 1;
              }
              WPP_SF__ATTRTYP_LOG_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19271181,
                5,
                5,
                v128,
                v127,
                116,
                (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
            }
            v87 = v214;
          }
        }
      }
      if ( !v48 )
      {
        if ( v87 )
          goto LABEL_249;
        if ( v220 )
        {
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
            || (unsigned int)THStateCheckForTraceOverride(v117, v116)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v117, v116)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v117, v116, v118, v119)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
          {
            v122 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v117, v116)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v117, v116, v120, v121)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
            if ( (unsigned int)THStateCheckForTraceOverride(v117, v116)
              || (v135 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
            {
              v135 = 1;
            }
            WPP_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19271195,
              5,
              5,
              v135,
              v122,
              118,
              &WPP_86babf8413563011cdbb63299f85e207_Traceguids);
          }
          v87 = 1;
          v214 = 1;
          v235 = 1;
          v48 = 1;
          v219 = 1;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
            || (unsigned int)THStateCheckForTraceOverride(v71, v70)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v136, v137)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
          {
            v140 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v138, v139)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
            if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
              || (v141 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
            {
              v141 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19271198,
              5,
              5,
              v141,
              v140,
              119,
              (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
          }
        }
      }
      if ( v87 )
      {
LABEL_249:
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
          || (unsigned int)THStateCheckForTraceOverride(v143, v142)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v143, v142)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v143, v142, v144, v145)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
        {
          v148 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v143, v142)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v143, v142, v146, v147)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
          if ( (unsigned int)THStateCheckForTraceOverride(v143, v142)
            || (v149 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
          {
            v149 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19271202,
            5,
            5,
            v149,
            v148,
            120,
            (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
        }
        v150 = 168 * v72;
        v42 = v216;
        v151 = v216 + v150;
        if ( (unsigned int)AssignValueWorkItemFromRetryList(v151, &v228) )
        {
          SetEvent(*(HANDLE *)(v151 + 112));
        }
        else
        {
          v219 = --v48;
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
            || (unsigned int)THStateCheckForTraceOverride(v71, v70)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v152, v153)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
          {
            v156 = gfTraceToSecondProvider
                && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
                 || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v154, v155)
                 && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
            if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
              || (v157 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
            {
              v157 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19271208,
              5,
              5,
              v157,
              v156,
              121,
              (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
          }
        }
        continue;
      }
    }
    v42 = v216;
  }
  while ( v48 && !v223 );
  v158 = 0;
  v159 = 0;
  v160 = v215;
  for ( j = lpHandles; (unsigned int)v159 < v160; v159 = (unsigned int)(v159 + 1) )
  {
    if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v162, v163)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
    {
      v166 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v71, v70)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v71, v70, v164, v165)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
      v167 = (unsigned int)THStateCheckForTraceOverride(v71, v70)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5);
      WPP_SF_ddq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19271231,
        5,
        5,
        v167,
        v166,
        122,
        (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
      j = lpHandles;
    }
    if ( j[v159] )
    {
      ++v158;
      *(_DWORD *)(168LL * (unsigned int)v159 + v42 + 136) = 1;
      SetEvent(*(HANDLE *)(168LL * (unsigned int)v159 + v42 + 112));
    }
  }
  if ( (unsigned int)THStateCheckForTraceOverride(v71, v70)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v169, v168)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v169, v168, v170, v171)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
  {
    v174 = gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v169, v168)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v169, v168, v172, v173)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
    if ( (unsigned int)THStateCheckForTraceOverride(v169, v168)
      || (v175 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
    {
      v175 = 1;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19271243,
      5,
      5,
      v175,
      v174,
      123,
      (__int64)&WPP_86babf8413563011cdbb63299f85e207_Traceguids);
  }
  if ( v158 )
  {
    while ( 1 )
    {
      v177 = WaitForMultipleObjects(v158, j, 1, 0xEA60u);
      v178 = (unsigned int)eServiceShutdown;
      if ( eServiceShutdown
        && ((unsigned int)IncrementWPPPerfCountersForLevel(3)
         || (unsigned int)THStateCheckForTraceOverride(v178, v176)
         || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 5)
         || gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v178, v176)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v178, v176, v179, v180)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 5))) )
      {
        v183 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v178, v176)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v178, v176, v181, v182)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 5));
        if ( (unsigned int)THStateCheckForTraceOverride(v178, v176)
          || (v184 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 5)) != 0 )
        {
          v184 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19271255,
          3,
          5,
          v184,
          v183,
          124,
          &WPP_86babf8413563011cdbb63299f85e207_Traceguids);
      }
      if ( v177 != 258 )
        break;
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
        || (unsigned int)THStateCheckForTraceOverride(v186, v185)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 5)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v186, v185)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v186, v185, v187, v188)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 5)) )
      {
        v191 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v186, v185)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v186, v185, v189, v190)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 5));
        if ( (unsigned int)THStateCheckForTraceOverride(v186, v185)
          || (v192 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 5)) != 0 )
        {
          v192 = 1;
        }
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19271261,
          3,
          5,
          v192,
          v191,
          125,
          &WPP_86babf8413563011cdbb63299f85e207_Traceguids);
      }
      DoLogUnhandledError2(19271262, &word_18049B11A, 258, 1);
      j = lpHandles;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v178, v176)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v194, v193)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v194, v193, v195, v196)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5)) )
    {
      v199 = gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v194, v193)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v194, v193, v197, v198)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 5));
      if ( (unsigned int)THStateCheckForTraceOverride(v194, v193)
        || (v200 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 5)) != 0 )
      {
        v200 = 1;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19271269,
        5,
        5,
        v200,
        v199,
        126,
        &WPP_86babf8413563011cdbb63299f85e207_Traceguids);
    }
  }
  v201 = v215;
  if ( v215 )
  {
    v202 = 0;
    v203 = v227;
    v204 = 0;
    do
    {
      v205 = v204;
      v206 = 168LL * v202;
      CloseHandle(*(HANDLE *)(v206 + v42 + 112));
      CloseHandle(*(HANDLE *)(168 * v205 + v42 + 120));
      v207 = lpHandles[v205];
      if ( v207 )
        CloseHandle(v207);
      MergeLargeAttributesArrays(v206 + v42 + 144, v203 + 48);
      v204 = ++v202;
    }
    while ( v202 < v201 );
  }
  *(_DWORD *)(v227 + 12) = v221;
  v208 = gpDsEventConfig;
  if ( !gpDsEventConfig )
    return v212;
  if ( (int)gpDsEventConfig[2].OffsetHigh >= 2
    || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(294, 2) )
  {
LABEL_391:
    v244 = 2;
    v250 = 0;
    v253 = 0;
    v254 = 0;
    Offset = v208[2].Offset;
    v242 = 1073744812;
    v245 = 0;
    v246 = 1;
    v255 = &v256;
    v256 = 6;
    v257 = v231;
    v258 = 5;
    v260 = v238;
    v259 = &v260;
    v261 = 5;
    v263 = *(unsigned int *)(v239 + 148);
    v262 = &v263;
    v264 = 4;
    v209 = v212;
    v266 = v212;
    v265 = &v266;
    v241 = 4;
    v249 = 0;
    v248 = 294;
    v247 = 1;
    v251 = 0;
    v252 = 0;
    DoLogEventAndTrace(&v241);
  }
  else
  {
    if ( (unsigned int)DoLogMsgOverride(1073744812) )
    {
      v208 = gpDsEventConfig;
      goto LABEL_391;
    }
    return v212;
  }
  return v209;
}

```

## disassembly

```asm
0x1802ec838  mov     r11, rsp
0x1802ec83b  push    rbx
0x1802ec83c  push    rsi
0x1802ec83d  push    rdi
0x1802ec83e  push    r12
0x1802ec840  push    r13
0x1802ec842  push    r14
0x1802ec844  push    r15
0x1802ec846  sub     rsp, 3C0h
0x1802ec84d  mov     rax, cs:__security_cookie
0x1802ec854  xor     rax, rsp
0x1802ec857  mov     [rsp+3F8h+var_48], rax
0x1802ec85f  mov     r15d, r9d
0x1802ec862  mov     [rsp+3F8h+var_388], r15d
0x1802ec867  mov     [rsp+3F8h+var_398], r8d
0x1802ec86c  mov     rdi, rdx
0x1802ec86f  mov     [rsp+3F8h+var_318], rdx
0x1802ec877  mov     r14, rcx
0x1802ec87a  mov     [rsp+3F8h+var_320], rcx
0x1802ec882  mov     [rsp+3F8h+var_348], r15d
0x1802ec88a  mov     rdx, [rsp+3F8h+arg_20]
0x1802ec892  mov     [rsp+3F8h+var_2E8], rdx
0x1802ec89a  mov     rax, [rsp+3F8h+arg_48]
0x1802ec8a2  mov     [rsp+3F8h+var_2F8], rax
0x1802ec8aa  mov     rax, [rsp+3F8h+arg_50]
0x1802ec8b2  mov     [rsp+3F8h+var_340], rax
0x1802ec8ba  mov     [rsp+3F8h+var_2D8], rax
0x1802ec8c2  mov     rcx, [rsp+3F8h+arg_58]
0x1802ec8ca  mov     [rsp+3F8h+var_300], rcx
0x1802ec8d2  xor     r12d, r12d
0x1802ec8d5  mov     [r11-378h], r12
0x1802ec8dc  mov     [rsp+3F8h+var_380], r12
0x1802ec8e1  mov     [rsp+3F8h+var_394], r12d
0x1802ec8e6  mov     [r11-35Ch], r12d
0x1802ec8ed  mov     [r11-364h], r12d
0x1802ec8f4  mov     eax, [rdx+94h]
0x1802ec8fa  mov     [rsp+3F8h+var_370], eax
0x1802ec901  mov     rax, [rdx+98h]
0x1802ec908  mov     [rsp+3F8h+var_358], rax
0x1802ec910  xorps   xmm0, xmm0
0x1802ec913  movups  [rsp+3F8h+var_338], xmm0
0x1802ec91b  mov     [rsp+3F8h+var_38C], r12d
0x1802ec920  mov     [r11-368h], r12d
0x1802ec927  mov     [rcx], r12
0x1802ec92a  cmp     r8d, 0FFFFFFFFh
0x1802ec92e  jnz     short loc_1802EC98B
0x1802ec930  xor     ecx, ecx
0x1802ec932  xor     edx, edx
0x1802ec934  call    BeginDraTransactionEx
0x1802ec939  nop
0x1802ec93a  mov     rdx, rdi
0x1802ec93d  mov     rcx, [r14+15C8h]
0x1802ec944  call    DBFindDSName
0x1802ec949  test    eax, eax
0x1802ec94b  jnz     short loc_1802EC962
0x1802ec94d  mov     rax, [r14+15C8h]
0x1802ec954  mov     eax, [rax+18h]
0x1802ec957  mov     [rsp+3F8h+var_398], eax
0x1802ec95b  lea     esi, [r12+1]
0x1802ec960  jmp     short loc_1802EC982
0x1802ec962  mov     ebx, eax
0x1802ec964  call    cs:__imp_GetLastError
0x1802ec96a  mov     ecx, eax
0x1802ec96c  mov     esi, 1
0x1802ec971  mov     r9d, esi
0x1802ec974  mov     r8d, 1260D5Ah
0x1802ec97a  mov     edx, ebx
0x1802ec97c  call    DraExcept
0x1802ec981  nop
0x1802ec982  xor     ecx, ecx
0x1802ec984  call    EndDraTransaction
0x1802ec989  jmp     short loc_1802EC990
0x1802ec98b  mov     esi, 1
0x1802ec990  mov     r13d, 5
0x1802ec996  mov     ecx, r13d
0x1802ec999  call    IncrementWPPPerfCountersForLevel
0x1802ec99e  test    eax, eax
0x1802ec9a0  jnz     short loc_1802EC9F5
0x1802ec9a2  call    THStateCheckForTraceOverride
0x1802ec9a7  test    eax, eax
0x1802ec9a9  jnz     short loc_1802EC9F5
0x1802ec9ab  mov     r8d, r13d
0x1802ec9ae  mov     edx, r13d
0x1802ec9b1  xor     ecx, ecx
0x1802ec9b3  call    CheckWPPLevelFlagsEnabledForProvider
0x1802ec9b8  test    eax, eax
0x1802ec9ba  jnz     short loc_1802EC9F5
0x1802ec9bc  mov     eax, cs:gfTraceToSecondProvider
0x1802ec9c2  test    eax, eax
0x1802ec9c4  jz      loc_1802ECA86
0x1802ec9ca  call    THStateCheckForTraceOverride
0x1802ec9cf  test    eax, eax
0x1802ec9d1  jnz     short loc_1802EC9F5
0x1802ec9d3  call    ThStateCheckIfTraceToSecondProvier
0x1802ec9d8  test    eax, eax
0x1802ec9da  jz      loc_1802ECA86
0x1802ec9e0  mov     r8d, r13d
0x1802ec9e3  mov     edx, r13d
0x1802ec9e6  mov     ecx, esi
0x1802ec9e8  call    CheckWPPLevelFlagsEnabledForProvider
0x1802ec9ed  test    eax, eax
0x1802ec9ef  jz      loc_1802ECA86
0x1802ec9f5  mov     eax, cs:gfTraceToSecondProvider
0x1802ec9fb  test    eax, eax
0x1802ec9fd  jz      short loc_1802ECA26
0x1802ec9ff  call    THStateCheckForTraceOverride
0x1802eca04  test    eax, eax
0x1802eca06  jnz     short loc_1802ECA22
0x1802eca08  call    ThStateCheckIfTraceToSecondProvier
0x1802eca0d  test    eax, eax
0x1802eca0f  jz      short loc_1802ECA26
0x1802eca11  mov     r8d, r13d
0x1802eca14  mov     edx, r13d
0x1802eca17  mov     ecx, esi
0x1802eca19  call    CheckWPPLevelFlagsEnabledForProvider
0x1802eca1e  test    eax, eax
0x1802eca20  jz      short loc_1802ECA26
0x1802eca22  mov     ebx, esi
0x1802eca24  jmp     short loc_1802ECA29
0x1802eca26  mov     ebx, r12d
0x1802eca29  call    THStateCheckForTraceOverride
0x1802eca2e  test    eax, eax
0x1802eca30  jnz     short loc_1802ECA46
0x1802eca32  mov     r8d, r13d
0x1802eca35  mov     edx, r13d
0x1802eca38  xor     ecx, ecx
0x1802eca3a  call    CheckWPPLevelFlagsEnabledForProvider
0x1802eca3f  test    eax, eax
0x1802eca41  mov     eax, r12d
0x1802eca44  jz      short loc_1802ECA48
0x1802eca46  mov     eax, esi
0x1802eca48  mov     ecx, 6Dh ; 'm'
0x1802eca4d  mov     dword ptr [rsp+3F8h+var_3B8], r15d
0x1802eca52  lea     rdi, WPP_86babf8413563011cdbb63299f85e207_Traceguids
0x1802eca59  mov     [rsp+3F8h+var_3C0], rdi
0x1802eca5e  mov     [rsp+3F8h+var_3C8], cx
0x1802eca63  mov     [rsp+3F8h+var_3D0], ebx
0x1802eca67  mov     [rsp+3F8h+var_3D8], eax
0x1802eca6b  mov     r9d, r13d
0x1802eca6e  mov     r8d, r13d
0x1802eca71  mov     edx, 1260D65h
0x1802eca76  mov     rcx, cs:WPP_GLOBAL_Control
0x1802eca7d  mov     rcx, [rcx+10h]
0x1802eca81  call    WPP_SF__ATTRTYP_LOG_
0x1802eca86  mov     [rsp+3F8h+var_2F0], r15
0x1802eca8e  mov     [rsp+3F8h+var_3D0], 1260D68h
0x1802eca96  mov     [rsp+3F8h+var_3D8], r12d
0x1802eca9b  mov     r9d, esi
0x1802eca9e  mov     edi, 8
0x1802ecaa3  mov     r8d, edi
0x1802ecaa6  mov     rdx, r15
0x1802ecaa9  mov     rcx, r14
0x1802ecaac  call    THAlloc_
0x1802ecab1  mov     [rsp+3F8h+lpHandles], rax
0x1802ecab9  lea     eax, [r15+1]
0x1802ecabd  mov     [rsp+3F8h+nCount], eax
0x1802ecac4  mov     edx, eax
0x1802ecac6  mov     [rsp+3F8h+var_3D0], 1260D6Ch
0x1802ecace  mov     [rsp+3F8h+var_3D8], r12d
0x1802ecad3  mov     r9d, esi
0x1802ecad6  mov     r8d, edi
0x1802ecad9  mov     rcx, r14
0x1802ecadc  call    THAlloc_
0x1802ecae1  mov     [rsp+3F8h+var_328], rax
0x1802ecae9  mov     rcx, cs:hServDoneEvent
0x1802ecaf0  mov     [rax], rcx
0x1802ecaf3  mov     [rsp+3F8h+var_3D0], 1260D70h
0x1802ecafb  mov     [rsp+3F8h+var_3D8], r12d
0x1802ecb00  mov     r9d, esi
0x1802ecb03  mov     r8d, 0A8h
0x1802ecb09  mov     rdx, r15
0x1802ecb0c  mov     rcx, r14
0x1802ecb0f  call    THAlloc_
0x1802ecb14  mov     [rsp+3F8h+var_380], rax
0x1802ecb19  mov     [rsp+3F8h+var_390], r12d
0x1802ecb1e  mov     ebx, r12d
0x1802ecb21  mov     r14d, r12d
0x1802ecb24  mov     r12, [rsp+3F8h+arg_40]
0x1802ecb2c  mov     r13, [rsp+3F8h+arg_38]
0x1802ecb34  cmp     ebx, r15d
0x1802ecb37  jnb     loc_1802ECCE9
0x1802ecb3d  xor     r9d, r9d; lpName
0x1802ecb40  xor     r8d, r8d; bInitialState
0x1802ecb43  xor     edx, edx; bManualReset
0x1802ecb45  xor     ecx, ecx; lpEventAttributes
0x1802ecb47  call    cs:__imp_CreateEventA
0x1802ecb4d  mov     edi, r14d
0x1802ecb50  mov     ecx, ebx
0x1802ecb52  imul    r15, rcx, 0A8h
0x1802ecb59  mov     rbx, [rsp+3F8h+var_380]
0x1802ecb5e  mov     [r15+rbx+70h], rax
0x1802ecb63  test    rax, rax
0x1802ecb66  jnz     short loc_1802ECB80
0x1802ecb68  call    cs:__imp_GetLastError
0x1802ecb6e  mov     ecx, eax
0x1802ecb70  mov     r9d, esi
0x1802ecb73  xor     edx, edx
0x1802ecb75  mov     r8d, 1260D76h
0x1802ecb7b  call    DraExcept
0x1802ecb80  imul    rdi, 0A8h
0x1802ecb87  mov     rcx, [rdi+rbx+70h]; hEvent
0x1802ecb8c  call    cs:__imp_ResetEvent
0x1802ecb92  xor     r9d, r9d; lpName
0x1802ecb95  xor     r8d, r8d; bInitialState
0x1802ecb98  xor     edx, edx; bManualReset
0x1802ecb9a  xor     ecx, ecx; lpEventAttributes
0x1802ecb9c  call    cs:__imp_CreateEventA
0x1802ecba2  lea     ebx, [r14+1]
0x1802ecba6  mov     rdx, [rsp+3F8h+var_328]
0x1802ecbae  mov     [rdx+rbx*8], rax
0x1802ecbb2  mov     r14, [rsp+3F8h+var_380]
0x1802ecbb7  mov     [rdi+r14+78h], rax
0x1802ecbbc  test    rax, rax
0x1802ecbbf  jnz     short loc_1802ECBD9
0x1802ecbc1  call    cs:__imp_GetLastError
0x1802ecbc7  mov     ecx, eax
0x1802ecbc9  mov     r9d, esi
0x1802ecbcc  xor     edx, edx
0x1802ecbce  mov     r8d, 1260D7Ch
0x1802ecbd4  call    DraExcept
0x1802ecbd9  mov     rcx, [rdi+r14+78h]; hEvent
0x1802ecbde  call    cs:__imp_ResetEvent
0x1802ecbe4  xor     r9d, r9d
0x1802ecbe7  mov     [r15+r14+88h], r9d
0x1802ecbef  mov     [rdi+r14+84h], esi
0x1802ecbf7  mov     [rdi+r14+10h], r12
0x1802ecbfc  mov     eax, [rsp+3F8h+var_398]
0x1802ecc00  mov     [rdi+r14], eax
0x1802ecc04  mov     rax, [rsp+3F8h+var_318]
0x1802ecc0c  mov     [rdi+r14+8], rax
0x1802ecc11  mov     [rdi+r14+18h], r13
0x1802ecc16  mov     rax, [rsp+3F8h+arg_28]
0x1802ecc1e  mov     [rdi+r14+30h], rax
0x1802ecc23  mov     r8, [rsp+3F8h+arg_30]
0x1802ecc2b  mov     eax, [r8+8]
0x1802ecc2f  shl     eax, 6
0x1802ecc32  mov     ecx, eax
0x1802ecc34  xor     ecx, [rdi+r14+38h]
0x1802ecc39  and     ecx, 0FFFFFFBFh
0x1802ecc3c  xor     ecx, eax
0x1802ecc3e  mov     [rdi+r14+38h], ecx
0x1802ecc43  mov     eax, [r8]
0x1802ecc46  shl     eax, 5
0x1802ecc49  mov     edx, eax
0x1802ecc4b  xor     edx, ecx
0x1802ecc4d  and     edx, 0FFFFFFDFh
0x1802ecc50  xor     edx, eax
0x1802ecc52  mov     [rdi+r14+38h], edx
0x1802ecc57  mov     eax, [r8+0Ch]
0x1802ecc5b  shl     eax, 4
0x1802ecc5e  xor     edx, eax
0x1802ecc60  and     edx, 0FFFFFFEFh
0x1802ecc63  xor     edx, eax
0x1802ecc65  mov     [rdi+r14+38h], edx
0x1802ecc6a  mov     rcx, [rsp+3F8h+var_320]
0x1802ecc72  movups  xmm0, xmmword ptr [rcx+1738h]
0x1802ecc79  movdqu  xmmword ptr [rdi+r14+40h], xmm0
0x1802ecc80  mov     rax, [rcx+16C8h]
0x1802ecc87  mov     [rdi+r14+50h], rax
0x1802ecc8c  mov     [rdi+r14+64h], r9d
0x1802ecc91  mov     rax, [rsp+3F8h+var_340]
0x1802ecc99  mov     eax, [rax+38h]
0x1802ecc9c  mov     [rdi+r14+98h], eax
0x1802ecca4  mov     edx, eax
0x1802ecca6  mov     [rsp+3F8h+var_3D0], 1260D94h
0x1802eccae  mov     [rsp+3F8h+var_3D8], r9d
0x1802eccb3  mov     r9d, esi
0x1802eccb6  mov     r8d, 1Ch
0x1802eccbc  call    THAlloc_
0x1802eccc1  mov     [rdi+r14+0A0h], rax
0x1802eccc9  lea     rcx, [r14+90h]
0x1802eccd0  add     rcx, r15
0x1802eccd3  call    InitLargeAttributes
0x1802eccd8  mov     [rsp+3F8h+var_390], ebx
0x1802eccdc  mov     r14d, ebx
0x1802eccdf  mov     r15d, [rsp+3F8h+var_388]
0x1802ecce4  jmp     loc_1802ECB34
0x1802ecce9  xor     r13d, r13d
0x1802eccec  mov     [rsp+3F8h+var_390], r13d
0x1802eccf1  mov     ebx, r13d
0x1802eccf4  mov     edi, r13d
0x1802eccf7  mov     r12, [rsp+3F8h+var_380]
0x1802eccfc  mov     r14, [rsp+3F8h+lpHandles]
0x1802ecd04  cmp     ebx, r15d
0x1802ecd07  jnb     short loc_1802ECD5D
0x1802ecd09  mov     eax, ebx
0x1802ecd0b  imul    r9, rax, 0A8h
0x1802ecd12  add     r9, r12
0x1802ecd15  mov     qword ptr [rsp+3F8h+var_3D0], r13
0x1802ecd1a  mov     [rsp+3F8h+var_3D8], r13d
0x1802ecd1f  lea     r8, UpdateNCValuesMultipleThreadsHelper
0x1802ecd26  xor     edx, edx
0x1802ecd28  xor     ecx, ecx
0x1802ecd2a  call    cs:__imp__o__beginthreadex
0x1802ecd30  mov     ecx, edi
0x1802ecd32  mov     [r14+rcx*8], rax
0x1802ecd36  test    rax, rax
0x1802ecd39  jnz     short loc_1802ECD53
0x1802ecd3b  call    cs:__imp_GetLastError
0x1802ecd41  mov     ecx, eax
  ... truncated ...
```
