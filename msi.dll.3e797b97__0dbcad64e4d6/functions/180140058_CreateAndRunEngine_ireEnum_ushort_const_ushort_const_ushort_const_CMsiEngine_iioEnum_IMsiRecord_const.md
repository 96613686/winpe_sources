# CreateAndRunEngine(ireEnum,ushort const *,ushort const *,ushort const *,CMsiEngine *,iioEnum,IMsiRecord const *)

- ea: `0x180140058`
- end: `0x180144850`
- name: `?CreateAndRunEngine@@YAHW4ireEnum@@PEBG11PEAVCMsiEngine@@W4iioEnum@@PEBVIMsiRecord@@@Z`
- size: `18424`
- prototype: `int __high(enum ireEnum, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CMsiEngine *, enum iioEnum, const struct IMsiRecord *)`
- caller_count: `3`
- callee_count: `93`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009268`
- `0x1801cd010`
- `0x1801cd1b0`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180006970`
- `0x1800069f8`
- `0x18000879c`
- `0x18000c1a4`
- `0x18000c4bc`
- `0x180013d64`
- `0x180014160`
- `0x1800141e0`
- `0x180014288`
- `0x180014528`
- `0x180014e38`
- `0x180014f18`
- `0x180015c14`
- `0x18001a5b4`
- `0x18001bbf0`
- `0x18001f57c`
- `0x1800202e4`
- `0x180027634`
- `0x18002e870`
- `0x1800399d0`
- `0x18003c030`
- `0x180042810`
- `0x180044560`
- `0x18004a014`
- `0x180056140`
- `0x180057234`
- `0x180059758`
- `0x180062158`
- `0x180067fec`
- `0x18006d108`
- `0x180077470`
- `0x18007bf24`
- `0x180081150`
- `0x180082cec`
- `0x180086264`
- `0x18008c93c`
- `0x180097608`
- `0x18009f900`
- `0x1800ae46c`
- `0x1800bfd04`
- `0x1800c0678`
- `0x1800c08f8`
- `0x1800ca378`
- `0x1800ca3a0`
- `0x1800d04fc`
- `0x1800d27a0`
- `0x1800d92c4`
- `0x1800db998`

## import_xrefs

- `msvcrt!wcstol` at `0x180140b27`
- `msvcrt!wcstol` at `0x180142025`
- `msvcrt!wcstol` at `0x180142067`
- `msvcrt!wcstol` at `0x180140b27`
- `msvcrt!wcstol` at `0x180142025`
- `msvcrt!wcstol` at `0x180142067`
- `KERNEL32!DeleteFileW` at `0x180143e6a`
- `KERNEL32!DeleteFileW` at `0x180143e9e`
- `KERNEL32!DeleteFileW` at `0x180143f2e`
- `KERNEL32!DeleteFileW` at `0x180143f54`
- `KERNEL32!DeleteFileW` at `0x18014427c`
- `KERNEL32!DeleteFileW` at `0x18014451a`
- `KERNEL32!DeleteFileW` at `0x1801445ee`
- `KERNEL32!DeleteFileW` at `0x180143e6a`
- `KERNEL32!DeleteFileW` at `0x180143e9e`
- `KERNEL32!DeleteFileW` at `0x180143f2e`
- `KERNEL32!DeleteFileW` at `0x180143f54`
- `KERNEL32!DeleteFileW` at `0x18014427c`
- `KERNEL32!DeleteFileW` at `0x18014451a`
- `KERNEL32!DeleteFileW` at `0x1801445ee`
- `KERNEL32!GetLastError` at `0x180142a67`
- `KERNEL32!GetLastError` at `0x180143e7d`
- `KERNEL32!GetLastError` at `0x180143eae`
- `KERNEL32!GetLastError` at `0x180144026`
- `KERNEL32!GetLastError` at `0x180144201`
- `KERNEL32!GetLastError` at `0x180144533`
- `KERNEL32!GetLastError` at `0x180144607`
- `KERNEL32!GetLastError` at `0x180142a67`
- `KERNEL32!GetLastError` at `0x180143e7d`
- `KERNEL32!GetLastError` at `0x180143eae`
- `KERNEL32!GetLastError` at `0x180144026`
- `KERNEL32!GetLastError` at `0x180144201`
- `KERNEL32!GetLastError` at `0x180144533`
- `KERNEL32!GetLastError` at `0x180144607`
- `KERNEL32!GlobalAlloc` at `0x1801443f1`
- `KERNEL32!GlobalAlloc` at `0x1801443f1`
- `KERNEL32!Sleep` at `0x180143ec4`
- `KERNEL32!Sleep` at `0x180143ec4`
- `KERNEL32!lstrlenW` at `0x18014018f`
- `KERNEL32!lstrlenW` at `0x18014286f`
- `KERNEL32!lstrlenW` at `0x18014018f`
- `KERNEL32!lstrlenW` at `0x18014286f`
- `KERNEL32!lstrcmpiW` at `0x180141f21`
- `KERNEL32!lstrcmpiW` at `0x180141f21`
- `KERNEL32!GetCurrentProcessId` at `0x180140ef1`
- `KERNEL32!GetCurrentProcessId` at `0x180140ef1`
- `KERNEL32!GetCurrentDirectoryW` at `0x180140db0`
- `KERNEL32!GetCurrentDirectoryW` at `0x180140dee`
- `KERNEL32!GetCurrentDirectoryW` at `0x180140db0`
- `KERNEL32!GetCurrentDirectoryW` at `0x180140dee`

## string_xrefs

- `0x1801411da`: `CLIENTPROCESSID`
- `0x18014367c`: `REMOVE`
- `0x18014342d`: `MSIFASTINSTALL`
- `0x180143532`: `MSIFASTINSTALL`
- `0x180140823`: `SeShutdownPrivilege`
- `0x180140f3b`: `SeShutdownPrivilege`
- `0x1801402f3`: `REINSTALLMODE`
- `0x180140477`: `MSINEWINSTANCE`
- `0x180140686`: `MSIPACKAGEDOWNLOADLOCALCOPY`
- `0x1801406ff`: `MSIPATCHDOWNLOADLOCALCOPY`
- `0x180140500`: `MSIINSTANCEGUID`
- `0x1801444d4`: `Attempting to delete file %s`
- `0x1801445a8`: `Attempting to delete file %s`
- `0x180141761`: `CURRENTDIRECTORY`
- `0x18014377a`: `MSICLIENTUSESEMBEDDEDUI`
- `0x180140f69`: `SeIncreaseQuotaPrivilege`
- `0x180144042`: `SAFER: Unable to create a fully trusted authorization level.  GetLastError returned %d`
- `0x18014013c`: `******* RunEngine:\n           ******* Product: %s\n           ******* Action: %s\n           ******* CommandLine: %s`
- `0x180140851`: `ERROR: Forcereboot flag passed, Client does not have reboot privilege`
- `0x180140a77`: `Invalid use of MSINEWINSTANCE property.`
- `0x1801409c1`: `Invalid use of MSINEWINSTANCE property. Use of property requires package path invocation.`
- `0x1801409df`: `Invalid use of MSINEWINSTANCE property. Multiple instance is not supported with nested installs.`
- `0x180140a44`: `Specified instance %s is not installed. MSIINSTANCEGUID must reference an installed instance.`
- `0x180140c20`: `Invalid use of MSIINSTANCEGUID property. This can only be used for a multiple instance install.`
- `0x180140c86`: `Cannot remove RunOnce entry: %s.  Couldn't connect to service`
- `0x180140dfa`: ` CURRENTDIRECTORY="`
- `0x180140e98`: ` MSICLIENTUSESEXTERNALUI=`
- `0x180140ee1`: ` CLIENTPROCESSID=`
- `0x1801410a8`: `Client-side and UI is none or basic: Running entire install on the server.`
- `0x180141583`: `Adding MSIPACKAGEDOWNLOADLOCALCOPY to command line.`
- `0x180142c57`: `Adding MSIPACKAGEDOWNLOADLOCALCOPY to command line.`
- `0x1801415b5`: ` MSIPACKAGEDOWNLOADLOCALCOPY="`
- `0x180142c89`: ` MSIPACKAGEDOWNLOADLOCALCOPY="`
- `0x180141c93`: `Specified instance %s via transform %s is already installed. MSINEWINSTANCE requires a new instance that is not installed.`
- `0x180141da5`: `Product code changing transform not found in transforms list. MSINEWINSTANCE property requires existance of instance transform.`
- `0x180141ecd`: `Unable to obtain registered PackageCode for instance install %s`
- `0x180142090`: `Adding MSIINSTANCEGUID to command line.`
- `0x1801420c2`: ` MSIINSTANCEGUID=`
- `0x1801426ea`: `Attempting to recache package via ProductCode. Beginning source resolution.`
- `0x1801443b7`: `Cleaning up uninstalled install packages, if any exist`
- `0x180144544`: `Unable to delete the file outside of the engine. LastError = %d`
- `0x180144618`: `Unable to delete the file outside of the engine. LastError = %d`

## pseudocode

```c
__int64 __fastcall CreateAndRunEngine(
        unsigned int a1,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  int v11; // ecx
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // rcx
  unsigned int v16; // eax
  struct IMsiServices *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  MsiString *v26; // rax
  MsiString *v27; // rax
  MsiString *v28; // rax
  MsiString *v29; // rax
  MsiString *v30; // rax
  int v31; // ebx
  int v32; // eax
  int v33; // ebx
  int v34; // eax
  int v35; // edi
  unsigned int v36; // r12d
  unsigned int PackageCodeAndLanguageFromStorage; // r14d
  const unsigned __int16 *v38; // r9
  const WCHAR *v39; // rax
  const unsigned __int16 *v40; // rax
  const WCHAR *v41; // rax
  struct IMsiServer *v42; // rbx
  const unsigned __int16 *v43; // rax
  void (__fastcall *v44)(struct IMsiServer *, __int64); // rdi
  __int64 v45; // rax
  const unsigned __int16 *v46; // rax
  int v47; // ecx
  DWORD CurrentDirectoryW; // eax
  int v49; // ebx
  MsiString *v50; // rax
  MsiString *v51; // rax
  DWORD CurrentProcessId; // eax
  MsiString *v53; // rax
  __int64 v54; // rax
  MsiString *v55; // rax
  MsiString *v56; // rax
  int v57; // eax
  int v58; // eax
  const unsigned __int16 *v59; // rbx
  __int64 v60; // rbx
  __int64 v61; // rax
  unsigned __int16 *v62; // rcx
  const WCHAR *v63; // rax
  const unsigned __int16 *v64; // rax
  bool v65; // al
  __int64 v66; // rbx
  __int64 v67; // rax
  int v68; // eax
  unsigned int v69; // r14d
  MsiString *v70; // rax
  struct IMsiRecord *v71; // rax
  char v72; // si
  unsigned int v73; // edi
  struct IMsiStorage *v74; // rsi
  __int64 (__fastcall *v75)(struct IMsiStorage *, __int64, _QWORD, __int64); // rdi
  __int64 v76; // rbx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  int v80; // eax
  __int64 v81; // rax
  IMsiData *v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rax
  __int64 v87; // rbx
  __int64 v88; // rax
  __int64 v89; // rdi
  __int64 (__fastcall *v90)(__int64, _QWORD, __int64); // rbx
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  const WCHAR *v94; // rax
  const unsigned __int16 *v95; // rbx
  const unsigned __int16 *v96; // rax
  const unsigned __int16 *v97; // r9
  const WCHAR *v98; // rax
  const unsigned __int16 *v99; // rax
  const unsigned __int16 *v100; // rax
  __int64 v101; // rax
  struct IMsiRecord *v102; // rdi
  void (__fastcall *v103)(struct IMsiRecord *, __int64, _QWORD); // rbx
  unsigned int Codepage; // eax
  int v105; // eax
  __int64 v106; // rbx
  __int64 (__fastcall *v107)(__int64, const WCHAR *, _QWORD, __int64); // rdi
  __int64 v108; // rax
  unsigned int i; // ecx
  int v110; // edx
  struct IUnknown *MsiHandle; // rax
  __int64 v112; // rax
  int v113; // ebx
  __int64 v114; // rdx
  IMsiData *v115; // rcx
  const unsigned __int16 *v116; // rax
  DWORD v117; // eax
  __int64 v118; // rax
  const WCHAR *v119; // rax
  const unsigned __int16 *v120; // rax
  unsigned int v121; // eax
  __int64 v122; // rbx
  __int64 v123; // rax
  int v124; // eax
  struct IMsiRecord **v125; // rax
  struct IMsiRecord *v126; // rax
  __int64 (__fastcall *v127)(struct IMsiServices *, unsigned __int16 *, _QWORD, __int64); // rbx
  __int64 v128; // rax
  __int64 v129; // rax
  __int64 (__fastcall *v130)(struct IMsiServices *, __int64, __int64, __int64); // rbx
  __int64 v131; // rax
  __int64 v132; // rax
  struct IMsiDatabase *v133; // rbx
  unsigned int j; // ecx
  int v135; // edx
  struct IUnknown *v136; // rax
  unsigned int v137; // r12d
  __int64 v138; // rax
  __int64 (__fastcall *v139)(struct IMsiDatabase *, _QWORD, _QWORD, __int64); // rsi
  __int64 v140; // rdi
  MsiString *v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rdi
  __int64 (__fastcall *v145)(__int64, _QWORD); // rbx
  unsigned int v146; // eax
  __int64 v147; // rdi
  __int64 (__fastcall *v148)(__int64, _QWORD); // rbx
  unsigned int v149; // eax
  unsigned int v150; // esi
  char v151; // bl
  __int64 v152; // rdi
  void (__fastcall *v153)(__int64, _QWORD); // rbx
  unsigned int v154; // eax
  __int64 v155; // rdi
  void (__fastcall *v156)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v157; // rax
  LPWSTR *v158; // rcx
  UINT ProductInfoW; // eax
  LPWSTR *p_lpValueBuf; // rcx
  __int64 v161; // rdi
  void (__fastcall *v162)(__int64, _QWORD); // rbx
  unsigned int v163; // eax
  __int64 v164; // rdi
  void (__fastcall *v165)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v166; // rax
  IMsiData *v167; // rbx
  WCHAR *v168; // rbx
  const WCHAR *v169; // rax
  UINT v170; // eax
  __int64 v171; // rdi
  void (__fastcall *v172)(__int64, _QWORD); // rbx
  unsigned int v173; // eax
  __int64 v174; // rdi
  void (__fastcall *v175)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v176; // rax
  IMsiData *v177; // rbx
  __int64 v178; // rbx
  __int64 v179; // rax
  int v180; // r15d
  __int64 v181; // rdi
  void (__fastcall *v182)(__int64, _QWORD); // rbx
  unsigned int v183; // eax
  __int64 v184; // rdi
  void (__fastcall *v185)(__int64, _QWORD, _QWORD); // rbx
  MsiString *v186; // rax
  IMsiData *v187; // rbx
  char v188; // bl
  MsiString *v189; // rax
  const unsigned __int16 *v190; // rdi
  MsiString *v191; // rax
  MsiString *v192; // rax
  MsiString *v193; // rax
  char v194; // di
  char v195; // di
  int v196; // ebx
  bool v197; // si
  __int64 v198; // rax
  BOOL v199; // r12d
  __int64 v200; // rax
  __int64 v201; // r9
  unsigned int v202; // r15d
  __int64 v203; // r8
  __int64 v204; // rdx
  struct IMsiServices *v205; // r12
  DWORD LastError; // ebx
  __int64 *v207; // rsi
  void *v208; // rdi
  __int64 v209; // rbx
  __int64 v210; // rax
  signed int v211; // eax
  __int64 v212; // rbx
  struct IMsiStorage *v213; // rsi
  bool v214; // r14
  __int64 v215; // rdi
  __int64 v216; // rax
  unsigned int v217; // esi
  __int64 v218; // rax
  unsigned int v219; // ebx
  unsigned int v220; // eax
  const WCHAR *v221; // rax
  int v222; // edi
  const WCHAR *v223; // rax
  DWORD v224; // ebx
  const WCHAR *v225; // rax
  const WCHAR *v226; // rax
  __int64 v227; // rax
  DWORD v228; // eax
  signed int v229; // eax
  int v230; // ebx
  bool v231; // zf
  const WCHAR *v232; // rax
  bool v233; // bl
  _DWORD *v234; // rdx
  __int64 v235; // r8
  const unsigned __int16 *v236; // rax
  const WCHAR *v237; // rax
  DWORD v238; // eax
  const unsigned __int16 *v239; // rax
  const WCHAR *v240; // rax
  DWORD v241; // eax
  PTOKEN_PRIVILEGES NewState; // [rsp+20h] [rbp-E0h]
  int NewStatea; // [rsp+20h] [rbp-E0h]
  struct _FILETIME *v244; // [rsp+28h] [rbp-D8h]
  char *v245; // [rsp+30h] [rbp-D0h]
  int v246; // [rsp+30h] [rbp-D0h]
  int v247; // [rsp+38h] [rbp-C8h]
  BOOL v248; // [rsp+38h] [rbp-C8h]
  int v249; // [rsp+40h] [rbp-C0h]
  int v250; // [rsp+50h] [rbp-B0h]
  int v251; // [rsp+60h] [rbp-A0h]
  int v252; // [rsp+60h] [rbp-A0h]
  int v253; // [rsp+60h] [rbp-A0h]
  int v254; // [rsp+60h] [rbp-A0h]
  int v255; // [rsp+60h] [rbp-A0h]
  int v256; // [rsp+60h] [rbp-A0h]
  int v257; // [rsp+60h] [rbp-A0h]
  int v258; // [rsp+60h] [rbp-A0h]
  int v259; // [rsp+60h] [rbp-A0h]
  int v260; // [rsp+60h] [rbp-A0h]
  int v261; // [rsp+60h] [rbp-A0h]
  int v262; // [rsp+60h] [rbp-A0h]
  int v263; // [rsp+60h] [rbp-A0h]
  int v264; // [rsp+60h] [rbp-A0h]
  bool v265; // [rsp+70h] [rbp-90h] BYREF
  char v266; // [rsp+71h] [rbp-8Fh]
  bool v267; // [rsp+72h] [rbp-8Eh] BYREF
  char v268; // [rsp+73h] [rbp-8Dh]
  IMsiData *v269; // [rsp+78h] [rbp-88h] BYREF
  BOOL v270; // [rsp+80h] [rbp-80h]
  IMsiData *v271; // [rsp+88h] [rbp-78h] BYREF
  __int64 v272; // [rsp+90h] [rbp-70h] BYREF
  bool v273[8]; // [rsp+98h] [rbp-68h] BYREF
  struct IMsiStorage *v274; // [rsp+A0h] [rbp-60h] BYREF
  struct IMsiRecord *Record; // [rsp+A8h] [rbp-58h] BYREF
  struct IMsiDatabase *v276; // [rsp+B0h] [rbp-50h] BYREF
  int v277; // [rsp+B8h] [rbp-48h]
  char v278; // [rsp+BCh] [rbp-44h]
  IMsiData *v279; // [rsp+C0h] [rbp-40h] BYREF
  IMsiData *v280; // [rsp+C8h] [rbp-38h] BYREF
  IMsiData *v281; // [rsp+D0h] [rbp-30h] BYREF
  IMsiData *v282; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v283; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v284; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v285; // [rsp+F0h] [rbp-10h] BYREF
  int v286; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v287; // [rsp+FCh] [rbp-4h] BYREF
  __int64 v288; // [rsp+100h] [rbp+0h] BYREF
  IMsiData *v289; // [rsp+108h] [rbp+8h] BYREF
  IMsiData *v290; // [rsp+110h] [rbp+10h] BYREF
  IMsiData *v291; // [rsp+118h] [rbp+18h] BYREF
  IMsiData *v292; // [rsp+120h] [rbp+20h] BYREF
  int v293; // [rsp+128h] [rbp+28h]
  IMsiData *v294; // [rsp+130h] [rbp+30h] BYREF
  IMsiData *v295; // [rsp+138h] [rbp+38h] BYREF
  __int64 v296; // [rsp+140h] [rbp+40h] BYREF
  IMsiData *v297; // [rsp+148h] [rbp+48h] BYREF
  __int64 v298; // [rsp+150h] [rbp+50h] BYREF
  IMsiData *v299; // [rsp+158h] [rbp+58h] BYREF
  __int64 v300; // [rsp+160h] [rbp+60h] BYREF
  IMsiData *v301; // [rsp+168h] [rbp+68h] BYREF
  IMsiData *v302; // [rsp+170h] [rbp+70h] BYREF
  IMsiData *v303; // [rsp+178h] [rbp+78h] BYREF
  IMsiData *v304; // [rsp+180h] [rbp+80h] BYREF
  IMsiData *v305; // [rsp+188h] [rbp+88h] BYREF
  IMsiData *v306; // [rsp+190h] [rbp+90h] BYREF
  IMsiData *v307; // [rsp+198h] [rbp+98h] BYREF
  IMsiData *v308; // [rsp+1A0h] [rbp+A0h] BYREF
  IMsiData *v309; // [rsp+1A8h] [rbp+A8h] BYREF
  IMsiData *v310; // [rsp+1B0h] [rbp+B0h] BYREF
  int v311; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v312; // [rsp+1BCh] [rbp+BCh] BYREF
  IMsiData *v313; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v314; // [rsp+1C8h] [rbp+C8h] BYREF
  IMsiData *v315; // [rsp+1D0h] [rbp+D0h] BYREF
  IMsiData *v316; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v317; // [rsp+1E0h] [rbp+E0h]
  IMsiData *v318; // [rsp+1E8h] [rbp+E8h] BYREF
  char v319[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  IMsiData *v320; // [rsp+1F8h] [rbp+F8h] BYREF
  IMsiData *v321; // [rsp+200h] [rbp+100h] BYREF
  IMsiData *v322; // [rsp+208h] [rbp+108h] BYREF
  struct IMsiServices *v323; // [rsp+210h] [rbp+110h]
  __int64 v324; // [rsp+218h] [rbp+118h] BYREF
  IMsiData *v325; // [rsp+220h] [rbp+120h] BYREF
  IMsiData *v326; // [rsp+228h] [rbp+128h] BYREF
  IMsiData *v327; // [rsp+230h] [rbp+130h] BYREF
  IMsiData *v328; // [rsp+238h] [rbp+138h] BYREF
  IMsiData *v329; // [rsp+240h] [rbp+140h] BYREF
  IMsiData *v330; // [rsp+248h] [rbp+148h] BYREF
  DWORD v331; // [rsp+250h] [rbp+150h] BYREF
  DWORD v332; // [rsp+254h] [rbp+154h] BYREF
  int v333; // [rsp+258h] [rbp+158h] BYREF
  int v334; // [rsp+25Ch] [rbp+15Ch] BYREF
  __int64 v335; // [rsp+260h] [rbp+160h] BYREF
  __int64 v336; // [rsp+268h] [rbp+168h] BYREF
  __int64 v337; // [rsp+270h] [rbp+170h]
  IMsiData *v338; // [rsp+278h] [rbp+178h] BYREF
  __int64 v339; // [rsp+280h] [rbp+180h] BYREF
  int v340; // [rsp+288h] [rbp+188h]
  int v341; // [rsp+28Ch] [rbp+18Ch] BYREF
  IMsiData *v342; // [rsp+290h] [rbp+190h] BYREF
  IMsiData *v343; // [rsp+298h] [rbp+198h] BYREF
  IMsiData *v344; // [rsp+2A0h] [rbp+1A0h] BYREF
  IMsiData *v345; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v346; // [rsp+2B0h] [rbp+1B0h] BYREF
  IMsiData *v347; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v348; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned int v349; // [rsp+2C8h] [rbp+1C8h] BYREF
  DWORD pcchValueBuf[2]; // [rsp+2CCh] [rbp+1CCh] BYREF
  unsigned int v351; // [rsp+2D4h] [rbp+1D4h] BYREF
  int v352; // [rsp+2D8h] [rbp+1D8h]
  IMsiData *v353; // [rsp+2E0h] [rbp+1E0h] BYREF
  const unsigned __int16 *v354; // [rsp+2E8h] [rbp+1E8h]
  __int64 v355; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v356[8]; // [rsp+2F8h] [rbp+1F8h] BYREF
  struct IMsiServer *MsiServer; // [rsp+300h] [rbp+200h] BYREF
  __int64 v358; // [rsp+308h] [rbp+208h] BYREF
  IMsiData *v359; // [rsp+310h] [rbp+210h] BYREF
  __int64 v360; // [rsp+318h] [rbp+218h]
  const unsigned __int16 *v361; // [rsp+320h] [rbp+220h]
  IMsiData *v362; // [rsp+328h] [rbp+228h] BYREF
  IMsiData *v363; // [rsp+330h] [rbp+230h] BYREF
  IMsiData *v364; // [rsp+338h] [rbp+238h] BYREF
  IMsiData *v365; // [rsp+340h] [rbp+240h] BYREF
  IMsiData *v366; // [rsp+348h] [rbp+248h] BYREF
  IMsiData *v367; // [rsp+350h] [rbp+250h] BYREF
  IMsiData *v368; // [rsp+358h] [rbp+258h] BYREF
  IMsiData *v369; // [rsp+360h] [rbp+260h] BYREF
  IMsiData *v370; // [rsp+368h] [rbp+268h] BYREF
  IMsiData *v371; // [rsp+370h] [rbp+270h] BYREF
  IMsiData *v372; // [rsp+378h] [rbp+278h] BYREF
  IMsiData *v373; // [rsp+380h] [rbp+280h] BYREF
  IMsiData *v374; // [rsp+388h] [rbp+288h] BYREF
  unsigned __int16 *v375; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 *v376; // [rsp+398h] [rbp+298h] BYREF
  IMsiData *v377; // [rsp+3A0h] [rbp+2A0h] BYREF
  IMsiData *v378; // [rsp+3A8h] [rbp+2A8h] BYREF
  IMsiData *v379; // [rsp+3B0h] [rbp+2B0h] BYREF
  IMsiData *v380; // [rsp+3B8h] [rbp+2B8h] BYREF
  IMsiData *v381; // [rsp+3C0h] [rbp+2C0h] BYREF
  IMsiData *v382; // [rsp+3C8h] [rbp+2C8h] BYREF
  IMsiData *v383; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v384; // [rsp+3D8h] [rbp+2D8h] BYREF
  IMsiData *v385; // [rsp+3E0h] [rbp+2E0h] BYREF
  IMsiData *v386; // [rsp+3E8h] [rbp+2E8h] BYREF
  IMsiData *v387; // [rsp+3F0h] [rbp+2F0h] BYREF
  IMsiData *v388; // [rsp+3F8h] [rbp+2F8h] BYREF
  IMsiData *v389; // [rsp+400h] [rbp+300h] BYREF
  IMsiData *v390; // [rsp+408h] [rbp+308h] BYREF
  IMsiData *v391; // [rsp+410h] [rbp+310h] BYREF
  IMsiData *v392; // [rsp+418h] [rbp+318h] BYREF
  IMsiData *v393; // [rsp+420h] [rbp+320h] BYREF
  IMsiData *v394; // [rsp+428h] [rbp+328h] BYREF
  IMsiData *v395; // [rsp+430h] [rbp+330h] BYREF
  char v396[8]; // [rsp+438h] [rbp+338h] BYREF
  char v397[8]; // [rsp+440h] [rbp+340h] BYREF
  _DWORD *v398; // [rsp+448h] [rbp+348h] BYREF
  char v399[8]; // [rsp+450h] [rbp+350h] BYREF
  LPWSTR lpBuffer; // [rsp+458h] [rbp+358h] BYREF
  DWORD nBufferLength; // [rsp+460h] [rbp+360h]
  unsigned __int16 *v402; // [rsp+470h] [rbp+370h] BYREF
  signed int v403; // [rsp+478h] [rbp+378h]
  int v404; // [rsp+47Ch] [rbp+37Ch]
  char v405; // [rsp+480h] [rbp+380h] BYREF
  PCNZWCH lpString1; // [rsp+488h] [rbp+388h] BYREF
  signed int v407; // [rsp+490h] [rbp+390h]
  LPWSTR lpValueBuf; // [rsp+4A0h] [rbp+3A0h] BYREF
  DWORD v409; // [rsp+4A8h] [rbp+3A8h]
  char v410; // [rsp+4B0h] [rbp+3B0h] BYREF
  LPWSTR v411; // [rsp+4B8h] [rbp+3B8h] BYREF
  DWORD v412; // [rsp+4C0h] [rbp+3C0h]
  char v413; // [rsp+4C8h] [rbp+3C8h] BYREF
  _QWORD v414[4]; // [rsp+4D0h] [rbp+3D0h] BYREF
  LPCWSTR szProduct; // [rsp+4F0h] [rbp+3F0h] BYREF
  int v416; // [rsp+4F8h] [rbp+3F8h]
  _BYTE v417[80]; // [rsp+500h] [rbp+400h] BYREF
  HKEY hKey[10]; // [rsp+550h] [rbp+450h] BYREF
  wchar_t *v419; // [rsp+5A0h] [rbp+4A0h] BYREF
  int v420; // [rsp+5A8h] [rbp+4A8h]
  int v421; // [rsp+5ACh] [rbp+4ACh]
  _BYTE v422[208]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 *v423; // [rsp+680h] [rbp+580h] BYREF
  int v424; // [rsp+688h] [rbp+588h]
  int v425; // [rsp+68Ch] [rbp+58Ch]
  _BYTE v426[208]; // [rsp+690h] [rbp+590h] BYREF
  LPCWSTR lpString; // [rsp+760h] [rbp+660h] BYREF
  int v428; // [rsp+768h] [rbp+668h]
  int v429; // [rsp+76Ch] [rbp+66Ch]
  char v430; // [rsp+770h] [rbp+670h] BYREF
  wchar_t *String; // [rsp+840h] [rbp+740h] BYREF
  int v432; // [rsp+848h] [rbp+748h]
  int v433; // [rsp+84Ch] [rbp+74Ch]
  _BYTE v434[208]; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v435[272]; // [rsp+920h] [rbp+820h] BYREF
  WCHAR ValueBuf[40]; // [rsp+A30h] [rbp+930h] BYREF
  WCHAR String2[40]; // [rsp+A80h] [rbp+980h] BYREF

  v337 = a5;
  v360 = a7;
  v354 = a4;
  v361 = a3;
  v340 = 0;
  PopulateDomainBasedAllowLockdownMediaDefault();
  v11 = ((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147417850 )
    return 1603;
  v273[0] = v11 >= 0;
  ResetCachedPolicyValuesW();
  CImpersonate::CImpersonate((CImpersonate *)v356, 1);
  if ( g_dmDiagnosticMode )
  {
    v13 = LoggedCommandLine(a4);
    v14 = a3;
    if ( !a3 )
      v14 = &Default;
    v15 = a2;
    if ( !a2 )
      v15 = &Default;
    DebugString(
      9,
      0,
      0,
      L"******* RunEngine:\r\n"
       "           ******* Product: %s\r\n"
       "           ******* Action: %s\r\n"
       "           ******* CommandLine: %s",
      v15,
      v14,
      v13,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  if ( a2 )
    v16 = lstrlenW(a2) + 1;
  else
    v16 = 261;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&lpString1, v16);
  v403 = 1;
  v402 = (unsigned __int16 *)&v405;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(v414, 261);
  memset_0(v417, 0, 0x4Eu);
  v416 = 39;
  szProduct = (LPCWSTR)v417;
  if ( !lpString1 || !v414[0] || !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v402, 261, 0) )
  {
    CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>(&szProduct);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(v414);
    CAPITempBuffer<unsigned short,1>::Destroy(&v402);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString1);
    CImpersonate::~CImpersonate((CImpersonate *)v356);
    CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v273);
    return 14;
  }
  *v402 = 0;
  *szProduct = 0;
  v17 = g_piSharedServices;
  v323 = g_piSharedServices;
  v265 = 0;
  v267 = 0;
  v348 = 0;
  v324 = 0;
  v274 = 0;
  v339 = 0;
  v277 = 7;
  v287 = 0;
  v304 = (IMsiData *)&MsiString::s_NullString;
  v338 = (IMsiData *)&MsiString::s_NullString;
  v309 = (IMsiData *)&MsiString::s_NullString;
  v313 = (IMsiData *)&MsiString::s_NullString;
  v303 = (IMsiData *)&MsiString::s_NullString;
  v297 = (IMsiData *)&MsiString::s_NullString;
  v292 = (IMsiData *)&MsiString::s_NullString;
  v330 = (IMsiData *)&MsiString::s_NullString;
  v329 = (IMsiData *)&MsiString::s_NullString;
  v328 = (IMsiData *)&MsiString::s_NullString;
  v289 = (IMsiData *)&MsiString::s_NullString;
  v327 = (IMsiData *)&MsiString::s_NullString;
  v326 = (IMsiData *)&MsiString::s_NullString;
  MsiString::MsiString((MsiString *)&v271, a4);
  IMsiData::Release(v313);
  v313 = (IMsiData *)&MsiString::s_NullString;
  v18 = *(_QWORD *)MsiString::MsiString((MsiString *)&v363, L"REINSTALLMODE");
  IMsiData::Release(v338);
  v338 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v304);
  v304 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v309);
  v309 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v297);
  v297 = (IMsiData *)&MsiString::s_NullString;
  v19 = MsiString::operator unsigned short const *(&v271);
  ProcessCommandLine(v19, 0, &v297, &v309, 0, &v304, &v338, v18, &v313, 1, 0, 0, 0);
  IMsiData::Release(v363);
  IMsiData::Release(v303);
  v303 = (IMsiData *)&MsiString::s_NullString;
  v20 = *(_QWORD *)MsiString::MsiString((MsiString *)&v364, L"RUNONCEENTRY");
  v21 = MsiString::operator unsigned short const *(&v271);
  LOBYTE(v251) = 0;
  ProcessCommandLine(v21, 0, 0, 0, 0, 0, 0, v20, &v303, 1, 0, 0, v251);
  IMsiData::Release(v364);
  IMsiData::Release(v330);
  v330 = (IMsiData *)&MsiString::s_NullString;
  v22 = *(_QWORD *)MsiString::MsiString((MsiString *)&v365, L"MSINEWINSTANCE");
  v23 = MsiString::operator unsigned short const *(&v271);
  LOBYTE(v252) = 0;
  ProcessCommandLine(v23, 0, 0, 0, 0, 0, 0, v22, &v330, 1, 0, 0, v252);
  IMsiData::Release(v365);
  IMsiData::Release(v292);
  v292 = (IMsiData *)&MsiString::s_NullString;
  v24 = *(_QWORD *)MsiString::MsiString((MsiString *)&v366, L"MSIINSTANCEGUID");
  v25 = MsiString::operator unsigned short const *(&v271);
  LOBYTE(v253) = 0;
  ProcessCommandLine(v25, 0, 0, 0, 0, 0, 0, v24, &v292, 1, 0, 0, v253);
  IMsiData::Release(v366);
  IMsiData::Release(v329);
  v329 = (IMsiData *)&MsiString::s_NullString;
  v26 = MsiString::MsiString((MsiString *)&v367, L"TRANSFORMSSECURE");
  LOBYTE(v254) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v26, &v329, 1, 0, 0, v254);
  IMsiData::Release(v367);
  IMsiData::Release(v328);
  v328 = (IMsiData *)&MsiString::s_NullString;
  v27 = MsiString::MsiString((MsiString *)&v368, L"TRANSFORMSATSOURCE");
  LOBYTE(v255) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v27, &v328, 1, 0, 0, v255);
  IMsiData::Release(v368);
  IMsiData::Release(v289);
  v289 = (IMsiData *)&MsiString::s_NullString;
  v28 = MsiString::MsiString((MsiString *)&v369, L"MSIPACKAGEDOWNLOADLOCALCOPY");
  LOBYTE(v256) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v28, &v289, 1, 0, 0, v256);
  IMsiData::Release(v369);
  IMsiData::Release(v327);
  v327 = (IMsiData *)&MsiString::s_NullString;
  v29 = MsiString::MsiString((MsiString *)&v370, L"MSIPATCHDOWNLOADLOCALCOPY");
  LOBYTE(v257) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v29, &v327, 1, 0, 0, v257);
  IMsiData::Release(v370);
  IMsiData::Release(v326);
  v326 = (IMsiData *)&MsiString::s_NullString;
  v30 = MsiString::MsiString((MsiString *)&v371, L"REBOOT");
  LOBYTE(v258) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v30, &v326, 1, 0, 0, v258);
  IMsiData::Release(v371);
  if ( a3 && *a3 )
    MsiString::operator=(&v304, a3);
  if ( !IsAdmin()
    && (*(_BYTE *)MsiString::operator unsigned short const *(&v326) & 0xDF) == 0x46
    && !IsClientPrivileged(L"SeShutdownPrivilege") )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"ERROR: Forcereboot flag passed, Client does not have reboot privilege",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_533;
  }
  v31 = MsiString::Compare(&v304, 0, L"ADMIN");
  v352 = v31;
  v270 = v31 != 0;
  v32 = MsiString::Compare(&v304, 0, L"ADVERTISE");
  v340 = v32;
  if ( v31 || v32 )
  {
    v286 = 1;
    if ( v31 )
      MsiString::TextSize((MsiString *)&v309);
  }
  else
  {
    v286 = 0;
  }
  v33 = 0;
  v34 = 1024;
  do
  {
    v34 >>= 1;
    ++v33;
  }
  while ( (v34 & 1) == 0 );
  MsiString::LowerCase((MsiString *)&v313);
  v293 = MsiString::Compare(&v313, 6, &aRpoedcamusv_0[v33]);
  v35 = v293;
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v327) )
  {
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v309) )
      goto LABEL_35;
    v36 = a6;
    if ( (a6 & 0x2000) == 0 || !IsAdmin() )
      goto LABEL_35;
  }
  else
  {
    v36 = a6;
  }
  v268 = 0;
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v330) )
  {
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v297) || (unsigned int)MsiString::TextSize((MsiString *)&v292) )
    {
      if ( g_dmDiagnosticMode )
      {
        v38 = L"Invalid use of MSINEWINSTANCE property.";
        goto LABEL_53;
      }
      goto LABEL_35;
    }
    if ( a1 != 1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v38 = L"Invalid use of MSINEWINSTANCE property. Use of property requires package path invocation.";
LABEL_53:
        DebugString(10, 0, 0, v38, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_35;
      }
      goto LABEL_35;
    }
    if ( v337 )
    {
      if ( g_dmDiagnosticMode )
      {
        v38 = L"Invalid use of MSINEWINSTANCE property. Multiple instance is not supported with nested installs.";
        goto LABEL_53;
      }
LABEL_35:
      PackageCodeAndLanguageFromStorage = 1639;
      goto LABEL_289;
    }
    v268 = 1;
  }
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v292) )
  {
    v39 = (const WCHAR *)MsiString::operator unsigned short const *(&v292);
    if ( ((MsiQueryProductStateW(v39) - 1) & 0xFFFFFFFB) != 0 )
    {
      if ( g_dmDiagnosticMode )
      {
        v40 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v292);
        DebugString(
          9,
          0,
          0,
          L"Specified instance %s is not installed. MSIINSTANCEGUID must reference an installed instance.",
          v40,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_35;
    }
    memset_0(v434, 0, 0xC8u);
    v432 = 100;
    v433 = 100;
    String = (wchar_t *)v434;
    v41 = (const WCHAR *)MsiString::operator unsigned short const *(&v292);
    if ( !(unsigned int)GetProductInfo(v41, L"InstanceType") || wcstol(String, 0, 10) != 1 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"Invalid use of MSIINSTANCEGUID property. This can only be used for a multiple instance install.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
      goto LABEL_35;
    }
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&String);
  }
  if ( (!g_scServerContext || g_scServerContext == 3) && (unsigned int)MsiString::TextSize((MsiString *)&v303) )
  {
    MsiServer = CreateMsiServer();
    v42 = MsiServer;
    if ( MsiServer )
    {
      if ( g_dmDiagnosticMode )
      {
        v43 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v303);
        DebugString(
          9,
          0,
          0,
          L"Removing RunOnce entry: %s",
          v43,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
        v42 = MsiServer;
      }
      v44 = *(void (__fastcall **)(struct IMsiServer *, __int64))(*(_QWORD *)v42 + 72LL);
      v45 = MsiString::operator unsigned short const *(&v303);
      v44(v42, v45);
      v35 = v293;
    }
    else if ( g_dmDiagnosticMode )
    {
      v46 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v303);
      DebugString(
        9,
        0,
        0,
        L"Cannot remove RunOnce entry: %s.  Couldn't connect to service",
        v46,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&MsiServer);
  }
  if ( a1 == 1 )
  {
    if ( (int)StringCchCopyW((unsigned __int16 *)lpString1, v407, a2) < 0 )
      goto LABEL_72;
    v404 = 1;
    if ( !(unsigned int)ExpandPath((unsigned __int16 *)lpString1) )
    {
      PackageCodeAndLanguageFromStorage = 87;
      goto LABEL_289;
    }
    CTempBuffer<unsigned short,1>::SetSize(&lpString1, (unsigned int)v403);
    if ( !lpString1 || (int)StringCchCopyW((unsigned __int16 *)lpString1, v407, v402) < 0 )
    {
LABEL_72:
      PackageCodeAndLanguageFromStorage = 14;
      goto LABEL_289;
    }
  }
  LODWORD(qword_1803136B4) = qword_1803136B4 + 1;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&lpBuffer, 260);
  if ( !lpBuffer )
  {
LABEL_77:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
    goto LABEL_72;
  }
  v47 = g_scServerContext;
  if ( !g_scServerContext || g_scServerContext == 3 )
  {
    *lpBuffer = 0;
    CurrentDirectoryW = GetCurrentDirectoryW(nBufferLength, lpBuffer);
    if ( CurrentDirectoryW > nBufferLength )
    {
      CTempBuffer<unsigned short,1>::SetSize(&lpBuffer, CurrentDirectoryW);
      if ( !lpBuffer )
        goto LABEL_77;
      *lpBuffer = 0;
      GetCurrentDirectoryW(nBufferLength, lpBuffer);
    }
    MsiString::operator+=(&v271, L" CURRENTDIRECTORY=\"");
    MsiString::operator+=(&v271, lpBuffer);
    MsiString::operator+=(&v271, L"\"");
    v49 = 2;
    if ( qword_1803138F0 != 0x2000 )
      v49 = qword_1803138F0;
    MsiString::operator+=(&v271, L" CLIENTUILEVEL=");
    v50 = MsiString::MsiString((MsiString *)&v372, v49);
    MsiString::operator+=(&v271, v50);
    IMsiData::Release(v372);
    MsiString::operator+=(&v271, L" ");
    if ( dword_180313768 || dword_180313928 )
    {
      MsiString::operator+=(&v271, L" MSICLIENTUSESEXTERNALUI=");
      v51 = MsiString::MsiString((MsiString *)&v373, 1);
      MsiString::operator+=(&v271, v51);
      IMsiData::Release(v373);
      MsiString::operator+=(&v271, L" ");
    }
    MsiString::operator+=(&v271, L" CLIENTPROCESSID=");
    CurrentProcessId = GetCurrentProcessId();
    v53 = MsiString::MsiString((MsiString *)&v374, CurrentProcessId);
    MsiString::operator+=(&v271, v53);
    IMsiData::Release(v374);
    MsiString::operator+=(&v271, L" ");
    v375 = L"SeShutdownPrivilege";
    AdjustTokenPrivileges((const unsigned __int16 **)&v375, 1, 1, 0, 0, 0);
    v376 = L"SeIncreaseQuotaPrivilege";
    AdjustTokenPrivileges((const unsigned __int16 **)&v376, 1, 1, 0, 0, 0);
    v47 = g_scServerContext;
  }
  if ( (_BYTE)dword_180313900 )
  {
    v36 |= 8u;
    a6 = v36;
  }
  if ( BYTE1(dword_180313900) )
  {
    v36 |= 0x8000u;
    a6 = v36;
  }
  if ( BYTE2(dword_180313900) )
  {
    v36 |= 0x10000u;
    a6 = v36;
  }
  if ( HIBYTE(dword_180313900) )
  {
    v36 |= 0x20000u;
    a6 = v36;
  }
  if ( byte_180313904 )
  {
    v36 |= 0x800000u;
    a6 = v36;
  }
  if ( !v337 && (!v47 || v47 == 3) && ((unsigned int)(qword_1803138F0 - 2) <= 1 || qword_1803138F0 == 0x2000) )
  {
    if ( !v47 )
    {
      if ( a1 != 1 || (v36 & 0x800) != 0 )
        goto LABEL_565;
      if ( IsInstallingFromTSClient(lpString1) )
      {
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
        PackageCodeAndLanguageFromStorage = 1645;
        goto LABEL_289;
      }
      if ( !g_scServerContext )
      {
LABEL_565:
        if ( (unsigned int)MsiString::TextSize((MsiString *)&v289) )
          goto LABEL_112;
      }
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        "Client-side and UI is none or basic: Running entire install on the server.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        0,
        0);
    v54 = MsiString::operator unsigned short const *(&v271);
    if ( a1 == 1 )
      a2 = lpString1;
    PackageCodeAndLanguageFromStorage = RunServerSideInstall(a1, a2, a3, v54, v36, v17, v360);
    g_uiReturnCode = PackageCodeAndLanguageFromStorage;
LABEL_288:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
    goto LABEL_289;
  }
  PackageCodeAndLanguageFromStorage = 0;
  if ( v47 == 2 )
  {
    v342 = (IMsiData *)&MsiString::s_NullString;
    v320 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v342 = (IMsiData *)&MsiString::s_NullString;
    v55 = MsiString::MsiString((MsiString *)&v377, L"CLIENTUILEVEL");
    LOBYTE(v259) = 0;
    ProcessCommandLine(v354, 0, 0, 0, 0, 0, 0, *(_QWORD *)v55, &v342, 1, 0, 0, v259);
    IMsiData::Release(v377);
    IMsiData::Release(v320);
    v320 = (IMsiData *)&MsiString::s_NullString;
    v56 = MsiString::MsiString((MsiString *)&v378, L"CLIENTPROCESSID");
    LOBYTE(v260) = 0;
    ProcessCommandLine(v354, 0, 0, 0, 0, 0, 0, *(_QWORD *)v56, &v320, 1, 0, 0, v260);
    IMsiData::Release(v378);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v342) )
    {
      v57 = MsiString::operator int(&v342);
      if ( v57 != 0x80000000 )
        dword_180313724 = v57;
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v320) )
    {
      v58 = MsiString::operator int(&v320);
      if ( v58 != 0x80000000 )
        dword_18031372C = v58;
    }
    IMsiData::Release(v320);
    IMsiData::Release(v342);
  }
  v59 = v361;
  if ( v361 )
  {
    MsiString::operator+=(&v271, L" ACTION=");
    MsiString::operator+=(&v271, v59);
  }
  v60 = v337;
  if ( v337 || (v266 = 0, a1 == 2) )
    v266 = 1;
  v336 = 0;
  v269 = (IMsiData *)&MsiString::s_NullString;
  if ( a1 != 1 )
  {
    if ( v286 )
      goto LABEL_244;
    if ( a1 )
      goto LABEL_270;
    if ( ((MsiQueryProductStateW(a2) - 1) & 0xFFFFFFFB) != 0 )
    {
LABEL_247:
      IMsiData::Release(v269);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
      PackageCodeAndLanguageFromStorage = 1605;
      goto LABEL_289;
    }
    memset_0(v422, 0, 0xC8u);
    v419 = (wchar_t *)v422;
    v420 = 100;
    v421 = 100;
    if ( (unsigned int)GetProductInfo(a2, L"Language") )
      v287 = wcstol(v419, 0, 10);
    v421 = 100;
    if ( (unsigned int)GetProductInfo(a2, L"InstanceType") && wcstol(v419, 0, 10) == 1 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Adding MSIINSTANCEGUID to command line.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      MsiString::operator+=(&v271, L" MSIINSTANCEGUID=");
      MsiString::operator+=(&v271, a2);
    }
    if ( (v36 & 2) != 0 )
    {
      memset_0(v426, 0, 0xC8u);
      v424 = 100;
      v425 = 100;
      v423 = (unsigned __int16 *)v426;
      if ( !(unsigned int)GetProductInfo(a2, L"Clients") )
      {
LABEL_257:
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v423);
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v419);
        goto LABEL_247;
      }
      v345 = (IMsiData *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 296LL))(v60);
      MsiString::MsiString((MsiString *)&v302, v423);
      v344 = (IMsiData *)MsiString::Extract(&v302, 0, 38);
      MsiString::Remove(&v302, 0, 39);
      if ( *(_WORD *)MsiString::operator unsigned short const *(&v302) == 58 )
      {
        v101 = MsiString::operator unsigned short const *(&v345);
        if ( !(unsigned int)MsiString::Compare(&v344, 3, v101) )
        {
          IMsiData::Release(v344);
          IMsiData::Release(v302);
          IMsiData::Release(v345);
          goto LABEL_257;
        }
        a1 = 2;
        MsiString::Remove(&v302, 0, 1);
        MsiString::Remove(&v302, 4, 1);
        MsiString::operator=(&v269, &v302);
        a2 = (const WCHAR *)MsiString::operator unsigned short const *(&v269);
        goto LABEL_266;
      }
      if ( (int)StringCchCopyW((unsigned __int16 *)szProduct, v416, a2) >= 0 )
      {
        v277 = 7;
LABEL_266:
        IMsiData::Release(v344);
        IMsiData::Release(v302);
        IMsiData::Release(v345);
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v423);
LABEL_269:
        PackageCodeAndLanguageFromStorage = 0;
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v419);
        goto LABEL_270;
      }
      IMsiData::Release(v344);
      IMsiData::Release(v302);
      IMsiData::Release(v345);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v423);
    }
    else if ( (int)StringCchCopyW((unsigned __int16 *)szProduct, v416, a2) >= 0 )
    {
      v277 = 7;
      goto LABEL_269;
    }
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>(&v419);
    goto LABEL_136;
  }
  v265 = IsURL(a2, &v267);
  if ( !v265 )
  {
    v61 = CComPointer<IEnumMsiRecord>::operator=(&v274);
    v62 = (unsigned __int16 *)a2;
LABEL_139:
    LOBYTE(NewState) = 0;
    PackageCodeAndLanguageFromStorage = OpenAndValidateMsiStorage(v62, 0, v17, v61, (_DWORD)NewState, 0, 0);
    goto LABEL_167;
  }
  if ( v267 )
  {
    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v402, 261, 0) )
    {
LABEL_136:
      IMsiData::Release(v269);
      goto LABEL_77;
    }
    v349 = v403;
    if ( MsiConvertFileUrlToFilePath(lpString1, v402, &v349, 0) )
    {
      v61 = CComPointer<IEnumMsiRecord>::operator=(&v274);
      v62 = v402;
      goto LABEL_139;
    }
LABEL_244:
    PackageCodeAndLanguageFromStorage = 87;
    goto LABEL_270;
  }
  v294 = (IMsiData *)&MsiString::s_NullString;
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v289) && g_scServerContext == 2 && IsAdmin() )
  {
    v63 = (const WCHAR *)MsiString::operator unsigned short const *(&v289);
    if ( MsiGetFileAttributesEx(v63, 0, 0, 0, 0, 0) != -1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v64 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v289);
        DebugString(
          9,
          0,
          0,
          L"Using previously downloaded file %s",
          v64,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      MsiString::operator=(&v294, &v289);
      v65 = 1;
      v265 = 1;
      goto LABEL_160;
    }
  }
  else if ( (unsigned int)MsiString::TextSize((MsiString *)&v289) )
  {
    IMsiData::Release(v294);
LABEL_149:
    IMsiData::Release(v269);
LABEL_112:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
    goto LABEL_35;
  }
  IMsiData::Release(v294);
  v294 = (IMsiData *)&MsiString::s_NullString;
  PackageCodeAndLanguageFromStorage = DownloadUrlFile(lpString1, &v294, &v265, 0);
  if ( PackageCodeAndLanguageFromStorage == 1602 )
  {
    IMsiData::Release(v294);
    IMsiData::Release(v269);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
    goto LABEL_289;
  }
  v65 = v265;
  if ( !v265 )
    goto LABEL_165;
  if ( !PackageCodeAndLanguageFromStorage )
  {
    MsiString::MsiString((MsiString *)&v379, lpString1);
    CDeleteUrlLocalFileOnClose::SetFileName((CDeleteUrlLocalFileOnClose *)&v348, v294);
    if ( IsAdmin() || g_scServerContext == 2 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Adding MSIPACKAGEDOWNLOADLOCALCOPY to command line.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      MsiString::operator+=(&v271, L" MSIPACKAGEDOWNLOADLOCALCOPY=\"");
      MsiString::operator+=(&v271, &v294);
      MsiString::operator+=(&v271, L"\" ");
    }
    IMsiData::Release(v379);
    v65 = v265;
  }
LABEL_160:
  if ( !v65 )
  {
LABEL_165:
    PackageCodeAndLanguageFromStorage = 87;
    goto LABEL_166;
  }
  if ( !PackageCodeAndLanguageFromStorage )
  {
    v66 = CComPointer<IEnumMsiRecord>::operator=(&v274);
    v67 = MsiString::operator unsigned short const *(&v294);
    LOBYTE(NewState) = 0;
    PackageCodeAndLanguageFromStorage = OpenAndValidateMsiStorage(v67, 0, v17, v66, (_DWORD)NewState, 0, 0);
    v68 = MsiString::TextSize((MsiString *)&v294);
    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v402, (unsigned int)(v68 + 1), 0) )
    {
      IMsiData::Release(v294);
      goto LABEL_136;
    }
    MsiString::CopyToBuf((MsiString *)&v294, v402, v403 - 1);
  }
LABEL_166:
  IMsiData::Release(v294);
LABEL_167:
  if ( PackageCodeAndLanguageFromStorage )
    goto LABEL_270;
  if ( !v268 )
  {
    PackageCodeAndLanguageFromStorage = GetPackageCodeAndLanguageFromStorage(v274, String2, &v287);
    if ( PackageCodeAndLanguageFromStorage )
      goto LABEL_270;
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v292) )
    {
      memset_0(ValueBuf, 0, PackageCodeAndLanguageFromStorage + 78);
      pcchValueBuf[0] = 39;
      v98 = (const WCHAR *)MsiString::operator unsigned short const *(&v292);
      if ( MsiGetProductInfoW(v98, L"PackageCode", ValueBuf, pcchValueBuf) )
      {
        if ( g_dmDiagnosticMode )
        {
          v99 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v292);
          DebugString(
            9,
            0,
            0,
            L"Unable to obtain registered PackageCode for instance install %s",
            v99,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        CComPointer<IMsiDatabase>::operator=(&v274, 0);
        goto LABEL_149;
      }
      if ( v35 || !lstrcmpiW(ValueBuf, String2) )
      {
        v100 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v292);
        if ( (int)StringCchCopyW((unsigned __int16 *)szProduct, v416, v100) < 0 )
          goto LABEL_136;
      }
    }
    else
    {
      PackageCodeAndLanguageFromStorage = MsiGetProductCodeFromPackageCodeW(String2, (unsigned __int16 *)szProduct);
    }
    v277 = 3;
    goto LABEL_270;
  }
  if ( *(_WORD *)MsiString::operator unsigned short const *(&v297) == 64 )
  {
    v69 = 3;
  }
  else
  {
    v69 = 0;
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v297) != 124 )
      goto LABEL_174;
    v69 = 4;
  }
  MsiString::Remove(&v297, 0, 1);
LABEL_174:
  if ( (unsigned int)MsiString::operator int(&v329) == 1
    || (unsigned int)MsiString::operator int(&v328) == 1
    || (unsigned int)GetIntegerPolicyValue(3, 1, 0)
    || (unsigned int)GetIntegerPolicyValue(4, 0, 0) )
  {
    v69 = 1;
  }
  v295 = (IMsiData *)&MsiString::s_NullString;
  v296 = 0;
  v298 = 0;
  v300 = 0;
  if ( !g_scServerContext || g_scServerContext == 3 )
  {
    MsiString::operator=(&v295, lpBuffer);
  }
  else
  {
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v295 = (IMsiData *)&MsiString::s_NullString;
    v70 = MsiString::MsiString((MsiString *)&v380, L"CURRENTDIRECTORY");
    LOBYTE(v259) = 0;
    ProcessCommandLine(v354, 0, 0, 0, 0, 0, 0, *(_QWORD *)v70, &v295, 1, 0, 0, v259);
    IMsiData::Release(v380);
  }
  v290 = (IMsiData *)&MsiString::s_NullString;
  v299 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release((IMsiData *)&MsiString::s_NullString);
  v299 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v290);
  v290 = (IMsiData *)&MsiString::s_NullString;
  v71 = SplitPath(lpString1, &v290, &v299);
  if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v298, v71) )
  {
    CComPointer<IMsiDatabase>::operator=(&v274, 0);
LABEL_185:
    IMsiData::Release(v299);
    IMsiData::Release(v290);
    IMsiData::Release(v295);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v300);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v298);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v296);
    IMsiData::Release(v269);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
    PackageCodeAndLanguageFromStorage = 1624;
    goto LABEL_289;
  }
  v72 = 0;
  v278 = 1;
  v268 = 0;
  v73 = v265 ? 47 : 92;
  v317 = v73;
  while ( (unsigned int)MsiString::TextSize((MsiString *)&v297) )
  {
    v280 = (IMsiData *)MsiString::ExtractAndRemove(&v297, 2, 59);
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v280) == 58 )
    {
      MsiString::Remove(&v280, 0, 1);
      v74 = v274;
      v75 = *(__int64 (__fastcall **)(struct IMsiStorage *, __int64, _QWORD, __int64))(*(_QWORD *)v274 + 64LL);
      v76 = CComPointer<IEnumMsiRecord>::operator=(&v296);
      v77 = MsiString::operator unsigned short const *(&v280);
      v78 = v75(v74, v77, 0, v76);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v298, v78) )
        goto LABEL_214;
      v72 = v268;
      goto LABEL_207;
    }
    if ( v69 <= 1 )
    {
      v79 = MsiString::operator unsigned short const *(&v280);
      v80 = PathType(v79);
      v301 = (IMsiData *)&MsiString::s_NullString;
      if ( v80 != 3 )
      {
        v231 = v69 == 0;
        v69 = 2;
        if ( !v231 )
          v69 = 3;
LABEL_199:
        MsiString::operator=(&v301, &v280);
        if ( v69 == 2 )
        {
          MsiString::operator=(&v280, &v295);
          v81 = MsiString::MsiString(&v381, 92);
          MsiString::operator+=(&v280, v81);
          v82 = v381;
        }
        else
        {
          MsiString::operator=(&v280, &v290);
          v83 = MsiString::MsiString(&v382, v73);
          MsiString::operator+=(&v280, v83);
          v82 = v382;
        }
        IMsiData::Release(v82);
        MsiString::operator+=(&v280, &v301);
        goto LABEL_203;
      }
      v69 = 4;
    }
    else
    {
      v301 = (IMsiData *)&MsiString::s_NullString;
      if ( v69 == 2 || v69 == 3 )
        goto LABEL_199;
    }
LABEL_203:
    v84 = CComPointer<IEnumMsiRecord>::operator=(&v296);
    v85 = MsiString::operator unsigned short const *(&v280);
    LOBYTE(NewState) = 0;
    if ( (unsigned int)OpenAndValidateMsiStorage(v85, 2, v323, v84, (_DWORD)NewState, 0, 0) )
    {
      if ( v69 != 2 )
        goto LABEL_216;
      MsiString::operator=(&v280, &v290);
      v86 = MsiString::MsiString(&v383, v73);
      MsiString::operator+=(&v280, v86);
      IMsiData::Release(v383);
      MsiString::operator+=(&v280, &v301);
      v87 = CComPointer<IEnumMsiRecord>::operator=(&v296);
      v88 = MsiString::operator unsigned short const *(&v280);
      LOBYTE(NewState) = 0;
      if ( (unsigned int)OpenAndValidateMsiStorage(v88, 2, v323, v87, (_DWORD)NewState, 0, 0) )
      {
LABEL_216:
        CComPointer<IMsiDatabase>::operator=(&v274, 0);
        IMsiData::Release(v301);
        goto LABEL_215;
      }
    }
    IMsiData::Release(v301);
LABEL_207:
    v89 = v296;
    v90 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v296 + 136LL);
    v91 = CComPointer<IEnumMsiRecord>::operator=(&v300);
    v92 = v90(v89, 0, v91);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v298, v92) )
    {
LABEL_214:
      CComPointer<IMsiDatabase>::operator=(&v274, 0);
LABEL_215:
      IMsiData::Release(v280);
      goto LABEL_185;
    }
    v308 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v300 + 40LL))(v300, 9);
    v343 = (IMsiData *)MsiString::Extract(&v308, 0, 38);
    MsiString::Remove(&v308, 3, 59);
    v310 = (IMsiData *)MsiString::Extract(&v308, 0, 38);
    v93 = MsiString::operator unsigned short const *(&v310);
    if ( !(unsigned int)MsiString::Compare(&v343, 1, v93) )
    {
      if ( v72 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_224;
        v97 = L"Only one product code changing transform is allowed in multiple instance support.  More than one product c"
               "ode changing transform has been supplied.";
        goto LABEL_223;
      }
      if ( !v278 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_224;
        v97 = L"The instance transform must be the first transform in the transforms list of the TRANSFORMS property";
LABEL_223:
        DebugString(10, 0, 0, v97, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_224;
      }
      v72 = 1;
      v268 = 1;
      if ( (v36 & 0x10) == 0 )
      {
        v94 = (const WCHAR *)MsiString::operator unsigned short const *(&v310);
        if ( ((MsiQueryProductStateW(v94) - 1) & 0xFFFFFFFB) == 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v95 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v297);
            v96 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v310);
            DebugString(
              10,
              0,
              0,
              L"Specified instance %s via transform %s is already installed. MSINEWINSTANCE requires a new instance that i"
               "s not installed.",
              v96,
              v95,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
LABEL_224:
          CComPointer<IMsiDatabase>::operator=(&v274, 0);
          IMsiData::Release(v310);
          IMsiData::Release(v343);
          IMsiData::Release(v308);
          IMsiData::Release(v280);
LABEL_225:
          IMsiData::Release(v299);
          IMsiData::Release(v290);
          IMsiData::Release(v295);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v300);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v298);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v296);
          goto LABEL_149;
        }
      }
    }
    v278 = 0;
    IMsiData::Release(v310);
    IMsiData::Release(v343);
    IMsiData::Release(v308);
    IMsiData::Release(v280);
    v73 = v317;
  }
  if ( !v72 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Product code changing transform not found in transforms list. MSINEWINSTANCE property requires existance of instance transform.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    CComPointer<IMsiDatabase>::operator=(&v274, 0);
    goto LABEL_225;
  }
  PackageCodeAndLanguageFromStorage = 1605;
  v277 = 3;
  IMsiData::Release(v299);
  IMsiData::Release(v290);
  IMsiData::Release(v295);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v300);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v298);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v296);
  v17 = v323;
LABEL_270:
  Record = CreateRecord(3u);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)Record + 104LL))(Record, 1);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)Record + 104LL))(Record, 2, v287);
  v102 = Record;
  v103 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)Record + 104LL);
  Codepage = MsiGetCodepage(v287);
  v103(v102, 3, Codepage);
  MsiUIMessageContext::Invoke(&g_MessageContext, 184549376, Record);
  v105 = v286;
  if ( v286 )
    goto LABEL_291;
  if ( a1 != 2 )
  {
    if ( a1 == 3 )
    {
      for ( i = 0; ; i = v110 + 2 * (5 * i - 24) )
      {
        v110 = *a2++;
        if ( !v110 )
          break;
        if ( (unsigned int)(v110 - 48) > 9 )
        {
          i = 0;
          break;
        }
      }
      MsiHandle = FindMsiHandle(i, 790541);
      CComPointer<IMsiDatabase>::operator=(&v339, MsiHandle);
      if ( !v339 )
      {
        PackageCodeAndLanguageFromStorage = 6;
        goto LABEL_286;
      }
      PackageCodeAndLanguageFromStorage = 0;
      goto LABEL_277;
    }
LABEL_291:
    if ( PackageCodeAndLanguageFromStorage && PackageCodeAndLanguageFromStorage != 1605 )
      goto LABEL_286;
LABEL_293:
    if ( v293 )
    {
      v36 |= 0x80u;
      v277 = 2;
      a6 = v36;
    }
    if ( v105 || a1 == 3 )
    {
      PackageCodeAndLanguageFromStorage = 1605;
LABEL_363:
      if ( a1 )
      {
        v277 = 2;
        goto LABEL_365;
      }
LABEL_286:
      CComPointer<IMsiDatabase>::operator=(&v274, 0);
LABEL_287:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
      IMsiData::Release(v269);
      goto LABEL_288;
    }
    if ( a1 == 2 )
    {
      *v402 = 58;
      if ( (int)StringCchCopyW(v402 + 1, v403 - 1, a2) < 0 )
      {
LABEL_299:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
        goto LABEL_136;
      }
LABEL_359:
      if ( PackageCodeAndLanguageFromStorage != 1605 )
      {
        if ( PackageCodeAndLanguageFromStorage )
          goto LABEL_286;
LABEL_365:
        v282 = (IMsiData *)&MsiString::s_NullString;
        PackageCodeAndLanguageFromStorage = 14;
        v341 = 0;
        v311 = 0;
        if ( !qword_180313730
          || CMsiTransaction::m_pMsiTransaction
          && CMsiTransaction::FMultiPackageTransaction((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction) )
        {
          goto LABEL_447;
        }
        v284 = 0;
        v276 = 0;
        v281 = (IMsiData *)&MsiString::s_NullString;
        v279 = (IMsiData *)&MsiString::s_NullString;
        v283 = 0;
        v285 = 0;
        v125 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v285);
        v126 = CMsiIpiReader::GetInProgressInstallInfo((CMsiIpiReader *)v319, v17, v125);
        if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v283, v126)
          || v285 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v285 + 24LL))(v285)
          || a1 == 2 )
        {
          goto LABEL_446;
        }
        if ( a1 == 3 )
        {
          for ( j = 0; ; j = v135 + 2 * (5 * j - 24) )
          {
            v135 = *a2++;
            if ( !v135 )
              break;
            if ( (unsigned int)(v135 - 48) > 9 )
              goto LABEL_446;
          }
          v136 = FindMsiHandle(j, 790541);
          CComPointer<IMsiDatabase>::operator=(&v276, v136);
          v133 = v276;
          if ( !v276 )
            goto LABEL_446;
        }
        else
        {
          v127 = *(__int64 (__fastcall **)(struct IMsiServices *, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v17 + 224LL);
          v128 = CComPointer<IEnumMsiRecord>::operator=(&v284);
          v129 = v127(v17, v402, 0, v128);
          if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v283, v129) )
            goto LABEL_446;
          v130 = *(__int64 (__fastcall **)(struct IMsiServices *, __int64, __int64, __int64))(*(_QWORD *)v17 + 112LL);
          v131 = CComPointer<IEnumMsiRecord>::operator=(&v276);
          v132 = v130(v17, v284, 1, v131);
          if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v283, v132) )
            goto LABEL_446;
          v133 = v276;
        }
        v288 = 0;
        v272 = 0;
        v137 = 0;
        v138 = *(_QWORD *)v133;
        v286 = 0;
        v139 = *(__int64 (__fastcall **)(struct IMsiDatabase *, _QWORD, _QWORD, __int64))(v138 + 80);
        v140 = CComPointer<IEnumMsiRecord>::operator=(&v288);
        v141 = MsiString::MsiString((MsiString *)&v386, L"Property");
        v142 = v139(v133, *(_QWORD *)v141, 0, v140);
        if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v283, v142)
          || (v143 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v288 + 128LL))(v288, 0),
              !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v272, v143)) )
        {
          v150 = 0;
        }
        else
        {
          v144 = v288;
          v145 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v288 + 96LL);
          v146 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const wchar_t *))(*(_QWORD *)v276 + 120LL))(
                   v276,
                   L"Property");
          v137 = v145(v144, v146);
          if ( v137 )
          {
            v147 = v288;
            v148 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v288 + 96LL);
            v149 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const wchar_t *))(*(_QWORD *)v276 + 120LL))(
                     v276,
                     L"Value");
            v150 = v148(v147, v149);
            if ( v150 )
            {
              v151 = 0;
LABEL_390:
              IMsiData::Release(v386);
              if ( v151 )
                goto LABEL_391;
              v152 = v272;
              v153 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 48LL);
              v154 = iColumnBit(v137);
              v153(v152, v154);
              v155 = v272;
              v156 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v272 + 96LL);
              v157 = MsiString::MsiString((MsiString *)&v387, L"ProductLanguage");
              v156(v155, v137, *(_QWORD *)v157);
              IMsiData::Release(v387);
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v272 + 40LL))(v272) )
                goto LABEL_391;
              v359 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 64LL))(v272, v150);
              v317 = MsiString::operator int(&v359);
              IMsiData::Release(v359);
              if ( !a1 )
              {
                v409 = 1;
                lpValueBuf = (LPWSTR)&v410;
                if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpValueBuf, 260, 0) )
                {
                  v331 = v409;
                  while ( 1 )
                  {
                    ProductInfoW = MsiGetProductInfoW(a2, L"ProductName", lpValueBuf, &v331);
                    if ( ProductInfoW != 234 )
                      break;
                    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpValueBuf, v331 + 1, 0) )
                      goto LABEL_395;
                  }
                  if ( !ProductInfoW )
                  {
                    MsiString::operator=(&v281, a2);
                    MsiString::operator=(&v279, lpValueBuf);
                    p_lpValueBuf = &lpValueBuf;
LABEL_416:
                    CAPITempBuffer<unsigned short,1>::Destroy(p_lpValueBuf);
LABEL_417:
                    v353 = 0;
                    v178 = *(_QWORD *)MsiString::MsiString((MsiString *)&v390, L"MSIFASTINSTALL");
                    v179 = MsiString::operator unsigned short const *(&v271);
                    LOBYTE(v259) = 0;
                    LODWORD(v178) = ProcessCommandLine(v179, 0, 0, 0, 0, 0, 0, v178, &v353, 1, 0, 0, v259);
                    IMsiData::Release(v390);
                    if ( (_DWORD)v178 )
                    {
                      if ( v353 )
                      {
                        v180 = (*(__int64 (__fastcall **)(IMsiData *))(*(_QWORD *)v353 + 32LL))(v353);
                        IMsiData::Release(v353);
                        if ( v180 == 0x80000000 )
                          LOBYTE(v180) = 0;
                      }
                      else
                      {
                        v347 = (IMsiData *)&MsiString::s_NullString;
                        LOBYTE(v180) = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v272 + 32LL))(v272);
                        v181 = v272;
                        v182 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 48LL);
                        v183 = iColumnBit(v137);
                        v182(v181, v183);
                        v184 = v272;
                        v185 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v272 + 96LL);
                        v186 = MsiString::MsiString((MsiString *)&v391, L"MSIFASTINSTALL");
                        v185(v184, v137, *(_QWORD *)v186);
                        IMsiData::Release(v391);
                        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v272 + 40LL))(v272) )
                        {
                          v187 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 64LL))(
                                               v272,
                                               v150);
                          IMsiData::Release(v347);
                          v347 = v187;
                          LOBYTE(v180) = MsiString::operator int(&v347);
                        }
                        IMsiData::Release(v347);
                      }
                      v305 = (IMsiData *)&MsiString::s_NullString;
                      v316 = (IMsiData *)&MsiString::s_NullString;
                      v318 = (IMsiData *)&MsiString::s_NullString;
                      v307 = (IMsiData *)&MsiString::s_NullString;
                      IMsiData::Release((IMsiData *)&MsiString::s_NullString);
                      v305 = (IMsiData *)&MsiString::s_NullString;
                      v188 = 2;
                      v189 = MsiString::MsiString((MsiString *)&v395, L"CLIENTUILEVEL");
                      LOBYTE(v261) = 0;
                      v190 = v354;
                      if ( !(unsigned int)ProcessCommandLine(
                                            v354,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            *(_QWORD *)v189,
                                            &v305,
                                            1,
                                            0,
                                            0,
                                            v261) )
                        goto LABEL_429;
                      IMsiData::Release(v316);
                      v316 = (IMsiData *)&MsiString::s_NullString;
                      v188 = 6;
                      v191 = MsiString::MsiString((MsiString *)&v394, L"REMOVE");
                      LOBYTE(v262) = 0;
                      if ( !(unsigned int)ProcessCommandLine(
                                            v190,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            *(_QWORD *)v191,
                                            &v316,
                                            1,
                                            0,
                                            0,
                                            v262) )
                        goto LABEL_429;
                      IMsiData::Release(v318);
                      v188 = 14;
                      v318 = (IMsiData *)&MsiString::s_NullString;
                      v192 = MsiString::MsiString((MsiString *)&v393, L"FASTOEM");
                      LOBYTE(v263) = 0;
                      if ( !(unsigned int)ProcessCommandLine(
                                            v190,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            *(_QWORD *)v192,
                                            &v318,
                                            1,
                                            0,
                                            0,
                                            v263) )
                        goto LABEL_429;
                      IMsiData::Release(v307);
                      v307 = (IMsiData *)&MsiString::s_NullString;
                      v188 = 30;
                      v193 = MsiString::MsiString((MsiString *)&v392, L"MSICLIENTUSESEMBEDDEDUI");
                      LOBYTE(v264) = 0;
                      if ( (unsigned int)ProcessCommandLine(
                                           v190,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           *(_QWORD *)v193,
                                           &v307,
                                           1,
                                           0,
                                           0,
                                           v264) )
                      {
                        v194 = 0;
                      }
                      else
                      {
LABEL_429:
                        v194 = 1;
                        if ( (v188 & 0x10) == 0 )
                        {
LABEL_431:
                          if ( (v188 & 8) != 0 )
                            IMsiData::Release(v393);
                          if ( (v188 & 4) != 0 )
                            IMsiData::Release(v394);
                          IMsiData::Release(v395);
                          if ( v194 )
                          {
                            IMsiData::Release(v307);
                            IMsiData::Release(v318);
                            IMsiData::Release(v316);
                            IMsiData::Release(v305);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v272);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v288);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v285);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v283);
                            IMsiData::Release(v279);
                            IMsiData::Release(v281);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v276);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v284);
LABEL_447:
                            v202 = a6;
                            v199 = v270;
                            goto LABEL_448;
                          }
                          v195 = 0;
                          if ( (unsigned int)MsiString::TextSize((MsiString *)&v305)
                            && (unsigned int)MsiString::operator int(&v305) != 0x80000000 )
                          {
                            v196 = MsiString::operator int(&v305);
                            if ( (unsigned int)MsiString::TextSize((MsiString *)&v307) )
                              v196 = 2;
                            v197 = (unsigned int)MsiString::Compare(&v316, 1, L"ALL") != 0;
                            if ( (v180 & 1) != 0 || (unsigned int)MsiString::TextSize((MsiString *)&v318) )
                              v195 = 1;
                            v333 = 0;
                            v334 = 0;
                            v198 = MsiString::operator unsigned short const *(&v281);
                            v199 = v270;
                            GetProductState(v198, v270, &v333, &v334);
                            v200 = MsiString::operator unsigned short const *(&v279);
                            LOWORD(v250) = v317;
                            LOBYTE(v247) = v195;
                            LOBYTE(v201) = v333 != 0;
                            LOBYTE(v246) = v197;
                            v202 = a6;
                            LOBYTE(v203) = v334 != 0;
                            LOBYTE(v244) = v352 != 0;
                            v204 = a6 >> 4;
                            LOBYTE(NewState) = v340 != 0;
                            LOBYTE(v204) = (a6 & 0x10) != 0;
                            CMsiSystemChange::SetSystemChangeInfo(
                              qword_180313730,
                              v204,
                              v203,
                              v201,
                              (_DWORD)NewState,
                              (_DWORD)v244,
                              v246,
                              v247,
                              v200,
                              v196,
                              v250);
                            CMsiSystemChange::BeginSystemChange(qword_180313730, v276);
                            IMsiData::Release(v307);
                            IMsiData::Release(v318);
                            IMsiData::Release(v316);
                            IMsiData::Release(v305);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v272);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v288);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v285);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v283);
                            IMsiData::Release(v279);
                            IMsiData::Release(v281);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v276);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v284);
LABEL_448:
                            if ( v277 == 2 )
                            {
                              if ( a1 - 2 <= 1 )
                                goto LABEL_501;
                              if ( !v265 )
                              {
                                v322 = (IMsiData *)&MsiString::s_NullString;
                                IMsiData::Release((IMsiData *)&MsiString::s_NullString);
                                v322 = (IMsiData *)&MsiString::s_NullString;
                                IMsiData::Release(v282);
                                v248 = v199;
                                v205 = v323;
                                LODWORD(v244) = 0;
                                v282 = (IMsiData *)&MsiString::s_NullString;
                                LastError = CopyTempDatabase(v402, &v282, &v341, &v322, v323, v244, &v311, v248);
                                if ( LastError )
                                  goto LABEL_481;
                                v207 = &v336;
                                if ( v266 )
                                  v207 = 0;
                                v208 = v402;
                                if ( a1 == 1 )
                                  v208 = (void *)lpString1;
                                v209 = CComPointer<IEnumMsiRecord>::operator=(&v274);
                                v210 = MsiString::operator unsigned short const *(&v282);
                                LOBYTE(NewStatea) = v266 ^ 1;
                                LastError = OpenAndValidateMsiStorage(v210, 0, v205, v209, NewStatea, v208, v207);
                                if ( LastError )
                                {
LABEL_481:
                                  CComPointer<IMsiDatabase>::operator=(&v274, 0);
                                  if ( v311 )
                                  {
                                    if ( g_scServerContext == 2 )
                                    {
                                      CElevate::CElevate((CElevate *)v396, 1);
                                      v225 = (const WCHAR *)MsiString::operator unsigned short const *(&v282);
                                      DeleteFileW(v225);
                                      CElevate::~CElevate((CElevate *)v396);
                                    }
                                    else
                                    {
                                      v226 = (const WCHAR *)MsiString::operator unsigned short const *(&v282);
                                      DeleteFileW(v226);
                                    }
                                  }
                                  IMsiData::Release(v322);
                                  goto LABEL_486;
                                }
                                if ( v341 )
                                {
                                  MsiString::operator+=(&v271, L" CURRENTMEDIAVOLUMELABEL=\"");
                                  if ( (unsigned int)MsiString::TextSize((MsiString *)&v322) )
                                    MsiString::operator+=(&v271, &v322);
                                  else
                                    MsiString::operator+=(&v271, L"?");
                                  MsiString::operator+=(&v271, L"\"");
                                }
                                IMsiData::Release(v322);
LABEL_463:
                                if ( !v265 )
                                  goto LABEL_469;
                                v211 = v403;
                                if ( v267 )
                                {
                                  if ( v403 < v407 )
                                  {
                                    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                                             &v402,
                                                             (unsigned int)v407,
                                                             0) )
                                      goto LABEL_497;
                                    v211 = v403;
                                  }
                                  if ( (int)StringCchCopyW(v402, v211, lpString1 + 7) >= 0 )
                                    goto LABEL_469;
LABEL_497:
                                  IMsiData::Release(v282);
                                  goto LABEL_287;
                                }
                                v312 = v403;
                                if ( !(unsigned int)MsiCanonicalizeUrl(lpString1, v402, &v312, 0x20000000u) )
                                {
                                  LastError = GetLastError();
                                  if ( LastError == 122 )
                                  {
                                    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v402, v312, 0) )
                                      goto LABEL_497;
                                    if ( !(unsigned int)MsiCanonicalizeUrl(lpString1, v402, &v312, 0x20000000u) )
                                      goto LABEL_521;
                                  }
                                  else if ( LastError )
                                  {
LABEL_521:
                                    CComPointer<IMsiDatabase>::operator=(&v274, 0);
                                    goto LABEL_486;
                                  }
                                }
LABEL_469:
                                LODWORD(qword_1803136B4) = qword_1803136B4 + 1;
                                v212 = v336;
                                v213 = v274;
                                v314 = 0;
                                v214 = 0;
                                v215 = v339;
                                v216 = MsiString::operator unsigned short const *(&v271);
                                LODWORD(NewState) = 2;
                                v293 = CreateInitializedEngine(
                                         v402,
                                         szProduct,
                                         v216,
                                         1,
                                         NewState,
                                         v213,
                                         v215,
                                         v337,
                                         v202,
                                         &v324,
                                         v212,
                                         v360);
                                v217 = v293;
                                CComPointer<IMsiDatabase>::operator=(&v274, 0);
                                v325 = (IMsiData *)&MsiString::s_NullString;
                                if ( !v217 )
                                {
                                  v218 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v324 + 80LL))(v324);
                                  CComPointer<IMsiDatabase>::operator=(&v314, v218);
                                  v219 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v324 + 112LL))(
                                           v324,
                                           v361,
                                           0);
                                  v362 = (IMsiData *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v324 + 800LL))(v324);
                                  MsiString::operator=(&v325, &v362);
                                  IMsiData::Release(v362);
                                  g_uiReturnCode = MapInstallActionReturnToError(v219);
                                  v220 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v324 + 48LL))(
                                           v324,
                                           v219);
                                  if ( !g_scServerContext )
                                    v214 = v220 == -3;
                                  v217 = MapInstallActionReturnToError(v220);
                                  v293 = v217;
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v324 + 16LL))(v324);
                                }
                                LODWORD(qword_1803136B4) = qword_1803136B4 + 1;
                                if ( v311 )
                                {
                                  if ( g_scServerContext == 2 )
                                  {
                                    CElevate::CElevate((CElevate *)v397, 1);
                                    v221 = (const WCHAR *)MsiString::operator unsigned short const *(&v282);
                                    if ( !DeleteFileW(v221) )
                                    {
                                      v222 = 10;
                                      if ( GetLastError() == 32 )
                                      {
                                        do
                                        {
                                          if ( v222 <= 0 )
                                            break;
                                          v223 = (const WCHAR *)MsiString::operator unsigned short const *(&v282);
                                          if ( DeleteFileW(v223) )
                                            break;
                                          --v222;
                                          v224 = GetLastError();
                                          Sleep(0xC8u);
                                        }
                                        while ( v224 == 32 );
                                      }
                                    }
                                    CElevate::~CElevate((CElevate *)v397);
                                  }
                                  else
                                  {
                                    v232 = (const WCHAR *)MsiString::operator unsigned short const *(&v282);
                                    DeleteFileW(v232);
                                  }
                                }
                                if ( v314 && (v202 & 0x103) == 0 )
                                {
                                  v355 = 0;
                                  if ( g_scServerContext == 2 )
                                  {
                                    v233 = (*(unsigned __int8 (**)(void))(*(_QWORD *)v314 + 56LL))() == 0;
                                  }
                                  else
                                  {
                                    v233 = 1;
                                    GrabExecuteMutex((struct CMutex *)&v355);
                                  }
                                  if ( g_scServerContext == 2 )
                                  {
                                    if ( g_dmDiagnosticMode )
                                      DebugString(
                                        9,
                                        0,
                                        0,
                                        L"Deferring clean up of packages/files, if any exist",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        0,
                                        0);
                                    if ( !CMsiTransaction::m_pMsiTransaction )
                                    {
                                      CMutex::Release((CMutex *)&v355);
                                      IMsiData::Release(v325);
                                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v314);
                                      IMsiData::Release(v282);
                                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
                                      IMsiData::Release(v269);
                                      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
LABEL_533:
                                      PackageCodeAndLanguageFromStorage = 1603;
                                      goto LABEL_289;
                                    }
                                    BYTE1(CMsiTransaction::m_pMsiTransaction[105].lpVtbl) = 1;
                                  }
                                  else
                                  {
                                    if ( g_dmDiagnosticMode )
                                      DebugString(
                                        9,
                                        0,
                                        0,
                                        L"Cleaning up uninstalled install packages, if any exist",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        L"(NULL)",
                                        0,
                                        0);
                                    v234 = GlobalAlloc(0x40u, 0x10u);
                                    if ( v234 )
                                    {
                                      *(_QWORD *)v234 = &CMsiClientMessage::`vftable';
                                      v234[2] = 1;
                                      _InterlockedAdd(&g_cInstances, 1u);
                                    }
                                    else
                                    {
                                      v234 = 0;
                                    }
                                    LOBYTE(v235) = v233;
                                    v398 = v234;
                                    (*(void (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v314 + 80LL))(
                                      v314,
                                      v234,
                                      v235);
                                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v398);
                                  }
                                  CMutex::Release((CMutex *)&v355);
                                }
                                if ( (unsigned int)MsiString::TextSize((MsiString *)&v325) )
                                {
                                  do
                                  {
                                    v315 = (IMsiData *)MsiString::ExtractAndRemove(&v325, 2, 59);
                                    if ( (unsigned int)MsiString::TextSize((MsiString *)&v315) )
                                    {
                                      if ( g_scServerContext == 2 )
                                      {
                                        CElevate::CElevate((CElevate *)v399, 1);
                                        if ( g_dmDiagnosticMode )
                                        {
                                          v236 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v315);
                                          DebugString(
                                            10,
                                            0,
                                            0,
                                            L"Attempting to delete file %s",
                                            v236,
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            0,
                                            0);
                                        }
                                        v237 = (const WCHAR *)MsiString::operator unsigned short const *(&v315);
                                        if ( !DeleteFileW(v237) && g_dmDiagnosticMode )
                                        {
                                          v238 = GetLastError();
                                          DebugString(
                                            10,
                                            0,
                                            0,
                                            L"Unable to delete the file outside of the engine. LastError = %d",
                                            (const unsigned __int16 *)v238,
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            0,
                                            0);
                                        }
                                        CElevate::~CElevate((CElevate *)v399);
                                      }
                                      else
                                      {
                                        if ( g_dmDiagnosticMode )
                                        {
                                          v239 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v315);
                                          DebugString(
                                            10,
                                            0,
                                            0,
                                            L"Attempting to delete file %s",
                                            v239,
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            L"(NULL)",
                                            0,
                                            0);
                                        }
                                        v240 = (const WCHAR *)MsiString::operator unsigned short const *(&v315);
                                        if ( !DeleteFileW(v240) && g_dmDiagnosticMode )
                                        {
                                          v241 = GetLastError();
                                          DebugString(
                                            10,
                                            0,
                                            0,
                                            L"Unable to delete the file outside of the engine. LastError = %d",
                                            (const unsigned __int16 *)v241,
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
                                    IMsiData::Release(v315);
                                  }
                                  while ( (unsigned int)MsiString::TextSize((MsiString *)&v325) );
                                  v217 = v293;
                                }
                                if ( v214 && v314 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v314 + 40LL))(v314);
                                CComPointer<IMsiDatabase>::operator=(&v314, 0);
                                IMsiData::Release(v325);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v314);
                                IMsiData::Release(v282);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
                                IMsiData::Release(v269);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
                                IMsiData::Release(v271);
                                IMsiData::Release(v326);
                                IMsiData::Release(v327);
                                IMsiData::Release(v289);
                                IMsiData::Release(v328);
                                IMsiData::Release(v329);
                                IMsiData::Release(v330);
                                IMsiData::Release(v292);
                                IMsiData::Release(v297);
                                IMsiData::Release(v303);
                                IMsiData::Release(v313);
                                IMsiData::Release(v309);
                                IMsiData::Release(v338);
                                IMsiData::Release(v304);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v339);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v274);
                                CDeleteUrlLocalFileOnClose::~CDeleteUrlLocalFileOnClose((CDeleteUrlLocalFileOnClose *)&v348);
                                CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>(&szProduct);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(v414);
                                CAPITempBuffer<unsigned short,1>::Destroy(&v402);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString1);
                                CImpersonate::~CImpersonate((CImpersonate *)v356);
                                CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v273);
                                return v217;
                              }
                            }
                            if ( a1 == 1 && v277 == 1 )
                            {
                              v227 = CComPointer<IEnumMsiRecord>::operator=(&v274);
                              LOBYTE(NewState) = 0;
                              LastError = OpenAndValidateMsiStorage(v402, 0, v323, v227, (_DWORD)NewState, 0, 0);
                              if ( LastError )
                              {
LABEL_486:
                                IMsiData::Release(v282);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
                                IMsiData::Release(v269);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
                                PackageCodeAndLanguageFromStorage = LastError;
                                goto LABEL_289;
                              }
                              if ( v266
                                || (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *, _QWORD))ADVAPI32::SaferCreateLevel)(
                                                   1,
                                                   0x40000,
                                                   1,
                                                   &v336,
                                                   0) )
                              {
                                v229 = v403;
                                if ( v403 < v407 )
                                {
                                  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                                           &v402,
                                                           (unsigned int)v407,
                                                           0) )
                                    goto LABEL_497;
                                  v229 = v403;
                                }
                                if ( (int)StringCchCopyW(v402, v229, lpString1) < 0 )
                                  goto LABEL_497;
                                goto LABEL_463;
                              }
                              goto LABEL_492;
                            }
LABEL_501:
                            if ( v265 && v277 == 2 && !v266 )
                            {
                              LOBYTE(v244) = 0;
                              v230 = VerifyMsiObjectAgainstSAFER(v323, v274, v402, lpString1, 0, v244, &v336);
                              if ( !v230 )
                                goto LABEL_463;
                              CComPointer<IMsiDatabase>::operator=(&v274, 0);
                              v231 = v230 == 1;
                            }
                            else
                            {
                              if ( a1 )
                              {
                                if ( a1 - 2 <= 1 )
                                  goto LABEL_463;
                              }
                              else if ( v277 == 1 )
                              {
                                if ( v266
                                  || (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *, _QWORD))ADVAPI32::SaferCreateLevel)(
                                                     1,
                                                     0x40000,
                                                     1,
                                                     &v336,
                                                     0) )
                                {
                                  goto LABEL_463;
                                }
LABEL_492:
                                if ( g_dmDiagnosticMode )
                                {
                                  v228 = GetLastError();
                                  DebugString(
                                    9,
                                    0,
                                    0,
                                    L"SAFER: Unable to create a fully trusted authorization level.  GetLastError returned %d",
                                    (const unsigned __int16 *)v228,
                                    L"(NULL)",
                                    L"(NULL)",
                                    L"(NULL)",
                                    L"(NULL)",
                                    L"(NULL)",
                                    0,
                                    0);
                                }
                                goto LABEL_494;
                              }
                              v231 = v266 == 0;
                            }
                            if ( !v231 )
                              goto LABEL_463;
LABEL_494:
                            IMsiData::Release(v282);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
                            IMsiData::Release(v269);
                            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
                            PackageCodeAndLanguageFromStorage = 1625;
                            goto LABEL_289;
                          }
                          IMsiData::Release(v307);
                          IMsiData::Release(v318);
                          IMsiData::Release(v316);
                          IMsiData::Release(v305);
                          goto LABEL_391;
                        }
                      }
                      v188 &= ~0x10u;
                      IMsiData::Release(v392);
                      goto LABEL_431;
                    }
LABEL_391:
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v272);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v288);
LABEL_446:
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v285);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v283);
                    IMsiData::Release(v279);
                    IMsiData::Release(v281);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v276);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v284);
                    goto LABEL_447;
                  }
                }
LABEL_395:
                v158 = &lpValueBuf;
LABEL_396:
                CAPITempBuffer<unsigned short,1>::Destroy(v158);
                goto LABEL_391;
              }
              if ( ((a1 - 1) & 0xFFFFFFFD) != 0 )
                goto LABEL_417;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v272 + 32LL))(v272);
              v161 = v272;
              v162 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 48LL);
              v163 = iColumnBit(v137);
              v162(v161, v163);
              v164 = v272;
              v165 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v272 + 96LL);
              v166 = MsiString::MsiString((MsiString *)&v388, L"ProductCode");
              v165(v164, v137, *(_QWORD *)v166);
              IMsiData::Release(v388);
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v272 + 40LL))(v272) )
                goto LABEL_391;
              v167 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 64LL))(v272, v150);
              IMsiData::Release(v281);
              v281 = v167;
              v411 = (LPWSTR)&v413;
              v412 = 1;
              if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v411, 260, 0) )
              {
LABEL_406:
                v158 = &v411;
                goto LABEL_396;
              }
              v332 = v412;
              while ( 1 )
              {
                v168 = v411;
                v169 = (const WCHAR *)MsiString::operator unsigned short const *(&v281);
                v170 = MsiGetProductInfoW(v169, L"ProductName", v168, &v332);
                if ( v170 != 234 )
                  break;
                if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v411, v332 + 1, 0) )
                  goto LABEL_406;
              }
              if ( v170 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v272 + 32LL))(v272);
                v171 = v272;
                v172 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 48LL);
                v173 = iColumnBit(v137);
                v172(v171, v173);
                v174 = v272;
                v175 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v272 + 96LL);
                v176 = MsiString::MsiString((MsiString *)&v389, L"ProductName");
                v175(v174, v137, *(_QWORD *)v176);
                IMsiData::Release(v389);
                if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v272 + 40LL))(v272) )
                  goto LABEL_406;
                v177 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v272 + 64LL))(v272, v150);
                IMsiData::Release(v279);
                v279 = v177;
              }
              else
              {
                MsiString::operator=(&v279, v411);
              }
              p_lpValueBuf = &v411;
              goto LABEL_416;
            }
          }
          else
          {
            v150 = v286;
          }
        }
        v151 = 1;
        goto LABEL_390;
      }
      goto LABEL_363;
    }
    if ( !*szProduct )
      goto LABEL_359;
    if ( (v36 & 0x80u) == 0 )
    {
      v404 = 1;
      PackageCodeAndLanguageFromStorage = GetPackageFullPath(szProduct);
    }
    else if ( a1 )
    {
      PackageCodeAndLanguageFromStorage = 1605;
    }
    else
    {
      v306 = (IMsiData *)&MsiString::s_NullString;
      v321 = (IMsiData *)&MsiString::s_NullString;
      v335 = 0;
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          "Attempting to recache package via ProductCode. Beginning source resolution.",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          0,
          0);
      CResolveSource::CResolveSource((CResolveSource *)v435, v17, 1);
      IMsiData::Release(v321);
      v321 = (IMsiData *)&MsiString::s_NullString;
      IMsiData::Release(v306);
      LOBYTE(v249) = 0;
      LODWORD(v245) = 1;
      v306 = (IMsiData *)&MsiString::s_NullString;
      v112 = CResolveSource::ResolveSource(v435, szProduct, 0, 1, &v306, &v321, v245, 0, v249, 0, 0);
      CComPointer<IMsiDatabase>::operator=(&v335, v112);
      if ( v335 )
      {
        PackageCodeAndLanguageFromStorage = 1605;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v335 + 56LL))(v335, 1) != 2720 )
          PackageCodeAndLanguageFromStorage = 1612;
      }
      else
      {
        CRegHandle::CRegHandle((CRegHandle *)hKey);
        LOBYTE(NewState) = 0;
        if ( (unsigned int)OpenSourceListKeyW(szProduct, 0, hKey, 0, (_DWORD)NewState) )
        {
          PackageCodeAndLanguageFromStorage = 1605;
        }
        else
        {
          v428 = 100;
          lpString = (LPCWSTR)&v430;
          v429 = 100;
          pcchValueBuf[1] = 0;
          MsiRegQueryValueExW(hKey[0], L"PackageName", (__int64)&lpString, 0);
          v113 = lstrlenW(lpString);
          v114 = (unsigned int)MsiString::TextSize((MsiString *)&v306) + v113 + 1;
          if ( v403 < (int)v114 && !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v402, v114, 0)
            || (v116 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v306),
                (int)StringCchCopyW(v402, v403, v116) < 0)
            || (int)StringCchCatW(v402, v403, lpString) < 0 )
          {
            CAPITempBuffer<unsigned short,100>::Destroy(&lpString);
            CRegHandle::~CRegHandle((CRegHandle *)hKey);
            CResolveSource::~CResolveSource((CResolveSource *)v435);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v335);
            IMsiData::Release(v321);
            v115 = v306;
LABEL_313:
            IMsiData::Release(v115);
            goto LABEL_299;
          }
          CAPITempBuffer<unsigned short,100>::Destroy(&lpString);
        }
        CRegHandle::~CRegHandle((CRegHandle *)hKey);
      }
      CResolveSource::~CResolveSource((CResolveSource *)v435);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v335);
      IMsiData::Release(v321);
      IMsiData::Release(v306);
    }
    if ( PackageCodeAndLanguageFromStorage )
      goto LABEL_359;
    if ( v265 )
      goto LABEL_365;
    v291 = (IMsiData *)&MsiString::s_NullString;
    if ( !IsURL(v402, &v267) )
      goto LABEL_352;
    if ( v267 )
    {
      v351 = v403;
      CTempBuffer<unsigned short,1>::SetSize(&lpString1, (unsigned int)v403);
      if ( !lpString1 || (int)StringCchCopyW((unsigned __int16 *)lpString1, v407, v402) < 0 )
      {
LABEL_332:
        v115 = v291;
        goto LABEL_313;
      }
      if ( MsiConvertFileUrlToFilePath(lpString1, v402, &v351, 0) )
      {
        v118 = CComPointer<IEnumMsiRecord>::operator=(&v274);
        LOBYTE(NewState) = 0;
        v117 = OpenAndValidateMsiStorage(v402, 0, v17, v118, (_DWORD)NewState, 0, 0);
      }
      else
      {
        v117 = GetLastError();
      }
      PackageCodeAndLanguageFromStorage = v117;
LABEL_352:
      if ( !v265 || PackageCodeAndLanguageFromStorage )
        goto LABEL_358;
      v122 = CComPointer<IEnumMsiRecord>::operator=(&v274);
      v123 = MsiString::operator unsigned short const *(&v291);
      LOBYTE(NewState) = 0;
      PackageCodeAndLanguageFromStorage = OpenAndValidateMsiStorage(v123, 0, v17, v122, (_DWORD)NewState, 0, 0);
      CTempBuffer<unsigned short,1>::SetSize(&lpString1, (unsigned int)v403);
      if ( lpString1 )
      {
        if ( (int)StringCchCopyW((unsigned __int16 *)lpString1, v407, v402) >= 0 )
        {
          v124 = MsiString::TextSize((MsiString *)&v291);
          if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v402, (unsigned int)(v124 + 1), 0) )
          {
            MsiString::CopyToBuf((MsiString *)&v291, v402, v403 - 1);
LABEL_358:
            IMsiData::Release(v291);
            goto LABEL_359;
          }
        }
      }
      goto LABEL_332;
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v289) && g_scServerContext == 2 && IsAdmin() )
    {
      v119 = (const WCHAR *)MsiString::operator unsigned short const *(&v289);
      if ( MsiGetFileAttributesEx(v119, 0, 0, 0, 0, 0) != -1 )
      {
        if ( g_dmDiagnosticMode )
        {
          v120 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v289);
          DebugString(
            9,
            0,
            0,
            L"Using previously downloaded file %s",
            v120,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        MsiString::operator=(&v291, &v289);
        v265 = 1;
        goto LABEL_352;
      }
    }
    else if ( (unsigned int)MsiString::TextSize((MsiString *)&v289) )
    {
      PackageCodeAndLanguageFromStorage = 1639;
      goto LABEL_352;
    }
    IMsiData::Release(v291);
    v291 = (IMsiData *)&MsiString::s_NullString;
    v121 = DownloadUrlFile(v402, &v291, &v265, 0);
    PackageCodeAndLanguageFromStorage = v121;
    if ( v121 == 1602 )
    {
      CComPointer<IMsiDatabase>::operator=(&v274, 0);
      IMsiData::Release(v291);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
      IMsiData::Release(v269);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
      PackageCodeAndLanguageFromStorage = 1602;
      goto LABEL_289;
    }
    if ( !v265 )
      goto LABEL_358;
    if ( !v121 )
    {
      MsiString::MsiString((MsiString *)&v385, v402);
      CDeleteUrlLocalFileOnClose::SetFileName((CDeleteUrlLocalFileOnClose *)&v348, v291);
      if ( IsAdmin() || g_scServerContext == 2 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Adding MSIPACKAGEDOWNLOADLOCALCOPY to command line.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        MsiString::operator+=(&v271, L" MSIPACKAGEDOWNLOADLOCALCOPY=\"");
        MsiString::operator+=(&v271, &v291);
        MsiString::operator+=(&v271, L"\" ");
      }
      IMsiData::Release(v385);
    }
    goto LABEL_352;
  }
  v384 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v337 + 72LL))(v337);
  v346 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v384 + 168LL))(v384, 1);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v384);
  v106 = v346;
  if ( !v346 )
    goto LABEL_273;
  v107 = *(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD, __int64))(*(_QWORD *)v346 + 64LL);
  v108 = CComPointer<IEnumMsiRecord>::operator=(&v274);
  v358 = v107(v106, a2, 0, v108);
  if ( !v358 )
  {
    v277 = 0;
    PackageCodeAndLanguageFromStorage = 0;
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v358);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v346);
LABEL_277:
    v105 = v286;
    goto LABEL_293;
  }
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v358);
LABEL_273:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v346);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&Record);
  IMsiData::Release(v269);
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpBuffer);
  PackageCodeAndLanguageFromStorage = 1631;
LABEL_289:
  IMsiData::Release(v271);
  IMsiData::Release(v326);
  IMsiData::Release(v327);
  IMsiData::Release(v289);
  IMsiData::Release(v328);
  IMsiData::Release(v329);
  IMsiData::Release(v330);
  IMsiData::Release(v292);
  IMsiData::Release(v297);
  IMsiData::Release(v303);
  IMsiData::Release(v313);
  IMsiData::Release(v309);
  IMsiData::Release(v338);
  IMsiData::Release(v304);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v339);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v274);
  CDeleteUrlLocalFileOnClose::~CDeleteUrlLocalFileOnClose((CDeleteUrlLocalFileOnClose *)&v348);
  CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>(&szProduct);
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(v414);
  CAPITempBuffer<unsigned short,1>::Destroy(&v402);
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&lpString1);
  CImpersonate::~CImpersonate((CImpersonate *)v356);
  CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v273);
  return PackageCodeAndLanguageFromStorage;
}

```

## disassembly

```asm
0x180140058  push    rbp
0x18014005a  push    rbx
0x18014005b  push    rsi
0x18014005c  push    rdi
0x18014005d  push    r12
0x18014005f  push    r13
0x180140061  push    r14
0x180140063  push    r15
0x180140065  lea     rbp, [rsp-9E8h]
0x18014006d  sub     rsp, 0AE8h
0x180140074  mov     rax, cs:__security_cookie
0x18014007b  xor     rax, rsp
0x18014007e  mov     [rbp+0A20h+var_50], rax
0x180140085  mov     rax, [rbp+0A20h+arg_20]
0x18014008c  xor     r12d, r12d
0x18014008f  mov     [rbp+0A20h+var_8B0], rax
0x180140096  mov     rdi, r9
0x180140099  mov     rax, [rbp+0A20h+arg_30]
0x1801400a0  mov     r14, r8
0x1801400a3  mov     [rbp+0A20h+var_808], rax
0x1801400aa  mov     r15, rdx
0x1801400ad  mov     [rbp+0A20h+var_838], r9
0x1801400b4  mov     r13d, ecx
0x1801400b7  mov     [rbp+0A20h+var_800], r8
0x1801400be  mov     [rbp+0A20h+var_898], r12d
0x1801400c5  call    ?PopulateDomainBasedAllowLockdownMediaDefault@@YAXXZ; PopulateDomainBasedAllowLockdownMediaDefault(void)
0x1801400ca  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x1801400d1  xor     ecx, ecx
0x1801400d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801400d8  mov     edx, 80000000h
0x1801400dd  mov     ecx, eax
0x1801400df  add     eax, edx
0x1801400e1  test    edx, eax
0x1801400e3  jnz     short loc_1801400F7
0x1801400e5  cmp     ecx, 80010106h
0x1801400eb  jz      short loc_1801400F7
0x1801400ed  mov     eax, 643h
0x1801400f2  jmp     loc_18014482C
0x1801400f7  shr     ecx, 1Fh
0x1801400fa  xor     cl, 1
0x1801400fd  mov     [rbp+0A20h+var_A88], cl
0x180140100  call    ?ResetCachedPolicyValuesW@@YAXXZ; ResetCachedPolicyValuesW(void)
0x180140105  mov     dl, 1; bool
0x180140107  lea     rcx, [rbp+0A20h+var_828]; this
0x18014010e  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x180140113  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18014011a  lea     rbx, aNull; "(NULL)"
0x180140121  jz      short loc_180140182
0x180140123  mov     rcx, rdi; unsigned __int16 *
0x180140126  call    ?LoggedCommandLine@@YAPEBGPEBG@Z; LoggedCommandLine(ushort const *)
0x18014012b  mov     [rsp+0B20h+var_AC8], r12; void *
0x180140130  lea     rdx, Default
0x180140137  mov     [rsp+0B20h+var_AD0], r12d; unsigned int
0x18014013c  lea     r9, aRunengineProdu; "******* RunEngine:\r\n           ******"...
0x180140143  mov     [rsp+0B20h+var_AD8], rbx; unsigned __int16 *
0x180140148  test    r14, r14
0x18014014b  mov     [rsp+0B20h+var_AE0], rbx; unsigned __int16 *
0x180140150  mov     r8, r14
0x180140153  cmovz   r8, rdx
0x180140157  mov     [rsp+0B20h+var_AE8], rbx; unsigned __int16 *
0x18014015c  mov     [rsp+0B20h+var_AF0], rax; unsigned __int16 *
0x180140161  test    r15, r15
0x180140164  mov     [rsp+0B20h+var_AF8], r8; unsigned __int16 *
0x180140169  mov     rcx, r15
0x18014016c  cmovz   rcx, rdx
0x180140170  xor     edx, edx; unsigned __int16
0x180140172  mov     [rsp+0B20h+NewState], rcx; unsigned __int16 *
0x180140177  xor     r8d, r8d; int
0x18014017a  lea     ecx, [rdx+9]; int
0x18014017d  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180140182  mov     ebx, 105h
0x180140187  test    r15, r15
0x18014018a  jz      short loc_18014019F
0x18014018c  mov     rcx, r15; lpString
0x18014018f  call    cs:__imp_lstrlenW
0x180140196  nop     dword ptr [rax+rax+00h]
0x18014019b  inc     eax
0x18014019d  jmp     short loc_1801401A1
0x18014019f  mov     eax, ebx
0x1801401a1  mov     edx, eax
0x1801401a3  lea     rcx, [rbp+0A20h+lpString1]
0x1801401aa  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801401af  lea     rax, [rbp+0A20h+var_6A0]
0x1801401b6  mov     [rbp+0A20h+var_6A8], 1
0x1801401c0  mov     edx, ebx
0x1801401c2  mov     [rbp+0A20h+var_6B0], rax
0x1801401c9  lea     rcx, [rbp+0A20h+var_650]
0x1801401d0  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x1801401d5  xor     edx, edx; Val
0x1801401d7  lea     rcx, [rbp+0A20h+var_620]; void *
0x1801401de  lea     r8d, [rdx+4Eh]; Size
0x1801401e2  call    memset_0
0x1801401e7  lea     rax, [rbp+0A20h+var_620]
0x1801401ee  mov     [rbp+0A20h+var_628], 27h ; '''
0x1801401f8  mov     [rbp+0A20h+szProduct], rax
0x1801401ff  cmp     [rbp+0A20h+lpString1], r12
0x180140206  jz      loc_1801447E2
0x18014020c  cmp     [rbp+0A20h+var_650], r12
0x180140213  jz      loc_1801447E2
0x180140219  xor     r8d, r8d
0x18014021c  lea     rcx, [rbp+0A20h+var_6B0]
0x180140223  mov     edx, ebx
0x180140225  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18014022a  test    al, al
0x18014022c  jz      loc_1801447E2
0x180140232  mov     rax, [rbp+0A20h+var_6B0]
0x180140239  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180140240  mov     rdx, rdi; unsigned __int16 *
0x180140243  lea     rcx, [rbp+0A20h+var_A98]; this
0x180140247  mov     [rax], r12w
0x18014024b  mov     rax, [rbp+0A20h+szProduct]
0x180140252  mov     [rax], r12w
0x180140256  mov     rsi, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18014025d  mov     [rbp+0A20h+var_910], rsi
0x180140264  mov     [rsp+0B20h+var_AB0], r12b
0x180140269  mov     [rsp+0B20h+var_AAE], r12b
0x18014026e  mov     [rbp+0A20h+var_860], r12
0x180140275  mov     [rbp+0A20h+var_908], r12
0x18014027c  mov     [rbp+0A20h+var_A80], r12
0x180140280  mov     [rbp+0A20h+var_8A0], r12
0x180140287  mov     [rbp+0A20h+var_A68], 7
0x18014028e  mov     [rbp+0A20h+var_A24], r12w
0x180140293  mov     [rbp+0A20h+var_9A0], rbx
0x18014029a  mov     [rbp+0A20h+var_8A8], rbx
0x1801402a1  mov     [rbp+0A20h+var_978], rbx
0x1801402a8  mov     [rbp+0A20h+var_960], rbx
0x1801402af  mov     [rbp+0A20h+var_9A8], rbx
0x1801402b3  mov     [rbp+0A20h+var_9D8], rbx
0x1801402b7  mov     [rbp+0A20h+var_A00], rbx
0x1801402bb  mov     [rbp+0A20h+var_8D8], rbx
0x1801402c2  mov     [rbp+0A20h+var_8E0], rbx
0x1801402c9  mov     [rbp+0A20h+var_8E8], rbx
0x1801402d0  mov     [rbp+0A20h+var_A18], rbx
0x1801402d4  mov     [rbp+0A20h+var_8F0], rbx
0x1801402db  mov     [rbp+0A20h+var_8F8], rbx
0x1801402e2  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801402e7  mov     rcx, [rbp+0A20h+var_960]; this
0x1801402ee  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1801402f3  lea     rdx, aReinstallmode; "REINSTALLMODE"
0x1801402fa  mov     [rbp+0A20h+var_960], rbx
0x180140301  lea     rcx, [rbp+0A20h+var_7F0]; this
0x180140308  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18014030d  mov     rcx, [rbp+0A20h+var_8A8]; this
0x180140314  mov     rbx, [rax]
0x180140317  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18014031c  mov     rcx, [rbp+0A20h+var_9A0]; this
0x180140323  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014032a  mov     [rbp+0A20h+var_8A8], rax
0x180140331  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140336  mov     rcx, [rbp+0A20h+var_978]; this
0x18014033d  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180140344  mov     [rbp+0A20h+var_9A0], rax
0x18014034b  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140350  mov     rcx, [rbp+0A20h+var_9D8]; this
0x180140354  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014035b  mov     [rbp+0A20h+var_978], rax
0x180140362  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140367  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014036e  lea     rcx, [rbp+0A20h+var_A98]
0x180140372  mov     [rbp+0A20h+var_9D8], rax
0x180140376  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18014037b  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x180140380  lea     rcx, [rbp+0A20h+var_960]
0x180140387  mov     [rsp+0B20h+var_AC8], r12
0x18014038c  lea     r9, [rbp+0A20h+var_978]
0x180140393  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x180140398  lea     r8, [rbp+0A20h+var_9D8]
0x18014039c  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x1801403a4  xor     edx, edx
0x1801403a6  mov     [rsp+0B20h+var_AE0], rcx
0x1801403ab  lea     rcx, [rbp+0A20h+var_8A8]
0x1801403b2  mov     [rsp+0B20h+var_AE8], rbx
0x1801403b7  mov     [rsp+0B20h+var_AF0], rcx
0x1801403bc  lea     rcx, [rbp+0A20h+var_9A0]
0x1801403c3  mov     [rsp+0B20h+var_AF8], rcx
0x1801403c8  mov     rcx, rax
0x1801403cb  mov     [rsp+0B20h+NewState], r12
0x1801403d0  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x1801403d5  mov     rcx, [rbp+0A20h+var_7F0]; this
0x1801403dc  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1801403e1  mov     rcx, [rbp+0A20h+var_9A8]; this
0x1801403e5  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1801403ea  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801403f1  mov     [rbp+0A20h+var_9A8], rax
0x1801403f5  lea     rdx, aRunonceentry; "RUNONCEENTRY"
0x1801403fc  lea     rcx, [rbp+0A20h+var_7E8]; this
0x180140403  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180140408  lea     rcx, [rbp+0A20h+var_A98]
0x18014040c  mov     rbx, [rax]
0x18014040f  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x180140414  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x180140419  lea     rcx, [rbp+0A20h+var_9A8]
0x18014041d  mov     [rsp+0B20h+var_AC8], r12
0x180140422  xor     r9d, r9d
0x180140425  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18014042a  xor     r8d, r8d
0x18014042d  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x180140435  xor     edx, edx
0x180140437  mov     [rsp+0B20h+var_AE0], rcx
0x18014043c  mov     rcx, rax
0x18014043f  mov     [rsp+0B20h+var_AE8], rbx
0x180140444  mov     [rsp+0B20h+var_AF0], r12
0x180140449  mov     [rsp+0B20h+var_AF8], r12
0x18014044e  mov     [rsp+0B20h+NewState], r12
0x180140453  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x180140458  mov     rcx, [rbp+0A20h+var_7E8]; this
0x18014045f  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140464  mov     rcx, [rbp+0A20h+var_8D8]; this
0x18014046b  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140470  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180140477  lea     rdx, aMsinewinstance_0; "MSINEWINSTANCE"
0x18014047e  mov     [rbp+0A20h+var_8D8], rax
0x180140485  lea     rcx, [rbp+0A20h+var_7E0]; this
0x18014048c  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180140491  lea     rcx, [rbp+0A20h+var_A98]
0x180140495  mov     rbx, [rax]
0x180140498  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18014049d  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x1801404a2  lea     rcx, [rbp+0A20h+var_8D8]
0x1801404a9  mov     [rsp+0B20h+var_AC8], r12
0x1801404ae  xor     r9d, r9d
0x1801404b1  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x1801404b6  xor     r8d, r8d
0x1801404b9  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x1801404c1  xor     edx, edx
0x1801404c3  mov     [rsp+0B20h+var_AE0], rcx
0x1801404c8  mov     rcx, rax
0x1801404cb  mov     [rsp+0B20h+var_AE8], rbx
0x1801404d0  mov     [rsp+0B20h+var_AF0], r12
0x1801404d5  mov     [rsp+0B20h+var_AF8], r12
0x1801404da  mov     [rsp+0B20h+NewState], r12
0x1801404df  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x1801404e4  mov     rcx, [rbp+0A20h+var_7E0]; this
0x1801404eb  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1801404f0  mov     rcx, [rbp+0A20h+var_A00]; this
0x1801404f4  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1801404f9  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180140500  lea     rdx, aMsiinstancegui; "MSIINSTANCEGUID"
0x180140507  mov     [rbp+0A20h+var_A00], rax
0x18014050b  lea     rcx, [rbp+0A20h+var_7D8]; this
0x180140512  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180140517  lea     rcx, [rbp+0A20h+var_A98]
0x18014051b  mov     rbx, [rax]
0x18014051e  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x180140523  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x180140528  lea     rcx, [rbp+0A20h+var_A00]
0x18014052c  mov     [rsp+0B20h+var_AC8], r12
0x180140531  xor     r9d, r9d
0x180140534  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x180140539  xor     r8d, r8d
0x18014053c  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x180140544  xor     edx, edx
0x180140546  mov     [rsp+0B20h+var_AE0], rcx
0x18014054b  mov     rcx, rax
0x18014054e  mov     [rsp+0B20h+var_AE8], rbx
0x180140553  mov     [rsp+0B20h+var_AF0], r12
0x180140558  mov     [rsp+0B20h+var_AF8], r12
0x18014055d  mov     [rsp+0B20h+NewState], r12
0x180140562  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x180140567  mov     rcx, [rbp+0A20h+var_7D8]; this
0x18014056e  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140573  mov     rcx, [rbp+0A20h+var_8E0]; this
0x18014057a  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18014057f  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180140586  mov     [rbp+0A20h+var_8E0], rax
0x18014058d  lea     rdx, aTransformssecu_1; "TRANSFORMSSECURE"
0x180140594  lea     rcx, [rbp+0A20h+var_7D0]; this
0x18014059b  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801405a0  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x1801405a5  lea     rcx, [rbp+0A20h+var_8E0]
0x1801405ac  mov     [rsp+0B20h+var_AC8], r12
0x1801405b1  mov     ebx, 1
0x1801405b6  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x1801405bb  xor     r9d, r9d
0x1801405be  mov     rax, [rax]
0x1801405c1  xor     r8d, r8d
0x1801405c4  mov     dword ptr [rsp+0B20h+var_AD8], ebx
0x1801405c8  xor     edx, edx
0x1801405ca  mov     [rsp+0B20h+var_AE0], rcx
0x1801405cf  mov     rcx, rdi
0x1801405d2  mov     [rsp+0B20h+var_AE8], rax
0x1801405d7  mov     [rsp+0B20h+var_AF0], r12
0x1801405dc  mov     [rsp+0B20h+var_AF8], r12
0x1801405e1  mov     [rsp+0B20h+NewState], r12
0x1801405e6  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x1801405eb  mov     rcx, [rbp+0A20h+var_7D0]; this
0x1801405f2  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x1801405f7  mov     rcx, [rbp+0A20h+var_8E8]; this
0x1801405fe  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x180140603  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18014060a  lea     rdx, aTransformsatso_0; "TRANSFORMSATSOURCE"
0x180140611  mov     [rbp+0A20h+var_8E8], rax
0x180140618  lea     rcx, [rbp+0A20h+var_7C8]; this
0x18014061f  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180140624  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x180140629  lea     rcx, [rbp+0A20h+var_8E8]
0x180140630  mov     [rsp+0B20h+var_AC8], r12
0x180140635  xor     r9d, r9d
0x180140638  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18014063d  xor     r8d, r8d
  ... truncated ...
```
