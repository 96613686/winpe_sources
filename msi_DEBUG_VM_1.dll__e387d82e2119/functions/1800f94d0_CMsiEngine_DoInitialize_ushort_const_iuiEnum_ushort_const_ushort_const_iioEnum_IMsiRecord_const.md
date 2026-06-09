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
  void *v103; // rax
  char v104; // di
  unsigned int v105; // eax
  struct IMsiRecord **v106; // rcx
  void *v107; // rax
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
  unsigned int v118; // eax
  char v119; // al
  MsiString *v120; // rax
  unsigned __int16 *v121; // rsi
  bool v122; // bl
  unsigned int PatchMetaDataForNewObsoletedAndSupercededMSPs; // ebx
  __int64 v124; // rax
  GUIDAndSequence *v125; // rcx
  __int64 v126; // rbx
  MsiString *v127; // rax
  __int64 v128; // rax
  char v129; // si
  __int64 v130; // rax
  __int64 v131; // r9
  __int64 v132; // rax
  char v133; // bl
  __int64 v134; // rax
  __int64 v135; // r8
  unsigned int v136; // edi
  __int64 v137; // rax
  __int64 v138; // r9
  unsigned int v139; // ebx
  __int64 v140; // rax
  __int64 v141; // rbx
  MsiString *v142; // rax
  __int64 v143; // rax
  const unsigned __int16 *v144; // rax
  CMsiPatchManager *v145; // rbx
  struct IMsiDatabase *v146; // rax
  CMsiPatchManager *v147; // rax
  __int16 v148; // ax
  __int64 v149; // rbx
  unsigned __int16 v150; // ax
  struct IMsiRecord *Record; // rax
  __int64 v152; // rax
  __int64 v153; // rdi
  void (__fastcall *v154)(__int64, __int64, _QWORD); // rbx
  unsigned __int16 v155; // ax
  __int64 v156; // rdi
  void (__fastcall *v157)(__int64, __int64, _QWORD); // rbx
  __int64 v158; // rax
  unsigned int v159; // eax
  __int64 v160; // rax
  __int64 v161; // rsi
  __int64 v162; // rbx
  bool v163; // di
  __int64 v164; // r14
  __int64 v165; // rax
  unsigned int v166; // eax
  __int64 v167; // r15
  __int64 v168; // rax
  unsigned int v169; // esi
  unsigned int v170; // r14d
  __int64 v171; // rdi
  __int64 v172; // rbx
  __int64 v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // rax
  int v177; // eax
  bool v178; // di
  __int64 v179; // rsi
  __int64 v180; // rbx
  __int64 v181; // rax
  const unsigned __int16 *v182; // rax
  __int64 v183; // rax
  _WORD *v184; // rax
  void (__fastcall *v185)(__int64, __int64, __int64); // rdi
  const unsigned __int16 *v186; // rax
  MsiString *v187; // rax
  __int64 v188; // rbx
  MsiString *v189; // rax
  __int64 v190; // rax
  GUIDAndSequence *v191; // rcx
  MsiString *v192; // rax
  __int64 v193; // rbx
  MsiString *v194; // rax
  __int64 v195; // rax
  struct IMsiDatabase *v196; // rax
  void (__fastcall *v197)(__int64, __int64, __int64); // rdi
  __int64 v198; // rbx
  MsiString *v199; // rax
  __int64 v200; // rax
  IMsiData *v201; // rbx
  void (__fastcall *v202)(__int64, __int64, IMsiData *); // rdi
  MsiString *v203; // rax
  __int64 v204; // rax
  IMsiData *v205; // rbx
  void (__fastcall *v206)(__int64, __int64, IMsiData *); // rdi
  MsiString *v207; // rax
  __int64 v208; // rax
  struct IUnknown v209; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  MsiString *v211; // rax
  __int64 v212; // rax
  void (__fastcall *v213)(__int64, __int64, void ***); // rbx
  MsiString *v214; // rax
  __int64 v215; // rax
  GUIDAndSequence *v216; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v218; // rax
  __int64 v219; // rax
  void (__fastcall *v220)(__int64, __int64, __int64); // rbx
  MsiString *v221; // rax
  __int64 v222; // rax
  __int64 v223; // rax
  const unsigned __int16 *v224; // rax
  const unsigned __int16 *v225; // rax
  const unsigned __int16 *v226; // rax
  const unsigned __int16 *v227; // rax
  __int64 v228; // rax
  __int64 v229; // rax
  void (__fastcall *v230)(__int64, __int64, __int64); // rdi
  __int64 v231; // rbx
  MsiString *v232; // rax
  __int64 v233; // rax
  void (__fastcall *v234)(__int64, __int64, __int64); // rdi
  __int64 v235; // rbx
  MsiString *v236; // rax
  __int64 v237; // rax
  const unsigned __int16 *v238; // rax
  __int64 v239; // rax
  const unsigned __int16 *v240; // rax
  __int64 v241; // rax
  const unsigned __int16 *v242; // r9
  __int64 (__fastcall *v243)(__int64, __int64); // rbx
  MsiString *v244; // rax
  __int64 v245; // rax
  int v246; // edi
  unsigned int v247; // ebx
  CMsiSQMSession *SQMSession; // rax
  CMsiSQMSession *v249; // rbx
  unsigned int IntegerPolicyValue; // eax
  CMsiSQMSession *v251; // rbx
  unsigned int v252; // eax
  const OLECHAR *v253; // rax
  unsigned int v254; // ebx
  const unsigned __int16 *v255; // rax
  CMsiSQMSession *v256; // rax
  const WCHAR *v257; // rax
  const WCHAR *v258; // rax
  const unsigned __int16 *v259; // rax
  MsiString *v260; // rax
  int v261; // ebx
  BOOL v262; // edi
  const unsigned __int16 *v263; // rcx
  const WCHAR *v264; // rax
  const WCHAR *v265; // rax
  const unsigned __int16 *v266; // rax
  int v267; // eax
  struct IUnknown v268; // rax
  HRESULT (__stdcall *v269)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v270; // rax
  __int64 v271; // rax
  void (__fastcall *v272)(__int64, __int64, __int64); // rbx
  MsiString *v273; // rax
  __int64 v274; // rax
  __int64 v275; // r14
  MsiString *v276; // rax
  __int64 v277; // rax
  unsigned int v278; // ebx
  CMsiSQMSession *v279; // rax
  IMsiData *v280; // rdi
  void (__fastcall *v281)(__int64, __int64, IMsiData *); // rbx
  MsiString *v282; // rax
  __int64 v283; // rax
  MsiString *v284; // rax
  __int64 v285; // rax
  IMsiData *v286; // rdi
  void (__fastcall *v287)(__int64, __int64, IMsiData *); // rbx
  MsiString *v288; // rax
  __int64 v289; // rax
  _QWORD *v290; // rdi
  __int64 (__fastcall *v291)(__int64, __int64); // rbx
  MsiString *v292; // rax
  __int64 v293; // rax
  struct IUnknown v294; // rax
  HRESULT (__stdcall *v295)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v296; // rax
  __int64 v297; // rax
  struct IUnknown v298; // rax
  ULONG (__stdcall *v299)(IUnknown *); // rdi
  MsiString *v300; // rax
  __int64 v301; // rbx
  MsiString *v302; // rax
  __int64 v303; // rax
  GUIDAndSequence *v304; // rbx
  char v305; // al
  struct IUnknown v306; // rbx
  ULONG (__stdcall *v307)(IUnknown *); // rdi
  MsiString *v308; // rax
  __int64 v309; // rbx
  MsiString *v310; // rax
  __int64 v311; // rax
  HRESULT (__stdcall *v312)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v313; // rax
  __int64 v314; // rax
  __int64 v315; // rax
  MsiString *v316; // rax
  void (__fastcall *v317)(__int64, __int64, __int64); // rbx
  MsiString *v318; // rax
  __int64 v319; // rax
  void (__fastcall *v320)(__int64, __int64, __int64); // rdi
  MsiString *v321; // rax
  __int64 v322; // rbx
  MsiString *v323; // rax
  __int64 v324; // rax
  __int64 (__fastcall *v325)(__int64, __int64); // rbx
  MsiString *v326; // rax
  __int64 v327; // rax
  void (__fastcall *v328)(__int64, __int64, __int64); // rdi
  MsiString *v329; // rax
  __int64 v330; // rbx
  MsiString *v331; // rax
  __int64 v332; // rax
  char v333; // di
  __int64 v334; // rcx
  char v335; // al
  const unsigned __int16 *v336; // rcx
  const unsigned __int16 *v337; // rax
  const unsigned __int16 *v338; // rax
  const struct IMsiString *PackedGUID; // rax
  const unsigned __int16 *v340; // rax
  int v341; // eax
  bool v342; // r14
  char v343; // al
  unsigned int v344; // esi
  char v345; // di
  __int64 v346; // rbx
  __int64 v347; // rax
  int v348; // eax
  unsigned int v349; // ebx
  struct CMsiSQMSession *v350; // rax
  __int64 v351; // rax
  GUIDAndSequence *v352; // rcx
  void (__fastcall *v353)(__int64, __int64, _QWORD); // rbx
  MsiString *v354; // rax
  __int64 v355; // rax
  void (__fastcall *v356)(__int64, __int64, __int64); // rbx
  MsiString *v357; // rax
  __int64 v358; // rax
  IMsiData *v359; // rcx
  IMsiData *v360; // rax
  __int64 v361; // rax
  __int64 v362; // rbx
  MsiString *v363; // rax
  __int64 v364; // rax
  __int64 v365; // rax
  __int64 v366; // r14
  __int64 (__fastcall *v367)(__int64, __int64, __int64, __int64); // rsi
  __int64 v368; // rdi
  __int64 v369; // rbx
  __int64 v370; // rax
  __int64 v371; // rax
  __int64 v372; // rax
  __int64 v373; // rbx
  __int64 v374; // rax
  __int64 v375; // r9
  __int64 v376; // rax
  __int64 v377; // rax
  __int64 v378; // rax
  __int64 v379; // rbx
  __int64 v380; // rax
  __int64 v381; // rdx
  struct CMsiSQMSession *v382; // rax
  __int64 v383; // rax
  __int64 v384; // rax
  const WCHAR *v385; // rax
  __int64 v386; // rax
  void (__fastcall *v387)(__int64, __int64, __int64); // rbx
  MsiString *v388; // rax
  __int64 v389; // rax
  __int64 v390; // rax
  MsiString *v391; // rax
  char v392; // bl
  __int64 v393; // rax
  int v394; // eax
  IMsiData **v395; // rdx
  const WCHAR *v396; // rax
  __int64 v397; // rax
  const unsigned __int16 *v398; // rax
  __int64 v399; // r14
  __int64 (__fastcall *v400)(__int64, __int64, __int64, __int64); // rsi
  __int64 v401; // rdi
  __int64 v402; // rbx
  __int64 v403; // rax
  __int64 v404; // rax
  __int64 v405; // rax
  __int64 v406; // rbx
  __int64 v407; // rax
  const unsigned __int16 *v408; // rax
  __int64 v409; // rax
  const WCHAR *v410; // rax
  __int64 v411; // rax
  const unsigned __int16 *v412; // rax
  const struct IMsiString **v413; // rbx
  const unsigned __int16 *v414; // rax
  struct IMsiRecord *v415; // rax
  __int64 v416; // rax
  __int64 v417; // rbx
  __int64 v418; // rax
  void (__fastcall *v419)(__int64, __int64, __int64); // rdi
  __int64 v420; // rbx
  MsiString *v421; // rax
  __int64 v422; // rax
  void (__fastcall *v423)(__int64, __int64, __int64); // rbx
  MsiString *v424; // rax
  __int64 v425; // rax
  __int64 v426; // rax
  __int64 v427; // rdi
  __int64 (__fastcall *v428)(__int64, const unsigned __int16 *, _QWORD, __int64); // rbx
  __int64 v429; // rax
  __int64 v430; // rax
  __int64 v431; // rax
  unsigned int v432; // esi
  struct IMsiRecord *v433; // rax
  __int64 v434; // rax
  __int64 v435; // rdi
  void (__fastcall *v436)(__int64, __int64, _QWORD); // rbx
  __int64 v437; // rax
  __int64 v438; // rax
  char v439; // al
  char v440; // si
  char v441; // r14
  bool v442; // di
  bool v443; // bl
  __int64 v444; // rax
  __int64 v445; // r9
  __int64 v446; // r8
  __int64 v447; // rdx
  int v448; // eax
  int v449; // eax
  MsiString *v450; // rax
  __int64 v451; // rax
  unsigned __int16 *v452; // r14
  __int64 v453; // rsi
  const unsigned __int16 *v454; // rax
  struct IMsiPath **v455; // rbx
  const struct IMsiString *v456; // rax
  struct IMsiRecord *PathObject; // rax
  __int64 v458; // rax
  __int64 v459; // rax
  __int64 v460; // rax
  __int64 v461; // rax
  __int64 v462; // rsi
  __int64 (__fastcall *v463)(__int64, __int64, __int64); // rdi
  __int64 v464; // rbx
  __int64 v465; // rax
  __int64 v466; // rax
  __int64 v467; // rax
  __int64 v468; // rax
  __int64 v469; // rax
  __int64 v470; // rax
  __int64 v471; // rbx
  __int64 v472; // rdi
  __int64 (__fastcall *v473)(__int64, __int64); // rbx
  MsiString *v474; // rax
  __int64 v475; // rax
  __int64 v476; // rax
  __int64 v477; // rax
  __int64 v478; // rbx
  __int64 v479; // rax
  __int64 v480; // rax
  __int64 v481; // rbx
  __int64 v482; // rax
  __int64 v483; // rax
  __int64 v484; // rax
  __int64 v485; // rax
  const unsigned __int16 *v486; // rax
  const unsigned __int16 *v487; // r9
  bool v488; // bl
  __int64 v489; // rax
  MsiString *v490; // rax
  void (__fastcall *v491)(__int64, __int64, __int64); // rbx
  MsiString *v492; // rax
  __int64 v493; // rax
  unsigned int v494; // ebx
  char v495; // di
  CRestartManagerWrapper *Instance; // rsi
  unsigned int v497; // eax
  const unsigned __int16 *v498; // rax
  __int64 v499; // rax
  int v500; // r14d
  MsiString *v501; // rax
  __int64 v502; // rax
  CMsiSQMSession *v503; // rax
  unsigned int v504; // r8d
  int Disable; // eax
  CMsiSQMSession *v506; // rax
  unsigned int started; // eax
  void (__fastcall *v508)(__int64, __int64, __int64); // rdi
  const unsigned __int16 *v509; // rax
  MsiString *v510; // rax
  __int64 v511; // rbx
  MsiString *v512; // rax
  __int64 v513; // rax
  int v514; // eax
  __int64 v515; // rax
  __int64 v516; // rax
  __int64 v517; // rax
  __int64 v518; // rax
  __int64 v519; // rax
  __int64 v520; // rax
  __int64 v521; // rax
  __int64 v522; // rax
  __int64 v523; // rdi
  __int64 (__fastcall *v524)(__int64, const WCHAR *, __int64); // rbx
  __int64 v525; // rax
  __int64 v526; // rax
  __int64 v527; // rax
  unsigned int v528; // r14d
  void (__fastcall *v529)(__int64, __int64, __int64); // rbx
  MsiString *v530; // rax
  __int64 v531; // rax
  __int64 v532; // rax
  MsiString *v533; // rax
  int v534; // ebx
  __int64 v535; // rax
  MsiString *v536; // rax
  char v537; // bl
  const unsigned __int16 *v538; // rax
  struct IUnknown v539; // rdi
  HRESULT (__stdcall *v540)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v541; // rax
  __int64 v542; // rax
  GUIDAndSequence *v543; // rcx
  ULONG (__stdcall *v544)(IUnknown *); // rdi
  MsiString *v545; // rax
  __int64 v546; // rbx
  MsiString *v547; // rax
  __int64 v548; // rax
  char v549; // si
  struct IUnknown v550; // rdi
  HRESULT (__stdcall *v551)(IUnknown *, const IID *const, void **); // rbx
  MsiString *v552; // rax
  __int64 v553; // rax
  GUIDAndSequence *v554; // rcx
  ULONG (__stdcall *v555)(IUnknown *); // rdi
  MsiString *v556; // rax
  __int64 v557; // rbx
  MsiString *v558; // rax
  __int64 v559; // rax
  CMsiSQMSession *v560; // rax
  void (__fastcall *v561)(__int64, __int64, __int64); // rdi
  __int64 v562; // rbx
  MsiString *v563; // rax
  __int64 v564; // rax
  __int64 v565; // rax
  __int64 v566; // rax
  const unsigned __int16 *v567; // rax
  void (__fastcall *v568)(__int64, __int64, __int64); // rdi
  __int64 v569; // rbx
  MsiString *v570; // rax
  __int64 v571; // rax
  void (__fastcall *v572)(__int64, __int64, __int64); // rdi
  __int64 v573; // rax
  __int64 v574; // rax
  __int64 v575; // rbx
  MsiString *v576; // rax
  __int64 v577; // rax
  void (__fastcall *v578)(__int64, __int64, __int64); // rdi
  __int64 v579; // rax
  __int64 v580; // rax
  __int64 v581; // rbx
  MsiString *v582; // rax
  __int64 v583; // rax
  void (__fastcall *v584)(__int64, __int64, __int64); // rdi
  __int64 v585; // rbx
  MsiString *v586; // rax
  __int64 v587; // rax
  void (__fastcall *v588)(__int64, __int64, __int64); // rdi
  __int64 v589; // rbx
  MsiString *v590; // rax
  __int64 v591; // rax
  void (__fastcall *v592)(__int64, __int64, __int64); // rdi
  __int64 v593; // rbx
  MsiString *v594; // rax
  __int64 v595; // rax
  __int64 (__fastcall *v596)(__int64, __int64); // rbx
  MsiString *v597; // rax
  __int64 v598; // rax
  unsigned int v599; // ebx
  void (__fastcall *v600)(__int64, __int64, _QWORD); // rdi
  MsiString *v601; // rax
  __int64 v602; // rax
  struct IMsiDatabase *v603; // rax
  __int64 v604; // rsi
  __int64 (__fastcall *v605)(__int64, __int64, _QWORD, __int64, __int64); // rdi
  __int64 v606; // rbx
  __int64 v607; // rax
  __int64 v608; // rax
  __int64 v609; // rax
  __int64 v610; // r9
  unsigned int v611; // r14d
  __int64 v612; // rdi
  __int64 (__fastcall *v613)(__int64, __int64, __int64); // rbx
  __int64 v614; // rax
  __int64 v615; // rax
  __int64 v616; // rax
  int v617; // edi
  MsiString *v618; // rsi
  __int64 (__fastcall *v619)(__int64, __int64); // rbx
  __int64 v620; // rax
  __int64 v621; // rax
  __int64 (__fastcall *v622)(__int64, __int64); // rbx
  __int64 v623; // rax
  __int64 v624; // rax
  int v626; // edi
  __int64 (__fastcall *v627)(__int64, __int64); // rbx
  MsiString *v628; // rax
  __int64 v629; // rax
  int v630; // ebx
  void (__fastcall *v631)(__int64, __int64, __int64); // rbx
  MsiString *v632; // rax
  __int64 v633; // rax
  GUIDAndSequence *v634; // rcx
  void (__fastcall *v635)(__int64, __int64, __int64); // rbx
  MsiString *v636; // rax
  __int64 v637; // rax
  void (__fastcall *v638)(__int64, __int64, __int64); // rbx
  MsiString *v639; // rax
  __int64 v640; // rax
  __int64 v641; // rax
  MsiString *v642; // rax
  int v643; // esi
  void (__fastcall *v644)(__int64, __int64, __int64); // rbx
  MsiString *v645; // rax
  __int64 v646; // rax
  const struct IMsiString *v647; // rax
  IMsiData *v648; // rax
  void (__fastcall *v649)(__int64, __int64, __int64); // rdi
  const struct IMsiString *v650; // rax
  __int64 v651; // rax
  __int64 v652; // rbx
  MsiString *v653; // rax
  __int64 v654; // rax
  void (__fastcall *v655)(__int64, __int64, __int64); // rdi
  __int64 v656; // rbx
  MsiString *v657; // rax
  __int64 v658; // rax
  void (__fastcall *v659)(__int64, __int64, __int64); // rdi
  __int64 v660; // rbx
  MsiString *v661; // rax
  __int64 v662; // rax
  __int64 v663; // rax
  __int64 v664; // rax
  MsiString *v665; // rax
  __int64 v666; // rax
  MsiString *v667; // rax
  bool v668; // bl
  __int64 v669; // rdi
  unsigned int (__fastcall *v670)(__int64, __int64); // rbx
  MsiString *v671; // rax
  __int64 v672; // rax
  bool v673; // di
  unsigned int (__fastcall *v674)(__int64, __int64); // rbx
  MsiString *v675; // rax
  __int64 v676; // rax
  bool v677; // bl
  unsigned int (__fastcall *v678)(__int64, __int64); // rbx
  MsiString *v679; // rax
  __int64 v680; // rax
  unsigned int (__fastcall *v681)(__int64, __int64); // rbx
  MsiString *v682; // rax
  __int64 v683; // rax
  char v684; // bl
  int v685; // ebx
  int v686; // eax
  void (__fastcall *v687)(__int64, __int64, _QWORD); // rbx
  unsigned int v688; // eax
  CMsiEmbeddedUIManager *v689; // rbx
  struct IMsiDatabase *v690; // rax
  struct CMsiCustomActionManager *CustomActionManager; // rax
  unsigned int v692; // eax
  bool v693; // bl
  struct IMsiRecord *v694; // rax
  __int64 v695; // rax
  __int64 v696; // rax
  __int64 v697; // rax
  unsigned int v698; // eax
  __int64 v699; // rax
  __int64 v700; // rax
  __int64 v701; // rcx
  void (__fastcall *v702)(__int64, __int64, __int64); // rbx
  MsiString *v703; // rax
  __int64 v704; // rax
  void (__fastcall *v705)(__int64, __int64, _QWORD); // rdi
  MsiString *v706; // rax
  __int64 v707; // rax
  __int64 v708; // rax
  void (__fastcall *v709)(__int64, __int64, bool); // rbx
  int v710; // eax
  int v711; // eax
  __int64 (__fastcall *v712)(__int64, __int64); // rbx
  MsiString *v713; // rax
  __int64 v714; // rax
  int v715; // ebx
  __int64 v716; // rax
  MsiString *v717; // rax
  __int64 v718; // rax
  MsiString *v719; // rax
  bool v720; // di
  int v721; // ebx
  int v722; // ebx
  unsigned int v723; // r15d
  void (__fastcall *v724)(__int64, __int64, _QWORD); // rbx
  MsiString *v725; // rax
  __int64 v726; // rax
  unsigned int v727; // eax
  void (__fastcall *v728)(__int64, __int64, __int64); // rbx
  MsiString *v729; // rax
  __int64 v730; // rax
  void (__fastcall *v731)(__int64, __int64, __int64); // rbx
  MsiString *v732; // rax
  __int64 v733; // rax
  void (__fastcall *v734)(__int64, __int64, __int64); // rbx
  MsiString *v735; // rax
  __int64 v736; // rax
  void (__fastcall *v737)(__int64, __int64, __int64); // rbx
  MsiString *v738; // rax
  __int64 v739; // rax
  __int64 v740; // rax
  MsiString *v741; // rax
  int v742; // ebx
  __int64 v743; // rax
  MsiString *v744; // rax
  int v745; // ebx
  const unsigned __int16 *v746; // r9
  __int64 v747; // rax
  __int64 v748; // rax
  int v749; // ebx
  __int64 v750; // rax
  const unsigned __int16 *v751; // rax
  unsigned int v752; // edi
  __int64 v753; // rax
  MsiString *v754; // rax
  int v755; // ebx
  void (__fastcall *v756)(__int64, __int64, _QWORD); // rbx
  MsiString *v757; // rax
  __int64 v758; // rax
  __int64 v759; // rsi
  __int64 (__fastcall *v760)(__int64, __int64, _QWORD, __int64); // rdi
  __int64 v761; // rbx
  MsiString *v762; // rax
  __int64 v763; // rax
  __int64 v764; // rax
  __int64 v765; // rax
  __int64 v766; // rax
  __int64 (__fastcall *v767)(__int64, __int64); // rbx
  MsiString *v768; // rax
  __int64 v769; // rax
  unsigned int v770; // ebx
  __int64 v771; // rax
  __int64 v772; // rax
  __int64 v773; // rdi
  void (__fastcall *v774)(__int64, __int64, _QWORD); // rbx
  __int64 v775; // rax
  unsigned int v776; // eax
  void (__fastcall *v777)(__int64, __int64, __int64); // rbx
  __int64 v778; // rax
  __int64 v779; // rax
  __int64 v780; // rax
  __int64 v781; // rax
  void (__fastcall *v782)(__int64, __int64, __int64); // rbx
  __int64 v783; // rax
  CMsiSQMSession *v784; // rax
  CMsiSQMSession *v785; // rax
  unsigned __int16 *v786; // rbx
  CMsiSQMSession *v787; // rax
  CMsiSQMSession *v788; // rax
  CMsiCustomActionManager *v789; // rax
  int lpString2; // [rsp+20h] [rbp-E0h]
  unsigned int lpString2a; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  int cchCount2b[2]; // [rsp+28h] [rbp-D8h]
  int cchCount2a; // [rsp+28h] [rbp-D8h]
  char *v795; // [rsp+30h] [rbp-D0h]
  int v796; // [rsp+30h] [rbp-D0h]
  int v797; // [rsp+38h] [rbp-C8h]
  int v798; // [rsp+38h] [rbp-C8h]
  int v799; // [rsp+40h] [rbp-C0h]
  int v800; // [rsp+40h] [rbp-C0h]
  int v801; // [rsp+48h] [rbp-B8h]
  int v802; // [rsp+48h] [rbp-B8h]
  int v803; // [rsp+50h] [rbp-B0h]
  int v804; // [rsp+60h] [rbp-A0h]
  int v805; // [rsp+60h] [rbp-A0h]
  int v806; // [rsp+60h] [rbp-A0h]
  int v807; // [rsp+60h] [rbp-A0h]
  int v808; // [rsp+60h] [rbp-A0h]
  int v809; // [rsp+60h] [rbp-A0h]
  int v810; // [rsp+60h] [rbp-A0h]
  int v811; // [rsp+60h] [rbp-A0h]
  int v812; // [rsp+60h] [rbp-A0h]
  int v813; // [rsp+60h] [rbp-A0h]
  int v814; // [rsp+60h] [rbp-A0h]
  int v815; // [rsp+60h] [rbp-A0h]
  IMsiData *v816; // [rsp+70h] [rbp-90h] BYREF
  IMsiData *v817; // [rsp+78h] [rbp-88h] BYREF
  IMsiData *v818; // [rsp+80h] [rbp-80h] BYREF
  __int64 v819; // [rsp+88h] [rbp-78h] BYREF
  IMsiData *v820; // [rsp+90h] [rbp-70h] BYREF
  IMsiData *v821; // [rsp+98h] [rbp-68h] BYREF
  IMsiData *v822; // [rsp+A0h] [rbp-60h] BYREF
  bool v823; // [rsp+A8h] [rbp-58h]
  IMsiData *v824; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v825; // [rsp+B8h] [rbp-48h] BYREF
  IMsiData *v826; // [rsp+C0h] [rbp-40h] BYREF
  IMsiData *v827; // [rsp+C8h] [rbp-38h] BYREF
  IMsiData *v828; // [rsp+D0h] [rbp-30h] BYREF
  IMsiData *v829; // [rsp+D8h] [rbp-28h] BYREF
  IMsiData *v830; // [rsp+E0h] [rbp-20h] BYREF
  IMsiData *v831; // [rsp+E8h] [rbp-18h] BYREF
  IMsiData *v832; // [rsp+F0h] [rbp-10h] BYREF
  IMsiData *v833; // [rsp+F8h] [rbp-8h] BYREF
  IMsiData *v834; // [rsp+100h] [rbp+0h] BYREF
  IMsiData *v835; // [rsp+108h] [rbp+8h] BYREF
  IMsiData *v836; // [rsp+110h] [rbp+10h] BYREF
  IMsiData *v837; // [rsp+118h] [rbp+18h] BYREF
  IMsiData *v838; // [rsp+120h] [rbp+20h] BYREF
  char v839; // [rsp+128h] [rbp+28h]
  struct IMsiSummaryInfo *v840; // [rsp+130h] [rbp+30h] BYREF
  char v841; // [rsp+138h] [rbp+38h] BYREF
  char v842; // [rsp+139h] [rbp+39h]
  IMsiData *v843; // [rsp+140h] [rbp+40h] BYREF
  IMsiData *v844; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v845; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v846; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v847; // [rsp+15Ch] [rbp+5Ch]
  IMsiData *v848; // [rsp+160h] [rbp+60h] BYREF
  IMsiData *v849; // [rsp+168h] [rbp+68h] BYREF
  int v850; // [rsp+170h] [rbp+70h] BYREF
  __int64 v851; // [rsp+178h] [rbp+78h] BYREF
  __int64 v852; // [rsp+180h] [rbp+80h] BYREF
  __int64 v853; // [rsp+188h] [rbp+88h] BYREF
  char v854; // [rsp+190h] [rbp+90h] BYREF
  char v855[3]; // [rsp+191h] [rbp+91h] BYREF
  unsigned int v856; // [rsp+194h] [rbp+94h]
  char v857[8]; // [rsp+198h] [rbp+98h] BYREF
  char v858[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v859; // [rsp+1A8h] [rbp+A8h]
  char v860[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned int v861; // [rsp+1B8h] [rbp+B8h]
  bool v862; // [rsp+1BCh] [rbp+BCh]
  bool v863; // [rsp+1BDh] [rbp+BDh]
  int v864; // [rsp+1C0h] [rbp+C0h] BYREF
  void *v865; // [rsp+1C8h] [rbp+C8h] BYREF
  char v866[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int16 v867; // [rsp+1D8h] [rbp+D8h] BYREF
  char v868[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v869; // [rsp+1E8h] [rbp+E8h]
  char v870[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v871[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  IMsiData *v872; // [rsp+200h] [rbp+100h] BYREF
  IMsiData *v873; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int16 *v874; // [rsp+210h] [rbp+110h]
  int v875; // [rsp+218h] [rbp+118h] BYREF
  enum tagINSTALLSTATE ProductState; // [rsp+21Ch] [rbp+11Ch]
  char v877[8]; // [rsp+220h] [rbp+120h] BYREF
  char v878[8]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v879; // [rsp+230h] [rbp+130h]
  char v880[8]; // [rsp+238h] [rbp+138h] BYREF
  char v881[8]; // [rsp+240h] [rbp+140h] BYREF
  char v882[8]; // [rsp+248h] [rbp+148h] BYREF
  char v883[8]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 *v884; // [rsp+258h] [rbp+158h]
  IMsiData *v885; // [rsp+260h] [rbp+160h] BYREF
  char v886[8]; // [rsp+268h] [rbp+168h] BYREF
  char v887[8]; // [rsp+270h] [rbp+170h] BYREF
  unsigned int v888; // [rsp+278h] [rbp+178h] BYREF
  unsigned int v889; // [rsp+27Ch] [rbp+17Ch] BYREF
  unsigned int v890; // [rsp+280h] [rbp+180h] BYREF
  unsigned int v891; // [rsp+284h] [rbp+184h] BYREF
  unsigned int v892; // [rsp+288h] [rbp+188h] BYREF
  int v893; // [rsp+28Ch] [rbp+18Ch] BYREF
  int v894; // [rsp+290h] [rbp+190h] BYREF
  int v895; // [rsp+294h] [rbp+194h] BYREF
  int v896; // [rsp+298h] [rbp+198h] BYREF
  IMsiData *v897; // [rsp+2A0h] [rbp+1A0h] BYREF
  IMsiData *v898; // [rsp+2A8h] [rbp+1A8h] BYREF
  char v899[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  IMsiData *v900; // [rsp+2B8h] [rbp+1B8h] BYREF
  char v901[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v902[8]; // [rsp+2C8h] [rbp+1C8h] BYREF
  IMsiData *v903; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v904[8]; // [rsp+2D8h] [rbp+1D8h] BYREF
  char v905[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v906[8]; // [rsp+2E8h] [rbp+1E8h] BYREF
  char v907[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v908[8]; // [rsp+2F8h] [rbp+1F8h] BYREF
  char v909[8]; // [rsp+300h] [rbp+200h] BYREF
  char v910[8]; // [rsp+308h] [rbp+208h] BYREF
  char v911[8]; // [rsp+310h] [rbp+210h] BYREF
  char v912[8]; // [rsp+318h] [rbp+218h] BYREF
  char v913[8]; // [rsp+320h] [rbp+220h] BYREF
  char v914[8]; // [rsp+328h] [rbp+228h] BYREF
  IMsiData *v915; // [rsp+330h] [rbp+230h] BYREF
  char v916[8]; // [rsp+338h] [rbp+238h] BYREF
  char v917[8]; // [rsp+340h] [rbp+240h] BYREF
  char v918[8]; // [rsp+348h] [rbp+248h] BYREF
  __int64 v919; // [rsp+350h] [rbp+250h] BYREF
  IMsiData *v920; // [rsp+358h] [rbp+258h] BYREF
  const unsigned __int16 *v921; // [rsp+360h] [rbp+260h]
  char v922[8]; // [rsp+368h] [rbp+268h] BYREF
  __int64 v923; // [rsp+370h] [rbp+270h] BYREF
  IMsiData *v924; // [rsp+378h] [rbp+278h] BYREF
  char v925[8]; // [rsp+380h] [rbp+280h] BYREF
  IMsiData *v926; // [rsp+388h] [rbp+288h] BYREF
  IMsiData *v927; // [rsp+390h] [rbp+290h] BYREF
  IMsiData *v928; // [rsp+398h] [rbp+298h] BYREF
  IMsiData *v929; // [rsp+3A0h] [rbp+2A0h] BYREF
  IMsiData *v930; // [rsp+3A8h] [rbp+2A8h] BYREF
  IMsiData *v931; // [rsp+3B0h] [rbp+2B0h] BYREF
  IMsiData *v932; // [rsp+3B8h] [rbp+2B8h] BYREF
  IMsiData *v933; // [rsp+3C0h] [rbp+2C0h] BYREF
  IMsiData *v934; // [rsp+3C8h] [rbp+2C8h] BYREF
  IMsiData *v935; // [rsp+3D0h] [rbp+2D0h] BYREF
  IMsiData *v936; // [rsp+3D8h] [rbp+2D8h] BYREF
  IMsiData *v937; // [rsp+3E0h] [rbp+2E0h] BYREF
  struct IMsiRecord *v938; // [rsp+3E8h] [rbp+2E8h] BYREF
  struct IMsiRecord *v939; // [rsp+3F0h] [rbp+2F0h] BYREF
  IMsiData *v940; // [rsp+3F8h] [rbp+2F8h] BYREF
  IMsiData *v941; // [rsp+400h] [rbp+300h] BYREF
  IMsiData *v942; // [rsp+408h] [rbp+308h] BYREF
  char v943[8]; // [rsp+410h] [rbp+310h] BYREF
  char v944[8]; // [rsp+418h] [rbp+318h] BYREF
  char v945[8]; // [rsp+420h] [rbp+320h] BYREF
  char v946[8]; // [rsp+428h] [rbp+328h] BYREF
  char v947[8]; // [rsp+430h] [rbp+330h] BYREF
  char v948[8]; // [rsp+438h] [rbp+338h] BYREF
  char v949[8]; // [rsp+440h] [rbp+340h] BYREF
  char v950[8]; // [rsp+448h] [rbp+348h] BYREF
  char v951[8]; // [rsp+450h] [rbp+350h] BYREF
  char v952[8]; // [rsp+458h] [rbp+358h] BYREF
  char v953[8]; // [rsp+460h] [rbp+360h] BYREF
  char v954[8]; // [rsp+468h] [rbp+368h] BYREF
  char v955[8]; // [rsp+470h] [rbp+370h] BYREF
  char v956[8]; // [rsp+478h] [rbp+378h] BYREF
  char v957[8]; // [rsp+480h] [rbp+380h] BYREF
  char v958[8]; // [rsp+488h] [rbp+388h] BYREF
  char v959[8]; // [rsp+490h] [rbp+390h] BYREF
  char v960[8]; // [rsp+498h] [rbp+398h] BYREF
  char v961[8]; // [rsp+4A0h] [rbp+3A0h] BYREF
  char v962[8]; // [rsp+4A8h] [rbp+3A8h] BYREF
  char v963[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v964[8]; // [rsp+4B8h] [rbp+3B8h] BYREF
  char v965[8]; // [rsp+4C0h] [rbp+3C0h] BYREF
  char v966[8]; // [rsp+4C8h] [rbp+3C8h] BYREF
  char v967[8]; // [rsp+4D0h] [rbp+3D0h] BYREF
  char v968[8]; // [rsp+4D8h] [rbp+3D8h] BYREF
  char v969[8]; // [rsp+4E0h] [rbp+3E0h] BYREF
  char v970[8]; // [rsp+4E8h] [rbp+3E8h] BYREF
  char v971[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  char v972[8]; // [rsp+4F8h] [rbp+3F8h] BYREF
  char v973[8]; // [rsp+500h] [rbp+400h] BYREF
  char v974[8]; // [rsp+508h] [rbp+408h] BYREF
  char v975[8]; // [rsp+510h] [rbp+410h] BYREF
  char v976[8]; // [rsp+518h] [rbp+418h] BYREF
  char v977[8]; // [rsp+520h] [rbp+420h] BYREF
  char v978[8]; // [rsp+528h] [rbp+428h] BYREF
  char v979[8]; // [rsp+530h] [rbp+430h] BYREF
  char v980[8]; // [rsp+538h] [rbp+438h] BYREF
  char v981[8]; // [rsp+540h] [rbp+440h] BYREF
  char v982[8]; // [rsp+548h] [rbp+448h] BYREF
  char v983[8]; // [rsp+550h] [rbp+450h] BYREF
  char v984[8]; // [rsp+558h] [rbp+458h] BYREF
  char v985[8]; // [rsp+560h] [rbp+460h] BYREF
  char v986[8]; // [rsp+568h] [rbp+468h] BYREF
  char v987[8]; // [rsp+570h] [rbp+470h] BYREF
  char v988[8]; // [rsp+578h] [rbp+478h] BYREF
  char v989[8]; // [rsp+580h] [rbp+480h] BYREF
  char v990[8]; // [rsp+588h] [rbp+488h] BYREF
  char v991[8]; // [rsp+590h] [rbp+490h] BYREF
  char v992[8]; // [rsp+598h] [rbp+498h] BYREF
  char v993[8]; // [rsp+5A0h] [rbp+4A0h] BYREF
  char v994[8]; // [rsp+5A8h] [rbp+4A8h] BYREF
  char v995[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  char v996[8]; // [rsp+5B8h] [rbp+4B8h] BYREF
  char v997[8]; // [rsp+5C0h] [rbp+4C0h] BYREF
  char v998[8]; // [rsp+5C8h] [rbp+4C8h] BYREF
  char v999[8]; // [rsp+5D0h] [rbp+4D0h] BYREF
  char v1000[8]; // [rsp+5D8h] [rbp+4D8h] BYREF
  char v1001[8]; // [rsp+5E0h] [rbp+4E0h] BYREF
  char v1002[8]; // [rsp+5E8h] [rbp+4E8h] BYREF
  char v1003[8]; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v1004[8]; // [rsp+5F8h] [rbp+4F8h] BYREF
  char v1005[8]; // [rsp+600h] [rbp+500h] BYREF
  char v1006[8]; // [rsp+608h] [rbp+508h] BYREF
  char v1007[8]; // [rsp+610h] [rbp+510h] BYREF
  char v1008[8]; // [rsp+618h] [rbp+518h] BYREF
  char v1009[8]; // [rsp+620h] [rbp+520h] BYREF
  char v1010[8]; // [rsp+628h] [rbp+528h] BYREF
  char v1011[8]; // [rsp+630h] [rbp+530h] BYREF
  char v1012[8]; // [rsp+638h] [rbp+538h] BYREF
  char v1013[8]; // [rsp+640h] [rbp+540h] BYREF
  char v1014[8]; // [rsp+648h] [rbp+548h] BYREF
  char v1015[8]; // [rsp+650h] [rbp+550h] BYREF
  char v1016[8]; // [rsp+658h] [rbp+558h] BYREF
  char v1017[8]; // [rsp+660h] [rbp+560h] BYREF
  char v1018[8]; // [rsp+668h] [rbp+568h] BYREF
  char v1019[8]; // [rsp+670h] [rbp+570h] BYREF
  char v1020[8]; // [rsp+678h] [rbp+578h] BYREF
  char v1021[8]; // [rsp+680h] [rbp+580h] BYREF
  char v1022[8]; // [rsp+688h] [rbp+588h] BYREF
  char v1023[8]; // [rsp+690h] [rbp+590h] BYREF
  char v1024[8]; // [rsp+698h] [rbp+598h] BYREF
  char v1025[8]; // [rsp+6A0h] [rbp+5A0h] BYREF
  char v1026[8]; // [rsp+6A8h] [rbp+5A8h] BYREF
  char v1027[8]; // [rsp+6B0h] [rbp+5B0h] BYREF
  char v1028[8]; // [rsp+6B8h] [rbp+5B8h] BYREF
  char v1029[8]; // [rsp+6C0h] [rbp+5C0h] BYREF
  char v1030[8]; // [rsp+6C8h] [rbp+5C8h] BYREF
  char v1031[8]; // [rsp+6D0h] [rbp+5D0h] BYREF
  char v1032[8]; // [rsp+6D8h] [rbp+5D8h] BYREF
  char v1033[8]; // [rsp+6E0h] [rbp+5E0h] BYREF
  char v1034[8]; // [rsp+6E8h] [rbp+5E8h] BYREF
  char v1035[8]; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v1036[8]; // [rsp+6F8h] [rbp+5F8h] BYREF
  char v1037[8]; // [rsp+700h] [rbp+600h] BYREF
  char v1038[8]; // [rsp+708h] [rbp+608h] BYREF
  char v1039[8]; // [rsp+710h] [rbp+610h] BYREF
  char v1040[8]; // [rsp+718h] [rbp+618h] BYREF
  char v1041[8]; // [rsp+720h] [rbp+620h] BYREF
  char v1042[8]; // [rsp+728h] [rbp+628h] BYREF
  char v1043[8]; // [rsp+730h] [rbp+630h] BYREF
  char v1044[8]; // [rsp+738h] [rbp+638h] BYREF
  char v1045[8]; // [rsp+740h] [rbp+640h] BYREF
  char v1046[8]; // [rsp+748h] [rbp+648h] BYREF
  char v1047[8]; // [rsp+750h] [rbp+650h] BYREF
  char v1048[8]; // [rsp+758h] [rbp+658h] BYREF
  char v1049[8]; // [rsp+760h] [rbp+660h] BYREF
  char v1050[8]; // [rsp+768h] [rbp+668h] BYREF
  char v1051[8]; // [rsp+770h] [rbp+670h] BYREF
  char v1052[8]; // [rsp+778h] [rbp+678h] BYREF
  char v1053[8]; // [rsp+780h] [rbp+680h] BYREF
  char v1054[8]; // [rsp+788h] [rbp+688h] BYREF
  wchar_t *String; // [rsp+790h] [rbp+690h] BYREF
  int v1056; // [rsp+798h] [rbp+698h]
  int v1057; // [rsp+79Ch] [rbp+69Ch]
  _BYTE v1058[208]; // [rsp+7A0h] [rbp+6A0h] BYREF
  GUID iid; // [rsp+870h] [rbp+770h] BYREF
  unsigned __int16 *v1060; // [rsp+880h] [rbp+780h] BYREF
  int v1061; // [rsp+88Ch] [rbp+78Ch]
  _BYTE v1062[24]; // [rsp+898h] [rbp+798h] BYREF
  _BYTE v1063[32]; // [rsp+8B0h] [rbp+7B0h] BYREF
  _BYTE v1064[96]; // [rsp+8D0h] [rbp+7D0h] BYREF
  _BYTE v1065[64]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v1066[8]; // [rsp+970h] [rbp+870h] BYREF
  _QWORD v1067[2]; // [rsp+978h] [rbp+878h] BYREF
  char v1068[24]; // [rsp+988h] [rbp+888h] BYREF
  char v1069[24]; // [rsp+9A0h] [rbp+8A0h] BYREF
  char v1070[24]; // [rsp+9B8h] [rbp+8B8h] BYREF

  v8 = a7;
  v921 = a5;
  v9 = a4;
  v874 = a4;
  v826 = (IMsiData *)&MsiString::s_NullString;
  v10 = a2;
  v11 = 5;
  v824 = (IMsiData *)&MsiString::s_NullString;
  v829 = (IMsiData *)&MsiString::s_NullString;
  v12 = 0;
  v834 = (IMsiData *)&MsiString::s_NullString;
  v831 = (IMsiData *)&MsiString::s_NullString;
  v817 = (IMsiData *)&MsiString::s_NullString;
  v828 = (IMsiData *)&MsiString::s_NullString;
  v830 = (IMsiData *)&MsiString::s_NullString;
  v832 = (IMsiData *)&MsiString::s_NullString;
  v835 = (IMsiData *)&MsiString::s_NullString;
  v827 = (IMsiData *)&MsiString::s_NullString;
  v837 = (IMsiData *)&MsiString::s_NullString;
  v838 = (IMsiData *)&MsiString::s_NullString;
  v833 = (IMsiData *)&MsiString::s_NullString;
  v836 = (IMsiData *)&MsiString::s_NullString;
  v884 = a2;
  v845 = a3;
  v879 = a7;
  v856 = 0;
  v853 = 0;
  if ( a3 == 5 )
  {
    v13 = 1;
    v845 = 0;
    v859 = 1;
  }
  else
  {
    v859 = 0;
    v13 = 0;
    if ( a3 > 4 )
    {
      v845 = 2;
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
      v845 = 3;
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
  v819 = 0;
  v825 = 0;
  *(_DWORD *)(a1 + 584) = a6;
  if ( (a6 & 0x800) != 0 )
    *(_BYTE *)(a1 + 606) = 1;
  v823 = CMsiEngine::IgnoreMachineState((CMsiEngine *)a1);
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
      CComPointer<IMsiDatabase>::operator=(&v825, v17);
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
      v24 = CComPointer<IEnumMsiRecord>::operator=(&v825);
      v25 = v23(v22, v884, 0, v24);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v853, v25) )
      {
LABEL_245:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
        IMsiData::Release(v836);
        IMsiData::Release(v833);
        IMsiData::Release(v838);
        IMsiData::Release(v837);
        IMsiData::Release(v827);
        IMsiData::Release(v835);
        IMsiData::Release(v832);
        IMsiData::Release(v830);
        IMsiData::Release(v828);
        IMsiData::Release(v817);
        IMsiData::Release(v831);
        IMsiData::Release(v834);
        IMsiData::Release(v829);
        IMsiData::Release(v824);
        IMsiData::Release(v826);
LABEL_691:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v853);
        return v11;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v825 + 168LL))(v825, 0) )
      {
        v11 = 6;
        goto LABEL_245;
      }
      v10 = v884;
    }
LABEL_24:
    IMsiData::Release(v832);
    v832 = (IMsiData *)&MsiString::s_NullString;
    v18 = *(_QWORD *)MsiString::MsiString((MsiString *)&v926, L"CURRENTDIRECTORY");
    IMsiData::Release(v831);
    v831 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v834);
    v834 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v829);
    v829 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v824);
    v824 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release(v826);
    v826 = (IMsiData *)&MsiString::s_NullString;
    ProcessCommandLine(v9, &v826, &v824, &v829, &v834, &v831, 0, v18, &v832, 1, a1 + 448, 0, 0);
    IMsiData::Release(v926);
    if ( !(unsigned int)MsiString::operator int(&v826) )
      MsiString::operator=(&v826, &Default);
    v19 = (const WCHAR *)MsiString::operator unsigned short const *(&v831);
    if ( CompareStringW(0x409u, 1u, v19, -1, L"ADMIN", -1) == 2 )
    {
      v20 = 1;
    }
    else
    {
      v26 = (const WCHAR *)MsiString::operator unsigned short const *(&v831);
      if ( CompareStringW(0x409u, 1u, v26, -1, L"ADVERTISE", -1) != 2 )
        goto LABEL_29;
      v20 = 2;
    }
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, v20, 1);
LABEL_29:
    v13 = v859;
  }
  v847 = -1;
  v842 = 0;
  MsiString::MsiString((MsiString *)&v816, v10);
  v818 = (IMsiData *)&MsiString::s_NullString;
  MsiString::operator=(a1 + 520, &v816);
  if ( g_dmDiagnosticMode )
  {
    v27 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v816);
    DebugString(9, 0, 0, L"Original package ==> %s", v27, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
  }
  v846 = 0;
  v820 = (IMsiData *)&MsiString::s_NullString;
  v822 = (IMsiData *)&MsiString::s_NullString;
  v821 = (IMsiData *)&MsiString::s_NullString;
  v850 = 0;
  ProductState = INSTALLSTATE_UNKNOWN;
  v861 = 3;
  v869 = 0;
  memset_0(v1058, 0, 0xC8u);
  v1056 = 100;
  String = (wchar_t *)v1058;
  v28 = *(_QWORD *)(a1 + 168);
  if ( v28 )
  {
    CComPointer<IMsiDatabase>::operator=(&v819, v28);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 168) + 8LL))(*(_QWORD *)(a1 + 168));
  }
  v11 = 6;
  if ( !v13 )
  {
    if ( (!v10 || !*v10) && !*(_QWORD *)(a1 + 168) )
    {
      v29 = *(_QWORD *)(a1 + 128);
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v29 + 104LL);
      v31 = CComPointer<IEnumMsiRecord>::operator=(&v819);
      v32 = v30(v29, 0, 3, v31);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v853, v32)
        || !(unsigned int)CMsiEngine::CreatePropertyTable(a1, v819, 0, 0) )
      {
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
        IMsiData::Release(v821);
        IMsiData::Release(v822);
        IMsiData::Release(v820);
        IMsiData::Release(v818);
        IMsiData::Release(v816);
        v11 = 5;
        goto LABEL_245;
      }
      goto LABEL_393;
    }
    v33 = v825;
    v34 = *(__int64 (__fastcall **)(__int64, IMsiData **))(*(_QWORD *)v825 + 152LL);
    IMsiData::Release(v818);
    v818 = (IMsiData *)&MsiString::s_NullString;
    v35 = v34(v33, &v818);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v853, v35) )
    {
      v11 = CMsiEngine::PostInitializeError(a1, v853, v818, 5);
      goto LABEL_46;
    }
    if ( g_dmDiagnosticMode )
    {
      v36 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v818);
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
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v816) )
      MsiString::operator=(&v816, &v818);
    MsiString::operator=(a1 + 512, &v818);
    v37 = *(IMsiData **)(a1 + 448);
    if ( v37 )
      IMsiData::Release(v37);
    *(_QWORD *)(a1 + 448) = v816;
    IMsiData::AddRef(v816);
    v840 = 0;
    *(_DWORD *)(a1 + 404) = 0;
    *(_DWORD *)(a1 + 456) = 0;
    v38 = v825;
    v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v825 + 136LL);
    v40 = CComPointer<IEnumMsiRecord>::operator=(&v840);
    v41 = v39(v38, 0, v40);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v853, v41) )
      goto LABEL_63;
    IMsiData::Release(v833);
    v833 = (IMsiData *)&MsiString::s_NullString;
    CMsiEngine::GetSummaryInfoProperties((CMsiEngine *)a1, v840, &v833, (int *)(a1 + 596));
    *(_BYTE *)(a1 + 600) = PackageInstallsAsLUA(*(_DWORD *)(a1 + 596));
    v42 = (IMsiData *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 392) + 176LL))(
                        *(_QWORD *)(a1 + 392),
                        0,
                        38);
    IMsiData::Release(v830);
    v830 = v42;
    v43 = 0;
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v830) )
    {
LABEL_63:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
      goto LABEL_46;
    }
    if ( (unsigned int)(*(_DWORD *)(a1 + 456) - 30) > 0x1D6
      || !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 128) + 24LL))(*(_QWORD *)(a1 + 128)) )
    {
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      IMsiData::Release(v821);
      IMsiData::Release(v822);
      IMsiData::Release(v820);
      IMsiData::Release(v818);
      IMsiData::Release(v816);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
      IMsiData::Release(v836);
      IMsiData::Release(v833);
      IMsiData::Release(v838);
      IMsiData::Release(v837);
      IMsiData::Release(v827);
      IMsiData::Release(v835);
      IMsiData::Release(v832);
      IMsiData::Release(v830);
      IMsiData::Release(v828);
      IMsiData::Release(v817);
      IMsiData::Release(v831);
      IMsiData::Release(v834);
      IMsiData::Release(v829);
      IMsiData::Release(v824);
      IMsiData::Release(v826);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v853);
      return 7;
    }
    v44 = v819;
    if ( !v819 )
    {
      v45 = *(_QWORD *)(a1 + 128);
      v46 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v45 + 112LL);
      v47 = CComPointer<IEnumMsiRecord>::operator=(&v819);
      v48 = v46(v45, v825, 1, v47);
      v43 = 0;
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v853, v48) )
      {
        v11 = CMsiEngine::PostInitializeError(a1, v853, v818, 6);
        goto LABEL_63;
      }
      v44 = v819;
    }
    PropertyTable = CMsiEngine::CreatePropertyTable(a1, v44, L"Property", 1);
    if ( v921 && *v921 )
    {
      MsiString::operator=(&v817, v921);
      MsiString::UpperCase((MsiString *)&v817);
    }
    else if ( PropertyTable )
    {
      v50 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                          a1,
                          L"ProductCode");
      IMsiData::Release(v817);
      v817 = v50;
      v43 = 0;
    }
    IMsiData::Release(v835);
    v835 = (IMsiData *)&MsiString::s_NullString;
    v51 = MsiString::MsiString((MsiString *)&v927, L"MSINEWINSTANCE");
    LOBYTE(v804) = 0;
    v52 = v874;
    ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, *(_QWORD *)v51, &v835, 1, 0, 0, v804);
    IMsiData::Release(v927);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v835) )
    {
      *(_BYTE *)(a1 + 612) = 1;
      v53 = (IMsiData *)MsiString::Extract(&v824, 2, 59);
      IMsiData::Release(v827);
      v827 = v53;
      v43 = 0;
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v817) && !v823 && !*(_BYTE *)(a1 + 612) )
    {
      v54 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
      ProductState = CMsiEngine::GetProductState((CMsiEngine *)a1, v54, (enum Bool *)&v846, (enum Bool *)&v850);
    }
    v844 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v844 = (IMsiData *)&MsiString::s_NullString;
    v55 = MsiString::MsiString((MsiString *)&v928, L"REMOVE");
    LOBYTE(v805) = 0;
    ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, *(_QWORD *)v55, &v844, 1, a1 + 448, 0, v805);
    IMsiData::Release(v928);
    *(_BYTE *)(a1 + 98) = 0;
    if ( (unsigned int)MsiString::Compare(&v844, 0, L"ALL") )
      *(_BYTE *)(a1 + 98) = 1;
    v843 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v843 = (IMsiData *)&MsiString::s_NullString;
    v56 = MsiString::MsiString((MsiString *)&v929, L"CLIENTUILEVEL");
    LOBYTE(v806) = 0;
    ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, *(_QWORD *)v56, &v843, 1, 0, 0, v806);
    IMsiData::Release(v929);
    if ( g_scServerContext )
    {
      if ( !(unsigned int)MsiString::TextSize((MsiString *)&v843) )
        goto LABEL_90;
      v57 = MsiString::operator int(&v843);
      v861 = v57;
      dword_180309774 = v57;
    }
    else
    {
      v57 = v845;
      v861 = v845;
    }
    if ( v57 != 3 )
      goto LABEL_106;
    v43 = 0;
LABEL_90:
    v898 = (IMsiData *)&MsiString::s_NullString;
    v897 = (IMsiData *)&MsiString::s_NullString;
    if ( CMsiTransaction::m_pMsiTransaction )
    {
      if ( CMsiTransaction::FMultiPackageTransaction((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction) )
      {
        IMsiData::Release(v898);
        v898 = (IMsiData *)&MsiString::s_NullString;
        LOBYTE(v807) = 0;
        v12 = 1;
        v58 = *(_QWORD *)MsiString::MsiString((MsiString *)&v930, L"MSICLIENTUSESEXTERNALUI");
        v856 = 1;
        if ( (unsigned int)ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, v58, &v898, 1, a1 + 448, 0, v807) )
        {
          v856 = 1;
          if ( (unsigned int)MsiString::TextSize((MsiString *)&v898) )
          {
            v43 = 1;
            v856 = 1;
          }
        }
      }
    }
    if ( (v12 & 1) != 0 )
    {
      v12 &= ~1u;
      v856 = v12;
      IMsiData::Release(v930);
    }
    if ( v43 )
    {
      v57 = 4;
    }
    else
    {
      IMsiData::Release(v897);
      v59 = v12 | 2;
      v897 = (IMsiData *)&MsiString::s_NullString;
      v60 = MsiString::MsiString((MsiString *)&v931, L"MSICLIENTUSESEMBEDDEDUI");
      v61 = 0;
      LOBYTE(v807) = 0;
      if ( (unsigned int)ProcessCommandLine(v52, 0, 0, 0, 0, 0, 0, *(_QWORD *)v60, &v897, 1, a1 + 448, 0, v807) )
        v61 = (unsigned int)MsiString::TextSize((MsiString *)&v897) != 0;
      v12 = v59 & 0xFFFFFFFD;
      v856 = v12;
      IMsiData::Release(v931);
      v62 = !v61;
      v57 = v861;
      if ( !v62 )
        v57 = 4;
    }
    if ( (a6 & 0x800000) != 0 )
      v57 = 4;
    v861 = v57;
    dword_180309774 = v57;
    IMsiData::Release(v897);
    IMsiData::Release(v898);
LABEL_106:
    *(_DWORD *)(a1 + 608) = 0;
    v841 = 0;
    if ( v57 == 3 || (v63 = 0, v839 = 0, g_scServerContext == 2) )
    {
      v63 = 1;
      v839 = 1;
    }
    LOBYTE(v801) = 0;
    LOBYTE(v799) = v63;
    CMsiEngine::ApplyAppCompatTransforms(a1, v884, v52, v819, v817, v830, 1, a1 + 608, v799, v801, &v841);
    if ( v841 && !v846 )
    {
      v903 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a1 + 184LL))(a1, L"ProductName");
      if ( !(unsigned int)MsiString::TextSize((MsiString *)&v903) )
        MsiString::operator=(&v903, &v816);
      v64 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v903);
      DebugString(21, 1u, 1018, v64, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      v65 = CMsiEngine::PostInitializeError(a1, 0, v816, 30);
      v66 = v903;
      v11 = v65;
      goto LABEL_114;
    }
    if ( v850 && !v823 )
    {
      v1057 = 100;
      v67 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
      if ( (unsigned int)GetExpandedProductInfo(v67, L"Transforms") )
        MsiString::operator=(&v824, String);
      v1057 = 100;
      v68 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
      if ( (unsigned int)GetProductInfo(v68, L"Language") )
        MsiString::operator=(&v826, String);
      v1057 = 100;
      v69 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
      if ( (unsigned int)GetProductInfo(v69, L"InstanceType") )
      {
        v70 = MsiString::MsiString((MsiString *)&v932, String);
        v71 = MsiString::operator int(v70);
        IMsiData::Release(v932);
        if ( v71 == 1 )
        {
          v72 = (IMsiData *)MsiString::Extract(&v824, 2, 59);
          IMsiData::Release(v827);
          v827 = v72;
        }
      }
      v1057 = 100;
      v73 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
      if ( (unsigned int)GetProductInfo(v73, L"AuthorizedLUAApp") )
      {
        v74 = MsiString::MsiString((MsiString *)&v933, String);
        v75 = MsiString::operator int(v74);
        IMsiData::Release(v933);
        if ( v75 == 1 )
          *(_BYTE *)(a1 + 97) = 1;
      }
      v1057 = 100;
      v76 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
      if ( (unsigned int)GetProductInfo(v76, L"DeploymentFlags") )
      {
        v77 = wcstol(String, 0, 10);
        if ( v77 > 6 )
          v77 = 0;
        v869 = v77;
      }
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v827) && g_dmDiagnosticMode )
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
      IMsiData::Release(v843);
      IMsiData::Release(v844);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      IMsiData::Release(v821);
      IMsiData::Release(v822);
      IMsiData::Release(v820);
      IMsiData::Release(v818);
      IMsiData::Release(v816);
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
    v79 = (IMsiData *)MsiString::ExtractAndRemove(&v833, 2, 59);
    IMsiData::Release(v836);
    v80 = (_WORD *)(a1 + 604);
    v836 = v79;
    v81 = CMsiEngine::ProcessPlatform(a1, v79, a1 + 604);
    if ( *(_WORD *)(a1 + 604) == 0xFFFF )
      goto LABEL_115;
    g_wPackagePlatform = *(_WORD *)(a1 + 604);
    if ( (a6 & 4) == 0 && v81 )
    {
LABEL_244:
      IMsiData::Release(v843);
      IMsiData::Release(v844);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      IMsiData::Release(v821);
      IMsiData::Release(v822);
      IMsiData::Release(v820);
      IMsiData::Release(v818);
      IMsiData::Release(v816);
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
    v82 = v823;
    LOBYTE(cchCount2) = v823;
    v867 = 0;
    v81 = CMsiEngine::ProcessLanguage(a1, v833, v826, &v867, 1, cchCount2);
    if ( v81 )
    {
      if ( v850 && !v82 && (unsigned int)MsiString::TextSize((MsiString *)&v826) && v81 == 12 )
        v81 = 24;
      goto LABEL_244;
    }
    v864 = 1;
    v849 = (IMsiData *)&MsiString::s_NullString;
    v848 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v849 = (IMsiData *)&MsiString::s_NullString;
    v83 = MsiString::MsiString((MsiString *)&v934, L"TRANSFORMSSECURE");
    LOBYTE(v807) = 0;
    ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, *(_QWORD *)v83, &v849, 1, a1 + 448, 0, v807);
    IMsiData::Release(v934);
    IMsiData::Release(v848);
    v848 = (IMsiData *)&MsiString::s_NullString;
    v84 = MsiString::MsiString((MsiString *)&v935, L"TRANSFORMSATSOURCE");
    LOBYTE(v808) = 0;
    ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, *(_QWORD *)v84, &v848, 1, a1 + 448, 0, v808);
    IMsiData::Release(v935);
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v824) == 64 )
    {
      v864 = 2;
    }
    else if ( *(_WORD *)MsiString::operator unsigned short const *(&v824) == 124 )
    {
      v864 = 3;
    }
    else if ( !v850 )
    {
      v85 = v12 | 4;
      v86 = *(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 192LL);
      v87 = MsiString::MsiString((MsiString *)&v937, L"TRANSFORMSSECURE");
      v90 = 1;
      if ( v86(a1, *(_QWORD *)v87) != 1 )
      {
        v85 |= 8u;
        v88 = *(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 192LL);
        v89 = MsiString::MsiString((MsiString *)&v936, L"TRANSFORMSATSOURCE");
        if ( v88(a1, *(_QWORD *)v89) != 1
          && (unsigned int)MsiString::operator int(&v849) != 1
          && (unsigned int)MsiString::operator int(&v848) != 1
          && (v82 || !(unsigned int)GetIntegerPolicyValue(3, 1, 0) && !(unsigned int)GetIntegerPolicyValue(4, 0, 0)) )
        {
          v90 = 0;
        }
      }
      if ( (v85 & 8) != 0 )
      {
        v85 &= ~8u;
        IMsiData::Release(v936);
      }
      v12 = v85 & 0xFFFFFFFB;
      v856 = v12;
      IMsiData::Release(v937);
      if ( v90 )
        v864 = 0;
    }
    v895 = 0;
    v873 = (IMsiData *)&g_MsiStringNull;
    v872 = (IMsiData *)&g_MsiStringNull;
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v827) )
    {
      if ( g_dmDiagnosticMode )
      {
        v91 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v827);
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
        v93 = MsiString::operator unsigned short const *(&v832);
        v94 = MsiString::operator unsigned short const *(&v820);
        LOBYTE(v797) = 1;
        LOBYTE(v795) = 1;
        v95 = CMsiEngine::InitializeTransforms(
                a1,
                v819,
                0,
                v827,
                1,
                0,
                v795,
                v797,
                &v895,
                v94,
                v93,
                &v873,
                &v864,
                &v872);
        v81 = v95;
        if ( !v95 )
        {
LABEL_193:
          v100 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                               a1,
                               L"ProductCode");
          IMsiData::Release(v828);
          v828 = v100;
          MsiString::UpperCase((MsiString *)&v828);
          v8 = v879;
          v82 = v823;
          goto LABEL_194;
        }
        if ( v95 != -2 )
          break;
        IMsiData::Release(v822);
        v822 = (IMsiData *)&MsiString::s_NullString;
        IMsiData::Release(v820);
        v96 = v846;
        v97 = v845;
        v820 = (IMsiData *)&MsiString::s_NullString;
        v98 = MsiString::operator unsigned short const *(&v816);
        v99 = MsiString::operator unsigned short const *(&v817);
        v919 = CMsiEngine::ResolveSource(a1, v99, v98, v97, v96, &v820, &v822, 0);
        if ( v919 )
        {
          IMsiData::Release(v873);
          IMsiData::Release(v872);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v919);
          IMsiData::Release(v848);
          IMsiData::Release(v849);
          IMsiData::Release(v843);
          IMsiData::Release(v844);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
          IMsiData::Release(v821);
          IMsiData::Release(v822);
          IMsiData::Release(v820);
          IMsiData::Release(v818);
          IMsiData::Release(v816);
          v11 = 8;
          goto LABEL_245;
        }
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v919);
        if ( ++v92 >= 2 )
          goto LABEL_193;
      }
      IMsiData::Release(v873);
      IMsiData::Release(v872);
      goto LABEL_243;
    }
LABEL_194:
    v852 = 0;
    v851 = 0;
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v817) )
    {
      if ( !v82 )
      {
        v101 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v851);
        v102 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v852);
        CMsiEngine::ParsePatchProperties((CMsiEngine *)a1, v829, v834, v102, v101);
        CMsiEngine::SetPatchingRunFromSourceFeatures((CMsiEngine *)a1, 0);
        CMsiEngine::SetActiveMajorUpgradePatch((CMsiEngine *)a1, 0);
        v103 = operator new(0xF8u);
        v104 = 0;
        *(_QWORD *)(a1 + 1256) = v103;
        if ( !v103 )
        {
          v938 = PostError(2346);
          v105 = CMsiEngine::PostInitializeError(a1, v938, v816, 33);
          v106 = &v938;
LABEL_198:
          v11 = v105;
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v106);
LABEL_199:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
          IMsiData::Release(v848);
          v66 = v849;
LABEL_114:
          IMsiData::Release(v66);
LABEL_115:
          IMsiData::Release(v843);
          IMsiData::Release(v844);
          goto LABEL_63;
        }
        v107 = operator new(0xF8u);
        *(_QWORD *)(a1 + 1264) = v107;
        if ( !v107 )
        {
          v939 = PostError(2346);
          v105 = CMsiEngine::PostInitializeError(a1, v939, v816, 33);
          v106 = &v939;
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
            CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&v1060, 20);
            v885 = (IMsiData *)&MsiString::s_NullString;
            if ( !v1060 )
              goto LABEL_210;
            v1061 = 1;
            v110 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
            if ( !(unsigned int)GetProductInfo(v110, L"LocalPackage")
              || (IMsiData::Release(v885),
                  v885 = (IMsiData *)&MsiString::s_NullString,
                  v12 |= 0x30u,
                  v111 = *(const struct IMsiString **)MsiString::MsiString((MsiString *)&v941, L"ProductVersion"),
                  v112 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v940, v1060),
                  PropertyFromDatabase = GetPropertyFromDatabase(
                                           0,
                                           *v112,
                                           (const struct IMsiString *)&MsiString::s_NullString,
                                           v111,
                                           &v885),
                  v114 = 1,
                  *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v853, PropertyFromDatabase)) )
            {
LABEL_210:
              v114 = 0;
            }
            if ( (v12 & 0x20) != 0 )
            {
              v12 &= ~0x20u;
              IMsiData::Release(v940);
            }
            if ( (v12 & 0x10) != 0 )
            {
              v12 &= ~0x10u;
              IMsiData::Release(v941);
            }
            if ( !v114 )
              goto LABEL_925;
            v115 = 0;
            v920 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
                                 a1,
                                 L"ProductVersion");
            v891 = 0;
            v890 = 0;
            v889 = 0;
            v888 = 0;
            v116 = MsiString::operator unsigned short const *(&v885);
            if ( !(unsigned int)ParseVersionString(v116, &v891, &v890) )
              goto LABEL_220;
            v117 = MsiString::operator unsigned short const *(&v920);
            if ( (unsigned int)ParseVersionString(v117, &v889, &v888) )
            {
              if ( (unsigned int)CompareVersions(v891, v890, v889, v888) != 2 )
                v104 = 1;
            }
            else
            {
LABEL_220:
              v115 = 1;
            }
            IMsiData::Release(v920);
            if ( v115 || v104 )
            {
LABEL_925:
              if ( v851 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v851 + 24LL))(v851) )
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
                IMsiData::Release(v885);
                IMsiData::Release((IMsiData *)&MsiString::s_NullString);
                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v1060);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                IMsiData::Release(v848);
                IMsiData::Release(v849);
                IMsiData::Release(v843);
                IMsiData::Release(v844);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
                CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
                IMsiData::Release(v821);
                IMsiData::Release(v822);
                IMsiData::Release(v820);
                IMsiData::Release(v818);
                IMsiData::Release(v816);
                v11 = 36;
                goto LABEL_245;
              }
              v109 = 2;
            }
            IMsiData::Release(v885);
            IMsiData::Release((IMsiData *)&MsiString::s_NullString);
            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v1060);
          }
        }
        LOBYTE(v108) = v850 != 0;
        LOBYTE(lpString2) = (a6 & 0x40000) != 0;
        v81 = CMsiEngine::InitializePatches(a1, v819, v817, v108, lpString2, v109, v852, v851, v8);
        if ( !v81 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 272LL))(a1, v8);
          v854 = 0;
          v81 = CMsiEngine::CheckPatchSecurity(a1, v817, &v854);
          if ( v81 == 38 )
          {
            if ( !*(_BYTE *)(a1 + 601) )
            {
              if ( qword_180309730 )
                CMsiSQMSession::RecordElevationCause(qword_180309730, 2);
              v118 = CMsiEngine::EnginePromptForElevatedCredentials(a1, v819, 4);
              if ( v118 )
              {
                v11 = v118;
                if ( v854 )
                  v11 = 35;
                goto LABEL_199;
              }
              *(_BYTE *)(a1 + 601) = 1;
            }
LABEL_241:
            v81 = CMsiEngine::VerifyAccessAndOpenPatchFiles(a1, v817);
            if ( v81 )
              goto LABEL_242;
            if ( (unsigned int)GetIntegerPolicyValue(22, 1, 0)
              || !(*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 664LL))(a1, 4)
              || (v119 = 1, !v846) )
            {
              v119 = 0;
            }
            *(_BYTE *)(a1 + 944) = v119;
            *(_BYTE *)(a1 + 953) = 0;
            CMsiEngine::SetForceRepair((CMsiEngine *)a1, 0);
            CMsiEngine::SetPatchingDownRevFiles((CMsiEngine *)a1, 0);
            *(_BYTE *)(a1 + 952) = 1;
            v865 = &MsiString::s_NullString;
            IMsiData::Release((IMsiData *)&MsiString::s_NullString);
            v865 = &MsiString::s_NullString;
            v120 = MsiString::MsiString((MsiString *)&v942, L"REINSTALL");
            v121 = v874;
            LOBYTE(v809) = 0;
            v122 = 0;
            if ( (unsigned int)ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, *(_QWORD *)v120, &v865, 1, a1 + 448, 0, v809) )
              v122 = (unsigned int)MsiString::TextSize((MsiString *)&v865) != 0;
            IMsiData::Release(v942);
            if ( v122 )
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
                (*(void (__fastcall **)(void *))(*(_QWORD *)v865 + 16LL))(v865);
                if ( v851 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v851 + 16LL))(v851);
                if ( v852 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v852 + 16LL))(v852);
                (*(void (__fastcall **)(IMsiData *))(*(_QWORD *)v848 + 16LL))(v848);
                (*(void (__fastcall **)(IMsiData *))(*(_QWORD *)v849 + 16LL))(v849);
                goto LABEL_263;
              }
            }
            v124 = CComPointer<IMsiStorage>::operator->(&v819);
            PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ProcessSingleFeaturePackage(a1, v124);
            if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
              goto LABEL_266;
            MsiString::MsiString((MsiString *)v868);
            v126 = MsiString::operator&(v868);
            v127 = MsiString::MsiString((MsiString *)v943, L"MSIUNINSTALLSUPERSEDEDCOMPONENTS");
            v128 = CComPointer<IMsiStorage>::operator->(v127);
            LOBYTE(v810) = 0;
            if ( !(unsigned int)ProcessCommandLine(v121, 0, 0, 0, 0, 0, 0, v128, v126, 1, a1 + 448, 0, v810)
              || (v129 = 1, !(unsigned int)MsiString::TextSize((MsiString *)v868)) )
            {
              v129 = 0;
            }
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v943);
            v130 = CComPointer<IMsiStorage>::operator->(&v819);
            LOBYTE(v131) = v129;
            PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ProcessSupersededPatches(a1, v130, 1, v131);
            if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
            {
              v132 = CComPointer<IMsiStorage>::operator->(&v819);
              PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ApplyPatchTransforms(a1, v132);
              if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
              {
                PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::OptimizeCustomActions(a1);
                if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
                {
                  PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::QueryPatchMetaDataForNewObsoletedAndSupercededMSPs(a1);
                  if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
                  {
                    if ( g_scServerContext == 2 && v846 || (v133 = 0, (a6 & 0x80000) != 0) )
                      v133 = 1;
                    v134 = CComPointer<IMsiStorage>::operator->(&v819);
                    LOBYTE(v135) = v133;
                    v136 = CMsiEngine::ProcessPatchesMarkedForUninstall(a1, v134, v135);
                    if ( v136
                      || (v137 = CComPointer<IMsiStorage>::operator->(&v819),
                          LOBYTE(v138) = v129,
                          (v136 = CMsiEngine::ProcessSupersededPatches(a1, v137, 0, v138)) != 0) )
                    {
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v868);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v865);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
                      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
                      v11 = v136;
                      goto LABEL_691;
                    }
                    if ( !v133 )
                      goto LABEL_290;
                    v139 = a6;
                    v140 = CComPointer<IMsiStorage>::operator->(&v819);
                    PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::GeneratePatchFileList(a1, v140, v139);
                    if ( !PatchMetaDataForNewObsoletedAndSupercededMSPs )
                    {
                      MsiString::MsiString((MsiString *)v913);
                      v141 = MsiString::operator&(v913);
                      v142 = MsiString::MsiString((MsiString *)v944, L"REINSTALLMODE");
                      v143 = CComPointer<IMsiStorage>::operator->(v142);
                      LOBYTE(v811) = 0;
                      LODWORD(v141) = ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, v143, v141, 1, a1 + 448, 0, v811);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v944);
                      if ( (_DWORD)v141 )
                      {
                        v892 = 0;
                        v144 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v913);
                        StringToModeBits(v144, L"rpoedcamusv", &v892);
                        if ( (v892 & 0x40) != 0 )
                        {
                          CMsiEngine::SetPatchingDownRevFiles((CMsiEngine *)a1, 1);
                          *(_BYTE *)(a1 + 944) = 0;
                        }
                      }
                      CMsiEngine::CheckForActiveMajorUpgradePatches((CMsiEngine *)a1);
                      CMsiEngine::DumpPatchFileListTable((CMsiEngine *)a1);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v913);
LABEL_290:
                      if ( g_scServerContext == 2 )
                      {
                        v145 = (CMsiPatchManager *)operator new(0x188u);
                        if ( v145 )
                        {
                          v146 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v819);
                          v147 = CMsiPatchManager::CMsiPatchManager(v145, (struct IMsiEngine *)a1, v146);
                        }
                        else
                        {
                          v147 = 0;
                        }
                        *(_QWORD *)(a1 + 936) = v147;
                        if ( !v147 )
                        {
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v868);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v865);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
LABEL_690:
                          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
                          v11 = 33;
                          goto LABEL_691;
                        }
                      }
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v868);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v865);
                      v856 = v12 & 0xFFFFFF3F;
LABEL_299:
                      if ( (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1) )
                      {
                        v148 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
                        if ( v867 != v148 )
                        {
                          v149 = CComPointer<IMsiStorage>::operator->(&v819);
                          v150 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
                          PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::ApplyLanguageTransform(
                                                                            a1,
                                                                            v150,
                                                                            v149);
                          if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
                            goto LABEL_268;
                        }
                      }
                      if ( !*(_QWORD *)(a1 + 176) )
                      {
                        Record = CreateRecord(3u);
                        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v899, Record);
                        v152 = CComPointer<IMsiStorage>::operator->(v899);
                        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v152 + 104LL))(v152, 1, 0);
                        v153 = CComPointer<IMsiStorage>::operator->(v899);
                        v154 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v153 + 104LL);
                        v155 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 88LL))(a1);
                        v154(v153, 2, v155);
                        v156 = CComPointer<IMsiStorage>::operator->(v899);
                        v157 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v156 + 104LL);
                        v158 = CComPointer<IMsiStorage>::operator->(&v819);
                        v159 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v158 + 216LL))(v158);
                        v157(v156, 3, v159);
                        v160 = CComPointer<IMsiStorage>::operator->(v899);
                        MsiUIMessageContext::Invoke(&g_MessageContext, 2332033024LL, v160);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v899);
                      }
                      LODWORD(v879) = 0;
                      do
                      {
                        v161 = MsiString::operator unsigned short const *(&v832);
                        v162 = MsiString::operator unsigned short const *(&v820);
                        v163 = v846 != 0;
                        v164 = CComPointer<IMsiStorage>::operator->(&v824);
                        v165 = CComPointer<IMsiStorage>::operator->(&v819);
                        LOBYTE(v797) = v163;
                        LOBYTE(v795) = 0;
                        v166 = CMsiEngine::InitializeTransforms(
                                 a1,
                                 v165,
                                 0,
                                 v164,
                                 1,
                                 0,
                                 v795,
                                 v797,
                                 &v895,
                                 v162,
                                 v161,
                                 &v873,
                                 &v864,
                                 &v872);
                        PatchMetaDataForNewObsoletedAndSupercededMSPs = v166;
                        if ( !v166 )
                          break;
                        if ( v166 != -2 )
                        {
                          IMsiData::Release(v873);
                          IMsiData::Release(v872);
                          goto LABEL_268;
                        }
                        v167 = MsiString::operator&(&v822);
                        v168 = MsiString::operator&(&v820);
                        v169 = v846;
                        v170 = v845;
                        v171 = v168;
                        v172 = MsiString::operator unsigned short const *(&v816);
                        v173 = MsiString::operator unsigned short const *(&v817);
                        v174 = CMsiEngine::ResolveSource(a1, v173, v172, v170, v169, v171, v167, 0);
                        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v914, v174);
                        if ( CComPointer<IMsiStorage>::operator->(v914) )
                        {
                          IMsiData::Release(v873);
                          IMsiData::Release(v872);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v914);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
                          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
                          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
                          v11 = 8;
                          goto LABEL_691;
                        }
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v914);
                        LODWORD(v879) = v879 + 1;
                      }
                      while ( (int)v879 < 2 );
                      v175 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                               a1,
                               L"ProductCode");
                      CComPointer<IMsiPath>::CComPointer<IMsiPath>(v880, v175);
                      v176 = MsiString::operator unsigned short const *(v880);
                      v177 = MsiString::Compare(&v817, 1, v176);
                      v894 = 0;
                      v178 = v177 == 0;
                      v179 = CComPointer<IMsiStorage>::operator->(&v830);
                      v180 = CComPointer<IMsiStorage>::operator->(v880);
                      v181 = CComPointer<IMsiStorage>::operator->(&v819);
                      LOBYTE(v802) = v178;
                      LOBYTE(v800) = v839;
                      *(_QWORD *)cchCount2b = v179;
                      v9 = v874;
                      CMsiEngine::ApplyAppCompatTransforms(
                        a1,
                        v884,
                        v874,
                        v181,
                        v180,
                        *(_QWORD *)cchCount2b,
                        2,
                        &v894,
                        v800,
                        v802,
                        &v841);
                      *(_DWORD *)(a1 + 608) |= v894;
                      if ( g_dmDiagnosticMode )
                      {
                        if ( v864 == 1 )
                        {
                          v182 = L"not";
                        }
                        else if ( v864 == 3 )
                        {
                          v182 = L"absolute";
                        }
                        else
                        {
                          v182 = L"relative";
                          if ( v864 != 2 )
                            v182 = L"??";
                        }
                        DebugString(
                          9,
                          0,
                          0,
                          L"Transforms are %s secure.",
                          v182,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                      }
                      v183 = CComPointer<IMsiStorage>::operator->(&v819);
                      if ( !(unsigned int)CMsiEngine::CreatePropertyTable(a1, v183, L"Property", 0) )
                      {
LABEL_320:
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v880);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
LABEL_321:
                        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
                        goto LABEL_691;
                      }
                      if ( !*(_QWORD *)(a1 + 176) )
                      {
                        v184 = (_WORD *)CAPITempBuffer<unsigned short,261>::operator[](&g_rgchLogFile, 0);
                        v185 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                        if ( *v184 )
                        {
                          v186 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(&g_rgchLogFile);
                          v187 = MsiString::MsiString((MsiString *)v946, v186);
                          v188 = CComPointer<IMsiStorage>::operator->(v187);
                          v189 = MsiString::MsiString((MsiString *)v945, L"MsiLogFileLocation");
                          v190 = CComPointer<IMsiStorage>::operator->(v189);
                          v185(a1, v190, v188);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v945);
                          v191 = (GUIDAndSequence *)v946;
                        }
                        else
                        {
                          v192 = MsiString::MsiString((MsiString *)v948, &Default);
                          v193 = CComPointer<IMsiStorage>::operator->(v192);
                          v194 = MsiString::MsiString((MsiString *)v947, L"MsiLogFileLocation");
                          v195 = CComPointer<IMsiStorage>::operator->(v194);
                          v185(a1, v195, v193);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v947);
                          v191 = (GUIDAndSequence *)v948;
                        }
                        GUIDAndSequence::~GUIDAndSequence(v191);
                      }
                      v196 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v819);
                      CMsiEngine::LogCommandLine((CMsiEngine *)a1, v9, v196);
                      v197 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                      v198 = CComPointer<IMsiStorage>::operator->(&v830);
                      v199 = MsiString::MsiString((MsiString *)v949, L"PackageCode");
                      v200 = CComPointer<IMsiStorage>::operator->(v199);
                      v197(a1, v200, v198);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v949);
                      v201 = v873;
                      v202 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
                      v203 = MsiString::MsiString((MsiString *)v950, L"RecacheTransforms");
                      v204 = CComPointer<IMsiStorage>::operator->(v203);
                      v202(a1, v204, v201);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v950);
                      v205 = v872;
                      v206 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
                      v207 = MsiString::MsiString((MsiString *)v951, L"TRANSFORMS");
                      v208 = CComPointer<IMsiStorage>::operator->(v207);
                      v206(a1, v208, v205);
                      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v951);
                      PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::PopulatePatchRemovalListProperty(a1);
                      if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
                      {
                        v125 = (GUIDAndSequence *)v880;
                        goto LABEL_267;
                      }
                      MsiString::operator=(&v824, v872);
                      IMsiData::Release(v873);
                      v209.lpVtbl = *(struct IUnknownVtbl **)a1;
                      if ( (unsigned int)(v864 - 2) <= 1 )
                      {
                        QueryInterface = v209.lpVtbl[7].QueryInterface;
                        v218 = MsiString::MsiString((MsiString *)v954, L"TRANSFORMSSECURE");
                        v219 = CComPointer<IMsiStorage>::operator->(v218);
                        ((void (__fastcall *)(__int64, __int64, __int64))QueryInterface)(a1, v219, 1);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v954);
                        v220 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
                        v221 = MsiString::MsiString((MsiString *)v955, L"TRANSFORMSATSOURCE");
                        v222 = CComPointer<IMsiStorage>::operator->(v221);
                        v220(a1, v222, 1);
                        v216 = (GUIDAndSequence *)v955;
                      }
                      else
                      {
                        Release = v209.lpVtbl[6].Release;
                        v211 = MsiString::MsiString((MsiString *)v952, L"TRANSFORMSSECURE");
                        v212 = CComPointer<IMsiStorage>::operator->(v211);
                        ((void (__fastcall *)(__int64, __int64, void ***))Release)(a1, v212, &g_MsiStringNull);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v952);
                        v213 = *(void (__fastcall **)(__int64, __int64, void ***))(*(_QWORD *)a1 + 160LL);
                        v214 = MsiString::MsiString((MsiString *)v953, L"TRANSFORMSATSOURCE");
                        v215 = CComPointer<IMsiStorage>::operator->(v214);
                        v213(a1, v215, &g_MsiStringNull);
                        v216 = (GUIDAndSequence *)v953;
                      }
                      GUIDAndSequence::~GUIDAndSequence(v216);
                      v223 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(
                               a1,
                               L"ProductCode");
                      CComPointer<IMsiPath>::CComPointer<IMsiPath>(v878, v223);
                      if ( g_dmDiagnosticMode )
                      {
                        v224 = v921;
                        if ( !v921 )
                          v224 = L"(none)";
                        DebugString(
                          9,
                          0,
                          0,
                          L"Product Code passed to Engine.Initialize:           '%s'",
                          v224,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                        if ( g_dmDiagnosticMode )
                        {
                          v225 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
                          DebugString(
                            9,
                            0,
                            0,
                            L"Product Code from property table before transforms: '%s'",
                            v225,
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
                        }
                      }
                      if ( (unsigned int)MsiString::TextSize((MsiString *)&v828) )
                      {
                        if ( !g_dmDiagnosticMode )
                          goto LABEL_343;
                        v226 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v828);
                        DebugString(
                          9,
                          0,
                          0,
                          L"Product Code from property table after multiple instance transforms: '%s'",
                          v226,
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
                        MsiString::operator=(&v828, &v817);
                      }
                      if ( g_dmDiagnosticMode )
                      {
                        v227 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v878);
                        DebugString(
                          9,
                          0,
                          0,
                          L"Product Code from property table after transforms:  '%s'",
                          v227,
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          L"(NULL)",
                          0,
                          0);
                      }
LABEL_343:
                      v228 = MsiString::operator unsigned short const *(v878);
                      if ( !(unsigned int)MsiString::Compare(&v817, 1, v228) )
                      {
                        if ( (unsigned int)MsiString::TextSize((MsiString *)&v829) )
                        {
                          v229 = MsiString::operator unsigned short const *(v878);
                          if ( !(unsigned int)MsiString::Compare(&v828, 1, v229) )
                          {
                            MsiString::operator=(&v821, &v817);
                            v230 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                            v231 = CComPointer<IMsiStorage>::operator->(&v817);
                            v232 = MsiString::MsiString((MsiString *)v956, L"MIGRATE");
                            v233 = CComPointer<IMsiStorage>::operator->(v232);
                            v230(a1, v233, v231);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v956);
                            v234 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
                            v235 = CComPointer<IMsiStorage>::operator->(&v817);
                            v236 = MsiString::MsiString((MsiString *)v957, L"PatchedProductCode");
                            v237 = CComPointer<IMsiStorage>::operator->(v236);
                            v234(a1, v237, v235);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v957);
                          }
                        }
                        MsiString::operator=(&v817, v878);
                        v238 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
                        ProductState = CMsiEngine::GetProductState(
                                         (CMsiEngine *)a1,
                                         v238,
                                         (enum Bool *)&v846,
                                         (enum Bool *)&v850);
                      }
                      if ( *(_BYTE *)(a1 + 98) && !v850 )
                        goto LABEL_354;
                      if ( (*(_DWORD *)(a1 + 584) & 0x4000) == 0
                        && !(unsigned int)MsiString::TextSize((MsiString *)&v817) )
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
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v878);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v880);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
                        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
                        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
                        v11 = 22;
                        goto LABEL_691;
                      }
                      if ( v841 )
                      {
                        if ( !v846 )
                        {
                          v239 = (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a1 + 184LL))(
                                   a1,
                                   L"ProductName");
                          CComPointer<IMsiPath>::CComPointer<IMsiPath>(v904, v239);
                          if ( !(unsigned int)MsiString::TextSize((MsiString *)v904) )
                            MsiString::operator=(v904, &v816);
                          v240 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v904);
                          DebugString(
                            21,
                            1u,
                            1018,
                            v240,
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
                          v241 = CComPointer<IMsiStorage>::operator->(&v816);
                          v11 = CMsiEngine::PostInitializeError(a1, 0, v241, 30);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v904);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v878);
                          goto LABEL_320;
                        }
                      }
                      else if ( !v846 )
                      {
                        if ( g_dmDiagnosticMode )
                        {
                          v242 = L"Product not registered: beginning first-time install";
                          goto LABEL_365;
                        }
LABEL_366:
                        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 104LL))(a1, 4, v846);
                        *(_DWORD *)(a1 + 68) = v846;
                        *(_DWORD *)(a1 + 72) = v850;
                        if ( !*(_QWORD *)(a1 + 176)
                          && g_scServerContext == 2
                          && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
                        {
                          v243 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
                          v244 = MsiString::MsiString((MsiString *)v958, L"MSIINSTALLPERUSER");
                          v245 = CComPointer<IMsiStorage>::operator->(v244);
                          v246 = v243(a1, v245);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v958);
                          if ( v246 == 0x80000000 )
                            v247 = 99;
                          else
                            v247 = v246 == 1;
                          SQMSession = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          CMsiSQMSession::RecordDWORD(SQMSession, 0x1053u, v247);
                          v249 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          IntegerPolicyValue = GetIntegerPolicyValue(0, 1, 0);
                          CMsiSQMSession::RecordDWORD(v249, 0x1056u, IntegerPolicyValue);
                          v251 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          v252 = GetIntegerPolicyValue(6, 1, 0);
                          CMsiSQMSession::RecordDWORD(v251, 0x1057u, v252);
                          iid = 0;
                          v253 = (const OLECHAR *)MsiString::operator unsigned short const *(&v817);
                          if ( IIDFromString(v253, &iid) )
                          {
                            v254 = 0;
                            if ( g_dmDiagnosticMode )
                            {
                              v255 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
                              DebugString(
                                10,
                                0,
                                0,
                                L"Failed to convert Product Code %s to GUID",
                                v255,
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
                            v254 = *(_DWORD *)&iid.Data4[4] ^ *(_DWORD *)iid.Data4 ^ *(_DWORD *)&iid.Data2 ^ iid.Data1;
                          }
                          v256 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
                          CMsiSQMSession::RecordDWORD(v256, 0x1055u, v254);
                        }
                        CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                        v257 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
                        if ( !(unsigned int)GetProductInfo(v257, L"AssignmentType") )
                        {
                          if ( !(unsigned int)MsiString::TextSize((MsiString *)&v821) )
                            goto LABEL_392;
                          CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                          v258 = (const WCHAR *)MsiString::operator unsigned short const *(&v821);
                          if ( !(unsigned int)GetProductInfo(v258, L"AssignmentType") )
                            goto LABEL_392;
                        }
                        v259 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(&String);
                        v260 = MsiString::MsiString((MsiString *)v959, v259);
                        v261 = MsiString::operator int(v260);
                        v262 = v261 == 1;
                        v847 = v262;
                        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v959);
                        if ( g_dmDiagnosticMode )
                        {
                          v263 = L"machine";
                          if ( v261 != 1 )
                            v263 = L"user";
                          DebugString(
                            9,
                            0,
                            0,
                            L"Determined that existing product (either this product or the product being upgraded with a p"
                             "atch) is installed per-%s.",
                            v263,
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            L"(NULL)",
                            0,
                            0);
                        }
                        if ( v261 == 1 )
                          goto LABEL_391;
                        CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                        v264 = (const WCHAR *)MsiString::operator unsigned short const *(&v817);
                        if ( !(unsigned int)GetProductInfo(v264, L"DeploymentFlags") )
                        {
                          if ( !(unsigned int)MsiString::TextSize((MsiString *)&v821) )
                          {
LABEL_391:
                            v847 = v262;
                            goto LABEL_392;
                          }
                          CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
                          v265 = (const WCHAR *)MsiString::operator unsigned short const *(&v821);
                          if ( !(unsigned int)GetProductInfo(v265, L"DeploymentFlags") )
                          {
LABEL_392:
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v878);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v880);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
                            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
                            v12 = v856;
                            goto LABEL_393;
                          }
                        }
                        v266 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(&String);
                        v267 = strtol(v266);
                        if ( IsInstalledPerUser(v267) )
                        {
                          v268.lpVtbl = *(struct IUnknownVtbl **)a1;
                          v842 = 1;
                          v269 = v268.lpVtbl[7].QueryInterface;
                          v270 = MsiString::MsiString((MsiString *)v960, L"MSIINSTALLPERUSER");
                          v271 = CComPointer<IMsiStorage>::operator->(v270);
                          ((void (__fastcall *)(__int64, __int64, __int64))v269)(a1, v271, 1);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v960);
                          v272 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
                          v273 = MsiString::MsiString((MsiString *)v961, L"MSIINTERNALINSTALLEDPERUSER");
                          v274 = CComPointer<IMsiStorage>::operator->(v273);
                          v272(a1, v274, 1);
                          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v961);
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
                        v242 = L"Product registered: entering maintenance mode";
LABEL_365:
                        DebugString(
                          9,
                          0,
                          0,
                          v242,
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
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v868);
LABEL_266:
            v125 = (GUIDAndSequence *)&v865;
LABEL_267:
            GUIDAndSequence::~GUIDAndSequence(v125);
LABEL_268:
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v848);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v849);
LABEL_263:
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v843);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v844);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v840);
LABEL_264:
            CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
            GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
            v11 = PatchMetaDataForNewObsoletedAndSupercededMSPs;
            goto LABEL_691;
          }
          if ( !v81 )
            goto LABEL_241;
        }
LABEL_242:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v851);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v852);
LABEL_243:
        IMsiData::Release(v848);
        IMsiData::Release(v849);
        goto LABEL_244;
      }
    }
    else
    {
      v856 = v12;
      if ( !v82 )
        goto LABEL_299;
    }
    *(_BYTE *)(a1 + 944) = 0;
    goto LABEL_299;
  }
  if ( !(unsigned int)CMsiEngine::CreatePropertyTable(a1, v819, L"Property", 0) )
  {
LABEL_46:
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
    IMsiData::Release(v821);
    IMsiData::Release(v822);
    IMsiData::Release(v820);
    IMsiData::Release(v818);
    IMsiData::Release(v816);
    goto LABEL_245;
  }
LABEL_393:
  v900 = 0;
  v275 = a1 + 448;
  v276 = MsiString::MsiString((MsiString *)v962, L"ALLUSERS");
  v277 = CComPointer<IMsiStorage>::operator->(v276);
  LOBYTE(v804) = 0;
  ProcessCommandLine(v9, 0, 0, 0, 0, 0, 0, v277, &v900, 1, a1 + 448, 0, v804);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v962);
  if ( !*(_QWORD *)(a1 + 176)
    && (!g_scServerContext || g_scServerContext == 2 && (unsigned int)(dword_180309774 - 2) <= 1)
    && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
  {
    v278 = 3;
    if ( v900 )
    {
      if ( (*(unsigned int (__fastcall **)(IMsiData *))(*(_QWORD *)v900 + 32LL))(v900) == 2 )
        v278 = 2;
      else
        v278 = (*(__int64 (__fastcall **)(IMsiData *))(*(_QWORD *)v900 + 56LL))(v900) != 0;
    }
    v279 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
    CMsiSQMSession::RecordDWORD(v279, 0xE1Fu, v278);
  }
  v280 = v900;
  if ( v900 )
  {
    v281 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
    v282 = MsiString::MsiString((MsiString *)v963, L"ALLUSERS");
    v283 = CComPointer<IMsiStorage>::operator->(v282);
    v281(a1, v283, v280);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v963);
    IMsiData::Release(v900);
  }
  v915 = 0;
  v284 = MsiString::MsiString((MsiString *)v964, L"MSIINSTALLPERUSER");
  v285 = CComPointer<IMsiStorage>::operator->(v284);
  LOBYTE(v812) = 0;
  ProcessCommandLine(v9, 0, 0, 0, 0, 0, 0, v285, &v915, 1, a1 + 448, 0, v812);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v964);
  v286 = v915;
  if ( v915 )
  {
    v287 = *(void (__fastcall **)(__int64, __int64, IMsiData *))(*(_QWORD *)a1 + 160LL);
    v288 = MsiString::MsiString((MsiString *)v965, L"MSIINSTALLPERUSER");
    v289 = CComPointer<IMsiStorage>::operator->(v288);
    v287(a1, v289, v286);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v965);
    IMsiData::Release(v915);
  }
  v290 = *(_QWORD **)a1;
  if ( v847 == -1 )
  {
    v291 = (__int64 (__fastcall *)(__int64, __int64))v290[24];
    v292 = MsiString::MsiString((MsiString *)v966, L"ALLUSERS");
    v293 = CComPointer<IMsiStorage>::operator->(v292);
    LODWORD(v291) = v291(a1, v293);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v966);
    v294.lpVtbl = *(struct IUnknownVtbl **)a1;
    if ( (_DWORD)v291 == 2 )
    {
      v295 = v294.lpVtbl[8].QueryInterface;
      v296 = MsiString::MsiString((MsiString *)v967, L"MSIINSTALLPERUSER");
      v297 = CComPointer<IMsiStorage>::operator->(v296);
      LODWORD(v295) = ((__int64 (__fastcall *)(__int64, __int64))v295)(a1, v297);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v967);
      v298.lpVtbl = *(struct IUnknownVtbl **)a1;
      if ( (_DWORD)v295 == 1 )
      {
        v299 = v298.lpVtbl[6].Release;
        v847 = 0;
        v300 = MsiString::MsiString((MsiString *)v969, &Default);
        v301 = CComPointer<IMsiStorage>::operator->(v300);
        v302 = MsiString::MsiString((MsiString *)v968, L"ALLUSERS");
        v303 = CComPointer<IMsiStorage>::operator->(v302);
        ((void (__fastcall *)(__int64, __int64, __int64))v299)(a1, v303, v301);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v968);
        v842 = 1;
        v304 = (GUIDAndSequence *)v969;
      }
      else
      {
        v305 = ((__int64 (__fastcall *)(__int64, __int64))v298.lpVtbl[24].Release)(a1, 64);
        v306.lpVtbl = *(struct IUnknownVtbl **)a1;
        if ( v305 )
        {
          v307 = v306.lpVtbl[6].Release;
          v847 = 0;
          v308 = MsiString::MsiString((MsiString *)v971, &Default);
          v309 = CComPointer<IMsiStorage>::operator->(v308);
          v310 = MsiString::MsiString((MsiString *)v970, L"ALLUSERS");
          v311 = CComPointer<IMsiStorage>::operator->(v310);
          ((void (__fastcall *)(__int64, __int64, __int64))v307)(a1, v311, v309);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v970);
          v304 = (GUIDAndSequence *)v971;
        }
        else
        {
          v312 = v306.lpVtbl[7].QueryInterface;
          v847 = 1;
          v313 = MsiString::MsiString((MsiString *)v972, L"ALLUSERS");
          v314 = CComPointer<IMsiStorage>::operator->(v313);
          ((void (__fastcall *)(__int64, __int64, __int64))v312)(a1, v314, 1);
          v304 = (GUIDAndSequence *)v972;
        }
      }
    }
    else
    {
      v304 = (GUIDAndSequence *)v973;
      v315 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *))v294.lpVtbl[7].Release)(a1, L"ALLUSERS");
      v316 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v973, v315);
      v847 = MsiString::TextSize(v316) != 0;
    }
  }
  else if ( v847 == 1 )
  {
    v317 = (void (__fastcall *)(__int64, __int64, __int64))v290[21];
    v318 = MsiString::MsiString((MsiString *)v974, L"ALLUSERS");
    v319 = CComPointer<IMsiStorage>::operator->(v318);
    v317(a1, v319, 1);
    v304 = (GUIDAndSequence *)v974;
  }
  else
  {
    v320 = (void (__fastcall *)(__int64, __int64, __int64))v290[20];
    v321 = MsiString::MsiString((MsiString *)v976, &Default);
    v322 = CComPointer<IMsiStorage>::operator->(v321);
    v323 = MsiString::MsiString((MsiString *)v975, L"ALLUSERS");
    v324 = CComPointer<IMsiStorage>::operator->(v323);
    v320(a1, v324, v322);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v975);
    v304 = (GUIDAndSequence *)v976;
  }
  GUIDAndSequence::~GUIDAndSequence(v304);
  v325 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v326 = MsiString::MsiString((MsiString *)v977, L"MSIINSTALLPERUSER");
  v327 = CComPointer<IMsiStorage>::operator->(v326);
  LODWORD(v325) = v325(a1, v327);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v977);
  if ( (_DWORD)v325 != 1 )
  {
    v328 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
    v329 = MsiString::MsiString((MsiString *)v979, &Default);
    v330 = CComPointer<IMsiStorage>::operator->(v329);
    v331 = MsiString::MsiString((MsiString *)v978, L"MSIINSTALLPERUSER");
    v332 = CComPointer<IMsiStorage>::operator->(v331);
    v328(a1, v332, v330);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v978);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v979);
  }
  v333 = 0;
  if ( !v859 && (v884 && *v884 || *(_QWORD *)(a1 + 168)) )
  {
    if ( !v823 && g_scServerContext == 2 )
    {
      v334 = *(_QWORD *)(a1 + 176);
      if ( v334 )
      {
        v335 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v334 + 576LL))(v334);
        v62 = g_dmDiagnosticMode == 0;
        *(_BYTE *)(a1 + 601) = v335;
        if ( !v62 )
        {
          v336 = L"is";
          if ( !v335 )
            v336 = L"is not";
          DebugString(
            10,
            0,
            0,
            L"MSI_LUA: Nested installation UAC elevation tracks that of parent (%s elevated)",
            v336,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
      }
      v337 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
      v863 = IsProductManaged(v337);
      v875 = 3;
      v338 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
      PackedGUID = GetPackedGUID(v338);
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(v905, PackedGUID);
      v340 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v905);
      if ( GetProductAssignmentType(v340, (enum iaaAppAssignment *)&v875) )
      {
        v341 = 3;
        v875 = 3;
      }
      else
      {
        v341 = v875;
      }
      v855[0] = 0;
      v862 = v341 == 0;
      LODWORD(v879) = a6;
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 504LL))(a1) == 4
        && (!*(_BYTE *)(a1 + 98) || *(_BYTE *)(a1 + 99)) )
      {
        LODWORD(v879) = a6 & 0xFFEFFFFF;
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
      v856 = *(_DWORD *)(a1 + 608);
      if ( !*(_BYTE *)(a1 + 98) || (v839 = 1, *(_BYTE *)(a1 + 99)) )
        v839 = 0;
      v342 = v850 != 0;
      v343 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
      v344 = *(_DWORD *)(a1 + 596);
      v345 = v343;
      v346 = CComPointer<IMsiStorage>::operator->(&v819);
      v347 = CComPointer<IMsiStorage>::operator->(&v818);
      LOBYTE(v813) = v842;
      LOBYTE(v803) = v839;
      LOBYTE(v798) = v862;
      LOBYTE(v796) = v863;
      LOBYTE(cchCount2a) = v342;
      LOBYTE(lpString2a) = v345 & 1;
      v348 = ElevatedCredentialsPromptRequired(
               v347,
               v346,
               v344,
               v861,
               lpString2a,
               cchCount2a,
               v796,
               v798,
               v879,
               v869,
               v803,
               v856,
               v813,
               v855);
      switch ( v348 )
      {
        case -1:
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v905);
          goto LABEL_690;
        case 2:
          if ( !*(_BYTE *)(a1 + 601) )
            CMsiEngine::FSetPendingElevatedCredentialsPrompt((CMsiEngine *)a1);
          break;
        case 1:
          if ( !*(_BYTE *)(a1 + 601) )
          {
            v349 = 1;
            if ( v846 )
              v349 = 4;
            if ( MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
            {
              v350 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
              CMsiSQMSession::RecordElevationCause(v350, 5);
            }
            v351 = CComPointer<IMsiStorage>::operator->(&v819);
            PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::EnginePromptForElevatedCredentials(
                                                              a1,
                                                              v351,
                                                              v349);
            if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
            {
              *(_BYTE *)(a1 + 601) = 0;
              v352 = (GUIDAndSequence *)v905;
LABEL_456:
              GUIDAndSequence::~GUIDAndSequence(v352);
              goto LABEL_264;
            }
            *(_BYTE *)(a1 + 601) = 1;
          }
          break;
        default:
          if ( v855[0] )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 584LL))(a1);
          break;
      }
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v905);
      v9 = v874;
    }
    v353 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
    v354 = MsiString::MsiString((MsiString *)v980, L"ProductState");
    v355 = CComPointer<IMsiStorage>::operator->(v354);
    v353(a1, v355, (unsigned int)ProductState);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v980);
    if ( v846 )
    {
      v356 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v357 = MsiString::MsiString((MsiString *)v981, L"ProductToBeRegistered");
      v358 = CComPointer<IMsiStorage>::operator->(v357);
      v356(a1, v358, 1);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v981);
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v817) )
    {
      v359 = *(IMsiData **)(a1 + 416);
      if ( v359 )
        IMsiData::Release(v359);
      v360 = (IMsiData *)CComPointer<IMsiStorage>::operator->(&v817);
      *(_QWORD *)(a1 + 416) = v360;
      IMsiData::AddRef(v360);
    }
    v361 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 296LL))(a1);
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v866, v361);
    MsiString::operator=(a1 + 616, &g_MsiStringNull);
    v362 = MsiString::operator&(&v837);
    v363 = MsiString::MsiString((MsiString *)v982, L"MSIPACKAGEDOWNLOADLOCALCOPY");
    v364 = CComPointer<IMsiStorage>::operator->(v363);
    LOBYTE(v813) = 0;
    ProcessCommandLine(v9, 0, 0, 0, 0, 0, 0, v364, v362, 1, 0, 0, v813);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v982);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v837) )
      MsiString::operator=(a1 + 616, &v837);
    if ( !*(_BYTE *)(a1 + 577) )
    {
      if ( !v850 || (v365 = CComPointer<IMsiStorage>::operator->(&v816), !(unsigned int)IsCachedPackage(a1, v365, 0, 0)) )
      {
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v901, 0);
        MsiString::MsiString((MsiString *)v906);
        v366 = *(_QWORD *)(a1 + 128);
        v367 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v366 + 360LL);
        v368 = MsiString::operator&(v906);
        v369 = CComPointer<IEnumMsiRecord>::operator=(v901);
        v370 = MsiString::operator unsigned short const *(&v816);
        v371 = v367(v366, v370, v369, v368);
        v372 = CComPointer<IMsiDatabase>::operator=(&v853, v371);
        if ( CComPointer<IMsiStorage>::operator->(v372) )
        {
          v373 = CComPointer<IMsiStorage>::operator->(&v816);
          v374 = CComPointer<IMsiStorage>::operator->(&v853);
          v375 = 5;
LABEL_473:
          v11 = CMsiEngine::PostInitializeError(a1, v374, v373, v375);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v906);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v901);
LABEL_474:
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v866);
          goto LABEL_321;
        }
        v376 = CComPointer<IMsiStorage>::operator->(v901);
        v377 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v376 + 56LL))(v376);
        v378 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v983, v377);
        v379 = MsiString::operator unsigned short const *(v378);
        v380 = MsiString::operator unsigned short const *(v866);
        LOBYTE(v381) = v850 == 0;
        LOBYTE(v379) = FSourceIsAllowed(*(_QWORD *)(a1 + 128), v381, v380, v379, 0);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v983);
        if ( !(_BYTE)v379 && g_scServerContext && !*(_BYTE *)(a1 + 601) )
        {
          if ( MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
          {
            v382 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
            CMsiSQMSession::RecordElevationCause(v382, 4);
          }
          v383 = CComPointer<IMsiStorage>::operator->(&v819);
          lpString2a = v869;
          if ( (unsigned int)CMsiEngine::EnginePromptForElevatedCredentials(a1, v383, 1) )
          {
            v373 = CComPointer<IMsiStorage>::operator->(&v816);
            v374 = CComPointer<IMsiStorage>::operator->(&v853);
            v375 = 21;
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
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v906);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v901);
      }
    }
    CTempBuffer<unsigned short,39>::CTempBuffer<unsigned short,39>(v1064);
    *(_WORD *)CComPointer<IMsiStorage>::operator->(v1064) = 0;
    v384 = (*(__int64 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)a1 + 184LL))(a1, L"PackageCode");
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v886, v384);
    CTempBuffer<unsigned short,39>::operator CTempBufferRef<unsigned short> &(v1064);
    v385 = (const WCHAR *)MsiString::operator unsigned short const *(v866);
    GetProductInfo(v385, L"PackageCode");
    v386 = CComPointer<IMsiStorage>::operator->(v1064);
    if ( !(unsigned int)MsiString::Compare(v886, 1, v386) )
    {
      v387 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v388 = MsiString::MsiString((MsiString *)v984, L"PackagecodeChanging");
      v389 = CComPointer<IMsiStorage>::operator->(v388);
      v387(a1, v389, 1);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v984);
    }
    if ( (a6 & 0x80u) != 0
      || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 2) != 0
      || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) != 0
      || !*(_DWORD *)(a1 + 68)
      || (v12 |= 0x100u,
          v390 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
                   a1,
                   L"PackagecodeChanging"),
          v391 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v985, v390),
          v392 = 1,
          !(unsigned int)MsiString::TextSize(v391)) )
    {
      v392 = 0;
    }
    if ( (v12 & 0x100) != 0 )
    {
      v12 &= ~0x100u;
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v985);
    }
    if ( v392 )
    {
      v393 = CComPointer<IMsiStorage>::operator->(v866);
      v11 = CMsiEngine::PostInitializeError(a1, 0, v393, 24);
LABEL_497:
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v886);
      CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>(v1064);
      goto LABEL_474;
    }
    MsiString::operator=(a1 + 528, &g_MsiStringNull);
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v816) == 58 )
    {
      MsiString::operator=(a1 + 528, &v816);
    }
    else
    {
      if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) == 0
        && !v823
        && (unsigned int)MsiString::TextSize((MsiString *)v866) )
      {
        MsiString::MsiString((MsiString *)v916);
        v394 = MsiString::TextSize((MsiString *)&v821);
        v395 = (IMsiData **)v866;
        if ( v394 )
          v395 = &v821;
        MsiString::operator=(v916, v395);
        CTempBuffer<unsigned short,100>::operator CTempBufferRef<unsigned short> &(&String);
        v396 = (const WCHAR *)MsiString::operator unsigned short const *(v916);
        if ( (unsigned int)GetProductInfo(v396, L"PackageName") )
        {
          if ( *(_WORD *)CTempBuffer<unsigned short,100>::operator[](&String, 0) )
          {
            v397 = CComPointer<IMsiStorage>::operator->(&String);
            MsiString::operator=(a1 + 528, v397);
            if ( g_dmDiagnosticMode )
            {
              v398 = (const unsigned __int16 *)MsiString::operator unsigned short const *(a1 + 528);
              DebugString(
                9,
                0,
                0,
                L"Package name retrieved from configuration data: '%s'",
                v398,
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
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v916);
      }
      if ( !(unsigned int)MsiString::TextSize((MsiString *)(a1 + 528)) )
      {
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v907, 0);
        v399 = *(_QWORD *)(a1 + 128);
        v400 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v399 + 360LL);
        v401 = MsiString::operator&(a1 + 528);
        v402 = CComPointer<IEnumMsiRecord>::operator=(v907);
        v403 = MsiString::operator unsigned short const *(&v816);
        v404 = v400(v399, v403, v402, v401);
        v405 = CComPointer<IMsiDatabase>::operator=(&v853, v404);
        if ( CComPointer<IMsiStorage>::operator->(v405) )
        {
          v406 = CComPointer<IMsiStorage>::operator->(&v818);
          v407 = CComPointer<IMsiStorage>::operator->(&v853);
          v11 = CMsiEngine::PostInitializeError(a1, v407, v406, 5);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v907);
          goto LABEL_497;
        }
        if ( g_dmDiagnosticMode )
        {
          v408 = (const unsigned __int16 *)MsiString::operator unsigned short const *(a1 + 528);
          DebugString(
            9,
            0,
            0,
            L"Package name extracted from package path: '%s'",
            v408,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        v409 = CComPointer<IMsiStorage>::operator->(v907);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v409 + 424LL))(v409) )
        {
          CTempBuffer<unsigned short,20>::CTempBuffer<unsigned short,20>(v1065);
          CTempBuffer<unsigned short,20>::operator CTempBufferRef<unsigned short> &(v1065);
          v410 = (const WCHAR *)MsiString::operator unsigned short const *(&v816);
          if ( (unsigned __int8)DetermineLongFileNameOnly(v410) )
          {
            v411 = CComPointer<IMsiStorage>::operator->(v1065);
            MsiString::operator=(a1 + 528, v411);
            if ( g_dmDiagnosticMode )
            {
              v412 = (const unsigned __int16 *)MsiString::operator unsigned short const *(a1 + 528);
              DebugString(
                9,
                0,
                0,
                L"Package to be registered: '%s'",
                v412,
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                L"(NULL)",
                0,
                0);
            }
          }
          CTempBuffer<unsigned short,20>::~CTempBuffer<unsigned short,20>(v1065);
        }
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v907);
      }
    }
    if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) & 1) != 0
      && (unsigned int)MsiString::TextSize((MsiString *)&v829) )
    {
      MsiString::MsiString((MsiString *)v908);
      v413 = (const struct IMsiString **)MsiString::operator&(v908);
      v414 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v816);
      v415 = SplitPath(v414, v413, 0);
      v416 = CComPointer<IMsiDatabase>::operator=(&v853, v415);
      if ( CComPointer<IMsiStorage>::operator->(v416) )
      {
        v417 = CComPointer<IMsiStorage>::operator->(&v818);
        v418 = CComPointer<IMsiStorage>::operator->(&v853);
        v11 = CMsiEngine::PostInitializeError(a1, v418, v417, 5);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v908);
        goto LABEL_497;
      }
      v419 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
      v420 = CComPointer<IMsiStorage>::operator->(v908);
      v421 = MsiString::MsiString((MsiString *)v986, L"TARGETDIR");
      v422 = CComPointer<IMsiStorage>::operator->(v421);
      v419(a1, v422, v420);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v986);
      if ( (*(char (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) < 0 )
      {
        v423 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
        v424 = MsiString::MsiString((MsiString *)v987, L"SHORTFILENAMES");
        v425 = CComPointer<IMsiStorage>::operator->(v424);
        v423(a1, v425, 1);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v987);
      }
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v908);
    }
    v426 = CComPointer<IMsiStorage>::operator->(&v819);
    PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::LoadMessageHeaders(a1, v426);
    if ( PatchMetaDataForNewObsoletedAndSupercededMSPs )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v886);
      CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>(v1064);
      v352 = (GUIDAndSequence *)v866;
      goto LABEL_456;
    }
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v886);
    CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>(v1064);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v866);
    v333 = 0;
    v275 = a1 + 448;
  }
  if ( CComPointer<IMsiStorage>::operator->(&v825) )
  {
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v887, 0);
    v427 = CComPointer<IMsiStorage>::operator->(&v825);
    v428 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v427 + 56LL);
    v429 = CComPointer<IEnumMsiRecord>::operator=(v887);
    v430 = v428(v427, L"AdminProperties", 0, v429);
    CComPointer<IMsiDatabase>::operator=(&v853, v430);
    v333 = 0;
    if ( !CComPointer<IMsiStorage>::operator->(&v853) && CComPointer<IMsiStorage>::operator->(v887) )
    {
      *(_BYTE *)(a1 + 96) = 1;
      v431 = CComPointer<IMsiStorage>::operator->(v887);
      v432 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v431 + 56LL))(v431);
      CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(v1062, (unsigned __int64)(int)(v432 + 1) >> 1);
      if ( !CComPointer<IMsiStorage>::operator->(v1062) )
      {
        v433 = PostError(2346);
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v922, v433);
        v434 = CComPointer<IMsiStorage>::operator->(v922);
        v11 = CMsiEngine::PostInitializeError(a1, v434, &g_MsiStringNull, 33);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v922);
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(v1062);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v887);
        goto LABEL_321;
      }
      v435 = CComPointer<IMsiStorage>::operator->(v887);
      v436 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v435 + 64LL);
      v437 = CComPointer<IMsiStorage>::operator->(v1062);
      v436(v435, v437, v432);
      v438 = CComPointer<IMsiStorage>::operator->(v1062);
      v333 = 0;
      LOBYTE(v813) = 0;
      ProcessCommandLine(v438, 0, 0, 0, 0, 0, 0, 0, 0, 0, v275, a1, v813);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(v1062);
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v887);
  }
  if ( !v823 )
  {
    v439 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
    v440 = *(_BYTE *)(a1 + 601);
    v441 = v439 & 1;
    v442 = v847 != 0;
    v443 = v850 != 0;
    v444 = MsiString::operator unsigned short const *(&v817);
    LOBYTE(v445) = v440;
    LOBYTE(lpString2a) = v441;
    LOBYTE(v446) = v442;
    LOBYTE(v447) = v443;
    v448 = AcceptProduct(v444, v447, v446, v445, lpString2a);
    v333 = 0;
    *(_DWORD *)(a1 + 580) = v448;
    if ( !v448 )
      goto LABEL_785;
    v449 = v448 - 1;
    if ( v449 )
    {
      if ( (unsigned int)(v449 - 1) <= 1 )
      {
        *(_BYTE *)(a1 + 579) = 1;
        g_fRunScriptElevated = 1;
        goto LABEL_544;
      }
LABEL_785:
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
      v11 = 21;
      goto LABEL_691;
    }
    *(_BYTE *)(a1 + 579) = 0;
    g_fRunScriptElevated = 0;
  }
LABEL_544:
  v923 = 0;
  v450 = MsiString::MsiString((MsiString *)v988, L"TARGETDIR");
  v451 = CComPointer<IMsiStorage>::operator->(v450);
  v452 = v874;
  LOBYTE(v813) = 0;
  v453 = a1 + 448;
  ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, v451, &v923, 1, a1 + 448, 0, v813);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v988);
  if ( v923 )
  {
    v454 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v923 + 80LL))(v923);
    MsiString::MsiString((MsiString *)v870, v454);
    if ( (unsigned int)MsiString::Compare(v870, 7, L"Config.Msi") )
    {
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(v882, 0);
      v455 = (struct IMsiPath **)CComPointer<IEnumMsiRecord>::operator=(v882);
      v456 = (const struct IMsiString *)CComPointer<IMsiStorage>::operator->(v870);
      PathObject = CMsiEngine::CreatePathObject((CMsiEngine *)a1, v456, v455);
      v458 = CComPointer<IMsiDatabase>::operator=(&v853, PathObject);
      if ( CComPointer<IMsiStorage>::operator->(v458) )
      {
        if ( g_dmDiagnosticMode )
        {
          v498 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v870);
          DebugString(
            9,
            0,
            0,
            L"Error : Invalid string could not crate path %s",
            v498,
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
      v459 = CComPointer<IMsiStorage>::operator->(v882);
      v460 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v459 + 72LL))(v459);
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(v909, v460);
      v461 = CComPointer<IMsiStorage>::operator->(v909);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v461 + 56LL))(v461) != 4 )
      {
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v902, 0);
        v462 = *(_QWORD *)(a1 + 128);
        v463 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v462 + 120LL);
        v464 = CComPointer<IEnumMsiRecord>::operator=(v902);
        v465 = CComPointer<IMsiStorage>::operator->(v909);
        v466 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v465 + 168LL))(v465);
        v467 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v989, v466);
        v468 = MsiString::operator unsigned short const *(v467);
        v469 = v463(v462, v468, v464);
        v470 = CComPointer<IMsiDatabase>::operator=(&v853, v469);
        v471 = CComPointer<IMsiStorage>::operator->(v470);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v989);
        if ( v471 )
        {
          if ( g_dmDiagnosticMode )
          {
            v486 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v870);
            v487 = L"Error : Could Not create path in the given volume: %s";
            goto LABEL_582;
          }
          goto LABEL_583;
        }
        v472 = CComPointer<IMsiStorage>::operator->(v902);
        v473 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v472 + 104LL);
        v474 = MsiString::MsiString((MsiString *)v990, L"Config.Msi");
        v475 = CComPointer<IMsiStorage>::operator->(v474);
        v476 = v473(v472, v475);
        v477 = CComPointer<IMsiDatabase>::operator=(&v853, v476);
        v478 = CComPointer<IMsiStorage>::operator->(v477);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v990);
        v333 = 0;
        if ( v478 )
        {
          if ( g_dmDiagnosticMode )
          {
            v486 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v870);
            v487 = L"Error : Could Not add Backupfolder string to verify TARGETDIR: %s";
            goto LABEL_582;
          }
LABEL_583:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v902);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v909);
LABEL_584:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v882);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v870);
LABEL_585:
          CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
          v11 = 3;
          goto LABEL_691;
        }
        v479 = CComPointer<IMsiStorage>::operator->(v882);
        v480 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v479 + 56LL))(v479);
        v481 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v992, v480);
        v482 = CComPointer<IMsiStorage>::operator->(v902);
        v483 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v482 + 56LL))(v482);
        v484 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v991, v483);
        v485 = MsiString::operator unsigned short const *(v484);
        LODWORD(v481) = MsiString::Compare(v481, 3, v485);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v991);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v992);
        if ( (_DWORD)v481 )
        {
          if ( g_dmDiagnosticMode )
          {
            v486 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v870);
            v487 = L"Error : Invalid TARGETDIR: %s";
LABEL_582:
            DebugString(9, 0, 0, v487, v486, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
            goto LABEL_583;
          }
          goto LABEL_583;
        }
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v902);
        v453 = a1 + 448;
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v909);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v882);
    }
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v870);
  }
  v488 = 0;
  if ( *(_BYTE *)(a1 + 579) )
  {
    if ( !IsAdmin() && !*(_BYTE *)(a1 + 601) )
    {
      v12 |= 0x200u;
      v489 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"EnableUserControl");
      v490 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v993, v489);
      if ( !(unsigned int)MsiString::TextSize(v490) )
        v488 = (unsigned int)GetIntegerPolicyValue(13, 1, 0) != 1;
    }
  }
  if ( (v12 & 0x200) != 0 )
  {
    v12 &= ~0x200u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v993);
  }
  if ( v488 )
  {
    v491 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v492 = MsiString::MsiString((MsiString *)v994, L"RestrictedUserControl");
    v493 = CComPointer<IMsiStorage>::operator->(v492);
    v491(a1, v493, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v994);
    v333 = 1;
  }
  LOBYTE(v814) = v333;
  v494 = 0;
  if ( !(unsigned int)ProcessCommandLine(v452, 0, 0, 0, 0, 0, 0, 0, 0, 1, v453, a1, v814) )
    goto LABEL_585;
  if ( g_scServerContext == 2 )
  {
    v495 = 1;
    LOBYTE(v494) = (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 784LL))(a1) != 0;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 784LL))(a1)
      || (Instance = 0, !*(_QWORD *)(a1 + 176)) )
    {
      Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(v494);
    }
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 784LL))(a1)
      && Instance
      && CRestartManagerWrapper::HasSessionHandle(Instance) )
    {
      v497 = CRestartManagerWrapper::EndSession(Instance);
      if ( v497 != 1626 )
      {
        if ( v497 )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"RESTART MANAGER: Failed while closing session. Error: %d",
              (const unsigned __int16 *)v497,
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
      CRestartManagerWrapper::DestroyInstance(v494);
      Instance = (CRestartManagerWrapper *)CRestartManagerWrapper::GetInstance(v494);
    }
    v499 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(
             a1,
             L"MSIRESTARTMANAGERCONTROL");
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v910, v499);
    v500 = GetIntegerPolicyValue(26, 1, 0);
    if ( (unsigned int)MsiString::TextSize((MsiString *)v910) )
    {
      if ( (unsigned int)MsiString::Compare(v910, 0, L"Disable") == 1 )
      {
        v495 = 0;
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
          v924 = 0;
          v501 = MsiString::MsiString((MsiString *)v995, L"MSIRESTARTMANAGERCONTROL");
          v502 = CComPointer<IMsiStorage>::operator->(v501);
          LOBYTE(v815) = 0;
          ProcessCommandLine(v874, 0, 0, 0, 0, 0, 0, v502, &v924, 1, a1 + 448, 0, v815);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v995);
          if ( v924 )
          {
            IMsiData::Release(v924);
            v503 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
            v504 = 1;
          }
          else
          {
            v503 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
            v504 = 2;
          }
          goto LABEL_606;
        }
      }
    }
    else if ( v500 == 1 )
    {
      v495 = 0;
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
        v503 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        v504 = 3;
LABEL_606:
        CMsiSQMSession::RecordDWORD(v503, 0xE25u, v504);
      }
    }
    if ( Instance )
    {
      if ( !v495 )
      {
        Disable = CRestartManagerWrapper::GetDisable(Instance);
        CRestartManagerWrapper::SetDisable(Instance, Disable | 4u);
LABEL_624:
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v910);
        goto LABEL_625;
      }
    }
    else if ( !v495 )
    {
      goto LABEL_624;
    }
    if ( !*(_QWORD *)(a1 + 176) && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
    {
      v506 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
      CMsiSQMSession::RecordDWORD(v506, 0xE25u, 0);
    }
    if ( Instance )
    {
      CAPITempBuffer<unsigned short,1>::CAPITempBuffer<unsigned short,1>(v1063);
      *(_WORD *)CComPointer<IMsiStorage>::operator->(v1063) = 0;
      CAPITempBuffer<unsigned short,1>::operator CAPITempBufferRef<unsigned short> &(v1063);
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
        v508 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
        v509 = (const unsigned __int16 *)CComPointer<IMsiStorage>::operator->(v1063);
        v510 = MsiString::MsiString((MsiString *)v997, v509);
        v511 = CComPointer<IMsiStorage>::operator->(v510);
        v512 = MsiString::MsiString((MsiString *)v996, L"MsiRestartManagerSessionKey");
        v513 = CComPointer<IMsiStorage>::operator->(v512);
        v508(a1, v513, v511);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v996);
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v997);
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
      if ( v500 == 2 || (unsigned int)MsiString::Compare(v910, 0, L"DisableShutdown") == 1 )
      {
        v514 = CRestartManagerWrapper::GetDisable(Instance);
        CRestartManagerWrapper::SetDisable(Instance, v514 | 8u);
      }
      CAPITempBuffer<unsigned short,1>::Destroy(v1063);
    }
    goto LABEL_624;
  }
LABEL_625:
  CComPointer<IMsiPath>::CComPointer<IMsiPath>(v860, 0);
  CComPointer<IMsiPath>::CComPointer<IMsiPath>(v858, 0);
  v515 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 128) + 192LL))(
           *(_QWORD *)(a1 + 128),
           2147483650LL,
           0xFFFFFFFFLL);
  v516 = CComPointer<IMsiDatabase>::operator=(v860, v515);
  if ( !CComPointer<IMsiStorage>::operator->(v516) )
    goto LABEL_689;
  v517 = CComPointer<IMsiStorage>::operator->(v860);
  v518 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v517 + 112LL))(
           v517,
           L"SYSTEM\\CurrentControlSet\\Control\\Session Manager",
           0,
           0xFFFFFFFFLL);
  v519 = CComPointer<IMsiDatabase>::operator=(v858, v518);
  if ( !CComPointer<IMsiStorage>::operator->(v519) )
    goto LABEL_689;
  v893 = 0;
  MsiString::MsiString((MsiString *)v857);
  v520 = CComPointer<IMsiStorage>::operator->(v858);
  v521 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v520 + 88LL))(v520, &v893);
  v522 = CComPointer<IMsiDatabase>::operator=(&v853, v521);
  if ( CComPointer<IMsiStorage>::operator->(v522) || !v893 )
  {
    v528 = 0;
  }
  else
  {
    v523 = CComPointer<IMsiStorage>::operator->(v858);
    v524 = *(__int64 (__fastcall **)(__int64, const WCHAR *, __int64))(*(_QWORD *)v523 + 40LL);
    v525 = MsiString::operator&(v857);
    v526 = v524(v523, L"PendingFileRenameOperations", v525);
    v527 = CComPointer<IMsiDatabase>::operator=(&v853, v526);
    v528 = 0;
    if ( !CComPointer<IMsiStorage>::operator->(v527)
      && ((unsigned int)MsiString::TextSize((MsiString *)v857) != 1
       || *(_WORD *)MsiString::operator unsigned short const *(v857))
      && (unsigned int)MsiString::TextSize((MsiString *)v857) )
    {
      v529 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v530 = MsiString::MsiString((MsiString *)v998, L"MsiSystemRebootPending");
      v531 = CComPointer<IMsiStorage>::operator->(v530);
      v529(a1, v531, 1);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v998);
    }
  }
  v532 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"SECONDSEQUENCE");
  v533 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v999, v532);
  v534 = MsiString::TextSize(v533);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v999);
  if ( v534 )
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
  if ( v823
    || !v850
    || v846
    || (v12 |= 0x400u,
        v535 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"PATCH"),
        v536 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1000, v535),
        v537 = 1,
        !(unsigned int)MsiString::TextSize(v536)) )
  {
    v537 = 0;
  }
  if ( (v12 & 0x400) != 0 )
  {
    v12 &= ~0x400u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1000);
  }
  if ( v537 )
  {
    v538 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v817);
    if ( IsProductManaged(v538) )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
      v11 = 37;
      goto LABEL_691;
    }
  }
  v539.lpVtbl = *(struct IUnknownVtbl **)a1;
  if ( v847 == 1 )
  {
    v540 = v539.lpVtbl[7].QueryInterface;
    v541 = MsiString::MsiString((MsiString *)v1001, L"ALLUSERS");
    v542 = CComPointer<IMsiStorage>::operator->(v541);
    ((void (__fastcall *)(__int64, __int64, __int64))v540)(a1, v542, 1);
    v543 = (GUIDAndSequence *)v1001;
  }
  else
  {
    v544 = v539.lpVtbl[6].Release;
    v545 = MsiString::MsiString((MsiString *)v1003, &Default);
    v546 = CComPointer<IMsiStorage>::operator->(v545);
    v547 = MsiString::MsiString((MsiString *)v1002, L"ALLUSERS");
    v548 = CComPointer<IMsiStorage>::operator->(v547);
    ((void (__fastcall *)(__int64, __int64, __int64))v544)(a1, v548, v546);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1002);
    v543 = (GUIDAndSequence *)v1003;
  }
  GUIDAndSequence::~GUIDAndSequence(v543);
  v549 = v842;
  v550.lpVtbl = *(struct IUnknownVtbl **)a1;
  if ( v842 == 1 )
  {
    v551 = v550.lpVtbl[7].QueryInterface;
    v552 = MsiString::MsiString((MsiString *)v1004, L"MSIINSTALLPERUSER");
    v553 = CComPointer<IMsiStorage>::operator->(v552);
    ((void (__fastcall *)(__int64, __int64, __int64))v551)(a1, v553, 1);
    v554 = (GUIDAndSequence *)v1004;
  }
  else
  {
    v555 = v550.lpVtbl[6].Release;
    v556 = MsiString::MsiString((MsiString *)v1006, &Default);
    v557 = CComPointer<IMsiStorage>::operator->(v556);
    v558 = MsiString::MsiString((MsiString *)v1005, L"MSIINSTALLPERUSER");
    v559 = CComPointer<IMsiStorage>::operator->(v558);
    ((void (__fastcall *)(__int64, __int64, __int64))v555)(a1, v559, v557);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1005);
    v554 = (GUIDAndSequence *)v1006;
  }
  GUIDAndSequence::~GUIDAndSequence(v554);
  if ( !*(_QWORD *)(a1 + 176)
    && g_scServerContext == 2
    && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
  {
    v560 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
    CMsiSQMSession::RecordDWORD(v560, 0x1054u, v549 != 0);
  }
  v561 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v562 = CComPointer<IMsiStorage>::operator->(&v824);
  v563 = MsiString::MsiString((MsiString *)v1007, L"TRANSFORMS");
  v564 = CComPointer<IMsiStorage>::operator->(v563);
  v561(a1, v564, v562);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1007);
  if ( g_dmDiagnosticMode )
  {
    v12 |= 0x800u;
    v565 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"TRANSFORMS");
    v566 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1008, v565);
    v567 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v566);
    DebugString(
      9,
      0,
      0,
      L"TRANSFORMS property is now: %s",
      v567,
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
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1008);
  }
  v568 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v569 = CComPointer<IMsiStorage>::operator->(&v826);
  v570 = MsiString::MsiString((MsiString *)v1009, L"PRODUCTLANGUAGE");
  v571 = CComPointer<IMsiStorage>::operator->(v570);
  v568(a1, v571, v569);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1009);
  if ( *(_BYTE *)(a1 + 577) )
  {
    v572 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
    v573 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 176) + 296LL))(*(_QWORD *)(a1 + 176));
    v574 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1011, v573);
    v575 = CComPointer<IMsiStorage>::operator->(v574);
    v576 = MsiString::MsiString((MsiString *)v1010, L"ParentProductCode");
    v577 = CComPointer<IMsiStorage>::operator->(v576);
    v572(a1, v577, v575);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1010);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1011);
    v578 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
    v579 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)(a1 + 176) + 184LL))(
             *(_QWORD *)(a1 + 176),
             L"OriginalDatabase");
    v580 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1013, v579);
    v581 = CComPointer<IMsiStorage>::operator->(v580);
    v582 = MsiString::MsiString((MsiString *)v1012, L"ParentOriginalDatabase");
    v583 = CComPointer<IMsiStorage>::operator->(v582);
    v578(a1, v583, v581);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1012);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1013);
  }
  v584 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v585 = CComPointer<IMsiStorage>::operator->(&v820);
  v586 = MsiString::MsiString((MsiString *)v1014, L"SourceDir");
  v587 = CComPointer<IMsiStorage>::operator->(v586);
  v584(a1, v587, v585);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1014);
  v588 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v589 = CComPointer<IMsiStorage>::operator->(&v820);
  v590 = MsiString::MsiString((MsiString *)v1015, L"SOURCEDIR");
  v591 = CComPointer<IMsiStorage>::operator->(v590);
  v588(a1, v591, v589);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1015);
  v592 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v593 = CComPointer<IMsiStorage>::operator->(&v822);
  v594 = MsiString::MsiString((MsiString *)v1016, L"SourcedirProduct");
  v595 = CComPointer<IMsiStorage>::operator->(v594);
  v592(a1, v595, v593);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1016);
  v596 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v597 = MsiString::MsiString((MsiString *)v1017, L"VersionDatabase");
  v598 = CComPointer<IMsiStorage>::operator->(v597);
  LODWORD(v596) = v596(a1, v598);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1017);
  if ( (_DWORD)v596 == 0x80000000 )
  {
    v599 = *(_DWORD *)(a1 + 456);
    v600 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
    v601 = MsiString::MsiString((MsiString *)v1018, L"VersionDatabase");
    v602 = CComPointer<IMsiStorage>::operator->(v601);
    v600(a1, v602, v599);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1018);
  }
  if ( (a6 & 0x10) != 0 )
  {
    if ( (a6 & 0x200) != 0 )
    {
      v528 = 1;
    }
    else if ( (a6 & 0x1000) != 0 )
    {
      v528 = 3;
    }
    else if ( (a6 & 0x400) != 0 )
    {
      v528 = 2;
    }
  }
  v603 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v819);
  CMsiEngine::CreateFolderCache((CMsiEngine *)a1, v603);
  v604 = *(_QWORD *)(a1 + 128);
  v605 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64))(*(_QWORD *)v604 + 64LL);
  v606 = CComPointer<IMsiStorage>::operator->(a1 + 1896);
  v607 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 184) + 24LL))(*(_QWORD *)(a1 + 184));
  v608 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1019, v607);
  v609 = CComPointer<IMsiStorage>::operator->(v608);
  v610 = v528;
  v611 = v847;
  LODWORD(v606) = v605(v604, v609, v847, v610, v606);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v1019);
  if ( !(_DWORD)v606 )
    goto LABEL_913;
  v612 = *(_QWORD *)(a1 + 128);
  v613 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v612 + 72LL);
  v614 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 184) + 24LL))(*(_QWORD *)(a1 + 184));
  v615 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1020, v614);
  v616 = CComPointer<IMsiStorage>::operator->(v615);
  LOBYTE(v613) = v613(v612, a1, v616);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v1020);
  if ( !(_BYTE)v613 )
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
      strFolderPairs::strFolderPairs((strFolderPairs *)v1066, L"System64Folder", L"SystemFolder", 1);
      strFolderPairs::strFolderPairs((strFolderPairs *)v1068, L"ProgramFiles64Folder", L"ProgramFilesFolder");
      strFolderPairs::strFolderPairs((strFolderPairs *)v1069, L"CommonFiles64Folder", L"CommonFilesFolder");
      strFolderPairs::strFolderPairs((strFolderPairs *)v1070, &Default, &Default);
      v617 = 0;
      if ( (unsigned int)MsiString::TextSize((MsiString *)v1067) )
      {
        do
        {
          v618 = (MsiString *)&v1066[24 * v617];
          if ( !(unsigned int)MsiString::TextSize(v618) )
            break;
          v619 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 176LL);
          v620 = CComPointer<IMsiStorage>::operator->(&v1066[24 * v617]);
          v621 = v619(a1, v620);
          CComPointer<IMsiPath>::CComPointer<IMsiPath>(v918, v621);
          v622 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 176LL);
          v623 = CComPointer<IMsiStorage>::operator->((char *)v618 + 8);
          v624 = v622(a1, v623);
          CComPointer<IMsiPath>::CComPointer<IMsiPath>(v917, v624);
          if ( (unsigned int)MsiString::TextSize((MsiString *)v918)
            && (unsigned int)MsiString::TextSize((MsiString *)v917) )
          {
            MsiString::operator=(&v1066[24 * v617], v918);
            MsiString::operator=((char *)v618 + 8, v917);
          }
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v917);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v918);
          ++v617;
        }
        while ( (unsigned int)MsiString::TextSize((MsiString *)&v1067[3 * v617]) );
        v611 = v847;
      }
      if ( !CWin64DualFolders::Initialize(
              (CWin64DualFolders *)&g_Win64DualFolders,
              *(_WORD *)(a1 + 604) == 0,
              (const struct strFolderPairs *)v1066,
              4u) )
      {
        `vector destructor iterator'(v1066, 0x18u, 4u, (void (*)(void *))strFolderPairs::~strFolderPairs);
        goto LABEL_688;
      }
      `vector destructor iterator'(v1066, 0x18u, 4u, (void (*)(void *))strFolderPairs::~strFolderPairs);
    }
  }
  v896 = 0;
  v626 = ((__int64 (__fastcall *)(int *))KERNEL32::CheckElevationEnabled)(&v896);
  v627 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v628 = MsiString::MsiString((MsiString *)v1021, L"MSIUSEREALADMINDETECTION");
  v629 = CComPointer<IMsiStorage>::operator->(v628);
  v630 = v627(a1, v629);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1021);
  if ( !v626 && v896 && v630 != 1 && !*(_BYTE *)(a1 + 600) )
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
      v635 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v636 = MsiString::MsiString((MsiString *)v1023, L"AdminUser");
      v637 = CComPointer<IMsiStorage>::operator->(v636);
      v635(a1, v637, 1);
      v634 = (GUIDAndSequence *)v1023;
      goto LABEL_708;
    }
    if ( *(_BYTE *)(a1 + 579) && v611 == 1 && v846 )
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
      v631 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
      v632 = MsiString::MsiString((MsiString *)v1022, L"AdminUser");
      v633 = CComPointer<IMsiStorage>::operator->(v632);
      v631(a1, v633, 1);
      v634 = (GUIDAndSequence *)v1022;
LABEL_708:
      GUIDAndSequence::~GUIDAndSequence(v634);
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
    v638 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v639 = MsiString::MsiString((MsiString *)v1024, L"MsiRunningElevated");
    v640 = CComPointer<IMsiStorage>::operator->(v639);
    v638(a1, v640, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1024);
  }
  v641 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"AdminUser");
  v642 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1025, v641);
  v643 = MsiString::TextSize(v642);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1025);
  if ( (unsigned int)IsTerminalServerInstalled()
    && !CMsiEngine::TerminalServerInstallsAreAllowed((CMsiEngine *)a1, v643 != 0) )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
    v11 = 25;
    goto LABEL_691;
  }
  if ( *(_BYTE *)(a1 + 579) || v643 )
  {
    v644 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v645 = MsiString::MsiString((MsiString *)v1026, L"Privileged");
    v646 = CComPointer<IMsiStorage>::operator->(v645);
    v644(a1, v646, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1026);
  }
  v647 = (const struct IMsiString *)CComPointer<IMsiStorage>::operator->(&v817);
  CMsiEngine::InitializeUserInfo((CMsiEngine *)a1, v647);
  if ( *(_DWORD *)(a1 + 356) )
  {
    v648 = (IMsiData *)CComPointer<IMsiStorage>::operator->(&v836);
    *(_QWORD *)(a1 + 424) = v648;
    IMsiData::AddRef(v648);
    if ( (*(_BYTE *)(a1 + 36) & 4) != 0 )
    {
      v649 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
      v650 = DateTimeToString(*(_DWORD *)(a1 + 404));
      v651 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1028, v650);
      v652 = CComPointer<IMsiStorage>::operator->(v651);
      v653 = MsiString::MsiString((MsiString *)v1027, L"Installed");
      v654 = CComPointer<IMsiStorage>::operator->(v653);
      v649(a1, v654, v652);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1027);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1028);
    }
  }
  v655 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v656 = CComPointer<IMsiStorage>::operator->(&v818);
  v657 = MsiString::MsiString((MsiString *)v1029, L"DATABASE");
  v658 = CComPointer<IMsiStorage>::operator->(v657);
  v655(a1, v658, v656);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1029);
  v659 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 160LL);
  v660 = CComPointer<IMsiStorage>::operator->(&v816);
  v661 = MsiString::MsiString((MsiString *)v1030, L"OriginalDatabase");
  v662 = CComPointer<IMsiStorage>::operator->(v661);
  v659(a1, v662, v660);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1030);
  v663 = CComPointer<IMsiStorage>::operator->(&v819);
  *(_QWORD *)(a1 + 152) = v663;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v663 + 8LL))(v663);
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 104LL))(a1, 0x8000, 1);
  v668 = 0;
  if ( v845 != 3 )
  {
    v12 |= 0x1000u;
    v664 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"LIMITUI");
    v665 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1032, v664);
    if ( (unsigned int)MsiString::TextSize(v665)
      || (v12 |= 0x2000u,
          v666 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"NOUI"),
          v667 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1031, v666),
          (unsigned int)MsiString::TextSize(v667)) )
    {
      v668 = 1;
    }
  }
  if ( (v12 & 0x2000) != 0 )
  {
    v12 &= ~0x2000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1031);
  }
  if ( (v12 & 0x1000) != 0 )
  {
    v12 &= ~0x1000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1032);
  }
  if ( v668 )
    v845 = 2;
  v669 = *(_QWORD *)(a1 + 152);
  v670 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v669 + 72LL);
  v671 = MsiString::MsiString((MsiString *)v1033, L"MsiEmbeddedUI");
  v672 = CComPointer<IMsiStorage>::operator->(v671);
  v673 = v670(v669, v672) != 0;
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1033);
  v677 = 1;
  if ( (unsigned int)GetIntegerPolicyValue(27, 1, 0) != 1 )
  {
    v12 |= 0x4000u;
    v674 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
    v675 = MsiString::MsiString((MsiString *)v1034, L"MSIDISABLEEEUI");
    v676 = CComPointer<IMsiStorage>::operator->(v675);
    if ( v674(a1, v676) != 1 )
      v677 = 0;
  }
  if ( (v12 & 0x4000) != 0 )
  {
    v12 &= ~0x4000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1034);
  }
  if ( v677 )
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
    v673 = 0;
  }
  if ( g_pEmbeddedUI )
    goto LABEL_750;
  if ( dword_1803097B8 )
    goto LABEL_750;
  if ( dword_180309978 )
    goto LABEL_750;
  v12 |= 0x8000u;
  v678 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v679 = MsiString::MsiString((MsiString *)v1036, L"MSICLIENTUSESEXTERNALUI");
  v680 = CComPointer<IMsiStorage>::operator->(v679);
  if ( v678(a1, v680) == 1
    || (v12 |= 0x10000u,
        v681 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL),
        v682 = MsiString::MsiString((MsiString *)v1035, L"MSICLIENTUSESEMBEDDEDUI"),
        v683 = CComPointer<IMsiStorage>::operator->(v682),
        v681(a1, v683) == 1) )
  {
LABEL_750:
    v684 = 1;
  }
  else
  {
    v684 = 0;
  }
  if ( (v12 & 0x10000) != 0 )
  {
    v12 &= ~0x10000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1035);
  }
  if ( (v12 & 0x8000) != 0 )
  {
    v12 &= ~0x8000u;
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1036);
  }
  if ( v684 )
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
    v673 = 0;
  }
  v685 = v859;
  if ( v859 )
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
    v673 = 0;
  }
  v686 = g_scServerContext;
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
      v686 = g_scServerContext;
    }
    v673 = 0;
  }
  if ( !v686 && v845 == 2 )
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
    v673 = 0;
  }
LABEL_773:
  if ( v845 == 3 )
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
  if ( v673 )
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
    v689 = (CMsiEmbeddedUIManager *)operator new(0x448u);
    if ( !v689 )
    {
      g_pEmbeddedUI = 0;
      goto LABEL_688;
    }
    v690 = (struct IMsiDatabase *)CComPointer<IMsiStorage>::operator->(&v819);
    g_pEmbeddedUI = (LPCWSTR)CMsiEmbeddedUIManager::CMsiEmbeddedUIManager(v689, v690);
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
      v692 = CreateMsiHandle((struct IUnknown *)a1, 790542);
      PMSIHANDLE::PMSIHANDLE((PMSIHANDLE *)v877, v692);
      v693 = 0;
      v694 = CreateRecord(1u);
      CComPointer<IMsiPath>::CComPointer<IMsiPath>(v883, v694);
      v695 = CComPointer<IMsiStorage>::operator->(v883);
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v695 + 104LL))(v695, 1, 7);
      v696 = CComPointer<IMsiStorage>::operator->(v883);
      MsiUIMessageContext::Invoke(&g_MessageContext, 402653184, v696);
      if ( IsAdmin() )
      {
        v697 = (*(__int64 (**)(__int64, const wchar_t *, ...))(*(_QWORD *)a1 + 184LL))(a1, L"%MsiBreak");
        CComPointer<IMsiPath>::CComPointer<IMsiPath>(v925, v697);
        v693 = (unsigned int)MsiString::Compare(v925, 0, L"MsiEmbeddedUI") == 1;
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v925);
      }
      v698 = PMSIHANDLE::operator unsigned long(v877);
      if ( CMsiEmbeddedUIManager::InitializeHandlers(
             (CMsiEmbeddedUIManager *)g_pEmbeddedUI,
             v698,
             (enum iuiEnum *)&v845,
             (enum iioEnum *)&a6,
             v693) )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v883);
        PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)v877);
        goto LABEL_688;
      }
      if ( v845 != 3 )
      {
        v699 = CComPointer<IMsiStorage>::operator->(v883);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v699 + 104LL))(v699, 1, 8);
        v700 = CComPointer<IMsiStorage>::operator->(v883);
        MsiUIMessageContext::Invoke(&g_MessageContext, 402653184, v700);
      }
      if ( !g_scServerContext )
      {
        v701 = *(_QWORD *)(a1 + 136);
        if ( !v701 )
        {
LABEL_810:
          *(_BYTE *)(a1 + 578) = (a6 & 8) != 0;
          *(_DWORD *)(a1 + 584) = a6;
          MsiUIMessageContext::ResetUILevel(&g_MessageContext, v845, a6);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v883);
          PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)v877);
LABEL_811:
          v702 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
          v703 = MsiString::MsiString((MsiString *)v1037, L"MSICLIENTUSESEMBEDDEDUI");
          v704 = CComPointer<IMsiStorage>::operator->(v703);
          v702(a1, v704, 1);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1037);
          LODWORD(v702) = v845;
          v705 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
          v706 = MsiString::MsiString((MsiString *)v1038, L"CLIENTUILEVEL");
          v707 = CComPointer<IMsiStorage>::operator->(v706);
          v705(a1, v707, (unsigned int)v702);
          GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1038);
          v685 = v859;
          goto LABEL_776;
        }
        if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v701 + 184LL))(v701) & 1) != 0
          && v845 == 3
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
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
LABEL_689:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
    goto LABEL_690;
  }
LABEL_776:
  *(_DWORD *)(a1 + 56) = v845;
  if ( *(_QWORD *)(a1 + 176) )
  {
    if ( (unsigned int)CMsiEngine::InTransaction() )
    {
      *(_DWORD *)(a1 + 76) = 1;
      *(_DWORD *)(a1 + 88) = 1;
      if ( (a6 & 1) == 0 )
        *(_DWORD *)(a1 + 80) = 1;
    }
    v687 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 104LL);
    v688 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 176) + 96LL))(*(_QWORD *)(a1 + 176));
    v687(a1, 256, (v688 >> 8) & 1);
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
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
      goto LABEL_785;
    }
  }
  else if ( v685 )
  {
    if ( (unsigned int)CMsiEngine::LoadHandler(a1) == 0x3FFF )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
      v11 = 10;
      goto LABEL_691;
    }
  }
  else
  {
    PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::InitializeUI(a1, v845);
    if ( PatchMetaDataForNewObsoletedAndSupercededMSPs
      || (PatchMetaDataForNewObsoletedAndSupercededMSPs = CMsiEngine::InitializeLogging(a1)) != 0 )
    {
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
      goto LABEL_264;
    }
  }
  CMsiEngine::SetPatchSourceProperties(a1);
  v708 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"SHORTFILENAMES");
  CComPointer<IMsiPath>::CComPointer<IMsiPath>(v881, v708);
  v709 = *(void (__fastcall **)(__int64, __int64, bool))(*(_QWORD *)a1 + 104LL);
  v710 = MsiString::TextSize((MsiString *)v881);
  v709(a1, 1024, v710 > 0);
  v711 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 8) + 296LL))(a1 + 8, 1);
  if ( v711 == 2 )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v881);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
    v11 = 34;
    goto LABEL_691;
  }
  if ( v711 == 10 )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v881);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
    v11 = 39;
    goto LABEL_691;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 840LL))(a1, 4) )
  {
    g_iUITicksStep = 6;
    g_iUIWaitTick = 300;
  }
  v712 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
  v713 = MsiString::MsiString((MsiString *)v1039, L"CLIENTUILEVEL");
  v714 = CComPointer<IMsiStorage>::operator->(v713);
  v715 = v712(a1, v714);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1039);
  v720 = 0;
  if ( v715 != 3 )
  {
    v12 |= 0x20000u;
    v716 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"LIMITUI");
    v717 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1041, v716);
    if ( (unsigned int)MsiString::TextSize(v717)
      || (v12 |= 0x40000u,
          v718 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"NOUI"),
          v719 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1040, v718),
          (unsigned int)MsiString::TextSize(v719)) )
    {
      v720 = 1;
    }
  }
  if ( (v12 & 0x40000) != 0 )
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1040);
  if ( (v12 & 0x20000) != 0 )
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1041);
  if ( v720 )
    goto LABEL_845;
  if ( v715 == 0x80000000 )
    v715 = *(_DWORD *)(a1 + 56);
  if ( !v715 )
  {
    v723 = 5;
    goto LABEL_846;
  }
  v721 = v715 - 1;
  if ( !v721 )
  {
    v723 = 4;
    goto LABEL_846;
  }
  v722 = v721 - 1;
  if ( !v722 )
  {
LABEL_845:
    v723 = 3;
    goto LABEL_846;
  }
  if ( v722 == 1 )
    v723 = 2;
  else
    v723 = 1;
LABEL_846:
  v724 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
  v725 = MsiString::MsiString((MsiString *)v1042, L"UILevel");
  v726 = CComPointer<IMsiStorage>::operator->(v725);
  v724(a1, v726, v723);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1042);
  if ( g_scServerContext == 2 && CMsiTransaction::m_pMsiTransaction )
    CMsiTransaction::SetClientUILevel((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction, v723);
  v727 = a6;
  if ( (a6 & 0x8000) != 0 )
  {
    HIBYTE(word_180309778) = 1;
    v728 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v729 = MsiString::MsiString((MsiString *)v1043, L"MsiUIProgressOnly");
    v730 = CComPointer<IMsiStorage>::operator->(v729);
    v728(a1, v730, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1043);
    v727 = a6;
  }
  if ( (v727 & 0x10000) != 0 )
  {
    v731 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v732 = MsiString::MsiString((MsiString *)v1044, L"MsiUIHideCancel");
    v733 = CComPointer<IMsiStorage>::operator->(v732);
    v731(a1, v733, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1044);
    v727 = a6;
  }
  if ( (v727 & 0x20000) != 0 )
  {
    v734 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v735 = MsiString::MsiString((MsiString *)v1045, L"MsiUISourceResOnly");
    v736 = CComPointer<IMsiStorage>::operator->(v735);
    v734(a1, v736, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1045);
  }
  if ( v861 == 4 )
  {
    v737 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 168LL);
    v738 = MsiString::MsiString((MsiString *)v1046, L"MsiUIUACOnly");
    v739 = CComPointer<IMsiStorage>::operator->(v738);
    v737(a1, v739, 1);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1046);
  }
  v740 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"FASTOEM");
  v741 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1047, v740);
  v742 = MsiString::TextSize(v741);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1047);
  MsiUIMessageContext::SetOEMInstall((MsiUIMessageContext *)&g_MessageContext, v742 != 0);
  if ( v742 )
  {
    v743 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"PATCH");
    v744 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1048, v743);
    v745 = MsiString::TextSize(v744);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1048);
    if ( v745 )
    {
      if ( g_dmDiagnosticMode )
      {
        v746 = L"OEM-mode installation does not support patching.";
LABEL_880:
        DebugString(9, 0, 0, v746, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_881;
      }
      goto LABEL_881;
    }
    if ( !v643 || !v611 )
    {
      if ( g_dmDiagnosticMode )
      {
        v746 = L"OEM-mode installation supports only per machine installations.";
        goto LABEL_880;
      }
      goto LABEL_881;
    }
    v747 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"ProductState");
    v748 = CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1049, v747);
    v749 = MsiString::operator int(v748);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1049);
    if ( v749 != -1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v746 = L"OEM-mode installation supports only first time installations.";
        goto LABEL_880;
      }
LABEL_881:
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v881);
      GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
      goto LABEL_585;
    }
    if ( v859 || v723 != 2 )
    {
      if ( g_dmDiagnosticMode )
      {
        v746 = L"OEM-mode installation supports only UI-less installations.";
        goto LABEL_880;
      }
      goto LABEL_881;
    }
    v750 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 184LL))(a1, L"ACTION");
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v911, v750);
    if ( (unsigned int)MsiString::TextSize((MsiString *)v911) )
    {
      v751 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v911);
      if ( (unsigned int)IStrComp(v751, L"INSTALL") )
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
        GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v911);
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
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v911);
  }
  if ( !v850 )
    goto LABEL_888;
  if ( (a6 & 0x80u) != 0 )
  {
    v752 = 1;
LABEL_887:
    v756 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL);
    v757 = MsiString::MsiString((MsiString *)v1051, L"QFEUpgrade");
    v758 = CComPointer<IMsiStorage>::operator->(v757);
    v756(a1, v758, v752);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1051);
    goto LABEL_888;
  }
  v753 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a1 + 184LL))(a1, L"PATCH");
  v754 = (MsiString *)CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1050, v753);
  v755 = MsiString::TextSize(v754);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1050);
  if ( v755 )
  {
    v752 = 2;
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
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v912, 0);
    v759 = *(_QWORD *)(a1 + 152);
    v760 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v759 + 80LL);
    v761 = CComPointer<IEnumMsiRecord>::operator=(v912);
    v762 = MsiString::MsiString((MsiString *)v1052, L"Font");
    v763 = CComPointer<IMsiStorage>::operator->(v762);
    v764 = v760(v759, v763, 0, v761);
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v1053, v764);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1052);
    if ( CComPointer<IMsiStorage>::operator->(v912) )
    {
      v765 = CComPointer<IMsiStorage>::operator->(v912);
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v765 + 64LL))(v765) )
        *(_BYTE *)(a1 + 2192) = 1;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v1053);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v912);
  }
  if ( !*(_QWORD *)(a1 + 176) )
  {
    v766 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 128) + 48LL))(*(_QWORD *)(a1 + 128), 3);
    CComPointer<IMsiPath>::CComPointer<IMsiPath>(v871, v766);
    v767 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 192LL);
    v768 = MsiString::MsiString((MsiString *)v1054, L"ProductLanguage");
    v769 = CComPointer<IMsiStorage>::operator->(v768);
    v770 = v767(a1, v769);
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v1054);
    if ( v770 == 0x80000000 )
      v770 = *(unsigned __int16 *)(a1 + 32);
    v771 = CComPointer<IMsiStorage>::operator->(v871);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v771 + 104LL))(v771, 1);
    v772 = CComPointer<IMsiStorage>::operator->(v871);
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v772 + 104LL))(v772, 2, v770);
    v773 = CComPointer<IMsiStorage>::operator->(v871);
    v774 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v773 + 104LL);
    v775 = CComPointer<IMsiStorage>::operator->(&v819);
    v776 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v775 + 216LL))(v775);
    v774(v773, 3, v776);
    v777 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 24LL);
    v778 = CComPointer<IMsiStorage>::operator->(v871);
    v777(a1, 184549376, v778);
    v779 = CComPointer<IMsiStorage>::operator->(v871);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v779 + 96LL))(v779, 3);
    if ( *(_QWORD *)(a1 + 280) )
    {
      v780 = CComPointer<IMsiStorage>::operator->(v871);
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v780 + 104LL))(v780, 1, 1);
      v781 = CComPointer<IMsiStorage>::operator->(v871);
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v781 + 120LL))(v781, 2, *(_QWORD *)(a1 + 280));
      v782 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 24LL);
      v783 = CComPointer<IMsiStorage>::operator->(v871);
      v782(a1, 184549376, v783);
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v871);
    if ( !*(_QWORD *)(a1 + 176) && MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext) )
    {
      if ( g_scServerContext == 2 )
      {
        if ( v723 - 2 <= 1 )
        {
          v784 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
          CMsiSQMSession::RecordInstallType(v784, (struct IMsiEngine *)a1);
        }
        v785 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        CMsiSQMSession::RecordDWORD(v785, 0xE28u, v611 != 0);
        v786 = v884;
        if ( !v884 || !*v884 )
          v786 = (unsigned __int16 *)MsiString::operator unsigned short const *(&v818);
        v787 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        CMsiSQMSession::UpdateInstallSourceType(v787, 0, v786, *(struct IMsiServices **)(a1 + 128));
      }
      else if ( !g_scServerContext )
      {
        v788 = MsiUIMessageContext::GetSQMSession((MsiUIMessageContext *)&g_MessageContext);
        CMsiSQMSession::RecordInstallType(v788, (struct IMsiEngine *)a1);
      }
    }
  }
  v11 = CMsiEngine::ProcessPreselectedAndResumeInfo(a1);
  if ( v11 )
  {
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v881);
LABEL_913:
    GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
    goto LABEL_321;
  }
  if ( g_scServerContext == 2 )
  {
    *(_BYTE *)(a1 + 607) = 1;
    if ( (unsigned int)IsTerminalServerInstalled() && v611 )
      *(_BYTE *)(a1 + 607) = 0;
    v789 = GetCustomActionManager(0);
    if ( v789 )
      CMsiCustomActionManager::EnsureHKCUKeyMappingState(v789, *(_BYTE *)(a1 + 607));
    else
      CreateCustomActionManager(*(_BYTE *)(a1 + 607));
  }
  MsiSuppressTimeout();
  CMsiEngine::ApplyAppCompatProperties((CMsiEngine *)a1);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v881);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)v857);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v858);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v860);
  CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v821);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v822);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v820);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v818);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v816);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v825);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v819);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v836);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v833);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v838);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v837);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v827);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v835);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v832);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v830);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v828);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v817);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v831);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v834);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v829);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v824);
  GUIDAndSequence::~GUIDAndSequence((GUIDAndSequence *)&v826);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v853);
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
