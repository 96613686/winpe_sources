# KerbGetKerbRegParams(HKEY__ *)

- ea: `0x18007b8ac`
- end: `0x18007d1f7`
- name: `?KerbGetKerbRegParams@@YAXPEAUHKEY__@@@Z`
- size: `6475`
- prototype: `void __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007e200`

## callees

- `0x180001808`
- `0x180002b84`
- `0x1800069a0`
- `0x1800093f0`
- `0x180035c68`
- `0x18003acc0`
- `0x18003aef0`
- `0x18006847c`
- `0x18006ba6c`
- `0x18006c1ac`
- `0x18006d958`
- `0x18006da5c`
- `0x18006eb4c`
- `0x180070680`
- `0x1800744c3`
- `0x18007b648`
- `0x18007b8ac`
- `0x18007d5e8`
- `0x18007ece4`
- `0x18007f508`
- `0x18008b70c`
- `0x18008db80`
- `0x1800dabcc`
- `0x1800db020`
- `0x1800db8f4`
- `0x1800ddb74`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cdce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cdce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007c9ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007cc88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ce9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007cf46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007c9ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007cc88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ce9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007cf46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ca48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cb64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ca48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007cb64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ca31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ca31`
- `ntdll!WinSqmSetDWORD` at `0x18007ccf2`
- `ntdll!WinSqmSetDWORD` at `0x18007ccf2`
- `ntdll!RtlEnterCriticalSection` at `0x18007cd7f`
- `ntdll!RtlEnterCriticalSection` at `0x18007cd7f`
- `ntdll!RtlLeaveCriticalSection` at `0x18007ce6b`
- `ntdll!RtlLeaveCriticalSection` at `0x18007ce6b`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x18007d10d`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x18007d10d`
- `KerbClientShared!KerbClient3961UpdateSharedConfiguration` at `0x18007d16e`
- `KerbClientShared!KerbClient3961UpdateSharedConfiguration` at `0x18007d16e`
- `LSASRV!LsaIUpdateKerbMaxTokenSize` at `0x18007cd3b`
- `LSASRV!LsaIUpdateKerbMaxTokenSize` at `0x18007cd3b`

## string_xrefs

- `0x18007bb59`: `ServiceIterationCount`
- `0x18007bdda`: `SpnCacheTimeout`
- `0x18007be0c`: `S4UCacheTimeout`
- `0x18007bf72`: `CachedKdcConnectTimeout`
- `0x18007c07f`: `CacheS4UTickets`
- `0x18007c0e1`: `UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors`
- `0x18007c371`: `FsoCacheTimeout`
- `0x18007c467`: `ProxyCacheExpiry`
- `0x18007c56e`: `AlwaysSendCompoundId`
- `0x18007c704`: `PKInitHashAlgorithmConfigurationEnabled`
- `0x18007cc7e`: `MaxTokenSize`
- `0x18007ccbf`: `KerbGetKerbRegParams MaxToken out of range %d\n`
- `0x18007cd17`: `KerbGetKerbRegParams updating old maxtoken size %d to %d\n`
- `0x18007d0c7`: `KerbGetKerbRegParams failed to invoke UpdateSharedConfiguration`
- `0x18007d157`: `UpdateKerb3961SharedConfiguration failed with status: 0x%X\n`
- `0x18007d178`: `KerbClient3961UpdateSharedConfiguration failed with status: 0x%X\n`

## pseudocode

```c
void __fastcall KerbGetKerbRegParams(HKEY a1, __int64 a2)
{
  HKEY v2; // rbx
  int v3; // edi
  int v4; // esi
  int v5; // r14d
  int v6; // r15d
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  unsigned int v9; // r8d
  HKEY v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  unsigned int v13; // r8d
  union _LARGE_INTEGER v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // edx
  struct _CERT_X942_DH_PARAMETERS *v17; // r8
  DWORD LastError; // eax
  const char *v19; // rcx
  const char *v20; // rcx
  LSTATUS v21; // eax
  BYTE *v22; // rax
  LSTATUS v23; // eax
  __int64 v24; // rbx
  int v25; // edi
  __int64 *v26; // rbx
  int v27; // r8d
  Ntlmless::Kerberos *v28; // rcx
  __int64 LocalCipherPolicy; // rax
  int updated; // eax
  const char *v31; // r9
  __int64 v32; // r8
  KerbTelemetry *v33; // rcx
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v38; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v41; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v44; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v46; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v47; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v48; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v49; // [rsp+90h] [rbp-70h] BYREF
  int v50; // [rsp+94h] [rbp-6Ch] BYREF
  int v51; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v52; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v53; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v54; // [rsp+A4h] [rbp-5Ch] BYREF
  __int128 v55; // [rsp+B0h] [rbp-50h] BYREF
  int v56; // [rsp+C0h] [rbp-40h]
  LPBYTE lpcbData[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v58; // [rsp+E0h] [rbp-20h] BYREF
  int v59; // [rsp+E4h] [rbp-1Ch] BYREF
  int v60; // [rsp+E8h] [rbp-18h] BYREF
  BOOL v61; // [rsp+ECh] [rbp-14h] BYREF
  __int128 v62; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v63[2]; // [rsp+100h] [rbp+0h] BYREF
  int v64; // [rsp+110h] [rbp+10h]
  int v65; // [rsp+114h] [rbp+14h]
  const char *v66; // [rsp+118h] [rbp+18h]
  __int64 v67; // [rsp+120h] [rbp+20h]
  int v68; // [rsp+128h] [rbp+28h]
  int v69; // [rsp+12Ch] [rbp+2Ch]
  const char *v70; // [rsp+130h] [rbp+30h]
  __int64 v71; // [rsp+138h] [rbp+38h]
  int v72; // [rsp+140h] [rbp+40h]
  int v73; // [rsp+144h] [rbp+44h]
  const char *v74; // [rsp+148h] [rbp+48h]
  __int64 v75; // [rsp+150h] [rbp+50h]
  int v76; // [rsp+158h] [rbp+58h]
  int v77; // [rsp+15Ch] [rbp+5Ch]
  __int128 v78; // [rsp+160h] [rbp+60h] BYREF
  int v79; // [rsp+170h] [rbp+70h] BYREF
  __int128 v80; // [rsp+178h] [rbp+78h] BYREF
  unsigned int v81; // [rsp+188h] [rbp+88h]
  _QWORD v82[24]; // [rsp+190h] [rbp+90h] BYREF
  int v83; // [rsp+250h] [rbp+150h]
  int v84; // [rsp+254h] [rbp+154h]
  const wchar_t *v85; // [rsp+258h] [rbp+158h]
  unsigned int *v86; // [rsp+260h] [rbp+160h]
  __int64 v87; // [rsp+268h] [rbp+168h]
  __int64 v88; // [rsp+270h] [rbp+170h]
  __int64 v89; // [rsp+278h] [rbp+178h]
  const wchar_t *v90; // [rsp+280h] [rbp+180h]
  char *v91; // [rsp+288h] [rbp+188h]
  __int64 v92; // [rsp+290h] [rbp+190h]
  __int64 v93; // [rsp+298h] [rbp+198h]
  __int64 v94; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v95; // [rsp+2A8h] [rbp+1A8h]
  __int128 *v96; // [rsp+2B0h] [rbp+1B0h]
  __int64 v97; // [rsp+2B8h] [rbp+1B8h]
  __int64 v98; // [rsp+2C0h] [rbp+1C0h]
  int v99; // [rsp+2C8h] [rbp+1C8h]
  int v100; // [rsp+2CCh] [rbp+1CCh]
  const wchar_t *v101; // [rsp+2D0h] [rbp+1D0h]
  char *v102; // [rsp+2D8h] [rbp+1D8h]
  int v103; // [rsp+2E0h] [rbp+1E0h]
  int v104; // [rsp+2E4h] [rbp+1E4h]
  __int64 v105; // [rsp+2E8h] [rbp+1E8h]
  __int64 v106; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v107; // [rsp+2F8h] [rbp+1F8h]
  unsigned int *v108; // [rsp+300h] [rbp+200h]
  __int64 v109; // [rsp+308h] [rbp+208h]
  __int64 v110; // [rsp+310h] [rbp+210h]
  __int64 v111; // [rsp+318h] [rbp+218h]
  const wchar_t *v112; // [rsp+320h] [rbp+220h]
  int *v113; // [rsp+328h] [rbp+228h]
  __int64 v114; // [rsp+330h] [rbp+230h]
  __int64 v115; // [rsp+338h] [rbp+238h]
  __int64 v116; // [rsp+340h] [rbp+240h]
  const wchar_t *v117; // [rsp+348h] [rbp+248h]
  unsigned int *v118; // [rsp+350h] [rbp+250h]
  __int64 v119; // [rsp+358h] [rbp+258h]
  __int64 v120; // [rsp+360h] [rbp+260h]
  __int64 v121; // [rsp+368h] [rbp+268h]
  const wchar_t *v122; // [rsp+370h] [rbp+270h]
  unsigned int *v123; // [rsp+378h] [rbp+278h]
  __int64 v124; // [rsp+380h] [rbp+280h]
  __int64 v125; // [rsp+388h] [rbp+288h]
  __int64 v126; // [rsp+390h] [rbp+290h]
  const wchar_t *v127; // [rsp+398h] [rbp+298h]
  unsigned int *v128; // [rsp+3A0h] [rbp+2A0h]
  __int64 v129; // [rsp+3A8h] [rbp+2A8h]
  __int64 v130; // [rsp+3B0h] [rbp+2B0h]
  __int64 v131; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v132; // [rsp+3C0h] [rbp+2C0h]
  unsigned int *v133; // [rsp+3C8h] [rbp+2C8h]
  __int64 v134; // [rsp+3D0h] [rbp+2D0h]
  __int64 v135; // [rsp+3D8h] [rbp+2D8h]
  __int64 v136; // [rsp+3E0h] [rbp+2E0h]
  const wchar_t *v137; // [rsp+3E8h] [rbp+2E8h]
  unsigned int *v138; // [rsp+3F0h] [rbp+2F0h]
  __int64 v139; // [rsp+3F8h] [rbp+2F8h]
  __int64 v140; // [rsp+400h] [rbp+300h]
  __int64 v141; // [rsp+408h] [rbp+308h]
  const wchar_t *v142; // [rsp+410h] [rbp+310h]
  char *v143; // [rsp+418h] [rbp+318h]
  __int64 v144; // [rsp+420h] [rbp+320h]
  __int64 v145; // [rsp+428h] [rbp+328h]
  __int64 v146; // [rsp+430h] [rbp+330h]
  const wchar_t *v147; // [rsp+438h] [rbp+338h]
  unsigned int *v148; // [rsp+440h] [rbp+340h]
  __int64 v149; // [rsp+448h] [rbp+348h]
  __int64 v150; // [rsp+450h] [rbp+350h]
  __int64 v151; // [rsp+458h] [rbp+358h]
  const wchar_t *v152; // [rsp+460h] [rbp+360h]
  unsigned int *v153; // [rsp+468h] [rbp+368h]
  __int64 v154; // [rsp+470h] [rbp+370h]
  __int64 v155; // [rsp+478h] [rbp+378h]
  __int64 v156; // [rsp+480h] [rbp+380h]
  const wchar_t *v157; // [rsp+488h] [rbp+388h]
  unsigned int *v158; // [rsp+490h] [rbp+390h]
  __int64 v159; // [rsp+498h] [rbp+398h]
  __int64 v160; // [rsp+4A0h] [rbp+3A0h]
  __int64 v161; // [rsp+4A8h] [rbp+3A8h]
  const wchar_t *v162; // [rsp+4B0h] [rbp+3B0h]
  int *v163; // [rsp+4B8h] [rbp+3B8h]
  __int64 v164; // [rsp+4C0h] [rbp+3C0h]
  __int64 v165; // [rsp+4C8h] [rbp+3C8h]
  __int64 v166; // [rsp+4D0h] [rbp+3D0h]
  const wchar_t *v167; // [rsp+4D8h] [rbp+3D8h]
  int *v168; // [rsp+4E0h] [rbp+3E0h]
  __int64 v169; // [rsp+4E8h] [rbp+3E8h]
  __int64 v170; // [rsp+4F0h] [rbp+3F0h]
  __int64 v171; // [rsp+4F8h] [rbp+3F8h]
  const wchar_t *v172; // [rsp+500h] [rbp+400h]
  unsigned int *v173; // [rsp+508h] [rbp+408h]
  __int64 v174; // [rsp+510h] [rbp+410h]
  __int64 v175; // [rsp+518h] [rbp+418h]
  __int64 v176; // [rsp+520h] [rbp+420h]
  const wchar_t *v177; // [rsp+528h] [rbp+428h]
  unsigned int *v178; // [rsp+530h] [rbp+430h]
  __int64 v179; // [rsp+538h] [rbp+438h]
  __int64 v180; // [rsp+540h] [rbp+440h]
  __int64 v181; // [rsp+548h] [rbp+448h]
  const wchar_t *v182; // [rsp+550h] [rbp+450h]
  unsigned int *v183; // [rsp+558h] [rbp+458h]
  __int64 v184; // [rsp+560h] [rbp+460h]
  __int64 v185; // [rsp+568h] [rbp+468h]
  __int64 v186; // [rsp+570h] [rbp+470h]
  const wchar_t *v187; // [rsp+578h] [rbp+478h]
  unsigned int *v188; // [rsp+580h] [rbp+480h]
  __int64 v189; // [rsp+588h] [rbp+488h]
  __int64 v190; // [rsp+590h] [rbp+490h]
  __int64 v191; // [rsp+598h] [rbp+498h]
  const wchar_t *v192; // [rsp+5A0h] [rbp+4A0h]
  unsigned int *v193; // [rsp+5A8h] [rbp+4A8h]
  __int64 v194; // [rsp+5B0h] [rbp+4B0h]
  __int64 v195; // [rsp+5B8h] [rbp+4B8h]
  __int64 v196; // [rsp+5C0h] [rbp+4C0h]
  const wchar_t *v197; // [rsp+5C8h] [rbp+4C8h]
  size_t *v198; // [rsp+5D0h] [rbp+4D0h]
  __int64 v199; // [rsp+5D8h] [rbp+4D8h]
  __int64 v200; // [rsp+5E0h] [rbp+4E0h]
  __int64 v201; // [rsp+5E8h] [rbp+4E8h]
  const wchar_t *v202; // [rsp+5F0h] [rbp+4F0h]
  unsigned int *v203; // [rsp+5F8h] [rbp+4F8h]
  __int64 v204; // [rsp+600h] [rbp+500h]
  __int64 v205; // [rsp+608h] [rbp+508h]
  __int64 v206; // [rsp+610h] [rbp+510h]
  const wchar_t *v207; // [rsp+618h] [rbp+518h]
  unsigned int *v208; // [rsp+620h] [rbp+520h]
  __int64 v209; // [rsp+628h] [rbp+528h]
  __int64 v210; // [rsp+630h] [rbp+530h]
  __int64 v211; // [rsp+638h] [rbp+538h]
  const wchar_t *v212; // [rsp+640h] [rbp+540h]
  unsigned int *v213; // [rsp+648h] [rbp+548h]
  __int64 v214; // [rsp+650h] [rbp+550h]
  __int64 v215; // [rsp+658h] [rbp+558h]
  __int64 v216; // [rsp+660h] [rbp+560h]
  const wchar_t *v217; // [rsp+668h] [rbp+568h]
  unsigned int *v218; // [rsp+670h] [rbp+570h]
  __int64 v219; // [rsp+678h] [rbp+578h]
  __int64 v220; // [rsp+680h] [rbp+580h]
  __int64 v221; // [rsp+688h] [rbp+588h]
  const wchar_t *v222; // [rsp+690h] [rbp+590h]
  unsigned int *v223; // [rsp+698h] [rbp+598h]
  __int64 v224; // [rsp+6A0h] [rbp+5A0h]
  __int64 v225; // [rsp+6A8h] [rbp+5A8h]
  __int64 v226; // [rsp+6B0h] [rbp+5B0h]
  const wchar_t *v227; // [rsp+6B8h] [rbp+5B8h]
  unsigned int *v228; // [rsp+6C0h] [rbp+5C0h]
  unsigned int v229; // [rsp+6C8h] [rbp+5C8h]
  __int64 v230; // [rsp+6CCh] [rbp+5CCh]
  __int64 v231; // [rsp+6D4h] [rbp+5D4h]
  int v232; // [rsp+6DCh] [rbp+5DCh]
  const wchar_t *v233; // [rsp+6E0h] [rbp+5E0h]
  unsigned int *v234; // [rsp+6E8h] [rbp+5E8h]
  __int64 v235; // [rsp+6F0h] [rbp+5F0h]
  __int64 v236; // [rsp+6F8h] [rbp+5F8h]
  __int64 v237; // [rsp+700h] [rbp+600h]
  const wchar_t *v238; // [rsp+708h] [rbp+608h]
  unsigned int *v239; // [rsp+710h] [rbp+610h]
  __int64 v240; // [rsp+718h] [rbp+618h]
  __int64 v241; // [rsp+720h] [rbp+620h]
  __int64 v242; // [rsp+728h] [rbp+628h]
  const wchar_t *v243; // [rsp+730h] [rbp+630h]
  unsigned int *v244; // [rsp+738h] [rbp+638h]
  __int64 v245; // [rsp+740h] [rbp+640h]
  __int64 v246; // [rsp+748h] [rbp+648h]
  __int64 v247; // [rsp+750h] [rbp+650h]
  const wchar_t *v248; // [rsp+758h] [rbp+658h]
  unsigned int *v249; // [rsp+760h] [rbp+660h]
  __int64 v250; // [rsp+768h] [rbp+668h]
  __int64 v251; // [rsp+770h] [rbp+670h]
  __int64 v252; // [rsp+778h] [rbp+678h]
  const wchar_t *v253; // [rsp+780h] [rbp+680h]
  unsigned int *v254; // [rsp+788h] [rbp+688h]
  __int64 v255; // [rsp+790h] [rbp+690h]
  __int64 v256; // [rsp+798h] [rbp+698h]
  __int64 v257; // [rsp+7A0h] [rbp+6A0h]
  const wchar_t *v258; // [rsp+7A8h] [rbp+6A8h]
  unsigned int *v259; // [rsp+7B0h] [rbp+6B0h]
  __int64 v260; // [rsp+7B8h] [rbp+6B8h]
  __int64 v261; // [rsp+7C0h] [rbp+6C0h]
  int v262; // [rsp+7C8h] [rbp+6C8h]
  int v263; // [rsp+7CCh] [rbp+6CCh]
  const wchar_t *v264; // [rsp+7D0h] [rbp+6D0h]
  unsigned int *v265; // [rsp+7D8h] [rbp+6D8h]
  __int64 v266; // [rsp+7E0h] [rbp+6E0h]
  __int64 v267; // [rsp+7E8h] [rbp+6E8h]
  __int64 v268; // [rsp+7F0h] [rbp+6F0h]
  const wchar_t *v269; // [rsp+7F8h] [rbp+6F8h]
  int *v270; // [rsp+800h] [rbp+700h]
  __int64 v271; // [rsp+808h] [rbp+708h]
  __int64 v272; // [rsp+810h] [rbp+710h]
  __int64 v273; // [rsp+818h] [rbp+718h]
  const wchar_t *v274; // [rsp+820h] [rbp+720h]
  unsigned int *v275; // [rsp+828h] [rbp+728h]
  __int64 v276; // [rsp+830h] [rbp+730h]
  __int64 v277; // [rsp+838h] [rbp+738h]
  __int64 v278; // [rsp+840h] [rbp+740h]
  const wchar_t *v279; // [rsp+848h] [rbp+748h]
  unsigned int *v280; // [rsp+850h] [rbp+750h]
  __int64 v281; // [rsp+858h] [rbp+758h]
  __int64 v282; // [rsp+860h] [rbp+760h]
  __int64 v283; // [rsp+868h] [rbp+768h]
  const wchar_t *v284; // [rsp+870h] [rbp+770h]
  unsigned int *v285; // [rsp+878h] [rbp+778h]
  __int64 v286; // [rsp+880h] [rbp+780h]
  __int64 v287; // [rsp+888h] [rbp+788h]
  __int64 v288; // [rsp+890h] [rbp+790h]
  const wchar_t *v289; // [rsp+898h] [rbp+798h]
  unsigned int *v290; // [rsp+8A0h] [rbp+7A0h]
  __int64 v291; // [rsp+8A8h] [rbp+7A8h]
  __int64 v292; // [rsp+8B0h] [rbp+7B0h]
  __int64 v293; // [rsp+8B8h] [rbp+7B8h]
  const wchar_t *v294; // [rsp+8C0h] [rbp+7C0h]
  unsigned int *v295; // [rsp+8C8h] [rbp+7C8h]
  __int64 v296; // [rsp+8D0h] [rbp+7D0h]
  __int64 v297; // [rsp+8D8h] [rbp+7D8h]
  __int64 v298; // [rsp+8E0h] [rbp+7E0h]
  const wchar_t *v299; // [rsp+8E8h] [rbp+7E8h]
  unsigned int *v300; // [rsp+8F0h] [rbp+7F0h]
  __int64 v301; // [rsp+8F8h] [rbp+7F8h]
  __int64 v302; // [rsp+900h] [rbp+800h]
  __int64 v303; // [rsp+908h] [rbp+808h]
  const wchar_t *v304; // [rsp+910h] [rbp+810h]
  unsigned int *v305; // [rsp+918h] [rbp+818h]
  __int64 v306; // [rsp+920h] [rbp+820h]
  __int64 v307; // [rsp+928h] [rbp+828h]
  __int64 v308; // [rsp+930h] [rbp+830h]
  const wchar_t *v309; // [rsp+938h] [rbp+838h]
  unsigned int *v310; // [rsp+940h] [rbp+840h]
  __int64 v311; // [rsp+948h] [rbp+848h]
  __int64 v312; // [rsp+950h] [rbp+850h]
  __int64 v313; // [rsp+958h] [rbp+858h]
  const wchar_t *v314; // [rsp+960h] [rbp+860h]
  unsigned int *v315; // [rsp+968h] [rbp+868h]
  __int64 v316; // [rsp+970h] [rbp+870h]
  __int64 v317; // [rsp+978h] [rbp+878h]
  __int64 v318; // [rsp+980h] [rbp+880h]
  const wchar_t *v319; // [rsp+988h] [rbp+888h]
  unsigned int *v320; // [rsp+990h] [rbp+890h]
  __int64 v321; // [rsp+998h] [rbp+898h]
  __int64 v322; // [rsp+9A0h] [rbp+8A0h]
  __int64 v323; // [rsp+9A8h] [rbp+8A8h]
  const wchar_t *v324; // [rsp+9B0h] [rbp+8B0h]
  unsigned int *v325; // [rsp+9B8h] [rbp+8B8h]
  __int64 v326; // [rsp+9C0h] [rbp+8C0h]
  __int64 v327; // [rsp+9C8h] [rbp+8C8h]
  __int64 v328; // [rsp+9D0h] [rbp+8D0h]
  const wchar_t *v329; // [rsp+9D8h] [rbp+8D8h]
  unsigned int *v330; // [rsp+9E0h] [rbp+8E0h]
  __int64 v331; // [rsp+9E8h] [rbp+8E8h]
  __int64 v332; // [rsp+9F0h] [rbp+8F0h]
  __int64 v333; // [rsp+9F8h] [rbp+8F8h]
  const wchar_t *v334; // [rsp+A00h] [rbp+900h]
  unsigned int *v335; // [rsp+A08h] [rbp+908h]
  __int64 v336; // [rsp+A10h] [rbp+910h]
  __int64 v337; // [rsp+A18h] [rbp+918h]
  __int64 v338; // [rsp+A20h] [rbp+920h]
  const wchar_t *v339; // [rsp+A28h] [rbp+928h]
  unsigned int *v340; // [rsp+A30h] [rbp+930h]
  __int64 v341; // [rsp+A38h] [rbp+938h]
  __int64 v342; // [rsp+A40h] [rbp+940h]
  __int64 v343; // [rsp+A48h] [rbp+948h]
  const wchar_t *v344; // [rsp+A50h] [rbp+950h]
  unsigned int *v345; // [rsp+A58h] [rbp+958h]
  __int64 v346; // [rsp+A60h] [rbp+960h]
  __int64 v347; // [rsp+A68h] [rbp+968h]
  __int64 v348; // [rsp+A70h] [rbp+970h]
  const wchar_t *v349; // [rsp+A78h] [rbp+978h]
  unsigned int *v350; // [rsp+A80h] [rbp+980h]
  __int64 v351; // [rsp+A88h] [rbp+988h]
  __int64 v352; // [rsp+A90h] [rbp+990h]
  __int64 v353; // [rsp+A98h] [rbp+998h]
  const wchar_t *v354; // [rsp+AA0h] [rbp+9A0h]
  unsigned int *v355; // [rsp+AA8h] [rbp+9A8h]
  __int64 v356; // [rsp+AB0h] [rbp+9B0h]
  __int64 v357; // [rsp+AB8h] [rbp+9B8h]
  int v358; // [rsp+AC0h] [rbp+9C0h]
  int v359; // [rsp+AC4h] [rbp+9C4h]
  const wchar_t *v360; // [rsp+AC8h] [rbp+9C8h]
  unsigned int *v361; // [rsp+AD0h] [rbp+9D0h]
  __int64 v362; // [rsp+AD8h] [rbp+9D8h]
  __int64 v363; // [rsp+AE0h] [rbp+9E0h]
  int v364; // [rsp+AE8h] [rbp+9E8h]
  int v365; // [rsp+AECh] [rbp+9ECh]
  const wchar_t *v366; // [rsp+AF0h] [rbp+9F0h]
  unsigned int *v367; // [rsp+AF8h] [rbp+9F8h]
  __int64 v368; // [rsp+B00h] [rbp+A00h]
  __int64 v369; // [rsp+B08h] [rbp+A08h]
  __int64 v370; // [rsp+B10h] [rbp+A10h]
  const wchar_t *v371; // [rsp+B18h] [rbp+A18h]
  unsigned int *v372; // [rsp+B20h] [rbp+A20h]
  __int64 v373; // [rsp+B28h] [rbp+A28h]
  __int64 v374; // [rsp+B30h] [rbp+A30h]
  __int64 v375; // [rsp+B38h] [rbp+A38h]
  const wchar_t *v376; // [rsp+B40h] [rbp+A40h]
  unsigned int *v377; // [rsp+B48h] [rbp+A48h]
  __int64 v378; // [rsp+B50h] [rbp+A50h]
  __int64 v379; // [rsp+B58h] [rbp+A58h]
  int v380; // [rsp+B60h] [rbp+A60h]
  int v381; // [rsp+B64h] [rbp+A64h]
  const wchar_t *v382; // [rsp+B68h] [rbp+A68h]
  unsigned int *v383; // [rsp+B70h] [rbp+A70h]
  __int64 v384; // [rsp+B78h] [rbp+A78h]
  __int64 v385; // [rsp+B80h] [rbp+A80h]
  int v386; // [rsp+B88h] [rbp+A88h]
  int v387; // [rsp+B8Ch] [rbp+A8Ch]
  const wchar_t *v388; // [rsp+B90h] [rbp+A90h]
  unsigned int *v389; // [rsp+B98h] [rbp+A98h]
  __int64 v390; // [rsp+BA0h] [rbp+AA0h]
  __int64 v391; // [rsp+BA8h] [rbp+AA8h]
  __int64 v392; // [rsp+BB0h] [rbp+AB0h]
  const wchar_t *v393; // [rsp+BB8h] [rbp+AB8h]
  unsigned int *v394; // [rsp+BC0h] [rbp+AC0h]
  __int64 v395; // [rsp+BC8h] [rbp+AC8h]
  __int64 v396; // [rsp+BD0h] [rbp+AD0h]
  __int64 v397; // [rsp+BD8h] [rbp+AD8h]
  const wchar_t *v398; // [rsp+BE0h] [rbp+AE0h]
  unsigned int *v399; // [rsp+BE8h] [rbp+AE8h]
  __int64 v400; // [rsp+BF0h] [rbp+AF0h]
  __int64 v401; // [rsp+BF8h] [rbp+AF8h]
  __int64 v402; // [rsp+C00h] [rbp+B00h]
  const wchar_t *v403; // [rsp+C08h] [rbp+B08h]
  unsigned int *v404; // [rsp+C10h] [rbp+B10h]
  __int64 v405; // [rsp+C18h] [rbp+B18h]
  __int64 v406; // [rsp+C20h] [rbp+B20h]
  __int64 v407; // [rsp+C28h] [rbp+B28h]
  const wchar_t *v408; // [rsp+C30h] [rbp+B30h]
  int *v409; // [rsp+C38h] [rbp+B38h]
  __int64 v410; // [rsp+C40h] [rbp+B40h]
  __int64 v411; // [rsp+C48h] [rbp+B48h]
  int v412; // [rsp+C50h] [rbp+B50h]
  int v413; // [rsp+C54h] [rbp+B54h]
  const wchar_t *v414; // [rsp+C58h] [rbp+B58h]
  unsigned int *v415; // [rsp+C60h] [rbp+B60h]
  __int64 v416; // [rsp+C68h] [rbp+B68h]
  __int64 v417; // [rsp+C70h] [rbp+B70h]
  int v418; // [rsp+C78h] [rbp+B78h]
  int v419; // [rsp+C7Ch] [rbp+B7Ch]
  const wchar_t *v420; // [rsp+C80h] [rbp+B80h]
  unsigned int *v421; // [rsp+C88h] [rbp+B88h]
  __int64 v422; // [rsp+C90h] [rbp+B90h]
  __int64 v423; // [rsp+C98h] [rbp+B98h]
  int v424; // [rsp+CA0h] [rbp+BA0h]
  int v425; // [rsp+CA4h] [rbp+BA4h]
  const wchar_t *v426; // [rsp+CA8h] [rbp+BA8h]
  unsigned int *v427; // [rsp+CB0h] [rbp+BB0h]
  __int64 v428; // [rsp+CB8h] [rbp+BB8h]
  __int64 v429; // [rsp+CC0h] [rbp+BC0h]
  int v430; // [rsp+CC8h] [rbp+BC8h]
  int v431; // [rsp+CCCh] [rbp+BCCh]
  const wchar_t *v432; // [rsp+CD0h] [rbp+BD0h]
  unsigned int *v433; // [rsp+CD8h] [rbp+BD8h]
  __int64 v434; // [rsp+CE0h] [rbp+BE0h]
  __int64 v435; // [rsp+CE8h] [rbp+BE8h]
  int v436; // [rsp+CF0h] [rbp+BF0h]
  int v437; // [rsp+CF4h] [rbp+BF4h]
  const wchar_t *v438; // [rsp+CF8h] [rbp+BF8h]
  unsigned int *v439; // [rsp+D00h] [rbp+C00h]
  __int64 v440; // [rsp+D08h] [rbp+C08h]
  __int64 v441; // [rsp+D10h] [rbp+C10h]
  int v442; // [rsp+D18h] [rbp+C18h]
  int v443; // [rsp+D1Ch] [rbp+C1Ch]
  const wchar_t *v444; // [rsp+D20h] [rbp+C20h]
  unsigned int *v445; // [rsp+D28h] [rbp+C28h]
  __int64 v446; // [rsp+D30h] [rbp+C30h]
  __int64 v447; // [rsp+D38h] [rbp+C38h]
  int v448; // [rsp+D40h] [rbp+C40h]
  int v449; // [rsp+D44h] [rbp+C44h]
  const wchar_t *v450; // [rsp+D48h] [rbp+C48h]
  void *v451; // [rsp+D50h] [rbp+C50h]
  __int64 v452; // [rsp+D58h] [rbp+C58h]
  __int64 v453; // [rsp+D60h] [rbp+C60h]
  int v454; // [rsp+D68h] [rbp+C68h]
  int v455; // [rsp+D6Ch] [rbp+C6Ch]
  const wchar_t *v456; // [rsp+D70h] [rbp+C70h]
  void *v457; // [rsp+D78h] [rbp+C78h]
  __int64 v458; // [rsp+D80h] [rbp+C80h]
  __int64 v459; // [rsp+D88h] [rbp+C88h]
  int v460; // [rsp+D90h] [rbp+C90h]
  int v461; // [rsp+D94h] [rbp+C94h]
  const wchar_t *v462; // [rsp+D98h] [rbp+C98h]
  void *v463; // [rsp+DA0h] [rbp+CA0h]
  __int64 v464; // [rsp+DA8h] [rbp+CA8h]
  __int64 v465; // [rsp+DB0h] [rbp+CB0h]
  int v466; // [rsp+DB8h] [rbp+CB8h]
  int v467; // [rsp+DBCh] [rbp+CBCh]
  const wchar_t *v468; // [rsp+DC0h] [rbp+CC0h]
  unsigned int *v469; // [rsp+DC8h] [rbp+CC8h]
  __int64 v470; // [rsp+DD0h] [rbp+CD0h]
  __int64 v471; // [rsp+DD8h] [rbp+CD8h]
  int v472; // [rsp+DE0h] [rbp+CE0h]
  int v473; // [rsp+DE4h] [rbp+CE4h]
  const wchar_t *v474; // [rsp+DE8h] [rbp+CE8h]
  void *v475; // [rsp+DF0h] [rbp+CF0h]
  __int64 v476; // [rsp+DF8h] [rbp+CF8h]
  __int64 v477; // [rsp+E00h] [rbp+D00h]
  int v478; // [rsp+E08h] [rbp+D08h]
  int v479; // [rsp+E0Ch] [rbp+D0Ch]
  __int64 v480; // [rsp+E10h] [rbp+D10h] BYREF

  v2 = g_hKeyParams;
  Type = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v54 = 0;
  v52 = 0;
  v53 = 0;
  v41 = 0;
  v38 = KerbGlobalMODPDHModulusSize;
  v37 = KerbGlobalPreferWellknownMODPDHDomainParameters;
  *(_OWORD *)lpcbData = 0;
  phkResult = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DHDefaultUpgrade>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DHDefaultUpgrade>::GetImpl'::`2'::impl,
    a2);
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v3 = 1;
  v4 = 1;
  v5 = 1;
  v6 = 1;
  v82[0] = L"RetryPDC";
  v82[1] = &KerbGlobalRetryPdc;
  v82[2] = 0;
  v82[3] = 1;
  v82[4] = 0;
  v82[5] = L"ClientIpAddresses";
  v82[6] = &KerbGlobalUseClientIpAddresses;
  memset(&v82[7], 0, 24);
  v82[10] = L"TgtRenewalTime";
  v82[11] = &KerbGlobalTgtRenewalTime;
  v82[12] = 900;
  v82[13] = 0;
  v82[14] = 0;
  v82[15] = L"LogLevel";
  v82[16] = &KerbGlobalLoggingLevel;
  v82[17] = 1;
  v82[18] = 0;
  v82[19] = 0;
  v82[20] = L"AllowTgtSessionKey";
  v82[21] = &v79;
  v82[22] = 0;
  v82[23] = 0;
  v83 = 0;
  v84 = 1;
  v85 = L"MaximumTickets";
  v86 = &KerbGlobalMaxTickets;
  v87 = 2000;
  v88 = 0;
  v89 = 0;
  v90 = L"IterationCount";
  v91 = (char *)&v78 + 4;
  v92 = 4096;
  v93 = 1;
  v94 = 0;
  v95 = L"MinIterationCount";
  v96 = &v78;
  v97 = 512;
  v98 = 1;
  v99 = 0;
  v100 = 1;
  v101 = L"MaxIterationCount";
  v102 = (char *)&v78 + 8;
  v103 = 0x400000;
  v104 = 1;
  v105 = 1;
  v106 = 0;
  v107 = L"ServiceIterationCount";
  v108 = &KerbGlobalServiceIterationCount;
  v109 = 4096;
  v110 = 0;
  v111 = 0;
  v112 = L"CRLTimeoutPeriod";
  v113 = &KerbGlobalCRLRetrievalTimeout;
  v114 = 0;
  v115 = 1;
  v116 = 0;
  v117 = L"RejectExts";
  v118 = &KerbGlobalRejectGsscfxExtensions;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = L"EmitExts";
  v123 = &KerbGlobalEmitGsscfxExtensions;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = L"LogInvalidCertficate";
  v128 = &KerbGlobalLogInvalidCertificate;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = L"RequireAsChecksum";
  v133 = &KerbGlobalRequireAsChecksum;
  v134 = 0;
  v135 = 1;
  v136 = 0;
  v137 = L"ValidateKDCPACSignature";
  v138 = &KerbGlobalValidateKDCPACSignature;
  v139 = 0;
  v140 = 1;
  v141 = 0;
  v142 = L"SendPreauthForNewerETypes";
  v143 = (char *)&v78 + 12;
  v144 = 0;
  v145 = 1;
  v146 = 0;
  v147 = L"KdcValidation";
  v148 = &KerbGlobalKdcValidation;
  v149 = 1;
  v150 = 1;
  v151 = 0;
  v152 = L"StandaloneKdcValidation";
  v153 = &KerbGlobalStandaloneKdcValidation;
  v154 = 1;
  v155 = 0;
  v156 = 0;
  v157 = L"SkewTime";
  v158 = &v49;
  v159 = 5;
  v160 = 0;
  v161 = 0;
  v162 = L"FarKdcTimeout";
  v163 = &v50;
  v164 = 10;
  v165 = 0;
  v166 = 0;
  v167 = L"NearKdcTimeout";
  v168 = &v51;
  v169 = 30;
  v170 = 0;
  v171 = 0;
  v172 = L"SpnCacheTimeout";
  v173 = &v52;
  v174 = 15;
  v175 = 0;
  v176 = 0;
  v177 = L"S4UCacheTimeout";
  v178 = &v53;
  v179 = 15;
  v180 = 1;
  v181 = 0;
  v182 = L"S4UTicketLifetime";
  v183 = &v41;
  v184 = 15;
  v185 = 1;
  v186 = 0;
  v187 = L"StronglyEncryptDatagram";
  v188 = &KerbGlobalUseStrongEncryptionForDatagram;
  v189 = 1;
  v190 = 0;
  v191 = 0;
  v192 = L"RequestOptions";
  v193 = &KerbGlobalKdcOptions;
  v194 = 0x10000;
  v195 = 0;
  v196 = 0;
  v197 = L"MaxPacketSize";
  v198 = &KerbGlobalMaxDatagramSize;
  v199 = 0;
  v200 = 0;
  v201 = 0;
  v202 = L"StartupTime";
  v203 = &KerbGlobalKdcWaitTime;
  v204 = 120;
  v205 = 0;
  v206 = 0;
  v207 = L"KdcWaitTime";
  v208 = &KerbGlobalKdcCallTimeout;
  v209 = 5;
  v210 = 0;
  v211 = 0;
  v212 = L"CachedKdcConnectTimeout";
  v213 = &KerbGlobalCachedKdcConnectTimeout;
  v214 = 0;
  v215 = 1;
  v216 = 0;
  v217 = L"KdcBackoffTime";
  v218 = &KerbGlobalKdcCallBackoff;
  v219 = 5;
  v220 = 0;
  v221 = 0;
  v222 = L"KdcSendRetries";
  v223 = &KerbGlobalKdcSendRetries;
  v224 = 3;
  v225 = 0;
  v226 = 0;
  v227 = L"DefaultEncryptionType";
  v228 = &KerbGlobalDefaultPreauthEtype;
  v229 = KerbGlobalDefaultPreauthEtypeDefault;
  v230 = 0;
  v231 = 0;
  v232 = 1;
  v233 = L"MaxReferralCount";
  v234 = &KerbGlobalMaxReferralCount;
  v235 = 3;
  v236 = 0;
  v237 = 0;
  v238 = L"CacheS4UTickets";
  v239 = &KerbGlobalCacheS4UTicket;
  v240 = 1;
  v241 = 1;
  v242 = 0;
  v243 = L"UseSubjectAltName";
  v244 = &KerbGlobalUseSubjectAltName;
  v245 = 1;
  v246 = 0;
  v247 = 0;
  v248 = L"UseCachedCRLOnlyAndIgnoreRevocationUnknownErrors";
  v249 = &KerbGlobalUseCachedCRLOnlyAndIgnoreRevocationUnknownErrors;
  v250 = 0;
  v251 = 1;
  v252 = 0;
  v253 = L"MODPDHModulusSize";
  v254 = &v38;
  v255 = 2048;
  v256 = 1;
  v257 = 0;
  v258 = L"MinMODPDHModulusSize";
  v259 = &KerbGlobalMinMODPDHModulusSize;
  v260 = 1024;
  v261 = 1;
  v262 = 0;
  v263 = 1;
  v264 = L"MaxMODPDHModulusSize";
  v265 = &KerbGlobalMaxMODPDHModulusSize;
  v266 = 0x4000;
  v267 = 1;
  v268 = 0;
  v269 = L"PreferWellKnownMODPDHDomainParameters";
  v270 = &v37;
  v271 = 1;
  v272 = 1;
  v273 = 0;
  v274 = L"AcceptOnlyWellknownMODPDHDomainParameters";
  v275 = &KerbGlobalAcceptOnlyWellKnownMODPDHDomainParameters;
  v276 = 1;
  v277 = 1;
  v278 = 0;
  v279 = L"ReuseDHKey";
  v280 = &KerbGlobalAcceptReusedDHKey;
  v281 = 1;
  v282 = 0;
  v283 = 0;
  v284 = L"RequestOCSP";
  v285 = &KerbGlobalRequestOcspResponse;
  v286 = 1;
  v287 = 1;
  v288 = 0;
  v289 = L"LeafOnly";
  v290 = &KerbGlobalSendOnlyLeafCertificate;
  v291 = 1;
  v292 = 1;
  v293 = 0;
  v294 = L"NoETypeNego";
  v295 = &KerbGlobalNoETypeNeogitation;
  v296 = 0;
  v297 = 0;
  v298 = 0;
  v299 = L"UseDirectionalAddresses";
  v300 = &KerbGlobalUseDirectionalAddr;
  v301 = 0;
  v302 = 1;
  v303 = 0;
  v304 = L"KPasswdWaitTime";
  v305 = &KerbGlobalKPassCallTimeout;
  v306 = 60;
  v307 = 0;
  v308 = 0;
  v309 = L"UseForestSearch";
  v310 = &KerbGlobalUseForestSearch;
  v311 = 0;
  v312 = 1;
  v313 = 0;
  v314 = L"FsoCacheTimeout";
  v315 = &v54;
  v316 = 30;
  v317 = 0;
  v318 = 0;
  v319 = L"StrictTargetContext";
  v320 = &KerbGlobalStrictTarget;
  v321 = 0;
  v322 = 1;
  v323 = 0;
  v324 = L"RejectOldEtypesInS4uData";
  v325 = &KerbGlobalRejectOldEtypesInS4uData;
  v326 = 0;
  v327 = 1;
  v328 = 0;
  v329 = L"NoRevocationCheck";
  v330 = &KerbGlobalNoRevocationCheck;
  v331 = 0;
  v332 = 1;
  v333 = 0;
  v334 = L"TrustSuppliedProxyServer";
  v335 = &KerbGlobalTrustSuppliedProxyServer;
  v336 = 0;
  v337 = 1;
  v338 = 0;
  v339 = L"ProxyCacheExpiry";
  v340 = &KerbGlobalProxyCacheExpiry;
  v341 = 15;
  v342 = 1;
  v343 = 0;
  v344 = L"ForceProxy";
  v345 = &KerbGlobalForceProxy;
  v346 = 0;
  v347 = 1;
  v348 = 0;
  v349 = L"ProxyUsageLevel";
  v350 = &KerbGlobalKdcProxyUsageLevel;
  v351 = 0;
  v352 = 1;
  v353 = 0;
  v354 = L"RequireFast";
  v355 = &KerbGlobalRequireFast;
  v356 = 0;
  v357 = 1;
  v358 = 0;
  v359 = 1;
  v360 = L"EnableCbacAndArmor";
  v361 = &KerbGlobalEnableCbacAndArmor;
  v362 = 0;
  v363 = 1;
  v364 = 0;
  v365 = 1;
  v366 = L"AlwaysSendCompoundId";
  v367 = &KerbGlobalSendCompoundFirst;
  v368 = 0;
  v369 = 1;
  v370 = 0;
  v371 = L"TryIPSPN";
  v372 = &KerbGlobalTryIPSPN;
  v373 = 0;
  v374 = 1;
  v375 = 0;
  v376 = L"DevicePKInitEnabled";
  v377 = &KerbDevicePkinitEnabled;
  v378 = 1;
  v379 = 1;
  v380 = 0;
  v381 = 1;
  v382 = L"DevicePKInitBehavior";
  v383 = &KerbDevicePkinitBehavior;
  v384 = 0;
  v385 = 1;
  v386 = 0;
  v387 = 1;
  v388 = L"FreshnessOptimism";
  v389 = &KerbGlobalFreshnessOptimism;
  v390 = 1;
  v391 = 1;
  v392 = 0;
  v393 = L"AllowStaleDeviceAuthzData";
  v394 = &KerbGlobalAllowStaleAuthzData;
  v395 = 0;
  v396 = 0;
  v397 = 0;
  v398 = L"KeyListReqSupportOverride";
  v399 = &KerbGlobalKeyListReqSupportOverride;
  v400 = 1;
  v401 = 0;
  v402 = 0;
  v403 = L"CloudKerberosTicketRetrievalEnabled";
  v404 = &KerbGlobalCloudKerberosTicketRetrievalEnabled;
  v405 = 0;
  v406 = 1;
  v407 = 0;
  v408 = L"PKInitHashAlgorithmConfigurationEnabled";
  v409 = &v42;
  v410 = 0;
  v411 = 1;
  v412 = 0;
  v413 = 1;
  v414 = L"PKInitSHA1";
  v415 = &v43;
  v416 = 1;
  v417 = 1;
  v418 = 0;
  v419 = 1;
  v420 = L"PKInitSHA256";
  v421 = &v44;
  v422 = 1;
  v423 = 1;
  v424 = 0;
  v425 = 1;
  v426 = L"PKInitSHA384";
  v427 = &v45;
  v428 = 1;
  v429 = 1;
  v430 = 0;
  v431 = 1;
  v432 = L"PKInitSHA512";
  v433 = &v46;
  v434 = 1;
  v435 = 1;
  v436 = 0;
  v437 = 1;
  v438 = L"DelegatedMSAEnabled";
  v439 = &v47;
  v440 = 0;
  v441 = 1;
  v442 = 0;
  v443 = 1;
  v444 = L"DelegatedMSAPermissionTimer";
  v445 = &v48;
  v446 = 8;
  v447 = 0;
  v448 = 0;
  v449 = 1;
  v450 = L"PacSignatureValidationLevel";
  v451 = &KerbGlobalPacSignatureValidation;
  v452 = 0;
  v453 = 1;
  v454 = 0;
  v455 = 1;
  v456 = L"CrossDomainFilteringLevel";
  v457 = &KerbGlobalCrossDomainFilteringLevel;
  v458 = 0;
  v459 = 1;
  v460 = 0;
  v461 = 1;
  v462 = L"CrossDomainResourceGroups";
  v463 = &KerbGlobalCrossDomainResourceGroups;
  v464 = 0;
  v465 = 1;
  v466 = 0;
  v467 = 1;
  v468 = L"DeferredLogonRequiresNormalizationForAcquisition";
  v469 = &DeferredLogonRequiresNormalizationForAcquisition;
  v470 = 0;
  v471 = 1;
  v472 = 0;
  v473 = 1;
  v474 = L"PhaseOutOldS4U";
  v475 = &KerbGlobalOldS4UPhaseOut;
  v476 = 0;
  v477 = 1;
  v478 = 0;
  v479 = 1;
  cbData = 4;
  *(_DWORD *)Data = KerbInfoLevel;
  v7 = RegQueryValueExW(v2, L"KerbControlLevel", 0, &Type, Data, &cbData);
  if ( (v7 || Type != 4) && v7 != 2 )
    KerbTracerT::Log(2, "KerbGetKerbRegParams", 982, "Failed to query DebugLevel: 0x%x\n", v7);
  KerbInfoLevel = *(_DWORD *)Data;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System\\Kerberos\\Parameters",
         0,
         0x20019u,
         &phkResult);
  v10 = phkResult;
  if ( v8 && phkResult )
  {
    RegCloseKey(phkResult);
    v10 = 0;
    phkResult = 0;
  }
  GetRegistryDwords(v2, v10, v9, (struct _KERB_REG_PARAMETER *)v82);
  if ( v42 )
  {
    v3 = KerbPkinitHashAlgStateDwordToEnum(v43);
    v4 = KerbPkinitHashAlgStateDwordToEnum(v44);
    v5 = KerbPkinitHashAlgStateDwordToEnum(v45);
    v6 = KerbPkinitHashAlgStateDwordToEnum(v46);
  }
  v63[0] = "2.16.840.1.101.3.4.2.3";
  v63[1] = 22;
  v64 = v6;
  v65 = 3;
  v66 = "2.16.840.1.101.3.4.2.2";
  v67 = 22;
  v68 = v5;
  v69 = 3;
  v70 = "2.16.840.1.101.3.4.2.1";
  v71 = 22;
  v72 = v4;
  v73 = 3;
  v74 = "1.3.14.3.2.26";
  v75 = 13;
  v76 = v3;
  v77 = 3;
  *(_QWORD *)&v55 = 0;
  utl::_SharedAlloc<KerbDigestAlgorithmPolicy,utl::allocator<int>,0>::_Create<utl::shared_ptr<KerbDigestAlgorithmPolicy>,>(
    &v55,
    &v62);
  utl::_SharedAlloc<KerbDigestAlgorithmPolicy,utl::allocator<int>,0>::~_SharedAlloc<KerbDigestAlgorithmPolicy,utl::allocator<int>,0>(&v55);
  v55 = v62;
  utl::atomic<utl::shared_ptr<KerbDigestAlgorithmPolicy const>>::store(v11, &v55);
  KerbConfigureHashAlgorithmPolicy(v12, (struct PkinitAddAlgorithmParam *)v63);
  KerbGetKerbSearchForests(phkResult);
  KerbDmsaPolicy::UpdatePolicy(phkResult, v48, v47);
  if ( phkResult )
  {
    KerbReadUPNNameHints(phkResult);
    RegCloseKey(phkResult);
  }
  v13 = v41;
  if ( v41 < 5 )
  {
    v13 = 5;
    v41 = 5;
  }
  v14.QuadPart = 600000000LL * v49;
  KerbGlobalSkewTime = v14;
  KerbGlobalFarKdcTimeout = (unsigned int)(60000 * v50);
  KerbGlobalNearKdcTimeout = (unsigned int)(60000 * v51);
  KerbGlobalSpnCacheTimeout.QuadPart = 600000000LL * v52;
  KerbGlobalS4UCacheTimeout.QuadPart = 600000000LL * v53;
  KerbGlobalS4UTicketLifetime.QuadPart = 600000000LL * v13;
  KerbFsoBindingCacheTimeout.QuadPart = 600000000LL * v54;
  if ( Authenticators[1].TableRoot != (PRTL_SPLAY_LINKS)v14.QuadPart )
    CAuthenticatorList::SetMaxAge((CAuthenticatorList *)(600000000LL * v54), v14);
  if ( (unsigned int)KerbGlobalMaxDatagramSize >= 0x10000 )
    LODWORD(KerbGlobalMaxDatagramSize) = 0x10000;
  if ( !KerbGlobalServiceIterationCount )
    KerbGlobalServiceIterationCount = 1;
  v15 = KerbGlobalMaxMODPDHModulusSize;
  if ( KerbGlobalMaxMODPDHModulusSize < KerbGlobalMinMODPDHModulusSize )
  {
    v15 = KerbGlobalMinMODPDHModulusSize;
    KerbGlobalMaxMODPDHModulusSize = KerbGlobalMinMODPDHModulusSize;
  }
  v16 = KerbGlobalMODPDHModulusSize;
  if ( KerbGlobalMODPDHModulusSize < KerbGlobalMinMODPDHModulusSize )
  {
    v16 = KerbGlobalMinMODPDHModulusSize;
    KerbGlobalMODPDHModulusSize = KerbGlobalMinMODPDHModulusSize;
  }
  if ( v16 > v15 )
    KerbGlobalMODPDHModulusSize = v15;
  cbData = 4;
  if ( !RegQueryValueExW(v2, L"MaxTokenSize", 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
  {
    if ( (unsigned int)(*(_DWORD *)Data - 1200) <= 0x181F0 )
      goto LABEL_32;
    KerbTracerT::Log(
      1,
      "KerbGetKerbRegParams",
      1120,
      "KerbGetKerbRegParams MaxToken out of range %d\n",
      *(_DWORD *)Data);
  }
  *(_DWORD *)Data = 48000;
LABEL_32:
  WinSqmSetDWORD(0, 6548);
  if ( KerbGlobalMaxTokenSize != *(_DWORD *)Data )
  {
    if ( KerbGlobalMaxTokenSizeInitialized )
    {
      KerbTracerT::Log(
        2,
        "KerbGetKerbRegParams",
        1135,
        "KerbGetKerbRegParams updating old maxtoken size %d to %d\n",
        KerbGlobalMaxTokenSize,
        *(_DWORD *)Data);
      KerbGlobalMaxTokenSize = *(_DWORD *)Data;
      LsaIUpdateKerbMaxTokenSize();
    }
    else
    {
      KerbGlobalMaxTokenSize = *(_DWORD *)Data;
    }
  }
  KerbGlobalMaxTokenSizeInitialized = 1;
  if ( v37 != KerbGlobalPreferWellknownMODPDHDomainParameters
    || v38 != KerbGlobalMODPDHModulusSize
    || !KerbGlobalDHParametersInitialized )
  {
    RtlEnterCriticalSection(&KerbGlobalDHParametersLock);
    if ( KerbGlobalDHAvailable )
    {
      KerbFreeDHParameters((struct _CERT_X942_DH_PARAMETERS *)&KerbGlobalDHParameters);
      if ( KerbGlobalDHAlgorithm.Parameters.pbData )
      {
        KerbFree(KerbGlobalDHAlgorithm.Parameters.pbData);
        KerbGlobalDHAlgorithm.Parameters.pbData = 0;
      }
      if ( !KerbGenerateDHAlgorithmId(v38, v37, v17, &KerbGlobalDHAlgorithm) )
      {
        LastError = GetLastError();
        v19 = "true";
        if ( !v37 )
          v19 = "false";
        KerbTracerT::Log(
          1,
          "KerbGetKerbRegParams",
          1171,
          "failed to genrate DH domain parameters for modulus size %d, prefer wellknown parameters %s: last error %#x\n",
          v38,
          v19,
          LastError);
        goto LABEL_50;
      }
      v20 = "true";
      if ( !v37 )
        v20 = "false";
      KerbTracerT::Log(
        2,
        "KerbGetKerbRegParams",
        1179,
        "updating DH domain parameters for modulus size %d, prefer wellknown parameters: %s\n",
        v38,
        v20);
    }
    KerbGlobalPreferWellknownMODPDHDomainParameters = v37;
    KerbGlobalMODPDHModulusSize = v38;
LABEL_50:
    RtlLeaveCriticalSection(&KerbGlobalDHParametersLock);
  }
  KerbGlobalDHParametersInitialized = 1;
  v21 = RegQueryValueExW(v2, L"DHDomainParameters", 0, &Type, lpcbData[1], (LPDWORD)lpcbData);
  if ( v21 == 2 )
  {
    if ( *((_QWORD *)&xmmword_1801454B0 + 1) )
    {
      KerbFree(*((_QWORD *)&xmmword_1801454B0 + 1));
      KerbTracerT::Log(28, "KerbGetKerbRegParams", 1216, "resetting DH parameters\n");
      KerbAddWellknownDomainParameters(0x400u, 0, 0);
    }
    xmmword_1801454B0 = 0;
  }
  else if ( !v21 )
  {
    v22 = (BYTE *)MIDL_user_allocate(LODWORD(lpcbData[0]));
    lpcbData[1] = v22;
    if ( v22 )
    {
      v23 = RegQueryValueExW(v2, L"DHDomainParameters", 0, &Type, v22, (LPDWORD)lpcbData);
      if ( v23 )
      {
        KerbTracerT::Log(1, "KerbGetKerbRegParams", 1246, "Query wellknown DH failed with %#x\n", v23);
      }
      else if ( Type == 3 )
      {
        v24 = *((_QWORD *)&xmmword_1801454B0 + 1);
        if ( (_DWORD)xmmword_1801454B0 != LODWORD(lpcbData[0])
          || (v25 = 0, memcmp_0(lpcbData[1], *((const void **)&xmmword_1801454B0 + 1), LODWORD(lpcbData[0]))) )
        {
          v25 = 1;
        }
        if ( v24 )
          KerbFree(v24);
        xmmword_1801454B0 = *(_OWORD *)lpcbData;
        if ( v25 )
        {
          KerbTracerT::Log(28, "KerbGetKerbRegParams", 1267, "Updating DH parameters\n");
          KerbAddWellknownDomainParameters(KerbGlobalMinMODPDHModulusSize, lpcbData[1], (unsigned int)lpcbData[0]);
        }
      }
    }
    else
    {
      KerbTracerT::Log(1, "KerbGetKerbRegParams", 1231, "KerbGetKerbRegParams no memory");
    }
  }
  v26 = v82;
  do
  {
    if ( *((_DWORD *)v26 + 9) == 1
      && (unsigned int)dword_180140048 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180140048, 0x400000000000LL) )
    {
      v58 = KerbGlobalIsRunningIsolated;
      v59 = *(_DWORD *)v26[1];
      v60 = *((_DWORD *)v26 + 8);
      v61 = *((_DWORD *)v26 + 7) != 0;
      *(_QWORD *)&v62 = *v26;
      *(_QWORD *)&v55 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v59,
        (unsigned int)byte_18012B6C9,
        v27,
        (unsigned int)&v55,
        (__int64)&v62,
        (__int64)&v61,
        (__int64)&v60,
        (__int64)&v59,
        (__int64)&v58);
    }
    v26 += 5;
  }
  while ( v26 != &v480 );
  if ( (*(int (__fastcall **)(struct KerbCredIsoApi *, __int128 *, __int128 *))(*(_QWORD *)LocalhostKerbCredIsoObj::IsoObj
                                                                              + 184LL))(
         LocalhostKerbCredIsoObj::IsoObj,
         &v78,
         &v80) >= 0 )
  {
    KerbGlobalSendPreauthForNewerETypes = HIDWORD(v80);
    KerbGlobalAllowTgtSessionKey = v81;
  }
  else
  {
    KerbTracerT::Log(1, "KerbGetKerbRegParams", 1300, "KerbGetKerbRegParams failed to invoke UpdateSharedConfiguration");
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CaCGVelocity>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CaCGVelocity>::GetImpl'::`2'::impl) )
    goto LABEL_85;
  LocalCipherPolicy = GetLocalCipherPolicy();
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)LocalCipherPolicy + 32LL))(LocalCipherPolicy, &v55);
  if ( v56 < 0 )
  {
    KerbTracerT::Log(1, "KerbGetKerbRegParams", 1315, "MarshalCipherPolicies failed with status: 0x%x\n", v56);
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v55);
    return;
  }
  updated = (*(__int64 (__fastcall **)(struct KerbCredIsoApi *, _QWORD, _QWORD))(*(_QWORD *)LocalhostKerbCredIsoObj::IsoObj
                                                                               + 192LL))(
              LocalhostKerbCredIsoObj::IsoObj,
              *((_QWORD *)&v55 + 1),
              (unsigned int)v55);
  if ( updated < 0 )
  {
    v31 = "UpdateKerb3961SharedConfiguration failed with status: 0x%X\n";
    v32 = 1322;
LABEL_83:
    LODWORD(lpData) = updated;
    KerbTracerT::Log(1, "KerbGetKerbRegParams", v32, v31, lpData);
    goto LABEL_84;
  }
  updated = KerbClient3961UpdateSharedConfiguration(*((unsigned __int8 **)&v55 + 1), v55);
  if ( updated < 0 )
  {
    v31 = "KerbClient3961UpdateSharedConfiguration failed with status: 0x%X\n";
    v32 = 1330;
    goto LABEL_83;
  }
LABEL_84:
  Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v55);
LABEL_85:
  if ( Ntlmless::Kerberos::IsEnabled(v28) )
    KerbTelemetry::ReportNtlmlessConfiguration(v33);
}

```

## disassembly

```asm
0x18007b8ac  push    rbp
0x18007b8ae  push    rbx
0x18007b8af  push    rsi
0x18007b8b0  push    rdi
0x18007b8b1  push    r12
0x18007b8b3  push    r13
0x18007b8b5  push    r14
0x18007b8b7  push    r15
0x18007b8b9  lea     rbp, [rsp-0D28h]
0x18007b8c1  sub     rsp, 0E28h
0x18007b8c8  mov     rax, cs:__security_cookie
0x18007b8cf  xor     rax, rsp
0x18007b8d2  mov     [rbp+0D60h+var_50], rax
0x18007b8d9  mov     rbx, cs:?g_hKeyParams@@3PEAUHKEY__@@EA; HKEY__ * g_hKeyParams
0x18007b8e0  xor     r12d, r12d
0x18007b8e3  mov     [rsp+0E60h+Type], r12d
0x18007b8e8  mov     dword ptr [rsp+0E60h+Data], r12d
0x18007b8ed  mov     [rsp+0E60h+cbData], r12d
0x18007b8f2  mov     [rbp+0D60h+var_DD0], r12d
0x18007b8f6  mov     [rbp+0D60h+var_DCC], r12d
0x18007b8fa  mov     [rbp+0D60h+var_DC8], r12d
0x18007b8fe  mov     [rbp+0D60h+var_DBC], r12d
0x18007b902  mov     [rbp+0D60h+var_DC4], r12d
0x18007b906  mov     [rbp+0D60h+var_DC0], r12d
0x18007b90a  mov     [rsp+0E60h+var_DF0], r12d
0x18007b90f  mov     eax, cs:?KerbGlobalMODPDHModulusSize@@3KA; ulong KerbGlobalMODPDHModulusSize
0x18007b915  mov     [rsp+0E60h+var_E04], eax
0x18007b919  mov     eax, cs:?KerbGlobalPreferWellknownMODPDHDomainParameters@@3KA; ulong KerbGlobalPreferWellknownMODPDHDomainParameters
0x18007b91f  mov     [rsp+0E60h+var_E08], eax
0x18007b923  xorps   xmm0, xmm0
0x18007b926  movups  xmmword ptr [rbp+0D60h+var_D90], xmm0
0x18007b92a  mov     [rsp+0E60h+phkResult], r12
0x18007b92f  xorps   xmm1, xmm1
0x18007b932  xor     eax, eax
0x18007b934  movups  [rbp+0D60h+var_D00], xmm1
0x18007b938  mov     [rbp+0D60h+var_CF0], eax
0x18007b93b  movups  [rbp+0D60h+var_CE8], xmm0
0x18007b93f  mov     [rbp+0D60h+var_CD8], eax
0x18007b945  lea     r13d, [r12+1]
0x18007b94a  mov     dl, r13b
0x18007b94d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DHDefaultUpgrade@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DHDefaultUpgrade@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DHDefaultUpgrade> `wil::Feature<__WilFeatureTraits_Feature_DHDefaultUpgrade>::GetImpl(void)'::`2'::impl
0x18007b954  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DHDefaultUpgrade@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DHDefaultUpgrade>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007b959  mov     [rsp+0E60h+var_DEC], r12d
0x18007b95e  mov     [rsp+0E60h+var_DE8], r12d
0x18007b963  mov     [rsp+0E60h+var_DE4], r12d
0x18007b968  mov     [rbp+0D60h+var_DE0], r12d
0x18007b96c  mov     [rbp+0D60h+var_DDC], r12d
0x18007b970  mov     [rbp+0D60h+var_DD8], r12d
0x18007b974  mov     [rbp+0D60h+var_DD4], r12d
0x18007b978  mov     edi, r13d
0x18007b97b  mov     esi, r13d
0x18007b97e  mov     r14d, r13d
0x18007b981  mov     r15d, r13d
0x18007b984  lea     rax, aRetrypdc; "RetryPDC"
0x18007b98b  mov     [rbp+0D60h+var_CD0], rax
0x18007b992  lea     rax, ?KerbGlobalRetryPdc@@3KA; ulong KerbGlobalRetryPdc
0x18007b999  mov     [rbp+0D60h+var_CC8], rax
0x18007b9a0  mov     [rbp+0D60h+var_CC0], r12
0x18007b9a7  mov     [rbp+0D60h+var_CB8], rsi
0x18007b9ae  mov     [rbp+0D60h+var_CB0], r12
0x18007b9b5  lea     rax, aClientipaddres; "ClientIpAddresses"
0x18007b9bc  mov     [rbp+0D60h+var_CA8], rax
0x18007b9c3  lea     rax, ?KerbGlobalUseClientIpAddresses@@3KA; ulong KerbGlobalUseClientIpAddresses
0x18007b9ca  mov     [rbp+0D60h+var_CA0], rax
0x18007b9d1  mov     [rbp+0D60h+var_C98], r12
0x18007b9d8  mov     [rbp+0D60h+var_C90], r12
0x18007b9df  mov     [rbp+0D60h+var_C88], r12
0x18007b9e6  lea     rax, aTgtrenewaltime; "TgtRenewalTime"
0x18007b9ed  mov     [rbp+0D60h+var_C80], rax
0x18007b9f4  lea     rax, ?KerbGlobalTgtRenewalTime@@3KA; ulong KerbGlobalTgtRenewalTime
0x18007b9fb  mov     [rbp+0D60h+var_C78], rax
0x18007ba02  mov     [rbp+0D60h+var_C70], 384h
0x18007ba0d  mov     [rbp+0D60h+var_C68], r12
0x18007ba14  mov     [rbp+0D60h+var_C60], r12
0x18007ba1b  lea     rax, aLoglevel; "LogLevel"
0x18007ba22  mov     [rbp+0D60h+var_C58], rax
0x18007ba29  lea     rax, ?KerbGlobalLoggingLevel@@3KA; ulong KerbGlobalLoggingLevel
0x18007ba30  mov     [rbp+0D60h+var_C50], rax
0x18007ba37  mov     [rbp+0D60h+var_C48], rsi
0x18007ba3e  mov     [rbp+0D60h+var_C40], r12
0x18007ba45  mov     [rbp+0D60h+var_C38], r12
0x18007ba4c  lea     rax, aAllowtgtsessio; "AllowTgtSessionKey"
0x18007ba53  mov     [rbp+0D60h+var_C30], rax
0x18007ba5a  lea     rax, [rbp+0D60h+var_CF0]
0x18007ba5e  mov     [rbp+0D60h+var_C28], rax
0x18007ba65  mov     [rbp+0D60h+var_C20], r12
0x18007ba6c  mov     [rbp+0D60h+var_C18], r12
0x18007ba73  mov     [rbp+0D60h+var_C10], r12d
0x18007ba7a  mov     [rbp+0D60h+var_C0C], r13d
0x18007ba81  lea     rax, aMaximumtickets; "MaximumTickets"
0x18007ba88  mov     [rbp+0D60h+var_C08], rax
0x18007ba8f  lea     rax, ?KerbGlobalMaxTickets@@3KA; ulong KerbGlobalMaxTickets
0x18007ba96  mov     [rbp+0D60h+var_C00], rax
0x18007ba9d  mov     [rbp+0D60h+var_BF8], 7D0h
0x18007baa8  mov     [rbp+0D60h+var_BF0], r12
0x18007baaf  mov     [rbp+0D60h+var_BE8], r12
0x18007bab6  lea     rax, aIterationcount; "IterationCount"
0x18007babd  mov     [rbp+0D60h+var_BE0], rax
0x18007bac4  lea     rax, [rbp+0D60h+var_D00+4]
0x18007bac8  mov     [rbp+0D60h+var_BD8], rax
0x18007bacf  mov     [rbp+0D60h+var_BD0], 1000h
0x18007bada  mov     [rbp+0D60h+var_BC8], rsi
0x18007bae1  mov     [rbp+0D60h+var_BC0], r12
0x18007bae8  lea     rax, aMiniterationco; "MinIterationCount"
0x18007baef  mov     [rbp+0D60h+var_BB8], rax
0x18007baf6  lea     rax, [rbp+0D60h+var_D00]
0x18007bafa  mov     [rbp+0D60h+var_BB0], rax
0x18007bb01  mov     [rbp+0D60h+var_BA8], 200h
0x18007bb0c  mov     [rbp+0D60h+var_BA0], rsi
0x18007bb13  mov     [rbp+0D60h+var_B98], r12d
0x18007bb1a  mov     [rbp+0D60h+var_B94], r13d
0x18007bb21  lea     rax, aMaxiterationco; "MaxIterationCount"
0x18007bb28  mov     [rbp+0D60h+var_B90], rax
0x18007bb2f  lea     rax, [rbp+0D60h+var_D00+8]
0x18007bb33  mov     [rbp+0D60h+var_B88], rax
0x18007bb3a  mov     [rbp+0D60h+var_B80], 400000h
0x18007bb44  mov     [rbp+0D60h+var_B7C], r13d
0x18007bb4b  mov     [rbp+0D60h+var_B78], rsi
0x18007bb52  mov     [rbp+0D60h+var_B70], r12
0x18007bb59  lea     rax, aServiceiterati; "ServiceIterationCount"
0x18007bb60  mov     [rbp+0D60h+var_B68], rax
0x18007bb67  lea     rax, ?KerbGlobalServiceIterationCount@@3KA; ulong KerbGlobalServiceIterationCount
0x18007bb6e  mov     [rbp+0D60h+var_B60], rax
0x18007bb75  mov     [rbp+0D60h+var_B58], 1000h
0x18007bb80  mov     [rbp+0D60h+var_B50], r12
0x18007bb87  mov     [rbp+0D60h+var_B48], r12
0x18007bb8e  lea     rax, aCrltimeoutperi; "CRLTimeoutPeriod"
0x18007bb95  mov     [rbp+0D60h+var_B40], rax
0x18007bb9c  lea     rax, ?KerbGlobalCRLRetrievalTimeout@@3JA; long KerbGlobalCRLRetrievalTimeout
0x18007bba3  mov     [rbp+0D60h+var_B38], rax
0x18007bbaa  mov     [rbp+0D60h+var_B30], r12
0x18007bbb1  mov     [rbp+0D60h+var_B28], rsi
0x18007bbb8  mov     [rbp+0D60h+var_B20], r12
0x18007bbbf  lea     rax, aRejectexts; "RejectExts"
0x18007bbc6  mov     [rbp+0D60h+var_B18], rax
0x18007bbcd  lea     rax, ?KerbGlobalRejectGsscfxExtensions@@3KA; ulong KerbGlobalRejectGsscfxExtensions
0x18007bbd4  mov     [rbp+0D60h+var_B10], rax
0x18007bbdb  mov     [rbp+0D60h+var_B08], r12
0x18007bbe2  mov     [rbp+0D60h+var_B00], r12
0x18007bbe9  mov     [rbp+0D60h+var_AF8], r12
0x18007bbf0  lea     rax, aEmitexts; "EmitExts"
0x18007bbf7  mov     [rbp+0D60h+var_AF0], rax
0x18007bbfe  lea     rax, ?KerbGlobalEmitGsscfxExtensions@@3KA; ulong KerbGlobalEmitGsscfxExtensions
0x18007bc05  mov     [rbp+0D60h+var_AE8], rax
0x18007bc0c  mov     [rbp+0D60h+var_AE0], r12
0x18007bc13  mov     [rbp+0D60h+var_AD8], r12
0x18007bc1a  mov     [rbp+0D60h+var_AD0], r12
0x18007bc21  lea     rax, aLoginvalidcert; "LogInvalidCertficate"
0x18007bc28  mov     [rbp+0D60h+var_AC8], rax
0x18007bc2f  lea     rax, ?KerbGlobalLogInvalidCertificate@@3KA; ulong KerbGlobalLogInvalidCertificate
0x18007bc36  mov     [rbp+0D60h+var_AC0], rax
0x18007bc3d  mov     [rbp+0D60h+var_AB8], r12
0x18007bc44  mov     [rbp+0D60h+var_AB0], r12
0x18007bc4b  mov     [rbp+0D60h+var_AA8], r12
0x18007bc52  lea     rax, aRequireascheck; "RequireAsChecksum"
0x18007bc59  mov     [rbp+0D60h+var_AA0], rax
0x18007bc60  lea     rax, ?KerbGlobalRequireAsChecksum@@3KA; ulong KerbGlobalRequireAsChecksum
0x18007bc67  mov     [rbp+0D60h+var_A98], rax
0x18007bc6e  mov     [rbp+0D60h+var_A90], r12
0x18007bc75  mov     [rbp+0D60h+var_A88], rsi
0x18007bc7c  mov     [rbp+0D60h+var_A80], r12
0x18007bc83  lea     rax, aValidatekdcpac; "ValidateKDCPACSignature"
0x18007bc8a  mov     [rbp+0D60h+var_A78], rax
0x18007bc91  lea     rax, ?KerbGlobalValidateKDCPACSignature@@3KA; ulong KerbGlobalValidateKDCPACSignature
0x18007bc98  mov     [rbp+0D60h+var_A70], rax
0x18007bc9f  mov     [rbp+0D60h+var_A68], r12
0x18007bca6  mov     [rbp+0D60h+var_A60], rsi
0x18007bcad  mov     [rbp+0D60h+var_A58], r12
0x18007bcb4  lea     rax, aSendpreauthfor; "SendPreauthForNewerETypes"
0x18007bcbb  mov     [rbp+0D60h+var_A50], rax
0x18007bcc2  lea     rax, [rbp+0D60h+var_D00+0Ch]
0x18007bcc6  mov     [rbp+0D60h+var_A48], rax
0x18007bccd  mov     [rbp+0D60h+var_A40], r12
0x18007bcd4  mov     [rbp+0D60h+var_A38], rsi
0x18007bcdb  mov     [rbp+0D60h+var_A30], r12
0x18007bce2  lea     rax, aKdcvalidation; "KdcValidation"
0x18007bce9  mov     [rbp+0D60h+var_A28], rax
0x18007bcf0  lea     rax, ?KerbGlobalKdcValidation@@3KA; ulong KerbGlobalKdcValidation
0x18007bcf7  mov     [rbp+0D60h+var_A20], rax
0x18007bcfe  mov     [rbp+0D60h+var_A18], rsi
0x18007bd05  mov     [rbp+0D60h+var_A10], rsi
0x18007bd0c  mov     [rbp+0D60h+var_A08], r12
0x18007bd13  lea     rax, aStandalonekdcv; "StandaloneKdcValidation"
0x18007bd1a  mov     [rbp+0D60h+var_A00], rax
0x18007bd21  lea     rax, ?KerbGlobalStandaloneKdcValidation@@3KA; ulong KerbGlobalStandaloneKdcValidation
0x18007bd28  mov     [rbp+0D60h+var_9F8], rax
0x18007bd2f  mov     [rbp+0D60h+var_9F0], rsi
0x18007bd36  mov     [rbp+0D60h+var_9E8], r12
0x18007bd3d  mov     [rbp+0D60h+var_9E0], r12
0x18007bd44  lea     rax, aSkewtime; "SkewTime"
0x18007bd4b  mov     [rbp+0D60h+var_9D8], rax
0x18007bd52  lea     rax, [rbp+0D60h+var_DD0]
0x18007bd56  mov     [rbp+0D60h+var_9D0], rax
0x18007bd5d  mov     [rbp+0D60h+var_9C8], 5
0x18007bd68  mov     [rbp+0D60h+var_9C0], r12
0x18007bd6f  mov     [rbp+0D60h+var_9B8], r12
0x18007bd76  lea     rax, aFarkdctimeout; "FarKdcTimeout"
0x18007bd7d  mov     [rbp+0D60h+var_9B0], rax
0x18007bd84  lea     rax, [rbp+0D60h+var_DCC]
0x18007bd88  mov     [rbp+0D60h+var_9A8], rax
0x18007bd8f  mov     [rbp+0D60h+var_9A0], 0Ah
0x18007bd9a  mov     [rbp+0D60h+var_998], r12
0x18007bda1  mov     [rbp+0D60h+var_990], r12
0x18007bda8  lea     rax, aNearkdctimeout; "NearKdcTimeout"
0x18007bdaf  mov     [rbp+0D60h+var_988], rax
0x18007bdb6  lea     rax, [rbp+0D60h+var_DC8]
0x18007bdba  mov     [rbp+0D60h+var_980], rax
0x18007bdc1  mov     [rbp+0D60h+var_978], 1Eh
0x18007bdcc  mov     [rbp+0D60h+var_970], r12
0x18007bdd3  mov     [rbp+0D60h+var_968], r12
0x18007bdda  lea     rax, aSpncachetimeou; "SpnCacheTimeout"
0x18007bde1  mov     [rbp+0D60h+var_960], rax
0x18007bde8  lea     rax, [rbp+0D60h+var_DC4]
0x18007bdec  mov     [rbp+0D60h+var_958], rax
0x18007bdf3  mov     [rbp+0D60h+var_950], 0Fh
0x18007bdfe  mov     [rbp+0D60h+var_948], r12
0x18007be05  mov     [rbp+0D60h+var_940], r12
0x18007be0c  lea     rax, aS4ucachetimeou; "S4UCacheTimeout"
0x18007be13  mov     [rbp+0D60h+var_938], rax
0x18007be1a  lea     rax, [rbp+0D60h+var_DC0]
0x18007be1e  mov     [rbp+0D60h+var_930], rax
0x18007be25  mov     [rbp+0D60h+var_928], 0Fh
0x18007be30  mov     [rbp+0D60h+var_920], rsi
0x18007be37  mov     [rbp+0D60h+var_918], r12
0x18007be3e  lea     rax, aS4uticketlifet; "S4UTicketLifetime"
0x18007be45  mov     [rbp+0D60h+var_910], rax
0x18007be4c  lea     rax, [rsp+0E60h+var_DF0]
0x18007be51  mov     [rbp+0D60h+var_908], rax
0x18007be58  mov     [rbp+0D60h+var_900], 0Fh
0x18007be63  mov     [rbp+0D60h+var_8F8], rsi
0x18007be6a  mov     [rbp+0D60h+var_8F0], r12
0x18007be71  lea     rax, aStronglyencryp; "StronglyEncryptDatagram"
0x18007be78  mov     [rbp+0D60h+var_8E8], rax
0x18007be7f  lea     rax, ?KerbGlobalUseStrongEncryptionForDatagram@@3KA; ulong KerbGlobalUseStrongEncryptionForDatagram
0x18007be86  mov     [rbp+0D60h+var_8E0], rax
0x18007be8d  mov     [rbp+0D60h+var_8D8], rsi
0x18007be94  mov     [rbp+0D60h+var_8D0], r12
0x18007be9b  mov     [rbp+0D60h+var_8C8], r12
0x18007bea2  lea     rax, aRequestoptions; "RequestOptions"
0x18007bea9  mov     [rbp+0D60h+var_8C0], rax
0x18007beb0  lea     rax, ?KerbGlobalKdcOptions@@3KA; ulong KerbGlobalKdcOptions
0x18007beb7  mov     [rbp+0D60h+var_8B8], rax
0x18007bebe  mov     [rbp+0D60h+var_8B0], 10000h
0x18007bec9  mov     [rbp+0D60h+var_8A8], r12
0x18007bed0  mov     [rbp+0D60h+var_8A0], r12
0x18007bed7  lea     rax, aMaxpacketsize; "MaxPacketSize"
0x18007bede  mov     [rbp+0D60h+var_898], rax
0x18007bee5  lea     rax, ?KerbGlobalMaxDatagramSize@@3KA; ulong KerbGlobalMaxDatagramSize
0x18007beec  mov     [rbp+0D60h+var_890], rax
0x18007bef3  mov     [rbp+0D60h+var_888], r12
0x18007befa  mov     [rbp+0D60h+var_880], r12
0x18007bf01  mov     [rbp+0D60h+var_878], r12
0x18007bf08  lea     rax, aStartuptime; "StartupTime"
0x18007bf0f  mov     [rbp+0D60h+var_870], rax
0x18007bf16  lea     rax, ?KerbGlobalKdcWaitTime@@3KA; ulong KerbGlobalKdcWaitTime
0x18007bf1d  mov     [rbp+0D60h+var_868], rax
0x18007bf24  mov     [rbp+0D60h+var_860], 78h ; 'x'
0x18007bf2f  mov     [rbp+0D60h+var_858], r12
0x18007bf36  mov     [rbp+0D60h+var_850], r12
0x18007bf3d  lea     rax, aKdcwaittime; "KdcWaitTime"
0x18007bf44  mov     [rbp+0D60h+var_848], rax
0x18007bf4b  lea     rax, ?KerbGlobalKdcCallTimeout@@3KA; ulong KerbGlobalKdcCallTimeout
0x18007bf52  mov     [rbp+0D60h+var_840], rax
0x18007bf59  mov     [rbp+0D60h+var_838], 5
0x18007bf64  mov     [rbp+0D60h+var_830], r12
0x18007bf6b  mov     [rbp+0D60h+var_828], r12
0x18007bf72  lea     rax, aCachedkdcconne; "CachedKdcConnectTimeout"
0x18007bf79  mov     [rbp+0D60h+var_820], rax
0x18007bf80  lea     rax, ?KerbGlobalCachedKdcConnectTimeout@@3KA; ulong KerbGlobalCachedKdcConnectTimeout
0x18007bf87  mov     [rbp+0D60h+var_818], rax
0x18007bf8e  mov     [rbp+0D60h+var_810], r12
0x18007bf95  mov     [rbp+0D60h+var_808], rsi
0x18007bf9c  mov     [rbp+0D60h+var_800], r12
0x18007bfa3  lea     rax, aKdcbackofftime; "KdcBackoffTime"
0x18007bfaa  mov     [rbp+0D60h+var_7F8], rax
0x18007bfb1  lea     rax, ?KerbGlobalKdcCallBackoff@@3KA; ulong KerbGlobalKdcCallBackoff
0x18007bfb8  mov     [rbp+0D60h+var_7F0], rax
0x18007bfbf  mov     [rbp+0D60h+var_7E8], 5
0x18007bfca  mov     [rbp+0D60h+var_7E0], r12
0x18007bfd1  mov     [rbp+0D60h+var_7D8], r12
0x18007bfd8  lea     rax, aKdcsendretries; "KdcSendRetries"
0x18007bfdf  mov     [rbp+0D60h+var_7D0], rax
0x18007bfe6  lea     rax, ?KerbGlobalKdcSendRetries@@3KA; ulong KerbGlobalKdcSendRetries
0x18007bfed  mov     [rbp+0D60h+var_7C8], rax
0x18007bff4  mov     [rbp+0D60h+var_7C0], 3
0x18007bfff  mov     [rbp+0D60h+var_7B8], r12
0x18007c006  mov     [rbp+0D60h+var_7B0], r12
0x18007c00d  lea     rax, aDefaultencrypt; "DefaultEncryptionType"
0x18007c014  mov     [rbp+0D60h+var_7A8], rax
0x18007c01b  lea     rax, ?KerbGlobalDefaultPreauthEtype@@3KA; ulong KerbGlobalDefaultPreauthEtype
0x18007c022  mov     [rbp+0D60h+var_7A0], rax
0x18007c029  mov     eax, cs:?KerbGlobalDefaultPreauthEtypeDefault@@3KA; ulong KerbGlobalDefaultPreauthEtypeDefault
0x18007c02f  mov     [rbp+0D60h+var_798], eax
0x18007c035  mov     [rbp+0D60h+var_794], r12
0x18007c03c  mov     [rbp+0D60h+var_78C], r12
0x18007c043  mov     [rbp+0D60h+var_784], r13d
0x18007c04a  lea     rax, aMaxreferralcou; "MaxReferralCount"
0x18007c051  mov     [rbp+0D60h+var_780], rax
0x18007c058  lea     rax, ?KerbGlobalMaxReferralCount@@3KA; ulong KerbGlobalMaxReferralCount
0x18007c05f  mov     [rbp+0D60h+var_778], rax
  ... truncated ...
```
