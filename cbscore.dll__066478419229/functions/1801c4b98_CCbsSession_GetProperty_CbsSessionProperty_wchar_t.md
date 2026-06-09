# CCbsSession::GetProperty(_CbsSessionProperty,wchar_t * *)

- ea: `0x1801c4b98`
- end: `0x1801c76bc`
- name: `?GetProperty@CCbsSession@@QEAAJW4_CbsSessionProperty@@PEAPEA_W@Z`
- size: `11044`
- prototype: ``
- caller_count: `2`
- callee_count: `68`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801dc874`
- `0x1802b5ca4`

## callees

- `0x18000f090`
- `0x180010b60`
- `0x180010cc0`
- `0x1800115a8`
- `0x180011a14`
- `0x180012034`
- `0x180012fe4`
- `0x180013250`
- `0x180013c54`
- `0x18001837c`
- `0x180019bdc`
- `0x180023ca8`
- `0x180023e74`
- `0x1800289f0`
- `0x18002a2bc`
- `0x18002a448`
- `0x18002a78c`
- `0x18002ac84`
- `0x18002de30`
- `0x18002e0d0`
- `0x18002f9a8`
- `0x1800406e4`
- `0x180044bdc`
- `0x180044c5c`
- `0x18004be14`
- `0x180051c8c`
- `0x180055b4c`
- `0x180056864`
- `0x180059a00`
- `0x18005dd58`
- `0x18005eef0`
- `0x180060d80`
- `0x1800653d8`
- `0x18008f280`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a0a78`
- `0x1800a6818`
- `0x1800a8678`
- `0x1800d0588`
- `0x1800e7500`
- `0x1800ea2d4`
- `0x1800eb500`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800fa3ec`
- `0x18010c754`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c69a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c69a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801c6c24`

## string_xrefs

- `0x1801c4f7f`: `Unserviceable`
- `0x1801c4c83`: `Failed to get task allocator.`
- `0x1801c7445`: `Failed to get path to UpdateAgent.dll`
- `0x1801c7410`: `UpdateAgent.dll`
- `0x1801c708a`: `Failed to get servicing directory`
- `0x1801c66a6`: `*.XML`
- `0x1801c712f`: `*.XML`
- `0x1801c6a5d`: `Failed directory walk on {}`
- `0x1801c7169`: `Failed directory walk on {}`
- `0x1801c6009`: `Failed to get target Windows directory`
- `0x1801c60a2`: `Failed to create servicing querier`
- `0x1801c6f27`: `Failed to create cbs identity`
- `0x1801c6bc9`: `Failed to query components of package manifest: {}`
- `0x1801c6ab8`: `Failed to create path to component: {}`
- `0x1801c4d27`: `Failed getting property.  Analysis must be completed first.`
- `0x1801c4dc8`: `Failed getting property. Session must be completed first.`
- `0x1801c5235`: `Failed to get session completion timestamp, last session state: {}`
- `0x1801c52d3`: `Failed to get session completion timestamp, last session state: {}`
- `0x1801c536d`: `Failed to get session completion timestamp, last session state: {}`
- `0x1801c53fd`: `Failed to format session completion date/time`
- `0x1801c6936`: `Failed to create path to component file: {}`

## pseudocode

```c
__int64 __fastcall CCbsSession::GetProperty(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *v3; // r12
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // rdx
  __int64 InitPointer; // rax
  int TaskAllocator; // eax
  int v12; // edx
  unsigned __int64 v13; // r9
  int v14; // edx
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // edx
  int v18; // eax
  unsigned int v19; // eax
  const wchar_t *v20; // r8
  int v21; // eax
  const wchar_t *v22; // r8
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  int Property; // eax
  unsigned int v27; // edx
  const wchar_t *v28; // r8
  int v29; // eax
  const wchar_t *v30; // r8
  int IsRebootRequired; // eax
  const wchar_t *v32; // r8
  unsigned __int64 v33; // r9
  int v35; // eax
  int v36; // edx
  int v37; // eax
  unsigned int v38; // edi
  const wchar_t *v39; // rax
  int v40; // eax
  int v41; // r10d
  int v42; // edx
  const wchar_t *v43; // rax
  int v44; // eax
  int v45; // r10d
  int v46; // edx
  const wchar_t *v47; // rax
  int SessionTimestamp; // eax
  int v49; // r10d
  int v50; // edx
  int v51; // eax
  int v52; // edx
  const wchar_t *v53; // r8
  int v54; // eax
  int v55; // eax
  int v56; // edx
  int v57; // eax
  int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // eax
  int v62; // eax
  int v63; // edx
  int v64; // eax
  int v65; // eax
  int v66; // edx
  int v67; // eax
  int v68; // eax
  int v69; // edx
  int v70; // eax
  const wchar_t *v71; // rax
  const wchar_t *v72; // r8
  int v73; // eax
  int v74; // edx
  int v75; // eax
  int v76; // edx
  int v77; // eax
  const wchar_t *v78; // rax
  const wchar_t *v79; // r8
  int v80; // eax
  int v81; // edx
  int v82; // eax
  int v83; // edx
  int v84; // eax
  const wchar_t *v85; // r8
  int v86; // eax
  int v87; // eax
  int v88; // edx
  unsigned __int64 v89; // r9
  __int64 v90; // rdx
  void *p_pv; // rcx
  int v92; // eax
  void *v93; // rcx
  int TotalPackageMinimumSize; // eax
  int v95; // edx
  int v96; // eax
  int v97; // edx
  int v98; // eax
  const wchar_t *v99; // rax
  const wchar_t *v100; // r8
  int TimestampDifference; // eax
  int v102; // edx
  int v103; // eax
  int v104; // edx
  int v105; // eax
  int v106; // edx
  unsigned int ImageProcessorArchitecture; // eax
  int ProcessorArchitectureString; // eax
  int v109; // edx
  __int64 v110; // rdx
  unsigned __int64 v111; // r9
  int TargetWindowsDirectory; // eax
  int v113; // edx
  int v114; // eax
  __int64 v115; // rdx
  int v116; // eax
  int v117; // edx
  int v118; // eax
  _QWORD *v119; // rdi
  _QWORD *v120; // r14
  __int64 v121; // r15
  union _ULARGE_INTEGER v122; // rbx
  __int64 *v123; // r15
  struct CCbsIdentity **v124; // rax
  int CbsIdentity; // r14d
  const struct CCbsIdentity **v126; // rbx
  const struct CCbsIdentity **v127; // rdi
  struct ICbsIdentity *v128; // rdx
  int v129; // edx
  void *v130; // rdi
  _QWORD *v131; // rdx
  char *v132; // rcx
  __int64 v133; // rax
  int v134; // edx
  void *v135; // rdi
  _QWORD *v136; // rdx
  char *v137; // rcx
  __int64 v138; // rax
  int v139; // edx
  void *v140; // rdi
  _QWORD *v141; // rdx
  char *v142; // rcx
  __int64 v143; // rax
  int v144; // eax
  __int64 *v145; // r14
  LPVOID v146; // rbx
  union _ULARGE_INTEGER v147; // rdi
  __int64 v148; // r8
  int v149; // esi
  wchar_t *v150; // rsi
  __int64 v151; // rcx
  int v152; // r15d
  __int64 v153; // rdi
  __int64 *v154; // r15
  __int64 *v155; // r13
  int v156; // edx
  void *v157; // rbx
  _QWORD *v158; // rdx
  char *v159; // rcx
  __int64 v160; // rax
  __int64 v161; // r8
  int v162; // r12d
  int v163; // edx
  __int64 v164; // rdx
  __int64 v165; // rdx
  int v166; // edx
  int v167; // edx
  __int64 v168; // rdx
  int v169; // edx
  int v170; // edx
  void *v171; // rcx
  int v172; // eax
  int v173; // edx
  int v174; // eax
  unsigned int v175; // edi
  int v176; // edx
  void *v177; // rbx
  _QWORD *v178; // rdx
  char *v179; // rcx
  __int64 v180; // rax
  int v181; // edx
  void *v182; // rbx
  _QWORD *v183; // rdx
  char *v184; // rcx
  __int64 v185; // rax
  int ServicingDirectory; // eax
  int v187; // edx
  __int64 v188; // rdx
  unsigned __int64 v189; // r9
  int v190; // eax
  __int64 v191; // rcx
  LPVOID v192; // rbx
  int v193; // eax
  int v194; // edx
  __int64 v195; // rdx
  int v196; // edi
  int v197; // edx
  __int64 *v198; // rdi
  __int64 *v199; // r14
  __int64 v200; // r8
  unsigned __int64 v201; // rdi
  unsigned __int64 v202; // r15
  unsigned __int64 v203; // r14
  _QWORD *v204; // rsi
  unsigned __int64 v205; // rbx
  unsigned __int64 v206; // r12
  __int64 v207; // rdx
  __int64 v208; // rcx
  int v209; // eax
  int v210; // edx
  int v211; // eax
  int Win32PathOfSiblingFile; // eax
  int v213; // edx
  unsigned __int64 v214; // r9
  __int64 v215; // rdx
  int v216; // eax
  __int64 v217; // rax
  int v218; // eax
  int ReofferProperty; // eax
  int v220; // edx
  const wchar_t *v221; // r8
  int v222; // eax
  int IsPended; // eax
  int v224; // edx
  const wchar_t *v225; // r8
  const wchar_t *v226; // r8
  int v227; // eax
  unsigned int *v228; // [rsp+20h] [rbp-E0h]
  unsigned int v229[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v230; // [rsp+48h] [rbp-B8h] BYREF
  union _ULARGE_INTEGER v231; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v232; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v233; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v234; // [rsp+68h] [rbp-98h] BYREF
  __int64 v235; // [rsp+70h] [rbp-90h] BYREF
  __int64 v236; // [rsp+78h] [rbp-88h] BYREF
  int v237[2]; // [rsp+80h] [rbp-80h] BYREF
  char v238; // [rsp+88h] [rbp-78h]
  wchar_t *v239; // [rsp+90h] [rbp-70h] BYREF
  int v240[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v241[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v242; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v244; // [rsp+B8h] [rbp-48h] BYREF
  void *v245[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v246; // [rsp+D8h] [rbp-28h]
  __int16 v247; // [rsp+E0h] [rbp-20h]
  __int128 v248; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v249; // [rsp+F8h] [rbp-8h]
  _BYTE v250[24]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v251; // [rsp+118h] [rbp+18h]
  __int64 *v252; // [rsp+128h] [rbp+28h]
  _BYTE v253[24]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v254; // [rsp+158h] [rbp+58h]
  _QWORD *v255; // [rsp+168h] [rbp+68h]
  _BYTE v256[24]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v257; // [rsp+198h] [rbp+98h]
  _QWORD v258[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _WORD v259[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v260[24]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v261; // [rsp+1F8h] [rbp+F8h]
  __int64 *v262; // [rsp+208h] [rbp+108h]
  wchar_t v263[32]; // [rsp+220h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *(_QWORD *)v229 = a3;
  v3 = a3;
  v242 = 0;
  v232 = 0;
  memset_0(v263, 0, sizeof(v263));
  v6 = CCbsSession::CheckInitialized((CCbsSession *)a1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v241[0] = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Cannot GetSessionID on a session that has not been initialized.");
      *(_QWORD *)v229 = v241;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v229);
    }
    v9 = 108;
LABEL_9:
    v13 = v7;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v13,
      (int)v228);
    goto LABEL_71;
  }
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v232);
  TaskAllocator = GetTaskAllocator(InitPointer);
  v7 = TaskAllocator;
  if ( TaskAllocator < 0 )
  {
    v241[0] = TaskAllocator;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get task allocator.");
      *(_QWORD *)v229 = v241;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)v229);
    }
    v9 = 109;
    goto LABEL_9;
  }
  if ( a2 <= 13 )
  {
    if ( a2 != 13 && a2 != 8 && a2 != 9 && a2 != 10 && (unsigned int)(a2 - 11) > 1 )
    {
LABEL_32:
      if ( a2 > 8 )
      {
        switch ( a2 )
        {
          case 9:
            v68 = StringCchPrintfW(v263, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1216));
            v7 = v68;
            if ( v68 >= 0 )
            {
              v70 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v70;
              if ( v70 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v70;
              v9 = 223;
              goto LABEL_10;
            }
            v241[0] = v68;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to format non-volatile size");
              *(_QWORD *)v229 = v241;
              LOBYTE(v69) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v69,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 221;
            goto LABEL_9;
          case 10:
            v65 = StringCchPrintfW(v263, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1224));
            v7 = v65;
            if ( v65 >= 0 )
            {
              v67 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v67;
              if ( v67 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v67;
              v9 = 233;
              goto LABEL_10;
            }
            v241[0] = v65;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to format shared-with-windows size");
              *(_QWORD *)v229 = v241;
              LOBYTE(v66) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v66,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 231;
            goto LABEL_9;
          case 11:
            v62 = StringCchPrintfW(v263, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1232));
            v7 = v62;
            if ( v62 >= 0 )
            {
              v64 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v64;
              if ( v64 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v64;
              v9 = 243;
              goto LABEL_10;
            }
            v241[0] = v62;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to format according-to-explorer size");
              *(_QWORD *)v229 = v241;
              LOBYTE(v63) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v63,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 241;
            goto LABEL_9;
          case 12:
            if ( !*(_QWORD *)(a1 + 1248) )
            {
              v61 = SczPublicAllocFromSz(&v242, v232, &qword_1802EB518);
              v7 = v61;
              if ( v61 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v61;
              v9 = 259;
              goto LABEL_10;
            }
            v58 = StringCchPrintfW(v263, 0x20u, L"%I64u");
            v7 = v58;
            if ( v58 >= 0 )
            {
              v60 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v60;
              if ( v60 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v60;
              v9 = 255;
              goto LABEL_10;
            }
            v241[0] = v58;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to format last scavenge date/time");
              *(_QWORD *)v229 = v241;
              LOBYTE(v59) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v59,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 253;
            goto LABEL_9;
          case 13:
            v55 = StringCchPrintfW(v263, 0x20u, L"%lu", *(unsigned int *)(a1 + 1240));
            v7 = v55;
            if ( v55 >= 0 )
            {
              v57 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v57;
              if ( v57 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v57;
              v9 = 270;
              goto LABEL_10;
            }
            v241[0] = v55;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to format superseded-package count");
              *(_QWORD *)v229 = v241;
              LOBYTE(v56) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v56,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 268;
            goto LABEL_9;
          case 14:
            v53 = L"1";
            if ( !*(_DWORD *)(a1 + 1256) )
              v53 = L"0";
            v54 = SczPublicAllocFromSz(&v242, v232, v53);
            v7 = v54;
            if ( v54 >= 0 )
              goto LABEL_70;
            v13 = (unsigned int)v54;
            v9 = 276;
            goto LABEL_10;
        }
        v231.QuadPart = 0;
        CritSecLocker::CritSecLocker((CritSecLocker *)&v248, (struct AutoCritSec *)(a1 + 584), 1);
        v38 = *(_DWORD *)(a1 + 768);
        CritSecLocker::Unlock((CritSecLocker *)&v248);
        if ( *(_DWORD *)(a1 + 1032) )
        {
          v47 = (const wchar_t *)CbsSessionStateToString(208);
          SessionTimestamp = PackageStoreGetSessionTimestamp((struct CCbsSession *)a1, v47, 1u, &v231);
          v7 = SessionTimestamp;
          if ( SessionTimestamp < 0 )
          {
            v241[0] = SessionTimestamp;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v229 = CbsSessionStateToString(v38);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                v49,
                0,
                3,
                (unsigned int)"Failed to get session completion timestamp, last session state: {}",
                (__int64)v229);
              v239 = (wchar_t *)v241;
              LOBYTE(v50) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v50,
                3,
                (unsigned int)": {}",
                (__int64)&v239);
            }
            v33 = v7;
            v24 = 325;
            goto LABEL_68;
          }
        }
        else if ( (int)v38 < 112 )
        {
          v43 = (const wchar_t *)CbsSessionStateToString(101);
          v44 = PackageStoreGetSessionTimestamp((struct CCbsSession *)a1, v43, 1u, &v231);
          v7 = v44;
          if ( v44 < 0 )
          {
            v241[0] = v44;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v229 = CbsSessionStateToString(v38);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                v45,
                0,
                3,
                (unsigned int)"Failed to get session completion timestamp, last session state: {}",
                (__int64)v229);
              v239 = (wchar_t *)v241;
              LOBYTE(v46) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v46,
                3,
                (unsigned int)": {}",
                (__int64)&v239);
            }
            v33 = v7;
            v24 = 313;
            goto LABEL_68;
          }
        }
        else
        {
          v39 = (const wchar_t *)CbsSessionStateToString(112);
          v40 = PackageStoreGetSessionTimestamp((struct CCbsSession *)a1, v39, 1u, &v231);
          v7 = v40;
          if ( v40 < 0 )
          {
            v241[0] = v40;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v229 = CbsSessionStateToString(v38);
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                v41,
                0,
                3,
                (unsigned int)"Failed to get session completion timestamp, last session state: {}",
                (__int64)v229);
              v239 = (wchar_t *)v241;
              LOBYTE(v42) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v42,
                3,
                (unsigned int)": {}",
                (__int64)&v239);
            }
            v33 = v7;
            v24 = 302;
            goto LABEL_68;
          }
        }
        v51 = StringCchPrintfW(v263, 0x20u, L"%I64u", v231.QuadPart);
        v7 = v51;
        if ( v51 < 0 )
        {
          v241[0] = v51;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to format session completion date/time");
            *(_QWORD *)v229 = v241;
            LOBYTE(v52) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v52,
              3,
              (unsigned int)": {}",
              (__int64)v229);
          }
          v33 = v7;
          v24 = 330;
          goto LABEL_68;
        }
        v23 = SczPublicAllocFromSz(&v242, v232, v263);
        v7 = v23;
        if ( v23 < 0 )
        {
          v24 = 332;
          goto LABEL_67;
        }
      }
      else
      {
        switch ( a2 )
        {
          case 8:
            v35 = StringCchPrintfW(v263, 0x20u, L"%I64u", *(_QWORD *)(a1 + 1208));
            v7 = v35;
            if ( v35 >= 0 )
            {
              v37 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v37;
              if ( v37 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v37;
              v9 = 213;
              goto LABEL_10;
            }
            v241[0] = v35;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to format volatile size");
              *(_QWORD *)v229 = v241;
              LOBYTE(v36) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v36,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 211;
            goto LABEL_9;
          case 1:
            CritSecLocker::CritSecLocker((CritSecLocker *)&v248, (struct AutoCritSec *)(a1 + 584), 1);
            IsRebootRequired = CCbsSession::IsRebootRequired((CCbsSession *)a1);
            v32 = L"1";
            if ( !IsRebootRequired )
              v32 = L"0";
            v23 = SczPublicAllocFromSz(&v242, v232, v32);
            v7 = v23;
            if ( v23 < 0 )
            {
              v24 = 148;
              goto LABEL_67;
            }
            break;
          case 2:
            CritSecLocker::CritSecLocker((CritSecLocker *)&v248, (struct AutoCritSec *)(a1 + 584), 1);
            v30 = &qword_1802EB518;
            if ( *(_QWORD *)(a1 + 1072) )
              v30 = *(const wchar_t **)(a1 + 1072);
            v23 = SczPublicAllocFromSz(&v242, v232, v30);
            v7 = v23;
            if ( v23 < 0 )
            {
              v24 = 155;
              goto LABEL_67;
            }
            break;
          case 3:
            v241[0] = 0;
            Property = PackageStoreGetProperty((struct CCbsSession *)a1, L"Unserviceable", v241);
            v27 = v241[0];
            v28 = L"1";
            if ( Property < 0 )
              v27 = 0;
            if ( !v27 )
              v28 = L"0";
            v29 = SczPublicAllocFromSz(&v242, v232, v28);
            v7 = v29;
            if ( v29 >= 0 )
              goto LABEL_70;
            v13 = (unsigned int)v29;
            v9 = 166;
            goto LABEL_10;
          case 4:
            v25 = SczPublicAllocFromSz(&v242, v232, L"1");
            v7 = v25;
            if ( v25 >= 0 )
              goto LABEL_70;
            v13 = (unsigned int)v25;
            v9 = 175;
            goto LABEL_10;
          case 5:
            CritSecLocker::CritSecLocker((CritSecLocker *)&v248, (struct AutoCritSec *)(a1 + 584), 1);
            v22 = &qword_1802EB518;
            if ( *(_QWORD *)(a1 + 1120) )
              v22 = *(const wchar_t **)(a1 + 1120);
            v23 = SczPublicAllocFromSz(&v242, v232, v22);
            v7 = v23;
            if ( v23 < 0 )
            {
              v24 = 182;
LABEL_67:
              v33 = (unsigned int)v23;
LABEL_68:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v24,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                (const char *)v33,
                (int)v228);
              CritSecLocker::~CritSecLocker((CritSecLocker *)&v248);
              goto LABEL_71;
            }
            break;
          case 6:
            v241[0] = 0;
            v19 = CheckStoreCorruptionFlag((struct CCbsSession *)a1, 0, (int *)v241);
            LogAdapter::TraceAtLevelIfFailed<long,>(1, v19, "Unable to GetAndResetCorruptionFlag");
            v20 = L"1";
            if ( !v241[0] )
              v20 = L"0";
            v21 = SczPublicAllocFromSz(&v242, v232, v20);
            v7 = v21;
            if ( v21 >= 0 )
              goto LABEL_70;
            v13 = (unsigned int)v21;
            v9 = 194;
            goto LABEL_10;
          case 7:
            v18 = SczPublicAllocFromSz(&v242, v232, L"0");
            v7 = v18;
            if ( v18 >= 0 )
              goto LABEL_70;
            v13 = (unsigned int)v18;
            v9 = 200;
            goto LABEL_10;
          default:
            goto LABEL_210;
        }
      }
LABEL_69:
      CritSecLocker::~CritSecLocker((CritSecLocker *)&v248);
      goto LABEL_70;
    }
    goto LABEL_17;
  }
  if ( a2 == 14 )
  {
LABEL_17:
    if ( !*(_QWORD *)(a1 + 1232) )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed getting property.  Analysis must be completed first.");
        *(_QWORD *)v229 = v241;
        v241[0] = -2147023728;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v14,
          3,
          (unsigned int)": {0}",
          (__int64)v229);
      }
      v15 = 1168;
      v16 = 126;
LABEL_21:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v16,
             (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
             (const char *)v15,
             (unsigned int)v228);
      goto LABEL_71;
    }
    goto LABEL_30;
  }
  if ( (a2 == 15 || a2 == 23 || (unsigned int)(a2 - 24) <= 1) && !*(_DWORD *)(a1 + 1036) )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed getting property. Session must be completed first.");
      *(_QWORD *)v229 = v241;
      v241[0] = -2147024846;
      LOBYTE(v17) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v17,
        3,
        (unsigned int)": {0}",
        (__int64)v229);
    }
    v15 = 50;
    v16 = 136;
    goto LABEL_21;
  }
LABEL_30:
  if ( a2 <= 16 )
  {
    if ( a2 != 16 )
      goto LABEL_32;
LABEL_184:
    v231.QuadPart = 0;
    TotalPackageMinimumSize = CCbsSession::GetTotalPackageMinimumSize(a1, (unsigned int)a2, &v231);
    v7 = TotalPackageMinimumSize;
    if ( TotalPackageMinimumSize >= 0 )
    {
      v96 = StringCchPrintfW(v263, 0x20u, L"%llu", v231.QuadPart);
      v7 = v96;
      if ( v96 >= 0 )
      {
        v98 = SczPublicAllocFromSz(&v242, v232, v263);
        v7 = v98;
        if ( v98 >= 0 )
          goto LABEL_70;
        v13 = (unsigned int)v98;
        v9 = 348;
        goto LABEL_10;
      }
      v241[0] = v96;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to format package minimum size.");
        *(_QWORD *)v229 = v241;
        LOBYTE(v97) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v97,
          3,
          (unsigned int)": {}",
          (__int64)v229);
      }
      v9 = 346;
    }
    else
    {
      v241[0] = TotalPackageMinimumSize;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get total package minimum size.");
        *(_QWORD *)v229 = v241;
        LOBYTE(v95) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v95,
          3,
          (unsigned int)": {}",
          (__int64)v229);
      }
      v9 = 342;
    }
    goto LABEL_9;
  }
  if ( a2 <= 25 )
  {
    switch ( a2 )
    {
      case 25:
        v241[0] = 0;
        CbsSessionStateToString(208);
        v99 = (const wchar_t *)CbsSessionStateToString(176);
        TimestampDifference = CbsGetTimestampDifference((struct CCbsSession *)a1, v99, v100, v241);
        v7 = TimestampDifference;
        if ( TimestampDifference >= 0 )
        {
          v103 = StringCchPrintfW(v263, 0x20u, L"%lu", v241[0]);
          v7 = v103;
          if ( v103 >= 0 )
          {
            v105 = SczPublicAllocFromSz(&v242, v232, v263);
            v7 = v105;
            if ( v105 >= 0 )
              goto LABEL_70;
            v13 = (unsigned int)v105;
            v9 = 445;
            goto LABEL_10;
          }
          v241[0] = v103;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to format session post-reboot time");
            *(_QWORD *)v229 = v241;
            LOBYTE(v104) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v104,
              3,
              (unsigned int)": {}",
              (__int64)v229);
          }
          v9 = 443;
        }
        else
        {
          v241[0] = TimestampDifference;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Post-reboot time performance datapoint is invalid.");
            *(_QWORD *)v229 = v241;
            LOBYTE(v102) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v102,
              3,
              (unsigned int)": {}",
              (__int64)v229);
          }
          v9 = 439;
        }
        goto LABEL_9;
      case 17:
        goto LABEL_184;
      case 19:
        v231.QuadPart = 0;
        v87 = CCbsSession::EnumerateFeaturesToRetry((CCbsSession *)a1, (wchar_t **)&v231);
        v7 = v87;
        if ( v87 >= 0 )
        {
          v92 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SczPublicAllocFromSz)(
                  &v242,
                  v232,
                  (union _ULARGE_INTEGER)v231.QuadPart);
          v7 = v92;
          if ( v92 >= 0 )
          {
            v93 = &v231;
            goto LABEL_183;
          }
          v89 = (unsigned int)v92;
          v90 = 358;
        }
        else
        {
          v241[0] = v87;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get retry features.");
            *(_QWORD *)v229 = v241;
            LOBYTE(v88) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v88,
              3,
              (unsigned int)": {}",
              (__int64)v229);
          }
          v89 = v7;
          v90 = 356;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v90,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)v89,
          (int)v228);
        p_pv = &v231;
        goto LABEL_179;
    }
    if ( a2 != 20 && a2 != 21 )
    {
      switch ( a2 )
      {
        case 22:
          v85 = L"1";
          if ( !*(_BYTE *)(a1 + 2252) )
            v85 = L"0";
          v86 = SczPublicAllocFromSz(&v242, v232, v85);
          v7 = v86;
          if ( v86 >= 0 )
            goto LABEL_70;
          v13 = (unsigned int)v86;
          v9 = 375;
          goto LABEL_10;
        case 23:
          v241[0] = 0;
          CbsSessionStateToString(160);
          v78 = (const wchar_t *)CbsSessionStateToString(144);
          v80 = CbsGetTimestampDifference((struct CCbsSession *)a1, v78, v79, v241);
          v7 = v80;
          if ( v80 >= 0 )
          {
            v82 = StringCchPrintfW(v263, 0x20u, L"%lu", v241[0]);
            v7 = v82;
            if ( v82 >= 0 )
            {
              v84 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v84;
              if ( v84 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v84;
              v9 = 398;
              goto LABEL_10;
            }
            v241[0] = v82;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to format session shutdown time");
              *(_QWORD *)v229 = v241;
              LOBYTE(v83) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v83,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 396;
          }
          else
          {
            v241[0] = v80;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Shutdown time performance datapoint is invalid.");
              *(_QWORD *)v229 = v241;
              LOBYTE(v81) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v81,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 392;
          }
          goto LABEL_9;
        case 24:
          v241[0] = 0;
          CbsSessionStateToString(176);
          v71 = (const wchar_t *)CbsSessionStateToString(160);
          v73 = CbsGetTimestampDifference((struct CCbsSession *)a1, v71, v72, v241);
          v7 = v73;
          if ( v73 >= 0 )
          {
            v75 = StringCchPrintfW(v263, 0x20u, L"%lu", v241[0]);
            v7 = v75;
            if ( v75 >= 0 )
            {
              v77 = SczPublicAllocFromSz(&v242, v232, v263);
              v7 = v77;
              if ( v77 >= 0 )
                goto LABEL_70;
              v13 = (unsigned int)v77;
              v9 = 421;
              goto LABEL_10;
            }
            v241[0] = v75;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to format session reboot time");
              *(_QWORD *)v229 = v241;
              LOBYTE(v76) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v76,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 419;
          }
          else
          {
            v241[0] = v73;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Reboot time performance datapoint is invalid.");
              *(_QWORD *)v229 = v241;
              LOBYTE(v74) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v74,
                3,
                (unsigned int)": {}",
                (__int64)v229);
            }
            v9 = 415;
          }
          goto LABEL_9;
      }
      goto LABEL_210;
    }
LABEL_408:
    LOBYTE(v241[0]) = 0;
    ReofferProperty = CCbsSession::GetReofferProperty(a1, (unsigned int)a2, v241);
    v7 = ReofferProperty;
    if ( ReofferProperty >= 0 )
    {
      v221 = L"1";
      if ( !LOBYTE(v241[0]) )
        v221 = L"0";
      v222 = SczPublicAllocFromSz(&v242, v232, v221);
      v7 = v222;
      if ( v222 >= 0 )
        goto LABEL_70;
      v13 = (unsigned int)v222;
      v9 = 369;
      goto LABEL_10;
    }
    LODWORD(v242) = ReofferProperty;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get reoffer property.");
      *(_QWORD *)v237 = &v242;
      LOBYTE(v220) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v220,
        3,
        (unsigned int)": {}",
        (__int64)v237);
    }
    v9 = 367;
    goto LABEL_9;
  }
  switch ( a2 )
  {
    case 26:
      v226 = L"1";
      if ( (*(_DWORD *)(a1 + 2208) & 0x20000) == 0 )
        v226 = L"0";
      v227 = SczPublicAllocFromSz(&v242, v232, v226);
      v7 = v227;
      if ( v227 >= 0 )
        goto LABEL_70;
      v13 = (unsigned int)v227;
      v9 = 453;
      goto LABEL_10;
    case 27:
      CritSecLocker::CritSecLocker((CritSecLocker *)&v248, (struct AutoCritSec *)(a1 + 584), 1);
      v241[0] = 0;
      IsPended = CCbsSession::LCUInstallIsPended((CCbsSession *)a1, (int *const)v241);
      v7 = IsPended;
      if ( IsPended < 0 )
      {
        LODWORD(v242) = IsPended;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to check whether LCU is pending");
          *(_QWORD *)v237 = &v242;
          LOBYTE(v224) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v224,
            3,
            (unsigned int)": {}",
            (__int64)v237);
        }
        v33 = v7;
        v24 = 462;
        goto LABEL_68;
      }
      v225 = L"1";
      if ( !v241[0] )
        v225 = L"0";
      v23 = SczPublicAllocFromSz(&v242, v232, v225);
      v7 = v23;
      if ( v23 < 0 )
      {
        v24 = 464;
        goto LABEL_67;
      }
      goto LABEL_69;
    case 28:
      goto LABEL_408;
    case 29:
      v249 = 0;
      v248 = 0;
      Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(&_ImageBase, L"UpdateAgent.dll", &v248);
      v7 = Win32PathOfSiblingFile;
      if ( Win32PathOfSiblingFile >= 0 )
      {
        *(_QWORD *)v237 = &v248;
        v216 = Windows::StringUtil::Rtl::EnsureNullTerminated<Windows::AutoOperatorAmpersandHelper<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>>(v237);
        if ( v216 < 0 )
        {
          v7 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x1DC,
                 (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                 (const char *)(unsigned int)v216,
                 (int)v228);
          goto LABEL_402;
        }
        v217 = Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v248);
        v218 = SczPublicAllocFromSz(&v242, v232, v217);
        v7 = v218;
        if ( v218 >= 0 )
        {
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v248);
          goto LABEL_70;
        }
        v214 = (unsigned int)v218;
        v215 = 478;
      }
      else
      {
        LODWORD(v242) = Win32PathOfSiblingFile;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get path to UpdateAgent.dll");
          *(_QWORD *)v237 = &v242;
          LOBYTE(v213) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v213,
            3,
            (unsigned int)": {}",
            (__int64)v237);
        }
        v214 = v7;
        v215 = 474;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v215,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)v214,
        (int)v228);
LABEL_402:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v248);
      goto LABEL_71;
    case 30:
      pv = 0;
      CCbsStringArray::CCbsStringArray((CCbsStringArray *)v250);
      CCbsStringArray::CCbsStringArray((CCbsStringArray *)v253);
      v230 = 0;
      ServicingDirectory = CCbsSession::GetServicingDirectory((CCbsSession *)a1, L"FodMetadata", (wchar_t **)&pv);
      v7 = ServicingDirectory;
      if ( ServicingDirectory < 0 )
      {
        LODWORD(v242) = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get servicing directory");
          *(_QWORD *)v237 = &v242;
          LOBYTE(v187) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v187,
            3,
            (unsigned int)": {}",
            (__int64)v237);
        }
        v188 = 489;
LABEL_356:
        v189 = v7;
LABEL_357:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v188,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)v189,
          (int)v228);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v253);
        CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
        p_pv = &pv;
        goto LABEL_179;
      }
      v190 = SczAllocConcatSz(&pv, L"\\metadata\\");
      v7 = v190;
      if ( v190 < 0 )
      {
        v189 = (unsigned int)v190;
        v188 = 491;
        goto LABEL_357;
      }
      v192 = pv;
      v193 = CbsEnumFiles(v191, pv, L"*.XML", v250);
      v149 = v193;
      if ( v193 >= 0 )
      {
        if ( v251 )
        {
          v198 = v252;
          v199 = &v252[v251];
          while ( v198 != v199 )
          {
            v200 = *v198;
            v231.QuadPart = 0;
            v149 = SczAllocCombinePath2Sz(&v231, v192, v200);
            if ( v149 < 0 )
            {
              v207 = 503;
LABEL_383:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v207,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                (const char *)(unsigned int)v149,
                (int)v228);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v231);
LABEL_365:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v253);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
              v171 = &pv;
LABEL_366:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v171);
              v7 = v149;
              goto LABEL_71;
            }
            v149 = PathPrefix(&v231);
            if ( v149 < 0 )
            {
              v207 = 504;
              goto LABEL_383;
            }
            *(union _ULARGE_INTEGER *)v237 = v231;
            v149 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v253, v237);
            if ( v149 < 0 )
            {
              v207 = 505;
              goto LABEL_383;
            }
            v231.QuadPart = 0;
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v231);
            ++v198;
          }
          v201 = v254;
          if ( v254 > 1 )
          {
            v202 = v254 - 1;
            v203 = 0;
            v204 = v255;
            do
            {
              v205 = v203 + 1;
              v206 = v203++;
              while ( v205 < v201 )
              {
                if ( (int)StringArrayCompareCaseInsensitive(
                            (wchar_t *const *)&v204[v206],
                            (wchar_t *const *)&v204[v205]) > 0 )
                {
                  v208 = v204[v206];
                  v204[v206] = v204[v205];
                  v204[v205] = v208;
                }
                ++v205;
              }
            }
            while ( v203 < v202 );
            v3 = *(_QWORD **)v229;
          }
          v209 = CCbsStringArray::SaveAsStringList((CCbsStringArray *)v253, L";", &v230);
          v7 = v209;
          if ( v209 >= 0 )
          {
            v211 = SczPublicAllocFromSz(&v242, v232, v230);
            v7 = v211;
            if ( v211 >= 0 )
            {
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v253);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
              v93 = &pv;
              goto LABEL_183;
            }
            v189 = (unsigned int)v211;
            v188 = 514;
            goto LABEL_357;
          }
          LODWORD(v242) = v209;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
            *(_QWORD *)v237 = &v242;
            LOBYTE(v210) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v210,
              3,
              (unsigned int)": {}",
              (__int64)v237);
          }
          v188 = 512;
          goto LABEL_356;
        }
        v149 = -2146498549;
        LODWORD(v244) = -2146498549;
        if ( LogAdapter::g_Logger )
        {
          v196 = v251 + 3;
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            (unsigned int)(v251 + 3),
            "Target image does not have required UUP metadata");
          *(_QWORD *)v237 = &v244;
          LOBYTE(v197) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v197,
            v196,
            (unsigned int)": {}",
            (__int64)v237);
        }
        v195 = 497;
      }
      else
      {
        LODWORD(v242) = v193;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v237 = v192;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed directory walk on {}",
            (__int64)v237);
          *(_QWORD *)v240 = &v242;
          LOBYTE(v194) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v194,
            3,
            (unsigned int)": {}",
            (__int64)v240);
        }
        v195 = 495;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v195,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)v149,
        (int)v228);
      goto LABEL_365;
  }
  if ( a2 != 31 )
  {
LABEL_210:
    v7 = -2147024809;
    LODWORD(v242) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LODWORD(v244) = a2;
      LogAdapter::Logger::LogNumObjects<long>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Invalid property query on session property: {}",
        (__int64)&v244);
      *(_QWORD *)v229 = &v242;
      LOBYTE(v106) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v106,
        3,
        (unsigned int)": {}",
        (__int64)v229);
    }
    v9 = 681;
    goto LABEL_9;
  }
  v239 = 0;
  v230 = 0;
  v236 = 0;
  pv = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v250);
  v233 = 0;
  v235 = 0;
  CCbsStringArray::CCbsStringArray((CCbsStringArray *)v256);
  v234 = 0;
  ImageProcessorArchitecture = CCbsSession::GetImageProcessorArchitecture((CCbsSession *)a1);
  ProcessorArchitectureString = GetProcessorArchitectureString(ImageProcessorArchitecture, (const wchar_t **)&v239);
  v7 = ProcessorArchitectureString;
  if ( ProcessorArchitectureString < 0 )
  {
    LODWORD(v242) = ProcessorArchitectureString;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get processor architecture string");
      *(_QWORD *)v229 = &v242;
      LOBYTE(v109) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v109,
        3,
        (unsigned int)": {}",
        (__int64)v229);
    }
    v110 = 532;
LABEL_217:
    v111 = v7;
LABEL_218:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v110,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v111,
      (int)v228);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
    goto LABEL_219;
  }
  TargetWindowsDirectory = CCbsSession::GetTargetWindowsDirectory((CCbsSession *)a1, &v230);
  v7 = TargetWindowsDirectory;
  if ( TargetWindowsDirectory < 0 )
  {
    LODWORD(v242) = TargetWindowsDirectory;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get target Windows directory");
      *(_QWORD *)v229 = &v242;
      LOBYTE(v113) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v113,
        3,
        (unsigned int)": {}",
        (__int64)v229);
    }
    v110 = 536;
    goto LABEL_217;
  }
  v114 = SczAllocCombinePath2Sz(&v236, v230, L"WinSxS");
  v7 = v114;
  if ( v114 < 0 )
  {
    v111 = (unsigned int)v114;
    v110 = 538;
    goto LABEL_218;
  }
  v116 = CCbsSession::CreateServicingQuerier(a1, v115, &pv);
  v7 = v116;
  if ( v116 < 0 )
  {
    LODWORD(v242) = v116;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create servicing querier");
      *(_QWORD *)v229 = &v242;
      LOBYTE(v117) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v117,
        3,
        (unsigned int)": {}",
        (__int64)v229);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)v7,
      (int)v228);
    goto LABEL_230;
  }
  CCbsInterfaceArray<ICbsSessionObserverListener *>::CCbsInterfaceArray<ICbsSessionObserverListener *>(v253);
  v118 = PackageStoreCollectPackages(a1, 112, v253);
  v7 = v118;
  if ( v118 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v118,
      (int)v228);
    goto LABEL_234;
  }
  CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::Sort<int (*)(CCbsIdentity * const &,CCbsIdentity * const &)>(
    v253,
    ReversedCompareCCbsIdentity);
  v119 = v255;
  v245[0] = v245;
  v245[1] = v245;
  v245[2] = 0;
  v246 = 0;
  v247 = 2048;
  v120 = &v255[v254];
  while ( v119 != v120 )
  {
    v121 = *v119 + 30LL;
    v244 = v121;
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::find<wchar_t *>(
      v245,
      &v231,
      &v244);
    v122 = v231;
    if ( (void **)v231.QuadPart == v245 )
    {
      v259[0] = 0;
      v258[0] = v259;
      v258[1] = v259;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               v258,
                               v121) )
      {
        v7 = -2147024882;
        LODWORD(v242) = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
          *(_QWORD *)v229 = &v242;
          LOBYTE(v134) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v134,
            3,
            (unsigned int)": {}",
            (__int64)v229);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x234,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)0x8007000ELL,
          (int)v228);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v258);
        while ( 1 )
        {
          v135 = v245[0];
          if ( v245[0] == v245 )
            break;
          v136 = (_QWORD *)*((_QWORD *)v245[0] + 1);
          v137 = (char *)v245[0] + 24;
          v138 = *(_QWORD *)v245[0];
          *v136 = *(_QWORD *)v245[0];
          *(_QWORD *)(v138 + 8) = v136;
          utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v137);
          operator delete(v135, (const struct std::nothrow_t *)&std::nothrow);
        }
        goto LABEL_264;
      }
      utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_TryEmplace<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,>(
        v245,
        v237,
        v258);
      if ( !v238 )
      {
        v7 = -2147024882;
        LODWORD(v242) = -2147024882;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
          *(_QWORD *)v229 = &v242;
          LOBYTE(v129) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v129,
            3,
            (unsigned int)": {}",
            (__int64)v229);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x237,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
          (const char *)0x8007000ELL,
          (int)v228);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v258);
        while ( 1 )
        {
          v130 = v245[0];
          if ( v245[0] == v245 )
            break;
          v131 = (_QWORD *)*((_QWORD *)v245[0] + 1);
          v132 = (char *)v245[0] + 24;
          v133 = *(_QWORD *)v245[0];
          *v131 = *(_QWORD *)v245[0];
          *(_QWORD *)(v133 + 8) = v131;
          utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v132);
          operator delete(v130, (const struct std::nothrow_t *)&std::nothrow);
        }
        goto LABEL_264;
      }
      v122 = *(union _ULARGE_INTEGER *)v237;
      v231 = *(union _ULARGE_INTEGER *)v237;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(v258);
    }
    if ( !(unsigned __int8)utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>::_PushBackOne<CCbsIdentity * const &>(
                             v122.QuadPart + 56,
                             v119) )
    {
      v7 = -2147024882;
      LODWORD(v242) = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
        *(_QWORD *)v229 = &v242;
        LOBYTE(v139) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v139,
          3,
          (unsigned int)": {}",
          (__int64)v229);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23B,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)0x8007000ELL,
        (int)v228);
      while ( 1 )
      {
        v140 = v245[0];
        if ( v245[0] == v245 )
          break;
        v141 = (_QWORD *)*((_QWORD *)v245[0] + 1);
        v142 = (char *)v245[0] + 24;
        v143 = *(_QWORD *)v245[0];
        *v141 = *(_QWORD *)v245[0];
        *(_QWORD *)(v143 + 8) = v141;
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v142);
        operator delete(v140, (const struct std::nothrow_t *)&std::nothrow);
      }
LABEL_264:
      v246 = 0;
LABEL_265:
      utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
LABEL_234:
      CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
LABEL_230:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
      if ( pv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
LABEL_219:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
      p_pv = &v230;
LABEL_179:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(p_pv);
      goto LABEL_71;
    }
    ++v119;
  }
  v123 = (__int64 *)off_1802E1430;
  do
  {
    v231.QuadPart = 0;
    v244 = 0;
    v124 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v231);
    CbsIdentity = CreateCbsIdentity(v124);
    if ( CbsIdentity < 0 )
    {
      LODWORD(v242) = CbsIdentity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create cbs identity");
        *(_QWORD *)v237 = &v242;
        LOBYTE(v181) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v181,
          3,
          (unsigned int)": {}",
          (__int64)v237);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x243,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)CbsIdentity,
        (int)v228);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v244);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v231);
      while ( 1 )
      {
        v182 = v245[0];
        if ( v245[0] == v245 )
          break;
        v183 = (_QWORD *)*((_QWORD *)v245[0] + 1);
        v184 = (char *)v245[0] + 24;
        v185 = *(_QWORD *)v245[0];
        *v183 = *(_QWORD *)v245[0];
        *(_QWORD *)(v185 + 8) = v183;
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v184);
        operator delete(v182, (const struct std::nothrow_t *)&std::nothrow);
      }
      goto LABEL_349;
    }
    LODWORD(v228) = 0;
    CbsIdentity = (*(__int64 (__fastcall **)(union _ULARGE_INTEGER, __int64, const wchar_t *, wchar_t *))(*(_QWORD *)v231.QuadPart + 48LL))(
                    v231,
                    *v123,
                    L"31bf3856ad364e35",
                    v239);
    if ( CbsIdentity < 0 )
    {
      LODWORD(v242) = CbsIdentity;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to parse identity: {}",
          (__int64)v123);
        *(_QWORD *)v237 = &v242;
        LOBYTE(v176) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v176,
          3,
          (unsigned int)": {}",
          (__int64)v237);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24C,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
        (const char *)(unsigned int)CbsIdentity,
        (int)v228);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v244);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v231);
      while ( 1 )
      {
        v177 = v245[0];
        if ( v245[0] == v245 )
          break;
        v178 = (_QWORD *)*((_QWORD *)v245[0] + 1);
        v179 = (char *)v245[0] + 24;
        v180 = *(_QWORD *)v245[0];
        *v178 = *(_QWORD *)v245[0];
        *(_QWORD *)(v180 + 8) = v178;
        utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v179);
        operator delete(v177, (const struct std::nothrow_t *)&std::nothrow);
      }
LABEL_349:
      v246 = 0;
      utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
      CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
      CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
      if ( pv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
      v7 = CbsIdentity;
      goto LABEL_71;
    }
    *(_QWORD *)v241 = v231.QuadPart + 30;
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::find<wchar_t *>(
      v245,
      v240,
      v241);
    if ( *(void ***)v240 != v245 )
    {
      v126 = *(const struct CCbsIdentity ***)(*(_QWORD *)v240 + 56LL);
      v127 = *(const struct CCbsIdentity ***)(*(_QWORD *)v240 + 64LL);
      while ( v126 != v127 )
      {
        v128 = *v126;
        v241[0] = 4096;
        CbsIdentity = PackageStoreQueryPackageAttributes(
                        (struct CCbsSession *)a1,
                        v128,
                        (enum CbsState *)v241,
                        0,
                        &v233,
                        0);
        if ( CbsIdentity < 0 )
        {
          LODWORD(v242) = CbsIdentity;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v240 = GetFastCbsIdentityString(*v126);
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to call PackageStoreQueryPackageAttributes for package: {}",
              (__int64)v240);
            *(_QWORD *)v229 = &v242;
            LOBYTE(v156) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v156,
              3,
              (unsigned int)": {}",
              (__int64)v229);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x263,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
            (const char *)(unsigned int)CbsIdentity,
            (int)v228);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v244);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v231);
          while ( 1 )
          {
            v157 = v245[0];
            if ( v245[0] == v245 )
              break;
            v158 = (_QWORD *)*((_QWORD *)v245[0] + 1);
            v159 = (char *)v245[0] + 24;
            v160 = *(_QWORD *)v245[0];
            *v158 = *(_QWORD *)v245[0];
            *(_QWORD *)(v160 + 8) = v158;
            utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>(v159);
            operator delete(v157, (const struct std::nothrow_t *)&std::nothrow);
          }
          goto LABEL_349;
        }
        if ( v241[0] == 64 || v241[0] == 112 || v241[0] == 128 )
        {
          Windows::AutoComPtr<CCbsPublicSession>::TakeReference(&v244, *v126);
          *(_QWORD *)v241 = v233;
          v144 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v250, v241);
          v7 = v144;
          if ( v144 >= 0 )
          {
            v233 = 0;
            break;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26D,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
            (const char *)(unsigned int)v144,
            (int)v228);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v244);
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v231);
          utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v245);
          goto LABEL_265;
        }
        ++v126;
      }
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v244);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v231);
    ++v123;
  }
  while ( v123 != ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EN__0GB__0GJ__0GO__0EP__0FD__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B );
  v145 = v252;
  v146 = pv;
  v147.QuadPart = (ULONGLONG)&v252[v251];
  *(union _ULARGE_INTEGER *)v237 = v147;
  if ( v252 != (__int64 *)v147.QuadPart )
  {
    while ( 1 )
    {
      v148 = *v145;
      pv = 0;
      LOWORD(v241[0]) = 0;
      v228 = v241;
      v149 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, LPVOID *))(*(_QWORD *)v146 + 48LL))(
               v146,
               1,
               v148,
               &pv);
      if ( v149 < 0 )
        break;
      v150 = (wchar_t *)pv;
      v239 = (wchar_t *)((char *)pv + 8 * LOWORD(v241[0]));
      if ( pv != v239 )
      {
        while ( 2 )
        {
          CCbsStringArray::CCbsStringArray((CCbsStringArray *)v260);
          v152 = SczAllocCombinePath2Sz(&v235, v236, *(_QWORD *)v150);
          if ( v152 < 0 )
          {
            LODWORD(v242) = v152;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to create path to component: {}",
                (__int64)v150);
              *(_QWORD *)v237 = &v242;
              LOBYTE(v169) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v169,
                3,
                (unsigned int)": {}",
                (__int64)v237);
            }
            v168 = 649;
            goto LABEL_316;
          }
          v153 = v235;
          v152 = CbsEnumFiles(v151, v235, L"*.XML", v260);
          if ( v152 < 0 )
          {
            LODWORD(v242) = v152;
            if ( LogAdapter::g_Logger )
            {
              *(_QWORD *)v237 = v153;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed directory walk on {}",
                (__int64)v237);
              *(_QWORD *)v240 = &v242;
              LOBYTE(v167) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v167,
                3,
                (unsigned int)": {}",
                (__int64)v240);
            }
            v168 = 654;
LABEL_316:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v168,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
              (const char *)(unsigned int)v152,
              (int)v228);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v260);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v245);
            utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
            CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
            if ( v146 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v146 + 16LL))(v146);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
            v7 = v152;
            goto LABEL_71;
          }
          v154 = v262;
          v155 = &v262[v261];
          while ( v154 != v155 )
          {
            v161 = *v154;
            v244 = 0;
            v162 = SczAllocCombinePath2Sz(&v244, v153, v161);
            if ( v162 < 0 )
            {
              LODWORD(v242) = v162;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to create path to component file: {}",
                  (__int64)v154);
                *(_QWORD *)v237 = &v242;
                LOBYTE(v166) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v166,
                  3,
                  (unsigned int)": {}",
                  (__int64)v237);
              }
              v165 = 661;
              goto LABEL_305;
            }
            *(_QWORD *)v240 = v244;
            v162 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v256, v240);
            if ( v162 < 0 )
            {
              v165 = 663;
LABEL_305:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v165,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
                (const char *)(unsigned int)v162,
                (int)v228);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v244);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v260);
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v245);
              utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
              CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
              CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
              if ( v146 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v146 + 16LL))(v146);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
              v7 = v162;
              goto LABEL_71;
            }
            v244 = 0;
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v244);
            ++v154;
          }
          CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v260);
          v150 += 4;
          if ( v150 != v239 )
            continue;
          break;
        }
        v150 = (wchar_t *)pv;
        v147 = *(union _ULARGE_INTEGER *)v237;
      }
      if ( v150 )
      {
        CoTaskMemFree(v150);
        pv = 0;
      }
      if ( ++v145 == (__int64 *)v147.QuadPart )
      {
        v3 = *(_QWORD **)v229;
        goto LABEL_296;
      }
    }
    LODWORD(v242) = v149;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to query components of package manifest: {}",
        (__int64)v145);
      *(_QWORD *)v237 = &v242;
      LOBYTE(v170) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v170,
        3,
        (unsigned int)": {}",
        (__int64)v237);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v149,
      (int)v228);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    goto LABEL_325;
  }
LABEL_296:
  if ( !v257 )
  {
    v149 = -2146498549;
    LODWORD(v244) = -2146498549;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Target image does not have required UUP metadata");
      *(_QWORD *)v237 = &v244;
      LOBYTE(v163) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v163,
        3,
        (unsigned int)": {}",
        (__int64)v237);
    }
    v164 = 669;
LABEL_300:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v164,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v149,
      (int)v228);
LABEL_325:
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v245);
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
    CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
    if ( v146 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v146 + 16LL))(v146);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
    v171 = &v230;
    goto LABEL_366;
  }
  CCbsArrayBase<wchar_t *,CCbsStringArray>::Sort<int (*)(wchar_t * const &,wchar_t * const &)>(v256);
  v172 = CCbsStringArray::SaveAsStringList((CCbsStringArray *)v256, L";", &v234);
  v149 = v172;
  if ( v172 < 0 )
  {
    LODWORD(v242) = v172;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
      *(_QWORD *)v237 = &v242;
      LOBYTE(v173) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v173,
        3,
        (unsigned int)": {}",
        (__int64)v237);
    }
    v164 = 674;
    goto LABEL_300;
  }
  v174 = SczPublicAllocFromSz(&v242, v232, v234);
  v175 = v174;
  if ( v174 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionproperties.cpp",
      (const char *)(unsigned int)v174,
      (int)v228);
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v245);
    utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
    CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
    CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
    if ( v146 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v146 + 16LL))(v146);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v230);
    v7 = v175;
    goto LABEL_71;
  }
  utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::vector<CCbsIdentity *,utl::allocator<CCbsIdentity *>>>>,0>::_ClearList(v245);
  utl::_HashTable<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>,tlx::istring_hash_ascii,tlx::istring_equal_to_ascii,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,CCbsSession::PlannedParentState>>,0>::_FreeBuckets(v245);
  CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>::~CCbsArrayBase<CCbsIdentity *,CCbsInterfaceArray<CCbsIdentity *>>(v253);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v234);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v256);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v235);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v233);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v250);
  if ( v146 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v146 + 16LL))(v146);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v236);
  v93 = &v230;
LABEL_183:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v93);
LABEL_70:
  v7 = 0;
  *v3 = v242;
LABEL_71:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v232);
  return v7;
}

```

## disassembly

```asm
0x1801c4b98  mov     [rsp-8+arg_18], rbx
0x1801c4b9d  push    rbp
0x1801c4b9e  push    rsi
0x1801c4b9f  push    rdi
0x1801c4ba0  push    r12
0x1801c4ba2  push    r13
0x1801c4ba4  push    r14
0x1801c4ba6  push    r15
0x1801c4ba8  lea     rbp, [rsp-170h]
0x1801c4bb0  sub     rsp, 270h
0x1801c4bb7  mov     rax, cs:__security_cookie
0x1801c4bbe  xor     rax, rsp
0x1801c4bc1  mov     [rbp+1A0h+var_40], rax
0x1801c4bc8  xor     r13d, r13d
0x1801c4bcb  mov     qword ptr [rsp+2A0h+var_260], r8
0x1801c4bd0  mov     r12, r8
0x1801c4bd3  mov     [rbp+1A0h+var_1F8], r13
0x1801c4bd7  mov     edi, edx
0x1801c4bd9  mov     [rsp+2A0h+var_248], r13
0x1801c4bde  mov     rsi, rcx
0x1801c4be1  xor     edx, edx; Val
0x1801c4be3  lea     r8d, [r13+40h]; Size
0x1801c4be7  lea     rcx, [rbp+1A0h+var_80]; void *
0x1801c4bee  call    memset_0
0x1801c4bf3  mov     rcx, rsi; this
0x1801c4bf6  call    ?CheckInitialized@CCbsSession@@QEAAJXZ; CCbsSession::CheckInitialized(void)
0x1801c4bfb  mov     ebx, eax
0x1801c4bfd  test    eax, eax
0x1801c4bff  jns     short loc_1801C4C57
0x1801c4c01  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c08  mov     [rbp+1A0h+var_200], eax
0x1801c4c0b  test    rcx, rcx
0x1801c4c0e  jz      short loc_1801C4C50
0x1801c4c10  lea     edi, [r13+3]
0x1801c4c14  xor     edx, edx
0x1801c4c16  mov     r8d, edi
0x1801c4c19  lea     r9, aCannotGetsessi; "Cannot GetSessionID on a session that h"...
0x1801c4c20  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4c25  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c2c  lea     rax, [rbp+1A0h+var_200]
0x1801c4c30  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4c35  lea     r9, asc_1802EE7AC; ": {}"
0x1801c4c3c  lea     rax, [rsp+2A0h+var_260]
0x1801c4c41  mov     r8d, edi
0x1801c4c44  mov     dl, 1
0x1801c4c46  mov     [rsp+2A0h+var_280], rax
0x1801c4c4b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4c50  mov     edx, 6Ch ; 'l'
0x1801c4c55  jmp     short loc_1801C4CC4
0x1801c4c57  lea     rcx, [rsp+2A0h+var_248]
0x1801c4c5c  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801c4c61  mov     rcx, rax
0x1801c4c64  call    GetTaskAllocator
0x1801c4c69  mov     ebx, eax
0x1801c4c6b  test    eax, eax
0x1801c4c6d  jns     short loc_1801C4CDF
0x1801c4c6f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c76  mov     [rbp+1A0h+var_200], eax
0x1801c4c79  test    rcx, rcx
0x1801c4c7c  jz      short loc_1801C4CBF
0x1801c4c7e  mov     edi, 3
0x1801c4c83  lea     r9, aFailedToGetTas; "Failed to get task allocator."
0x1801c4c8a  mov     r8d, edi
0x1801c4c8d  xor     edx, edx
0x1801c4c8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4c94  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4c9b  lea     rax, [rbp+1A0h+var_200]
0x1801c4c9f  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4ca4  lea     r9, asc_1802EE7AC; ": {}"
0x1801c4cab  lea     rax, [rsp+2A0h+var_260]
0x1801c4cb0  mov     r8d, edi
0x1801c4cb3  mov     dl, 1
0x1801c4cb5  mov     [rsp+2A0h+var_280], rax; int
0x1801c4cba  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4cbf  mov     edx, 6Dh ; 'm'; void *
0x1801c4cc4  mov     r9d, ebx; char *
0x1801c4cc7  mov     rcx, [rbp+1A8h]; this
0x1801c4cce  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1801c4cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c4cda  jmp     loc_1801C5090
0x1801c4cdf  cmp     edi, 0Dh
0x1801c4ce2  jg      loc_1801C4D8F
0x1801c4ce8  jz      short loc_1801C4D09
0x1801c4cea  mov     ecx, edi
0x1801c4cec  sub     ecx, 8
0x1801c4cef  jz      short loc_1801C4D09
0x1801c4cf1  sub     ecx, 1
0x1801c4cf4  jz      short loc_1801C4D09
0x1801c4cf6  sub     ecx, 1
0x1801c4cf9  jz      short loc_1801C4D09
0x1801c4cfb  sub     ecx, 1
0x1801c4cfe  jz      short loc_1801C4D09
0x1801c4d00  cmp     ecx, 1
0x1801c4d03  jnz     loc_1801C4E29
0x1801c4d09  cmp     [rsi+4D0h], r13
0x1801c4d10  jnz     loc_1801C4E1A
0x1801c4d16  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4d1d  test    rcx, rcx
0x1801c4d20  jz      short loc_1801C4D6A
0x1801c4d22  mov     edi, 3
0x1801c4d27  lea     r9, aFailedGettingP_0; "Failed getting property.  Analysis must"...
0x1801c4d2e  mov     r8d, edi
0x1801c4d31  xor     edx, edx
0x1801c4d33  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4d38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4d3f  lea     rax, [rbp+1A0h+var_200]
0x1801c4d43  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4d48  lea     r9, a0; ": {0}"
0x1801c4d4f  lea     rax, [rsp+2A0h+var_260]
0x1801c4d54  mov     [rbp+1A0h+var_200], 80070490h
0x1801c4d5b  mov     r8d, edi
0x1801c4d5e  mov     [rsp+2A0h+var_280], rax; unsigned int
0x1801c4d63  mov     dl, 1
0x1801c4d65  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4d6a  mov     r9d, 490h; char *
0x1801c4d70  mov     edx, 7Eh ; '~'; void *
0x1801c4d75  mov     rcx, [rbp+1A8h]; this
0x1801c4d7c  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1801c4d83  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801c4d88  mov     ebx, eax
0x1801c4d8a  jmp     loc_1801C5090
0x1801c4d8f  mov     ecx, edi
0x1801c4d91  sub     ecx, 0Eh
0x1801c4d94  jz      loc_1801C4D09
0x1801c4d9a  sub     ecx, 1
0x1801c4d9d  jz      short loc_1801C4DAE
0x1801c4d9f  sub     ecx, 8
0x1801c4da2  jz      short loc_1801C4DAE
0x1801c4da4  sub     ecx, 1
0x1801c4da7  jz      short loc_1801C4DAE
0x1801c4da9  cmp     ecx, 1
0x1801c4dac  jnz     short loc_1801C4E1A
0x1801c4dae  cmp     [rsi+40Ch], r13d
0x1801c4db5  jnz     short loc_1801C4E1A
0x1801c4db7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4dbe  test    rcx, rcx
0x1801c4dc1  jz      short loc_1801C4E0B
0x1801c4dc3  mov     edi, 3
0x1801c4dc8  lea     r9, aFailedGettingP_9; "Failed getting property. Session must b"...
0x1801c4dcf  mov     r8d, edi
0x1801c4dd2  xor     edx, edx
0x1801c4dd4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801c4dd9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801c4de0  lea     rax, [rbp+1A0h+var_200]
0x1801c4de4  mov     qword ptr [rsp+2A0h+var_260], rax
0x1801c4de9  lea     r9, a0; ": {0}"
0x1801c4df0  lea     rax, [rsp+2A0h+var_260]
0x1801c4df5  mov     [rbp+1A0h+var_200], 80070032h
0x1801c4dfc  mov     r8d, edi
0x1801c4dff  mov     [rsp+2A0h+var_280], rax
0x1801c4e04  mov     dl, 1
0x1801c4e06  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801c4e0b  mov     r9d, 32h ; '2'
0x1801c4e11  lea     edx, [r9+56h]
0x1801c4e15  jmp     loc_1801C4D75
0x1801c4e1a  cmp     edi, 10h
0x1801c4e1d  jg      loc_1801C5839
0x1801c4e23  jz      loc_1801C5BEF
0x1801c4e29  cmp     edi, 8
0x1801c4e2c  jg      loc_1801C5172
0x1801c4e32  jz      loc_1801C50C7
0x1801c4e38  mov     ecx, edi
0x1801c4e3a  sub     ecx, 1
0x1801c4e3d  jz      loc_1801C5013
0x1801c4e43  sub     ecx, 1
0x1801c4e46  jz      loc_1801C4FD0
0x1801c4e4c  sub     ecx, 1
0x1801c4e4f  jz      loc_1801C4F77
0x1801c4e55  sub     ecx, 1
0x1801c4e58  jz      loc_1801C4F4B
0x1801c4e5e  sub     ecx, 1
0x1801c4e61  jz      loc_1801C4F01
0x1801c4e67  sub     ecx, 1
0x1801c4e6a  jz      short loc_1801C4EA1
0x1801c4e6c  cmp     ecx, 1
0x1801c4e6f  jnz     loc_1801C5E72
0x1801c4e75  mov     rdx, [rsp+2A0h+var_248]
0x1801c4e7a  lea     r8, a0_1; "0"
0x1801c4e81  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4e85  call    SczPublicAllocFromSz
0x1801c4e8a  mov     ebx, eax
0x1801c4e8c  test    eax, eax
0x1801c4e8e  jns     loc_1801C5085
0x1801c4e94  mov     r9d, eax
0x1801c4e97  mov     edx, 0C8h
0x1801c4e9c  jmp     loc_1801C4CC7
0x1801c4ea1  lea     r8, [rbp+1A0h+var_200]; int *
0x1801c4ea5  mov     [rbp+1A0h+var_200], r13d
0x1801c4ea9  xor     edx, edx; int
0x1801c4eab  mov     rcx, rsi; struct CCbsSession *
0x1801c4eae  call    ?CheckStoreCorruptionFlag@@YAJPEAVCCbsSession@@HPEAH@Z; CheckStoreCorruptionFlag(CCbsSession *,int,int *)
0x1801c4eb3  lea     r8, aUnableToGetand; "Unable to GetAndResetCorruptionFlag"
0x1801c4eba  mov     edx, eax
0x1801c4ebc  mov     ecx, 1
0x1801c4ec1  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1801c4ec6  cmp     [rbp+1A0h+var_200], r13d
0x1801c4eca  lea     rcx, a0_1; "0"
0x1801c4ed1  mov     rdx, [rsp+2A0h+var_248]
0x1801c4ed6  lea     r8, a1; "1"
0x1801c4edd  cmovz   r8, rcx
0x1801c4ee1  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4ee5  call    SczPublicAllocFromSz
0x1801c4eea  mov     ebx, eax
0x1801c4eec  test    eax, eax
0x1801c4eee  jns     loc_1801C5085
0x1801c4ef4  mov     r9d, eax
0x1801c4ef7  mov     edx, 0C2h
0x1801c4efc  jmp     loc_1801C4CC7
0x1801c4f01  lea     rdx, [rsi+248h]; struct AutoCritSec *
0x1801c4f08  mov     r8b, 1; bool
0x1801c4f0b  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c4f0f  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801c4f14  mov     rax, [rsi+460h]
0x1801c4f1b  lea     r8, qword_1802EB518
0x1801c4f22  mov     rdx, [rsp+2A0h+var_248]
0x1801c4f27  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4f2b  test    rax, rax
0x1801c4f2e  cmovnz  r8, rax
0x1801c4f32  call    SczPublicAllocFromSz
0x1801c4f37  mov     ebx, eax
0x1801c4f39  test    eax, eax
0x1801c4f3b  jns     loc_1801C507C
0x1801c4f41  mov     edx, 0B6h
0x1801c4f46  jmp     loc_1801C505B
0x1801c4f4b  mov     rdx, [rsp+2A0h+var_248]
0x1801c4f50  lea     r8, a1; "1"
0x1801c4f57  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4f5b  call    SczPublicAllocFromSz
0x1801c4f60  mov     ebx, eax
0x1801c4f62  test    eax, eax
0x1801c4f64  jns     loc_1801C5085
0x1801c4f6a  mov     r9d, eax
0x1801c4f6d  mov     edx, 0AFh
0x1801c4f72  jmp     loc_1801C4CC7
0x1801c4f77  lea     r8, [rbp+1A0h+var_200]; unsigned int *
0x1801c4f7b  mov     [rbp+1A0h+var_200], r13d
0x1801c4f7f  lea     rdx, aUnserviceable; "Unserviceable"
0x1801c4f86  mov     rcx, rsi; struct CCbsSession *
0x1801c4f89  call    ?PackageStoreGetProperty@@YAJPEAVCCbsSession@@PEB_WPEAK@Z; PackageStoreGetProperty(CCbsSession *,wchar_t const *,ulong *)
0x1801c4f8e  mov     edx, [rbp+1A0h+var_200]
0x1801c4f91  lea     rcx, a0_1; "0"
0x1801c4f98  test    eax, eax
0x1801c4f9a  lea     r8, a1; "1"
0x1801c4fa1  cmovs   edx, r13d
0x1801c4fa5  test    edx, edx
0x1801c4fa7  mov     rdx, [rsp+2A0h+var_248]
0x1801c4fac  cmovz   r8, rcx
0x1801c4fb0  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4fb4  call    SczPublicAllocFromSz
0x1801c4fb9  mov     ebx, eax
0x1801c4fbb  test    eax, eax
0x1801c4fbd  jns     loc_1801C5085
0x1801c4fc3  mov     r9d, eax
0x1801c4fc6  mov     edx, 0A6h
0x1801c4fcb  jmp     loc_1801C4CC7
0x1801c4fd0  lea     rdx, [rsi+248h]; struct AutoCritSec *
0x1801c4fd7  mov     r8b, 1; bool
0x1801c4fda  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c4fde  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801c4fe3  mov     rax, [rsi+430h]
0x1801c4fea  lea     r8, qword_1802EB518
0x1801c4ff1  mov     rdx, [rsp+2A0h+var_248]
0x1801c4ff6  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c4ffa  test    rax, rax
0x1801c4ffd  cmovnz  r8, rax
0x1801c5001  call    SczPublicAllocFromSz
0x1801c5006  mov     ebx, eax
0x1801c5008  test    eax, eax
0x1801c500a  jns     short loc_1801C507C
0x1801c500c  mov     edx, 9Bh
0x1801c5011  jmp     short loc_1801C505B
0x1801c5013  lea     rdx, [rsi+248h]; struct AutoCritSec *
0x1801c501a  mov     r8b, 1; bool
0x1801c501d  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c5021  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1801c5026  mov     rcx, rsi; this
0x1801c5029  call    ?IsRebootRequired@CCbsSession@@AEAAHXZ; CCbsSession::IsRebootRequired(void)
0x1801c502e  mov     rdx, [rsp+2A0h+var_248]
0x1801c5033  lea     rcx, a0_1; "0"
0x1801c503a  test    eax, eax
0x1801c503c  lea     r8, a1; "1"
0x1801c5043  cmovz   r8, rcx
0x1801c5047  lea     rcx, [rbp+1A0h+var_1F8]
0x1801c504b  call    SczPublicAllocFromSz
0x1801c5050  mov     ebx, eax
0x1801c5052  test    eax, eax
0x1801c5054  jns     short loc_1801C507C
0x1801c5056  mov     edx, 94h; void *
0x1801c505b  mov     r9d, eax; char *
0x1801c505e  mov     rcx, [rbp+1A8h]; this
0x1801c5065  lea     r8, aOnecoreBaseCbs_67; "onecore\\base\\cbs\\core\\cbssessionpro"...
0x1801c506c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c5071  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c5075  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801c507a  jmp     short loc_1801C5090
0x1801c507c  lea     rcx, [rbp+1A0h+var_1B8]; this
0x1801c5080  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1801c5085  mov     rax, [rbp+1A0h+var_1F8]
0x1801c5089  mov     ebx, r13d
0x1801c508c  mov     [r12], rax
  ... truncated ...
```
