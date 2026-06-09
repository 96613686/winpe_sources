# CMsiEngine::DoInitialize(ushort const *,iuiEnum,ushort const *,ushort const *,iioEnum,IMsiRecord const *)

- ea: `0x1800f94d0`
- end: `0x1801023b0`
- name: `?DoInitialize@CMsiEngine@@IEAA?AW4ieiEnum@@PEBGW4iuiEnum@@00W4iioEnum@@PEBVIMsiRecord@@@Z`
- size: `36576`
- prototype: ``
- caller_count: `1`
- callee_count: `155`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18017ac60`

## callees

- `0x18000a150`
- `0x18000f1bc`
- `0x180013fe4`
- `0x18001dee8`
- `0x180025a18`
- `0x180030210`
- `0x180035a8c`
- `0x18003bccc`
- `0x18003ca18`
- `0x18004295c`
- `0x180043660`
- `0x180046d80`
- `0x180046ec0`
- `0x18004ceb0`
- `0x180061334`
- `0x1800616e0`
- `0x180063f88`
- `0x180063fc8`
- `0x180064a78`
- `0x180066074`
- `0x18006c0cc`
- `0x180076e28`
- `0x180079dd0`
- `0x180085dcc`
- `0x18008afe0`
- `0x18008be90`
- `0x18008f3e8`
- `0x18008fa24`
- `0x180091028`
- `0x180093960`
- `0x180097d10`
- `0x180098b50`
- `0x180098bd8`
- `0x1800a5fc4`
- `0x1800ad810`
- `0x1800add00`
- `0x1800adeb4`
- `0x1800afdec`
- `0x1800affa8`
- `0x1800b1314`
- `0x1800b7444`
- `0x1800b8034`
- `0x1800b9bac`
- `0x1800bc65c`
- `0x1800bc730`
- `0x1800c46c0`
- `0x1800c484c`
- `0x1800c986c`
- `0x1800cdb74`
- `0x1800ce17c`

## import_xrefs

- `msvcrt!wcstol` at `0x1800fa64b`
- `msvcrt!wcstol` at `0x1800fa64b`
- `KERNEL32!CompareStringW` at `0x1800f9892`
- `KERNEL32!CompareStringW` at `0x1800f99a1`
- `KERNEL32!CompareStringW` at `0x1800f9892`
- `KERNEL32!CompareStringW` at `0x1800f99a1`
- `ole32!IIDFromString` at `0x1800fce1a`
- `ole32!IIDFromString` at `0x1800fce1a`

## string_xrefs

- `0x1800fcd2f`: `MSIINSTALLPERUSER`
- `0x1800fd058`: `MSIINSTALLPERUSER`
- `0x1800fd30a`: `MSIINSTALLPERUSER`
- `0x1800fd38e`: `MSIINSTALLPERUSER`
- `0x1800fd43b`: `MSIINSTALLPERUSER`
- `0x1800fd6b9`: `MSIINSTALLPERUSER`
- `0x1800fd722`: `MSIINSTALLPERUSER`
- `0x1800ff97c`: `MSIINSTALLPERUSER`
- `0x1800ff9d6`: `MSIINSTALLPERUSER`
- `0x1800fffe1`: `CommonFiles64Folder`
- `0x1800fffda`: `CommonFilesFolder`
- `0x180101b06`: `INSTALL`
- `0x1800fa00d`: `REMOVE`
- `0x1800fb580`: `REINSTALL`
- `0x1800fbb31`: `REINSTALLMODE`
- `0x1800f9f0d`: `MSINEWINSTANCE`
- `0x1800fdc26`: `MSIPACKAGEDOWNLOADLOCALCOPY`
- `0x1800f95ef`: `CMsiEngine::DoInitialize: UI level set to none because we're running in a non-interactive context.`
- `0x1800f9767`: `CURRENTDIRECTORY`
- `0x1800fa1a1`: `MSICLIENTUSESEXTERNALUI`
- `0x180100a5d`: `MSICLIENTUSESEXTERNALUI`
- `0x1800fa277`: `MSICLIENTUSESEMBEDDEDUI`
- `0x180100a9b`: `MSICLIENTUSESEMBEDDEDUI`
- `0x1801011c5`: `MSICLIENTUSESEMBEDDEDUI`
- `0x1800fb1d5`: `Removal of individual patches cannot occur in the same transaction with a re-cache of an .MSI package that takes the product to a different version than the one registered.`
- `0x1800fb63f`: `Both REINSTALL and REMOVE=ALL specified. Actual operation is repair.`
- `0x1800fb85d`: `MSIUNINSTALLSUPERSEDEDCOMPONENTS`
- `0x1800fc41e`: `MsiLogFileLocation`
- `0x1800fc47d`: `MsiLogFileLocation`
- `0x1800fc52e`: `RecacheTransforms`
- `0x1800fca23`: `Failing install, missing product code`
- `0x1800fcc96`: `Product not registered: beginning first-time install`
- `0x1800fcf82`: `Determined that existing product (either this product or the product being upgraded with a patch) is installed per-%s.`
- `0x1800fd0a2`: `MSIINTERNALINSTALLEDPERUSER`
- `0x1800fd0f2`: `Determined that existing product (either this product or the product being upgraded with a patch) is a dual mode package installed in per-user mode.`
- `0x1800fd7f7`: `MSI_LUA: Nested installation UAC elevation tracks that of parent (%s elevated)`
- `0x1800fd913`: `MSI_LUA: Unsetting the  uninstall flag for repair operations`
- `0x1800fdec8`: `MSI_LUA: Allowing use of new source since consent was provided`
- `0x1800fe20c`: `Package name retrieved from configuration data: '%s'`
- `0x1800fe339`: `Package name extracted from package path: '%s'`
- `0x1800fee5d`: `Error : Could Not create path in the given volume: %s`
- `0x1800fefd6`: `Error : Invalid string could not crate path %s`
- `0x1800ff06e`: `MSIRESTARTMANAGERCONTROL`
- `0x1800ff11c`: `MSIRESTARTMANAGERCONTROL`
- `0x1800ff150`: `MSIRESTARTMANAGERCONTROL`
- `0x1800ff0f4`: `RESTART MANAGER: Disabled by %s property; Windows Installer will use the built-in FilesInUse functionality.`
- `0x1800ff234`: `RESTART MANAGER: Disabled by %s system policy; Windows Installer will use the built-in FilesInUse functionality.`
- `0x1800ff37c`: `MsiRestartManagerSessionKey`
- `0x1800ff3e1`: `RESTART MANAGER: Session opened.`
- `0x1800ff420`: `RESTART MANAGER: Failed to open session; Windows Installer will use the built-in FilesInUse functionality. Error: %d`
- `0x1800ff63e`: `MsiSystemRebootPending`
- `0x1801002a7`: `MSIUSEREALADMINDETECTION`
- `0x1801003f5`: `MSI_LUA: Setting AdminUser property to 1 because this is the client or the user has already permitted elevation`
- `0x180100365`: `MSI_LUA: Setting AdminUser property to 1 because the product is already installed managed and per-machine`
- `0x18010049c`: `MSI_LUA: Setting MsiRunningElevated property to 1 because the install is already running elevated.`
- `0x1801004d2`: `MsiRunningElevated`
- `0x18010068c`: `Privileged`
- `0x180100741`: `Installed`
- `0x18010092d`: `MsiEmbeddedUI`
- `0x180101033`: `MsiEmbeddedUI`
- `0x180100987`: `MSIDISABLEEEUI`
- `0x1801009f2`: `EEUI - Disabling MsiEmbeddedUI due to property or policy`
- `0x180100b29`: `EEUI - Disabling MsiEmbeddedUI due to existing external or embedded UI`
- `0x180100b82`: `EEUI - Disabling MsiEmbeddedUI in dialog preview mode`
- `0x180100bec`: `EEUI - Disabling MsiEmbeddedUI for service because it's not a quiet/basic install`
- `0x180100c4d`: `EEUI - Disabling MsiEmbeddedUI in quiet-basic mode on client side`
- `0x180100ca6`: `EEUI - Disabling MsiEmbeddedUI in quiet mode`
- `0x180100ee0`: `EEUI - Running MsiEmbeddedUI code`
- `0x18010100e`: `%MsiBreak`
- `0x180100d8a`: `Child install has different elevation state than parent. Possible pre-existing install or machine/user conflict. Failing child install.`
- `0x180101848`: `MsiUIProgressOnly`
- `0x18010189e`: `MsiUIHideCancel`
- `0x1801018f0`: `MsiUISourceResOnly`
- `0x18010193f`: `MsiUIUACOnly`
- `0x180101a29`: `OEM-mode installation does not support patching.`
- `0x180101beb`: `OEM-mode installation supports only per machine installations.`
- `0x180101a97`: `OEM-mode installation supports only first time installations.`
- `0x180101bd9`: `OEM-mode installation supports only UI-less installations.`
- `0x180101b30`: `OEM-mode installation supports only INSTALL type of ACTION.`
- `0x180101b8d`: `OEM-mode installation.`
- `0x1800fe93a`: `Config.Msi`
- `0x1800feab7`: `Config.Msi`
- `0x1800ff5d7`: `PendingFileRenameOperations`

## pseudocode

```c
__int64 __fastcall CMsiEngine::DoInitialize(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 v8; // r14
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // rdi
  unsigned int v11; // r13d
  unsigned int v12; // r15d
  int v13; // ebx
  unsigned int MsiHandle; // eax
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rbx
  const WCHAR *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, unsigned __int16 *, _QWORD, __int64); // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  const WCHAR *v26; // rax
  const unsigned __int16 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64, __int64); // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, IMsiData **); // rbx
  __int64 v35; // rax
  const unsigned __int16 *v36; // rax
  IMsiData *v37; // rcx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD, __int64); // rbx
  __int64 v40; // rax
  __int64 v41; // rax
  IMsiData *v42; // rbx
  char v43; // bl
  __int64 v44; // rdx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, __int64, __int64); // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  int PropertyTable; // eax
  IMsiData *v50; // rbx
  MsiString *v51; // rax
  unsigned __int16 *v52; // rdi
  IMsiData *v53; // rbx
  const unsigned __int16 *v54; // rax
  MsiString *v55; // rax
  MsiString *v56; // rax
  int v57; // ebx
  __int64 v58; // rax
  int v59; // r15d
  MsiString *v60; // rax
  bool v61; // bl
  bool v62; // zf
  char v63; // cl
  const unsigned __int16 *v64; // rax
  unsigned int v65; // eax
  IMsiData *v66; // rcx
  const WCHAR *v67; // rax
  const WCHAR *v68; // rax
  const WCHAR *v69; // rax
  MsiString *v70; // rax
  int v71; // ebx
  IMsiData *v72; // rbx
  const WCHAR *v73; // rax
  MsiString *v74; // rax
  int v75; // ebx
  const WCHAR *v76; // rax
  unsigned int v77; // eax
  char v78; // al
  IMsiData *v79; // rbx
  _WORD *v80; // rdi
  int v81; // ebx
  bool v82; // di
  MsiString *v83; // rax
  MsiString *v84; // rax
  int v85; // r15d
  unsigned int (__fastcall *v86)(__int64, _QWORD); // rbx
  MsiString *v87; // rax
  unsigned int (__fastcall *v88)(__int64, _QWORD); // rbx
  MsiString *v89; // rax
  bool v90; // bl
  const unsigned __int16 *v91; // rax
  int v92; // r14d
  __int64 v93; // rbx
  __int64 v94; // rax
  int v95; // eax
  unsigned int v96; // edi
  unsigned int v97; // esi
  __int64 v98; // rbx
  __int64 v99; // rax
  IMsiData *v100; // rbx
  struct IMsiRecord **v101; // rbx
  struct IMsiRecord **v102; // rax
  __int64 v103; // rax
  char v104; // di
  unsigned int v105; // eax
  __int64 *v106; // rcx
  __int64 v107; // rax
  __int64 v108; // r9
  int v109; // esi
  const WCHAR *v110; // rax
  const struct IMsiString *v111; // rbx
  const struct IMsiString **v112; // rax
  struct IMsiRecord *PropertyFromDatabase; // rax
  char v114; // bl
  char v115; // bl
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // r8
  unsigned int v119; // eax
  char v120; // al
  MsiString *v121; // rax
  unsigned __int16 *v122; // rsi
  bool v123; // bl
  unsigned int PatchMetaDataForNewObsoletedAndSupercededMSPs; // ebx
  __int64 v125; // rax
  GUIDAndSequence *v126; // rcx
  __int64 v127; // rbx
  MsiString *v128; // rax
  __int64 v129; // rax
  char v130; // si
  __int64 v131; // rax
  __int64 v132; // r9
  __int64 v133; // rax
  char v134; // bl
  __int64 v135; // rax
  __int64 v136; // r8
  unsigned int v137; // edi
  __int64 v138; // rax
  __int64 v139; // r9
  unsigned int v140; // ebx
  __int64 v141; // rax
  __int64 v142; // rbx
  MsiString *v143; // rax
  __int64 v144; // rax
  const unsigned __int16 *v145; // rax
  CMsiPatchManager *v146; // rbx
  struct IMsiDatabase *v147; // rax
  CMsiPatchManager *v148; // rax
  __int16 v149; // ax
  __int64 v150; // rbx
  unsigned __int16 v151; // ax
  struct IMsiRecord *Record; // rax
  __int64 v153; // rax
  __int64 v154; // rdi
  void (__fastcall *v155)(__int64, __int64, _QWORD); // rbx
  unsigned __int16 v156; // ax
  __int64 v157; // rdi
  void (__fastcall *v158)(__int64, __int64, _QWORD); // rbx
  __int64 v159; // rax
  unsigned int v160; // eax
  __int64 v161; // rax
  __int64 v162; // rsi
  __int64 v163; // rbx
  bool v164; // di
  __int64 v165; // r14
  __int64 v166; // rax
  unsigned int v167; // eax
  __int64 v168; // r15
  __int64 v169; // rax
  unsigned int v170; // esi
  unsigned int v171; // r14d
  __int64 v172; // rdi
  __int64 v173; // rbx
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rax
  int v178; // eax
  bool v179; // di
  __int64 v180; // rsi
  __int64 v181; // rbx
  __int64 v182; // rax
  const unsigned __int16 *v183; // rax
  __int64 v184; // rax
  _WORD *v185; // rax
  void (__fastcall *v186)(__int64, __int64, __int64); // rdi
  const unsigned __int16 *v187; // rax
  MsiString *v188; // rax
  __int64 v189; // rbx
  MsiString *v190; // rax
  __int64 v191; // rax
  GUIDAndSequence *v192; // rcx
  MsiString *v193; // rax
  __int64 v194; // rbx
  MsiString *v195; // rax
  __int64 v196; // rax
  struct IMsiDatabase *v197; // rax
  void (__fastcall *v198)(__int64, __int64, __int64); // rdi
  __int64 v199; // rbx
  MsiString *v200; // rax
  __int64 v201; // rax
  IMsiData *v202; // rbx
  void (__fastcall *v203)(__int64, __int64, IMsiData *); // rdi
  MsiString *v204; // rax
  __int64 v205; // rax
  IMsiData *v206; // rbx
  void (__fastcall *v207)(__int64, __int64, IMsiData *); // rdi
  MsiString *v208; // rax
  __int64 v209; // rax
  struct IUnknown v210; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  MsiString *v212; // rax
  __int64 v213; // rax
  void (__fastcall *v214)(__int64, __int64, void ***); // rbx
  MsiString *v215; // rax
  __int64 v216; // rax
  GUIDAndSequence *v217; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v219; // rax
  __int64 v220; // rax
  void (__fastcall *v221)(__int64, __int64, __int64); // rbx
  MsiString *v222; // rax
  __int64 v223; // rax
  __int64 v224; // rax
  const unsigned __int16 *v225; // rax
  const unsigned __int16 *v226; // rax
  const unsigned __int16 *v227; // rax
  const unsigned __int16 *v228; // rax
  __int64 v229; // rax
  __int64 v230; // rax
  void (__fastcall *v231)(__int64, __int64, __int64); // rdi
  __int64 v232; // rbx
  MsiString *v233; // rax
  __int64 v234; // rax
  void (__fastcall *v235)(__int64, __int64, __int64); // rdi
  __int64 v236; // rbx
  MsiString *v237; // rax
  __int64 v238; // rax
  const unsigned __int16 *v239; // rax
  __int64 v240; // rax
  const unsigned __int16 *v241; // rax
  __int64 v242; // rax
  const unsigned __int16 *v243; // r9
  __int64 (__fastcall *v244)(__int64, __int64); // rbx
  MsiString *v245; // rax
  __int64 v246; // rax
  int v247; // edi
  unsigned int v248; // ebx
  CMsiSQMSession *SQMSession; // rax
  CMsiSQMSession *v250; // rbx
  unsigned int IntegerPolicyValue; // eax
  CMsiSQMSession *v252; // rbx
  unsigned int v253; // eax
  const OLECHAR *v254; // rax
  unsigned int v255; // ebx
  const unsigned __int16 *v256; // rax
  CMsiSQMSession *v257; // rax
  const WCHAR *v258; // rax
  const WCHAR *v259; // rax
  const unsigned __int16 *v260; // rax
  MsiString *v261; // rax
  int v262; // ebx
  BOOL v263; // edi
  const unsigned __int16 *v264; // rcx
  const WCHAR *v265; // rax
  const WCHAR *v266; // rax
  const unsigned __int16 *v267; // rax
  int v268; // eax
  struct IUnknown v269; // rax
  HRESULT (__stdcall *v270)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v271; // rax
  __int64 v272; // rax
  void (__fastcall *v273)(__int64, __int64, __int64); // rbx
  MsiString *v274; // rax
  __int64 v275; // rax
  __int64 v276; // r14
  MsiString *v277; // rax
  __int64 v278; // rax
  unsigned int v279; // ebx
  CMsiSQMSession *v280; // rax
  IMsiData *v281; // rdi
  void (__fastcall *v282)(__int64, __int64, IMsiData *); // rbx
  MsiString *v283; // rax
  __int64 v284; // rax
  MsiString *v285; // rax
  __int64 v286; // rax
  IMsiData *v287; // rdi
  void (__fastcall *v288)(__int64, __int64, IMsiData *); // rbx
  MsiString *v289; // rax
  __int64 v290; // rax
  _QWORD *v291; // rdi
  __int64 (__fastcall *v292)(__int64, __int64); // rbx
  MsiString *v293; // rax
  __int64 v294; // rax
  struct IUnknown v295; // rax
  HRESULT (__stdcall *v296)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v297; // rax
  __int64 v298; // rax
  struct IUnknown v299; // rax
  ULONG (__stdcall *v300)(IUnknown *); // rdi
  MsiString *v301; // rax
  __int64 v302; // rbx
  MsiString *v303; // rax
  __int64 v304; // rax
  GUIDAndSequence *v305; // rbx
  char v306; // al
  struct IUnknown v307; // rbx
  ULONG (__stdcall *v308)(IUnknown *); // rdi
  MsiString *v309; // rax
  __int64 v310; // rbx
  MsiString *v311; // rax
  __int64 v312; // rax
  HRESULT (__stdcall *v313)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v314; // rax
  __int64 v315; // rax
  __int64 v316; // rax
  MsiString *v317; // rax
  void (__fastcall *v318)(__int64, __int64, __int64); // rbx
  MsiString *v319; // rax
  __int64 v320; // rax
  void (__fastcall *v321)(__int64, __int64, __int64); // rdi
  MsiString *v322; // rax
  __int64 v323; // rbx
  MsiString *v324; // rax
  __int64 v325; // rax
  __int64 (__fastcall *v326)(__int64, __int64); // rbx
  MsiString *v327; // rax
  __int64 v328; // rax
  void (__fastcall *v329)(__int64, __int64, __int64); // rdi
  MsiString *v330; // rax
  __int64 v331; // rbx
  MsiString *v332; // rax
  __int64 v333; // rax
  char v334; // di
  __int64 v335; // rcx
  char v336; // al
  const unsigned __int16 *v337; // rcx
  const unsigned __int16 *v338; // rax
  const unsigned __int16 *v339; // rax
  const struct IMsiString *PackedGUID; // rax
  const unsigned __int16 *v341; // rax
  int v342; // eax
  bool v343; // r14
  char v344; // al
  unsigned int v345; // esi
  char v346; // di
  __int64 v347; // rbx
  __int64 v348; // rax
  int v349; // eax
  unsigned int v350; // ebx
  struct CMsiSQMSession *v351; // rax
  __int64 v352; // r8
  __int64 v353; // rax
  GUIDAndSequence *v354; // rcx
  void (__fastcall *v355)(__int64, __int64, _QWORD); // rbx
  MsiString *v356; // rax
  __int64 v357; // rax
  void (__fastcall *v358)(__int64, __int64, __int64); // rbx
  MsiString *v359; // rax
  __int64 v360; // rax
  IMsiData *v361; // rcx
  IMsiData *v362; // rax
  __int64 v363; // rax
  __int64 v364; // rbx
  MsiString *v365; // rax
  __int64 v366; // rax
  __int64 v367; // rax
  __int64 v368; // r14
  __int64 (__fastcall *v369)(__int64, __int64, __int64, __int64); // rsi
  __int64 v370; // rdi
  __int64 v371; // rbx
  __int64 v372; // rax
  __int64 v373; // rax
  __int64 v374; // rax
  __int64 v375; // rbx
  __int64 v376; // rax
  __int64 v377; // r9
  __int64 v378; // rax
  __int64 v379; // rax
  _QWORD *v380; // rax
  __int64 v381; // rbx
  __int64 v382; // rax
  __int64 v383; // rdx
  struct CMsiSQMSession *v384; // rax
  __int64 v385; // r8
  __int64 v386; // rax
  __int64 v387; // rax
  const WCHAR *v388; // rax
  __int64 v389; // rax
  void (__fastcall *v390)(__int64, __int64, __int64); // rbx
  MsiString *v391; // rax
  __int64 v392; // rax
  __int64 v393; // rax
  MsiString *v394; // rax
  char v395; // bl
  __int64 v396; // rax
  int v397; // eax
  IMsiData **v398; // rdx
  const WCHAR *v399; // rax
  __int64 v400; // rax
  const unsigned __int16 *v401; // rax
  __int64 v402; // r14
  __int64 (__fastcall *v403)(__int64, __int64, __int64, __int64); // rsi
  __int64 v404; // rdi
  __int64 v405; // rbx
  __int64 v406; // rax
  __int64 v407; // rax
  __int64 v408; // rax
  __int64 v409; // rbx
  __int64 v410; // rax
  const unsigned __int16 *v411; // rax
  __int64 v412; // rax
  const WCHAR *v413; // rax
  __int64 v414; // rax
  const unsigned __int16 *v415; // rax
  const struct IMsiString **v416; // rbx
  const unsigned __int16 *v417; // rax
  struct IMsiRecord *v418; // rax
  __int64 v419; // rax
  __int64 v420; // rbx
  __int64 v421; // rax
  void (__fastcall *v422)(__int64, __int64, __int64); // rdi
  __int64 v423; // rbx
  MsiString *v424; // rax
  __int64 v425; // rax
  void (__fastcall *v426)(__int64, __int64, __int64); // rbx
  MsiString *v427; // rax
  __int64 v428; // rax
  __int64 v429; // rax
  __int64 v430; // rdi
  __int64 (__fastcall *v431)(__int64, const unsigned __int16 *, _QWORD, __int64); // rbx
  __int64 v432; // rax
  __int64 v433; // rax
  __int64 v434; // rax
  unsigned int v435; // esi
  struct IMsiRecord *v436; // rax
  __int64 v437; // rax
  __int64 v438; // rdi
  void (__fastcall *v439)(__int64, __int64, _QWORD); // rbx
  __int64 v440; // rax
  __int64 v441; // rax
  char v442; // al
  char v443; // si
  char v444; // r14
  bool v445; // di
  bool v446; // bl
  __int64 v447; // rax
  __int64 v448; // r9
  __int64 v449; // r8
  __int64 v450; // rdx
  int v451; // eax
  int v452; // eax
  MsiString *v453; // rax
  __int64 v454; // rax
  unsigned __int16 *v455; // r14
  __int64 v456; // rsi
  const unsigned __int16 *v457; // rax
  struct IMsiPath **v458; // rbx
  const struct IMsiString *v459; // rax
  struct IMsiRecord *PathObject; // rax
  __int64 v461; // rax
  __int64 v462; // rax
  __int64 v463; // rax
  __int64 v464; // rax
  __int64 v465; // rsi
  __int64 (__fastcall *v466)(__int64, __int64, __int64); // rdi
  __int64 v467; // rbx
  __int64 v468; // rax
  __int64 v469; // rax
  _QWORD *v470; // rax
  __int64 v471; // rax
  __int64 v472; // rax
  __int64 v473; // rax
  __int64 v474; // rbx
  __int64 v475; // rdi
  __int64 (__fastcall *v476)(__int64, __int64); // rbx
  MsiString *v477; // rax
  __int64 v478; // rax
  __int64 v479; // rax
  __int64 v480; // rax
  __int64 v481; // rbx
  __int64 v482; // rax
  __int64 v483; // rax
  _QWORD *v484; // rbx
  __int64 v485; // rax
  __int64 v486; // rax
  _QWORD *v487; // rax
  __int64 v488; // rax
  const unsigned __int16 *v489; // rax
  const unsigned __int16 *v490; // r9
  bool v491; // bl
  __int64 v492; // rax
  MsiString *v493; // rax
  void (__fastcall *v494)(__int64, __int64, __int64); // rbx
  MsiString *v495; // rax
  __int64 v496; // rax
  unsigned int v497; // ebx
  char v498; // di
  CRestartManagerWrapper *Instance; // rsi
  unsigned int v500; // eax
  const unsigned __int16 *v501; // rax
  __int64 v502; // rax
  int v503; // r14d
  MsiString *v504; // rax
  __int64 v505; // rax
  CMsiSQMSession *v506; // rax
  unsigned int v507; // r8d
  int Disable; // eax
  CMsiSQMSession *v509; // rax
  unsigned int started; // eax
  void (__fastcall *v511)(__int64, __int64, __int64); // rdi
  const unsigned __int16 *v512; // rax
  MsiString *v513; // rax
  __int64 v514; // rbx
  MsiString *v515; // rax
  __int64 v516; // rax
  int v517; // eax
  __int64 v518; // rax
  __int64 v519; // rax
  __int64 v520; // rax
  __int64 v521; // rax
  __int64 v522; // rax
  __int64 v523; // rax
  __int64 v524; // rax
  __int64 v525; // rax
  __int64 v526; // rdi
  __int64 (__fastcall *v527)(__int64, const WCHAR *, __int64); // rbx
  __int64 v528; // rax
  __int64 v529; // rax
  __int64 v530; // rax
  unsigned int v531; // r14d
  void (__fastcall *v532)(__int64, __int64, __int64); // rbx
  MsiString *v533; // rax
  __int64 v534; // rax
  __int64 v535; // rax
  MsiString *v536; // rax
  int v537; // ebx
  __int64 v538; // rax
  MsiString *v539; // rax
  char v540; // bl
  const unsigned __int16 *v541; // rax
  struct IUnknown v542; // rdi
  HRESULT (__stdcall *v543)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v544; // rax
  __int64 v545; // rax
  GUIDAndSequence *v546; // rcx
  ULONG (__stdcall *v547)(IUnknown *); // rdi
  MsiString *v548; // rax
  __int64 v549; // rbx
  MsiString *v550; // rax
  __int64 v551; // rax
  char v552; // si
  struct IUnknown v553; // rdi
  HRESULT (__stdcall *v554)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v555; // rax
  __int64 v556; // rax
  GUIDAndSequence *v557; // rcx
  ULONG (__stdcall *v558)(IUnknown *); // rdi
  MsiString *v559; // rax
  __int64 v560; // rbx
  MsiString *v561; // rax
  __int64 v562; // rax
  CMsiSQMSession *v563; // rax
  void (__fastcall *v564)(__int64, __int64, __int64); // rdi
  __int64 v565; // rbx
  MsiString *v566; // rax
  __int64 v567; // rax
  __int64 v568; // rax
  _QWORD *v569; // rax
  const unsigned __int16 *v570; // rax
  void (__fastcall *v571)(__int64, __int64, __int64); // rdi
  __int64 v572; // rbx
  MsiString *v573; // rax
  __int64 v574; // rax
  void (__fastcall *v575)(__int64, __int64, __int64); // rdi
  __int64 v576; // rax
  _QWORD *v577; // rax
  __int64 v578; // rbx
  MsiString *v579; // rax
  __int64 v580; // rax
  void (__fastcall *v581)(__int64, __int64, __int64); // rdi
  __int64 v582; // rax
  _QWORD *v583; // rax
  __int64 v584; // rbx
  MsiString *v585; // rax
  __int64 v586; // rax
  void (__fastcall *v587)(__int64, __int64, __int64); // rdi
  __int64 v588; // rbx
  MsiString *v589; // rax
  __int64 v590; // rax
  void (__fastcall *v591)(__int64, __int64, __int64); // rdi
  __int64 v592; // rbx
  MsiString *v593; // rax
  __int64 v594; // rax
  void (__fastcall *v595)(__int64, __int64, __int64); // rdi
  __int64 v596; // rbx
  MsiString *v597; // rax
  __int64 v598; // rax
  __int64 (__fastcall *v599)(__int64, __int64); // rbx
  MsiString *v600; // rax
  __int64 v601; // rax
  unsigned int v602; // ebx
  void (__fastcall *v603)(__int64, __int64, _QWORD); // rdi
  MsiString *v604; // rax
  __int64 v605; // rax
  struct IMsiDatabase *v606; // rax
  __int64 v607; // rsi
  __int64 (__fastcall *v608)(__int64, __int64, _QWORD, __int64, __int64); // rdi
  __int64 v609; // rbx
  __int64 v610; // rax
  _QWORD *v611; // rax
  __int64 v612; // rax
  __int64 v613; // r9
  unsigned int v614; // r14d
  __int64 v615; // rdi
  __int64 (__fastcall *v616)(__int64, __int64, __int64); // rbx
  __int64 v617; // rax
  _QWORD *v618; // rax
  __int64 v619; // rax
  int v620; // edi
  MsiString *v621; // rsi
  __int64 (__fastcall *v622)(__int64, __int64); // rbx
  __int64 v623; // rax
  __int64 v624; // rax
  __int64 (__fastcall *v625)(__int64, __int64); // rbx
  __int64 v626; // rax
  __int64 v627; // rax
  int v629; // edi
  __int64 (__fastcall *v630)(__int64, __int64); // rbx
  MsiString *v631; // rax
  __int64 v632; // rax
  int v633; // ebx
  void (__fastcall *v634)(__int64, __int64, __int64); // rbx
  MsiString *v635; // rax
  __int64 v636; // rax
  GUIDAndSequence *v637; // rcx
  void (__fastcall *v638)(__int64, __int64, __int64); // rbx
  MsiString *v639; // rax
  __int64 v640; // rax
  void (__fastcall *v641)(__int64, __int64, __int64); // rbx
  MsiString *v642; // rax
  __int64 v643; // rax
  __int64 v644; // rax
  MsiString *v645; // rax
  int v646; // esi
  void (__fastcall *v647)(__int64, __int64, __int64); // rbx
  MsiString *v648; // rax
  __int64 v649; // rax
  const struct IMsiString *v650; // rax
  IMsiData *v651; // rax
  void (__fastcall *v652)(__int64, __int64, __int64); // rdi
  const struct IMsiString *v653; // rax
  _QWORD *v654; // rax
  __int64 v655; // rbx
  MsiString *v656; // rax
  __int64 v657; // rax
  void (__fastcall *v658)(__int64, __int64, __int64); // rdi
  __int64 v659; // rbx
  MsiString *v660; // rax
  __int64 v661; // rax
  void (__fastcall *v662)(__int64, __int64, __int64); // rdi
  __int64 v663; // rbx
  MsiString *v664; // rax
  __int64 v665; // rax
  __int64 v666; // rax
  __int64 v667; // rax
  MsiString *v668; // rax
  __int64 v669; // rax
  MsiString *v670; // rax
  bool v671; // bl
  __int64 v672; // rdi
  unsigned int (__fastcall *v673)(__int64, __int64); // rbx
  MsiString *v674; // rax
  __int64 v675; // rax
  bool v676; // di
  unsigned int (__fastcall *v677)(__int64, __int64); // rbx
  MsiString *v678; // rax
  __int64 v679; // rax
  bool v680; // bl
  unsigned int (__fastcall *v681)(__int64, __int64); // rbx
  MsiString *v682; // rax
  __int64 v683; // rax
  unsigned int (__fastcall *v684)(__int64, __int64); // rbx
  MsiString *v685; // rax
  __int64 v686; // rax
  char v687; // bl
  int v688; // ebx
  int v689; // eax
  void (__fastcall *v690)(__int64, __int64, _QWORD); // rbx
  unsigned int v691; // eax
  CMsiEmbeddedUIManager *v692; // rbx
  struct IMsiDatabase *v693; // rax
  struct CMsiCustomActionManager *CustomActionManager; // rax
  int v695; // eax
  bool v696; // bl
  struct IMsiRecord *v697; // rax
  __int64 v698; // rax
  __int64 v699; // rax
  __int64 v700; // rax
  unsigned int v701; // eax
  __int64 v702; // rax
  __int64 v703; // rax
  __int64 v704; // rcx
  void (__fastcall *v705)(__int64, __int64, __int64); // rbx
  MsiString *v706; // rax
  __int64 v707; // rax
  void (__fastcall *v708)(__int64, __int64, _QWORD); // rdi
  MsiString *v709; // rax
  __int64 v710; // rax
  __int64 v711; // rax
  void (__fastcall *v712)(__int64, __int64, bool); // rbx
  int v713; // eax
  int v714; // eax
  __int64 (__fastcall *v715)(__int64, __int64); // rbx
  MsiString *v716; // rax
  __int64 v717; // rax
  int v718; // ebx
  __int64 v719; // rax
  MsiString *v720; // rax
  __int64 v721; // rax
  MsiString *v722; // rax
  bool v723; // di
  int v724; // ebx
  int v725; // ebx
  unsigned int v726; // r15d
  void (__fastcall *v727)(__int64, __int64, _QWORD); // rbx
  MsiString *v728; // rax
  __int64 v729; // rax
  unsigned int v730; // eax
  void (__fastcall *v731)(__int64, __int64, __int64); // rbx
  MsiString *v732; // rax
  __int64 v733; // rax
  void (__fastcall *v734)(__int64, __int64, __int64); // rbx
  MsiString *v735; // rax
  __int64 v736; // rax
  void (__fastcall *v737)(__int64, __int64, __int64); // rbx
  MsiString *v738; // rax
  __int64 v739; // rax
  void (__fastcall *v740)(__int64, __int64, __int64); // rbx
  MsiString *v741; // rax
  __int64 v742; // rax
  __int64 v743; // rax
  MsiString *v744; // rax
  int v745; // ebx
  __int64 v746; // rax
  MsiString *v747; // rax
  int v748; // ebx
  const unsigned __int16 *v749; // r9
  __int64 v750; // rax
  _QWORD *v751; // rax
  int v752; // ebx
  __int64 v753; // rax
  const unsigned __int16 *v754; // rax
  unsigned int v755; // edi
  __int64 v756; // rax
  MsiString *v757; // rax
  int v758; // ebx
  void (__fastcall *v759)(__int64, __int64, _QWORD); // rbx
  MsiString *v760; // rax
  __int64 v761; // rax
  __int64 v762; // rsi
  __int64 (__fastcall *v763)(__int64, __int64, _QWORD, __int64); // rdi
  __int64 v764; // rbx
  MsiString *v765; // rax
  __int64 v766; // rax
  __int64 v767; // rax
  __int64 v768; // rax
  __int64 v769; // rax
  __int64 (__fastcall *v770)(__int64, __int64); // rbx
  MsiString *v771; // rax
  __int64 v772; // rax
  unsigned int v773; // ebx
  __int64 v774; // rax
  __int64 v775; // rax
  __int64 v776; // rdi
  void (__fastcall *v777)(__int64, __int64, _QWORD); // rbx
  __int64 v778; // rax
  unsigned int v779; // eax
  void (__fastcall *v780)(__int64, __int64, __int64); // rbx
  __int64 v781; // rax
  __int64 v782; // rax
  __int64 v783; // rax
  __int64 v784; // rax
  void (__fastcall *v785)(__int64, __int64, __int64); // rbx
  __int64 v786; // rax
  CMsiSQMSession *v787; // rax
  CMsiSQMSession *v788; // rax
  unsigned __int16 *v789; // rbx
  CMsiSQMSession *v790; // rax
  CMsiSQMSession *v791; // rax
  CMsiCustomActionManager *v792; // rax
  int lpString2; // [rsp+20h] [rbp-E0h]
  unsigned int lpString2a; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  int cchCount2b[2]; // [rsp+28h] [rbp-D8h]
  int cchCount2a; // [rsp+28h] [rbp-D8h]
  char *v798; // [rsp+30h] [rbp-D0h]
  int v799; // [rsp+30h] [rbp-D0h]
  int v800; // [rsp+38h] [rbp-C8h]
  int v801; // [rsp+38h] [rbp-C8h]
  int v802; // [rsp+40h] [rbp-C0h]
  int v803; // [rsp+40h] [rbp-C0h]
  int v804; // [rsp+48h] [rbp-B8h]
  int v805; // [rsp+48h] [rbp-B8h]
  int v806; // [rsp+50h] [rbp-B0h]
  int v807; // [rsp+60h] [rbp-A0h]
  int v808; // [rsp+60h] [rbp-A0h]
  int v809; // [rsp+60h] [rbp-A0h]
  int v810; // [rsp+60h] [rbp-A0h]
  int v811; // [rsp+60h] [rbp-A0h]
  int v812; // [rsp+60h] [rbp-A0h]
  int v813; // [rsp+60h] [rbp-A0h]
  int v814; // [rsp+60h] [rbp-A0h]
  int v815; // [rsp+60h] [rbp-A0h]
  int v816; // [rsp+60h] [rbp-A0h]
  int v817; // [rsp+60h] [rbp-A0h]
  int v818; // [rsp+60h] [rbp-A0h]
  IMsiData *v819; // [rsp+70h] [rbp-90h] BYREF
  IMsiData *v820; // [rsp+78h] [rbp-88h] BYREF
  IMsiData *v821; // [rsp+80h] [rbp-80h] BYREF
  __int64 v822; // [rsp+88h] [rbp-78h] BYREF
  IMsiData *v823; // [rsp+90h] [rbp-70h] BYREF
  IMsiData *v824; // [rsp+98h] [rbp-68h] BYREF
  IMsiData *v825; // [rsp+A0h] [rbp-60h] BYREF
  bool v826; // [rsp+A8h] [rbp-58h]
  IMsiData *v827; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v828; // [rsp+B8h] [rbp-48h] BYREF
  IMsiData *v829; // [rsp+C0h] [rbp-40h] BYREF
  IMsiData *v830; // [rsp+C8h] [rbp-38h] BYREF
  IMsiData *v831; // [rsp+D0h] [rbp-30h] BYREF
  IMsiData *v832; // [rsp+D8h] [rbp-28h] BYREF
  IMsiData *v833; // [rsp+E0h] [rbp-20h] BYREF
  IMsiData *v834; // [rsp+E8h] [rbp-18h] BYREF
  IMsiData *v835; // [rsp+F0h] [rbp-10h] BYREF
  IMsiData *v836; // [rsp+F8h] [rbp-8h] BYREF
  IMsiData *v837; // [rsp+100h] [rbp+0h] BYREF
  IMsiData *v838; // [rsp+108h] [rbp+8h] BYREF
  IMsiData *v839; // [rsp+110h] [rbp+10h] BYREF
  IMsiData *v840; // [rsp+118h] [rbp+18h] BYREF
  IMsiData *v841; // [rsp+120h] [rbp+20h] BYREF
  char v842; // [rsp+128h] [rbp+28h]
  struct IMsiSummaryInfo *v843; // [rsp+130h] [rbp+30h] BYREF
  char v844; // [rsp+138h] [rbp+38h] BYREF
  char v845; // [rsp+139h] [rbp+39h]
  IMsiData *v846; // [rsp+140h] [rbp+40h] BYREF
  IMsiData *v847; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v848; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v849; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v850; // [rsp+15Ch] [rbp+5Ch]
  IMsiData *v851; // [rsp+160h] [rbp+60h] BYREF
  IMsiData *v852; // [rsp+168h] [rbp+68h] BYREF
  int v853; // [rsp+170h] [rbp+70h] BYREF
  __int64 v854; // [rsp+178h] [rbp+78h] BYREF
  __int64 v855; // [rsp+180h] [rbp+80h] BYREF
  __int64 v856; // [rsp+188h] [rbp+88h] BYREF
  char v857; // [rsp+190h] [rbp+90h] BYREF
  char v858[3]; // [rsp+191h] [rbp+91h] BYREF
  unsigned int v859; // [rsp+194h] [rbp+94h]
  char v860[8]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v861; // [rsp+1A0h] [rbp+A0h] BYREF
  int v862; // [rsp+1A8h] [rbp+A8h]
  __int64 v863; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v864; // [rsp+1B8h] [rbp+B8h]
  bool v865; // [rsp+1BCh] [rbp+BCh]
  bool v866; // [rsp+1BDh] [rbp+BDh]
  int v867; // [rsp+1C0h] [rbp+C0h] BYREF
  void *v868; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v869; // [rsp+1D0h] [rbp+D0h] BYREF
  __int16 v870; // [rsp+1D8h] [rbp+D8h] BYREF
  char v871[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v872; // [rsp+1E8h] [rbp+E8h]
  char v873[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v874; // [rsp+1F8h] [rbp+F8h] BYREF
  IMsiData *v875; // [rsp+200h] [rbp+100h] BYREF
  IMsiData *v876; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int16 *v877; // [rsp+210h] [rbp+110h]
  int v878; // [rsp+218h] [rbp+118h] BYREF
  enum tagINSTALLSTATE ProductState; // [rsp+21Ch] [rbp+11Ch]
  MSIHANDLE v880; // [rsp+220h] [rbp+120h] BYREF
  __int64 v881; // [rsp+228h] [rbp+128h] BYREF
  __int64 v882; // [rsp+230h] [rbp+130h]
  __int64 v883; // [rsp+238h] [rbp+138h] BYREF
  __int64 v884; // [rsp+240h] [rbp+140h] BYREF
  __int64 v885; // [rsp+248h] [rbp+148h] BYREF
  __int64 v886; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 *v887; // [rsp+258h] [rbp+158h]
  IMsiData *v888; // [rsp+260h] [rbp+160h] BYREF
  __int64 v889; // [rsp+268h] [rbp+168h] BYREF
  __int64 v890; // [rsp+270h] [rbp+170h] BYREF
  unsigned int v891; // [rsp+278h] [rbp+178h] BYREF
  unsigned int v892; // [rsp+27Ch] [rbp+17Ch] BYREF
  unsigned int v893; // [rsp+280h] [rbp+180h] BYREF
  unsigned int v894; // [rsp+284h] [rbp+184h] BYREF
  unsigned int v895; // [rsp+288h] [rbp+188h] BYREF
  int v896; // [rsp+28Ch] [rbp+18Ch] BYREF
  int v897; // [rsp+290h] [rbp+190h] BYREF
  int v898; // [rsp+294h] [rbp+194h] BYREF
  int v899; // [rsp+298h] [rbp+198h] BYREF
  IMsiData *v900; // [rsp+2A0h] [rbp+1A0h] BYREF
  IMsiData *v901; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v902; // [rsp+2B0h] [rbp+1B0h] BYREF
  IMsiData *v903; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v904; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v905; // [rsp+2C8h] [rbp+1C8h] BYREF
  IMsiData *v906; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v907; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v908; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v909[8]; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v910; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v911[8]; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int64 v912; // [rsp+300h] [rbp+200h] BYREF
  __int64 v913; // [rsp+308h] [rbp+208h] BYREF
  __int64 v914; // [rsp+310h] [rbp+210h] BYREF
  __int64 v915; // [rsp+318h] [rbp+218h] BYREF
  char v916[8]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v917; // [rsp+328h] [rbp+228h] BYREF
  IMsiData *v918; // [rsp+330h] [rbp+230h] BYREF
  char v919[8]; // [rsp+338h] [rbp+238h] BYREF
  __int64 v920; // [rsp+340h] [rbp+240h] BYREF
  __int64 v921; // [rsp+348h] [rbp+248h] BYREF
  __int64 v922; // [rsp+350h] [rbp+250h] BYREF
  IMsiData *v923; // [rsp+358h] [rbp+258h] BYREF
  const unsigned __int16 *v924; // [rsp+360h] [rbp+260h]
  __int64 v925; // [rsp+368h] [rbp+268h] BYREF
  __int64 v926; // [rsp+370h] [rbp+270h] BYREF
  IMsiData *v927; // [rsp+378h] [rbp+278h] BYREF
  __int64 v928; // [rsp+380h] [rbp+280h] BYREF
  IMsiData *v929; // [rsp+388h] [rbp+288h] BYREF
  IMsiData *v930; // [rsp+390h] [rbp+290h] BYREF
  IMsiData *v931; // [rsp+398h] [rbp+298h] BYREF
  IMsiData *v932; // [rsp+3A0h] [rbp+2A0h] BYREF
  IMsiData *v933; // [rsp+3A8h] [rbp+2A8h] BYREF
  IMsiData *v934; // [rsp+3B0h] [rbp+2B0h] BYREF
  IMsiData *v935; // [rsp+3B8h] [rbp+2B8h] BYREF
  IMsiData *v936; // [rsp+3C0h] [rbp+2C0h] BYREF
  IMsiData *v937; // [rsp+3C8h] [rbp+2C8h] BYREF
  IMsiData *v938; // [rsp+3D0h] [rbp+2D0h] BYREF
  IMsiData *v939; // [rsp+3D8h] [rbp+2D8h] BYREF
  IMsiData *v940; // [rsp+3E0h] [rbp+2E0h] BYREF
  struct IMsiRecord *v941; // [rsp+3E8h] [rbp+2E8h] BYREF
  struct IMsiRecord *v942; // [rsp+3F0h] [rbp+2F0h] BYREF
  IMsiData *v943; // [rsp+3F8h] [rbp+2F8h] BYREF
  IMsiData *v944; // [rsp+400h] [rbp+300h] BYREF
  IMsiData *v945; // [rsp+408h] [rbp+308h] BYREF
  char v946[8]; // [rsp+410h] [rbp+310h] BYREF
  char v947[8]; // [rsp+418h] [rbp+318h] BYREF
  char v948[8]; // [rsp+420h] [rbp+320h] BYREF
  char v949[8]; // [rsp+428h] [rbp+328h] BYREF
  char v950[8]; // [rsp+430h] [rbp+330h] BYREF
  char v951[8]; // [rsp+438h] [rbp+338h] BYREF
  char v952[8]; // [rsp+440h] [rbp+340h] BYREF
  char v953[8]; // [rsp+448h] [rbp+348h] BYREF
  char v954[8]; // [rsp+450h] [rbp+350h] BYREF
  char v955[8]; // [rsp+458h] [rbp+358h] BYREF
  char v956[8]; // [rsp+460h] [rbp+360h] BYREF
  char v957[8]; // [rsp+468h] [rbp+368h] BYREF
  char v958[8]; // [rsp+470h] [rbp+370h] BYREF
  char v959[8]; // [rsp+478h] [rbp+378h] BYREF
  char v960[8]; // [rsp+480h] [rbp+380h] BYREF
  char v961[8]; // [rsp+488h] [rbp+388h] BYREF
  char v962[8]; // [rsp+490h] [rbp+390h] BYREF
  char v963[8]; // [rsp+498h] [rbp+398h] BYREF
  char v964[8]; // [rsp+4A0h] [rbp+3A0h] BYREF
  char v965[8]; // [rsp+4A8h] [rbp+3A8h] BYREF
  char v966[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v967[8]; // [rsp+4B8h] [rbp+3B8h] BYREF
  char v968[8]; // [rsp+4C0h] [rbp+3C0h] BYREF
  char v969[8]; // [rsp+4C8h] [rbp+3C8h] BYREF
  char v970[8]; // [rsp+4D0h] [rbp+3D0h] BYREF
  char v971[8]; // [rsp+4D8h] [rbp+3D8h] BYREF
  char v972[8]; // [rsp+4E0h] [rbp+3E0h] BYREF
  char v973[8]; // [rsp+4E8h] [rbp+3E8h] BYREF
  char v974[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  char v975[8]; // [rsp+4F8h] [rbp+3F8h] BYREF
  __int64 v976; // [rsp+500h] [rbp+400h] BYREF
  char v977[8]; // [rsp+508h] [rbp+408h] BYREF
  char v978[8]; // [rsp+510h] [rbp+410h] BYREF
  char v979[8]; // [rsp+518h] [rbp+418h] BYREF
  char v980[8]; // [rsp+520h] [rbp+420h] BYREF
  char v981[8]; // [rsp+528h] [rbp+428h] BYREF
  char v982[8]; // [rsp+530h] [rbp+430h] BYREF
  char v983[8]; // [rsp+538h] [rbp+438h] BYREF
  char v984[8]; // [rsp+540h] [rbp+440h] BYREF
  char v985[8]; // [rsp+548h] [rbp+448h] BYREF
  __int64 v986; // [rsp+550h] [rbp+450h] BYREF
  char v987[8]; // [rsp+558h] [rbp+458h] BYREF
  __int64 v988; // [rsp+560h] [rbp+460h] BYREF
  char v989[8]; // [rsp+568h] [rbp+468h] BYREF
  char v990[8]; // [rsp+570h] [rbp+470h] BYREF
  char v991[8]; // [rsp+578h] [rbp+478h] BYREF
  __int64 v992; // [rsp+580h] [rbp+480h] BYREF
  char v993[8]; // [rsp+588h] [rbp+488h] BYREF
  __int64 v994; // [rsp+590h] [rbp+490h] BYREF
  __int64 v995; // [rsp+598h] [rbp+498h] BYREF
  __int64 v996; // [rsp+5A0h] [rbp+4A0h] BYREF
  char v997[8]; // [rsp+5A8h] [rbp+4A8h] BYREF
  char v998[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  char v999[8]; // [rsp+5B8h] [rbp+4B8h] BYREF
  char v1000[8]; // [rsp+5C0h] [rbp+4C0h] BYREF
  char v1001[8]; // [rsp+5C8h] [rbp+4C8h] BYREF
  __int64 v1002; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v1003; // [rsp+5D8h] [rbp+4D8h] BYREF
  char v1004[8]; // [rsp+5E0h] [rbp+4E0h] BYREF
  char v1005[8]; // [rsp+5E8h] [rbp+4E8h] BYREF
  char v1006[8]; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v1007[8]; // [rsp+5F8h] [rbp+4F8h] BYREF
  char v1008[8]; // [rsp+600h] [rbp+500h] BYREF
  char v1009[8]; // [rsp+608h] [rbp+508h] BYREF
  char v1010[8]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v1011; // [rsp+618h] [rbp+518h] BYREF
  char v1012[8]; // [rsp+620h] [rbp+520h] BYREF
  char v1013[8]; // [rsp+628h] [rbp+528h] BYREF
  __int64 v1014; // [rsp+630h] [rbp+530h] BYREF
  char v1015[8]; // [rsp+638h] [rbp+538h] BYREF
  __int64 v1016; // [rsp+640h] [rbp+540h] BYREF
  char v1017[8]; // [rsp+648h] [rbp+548h] BYREF
  char v1018[8]; // [rsp+650h] [rbp+550h] BYREF
  char v1019[8]; // [rsp+658h] [rbp+558h] BYREF
  char v1020[8]; // [rsp+660h] [rbp+560h] BYREF
  char v1021[8]; // [rsp+668h] [rbp+568h] BYREF
  __int64 v1022; // [rsp+670h] [rbp+570h] BYREF
  __int64 v1023; // [rsp+678h] [rbp+578h] BYREF
  char v1024[8]; // [rsp+680h] [rbp+580h] BYREF
  char v1025[8]; // [rsp+688h] [rbp+588h] BYREF
  char v1026[8]; // [rsp+690h] [rbp+590h] BYREF
  char v1027[8]; // [rsp+698h] [rbp+598h] BYREF
  __int64 v1028; // [rsp+6A0h] [rbp+5A0h] BYREF
  char v1029[8]; // [rsp+6A8h] [rbp+5A8h] BYREF
  char v1030[8]; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v1031; // [rsp+6B8h] [rbp+5B8h] BYREF
  char v1032[8]; // [rsp+6C0h] [rbp+5C0h] BYREF
  char v1033[8]; // [rsp+6C8h] [rbp+5C8h] BYREF
  __int64 v1034; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v1035; // [rsp+6D8h] [rbp+5D8h] BYREF
  char v1036[8]; // [rsp+6E0h] [rbp+5E0h] BYREF
  char v1037[8]; // [rsp+6E8h] [rbp+5E8h] BYREF
  char v1038[8]; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v1039[8]; // [rsp+6F8h] [rbp+5F8h] BYREF
  char v1040[8]; // [rsp+700h] [rbp+600h] BYREF
  char v1041[8]; // [rsp+708h] [rbp+608h] BYREF
  char v1042[8]; // [rsp+710h] [rbp+610h] BYREF
  __int64 v1043; // [rsp+718h] [rbp+618h] BYREF
  __int64 v1044; // [rsp+720h] [rbp+620h] BYREF
  char v1045[8]; // [rsp+728h] [rbp+628h] BYREF
  char v1046[8]; // [rsp+730h] [rbp+630h] BYREF
  char v1047[8]; // [rsp+738h] [rbp+638h] BYREF
  char v1048[8]; // [rsp+740h] [rbp+640h] BYREF
  char v1049[8]; // [rsp+748h] [rbp+648h] BYREF
  __int64 v1050; // [rsp+750h] [rbp+650h] BYREF
  __int64 v1051; // [rsp+758h] [rbp+658h] BYREF
  __int64 v1052; // [rsp+760h] [rbp+660h] BYREF
  __int64 v1053; // [rsp+768h] [rbp+668h] BYREF
  char v1054[8]; // [rsp+770h] [rbp+670h] BYREF
  char v1055[8]; // [rsp+778h] [rbp+678h] BYREF
  __int64 v1056; // [rsp+780h] [rbp+680h] BYREF
  char v1057[8]; // [rsp+788h] [rbp+688h] BYREF
  wchar_t *String; // [rsp+790h] [rbp+690h] BYREF
  int v1059; // [rsp+798h] [rbp+698h]
  int v1060; // [rsp+79Ch] [rbp+69Ch]
  _BYTE v1061[208]; // [rsp+7A0h] [rbp+6A0h] BYREF
  GUID iid; // [rsp+870h] [rbp+770h] BYREF
  unsigned __int16 *v1063; // [rsp+880h] [rbp+780h] BYREF
  int v1064; // [rsp+88Ch] [rbp+78Ch]
  _BYTE v1065[24]; // [rsp+898h] [rbp+798h] BYREF
  _BYTE v1066[32]; // [rsp+8B0h] [rbp+7B0h] BYREF
  _BYTE v1067[96]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _BYTE v1068[64]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v1069[8]; // [rsp+970h] [rbp+870h] BYREF
  _QWORD v1070[2]; // [rsp+978h] [rbp+878h] BYREF
  char v1071[24]; // [rsp+988h] [rbp+888h] BYREF
  char v1072[24]; // [rsp+9A0h] [rbp+8A0h] BYREF
  char v1073[24]; // [rsp+9B8h] [rbp+8B8h] BYREF

  v8 = a7;
  v924 = a5;
  v9 = a4;
  v877 = a4;
  v829 = (IMsiData *)&MsiString::s_NullString;
  v10 = a2;
  v11 = 5;
  v827 = (IMsiData *)&MsiString::s_NullString;
  v832 = (IMsiData *)&MsiString::s_NullString;
  v12 = 0;
  v837 = (IMsiData *)&MsiString::s_NullString;
  v834 = (IMsiData *)&MsiString::s_NullString;
  v820 = (IMsiData *)&MsiString::s_NullString;
  v831 = (IMsiData *)&MsiString::s_NullString;
  v833 = (IMsiData *)&MsiString::s_NullString;
  v835 = (IMsiData *)&MsiString::s_NullString;
  v838 = (IMsiData *)&MsiString::s_NullString;
  v830 = (IMsiData *)&MsiString::s_NullString;
  v840 = (IMsiData *)&MsiString::s_NullString;
  v841 = (IMsiData *)&MsiString::s_NullString;
  v836 = (IMsiData *)&MsiString::s_NullString;
  v839 = (IMsiData *)&MsiString::s_NullString;
  v887 = a2;
  v848 = a3;
  v882 = a7;
  v859 = 0;
  v856 = 0;
  if ( a3 == 5 )
  {
    v13 = 1;
    v848 = 0;
    v862 = 1;
  }
  else
  {
    v862 = 0;
    v13 = 0;
    if ( a3 > 4 )
    {
      v848 = 2;
    }
    else if ( a3 == 3 )
    {
      goto LABEL_11;
    }
  }
  if ( g_scServerContext != 2 )
  {
    if ( !IsInteractiveWindowStation() )
    {
      v848 = 3;
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"CMsiEngine::DoInitialize: UI level set to none because we're running in a non-interactive context.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
    }
LABEL_11:
    if ( g_scServerContext != 2 )
      goto LABEL_14;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  MsiHandle = CreateMsiHandle((struct IUnknown *)a1, 790542);
  if ( MsiHandle )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 376LL))(a1, MsiHandle);
    ((void (__fastcall *)(_QWORD))FUSION::SetMSIHandleForLogging)(*(unsigned int *)(a1 + 100));
  }
LABEL_14:
  v822 = 0;
  v828 = 0;
  *(_DWORD *)(a1 + 584) = a6;
  if ( (a6 & 0x800) != 0 )
    *(_BYTE *)(a1 + 606) = 1;
  v826 = CMsiEngine::IgnoreMachineState((CMsiEngine *)a1);
  if ( g_dmDiagnosticMode )
  {
    v15 = &Default;
    if ( (*(_BYTE *)(a1 + 584) & 8) == 0 )
      v15 = L" not";
    DebugString(9, 0, 0, L"End dialog%s enabled", v15, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
  }
  LODWORD(qword_180309704) = qword_180309704 + 1;
  if ( !v13 )
  {
    v16 = *(_QWORD *)(a1 + 168);
    if ( v16 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 168LL))(v16, 1);
LABEL_23:
      CComPointer<IMsiDatabase>::operator=(&v828, v17);
      goto LABEL_24;
    }
    v21 = *(_QWORD *)(a1 + 160);
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
      v17 = *(_QWORD *)(a1 + 160);
      goto LABEL_23;
    }
    if ( v10 && *v10 )
    {
      v22 = *(_QWORD *)(a1 + 128);
      v23 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v22 + 224LL);
      v24 = CComPointer<IEnumMsiRecord>::operator=(&v828);
      v25 = v23(v22, v887, 0, v24);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v856, v25) )
      {
LABEL_245:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
        IMsiData::Release(v839);
        IMsiData::Release(v836);
        IMsiData::Release(v841);
        IMsiData::Release(v840);
        IMsiData::Release(v830);
        IMsiData::Release(v838);
        IMsiData::Release(v835);
        IMsiData::Release(v833);
        IMsiData::Release(v831);
        IMsiData::Release(v820);
        IMsiData::Release(v834);
        IMsiData::Release(v837);
        IMsiData::Release(v832);
        IMsiData::Release(v827);
        IMsiData::Release(v829);
LABEL_691:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v856);
        return v11;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v828 + 168LL))(v828, 0) )
      {
        v11 = 6;
        goto LABEL_245;
      }
      v10 = v887;
    }
LABEL_24:
    IMsiData::Release(v835);
    v835 = (IMsiData *)&MsiString::s_NullString;
    v18 = *(_QWORD *)MsiString::MsiString((MsiString *)&v929, L"CURRENTDIRECTORY");
    IMsiData::Release(v834);
    v834 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v837);
    v837 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v832);
    v832 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v827);
    v827 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v829);
    v829 = (IMsiData *)&MsiString::s_NullString;
    ProcessCommandLine(v9, &v829, &v827, &v832, &v837, &v834, 0, v18, &v835, 1, a1 + 448, 0, 0);
    IMsiData::Release(v929);
    if ( !(unsigned int)MsiString::operator int(&v829) )
      MsiString::operator=(&v829, &Default);
    v19 = (const WCHAR *)MsiString::operator unsigned short const *(&v834);
    if ( CompareStringW(0x409u, 1u, v19, -1, L"ADMIN", -1) == 2 )
    {
      v20 = 1;
    }
    else
    {
      v26 = (const WCHAR *)MsiString::operator unsigned short const *(&v834);
      if ( CompareStringW(0x409u, 1u, v26, -1, L"ADVERTISE", -1) != 2 )
        goto LABEL_29;
      v20 = 2;
    }
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, v20, 1);
LABEL_29:
    v13 = v862;
  }
  v850 = -1;
  v845 = 0;
  MsiString::MsiString((MsiString *)&v819, v10);
  v821 = (IMsiData *)&MsiString::s_NullString;
  MsiString::operator=(a1 + 520, &v819);
  if ( g_dmDiagnosticMode )
  {
    v27 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v819);
    DebugString(9, 0, 0, L"Original package ==> %s", v27, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
  }
  v849 = 0;
  v823 = (IMsiData *)&MsiString::s_NullString;
  v825 = (IMsiData *)&MsiString::s_NullString;
  v824 = (IMsiData *)&MsiString::s_NullString;
  v853 = 0;
  ProductState = INSTALLSTATE_UNKNOWN;
  v864 = 3;
  v872 = 0;
  memset_0(v1061, 0, 0xC8u);
  v1059 = 100;
  String = (wchar_t *)v1061;
  v28 = *(_QWORD *)(a1 + 168);
  if ( v28 )
  {
    CComPointer<IMsiDatabase>::operator=(&v822, v28);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 168) + 8LL))(*(_QWORD *)(a1 + 168));
  }
  v11 = 6;
  if ( !v13 )
  {
    if ( (!v10 || !*v10) && !*(_QWORD *)(a1 + 168) )
    {
      v29 = *(_QWORD *)(a1 + 128);
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v29 + 104LL);
      v31 = CComPointer<IEnumMsiRecord>::operator=(&v822);
      v32 = v30(v29, 0, 3, v31);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v856, v32)
        || !(unsigned int)CMsiEngine::CreatePropertyTable(a1, v822, 0, 0) )
      {
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
        IMsiData::Release(v824);
        IMsiData::Release(v825);
        IMsiData::Release(v823);
        IMsiData::Release(v821);
        IMsiData::Release(v819);
        v11 = 5;
        goto LABEL_245;
      }
      goto LABEL_393;
    }
    v33 = v828;
    v34 = *(__int64 (__fastcall **)(__int64, IMsiData **))(*(_QWORD *)v828 + 152LL);
    IMsiData::Release(v821);
    v821 = (IMsiData *)&MsiString::s_NullString;
    v35 = v34(v33, &v821);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v856, v35) )
    {
      v11 = CMsiEngine::PostInitializeError(a1, v856, v821, 5);
      goto LABEL_46;
    }
    if ( g_dmDiagnosticMode )
    {
      v36 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v821);
      DebugString(
        9,
        0,
        0,
        L"Package we're running from ==> %s",
        v36,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v819) )
      MsiString::operator=(&v819, &v821);
    MsiString::operator=(a1 + 512, &v821);
    v37 = *(IMsiData **)(a1 + 448);
    if ( v37 )
      IMsiData::Release(v37);
    *(_QWORD *)(a1 + 448) = v819;
    IMsiData::AddRef(v819);
    v843 = 0;
    *(_DWORD *)(a1 + 404) = 0;
    *(_DWORD *)(a1 + 456) = 0;
    v38 = v828;
    v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v828 + 136LL);
    v40 = CComPointer<IEnumMsiRecord>::operator=(&v843);
    v41 = v39(v38, 0, v40);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v856, v41) )
      goto LABEL_63;
    IMsiData::Release(v836);
    v836 = (IMsiData *)&MsiString::s_NullString;
    CMsiEngine::GetSummaryInfoProperties((CMsiEngine *)a1, v843, &v836, (int *)(a1 + 596));
    *(_BYTE *)(a1 + 600) = PackageInstallsAsLUA(*(_DWORD *)(a1 + 596));
    v42 = (IMsiData *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 392) + 176LL))(
                        *(_QWORD *)(a1 + 392),
                        0,
                        38);
    IMsiData::Release(v833);
    v833 = v42;
    v43 = 0;
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v833) )
    {
LABEL_63:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
      goto LABEL_46;
    }
    if ( (unsigned int)(*(_DWORD *)(a1 + 456) - 30) > 0x1D6
      || !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 128) + 24LL))(*(_QWORD *)(a1 + 128)) )
    {
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      IMsiData::Release(v824);
      IMsiData::Release(v825);
      IMsiData::Release(v823);
      IMsiData::Release(v821);
      IMsiData::Release(v819);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
      IMsiData::Release(v839);
      IMsiData::Release(v836);
      IMsiData::Release(v841);
      IMsiData::Release(v840);
      IMsiData::Release(v830);
      IMsiData::Release(v838);
      IMsiData::Release(v835);
      IMsiData::Release(v833);
      IMsiData::Release(v831);
      IMsiData::Release(v820);
      IMsiData::Release(v834);
      IMsiData::Release(v837);
      IMsiData::Release(v832);
      IMsiData::Release(v827);
      IMsiData::Release(v829);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v856);
      return 7;
    }
    v44 = v822;
    if ( !v822 )
    {
      v45 = *(_QWORD *)(a1 + 128);
      v46 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v45 + 112LL);
      v47 = CComPointer<IEnumMsiRecord>::operator=(&v822);
      v48 = v46(v45, v828, 1, v47);
      v43 = 0;
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v856, v48) )
      {
        v11 = CMsiEngine::PostInitializeError(a1, v856, v821, 6);
        goto LABEL_63;
      }
      v44 = v822;
    }
    PropertyTable = CMsiEngine::CreatePropertyTable(a1, v44, L"Property", 1);
    if ( v924 && *v924 )
    {
      MsiString::operator=(&v820, v924);
      MsiString::UpperCase((MsiString *)&v820);
    }
    else if ( PropertyTable )
    {
      v50 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                          a1,
                          L"ProductCode");
      IMsiData::Release(v820);
      v820 = v50;
      v43 = 0;
    }
    IMsiData::Release(v838);
    v838 = (IMsiData *)&MsiString::s_NullString;
    v51 = MsiString::MsiString((MsiString *)&v930, L"MSINEWINSTANCE");
    LOBYTE(v807) = 0;
    v52 = v877;
    ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, *(_QWORD *)v51, &v838, 1, 0, 0, v807);
    IMsiData::Release(v930);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v838) )
    {
      *(_BYTE *)(a1 + 612) = 1;
      v53 = (IMsiData *)MsiString::Extract(&v827, 2, 59);
      IMsiData::Release(v830);
      v830 = v53;
      v43 = 0;
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v820) && !v826 && !*(_BYTE *)(a1 + 612) )
    {
      v54 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
      ProductState = CMsiEngine::GetProductState((CMsiEngine *)a1, v54, (enum Bool *)&v849, (enum Bool *)&v853);
    }
    v847 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v847 = (IMsiData *)&MsiString::s_NullString;
    v55 = MsiString::MsiString((MsiString *)&v931, L"REMOVE");
    LOBYTE(v808) = 0;
    ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, *(_QWORD *)v55, &v847, 1, a1 + 448, 0, v808);
    IMsiData::Release(v931);
    *(_BYTE *)(a1 + 98) = 0;
    if ( (unsigned int)MsiString::Compare(&v847, 0, L"ALL") )
      *(_BYTE *)(a1 + 98) = 1;
    v846 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v846 = (IMsiData *)&MsiString::s_NullString;
    v56 = MsiString::MsiString((MsiString *)&v932, L"CLIENTUILEVEL");
    LOBYTE(v809) = 0;
    ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, *(_QWORD *)v56, &v846, 1, 0, 0, v809);
    IMsiData::Release(v932);
    if ( g_scServerContext )
    {
      if ( !(unsigned int)MsiString::TextSize((MsiString *)&v846) )
        goto LABEL_90;
      v57 = MsiString::operator int(&v846);
      v864 = v57;
      dword_180309774 = v57;
    }
    else
    {
      v57 = v848;
      v864 = v848;
    }
    if ( v57 != 3 )
      goto LABEL_106;
    v43 = 0;
LABEL_90:
    v901 = (IMsiData *)&MsiString::s_NullString;
    v900 = (IMsiData *)&MsiString::s_NullString;
    if ( CMsiTransaction::m_pMsiTransaction )
    {
      if ( CMsiTransaction::FMultiPackageTransaction((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction) )
      {
        IMsiData::Release(v901);
        v901 = (IMsiData *)&MsiString::s_NullString;
        LOBYTE(v810) = 0;
        v12 = 1;
        v58 = *(_QWORD *)MsiString::MsiString((MsiString *)&v933, L"MSICLIENTUSESEXTERNALUI");
        v859 = 1;
        if ( (unsigned int)ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, v58, &v901, 1, a1 + 448, 0, v810) )
        {
          v859 = 1;
          if ( (unsigned int)MsiString::TextSize((MsiString *)&v901) )
          {
            v43 = 1;
            v859 = 1;
          }
        }
      }
    }
    if ( (v12 & 1) != 0 )
    {
      v12 &= ~1u;
      v859 = v12;
      IMsiData::Release(v933);
    }
    if ( v43 )
    {
      v57 = 4;
    }
    else
    {
      IMsiData::Release(v900);
      v59 = v12 | 2;
      v900 = (IMsiData *)&MsiString::s_NullString;
      v60 = MsiString::MsiString((MsiString *)&v934, L"MSICLIENTUSESEMBEDDEDUI");
      v61 = 0;
      LOBYTE(v810) = 0;
      if ( (unsigned int)ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, *(_QWORD *)v60, &v900, 1, a1 + 448, 0, v810) )
        v61 = (unsigned int)MsiString::TextSize((MsiString *)&v900) != 0;
      v12 = v59 & 0xFFFFFFFD;
      v859 = v12;
      IMsiData::Release(v934);
      v62 = !v61;
      v57 = v864;
      if ( !v62 )
        v57 = 4;
    }
    if ( (a6 & 0x800000) != 0 )
      v57 = 4;
    v864 = v57;
    dword_180309774 = v57;
    IMsiData::Release(v900);
    IMsiData::Release(v901);
LABEL_106:
    *(_DWORD *)(a1 + 608) = 0;
    v844 = 0;
    if ( v57 == 3 || (v63 = 0, v842 = 0, g_scServerContext == 2) )
    {
      v63 = 1;
      v842 = 1;
    }
    LOBYTE(v804) = 0;
    LOBYTE(v802) = v63;
    CMsiEngine::ApplyAppCompatTransforms(a1, v887, v52, v822, v820, v833, 1, a1 + 608, v802, v804, &v844);
    if ( v844 && !v849 )
    {
      v906 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a1 + 184LL))(a1, L"ProductName");
      if ( !(unsigned int)MsiString::TextSize((MsiString *)&v906) )
        MsiString::operator=(&v906, &v819);
      v64 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v906);
      DebugString(21, 1u, 1018, v64, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      v65 = CMsiEngine::PostInitializeError(a1, 0, v819, 30);
      v66 = v906;
      v11 = v65;
      goto LABEL_114;
    }
    if ( v853 && !v826 )
    {
      v1060 = 100;
      v67 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
      if ( (unsigned int)GetExpandedProductInfo(v67, L"Transforms") )
        MsiString::operator=(&v827, String);
      v1060 = 100;
      v68 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
      if ( (unsigned int)GetProductInfo(v68, L"Language") )
        MsiString::operator=(&v829, String);
      v1060 = 100;
      v69 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
      if ( (unsigned int)GetProductInfo(v69, L"InstanceType") )
      {
        v70 = MsiString::MsiString((MsiString *)&v935, String);
        v71 = MsiString::operator int(v70);
        IMsiData::Release(v935);
        if ( v71 == 1 )
        {
          v72 = (IMsiData *)MsiString::Extract(&v827, 2, 59);
          IMsiData::Release(v830);
          v830 = v72;
        }
      }
      v1060 = 100;
      v73 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
      if ( (unsigned int)GetProductInfo(v73, L"AuthorizedLUAApp") )
      {
        v74 = MsiString::MsiString((MsiString *)&v936, String);
        v75 = MsiString::operator int(v74);
        IMsiData::Release(v936);
        if ( v75 == 1 )
          *(_BYTE *)(a1 + 97) = 1;
      }
      v1060 = 100;
      v76 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
      if ( (unsigned int)GetProductInfo(v76, L"DeploymentFlags") )
      {
        v77 = wcstol(String, 0, 10);
        if ( v77 > 6 )
          v77 = 0;
        v872 = v77;
      }
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v830) && g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Detected that this product uses a multiple instance transform.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 0x40000, 1);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 0x800000, 1);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 0x1000000, 1);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 0x2000000, 1);
    if ( g_scServerContext == 2 )
      CreateCustomActionManager(1);
    if ( !CMsiEngine::CheckAssemblyPlatformSupport((CMsiEngine *)a1) )
    {
      IMsiData::Release(v846);
      IMsiData::Release(v847);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      IMsiData::Release(v824);
      IMsiData::Release(v825);
      IMsiData::Release(v823);
      IMsiData::Release(v821);
      IMsiData::Release(v819);
      v11 = 33;
      goto LABEL_245;
    }
    if ( (*(_BYTE *)(a1 + 596) & 1) != 0 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 128, 1);
    if ( (*(_BYTE *)(a1 + 596) & 2) != 0 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 2048, 1);
    v78 = a6;
    if ( (a6 & 1) != 0 )
    {
      *(_BYTE *)(a1 + 576) = 1;
      v78 = a6;
    }
    if ( (v78 & 2) != 0 )
    {
      *(_BYTE *)(a1 + 577) = 1;
      v78 = a6;
    }
    if ( (v78 & 8) != 0 )
      *(_BYTE *)(a1 + 578) = 1;
    v79 = (IMsiData *)MsiString::ExtractAndRemove(&v836, 2, 59);
    IMsiData::Release(v839);
    v80 = (_WORD *)(a1 + 604);
    v839 = v79;
    v81 = CMsiEngine::ProcessPlatform(a1, v79, a1 + 604);
    if ( *(_WORD *)(a1 + 604) == 0xFFFF )
      goto LABEL_115;
    g_wPackagePlatform = *(_WORD *)(a1 + 604);
    if ( (a6 & 4) == 0 && v81 )
    {
LABEL_244:
      IMsiData::Release(v846);
      IMsiData::Release(v847);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      IMsiData::Release(v824);
      IMsiData::Release(v825);
      IMsiData::Release(v823);
      IMsiData::Release(v821);
      IMsiData::Release(v819);
      v11 = v81;
      goto LABEL_245;
    }
    if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) == 0
      && (*v80 == 9 || *v80 == 6)
      && *(int *)(a1 + 456) < 150
      || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) == 0
      && (*v80 == 5 || *v80 == 12)
      && *(int *)(a1 + 456) < 500 )
    {
      goto LABEL_115;
    }
    v82 = v826;
    LOBYTE(cchCount2) = v826;
    v870 = 0;
    v81 = CMsiEngine::ProcessLanguage(a1, v836, v829, &v870, 1, cchCount2);
    if ( v81 )
    {
      if ( v853 && !v82 && (unsigned int)MsiString::TextSize((MsiString *)&v829) && v81 == 12 )
        v81 = 24;
      goto LABEL_244;
    }
    v867 = 1;
    v852 = (IMsiData *)&MsiString::s_NullString;
    v851 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v852 = (IMsiData *)&MsiString::s_NullString;
    v83 = MsiString::MsiString((MsiString *)&v937, L"TRANSFORMSSECURE");
    LOBYTE(v810) = 0;
    ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, *(_QWORD *)v83, &v852, 1, a1 + 448, 0, v810);
    IMsiData::Release(v937);
    IMsiData::Release(v851);
    v851 = (IMsiData *)&MsiString::s_NullString;
    v84 = MsiString::MsiString((MsiString *)&v938, L"TRANSFORMSATSOURCE");
    LOBYTE(v811) = 0;
    ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, *(_QWORD *)v84, &v851, 1, a1 + 448, 0, v811);
    IMsiData::Release(v938);
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v827) == 64 )
    {
      v867 = 2;
    }
    else if ( *(_WORD *)MsiString::operator unsigned short const *(&v827) == 124 )
    {
      v867 = 3;
    }
    else if ( !v853 )
    {
      v85 = v12 | 4;
      v86 = *(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 192LL);
      v87 = MsiString::MsiString((MsiString *)&v940, L"TRANSFORMSSECURE");
      v90 = 1;
      if ( v86(a1, *(_QWORD *)v87) != 1 )
      {
        v85 |= 8u;
        v88 = *(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 192LL);
        v89 = MsiString::MsiString((MsiString *)&v939, L"TRANSFORMSATSOURCE");
        if ( v88(a1, *(_QWORD *)v89) != 1
          && (unsigned int)MsiString::operator int(&v852) != 1
          && (unsigned int)MsiString::operator int(&v851) != 1
          && (v82 || !(unsigned int)GetIntegerPolicyValue(3) && !(unsigned int)GetIntegerPolicyValue(4)) )
        {
          v90 = 0;
        }
      }
      if ( (v85 & 8) != 0 )
      {
        v85 &= ~8u;
        IMsiData::Release(v939);
      }
      v12 = v85 & 0xFFFFFFFB;
      v859 = v12;
      IMsiData::Release(v940);
      if ( v90 )
        v867 = 0;
    }
    v898 = 0;
    v876 = (IMsiData *)&g_MsiStringNull;
    v875 = (IMsiData *)&g_MsiStringNull;
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v830) )
    {
      if ( g_dmDiagnosticMode )
      {
        v91 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v830);
        DebugString(
          10,
          0,
          0,
          L"Applying multiple instance transform '%s'...",
          v91,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      v92 = 0;
      while ( 1 )
      {
        v93 = MsiString::operator unsigned short const *(&v835);
        v94 = MsiString::operator unsigned short const *(&v823);
        LOBYTE(v800) = 1;
        LOBYTE(v798) = 1;
        v95 = CMsiEngine::InitializeTransforms(
                a1,
                v822,
                0,
                v830,
                1,
                0,
                v798,
                v800,
                &v898,
                v94,
                v93,
                &v876,
                &v867,
                &v875);
        v81 = v95;
        if ( !v95 )
        {
LABEL_193:
          v100 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                               a1,
                               L"ProductCode");
          IMsiData::Release(v831);
          v831 = v100;
          MsiString::UpperCase((MsiString *)&v831);
          v8 = v882;
          v82 = v826;
          goto LABEL_194;
        }
        if ( v95 != -2 )
          break;
        IMsiData::Release(v825);
        v825 = (IMsiData *)&MsiString::s_NullString;
        IMsiData::Release(v823);
        v96 = v849;
        v97 = v848;
        v823 = (IMsiData *)&MsiString::s_NullString;
        v98 = MsiString::operator unsigned short const *(&v819);
        v99 = MsiString::operator unsigned short const *(&v820);
        v922 = CMsiEngine::ResolveSource(a1, v99, v98, v97, v96, &v823, &v825, 0);
        if ( v922 )
        {
          IMsiData::Release(v876);
          IMsiData::Release(v875);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v922);
          IMsiData::Release(v851);
          IMsiData::Release(v852);
          IMsiData::Release(v846);
          IMsiData::Release(v847);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
          IMsiData::Release(v824);
          IMsiData::Release(v825);
          IMsiData::Release(v823);
          IMsiData::Release(v821);
          IMsiData::Release(v819);
          v11 = 8;
          goto LABEL_245;
        }
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v922);
        if ( ++v92 >= 2 )
          goto LABEL_193;
      }
      IMsiData::Release(v876);
      IMsiData::Release(v875);
      goto LABEL_243;
    }
LABEL_194:
    v855 = 0;
    v854 = 0;
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v820) )
    {
      if ( !v82 )
      {
        v101 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v854);
        v102 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v855);
        CMsiEngine::ParsePatchProperties((CMsiEngine *)a1, v832, v837, v102, v101);
        CMsiEngine::SetPatchingRunFromSourceFeatures((CMsiEngine *)a1, 0);
        CMsiEngine::SetActiveMajorUpgradePatch((CMsiEngine *)a1, 0);
        v103 = operator new(0xF8u);
        v104 = 0;
        *(_QWORD *)(a1 + 1256) = v103;
        if ( !v103 )
        {
          v941 = PostError(2346);
          v105 = CMsiEngine::PostInitializeError(a1, v941, v819, 33);
          v106 = (__int64 *)&v941;
LABEL_198:
          v11 = v105;
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v106);
LABEL_199:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
          IMsiData::Release(v851);
          v66 = v852;
LABEL_114:
          IMsiData::Release(v66);
LABEL_115:
          IMsiData::Release(v846);
          IMsiData::Release(v847);
          goto LABEL_63;
        }
        v107 = operator new(0xF8u);
        *(_QWORD *)(a1 + 1264) = v107;
        if ( !v107 )
        {
          v942 = PostError(2346);
          v105 = CMsiEngine::PostInitializeError(a1, v942, v819, 33);
          v106 = (__int64 *)&v942;
          goto LABEL_198;
        }
        memset_0(*(void **)(a1 + 1256), 0, 0xF8u);
        memset_0(*(void **)(a1 + 1264), 0, 0xF8u);
        *(_DWORD *)(a1 + 1272) = 31;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 592LL))(a1, 16) )
        {
          v109 = 4;
        }
        else
        {
          v109 = 1;
          if ( (a6 & 0x80u) != 0 )
          {
            CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>((__int64)&v1063, 20);
            v888 = (IMsiData *)&MsiString::s_NullString;
            if ( !v1063 )
              goto LABEL_210;
            v1064 = 1;
            v110 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
            if ( !(unsigned int)GetProductInfo(v110, L"LocalPackage")
              || (IMsiData::Release(v888),
                  v888 = (IMsiData *)&MsiString::s_NullString,
                  v12 |= 0x30u,
                  v111 = *(const struct IMsiString **)MsiString::MsiString((MsiString *)&v944, L"ProductVersion"),
                  v112 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v943, v1063),
                  PropertyFromDatabase = GetPropertyFromDatabase(
                                           0,
                                           *v112,
                                           (const struct IMsiString *)&MsiString::s_NullString,
                                           v111,
                                           &v888),
                  v114 = 1,
                  *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v856, PropertyFromDatabase)) )
            {
LABEL_210:
              v114 = 0;
            }
            if ( (v12 & 0x20) != 0 )
            {
              v12 &= ~0x20u;
              IMsiData::Release(v943);
            }
            if ( (v12 & 0x10) != 0 )
            {
              v12 &= ~0x10u;
              IMsiData::Release(v944);
            }
            if ( !v114 )
              goto LABEL_925;
            v115 = 0;
            v923 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
                                 a1,
                                 L"ProductVersion");
            v894 = 0;
            v893 = 0;
            v892 = 0;
            v891 = 0;
            v116 = MsiString::operator unsigned short const *(&v888);
            if ( !(unsigned int)ParseVersionString(v116, &v894, &v893) )
              goto LABEL_220;
            v117 = MsiString::operator unsigned short const *(&v923);
            if ( (unsigned int)ParseVersionString(v117, &v892, &v891) )
            {
              if ( (unsigned int)CompareVersions(v894, v893, v892, v891) != 2 )
                v104 = 1;
            }
            else
            {
LABEL_220:
              v115 = 1;
            }
            IMsiData::Release(v923);
            if ( v115 || v104 )
            {
LABEL_925:
              if ( v854 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v854 + 24LL))(v854) )
              {
                if ( g_dmDiagnosticMode )
                  DebugString(
                    9,
                    0,
                    0,
                    L"Removal of individual patches cannot occur in the same transaction with a re-cache of an .MSI packag"
                     "e that takes the product to a different version than the one registered.",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
                IMsiData::Release(v888);
                IMsiData::Release((IMsiData *)&MsiString::s_NullString);
                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&v1063);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                IMsiData::Release(v851);
                IMsiData::Release(v852);
                IMsiData::Release(v846);
                IMsiData::Release(v847);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
                CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
                IMsiData::Release(v824);
                IMsiData::Release(v825);
                IMsiData::Release(v823);
                IMsiData::Release(v821);
                IMsiData::Release(v819);
                v11 = 36;
                goto LABEL_245;
              }
              v109 = 2;
            }
            IMsiData::Release(v888);
            IMsiData::Release((IMsiData *)&MsiString::s_NullString);
            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&v1063);
          }
        }
        LOBYTE(v108) = v853 != 0;
        LOBYTE(lpString2) = (a6 & 0x40000) != 0;
        v81 = CMsiEngine::InitializePatches(a1, v822, v820, v108, lpString2, v109, v855, v854, v8);
        if ( !v81 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 272LL))(a1, v8);
          v857 = 0;
          v81 = CMsiEngine::CheckPatchSecurity(a1, v820, &v857);
          if ( v81 == 38 )
          {
            if ( !*(_BYTE *)(a1 + 601) )
            {
              if ( qword_180309730 )
                CMsiSQMSession::RecordElevationCause(qword_180309730, 2, v118);
              v119 = CMsiEngine::EnginePromptForElevatedCredentials(a1, v822, 4);
              if ( v119 )
              {
                v11 = v119;
                if ( v857 )
                  v11 = 35;
                goto LABEL_199;
              }
              *(_BYTE *)(a1 + 601) = 1;
            }
LABEL_241:
            v81 = CMsiEngine::VerifyAccessAndOpenPatchFiles(a1, v820);
            if ( v81 )
              goto LABEL_242;
            if ( (unsigned int)GetIntegerPolicyValue(22)
              || !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 664LL))(a1, 4)
              || (v120 = 1, !v849) )
            {
              v120 = 0;
            }
            *(_BYTE *)(a1 + 944) = v120;
            *(_BYTE *)(a1 + 953) = 0;
            CMsiEngine::SetForceRepair((CMsiEngine *)a1, 0);
            CMsiEngine::SetPatchingDownRevFiles((CMsiEngine *)a1, 0);
            *(_BYTE *)(a1 + 952) = 1;
            v868 = &MsiString::s_NullString;
            IMsiData::Release((IMsiData *)&MsiString::s_NullString);
            v868 = &MsiString::s_NullString;
            v121 = MsiString::MsiString((MsiString *)&v945, L"REINSTALL");
            v122 = v877;
            LOBYTE(v812) = 0;
            v123 = 0;
            if ( (unsigned int)ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, *(_QWORD *)v121, &v868, 1, a1 + 448, 0, v812) )
              v123 = (unsigned int)MsiString::TextSize((MsiString *)&v868) != 0;
            IMsiData::Release(v945);
            if ( v123 )
            {
              *(_BYTE *)(a1 + 952) = 0;
              if ( *(_BYTE *)(a1 + 98) )
              {
                v62 = g_dmDiagnosticMode == 0;
                *(_BYTE *)(a1 + 99) = 1;
                if ( !v62 )
                  DebugString(
                    9,
                    0,
                    0,
                    L"Both REINSTALL and REMOVE=ALL specified. Actual operation is repair.",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    L"(NULL)",
                    0,
                    0);
              }
            }
            if ( *(_QWORD *)(a1 + 928) )
            {
              PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiBaselineManager::SetBaselineCacheActivityForThisTransaction();
              if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
              {
                (*(void (__fastcall **)(void *))(*(_QWORD *)v868 + 16LL))(v868);
                if ( v854 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v854 + 16LL))(v854);
                if ( v855 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v855 + 16LL))(v855);
                (*(void (__fastcall **)(IMsiData *))(*(_QWORD *)v851 + 16LL))(v851);
                (*(void (__fastcall **)(IMsiData *))(*(_QWORD *)v852 + 16LL))(v852);
                goto LABEL_263;
              }
            }
            v125 = CComPointer<IMsiStorage>::operator->(&v822);
            PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ProcessSingleFeaturePackage(a1, v125);
            if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
              goto LABEL_266;
            MsiString::MsiString((MsiString *)v871);
            v127 = MsiString::operator&(v871);
            v128 = MsiString::MsiString((MsiString *)v946, L"MSIUNINSTALLSUPERSEDEDCOMPONENTS");
            v129 = CComPointer<IMsiStorage>::operator->(v128);
            LOBYTE(v813) = 0;
            if ( !(unsigned int)ProcessCommandLine(v122, 0, 0, 0, 0, 0, 0, v129, v127, 1, a1 + 448, 0, v813)
              || (v130 = 1, !(unsigned int)MsiString::TextSize((MsiString *)v871)) )
            {
              v130 = 0;
            }
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v946);
            v131 = CComPointer<IMsiStorage>::operator->(&v822);
            LOBYTE(v132) = v130;
            PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ProcessSupersededPatches(a1, v131, 1, v132);
            if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
            {
              v133 = CComPointer<IMsiStorage>::operator->(&v822);
              PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ApplyPatchTransforms(a1, v133);
              if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
              {
                PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::OptimizeCustomActions(a1);
                if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
                {
                  PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::QueryPatchMetaDataForNewObsoletedAndSupercededMSPs(a1);
                  if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
                  {
                    if ( g_scServerContext == 2 && v849 || (v134 = 0, (a6 & 0x80000) != 0) )
                      v134 = 1;
                    v135 = CComPointer<IMsiStorage>::operator->(&v822);
                    LOBYTE(v136) = v134;
                    v137 = CMsiEngine::ProcessPatchesMarkedForUninstall(a1, v135, v136);
                    if ( v137
                      || (v138 = CComPointer<IMsiStorage>::operator->(&v822),
                          LOBYTE(v139) = v130,
                          (v137 = CMsiEngine::ProcessSupersededPatches(a1, v138, 0, v139)) != 0) )
                    {
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v871);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v868);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
                      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                      v11 = v137;
                      goto LABEL_691;
                    }
                    if ( !v134 )
                      goto LABEL_290;
                    v140 = a6;
                    v141 = CComPointer<IMsiStorage>::operator->(&v822);
                    PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::GeneratePatchFileList(a1, v141, v140);
                    if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
                    {
                      MsiString::MsiString((MsiString *)v916);
                      v142 = MsiString::operator&(v916);
                      v143 = MsiString::MsiString((MsiString *)v947, L"REINSTALLMODE");
                      v144 = CComPointer<IMsiStorage>::operator->(v143);
                      LOBYTE(v814) = 0;
                      LODWORD(v142) = ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, v144, v142, 1, a1 + 448, 0, v814);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v947);
                      if ( (_DWORD)v142 )
                      {
                        v895 = 0;
                        v145 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v916);
                        StringToModeBits(v145, L"rpoedcamusv", &v895);
                        if ( (v895 & 0x40) != 0 )
                        {
                          CMsiEngine::SetPatchingDownRevFiles((CMsiEngine *)a1, 1);
                          *(_BYTE *)(a1 + 944) = 0;
                        }
                      }
                      CMsiEngine::CheckForActiveMajorUpgradePatches((CMsiEngine *)a1);
                      CMsiEngine::DumpPatchFileListTable((CMsiEngine *)a1);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v916);
LABEL_290:
                      if ( g_scServerContext == 2 )
                      {
                        v146 = (CMsiPatchManager *)operator new(0x188u);
                        if ( v146 )
                        {
                          v147 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v822);
                          v148 = CMsiPatchManager::CMsiPatchManager(v146, (struct IMsiEngine *)a1, v147);
                        }
                        else
                        {
                          v148 = 0;
                        }
                        *(_QWORD *)(a1 + 936) = v148;
                        if ( !v148 )
                        {
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v871);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v868);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
LABEL_690:
                          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                          v11 = 33;
                          goto LABEL_691;
                        }
                      }
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v871);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v868);
                      v859 = v12 & 0xFFFFFF3F;
LABEL_299:
                      if ( (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1) )
                      {
                        v149 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
                        if ( v870 != v149 )
                        {
                          v150 = CComPointer<IMsiStorage>::operator->(&v822);
                          v151 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
                          PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ApplyLanguageTransform(
                                                                            a1,
                                                                            v151,
                                                                            v150);
                          if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
                            goto LABEL_268;
                        }
                      }
                      if ( !*(_QWORD *)(a1 + 176) )
                      {
                        Record = CreateRecord(3u);
                        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v902, (__int64)Record);
                        v153 = CComPointer<IMsiStorage>::operator->(&v902);
                        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v153 + 104LL))(v153, 1, 0);
                        v154 = CComPointer<IMsiStorage>::operator->(&v902);
                        v155 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v154 + 104LL);
                        v156 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
                        v155(v154, 2, v156);
                        v157 = CComPointer<IMsiStorage>::operator->(&v902);
                        v158 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v157 + 104LL);
                        v159 = CComPointer<IMsiStorage>::operator->(&v822);
                        v160 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v159 + 216LL))(v159);
                        v158(v157, 3, v160);
                        v161 = CComPointer<IMsiStorage>::operator->(&v902);
                        MsiUIMessageContext::Invoke(&g_MessageContext, 2332033024LL, v161);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v902);
                      }
                      LODWORD(v882) = 0;
                      do
                      {
                        v162 = MsiString::operator unsigned short const *(&v835);
                        v163 = MsiString::operator unsigned short const *(&v823);
                        v164 = v849 != 0;
                        v165 = CComPointer<IMsiStorage>::operator->(&v827);
                        v166 = CComPointer<IMsiStorage>::operator->(&v822);
                        LOBYTE(v800) = v164;
                        LOBYTE(v798) = 0;
                        v167 = CMsiEngine::InitializeTransforms(
                                 a1,
                                 v166,
                                 0,
                                 v165,
                                 1,
                                 0,
                                 v798,
                                 v800,
                                 &v898,
                                 v163,
                                 v162,
                                 &v876,
                                 &v867,
                                 &v875);
                        PatchMetaDataForNewObsoletedAndSupercededMSPs = v167;
                        if ( !v167 )
                          break;
                        if ( v167 != -2 )
                        {
                          IMsiData::Release(v876);
                          IMsiData::Release(v875);
                          goto LABEL_268;
                        }
                        v168 = MsiString::operator&(&v825);
                        v169 = MsiString::operator&(&v823);
                        v170 = v849;
                        v171 = v848;
                        v172 = v169;
                        v173 = MsiString::operator unsigned short const *(&v819);
                        v174 = MsiString::operator unsigned short const *(&v820);
                        v175 = CMsiEngine::ResolveSource(a1, v174, v173, v171, v170, v172, v168, 0);
                        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v917, v175);
                        if ( CComPointer<IMsiStorage>::operator->(&v917) )
                        {
                          IMsiData::Release(v876);
                          IMsiData::Release(v875);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v917);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
                          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                          v11 = 8;
                          goto LABEL_691;
                        }
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v917);
                        LODWORD(v882) = v882 + 1;
                      }
                      while ( (int)v882 < 2 );
                      v176 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                               a1,
                               L"ProductCode");
                      CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v883, v176);
                      v177 = MsiString::operator unsigned short const *(&v883);
                      v178 = MsiString::Compare(&v820, 1, v177);
                      v897 = 0;
                      v179 = v178 == 0;
                      v180 = CComPointer<IMsiStorage>::operator->(&v833);
                      v181 = CComPointer<IMsiStorage>::operator->(&v883);
                      v182 = CComPointer<IMsiStorage>::operator->(&v822);
                      LOBYTE(v805) = v179;
                      LOBYTE(v803) = v842;
                      *(_QWORD *)cchCount2b = v180;
                      v9 = v877;
                      CMsiEngine::ApplyAppCompatTransforms(
                        a1,
                        v887,
                        v877,
                        v182,
                        v181,
                        *(_QWORD *)cchCount2b,
                        2,
                        &v897,
                        v803,
                        v805,
                        &v844);
                      *(_DWORD *)(a1 + 608) |= v897;
                      if ( g_dmDiagnosticMode )
                      {
                        if ( v867 == 1 )
                        {
                          v183 = L"not";
                        }
                        else if ( v867 == 3 )
                        {
                          v183 = L"absolute";
                        }
                        else
                        {
                          v183 = L"relative";
                          if ( v867 != 2 )
                            v183 = L"??";
                        }
                        DebugString(
                          9,
                          0,
                          0,
                          L"Transforms are %s secure.",
                          v183,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                      }
                      v184 = CComPointer<IMsiStorage>::operator->(&v822);
                      if ( !(unsigned int)CMsiEngine::CreatePropertyTable(a1, v184, L"Property", 0) )
                      {
LABEL_320:
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v883);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
LABEL_321:
                        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                        goto LABEL_691;
                      }
                      if ( !*(_QWORD *)(a1 + 176) )
                      {
                        v185 = (_WORD *)CAPITempBuffer<unsigned short,261>::operator[](&g_rgchLogFile, 0);
                        v186 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                        if ( *v185 )
                        {
                          v187 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(&g_rgchLogFile);
                          v188 = MsiString::MsiString((MsiString *)v949, v187);
                          v189 = CComPointer<IMsiStorage>::operator->(v188);
                          v190 = MsiString::MsiString((MsiString *)v948, L"MsiLogFileLocation");
                          v191 = CComPointer<IMsiStorage>::operator->(v190);
                          v186(a1, v191, v189);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v948);
                          v192 = (GUIDAndSequence *)v949;
                        }
                        else
                        {
                          v193 = MsiString::MsiString((MsiString *)v951, &Default);
                          v194 = CComPointer<IMsiStorage>::operator->(v193);
                          v195 = MsiString::MsiString((MsiString *)v950, L"MsiLogFileLocation");
                          v196 = CComPointer<IMsiStorage>::operator->(v195);
                          v186(a1, v196, v194);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v950);
                          v192 = (GUIDAndSequence *)v951;
                        }
                        GUIDAndSequence::~GUIDAndSequence(v192);
                      }
                      v197 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v822);
                      CMsiEngine::LogCommandLine((CMsiEngine *)a1, v9, v197);
                      v198 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                      v199 = CComPointer<IMsiStorage>::operator->(&v833);
                      v200 = MsiString::MsiString((MsiString *)v952, L"PackageCode");
                      v201 = CComPointer<IMsiStorage>::operator->(v200);
                      v198(a1, v201, v199);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v952);
                      v202 = v876;
                      v203 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
                      v204 = MsiString::MsiString((MsiString *)v953, L"RecacheTransforms");
                      v205 = CComPointer<IMsiStorage>::operator->(v204);
                      v203(a1, v205, v202);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v953);
                      v206 = v875;
                      v207 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
                      v208 = MsiString::MsiString((MsiString *)v954, L"TRANSFORMS");
                      v209 = CComPointer<IMsiStorage>::operator->(v208);
                      v207(a1, v209, v206);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v954);
                      PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::PopulatePatchRemovalListProperty(a1);
                      if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
                      {
                        v126 = (GUIDAndSequence *)&v883;
                        goto LABEL_267;
                      }
                      MsiString::operator=(&v827, v875);
                      IMsiData::Release(v876);
                      v210.lpVtbl = *(struct IUnknownVtbl **)a1;
                      if ( (unsigned int)(v867 - 2) <= 1 )
                      {
                        QueryInterface = v210.lpVtbl[7].QueryInterface;
                        v219 = MsiString::MsiString((MsiString *)v957, L"TRANSFORMSSECURE");
                        v220 = CComPointer<IMsiStorage>::operator->(v219);
                        ((void (__fastcall *)(__int64, __int64, __int64))QueryInterface)(a1, v220, 1);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v957);
                        v221 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
                        v222 = MsiString::MsiString((MsiString *)v958, L"TRANSFORMSATSOURCE");
                        v223 = CComPointer<IMsiStorage>::operator->(v222);
                        v221(a1, v223, 1);
                        v217 = (GUIDAndSequence *)v958;
                      }
                      else
                      {
                        Release = v210.lpVtbl[6].Release;
                        v212 = MsiString::MsiString((MsiString *)v955, L"TRANSFORMSSECURE");
                        v213 = CComPointer<IMsiStorage>::operator->(v212);
                        ((void (__fastcall *)(__int64, __int64, void ***))Release)(a1, v213, &g_MsiStringNull);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v955);
                        v214 = *(void (__fastcall **)(__int64, __int64, void ***))(*(_QWORD *)a1 + 160LL);
                        v215 = MsiString::MsiString((MsiString *)v956, L"TRANSFORMSATSOURCE");
                        v216 = CComPointer<IMsiStorage>::operator->(v215);
                        v214(a1, v216, &g_MsiStringNull);
                        v217 = (GUIDAndSequence *)v956;
                      }
                      GUIDAndSequence::~GUIDAndSequence(v217);
                      v224 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                               a1,
                               L"ProductCode");
                      CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v881, v224);
                      if ( g_dmDiagnosticMode )
                      {
                        v225 = v924;
                        if ( !v924 )
                          v225 = L"(none)";
                        DebugString(
                          9,
                          0,
                          0,
                          L"Product Code passed to Engine.Initialize:           '%s'",
                          v225,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                        if ( g_dmDiagnosticMode )
                        {
                          v226 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
                          DebugString(
                            9,
                            0,
                            0,
                            L"Product Code from property table before transforms: '%s'",
                            v226,
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
                        }
                      }
                      if ( (unsigned int)MsiString::TextSize((MsiString *)&v831) )
                      {
                        if ( !g_dmDiagnosticMode )
                          goto LABEL_343;
                        v227 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v831);
                        DebugString(
                          9,
                          0,
                          0,
                          L"Product Code from property table after multiple instance transforms: '%s'",
                          v227,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                      }
                      else
                      {
                        MsiString::operator=(&v831, &v820);
                      }
                      if ( g_dmDiagnosticMode )
                      {
                        v228 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v881);
                        DebugString(
                          9,
                          0,
                          0,
                          L"Product Code from property table after transforms:  '%s'",
                          v228,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                      }
LABEL_343:
                      v229 = MsiString::operator unsigned short const *(&v881);
                      if ( !(unsigned int)MsiString::Compare(&v820, 1, v229) )
                      {
                        if ( (unsigned int)MsiString::TextSize((MsiString *)&v832) )
                        {
                          v230 = MsiString::operator unsigned short const *(&v881);
                          if ( !(unsigned int)MsiString::Compare(&v831, 1, v230) )
                          {
                            MsiString::operator=(&v824, &v820);
                            v231 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                            v232 = CComPointer<IMsiStorage>::operator->(&v820);
                            v233 = MsiString::MsiString((MsiString *)v959, L"MIGRATE");
                            v234 = CComPointer<IMsiStorage>::operator->(v233);
                            v231(a1, v234, v232);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v959);
                            v235 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                            v236 = CComPointer<IMsiStorage>::operator->(&v820);
                            v237 = MsiString::MsiString((MsiString *)v960, L"PatchedProductCode");
                            v238 = CComPointer<IMsiStorage>::operator->(v237);
                            v235(a1, v238, v236);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v960);
                          }
                        }
                        MsiString::operator=(&v820, &v881);
                        v239 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
                        ProductState = CMsiEngine::GetProductState(
                                         (CMsiEngine *)a1,
                                         v239,
                                         (enum Bool *)&v849,
                                         (enum Bool *)&v853);
                      }
                      if ( *(_BYTE *)(a1 + 98) && !v853 )
                        goto LABEL_354;
                      if ( (*(_DWORD *)(a1 + 584) & 0x4000) == 0
                        && !(unsigned int)MsiString::TextSize((MsiString *)&v820) )
                      {
                        if ( g_dmDiagnosticMode )
                          DebugString(
                            5,
                            0,
                            0,
                            L"Failing install, missing product code",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
LABEL_354:
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v881);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v883);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
                        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                        v11 = 22;
                        goto LABEL_691;
                      }
                      if ( v844 )
                      {
                        if ( !v849 )
                        {
                          v240 = (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a1 + 184LL))(
                                   a1,
                                   L"ProductName");
                          CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v907, v240);
                          if ( !(unsigned int)MsiString::TextSize((MsiString *)&v907) )
                            MsiString::operator=(&v907, &v819);
                          v241 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v907);
                          DebugString(
                            21,
                            1u,
                            1018,
                            v241,
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
                          v242 = CComPointer<IMsiStorage>::operator->(&v819);
                          v11 = CMsiEngine::PostInitializeError(a1, 0, v242, 30);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v907);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v881);
                          goto LABEL_320;
                        }
                      }
                      else if ( !v849 )
                      {
                        if ( g_dmDiagnosticMode )
                        {
                          v243 = L"Product not registered: beginning first-time install";
                          goto LABEL_365;
                        }
LABEL_366:
                        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 104LL))(a1, 4, v849);
                        *(_DWORD *)(a1 + 68) = v849;
                        *(_DWORD *)(a1 + 72) = v853;
                        if ( !*(_QWORD *)(a1 + 176)
                          && g_scServerContext == 2
                          && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
                        {
                          v244 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
                          v245 = MsiString::MsiString((MsiString *)v961, L"MSIINSTALLPERUSER");
                          v246 = CComPointer<IMsiStorage>::operator->(v245);
                          v247 = v244(a1, v246);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v961);
                          if ( v247 == 0x80000000 )
                            v248 = 99;
                          else
                            v248 = v247 == 1;
                          SQMSession = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          CMsiSQMSession::RecordDWORD(SQMSession, 0x1053u, v248);
                          v250 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          IntegerPolicyValue = GetIntegerPolicyValue(0);
                          CMsiSQMSession::RecordDWORD(v250, 0x1056u, IntegerPolicyValue);
                          v252 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          v253 = GetIntegerPolicyValue(6);
                          CMsiSQMSession::RecordDWORD(v252, 0x1057u, v253);
                          iid = 0;
                          v254 = (const OLECHAR *)MsiString::operator unsigned short const *(&v820);
                          if ( IIDFromString(v254, &iid) )
                          {
                            v255 = 0;
                            if ( g_dmDiagnosticMode )
                            {
                              v256 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
                              DebugString(
                                10,
                                0,
                                0,
                                L"Failed to convert Product Code %s to GUID",
                                v256,
                                L"(NULL)",
                                L"(NULL)",
                                L"(NULL)",
                                L"(NULL)",
                                L"(NULL)",
                                0,
                                0);
                            }
                          }
                          else
                          {
                            v255 = *(_DWORD *)&iid.Data4[4] ^ *(_DWORD *)iid.Data4 ^ *(_DWORD *)&iid.Data2 ^ iid.Data1;
                          }
                          v257 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          CMsiSQMSession::RecordDWORD(v257, 0x1055u, v255);
                        }
                        CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                        v258 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
                        if ( !(unsigned int)GetProductInfo(v258, L"AssignmentType") )
                        {
                          if ( !(unsigned int)MsiString::TextSize((MsiString *)&v824) )
                            goto LABEL_392;
                          CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                          v259 = (const WCHAR *)MsiString::operator unsigned short const *(&v824);
                          if ( !(unsigned int)GetProductInfo(v259, L"AssignmentType") )
                            goto LABEL_392;
                        }
                        v260 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(&String);
                        v261 = MsiString::MsiString((MsiString *)v962, v260);
                        v262 = MsiString::operator int(v261);
                        v263 = v262 == 1;
                        v850 = v263;
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v962);
                        if ( g_dmDiagnosticMode )
                        {
                          v264 = L"machine";
                          if ( v262 != 1 )
                            v264 = L"user";
                          DebugString(
                            9,
                            0,
                            0,
                            L"Determined that existing product (either this product or the product being upgraded with a p"
                             "atch) is installed per-%s.",
                            v264,
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
                        }
                        if ( v262 == 1 )
                          goto LABEL_391;
                        CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                        v265 = (const WCHAR *)MsiString::operator unsigned short const *(&v820);
                        if ( !(unsigned int)GetProductInfo(v265, L"DeploymentFlags") )
                        {
                          if ( !(unsigned int)MsiString::TextSize((MsiString *)&v824) )
                          {
LABEL_391:
                            v850 = v263;
                            goto LABEL_392;
                          }
                          CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                          v266 = (const WCHAR *)MsiString::operator unsigned short const *(&v824);
                          if ( !(unsigned int)GetProductInfo(v266, L"DeploymentFlags") )
                          {
LABEL_392:
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v881);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v883);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
                            v12 = v859;
                            goto LABEL_393;
                          }
                        }
                        v267 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(&String);
                        v268 = strtol(v267);
                        if ( IsInstalledPerUser(v268) )
                        {
                          v269.lpVtbl = *(struct IUnknownVtbl **)a1;
                          v845 = 1;
                          v270 = v269.lpVtbl[7].QueryInterface;
                          v271 = MsiString::MsiString((MsiString *)v963, L"MSIINSTALLPERUSER");
                          v272 = CComPointer<IMsiStorage>::operator->(v271);
                          ((void (__fastcall *)(__int64, __int64, __int64))v270)(a1, v272, 1);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v963);
                          v273 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
                          v274 = MsiString::MsiString((MsiString *)v964, L"MSIINTERNALINSTALLEDPERUSER");
                          v275 = CComPointer<IMsiStorage>::operator->(v274);
                          v273(a1, v275, 1);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v964);
                          if ( g_dmDiagnosticMode )
                            DebugString(
                              9,
                              0,
                              0,
                              L"Determined that existing product (either this product or the product being upgraded with a"
                               " patch) is a dual mode package installed in per-user mode.",
                              L"(NULL)",
                              L"(NULL)",
                              L"(NULL)",
                              L"(NULL)",
                              L"(NULL)",
                              L"(NULL)",
                              0,
                              0);
                        }
                        goto LABEL_391;
                      }
                      if ( g_dmDiagnosticMode )
                      {
                        v243 = L"Product registered: entering maintenance mode";
LABEL_365:
                        DebugString(
                          9,
                          0,
                          0,
                          v243,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                        goto LABEL_366;
                      }
                      goto LABEL_366;
                    }
                  }
                }
              }
            }
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v871);
LABEL_266:
            v126 = (GUIDAndSequence *)&v868;
LABEL_267:
            GUIDAndSequence::~GUIDAndSequence(v126);
LABEL_268:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v851);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v852);
LABEL_263:
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v846);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v847);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v843);
LABEL_264:
            CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
            v11 = PatchMetaDataForNewObsoletedAndSupercededMSPs;
            goto LABEL_691;
          }
          if ( !v81 )
            goto LABEL_241;
        }
LABEL_242:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v854);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v855);
LABEL_243:
        IMsiData::Release(v851);
        IMsiData::Release(v852);
        goto LABEL_244;
      }
    }
    else
    {
      v859 = v12;
      if ( !v82 )
        goto LABEL_299;
    }
    *(_BYTE *)(a1 + 944) = 0;
    goto LABEL_299;
  }
  if ( !(unsigned int)CMsiEngine::CreatePropertyTable(a1, v822, L"Property", 0) )
  {
LABEL_46:
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
    IMsiData::Release(v824);
    IMsiData::Release(v825);
    IMsiData::Release(v823);
    IMsiData::Release(v821);
    IMsiData::Release(v819);
    goto LABEL_245;
  }
LABEL_393:
  v903 = 0;
  v276 = a1 + 448;
  v277 = MsiString::MsiString((MsiString *)v965, L"ALLUSERS");
  v278 = CComPointer<IMsiStorage>::operator->(v277);
  LOBYTE(v807) = 0;
  ProcessCommandLine(v9, 0, 0, 0, 0, 0, 0, v278, &v903, 1, a1 + 448, 0, v807);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v965);
  if ( !*(_QWORD *)(a1 + 176)
    && (!g_scServerContext || g_scServerContext == 2 && (unsigned int)(dword_180309774 - 2) <= 1)
    && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
  {
    v279 = 3;
    if ( v903 )
    {
      if ( (*(unsigned int (__fastcall **)(IMsiData *))(*(_QWORD *)v903 + 32LL))(v903) == 2 )
        v279 = 2;
      else
        v279 = (*(__int64 (__fastcall **)(IMsiData *))(*(_QWORD *)v903 + 56LL))(v903) != 0;
    }
    v280 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
    CMsiSQMSession::RecordDWORD(v280, 0xE1Fu, v279);
  }
  v281 = v903;
  if ( v903 )
  {
    v282 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
    v283 = MsiString::MsiString((MsiString *)v966, L"ALLUSERS");
    v284 = CComPointer<IMsiStorage>::operator->(v283);
    v282(a1, v284, v281);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v966);
    IMsiData::Release(v903);
  }
  v918 = 0;
  v285 = MsiString::MsiString((MsiString *)v967, L"MSIINSTALLPERUSER");
  v286 = CComPointer<IMsiStorage>::operator->(v285);
  LOBYTE(v815) = 0;
  ProcessCommandLine(v9, 0, 0, 0, 0, 0, 0, v286, &v918, 1, a1 + 448, 0, v815);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v967);
  v287 = v918;
  if ( v918 )
  {
    v288 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
    v289 = MsiString::MsiString((MsiString *)v968, L"MSIINSTALLPERUSER");
    v290 = CComPointer<IMsiStorage>::operator->(v289);
    v288(a1, v290, v287);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v968);
    IMsiData::Release(v918);
  }
  v291 = *(_QWORD **)a1;
  if ( v850 == -1 )
  {
    v292 = (__int64 (__fastcall *)(__int64, __int64))v291[24];
    v293 = MsiString::MsiString((MsiString *)v969, L"ALLUSERS");
    v294 = CComPointer<IMsiStorage>::operator->(v293);
    LODWORD(v292) = v292(a1, v294);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v969);
    v295.lpVtbl = *(struct IUnknownVtbl **)a1;
    if ( (_DWORD)v292 == 2 )
    {
      v296 = v295.lpVtbl[8].QueryInterface;
      v297 = MsiString::MsiString((MsiString *)v970, L"MSIINSTALLPERUSER");
      v298 = CComPointer<IMsiStorage>::operator->(v297);
      LODWORD(v296) = ((__int64 (__fastcall *)(__int64, __int64))v296)(a1, v298);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v970);
      v299.lpVtbl = *(struct IUnknownVtbl **)a1;
      if ( (_DWORD)v296 == 1 )
      {
        v300 = v299.lpVtbl[6].Release;
        v850 = 0;
        v301 = MsiString::MsiString((MsiString *)v972, &Default);
        v302 = CComPointer<IMsiStorage>::operator->(v301);
        v303 = MsiString::MsiString((MsiString *)v971, L"ALLUSERS");
        v304 = CComPointer<IMsiStorage>::operator->(v303);
        ((void (__fastcall *)(__int64, __int64, __int64))v300)(a1, v304, v302);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v971);
        v845 = 1;
        v305 = (GUIDAndSequence *)v972;
      }
      else
      {
        v306 = ((__int64 (__fastcall *)(__int64, __int64))v299.lpVtbl[24].Release)(a1, 64);
        v307.lpVtbl = *(struct IUnknownVtbl **)a1;
        if ( v306 )
        {
          v308 = v307.lpVtbl[6].Release;
          v850 = 0;
          v309 = MsiString::MsiString((MsiString *)v974, &Default);
          v310 = CComPointer<IMsiStorage>::operator->(v309);
          v311 = MsiString::MsiString((MsiString *)v973, L"ALLUSERS");
          v312 = CComPointer<IMsiStorage>::operator->(v311);
          ((void (__fastcall *)(__int64, __int64, __int64))v308)(a1, v312, v310);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v973);
          v305 = (GUIDAndSequence *)v974;
        }
        else
        {
          v313 = v307.lpVtbl[7].QueryInterface;
          v850 = 1;
          v314 = MsiString::MsiString((MsiString *)v975, L"ALLUSERS");
          v315 = CComPointer<IMsiStorage>::operator->(v314);
          ((void (__fastcall *)(__int64, __int64, __int64))v313)(a1, v315, 1);
          v305 = (GUIDAndSequence *)v975;
        }
      }
    }
    else
    {
      v305 = (GUIDAndSequence *)&v976;
      v316 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *))v295.lpVtbl[7].Release)(a1, L"ALLUSERS");
      v317 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v976, v316);
      v850 = MsiString::TextSize(v317) != 0;
    }
  }
  else if ( v850 == 1 )
  {
    v318 = (void (__fastcall *)(__int64, __int64, __int64))v291[21];
    v319 = MsiString::MsiString((MsiString *)v977, L"ALLUSERS");
    v320 = CComPointer<IMsiStorage>::operator->(v319);
    v318(a1, v320, 1);
    v305 = (GUIDAndSequence *)v977;
  }
  else
  {
    v321 = (void (__fastcall *)(__int64, __int64, __int64))v291[20];
    v322 = MsiString::MsiString((MsiString *)v979, &Default);
    v323 = CComPointer<IMsiStorage>::operator->(v322);
    v324 = MsiString::MsiString((MsiString *)v978, L"ALLUSERS");
    v325 = CComPointer<IMsiStorage>::operator->(v324);
    v321(a1, v325, v323);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v978);
    v305 = (GUIDAndSequence *)v979;
  }
  GUIDAndSequence::~GUIDAndSequence(v305);
  v326 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v327 = MsiString::MsiString((MsiString *)v980, L"MSIINSTALLPERUSER");
  v328 = CComPointer<IMsiStorage>::operator->(v327);
  LODWORD(v326) = v326(a1, v328);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v980);
  if ( (_DWORD)v326 != 1 )
  {
    v329 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
    v330 = MsiString::MsiString((MsiString *)v982, &Default);
    v331 = CComPointer<IMsiStorage>::operator->(v330);
    v332 = MsiString::MsiString((MsiString *)v981, L"MSIINSTALLPERUSER");
    v333 = CComPointer<IMsiStorage>::operator->(v332);
    v329(a1, v333, v331);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v981);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v982);
  }
  v334 = 0;
  if ( !v862 && (v887 && *v887 || *(_QWORD *)(a1 + 168)) )
  {
    if ( !v826 && g_scServerContext == 2 )
    {
      v335 = *(_QWORD *)(a1 + 176);
      if ( v335 )
      {
        v336 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v335 + 576LL))(v335);
        v62 = g_dmDiagnosticMode == 0;
        *(_BYTE *)(a1 + 601) = v336;
        if ( !v62 )
        {
          v337 = L"is";
          if ( !v336 )
            v337 = L"is not";
          DebugString(
            10,
            0,
            0,
            L"MSI_LUA: Nested installation UAC elevation tracks that of parent (%s elevated)",
            v337,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      v338 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
      v866 = IsProductManaged(v338);
      v878 = 3;
      v339 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
      PackedGUID = GetPackedGUID(v339);
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v908, (__int64)PackedGUID);
      v341 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v908);
      if ( GetProductAssignmentType(v341, (enum iaaAppAssignment *)&v878) )
      {
        v342 = 3;
        v878 = 3;
      }
      else
      {
        v342 = v878;
      }
      v858[0] = 0;
      v865 = v342 == 0;
      LODWORD(v882) = a6;
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 504LL))(a1) == 4
        && (!*(_BYTE *)(a1 + 98) || *(_BYTE *)(a1 + 99)) )
      {
        LODWORD(v882) = a6 & 0xFFEFFFFF;
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            "MSI_LUA: Unsetting the  uninstall flag for repair operations",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            "(NULL)",
            0,
            0);
      }
      v859 = *(_DWORD *)(a1 + 608);
      if ( !*(_BYTE *)(a1 + 98) || (v842 = 1, *(_BYTE *)(a1 + 99)) )
        v842 = 0;
      v343 = v853 != 0;
      v344 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
      v345 = *(_DWORD *)(a1 + 596);
      v346 = v344;
      v347 = CComPointer<IMsiStorage>::operator->(&v822);
      v348 = CComPointer<IMsiStorage>::operator->(&v821);
      LOBYTE(v816) = v845;
      LOBYTE(v806) = v842;
      LOBYTE(v801) = v865;
      LOBYTE(v799) = v866;
      LOBYTE(cchCount2a) = v343;
      LOBYTE(lpString2a) = v346 & 1;
      v349 = ElevatedCredentialsPromptRequired(
               v348,
               v347,
               v345,
               v864,
               lpString2a,
               cchCount2a,
               v799,
               v801,
               v882,
               v872,
               v806,
               v859,
               v816,
               v858);
      switch ( v349 )
      {
        case -1:
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v908);
          goto LABEL_690;
        case 2:
          if ( !*(_BYTE *)(a1 + 601) )
            CMsiEngine::FSetPendingElevatedCredentialsPrompt((CMsiEngine *)a1);
          break;
        case 1:
          if ( !*(_BYTE *)(a1 + 601) )
          {
            v350 = 1;
            if ( v849 )
              v350 = 4;
            if ( MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
            {
              v351 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
              CMsiSQMSession::RecordElevationCause(v351, 5, v352);
            }
            v353 = CComPointer<IMsiStorage>::operator->(&v822);
            PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::EnginePromptForElevatedCredentials(
                                                              a1,
                                                              v353,
                                                              v350);
            if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
            {
              *(_BYTE *)(a1 + 601) = 0;
              v354 = (GUIDAndSequence *)&v908;
LABEL_456:
              GUIDAndSequence::~GUIDAndSequence(v354);
              goto LABEL_264;
            }
            *(_BYTE *)(a1 + 601) = 1;
          }
          break;
        default:
          if ( v858[0] )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 584LL))(a1);
          break;
      }
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v908);
      v9 = v877;
    }
    v355 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
    v356 = MsiString::MsiString((MsiString *)v983, L"ProductState");
    v357 = CComPointer<IMsiStorage>::operator->(v356);
    v355(a1, v357, (unsigned int)ProductState);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v983);
    if ( v849 )
    {
      v358 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v359 = MsiString::MsiString((MsiString *)v984, L"ProductToBeRegistered");
      v360 = CComPointer<IMsiStorage>::operator->(v359);
      v358(a1, v360, 1);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v984);
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v820) )
    {
      v361 = *(IMsiData **)(a1 + 416);
      if ( v361 )
        IMsiData::Release(v361);
      v362 = (IMsiData *)CComPointer<IMsiStorage>::operator->(&v820);
      *(_QWORD *)(a1 + 416) = v362;
      IMsiData::AddRef(v362);
    }
    v363 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 296LL))(a1);
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v869, v363);
    MsiString::operator=(a1 + 616, &g_MsiStringNull);
    v364 = MsiString::operator&(&v840);
    v365 = MsiString::MsiString((MsiString *)v985, L"MSIPACKAGEDOWNLOADLOCALCOPY");
    v366 = CComPointer<IMsiStorage>::operator->(v365);
    LOBYTE(v816) = 0;
    ProcessCommandLine(v9, 0, 0, 0, 0, 0, 0, v366, v364, 1, 0, 0, v816);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v985);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v840) )
      MsiString::operator=(a1 + 616, &v840);
    if ( !*(_BYTE *)(a1 + 577) )
    {
      if ( !v853 || (v367 = CComPointer<IMsiStorage>::operator->(&v819), !(unsigned int)IsCachedPackage(a1, v367, 0, 0)) )
      {
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v904, 0);
        MsiString::MsiString((MsiString *)v909);
        v368 = *(_QWORD *)(a1 + 128);
        v369 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v368 + 360LL);
        v370 = MsiString::operator&(v909);
        v371 = CComPointer<IEnumMsiRecord>::operator=(&v904);
        v372 = MsiString::operator unsigned short const *(&v819);
        v373 = v369(v368, v372, v371, v370);
        v374 = CComPointer<IMsiDatabase>::operator=(&v856, v373);
        if ( CComPointer<IMsiStorage>::operator->(v374) )
        {
          v375 = CComPointer<IMsiStorage>::operator->(&v819);
          v376 = CComPointer<IMsiStorage>::operator->(&v856);
          v377 = 5;
LABEL_473:
          v11 = CMsiEngine::PostInitializeError(a1, v376, v375, v377);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v909);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v904);
LABEL_474:
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v869);
          goto LABEL_321;
        }
        v378 = CComPointer<IMsiStorage>::operator->(&v904);
        v379 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v378 + 56LL))(v378);
        v380 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v986, v379);
        v381 = MsiString::operator unsigned short const *(v380);
        v382 = MsiString::operator unsigned short const *(&v869);
        LOBYTE(v383) = v853 == 0;
        LOBYTE(v381) = FSourceIsAllowed(*(_QWORD *)(a1 + 128), v383, v382, v381, 0);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v986);
        if ( !(_BYTE)v381 && g_scServerContext && !*(_BYTE *)(a1 + 601) )
        {
          if ( MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
          {
            v384 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
            CMsiSQMSession::RecordElevationCause(v384, 4, v385);
          }
          v386 = CComPointer<IMsiStorage>::operator->(&v822);
          lpString2a = v872;
          if ( (unsigned int)CMsiEngine::EnginePromptForElevatedCredentials(a1, v386, 1) )
          {
            v375 = CComPointer<IMsiStorage>::operator->(&v819);
            v376 = CComPointer<IMsiStorage>::operator->(&v856);
            v377 = 21;
            goto LABEL_473;
          }
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"MSI_LUA: Allowing use of new source since consent was provided",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          *(_BYTE *)(a1 + 601) = 1;
        }
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v909);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v904);
      }
    }
    CTempBuffer<unsigned short,39>::CTempBuffer<unsigned short,39>((__int64)v1067);
    *(_WORD *)CComPointer<IMsiStorage>::operator->(v1067) = 0;
    v387 = (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a1 + 184LL))(a1, L"PackageCode");
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v889, v387);
    CTempBuffer<unsigned short,39>::operator CTempBufferRef<unsigned short> &(v1067);
    v388 = (const WCHAR *)MsiString::operator unsigned short const *(&v869);
    GetProductInfo(v388, L"PackageCode");
    v389 = CComPointer<IMsiStorage>::operator->(v1067);
    if ( !(unsigned int)MsiString::Compare(&v889, 1, v389) )
    {
      v390 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v391 = MsiString::MsiString((MsiString *)v987, L"PackagecodeChanging");
      v392 = CComPointer<IMsiStorage>::operator->(v391);
      v390(a1, v392, 1);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v987);
    }
    if ( (a6 & 0x80u) != 0
      || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 2) != 0
      || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) != 0
      || !*(_DWORD *)(a1 + 68)
      || (v12 |= 0x100u,
          v393 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
                   a1,
                   L"PackagecodeChanging"),
          v394 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v988, v393),
          v395 = 1,
          !(unsigned int)MsiString::TextSize(v394)) )
    {
      v395 = 0;
    }
    if ( (v12 & 0x100) != 0 )
    {
      v12 &= ~0x100u;
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v988);
    }
    if ( v395 )
    {
      v396 = CComPointer<IMsiStorage>::operator->(&v869);
      v11 = CMsiEngine::PostInitializeError(a1, 0, v396, 24);
LABEL_497:
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v889);
      CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>((__int64)v1067);
      goto LABEL_474;
    }
    MsiString::operator=(a1 + 528, &g_MsiStringNull);
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v819) == 58 )
    {
      MsiString::operator=(a1 + 528, &v819);
    }
    else
    {
      if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) == 0
        && !v826
        && (unsigned int)MsiString::TextSize((MsiString *)&v869) )
      {
        MsiString::MsiString((MsiString *)v919);
        v397 = MsiString::TextSize((MsiString *)&v824);
        v398 = (IMsiData **)&v869;
        if ( v397 )
          v398 = &v824;
        MsiString::operator=(v919, v398);
        CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
        v399 = (const WCHAR *)MsiString::operator unsigned short const *(v919);
        if ( (unsigned int)GetProductInfo(v399, L"PackageName") )
        {
          if ( *(_WORD *)CTempBuffer<unsigned short,100>::operator[](&String, 0) )
          {
            v400 = CComPointer<IMsiStorage>::operator->(&String);
            MsiString::operator=(a1 + 528, v400);
            if ( g_dmDiagnosticMode )
            {
              v401 = (const unsigned __int16 *)MsiString::operator unsigned short const *(a1 + 528);
              DebugString(
                9,
                0,
                0,
                L"Package name retrieved from configuration data: '%s'",
                v401,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            }
          }
        }
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v919);
      }
      if ( !(unsigned int)MsiString::TextSize((MsiString *)(a1 + 528)) )
      {
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v910, 0);
        v402 = *(_QWORD *)(a1 + 128);
        v403 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v402 + 360LL);
        v404 = MsiString::operator&(a1 + 528);
        v405 = CComPointer<IEnumMsiRecord>::operator=(&v910);
        v406 = MsiString::operator unsigned short const *(&v819);
        v407 = v403(v402, v406, v405, v404);
        v408 = CComPointer<IMsiDatabase>::operator=(&v856, v407);
        if ( CComPointer<IMsiStorage>::operator->(v408) )
        {
          v409 = CComPointer<IMsiStorage>::operator->(&v821);
          v410 = CComPointer<IMsiStorage>::operator->(&v856);
          v11 = CMsiEngine::PostInitializeError(a1, v410, v409, 5);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v910);
          goto LABEL_497;
        }
        if ( g_dmDiagnosticMode )
        {
          v411 = (const unsigned __int16 *)MsiString::operator unsigned short const *(a1 + 528);
          DebugString(
            9,
            0,
            0,
            L"Package name extracted from package path: '%s'",
            v411,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v412 = CComPointer<IMsiStorage>::operator->(&v910);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v412 + 424LL))(v412) )
        {
          CTempBuffer<unsigned short,20>::CTempBuffer<unsigned short,20>((__int64)v1068);
          CTempBuffer<unsigned short,20>::operator CTempBufferRef<unsigned short> &(v1068);
          v413 = (const WCHAR *)MsiString::operator unsigned short const *(&v819);
          if ( (unsigned __int8)DetermineLongFileNameOnly(v413) )
          {
            v414 = CComPointer<IMsiStorage>::operator->(v1068);
            MsiString::operator=(a1 + 528, v414);
            if ( g_dmDiagnosticMode )
            {
              v415 = (const unsigned __int16 *)MsiString::operator unsigned short const *(a1 + 528);
              DebugString(
                9,
                0,
                0,
                L"Package to be registered: '%s'",
                v415,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            }
          }
          CTempBuffer<unsigned short,20>::~CTempBuffer<unsigned short,20>((__int64)v1068);
        }
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v910);
      }
    }
    if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) != 0
      && (unsigned int)MsiString::TextSize((MsiString *)&v832) )
    {
      MsiString::MsiString((MsiString *)v911);
      v416 = (const struct IMsiString **)MsiString::operator&(v911);
      v417 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v819);
      v418 = SplitPath(v417, v416, 0);
      v419 = CComPointer<IMsiDatabase>::operator=(&v856, v418);
      if ( CComPointer<IMsiStorage>::operator->(v419) )
      {
        v420 = CComPointer<IMsiStorage>::operator->(&v821);
        v421 = CComPointer<IMsiStorage>::operator->(&v856);
        v11 = CMsiEngine::PostInitializeError(a1, v421, v420, 5);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v911);
        goto LABEL_497;
      }
      v422 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
      v423 = CComPointer<IMsiStorage>::operator->(v911);
      v424 = MsiString::MsiString((MsiString *)v989, L"TARGETDIR");
      v425 = CComPointer<IMsiStorage>::operator->(v424);
      v422(a1, v425, v423);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v989);
      if ( (*(char (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) < 0 )
      {
        v426 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
        v427 = MsiString::MsiString((MsiString *)v990, L"SHORTFILENAMES");
        v428 = CComPointer<IMsiStorage>::operator->(v427);
        v426(a1, v428, 1);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v990);
      }
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v911);
    }
    v429 = CComPointer<IMsiStorage>::operator->(&v822);
    PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::LoadMessageHeaders(a1, v429);
    if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v889);
      CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>((__int64)v1067);
      v354 = (GUIDAndSequence *)&v869;
      goto LABEL_456;
    }
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v889);
    CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>((__int64)v1067);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v869);
    v334 = 0;
    v276 = a1 + 448;
  }
  if ( CComPointer<IMsiStorage>::operator->(&v828) )
  {
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v890, 0);
    v430 = CComPointer<IMsiStorage>::operator->(&v828);
    v431 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v430 + 56LL);
    v432 = CComPointer<IEnumMsiRecord>::operator=(&v890);
    v433 = v431(v430, L"AdminProperties", 0, v432);
    CComPointer<IMsiDatabase>::operator=(&v856, v433);
    v334 = 0;
    if ( !CComPointer<IMsiStorage>::operator->(&v856) && CComPointer<IMsiStorage>::operator->(&v890) )
    {
      *(_BYTE *)(a1 + 96) = 1;
      v434 = CComPointer<IMsiStorage>::operator->(&v890);
      v435 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v434 + 56LL))(v434);
      CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(
        (__int64)v1065,
        (unsigned __int64)(int)(v435 + 1) >> 1);
      if ( !CComPointer<IMsiStorage>::operator->(v1065) )
      {
        v436 = PostError(2346);
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v925, (__int64)v436);
        v437 = CComPointer<IMsiStorage>::operator->(&v925);
        v11 = CMsiEngine::PostInitializeError(a1, v437, &g_MsiStringNull, 33);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v925);
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)v1065);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v890);
        goto LABEL_321;
      }
      v438 = CComPointer<IMsiStorage>::operator->(&v890);
      v439 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v438 + 64LL);
      v440 = CComPointer<IMsiStorage>::operator->(v1065);
      v439(v438, v440, v435);
      v441 = CComPointer<IMsiStorage>::operator->(v1065);
      v334 = 0;
      LOBYTE(v816) = 0;
      ProcessCommandLine(v441, 0, 0, 0, 0, 0, 0, 0, 0, 0, v276, a1, v816);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)v1065);
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v890);
  }
  if ( !v826 )
  {
    v442 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
    v443 = *(_BYTE *)(a1 + 601);
    v444 = v442 & 1;
    v445 = v850 != 0;
    v446 = v853 != 0;
    v447 = MsiString::operator unsigned short const *(&v820);
    LOBYTE(v448) = v443;
    LOBYTE(lpString2a) = v444;
    LOBYTE(v449) = v445;
    LOBYTE(v450) = v446;
    v451 = AcceptProduct(v447, v450, v449, v448, lpString2a);
    v334 = 0;
    *(_DWORD *)(a1 + 580) = v451;
    if ( !v451 )
      goto LABEL_785;
    v452 = v451 - 1;
    if ( v452 )
    {
      if ( (unsigned int)(v452 - 1) <= 1 )
      {
        *(_BYTE *)(a1 + 579) = 1;
        g_fRunScriptElevated = 1;
        goto LABEL_544;
      }
LABEL_785:
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
      v11 = 21;
      goto LABEL_691;
    }
    *(_BYTE *)(a1 + 579) = 0;
    g_fRunScriptElevated = 0;
  }
LABEL_544:
  v926 = 0;
  v453 = MsiString::MsiString((MsiString *)v991, L"TARGETDIR");
  v454 = CComPointer<IMsiStorage>::operator->(v453);
  v455 = v877;
  LOBYTE(v816) = 0;
  v456 = a1 + 448;
  ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, v454, &v926, 1, a1 + 448, 0, v816);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v991);
  if ( v926 )
  {
    v457 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v926 + 80LL))(v926);
    MsiString::MsiString((MsiString *)v873, v457);
    if ( (unsigned int)MsiString::Compare(v873, 7, L"Config.Msi") )
    {
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v885, 0);
      v458 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(&v885);
      v459 = (const struct IMsiString *)CComPointer<IMsiStorage>::operator->(v873);
      PathObject = CMsiEngine::CreatePathObject((CMsiEngine *)a1, v459, v458);
      v461 = CComPointer<IMsiDatabase>::operator=(&v856, PathObject);
      if ( CComPointer<IMsiStorage>::operator->(v461) )
      {
        if ( g_dmDiagnosticMode )
        {
          v501 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v873);
          DebugString(
            9,
            0,
            0,
            L"Error : Invalid string could not crate path %s",
            v501,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        goto LABEL_584;
      }
      v462 = CComPointer<IMsiStorage>::operator->(&v885);
      v463 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v462 + 72LL))(v462);
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v912, v463);
      v464 = CComPointer<IMsiStorage>::operator->(&v912);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v464 + 56LL))(v464) != 4 )
      {
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v905, 0);
        v465 = *(_QWORD *)(a1 + 128);
        v466 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v465 + 120LL);
        v467 = CComPointer<IEnumMsiRecord>::operator=(&v905);
        v468 = CComPointer<IMsiStorage>::operator->(&v912);
        v469 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v468 + 168LL))(v468);
        v470 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v992, v469);
        v471 = MsiString::operator unsigned short const *(v470);
        v472 = v466(v465, v471, v467);
        v473 = CComPointer<IMsiDatabase>::operator=(&v856, v472);
        v474 = CComPointer<IMsiStorage>::operator->(v473);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v992);
        if ( v474 )
        {
          if ( g_dmDiagnosticMode )
          {
            v489 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v873);
            v490 = L"Error : Could Not create path in the given volume: %s";
            goto LABEL_582;
          }
          goto LABEL_583;
        }
        v475 = CComPointer<IMsiStorage>::operator->(&v905);
        v476 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v475 + 104LL);
        v477 = MsiString::MsiString((MsiString *)v993, L"Config.Msi");
        v478 = CComPointer<IMsiStorage>::operator->(v477);
        v479 = v476(v475, v478);
        v480 = CComPointer<IMsiDatabase>::operator=(&v856, v479);
        v481 = CComPointer<IMsiStorage>::operator->(v480);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v993);
        v334 = 0;
        if ( v481 )
        {
          if ( g_dmDiagnosticMode )
          {
            v489 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v873);
            v490 = L"Error : Could Not add Backupfolder string to verify TARGETDIR: %s";
            goto LABEL_582;
          }
LABEL_583:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v905);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v912);
LABEL_584:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v885);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v873);
LABEL_585:
          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
          v11 = 3;
          goto LABEL_691;
        }
        v482 = CComPointer<IMsiStorage>::operator->(&v885);
        v483 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v482 + 56LL))(v482);
        v484 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v995, v483);
        v485 = CComPointer<IMsiStorage>::operator->(&v905);
        v486 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v485 + 56LL))(v485);
        v487 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v994, v486);
        v488 = MsiString::operator unsigned short const *(v487);
        LODWORD(v484) = MsiString::Compare(v484, 3, v488);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v994);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v995);
        if ( (_DWORD)v484 )
        {
          if ( g_dmDiagnosticMode )
          {
            v489 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v873);
            v490 = L"Error : Invalid TARGETDIR: %s";
LABEL_582:
            DebugString(9, 0, 0, v490, v489, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
            goto LABEL_583;
          }
          goto LABEL_583;
        }
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v905);
        v456 = a1 + 448;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v912);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v885);
    }
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v873);
  }
  v491 = 0;
  if ( *(_BYTE *)(a1 + 579) )
  {
    if ( !IsAdmin() && !*(_BYTE *)(a1 + 601) )
    {
      v12 |= 0x200u;
      v492 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"EnableUserControl");
      v493 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v996, v492);
      if ( !(unsigned int)MsiString::TextSize(v493) )
        v491 = (unsigned int)GetIntegerPolicyValue(13) != 1;
    }
  }
  if ( (v12 & 0x200) != 0 )
  {
    v12 &= ~0x200u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v996);
  }
  if ( v491 )
  {
    v494 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v495 = MsiString::MsiString((MsiString *)v997, L"RestrictedUserControl");
    v496 = CComPointer<IMsiStorage>::operator->(v495);
    v494(a1, v496, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v997);
    v334 = 1;
  }
  LOBYTE(v817) = v334;
  v497 = 0;
  if ( !(unsigned int)ProcessCommandLine(v455, 0, 0, 0, 0, 0, 0, 0, 0, 1, v456, a1, v817) )
    goto LABEL_585;
  if ( g_scServerContext == 2 )
  {
    v498 = 1;
    LOBYTE(v497) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 784LL))(a1) != 0;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 784LL))(a1)
      || (Instance = 0, !*(_QWORD *)(a1 + 176)) )
    {
      Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(v497);
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 784LL))(a1)
      && Instance
      && CRestartManagerWrapper::HasSessionHandle(Instance) )
    {
      v500 = CRestartManagerWrapper::EndSession(Instance);
      if ( v500 != 1626 )
      {
        if ( v500 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: Failed while closing session. Error: %d",
              (const unsigned __int16 *)v500,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        else if ( g_dmDiagnosticMode )
        {
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Session closed.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      CRestartManagerWrapper::DestroyInstance(v497);
      Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(v497);
    }
    v502 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
             a1,
             L"MSIRESTARTMANAGERCONTROL");
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v913, v502);
    v503 = GetIntegerPolicyValue(26);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v913) )
    {
      if ( (unsigned int)MsiString::Compare(&v913, 0, L"Disable") == 1 )
      {
        v498 = 0;
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Disabled by %s property; Windows Installer will use the built-in FilesInUse functionality.",
            L"MSIRESTARTMANAGERCONTROL",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( !*(_QWORD *)(a1 + 176) && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
        {
          v927 = 0;
          v504 = MsiString::MsiString((MsiString *)v998, L"MSIRESTARTMANAGERCONTROL");
          v505 = CComPointer<IMsiStorage>::operator->(v504);
          LOBYTE(v818) = 0;
          ProcessCommandLine(v877, 0, 0, 0, 0, 0, 0, v505, &v927, 1, a1 + 448, 0, v818);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v998);
          if ( v927 )
          {
            IMsiData::Release(v927);
            v506 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
            v507 = 1;
          }
          else
          {
            v506 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
            v507 = 2;
          }
          goto LABEL_606;
        }
      }
    }
    else if ( v503 == 1 )
    {
      v498 = 0;
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"RESTART MANAGER: Disabled by %s system policy; Windows Installer will use the built-in FilesInUse functionality.",
          L"DisableAutomaticApplicationShutdown",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( !*(_QWORD *)(a1 + 176) && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
      {
        v506 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        v507 = 3;
LABEL_606:
        CMsiSQMSession::RecordDWORD(v506, 0xE25u, v507);
      }
    }
    if ( Instance )
    {
      if ( !v498 )
      {
        Disable = CRestartManagerWrapper::GetDisable(Instance);
        CRestartManagerWrapper::SetDisable(Instance, Disable | 4u);
LABEL_624:
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v913);
        goto LABEL_625;
      }
    }
    else if ( !v498 )
    {
      goto LABEL_624;
    }
    if ( !*(_QWORD *)(a1 + 176) && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
    {
      v509 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
      CMsiSQMSession::RecordDWORD(v509, 0xE25u, 0);
    }
    if ( Instance )
    {
      CAPITempBuffer<unsigned short,1>::CAPITempBuffer<unsigned short,1>((__int64)v1066);
      *(_WORD *)CComPointer<IMsiStorage>::operator->(v1066) = 0;
      CAPITempBuffer<unsigned short,1>::operator CAPITempBufferRef<unsigned short> &(v1066);
      started = CRestartManagerWrapper::StartSession(Instance);
      if ( started )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Failed to open session; Windows Installer will use the built-in FilesInUse functionality. Error: %d",
            (const unsigned __int16 *)started,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
      }
      else
      {
        v511 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
        v512 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(v1066);
        v513 = MsiString::MsiString((MsiString *)v1000, v512);
        v514 = CComPointer<IMsiStorage>::operator->(v513);
        v515 = MsiString::MsiString((MsiString *)v999, L"MsiRestartManagerSessionKey");
        v516 = CComPointer<IMsiStorage>::operator->(v515);
        v511(a1, v516, v514);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v999);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1000);
        if ( g_dmDiagnosticMode )
          DebugString(
            10,
            0,
            0,
            L"RESTART MANAGER: Session opened.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
      }
      if ( v503 == 2 || (unsigned int)MsiString::Compare(&v913, 0, L"DisableShutdown") == 1 )
      {
        v517 = CRestartManagerWrapper::GetDisable(Instance);
        CRestartManagerWrapper::SetDisable(Instance, v517 | 8u);
      }
      CAPITempBuffer<unsigned short,1>::Destroy(v1066);
    }
    goto LABEL_624;
  }
LABEL_625:
  CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v863, 0);
  CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v861, 0);
  v518 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 128) + 192LL))(
           *(_QWORD *)(a1 + 128),
           2147483650LL,
           0xFFFFFFFFLL);
  v519 = CComPointer<IMsiDatabase>::operator=(&v863, v518);
  if ( !CComPointer<IMsiStorage>::operator->(v519) )
    goto LABEL_689;
  v520 = CComPointer<IMsiStorage>::operator->(&v863);
  v521 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v520 + 112LL))(
           v520,
           L"SYSTEM\\CurrentControlSet\\Control\\Session Manager",
           0,
           0xFFFFFFFFLL);
  v522 = CComPointer<IMsiDatabase>::operator=(&v861, v521);
  if ( !CComPointer<IMsiStorage>::operator->(v522) )
    goto LABEL_689;
  v896 = 0;
  MsiString::MsiString((MsiString *)v860);
  v523 = CComPointer<IMsiStorage>::operator->(&v861);
  v524 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v523 + 88LL))(v523, &v896);
  v525 = CComPointer<IMsiDatabase>::operator=(&v856, v524);
  if ( CComPointer<IMsiStorage>::operator->(v525) || !v896 )
  {
    v531 = 0;
  }
  else
  {
    v526 = CComPointer<IMsiStorage>::operator->(&v861);
    v527 = *(__int64 (__fastcall **)(__int64, const WCHAR *, __int64))(*(_QWORD *)v526 + 40LL);
    v528 = MsiString::operator&(v860);
    v529 = v527(v526, L"PendingFileRenameOperations", v528);
    v530 = CComPointer<IMsiDatabase>::operator=(&v856, v529);
    v531 = 0;
    if ( !CComPointer<IMsiStorage>::operator->(v530)
      && ((unsigned int)MsiString::TextSize((MsiString *)v860) != 1
       || *(_WORD *)MsiString::operator unsigned short const *(v860))
      && (unsigned int)MsiString::TextSize((MsiString *)v860) )
    {
      v532 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v533 = MsiString::MsiString((MsiString *)v1001, L"MsiSystemRebootPending");
      v534 = CComPointer<IMsiStorage>::operator->(v533);
      v532(a1, v534, 1);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1001);
    }
  }
  v535 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"SECONDSEQUENCE");
  v536 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1002, v535);
  v537 = MsiString::TextSize(v536);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1002);
  if ( v537 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Engine has iefSecondSequence set to true.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 16, 1);
  }
  if ( v826
    || !v853
    || v849
    || (v12 |= 0x400u,
        v538 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"PATCH"),
        v539 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1003, v538),
        v540 = 1,
        !(unsigned int)MsiString::TextSize(v539)) )
  {
    v540 = 0;
  }
  if ( (v12 & 0x400) != 0 )
  {
    v12 &= ~0x400u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1003);
  }
  if ( v540 )
  {
    v541 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v820);
    if ( IsProductManaged(v541) )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
      v11 = 37;
      goto LABEL_691;
    }
  }
  v542.lpVtbl = *(struct IUnknownVtbl **)a1;
  if ( v850 == 1 )
  {
    v543 = v542.lpVtbl[7].QueryInterface;
    v544 = MsiString::MsiString((MsiString *)v1004, L"ALLUSERS");
    v545 = CComPointer<IMsiStorage>::operator->(v544);
    ((void (__fastcall *)(__int64, __int64, __int64))v543)(a1, v545, 1);
    v546 = (GUIDAndSequence *)v1004;
  }
  else
  {
    v547 = v542.lpVtbl[6].Release;
    v548 = MsiString::MsiString((MsiString *)v1006, &Default);
    v549 = CComPointer<IMsiStorage>::operator->(v548);
    v550 = MsiString::MsiString((MsiString *)v1005, L"ALLUSERS");
    v551 = CComPointer<IMsiStorage>::operator->(v550);
    ((void (__fastcall *)(__int64, __int64, __int64))v547)(a1, v551, v549);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1005);
    v546 = (GUIDAndSequence *)v1006;
  }
  GUIDAndSequence::~GUIDAndSequence(v546);
  v552 = v845;
  v553.lpVtbl = *(struct IUnknownVtbl **)a1;
  if ( v845 == 1 )
  {
    v554 = v553.lpVtbl[7].QueryInterface;
    v555 = MsiString::MsiString((MsiString *)v1007, L"MSIINSTALLPERUSER");
    v556 = CComPointer<IMsiStorage>::operator->(v555);
    ((void (__fastcall *)(__int64, __int64, __int64))v554)(a1, v556, 1);
    v557 = (GUIDAndSequence *)v1007;
  }
  else
  {
    v558 = v553.lpVtbl[6].Release;
    v559 = MsiString::MsiString((MsiString *)v1009, &Default);
    v560 = CComPointer<IMsiStorage>::operator->(v559);
    v561 = MsiString::MsiString((MsiString *)v1008, L"MSIINSTALLPERUSER");
    v562 = CComPointer<IMsiStorage>::operator->(v561);
    ((void (__fastcall *)(__int64, __int64, __int64))v558)(a1, v562, v560);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1008);
    v557 = (GUIDAndSequence *)v1009;
  }
  GUIDAndSequence::~GUIDAndSequence(v557);
  if ( !*(_QWORD *)(a1 + 176)
    && g_scServerContext == 2
    && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
  {
    v563 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
    CMsiSQMSession::RecordDWORD(v563, 0x1054u, v552 != 0);
  }
  v564 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v565 = CComPointer<IMsiStorage>::operator->(&v827);
  v566 = MsiString::MsiString((MsiString *)v1010, L"TRANSFORMS");
  v567 = CComPointer<IMsiStorage>::operator->(v566);
  v564(a1, v567, v565);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1010);
  if ( g_dmDiagnosticMode )
  {
    v12 |= 0x800u;
    v568 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"TRANSFORMS");
    v569 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1011, v568);
    v570 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v569);
    DebugString(
      9,
      0,
      0,
      L"TRANSFORMS property is now: %s",
      v570,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  if ( (v12 & 0x800) != 0 )
  {
    v12 &= ~0x800u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1011);
  }
  v571 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v572 = CComPointer<IMsiStorage>::operator->(&v829);
  v573 = MsiString::MsiString((MsiString *)v1012, L"PRODUCTLANGUAGE");
  v574 = CComPointer<IMsiStorage>::operator->(v573);
  v571(a1, v574, v572);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1012);
  if ( *(_BYTE *)(a1 + 577) )
  {
    v575 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
    v576 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 176) + 296LL))(*(_QWORD *)(a1 + 176));
    v577 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1014, v576);
    v578 = CComPointer<IMsiStorage>::operator->(v577);
    v579 = MsiString::MsiString((MsiString *)v1013, L"ParentProductCode");
    v580 = CComPointer<IMsiStorage>::operator->(v579);
    v575(a1, v580, v578);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1013);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1014);
    v581 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
    v582 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)(a1 + 176) + 184LL))(
             *(_QWORD *)(a1 + 176),
             L"OriginalDatabase");
    v583 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1016, v582);
    v584 = CComPointer<IMsiStorage>::operator->(v583);
    v585 = MsiString::MsiString((MsiString *)v1015, L"ParentOriginalDatabase");
    v586 = CComPointer<IMsiStorage>::operator->(v585);
    v581(a1, v586, v584);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1015);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1016);
  }
  v587 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v588 = CComPointer<IMsiStorage>::operator->(&v823);
  v589 = MsiString::MsiString((MsiString *)v1017, L"SourceDir");
  v590 = CComPointer<IMsiStorage>::operator->(v589);
  v587(a1, v590, v588);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1017);
  v591 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v592 = CComPointer<IMsiStorage>::operator->(&v823);
  v593 = MsiString::MsiString((MsiString *)v1018, L"SOURCEDIR");
  v594 = CComPointer<IMsiStorage>::operator->(v593);
  v591(a1, v594, v592);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1018);
  v595 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v596 = CComPointer<IMsiStorage>::operator->(&v825);
  v597 = MsiString::MsiString((MsiString *)v1019, L"SourcedirProduct");
  v598 = CComPointer<IMsiStorage>::operator->(v597);
  v595(a1, v598, v596);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1019);
  v599 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v600 = MsiString::MsiString((MsiString *)v1020, L"VersionDatabase");
  v601 = CComPointer<IMsiStorage>::operator->(v600);
  LODWORD(v599) = v599(a1, v601);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1020);
  if ( (_DWORD)v599 == 0x80000000 )
  {
    v602 = *(_DWORD *)(a1 + 456);
    v603 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
    v604 = MsiString::MsiString((MsiString *)v1021, L"VersionDatabase");
    v605 = CComPointer<IMsiStorage>::operator->(v604);
    v603(a1, v605, v602);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1021);
  }
  if ( (a6 & 0x10) != 0 )
  {
    if ( (a6 & 0x200) != 0 )
    {
      v531 = 1;
    }
    else if ( (a6 & 0x1000) != 0 )
    {
      v531 = 3;
    }
    else if ( (a6 & 0x400) != 0 )
    {
      v531 = 2;
    }
  }
  v606 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v822);
  CMsiEngine::CreateFolderCache((CMsiEngine *)a1, v606);
  v607 = *(_QWORD *)(a1 + 128);
  v608 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)v607 + 64LL);
  v609 = CComPointer<IMsiStorage>::operator->(a1 + 1896);
  v610 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 184) + 24LL))(*(_QWORD *)(a1 + 184));
  v611 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1022, v610);
  v612 = CComPointer<IMsiStorage>::operator->(v611);
  v613 = v531;
  v614 = v850;
  LODWORD(v609) = v608(v607, v612, v850, v613, v609);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v1022);
  if ( !(_DWORD)v609 )
    goto LABEL_913;
  v615 = *(_QWORD *)(a1 + 128);
  v616 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v615 + 72LL);
  v617 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 184) + 24LL))(*(_QWORD *)(a1 + 184));
  v618 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1023, v617);
  v619 = CComPointer<IMsiStorage>::operator->(v618);
  LOBYTE(v616) = v616(v615, a1, v619);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v1023);
  if ( !(_BYTE)v616 )
    goto LABEL_913;
  if ( g_fWinNT64 )
  {
    if ( CWin64DualFolders::IsInitialized((CWin64DualFolders *)&g_Win64DualFolders) )
    {
      CWin64DualFolders::AddRef((CWin64DualFolders *)&g_Win64DualFolders);
      CWin64DualFolders::SetPackageBitness((CWin64DualFolders *)&g_Win64DualFolders, *(_WORD *)(a1 + 604) == 0);
    }
    else
    {
      strFolderPairs::strFolderPairs((strFolderPairs *)v1069, L"System64Folder", L"SystemFolder", 1);
      strFolderPairs::strFolderPairs((strFolderPairs *)v1071, L"ProgramFiles64Folder", L"ProgramFilesFolder");
      strFolderPairs::strFolderPairs((strFolderPairs *)v1072, L"CommonFiles64Folder", L"CommonFilesFolder");
      strFolderPairs::strFolderPairs((strFolderPairs *)v1073, &Default, &Default);
      v620 = 0;
      if ( (unsigned int)MsiString::TextSize((MsiString *)v1070) )
      {
        do
        {
          v621 = (MsiString *)&v1069[24 * v620];
          if ( !(unsigned int)MsiString::TextSize(v621) )
            break;
          v622 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 176LL);
          v623 = CComPointer<IMsiStorage>::operator->(&v1069[24 * v620]);
          v624 = v622(a1, v623);
          CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v921, v624);
          v625 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 176LL);
          v626 = CComPointer<IMsiStorage>::operator->((char *)v621 + 8);
          v627 = v625(a1, v626);
          CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v920, v627);
          if ( (unsigned int)MsiString::TextSize((MsiString *)&v921)
            && (unsigned int)MsiString::TextSize((MsiString *)&v920) )
          {
            MsiString::operator=(&v1069[24 * v620], &v921);
            MsiString::operator=((char *)v621 + 8, &v920);
          }
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v920);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v921);
          ++v620;
        }
        while ( (unsigned int)MsiString::TextSize((MsiString *)&v1070[3 * v620]) );
        v614 = v850;
      }
      if ( !CWin64DualFolders::Initialize(
              (CWin64DualFolders *)&g_Win64DualFolders,
              *(_WORD *)(a1 + 604) == 0,
              (const struct strFolderPairs *)v1069,
              4u) )
      {
        `vector destructor iterator'(v1069, 0x18u, 4u, (void (*)(void *))strFolderPairs::~strFolderPairs);
        goto LABEL_688;
      }
      `vector destructor iterator'(v1069, 0x18u, 4u, (void (*)(void *))strFolderPairs::~strFolderPairs);
    }
  }
  v899 = 0;
  v629 = ((__int64 (__fastcall *)(int *))KERNEL32::CheckElevationEnabled)(&v899);
  v630 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v631 = MsiString::MsiString((MsiString *)v1024, L"MSIUSEREALADMINDETECTION");
  v632 = CComPointer<IMsiStorage>::operator->(v631);
  v633 = v630(a1, v632);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1024);
  if ( !v629 && v899 && v633 != 1 && !*(_BYTE *)(a1 + 600) )
  {
    if ( *(_BYTE *)(a1 + 601) || !g_scServerContext )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"MSI_LUA: Setting AdminUser property to 1 because this is the client or the user has already permitted elevation",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v638 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v639 = MsiString::MsiString((MsiString *)v1026, L"AdminUser");
      v640 = CComPointer<IMsiStorage>::operator->(v639);
      v638(a1, v640, 1);
      v637 = (GUIDAndSequence *)v1026;
      goto LABEL_708;
    }
    if ( *(_BYTE *)(a1 + 579) && v614 == 1 && v849 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"MSI_LUA: Setting AdminUser property to 1 because the product is already installed managed and per-machine",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      v634 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v635 = MsiString::MsiString((MsiString *)v1025, L"AdminUser");
      v636 = CComPointer<IMsiStorage>::operator->(v635);
      v634(a1, v636, 1);
      v637 = (GUIDAndSequence *)v1025;
LABEL_708:
      GUIDAndSequence::~GUIDAndSequence(v637);
    }
  }
  if ( IsAdmin() || *(_BYTE *)(a1 + 579) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"MSI_LUA: Setting MsiRunningElevated property to 1 because the install is already running elevated.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    v641 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v642 = MsiString::MsiString((MsiString *)v1027, L"MsiRunningElevated");
    v643 = CComPointer<IMsiStorage>::operator->(v642);
    v641(a1, v643, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1027);
  }
  v644 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"AdminUser");
  v645 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1028, v644);
  v646 = MsiString::TextSize(v645);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1028);
  if ( (unsigned int)IsTerminalServerInstalled()
    && !CMsiEngine::TerminalServerInstallsAreAllowed((CMsiEngine *)a1, v646 != 0) )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
    v11 = 25;
    goto LABEL_691;
  }
  if ( *(_BYTE *)(a1 + 579) || v646 )
  {
    v647 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v648 = MsiString::MsiString((MsiString *)v1029, L"Privileged");
    v649 = CComPointer<IMsiStorage>::operator->(v648);
    v647(a1, v649, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1029);
  }
  v650 = (const struct IMsiString *)CComPointer<IMsiStorage>::operator->(&v820);
  CMsiEngine::InitializeUserInfo((CMsiEngine *)a1, v650);
  if ( *(_DWORD *)(a1 + 356) )
  {
    v651 = (IMsiData *)CComPointer<IMsiStorage>::operator->(&v839);
    *(_QWORD *)(a1 + 424) = v651;
    IMsiData::AddRef(v651);
    if ( (*(_BYTE *)(a1 + 36) & 4) != 0 )
    {
      v652 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
      v653 = DateTimeToString(*(_DWORD *)(a1 + 404));
      v654 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1031, (__int64)v653);
      v655 = CComPointer<IMsiStorage>::operator->(v654);
      v656 = MsiString::MsiString((MsiString *)v1030, L"Installed");
      v657 = CComPointer<IMsiStorage>::operator->(v656);
      v652(a1, v657, v655);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1030);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1031);
    }
  }
  v658 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v659 = CComPointer<IMsiStorage>::operator->(&v821);
  v660 = MsiString::MsiString((MsiString *)v1032, L"DATABASE");
  v661 = CComPointer<IMsiStorage>::operator->(v660);
  v658(a1, v661, v659);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1032);
  v662 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v663 = CComPointer<IMsiStorage>::operator->(&v819);
  v664 = MsiString::MsiString((MsiString *)v1033, L"OriginalDatabase");
  v665 = CComPointer<IMsiStorage>::operator->(v664);
  v662(a1, v665, v663);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1033);
  v666 = CComPointer<IMsiStorage>::operator->(&v822);
  *(_QWORD *)(a1 + 152) = v666;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v666 + 8LL))(v666);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 0x8000, 1);
  v671 = 0;
  if ( v848 != 3 )
  {
    v12 |= 0x1000u;
    v667 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"LIMITUI");
    v668 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1035, v667);
    if ( (unsigned int)MsiString::TextSize(v668)
      || (v12 |= 0x2000u,
          v669 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"NOUI"),
          v670 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1034, v669),
          (unsigned int)MsiString::TextSize(v670)) )
    {
      v671 = 1;
    }
  }
  if ( (v12 & 0x2000) != 0 )
  {
    v12 &= ~0x2000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1034);
  }
  if ( (v12 & 0x1000) != 0 )
  {
    v12 &= ~0x1000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1035);
  }
  if ( v671 )
    v848 = 2;
  v672 = *(_QWORD *)(a1 + 152);
  v673 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v672 + 72LL);
  v674 = MsiString::MsiString((MsiString *)v1036, L"MsiEmbeddedUI");
  v675 = CComPointer<IMsiStorage>::operator->(v674);
  v676 = v673(v672, v675) != 0;
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1036);
  v680 = 1;
  if ( (unsigned int)GetIntegerPolicyValue(27) != 1 )
  {
    v12 |= 0x4000u;
    v677 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
    v678 = MsiString::MsiString((MsiString *)v1037, L"MSIDISABLEEEUI");
    v679 = CComPointer<IMsiStorage>::operator->(v678);
    if ( v677(a1, v679) != 1 )
      v680 = 0;
  }
  if ( (v12 & 0x4000) != 0 )
  {
    v12 &= ~0x4000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1037);
  }
  if ( v680 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "EEUI - Disabling MsiEmbeddedUI due to property or policy",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    v676 = 0;
  }
  if ( g_pEmbeddedUI )
    goto LABEL_750;
  if ( dword_1803097B8 )
    goto LABEL_750;
  if ( dword_180309978 )
    goto LABEL_750;
  v12 |= 0x8000u;
  v681 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v682 = MsiString::MsiString((MsiString *)v1039, L"MSICLIENTUSESEXTERNALUI");
  v683 = CComPointer<IMsiStorage>::operator->(v682);
  if ( v681(a1, v683) == 1
    || (v12 |= 0x10000u,
        v684 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL),
        v685 = MsiString::MsiString((MsiString *)v1038, L"MSICLIENTUSESEMBEDDEDUI"),
        v686 = CComPointer<IMsiStorage>::operator->(v685),
        v684(a1, v686) == 1) )
  {
LABEL_750:
    v687 = 1;
  }
  else
  {
    v687 = 0;
  }
  if ( (v12 & 0x10000) != 0 )
  {
    v12 &= ~0x10000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1038);
  }
  if ( (v12 & 0x8000) != 0 )
  {
    v12 &= ~0x8000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1039);
  }
  if ( v687 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "EEUI - Disabling MsiEmbeddedUI due to existing external or embedded UI",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    v676 = 0;
  }
  v688 = v862;
  if ( v862 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "EEUI - Disabling MsiEmbeddedUI in dialog preview mode",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    v676 = 0;
  }
  v689 = g_scServerContext;
  if ( g_scServerContext == 2 )
  {
    if ( dword_180309774 == 2 )
      goto LABEL_773;
    if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        "EEUI - Disabling MsiEmbeddedUI for service because it's not a quiet/basic install",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
      v689 = g_scServerContext;
    }
    v676 = 0;
  }
  if ( !v689 && v848 == 2 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "EEUI - Disabling MsiEmbeddedUI in quiet-basic mode on client side",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    v676 = 0;
  }
LABEL_773:
  if ( v848 == 3 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "EEUI - Disabling MsiEmbeddedUI in quiet mode",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    goto LABEL_776;
  }
  if ( v676 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "EEUI - Running MsiEmbeddedUI code",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    v692 = (CMsiEmbeddedUIManager *)operator new(0x448u);
    if ( !v692 )
    {
      g_pEmbeddedUI = 0;
      goto LABEL_688;
    }
    v693 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v822);
    g_pEmbeddedUI = (LPCWSTR)CMsiEmbeddedUIManager::CMsiEmbeddedUIManager(v692, v693);
    if ( g_pEmbeddedUI )
    {
      CustomActionManager = GetCustomActionManager((struct IMsiEngine *)a1);
      if ( !CustomActionManager
        || !(unsigned int)CMsiEmbeddedUIManager::SetCustomActionManager(
                            (CMsiEmbeddedUIManager *)g_pEmbeddedUI,
                            CustomActionManager) )
      {
        goto LABEL_811;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v695 = CreateMsiHandle((struct IUnknown *)a1, 790542);
      PMSIHANDLE::PMSIHANDLE((PMSIHANDLE *)&v880, v695);
      v696 = 0;
      v697 = CreateRecord(1u);
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v886, (__int64)v697);
      v698 = CComPointer<IMsiStorage>::operator->(&v886);
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v698 + 104LL))(v698, 1, 7);
      v699 = CComPointer<IMsiStorage>::operator->(&v886);
      MsiUIMessageContext::Invoke(&g_MessageContext, 402653184, v699);
      if ( IsAdmin() )
      {
        v700 = (*(__int64 (**)(__int64, const wchar_t *, ...))(*(_QWORD *)a1 + 184LL))(a1, L"%MsiBreak");
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v928, v700);
        v696 = (unsigned int)MsiString::Compare(&v928, 0, L"MsiEmbeddedUI") == 1;
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v928);
      }
      v701 = PMSIHANDLE::operator unsigned long(&v880);
      if ( (unsigned int)CMsiEmbeddedUIManager::InitializeHandlers(
                           (CMsiEmbeddedUIManager *)g_pEmbeddedUI,
                           v701,
                           (enum iuiEnum *)&v848,
                           (enum iioEnum *)&a6,
                           v696) )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v886);
        PMSIHANDLE::~PMSIHANDLE(&v880);
        goto LABEL_688;
      }
      if ( v848 != 3 )
      {
        v702 = CComPointer<IMsiStorage>::operator->(&v886);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v702 + 104LL))(v702, 1, 8);
        v703 = CComPointer<IMsiStorage>::operator->(&v886);
        MsiUIMessageContext::Invoke(&g_MessageContext, 402653184, v703);
      }
      if ( !g_scServerContext )
      {
        v704 = *(_QWORD *)(a1 + 136);
        if ( !v704 )
        {
LABEL_810:
          *(_BYTE *)(a1 + 578) = (a6 & 8) != 0;
          *(_DWORD *)(a1 + 584) = a6;
          MsiUIMessageContext::ResetUILevel(&g_MessageContext, v848, a6);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v886);
          PMSIHANDLE::~PMSIHANDLE(&v880);
LABEL_811:
          v705 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
          v706 = MsiString::MsiString((MsiString *)v1040, L"MSICLIENTUSESEMBEDDEDUI");
          v707 = CComPointer<IMsiStorage>::operator->(v706);
          v705(a1, v707, 1);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1040);
          LODWORD(v705) = v848;
          v708 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
          v709 = MsiString::MsiString((MsiString *)v1041, L"CLIENTUILEVEL");
          v710 = CComPointer<IMsiStorage>::operator->(v709);
          v708(a1, v710, (unsigned int)v705);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1041);
          v688 = v862;
          goto LABEL_776;
        }
        if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v704 + 184LL))(v704) & 1) != 0
          && v848 == 3
          && CMsiEmbeddedUIManager::GetFilter((CMsiEmbeddedUIManager *)g_pEmbeddedUI) )
        {
          CMsiEmbeddedUIManager::SetChainTransaction((CMsiEmbeddedUIManager *)g_pEmbeddedUI, 1);
        }
      }
      if ( g_scServerContext == 2
        && CMsiTransaction::m_pMsiTransaction
        && !CMsiTransaction::FMultiPackageTransaction((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction)
        && !CMsiTransaction::m_fRollbackDisabled )
      {
        CMsiEmbeddedUIManager::SetChainTransaction((CMsiEmbeddedUIManager *)g_pEmbeddedUI, 1);
      }
      goto LABEL_810;
    }
LABEL_688:
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
LABEL_689:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
    goto LABEL_690;
  }
LABEL_776:
  *(_DWORD *)(a1 + 56) = v848;
  if ( *(_QWORD *)(a1 + 176) )
  {
    if ( (unsigned int)CMsiEngine::InTransaction() )
    {
      *(_DWORD *)(a1 + 76) = 1;
      *(_DWORD *)(a1 + 88) = 1;
      if ( (a6 & 1) == 0 )
        *(_DWORD *)(a1 + 80) = 1;
    }
    v690 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 104LL);
    v691 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 176) + 96LL))(*(_QWORD *)(a1 + 176));
    v690(a1, 256, (v691 >> 8) & 1);
    if ( *(_DWORD *)(a1 + 80) && *(_BYTE *)(*(_QWORD *)(a1 + 176) + 579LL) != *(_BYTE *)(a1 + 579) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          "Child install has different elevation state than parent. Possible pre-existing install or machine/user conflic"
          "t. Failing child install.",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          0,
          0);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
      goto LABEL_785;
    }
  }
  else if ( v688 )
  {
    if ( (unsigned int)CMsiEngine::LoadHandler(a1) == 0x3FFF )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
      v11 = 10;
      goto LABEL_691;
    }
  }
  else
  {
    PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::InitializeUI(a1, v848);
    if ( PatchMetaDataForNewObsoletedAndSupercededMSPs
      || (PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::InitializeLogging(a1)) != 0 )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
      goto LABEL_264;
    }
  }
  CMsiEngine::SetPatchSourceProperties(a1);
  v711 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"SHORTFILENAMES");
  CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v884, v711);
  v712 = *(void (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)a1 + 104LL);
  v713 = MsiString::TextSize((MsiString *)&v884);
  v712(a1, 1024, v713 > 0);
  v714 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 8) + 296LL))(a1 + 8, 1);
  if ( v714 == 2 )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v884);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
    v11 = 34;
    goto LABEL_691;
  }
  if ( v714 == 10 )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v884);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
    v11 = 39;
    goto LABEL_691;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 840LL))(a1, 4) )
  {
    g_iUITicksStep = 6;
    g_iUIWaitTick = 300;
  }
  v715 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v716 = MsiString::MsiString((MsiString *)v1042, L"CLIENTUILEVEL");
  v717 = CComPointer<IMsiStorage>::operator->(v716);
  v718 = v715(a1, v717);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1042);
  v723 = 0;
  if ( v718 != 3 )
  {
    v12 |= 0x20000u;
    v719 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"LIMITUI");
    v720 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1044, v719);
    if ( (unsigned int)MsiString::TextSize(v720)
      || (v12 |= 0x40000u,
          v721 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"NOUI"),
          v722 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1043, v721),
          (unsigned int)MsiString::TextSize(v722)) )
    {
      v723 = 1;
    }
  }
  if ( (v12 & 0x40000) != 0 )
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1043);
  if ( (v12 & 0x20000) != 0 )
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1044);
  if ( v723 )
    goto LABEL_845;
  if ( v718 == 0x80000000 )
    v718 = *(_DWORD *)(a1 + 56);
  if ( !v718 )
  {
    v726 = 5;
    goto LABEL_846;
  }
  v724 = v718 - 1;
  if ( !v724 )
  {
    v726 = 4;
    goto LABEL_846;
  }
  v725 = v724 - 1;
  if ( !v725 )
  {
LABEL_845:
    v726 = 3;
    goto LABEL_846;
  }
  if ( v725 == 1 )
    v726 = 2;
  else
    v726 = 1;
LABEL_846:
  v727 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
  v728 = MsiString::MsiString((MsiString *)v1045, L"UILevel");
  v729 = CComPointer<IMsiStorage>::operator->(v728);
  v727(a1, v729, v726);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1045);
  if ( g_scServerContext == 2 && CMsiTransaction::m_pMsiTransaction )
    CMsiTransaction::SetClientUILevel((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction, v726);
  v730 = a6;
  if ( (a6 & 0x8000) != 0 )
  {
    HIBYTE(word_180309778) = 1;
    v731 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v732 = MsiString::MsiString((MsiString *)v1046, L"MsiUIProgressOnly");
    v733 = CComPointer<IMsiStorage>::operator->(v732);
    v731(a1, v733, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1046);
    v730 = a6;
  }
  if ( (v730 & 0x10000) != 0 )
  {
    v734 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v735 = MsiString::MsiString((MsiString *)v1047, L"MsiUIHideCancel");
    v736 = CComPointer<IMsiStorage>::operator->(v735);
    v734(a1, v736, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1047);
    v730 = a6;
  }
  if ( (v730 & 0x20000) != 0 )
  {
    v737 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v738 = MsiString::MsiString((MsiString *)v1048, L"MsiUISourceResOnly");
    v739 = CComPointer<IMsiStorage>::operator->(v738);
    v737(a1, v739, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1048);
  }
  if ( v864 == 4 )
  {
    v740 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v741 = MsiString::MsiString((MsiString *)v1049, L"MsiUIUACOnly");
    v742 = CComPointer<IMsiStorage>::operator->(v741);
    v740(a1, v742, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1049);
  }
  v743 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"FASTOEM");
  v744 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1050, v743);
  v745 = MsiString::TextSize(v744);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1050);
  MsiUIMessageContext::SetOEMInstall((MsiUIMessageContext *)&g_MessageContext, v745 != 0);
  if ( v745 )
  {
    v746 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"PATCH");
    v747 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1051, v746);
    v748 = MsiString::TextSize(v747);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1051);
    if ( v748 )
    {
      if ( g_dmDiagnosticMode )
      {
        v749 = L"OEM-mode installation does not support patching.";
LABEL_880:
        DebugString(9, 0, 0, v749, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_881;
      }
      goto LABEL_881;
    }
    if ( !v646 || !v614 )
    {
      if ( g_dmDiagnosticMode )
      {
        v749 = L"OEM-mode installation supports only per machine installations.";
        goto LABEL_880;
      }
      goto LABEL_881;
    }
    v750 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"ProductState");
    v751 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1052, v750);
    v752 = MsiString::operator int(v751);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1052);
    if ( v752 != -1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v749 = L"OEM-mode installation supports only first time installations.";
        goto LABEL_880;
      }
LABEL_881:
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v884);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
      goto LABEL_585;
    }
    if ( v862 || v726 != 2 )
    {
      if ( g_dmDiagnosticMode )
      {
        v749 = L"OEM-mode installation supports only UI-less installations.";
        goto LABEL_880;
      }
      goto LABEL_881;
    }
    v753 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"ACTION");
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v914, v753);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v914) )
    {
      v754 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v914);
      if ( (unsigned int)IStrComp(v754, L"INSTALL") )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"OEM-mode installation supports only INSTALL type of ACTION.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v914);
        goto LABEL_881;
      }
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"OEM-mode installation.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v914);
  }
  if ( !v853 )
    goto LABEL_888;
  if ( (a6 & 0x80u) != 0 )
  {
    v755 = 1;
LABEL_887:
    v759 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
    v760 = MsiString::MsiString((MsiString *)v1054, L"QFEUpgrade");
    v761 = CComPointer<IMsiStorage>::operator->(v760);
    v759(a1, v761, v755);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1054);
    goto LABEL_888;
  }
  v756 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"PATCH");
  v757 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1053, v756);
  v758 = MsiString::TextSize(v757);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v1053);
  if ( v758 )
  {
    v755 = 2;
    goto LABEL_887;
  }
LABEL_888:
  *(_DWORD *)(a1 + 64) = 1;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)(a1 + 152) + 208LL))(
         *(_QWORD *)(a1 + 152),
         L"CustomAction",
         2) )
  {
    *(_DWORD *)(a1 + 84) = 1;
  }
  *(_BYTE *)(a1 + 2192) = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(**(_QWORD **)(a1 + 152) + 208LL))(
         *(_QWORD *)(a1 + 152),
         L"Font",
         2) )
  {
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v915, 0);
    v762 = *(_QWORD *)(a1 + 152);
    v763 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v762 + 80LL);
    v764 = CComPointer<IEnumMsiRecord>::operator=(&v915);
    v765 = MsiString::MsiString((MsiString *)v1055, L"Font");
    v766 = CComPointer<IMsiStorage>::operator->(v765);
    v767 = v763(v762, v766, 0, v764);
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v1056, v767);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1055);
    if ( CComPointer<IMsiStorage>::operator->(&v915) )
    {
      v768 = CComPointer<IMsiStorage>::operator->(&v915);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v768 + 64LL))(v768) )
        *(_BYTE *)(a1 + 2192) = 1;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v1056);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v915);
  }
  if ( !*(_QWORD *)(a1 + 176) )
  {
    v769 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 128) + 48LL))(*(_QWORD *)(a1 + 128), 3);
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(&v874, v769);
    v770 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
    v771 = MsiString::MsiString((MsiString *)v1057, L"ProductLanguage");
    v772 = CComPointer<IMsiStorage>::operator->(v771);
    v773 = v770(a1, v772);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1057);
    if ( v773 == 0x80000000 )
      v773 = *(unsigned __int16 *)(a1 + 32);
    v774 = CComPointer<IMsiStorage>::operator->(&v874);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v774 + 104LL))(v774, 1);
    v775 = CComPointer<IMsiStorage>::operator->(&v874);
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v775 + 104LL))(v775, 2, v773);
    v776 = CComPointer<IMsiStorage>::operator->(&v874);
    v777 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v776 + 104LL);
    v778 = CComPointer<IMsiStorage>::operator->(&v822);
    v779 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v778 + 216LL))(v778);
    v777(v776, 3, v779);
    v780 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 24LL);
    v781 = CComPointer<IMsiStorage>::operator->(&v874);
    v780(a1, 184549376, v781);
    v782 = CComPointer<IMsiStorage>::operator->(&v874);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v782 + 96LL))(v782, 3);
    if ( *(_QWORD *)(a1 + 280) )
    {
      v783 = CComPointer<IMsiStorage>::operator->(&v874);
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v783 + 104LL))(v783, 1, 1);
      v784 = CComPointer<IMsiStorage>::operator->(&v874);
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v784 + 120LL))(v784, 2, *(_QWORD *)(a1 + 280));
      v785 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 24LL);
      v786 = CComPointer<IMsiStorage>::operator->(&v874);
      v785(a1, 184549376, v786);
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v874);
    if ( !*(_QWORD *)(a1 + 176) && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
    {
      if ( g_scServerContext == 2 )
      {
        if ( v726 - 2 <= 1 )
        {
          v787 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
          CMsiSQMSession::RecordInstallType(v787, (struct IMsiEngine *)a1);
        }
        v788 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        CMsiSQMSession::RecordDWORD(v788, 0xE28u, v614 != 0);
        v789 = v887;
        if ( !v887 || !*v887 )
          v789 = (unsigned __int16 *)MsiString::operator unsigned short const *(&v821);
        v790 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        CMsiSQMSession::UpdateInstallSourceType(v790, 0, v789, *(struct IMsiServices **)(a1 + 128));
      }
      else if ( !g_scServerContext )
      {
        v791 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        CMsiSQMSession::RecordInstallType(v791, (struct IMsiEngine *)a1);
      }
    }
  }
  v11 = CMsiEngine::ProcessPreselectedAndResumeInfo(a1);
  if ( v11 )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v884);
LABEL_913:
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
    goto LABEL_321;
  }
  if ( g_scServerContext == 2 )
  {
    *(_BYTE *)(a1 + 607) = 1;
    if ( (unsigned int)IsTerminalServerInstalled() && v614 )
      *(_BYTE *)(a1 + 607) = 0;
    v792 = GetCustomActionManager(0);
    if ( v792 )
      CMsiCustomActionManager::EnsureHKCUKeyMappingState(v792, *(_BYTE *)(a1 + 607));
    else
      CreateCustomActionManager(*(_BYTE *)(a1 + 607));
  }
  MsiSuppressTimeout();
  CMsiEngine::ApplyAppCompatProperties((CMsiEngine *)a1);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v884);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v860);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v861);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v863);
  CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v825);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v823);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v819);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v828);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v822);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v839);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v841);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v840);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v856);
  return 0;
}

```

## disassembly

```asm
0x1800f94d0  push    rbp
0x1800f94d2  push    rbx
0x1800f94d3  push    rsi
0x1800f94d4  push    rdi
0x1800f94d5  push    r12
0x1800f94d7  push    r13
0x1800f94d9  push    r14
0x1800f94db  push    r15
0x1800f94dd  lea     rbp, [rsp-8E8h]
0x1800f94e5  sub     rsp, 9E8h
0x1800f94ec  mov     rax, cs:__security_cookie
0x1800f94f3  xor     rax, rsp
0x1800f94f6  mov     [rbp+920h+var_50], rax
0x1800f94fd  mov     rax, [rbp+920h+arg_20]
0x1800f9504  mov     r12, rcx
0x1800f9507  mov     r14, [rbp+920h+arg_30]
0x1800f950e  xor     ecx, ecx
0x1800f9510  mov     [rbp+920h+var_6C0], rax
0x1800f9517  mov     rsi, r9
0x1800f951a  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f9521  mov     [rbp+920h+var_810], r9
0x1800f9528  mov     [rbp+920h+var_960], rax
0x1800f952c  mov     rdi, rdx
0x1800f952f  lea     r13d, [rcx+5]
0x1800f9533  mov     [rbp+920h+var_970], rax
0x1800f9537  mov     [rbp+920h+var_948], rax
0x1800f953b  mov     r15d, ecx
0x1800f953e  mov     [rbp+920h+var_920], rax
0x1800f9542  mov     [rbp+920h+var_938], rax
0x1800f9546  mov     [rsp+0A20h+var_9A8], rax
0x1800f954b  mov     [rbp+920h+var_950], rax
0x1800f954f  mov     [rbp+920h+var_940], rax
0x1800f9553  mov     [rbp+920h+var_930], rax
0x1800f9557  mov     [rbp+920h+var_918], rax
0x1800f955b  mov     [rbp+920h+var_958], rax
0x1800f955f  mov     [rbp+920h+var_908], rax
0x1800f9563  mov     [rbp+920h+var_900], rax
0x1800f9567  mov     [rbp+920h+var_928], rax
0x1800f956b  mov     [rbp+920h+var_910], rax
0x1800f956f  lea     eax, [rcx+2]
0x1800f9572  mov     [rbp+920h+var_7C8], rdx
0x1800f9579  mov     [rbp+920h+var_8D0], r8d
0x1800f957d  mov     [rbp+920h+var_7F0], r14
0x1800f9584  mov     [rbp+920h+var_88C], ecx
0x1800f958a  mov     [rbp+920h+var_898], rcx
0x1800f9591  cmp     r8d, r13d
0x1800f9594  jnz     short loc_1800F95A4
0x1800f9596  lea     ebx, [rcx+1]
0x1800f9599  mov     [rbp+920h+var_8D0], ecx
0x1800f959c  mov     [rbp+920h+var_878], ebx
0x1800f95a2  jmp     short loc_1800F95BD
0x1800f95a4  mov     [rbp+920h+var_878], ecx
0x1800f95aa  mov     ebx, ecx
0x1800f95ac  cmp     r8d, 4
0x1800f95b0  ja      short loc_1800F95BA
0x1800f95b2  cmp     r8d, 3
0x1800f95b6  jz      short loc_1800F9626
0x1800f95b8  jmp     short loc_1800F95BD
0x1800f95ba  mov     [rbp+920h+var_8D0], eax
0x1800f95bd  cmp     cs:?g_scServerContext@@3W4scEnum@@A, eax; scEnum g_scServerContext
0x1800f95c3  jz      short loc_1800F962E
0x1800f95c5  call    ?IsInteractiveWindowStation@@YA_NXZ; IsInteractiveWindowStation(void)
0x1800f95ca  xor     ecx, ecx
0x1800f95cc  test    al, al
0x1800f95ce  jnz     short loc_1800F9621
0x1800f95d0  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x1800f95d6  mov     [rbp+920h+var_8D0], 3
0x1800f95dd  jz      short loc_1800F9621
0x1800f95df  mov     [rsp+0A20h+var_9C8], rcx; void *
0x1800f95e4  lea     rax, aNull; "(NULL)"
0x1800f95eb  mov     [rsp+0A20h+var_9D0], ecx; unsigned int
0x1800f95ef  lea     r9, aCmsiengineDoin; "CMsiEngine::DoInitialize: UI level set "...
0x1800f95f6  mov     [rsp+0A20h+var_9D8], rax; unsigned __int16 *
0x1800f95fb  xor     edx, edx; unsigned __int16
0x1800f95fd  mov     [rsp+0A20h+var_9E0], rax; unsigned __int16 *
0x1800f9602  xor     r8d, r8d; int
0x1800f9605  mov     [rsp+0A20h+var_9E8], rax; unsigned __int16 *
0x1800f960a  mov     [rsp+0A20h+var_9F0], rax; unsigned __int16 *
0x1800f960f  mov     qword ptr [rsp+0A20h+cchCount2], rax; unsigned __int16 *
0x1800f9614  lea     ecx, [rdx+9]; int
0x1800f9617  mov     [rsp+0A20h+lpString2], rax; unsigned __int16 *
0x1800f961c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f9621  mov     eax, 2
0x1800f9626  cmp     cs:?g_scServerContext@@3W4scEnum@@A, eax; scEnum g_scServerContext
0x1800f962c  jnz     short loc_1800F9675
0x1800f962e  mov     rax, [r12]
0x1800f9632  mov     rcx, r12
0x1800f9635  mov     rax, [rax+8]
0x1800f9639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f963e  mov     edx, 0C100Eh; int
0x1800f9643  mov     rcx, r12; struct IUnknown *
0x1800f9646  call    ?CreateMsiHandle@@YAKPEAUIUnknown@@H@Z; CreateMsiHandle(IUnknown *,int)
0x1800f964b  mov     edx, eax
0x1800f964d  test    eax, eax
0x1800f964f  jz      short loc_1800F9675
0x1800f9651  mov     rcx, [r12]
0x1800f9655  mov     rax, [rcx+178h]
0x1800f965c  mov     rcx, r12
0x1800f965f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9664  mov     ecx, [r12+64h]
0x1800f9669  mov     rax, cs:?SetMSIHandleForLogging@FUSION@@3P6AJK@ZEA; long (*FUSION::SetMSIHandleForLogging)(ulong)
0x1800f9670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9675  mov     eax, [rbp+920h+arg_28]
0x1800f967b  xor     edx, edx
0x1800f967d  mov     [rbp+920h+var_998], rdx
0x1800f9681  mov     [rbp+920h+var_968], rdx
0x1800f9685  mov     [r12+248h], eax
0x1800f968d  test    [rbp+920h+arg_28], 800h
0x1800f9697  jz      short loc_1800F96A2
0x1800f9699  mov     byte ptr [r12+25Eh], 1
0x1800f96a2  mov     rcx, r12; this
0x1800f96a5  call    ?IgnoreMachineState@CMsiEngine@@IEAA_NXZ; CMsiEngine::IgnoreMachineState(void)
0x1800f96aa  xor     r8d, r8d; int
0x1800f96ad  mov     [rbp+920h+var_978], al
0x1800f96b0  cmp     cs:?g_dmDiagnosticMode@@3HA, r8d; int g_dmDiagnosticMode
0x1800f96b7  jz      short loc_1800F9717
0x1800f96b9  test    byte ptr [r12+248h], 8
0x1800f96c2  lea     rax, aNot_1; " not"
0x1800f96c9  mov     [rsp+0A20h+var_9C8], r8; void *
0x1800f96ce  lea     rcx, Default
0x1800f96d5  mov     [rsp+0A20h+var_9D0], r8d; unsigned int
0x1800f96da  lea     r9, aEndDialogSEnab; "End dialog%s enabled"
0x1800f96e1  cmovz   rcx, rax
0x1800f96e5  lea     rax, aNull; "(NULL)"
0x1800f96ec  mov     [rsp+0A20h+var_9D8], rax; unsigned __int16 *
0x1800f96f1  xor     edx, edx; unsigned __int16
0x1800f96f3  mov     [rsp+0A20h+var_9E0], rax; unsigned __int16 *
0x1800f96f8  mov     [rsp+0A20h+var_9E8], rax; unsigned __int16 *
0x1800f96fd  mov     [rsp+0A20h+var_9F0], rax; unsigned __int16 *
0x1800f9702  mov     qword ptr [rsp+0A20h+cchCount2], rax; unsigned __int16 *
0x1800f9707  mov     [rsp+0A20h+lpString2], rcx; unsigned __int16 *
0x1800f970c  lea     ecx, [rdx+9]; int
0x1800f970f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800f9714  xor     r8d, r8d
0x1800f9717  inc     dword ptr cs:qword_180309704
0x1800f971d  test    ebx, ebx
0x1800f971f  jnz     loc_1800F99BB
0x1800f9725  mov     rcx, [r12+0A8h]
0x1800f972d  test    rcx, rcx
0x1800f9730  jz      loc_1800F98C1
0x1800f9736  mov     rax, [rcx]
0x1800f9739  lea     edx, [rbx+1]
0x1800f973c  mov     rax, [rax+0A8h]
0x1800f9743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9748  mov     rdx, rax
0x1800f974b  lea     rcx, [rbp+920h+var_968]
0x1800f974f  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800f9754  xor     r13d, r13d
0x1800f9757  mov     rcx, [rbp+920h+var_930]; this
0x1800f975b  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f9760  lea     r8, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f9767  lea     rdx, aCurrentdirecto_0; "CURRENTDIRECTORY"
0x1800f976e  mov     [rbp+920h+var_930], r8
0x1800f9772  lea     rcx, [rbp+920h+var_698]; this
0x1800f9779  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1800f977e  mov     rcx, [rbp+920h+var_938]; this
0x1800f9782  mov     rbx, [rax]
0x1800f9785  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f978a  mov     rcx, [rbp+920h+var_920]; this
0x1800f978e  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f9795  mov     [rbp+920h+var_938], rax
0x1800f9799  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f979e  mov     rcx, [rbp+920h+var_948]; this
0x1800f97a2  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f97a9  mov     [rbp+920h+var_920], rax
0x1800f97ad  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f97b2  mov     rcx, [rbp+920h+var_970]; this
0x1800f97b6  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f97bd  mov     [rbp+920h+var_948], rax
0x1800f97c1  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f97c6  mov     rcx, [rbp+920h+var_960]; this
0x1800f97ca  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f97d1  mov     [rbp+920h+var_970], rax
0x1800f97d5  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f97da  mov     byte ptr [rsp+0A20h+var_9C0], r13b
0x1800f97df  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f97e6  mov     [rsp+0A20h+var_9C8], r13
0x1800f97eb  lea     r9, [rbp+920h+var_948]
0x1800f97ef  mov     [rbp+920h+var_960], rax
0x1800f97f3  lea     r8, [rbp+920h+var_970]
0x1800f97f7  lea     rax, [r12+1C0h]
0x1800f97ff  mov     rcx, rsi
0x1800f9802  mov     qword ptr [rsp+0A20h+var_9D0], rax
0x1800f9807  lea     rdx, [rbp+920h+var_960]
0x1800f980b  mov     dword ptr [rsp+0A20h+var_9D8], 1
0x1800f9813  lea     rax, [rbp+920h+var_930]
0x1800f9817  mov     [rsp+0A20h+var_9E0], rax
0x1800f981c  lea     rax, [rbp+920h+var_938]
0x1800f9820  mov     [rsp+0A20h+var_9E8], rbx
0x1800f9825  mov     [rsp+0A20h+var_9F0], r13
0x1800f982a  mov     qword ptr [rsp+0A20h+cchCount2], rax
0x1800f982f  lea     rax, [rbp+920h+var_920]
0x1800f9833  mov     [rsp+0A20h+lpString2], rax
0x1800f9838  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x1800f983d  mov     rcx, [rbp+920h+var_698]; this
0x1800f9844  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1800f9849  lea     rcx, [rbp+920h+var_960]
0x1800f984d  call    ??BMsiString@@QEBAHXZ; MsiString::operator int(void)
0x1800f9852  test    eax, eax
0x1800f9854  jnz     short loc_1800F9866
0x1800f9856  lea     rdx, Default
0x1800f985d  lea     rcx, [rbp+920h+var_960]
0x1800f9861  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1800f9866  lea     rcx, [rbp+920h+var_938]
0x1800f986a  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x1800f986f  or      ecx, 0FFFFFFFFh
0x1800f9872  mov     r8, rax; lpString1
0x1800f9875  mov     [rsp+0A20h+cchCount2], ecx; cchCount2
0x1800f9879  lea     rax, aAdmin; "ADMIN"
0x1800f9880  mov     r9d, ecx; cchCount1
0x1800f9883  mov     [rsp+0A20h+lpString2], rax; lpString2
0x1800f9888  lea     ebx, [rcx+2]
0x1800f988b  mov     ecx, 409h; Locale
0x1800f9890  mov     edx, ebx; dwCmpFlags
0x1800f9892  call    cs:__imp_CompareStringW
0x1800f9898  cmp     eax, 2
0x1800f989b  jnz     loc_1800F9978
0x1800f98a1  mov     edx, ebx
0x1800f98a3  mov     rax, [r12]
0x1800f98a7  mov     r8d, ebx
0x1800f98aa  mov     rcx, r12
0x1800f98ad  mov     rax, [rax+68h]
0x1800f98b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f98b6  mov     ebx, [rbp+920h+var_878]
0x1800f98bc  jmp     loc_1800F99BE
0x1800f98c1  mov     rcx, [r12+0A0h]
0x1800f98c9  test    rcx, rcx
0x1800f98cc  jz      short loc_1800F98E7
0x1800f98ce  mov     rax, [rcx]
0x1800f98d1  mov     rax, [rax+8]
0x1800f98d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f98da  mov     rdx, [r12+0A0h]
0x1800f98e2  jmp     loc_1800F974B
0x1800f98e7  test    rdi, rdi
0x1800f98ea  jz      loc_1800F9754
0x1800f98f0  cmp     [rdi], r8w
0x1800f98f4  jz      loc_1800F9754
0x1800f98fa  mov     rdi, [r12+80h]
0x1800f9902  lea     rcx, [rbp+920h+var_968]
0x1800f9906  mov     rax, [rdi]
0x1800f9909  mov     rbx, [rax+0E0h]
0x1800f9910  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800f9915  mov     rdx, [rbp+920h+var_7C8]
0x1800f991c  mov     r9, rax
0x1800f991f  mov     rax, rbx
0x1800f9922  xor     r8d, r8d
0x1800f9925  mov     rcx, rdi
0x1800f9928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f992d  mov     rdx, rax
0x1800f9930  lea     rcx, [rbp+920h+var_898]
0x1800f9937  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800f993c  cmp     [rax], r15
0x1800f993f  jnz     loc_1800FB462
0x1800f9945  mov     rcx, [rbp+920h+var_968]
0x1800f9949  xor     edx, edx
0x1800f994b  mov     rax, [rcx]
0x1800f994e  mov     rax, [rax+0A8h]
0x1800f9955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f995a  xor     r13d, r13d
0x1800f995d  test    al, al
0x1800f995f  jnz     short loc_1800F996C
0x1800f9961  mov     r13d, 6
0x1800f9967  jmp     loc_1800FB462
0x1800f996c  mov     rdi, [rbp+920h+var_7C8]
0x1800f9973  jmp     loc_1800F9757
0x1800f9978  lea     rcx, [rbp+920h+var_938]
0x1800f997c  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x1800f9981  or      ecx, 0FFFFFFFFh
0x1800f9984  mov     r8, rax; lpString1
0x1800f9987  mov     [rsp+0A20h+cchCount2], ecx; cchCount2
0x1800f998b  lea     rax, aAdvertise_0; "ADVERTISE"
0x1800f9992  mov     r9d, ecx; cchCount1
0x1800f9995  mov     [rsp+0A20h+lpString2], rax; lpString2
0x1800f999a  mov     ecx, 409h; Locale
0x1800f999f  mov     edx, ebx; dwCmpFlags
0x1800f99a1  call    cs:__imp_CompareStringW
0x1800f99a7  mov     ecx, 2
0x1800f99ac  cmp     eax, ecx
0x1800f99ae  jnz     loc_1800F98B6
0x1800f99b4  mov     edx, ecx
0x1800f99b6  jmp     loc_1800F98A3
0x1800f99bb  xor     r13d, r13d
0x1800f99be  mov     rdx, rdi; unsigned __int16 *
0x1800f99c1  mov     [rbp+920h+var_8C4], 0FFFFFFFFh
0x1800f99c8  lea     rcx, [rsp+0A20h+var_9B0]; this
0x1800f99cd  mov     [rbp+920h+var_8E7], r13b
0x1800f99d1  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1800f99d6  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800f99dd  lea     rcx, [r12+208h]
0x1800f99e5  mov     [rbp+920h+var_9A0], rax
0x1800f99e9  lea     rdx, [rsp+0A20h+var_9B0]
0x1800f99ee  call    ??4MsiString@@QEAAAEAV0@AEBV0@@Z; MsiString::operator=(MsiString const &)
0x1800f99f3  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1800f99fa  jz      short loc_1800F9A49
0x1800f99fc  lea     rcx, [rsp+0A20h+var_9B0]
0x1800f9a01  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x1800f9a06  lea     rcx, aNull; "(NULL)"
0x1800f9a0d  mov     [rsp+0A20h+var_9C8], r13; void *
0x1800f9a12  mov     [rsp+0A20h+var_9D0], r13d; unsigned int
0x1800f9a17  lea     r9, aOriginalPackag; "Original package ==> %s"
  ... truncated ...
```
