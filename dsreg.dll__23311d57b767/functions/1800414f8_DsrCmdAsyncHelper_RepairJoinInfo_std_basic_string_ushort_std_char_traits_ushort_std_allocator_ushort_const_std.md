# DsrCmdAsyncHelper::RepairJoinInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,struct_dsreg_server_response *)

- ea: `0x1800414f8`
- end: `0x1800420e8`
- name: `?RepairJoinInfo@DsrCmdAsyncHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUstruct_dsreg_server_response@@@Z`
- size: `3056`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18009b940`

## callees

- `0x1800084f4`
- `0x18000ab70`
- `0x18000bd20`
- `0x180012948`
- `0x180012c7c`
- `0x18001ebe4`
- `0x180038e44`
- `0x1800414f8`
- `0x18004271c`
- `0x180046ae8`
- `0x180046b3c`
- `0x18006850c`
- `0x1800aadc4`
- `0x1800aae0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041996`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041996`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041aaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800420a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800420a9`
- `netutils!NetApiBufferFree` at `0x1800420ba`
- `netutils!NetApiBufferFree` at `0x1800420ba`

## string_xrefs

- `0x180042068`: `The device is not joined to tenant %s. Nothing to repair. Exiting...\n`
- `0x180042088`: `The device is not joined to tenant %s. Nothing to repair. Exiting...\n`
- `0x18004157b`: `DsrCmdAsyncHelper::RepairJoinInfo`
- `0x18004169d`: `DsrCmdAsyncHelper::RepairJoinInfo`
- `0x180042010`: `The device is not joined to AAD. Nothing to repair. Exiting...\n`
- `0x180042023`: `The device is not joined to AAD. Nothing to repair. Exiting...\n`
- `0x1800415e0`: `There are multiple AAD accounts. Please specify one of the following tenant IDs using /RepairRegistry <tenantId>.\n`
- `0x1800415f3`: `There are multiple AAD accounts. Please specify one of the following tenant IDs using /RepairRegistry <tenantId>.\n`
- `0x1800418c3`: `To repair hybrid joined device, you need to run the process as "NT AUTHORITY\SYSTEM".\n`
- `0x1800418d6`: `To repair hybrid joined device, you need to run the process as "NT AUTHORITY\SYSTEM".\n`
- `0x1800419c6`: `%s: CreateEventW failed with error code 0x%08x.\n`
- `0x180041a95`: `%s: DiscoverApi::BeginRepairJoinInfo failed with error code 0x%08x.\n`
- `0x180041921`: `Failed to determine if the process has administrator privileges: 0x%08x.\n`
- `0x180041934`: `Failed to determine if the process has administrator privileges: 0x%08x.\n`
- `0x18004196d`: `To repair Azure AD joined device, you need to run the process as administrator.\n`
- `0x180041980`: `To repair Azure AD joined device, you need to run the process as administrator.\n`
- `0x180041b55`: `%s: WaitForSingleObject failed for DiscoverApi::BeginRepairJoinInfo.\n`
- `0x180041ad7`: `%s: WaitForSingleObject returned unexpected wait status 0x%08x for DiscoverApi::BeginRepairJoinInfo.\n`
- `0x180041c7d`: `%s: RepairJoinInfoCallback failed with error code 0x%08x.\n`
- `0x180041c10`: `%s: WaitForSingleObject timed out for DiscoverApi::BeginRepairJoinInfo.\n`
- `0x180041d0e`: `Registry repair failed with error code 0x%08x.\n`
- `0x180041d23`: `Registry repair failed with error code 0x%08x.\n`
- `0x180041bdf`: `Registry repair succeeded.\n`
- `0x180041bf2`: `Registry repair succeeded.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DsrCmdAsyncHelper::RepairJoinInfo(_QWORD *a1, _QWORD *a2, struct struct_dsreg_server_response *a3)
{
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int JoinInfo; // edi
  _BYTE **CurrentRef; // rax
  const wchar_t *v11; // rbx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int i; // esi
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  _QWORD *v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  _QWORD *v39; // rax
  __int64 v40; // rdx
  _QWORD *v41; // rax
  __int64 v42; // rdx
  _QWORD *v43; // rbx
  __int64 v44; // rax
  _QWORD *v45; // r8
  __int64 v46; // rdx
  __int64 v47; // rcx
  _QWORD *v48; // rax
  __int64 v49; // rdx
  _QWORD *v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  bool v53; // zf
  __int64 v54; // rdx
  __int64 v55; // rcx
  _QWORD *v56; // rax
  __int64 v57; // rdx
  _QWORD *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  _QWORD *v61; // rax
  __int64 v62; // rdx
  _QWORD *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rcx
  _QWORD *v68; // rax
  __int64 v69; // rdx
  _QWORD *v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rax
  _QWORD *v73; // rax
  __int64 v74; // rdx
  _QWORD *v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rax
  signed int LastError; // eax
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rdx
  _QWORD *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rax
  __int64 v88; // rdx
  __int64 v89; // rcx
  _QWORD *v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rcx
  DWORD v93; // eax
  DWORD v94; // ebx
  __int64 v95; // rdx
  __int64 v96; // rcx
  _QWORD *v97; // rax
  __int64 v98; // rdx
  _QWORD *v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rax
  signed int v102; // eax
  __int64 v103; // rdx
  __int64 v104; // rcx
  __int64 v105; // rdx
  __int64 v106; // rcx
  _QWORD *v107; // rax
  __int64 v108; // rdx
  _QWORD *v109; // rax
  __int64 v110; // rcx
  __int64 v111; // rax
  _QWORD *v112; // rax
  __int64 v113; // rdx
  _QWORD *v114; // rax
  __int64 v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // rcx
  _QWORD *v119; // rax
  __int64 v120; // rdx
  _QWORD *v121; // rax
  __int64 v122; // rcx
  __int64 v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rcx
  _QWORD *v126; // rax
  __int64 v127; // rdx
  _QWORD *v128; // rax
  __int64 v129; // rdx
  __int64 v130; // rax
  _QWORD *v131; // rax
  __int64 v132; // rdx
  _QWORD *v133; // rax
  __int64 v134; // rcx
  __int64 v135; // rax
  __int64 v136; // rdx
  __int64 v137; // rcx
  _QWORD *v138; // rax
  __int64 v139; // rdx
  const WCHAR *v140; // rsi
  _QWORD *v141; // rax
  __int64 v142; // rdx
  const WCHAR *v143; // rbx
  __int64 v144; // rax
  const WCHAR *v145; // rdx
  __int64 v146; // rdx
  __int64 v147; // rcx
  _QWORD *v148; // rax
  __int64 v149; // rdx
  _QWORD *v150; // rax
  __int64 v151; // rdx
  const WCHAR *v152; // rbx
  __int64 v153; // rax
  const WCHAR *v154; // rdx
  __int64 v155; // rdx
  __int64 v156; // rcx
  _QWORD *v157; // rax
  __int64 v158; // rdx
  _QWORD *v159; // rax
  __int64 v160; // rcx
  unsigned int v161; // ebx
  __int64 v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rcx
  _QWORD *v165; // rax
  __int64 v166; // rdx
  _QWORD *v167; // rax
  __int64 v168; // rdx
  const WCHAR *v169; // rbx
  __int64 v170; // rax
  const WCHAR *v171; // rdx
  __int64 v172; // rdx
  __int64 v173; // rcx
  _QWORD *v174; // rax
  __int64 v175; // rdx
  _QWORD *v176; // rax
  __int64 v177; // rdx
  const WCHAR *v178; // rbx
  __int64 v179; // rax
  const WCHAR *v180; // rdx
  __int64 v181; // rdx
  __int64 v182; // rcx
  _QWORD *v183; // rax
  __int64 v184; // rdx
  _QWORD *v185; // rax
  __int64 v186; // rdx
  const WCHAR *v187; // rbx
  __int64 v188; // rax
  const WCHAR *v189; // rdx
  __int64 v190; // rdx
  __int64 v191; // rcx
  _QWORD *v192; // rax
  __int64 v193; // rdx
  _QWORD *v194; // rax
  __int64 v195; // rdx
  const WCHAR *v196; // rbx
  __int64 v197; // rax
  _QWORD *v198; // rax
  __int64 v199; // rdx
  _QWORD *v200; // rax
  __int64 v201; // rcx
  __int64 v202; // rax
  _QWORD *v203; // rax
  __int64 v204; // rdx
  _QWORD *v205; // rax
  __int64 v206; // rdx
  _QWORD *v207; // rsi
  __int64 v208; // rax
  _QWORD *v210; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v211[3]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v212; // [rsp+60h] [rbp-19h] BYREF
  __int128 v213; // [rsp+68h] [rbp-11h] BYREF
  __int128 v214; // [rsp+78h] [rbp-1h]
  __int128 v215; // [rsp+88h] [rbp+Fh]
  const WCHAR *v216; // [rsp+98h] [rbp+1Fh]
  HANDLE hHandle; // [rsp+A0h] [rbp+27h]
  WINBOOL IsMember; // [rsp+E0h] [rbp+67h] BYREF
  void *Block; // [rsp+F8h] [rbp+7Fh] BYREF

  v5 = a1;
  Block = 0;
  v212 = 0;
  v213 = 0;
  v214 = 0;
  v215 = 0;
  v216 = 0;
  hHandle = 0;
  v211[0] = 0;
  if ( a1[3] <= 7u )
    v6 = a1;
  else
    v6 = (_QWORD *)*a1;
  v211[1] = v6;
  v211[2] = 0;
  JoinInfo = DsrGetJoinInfoEx(3, v211, &Block);
  if ( (JoinInfo & 0x80000000) != 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v8, v7);
    v11 = L"%s: DsrGetJoinInfoEx failed with error code 0x%08x.\n";
    goto LABEL_106;
  }
  if ( Block && *((_DWORD *)Block + 4) && *((_QWORD *)Block + 1) )
  {
    if ( *((_DWORD *)Block + 4) > 1u )
    {
      v12 = (_QWORD *)CmdOptions::GetCurrentRef(v8, v7);
      if ( *(_BYTE *)(*v12 + 12LL) )
      {
        v14 = (_QWORD *)CmdOptions::GetCurrentRef(*v12, v13);
        if ( *(_QWORD *)(*v14 + 184LL) )
        {
          v16 = CmdOptions::GetCurrentRef(v15, *v14);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v16 + 184LL),
            L"There are multiple AAD accounts. Please specify one of the following tenant IDs using /RepairRegistry <tenantId>.\n");
        }
      }
      wprintf(
        L"There are multiple AAD accounts. Please specify one of the following tenant IDs using /RepairRegistry <tenantId>.\n");
      for ( i = 0; i < *((_DWORD *)Block + 4); ++i )
      {
        v20 = (_QWORD *)CmdOptions::GetCurrentRef(v18, v17);
        if ( *(_BYTE *)(*v20 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v20, v21) + 184LL) )
        {
          v22 = 336LL * i;
          v23 = *((_QWORD *)Block + 1);
          v24 = *(_QWORD *)(v22 + v23 + 32);
          v25 = CmdOptions::GetCurrentRef(v23, v22);
          fwprintf_s(*(FILE *const *)(*(_QWORD *)v25 + 184LL), L"%s\n", v24);
        }
        wprintf(L"%s\n", *(_QWORD *)(336LL * i + *((_QWORD *)Block + 1) + 32));
      }
      goto LABEL_174;
    }
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v8, v7) )
    {
      wprintf(L"%s: Tenant ID: %s\n", L"DsrCmdAsyncHelper::RepairJoinInfo", *(_QWORD *)(*((_QWORD *)Block + 1) + 32LL));
      v28 = (_QWORD *)CmdOptions::GetCurrentRef(v27, v26);
      if ( *(_BYTE *)(*v28 + 12LL) )
      {
        if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v28, v29) + 184LL) )
        {
          v31 = *((_QWORD *)Block + 1);
          v32 = *(_QWORD *)(v31 + 32);
          v33 = CmdOptions::GetCurrentRef(v31, v30);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v33 + 184LL),
            L"%s: Tenant ID: %s\n",
            L"DsrCmdAsyncHelper::RepairJoinInfo",
            v32);
        }
      }
    }
    Logger::TraceInformation(
      L"%s: Tenant ID: %s\n",
      L"DsrCmdAsyncHelper::RepairJoinInfo",
      *(_QWORD *)(*((_QWORD *)Block + 1) + 32LL));
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v35, v34) )
    {
      v36 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
      wprintf(L"%s: Join user UPN: %s\n", L"DsrCmdAsyncHelper::RepairJoinInfo", v36);
      v39 = (_QWORD *)CmdOptions::GetCurrentRef(v38, v37);
      if ( *(_BYTE *)(*v39 + 12LL) )
      {
        v41 = (_QWORD *)CmdOptions::GetCurrentRef(*v39, v40);
        if ( *(_QWORD *)(*v41 + 184LL) )
        {
          if ( a2[3] <= 7u )
            v43 = a2;
          else
            v43 = (_QWORD *)*a2;
          v44 = CmdOptions::GetCurrentRef(*v41, v42);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v44 + 184LL),
            L"%s: Join user UPN: %s\n",
            L"DsrCmdAsyncHelper::RepairJoinInfo",
            v43);
        }
      }
    }
    if ( a2[3] <= 7u )
      v45 = a2;
    else
      v45 = (_QWORD *)*a2;
    Logger::TraceInformation(L"%s: Join user UPN: %s\n", L"DsrCmdAsyncHelper::RepairJoinInfo", v45);
    if ( **((_DWORD **)Block + 1) != 1 )
      goto LABEL_65;
    IsMember = 0;
    JoinInfo = IsLocalMachineDomainJoined(&IsMember, 0);
    if ( (JoinInfo & 0x80000000) != 0 )
    {
      v48 = (_QWORD *)CmdOptions::GetCurrentRef(v47, v46);
      if ( *(_BYTE *)(*v48 + 12LL) )
      {
        v50 = (_QWORD *)CmdOptions::GetCurrentRef(*v48, v49);
        if ( *(_QWORD *)(*v50 + 184LL) )
        {
          v52 = CmdOptions::GetCurrentRef(v51, *v50);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v52 + 184LL),
            L"Failed to determine if the device is domain joined: 0x%08x.\n",
            JoinInfo);
        }
      }
      wprintf(L"Failed to determine if the device is domain joined: 0x%08x.\n", JoinInfo);
      goto LABEL_174;
    }
    v53 = IsMember == 0;
    IsMember = 0;
    if ( !v53 )
    {
      JoinInfo = IsCurrentUserSystem(&IsMember);
      if ( (JoinInfo & 0x80000000) != 0 )
      {
        v56 = (_QWORD *)CmdOptions::GetCurrentRef(v55, v54);
        if ( *(_BYTE *)(*v56 + 12LL) )
        {
          v58 = (_QWORD *)CmdOptions::GetCurrentRef(*v56, v57);
          if ( *(_QWORD *)(*v58 + 184LL) )
          {
            v60 = CmdOptions::GetCurrentRef(v59, *v58);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v60 + 184LL),
              L"Failed to determine if the process is running as \"NT AUTHORITY\\SYSTEM\": 0x%08x.\n",
              JoinInfo);
          }
        }
        wprintf(L"Failed to determine if the process is running as \"NT AUTHORITY\\SYSTEM\": 0x%08x.\n", JoinInfo);
        goto LABEL_174;
      }
      if ( !IsMember )
      {
        v61 = (_QWORD *)CmdOptions::GetCurrentRef(v55, v54);
        if ( *(_BYTE *)(*v61 + 12LL) )
        {
          v63 = (_QWORD *)CmdOptions::GetCurrentRef(*v61, v62);
          if ( *(_QWORD *)(*v63 + 184LL) )
          {
            v65 = CmdOptions::GetCurrentRef(v64, *v63);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v65 + 184LL),
              L"To repair hybrid joined device, you need to run the process as \"NT AUTHORITY\\SYSTEM\".\n");
          }
        }
        wprintf(L"To repair hybrid joined device, you need to run the process as \"NT AUTHORITY\\SYSTEM\".\n");
LABEL_54:
        JoinInfo = -2147024891;
        goto LABEL_174;
      }
      goto LABEL_65;
    }
    JoinInfo = IsCurrentUserElevated(&IsMember);
    if ( (JoinInfo & 0x80000000) == 0 )
    {
      if ( !IsMember )
      {
        v73 = (_QWORD *)CmdOptions::GetCurrentRef(v67, v66);
        if ( *(_BYTE *)(*v73 + 12LL) )
        {
          v75 = (_QWORD *)CmdOptions::GetCurrentRef(*v73, v74);
          if ( *(_QWORD *)(*v75 + 184LL) )
          {
            v77 = CmdOptions::GetCurrentRef(v76, *v75);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v77 + 184LL),
              L"To repair Azure AD joined device, you need to run the process as administrator.\n");
          }
        }
        wprintf(L"To repair Azure AD joined device, you need to run the process as administrator.\n");
        goto LABEL_54;
      }
LABEL_65:
      hHandle = CreateEventW(0, 0, 0, 0);
      if ( !hHandle )
      {
        LastError = GetLastError();
        JoinInfo = LastError;
        if ( LastError > 0 )
          JoinInfo = (unsigned __int16)LastError | 0x80070000;
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v80, v79) )
        {
          wprintf(L"%s: CreateEventW failed with error code 0x%08x.\n", L"DsrCmdAsyncHelper::RepairJoinInfo", JoinInfo);
          v83 = (_QWORD *)CmdOptions::GetCurrentRef(v82, v81);
          if ( *(_BYTE *)(*v83 + 12LL) )
          {
            v85 = (_QWORD *)CmdOptions::GetCurrentRef(*v83, v84);
            if ( *(_QWORD *)(*v85 + 184LL) )
            {
              v87 = CmdOptions::GetCurrentRef(*v85, v86);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v87 + 184LL),
                L"%s: CreateEventW failed with error code 0x%08x.\n",
                L"DsrCmdAsyncHelper::RepairJoinInfo",
                JoinInfo);
            }
          }
        }
        Logger::TraceError(
          L"%s: CreateEventW failed with error code 0x%08x.\n",
          L"DsrCmdAsyncHelper::RepairJoinInfo",
          JoinInfo);
        goto LABEL_93;
      }
      if ( a2[3] <= 7u )
        v90 = a2;
      else
        v90 = (_QWORD *)*a2;
      v210 = v90;
      JoinInfo = DiscoverApi::BeginRepairJoinInfo(
                   **((unsigned int **)Block + 1),
                   *(_QWORD *)(*((_QWORD *)Block + 1) + 32LL),
                   (const unsigned __int16 **)((unsigned __int64)&v210 & -(__int64)(a2[2] != 0)),
                   a2[2] != 0,
                   0,
                   (unsigned int)DsrCmdAsyncHelper::RepairJoinInfoCallback,
                   (__int64)&v212);
      if ( (JoinInfo & 0x80000000) == 0 )
      {
        v93 = WaitForSingleObject(hHandle, 0x1D4C0u);
        v94 = v93;
        if ( v93 )
        {
          if ( v93 == 258 )
          {
            JoinInfo = -2147023436;
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v89, v88) )
            {
              wprintf(
                L"%s: WaitForSingleObject timed out for DiscoverApi::BeginRepairJoinInfo.\n",
                L"DsrCmdAsyncHelper::RepairJoinInfo");
              v119 = (_QWORD *)CmdOptions::GetCurrentRef(v118, v117);
              if ( *(_BYTE *)(*v119 + 12LL) )
              {
                v121 = (_QWORD *)CmdOptions::GetCurrentRef(*v119, v120);
                if ( *(_QWORD *)(*v121 + 184LL) )
                {
                  v123 = CmdOptions::GetCurrentRef(v122, *v121);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v123 + 184LL),
                    L"%s: WaitForSingleObject timed out for DiscoverApi::BeginRepairJoinInfo.\n",
                    L"DsrCmdAsyncHelper::RepairJoinInfo");
                }
              }
            }
            Logger::TraceError(
              L"%s: WaitForSingleObject timed out for DiscoverApi::BeginRepairJoinInfo.\n",
              L"DsrCmdAsyncHelper::RepairJoinInfo");
            goto LABEL_111;
          }
          if ( v93 != -1 )
          {
            JoinInfo = -2147023436;
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v89, v88) )
            {
              wprintf(
                L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DiscoverApi::BeginRepairJoinInfo.\n",
                L"DsrCmdAsyncHelper::RepairJoinInfo",
                v94);
              v97 = (_QWORD *)CmdOptions::GetCurrentRef(v96, v95);
              if ( *(_BYTE *)(*v97 + 12LL) )
              {
                v99 = (_QWORD *)CmdOptions::GetCurrentRef(*v97, v98);
                if ( *(_QWORD *)(*v99 + 184LL) )
                {
                  v101 = CmdOptions::GetCurrentRef(*v99, v100);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v101 + 184LL),
                    L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DiscoverApi::BeginRepairJoinInfo.\n",
                    L"DsrCmdAsyncHelper::RepairJoinInfo",
                    v94);
                }
              }
            }
            Logger::TraceError(
              L"%s: WaitForSingleObject returned unexpected wait status 0x%08x for DiscoverApi::BeginRepairJoinInfo.\n",
              L"DsrCmdAsyncHelper::RepairJoinInfo",
              v94);
            goto LABEL_111;
          }
          v102 = GetLastError();
          JoinInfo = v102;
          if ( v102 > 0 )
            JoinInfo = (unsigned __int16)v102 | 0x80070000;
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v104, v103) )
          {
            wprintf(
              L"%s: WaitForSingleObject failed for DiscoverApi::BeginRepairJoinInfo.\n",
              L"DsrCmdAsyncHelper::RepairJoinInfo");
            v107 = (_QWORD *)CmdOptions::GetCurrentRef(v106, v105);
            if ( *(_BYTE *)(*v107 + 12LL) )
            {
              v109 = (_QWORD *)CmdOptions::GetCurrentRef(*v107, v108);
              if ( *(_QWORD *)(*v109 + 184LL) )
              {
                v111 = CmdOptions::GetCurrentRef(v110, *v109);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v111 + 184LL),
                  L"%s: WaitForSingleObject failed for DiscoverApi::BeginRepairJoinInfo.\n",
                  L"DsrCmdAsyncHelper::RepairJoinInfo");
              }
            }
          }
          Logger::TraceError(
            L"%s: WaitForSingleObject failed for DiscoverApi::BeginRepairJoinInfo.\n",
            L"DsrCmdAsyncHelper::RepairJoinInfo");
LABEL_93:
          if ( (JoinInfo & 0x80000000) != 0 )
          {
LABEL_111:
            v131 = (_QWORD *)CmdOptions::GetCurrentRef(v89, v88);
            if ( *(_BYTE *)(*v131 + 12LL) )
            {
              v133 = (_QWORD *)CmdOptions::GetCurrentRef(*v131, v132);
              if ( *(_QWORD *)(*v133 + 184LL) )
              {
                v135 = CmdOptions::GetCurrentRef(v134, *v133);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v135 + 184LL),
                  L"Registry repair failed with error code 0x%08x.\n",
                  JoinInfo);
              }
            }
            wprintf(L"Registry repair failed with error code 0x%08x.\n", JoinInfo);
            v138 = (_QWORD *)CmdOptions::GetCurrentRef(v137, v136);
            v140 = &cchOriginalDestLength;
            if ( *(_BYTE *)(*v138 + 12LL) )
            {
              v141 = (_QWORD *)CmdOptions::GetCurrentRef(*v138, v139);
              if ( *(_QWORD *)(*v141 + 184LL) )
              {
                v143 = &cchOriginalDestLength;
                if ( (_QWORD)v213 )
                  v143 = (const WCHAR *)v213;
                v144 = CmdOptions::GetCurrentRef(*v141, v142);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v144 + 184LL), L"Reequest ID: %s\n", v143);
              }
            }
            v145 = &cchOriginalDestLength;
            if ( (_QWORD)v213 )
              v145 = (const WCHAR *)v213;
            wprintf(L"Reequest ID: %s\n", v145);
            v148 = (_QWORD *)CmdOptions::GetCurrentRef(v147, v146);
            if ( *(_BYTE *)(*v148 + 12LL) )
            {
              v150 = (_QWORD *)CmdOptions::GetCurrentRef(*v148, v149);
              if ( *(_QWORD *)(*v150 + 184LL) )
              {
                v152 = &cchOriginalDestLength;
                if ( *((_QWORD *)&v213 + 1) )
                  v152 = (const WCHAR *)*((_QWORD *)&v213 + 1);
                v153 = CmdOptions::GetCurrentRef(*v150, v151);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v153 + 184LL), L"Time: %s\n", v152);
              }
            }
            v154 = &cchOriginalDestLength;
            if ( *((_QWORD *)&v213 + 1) )
              v154 = (const WCHAR *)*((_QWORD *)&v213 + 1);
            wprintf(L"Time: %s\n", v154);
            v157 = (_QWORD *)CmdOptions::GetCurrentRef(v156, v155);
            if ( *(_BYTE *)(*v157 + 12LL) )
            {
              v159 = (_QWORD *)CmdOptions::GetCurrentRef(*v157, v158);
              if ( *(_QWORD *)(*v159 + 184LL) )
              {
                v161 = v214;
                v162 = CmdOptions::GetCurrentRef(v160, *v159);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v162 + 184LL), L"HTTP status: %lu\n", v161);
              }
            }
            wprintf(L"HTTP status: %lu\n", (unsigned int)v214);
            v165 = (_QWORD *)CmdOptions::GetCurrentRef(v164, v163);
            if ( *(_BYTE *)(*v165 + 12LL) )
            {
              v167 = (_QWORD *)CmdOptions::GetCurrentRef(*v165, v166);
              if ( *(_QWORD *)(*v167 + 184LL) )
              {
                v169 = &cchOriginalDestLength;
                if ( *((_QWORD *)&v214 + 1) )
                  v169 = (const WCHAR *)*((_QWORD *)&v214 + 1);
                v170 = CmdOptions::GetCurrentRef(*v167, v168);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v170 + 184LL), L"Server error code: %s\n", v169);
              }
            }
            v171 = &cchOriginalDestLength;
            if ( *((_QWORD *)&v214 + 1) )
              v171 = (const WCHAR *)*((_QWORD *)&v214 + 1);
            wprintf(L"Server error code: %s\n", v171);
            v174 = (_QWORD *)CmdOptions::GetCurrentRef(v173, v172);
            if ( *(_BYTE *)(*v174 + 12LL) )
            {
              v176 = (_QWORD *)CmdOptions::GetCurrentRef(*v174, v175);
              if ( *(_QWORD *)(*v176 + 184LL) )
              {
                v178 = &cchOriginalDestLength;
                if ( (_QWORD)v215 )
                  v178 = (const WCHAR *)v215;
                v179 = CmdOptions::GetCurrentRef(*v176, v177);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v179 + 184LL), L"Server error sub-code: %s\n", v178);
              }
            }
            v180 = &cchOriginalDestLength;
            if ( (_QWORD)v215 )
              v180 = (const WCHAR *)v215;
            wprintf(L"Server error sub-code: %s\n", v180);
            v183 = (_QWORD *)CmdOptions::GetCurrentRef(v182, v181);
            if ( *(_BYTE *)(*v183 + 12LL) )
            {
              v185 = (_QWORD *)CmdOptions::GetCurrentRef(*v183, v184);
              if ( *(_QWORD *)(*v185 + 184LL) )
              {
                v187 = &cchOriginalDestLength;
                if ( *((_QWORD *)&v215 + 1) )
                  v187 = (const WCHAR *)*((_QWORD *)&v215 + 1);
                v188 = CmdOptions::GetCurrentRef(*v185, v186);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v188 + 184LL), L"Server message: %s\n", v187);
              }
            }
            v189 = &cchOriginalDestLength;
            if ( *((_QWORD *)&v215 + 1) )
              v189 = (const WCHAR *)*((_QWORD *)&v215 + 1);
            wprintf(L"Server message: %s\n", v189);
            v192 = (_QWORD *)CmdOptions::GetCurrentRef(v191, v190);
            if ( *(_BYTE *)(*v192 + 12LL) )
            {
              v194 = (_QWORD *)CmdOptions::GetCurrentRef(*v192, v193);
              if ( *(_QWORD *)(*v194 + 184LL) )
              {
                v196 = &cchOriginalDestLength;
                if ( v216 )
                  v196 = v216;
                v197 = CmdOptions::GetCurrentRef(*v194, v195);
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v197 + 184LL), L"Server operation: %s\n", v196);
              }
            }
            if ( v216 )
              v140 = v216;
            wprintf(L"Server operation: %s\n", v140);
            goto LABEL_174;
          }
          goto LABEL_94;
        }
        JoinInfo = v212;
        if ( (int)v212 >= 0 )
        {
LABEL_94:
          v112 = (_QWORD *)CmdOptions::GetCurrentRef(v89, v88);
          if ( *(_BYTE *)(*v112 + 12LL) )
          {
            v114 = (_QWORD *)CmdOptions::GetCurrentRef(*v112, v113);
            if ( *(_QWORD *)(*v114 + 184LL) )
            {
              v116 = CmdOptions::GetCurrentRef(v115, *v114);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v116 + 184LL), L"Registry repair succeeded.\n");
            }
          }
          wprintf(L"Registry repair succeeded.\n");
          goto LABEL_174;
        }
        CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v89, v88);
        v11 = L"%s: RepairJoinInfoCallback failed with error code 0x%08x.\n";
      }
      else
      {
        CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v92, v91);
        v11 = L"%s: DiscoverApi::BeginRepairJoinInfo failed with error code 0x%08x.\n";
      }
LABEL_106:
      if ( **CurrentRef )
      {
        wprintf(v11, L"DsrCmdAsyncHelper::RepairJoinInfo", JoinInfo);
        v126 = (_QWORD *)CmdOptions::GetCurrentRef(v125, v124);
        if ( *(_BYTE *)(*v126 + 12LL) )
        {
          v128 = (_QWORD *)CmdOptions::GetCurrentRef(*v126, v127);
          if ( *(_QWORD *)(*v128 + 184LL) )
          {
            v130 = CmdOptions::GetCurrentRef(*v128, v129);
            fwprintf_s(*(FILE *const *)(*(_QWORD *)v130 + 184LL), v11, L"DsrCmdAsyncHelper::RepairJoinInfo", JoinInfo);
          }
        }
      }
      Logger::TraceError(v11, L"DsrCmdAsyncHelper::RepairJoinInfo", JoinInfo);
      goto LABEL_111;
    }
    v68 = (_QWORD *)CmdOptions::GetCurrentRef(v67, v66);
    if ( *(_BYTE *)(*v68 + 12LL) )
    {
      v70 = (_QWORD *)CmdOptions::GetCurrentRef(*v68, v69);
      if ( *(_QWORD *)(*v70 + 184LL) )
      {
        v72 = CmdOptions::GetCurrentRef(v71, *v70);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v72 + 184LL),
          L"Failed to determine if the process has administrator privileges: 0x%08x.\n",
          JoinInfo);
      }
    }
    wprintf(L"Failed to determine if the process has administrator privileges: 0x%08x.\n", JoinInfo);
  }
  else if ( v5[2] )
  {
    v203 = (_QWORD *)CmdOptions::GetCurrentRef(v8, v7);
    if ( *(_BYTE *)(*v203 + 12LL) )
    {
      v205 = (_QWORD *)CmdOptions::GetCurrentRef(*v203, v204);
      if ( *(_QWORD *)(*v205 + 184LL) )
      {
        if ( v5[3] <= 7u )
          v207 = v5;
        else
          v207 = (_QWORD *)*v5;
        v208 = CmdOptions::GetCurrentRef(*v205, v206);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v208 + 184LL),
          L"The device is not joined to tenant %s. Nothing to repair. Exiting...\n",
          v207);
      }
    }
    if ( v5[3] > 7u )
      v5 = (_QWORD *)*v5;
    wprintf(L"The device is not joined to tenant %s. Nothing to repair. Exiting...\n", v5);
  }
  else
  {
    v198 = (_QWORD *)CmdOptions::GetCurrentRef(v8, v7);
    if ( *(_BYTE *)(*v198 + 12LL) )
    {
      v200 = (_QWORD *)CmdOptions::GetCurrentRef(*v198, v199);
      if ( *(_QWORD *)(*v200 + 184LL) )
      {
        v202 = CmdOptions::GetCurrentRef(v201, *v200);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v202 + 184LL),
          L"The device is not joined to AAD. Nothing to repair. Exiting...\n");
      }
    }
    wprintf(L"The device is not joined to AAD. Nothing to repair. Exiting...\n");
  }
LABEL_174:
  DsregServerResponse::MoveTo((DsregServerResponse *)&v213, a3);
  if ( hHandle )
    CloseHandle(hHandle);
  DsrFreeJoinInfoEx(Block);
  NetApiBufferFree(0);
  DsrFreeServerResponseContent(&v213);
  return JoinInfo;
}

```

## disassembly

```asm
0x1800414f8  mov     [rsp-8+arg_8], rbx
0x1800414fd  mov     [rsp-8+arg_10], rsi
0x180041502  push    rbp
0x180041503  push    rdi
0x180041504  push    r12
0x180041506  push    r14
0x180041508  push    r15
0x18004150a  lea     rbp, [rsp-37h]
0x18004150f  sub     rsp, 0B0h
0x180041516  mov     r15, r8
0x180041519  mov     r14, rdx
0x18004151c  mov     rbx, rcx
0x18004151f  xor     r12d, r12d
0x180041522  mov     [rbp+57h+Block], r12
0x180041526  xor     eax, eax
0x180041528  mov     [rbp+57h+var_70], rax
0x18004152c  xorps   xmm0, xmm0
0x18004152f  movups  [rbp+57h+var_68], xmm0
0x180041533  movups  [rbp+57h+var_58], xmm0
0x180041537  movups  [rbp+57h+var_48], xmm0
0x18004153b  mov     [rbp+57h+var_38], rax
0x18004153f  mov     [rbp+57h+hHandle], rax
0x180041543  mov     [rbp+57h+var_88], r12
0x180041547  cmp     qword ptr [rcx+18h], 7
0x18004154c  jbe     short loc_180041553
0x18004154e  mov     rax, [rcx]
0x180041551  jmp     short loc_180041556
0x180041553  mov     rax, rbx
0x180041556  mov     [rbp+57h+var_80], rax
0x18004155a  mov     [rbp+57h+var_78], r12
0x18004155e  lea     r8, [rbp+57h+Block]
0x180041562  lea     rdx, [rbp+57h+var_88]
0x180041566  mov     ecx, 3
0x18004156b  call    DsrGetJoinInfoEx
0x180041570  mov     edi, eax
0x180041572  test    eax, eax
0x180041574  jns     short loc_18004158E
0x180041576  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004157b  lea     rsi, aDsrcmdasynchel_0; "DsrCmdAsyncHelper::RepairJoinInfo"
0x180041582  lea     rbx, aSDsrgetjoininf; "%s: DsrGetJoinInfoEx failed with error "...
0x180041589  jmp     loc_180041C84
0x18004158e  mov     rax, [rbp+57h+Block]
0x180041592  test    rax, rax
0x180041595  jz      loc_180041FE3
0x18004159b  cmp     [rax+10h], r12d
0x18004159f  jz      loc_180041FE3
0x1800415a5  cmp     [rax+8], r12
0x1800415a9  jz      loc_180041FE3
0x1800415af  cmp     dword ptr [rax+10h], 1
0x1800415b3  jbe     loc_180041695
0x1800415b9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800415be  mov     rcx, [rax]
0x1800415c1  cmp     [rcx+0Ch], r12b
0x1800415c5  jz      short loc_1800415F3
0x1800415c7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800415cc  mov     rdx, [rax]
0x1800415cf  cmp     [rdx+0B8h], r12
0x1800415d6  jz      short loc_1800415F3
0x1800415d8  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800415dd  mov     rcx, [rax]
0x1800415e0  lea     rdx, aThereAreMultip; "There are multiple AAD accounts. Please"...
0x1800415e7  mov     rcx, [rcx+0B8h]; Stream
0x1800415ee  call    fwprintf_s
0x1800415f3  lea     rcx, aThereAreMultip; "There are multiple AAD accounts. Please"...
0x1800415fa  call    wprintf
0x1800415ff  mov     esi, r12d
0x180041602  mov     rax, [rbp+57h+Block]
0x180041606  cmp     [rax+10h], r12d
0x18004160a  jbe     loc_180042094
0x180041610  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041615  mov     rcx, [rax]
0x180041618  cmp     [rcx+0Ch], r12b
0x18004161c  jz      short loc_180041663
0x18004161e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041623  mov     rcx, [rax]
0x180041626  cmp     [rcx+0B8h], r12
0x18004162d  jz      short loc_180041663
0x18004162f  mov     eax, esi
0x180041631  imul    rdx, rax, 150h
0x180041638  mov     rax, [rbp+57h+Block]
0x18004163c  mov     rcx, [rax+8]
0x180041640  mov     rbx, [rdx+rcx+20h]
0x180041645  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004164a  mov     rcx, [rax]
0x18004164d  mov     r8, rbx
0x180041650  lea     rdx, aS_6; "%s\n"
0x180041657  mov     rcx, [rcx+0B8h]; Stream
0x18004165e  call    fwprintf_s
0x180041663  mov     eax, esi
0x180041665  imul    rcx, rax, 150h
0x18004166c  mov     rax, [rbp+57h+Block]
0x180041670  mov     rdx, [rax+8]
0x180041674  mov     rdx, [rcx+rdx+20h]
0x180041679  lea     rcx, aS_6; "%s\n"
0x180041680  call    wprintf
0x180041685  inc     esi
0x180041687  mov     rax, [rbp+57h+Block]
0x18004168b  cmp     esi, [rax+10h]
0x18004168e  jb      short loc_180041610
0x180041690  jmp     loc_180042094
0x180041695  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004169a  mov     rcx, [rax]
0x18004169d  lea     rsi, aDsrcmdasynchel_0; "DsrCmdAsyncHelper::RepairJoinInfo"
0x1800416a4  lea     rdi, aSTenantIdS; "%s: Tenant ID: %s\n"
0x1800416ab  cmp     [rcx], r12b
0x1800416ae  jz      short loc_18004170F
0x1800416b0  mov     rax, [rbp+57h+Block]
0x1800416b4  mov     r8, [rax+8]
0x1800416b8  mov     r8, [r8+20h]
0x1800416bc  mov     rdx, rsi
0x1800416bf  mov     rcx, rdi; Format
0x1800416c2  call    wprintf
0x1800416c7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800416cc  mov     rcx, [rax]
0x1800416cf  cmp     [rcx+0Ch], r12b
0x1800416d3  jz      short loc_18004170F
0x1800416d5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800416da  mov     rcx, [rax]
0x1800416dd  cmp     [rcx+0B8h], r12
0x1800416e4  jz      short loc_18004170F
0x1800416e6  mov     rax, [rbp+57h+Block]
0x1800416ea  mov     rcx, [rax+8]
0x1800416ee  mov     rbx, [rcx+20h]
0x1800416f2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800416f7  mov     rcx, [rax]
0x1800416fa  mov     r9, rbx
0x1800416fd  mov     r8, rsi
0x180041700  mov     rdx, rdi; Format
0x180041703  mov     rcx, [rcx+0B8h]; Stream
0x18004170a  call    fwprintf_s
0x18004170f  mov     rax, [rbp+57h+Block]
0x180041713  mov     r8, [rax+8]
0x180041717  mov     r8, [r8+20h]
0x18004171b  mov     rdx, rsi
0x18004171e  mov     rcx, rdi; unsigned __int16 *
0x180041721  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180041726  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004172b  mov     rcx, [rax]
0x18004172e  lea     rdi, aSJoinUserUpnS; "%s: Join user UPN: %s\n"
0x180041735  cmp     [rcx], r12b
0x180041738  jz      short loc_18004179F
0x18004173a  cmp     qword ptr [r14+18h], 7
0x18004173f  jbe     short loc_180041746
0x180041741  mov     r8, [r14]
0x180041744  jmp     short loc_180041749
0x180041746  mov     r8, r14
0x180041749  mov     rdx, rsi
0x18004174c  mov     rcx, rdi; Format
0x18004174f  call    wprintf
0x180041754  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041759  mov     rcx, [rax]
0x18004175c  cmp     [rcx+0Ch], r12b
0x180041760  jz      short loc_18004179F
0x180041762  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041767  mov     rcx, [rax]
0x18004176a  cmp     [rcx+0B8h], r12
0x180041771  jz      short loc_18004179F
0x180041773  cmp     qword ptr [r14+18h], 7
0x180041778  jbe     short loc_18004177F
0x18004177a  mov     rbx, [r14]
0x18004177d  jmp     short loc_180041782
0x18004177f  mov     rbx, r14
0x180041782  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041787  mov     rcx, [rax]
0x18004178a  mov     r9, rbx
0x18004178d  mov     r8, rsi
0x180041790  mov     rdx, rdi; Format
0x180041793  mov     rcx, [rcx+0B8h]; Stream
0x18004179a  call    fwprintf_s
0x18004179f  cmp     qword ptr [r14+18h], 7
0x1800417a4  jbe     short loc_1800417AB
0x1800417a6  mov     r8, [r14]
0x1800417a9  jmp     short loc_1800417AE
0x1800417ab  mov     r8, r14
0x1800417ae  mov     rdx, rsi
0x1800417b1  mov     rcx, rdi; unsigned __int16 *
0x1800417b4  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800417b9  mov     rax, [rbp+57h+Block]
0x1800417bd  mov     rcx, [rax+8]
0x1800417c1  cmp     dword ptr [rcx], 1
0x1800417c4  jnz     loc_18004198C
0x1800417ca  mov     [rbp+57h+IsMember], r12d
0x1800417ce  xor     edx, edx; unsigned __int16 **
0x1800417d0  lea     rcx, [rbp+57h+IsMember]; int *
0x1800417d4  call    ?IsLocalMachineDomainJoined@@YAJPEAHPEAPEAG@Z; IsLocalMachineDomainJoined(int *,ushort * *)
0x1800417d9  mov     edi, eax
0x1800417db  test    eax, eax
0x1800417dd  jns     short loc_18004182F
0x1800417df  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800417e4  mov     rcx, [rax]
0x1800417e7  cmp     [rcx+0Ch], r12b
0x1800417eb  jz      short loc_18004181C
0x1800417ed  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800417f2  mov     rdx, [rax]
0x1800417f5  cmp     [rdx+0B8h], r12
0x1800417fc  jz      short loc_18004181C
0x1800417fe  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041803  mov     rcx, [rax]
0x180041806  mov     r8d, edi
0x180041809  lea     rdx, aFailedToDeterm_0; "Failed to determine if the device is do"...
0x180041810  mov     rcx, [rcx+0B8h]; Stream
0x180041817  call    fwprintf_s
0x18004181c  lea     rcx, aFailedToDeterm_0; "Failed to determine if the device is do"...
0x180041823  mov     edx, edi
0x180041825  call    wprintf
0x18004182a  jmp     loc_180042094
0x18004182f  lea     rcx, [rbp+57h+IsMember]; IsMember
0x180041833  cmp     [rbp+57h+IsMember], r12d
0x180041837  mov     [rbp+57h+IsMember], r12d
0x18004183b  jz      loc_1800418EC
0x180041841  call    ?IsCurrentUserSystem@@YAJAEAH@Z; IsCurrentUserSystem(int &)
0x180041846  mov     edi, eax
0x180041848  test    eax, eax
0x18004184a  jns     short loc_180041892
0x18004184c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041851  mov     rcx, [rax]
0x180041854  cmp     [rcx+0Ch], r12b
0x180041858  jz      short loc_180041889
0x18004185a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004185f  mov     rdx, [rax]
0x180041862  cmp     [rdx+0B8h], r12
0x180041869  jz      short loc_180041889
0x18004186b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041870  mov     rcx, [rax]
0x180041873  mov     r8d, edi
0x180041876  lea     rdx, aFailedToDeterm; "Failed to determine if the process is r"...
0x18004187d  mov     rcx, [rcx+0B8h]; Stream
0x180041884  call    fwprintf_s
0x180041889  lea     rcx, aFailedToDeterm; "Failed to determine if the process is r"...
0x180041890  jmp     short loc_180041823
0x180041892  cmp     [rbp+57h+IsMember], r12d
0x180041896  jnz     loc_18004198C
0x18004189c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800418a1  mov     rcx, [rax]
0x1800418a4  cmp     [rcx+0Ch], r12b
0x1800418a8  jz      short loc_1800418D6
0x1800418aa  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800418af  mov     rdx, [rax]
0x1800418b2  cmp     [rdx+0B8h], r12
0x1800418b9  jz      short loc_1800418D6
0x1800418bb  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800418c0  mov     rcx, [rax]
0x1800418c3  lea     rdx, aToRepairHybrid; "To repair hybrid joined device, you nee"...
0x1800418ca  mov     rcx, [rcx+0B8h]; Stream
0x1800418d1  call    fwprintf_s
0x1800418d6  lea     rcx, aToRepairHybrid; "To repair hybrid joined device, you nee"...
0x1800418dd  call    wprintf
0x1800418e2  mov     edi, 80070005h
0x1800418e7  jmp     loc_180042094
0x1800418ec  call    ?IsCurrentUserElevated@@YAJAEAH@Z; IsCurrentUserElevated(int &)
0x1800418f1  mov     edi, eax
0x1800418f3  test    eax, eax
0x1800418f5  jns     short loc_180041940
0x1800418f7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800418fc  mov     rcx, [rax]
0x1800418ff  cmp     [rcx+0Ch], r12b
0x180041903  jz      short loc_180041934
0x180041905  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004190a  mov     rdx, [rax]
0x18004190d  cmp     [rdx+0B8h], r12
0x180041914  jz      short loc_180041934
0x180041916  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004191b  mov     rcx, [rax]
0x18004191e  mov     r8d, edi
0x180041921  lea     rdx, aFailedToDeterm_1; "Failed to determine if the process has "...
0x180041928  mov     rcx, [rcx+0B8h]; Stream
0x18004192f  call    fwprintf_s
0x180041934  lea     rcx, aFailedToDeterm_1; "Failed to determine if the process has "...
0x18004193b  jmp     loc_180041823
0x180041940  cmp     [rbp+57h+IsMember], r12d
0x180041944  jnz     short loc_18004198C
0x180041946  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004194b  mov     rcx, [rax]
0x18004194e  cmp     [rcx+0Ch], r12b
0x180041952  jz      short loc_180041980
0x180041954  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180041959  mov     rdx, [rax]
0x18004195c  cmp     [rdx+0B8h], r12
0x180041963  jz      short loc_180041980
0x180041965  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18004196a  mov     rcx, [rax]
0x18004196d  lea     rdx, aToRepairAzureA; "To repair Azure AD joined device, you n"...
0x180041974  mov     rcx, [rcx+0B8h]; Stream
0x18004197b  call    fwprintf_s
0x180041980  lea     rcx, aToRepairAzureA; "To repair Azure AD joined device, you n"...
0x180041987  jmp     loc_1800418DD
0x18004198c  xor     r9d, r9d; lpName
0x18004198f  xor     r8d, r8d; bInitialState
0x180041992  xor     edx, edx; bManualReset
0x180041994  xor     ecx, ecx; lpEventAttributes
0x180041996  call    cs:__imp_CreateEventW
0x18004199c  mov     [rbp+57h+hHandle], rax
0x1800419a0  test    rax, rax
0x1800419a3  jnz     loc_180041A2F
0x1800419a9  call    cs:__imp_GetLastError
0x1800419af  mov     edi, eax
0x1800419b1  test    eax, eax
0x1800419b3  jle     short loc_1800419BE
0x1800419b5  movzx   edi, ax
0x1800419b8  or      edi, 80070000h
  ... truncated ...
```
