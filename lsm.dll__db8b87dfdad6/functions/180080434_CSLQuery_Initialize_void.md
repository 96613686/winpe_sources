# CSLQuery::Initialize(void)

- ea: `0x180080434`
- end: `0x18008247f`
- name: `?Initialize@CSLQuery@@SAJXZ`
- size: `8267`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003d87c`
- `0x180080374`
- `0x180082488`
- `0x180082544`
- `0x180082608`

## callees

- `0x180001874`
- `0x18000345c`
- `0x18001deb8`
- `0x18001fc20`
- `0x180022b28`
- `0x180025af8`
- `0x18002f624`
- `0x18003e6a4`
- `0x18004b460`
- `0x180080434`
- `0x180082970`
- `0x180082a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080536`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180080486`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180080486`

## string_xrefs

- `0x18008084c`: `TerminalServices-RemoteConnectionManager-AllowMultipleSessions`
- `0x1800805d1`: `TerminalServices-RemoteConnectionManager-AllowRemoteConnections`
- `0x180080ae2`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`
- `0x180080e0f`: `The SL policy for 'Automated App Server Installation' is not defined - assuming FALSE`
- `0x180080d81`: `TerminalServices-RemoteConnectionManager-AutomatedAppServerInstallation`
- `0x180080ffc`: `TerminalServices-RemoteConnectionManager-AllowMultimon`
- `0x180080f2d`: `CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAutomatedAppServerInstallation`
- `0x180081277`: `TerminalServices-ADD-Licensing`
- `0x1800814f2`: `TerminalServices-RemoteConnectionManager-MaxUserSessions`
- `0x18008174b`: `TerminalServices-RemoteConnectionManager-ce0ad219-4670-4988-98fb-89b14c2f072b-MaxSessions`
- `0x180081bfd`: `TerminalServices-RemoteConnectionManager-WVD-Enabled`
- `0x18008220f`: `TerminalServices-RemoteConnectionManager-cd051c59-3fe7-499c-9b66-02d99dbd8d3b-MaxSessions`
- `0x1800823bb`: `CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxAgentSessions`
- `0x18008229d`: `The SL policy for 'Max Agent Sessions' is not defined - assuming no limit to user sessions`

## pseudocode

```c
__int64 CSLQuery::Initialize(void)
{
  const unsigned __int16 **v0; // rax
  const unsigned __int16 **v1; // rax
  const unsigned __int16 **v2; // rax
  const unsigned __int16 **v3; // rax
  const unsigned __int16 **v4; // rax
  const unsigned __int16 **v5; // rax
  const unsigned __int16 **v6; // rax
  const unsigned __int16 **v7; // rax
  const unsigned __int16 **v8; // rax
  const unsigned __int16 **v9; // rax
  const unsigned __int16 **v10; // rax
  int v12; // [rsp+40h] [rbp-758h]
  unsigned int v13; // [rsp+44h] [rbp-754h] BYREF
  char v14; // [rsp+48h] [rbp-750h]
  char v15; // [rsp+49h] [rbp-74Fh]
  char v16; // [rsp+4Ah] [rbp-74Eh]
  char v17; // [rsp+4Bh] [rbp-74Dh]
  char v18; // [rsp+4Ch] [rbp-74Ch]
  char v19; // [rsp+4Dh] [rbp-74Bh]
  char v20; // [rsp+4Eh] [rbp-74Ah]
  char v21; // [rsp+4Fh] [rbp-749h]
  char v22; // [rsp+50h] [rbp-748h]
  char v23; // [rsp+51h] [rbp-747h]
  char v24; // [rsp+52h] [rbp-746h]
  char v25; // [rsp+53h] [rbp-745h]
  char v26; // [rsp+54h] [rbp-744h]
  char v27; // [rsp+55h] [rbp-743h]
  char v28; // [rsp+56h] [rbp-742h]
  char v29; // [rsp+57h] [rbp-741h]
  char v30; // [rsp+58h] [rbp-740h]
  char v31; // [rsp+59h] [rbp-73Fh]
  char v32; // [rsp+5Ah] [rbp-73Eh]
  char v33; // [rsp+5Bh] [rbp-73Dh]
  bool v34; // [rsp+5Ch] [rbp-73Ch]
  bool v35; // [rsp+5Dh] [rbp-73Bh]
  __int64 *v36; // [rsp+60h] [rbp-738h]
  unsigned int v37; // [rsp+68h] [rbp-730h]
  unsigned int v38; // [rsp+6Ch] [rbp-72Ch]
  unsigned int v39; // [rsp+70h] [rbp-728h]
  unsigned int v40; // [rsp+74h] [rbp-724h]
  BOOL v41; // [rsp+78h] [rbp-720h]
  unsigned int v42; // [rsp+7Ch] [rbp-71Ch]
  unsigned int v43; // [rsp+80h] [rbp-718h]
  unsigned int v44; // [rsp+84h] [rbp-714h]
  BOOL v45; // [rsp+88h] [rbp-710h]
  unsigned int v46; // [rsp+8Ch] [rbp-70Ch]
  unsigned int v47; // [rsp+90h] [rbp-708h]
  BOOL v48; // [rsp+94h] [rbp-704h]
  unsigned int v49; // [rsp+98h] [rbp-700h]
  unsigned int v50; // [rsp+9Ch] [rbp-6FCh]
  BOOL v51; // [rsp+A0h] [rbp-6F8h]
  unsigned int v52; // [rsp+A4h] [rbp-6F4h]
  unsigned int v53; // [rsp+A8h] [rbp-6F0h]
  BOOL v54; // [rsp+ACh] [rbp-6ECh]
  unsigned int v55; // [rsp+B0h] [rbp-6E8h]
  unsigned int v56; // [rsp+B4h] [rbp-6E4h]
  BOOL v57; // [rsp+B8h] [rbp-6E0h]
  unsigned int v58; // [rsp+BCh] [rbp-6DCh]
  unsigned int v59; // [rsp+C0h] [rbp-6D8h]
  unsigned int v60; // [rsp+C4h] [rbp-6D4h]
  unsigned int v61; // [rsp+C8h] [rbp-6D0h]
  unsigned int v62; // [rsp+CCh] [rbp-6CCh]
  BOOL v63; // [rsp+D0h] [rbp-6C8h]
  unsigned int v64; // [rsp+D4h] [rbp-6C4h]
  unsigned int v65; // [rsp+D8h] [rbp-6C0h]
  BOOL v66; // [rsp+DCh] [rbp-6BCh]
  int v67; // [rsp+E0h] [rbp-6B8h]
  int v68; // [rsp+E4h] [rbp-6B4h]
  int v69; // [rsp+E8h] [rbp-6B0h]
  int v70; // [rsp+ECh] [rbp-6ACh]
  unsigned int v71; // [rsp+F0h] [rbp-6A8h]
  int v72; // [rsp+F4h] [rbp-6A4h]
  int v73; // [rsp+F8h] [rbp-6A0h]
  int v74; // [rsp+FCh] [rbp-69Ch]
  int v75; // [rsp+100h] [rbp-698h]
  BOOL v76; // [rsp+104h] [rbp-694h]
  unsigned int v77; // [rsp+108h] [rbp-690h]
  unsigned int v78; // [rsp+10Ch] [rbp-68Ch]
  int v79; // [rsp+110h] [rbp-688h]
  unsigned int v80; // [rsp+114h] [rbp-684h]
  DWORD LastError; // [rsp+118h] [rbp-680h] BYREF
  _BYTE v82[4]; // [rsp+11Ch] [rbp-67Ch] BYREF
  unsigned int v83; // [rsp+120h] [rbp-678h]
  unsigned int v84; // [rsp+124h] [rbp-674h]
  int v85; // [rsp+128h] [rbp-670h] BYREF
  _BYTE v86[4]; // [rsp+12Ch] [rbp-66Ch] BYREF
  unsigned int v87; // [rsp+130h] [rbp-668h]
  unsigned int v88; // [rsp+134h] [rbp-664h]
  int v89; // [rsp+138h] [rbp-660h] BYREF
  _BYTE v90[4]; // [rsp+13Ch] [rbp-65Ch] BYREF
  unsigned int v91; // [rsp+140h] [rbp-658h]
  int v92; // [rsp+144h] [rbp-654h]
  unsigned int v93; // [rsp+148h] [rbp-650h]
  int v94; // [rsp+14Ch] [rbp-64Ch] BYREF
  _BYTE v95[4]; // [rsp+150h] [rbp-648h] BYREF
  unsigned int v96; // [rsp+154h] [rbp-644h]
  unsigned int v97; // [rsp+158h] [rbp-640h]
  int v98; // [rsp+15Ch] [rbp-63Ch] BYREF
  _BYTE v99[4]; // [rsp+160h] [rbp-638h] BYREF
  unsigned int v100; // [rsp+164h] [rbp-634h]
  unsigned int v101; // [rsp+168h] [rbp-630h]
  int v102; // [rsp+16Ch] [rbp-62Ch] BYREF
  _BYTE v103[4]; // [rsp+170h] [rbp-628h] BYREF
  unsigned int v104; // [rsp+174h] [rbp-624h]
  unsigned int v105; // [rsp+178h] [rbp-620h]
  int v106; // [rsp+17Ch] [rbp-61Ch] BYREF
  _BYTE v107[4]; // [rsp+180h] [rbp-618h] BYREF
  unsigned int v108; // [rsp+184h] [rbp-614h]
  unsigned int v109; // [rsp+188h] [rbp-610h]
  int v110; // [rsp+18Ch] [rbp-60Ch] BYREF
  _BYTE v111[4]; // [rsp+190h] [rbp-608h] BYREF
  unsigned int v112; // [rsp+194h] [rbp-604h]
  unsigned int v113; // [rsp+198h] [rbp-600h]
  int v114; // [rsp+19Ch] [rbp-5FCh] BYREF
  _BYTE v115[4]; // [rsp+1A0h] [rbp-5F8h] BYREF
  unsigned int v116; // [rsp+1A4h] [rbp-5F4h]
  unsigned int v117; // [rsp+1A8h] [rbp-5F0h]
  int v118; // [rsp+1ACh] [rbp-5ECh] BYREF
  _BYTE v119[4]; // [rsp+1B0h] [rbp-5E8h] BYREF
  unsigned int v120; // [rsp+1B4h] [rbp-5E4h]
  unsigned int v121; // [rsp+1B8h] [rbp-5E0h]
  int v122; // [rsp+1BCh] [rbp-5DCh] BYREF
  _BYTE v123[4]; // [rsp+1C0h] [rbp-5D8h] BYREF
  unsigned int v124; // [rsp+1C4h] [rbp-5D4h]
  unsigned int v125; // [rsp+1C8h] [rbp-5D0h]
  int v126; // [rsp+1CCh] [rbp-5CCh] BYREF
  _BYTE v127[8]; // [rsp+1D0h] [rbp-5C8h] BYREF
  __int64 v128; // [rsp+1D8h] [rbp-5C0h]
  __int64 v129; // [rsp+1E0h] [rbp-5B8h]
  __int64 v130; // [rsp+1E8h] [rbp-5B0h]
  __int64 v131; // [rsp+1F0h] [rbp-5A8h]
  __int64 v132; // [rsp+1F8h] [rbp-5A0h]
  __int64 v133; // [rsp+200h] [rbp-598h]
  __int64 v134; // [rsp+208h] [rbp-590h]
  __int64 v135; // [rsp+210h] [rbp-588h]
  __int64 v136; // [rsp+218h] [rbp-580h]
  __int64 v137; // [rsp+220h] [rbp-578h]
  __int64 v138; // [rsp+228h] [rbp-570h]
  __int64 v139; // [rsp+230h] [rbp-568h]
  __int64 v140; // [rsp+238h] [rbp-560h]
  __int64 v141; // [rsp+240h] [rbp-558h]
  __int64 v142; // [rsp+248h] [rbp-550h]
  __int64 v143; // [rsp+250h] [rbp-548h]
  __int64 v144; // [rsp+258h] [rbp-540h]
  __int64 v145; // [rsp+260h] [rbp-538h]
  __int64 v146; // [rsp+268h] [rbp-530h]
  __int64 v147; // [rsp+270h] [rbp-528h]
  __int64 v148; // [rsp+278h] [rbp-520h]
  __int64 v149; // [rsp+280h] [rbp-518h]
  __int64 v150; // [rsp+288h] [rbp-510h]
  __int64 v151; // [rsp+290h] [rbp-508h]
  _BYTE *v152; // [rsp+298h] [rbp-500h]
  const unsigned __int16 **v153; // [rsp+2A0h] [rbp-4F8h]
  __int64 v154; // [rsp+2A8h] [rbp-4F0h]
  __int64 v155; // [rsp+2B0h] [rbp-4E8h]
  const unsigned __int16 **v156; // [rsp+2B8h] [rbp-4E0h]
  _BYTE *v157; // [rsp+2C0h] [rbp-4D8h]
  const unsigned __int16 **v158; // [rsp+2C8h] [rbp-4D0h]
  const unsigned __int16 **v159; // [rsp+2D0h] [rbp-4C8h]
  __int64 v160; // [rsp+2D8h] [rbp-4C0h]
  __int64 v161; // [rsp+2E0h] [rbp-4B8h]
  const unsigned __int16 **v162; // [rsp+2E8h] [rbp-4B0h]
  _BYTE *v163; // [rsp+2F0h] [rbp-4A8h]
  const unsigned __int16 **v164; // [rsp+2F8h] [rbp-4A0h]
  const unsigned __int16 **v165; // [rsp+300h] [rbp-498h]
  __int64 v166; // [rsp+308h] [rbp-490h]
  __int64 v167; // [rsp+310h] [rbp-488h]
  const unsigned __int16 **v168; // [rsp+318h] [rbp-480h]
  _BYTE *v169; // [rsp+320h] [rbp-478h]
  const unsigned __int16 **v170; // [rsp+328h] [rbp-470h]
  const unsigned __int16 **v171; // [rsp+330h] [rbp-468h]
  __int64 v172; // [rsp+338h] [rbp-460h]
  __int64 v173; // [rsp+340h] [rbp-458h]
  const unsigned __int16 **v174; // [rsp+348h] [rbp-450h]
  _BYTE *v175; // [rsp+350h] [rbp-448h]
  const unsigned __int16 **v176; // [rsp+358h] [rbp-440h]
  const unsigned __int16 **v177; // [rsp+360h] [rbp-438h]
  __int64 v178; // [rsp+368h] [rbp-430h]
  __int64 v179; // [rsp+370h] [rbp-428h]
  const unsigned __int16 **v180; // [rsp+378h] [rbp-420h]
  _BYTE *v181; // [rsp+380h] [rbp-418h]
  const unsigned __int16 **v182; // [rsp+388h] [rbp-410h]
  const unsigned __int16 **v183; // [rsp+390h] [rbp-408h]
  __int64 v184; // [rsp+398h] [rbp-400h]
  __int64 v185; // [rsp+3A0h] [rbp-3F8h]
  const unsigned __int16 **v186; // [rsp+3A8h] [rbp-3F0h]
  _BYTE *v187; // [rsp+3B0h] [rbp-3E8h]
  const unsigned __int16 **v188; // [rsp+3B8h] [rbp-3E0h]
  const unsigned __int16 **v189; // [rsp+3C0h] [rbp-3D8h]
  __int64 v190; // [rsp+3C8h] [rbp-3D0h]
  __int64 v191; // [rsp+3D0h] [rbp-3C8h]
  const unsigned __int16 **v192; // [rsp+3D8h] [rbp-3C0h]
  _BYTE *v193; // [rsp+3E0h] [rbp-3B8h]
  const unsigned __int16 **v194; // [rsp+3E8h] [rbp-3B0h]
  const unsigned __int16 **v195; // [rsp+3F0h] [rbp-3A8h]
  __int64 v196; // [rsp+3F8h] [rbp-3A0h]
  __int64 v197; // [rsp+400h] [rbp-398h]
  const unsigned __int16 **v198; // [rsp+408h] [rbp-390h]
  _BYTE *v199; // [rsp+410h] [rbp-388h]
  const unsigned __int16 **v200; // [rsp+418h] [rbp-380h]
  const unsigned __int16 **v201; // [rsp+420h] [rbp-378h]
  __int64 v202; // [rsp+428h] [rbp-370h]
  __int64 v203; // [rsp+430h] [rbp-368h]
  const unsigned __int16 **v204; // [rsp+438h] [rbp-360h]
  _BYTE *v205; // [rsp+440h] [rbp-358h]
  const unsigned __int16 **v206; // [rsp+448h] [rbp-350h]
  const unsigned __int16 **v207; // [rsp+450h] [rbp-348h]
  __int64 v208; // [rsp+458h] [rbp-340h]
  __int64 v209; // [rsp+460h] [rbp-338h]
  const unsigned __int16 **v210; // [rsp+468h] [rbp-330h]
  _BYTE *v211; // [rsp+470h] [rbp-328h]
  const unsigned __int16 **v212; // [rsp+478h] [rbp-320h]
  const unsigned __int16 **v213; // [rsp+480h] [rbp-318h]
  __int64 *v214; // [rsp+488h] [rbp-310h]
  __int64 v215; // [rsp+490h] [rbp-308h]
  __int64 v216; // [rsp+498h] [rbp-300h]
  const unsigned __int16 **v217; // [rsp+4A0h] [rbp-2F8h]
  _BYTE *v218; // [rsp+4A8h] [rbp-2F0h]
  const unsigned __int16 **v219; // [rsp+4B0h] [rbp-2E8h]
  const unsigned __int16 **v220; // [rsp+4B8h] [rbp-2E0h]
  _BYTE v221[8]; // [rsp+4C0h] [rbp-2D8h] BYREF
  _BYTE v222[8]; // [rsp+4C8h] [rbp-2D0h] BYREF
  _BYTE v223[8]; // [rsp+4D0h] [rbp-2C8h] BYREF
  _BYTE v224[8]; // [rsp+4D8h] [rbp-2C0h] BYREF
  _BYTE v225[8]; // [rsp+4E0h] [rbp-2B8h] BYREF
  _BYTE v226[8]; // [rsp+4E8h] [rbp-2B0h] BYREF
  _BYTE v227[8]; // [rsp+4F0h] [rbp-2A8h] BYREF
  _BYTE v228[8]; // [rsp+4F8h] [rbp-2A0h] BYREF
  _BYTE v229[8]; // [rsp+500h] [rbp-298h] BYREF
  _BYTE v230[8]; // [rsp+508h] [rbp-290h] BYREF
  _BYTE v231[8]; // [rsp+510h] [rbp-288h] BYREF
  _BYTE v232[8]; // [rsp+518h] [rbp-280h] BYREF
  _BYTE v233[8]; // [rsp+520h] [rbp-278h] BYREF
  _BYTE v234[8]; // [rsp+528h] [rbp-270h] BYREF
  _BYTE v235[8]; // [rsp+530h] [rbp-268h] BYREF
  _BYTE v236[8]; // [rsp+538h] [rbp-260h] BYREF
  _BYTE v237[8]; // [rsp+540h] [rbp-258h] BYREF
  _BYTE v238[8]; // [rsp+548h] [rbp-250h] BYREF
  _BYTE v239[8]; // [rsp+550h] [rbp-248h] BYREF
  _BYTE v240[8]; // [rsp+558h] [rbp-240h] BYREF
  _BYTE v241[8]; // [rsp+560h] [rbp-238h] BYREF
  _BYTE v242[8]; // [rsp+568h] [rbp-230h] BYREF
  _BYTE v243[8]; // [rsp+570h] [rbp-228h] BYREF
  _BYTE v244[8]; // [rsp+578h] [rbp-220h] BYREF
  _BYTE v245[8]; // [rsp+580h] [rbp-218h] BYREF
  _BYTE v246[8]; // [rsp+588h] [rbp-210h] BYREF
  _BYTE v247[8]; // [rsp+590h] [rbp-208h] BYREF
  _BYTE v248[8]; // [rsp+598h] [rbp-200h] BYREF
  _BYTE v249[8]; // [rsp+5A0h] [rbp-1F8h] BYREF
  _BYTE v250[8]; // [rsp+5A8h] [rbp-1F0h] BYREF
  _BYTE v251[8]; // [rsp+5B0h] [rbp-1E8h] BYREF
  _BYTE v252[8]; // [rsp+5B8h] [rbp-1E0h] BYREF
  _BYTE v253[8]; // [rsp+5C0h] [rbp-1D8h] BYREF
  _BYTE v254[8]; // [rsp+5C8h] [rbp-1D0h] BYREF
  _BYTE v255[8]; // [rsp+5D0h] [rbp-1C8h] BYREF
  _BYTE v256[8]; // [rsp+5D8h] [rbp-1C0h] BYREF
  _BYTE v257[8]; // [rsp+5E0h] [rbp-1B8h] BYREF
  _BYTE v258[8]; // [rsp+5E8h] [rbp-1B0h] BYREF
  _BYTE v259[8]; // [rsp+5F0h] [rbp-1A8h] BYREF
  _BYTE v260[8]; // [rsp+5F8h] [rbp-1A0h] BYREF
  _BYTE v261[8]; // [rsp+600h] [rbp-198h] BYREF
  __int64 *v262; // [rsp+608h] [rbp-190h]
  __int64 *v263; // [rsp+610h] [rbp-188h]
  __int64 *v264; // [rsp+628h] [rbp-170h]
  __int64 *v265; // [rsp+630h] [rbp-168h]
  __int64 *v266; // [rsp+638h] [rbp-160h]
  _BYTE v267[8]; // [rsp+640h] [rbp-158h] BYREF
  _BYTE v268[8]; // [rsp+648h] [rbp-150h] BYREF
  _BYTE v269[8]; // [rsp+650h] [rbp-148h] BYREF
  _BYTE v270[8]; // [rsp+658h] [rbp-140h] BYREF
  _BYTE VersionInformation[284]; // [rsp+660h] [rbp-138h] BYREF

  v13 = 0;
  memset(VersionInformation, 0, sizeof(VersionInformation));
  *(_DWORD *)VersionInformation = 284;
  if ( GetVersionExW((LPOSVERSIONINFOW)VersionInformation) )
  {
    v63 = VersionInformation[282] != 1;
    CSLQuery::bServerSku = v63;
  }
  else
  {
    v128 = g_ProviderToUse;
    v151 = g_ProviderToUse;
    v37 = 0;
    v37 = *g_ProviderToUse;
    v80 = v37;
    if ( v37 > 3 && (unsigned __int8)tlgKeywordOn(v128, 0) )
    {
      LastError = GetLastError();
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v82, &LastError);
      v152 = v82;
      v153 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v221, "GetVersionEx FAILED");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v128,
        (__int64)&word_1800C889E,
        0,
        0,
        v153,
        (__int64)v152);
    }
  }
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowRemoteConnections", &v13);
  if ( v12 == -1073418222 )
  {
    v129 = g_ProviderToUse;
    v154 = g_ProviderToUse;
    v38 = 0;
    v38 = *g_ProviderToUse;
    v83 = v38;
    if ( v38 > 3 && (unsigned __int8)tlgKeywordOn(v129, 0) )
    {
      v0 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v222,
                                        "The SL policy for 'Allow Remote Connections' is not defined - assuming Reduced F"
                                        "unctionality Mode");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v129,
        (unsigned __int8 *)&byte_1800C8B1F,
        0,
        0,
        v0);
    }
    v39 = CSLQuery::bServerSku != 0;
    v13 = v39;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v130 = g_ProviderToUse;
    v155 = g_ProviderToUse;
    v40 = 0;
    v40 = *g_ProviderToUse;
    v84 = v40;
    if ( v40 > 3 && (unsigned __int8)tlgKeywordOn(v130, 0) )
    {
      v156 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v223, "Initialize");
      v85 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v86, &v85);
      v157 = v86;
      v158 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v224,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bRemoteConnAllowed");
      v159 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v225, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v130,
        (__int64)&word_1800C8756,
        0,
        0,
        v159,
        v158,
        (__int64)v157,
        v156);
    }
    return (unsigned int)v12;
  }
  v41 = v13 != 0;
  CSLQuery::bRemoteConnAllowed = v41;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowMultipleSessions", &v13);
  if ( v12 == -1073418222 )
  {
    v131 = g_ProviderToUse;
    v160 = g_ProviderToUse;
    v42 = 0;
    v42 = *g_ProviderToUse;
    v87 = v42;
    if ( v42 > 3 && (unsigned __int8)tlgKeywordOn(v131, 0) )
    {
      v1 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v226,
                                        "The SL policy for 'Allow Multiple Sessions' is not defined - assuming Reduced Fu"
                                        "nctionality Mode");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v131,
        (unsigned __int8 *)&word_1800C8AFE,
        0,
        0,
        v1);
    }
    v43 = CSLQuery::bServerSku != 0;
    v13 = v43;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v132 = g_ProviderToUse;
    v161 = g_ProviderToUse;
    v44 = 0;
    v44 = *g_ProviderToUse;
    v88 = v44;
    if ( v44 > 3 && (unsigned __int8)tlgKeywordOn(v132, 0) )
    {
      v162 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v227, "Initialize");
      v89 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v90, &v89);
      v163 = v90;
      v164 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v228,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bFUSEnabled");
      v165 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v229, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v132,
        (__int64)&byte_1800C8A67,
        0,
        0,
        v165,
        v164,
        (__int64)v163,
        v162);
    }
    return (unsigned int)v12;
  }
  v45 = v13 != 0;
  CSLQuery::bFUSEnabled = v45;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowAppServerMode", &v13);
  if ( v12 == -1073418222 )
  {
    v133 = g_ProviderToUse;
    v166 = g_ProviderToUse;
    v46 = 0;
    v46 = *g_ProviderToUse;
    v91 = v46;
    if ( v46 > 3 && (unsigned __int8)tlgKeywordOn(v133, 0) )
    {
      v2 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v230,
                                        "The SL policy for 'Allow Multiple Sessions' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v133,
        (unsigned __int8 *)&word_1800C88FE,
        0,
        0,
        v2);
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v92 = 0;
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v134 = g_ProviderToUse;
    v167 = g_ProviderToUse;
    v47 = 0;
    v47 = *g_ProviderToUse;
    v93 = v47;
    if ( v47 > 3 && (unsigned __int8)tlgKeywordOn(v134, 0) )
    {
      v168 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v231, "Initialize");
      v94 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v95, &v94);
      v169 = v95;
      v170 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v232,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAppServerAllowed");
      v171 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v233, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v134,
        (__int64)byte_1800C88C3,
        0,
        0,
        v171,
        v170,
        (__int64)v169,
        v168);
    }
    return (unsigned int)v12;
  }
  v48 = v13 != 0;
  CSLQuery::bAppServerAllowed = v48;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-AutomatedAppServerInstallation",
          &v13);
  if ( v12 == -1073418222 )
  {
    v135 = g_ProviderToUse;
    v172 = g_ProviderToUse;
    v49 = 0;
    v49 = *g_ProviderToUse;
    v96 = v49;
    if ( v49 > 3 && (unsigned __int8)tlgKeywordOn(v135, 0) )
    {
      v3 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v234,
                                        "The SL policy for 'Automated App Server Installation' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v135,
        (unsigned __int8 *)&word_1800C869E,
        0,
        0,
        v3);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v136 = g_ProviderToUse;
    v173 = g_ProviderToUse;
    v50 = 0;
    v50 = *g_ProviderToUse;
    v97 = v50;
    if ( v50 > 3 && (unsigned __int8)tlgKeywordOn(v136, 0) )
    {
      v174 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v235, "Initialize");
      v98 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v99, &v98);
      v175 = v99;
      v176 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v236,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAutomatedAppServerInstallation");
      v177 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v237, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v136,
        (__int64)byte_1800C8B40,
        0,
        0,
        v177,
        v176,
        (__int64)v175,
        v174);
    }
    return (unsigned int)v12;
  }
  v51 = v13 != 0;
  CSLQuery::bAutomatedAppServerInstallation = v51;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-AllowMultimon", &v13);
  if ( v12 == -1073418222 )
  {
    v137 = g_ProviderToUse;
    v178 = g_ProviderToUse;
    v52 = 0;
    v52 = *g_ProviderToUse;
    v100 = v52;
    if ( v52 > 3 && (unsigned __int8)tlgKeywordOn(v137, 0) )
    {
      v4 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v238,
                                        "The SL policy for 'Allow Multiple Monitors' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v137,
        (unsigned __int8 *)byte_1800C8995,
        0,
        0,
        v4);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v138 = g_ProviderToUse;
    v179 = g_ProviderToUse;
    v53 = 0;
    v53 = *g_ProviderToUse;
    v101 = v53;
    if ( v53 > 3 && (unsigned __int8)tlgKeywordOn(v138, 0) )
    {
      v180 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v239, "Initialize");
      v102 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v103, &v102);
      v181 = v103;
      v182 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v240,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bMultimonAllowed");
      v183 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v241, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v138,
        (__int64)&word_1800C89B6,
        0,
        0,
        v183,
        v182,
        (__int64)v181,
        v180);
    }
    return (unsigned int)v12;
  }
  v54 = v13 != 0;
  CSLQuery::bMultimonAllowed = v54;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-ADD-Licensing", &v13);
  if ( v12 == -1073418222 )
  {
    v139 = g_ProviderToUse;
    v184 = g_ProviderToUse;
    v55 = 0;
    v55 = *g_ProviderToUse;
    v104 = v55;
    if ( v55 > 3 && (unsigned __int8)tlgKeywordOn(v139, 0) )
    {
      v5 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v242,
                                        "The SL policy for 'Allow AAD Licensing' is not defined - assuming FALSE");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v139,
        (unsigned __int8 *)byte_1800C863B,
        0,
        0,
        v5);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v140 = g_ProviderToUse;
    v185 = g_ProviderToUse;
    v56 = 0;
    v56 = *g_ProviderToUse;
    v105 = v56;
    if ( v56 > 3 && (unsigned __int8)tlgKeywordOn(v140, 0) )
    {
      v186 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v243, "Initialize");
      v106 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v107, &v106);
      v187 = v107;
      v188 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v244,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bAllowAADLicensing");
      v189 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v245, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v140,
        (__int64)&word_1800C895A,
        0,
        0,
        v189,
        v188,
        (__int64)v187,
        v186);
    }
    return (unsigned int)v12;
  }
  v57 = v13 != 0;
  CSLQuery::bAllowAADLicensing = v57;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-MaxUserSessions", &v13);
  if ( v12 == -1073418222 )
  {
    v141 = g_ProviderToUse;
    v190 = g_ProviderToUse;
    v58 = 0;
    v58 = *g_ProviderToUse;
    v108 = v58;
    if ( v58 > 3 && (unsigned __int8)tlgKeywordOn(v141, 0) )
    {
      v6 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v246,
                                        "The SL policy for 'Max User Sessions' is not defined - assuming no limit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v141,
        (unsigned __int8 *)byte_1800C867D,
        0,
        0,
        v6);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v142 = g_ProviderToUse;
    v191 = g_ProviderToUse;
    v59 = 0;
    v59 = *g_ProviderToUse;
    v109 = v59;
    if ( v59 > 3 && (unsigned __int8)tlgKeywordOn(v142, 0) )
    {
      v192 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v247, "Initialize");
      v110 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v111, &v110);
      v193 = v111;
      v194 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v248,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for lMaxUserSessions");
      v195 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v249, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v142,
        (__int64)byte_1800C8B7B,
        0,
        0,
        v195,
        v194,
        (__int64)v193,
        v192);
    }
    return (unsigned int)v12;
  }
  CSLQuery::lMaxUserSessions = v13;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-ce0ad219-4670-4988-98fb-89b14c2f072b-MaxSessions",
          &v13);
  if ( v12 == -1073418222 )
  {
    v143 = g_ProviderToUse;
    v196 = g_ProviderToUse;
    v60 = 0;
    v60 = *g_ProviderToUse;
    v112 = v60;
    if ( v60 > 3 && (unsigned __int8)tlgKeywordOn(v143, 0) )
    {
      v7 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v250,
                                        "The SL policy for 'Max Debug Sessions' is not defined - assuming no limit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v143,
        (unsigned __int8 *)&word_1800C86FA,
        0,
        0,
        v7);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v144 = g_ProviderToUse;
    v197 = g_ProviderToUse;
    v61 = 0;
    v61 = *g_ProviderToUse;
    v113 = v61;
    if ( v61 > 3 && (unsigned __int8)tlgKeywordOn(v144, 0) )
    {
      v198 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v251, "Initialize");
      v114 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v115, &v114);
      v199 = v115;
      v200 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v252,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxDebugSessions");
      v201 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v253, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v144,
        (__int64)&byte_1800C86BF,
        0,
        0,
        v201,
        v200,
        (__int64)v199,
        v198);
    }
    return (unsigned int)v12;
  }
  CSLQuery::ulMaxDebugSessions = v13;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"Kernel-OneCore-VailGuest", &v13);
  if ( v12 == -1073418222 )
  {
    v145 = g_ProviderToUse;
    v202 = g_ProviderToUse;
    v62 = 0;
    v62 = *g_ProviderToUse;
    v116 = v62;
    if ( v62 > 3 && (unsigned __int8)tlgKeywordOn(v145, 0) )
    {
      v8 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v254,
                                        "The SL policy for 'VAIL Guest Policy' is not defined - assuming not in VAIL");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v145,
        (unsigned __int8 *)byte_1800C887D,
        0,
        0,
        v8);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v146 = g_ProviderToUse;
    v203 = g_ProviderToUse;
    v71 = 0;
    v71 = *g_ProviderToUse;
    v117 = v71;
    if ( v71 > 3 && (unsigned __int8)tlgKeywordOn(v146, 0) )
    {
      v204 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v255, "Initialize");
      v118 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v119, &v118);
      v205 = v119;
      v206 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v256,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bVailGuest");
      v207 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v257, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v146,
        (__int64)&byte_1800C891F,
        0,
        0,
        v207,
        v206,
        (__int64)v205,
        v204);
    }
    return (unsigned int)v12;
  }
  CSLQuery::bVailGuest = v13;
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(L"TerminalServices-RemoteConnectionManager-WVD-Enabled", &v13);
  if ( v12 == -1073418222 )
  {
    v147 = g_ProviderToUse;
    v208 = g_ProviderToUse;
    v64 = 0;
    v64 = *g_ProviderToUse;
    v120 = v64;
    if ( v64 > 3 && (unsigned __int8)tlgKeywordOn(v147, 0) )
    {
      v9 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v258,
                                        "The SL policy for 'WVD Enabled' is not defined - assuming WVD is disabled");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v147,
        (unsigned __int8 *)&word_1800C8AA2,
        0,
        0,
        v9);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 < 0 )
  {
    v148 = g_ProviderToUse;
    v209 = g_ProviderToUse;
    v65 = 0;
    v65 = *g_ProviderToUse;
    v121 = v65;
    if ( v65 > 3 && (unsigned __int8)tlgKeywordOn(v148, 0) )
    {
      v210 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v259, "Initialize");
      v122 = v12;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v123, &v122);
      v211 = v123;
      v212 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                          v260,
                                          "CSLQuery::Initialize - SLGetWindowsInformationDWORD for bWVDEnabled");
      v213 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v261, "Warning HResult failed");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v148,
        (__int64)byte_1800C87CC,
        0,
        0,
        v213,
        v212,
        (__int64)v211,
        v210);
    }
    return (unsigned int)v12;
  }
  v66 = v13 != 0;
  CSLQuery::bWVDEnabled = v66;
  v214 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v36 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v262 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  v263 = `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl;
  _scrt_stub_for_acrt_uninitialize_critical(`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl);
  v264 = v36;
  v265 = v36;
  v266 = v36;
  v14 = 1;
  v67 = 1;
  v15 = 1;
  v16 = 1;
  v17 = 1;
  v68 = 1;
  v18 = 1;
  v19 = 1;
  v69 = 1;
  v20 = 1;
  v21 = 1;
  v70 = 1;
  v22 = 1;
  v79 = 1;
  v23 = 1;
  v24 = 1;
  v72 = 1;
  v25 = 1;
  v26 = 1;
  v27 = 1;
  v28 = 1;
  v73 = 1;
  v29 = 1;
  v74 = 1;
  v30 = 1;
  v31 = 1;
  v75 = 1;
  v32 = 1;
  v33 = 1;
  v76 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(v36) != 0;
  v34 = v76;
  v35 = v76;
  if ( !v76 )
  {
LABEL_118:
    CSLQuery::bInitialized = 1;
    return (unsigned int)v12;
  }
  v13 = 0;
  v12 = SLGetWindowsInformationDWORDWrapper(
          L"TerminalServices-RemoteConnectionManager-cd051c59-3fe7-499c-9b66-02d99dbd8d3b-MaxSessions",
          &v13);
  if ( v12 == -1073418222 )
  {
    v149 = g_ProviderToUse;
    v215 = g_ProviderToUse;
    v77 = 0;
    v77 = *g_ProviderToUse;
    v124 = v77;
    if ( v77 > 3 && (unsigned __int8)tlgKeywordOn(v149, 0) )
    {
      v10 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                         v267,
                                         "The SL policy for 'Max Agent Sessions' is not defined - assuming no limit to user sessions");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v149,
        (unsigned __int8 *)byte_1800C865C,
        0,
        0,
        v10);
    }
    v13 = 0;
    v12 = 0;
  }
  if ( v12 >= 0 )
  {
    CSLQuery::ulMaxAgentSessions = v13;
    goto LABEL_118;
  }
  v150 = g_ProviderToUse;
  v216 = g_ProviderToUse;
  v78 = 0;
  v78 = *g_ProviderToUse;
  v125 = v78;
  if ( v78 > 3 && (unsigned __int8)tlgKeywordOn(v150, 0) )
  {
    v217 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v268, "Initialize");
    v126 = v12;
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v127, &v126);
    v218 = v127;
    v219 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(
                                        v269,
                                        "CSLQuery::Initialize - SLGetWindowsInformationDWORD for ulMaxAgentSessions");
    v220 = (const unsigned __int16 **)_tlgWrapSz<char>::_tlgWrapSz<char>(v270, "Warning HResult failed");
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v150,
      (__int64)byte_1800C8791,
      0,
      0,
      v220,
      v219,
      (__int64)v218,
      v217);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180080434  push    rdi
0x180080436  sub     rsp, 790h
0x18008043d  mov     rax, cs:__security_cookie
0x180080444  xor     rax, rsp
0x180080447  mov     [rsp+798h+var_18], rax
0x18008044f  mov     [rsp+798h+var_758], 80004001h
0x180080457  mov     [rsp+798h+var_754], 0
0x18008045f  lea     rax, [rsp+798h+VersionInformation]
0x180080467  mov     rdi, rax
0x18008046a  xor     eax, eax
0x18008046c  mov     ecx, 11Ch
0x180080471  rep stosb
0x180080473  mov     [rsp+798h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18008047e  lea     rcx, [rsp+798h+VersionInformation]; lpVersionInformation
0x180080486  call    cs:__imp_GetVersionExW
0x18008048c  test    eax, eax
0x18008048e  jz      short loc_1800804C7
0x180080490  movzx   eax, [rsp+798h+var_1E]
0x180080498  cmp     eax, 1
0x18008049b  jnz     short loc_1800804AA
0x18008049d  mov     [rsp+798h+var_6C8], 0
0x1800804a8  jmp     short loc_1800804B5
0x1800804aa  mov     [rsp+798h+var_6C8], 1
0x1800804b5  mov     eax, [rsp+798h+var_6C8]
0x1800804bc  mov     cs:?bServerSku@CSLQuery@@0HA, eax; int CSLQuery::bServerSku
0x1800804c2  jmp     loc_1800805C4
0x1800804c7  mov     rax, cs:g_ProviderToUse
0x1800804ce  mov     [rsp+798h+var_5C0], rax
0x1800804d6  mov     rax, [rsp+798h+var_5C0]
0x1800804de  mov     [rsp+798h+var_508], rax
0x1800804e6  mov     [rsp+798h+var_730], 0
0x1800804ee  mov     rax, [rsp+798h+var_508]
0x1800804f6  mov     eax, [rax]
0x1800804f8  mov     [rsp+798h+var_730], eax
0x1800804fc  mov     eax, [rsp+798h+var_730]
0x180080500  mov     [rsp+798h+var_684], eax
0x180080507  mov     eax, [rsp+798h+var_684]
0x18008050e  cmp     eax, 3
0x180080511  jbe     loc_1800805BA
0x180080517  mov     rdx, cs:qword_1800C88A1
0x18008051e  mov     rcx, [rsp+798h+var_5C0]
0x180080526  call    _tlgKeywordOn
0x18008052b  movzx   eax, al
0x18008052e  test    eax, eax
0x180080530  jz      loc_1800805BA
0x180080536  call    cs:__imp_GetLastError
0x18008053c  mov     [rsp+798h+var_680], eax
0x180080543  lea     rdx, [rsp+798h+var_680]
0x18008054b  lea     rcx, [rsp+798h+var_67C]
0x180080553  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180080558  nop
0x180080559  lea     rax, [rsp+798h+var_67C]
0x180080561  mov     [rsp+798h+var_500], rax
0x180080569  lea     rdx, aGetversionexFa; "GetVersionEx FAILED"
0x180080570  lea     rcx, [rsp+798h+var_2D8]
0x180080578  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x18008057d  mov     [rsp+798h+var_4F8], rax
0x180080585  mov     rax, [rsp+798h+var_500]
0x18008058d  mov     [rsp+798h+var_770], rax
0x180080592  mov     rax, [rsp+798h+var_4F8]
0x18008059a  mov     [rsp+798h+var_778], rax
0x18008059f  xor     r9d, r9d
0x1800805a2  xor     r8d, r8d
0x1800805a5  lea     rdx, word_1800C889E
0x1800805ac  mov     rcx, [rsp+798h+var_5C0]
0x1800805b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800805b9  nop
0x1800805ba  xor     eax, eax
0x1800805bc  test    eax, eax
0x1800805be  jnz     loc_1800804C7
0x1800805c4  mov     [rsp+798h+var_754], 0
0x1800805cc  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x1800805d1  lea     rcx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x1800805d8  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
0x1800805dd  mov     [rsp+798h+var_758], eax
0x1800805e1  cmp     [rsp+798h+var_758], 0C004F012h
0x1800805e9  jnz     loc_1800806BF
0x1800805ef  mov     rax, cs:g_ProviderToUse
0x1800805f6  mov     [rsp+798h+var_5B8], rax
0x1800805fe  mov     rax, [rsp+798h+var_5B8]
0x180080606  mov     [rsp+798h+var_4F0], rax
0x18008060e  mov     [rsp+798h+var_72C], 0
0x180080616  mov     rax, [rsp+798h+var_4F0]
0x18008061e  mov     eax, [rax]
0x180080620  mov     [rsp+798h+var_72C], eax
0x180080624  mov     eax, [rsp+798h+var_72C]
0x180080628  mov     [rsp+798h+var_678], eax
0x18008062f  mov     eax, [rsp+798h+var_678]
0x180080636  cmp     eax, 3
0x180080639  jbe     short loc_18008068A
0x18008063b  mov     rdx, cs:qword_1800C8B22
0x180080642  mov     rcx, [rsp+798h+var_5B8]
0x18008064a  call    _tlgKeywordOn
0x18008064f  movzx   eax, al
0x180080652  test    eax, eax
0x180080654  jz      short loc_18008068A
0x180080656  lea     rdx, aTheSlPolicyFor_3; "The SL policy for 'Allow Remote Connect"...
0x18008065d  lea     rcx, [rsp+798h+var_2D0]
0x180080665  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x18008066a  mov     [rsp+798h+var_778], rax
0x18008066f  xor     r9d, r9d
0x180080672  xor     r8d, r8d
0x180080675  lea     rdx, byte_1800C8B1F
0x18008067c  mov     rcx, [rsp+798h+var_5B8]
0x180080684  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180080689  nop
0x18008068a  xor     eax, eax
0x18008068c  test    eax, eax
0x18008068e  jnz     loc_1800805EF
0x180080694  cmp     cs:?bServerSku@CSLQuery@@0HA, 0; int CSLQuery::bServerSku
0x18008069b  jz      short loc_1800806A7
0x18008069d  mov     [rsp+798h+var_728], 1
0x1800806a5  jmp     short loc_1800806AF
0x1800806a7  mov     [rsp+798h+var_728], 0
0x1800806af  mov     eax, [rsp+798h+var_728]
0x1800806b3  mov     [rsp+798h+var_754], eax
0x1800806b7  mov     [rsp+798h+var_758], 0
0x1800806bf  cmp     [rsp+798h+var_758], 0
0x1800806c4  jge     loc_18008081C
0x1800806ca  mov     rax, cs:g_ProviderToUse
0x1800806d1  mov     [rsp+798h+var_5B0], rax
0x1800806d9  mov     rax, [rsp+798h+var_5B0]
0x1800806e1  mov     [rsp+798h+var_4E8], rax
0x1800806e9  mov     [rsp+798h+var_724], 0
0x1800806f1  mov     rax, [rsp+798h+var_4E8]
0x1800806f9  mov     eax, [rax]
0x1800806fb  mov     [rsp+798h+var_724], eax
0x1800806ff  mov     eax, [rsp+798h+var_724]
0x180080703  mov     [rsp+798h+var_674], eax
0x18008070a  mov     eax, [rsp+798h+var_674]
0x180080711  cmp     eax, 3
0x180080714  jbe     loc_18008080D
0x18008071a  mov     rdx, cs:qword_1800C8759
0x180080721  mov     rcx, [rsp+798h+var_5B0]
0x180080729  call    _tlgKeywordOn
0x18008072e  movzx   eax, al
0x180080731  test    eax, eax
0x180080733  jz      loc_18008080D
0x180080739  lea     rdx, aInitialize; "Initialize"
0x180080740  lea     rcx, [rsp+798h+var_2C8]
0x180080748  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x18008074d  mov     [rsp+798h+var_4E0], rax
0x180080755  mov     eax, [rsp+798h+var_758]
0x180080759  mov     [rsp+798h+var_670], eax
0x180080760  lea     rdx, [rsp+798h+var_670]
0x180080768  lea     rcx, [rsp+798h+var_66C]
0x180080770  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180080775  nop
0x180080776  lea     rax, [rsp+798h+var_66C]
0x18008077e  mov     [rsp+798h+var_4D8], rax
0x180080786  lea     rdx, aCslqueryInitia_2; "CSLQuery::Initialize - SLGetWindowsInfo"...
0x18008078d  lea     rcx, [rsp+798h+var_2C0]
0x180080795  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x18008079a  mov     [rsp+798h+var_4D0], rax
0x1800807a2  lea     rdx, aWarningHresult; "Warning HResult failed"
0x1800807a9  lea     rcx, [rsp+798h+var_2B8]
0x1800807b1  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x1800807b6  mov     [rsp+798h+var_4C8], rax
0x1800807be  mov     rax, [rsp+798h+var_4E0]
0x1800807c6  mov     [rsp+798h+var_760], rax
0x1800807cb  mov     rax, [rsp+798h+var_4D8]
0x1800807d3  mov     [rsp+798h+var_768], rax
0x1800807d8  mov     rax, [rsp+798h+var_4D0]
0x1800807e0  mov     [rsp+798h+var_770], rax
0x1800807e5  mov     rax, [rsp+798h+var_4C8]
0x1800807ed  mov     [rsp+798h+var_778], rax
0x1800807f2  xor     r9d, r9d
0x1800807f5  xor     r8d, r8d
0x1800807f8  lea     rdx, word_1800C8756
0x1800807ff  mov     rcx, [rsp+798h+var_5B0]
0x180080807  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008080c  nop
0x18008080d  xor     eax, eax
0x18008080f  test    eax, eax
0x180080811  jnz     loc_1800806CA
0x180080817  jmp     loc_180082462
0x18008081c  cmp     [rsp+798h+var_754], 0
0x180080821  jz      short loc_18008082D
0x180080823  mov     [rsp+798h+var_720], 1
0x18008082b  jmp     short loc_180080835
0x18008082d  mov     [rsp+798h+var_720], 0
0x180080835  mov     eax, [rsp+798h+var_720]
0x180080839  mov     cs:?bRemoteConnAllowed@CSLQuery@@0HA, eax; int CSLQuery::bRemoteConnAllowed
0x18008083f  mov     [rsp+798h+var_754], 0
0x180080847  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x18008084c  lea     rcx, aTerminalservic_5; "TerminalServices-RemoteConnectionManage"...
0x180080853  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
0x180080858  mov     [rsp+798h+var_758], eax
0x18008085c  cmp     [rsp+798h+var_758], 0C004F012h
0x180080864  jnz     loc_180080943
0x18008086a  mov     rax, cs:g_ProviderToUse
0x180080871  mov     [rsp+798h+var_5A8], rax
0x180080879  mov     rax, [rsp+798h+var_5A8]
0x180080881  mov     [rsp+798h+var_4C0], rax
0x180080889  mov     [rsp+798h+var_71C], 0
0x180080891  mov     rax, [rsp+798h+var_4C0]
0x180080899  mov     eax, [rax]
0x18008089b  mov     [rsp+798h+var_71C], eax
0x18008089f  mov     eax, [rsp+798h+var_71C]
0x1800808a3  mov     [rsp+798h+var_668], eax
0x1800808aa  mov     eax, [rsp+798h+var_668]
0x1800808b1  cmp     eax, 3
0x1800808b4  jbe     short loc_180080905
0x1800808b6  mov     rdx, cs:qword_1800C8B01
0x1800808bd  mov     rcx, [rsp+798h+var_5A8]
0x1800808c5  call    _tlgKeywordOn
0x1800808ca  movzx   eax, al
0x1800808cd  test    eax, eax
0x1800808cf  jz      short loc_180080905
0x1800808d1  lea     rdx, aTheSlPolicyFor_2; "The SL policy for 'Allow Multiple Sessi"...
0x1800808d8  lea     rcx, [rsp+798h+var_2B0]
0x1800808e0  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x1800808e5  mov     [rsp+798h+var_778], rax
0x1800808ea  xor     r9d, r9d
0x1800808ed  xor     r8d, r8d
0x1800808f0  lea     rdx, word_1800C8AFE
0x1800808f7  mov     rcx, [rsp+798h+var_5A8]
0x1800808ff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180080904  nop
0x180080905  xor     eax, eax
0x180080907  test    eax, eax
0x180080909  jnz     loc_18008086A
0x18008090f  cmp     cs:?bServerSku@CSLQuery@@0HA, 0; int CSLQuery::bServerSku
0x180080916  jz      short loc_180080925
0x180080918  mov     [rsp+798h+var_718], 1
0x180080923  jmp     short loc_180080930
0x180080925  mov     [rsp+798h+var_718], 0
0x180080930  mov     eax, [rsp+798h+var_718]
0x180080937  mov     [rsp+798h+var_754], eax
0x18008093b  mov     [rsp+798h+var_758], 0
0x180080943  cmp     [rsp+798h+var_758], 0
0x180080948  jge     loc_180080AA9
0x18008094e  mov     rax, cs:g_ProviderToUse
0x180080955  mov     [rsp+798h+var_5A0], rax
0x18008095d  mov     rax, [rsp+798h+var_5A0]
0x180080965  mov     [rsp+798h+var_4B8], rax
0x18008096d  mov     [rsp+798h+var_714], 0
0x180080978  mov     rax, [rsp+798h+var_4B8]
0x180080980  mov     eax, [rax]
0x180080982  mov     [rsp+798h+var_714], eax
0x180080989  mov     eax, [rsp+798h+var_714]
0x180080990  mov     [rsp+798h+var_664], eax
0x180080997  mov     eax, [rsp+798h+var_664]
0x18008099e  cmp     eax, 3
0x1800809a1  jbe     loc_180080A9A
0x1800809a7  mov     rdx, cs:qword_1800C8A6A
0x1800809ae  mov     rcx, [rsp+798h+var_5A0]
0x1800809b6  call    _tlgKeywordOn
0x1800809bb  movzx   eax, al
0x1800809be  test    eax, eax
0x1800809c0  jz      loc_180080A9A
0x1800809c6  lea     rdx, aInitialize; "Initialize"
0x1800809cd  lea     rcx, [rsp+798h+var_2A8]
0x1800809d5  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x1800809da  mov     [rsp+798h+var_4B0], rax
0x1800809e2  mov     eax, [rsp+798h+var_758]
0x1800809e6  mov     [rsp+798h+var_660], eax
0x1800809ed  lea     rdx, [rsp+798h+var_660]
0x1800809f5  lea     rcx, [rsp+798h+var_65C]
0x1800809fd  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180080a02  nop
0x180080a03  lea     rax, [rsp+798h+var_65C]
0x180080a0b  mov     [rsp+798h+var_4A8], rax
0x180080a13  lea     rdx, aCslqueryInitia_4; "CSLQuery::Initialize - SLGetWindowsInfo"...
0x180080a1a  lea     rcx, [rsp+798h+var_2A0]
0x180080a22  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x180080a27  mov     [rsp+798h+var_4A0], rax
0x180080a2f  lea     rdx, aWarningHresult; "Warning HResult failed"
0x180080a36  lea     rcx, [rsp+798h+var_298]
0x180080a3e  call    ??0?$_tlgWrapSz@D@@QEAA@PEBD@Z; _tlgWrapSz<char>::_tlgWrapSz<char>(char const *)
0x180080a43  mov     [rsp+798h+var_498], rax
0x180080a4b  mov     rax, [rsp+798h+var_4B0]
0x180080a53  mov     [rsp+798h+var_760], rax
0x180080a58  mov     rax, [rsp+798h+var_4A8]
0x180080a60  mov     [rsp+798h+var_768], rax
0x180080a65  mov     rax, [rsp+798h+var_4A0]
0x180080a6d  mov     [rsp+798h+var_770], rax
0x180080a72  mov     rax, [rsp+798h+var_498]
0x180080a7a  mov     [rsp+798h+var_778], rax
0x180080a7f  xor     r9d, r9d
0x180080a82  xor     r8d, r8d
0x180080a85  lea     rdx, byte_1800C8A67
0x180080a8c  mov     rcx, [rsp+798h+var_5A0]
0x180080a94  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180080a99  nop
0x180080a9a  xor     eax, eax
0x180080a9c  test    eax, eax
0x180080a9e  jnz     loc_18008094E
0x180080aa4  jmp     loc_180082462
0x180080aa9  cmp     [rsp+798h+var_754], 0
0x180080aae  jz      short loc_180080ABD
0x180080ab0  mov     [rsp+798h+var_710], 1
0x180080abb  jmp     short loc_180080AC8
0x180080abd  mov     [rsp+798h+var_710], 0
0x180080ac8  mov     eax, [rsp+798h+var_710]
0x180080acf  mov     cs:?bFUSEnabled@CSLQuery@@0HA, eax; int CSLQuery::bFUSEnabled
0x180080ad5  mov     [rsp+798h+var_754], 0
0x180080add  lea     rdx, [rsp+798h+var_754]; unsigned int *
0x180080ae2  lea     rcx, aTerminalservic_8; "TerminalServices-RemoteConnectionManage"...
0x180080ae9  call    ?SLGetWindowsInformationDWORDWrapper@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORDWrapper(ushort const *,ulong *)
  ... truncated ...
```
