# DsrCmdJoinHelper::Join(CLI_EXTENSIONS const &,struct_dsreg_server_response *)

- ea: `0x1800aee10`
- end: `0x1800b0bf0`
- name: `?Join@DsrCmdJoinHelper@@QEAAJAEBUCLI_EXTENSIONS@@PEAUstruct_dsreg_server_response@@@Z`
- size: `7648`
- prototype: `__int64 __fastcall(DsrCmdJoinHelper *__hidden this, const struct CLI_EXTENSIONS *, struct struct_dsreg_server_response *)`
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009b940`

## callees

- `0x180003014`
- `0x1800030f8`
- `0x180003354`
- `0x180003680`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000eda4`
- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x180016b90`
- `0x180017f50`
- `0x18001d258`
- `0x18001dfcc`
- `0x1800204f0`
- `0x18002927c`
- `0x1800299d8`
- `0x18002b9b4`
- `0x18002df9c`
- `0x1800319ac`
- `0x180032618`
- `0x180033450`
- `0x180034684`
- `0x1800360e8`
- `0x180037134`
- `0x180038c60`
- `0x18003a714`
- `0x18003b9b4`
- `0x18003c160`
- `0x18003e908`
- `0x180040d38`
- `0x1800422ac`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x180046ae8`
- `0x180046b3c`
- `0x180053db4`
- `0x180055174`
- `0x18008cd14`
- `0x180097efc`
- `0x180097f48`
- `0x180097f94`
- `0x180097fe0`
- `0x18009802c`
- `0x1800984d8`
- `0x18009eb34`
- `0x18009f1dc`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800af054`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800af1cc`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800b060d`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800b07cb`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800b08f0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800af054`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800af1cc`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800b060d`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800b07cb`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800b08f0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800b038f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800b038f`

## string_xrefs

- `0x1800af533`: `%s: RegistryHelper::IncrementCounter(REG_STATISTICS_COUNTER_RECOVERY_START_COUNT) failed 0x%08x.\n`
- `0x1800af66d`: `%s: Join state is incomplete but auto rejoin is disabled.\n`
- `0x1800b0303`: `%s: DsrCmdDeviceEnroller::AutoEnroll(%s) completed successfully.\n`
- `0x1800b0044`: `%s: Unable to retrieve access token. GetComputerTokenForADRS failed with error 0x%08x.\n`
- `0x1800b0081`: `%s: Unable to retrieve access token. GetComputerTokenForADRS failed with error 0x%08x.\n`
- `0x1800b009e`: `%s: Unable to retrieve access token. GetComputerTokenForADRS failed with error 0x%08x.\n`
- `0x1800b01ee`: `%s: Purge cached Kerberos tickets and KDC proxy, then try again.\n`
- `0x1800b0228`: `%s: Purge cached Kerberos tickets and KDC proxy, then try again.\n`
- `0x1800b0242`: `%s: Purge cached Kerberos tickets and KDC proxy, then try again.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall DsrCmdJoinHelper::Join(
        DsrCmdJoinHelper *this,
        const struct CLI_EXTENSIONS *a2,
        struct struct_dsreg_server_response *a3)
{
  AutoJoinTelemetryInfo *AutoRegistrationJoinEventData; // rax
  const WCHAR *v4; // rbx
  char **v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  const WCHAR *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  const WCHAR *v17; // rbx
  __int64 v18; // rax
  const WCHAR *v19; // r8
  int v20; // eax
  __int64 v21; // r13
  __int64 v22; // r12
  __int64 v23; // r15
  __int64 v24; // r14
  __int64 v25; // rsi
  __int64 v26; // rdi
  struct AutoJoinTelemetryInfo *v27; // rax
  __int64 v28; // rbx
  __time64_t v29; // rax
  unsigned int v30; // r14d
  __int64 v31; // r13
  __int64 v32; // r12
  __int64 v33; // r15
  __int64 v34; // r14
  __int64 v35; // rsi
  __int64 v36; // rdi
  struct AutoJoinTelemetryInfo *v37; // rax
  __int64 v38; // rbx
  __time64_t v39; // rax
  bool v40; // di
  __int64 v41; // rbx
  struct AutoJoinTelemetryInfo *v42; // rax
  const unsigned __int16 *v43; // rdx
  const unsigned __int16 *AutoJoinPolicy; // rbx
  const unsigned __int16 *v45; // rdx
  const unsigned __int16 *v46; // r15
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  __int64 v49; // rdx
  __int64 v50; // rcx
  unsigned int v51; // edx
  __int64 v52; // rdx
  __int64 v53; // rcx
  int ParentProcessName; // ebx
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD *v57; // rax
  __int64 v58; // rdx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rax
  struct AutoJoinTelemetryInfo *v62; // rax
  unsigned int ComputerTokenForADRS; // edi
  struct AutoJoinTelemetryInfo *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  _QWORD *v69; // rax
  __int64 v70; // rdx
  _QWORD *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  unsigned int v76; // ebx
  __int64 v77; // rdx
  __int64 v78; // rcx
  _QWORD *v79; // rax
  __int64 v80; // rdx
  _QWORD *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rax
  unsigned __int16 *v84; // rdx
  struct AutoJoinTelemetryInfo *v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rdx
  __int64 v89; // rcx
  _QWORD *v90; // rax
  __int64 v91; // rdx
  _QWORD *v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rcx
  _QWORD *v97; // rax
  __int64 v98; // rdx
  _QWORD *v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rax
  struct AutoJoinTelemetryInfo *v102; // rax
  struct AutoJoinTelemetryInfo *v103; // rax
  int v104; // r15d
  int v105; // r12d
  const WCHAR *v106; // rdx
  __int64 v107; // rbx
  struct AutoJoinTelemetryInfo *v108; // rax
  const wchar_t *v109; // rbx
  char **v110; // rcx
  __int64 v111; // r8
  const wchar_t *v112; // rbx
  char **v113; // rcx
  __int64 v114; // rdx
  __int64 v115; // rcx
  char v116; // r12
  int v117; // r13d
  unsigned int v118; // r14d
  __int64 v119; // rdx
  __int64 v120; // rcx
  _QWORD *v121; // rax
  __int64 v122; // rdx
  _QWORD *v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rax
  _QWORD *v126; // rax
  struct AutoJoinTelemetryInfo *v127; // rax
  _QWORD *v128; // rax
  _QWORD *v129; // rax
  _QWORD *v130; // rax
  _QWORD *v131; // rax
  _QWORD *v132; // rax
  _QWORD *v133; // rax
  const unsigned __int16 *v134; // rax
  __int64 v135; // r9
  struct AutoJoinTelemetryInfo *v136; // rax
  __int64 v137; // rax
  const unsigned __int16 *v138; // rsi
  struct AutoJoinTelemetryInfo *v139; // rax
  const unsigned __int16 *v140; // rbx
  struct AutoJoinTelemetryInfo *v141; // rax
  const unsigned __int16 *v142; // r8
  const unsigned __int16 *v143; // rdx
  __int64 v144; // r9
  __int64 v145; // rdx
  __int64 v146; // rcx
  __int64 v147; // rdx
  __int64 v148; // rcx
  _QWORD *v149; // rax
  __int64 v150; // rdx
  _QWORD *v151; // rax
  __int64 v152; // rdx
  __int64 v153; // rax
  __int64 v154; // rdx
  __int64 v155; // rcx
  __int64 v156; // rdx
  __int64 v157; // rcx
  _QWORD *v158; // rax
  __int64 v159; // rdx
  _QWORD *v160; // rax
  __int64 v161; // rdx
  __int64 v162; // rax
  struct AutoJoinTelemetryInfo *v163; // rax
  struct AutoJoinTelemetryInfo *v164; // rax
  struct AutoJoinTelemetryInfo *v165; // rax
  const wchar_t *v166; // rdx
  const wchar_t *v167; // rbx
  __int64 v168; // rdi
  __int64 v169; // r8
  __int64 v170; // rdx
  __int64 v171; // r8
  __int64 v172; // r9
  __int64 JoinTypeName; // rbx
  __int64 v174; // rdx
  __int64 v175; // rcx
  _QWORD *v176; // rax
  _QWORD *v177; // rax
  __int64 v178; // rax
  __int64 v179; // rbx
  __int64 v180; // r8
  unsigned __int16 *v181; // r9
  struct AutoJoinTelemetryInfo *v182; // rax
  __int64 v183; // rdx
  __int64 v184; // rcx
  __int64 v185; // rdx
  __int64 v186; // rcx
  _QWORD *v187; // rax
  __int64 v188; // rdx
  _QWORD *v189; // rax
  __int64 v190; // rdx
  __int64 v191; // rax
  __int64 **v192; // rax
  struct AutoJoinTelemetryInfo *v193; // rax
  __int64 v194; // rdx
  __int64 v195; // rcx
  __int64 v196; // rdx
  __int64 v197; // rcx
  _QWORD *v198; // rax
  __int64 v199; // rdx
  _QWORD *v200; // rax
  __int64 v201; // rdx
  __int64 v202; // rax
  _QWORD **v203; // rax
  unsigned __int16 *v204; // r9
  __int64 v205; // rdx
  __int64 v206; // rcx
  struct AutoJoinTelemetryInfo *v207; // rax
  __int64 v208; // rdx
  __int64 v209; // rcx
  __int64 v210; // rdx
  __int64 v211; // rcx
  _QWORD *v212; // rax
  __int64 v213; // rdx
  _QWORD *v214; // rax
  __int64 v215; // rdx
  __int64 v216; // rax
  __int64 v217; // rdx
  __int64 v218; // rcx
  _QWORD *v219; // rax
  __int64 v220; // rdx
  _QWORD *v221; // rax
  __int64 v222; // rdx
  __int64 v223; // rax
  bool v224; // dl
  bool v225; // cl
  __int64 v226; // rdx
  __int64 v227; // rcx
  _QWORD *v228; // rax
  __int64 v229; // rdx
  _QWORD *v230; // rax
  __int64 v231; // rdx
  __int64 v232; // rax
  __int64 v233; // rdx
  __int64 v234; // rcx
  _QWORD *v235; // rax
  __int64 v236; // rdx
  _QWORD *v237; // rax
  __int64 v238; // rdx
  __int64 v239; // rax
  DsrCmdJoinHelper *v240; // rax
  struct AutoJoinTelemetryInfo *v241; // rax
  const unsigned __int16 *v242; // rax
  const unsigned __int16 *v243; // rax
  _QWORD *v244; // rax
  _QWORD *v245; // rax
  _QWORD *v246; // rax
  _QWORD *v247; // rax
  _QWORD *AdalLogForTelemetry; // rax
  __int64 v249; // r9
  __int64 v250; // r13
  __int64 v251; // r12
  __int64 v252; // r15
  __int64 v253; // r14
  __int64 v254; // rsi
  __int64 v255; // rdi
  struct AutoJoinTelemetryInfo *v256; // rax
  __int64 v257; // rbx
  __time64_t v258; // rax
  struct AutoJoinTelemetryInfo *v259; // rax
  __int64 String; // rax
  const unsigned __int16 *v261; // rsi
  struct AutoJoinTelemetryInfo *v262; // rax
  const unsigned __int16 *v263; // rbx
  struct AutoJoinTelemetryInfo *v264; // rax
  const unsigned __int16 *v265; // r8
  const unsigned __int16 *v266; // rdx
  struct AutoJoinTelemetryInfo *v267; // rax
  _QWORD *v268; // rcx
  char v269; // al
  const WCHAR *v270; // rdx
  __int64 v271; // r13
  __int64 v272; // r12
  __int64 v273; // r15
  __int64 v274; // r14
  struct AutoJoinTelemetryInfo *v275; // rax
  __int64 v276; // rsi
  struct AutoJoinTelemetryInfo *v277; // rax
  __int64 v278; // rdi
  struct AutoJoinTelemetryInfo *v279; // rax
  __int64 v280; // rbx
  __time64_t v281; // rax
  const WCHAR *v282; // rdx
  __int64 v283; // r13
  const WCHAR *v284; // rdx
  __int64 v285; // r12
  const WCHAR *v286; // rdx
  __int64 v287; // r15
  int v288; // r14d
  const WCHAR *v289; // rdx
  struct AutoJoinTelemetryInfo *v290; // rax
  struct AutoJoinTelemetryInfo *v291; // rax
  __int64 v292; // rdx
  __int64 v293; // rcx
  _QWORD *v294; // r9
  _QWORD *v295; // r8
  _QWORD *v296; // rdx
  __int64 v297; // rdx
  __int64 v298; // rcx
  _QWORD *v299; // rax
  __int64 v300; // rdx
  _QWORD *v301; // rax
  __int64 v302; // rdx
  _QWORD *v303; // rsi
  _QWORD *v304; // rdi
  _QWORD *v305; // rbx
  __int64 v306; // rax
  _QWORD *v307; // r9
  _QWORD *v308; // r8
  _QWORD *v309; // rdx
  unsigned __int16 **v311; // [rsp+20h] [rbp-E0h]
  int v312; // [rsp+28h] [rbp-D8h]
  __int64 v313; // [rsp+30h] [rbp-D0h]
  __int64 v314; // [rsp+30h] [rbp-D0h]
  __int64 v315; // [rsp+38h] [rbp-C8h]
  __int64 v316; // [rsp+40h] [rbp-C0h]
  DsrCmdJoinHelper *v317; // [rsp+48h] [rbp-B8h]
  bool v318; // [rsp+80h] [rbp-80h] BYREF
  bool v319; // [rsp+81h] [rbp-7Fh]
  char v320; // [rsp+82h] [rbp-7Eh]
  char v321; // [rsp+83h] [rbp-7Dh] BYREF
  char v322[4]; // [rsp+84h] [rbp-7Ch] BYREF
  _QWORD *v323; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v324; // [rsp+90h] [rbp-70h] BYREF
  void *Block[2]; // [rsp+98h] [rbp-68h] BYREF
  void *v326[2]; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v327[2]; // [rsp+B8h] [rbp-48h]
  void *v328; // [rsp+C8h] [rbp-38h]
  _BYTE *v329; // [rsp+D0h] [rbp-30h] BYREF
  DsrCmdJoinHelper *v330; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE *v331; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v332; // [rsp+E8h] [rbp-18h] BYREF
  const unsigned __int16 *v333; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v334; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE *v335; // [rsp+100h] [rbp+0h] BYREF
  const unsigned __int16 *v336; // [rsp+108h] [rbp+8h] BYREF
  int v337; // [rsp+110h] [rbp+10h] BYREF
  const unsigned __int16 *v338; // [rsp+118h] [rbp+18h] BYREF
  __int64 v339; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v340; // [rsp+128h] [rbp+28h] BYREF
  std::_Ref_count_base *v341[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v342; // [rsp+140h] [rbp+40h] BYREF
  struct struct_dsreg_server_response *v343; // [rsp+148h] [rbp+48h]
  _QWORD *v344; // [rsp+150h] [rbp+50h] BYREF
  struct CLI_EXTENSIONS *v345; // [rsp+158h] [rbp+58h]
  _BYTE v346[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v347[32]; // [rsp+180h] [rbp+80h] BYREF
  _DWORD v348[4]; // [rsp+1A0h] [rbp+A0h]
  _BYTE v349[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v350[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v351[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v352[32]; // [rsp+210h] [rbp+110h] BYREF
  struct AutoJoinTelemetryInfo *v353; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v354[32]; // [rsp+238h] [rbp+138h] BYREF
  _QWORD v355[3]; // [rsp+258h] [rbp+158h] BYREF
  unsigned __int64 v356; // [rsp+270h] [rbp+170h]
  _QWORD v357[3]; // [rsp+278h] [rbp+178h] BYREF
  unsigned __int64 v358; // [rsp+290h] [rbp+190h]
  _QWORD v359[3]; // [rsp+298h] [rbp+198h] BYREF
  unsigned __int64 v360; // [rsp+2B0h] [rbp+1B0h]
  int v361; // [rsp+2B8h] [rbp+1B8h] BYREF
  char v362; // [rsp+2BCh] [rbp+1BCh]
  _BYTE v363[16]; // [rsp+2C0h] [rbp+1C0h] BYREF
  GUID ActivityId; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v365[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v366[16]; // [rsp+2E8h] [rbp+1E8h] BYREF
  WCHAR *v367; // [rsp+2F8h] [rbp+1F8h]
  _BYTE v368[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v369[32]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR ExeName[264]; // [rsp+350h] [rbp+250h] BYREF

  v343 = a3;
  v345 = a2;
  v330 = this;
  v361 = 0;
  v362 = 0;
  v318 = 0;
  *(_OWORD *)v341 = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v326 = 0;
  *(_OWORD *)v327 = 0;
  v328 = 0;
  DsrCmdDeviceEnroller::DsrCmdDeviceEnroller((DsrCmdDeviceEnroller *)v365);
  v334 = 0;
  AutoRegistrationJoinEventData = GetAutoRegistrationJoinEventData();
  AutoJoinTelemetryInfo::Reset(AutoRegistrationJoinEventData);
  v4 = &cchOriginalDestLength;
  if ( v367 )
    v4 = v367;
  v5 = (char **)((char *)GetAutoRegistrationJoinEventData() + 192);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( v4[v7] );
  std::wstring::_Assign<unsigned short>(v5, v4, (char *)v7);
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v9, v8) )
  {
    v10 = &cchOriginalDestLength;
    if ( v367 )
      v10 = v367;
    wprintf(L"%s: ClientRequestId: %s\n", L"DsrCmdJoinHelper::Join", v10);
    CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v12, v11);
    if ( *(_BYTE *)(*CurrentRef + 12LL) )
    {
      v15 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v14);
      if ( *(_QWORD *)(*v15 + 184LL) )
      {
        v17 = &cchOriginalDestLength;
        if ( v367 )
          v17 = v367;
        v18 = CmdOptions::GetCurrentRef(*v15, v16);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v18 + 184LL),
          L"%s: ClientRequestId: %s\n",
          L"DsrCmdJoinHelper::Join",
          v17);
      }
    }
  }
  v19 = &cchOriginalDestLength;
  if ( v367 )
    v19 = v367;
  Logger::TraceInformation(L"%s: ClientRequestId: %s\n", L"DsrCmdJoinHelper::Join", v19);
  v20 = PreJoinChecks(&v318);
  LODWORD(v336) = v20;
  if ( v20 < 0 )
  {
    v343 = (struct struct_dsreg_server_response *)v347;
    v21 = std::wstring::wstring((__int64)v347, (__int64)&cchOriginalDestLength);
    v330 = (DsrCmdJoinHelper *)v346;
    v22 = std::wstring::wstring((__int64)v346, (__int64)&cchOriginalDestLength);
    v331 = v350;
    v23 = std::wstring::wstring((__int64)v350, (__int64)&cchOriginalDestLength);
    v333 = (const unsigned __int16 *)v351;
    v24 = std::wstring::wstring((__int64)v351, (__int64)&cchOriginalDestLength);
    v324 = (const unsigned __int16 *)v352;
    v25 = std::wstring::wstring((__int64)v352, (__int64)&cchOriginalDestLength);
    v329 = v349;
    v26 = std::wstring::wstring((__int64)v349, (__int64)L"pre-check");
    v27 = GetAutoRegistrationJoinEventData();
    v28 = std::wstring::wstring(v354, (char *)v27 + 96);
    v29 = _time64(0);
    v313 = v24;
    v30 = (unsigned int)v336;
    RegistryHelper::WriteJoinDiagnosticInfo(v29, v28, v26, (unsigned int)v336, v25, 0, v313, v23, v22, v21);
    DsrCmdDeviceEnroller::~DsrCmdDeviceEnroller((DsrCmdDeviceEnroller *)v365);
    operator delete(Block[0]);
    Block[0] = 0;
    operator delete(Block[1]);
    Block[1] = 0;
    LODWORD(v326[0]) = 0;
    operator delete(v326[1]);
    v326[1] = 0;
    operator delete(v327[0]);
    v327[0] = 0;
    operator delete(v327[1]);
    v327[1] = 0;
    operator delete(v328);
    v328 = 0;
LABEL_275:
    if ( v341[1] )
      std::_Ref_count_base::_Decref(v341[1]);
    goto LABEL_277;
  }
  if ( v20 != 1 )
  {
    v40 = v318;
    if ( v318 )
      v41 = std::wstring::wstring((__int64)v354, (__int64)L"LeaveThenJoin");
    else
      v41 = std::wstring::wstring((__int64)v354, (__int64)L"Join");
    v42 = GetAutoRegistrationJoinEventData();
    std::wstring::operator=((__int64)v42, v41);
    std::wstring::_Tidy_deallocate((__int64)v354);
    AutoJoinPolicy = GetAutoJoinPolicy(L"Software\\Policies\\Microsoft\\Windows\\WorkplaceJoin", v43);
    v331 = AutoJoinPolicy;
    v46 = GetAutoJoinPolicy(L"SYSTEM\\CurrentControlSet\\Control\\WorkplaceJoin", v45);
    v333 = v46;
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hautojoinTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v361);
    if ( (unsigned int)dword_18013D928 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D928, 0x400000000000LL) )
    {
      v338 = v46;
      v336 = AutoJoinPolicy;
      v339 = 16779264;
      if ( !v362 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
        p_ActivityId = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)&dword_18013D928,
        (__int64)&word_18012B966,
        (__int64)v363,
        (__int64)p_ActivityId,
        (__int64)&v339,
        &v336,
        &v338);
    }
    if ( v40 )
    {
      if ( !IsAutoRejoinEnabled() )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v50, v49) )
        {
          wprintf(L"%s: Join state is incomplete but auto rejoin is disabled.\n", L"DsrCmdJoinHelper::Join");
          v97 = (_QWORD *)CmdOptions::GetCurrentRef(v96, v95);
          if ( *(_BYTE *)(*v97 + 12LL) )
          {
            v99 = (_QWORD *)CmdOptions::GetCurrentRef(*v97, v98);
            if ( *(_QWORD *)(*v99 + 184LL) )
            {
              v101 = CmdOptions::GetCurrentRef(v100, *v99);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v101 + 184LL),
                L"%s: Join state is incomplete but auto rejoin is disabled.\n",
                L"DsrCmdJoinHelper::Join");
            }
          }
        }
        Logger::TraceVerbose(
          (wchar_t *)L"%s: Join state is incomplete but auto rejoin is disabled.\n",
          L"DsrCmdJoinHelper::Join");
        v102 = GetAutoRegistrationJoinEventData();
        std::wstring::_Assign<unsigned short>((char **)v102 + 12, L"leaveThenJoinTelem", (char *)0x12);
        v103 = GetAutoRegistrationJoinEventData();
        std::wstring::_Assign<unsigned short>((char **)v103 + 20, L"leave", (char *)5);
        ComputerTokenForADRS = -2145648489;
        LODWORD(v323) = -2145648489;
LABEL_203:
        if ( v362 )
          EventActivityIdControl(4u, &ActivityId);
        v361 = 2;
        if ( (unsigned int)dword_18013D928 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D928, 0x400000000000LL) )
        {
          v240 = (struct AutoJoinTelemetryInfo *)((char *)GetAutoRegistrationJoinEventData() + 264);
          if ( *((_QWORD *)v240 + 3) > 7u )
            v240 = *(DsrCmdJoinHelper **)v240;
          v330 = v240;
          v241 = GetAutoRegistrationJoinEventData();
          if ( *((_QWORD *)v241 + 3) > 7u )
            v241 = *(struct AutoJoinTelemetryInfo **)v241;
          v331 = v241;
          v242 = (const unsigned __int16 *)((char *)GetAutoRegistrationJoinEventData() + 64);
          if ( *((_QWORD *)v242 + 3) > 7u )
            v242 = *(const unsigned __int16 **)v242;
          v333 = v242;
          v243 = (const unsigned __int16 *)((char *)GetAutoRegistrationJoinEventData() + 32);
          if ( *((_QWORD *)v243 + 3) > 7u )
            v243 = *(const unsigned __int16 **)v243;
          v324 = v243;
          v244 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 96);
          if ( v244[3] > 7u )
            v244 = (_QWORD *)*v244;
          v329 = v244;
          v245 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 160);
          if ( v245[3] > 7u )
            v245 = (_QWORD *)*v245;
          v332 = v245;
          v246 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 128);
          if ( v246[3] > 7u )
            v246 = (_QWORD *)*v246;
          v335 = v246;
          v247 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 192);
          if ( v247[3] > 7u )
            v247 = (_QWORD *)*v247;
          v340 = v247;
          AdalLogForTelemetry = (_QWORD *)GetAdalLogForTelemetry(v354);
          if ( AdalLogForTelemetry[3] > 7u )
            AdalLogForTelemetry = (_QWORD *)*AdalLogForTelemetry;
          v344 = AdalLogForTelemetry;
          LODWORD(v338) = ComputerTokenForADRS;
          v342 = 16779264;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (__int64)&dword_18013D928,
            (__int64)&dword_18012B7E4,
            (__int64)v363,
            v249,
            (__int64)&v342,
            (__int64)&v338,
            &v344,
            &v340,
            &v335,
            &v332,
            &v329,
            &v324,
            &v333,
            &v331,
            &v330);
          std::wstring::_Tidy_deallocate((__int64)v354);
        }
        if ( (ComputerTokenForADRS & 0x80000000) != 0 )
        {
          v259 = GetAutoRegistrationJoinEventData();
          String = AutoJoinTelemetryInfo::getString(v259, v354);
          v261 = (const unsigned __int16 *)String;
          if ( *(_QWORD *)(String + 24) > 7u )
            v261 = *(const unsigned __int16 **)String;
          v262 = GetAutoRegistrationJoinEventData();
          v263 = (const unsigned __int16 *)((char *)v262 + 96);
          if ( *((_QWORD *)v262 + 15) > 7u )
            v263 = *(const unsigned __int16 **)v263;
          v264 = GetAutoRegistrationJoinEventData();
          v265 = (const unsigned __int16 *)((char *)v264 + 32);
          if ( *((_QWORD *)v264 + 7) > 7u )
            v265 = *(const unsigned __int16 **)v265;
          v266 = &cchOriginalDestLength;
          if ( v327[1] )
            v266 = v327[1];
          Logger::WriteDsRegCmdJoinFailureEvent(ComputerTokenForADRS, v266, v265, v263, v261);
          std::wstring::_Tidy_deallocate((__int64)v354);
          v267 = GetAutoRegistrationJoinEventData();
          v268 = (_QWORD *)((char *)v267 + 160);
          if ( *((_QWORD *)v267 + 23) > 7u )
            v268 = (_QWORD *)*v268;
          v269 = std::_Traits_equal<std::char_traits<unsigned short>>(v268, *((_QWORD *)v267 + 22), L"auth", 4);
          v270 = &cchOriginalDestLength;
          if ( v269 )
          {
            v330 = (DsrCmdJoinHelper *)v354;
            v271 = std::wstring::wstring((__int64)v354, (__int64)&cchOriginalDestLength);
            v331 = v349;
            v272 = std::wstring::wstring((__int64)v349, (__int64)&cchOriginalDestLength);
            v333 = (const unsigned __int16 *)v352;
            v273 = std::wstring::wstring((__int64)v352, (__int64)&cchOriginalDestLength);
            v324 = (const unsigned __int16 *)v351;
            v274 = std::wstring::wstring((__int64)v351, (__int64)&cchOriginalDestLength);
            v329 = v350;
            v275 = GetAutoRegistrationJoinEventData();
            v276 = std::wstring::wstring(v350, (char *)v275 + 192);
            v332 = v347;
            v277 = GetAutoRegistrationJoinEventData();
            v278 = std::wstring::wstring(v347, (char *)v277 + 160);
            v279 = GetAutoRegistrationJoinEventData();
            v280 = std::wstring::wstring(v346, (char *)v279 + 96);
            v281 = _time64(0);
            v317 = (DsrCmdJoinHelper *)v271;
            v316 = v272;
            v315 = v273;
            v314 = v274;
            v312 = 0;
          }
          else
          {
            v331 = v354;
            if ( v327[1] )
              v270 = v327[1];
            v330 = (DsrCmdJoinHelper *)std::wstring::wstring((__int64)v354, (__int64)v270);
            v333 = (const unsigned __int16 *)v349;
            v282 = &cchOriginalDestLength;
            if ( v328 )
              v282 = (const WCHAR *)v328;
            v283 = std::wstring::wstring((__int64)v349, (__int64)v282);
            v324 = (const unsigned __int16 *)v352;
            v284 = &cchOriginalDestLength;
            if ( v327[0] )
              v284 = v327[0];
            v285 = std::wstring::wstring((__int64)v352, (__int64)v284);
            v329 = v351;
            v286 = &cchOriginalDestLength;
            if ( v326[1] )
              v286 = (const WCHAR *)v326[1];
            v287 = std::wstring::wstring((__int64)v351, (__int64)v286);
            v288 = (int)v326[0];
            v332 = v350;
            v289 = &cchOriginalDestLength;
            if ( Block[0] )
              v289 = (const WCHAR *)Block[0];
            v276 = std::wstring::wstring((__int64)v350, (__int64)v289);
            v335 = v347;
            v290 = GetAutoRegistrationJoinEventData();
            v278 = std::wstring::wstring(v347, (char *)v290 + 160);
            v291 = GetAutoRegistrationJoinEventData();
            v280 = std::wstring::wstring(v346, (char *)v291 + 96);
            v281 = _time64(0);
            v317 = v330;
            v316 = v283;
            v315 = v285;
            v314 = v287;
            v312 = v288;
          }
          v30 = (unsigned int)v323;
          RegistryHelper::WriteJoinDiagnosticInfo(
            v281,
            v280,
            v278,
            (unsigned int)v323,
            v276,
            v312,
            v314,
            v315,
            v316,
            v317);
        }
        else
        {
          Logger::WriteDsRegCmdJoinSuccessEvent();
          v330 = (DsrCmdJoinHelper *)v354;
          v250 = std::wstring::wstring((__int64)v354, (__int64)&cchOriginalDestLength);
          v331 = v349;
          v251 = std::wstring::wstring((__int64)v349, (__int64)&cchOriginalDestLength);
          v333 = (const unsigned __int16 *)v352;
          v252 = std::wstring::wstring((__int64)v352, (__int64)&cchOriginalDestLength);
          v324 = (const unsigned __int16 *)v351;
          v253 = std::wstring::wstring((__int64)v351, (__int64)&cchOriginalDestLength);
          v329 = v350;
          v254 = std::wstring::wstring((__int64)v350, (__int64)&cchOriginalDestLength);
          v332 = v347;
          v255 = std::wstring::wstring((__int64)v347, (__int64)&cchOriginalDestLength);
          v256 = GetAutoRegistrationJoinEventData();
          v257 = std::wstring::wstring(v346, (char *)v256 + 96);
          v258 = _time64(0);
          RegistryHelper::WriteJoinDiagnosticInfo(v258, v257, v255, 0, v254, 0, v253, v252, v251, v250);
          v30 = (unsigned int)v323;
        }
        DsregServerResponse::MoveTo((DsregServerResponse *)Block, v343);
        operator delete(v334);
        v334 = 0;
        std::wstring::wstring((__int64)v359);
        std::wstring::wstring((__int64)v357);
        std::wstring::wstring((__int64)v355);
        std::wstring::wstring((__int64)v368);
        std::wstring::wstring((__int64)v369);
        v322[0] = 0;
        v321 = 0;
        DsrCmdStatusHelper::GetStatusAadJoin(
          (unsigned int)v359,
          (unsigned int)v357,
          (unsigned int)v355,
          (unsigned int)v368,
          (__int64)v369,
          (__int64)v322,
          (__int64)&v321);
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v293, v292) )
        {
          v294 = v355;
          if ( v356 > 7 )
            v294 = (_QWORD *)v355[0];
          v295 = v357;
          if ( v358 > 7 )
            v295 = (_QWORD *)v357[0];
          v296 = v359;
          if ( v360 > 7 )
            v296 = (_QWORD *)v359[0];
          wprintf(L"DSREGCMD_END_STATUS\n%s%s%s", v296, v295, v294);
          v299 = (_QWORD *)CmdOptions::GetCurrentRef(v298, v297);
          if ( *(_BYTE *)(*v299 + 12LL) )
          {
            v301 = (_QWORD *)CmdOptions::GetCurrentRef(*v299, v300);
            if ( *(_QWORD *)(*v301 + 184LL) )
            {
              v303 = v355;
              if ( v356 > 7 )
                v303 = (_QWORD *)v355[0];
              v304 = v357;
              if ( v358 > 7 )
                v304 = (_QWORD *)v357[0];
              v305 = v359;
              if ( v360 > 7 )
                v305 = (_QWORD *)v359[0];
              v306 = CmdOptions::GetCurrentRef(*v301, v302);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)v306 + 184LL), L"DSREGCMD_END_STATUS\n%s%s%s", v305, v304, v303);
            }
          }
        }
        v307 = v355;
        if ( v356 > 7 )
          v307 = (_QWORD *)v355[0];
        v308 = v357;
        if ( v358 > 7 )
          v308 = (_QWORD *)v357[0];
        v309 = v359;
        if ( v360 > 7 )
          v309 = (_QWORD *)v359[0];
        Logger::TraceInformation(L"DSREGCMD_END_STATUS\n%s%s%s", v309, v308, v307);
        std::wstring::_Tidy_deallocate((__int64)v369);
        std::wstring::_Tidy_deallocate((__int64)v368);
        std::wstring::_Tidy_deallocate((__int64)v355);
        std::wstring::_Tidy_deallocate((__int64)v357);
        std::wstring::_Tidy_deallocate((__int64)v359);
        DsrCmdDeviceEnroller::~DsrCmdDeviceEnroller((DsrCmdDeviceEnroller *)v365);
        operator delete(Block[0]);
        Block[0] = 0;
        operator delete(Block[1]);
        Block[1] = 0;
        LODWORD(v326[0]) = 0;
        operator delete(v326[1]);
        v326[1] = 0;
        operator delete(v327[0]);
        v327[0] = 0;
        operator delete(v327[1]);
        v327[1] = 0;
        operator delete(v328);
        v328 = 0;
        goto LABEL_275;
      }
      memset_0(ExeName, 0, 0x208u);
      ParentProcessName = GetParentProcessName(ExeName, v51);
      if ( ParentProcessName < 0 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v53, v52) )
        {
          wprintf(L"WARNING! GetParentProcessName failed with 0x%08x.\n", (unsigned int)ParentProcessName);
          v57 = (_QWORD *)CmdOptions::GetCurrentRef(v56, v55);
          if ( *(_BYTE *)(*v57 + 12LL) )
          {
            v59 = (_QWORD *)CmdOptions::GetCurrentRef(*v57, v58);
            if ( *(_QWORD *)(*v59 + 184LL) )
            {
              v61 = CmdOptions::GetCurrentRef(*v59, v60);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v61 + 184LL),
                L"WARNING! GetParentProcessName failed with 0x%08x.\n",
                (unsigned int)ParentProcessName);
            }
          }
        }
        StringCchCopyW(ExeName, 0x104u, L"<error>");
      }
      Logger::WriteDsRegCmdLeaveThenJoinEvent(ExeName);
      v62 = GetAutoRegistrationJoinEventData();
      std::wstring::_Assign<unsigned short>((char **)v62 + 12, L"leave", (char *)5);
      ComputerTokenForADRS = DsrCmdDeviceEnroller::Leave(
                               (DsrCmdDeviceEnroller *)v365,
                               (struct DsregServerResponse *)Block,
                               1);
      LODWORD(v323) = ComputerTokenForADRS;
      if ( (ComputerTokenForADRS & 0x80000000) != 0 )
      {
        v64 = GetAutoRegistrationJoinEventData();
        std::wstring::_Assign<unsigned short>((char **)v64 + 20, L"leave", (char *)5);
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v66, v65) )
        {
          wprintf(L"%s: DsrCmdDeviceEnroller::Leave failed 0x%08x.\n", L"DsrCmdJoinHelper::Join", ComputerTokenForADRS);
          v69 = (_QWORD *)CmdOptions::GetCurrentRef(v68, v67);
          if ( *(_BYTE *)(*v69 + 12LL) )
          {
            v71 = (_QWORD *)CmdOptions::GetCurrentRef(*v69, v70);
            if ( *(_QWORD *)(*v71 + 184LL) )
            {
              v73 = CmdOptions::GetCurrentRef(*v71, v72);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v73 + 184LL),
                L"%s: DsrCmdDeviceEnroller::Leave failed 0x%08x.\n",
                L"DsrCmdJoinHelper::Join",
                ComputerTokenForADRS);
            }
          }
        }
        Logger::TraceError(
          L"%s: DsrCmdDeviceEnroller::Leave failed 0x%08x.\n",
          L"DsrCmdJoinHelper::Join",
          ComputerTokenForADRS);
        goto LABEL_203;
      }
      v76 = RegistryHelper::IncrementCounter(0);
      if ( (v76 & 0x80000000) != 0 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v75, v74) )
        {
          wprintf(
            L"%s: RegistryHelper::IncrementCounter(REG_STATISTICS_COUNTER_RECOVERY_START_COUNT) failed 0x%08x.\n",
            L"DsrCmdJoinHelper::Join",
            v76);
          v79 = (_QWORD *)CmdOptions::GetCurrentRef(v78, v77);
          if ( *(_BYTE *)(*v79 + 12LL) )
          {
            v81 = (_QWORD *)CmdOptions::GetCurrentRef(*v79, v80);
            if ( *(_QWORD *)(*v81 + 184LL) )
            {
              v83 = CmdOptions::GetCurrentRef(*v81, v82);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v83 + 184LL),
                L"%s: RegistryHelper::IncrementCounter(REG_STATISTICS_COUNTER_RECOVERY_START_COUNT) failed 0x%08x.\n",
                L"DsrCmdJoinHelper::Join",
                v76);
            }
          }
        }
        Logger::TraceError(
          L"%s: RegistryHelper::IncrementCounter(REG_STATISTICS_COUNTER_RECOVERY_START_COUNT) failed 0x%08x.\n",
          L"DsrCmdJoinHelper::Join",
          v76);
      }
    }
    v84 = (unsigned __int16 *)&cchOriginalDestLength;
    if ( v367 )
      v84 = v367;
    ComputerTokenForADRS = TenantInfo::Discover((unsigned __int64 *)v341, v84, (__int64)Block);
    LODWORD(v323) = ComputerTokenForADRS;
    if ( (ComputerTokenForADRS & 0x80000000) != 0 )
    {
      v85 = GetAutoRegistrationJoinEventData();
      std::wstring::_Assign<unsigned short>((char **)v85 + 20, L"discover", (char *)8);
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v87, v86) )
      {
        wprintf(
          L"%s: TenantInfo::Discover failed with error code 0x%08x.\n",
          L"DsrCmdJoinHelper::Join",
          ComputerTokenForADRS);
        v90 = (_QWORD *)CmdOptions::GetCurrentRef(v89, v88);
        if ( *(_BYTE *)(*v90 + 12LL) )
        {
          v92 = (_QWORD *)CmdOptions::GetCurrentRef(*v90, v91);
          if ( *(_QWORD *)(*v92 + 184LL) )
          {
            v94 = CmdOptions::GetCurrentRef(*v92, v93);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v94 + 184LL),
              L"%s: TenantInfo::Discover failed with error code 0x%08x.\n",
              L"DsrCmdJoinHelper::Join",
              ComputerTokenForADRS);
          }
        }
      }
      Logger::TraceError(
        L"%s: TenantInfo::Discover failed with error code 0x%08x.\n",
        L"DsrCmdJoinHelper::Join",
        ComputerTokenForADRS);
      if ( ComputerTokenForADRS == -2145648611 )
        Logger::WriteDsRegCmdConfigFailureEvent(-2145648611);
      else
        Logger::WriteDsRegCmdDiscFailureEvent(ComputerTokenForADRS);
      goto LABEL_203;
    }
    operator delete(Block[0]);
    Block[0] = 0;
    operator delete(Block[1]);
    Block[1] = 0;
    LODWORD(v326[0]) = 0;
    operator delete(v326[1]);
    v326[1] = 0;
    operator delete(v327[0]);
    v327[0] = 0;
    operator delete(v327[1]);
    v327[1] = 0;
    operator delete(v328);
    v328 = 0;
    v318 = IsSimulateSyncJoinEnabled();
    v319 = IsSimulateFedJoinEnabled();
    v104 = *((_DWORD *)v341[0] + 3);
    LODWORD(v336) = v104;
    v105 = *((_DWORD *)v341[0] + 60);
    LODWORD(v339) = v105;
    v106 = &cchOriginalDestLength;
    if ( *((_QWORD *)v341[0] + 27) )
      v106 = (const WCHAR *)*((_QWORD *)v341[0] + 27);
    v107 = std::wstring::wstring((__int64)v354, (__int64)v106);
    v108 = GetAutoRegistrationJoinEventData();
    std::wstring::operator=((__int64)v108 + 64, v107);
    std::wstring::_Tidy_deallocate((__int64)v354);
    v109 = L"ent";
    if ( v105 != 1 )
      v109 = L"azure";
    v110 = (char **)((char *)GetAutoRegistrationJoinEventData() + 264);
    v111 = -1;
    do
      ++v111;
    while ( v109[v111] );
    std::wstring::_Assign<unsigned short>(v110, v109, (char *)v111);
    v112 = L"Federated";
    if ( v104 )
      v112 = L"Managed";
    v113 = (char **)((char *)GetAutoRegistrationJoinEventData() + 32);
    do
      ++v6;
    while ( v112[v6] );
    std::wstring::_Assign<unsigned short>(v113, v112, (char *)v6);
    v348[0] = 15;
    v348[1] = 10;
    v348[2] = 7;
    v116 = 1;
    v320 = 0;
    v337 = 0;
    v117 = 0;
    while ( 1 )
    {
      v118 = v348[v117];
      if ( v118 == 7 )
      {
        if ( (_DWORD)v339 == 1 && !v318 )
          goto LABEL_196;
        if ( v116 )
        {
          if ( !(_DWORD)v336 && v318 )
          {
            v165 = GetAutoRegistrationJoinEventData();
            v169 = 8;
            v166 = L"sim_sync";
            goto LABEL_155;
          }
          v165 = GetAutoRegistrationJoinEventData();
          v166 = L"sync";
LABEL_154:
          v169 = 4;
          goto LABEL_155;
        }
        if ( !IsFallbackToSyncJoinEnabled() )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v155, v154) )
          {
            wprintf(L"%s: Fallback to sync join is disabled.\n", L"DsrCmdJoinHelper::Join");
            v158 = (_QWORD *)CmdOptions::GetCurrentRef(v157, v156);
            if ( *(_BYTE *)(*v158 + 12LL) )
            {
              v160 = (_QWORD *)CmdOptions::GetCurrentRef(*v158, v159);
              if ( *(_QWORD *)(*v160 + 184LL) )
              {
                v162 = CmdOptions::GetCurrentRef(*v160, v161);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v162 + 184LL),
                  L"%s: Fallback to sync join is disabled.\n",
                  L"DsrCmdJoinHelper::Join");
              }
            }
          }
          Logger::TraceInformation(L"%s: Fallback to sync join is disabled.\n", L"DsrCmdJoinHelper::Join");
          goto LABEL_196;
        }
      }
      else if ( v118 == 10 )
      {
        if ( (_DWORD)v336 || v318 )
          goto LABEL_196;
        if ( v116 )
        {
          if ( v319 )
          {
            v167 = L"sim_fed";
            v168 = 7;
          }
          else
          {
            v167 = L"fed";
            v168 = 3;
          }
LABEL_148:
          v165 = GetAutoRegistrationJoinEventData();
          v169 = v168;
          v166 = v167;
LABEL_155:
          std::wstring::_Assign<unsigned short>((char **)v165 + 12, v166, (char *)v169);
          goto LABEL_156;
        }
        if ( !IsFallbackToFedJoinEnabled() )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v146, v145) )
          {
            wprintf(L"%s: Fallback to federated join is disabled.\n", L"DsrCmdJoinHelper::Join");
            v149 = (_QWORD *)CmdOptions::GetCurrentRef(v148, v147);
            if ( *(_BYTE *)(*v149 + 12LL) )
            {
              v151 = (_QWORD *)CmdOptions::GetCurrentRef(*v149, v150);
              if ( *(_QWORD *)(*v151 + 184LL) )
              {
                v153 = CmdOptions::GetCurrentRef(*v151, v152);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v153 + 184LL),
                  L"%s: Fallback to federated join is disabled.\n",
                  L"DsrCmdJoinHelper::Join");
              }
            }
          }
          Logger::TraceInformation(L"%s: Fallback to federated join is disabled.\n", L"DsrCmdJoinHelper::Join");
          goto LABEL_196;
        }
      }
      else
      {
        if ( v118 == 15 )
        {
          if ( (_DWORD)v339 == 1 || v318 || v319 )
            goto LABEL_196;
          if ( (unsigned int)IsEmptyString(*(const unsigned __int16 **)(*(_QWORD *)v341[0] + 224LL))
            || (unsigned int)IsEmptyString(*(const unsigned __int16 **)(v114 + 216)) )
          {
            if ( **(_BYTE **)CmdOptions::GetCurrentRef(v115, v114) )
            {
              wprintf(L"%s: Kerberos discovery data not available. Skip kerb join.", L"DsrCmdJoinHelper::Join");
              v121 = (_QWORD *)CmdOptions::GetCurrentRef(v120, v119);
              if ( *(_BYTE *)(*v121 + 12LL) )
              {
                v123 = (_QWORD *)CmdOptions::GetCurrentRef(*v121, v122);
                if ( *(_QWORD *)(*v123 + 184LL) )
                {
                  v125 = CmdOptions::GetCurrentRef(*v123, v124);
                  fwprintf_s(
                    *(FILE *const *)(*(_QWORD *)v125 + 184LL),
                    L"%s: Kerberos discovery data not available. Skip kerb join.",
                    L"DsrCmdJoinHelper::Join");
                }
              }
            }
            Logger::TraceInformation(
              L"%s: Kerberos discovery data not available. Skip kerb join.",
              L"DsrCmdJoinHelper::Join");
            goto LABEL_196;
          }
        }
        if ( v116 )
          goto LABEL_142;
      }
      if ( (unsigned int)dword_18013D928 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D928, 0x400000000000LL) )
      {
        v126 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 264);
        if ( v126[3] > 7u )
          v126 = (_QWORD *)*v126;
        v323 = v126;
        v127 = GetAutoRegistrationJoinEventData();
        if ( *((_QWORD *)v127 + 3) > 7u )
          v127 = *(struct AutoJoinTelemetryInfo **)v127;
        v353 = v127;
        v128 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 64);
        if ( v128[3] > 7u )
          v128 = (_QWORD *)*v128;
        v342 = (__int64)v128;
        v129 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 32);
        if ( v129[3] > 7u )
          v129 = (_QWORD *)*v129;
        v344 = v129;
        v130 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 96);
        if ( v130[3] > 7u )
          v130 = (_QWORD *)*v130;
        v340 = v130;
        v131 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 160);
        if ( v131[3] > 7u )
          v131 = (_QWORD *)*v131;
        v335 = v131;
        v132 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 128);
        if ( v132[3] > 7u )
          v132 = (_QWORD *)*v132;
        v332 = v132;
        v133 = (_QWORD *)((char *)GetAutoRegistrationJoinEventData() + 192);
        if ( v133[3] > 7u )
          v133 = (_QWORD *)*v133;
        v329 = v133;
        v134 = (const unsigned __int16 *)GetAdalLogForTelemetry(v354);
        if ( *((_QWORD *)v134 + 3) > 7u )
          v134 = *(const unsigned __int16 **)v134;
        v324 = v134;
        LODWORD(v338) = ComputerTokenForADRS;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)&dword_18013D928,
          (__int64)word_18012BAEA,
          (__int64)v363,
          v135,
          (__int64)&v338,
          &v324,
          &v329,
          &v332,
          &v335,
          &v340,
          &v344,
          &v342,
          &v353,
          &v323);
        std::wstring::_Tidy_deallocate((__int64)v354);
      }
      v136 = GetAutoRegistrationJoinEventData();
      v137 = AutoJoinTelemetryInfo::getString(v136, v354);
      v138 = (const unsigned __int16 *)v137;
      if ( *(_QWORD *)(v137 + 24) > 7u )
        v138 = *(const unsigned __int16 **)v137;
      v139 = GetAutoRegistrationJoinEventData();
      v140 = (const unsigned __int16 *)((char *)v139 + 96);
      if ( *((_QWORD *)v139 + 15) > 7u )
        v140 = *(const unsigned __int16 **)v140;
      v141 = GetAutoRegistrationJoinEventData();
      v142 = (const unsigned __int16 *)((char *)v141 + 32);
      if ( *((_QWORD *)v141 + 7) > 7u )
        v142 = *(const unsigned __int16 **)v142;
      v143 = &cchOriginalDestLength;
      if ( v327[1] )
        v143 = v327[1];
      Logger::WriteDsRegCmdJoinFailureEvent(ComputerTokenForADRS, v143, v142, v140, v138);
      std::wstring::_Tidy_deallocate((__int64)v354);
      if ( (unsigned int)dword_18013D928 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D928, 0x400000000000LL) )
      {
        v324 = v333;
        v329 = v331;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (__int64)&dword_18013D928,
          (__int64)byte_18012BA01,
          (__int64)v363,
          v144,
          &v329,
          &v324);
      }
      v163 = GetAutoRegistrationJoinEventData();
      std::wstring::_Assign<unsigned short>((char **)v163 + 20, L"undefined", (char *)9);
      v164 = GetAutoRegistrationJoinEventData();
      std::wstring::_Assign<unsigned short>((char **)v164 + 28, L"undefined", (char *)9);
      *((_DWORD *)GetAutoRegistrationJoinEventData() + 64) = 0;
      operator delete(Block[0]);
      Block[0] = 0;
      operator delete(Block[1]);
      Block[1] = 0;
      LODWORD(v326[0]) = 0;
      operator delete(v326[1]);
      v326[1] = 0;
      operator delete(v327[0]);
      v327[0] = 0;
      operator delete(v327[1]);
      v327[1] = 0;
      operator delete(v328);
      v328 = 0;
      if ( v118 == 7 )
      {
        v165 = GetAutoRegistrationJoinEventData();
        v169 = 13;
        v166 = L"fallback_sync";
        goto LABEL_155;
      }
      if ( v118 == 10 )
      {
        v167 = L"fallback_fed";
        v168 = 12;
        goto LABEL_148;
      }
LABEL_142:
      if ( v118 == 15 )
      {
        v165 = GetAutoRegistrationJoinEventData();
        v166 = L"kerb";
        goto LABEL_154;
      }
LABEL_156:
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v115, v114) )
      {
        JoinTypeName = GetJoinTypeName(v118, v170, v171, v172);
        wprintf(L"%s: Performing join type %s...\n", L"DsrCmdJoinHelper::Join", JoinTypeName);
        v176 = (_QWORD *)CmdOptions::GetCurrentRef(v175, v174);
        if ( *(_BYTE *)(*v176 + 12LL) )
        {
          v177 = (_QWORD *)CmdOptions::GetCurrentRef(*v176, v170);
          if ( *(_QWORD *)(*v177 + 184LL) )
          {
            v178 = CmdOptions::GetCurrentRef(*v177, v170);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v178 + 184LL),
              L"%s: Performing join type %s...\n",
              L"DsrCmdJoinHelper::Join",
              JoinTypeName);
          }
        }
      }
      v179 = GetJoinTypeName(v118, v170, v171, v172);
      Logger::TraceInformation(L"%s: Performing join type %s...\n", L"DsrCmdJoinHelper::Join", v179);
      v116 = 0;
      operator delete(v334);
      v181 = 0;
      v334 = 0;
      if ( v118 == 10 )
      {
        v192 = (__int64 **)std::shared_ptr<TenantInfo>::shared_ptr<TenantInfo>(v346, v341, v180, 0, v311);
        ComputerTokenForADRS = GetComputerTokenForADRS(
                                 *(__int64 (__fastcall **)(char **, const WCHAR *, _QWORD, const wchar_t *, int, __int64, __int64, void (*)(unsigned int, const unsigned __int16 *), void **))v345,
                                 v192,
                                 &v334,
                                 (__int64)v366);
        LODWORD(v323) = ComputerTokenForADRS;
        if ( (ComputerTokenForADRS & 0x80000000) != 0 )
        {
          v193 = GetAutoRegistrationJoinEventData();
          std::wstring::_Assign<unsigned short>((char **)v193 + 20, L"auth", (char *)4);
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v195, v194) )
          {
            wprintf(
              L"%s: Unable to retrieve access token. GetComputerTokenForADRS failed with error 0x%08x.\n",
              L"DsrCmdJoinHelper::Join",
              ComputerTokenForADRS);
            v198 = (_QWORD *)CmdOptions::GetCurrentRef(v197, v196);
            if ( *(_BYTE *)(*v198 + 12LL) )
            {
              v200 = (_QWORD *)CmdOptions::GetCurrentRef(*v198, v199);
              if ( *(_QWORD *)(*v200 + 184LL) )
              {
                v202 = CmdOptions::GetCurrentRef(*v200, v201);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v202 + 184LL),
                  L"%s: Unable to retrieve access token. GetComputerTokenForADRS failed with error 0x%08x.\n",
                  L"DsrCmdJoinHelper::Join",
                  ComputerTokenForADRS);
              }
            }
          }
          Logger::TraceError(
            L"%s: Unable to retrieve access token. GetComputerTokenForADRS failed with error 0x%08x.\n",
            L"DsrCmdJoinHelper::Join",
            ComputerTokenForADRS);
          if ( *((int *)GetAutoRegistrationJoinEventData() + 64) < 0 )
          {
            ComputerTokenForADRS = *((_DWORD *)GetAutoRegistrationJoinEventData() + 64);
            LODWORD(v323) = ComputerTokenForADRS;
          }
          goto LABEL_196;
        }
LABEL_175:
        v181 = v334;
        goto LABEL_176;
      }
      if ( v118 == 15 )
      {
        ComputerTokenForADRS = DsrCmdJoinHelper::GetCloudKerbToken(
                                 (HANDLE *)v330,
                                 v345,
                                 *(const unsigned __int16 **)(*(_QWORD *)v341[0] + 224LL),
                                 *(const unsigned __int16 **)(*(_QWORD *)v341[0] + 216LL),
                                 &v334,
                                 &v337);
        LODWORD(v323) = ComputerTokenForADRS;
        if ( (ComputerTokenForADRS & 0x80000000) != 0 )
        {
          v182 = GetAutoRegistrationJoinEventData();
          std::wstring::_Assign<unsigned short>((char **)v182 + 20, L"auth", (char *)4);
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v184, v183) )
          {
            wprintf(
              L"%s: Unable to retrieve Kerberos ticket. GetCloudKerbTicket failed with error 0x%08x.\n",
              L"DsrCmdJoinHelper::Join",
              ComputerTokenForADRS);
            v187 = (_QWORD *)CmdOptions::GetCurrentRef(v186, v185);
            if ( *(_BYTE *)(*v187 + 12LL) )
            {
              v189 = (_QWORD *)CmdOptions::GetCurrentRef(*v187, v188);
              if ( *(_QWORD *)(*v189 + 184LL) )
              {
                v191 = CmdOptions::GetCurrentRef(*v189, v190);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v191 + 184LL),
                  L"%s: Unable to retrieve Kerberos ticket. GetCloudKerbTicket failed with error 0x%08x.\n",
                  L"DsrCmdJoinHelper::Join",
                  ComputerTokenForADRS);
              }
            }
          }
          Logger::TraceError(
            L"%s: Unable to retrieve Kerberos ticket. GetCloudKerbTicket failed with error 0x%08x.\n",
            L"DsrCmdJoinHelper::Join",
            ComputerTokenForADRS);
          goto LABEL_196;
        }
        goto LABEL_175;
      }
LABEL_176:
      v203 = (_QWORD **)std::shared_ptr<TenantInfo>::shared_ptr<TenantInfo>(v347, v341, v180, v181, v311);
      ComputerTokenForADRS = DsrCmdDeviceEnroller::AutoEnroll((DsrCmdDeviceEnroller *)v365, v118, v203, v204, 0, Block);
      LODWORD(v323) = ComputerTokenForADRS;
      if ( (ComputerTokenForADRS & 0x80000000) == 0 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v206, v205) )
        {
          wprintf(
            L"%s: DsrCmdDeviceEnroller::AutoEnroll(%s) completed successfully.\n",
            L"DsrCmdJoinHelper::Join",
            v179);
          v235 = (_QWORD *)CmdOptions::GetCurrentRef(v234, v233);
          if ( *(_BYTE *)(*v235 + 12LL) )
          {
            v237 = (_QWORD *)CmdOptions::GetCurrentRef(*v235, v236);
            if ( *(_QWORD *)(*v237 + 184LL) )
            {
              v239 = CmdOptions::GetCurrentRef(*v237, v238);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v239 + 184LL),
                L"%s: DsrCmdDeviceEnroller::AutoEnroll(%s) completed successfully.\n",
                L"DsrCmdJoinHelper::Join",
                v179);
            }
          }
        }
        Logger::TraceVerbose(
          (wchar_t *)L"%s: DsrCmdDeviceEnroller::AutoEnroll(%s) completed successfully.\n",
          L"DsrCmdJoinHelper::Join",
          v179);
        goto LABEL_203;
      }
      v207 = GetAutoRegistrationJoinEventData();
      std::wstring::_Assign<unsigned short>((char **)v207 + 20, L"join", (char *)4);
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v209, v208) )
      {
        wprintf(
          L"%s: DsrCmdDeviceEnroller::AutoEnroll(%s) failed with error code 0x%08x.\n",
          L"DsrCmdJoinHelper::Join",
          v179,
          ComputerTokenForADRS);
        v212 = (_QWORD *)CmdOptions::GetCurrentRef(v211, v210);
        if ( *(_BYTE *)(*v212 + 12LL) )
        {
          v214 = (_QWORD *)CmdOptions::GetCurrentRef(*v212, v213);
          if ( *(_QWORD *)(*v214 + 184LL) )
          {
            v216 = CmdOptions::GetCurrentRef(*v214, v215);
            LODWORD(v311) = ComputerTokenForADRS;
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v216 + 184LL),
              L"%s: DsrCmdDeviceEnroller::AutoEnroll(%s) failed with error code 0x%08x.\n",
              L"DsrCmdJoinHelper::Join",
              v179);
          }
        }
      }
      Logger::TraceError(
        L"%s: DsrCmdDeviceEnroller::AutoEnroll(%s) failed with error code 0x%08x.\n",
        L"DsrCmdJoinHelper::Join",
        v179,
        ComputerTokenForADRS);
      if ( v118 == 15 && !v320 && ComputerTokenForADRS == -2145648491 && !v337 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v115, v114) )
        {
          wprintf(L"%s: Purge cached Kerberos tickets and KDC proxy, then try again.\n", L"DsrCmdJoinHelper::Join");
          v219 = (_QWORD *)CmdOptions::GetCurrentRef(v218, v217);
          if ( *(_BYTE *)(*v219 + 12LL) )
          {
            v221 = (_QWORD *)CmdOptions::GetCurrentRef(*v219, v220);
            if ( *(_QWORD *)(*v221 + 184LL) )
            {
              v223 = CmdOptions::GetCurrentRef(*v221, v222);
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v223 + 184LL),
                L"%s: Purge cached Kerberos tickets and KDC proxy, then try again.\n",
                L"DsrCmdJoinHelper::Join");
            }
          }
        }
        Logger::TraceInformation(
          L"%s: Purge cached Kerberos tickets and KDC proxy, then try again.\n",
          L"DsrCmdJoinHelper::Join");
        ComputerTokenForADRS = DsrCmdJoinHelper::PurgeKerbCache(v225, v224, 0);
        LODWORD(v323) = ComputerTokenForADRS;
        if ( (ComputerTokenForADRS & 0x80000000) != 0 )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef(v115, v114) )
          {
            wprintf(
              L"%s: Failed to purge Kerberos tickets or proxy. Error code: 0x%08x.\n",
              L"DsrCmdJoinHelper::Join",
              ComputerTokenForADRS);
            v228 = (_QWORD *)CmdOptions::GetCurrentRef(v227, v226);
            if ( *(_BYTE *)(*v228 + 12LL) )
            {
              v230 = (_QWORD *)CmdOptions::GetCurrentRef(*v228, v229);
              if ( *(_QWORD *)(*v230 + 184LL) )
              {
                v232 = CmdOptions::GetCurrentRef(*v230, v231);
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v232 + 184LL),
                  L"%s: Failed to purge Kerberos tickets or proxy. Error code: 0x%08x.\n",
                  L"DsrCmdJoinHelper::Join",
                  ComputerTokenForADRS);
              }
            }
          }
          Logger::TraceWarning(
            (wchar_t *)L"%s: Failed to purge Kerberos tickets or proxy. Error code: 0x%08x.\n",
            L"DsrCmdJoinHelper::Join",
            ComputerTokenForADRS);
          ComputerTokenForADRS = 0;
          LODWORD(v323) = 0;
        }
        --v117;
        v320 = 1;
      }
LABEL_196:
      if ( (unsigned int)++v117 >= 3 )
        goto LABEL_203;
    }
  }
  v343 = (struct struct_dsreg_server_response *)v354;
  v31 = std::wstring::wstring((__int64)v354, (__int64)&cchOriginalDestLength);
  v330 = (DsrCmdJoinHelper *)v349;
  v32 = std::wstring::wstring((__int64)v349, (__int64)&cchOriginalDestLength);
  v331 = v352;
  v33 = std::wstring::wstring((__int64)v352, (__int64)&cchOriginalDestLength);
  v333 = (const unsigned __int16 *)v351;
  v34 = std::wstring::wstring((__int64)v351, (__int64)&cchOriginalDestLength);
  v324 = (const unsigned __int16 *)v350;
  v35 = std::wstring::wstring((__int64)v350, (__int64)&cchOriginalDestLength);
  v329 = v347;
  v36 = std::wstring::wstring((__int64)v347, (__int64)L"pre-check");
  v37 = GetAutoRegistrationJoinEventData();
  v38 = std::wstring::wstring(v346, (char *)v37 + 96);
  v39 = _time64(0);
  RegistryHelper::WriteJoinDiagnosticInfo(v39, v38, v36, 1, v35, 0, v34, v33, v32, v31);
  DsrCmdDeviceEnroller::~DsrCmdDeviceEnroller((DsrCmdDeviceEnroller *)v365);
  operator delete(Block[0]);
  Block[0] = 0;
  operator delete(Block[1]);
  Block[1] = 0;
  LODWORD(v326[0]) = 0;
  operator delete(v326[1]);
  v326[1] = 0;
  operator delete(v327[0]);
  v327[0] = 0;
  operator delete(v327[1]);
  v327[1] = 0;
  operator delete(v328);
  v328 = 0;
  if ( v341[1] )
    std::_Ref_count_base::_Decref(v341[1]);
  v30 = 1;
LABEL_277:
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hautojoinTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hautojoinTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v361);
  return v30;
}

```

## disassembly

```asm
0x1800aee10  mov     [rsp-8+arg_18], rbx
0x1800aee15  push    rbp
0x1800aee16  push    rsi
0x1800aee17  push    rdi
0x1800aee18  push    r12
0x1800aee1a  push    r13
0x1800aee1c  push    r14
0x1800aee1e  push    r15
0x1800aee20  lea     rbp, [rsp-470h]
0x1800aee28  sub     rsp, 570h
0x1800aee2f  mov     rax, cs:__security_cookie
0x1800aee36  xor     rax, rsp
0x1800aee39  mov     [rbp+4A0h+var_40], rax
0x1800aee40  mov     [rbp+4A0h+var_458], r8
0x1800aee44  mov     [rbp+4A0h+var_448], rdx
0x1800aee48  mov     [rbp+4A0h+var_4C8], rcx
0x1800aee4c  xor     r13d, r13d
0x1800aee4f  mov     [rbp+4A0h+var_2E8], r13d
0x1800aee56  mov     [rbp+4A0h+var_2E4], r13b
0x1800aee5d  mov     [rbp+4A0h+var_520], r13b
0x1800aee61  xorps   xmm0, xmm0
0x1800aee64  movdqu  xmmword ptr [rbp+4A0h+var_470], xmm0
0x1800aee69  xor     eax, eax
0x1800aee6b  movups  xmmword ptr [rbp+4A0h+Block], xmm0
0x1800aee6f  movups  xmmword ptr [rbp+4A0h+var_4F8], xmm0
0x1800aee73  movups  xmmword ptr [rbp+4A0h+var_4E8], xmm0
0x1800aee77  mov     [rbp+4A0h+var_4D8], rax
0x1800aee7b  lea     rcx, [rbp+4A0h+var_2C0]; this
0x1800aee82  call    ??0DsrCmdDeviceEnroller@@QEAA@XZ; DsrCmdDeviceEnroller::DsrCmdDeviceEnroller(void)
0x1800aee87  nop
0x1800aee88  mov     [rbp+4A0h+var_4A8], r13
0x1800aee8c  call    ?GetAutoRegistrationJoinEventData@@YAAEAUAutoJoinTelemetryInfo@@XZ; GetAutoRegistrationJoinEventData(void)
0x1800aee91  mov     rcx, rax; this
0x1800aee94  call    ?Reset@AutoJoinTelemetryInfo@@QEAAXXZ; AutoJoinTelemetryInfo::Reset(void)
0x1800aee99  lea     r14, cchOriginalDestLength
0x1800aeea0  mov     rbx, r14
0x1800aeea3  mov     rax, [rbp+4A0h+var_2A8]
0x1800aeeaa  test    rax, rax
0x1800aeead  cmovnz  rbx, rax
0x1800aeeb1  call    ?GetAutoRegistrationJoinEventData@@YAAEAUAutoJoinTelemetryInfo@@XZ; GetAutoRegistrationJoinEventData(void)
0x1800aeeb6  lea     rcx, [rax+0C0h]
0x1800aeebd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800aeec1  mov     r8, rsi
0x1800aeec4  inc     r8
0x1800aeec7  cmp     [rbx+r8*2], r13w
0x1800aeecc  jnz     short loc_1800AEEC4
0x1800aeece  mov     rdx, rbx
0x1800aeed1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800aeed6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeedb  mov     rcx, [rax]
0x1800aeede  lea     r12, aDsrcmdjoinhelp_4; "DsrCmdJoinHelper::Join"
0x1800aeee5  lea     rdi, aSClientrequest_0; "%s: ClientRequestId: %s\n"
0x1800aeeec  cmp     [rcx], r13b
0x1800aeeef  jz      short loc_1800AEF5A
0x1800aeef1  mov     r8, r14
0x1800aeef4  mov     rax, [rbp+4A0h+var_2A8]
0x1800aeefb  test    rax, rax
0x1800aeefe  cmovnz  r8, rax
0x1800aef02  mov     rdx, r12
0x1800aef05  mov     rcx, rdi; Format
0x1800aef08  call    wprintf
0x1800aef0d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aef12  mov     rcx, [rax]
0x1800aef15  cmp     [rcx+0Ch], r13b
0x1800aef19  jz      short loc_1800AEF5A
0x1800aef1b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aef20  mov     rcx, [rax]
0x1800aef23  cmp     [rcx+0B8h], r13
0x1800aef2a  jz      short loc_1800AEF5A
0x1800aef2c  mov     rbx, r14
0x1800aef2f  mov     rax, [rbp+4A0h+var_2A8]
0x1800aef36  test    rax, rax
0x1800aef39  cmovnz  rbx, rax
0x1800aef3d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aef42  mov     rcx, [rax]
0x1800aef45  mov     r9, rbx
0x1800aef48  mov     r8, r12
0x1800aef4b  mov     rdx, rdi; Format
0x1800aef4e  mov     rcx, [rcx+0B8h]; Stream
0x1800aef55  call    fwprintf_s
0x1800aef5a  mov     r8, r14
0x1800aef5d  mov     rax, [rbp+4A0h+var_2A8]
0x1800aef64  test    rax, rax
0x1800aef67  cmovnz  r8, rax
0x1800aef6b  mov     rdx, r12
0x1800aef6e  mov     rcx, rdi; unsigned __int16 *
0x1800aef71  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800aef76  lea     rcx, [rbp+4A0h+var_520]; bool *
0x1800aef7a  call    ?PreJoinChecks@@YAJAEA_N@Z; PreJoinChecks(bool &)
0x1800aef7f  mov     dword ptr [rbp+4A0h+var_498], eax
0x1800aef82  test    eax, eax
0x1800aef84  jns     loc_1800AF0F6
0x1800aef8a  lea     rax, [rbp+4A0h+var_420]
0x1800aef91  mov     [rbp+4A0h+var_458], rax
0x1800aef95  mov     rdx, r14
0x1800aef98  lea     rcx, [rbp+4A0h+var_420]
0x1800aef9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aefa4  mov     r13, rax
0x1800aefa7  lea     rax, [rbp+4A0h+var_440]
0x1800aefab  mov     [rbp+4A0h+var_4C8], rax
0x1800aefaf  mov     rdx, r14
0x1800aefb2  lea     rcx, [rbp+4A0h+var_440]
0x1800aefb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aefbb  mov     r12, rax
0x1800aefbe  lea     rax, [rbp+4A0h+var_3D0]
0x1800aefc5  mov     [rbp+4A0h+var_4C0], rax
0x1800aefc9  mov     rdx, r14
0x1800aefcc  lea     rcx, [rbp+4A0h+var_3D0]
0x1800aefd3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aefd8  mov     r15, rax
0x1800aefdb  lea     rax, [rbp+4A0h+var_3B0]
0x1800aefe2  mov     [rbp+4A0h+var_4B0], rax
0x1800aefe6  mov     rdx, r14
0x1800aefe9  lea     rcx, [rbp+4A0h+var_3B0]
0x1800aeff0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aeff5  mov     r14, rax
0x1800aeff8  lea     rax, [rbp+4A0h+var_390]
0x1800aefff  mov     [rbp+4A0h+var_510], rax
0x1800af003  lea     rdx, cchOriginalDestLength
0x1800af00a  lea     rcx, [rbp+4A0h+var_390]
0x1800af011  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af016  mov     rsi, rax
0x1800af019  lea     rax, [rbp+4A0h+var_3F0]
0x1800af020  mov     [rbp+4A0h+var_4D0], rax
0x1800af024  lea     rdx, aPreCheck; "pre-check"
0x1800af02b  lea     rcx, [rbp+4A0h+var_3F0]
0x1800af032  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af037  mov     rdi, rax
0x1800af03a  call    ?GetAutoRegistrationJoinEventData@@YAAEAUAutoJoinTelemetryInfo@@XZ; GetAutoRegistrationJoinEventData(void)
0x1800af03f  lea     rdx, [rax+60h]
0x1800af043  lea     rcx, [rbp+4A0h+var_368]
0x1800af04a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800af04f  mov     rbx, rax
0x1800af052  xor     ecx, ecx; Time
0x1800af054  call    cs:__imp__time64
0x1800af05a  nop
0x1800af05b  mov     [rsp+5A0h+var_558], r13
0x1800af060  mov     [rsp+5A0h+var_560], r12
0x1800af065  mov     [rsp+5A0h+var_568], r15
0x1800af06a  mov     [rsp+5A0h+var_570], r14
0x1800af06f  xor     r15d, r15d
0x1800af072  mov     dword ptr [rsp+5A0h+var_578], r15d
0x1800af077  mov     [rsp+5A0h+var_580], rsi
0x1800af07c  mov     r14d, dword ptr [rbp+4A0h+var_498]
0x1800af080  mov     r9d, r14d
0x1800af083  mov     r8, rdi
0x1800af086  mov     rdx, rbx
0x1800af089  mov     rcx, rax
0x1800af08c  call    ?WriteJoinDiagnosticInfo@RegistryHelper@@SAJ_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1J1K1111@Z; RegistryHelper::WriteJoinDiagnosticInfo(__int64,std::wstring,std::wstring,long,std::wstring,ulong,std::wstring,std::wstring,std::wstring,std::wstring)
0x1800af091  nop
0x1800af092  lea     rcx, [rbp+4A0h+var_2C0]; this
0x1800af099  call    ??1DsrCmdDeviceEnroller@@QEAA@XZ; DsrCmdDeviceEnroller::~DsrCmdDeviceEnroller(void)
0x1800af09e  nop
0x1800af09f  mov     rcx, [rbp+4A0h+Block]; Block
0x1800af0a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af0a8  mov     [rbp+4A0h+Block], r15
0x1800af0ac  mov     rcx, [rbp+4A0h+Block+8]; Block
0x1800af0b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af0b5  mov     [rbp+4A0h+Block+8], r15
0x1800af0b9  mov     dword ptr [rbp+4A0h+var_4F8], r15d
0x1800af0bd  mov     rcx, [rbp+4A0h+var_4F8+8]; Block
0x1800af0c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af0c6  mov     [rbp+4A0h+var_4F8+8], r15
0x1800af0ca  mov     rcx, [rbp+4A0h+var_4E8]; Block
0x1800af0ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af0d3  mov     [rbp+4A0h+var_4E8], r15
0x1800af0d7  mov     rcx, [rbp+4A0h+var_4E8+8]; Block
0x1800af0db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af0e0  mov     [rbp+4A0h+var_4E8+8], r15
0x1800af0e4  mov     rcx, [rbp+4A0h+var_4D8]; Block
0x1800af0e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af0ed  mov     [rbp+4A0h+var_4D8], r15
0x1800af0f1  jmp     loc_1800B0BA8
0x1800af0f6  lea     rcx, [rbp+4A0h+var_368]
0x1800af0fd  cmp     eax, 1
0x1800af100  jnz     loc_1800AF27F
0x1800af106  lea     rax, [rbp+4A0h+var_368]
0x1800af10d  mov     [rbp+4A0h+var_458], rax
0x1800af111  mov     rdx, r14
0x1800af114  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af119  mov     r13, rax
0x1800af11c  lea     rax, [rbp+4A0h+var_3F0]
0x1800af123  mov     [rbp+4A0h+var_4C8], rax
0x1800af127  mov     rdx, r14
0x1800af12a  lea     rcx, [rbp+4A0h+var_3F0]
0x1800af131  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af136  mov     r12, rax
0x1800af139  lea     rax, [rbp+4A0h+var_390]
0x1800af140  mov     [rbp+4A0h+var_4C0], rax
0x1800af144  mov     rdx, r14
0x1800af147  lea     rcx, [rbp+4A0h+var_390]
0x1800af14e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af153  mov     r15, rax
0x1800af156  lea     rax, [rbp+4A0h+var_3B0]
0x1800af15d  mov     [rbp+4A0h+var_4B0], rax
0x1800af161  mov     rdx, r14
0x1800af164  lea     rcx, [rbp+4A0h+var_3B0]
0x1800af16b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af170  mov     r14, rax
0x1800af173  lea     rax, [rbp+4A0h+var_3D0]
0x1800af17a  mov     [rbp+4A0h+var_510], rax
0x1800af17e  lea     rdx, cchOriginalDestLength
0x1800af185  lea     rcx, [rbp+4A0h+var_3D0]
0x1800af18c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af191  mov     rsi, rax
0x1800af194  lea     rax, [rbp+4A0h+var_420]
0x1800af19b  mov     [rbp+4A0h+var_4D0], rax
0x1800af19f  lea     rdx, aPreCheck; "pre-check"
0x1800af1a6  lea     rcx, [rbp+4A0h+var_420]
0x1800af1ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af1b2  mov     rdi, rax
0x1800af1b5  call    ?GetAutoRegistrationJoinEventData@@YAAEAUAutoJoinTelemetryInfo@@XZ; GetAutoRegistrationJoinEventData(void)
0x1800af1ba  lea     rdx, [rax+60h]
0x1800af1be  lea     rcx, [rbp+4A0h+var_440]
0x1800af1c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800af1c7  mov     rbx, rax
0x1800af1ca  xor     ecx, ecx; Time
0x1800af1cc  call    cs:__imp__time64
0x1800af1d2  nop
0x1800af1d3  mov     [rsp+5A0h+var_558], r13
0x1800af1d8  mov     [rsp+5A0h+var_560], r12
0x1800af1dd  mov     [rsp+5A0h+var_568], r15
0x1800af1e2  mov     [rsp+5A0h+var_570], r14
0x1800af1e7  xor     r14d, r14d
0x1800af1ea  mov     dword ptr [rsp+5A0h+var_578], r14d
0x1800af1ef  mov     [rsp+5A0h+var_580], rsi
0x1800af1f4  lea     esi, [r14+1]
0x1800af1f8  mov     r9d, esi
0x1800af1fb  mov     r8, rdi
0x1800af1fe  mov     rdx, rbx
0x1800af201  mov     rcx, rax
0x1800af204  call    ?WriteJoinDiagnosticInfo@RegistryHelper@@SAJ_JV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1J1K1111@Z; RegistryHelper::WriteJoinDiagnosticInfo(__int64,std::wstring,std::wstring,long,std::wstring,ulong,std::wstring,std::wstring,std::wstring,std::wstring)
0x1800af209  nop
0x1800af20a  lea     rcx, [rbp+4A0h+var_2C0]; this
0x1800af211  call    ??1DsrCmdDeviceEnroller@@QEAA@XZ; DsrCmdDeviceEnroller::~DsrCmdDeviceEnroller(void)
0x1800af216  nop
0x1800af217  mov     rcx, [rbp+4A0h+Block]; Block
0x1800af21b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af220  mov     [rbp+4A0h+Block], r14
0x1800af224  mov     rcx, [rbp+4A0h+Block+8]; Block
0x1800af228  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af22d  mov     [rbp+4A0h+Block+8], r14
0x1800af231  mov     dword ptr [rbp+4A0h+var_4F8], r14d
0x1800af235  mov     rcx, [rbp+4A0h+var_4F8+8]; Block
0x1800af239  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af23e  mov     [rbp+4A0h+var_4F8+8], r14
0x1800af242  mov     rcx, [rbp+4A0h+var_4E8]; Block
0x1800af246  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af24b  mov     [rbp+4A0h+var_4E8], r14
0x1800af24f  mov     rcx, [rbp+4A0h+var_4E8+8]; Block
0x1800af253  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af258  mov     [rbp+4A0h+var_4E8+8], r14
0x1800af25c  mov     rcx, [rbp+4A0h+var_4D8]; Block
0x1800af260  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800af265  mov     [rbp+4A0h+var_4D8], r14
0x1800af269  mov     rcx, [rbp+4A0h+var_470+8]; this
0x1800af26d  test    rcx, rcx
0x1800af270  jz      short loc_1800AF277
0x1800af272  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800af277  mov     r14d, esi
0x1800af27a  jmp     loc_1800B0BB7
0x1800af27f  mov     dil, [rbp+4A0h+var_520]
0x1800af283  test    dil, dil
0x1800af286  jz      short loc_1800AF2AA
0x1800af288  lea     rdx, aLeavethenjoin; "LeaveThenJoin"
0x1800af28f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af294  mov     rbx, rax
0x1800af297  call    ?GetAutoRegistrationJoinEventData@@YAAEAUAutoJoinTelemetryInfo@@XZ; GetAutoRegistrationJoinEventData(void)
0x1800af29c  mov     rcx, rax
0x1800af29f  mov     rdx, rbx
0x1800af2a2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800af2a7  nop
0x1800af2a8  jmp     short loc_1800AF2CA
0x1800af2aa  lea     rdx, aJoin; "Join"
0x1800af2b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800af2b6  mov     rbx, rax
0x1800af2b9  call    ?GetAutoRegistrationJoinEventData@@YAAEAUAutoJoinTelemetryInfo@@XZ; GetAutoRegistrationJoinEventData(void)
0x1800af2be  mov     rcx, rax
0x1800af2c1  mov     rdx, rbx
0x1800af2c4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800af2c9  nop
0x1800af2ca  lea     rcx, [rbp+4A0h+var_368]
0x1800af2d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800af2d6  lea     rcx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x1800af2dd  call    ?GetAutoJoinPolicy@@YAPEBGPEBG0@Z; GetAutoJoinPolicy(ushort const *,ushort const *)
0x1800af2e2  mov     rbx, rax
0x1800af2e5  mov     [rbp+4A0h+var_4C0], rax
0x1800af2e9  lea     rcx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x1800af2f0  call    ?GetAutoJoinPolicy@@YAPEBGPEBG0@Z; GetAutoJoinPolicy(ushort const *,ushort const *)
0x1800af2f5  mov     r15, rax
0x1800af2f8  mov     [rbp+4A0h+var_4B0], rax
0x1800af2fc  lea     rcx, [rbp+4A0h+var_2E8]
0x1800af303  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hautojoinTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hautojoinTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800af308  mov     ecx, cs:dword_18013D928
0x1800af30e  cmp     ecx, 5
0x1800af311  jbe     loc_1800AF399
0x1800af317  mov     rdx, 400000000000h
0x1800af321  lea     rcx, dword_18013D928
0x1800af328  call    _tlgKeywordOn
0x1800af32d  test    al, al
  ... truncated ...
```
