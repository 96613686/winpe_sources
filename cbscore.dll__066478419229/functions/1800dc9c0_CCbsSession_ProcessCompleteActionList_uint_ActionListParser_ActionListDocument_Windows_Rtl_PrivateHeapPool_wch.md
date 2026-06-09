# CCbsSession::ProcessCompleteActionList(uint,ActionListParser::ActionListDocument *,Windows::Rtl::PrivateHeapPool &,wchar_t const *,bool)

- ea: `0x1800dc9c0`
- end: `0x1800e0ef1`
- name: `?ProcessCompleteActionList@CCbsSession@@AEAAJIPEAUActionListDocument@ActionListParser@@AEAVPrivateHeapPool@Rtl@Windows@@PEB_W_N@Z`
- size: `17713`
- prototype: `__int64 __usercall@<rax>(CCbsSession *__hidden this@<rcx>, unsigned int@<edx>, struct ActionListParser::ActionListDocument *@<r8>, struct Windows::Rtl::PrivateHeapPool *@<r9>, const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `89`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801cb8a0`

## callees

- `0x18000e780`
- `0x180010b60`
- `0x180010cc0`
- `0x180011a14`
- `0x180012fe4`
- `0x180013018`
- `0x1800130e0`
- `0x180013250`
- `0x1800132a4`
- `0x1800133a4`
- `0x1800138b8`
- `0x180015420`
- `0x1800158d0`
- `0x180018124`
- `0x18001837c`
- `0x1800194bc`
- `0x180019c10`
- `0x180023ca8`
- `0x18002573c`
- `0x1800261e0`
- `0x180028e24`
- `0x18002a2bc`
- `0x18002a448`
- `0x18002f04c`
- `0x1800337fc`
- `0x180042448`
- `0x180043990`
- `0x180043a48`
- `0x180043adc`
- `0x180045c24`
- `0x180048edc`
- `0x18004a6d8`
- `0x18004b1b8`
- `0x180052cb4`
- `0x1800532d4`
- `0x180057c28`
- `0x180059a00`
- `0x18005aa38`
- `0x18005ec58`
- `0x180093c4c`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a7340`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800be2e0`
- `0x1800c0054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ddeb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800de13b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ddeb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800de13b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800de119`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800de119`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800dded6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800dded6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfcfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfcfd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de711`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de72f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de711`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800de72f`

## string_xrefs

- `0x1800dfc78`: `Failed to move file from: {} to {}`
- `0x1800dfd30`: `Failed to move file from: {} to {}`
- `0x1800de8bb`: `update.mum`
- `0x1800dcb71`: `Failed to create private session store.`
- `0x1800dd220`: `Failed adding payload path source`
- `0x1800dd2b9`: `Failed adding payload path source`
- `0x1800df451`: `Failed adding payload path source`
- `0x1800dfb21`: `Failed adding payload path source`
- `0x1800e00ec`: `Failed adding payload path source`
- `0x1800e0089`: `Failed to create sandbox.`
- `0x1800df729`: `Failed to setup the environment for cimbased update`
- `0x1800df84b`: `Failed to get staging root directory path for payload cims catalog.`
- `0x1800dffd5`: `Failed to get Staging directory path for unmanifested files.`
- `0x1800df536`: `Failed to clean staging directory {} for unmanifested files.`
- `0x1800dff65`: `Failed to create staging directory {} for unmanifested files.`
- `0x1800df939`: `Failed to get staging root directory path for payload Cims.`
- `0x1800df61d`: `Failed to create staging directory {} for cim payload.`
- `0x1800df8cf`: `Failed to create staging directory {} for cim payload.`
- `0x1800de2c3`: `windows\system32\CatRoot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\microsoft-windows-cimcatalog.cat`
- `0x1800de2e5`: `Extracting completed.`
- `0x1800dcc20`: `ActionList: No feature or package to install or remove in actionList, this is not expected.`
- `0x1800dd1b6`: `Scheduling installation of package: {} after reboot`
- `0x1800dd491`: `Attempted to install a FOD or LP with a postponed LCU install pending, a reboot must be performed first`
- `0x1800ddd13`: `UpdateReserveManager available; checking if reserves should be used...`
- `0x1800ddd6b`: `The current quality update is not using the reserves`
- `0x1800dec9e`: `Scheduling installation of packages after reboot`
- `0x1800e055b`: `Failed adding payload path source: {}`
- `0x1800deda9`: `Failed to set payload path for package`
- `0x1800df01e`: `Skipping already installed SSU: {}`
- `0x1800defd0`: `SSU will pend. Setting IncompleteSetOfActions. Package: {}`
- `0x1800de2ff`: `CIM validation completed.`
- `0x1800dfbdc`: `Failed to get the packages directory`
- `0x1800de663`: `%wsupdate.cat`
- `0x1800de68a`: `%wsupdate.mum`
- `0x1800de8f0`: `Ignoring missing files in case of installation after reboot`
- `0x1800e0496`: `Failed to create package: {}`
- `0x1800e01a4`: `ActionList: Universal diff InstallPayload identity : ({}) does not match InstallPackage identity : ({}).`
- `0x1800e082f`: `Failed to process RemoveFeature Action`
- `0x1800e09aa`: `Failed to process InstallFeature Action`
- `0x1800e0a65`: `Failed to create foundation identity`
- `0x1800e0ba8`: `Failed to open foundation package`

## pseudocode

```c
__int64 __fastcall CCbsSession::ProcessCompleteActionList(
        CCbsSession *this,
        __int16 a2,
        struct ActionListParser::ActionListDocument *a3,
        struct Windows::Rtl::PrivateHeapPool *a4,
        wchar_t *a5,
        bool a6)
{
  int ServicingDirectory; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int SessionSandbox; // eax
  int v13; // edx
  unsigned __int64 v14; // r9
  _QWORD *v15; // rax
  int v16; // edx
  int v17; // eax
  int v18; // eax
  struct _LUTF8_STRING *v19; // rcx
  int v20; // eax
  int v21; // eax
  char v22; // bl
  char v23; // r12
  struct _LUTF8_STRING *v24; // rcx
  struct _LUTF8_STRING *v25; // r14
  __int128 *v26; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // edx
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  wchar_t **v37; // rcx
  int v38; // edx
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  int v41; // eax
  int v42; // edx
  int IsSmartPended; // eax
  int v44; // edx
  int v45; // edx
  char v46; // r13
  int v47; // ebx
  __int16 v48; // r12
  struct ActionListParser::InstallPackage *v49; // rcx
  struct ActionListParser::InstallPackage *v50; // r13
  int v51; // r14d
  unsigned int v52; // ebx
  __int64 v53; // r8
  bool IsOSFeatureUpdate; // al
  int v55; // ecx
  bool v56; // zf
  int v57; // eax
  int v58; // eax
  char v59; // al
  __int128 *v60; // r14
  const struct _LUTF8_STRING *v61; // rdx
  const struct _LUTF8_STRING *v62; // rbx
  int v63; // eax
  int v64; // eax
  __int128 *v65; // r14
  int v66; // eax
  const struct _LUTF8_STRING *v67; // rdx
  int v68; // ecx
  int v69; // r14d
  int v70; // eax
  unsigned int ReserveManager; // eax
  __int64 v72; // rbx
  const char *v73; // rdx
  wchar_t **v74; // r12
  int v75; // r13d
  wchar_t **v76; // rax
  const struct _LUTF8_STRING *v77; // r14
  int v78; // eax
  const wchar_t **v79; // r14
  const wchar_t **v80; // r13
  int v81; // eax
  int SingleFile; // eax
  int v83; // edx
  __int64 v84; // rdx
  unsigned __int64 v85; // r9
  int v86; // eax
  int v87; // eax
  int v88; // eax
  int v89; // eax
  int v90; // eax
  int v91; // eax
  int OfflineWindowsDirectory; // eax
  int v93; // edx
  __int64 v94; // rdx
  void *v95; // rbx
  void *v96; // rcx
  int v97; // eax
  int v98; // eax
  char v99; // r12
  wchar_t **v100; // r14
  wchar_t **v101; // r13
  wchar_t **v102; // r14
  wchar_t **v103; // r12
  int v104; // eax
  wchar_t **v105; // r14
  wchar_t **v106; // r12
  __int64 v107; // rdx
  int v108; // eax
  struct CCbsIdentity **v109; // rax
  struct ActionListParser::InstallPackage *v110; // rax
  CCbsPackage *v111; // rcx
  wchar_t **v112; // rcx
  char v113; // bl
  int v114; // eax
  wchar_t **v115; // r14
  wchar_t **v116; // r13
  const wchar_t **v117; // r12
  unsigned int v118; // ebx
  int v119; // eax
  int v120; // edx
  unsigned __int64 v121; // r9
  __int64 v122; // rdx
  struct ActionListParser::InstallPackage *v123; // r14
  unsigned int v124; // r13d
  int v125; // eax
  wchar_t **v126; // r14
  wchar_t **v127; // r12
  int v128; // eax
  bool v129; // cc
  int v130; // eax
  wchar_t **v131; // r14
  wchar_t **v132; // r12
  int v133; // eax
  wchar_t **v134; // r14
  wchar_t **v135; // r12
  __int64 v136; // rax
  char v137; // bl
  wchar_t **v138; // rcx
  __int64 v139; // rdx
  int v140; // edx
  int v141; // edx
  unsigned __int64 v142; // r9
  __int64 v143; // rdx
  int v144; // edx
  int v145; // edx
  __int64 v146; // rdx
  int v147; // edx
  int v148; // edx
  wchar_t **v149; // rcx
  int v150; // edx
  __int64 v151; // rdx
  int v152; // edx
  int v153; // edx
  int v154; // edx
  int v155; // edx
  int v156; // edx
  __int64 v157; // rdx
  int v158; // edx
  int v159; // edx
  int v160; // edx
  unsigned __int64 v161; // r9
  __int64 v162; // rdx
  int v163; // edx
  void *p_lpNewFileName; // rcx
  int v165; // edx
  int v166; // edx
  unsigned __int64 v167; // r9
  int v168; // edx
  signed int LastError; // ebx
  int v170; // edx
  unsigned int v171; // eax
  __int64 v172; // rdx
  int v173; // edx
  unsigned int v174; // eax
  __int64 v175; // rdx
  __int64 v176; // rdx
  int v177; // edx
  unsigned __int64 v178; // r9
  int v179; // edx
  int v180; // edx
  int v181; // edx
  int v182; // edx
  __int64 v183; // rdx
  int v184; // edx
  __int64 v185; // r9
  __int64 v186; // rdx
  int v187; // edx
  int v188; // edx
  int v189; // edx
  int v190; // edx
  __int64 v191; // rdx
  int v192; // edx
  int v193; // edx
  int v194; // edx
  int v195; // edx
  int v196; // edx
  int v197; // edx
  int v198; // edx
  int v199; // edx
  int v200; // edx
  int v201; // edx
  __int64 v202; // rcx
  int v203; // edx
  __int64 v204; // rcx
  int v205; // edx
  struct CCbsIdentity **InitPointer; // rax
  int CbsIdentity; // eax
  int v208; // edx
  __int64 v209; // rdx
  struct ICbsIdentity **v210; // rcx
  int v211; // eax
  int v212; // edx
  struct CCbsPackage **v213; // rax
  int v214; // eax
  int v215; // edx
  int CurrentState; // eax
  int v217; // edx
  int v218; // eax
  int v219; // edx
  struct CCbsIdentity **v220; // rax
  struct CCbsPackage **v221; // rax
  int v222; // eax
  int v223; // edx
  unsigned __int64 v224; // r9
  __int64 v225; // rdx
  int v226; // eax
  int *DirCount; // [rsp+20h] [rbp-E0h]
  int DirCounta; // [rsp+20h] [rbp-E0h]
  char v230; // [rsp+70h] [rbp-90h]
  char v231; // [rsp+71h] [rbp-8Fh]
  char v232; // [rsp+72h] [rbp-8Eh]
  char v233; // [rsp+73h] [rbp-8Dh]
  char v234; // [rsp+74h] [rbp-8Ch]
  int v235; // [rsp+78h] [rbp-88h]
  char v237; // [rsp+80h] [rbp-80h]
  struct ActionListParser::InstallPackage *v239; // [rsp+90h] [rbp-70h]
  int v240; // [rsp+98h] [rbp-68h]
  int v241; // [rsp+9Ch] [rbp-64h]
  int v242; // [rsp+A0h] [rbp-60h]
  int v243; // [rsp+A4h] [rbp-5Ch]
  int v244; // [rsp+A8h] [rbp-58h]
  int v245; // [rsp+ACh] [rbp-54h]
  unsigned int v246; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v247; // [rsp+B4h] [rbp-4Ch] BYREF
  struct ActionListParser::ActionListDocument *v248; // [rsp+B8h] [rbp-48h]
  int v249[4]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v250; // [rsp+D8h] [rbp-28h] BYREF
  int *v251; // [rsp+E0h] [rbp-20h] BYREF
  int *v252; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t *v253; // [rsp+F0h] [rbp-10h] BYREF
  int *v254; // [rsp+F8h] [rbp-8h] BYREF
  int *v255; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v256; // [rsp+108h] [rbp+8h] BYREF
  int *v257; // [rsp+110h] [rbp+10h] BYREF
  int *v258; // [rsp+118h] [rbp+18h] BYREF
  int *v259; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v260; // [rsp+128h] [rbp+28h] BYREF
  int v261[2]; // [rsp+130h] [rbp+30h] BYREF
  int *v262; // [rsp+138h] [rbp+38h] BYREF
  int *v263; // [rsp+140h] [rbp+40h] BYREF
  int *v264; // [rsp+148h] [rbp+48h] BYREF
  int *v265; // [rsp+150h] [rbp+50h] BYREF
  int *v266; // [rsp+158h] [rbp+58h] BYREF
  int v267[2]; // [rsp+160h] [rbp+60h] BYREF
  int *v268; // [rsp+168h] [rbp+68h] BYREF
  int v269[2]; // [rsp+170h] [rbp+70h] BYREF
  int *v270; // [rsp+178h] [rbp+78h] BYREF
  wchar_t *v271; // [rsp+180h] [rbp+80h] BYREF
  int v272[2]; // [rsp+188h] [rbp+88h] BYREF
  int *v273; // [rsp+190h] [rbp+90h] BYREF
  int *v274; // [rsp+198h] [rbp+98h] BYREF
  int *v275; // [rsp+1A0h] [rbp+A0h] BYREF
  int *v276; // [rsp+1A8h] [rbp+A8h] BYREF
  int *v277; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t *v278; // [rsp+1B8h] [rbp+B8h] BYREF
  int *v279; // [rsp+1C0h] [rbp+C0h] BYREF
  int v280[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  int *v281; // [rsp+1D0h] [rbp+D0h] BYREF
  wchar_t *v282; // [rsp+1D8h] [rbp+D8h] BYREF
  int *v283; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t *v284; // [rsp+1E8h] [rbp+E8h] BYREF
  int *v285; // [rsp+1F0h] [rbp+F0h] BYREF
  int *v286; // [rsp+1F8h] [rbp+F8h] BYREF
  const wchar_t *v287; // [rsp+200h] [rbp+100h] BYREF
  const wchar_t *IdentityFast; // [rsp+208h] [rbp+108h] BYREF
  const wchar_t *v289; // [rsp+210h] [rbp+110h] BYREF
  const wchar_t *v290; // [rsp+218h] [rbp+118h] BYREF
  const wchar_t *v291; // [rsp+220h] [rbp+120h] BYREF
  const wchar_t *v292; // [rsp+228h] [rbp+128h] BYREF
  int *v293; // [rsp+230h] [rbp+130h] BYREF
  int v294[2]; // [rsp+238h] [rbp+138h] BYREF
  int *v295; // [rsp+240h] [rbp+140h] BYREF
  wchar_t *v296; // [rsp+248h] [rbp+148h] BYREF
  __int64 v297; // [rsp+250h] [rbp+150h] BYREF
  wchar_t *v298; // [rsp+258h] [rbp+158h] BYREF
  int *v299; // [rsp+260h] [rbp+160h] BYREF
  int *v300; // [rsp+268h] [rbp+168h] BYREF
  int *v301; // [rsp+270h] [rbp+170h] BYREF
  int *v302; // [rsp+278h] [rbp+178h] BYREF
  int *v303; // [rsp+280h] [rbp+180h] BYREF
  int *v304; // [rsp+288h] [rbp+188h] BYREF
  int v305[2]; // [rsp+290h] [rbp+190h] BYREF
  int *v306; // [rsp+298h] [rbp+198h] BYREF
  int *v307; // [rsp+2A0h] [rbp+1A0h] BYREF
  int *v308; // [rsp+2A8h] [rbp+1A8h] BYREF
  int *v309; // [rsp+2B0h] [rbp+1B0h] BYREF
  int *v310; // [rsp+2B8h] [rbp+1B8h] BYREF
  wchar_t *FastCbsIdentityString; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v312[2]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v313; // [rsp+2D0h] [rbp+1D0h] BYREF
  int *v314; // [rsp+2D8h] [rbp+1D8h] BYREF
  LPCWSTR v315; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int *v316; // [rsp+2E8h] [rbp+1E8h] BYREF
  LPCWSTR v317; // [rsp+2F0h] [rbp+1F0h] BYREF
  LPCWSTR v318; // [rsp+2F8h] [rbp+1F8h] BYREF
  unsigned int v319[2]; // [rsp+300h] [rbp+200h] BYREF
  int *v320; // [rsp+308h] [rbp+208h] BYREF
  wchar_t *v321; // [rsp+310h] [rbp+210h] BYREF
  int *v322; // [rsp+318h] [rbp+218h] BYREF
  int v323[2]; // [rsp+320h] [rbp+220h] BYREF
  int *v324; // [rsp+328h] [rbp+228h] BYREF
  int *v325; // [rsp+330h] [rbp+230h] BYREF
  const wchar_t *v326; // [rsp+338h] [rbp+238h] BYREF
  int *v327; // [rsp+340h] [rbp+240h] BYREF
  int *v328; // [rsp+348h] [rbp+248h] BYREF
  int *v329; // [rsp+350h] [rbp+250h] BYREF
  int *v330; // [rsp+358h] [rbp+258h] BYREF
  const wchar_t *v331; // [rsp+360h] [rbp+260h] BYREF
  int *v332; // [rsp+368h] [rbp+268h] BYREF
  const wchar_t *v333; // [rsp+370h] [rbp+270h] BYREF
  int *v334; // [rsp+378h] [rbp+278h] BYREF
  wchar_t *v335; // [rsp+380h] [rbp+280h] BYREF
  int v336[2]; // [rsp+388h] [rbp+288h] BYREF
  int *v337; // [rsp+390h] [rbp+290h] BYREF
  wchar_t *v338; // [rsp+3C0h] [rbp+2C0h] BYREF
  wchar_t *v339; // [rsp+3C8h] [rbp+2C8h] BYREF
  wchar_t *Str; // [rsp+3D0h] [rbp+2D0h] BYREF
  wchar_t *v341; // [rsp+3D8h] [rbp+2D8h] BYREF
  wchar_t *v342; // [rsp+3E0h] [rbp+2E0h] BYREF
  struct IUpdateReserveManagerCBS *v343; // [rsp+3E8h] [rbp+2E8h] BYREF
  wchar_t *v344; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t *v345; // [rsp+3F8h] [rbp+2F8h] BYREF
  wchar_t *v346; // [rsp+400h] [rbp+300h] BYREF
  wchar_t *v347; // [rsp+408h] [rbp+308h] BYREF
  wchar_t *v348; // [rsp+410h] [rbp+310h] BYREF
  wchar_t *v349; // [rsp+418h] [rbp+318h] BYREF
  wchar_t *v350; // [rsp+420h] [rbp+320h] BYREF
  wchar_t *v351; // [rsp+428h] [rbp+328h] BYREF
  wchar_t *v352; // [rsp+430h] [rbp+330h] BYREF
  wchar_t *v353; // [rsp+438h] [rbp+338h] BYREF
  wchar_t *v354; // [rsp+440h] [rbp+340h] BYREF
  wchar_t *v355; // [rsp+448h] [rbp+348h] BYREF
  __int128 v356; // [rsp+450h] [rbp+350h] BYREF
  __int64 v357; // [rsp+460h] [rbp+360h]
  __int128 v358; // [rsp+468h] [rbp+368h]
  __int64 v359; // [rsp+478h] [rbp+378h]
  __int64 v360; // [rsp+480h] [rbp+380h]
  __int128 v361; // [rsp+488h] [rbp+388h]
  __int64 v362; // [rsp+498h] [rbp+398h]
  __int128 v363; // [rsp+4A0h] [rbp+3A0h]
  __int64 v364; // [rsp+4B0h] [rbp+3B0h]
  __int128 v365; // [rsp+4B8h] [rbp+3B8h]
  __int64 v366; // [rsp+4C8h] [rbp+3C8h]
  __int64 v367; // [rsp+4D0h] [rbp+3D0h]
  __int64 v368; // [rsp+4D8h] [rbp+3D8h]
  __int128 v369; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v370; // [rsp+4F0h] [rbp+3F0h]
  __int128 v371; // [rsp+4F8h] [rbp+3F8h]
  __int64 v372; // [rsp+508h] [rbp+408h]
  __int64 v373; // [rsp+510h] [rbp+410h]
  __int128 v374; // [rsp+518h] [rbp+418h]
  __int64 v375; // [rsp+528h] [rbp+428h]
  __int128 v376; // [rsp+530h] [rbp+430h]
  __int64 v377; // [rsp+540h] [rbp+440h]
  __int128 v378; // [rsp+548h] [rbp+448h]
  __int64 v379; // [rsp+558h] [rbp+458h]
  __int64 v380; // [rsp+560h] [rbp+460h]
  __int64 v381; // [rsp+568h] [rbp+468h]
  __int64 v382; // [rsp+570h] [rbp+470h] BYREF
  __int64 v383; // [rsp+578h] [rbp+478h] BYREF
  __int64 v384; // [rsp+580h] [rbp+480h] BYREF
  wchar_t *v385; // [rsp+588h] [rbp+488h] BYREF
  __int64 v386; // [rsp+590h] [rbp+490h] BYREF
  char v387[8]; // [rsp+598h] [rbp+498h] BYREF
  wchar_t *v388; // [rsp+5A0h] [rbp+4A0h] BYREF
  CCbsPackage *v389; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v390[24]; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v391; // [rsp+5C8h] [rbp+4C8h]
  wchar_t **v392; // [rsp+5D8h] [rbp+4D8h]
  int v393; // [rsp+5F0h] [rbp+4F0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+5F8h] [rbp+4F8h] BYREF
  wchar_t *v395; // [rsp+600h] [rbp+500h] BYREF
  wchar_t *v396; // [rsp+608h] [rbp+508h] BYREF
  struct ICbsIdentity *v397; // [rsp+610h] [rbp+510h] BYREF
  CCbsPackage *v398; // [rsp+618h] [rbp+518h] BYREF
  __int64 v399; // [rsp+620h] [rbp+520h] BYREF
  LPCWSTR v400; // [rsp+628h] [rbp+528h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+630h] [rbp+530h] BYREF
  wchar_t *v402; // [rsp+638h] [rbp+538h] BYREF
  CCbsIdentity *v403; // [rsp+640h] [rbp+540h] BYREF
  wchar_t *v404; // [rsp+648h] [rbp+548h] BYREF
  wchar_t *v405; // [rsp+650h] [rbp+550h] BYREF
  wchar_t *v406; // [rsp+658h] [rbp+558h] BYREF
  wchar_t *v407; // [rsp+660h] [rbp+560h] BYREF
  struct CCbsIdentity *v408; // [rsp+668h] [rbp+568h] BYREF
  wchar_t *v409; // [rsp+670h] [rbp+570h] BYREF
  wchar_t *v410; // [rsp+678h] [rbp+578h] BYREF
  wchar_t *v411; // [rsp+680h] [rbp+580h] BYREF
  __int64 v412; // [rsp+688h] [rbp+588h] BYREF
  unsigned int v413; // [rsp+690h] [rbp+590h] BYREF
  int v414; // [rsp+694h] [rbp+594h] BYREF
  int v415; // [rsp+698h] [rbp+598h] BYREF
  unsigned int v416; // [rsp+69Ch] [rbp+59Ch] BYREF
  unsigned int v417; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned int v418; // [rsp+6A4h] [rbp+5A4h] BYREF
  int v419; // [rsp+6A8h] [rbp+5A8h] BYREF
  int v420; // [rsp+6ACh] [rbp+5ACh] BYREF
  __int128 *v421; // [rsp+6B0h] [rbp+5B0h] BYREF
  struct _LUTF8_STRING *v422; // [rsp+6B8h] [rbp+5B8h] BYREF
  __int64 v423; // [rsp+6C0h] [rbp+5C0h] BYREF
  __int128 *v424; // [rsp+6C8h] [rbp+5C8h] BYREF
  __int128 *v425; // [rsp+6D0h] [rbp+5D0h] BYREF
  struct ActionListParser::InstallPackage *v426; // [rsp+6D8h] [rbp+5D8h] BYREF
  __int64 v427; // [rsp+6E0h] [rbp+5E0h] BYREF
  __int64 v428; // [rsp+6E8h] [rbp+5E8h] BYREF
  __int64 v429; // [rsp+6F0h] [rbp+5F0h] BYREF
  struct _LUTF8_STRING *v430; // [rsp+6F8h] [rbp+5F8h] BYREF
  int v431; // [rsp+700h] [rbp+600h] BYREF
  int v432; // [rsp+704h] [rbp+604h] BYREF
  int v433; // [rsp+708h] [rbp+608h] BYREF
  int v434; // [rsp+70Ch] [rbp+60Ch] BYREF
  int v435; // [rsp+710h] [rbp+610h] BYREF
  int v436; // [rsp+714h] [rbp+614h] BYREF
  int v437; // [rsp+718h] [rbp+618h] BYREF
  int v438; // [rsp+71Ch] [rbp+61Ch] BYREF
  int v439; // [rsp+720h] [rbp+620h] BYREF
  int v440; // [rsp+724h] [rbp+624h] BYREF
  int v441; // [rsp+728h] [rbp+628h] BYREF
  int v442; // [rsp+72Ch] [rbp+62Ch] BYREF
  int v443; // [rsp+730h] [rbp+630h] BYREF
  int v444; // [rsp+734h] [rbp+634h] BYREF
  int v445; // [rsp+738h] [rbp+638h] BYREF
  int v446; // [rsp+73Ch] [rbp+63Ch] BYREF
  int v447; // [rsp+740h] [rbp+640h] BYREF
  int v448; // [rsp+744h] [rbp+644h] BYREF
  int v449; // [rsp+748h] [rbp+648h] BYREF
  int v450; // [rsp+74Ch] [rbp+64Ch] BYREF
  int v451; // [rsp+750h] [rbp+650h] BYREF
  int v452; // [rsp+754h] [rbp+654h] BYREF
  int v453; // [rsp+758h] [rbp+658h] BYREF
  int v454; // [rsp+75Ch] [rbp+65Ch] BYREF
  int v455; // [rsp+760h] [rbp+660h] BYREF
  int v456; // [rsp+764h] [rbp+664h] BYREF
  int v457; // [rsp+768h] [rbp+668h] BYREF
  int v458; // [rsp+76Ch] [rbp+66Ch] BYREF
  int v459; // [rsp+770h] [rbp+670h] BYREF
  int v460; // [rsp+774h] [rbp+674h] BYREF
  int v461; // [rsp+778h] [rbp+678h] BYREF
  int v462; // [rsp+77Ch] [rbp+67Ch] BYREF
  int v463; // [rsp+780h] [rbp+680h] BYREF
  int v464; // [rsp+784h] [rbp+684h] BYREF
  int v465; // [rsp+788h] [rbp+688h] BYREF
  int v466; // [rsp+78Ch] [rbp+68Ch] BYREF
  int v467; // [rsp+790h] [rbp+690h] BYREF
  int v468; // [rsp+794h] [rbp+694h] BYREF
  int v469; // [rsp+798h] [rbp+698h] BYREF
  int v470; // [rsp+79Ch] [rbp+69Ch] BYREF
  int v471; // [rsp+7A0h] [rbp+6A0h] BYREF
  int v472; // [rsp+7A4h] [rbp+6A4h] BYREF
  int v473; // [rsp+7A8h] [rbp+6A8h] BYREF
  int v474; // [rsp+7ACh] [rbp+6ACh] BYREF
  int v475; // [rsp+7B0h] [rbp+6B0h] BYREF
  int v476; // [rsp+7B4h] [rbp+6B4h] BYREF
  int v477; // [rsp+7B8h] [rbp+6B8h] BYREF
  int v478; // [rsp+7BCh] [rbp+6BCh] BYREF
  int v479; // [rsp+7C0h] [rbp+6C0h] BYREF
  int v480; // [rsp+7C4h] [rbp+6C4h] BYREF
  int v481; // [rsp+7C8h] [rbp+6C8h] BYREF
  int v482; // [rsp+7CCh] [rbp+6CCh] BYREF
  int v483; // [rsp+7D0h] [rbp+6D0h] BYREF
  int v484; // [rsp+7D4h] [rbp+6D4h] BYREF
  int v485; // [rsp+7D8h] [rbp+6D8h] BYREF
  int v486; // [rsp+7DCh] [rbp+6DCh] BYREF
  int v487; // [rsp+7E0h] [rbp+6E0h] BYREF
  int v488; // [rsp+7E4h] [rbp+6E4h] BYREF
  int v489; // [rsp+7E8h] [rbp+6E8h] BYREF
  __int128 v490; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int128 v491; // [rsp+800h] [rbp+700h] BYREF
  __int128 v492; // [rsp+810h] [rbp+710h] BYREF
  __int64 v493; // [rsp+820h] [rbp+720h]
  __int64 v494; // [rsp+828h] [rbp+728h] BYREF
  __int64 v495; // [rsp+830h] [rbp+730h] BYREF
  _BYTE v496[24]; // [rsp+840h] [rbp+740h] BYREF
  __int64 v497; // [rsp+858h] [rbp+758h]
  const wchar_t **v498; // [rsp+868h] [rbp+768h]
  __int64 v499; // [rsp+880h] [rbp+780h] BYREF
  __int64 v500; // [rsp+888h] [rbp+788h] BYREF
  __int64 v501; // [rsp+890h] [rbp+790h] BYREF
  __int64 v502; // [rsp+898h] [rbp+798h] BYREF
  __int64 v503; // [rsp+8A0h] [rbp+7A0h] BYREF
  __int64 v504; // [rsp+8A8h] [rbp+7A8h] BYREF
  __int64 v505; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v506; // [rsp+8B8h] [rbp+7B8h] BYREF
  __int64 v507; // [rsp+8C0h] [rbp+7C0h] BYREF
  int v508[2]; // [rsp+8C8h] [rbp+7C8h] BYREF
  int v509; // [rsp+8D0h] [rbp+7D0h]
  __int128 v510; // [rsp+8D8h] [rbp+7D8h]
  __int64 v511; // [rsp+8E8h] [rbp+7E8h]
  wchar_t Ext[256]; // [rsp+8F0h] [rbp+7F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B38h] [rbp+A38h]

  v338 = a5;
  v248 = a3;
  v495 = 0;
  v242 = a2 & 0x400;
  v244 = a2 & 0x1000;
  if ( (a2 & 0x400) != 0 )
  {
    if ( (a2 & 0x1000) != 0 )
    {
      ServicingDirectory = -2147024809;
      v445 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid parameter: ServicingProcessorOptions.");
        v307 = &v445;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          1,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v10 = 892;
      goto LABEL_18;
    }
  }
  else if ( (a2 & 0x1000) != 0 && (a2 & 0x2000) != 0 )
  {
    ServicingDirectory = -2147024809;
    v444 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid parameter: ServicingProcessorOptions.");
      v306 = &v444;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        1,
        3,
        (unsigned int)": {}",
        (__int64)&v306);
    }
    v10 = 898;
LABEL_18:
    v14 = (unsigned int)ServicingDirectory;
    goto LABEL_19;
  }
  v11 = *((_DWORD *)a3 + 20);
  *((_DWORD *)this + 553) = v11;
  if ( (*((_BYTE *)a3 + 84) & 1) != 0 || v11 == 17 )
    *((_DWORD *)this + 552) |= 0x80000u;
  SessionSandbox = CCbsSession::CreateSessionSandbox(this, *((void **)this + 141), 0, 0);
  ServicingDirectory = SessionSandbox;
  if ( SessionSandbox < 0 )
  {
    v443 = SessionSandbox;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create private session store.");
      *(_QWORD *)v305 = &v443;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)v305);
    }
    v10 = 909;
    goto LABEL_18;
  }
  if ( !*(_QWORD *)(*((_QWORD *)a3 + 19) + 64LL) )
  {
    v15 = (_QWORD *)*((_QWORD *)a3 + 17);
    if ( !v15 || !v15[5] && !v15[1] && !v15[3] )
    {
      ServicingDirectory = -2146498222;
      v442 = -2146498222;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "ActionList: No feature or package to install or remove in actionList, this is not expected.");
        v304 = &v442;
        LOBYTE(v16) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v16,
          3,
          (unsigned int)": {}",
          (__int64)&v304);
      }
      v10 = 923;
      goto LABEL_18;
    }
  }
  if ( *((_BYTE *)a3 + 164) )
  {
    v352 = 0;
    v17 = DuplicateParserString(a4, (struct ActionListParser::ActionListDocument *)((char *)a3 + 88), &v352);
    ServicingDirectory = v17;
    if ( v17 < 0 )
    {
      v14 = (unsigned int)v17;
      v10 = 929;
      goto LABEL_19;
    }
    v18 = SczAllocFromSz((char *)this + 2216, v352);
    ServicingDirectory = v18;
    if ( v18 < 0 )
    {
      v14 = (unsigned int)v18;
      v10 = 930;
      goto LABEL_19;
    }
  }
  if ( CCbsSession::IsFODRetryOperation(this) )
  {
    v19 = (struct _LUTF8_STRING *)**((_QWORD **)a3 + 17);
    v499 = 0;
    while ( 1 )
    {
      v430 = v19;
      if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                               &v430,
                               &v499) )
        goto LABEL_41;
      v345 = 0;
      v20 = DuplicateParserString(a4, v430, &v345);
      ServicingDirectory = v20;
      if ( v20 < 0 )
      {
        v14 = (unsigned int)v20;
        v10 = 944;
        goto LABEL_19;
      }
      LogAdapter::TraceAtLevel<wchar_t *>(1, "ActionList: Adding FOD retry: {}", &v345);
      v21 = CCbsStringArray::CopyAndAdd((CCbsSession *)((char *)this + 1760), v345);
      ServicingDirectory = v21;
      if ( v21 < 0 )
        break;
      v19 = (struct _LUTF8_STRING *)*((_QWORD *)v430 + 9);
    }
    v14 = (unsigned int)v21;
    v10 = 948;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
      (const char *)v14,
      (int)DirCount);
    goto LABEL_698;
  }
LABEL_41:
  v22 = 0;
  v232 = 0;
  v23 = 0;
  v231 = 0;
  v24 = *(struct _LUTF8_STRING **)(*((_QWORD *)a3 + 19) + 56LL);
  v500 = 0;
  while ( 1 )
  {
    v422 = v24;
    if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                             &v422,
                             &v500) )
      break;
    v25 = v422;
    if ( *((_DWORD *)v422 + 34) == 4 )
      v23 = 1;
    LogAdapter::DebuggerLogger::IncludeNewline((LogAdapter::DebuggerLogger *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl) )
    {
      if ( CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(this, v25)
        || v23 && *((_BYTE *)v25 + 307) && *((_DWORD *)v25 + 35) == 6 && *((_DWORD *)v25 + 34) != 4 )
      {
        v360 = 0;
        v357 = 0;
        v359 = 0;
        v356 = 0;
        v362 = 0;
        v358 = 0;
        v364 = 0;
        v361 = 0;
        v366 = 0;
        v363 = 0;
        v367 = 0;
        v365 = 0;
        v368 = 0;
        if ( *((_QWORD *)v25 + 33) )
        {
          v26 = (__int128 *)*((_QWORD *)v25 + 32);
        }
        else
        {
          v26 = &v356;
          BYTE3(v368) = *((_BYTE *)v25 + 305);
          v361 = *(_OWORD *)((char *)v25 + 40);
          v362 = *((_QWORD *)v25 + 7);
          BYTE4(v368) = *((_BYTE *)v25 + 307);
          v363 = *(_OWORD *)((char *)v25 + 88);
          v364 = *((_QWORD *)v25 + 13);
          BYTE5(v368) = *((_BYTE *)v25 + 308);
          v365 = *((_OWORD *)v25 + 7);
          v366 = *((_QWORD *)v25 + 16);
        }
        v501 = 0;
        while ( 1 )
        {
          v421 = v26;
          if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                   &v421,
                                   &v501) )
            goto LABEL_69;
          v347 = 0;
          v27 = DuplicateParserString(a4, (const struct _LUTF8_STRING *)(v421 + 5), &v347);
          ServicingDirectory = v27;
          if ( v27 < 0 )
            break;
          v409 = 0;
          v28 = SczAllocFormatted(&v409, L"%ws%ws", v338, v347);
          ServicingDirectory = v28;
          if ( v28 < 0 )
          {
            v35 = (unsigned int)v28;
            v36 = 1002;
LABEL_92:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v36,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)v35,
              (int)DirCount);
            v37 = &v409;
            goto LABEL_93;
          }
          if ( (unsigned __int8)DoesDirectoryExist(v409, 0) )
          {
            LogAdapter::TraceAtLevel<wchar_t const *,wchar_t *>(1, "Adding sandbox metadata source: {}{}", &v338, &v347);
            ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v409, 0);
            if ( ServicingDirectory < 0 )
            {
              v441 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding payload path source");
                v303 = &v441;
                LOBYTE(v34) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v34,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v303);
              }
              v35 = (unsigned int)ServicingDirectory;
              v36 = 1017;
              goto LABEL_92;
            }
          }
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v409);
          v26 = (__int128 *)*((_QWORD *)v421 + 16);
        }
        v14 = (unsigned int)v27;
        v10 = 999;
        goto LABEL_19;
      }
    }
    else if ( v23 && *((_BYTE *)v25 + 307) && *((_DWORD *)v25 + 35) == 6 )
    {
      v346 = 0;
      v29 = DuplicateParserString(a4, (struct _LUTF8_STRING *)((char *)v25 + 88), &v346);
      ServicingDirectory = v29;
      if ( v29 < 0 )
      {
        v14 = (unsigned int)v29;
        v10 = 1031;
        goto LABEL_19;
      }
      v410 = 0;
      v30 = SczAllocFormatted(&v410, L"%ws%ws", v338, v346);
      ServicingDirectory = v30;
      if ( v30 < 0 )
      {
        v39 = (unsigned int)v30;
        v40 = 1034;
LABEL_99:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)v39,
          (int)DirCount);
        v37 = &v410;
        goto LABEL_93;
      }
      if ( (unsigned __int8)DoesDirectoryExist(v410, 0) )
      {
        LogAdapter::TraceAtLevel<wchar_t const *,wchar_t *>(1, "Adding sandbox metadata source: {}{}", &v338, &v346);
        ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v410, 0);
        if ( ServicingDirectory < 0 )
        {
          v440 = ServicingDirectory;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding payload path source");
            v302 = &v440;
            LOBYTE(v38) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v38,
              3,
              (unsigned int)": {}",
              (__int64)&v302);
          }
          v39 = (unsigned int)ServicingDirectory;
          v40 = 1049;
          goto LABEL_99;
        }
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v410);
LABEL_69:
      v22 = v231;
    }
    v31 = *((_DWORD *)v25 + 34);
    if ( !v31 || v31 == 5 )
    {
      if ( (unsigned int)CCbsSession::IsOffline(this) || *((_DWORD *)v25 + 57) != 1 || a6 )
      {
        if ( *((_DWORD *)v25 + 35) != 2 && *((_DWORD *)v25 + 35) != 3 && *((_DWORD *)v25 + 35) != 4 )
        {
          if ( *((_DWORD *)v25 + 35) == 5 || *((_DWORD *)v25 + 35) == 6 )
            goto LABEL_85;
          if ( *((_DWORD *)v25 + 35) != 9 )
          {
            if ( *((_DWORD *)v25 + 35) != 13 )
              goto LABEL_87;
LABEL_85:
            v232 = 1;
            goto LABEL_87;
          }
        }
        v22 = 1;
        v231 = 1;
      }
      else
      {
        v351 = 0;
        v32 = DuplicateParserString(a4, v25, &v351);
        ServicingDirectory = v32;
        if ( v32 < 0 )
        {
          v14 = (unsigned int)v32;
          v10 = 1065;
          goto LABEL_19;
        }
        *((_BYTE *)this + 2273) = 1;
        v33 = SczAllocFromSz((char *)this + 2280, v338);
        ServicingDirectory = v33;
        if ( v33 < 0 )
        {
          v14 = (unsigned int)v33;
          v10 = 1068;
          goto LABEL_19;
        }
        LogAdapter::TraceAtLevel<wchar_t *>(1, "Scheduling installation of package: {} after reboot", &v351);
        v22 = v231;
      }
    }
LABEL_87:
    v24 = (struct _LUTF8_STRING *)*((_QWORD *)v422 + 37);
  }
  if ( v232 )
  {
    if ( v22 )
    {
      LogAdapter::TraceAtLevel<>(1, "Delaying parallel hydration use until the LCU is processed.");
      v41 = CCbsSession::SetReservicingSandboxPath(this, v338);
      ServicingDirectory = v41;
      if ( v41 < 0 )
      {
        v439 = v41;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
          v301 = &v439;
          LOBYTE(v42) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v42,
            3,
            (unsigned int)": {}",
            (__int64)&v301);
        }
        v10 = 1100;
        goto LABEL_18;
      }
    }
  }
  v420 = 0;
  IsSmartPended = CCbsSession::LCUInstallIsSmartPended(this, &v420);
  ServicingDirectory = IsSmartPended;
  if ( IsSmartPended < 0 )
  {
    v438 = IsSmartPended;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting LCU smart pended state");
      v300 = &v438;
      LOBYTE(v44) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v44,
        3,
        (unsigned int)": {}",
        (__int64)&v300);
    }
    v10 = 1119;
    goto LABEL_18;
  }
  if ( v420 && v231 )
  {
    ServicingDirectory = -2146498554;
    v471 = -2146498554;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Attempted to install a FOD or LP with a postponed LCU install pending, a reboot must be performed first");
      v299 = &v471;
      LOBYTE(v45) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v45,
        3,
        (unsigned int)": {}",
        (__int64)&v299);
    }
    v10 = 1125;
    goto LABEL_18;
  }
  v230 = 0;
  v237 = 0;
  v46 = 0;
  v47 = 0;
LABEL_119:
  v240 = v47;
  if ( v47 > 5 )
    goto LABEL_432;
  v48 = a2;
  if ( v47 > 0 && (a2 & 0x4000) != 0 )
  {
    LogAdapter::TraceAtLevel<>(1, "Stopping after pass 0 because CbsServicingProcessorOptionSSUOnly is set");
    goto LABEL_432;
  }
  v49 = *(struct ActionListParser::InstallPackage **)(*((_QWORD *)v248 + 19) + 56LL);
  v505 = 0;
  while ( 1 )
  {
    v426 = v49;
    if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                             &v426,
                             &v505) )
    {
      if ( v46 )
        goto LABEL_432;
      v47 = v240 + 1;
      v230 = 0;
      goto LABEL_119;
    }
    v50 = v426;
    v339 = 0;
    v344 = 0;
    v342 = 0;
    v383 = 0;
    v382 = 0;
    v51 = *((_DWORD *)v426 + 36);
    v52 = *((_DWORD *)v426 + 66);
    v235 = v51;
    v239 = v426;
    CCbsArray<MultiplePayloadsforPackage>::CCbsArray<MultiplePayloadsforPackage>(v390, 1);
    v245 = v48 & 0x1400;
    if ( !*((_BYTE *)v50 + 312)
      || (v387[0] = 0,
          (int)Windows::StringUtil::Rtl::AreStringsEqualByOrdinalCaseInvariant<_LUTF8_STRING,_LUTF8_STRING>(
                 (char *)v50 + 152,
                 ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0EN__0GB__0GJ__0GO__0EP__0FD__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B,
                 v387) < 0)
      || v387[0] )
    {
      LOBYTE(v53) = CCbsSession::IsOSFeatureUpdate(this);
      if ( (unsigned __int8)IsActionListPackageSupportedByCBS(
                              *((unsigned int *)v50 + 35),
                              *((unsigned int *)v50 + 34),
                              v53) )
        break;
    }
LABEL_138:
    v46 = v230;
LABEL_139:
    CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v390);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v382);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v383);
    v48 = a2;
    v49 = (struct ActionListParser::InstallPackage *)*((_QWORD *)v426 + 37);
  }
  if ( v240 )
  {
    if ( v240 == 1 )
    {
      v56 = *((_DWORD *)v50 + 34) == 4;
LABEL_137:
      if ( !v56 )
        goto LABEL_138;
      goto LABEL_153;
    }
    if ( v240 >= 2 )
    {
      if ( *((_DWORD *)v50 + 34) == 4 )
        goto LABEL_138;
      if ( v240 == 2 )
      {
        v57 = *((_DWORD *)v50 + 35);
        if ( v57 != 4 )
        {
          v56 = v57 == 9;
          goto LABEL_137;
        }
LABEL_153:
        v59 = v237;
        if ( *((_DWORD *)v50 + 35) == 6 )
          v59 = 1;
        v237 = v59;
LABEL_156:
        v235 = v51;
        goto LABEL_157;
      }
    }
    if ( v240 == 3 )
    {
      if ( (unsigned int)(*((_DWORD *)v50 + 35) - 2) <= 1 )
        goto LABEL_153;
    }
    else
    {
      if ( v240 == 4 )
      {
        v58 = *((_DWORD *)v50 + 35);
        if ( v58 != 6 )
        {
          v56 = v58 == 13;
          goto LABEL_137;
        }
        goto LABEL_153;
      }
      if ( v240 != 5 || *((_DWORD *)v50 + 35) == 5 )
        goto LABEL_153;
    }
    goto LABEL_138;
  }
  if ( *((_DWORD *)v50 + 34) == 4 )
    goto LABEL_138;
  IsOSFeatureUpdate = CCbsSession::IsOSFeatureUpdate(this);
  v55 = *((_DWORD *)v50 + 35);
  if ( !IsOSFeatureUpdate )
  {
    if ( v55 != 7 )
      goto LABEL_138;
    goto LABEL_156;
  }
  if ( v55 != 11 )
    goto LABEL_138;
LABEL_157:
  if ( v52 )
    v235 = *(_DWORD *)(*((_QWORD *)v50 + 32) + 48LL);
  v380 = 0;
  v370 = 0;
  v372 = 0;
  v369 = 0;
  v373 = 0;
  v371 = 0;
  v375 = 0;
  v374 = 0;
  v377 = 0;
  v376 = 0;
  v379 = 0;
  v378 = 0;
  v381 = 0;
  v234 = 0;
  if ( *((_QWORD *)v50 + 33) )
  {
    v60 = (__int128 *)*((_QWORD *)v50 + 32);
    if ( *((_DWORD *)v50 + 35) == 6 && v52 > 1 )
    {
      if ( CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(this, v50) )
      {
        v423 = *((_QWORD *)v50 + 32);
        v507 = 0;
        while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                   &v423,
                                   &v507) )
        {
          if ( *(_QWORD *)(v423 + 128) )
          {
            v62 = (const struct _LUTF8_STRING *)(v423 + 104);
            if ( !Windows::StringUtil::IsEmpty((Windows::StringUtil *)(v423 + 104), v61) )
            {
              v63 = DuplicateParserString(a4, v62, &v342);
              ServicingDirectory = v63;
              if ( v63 < 0 )
              {
                v122 = 1290;
                goto LABEL_445;
              }
              v411 = 0;
              v64 = SczAllocCombinePath2Sz(&v411, v338, v342);
              ServicingDirectory = v64;
              if ( v64 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x511,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                  (const char *)(unsigned int)v64,
                  (int)DirCount);
                v138 = &v411;
                goto LABEL_443;
              }
              v298 = v411;
              LogAdapter::TraceAtLevel<wchar_t *>(1, "ActionList: Using TurboContainer: {}", &v298);
              CCbsSession::InitializeMetadataContainer(this, v411);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v411);
            }
          }
          v423 = *(_QWORD *)(v423 + 128);
        }
      }
      v234 = 1;
      v424 = v60;
      v494 = 0;
      while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                 &v424,
                                 &v494) )
      {
        v60 = v424;
        v424 = (__int128 *)*((_QWORD *)v424 + 16);
      }
      if ( !v231 )
        *((_BYTE *)this + 2254) = 1;
    }
  }
  else
  {
    v60 = &v369;
    BYTE3(v381) = *((_BYTE *)v50 + 305);
    v374 = *(_OWORD *)((char *)v50 + 40);
    v375 = *((_QWORD *)v50 + 7);
    BYTE4(v381) = *((_BYTE *)v50 + 307);
    v376 = *(_OWORD *)((char *)v50 + 88);
    v377 = *((_QWORD *)v50 + 13);
    BYTE5(v381) = *((_BYTE *)v50 + 308);
    v378 = *((_OWORD *)v50 + 7);
    v379 = *((_QWORD *)v50 + 16);
  }
  v425 = v60;
  v503 = 0;
  while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                             &v425,
                             &v503) )
  {
    v65 = v425;
    v493 = 0;
    v490 = 0;
    v491 = 0;
    v492 = 0;
    if ( !CCbsSession::IsOSFeatureUpdate(this)
      && v235 == 2
      && *((_BYTE *)v65 + 140)
      && (*((_DWORD *)v50 + 35) == 6 || *((_DWORD *)v50 + 34) != 4) )
    {
      v66 = DuplicateParserString(a4, (const struct _LUTF8_STRING *)(v65 + 5), &v339);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1375;
        goto LABEL_454;
      }
      v66 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v50 + 40), &v344);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1380;
        goto LABEL_454;
      }
      v66 = SczAllocFromSz(&v490, v339);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1382;
        goto LABEL_454;
      }
      v66 = SczAllocFromSz((char *)&v490 + 8, v344);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1384;
        goto LABEL_454;
      }
      if ( !Windows::StringUtil::IsEmpty((Windows::StringUtil *)((char *)v65 + 104), v67) )
      {
        v66 = DuplicateParserString(a4, (const struct _LUTF8_STRING *)((char *)v65 + 104), &v342);
        ServicingDirectory = v66;
        if ( v66 < 0 )
        {
          v139 = 1392;
          goto LABEL_454;
        }
        v66 = SczAllocCombinePath2Sz((char *)&v492 + 8, v338, v342);
        ServicingDirectory = v66;
        if ( v66 < 0 )
        {
          v139 = 1398;
LABEL_454:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v139,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)(unsigned int)v66,
            (int)DirCount);
          MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v490);
          goto LABEL_447;
        }
        v297 = *((_QWORD *)&v492 + 1);
        LogAdapter::TraceAtLevel<wchar_t *>(1, "ActionList: Using TurboContainer: {}", &v297);
      }
    }
    else
    {
      v66 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v50 + 40), &v339);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1407;
        goto LABEL_454;
      }
      v66 = SczAllocFromSz(&v490, v339);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1409;
        goto LABEL_454;
      }
      v66 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v50 + 40), &v344);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1411;
        goto LABEL_454;
      }
      v66 = SczAllocFromSz((char *)&v490 + 8, v344);
      ServicingDirectory = v66;
      if ( v66 < 0 )
      {
        v139 = 1413;
        goto LABEL_454;
      }
    }
    v66 = SczAllocFormatted(&v491, L"%ws%ws", v338, (_QWORD)v490);
    ServicingDirectory = v66;
    if ( v66 < 0 )
    {
      v139 = 1421;
      goto LABEL_454;
    }
    CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::SwapOntoBack(v390, &v490);
    MultiplePayloadsforPackage::~MultiplePayloadsforPackage((MultiplePayloadsforPackage *)&v490);
    v425 = (__int128 *)*((_QWORD *)v425 + 16);
  }
  v68 = *((_DWORD *)v50 + 34);
  v69 = v235;
  v70 = 64;
  if ( ((v68 - 2) & 0xFFFFFFFD) != 0 )
    v70 = v245 != 0 ? 64 : 112;
  v243 = v70;
  if ( *((_DWORD *)v50 + 35) == 6 && v235 == 2 && v68 != 4 && *((_BYTE *)v50 + 307) )
  {
    v63 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v50 + 88), &v339);
    ServicingDirectory = v63;
    if ( v63 < 0 )
    {
      v122 = 1436;
      goto LABEL_445;
    }
    v63 = SczAllocFormatted((char *)this + 2344, L"%ws%ws", v338, v339);
    ServicingDirectory = v63;
    if ( v63 < 0 )
    {
      v122 = 1440;
      goto LABEL_445;
    }
  }
  if ( (unsigned int)(*((_DWORD *)v50 + 35) - 6) <= 1 )
  {
    v343 = 0;
    ReserveManager = CCbsSession::GetReserveManager(this, &v343);
    if ( ReserveManager != -2146498192 )
      LogAdapter::TraceAtLevelIfFailed<long,>(1, ReserveManager, "Unable to get reserve manager.");
    if ( v343 )
    {
      if ( !(*(unsigned __int8 (__fastcall **)(struct IUpdateReserveManagerCBS *))(*(_QWORD *)v343 + 160LL))(v343) )
      {
        LogAdapter::TraceAtLevel<>(1, "UpdateReserveManager available; checking if reserves should be used...");
        v419 = 0;
        v72 = (*(unsigned int (__fastcall **)(struct IUpdateReserveManagerCBS *, wchar_t *, int *))(*(_QWORD *)v343
                                                                                                  + 104LL))(
                v343,
                v338,
                &v419);
        LogAdapter::TraceAtLevelIfFailed<long,>(1, v72, "Unable to get the scenario of the sandbox");
        if ( (int)v72 >= 0 )
        {
          if ( v419 != 4 )
          {
            v73 = "The current quality update is not using the reserves";
            goto LABEL_216;
          }
          ServicingDirectory = (*(__int64 (__fastcall **)(struct IUpdateReserveManagerCBS *, __int64, __int64, _QWORD))(*(_QWORD *)v343 + 88LL))(
                                 v343,
                                 1,
                                 4,
                                 *((_QWORD *)this + 138));
          if ( ServicingDirectory == -2146498188 )
          {
            v73 = "Unable to set the sandbox in hard reserve as it is not empty.";
LABEL_216:
            LogAdapter::TraceAtLevel<>(1, v73);
          }
          else
          {
            if ( ServicingDirectory < 0 )
            {
              v437 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to mark the sandbox in hard reserve.");
                v286 = &v437;
                LOBYTE(v140) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v140,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v286);
              }
              v121 = (unsigned int)ServicingDirectory;
              v122 = 1511;
LABEL_446:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v122,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)v121,
                (int)DirCount);
              goto LABEL_447;
            }
            *((_DWORD *)this + 552) |= 0x4000u;
          }
        }
      }
    }
  }
  v74 = v392;
  v75 = 1;
  v76 = &v392[7 * v391];
  v241 = 1;
  *(_QWORD *)v249 = v76;
  v233 = 0;
  while ( v74 != v76 )
  {
    if ( (v69 & 0xFFFFFFFB) == 0 )
    {
      ServicingDirectory = CCbsSession::CreateSessionSandbox(this, *((void **)this + 141), *v74, v74 + 4);
      if ( ServicingDirectory < 0 )
      {
        v477 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create sandbox.");
          v324 = &v477;
          LOBYTE(v181) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v181,
            3,
            (unsigned int)": {}",
            (__int64)&v324);
        }
        v121 = (unsigned int)ServicingDirectory;
        v122 = 1551;
        goto LABEL_446;
      }
      v77 = v239;
      v75 = 0;
      v241 = 0;
      if ( *((_DWORD *)v239 + 35) == 11 )
      {
        v384 = 0;
        v350 = 0;
        Str = 0;
        v78 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v239 + 176), &v350);
        ServicingDirectory = v78;
        if ( v78 < 0 )
        {
          v143 = 1573;
          goto LABEL_578;
        }
        v78 = DuplicateParserString(a4, v239, &Str);
        ServicingDirectory = v78;
        if ( v78 < 0 )
        {
          v143 = 1575;
          goto LABEL_578;
        }
        v78 = SczAllocFormatted(&v384, L"%ws.esd", v350);
        ServicingDirectory = v78;
        if ( v78 < 0 )
        {
          v143 = 1577;
LABEL_578:
          v142 = (unsigned int)v78;
LABEL_579:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v143,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)v142,
            (int)DirCount);
          goto LABEL_580;
        }
        if ( !(unsigned int)_o__wcsicmp(v384, *v74) || wcsstr(Str, L"_layercake_overlay") )
        {
          v385 = 0;
          ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Staging", &v385);
          if ( ServicingDirectory < 0 )
          {
            v478 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to get Staging directory path for unmanifested files.");
              *(_QWORD *)v323 = &v478;
              LOBYTE(v180) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v180,
                3,
                (unsigned int)": {}",
                (__int64)v323);
            }
            v146 = 1585;
            goto LABEL_572;
          }
          if ( (unsigned __int8)DoesDirectoryExist(v385, 0) )
          {
            ServicingDirectory = RecursiveRemoveDirectory(1, v385);
            if ( ServicingDirectory < 0 )
            {
              v434 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v282 = v385;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to clean staging directory {} for unmanifested files.",
                  (__int64)&v282);
                v281 = &v434;
                LOBYTE(v145) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v145,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v281);
              }
              v146 = 1591;
LABEL_572:
              v178 = (unsigned int)ServicingDirectory;
              goto LABEL_573;
            }
          }
          ServicingDirectory = RecursivelyCreateDirectory(v385, 0);
          if ( ServicingDirectory < 0 )
          {
            v479 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              v321 = v385;
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to create staging directory {} for unmanifested files.",
                (__int64)&v321);
              v322 = &v479;
              LOBYTE(v179) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v179,
                3,
                (unsigned int)": {}",
                (__int64)&v322);
            }
            v146 = 1596;
            goto LABEL_572;
          }
          if ( a2 < 0 )
          {
            LogAdapter::TraceAtLevel<>(1, "Extracting Payload CIMs from ESD.");
            CCbsStringArray::CCbsStringArray((CCbsStringArray *)v496);
            ServicingDirectory = CbsEsdEnumerateFiles(
                                   3u,
                                   v74[2],
                                   3u,
                                   L"windows\\winsxs\\cims\\",
                                   v385,
                                   L"payload*",
                                   (struct CCbsStringArray *)v496);
            if ( ServicingDirectory >= 0 )
            {
              v388 = 0;
              ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Staging\\Cims", &v388);
              if ( ServicingDirectory < 0 )
              {
                v488 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get staging root directory path for payload Cims.");
                  *(_QWORD *)v269 = &v488;
                  LOBYTE(v158) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v158,
                    3,
                    (unsigned int)": {}",
                    (__int64)v269);
                }
                v157 = 1618;
              }
              else
              {
                ServicingDirectory = RecursivelyCreateDirectory(v388, 0);
                if ( ServicingDirectory >= 0 )
                {
                  v79 = v498;
                  v80 = &v498[v497];
                  while ( v79 != v80 )
                  {
                    v395 = 0;
                    v81 = SczAllocCombinePath2Sz(&v395, L"windows\\winsxs\\cims\\", *v79);
                    ServicingDirectory = v81;
                    if ( v81 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x65F,
                        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                        (const char *)(unsigned int)v81,
                        (int)DirCount);
                      goto LABEL_483;
                    }
                    v396 = 0;
                    memset_0(Ext, 0, sizeof(Ext));
                    if ( _wsplitpath_s(*v79, 0, 0, 0, 0, 0, 0, Ext, 0x100u) || (unsigned int)_o__wcsicmp(Ext, L".cim") )
                    {
                      v86 = SczAllocCombinePath2Sz(&v396, v388, *v79);
                      ServicingDirectory = v86;
                      if ( v86 < 0 )
                      {
                        v85 = (unsigned int)v86;
                        v84 = 1655;
                        goto LABEL_253;
                      }
                      ServicingDirectory = RecursivelyCreateDirectory(v396, 0);
                      if ( ServicingDirectory < 0 )
                      {
                        v431 = ServicingDirectory;
                        if ( LogAdapter::g_Logger )
                        {
                          v278 = v396;
                          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                            (_DWORD)LogAdapter::g_Logger,
                            0,
                            3,
                            (unsigned int)"Failed to create staging directory {} for cim payload.",
                            (__int64)&v278);
                          v277 = &v431;
                          LOBYTE(v148) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v148,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v277);
                        }
                        v84 = 1659;
LABEL_252:
                        v85 = (unsigned int)ServicingDirectory;
LABEL_253:
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)v84,
                          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                          (const char *)v85,
                          (int)DirCount);
                        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v396);
LABEL_483:
                        v149 = &v395;
                        goto LABEL_484;
                      }
                      v87 = SczEnsureBackslashTerminated(&v395);
                      ServicingDirectory = v87;
                      if ( v87 < 0 )
                      {
                        v85 = (unsigned int)v87;
                        v84 = 1661;
                        goto LABEL_253;
                      }
                      ServicingDirectory = CbsEsdExtractDirectory(v74[2], 3u, v396, v395, 1);
                      if ( ServicingDirectory < 0 )
                      {
                        v432 = ServicingDirectory;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed to extract cim payload from ESD.");
                          v279 = &v432;
                          LOBYTE(v147) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v147,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v279);
                        }
                        v84 = 1669;
                        goto LABEL_252;
                      }
                    }
                    else
                    {
                      SingleFile = CbsEsdExtractSingleFile(v74[2], 3u, v388, v395, 1);
                      ServicingDirectory = SingleFile;
                      if ( SingleFile < 0 )
                      {
                        v433 = SingleFile;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed to extract cim payload file from ESD");
                          *(_QWORD *)v280 = &v433;
                          LOBYTE(v83) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v83,
                            3,
                            (unsigned int)": {}",
                            (__int64)v280);
                        }
                        v84 = 1647;
                        goto LABEL_252;
                      }
                    }
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v396);
                    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v395);
                    ++v79;
                  }
                  v405 = 0;
                  ServicingDirectory = CCbsSession::GetServicingDirectory(this, L"Staging\\", &v405);
                  if ( ServicingDirectory < 0 )
                  {
                    v453 = ServicingDirectory;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        LogAdapter::g_Logger,
                        0,
                        3,
                        "Failed to get staging root directory path for payload cims catalog.");
                      *(_QWORD *)v272 = &v453;
                      LOBYTE(v155) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v155,
                        3,
                        (unsigned int)": {}",
                        (__int64)v272);
                    }
                    v151 = 1678;
                  }
                  else
                  {
                    ServicingDirectory = CbsEsdExtractSingleFile(
                                           v74[2],
                                           3u,
                                           v405,
                                           L"windows\\system32\\CatRoot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}\\microsoft"
                                            "-windows-cimcatalog.cat",
                                           1);
                    if ( ServicingDirectory < 0 )
                    {
                      v458 = ServicingDirectory;
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(
                          LogAdapter::g_Logger,
                          0,
                          3,
                          "Failed to extract cat file from ESD");
                        v273 = &v458;
                        LOBYTE(v154) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v154,
                          3,
                          (unsigned int)": {}",
                          (__int64)&v273);
                      }
                      v151 = 1686;
                    }
                    else
                    {
                      LogAdapter::TraceAtLevel<>(1, "Extracting completed.");
                      ValidateCimPayloadFiles(v388);
                      LogAdapter::TraceAtLevel<>(1, "CIM validation completed.");
                      if ( Windows::AutoNewPtr<CimSetup>::Allocate<>((char *)this + 2456) )
                      {
                        ServicingDirectory = CimSetup::Initialize(*((CimSetup **)this + 307), v388, 0);
                        if ( ServicingDirectory < 0 )
                        {
                          v464 = ServicingDirectory;
                          if ( LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<>(
                              LogAdapter::g_Logger,
                              0,
                              3,
                              "Failed to setup the environment for cimbased update");
                            v275 = &v464;
                            LOBYTE(v152) = 1;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              (_DWORD)LogAdapter::g_Logger,
                              v152,
                              3,
                              (unsigned int)": {}",
                              (__int64)&v275);
                          }
                          v151 = 1700;
                        }
                        else
                        {
                          ServicingDirectory = CCbsSession::SetEnhancedOptions(this, 0x80000u);
                          if ( ServicingDirectory >= 0 )
                          {
                            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v405);
                            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v388);
                            CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v496);
                            v77 = v239;
                            goto LABEL_265;
                          }
                          v465 = ServicingDirectory;
                          if ( LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<>(
                              LogAdapter::g_Logger,
                              0,
                              3,
                              "Failed to set the enhanced option on the session.");
                            v276 = &v465;
                            LOBYTE(v150) = 1;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                              (_DWORD)LogAdapter::g_Logger,
                              v150,
                              3,
                              (unsigned int)": {}",
                              (__int64)&v276);
                          }
                          v151 = 1704;
                        }
                      }
                      else
                      {
                        ServicingDirectory = -2147024882;
                        v463 = -2147024882;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed to allocate CimSetup helper.");
                          v274 = &v463;
                          LOBYTE(v153) = 1;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v153,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v274);
                        }
                        v151 = 1696;
                      }
                    }
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v151,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                    (const char *)(unsigned int)ServicingDirectory,
                    (int)DirCount);
                  v149 = &v405;
LABEL_484:
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v149);
LABEL_508:
                  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v388);
LABEL_512:
                  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(v496);
                  goto LABEL_574;
                }
                v489 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  v271 = v388;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    (_DWORD)LogAdapter::g_Logger,
                    0,
                    3,
                    (unsigned int)"Failed to create staging directory {} for cim payload.",
                    (__int64)&v271);
                  v270 = &v489;
                  LOBYTE(v156) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v156,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v270);
                }
                v157 = 1622;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v157,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)ServicingDirectory,
                (int)DirCount);
              goto LABEL_508;
            }
            v487 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to enumerate cim payload directories ESD.");
              *(_QWORD *)v267 = &v487;
              LOBYTE(v159) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v159,
                3,
                (unsigned int)": {}",
                (__int64)v267);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x64D,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)ServicingDirectory,
              (int)DirCount);
            goto LABEL_512;
          }
LABEL_265:
          Str = 0;
          v88 = DuplicateParserString(a4, v77, &Str);
          ServicingDirectory = v88;
          if ( v88 < 0 )
          {
            v178 = (unsigned int)v88;
            v146 = 1708;
LABEL_573:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v146,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)v178,
              (int)DirCount);
            goto LABEL_574;
          }
          v353 = 0;
          v354 = 0;
          v349 = 0;
          v355 = 0;
          v348 = 0;
          ServicingDirectory = ShredStringIdIntoAttributes(
                                 Str,
                                 0x7Eu,
                                 (const wchar_t **)&v353,
                                 (const wchar_t **)&v354,
                                 (const wchar_t **)&v349,
                                 (const wchar_t **)&v355,
                                 (const wchar_t **)&v348);
          if ( ServicingDirectory < 0 )
          {
            v480 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                (_DWORD)LogAdapter::g_Logger,
                0,
                3,
                (unsigned int)"Failed to shred string ID: {}",
                (__int64)&Str);
              v320 = &v480;
              LOBYTE(v177) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v177,
                3,
                (unsigned int)": {}",
                (__int64)&v320);
            }
            v146 = 1724;
            goto LABEL_572;
          }
          v386 = 0;
          LODWORD(DirCount) = (_DWORD)v348;
          v89 = SczAllocFormatted(&v386, L"%ws~31bf3856ad364e35~%ws~~%ws", *((_QWORD *)this + 280), v349);
          ServicingDirectory = v89;
          if ( v89 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6C5,
              (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
              (const char *)(unsigned int)v89,
              (int)DirCount);
LABEL_561:
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v386);
LABEL_574:
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v385);
LABEL_580:
            v138 = (wchar_t **)&v384;
            goto LABEL_443;
          }
          if ( !(unsigned __int8)CCbsSession::IsSessionEnhancedOptionSet(this, 0x80000) )
          {
            v407 = 0;
            v406 = 0;
            v90 = SczAllocFormatted(&v407, L"windows\\servicing\\packages\\%ws.mum", v386);
            ServicingDirectory = v90;
            if ( v90 < 0 )
            {
              v162 = 1745;
              goto LABEL_521;
            }
            v90 = SczAllocFormatted(&v406, L"windows\\servicing\\packages\\%ws.cat", v386);
            ServicingDirectory = v90;
            if ( v90 < 0 )
            {
              v162 = 1751;
LABEL_521:
              v161 = (unsigned int)v90;
LABEL_522:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v162,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)v161,
                (int)DirCount);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v406);
              p_lpNewFileName = &v407;
              goto LABEL_523;
            }
            ServicingDirectory = CbsEsdExtractSingleFile(v74[2], 3u, v74[4], v406, 1);
            if ( ServicingDirectory < 0 )
            {
              v485 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to extract cat file from ESD");
                v265 = &v485;
                LOBYTE(v163) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v163,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v265);
              }
              v161 = (unsigned int)ServicingDirectory;
              v162 = 1769;
              goto LABEL_522;
            }
            ServicingDirectory = CbsEsdExtractSingleFile(v74[2], 3u, v74[4], v407, 1);
            if ( ServicingDirectory < 0 )
            {
              v486 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to extract mum file from ESD");
                v266 = &v486;
                LOBYTE(v160) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v160,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v266);
              }
              v161 = (unsigned int)ServicingDirectory;
              v162 = 1777;
              goto LABEL_522;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v406);
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v407);
          }
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v74 + 2);
          if ( (unsigned __int8)CCbsSession::IsSessionEnhancedOptionSet(this, 0x80000) )
          {
            v402 = 0;
            v404 = 0;
            ServicingDirectory = CCbsSession::GetPackageStoreDirectory(this, &v404);
            if ( ServicingDirectory < 0 )
            {
              v481 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get the packages directory");
                *(_QWORD *)v261 = &v481;
                LOBYTE(v168) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v168,
                  3,
                  (unsigned int)": {}",
                  (__int64)v261);
              }
              v94 = 1793;
LABEL_534:
              v167 = (unsigned int)ServicingDirectory;
LABEL_535:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v94,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)v167,
                (int)DirCount);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v404);
              p_lpNewFileName = &v402;
              goto LABEL_523;
            }
            v91 = SczAllocFormatted(v74 + 2, L"%ws%ws.mum", v404, v386);
            ServicingDirectory = v91;
            if ( v91 < 0 )
            {
              v167 = (unsigned int)v91;
              v94 = 1800;
              goto LABEL_535;
            }
            if ( (unsigned int)CCbsSession::IsOffline(this) )
            {
              OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(this, &v402);
              ServicingDirectory = OfflineWindowsDirectory;
              if ( OfflineWindowsDirectory < 0 )
              {
                v484 = OfflineWindowsDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get offline Windir.");
                  v264 = &v484;
                  LOBYTE(v93) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v93,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v264);
                }
                v94 = 1806;
                goto LABEL_534;
              }
            }
            else
            {
              ServicingDirectory = PathGetWindowsDirectory(&v402, 0);
              if ( ServicingDirectory < 0 )
              {
                v482 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get online Windir.");
                  v262 = &v482;
                  LOBYTE(v166) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v166,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v262);
                }
                v94 = 1812;
                goto LABEL_534;
              }
            }
            ServicingDirectory = CCbsSession::AddSource(this, 1, 0, v402, 0);
            if ( ServicingDirectory < 0 )
            {
              v483 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding payload path source");
                v263 = &v483;
                LOBYTE(v165) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v165,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v263);
              }
              v94 = 1817;
              goto LABEL_534;
            }
            v95 = &v402;
            v96 = &v404;
          }
          else
          {
            lpNewFileName = 0;
            v97 = SczAllocFormatted(&lpNewFileName, L"%wsupdate.cat", v74[4]);
            ServicingDirectory = v97;
            if ( v97 < 0 )
            {
              v176 = 1824;
              goto LABEL_558;
            }
            v97 = SczAllocFormatted(v74 + 2, L"%wsupdate.mum", v74[4]);
            ServicingDirectory = v97;
            if ( v97 < 0 )
            {
              v176 = 1830;
LABEL_558:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v176,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)v97,
                (int)DirCount);
              goto LABEL_559;
            }
            v400 = 0;
            lpExistingFileName = 0;
            v98 = SczAllocFormatted(&v400, L"%ws%ws.mum", v74[4], v386);
            ServicingDirectory = v98;
            if ( v98 < 0 )
            {
              v175 = 1840;
              goto LABEL_554;
            }
            v98 = SczAllocFormatted(&lpExistingFileName, L"%ws%ws.cat", v74[4], v386);
            ServicingDirectory = v98;
            if ( v98 < 0 )
            {
              v175 = 1847;
LABEL_554:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v175,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                (const char *)(unsigned int)v98,
                (int)DirCount);
              goto LABEL_555;
            }
            if ( !MoveFileW(lpExistingFileName, lpNewFileName) )
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                v317 = lpNewFileName;
                v318 = lpExistingFileName;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to move file from: {} to {}",
                  (__int64)&v318,
                  (__int64)&v317);
                if ( LastError > 0 )
                  v174 = (unsigned __int16)LastError | 0x80070000;
                else
                  v174 = LastError;
                v247 = v174;
                LOBYTE(v173) = 1;
                *(_QWORD *)v319 = &v247;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v173,
                  3,
                  (unsigned int)": {0}",
                  (__int64)v319);
              }
              if ( !LastError )
                goto LABEL_551;
              v172 = 1853;
LABEL_550:
              ServicingDirectory = wil::details::in1diag3::Return_Win32(
                                     retaddr,
                                     (void *)v172,
                                     (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                                     (const char *)(unsigned int)LastError,
                                     (unsigned int)DirCount);
LABEL_555:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v400);
LABEL_559:
              p_lpNewFileName = &lpNewFileName;
LABEL_523:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(p_lpNewFileName);
              goto LABEL_561;
            }
            if ( !MoveFileW(v400, v74[2]) )
            {
              LastError = GetLastError();
              if ( LogAdapter::g_Logger )
              {
                v260 = v74[2];
                v315 = v400;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to move file from: {} to {}",
                  (__int64)&v315,
                  (__int64)&v260);
                if ( LastError > 0 )
                  v171 = (unsigned __int16)LastError | 0x80070000;
                else
                  v171 = LastError;
                v246 = v171;
                LOBYTE(v170) = 1;
                v316 = &v246;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v170,
                  3,
                  (unsigned int)": {0}",
                  (__int64)&v316);
              }
              if ( LastError )
              {
                v172 = 1859;
                goto LABEL_550;
              }
LABEL_551:
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v400);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v386);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v385);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v384);
              CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v390);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v382);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v383);
              ServicingDirectory = 0;
              goto LABEL_698;
            }
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
            v96 = &v400;
            v95 = &lpNewFileName;
          }
          v75 = 4;
          v241 = 4;
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v96);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v95);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v386);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v385);
        }
        else if ( *((_DWORD *)v239 + 34) == 3 )
        {
          if ( a2 < 0 )
          {
            v296 = v74[2];
            LogAdapter::TraceAtLevel<wchar_t *>(1, "Skipping expansion of the package {}", &v296);
          }
          else
          {
            ServicingDirectory = DpxExtractAllFilesFromCabinet(v74[2], v74[4]);
            if ( ServicingDirectory < 0 )
            {
              v435 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v284 = v74[2];
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed to extract all files from the container {}",
                  (__int64)&v284);
                v283 = &v435;
                LOBYTE(v144) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v144,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v283);
              }
              v142 = (unsigned int)ServicingDirectory;
              v143 = 1875;
              goto LABEL_579;
            }
            ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v74[4], 0);
            if ( ServicingDirectory < 0 )
            {
              v436 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding payload path source");
                v285 = &v436;
                LOBYTE(v141) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v141,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v285);
              }
              v142 = (unsigned int)ServicingDirectory;
              v143 = 1886;
              goto LABEL_579;
            }
          }
          v233 = 1;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v384);
      }
      v76 = *(wchar_t ***)v249;
      v69 = v235;
    }
    v74 += 7;
  }
  if ( *((_DWORD *)v239 + 34) == 3 )
  {
    v99 = 0;
    if ( v233 )
      goto LABEL_138;
    v100 = v392;
    v101 = &v392[7 * v391];
    while ( v100 != v101 )
    {
      if ( (unsigned __int8)Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::IsValid(v100 + 1) )
      {
        v63 = SczAllocFormatted(v100 + 3, L"%ws%ws", v338, v100[1]);
        ServicingDirectory = v63;
        if ( v63 < 0 )
        {
          v122 = 1919;
          goto LABEL_445;
        }
        ServicingDirectory = CCbsSession::AddSource(this, 1, 2 * (a2 & 1u), v100[3], 0);
        if ( ServicingDirectory < 0 )
        {
          v476 = ServicingDirectory;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed adding payload path source");
            v325 = &v476;
            LOBYTE(v182) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v182,
              3,
              (unsigned int)": {}",
              (__int64)&v325);
          }
          v121 = (unsigned int)ServicingDirectory;
          v122 = 1923;
          goto LABEL_446;
        }
        v99 = 1;
      }
      v100 += 7;
    }
    if ( v99 )
      goto LABEL_138;
    v75 = v241;
  }
  if ( a6 && v75 == 1 )
  {
    v102 = v392;
    v103 = &v392[7 * v391];
    v399 = 0;
    while ( v102 != v103 )
    {
      v104 = SczAllocFromSz(&v399, v102[2]);
      ServicingDirectory = v104;
      if ( v104 < 0 )
      {
        v183 = 1943;
LABEL_591:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v183,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)(unsigned int)v104,
          (int)DirCount);
        v138 = (wchar_t **)&v399;
LABEL_443:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v138);
        goto LABEL_447;
      }
      v104 = SczEnsureBackslashTerminated(&v399);
      ServicingDirectory = v104;
      if ( v104 < 0 )
      {
        v183 = 1945;
        goto LABEL_591;
      }
      v104 = SczAllocConcatSz(&v399, L"update.mum");
      ServicingDirectory = v104;
      if ( v104 < 0 )
      {
        v183 = 1947;
        goto LABEL_591;
      }
      if ( !(unsigned int)DoesFileExist(v399, 0) )
      {
        LogAdapter::TraceAtLevel<>(1, "Ignoring missing files in case of installation after reboot");
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v399);
        goto LABEL_138;
      }
      v102 += 7;
    }
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v399);
  }
  v105 = v392;
  v106 = &v392[7 * v391];
  while ( 1 )
  {
    if ( v105 == v106 )
    {
      v112 = v392;
      v113 = 0;
      while ( v112 != &v392[7 * v391] )
      {
        if ( *((_BYTE *)v112[6] + 1057) )
        {
          v113 = 1;
          break;
        }
        v112 += 7;
      }
      if ( !(unsigned int)CCbsSession::IsOffline(this) && v113 && !a6 )
      {
        *(_QWORD *)v508 = 0;
        v510 = 0;
        v509 = 0;
        v511 = 0;
        if ( v237 )
          goto LABEL_349;
        DirCount = v508;
        if ( (int)CCbsSession::GetStoreObject(this, 0, 14) >= 0
          || (DirCount = v508, (int)CCbsSession::GetStoreObject(this, 0, 15) >= 0) )
        {
          v237 = 1;
LABEL_349:
          *((_BYTE *)this + 2273) = 1;
          v114 = SczAllocFromSz((char *)this + 2280, v338);
          ServicingDirectory = v114;
          if ( v114 >= 0 )
          {
            LogAdapter::TraceAtLevel<>(1, "Scheduling installation of packages after reboot");
            CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v508);
            goto LABEL_138;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85D,
            (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
            (const char *)(unsigned int)v114,
            (int)DirCount);
          CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v508);
          goto LABEL_447;
        }
        CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)v508);
      }
      v115 = v392;
      v116 = &v392[7 * v391];
      while ( v115 != v116 )
      {
        if ( (unsigned __int8)Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::IsValid(v115 + 1) )
        {
          v117 = (const wchar_t **)(v115 + 3);
          v63 = SczAllocFormatted(v115 + 3, L"%ws%ws", v338, v115[1]);
          ServicingDirectory = v63;
          if ( v63 < 0 )
          {
            v122 = 2169;
            goto LABEL_445;
          }
          v118 = 2 * (a2 & 1);
          if ( (unsigned __int8)DoesDirectoryExist(*v117, 0) )
          {
            ServicingDirectory = CCbsSession::AddSource(this, 1, v118, *v117, 0);
            if ( ServicingDirectory < 0 )
            {
              v466 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v250 = *v117;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed adding payload path source: {}",
                  (__int64)&v250);
                v251 = &v466;
                LOBYTE(v194) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v194,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v251);
              }
              v121 = (unsigned int)ServicingDirectory;
              v122 = 2177;
              goto LABEL_446;
            }
            v119 = CCbsPackage::SetPayloadPath((CCbsPackage *)v115[6], *v117);
            ServicingDirectory = v119;
            if ( v119 < 0 )
            {
              v467 = v119;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to set payload path for package");
                v337 = &v467;
                LOBYTE(v120) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v120,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v337);
              }
              v121 = (unsigned int)ServicingDirectory;
              v122 = 2184;
              goto LABEL_446;
            }
          }
          else if ( *((_BYTE *)this + 2254) && v235 == 4 && (unsigned __int8)DoesDirectoryExist(v115[4], 0) )
          {
            ServicingDirectory = CCbsSession::AddSource(this, 1, v118, v115[4], 0);
            if ( ServicingDirectory < 0 )
            {
              v461 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                v253 = v115[4];
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"Failed adding CBS sandbox as source for GDR package: {}",
                  (__int64)&v253);
                v268 = &v461;
                LOBYTE(v196) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v196,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v268);
              }
              v121 = (unsigned int)ServicingDirectory;
              v122 = 2196;
              goto LABEL_446;
            }
            ServicingDirectory = CCbsPackage::SetPayloadPath((CCbsPackage *)v115[6], v115[4]);
            if ( ServicingDirectory < 0 )
            {
              v462 = ServicingDirectory;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed adding CBS sandbox as source for GDR package");
                v252 = &v462;
                LOBYTE(v195) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v195,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v252);
              }
              v121 = (unsigned int)ServicingDirectory;
              v122 = 2203;
              goto LABEL_446;
            }
          }
        }
        v115 += 7;
      }
      v123 = v239;
      v124 = 16 * (a2 & 1) + 1;
      v125 = *((_DWORD *)v239 + 34);
      if ( (v125 == 4 || v242) && (v124 |= 0x200u, v125 == 4) )
      {
        v124 |= 0x80000u;
      }
      else if ( v125 == 5 )
      {
        v124 |= 0x100u;
      }
      if ( *((_DWORD *)v239 + 35) == 7 )
      {
        v126 = v392;
        v127 = &v392[7 * v391];
        while ( 1 )
        {
          if ( v126 == v127 )
          {
            v123 = v239;
            break;
          }
          v393 = 4096;
          v415 = 4096;
          ServicingDirectory = CCbsPackage::GetCurrentStateConsideringSmartPending(
                                 (CCbsPackage *)v126[6],
                                 this,
                                 (enum CbsState *)&v393);
          if ( ServicingDirectory < 0 )
          {
            v459 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting current state");
              v255 = &v459;
              LOBYTE(v198) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v198,
                3,
                (unsigned int)": {}",
                (__int64)&v255);
            }
            v121 = (unsigned int)ServicingDirectory;
            v122 = 2251;
            goto LABEL_446;
          }
          ServicingDirectory = CCbsPackage::GetApplicableState((CCbsPackage *)v126[6], this, 0, (enum CbsState *)&v415);
          if ( ServicingDirectory < 0 )
          {
            v460 = ServicingDirectory;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get applicable state");
              v254 = &v460;
              LOBYTE(v197) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v197,
                3,
                (unsigned int)": {}",
                (__int64)&v254);
            }
            v121 = (unsigned int)ServicingDirectory;
            v122 = 2255;
            goto LABEL_446;
          }
          v128 = v393;
          v129 = v393 < 96;
          if ( v393 == 96 )
          {
            if ( !v231 && !v232 )
            {
LABEL_400:
              IdentityFast = CCbsPackage::GetIdentityFast((CCbsPackage *)v126[6]);
              LogAdapter::TraceAtLevel<wchar_t const *>(1, "Skipping already installed SSU: {}", &IdentityFast);
              goto LABEL_138;
            }
            if ( !(unsigned int)CCbsSession::IsOffline(this) )
            {
              v290 = CCbsPackage::GetIdentityFast((CCbsPackage *)v126[6]);
              LogAdapter::TraceAtLevel<wchar_t const *>(1, "SSU is pending, need to skip other actions: {}", &v290);
              *((_DWORD *)this + 552) |= 0x40000u;
LABEL_398:
              v230 = 1;
              goto LABEL_399;
            }
            v128 = v393;
            v129 = v393 < 96;
          }
          if ( !v129 && v128 != 4096 )
            goto LABEL_400;
          if ( v128 != v415 )
          {
            if ( !v245 && (v231 || v232) )
            {
              if ( !(unsigned int)CCbsSession::IsOffline(this) && (unsigned int)PackageStoreIsPendingRequired(0, 0, 0) )
              {
                v289 = CCbsPackage::GetIdentityFast((CCbsPackage *)v126[6]);
                LogAdapter::TraceAtLevel<wchar_t const *>(
                  1,
                  "SSU will pend. Setting IncompleteSetOfActions. Package: {}",
                  &v289);
                *((_DWORD *)this + 552) |= 0x40000u;
              }
              v128 = v393;
            }
            if ( v243 != 64 || v128 != 64 )
              goto LABEL_398;
          }
LABEL_399:
          v126 += 7;
        }
      }
      if ( v235 == 2 && *((_BYTE *)v123 + 307) && *((_DWORD *)v123 + 34) != 4 )
      {
        v63 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v123 + 88), &v339);
        ServicingDirectory = v63;
        if ( v63 < 0 )
        {
          v122 = 2323;
LABEL_445:
          v121 = (unsigned int)v63;
          goto LABEL_446;
        }
      }
      else
      {
        v63 = DuplicateParserString(a4, (struct ActionListParser::InstallPackage *)((char *)v123 + 40), &v339);
        ServicingDirectory = v63;
        if ( v63 < 0 )
        {
          v122 = 2332;
          goto LABEL_445;
        }
      }
      LogAdapter::TraceAtLevel<wchar_t const *,wchar_t *>(1, "ActionList: Adding package: {}{}", &v338, &v339);
      if ( v231 && v232 && (v240 == 1 || (unsigned int)(v240 - 4) <= 1) )
      {
        v130 = *((_DWORD *)v123 + 34);
        if ( (v130 & 0xFFFFFFFA) == 0 && v130 != 1 )
        {
          v131 = v392;
          v132 = &v392[7 * v391];
          while ( 1 )
          {
            if ( v131 == v132 )
              goto LABEL_430;
            v287 = CCbsPackage::GetIdentityFast((CCbsPackage *)v131[6]);
            LogAdapter::TraceAtLevel<wchar_t const *>(1, "ActionList: Add package: {} for reservicing", &v287);
            v133 = *((_DWORD *)v239 + 34);
            if ( v133 == 4 )
            {
              *(wchar_t *)((char *)v131[6] + 1061) = 257;
            }
            else if ( v133 == 5 )
            {
              *((_BYTE *)v131[6] + 1062) = 1;
            }
            if ( *((_DWORD *)v239 + 35) == 6 && *((_QWORD *)v239 + 33) > 1u )
              *((_BYTE *)this + 2255) = 1;
            ServicingDirectory = CCbsSession::AddLCUOrGDRToInstall(this, (struct CCbsPackage *)v131[6]);
            if ( ServicingDirectory < 0 )
              break;
            v131 += 7;
          }
          v457 = ServicingDirectory;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
            v314 = &v457;
            LOBYTE(v199) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v199,
              3,
              (unsigned int)": {}",
              (__int64)&v314);
          }
          v121 = (unsigned int)ServicingDirectory;
          v122 = 2384;
          goto LABEL_446;
        }
      }
      if ( !v244 )
      {
        v134 = v392;
        v135 = &v392[7 * v391];
        while ( 1 )
        {
          if ( v134 == v135 )
            goto LABEL_430;
          ServicingDirectory = CCbsPackage::InitiateChanges(
                                 (__int64)v134[6],
                                 (__int64)this,
                                 *((void **)this + 141),
                                 v124,
                                 v243,
                                 1u,
                                 0,
                                 0);
          if ( ServicingDirectory < 0 )
            break;
          v134 += 7;
        }
        v456 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          v256 = v134[2];
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed Initiating changes for package: {}",
            (__int64)&v256);
          v257 = &v456;
          LOBYTE(v200) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v200,
            3,
            (unsigned int)": {}",
            (__int64)&v257);
        }
        v121 = (unsigned int)ServicingDirectory;
        v122 = 2401;
        goto LABEL_446;
      }
LABEL_430:
      v46 = v230;
      if ( v230 )
      {
        CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v390);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v382);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v383);
LABEL_432:
        if ( !v244 && (a2 & 0x4000) == 0 )
        {
          v136 = *((_QWORD *)v248 + 17);
          if ( v136 )
          {
            v137 = 0;
            v427 = *(_QWORD *)(v136 + 16);
            v504 = 0;
            while ( (unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                       &v427,
                                       &v504) )
            {
              ServicingDirectory = CCbsSession::AddFeatureToModify(this, v427, 0);
              if ( ServicingDirectory < 0 )
              {
                v455 = ServicingDirectory;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to process RemoveFeature Action");
                  v258 = &v455;
                  LOBYTE(v201) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v201,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v258);
                }
                v10 = 2445;
                goto LABEL_18;
              }
              v137 = 1;
              v427 = *(_QWORD *)(v427 + 72);
            }
            if ( !v242 )
            {
              v202 = *(_QWORD *)(*((_QWORD *)v248 + 17) + 32LL);
              v506 = 0;
              while ( 1 )
              {
                v428 = v202;
                if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                         &v428,
                                         &v506) )
                  break;
                ServicingDirectory = CCbsSession::AddFeatureToModify(this, v428, 64);
                if ( ServicingDirectory < 0 )
                {
                  v454 = ServicingDirectory;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to process DisableFeature Action");
                    v259 = &v454;
                    LOBYTE(v203) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v203,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v259);
                  }
                  v10 = 2456;
                  goto LABEL_18;
                }
                v137 = 1;
                v202 = *(_QWORD *)(v428 + 72);
              }
              v204 = **((_QWORD **)v248 + 17);
              v502 = 0;
              while ( 1 )
              {
                v429 = v204;
                if ( !(unsigned __int8)XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(
                                         &v429,
                                         &v502) )
                  break;
                ServicingDirectory = CCbsSession::AddFeatureToModify(this, v429, 112);
                if ( ServicingDirectory < 0 )
                {
                  v452 = ServicingDirectory;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to process InstallFeature Action");
                    v293 = &v452;
                    LOBYTE(v205) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v205,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v293);
                  }
                  v10 = 2464;
                  goto LABEL_18;
                }
                v137 = 1;
                v204 = *(_QWORD *)(v429 + 72);
              }
            }
            if ( !(unsigned int)CCbsSession::InspectSessionTask(this) && *((_QWORD *)v248 + 17) && v137 )
            {
              v397 = 0;
              v398 = 0;
              v414 = 4096;
              InitPointer = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v397);
              CbsIdentity = CreateCbsIdentity(InitPointer);
              ServicingDirectory = CbsIdentity;
              if ( CbsIdentity < 0 )
              {
                v451 = CbsIdentity;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to create foundation identity");
                  *(_QWORD *)v294 = &v451;
                  LOBYTE(v208) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v208,
                    3,
                    (unsigned int)": {}",
                    (__int64)v294);
                }
                v209 = 2476;
LABEL_666:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v209,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                  (const char *)(unsigned int)ServicingDirectory,
                  (int)DirCount);
                Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v398);
                v210 = &v397;
                goto LABEL_667;
              }
              v211 = (*(__int64 (__fastcall **)(struct ICbsIdentity *, const wchar_t *))(*(_QWORD *)v397 + 56LL))(
                       v397,
                       L"@Foundation");
              ServicingDirectory = v211;
              if ( v211 < 0 )
              {
                v450 = v211;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load foundation identity");
                  v295 = &v450;
                  LOBYTE(v212) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v212,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v295);
                }
                v209 = 2480;
                goto LABEL_666;
              }
              v213 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v398);
              v214 = CCbsSession::OpenPackage(this, *((void **)this + 141), 0, v397, 0, v213);
              ServicingDirectory = v214;
              if ( v214 < 0 )
              {
                v449 = v214;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open foundation package");
                  v308 = &v449;
                  LOBYTE(v215) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v215,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v308);
                }
                v209 = 2488;
                goto LABEL_666;
              }
              CurrentState = CCbsPackage::GetCurrentState(v398, this, (enum CbsState *)&v414);
              ServicingDirectory = CurrentState;
              if ( CurrentState < 0 )
              {
                v448 = CurrentState;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to get current state of foundation package");
                  v309 = &v448;
                  LOBYTE(v217) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v217,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v309);
                }
                v209 = 2492;
                goto LABEL_666;
              }
              v218 = CCbsPackage::InitiateChanges(
                       (__int64)v398,
                       (__int64)this,
                       *((void **)this + 141),
                       1u,
                       v414,
                       0,
                       0,
                       0);
              ServicingDirectory = v218;
              if ( v218 < 0 )
              {
                v447 = v218;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to initiate changes for foundation package");
                  v310 = &v447;
                  LOBYTE(v219) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v219,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v310);
                }
                v209 = 2502;
                goto LABEL_666;
              }
              Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v398);
              Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v397);
            }
          }
          if ( CCbsSession::IsOSFeatureUpdate(this) )
          {
            v408 = 0;
            v220 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v408);
            if ( CCbsSession::IsAnLCUInstalled(this, v220)
              && (unsigned __int8)Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::IsValid(&v408) )
            {
              v412 = 0;
              v221 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v412);
              v222 = CCbsSession::ResolvePackage(this, 0, *((void **)this + 141), 0, v408, 1, v221, 0);
              ServicingDirectory = v222;
              if ( v222 < 0 )
              {
                v446 = v222;
                if ( LogAdapter::g_Logger )
                {
                  FastCbsIdentityString = GetFastCbsIdentityString(v408);
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    (_DWORD)LogAdapter::g_Logger,
                    0,
                    3,
                    (unsigned int)"Failed to resolve the LCU package: {}",
                    (__int64)&FastCbsIdentityString);
                  *(_QWORD *)v312 = &v446;
                  LOBYTE(v223) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v223,
                    3,
                    (unsigned int)": {}",
                    (__int64)v312);
                }
                v224 = (unsigned int)ServicingDirectory;
                v225 = 2521;
LABEL_692:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v225,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
                  (const char *)v224,
                  DirCounta);
                Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v412);
                v210 = &v408;
LABEL_667:
                Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(v210);
                goto LABEL_698;
              }
              v313 = v412;
              v226 = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add((char *)this + 2144, &v313);
              ServicingDirectory = v226;
              if ( v226 < 0 )
              {
                v224 = (unsigned int)v226;
                v225 = 2523;
                goto LABEL_692;
              }
              *((_DWORD *)this + 173) |= 0x40000000u;
              Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v412);
            }
            Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v408);
          }
        }
        ServicingDirectory = 0;
        goto LABEL_698;
      }
      goto LABEL_139;
    }
    v389 = 0;
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v389);
    v107 = *((_QWORD *)this + 141);
    DirCount = v249;
    *(GUID *)v249 = GUID_NULL;
    ServicingDirectory = CCbsSession::CreateWindowsUpdatePackage(this, v107, 0, 0);
    if ( ServicingDirectory < 0 )
    {
      v468 = ServicingDirectory;
      if ( LogAdapter::g_Logger )
      {
        v335 = v105[2];
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to create package: {}",
          (__int64)&v335);
        *(_QWORD *)v336 = &v468;
        LOBYTE(v193) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v193,
          3,
          (unsigned int)": {}",
          (__int64)v336);
      }
      v191 = 1982;
      goto LABEL_615;
    }
    if ( v234 )
      break;
LABEL_329:
    LogAdapter::DebuggerLogger::IncludeNewline((LogAdapter::DebuggerLogger *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl);
    v56 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl'::`2'::impl) == 0;
    v110 = v239;
    if ( !v56 && *((_DWORD *)v239 + 34) == 4 && *((_DWORD *)v239 + 35) == 6 && *((_DWORD *)v239 + 66) > 1u )
    {
      v292 = CCbsPackage::GetIdentityFast(v389);
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "ActionList: Setting the partial baseline package flag for package: ({})",
        &v292);
      *(_WORD *)((char *)v389 + 1061) = 257;
      ServicingDirectory = CCbsPackage::SetParentRevisionApplicability(v389, 1);
      if ( ServicingDirectory < 0 )
      {
        v470 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          v331 = CCbsPackage::GetIdentityFast(v389);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"ActionList: Failed set parent revision applicability for package: ({})",
            (__int64)&v331);
          v332 = &v470;
          LOBYTE(v190) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v190,
            3,
            (unsigned int)": {}",
            (__int64)&v332);
        }
        v191 = 2070;
        goto LABEL_615;
      }
      v110 = v239;
    }
    if ( CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(this, v110) )
    {
      v291 = CCbsPackage::GetIdentityFast(v389);
      LogAdapter::TraceAtLevel<wchar_t const *>(
        1,
        "ActionList: Skipping parent revision level applicability for package: ({}) in WinPE",
        &v291);
      ServicingDirectory = CCbsPackage::SetParentRevisionApplicability(v389, 1);
      if ( ServicingDirectory < 0 )
      {
        v469 = ServicingDirectory;
        if ( LogAdapter::g_Logger )
        {
          v333 = CCbsPackage::GetIdentityFast(v389);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"ActionList: Failed to set parent revision applicability for package in WinPE: ({})",
            (__int64)&v333);
          v334 = &v469;
          LOBYTE(v192) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v192,
            3,
            (unsigned int)": {}",
            (__int64)&v334);
        }
        v191 = 2085;
LABEL_615:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v191,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)(unsigned int)ServicingDirectory,
          (int)DirCount);
        goto LABEL_616;
      }
    }
    v111 = (CCbsPackage *)v105[6];
    v105[6] = (wchar_t *)v389;
    v389 = v111;
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v389);
    v105 += 7;
  }
  v341 = 0;
  v403 = 0;
  v108 = DuplicateParserString(a4, v239, &v341);
  ServicingDirectory = v108;
  if ( v108 < 0 )
  {
    v185 = (unsigned int)v108;
    v186 = 2030;
    goto LABEL_605;
  }
  v109 = (struct CCbsIdentity **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v403);
  ServicingDirectory = GetCbsIdentityFromKeyForm(v341, v109);
  if ( ServicingDirectory >= 0 )
  {
    v417 = 0;
    v413 = 0;
    ServicingDirectory = CCbsIdentity::GetVersion(v403, &v417, &v413);
    if ( ServicingDirectory < 0 )
    {
      v473 = ServicingDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to get version from keyform: '{}'",
          (__int64)&v341);
        v329 = &v473;
        LOBYTE(v188) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v188,
          3,
          (unsigned int)": {}",
          (__int64)&v329);
      }
      v185 = (unsigned int)ServicingDirectory;
      v186 = 2040;
      goto LABEL_605;
    }
    v418 = 0;
    v416 = 0;
    ServicingDirectory = CCbsIdentity::GetVersion(*((CCbsIdentity **)v389 + 14), &v418, &v416);
    if ( ServicingDirectory < 0 )
    {
      v474 = ServicingDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get version from package");
        v328 = &v474;
        LOBYTE(v187) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v187,
          3,
          (unsigned int)": {}",
          (__int64)&v328);
      }
      v185 = (unsigned int)ServicingDirectory;
      v186 = 2046;
      goto LABEL_605;
    }
    if ( v417 != v418 || v413 != v416 )
    {
      ServicingDirectory = -2146498221;
      v475 = -2146498221;
      if ( LogAdapter::g_Logger )
      {
        v326 = CCbsPackage::GetIdentityFast(v389);
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"ActionList: Universal diff InstallPayload identity : ({}) does not match InstallPackage identity : ({}).",
          (__int64)&v326,
          (__int64)&v341);
        v327 = &v475;
        LOBYTE(v184) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v184,
          3,
          (unsigned int)": {}",
          (__int64)&v327);
      }
      v185 = 2148469075LL;
      v186 = 2054;
      goto LABEL_605;
    }
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v403);
    goto LABEL_329;
  }
  v472 = ServicingDirectory;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to get identity from keyform: '{}'",
      (__int64)&v341);
    v330 = &v472;
    LOBYTE(v189) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v189,
      3,
      (unsigned int)": {}",
      (__int64)&v330);
  }
  v185 = (unsigned int)ServicingDirectory;
  v186 = 2034;
LABEL_605:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v186,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
    (const char *)v185,
    (int)DirCount);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v403);
LABEL_616:
  Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v389);
LABEL_447:
  CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>::~CCbsArrayBase<MultiplePayloadsforPackage,CCbsArray<MultiplePayloadsforPackage>>(v390);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v382);
  v37 = (wchar_t **)&v383;
LABEL_93:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v37);
LABEL_698:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v495);
  return (unsigned int)ServicingDirectory;
}

```

## disassembly

```asm
0x1800dc9c0  mov     [rsp-8+arg_8], rbx
0x1800dc9c5  push    rbp
0x1800dc9c6  push    rsi
0x1800dc9c7  push    rdi
0x1800dc9c8  push    r12
0x1800dc9ca  push    r13
0x1800dc9cc  push    r14
0x1800dc9ce  push    r15
0x1800dc9d0  lea     rbp, [rsp-0A00h]
0x1800dc9d8  sub     rsp, 0B00h
0x1800dc9df  mov     rax, cs:__security_cookie
0x1800dc9e6  xor     rax, rsp
0x1800dc9e9  mov     [rbp+0A30h+var_40], rax
0x1800dc9f0  mov     rax, [rbp+0A30h+arg_20]
0x1800dc9f7  mov     r15, rcx
0x1800dc9fa  mov     [rbp+0A30h+var_770], rax
0x1800dca01  xor     edi, edi
0x1800dca03  mov     eax, edx
0x1800dca05  mov     [rbp+0A30h+var_AA8], r9
0x1800dca09  and     eax, 1000h
0x1800dca0e  mov     [rbp+0A30h+var_A78], r8
0x1800dca12  mov     ecx, edx
0x1800dca14  mov     [rsp+0B30h+var_AB4], edx
0x1800dca18  and     ecx, 400h
0x1800dca1e  mov     [rbp+0A30h+var_300], rdi
0x1800dca25  mov     [rbp+0A30h+var_A90], ecx
0x1800dca28  mov     r13, r9
0x1800dca2b  mov     [rbp+0A30h+var_A88], eax
0x1800dca2e  mov     r14, r8
0x1800dca31  test    ecx, ecx
0x1800dca33  jz      short loc_1800DCAA7
0x1800dca35  test    eax, eax
0x1800dca37  jz      loc_1800DCB1B
0x1800dca3d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dca44  mov     ebx, 80070057h
0x1800dca49  mov     [rbp+0A30h+var_3F8], ebx
0x1800dca4f  test    rcx, rcx
0x1800dca52  jz      short loc_1800DCA9D
0x1800dca54  mov     edi, 3
0x1800dca59  lea     r9, aInvalidParamet_20; "Invalid parameter: ServicingProcessorOp"...
0x1800dca60  mov     r8d, edi
0x1800dca63  xor     edx, edx
0x1800dca65  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dca6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dca71  lea     rax, [rbp+0A30h+var_3F8]
0x1800dca78  mov     [rbp+0A30h+var_890], rax
0x1800dca7f  lea     r9, asc_1802EE7AC; ": {}"
0x1800dca86  lea     rax, [rbp+0A30h+var_890]
0x1800dca8d  mov     r8d, edi
0x1800dca90  lea     edx, [rdi-2]
0x1800dca93  mov     [rsp+0B30h+DirCount], rax
0x1800dca98  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dca9d  mov     edx, 37Ch
0x1800dcaa2  jmp     loc_1800DCBBA
0x1800dcaa7  test    eax, eax
0x1800dcaa9  jz      short loc_1800DCB1B
0x1800dcaab  bt      edx, 0Dh
0x1800dcaaf  jnb     short loc_1800DCB1B
0x1800dcab1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcab8  mov     ebx, 80070057h
0x1800dcabd  mov     [rbp+0A30h+var_3FC], ebx
0x1800dcac3  test    rcx, rcx
0x1800dcac6  jz      short loc_1800DCB11
0x1800dcac8  mov     edi, 3
0x1800dcacd  lea     r9, aInvalidParamet_20; "Invalid parameter: ServicingProcessorOp"...
0x1800dcad4  mov     r8d, edi
0x1800dcad7  xor     edx, edx
0x1800dcad9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dcade  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcae5  lea     rax, [rbp+0A30h+var_3FC]
0x1800dcaec  mov     [rbp+0A30h+var_898], rax
0x1800dcaf3  lea     r9, asc_1802EE7AC; ": {}"
0x1800dcafa  lea     rax, [rbp+0A30h+var_898]
0x1800dcb01  mov     r8d, edi
0x1800dcb04  lea     edx, [rdi-2]
0x1800dcb07  mov     [rsp+0B30h+DirCount], rax
0x1800dcb0c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dcb11  mov     edx, 382h
0x1800dcb16  jmp     loc_1800DCBBA
0x1800dcb1b  mov     eax, [r8+50h]
0x1800dcb1f  mov     esi, 1
0x1800dcb24  mov     [r15+8A4h], eax
0x1800dcb2b  test    [r8+54h], sil
0x1800dcb2f  jnz     short loc_1800DCB36
0x1800dcb31  cmp     eax, 11h
0x1800dcb34  jnz     short loc_1800DCB3F
0x1800dcb36  bts     dword ptr [r15+8A0h], 13h
0x1800dcb3f  mov     rdx, [r15+468h]; void *
0x1800dcb46  xor     r9d, r9d; wchar_t **
0x1800dcb49  xor     r8d, r8d; wchar_t *
0x1800dcb4c  mov     rcx, r15; this
0x1800dcb4f  call    ?CreateSessionSandbox@CCbsSession@@QEAAJPEAXPEB_WPEAPEA_W@Z; CCbsSession::CreateSessionSandbox(void *,wchar_t const *,wchar_t * *)
0x1800dcb54  mov     ebx, eax
0x1800dcb56  test    eax, eax
0x1800dcb58  jns     short loc_1800DCBD5
0x1800dcb5a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcb61  mov     [rbp+0A30h+var_400], eax
0x1800dcb67  test    rcx, rcx
0x1800dcb6a  jz      short loc_1800DCBB5
0x1800dcb6c  mov     edi, 3
0x1800dcb71  lea     r9, aFailedToCreate_14; "Failed to create private session store."
0x1800dcb78  mov     r8d, edi
0x1800dcb7b  xor     edx, edx
0x1800dcb7d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dcb82  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcb89  lea     rax, [rbp+0A30h+var_400]
0x1800dcb90  mov     qword ptr [rbp+0A30h+var_8A0], rax
0x1800dcb97  lea     r9, asc_1802EE7AC; ": {}"
0x1800dcb9e  lea     rax, [rbp+0A30h+var_8A0]
0x1800dcba5  mov     r8d, edi
0x1800dcba8  mov     dl, sil
0x1800dcbab  mov     [rsp+0B30h+DirCount], rax; int
0x1800dcbb0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dcbb5  mov     edx, 38Dh; void *
0x1800dcbba  mov     r9d, ebx; char *
0x1800dcbbd  mov     rcx, [rbp+0A38h]; this
0x1800dcbc4  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1800dcbcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcbd0  jmp     loc_1800E0EB8
0x1800dcbd5  mov     rax, [r14+98h]
0x1800dcbdc  cmp     [rax+40h], rdi
0x1800dcbe0  jnz     loc_1800DCC6E
0x1800dcbe6  mov     rax, [r14+88h]
0x1800dcbed  test    rax, rax
0x1800dcbf0  jz      short loc_1800DCC04
0x1800dcbf2  cmp     [rax+28h], rdi
0x1800dcbf6  jnz     short loc_1800DCC6E
0x1800dcbf8  cmp     [rax+8], rdi
0x1800dcbfc  jnz     short loc_1800DCC6E
0x1800dcbfe  cmp     [rax+18h], rdi
0x1800dcc02  jnz     short loc_1800DCC6E
0x1800dcc04  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcc0b  mov     ebx, 800F0952h
0x1800dcc10  mov     [rbp+0A30h+var_404], ebx
0x1800dcc16  test    rcx, rcx
0x1800dcc19  jz      short loc_1800DCC64
0x1800dcc1b  mov     edi, 3
0x1800dcc20  lea     r9, aActionlistNoFe; "ActionList: No feature or package to in"...
0x1800dcc27  mov     r8d, edi
0x1800dcc2a  xor     edx, edx
0x1800dcc2c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800dcc31  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800dcc38  lea     rax, [rbp+0A30h+var_404]
0x1800dcc3f  mov     [rbp+0A30h+var_8A8], rax
0x1800dcc46  lea     r9, asc_1802EE7AC; ": {}"
0x1800dcc4d  lea     rax, [rbp+0A30h+var_8A8]
0x1800dcc54  mov     r8d, edi
0x1800dcc57  mov     dl, sil
0x1800dcc5a  mov     [rsp+0B30h+DirCount], rax
0x1800dcc5f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800dcc64  mov     edx, 39Bh
0x1800dcc69  jmp     loc_1800DCBBA
0x1800dcc6e  cmp     [r14+0A4h], dil
0x1800dcc75  jz      short loc_1800DCCCA
0x1800dcc77  lea     rdx, [r14+58h]; struct _LUTF8_STRING *
0x1800dcc7b  mov     [rbp+0A30h+var_700], rdi
0x1800dcc82  lea     r8, [rbp+0A30h+var_700]; wchar_t **
0x1800dcc89  mov     rcx, r13; struct Windows::Rtl::IPoolAllocator *
0x1800dcc8c  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800dcc91  mov     ebx, eax
0x1800dcc93  test    eax, eax
0x1800dcc95  jns     short loc_1800DCCA4
0x1800dcc97  mov     r9d, eax
0x1800dcc9a  mov     edx, 3A1h
0x1800dcc9f  jmp     loc_1800DCBBD
0x1800dcca4  mov     rdx, [rbp+0A30h+var_700]
0x1800dccab  lea     rcx, [r15+8A8h]
0x1800dccb2  call    SczAllocFromSz
0x1800dccb7  mov     ebx, eax
0x1800dccb9  test    eax, eax
0x1800dccbb  jns     short loc_1800DCCCA
0x1800dccbd  mov     r9d, eax
0x1800dccc0  mov     edx, 3A2h
0x1800dccc5  jmp     loc_1800DCBBD
0x1800dccca  mov     rcx, r15; this
0x1800dcccd  call    ?IsFODRetryOperation@CCbsSession@@QEBA_NXZ; CCbsSession::IsFODRetryOperation(void)
0x1800dccd2  test    al, al
0x1800dccd4  jz      loc_1800DCD81
0x1800dccda  mov     rax, [r14+88h]
0x1800dcce1  mov     rcx, [rax]
0x1800dcce4  mov     [rbp+0A30h+var_2B0], rdi
0x1800dcceb  mov     [rbp+0A30h+var_438], rcx
0x1800dccf2  lea     rdx, [rbp+0A30h+var_2B0]
0x1800dccf9  lea     rcx, [rbp+0A30h+var_438]
0x1800dcd00  call    ??9?$CConstIterator@UDisableFeature@ActionListParser@@@XmlParserGenerator@@QEBA_NAEBV01@@Z; XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature> const &)
0x1800dcd05  test    al, al
0x1800dcd07  jz      short loc_1800DCD81
0x1800dcd09  mov     rdx, [rbp+0A30h+var_438]; struct _LUTF8_STRING *
0x1800dcd10  lea     r8, [rbp+0A30h+var_738]; wchar_t **
0x1800dcd17  mov     rcx, r13; struct Windows::Rtl::IPoolAllocator *
0x1800dcd1a  mov     [rbp+0A30h+var_738], rdi
0x1800dcd21  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800dcd26  mov     ebx, eax
0x1800dcd28  test    eax, eax
0x1800dcd2a  js      short loc_1800DCD74
0x1800dcd2c  lea     r8, [rbp+0A30h+var_738]
0x1800dcd33  mov     ecx, esi
0x1800dcd35  lea     rdx, aActionlistAddi_0; "ActionList: Adding FOD retry: {}"
0x1800dcd3c  call    ??$TraceAtLevel@PEA_W@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEA_W@Z; LogAdapter::TraceAtLevel<wchar_t *>(LogAdapter::LogLevel,char const * const,wchar_t * const &)
0x1800dcd41  mov     rdx, [rbp+0A30h+var_738]; wchar_t *
0x1800dcd48  lea     rcx, [r15+6E0h]; this
0x1800dcd4f  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x1800dcd54  mov     ebx, eax
0x1800dcd56  test    eax, eax
0x1800dcd58  js      short loc_1800DCD67
0x1800dcd5a  mov     rax, [rbp+0A30h+var_438]
0x1800dcd61  mov     rcx, [rax+48h]
0x1800dcd65  jmp     short loc_1800DCCEB
0x1800dcd67  mov     r9d, eax
0x1800dcd6a  mov     edx, 3B4h
0x1800dcd6f  jmp     loc_1800DCBBD
0x1800dcd74  mov     r9d, eax
0x1800dcd77  mov     edx, 3B0h
0x1800dcd7c  jmp     loc_1800DCBBD
0x1800dcd81  mov     rax, [r14+98h]
0x1800dcd88  mov     bl, dil
0x1800dcd8b  mov     [rsp+0B30h+var_ABE], dil
0x1800dcd90  mov     r12b, dil
0x1800dcd93  mov     [rsp+0B30h+var_ABF], bl
0x1800dcd97  mov     rcx, [rax+38h]
0x1800dcd9b  mov     [rbp+0A30h+var_2A8], rdi
0x1800dcda2  mov     edi, 3
0x1800dcda7  mov     [rbp+0A30h+var_478], rcx
0x1800dcdae  lea     rdx, [rbp+0A30h+var_2A8]
0x1800dcdb5  lea     rcx, [rbp+0A30h+var_478]
0x1800dcdbc  call    ??9?$CConstIterator@UDisableFeature@ActionListParser@@@XmlParserGenerator@@QEBA_NAEBV01@@Z; XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature> const &)
0x1800dcdc1  test    al, al
0x1800dcdc3  jz      loc_1800DD355
0x1800dcdc9  mov     r14, [rbp+0A30h+var_478]
0x1800dcdd0  movzx   r12d, r12b
0x1800dcdd4  cmp     dword ptr [r14+88h], 4
0x1800dcddc  cmovz   r12d, esi
0x1800dcde0  mov     dl, dil
0x1800dcde3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@details@3@XZ@4V453@A; this
0x1800dcdea  call    ?IncludeNewline@DebuggerLogger@LogAdapter@@UEBA_NXZ; LogAdapter::DebuggerLogger::IncludeNewline(void)
0x1800dcdef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::GetImpl(void)'::`2'::impl
0x1800dcdf6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FixMultipleBaselinesSingleHopInstall>::__private_IsEnabled(void)
0x1800dcdfb  xor     edx, edx
0x1800dcdfd  test    al, al
0x1800dcdff  jz      loc_1800DD048
0x1800dce05  mov     rdx, r14; struct ActionListParser::InstallPackage *
0x1800dce08  mov     rcx, r15; this
0x1800dce0b  call    ?IsWinPEServicingWithMultiPayloadRebaseLCU@CCbsSession@@QEAA_NPEAUInstallPackage@ActionListParser@@@Z; CCbsSession::IsWinPEServicingWithMultiPayloadRebaseLCU(ActionListParser::InstallPackage *)
0x1800dce10  xor     edx, edx
0x1800dce12  test    al, al
0x1800dce14  jnz     short loc_1800DCE48
0x1800dce16  test    r12b, r12b
0x1800dce19  jz      loc_1800DD133
0x1800dce1f  cmp     [r14+133h], dl
0x1800dce26  jz      loc_1800DD133
0x1800dce2c  cmp     dword ptr [r14+8Ch], 6
0x1800dce34  jnz     loc_1800DD133
0x1800dce3a  cmp     dword ptr [r14+88h], 4
0x1800dce42  jz      loc_1800DD133
0x1800dce48  xor     eax, eax
0x1800dce4a  mov     [rbp+0A30h+var_6B0], rdx
0x1800dce51  xorps   xmm0, xmm0
0x1800dce54  mov     [rbp+0A30h+var_6D0], rax
0x1800dce5b  xorps   xmm1, xmm1
0x1800dce5e  mov     [rbp+0A30h+var_6B8], rax
0x1800dce65  movups  [rbp+0A30h+var_6E0], xmm0
0x1800dce6c  mov     [rbp+0A30h+var_698], rax
0x1800dce73  movups  [rbp+0A30h+var_6C8], xmm1
0x1800dce7a  mov     [rbp+0A30h+var_680], rax
0x1800dce81  movups  [rbp+0A30h+var_6A8], xmm0
0x1800dce88  mov     [rbp+0A30h+var_668], rax
0x1800dce8f  movups  [rbp+0A30h+var_690], xmm1
0x1800dce96  mov     [rbp+0A30h+var_660], rdx
0x1800dce9d  movups  [rbp+0A30h+var_678], xmm0
0x1800dcea4  mov     [rbp+0A30h+var_658], rdx
0x1800dceab  cmp     [r14+108h], rdx
0x1800dceb2  jnz     loc_1800DCF39
0x1800dceb8  mov     al, [r14+131h]
0x1800dcebf  lea     rcx, [rbp+0A30h+var_6E0]
0x1800dcec6  mov     byte ptr [rbp+0A30h+var_658+3], al
0x1800dcecc  movups  xmm0, xmmword ptr [r14+28h]
0x1800dced1  movups  [rbp+0A30h+var_6A8], xmm0
0x1800dced8  movsd   xmm1, qword ptr [r14+38h]
0x1800dcede  movsd   [rbp+0A30h+var_698], xmm1
0x1800dcee6  mov     al, [r14+133h]
0x1800dceed  mov     byte ptr [rbp+0A30h+var_658+4], al
0x1800dcef3  movups  xmm0, xmmword ptr [r14+58h]
0x1800dcef8  movaps  [rbp+0A30h+var_690], xmm0
0x1800dceff  movsd   xmm1, qword ptr [r14+68h]
0x1800dcf05  movsd   [rbp+0A30h+var_680], xmm1
0x1800dcf0d  mov     al, [r14+134h]
0x1800dcf14  mov     byte ptr [rbp+0A30h+var_658+5], al
0x1800dcf1a  movups  xmm0, xmmword ptr [r14+70h]
0x1800dcf1f  movups  [rbp+0A30h+var_678], xmm0
0x1800dcf26  movsd   xmm1, qword ptr [r14+80h]
0x1800dcf2f  movsd   [rbp+0A30h+var_668], xmm1
0x1800dcf37  jmp     short loc_1800DCF40
0x1800dcf39  mov     rcx, [r14+100h]
0x1800dcf40  mov     [rbp+0A30h+var_2A0], rdx
0x1800dcf47  mov     [rbp+0A30h+var_480], rcx
0x1800dcf4e  lea     rdx, [rbp+0A30h+var_2A0]
0x1800dcf55  lea     rcx, [rbp+0A30h+var_480]
0x1800dcf5c  call    ??9?$CConstIterator@UDisableFeature@ActionListParser@@@XmlParserGenerator@@QEBA_NAEBV01@@Z; XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature>::operator!=(XmlParserGenerator::CConstIterator<ActionListParser::DisableFeature> const &)
0x1800dcf61  xor     edx, edx
0x1800dcf63  test    al, al
  ... truncated ...
```
