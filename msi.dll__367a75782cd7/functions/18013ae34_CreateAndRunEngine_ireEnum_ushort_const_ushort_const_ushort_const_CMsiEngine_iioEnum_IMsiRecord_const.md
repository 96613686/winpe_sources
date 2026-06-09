# CreateAndRunEngine(ireEnum,ushort const *,ushort const *,ushort const *,CMsiEngine *,iioEnum,IMsiRecord const *)

- ea: `0x18013ae34`
- end: `0x18013f591`
- name: `?CreateAndRunEngine@@YAHW4ireEnum@@PEBG11PEAVCMsiEngine@@W4iioEnum@@PEBVIMsiRecord@@@Z`
- size: `18269`
- prototype: `int __high(enum ireEnum, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CMsiEngine *, enum iioEnum, const struct IMsiRecord *)`
- caller_count: `3`
- callee_count: `93`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009b280`
- `0x1801c4970`
- `0x1801c4b00`

## callees

- `0x18000a150`
- `0x180015950`
- `0x18001db00`
- `0x18001f190`
- `0x180025560`
- `0x1800255e0`
- `0x180025688`
- `0x180025904`
- `0x180025a18`
- `0x18002684c`
- `0x180027f18`
- `0x180031ff0`
- `0x180035a8c`
- `0x18003bccc`
- `0x18003ca18`
- `0x18004295c`
- `0x18004ceb0`
- `0x180050cf0`
- `0x180059f24`
- `0x18005eed0`
- `0x1800629b4`
- `0x180063fc8`
- `0x180064a78`
- `0x180064b4c`
- `0x180064f18`
- `0x180066074`
- `0x180068680`
- `0x180071494`
- `0x180076e28`
- `0x180079dd0`
- `0x18007ddf4`
- `0x18008be90`
- `0x18008f3e8`
- `0x180093960`
- `0x180098b50`
- `0x180098bd8`
- `0x18009a89c`
- `0x1800a5fc4`
- `0x1800b7444`
- `0x1800b8034`
- `0x1800b8e10`
- `0x1800bc65c`
- `0x1800bc708`
- `0x1800c2854`
- `0x1800c484c`
- `0x1800ca580`
- `0x1800d3178`
- `0x1800d6f44`
- `0x1800d6ff0`
- `0x1800deab4`

## import_xrefs

- `msvcrt!wcstol` at `0x18013b8fd`
- `msvcrt!wcstol` at `0x18013cddd`
- `msvcrt!wcstol` at `0x18013ce15`
- `msvcrt!wcstol` at `0x18013b8fd`
- `msvcrt!wcstol` at `0x18013cddd`
- `msvcrt!wcstol` at `0x18013ce15`
- `KERNEL32!DeleteFileW` at `0x18013ec06`
- `KERNEL32!DeleteFileW` at `0x18013ec2e`
- `KERNEL32!DeleteFileW` at `0x18013ecac`
- `KERNEL32!DeleteFileW` at `0x18013eccc`
- `KERNEL32!DeleteFileW` at `0x18013efe2`
- `KERNEL32!DeleteFileW` at `0x18013f274`
- `KERNEL32!DeleteFileW` at `0x18013f33c`
- `KERNEL32!DeleteFileW` at `0x18013ec06`
- `KERNEL32!DeleteFileW` at `0x18013ec2e`
- `KERNEL32!DeleteFileW` at `0x18013ecac`
- `KERNEL32!DeleteFileW` at `0x18013eccc`
- `KERNEL32!DeleteFileW` at `0x18013efe2`
- `KERNEL32!DeleteFileW` at `0x18013f274`
- `KERNEL32!DeleteFileW` at `0x18013f33c`
- `KERNEL32!GetLastError` at `0x18013d809`
- `KERNEL32!GetLastError` at `0x18013ec13`
- `KERNEL32!GetLastError` at `0x18013ec38`
- `KERNEL32!GetLastError` at `0x18013ed98`
- `KERNEL32!GetLastError` at `0x18013ef6d`
- `KERNEL32!GetLastError` at `0x18013f287`
- `KERNEL32!GetLastError` at `0x18013f34f`
- `KERNEL32!GetLastError` at `0x18013d809`
- `KERNEL32!GetLastError` at `0x18013ec13`
- `KERNEL32!GetLastError` at `0x18013ec38`
- `KERNEL32!GetLastError` at `0x18013ed98`
- `KERNEL32!GetLastError` at `0x18013ef6d`
- `KERNEL32!GetLastError` at `0x18013f287`
- `KERNEL32!GetLastError` at `0x18013f34f`
- `KERNEL32!GlobalAlloc` at `0x18013f151`
- `KERNEL32!GlobalAlloc` at `0x18013f151`
- `KERNEL32!Sleep` at `0x18013ec48`
- `KERNEL32!Sleep` at `0x18013ec48`
- `KERNEL32!lstrlenW` at `0x18013af6b`
- `KERNEL32!lstrlenW` at `0x18013d617`
- `KERNEL32!lstrlenW` at `0x18013af6b`
- `KERNEL32!lstrlenW` at `0x18013d617`
- `KERNEL32!lstrcmpiW` at `0x18013ccdf`
- `KERNEL32!lstrcmpiW` at `0x18013ccdf`
- `KERNEL32!GetCurrentProcessId` at `0x18013bcb5`
- `KERNEL32!GetCurrentProcessId` at `0x18013bcb5`
- `KERNEL32!GetCurrentDirectoryW` at `0x18013bb80`
- `KERNEL32!GetCurrentDirectoryW` at `0x18013bbb8`
- `KERNEL32!GetCurrentDirectoryW` at `0x18013bb80`
- `KERNEL32!GetCurrentDirectoryW` at `0x18013bbb8`

## string_xrefs

- `0x18013bf98`: `CLIENTPROCESSID`
- `0x18013e418`: `REMOVE`
- `0x18013e1c9`: `MSIFASTINSTALL`
- `0x18013e2ce`: `MSIFASTINSTALL`
- `0x18013b5f9`: `SeShutdownPrivilege`
- `0x18013bcf9`: `SeShutdownPrivilege`
- `0x18013b0c9`: `REINSTALLMODE`
- `0x18013b24d`: `MSINEWINSTANCE`
- `0x18013b45c`: `MSIPACKAGEDOWNLOADLOCALCOPY`
- `0x18013b4d5`: `MSIPATCHDOWNLOADLOCALCOPY`
- `0x18013b2d6`: `MSIINSTANCEGUID`
- `0x18013f22e`: `Attempting to delete file %s`
- `0x18013f2f6`: `Attempting to delete file %s`
- `0x18013c51f`: `CURRENTDIRECTORY`
- `0x18013e516`: `MSICLIENTUSESEMBEDDEDUI`
- `0x18013bd27`: `SeIncreaseQuotaPrivilege`
- `0x18013edae`: `SAFER: Unable to create a fully trusted authorization level.  GetLastError returned %d`
- `0x18013af18`: `******* RunEngine:\n           ******* Product: %s\n           ******* Action: %s\n           ******* CommandLine: %s`
- `0x18013b627`: `ERROR: Forcereboot flag passed, Client does not have reboot privilege`
- `0x18013b84d`: `Invalid use of MSINEWINSTANCE property.`
- `0x18013b797`: `Invalid use of MSINEWINSTANCE property. Use of property requires package path invocation.`
- `0x18013b7b5`: `Invalid use of MSINEWINSTANCE property. Multiple instance is not supported with nested installs.`
- `0x18013b81a`: `Specified instance %s is not installed. MSIINSTANCEGUID must reference an installed instance.`
- `0x18013b9f0`: `Invalid use of MSIINSTANCEGUID property. This can only be used for a multiple instance install.`
- `0x18013ba56`: `Cannot remove RunOnce entry: %s.  Couldn't connect to service`
- `0x18013bbbe`: ` CURRENTDIRECTORY="`
- `0x18013bc5c`: ` MSICLIENTUSESEXTERNALUI=`
- `0x18013bca5`: ` CLIENTPROCESSID=`
- `0x18013be66`: `Client-side and UI is none or basic: Running entire install on the server.`
- `0x18013c341`: `Adding MSIPACKAGEDOWNLOADLOCALCOPY to command line.`
- `0x18013d9f3`: `Adding MSIPACKAGEDOWNLOADLOCALCOPY to command line.`
- `0x18013c373`: ` MSIPACKAGEDOWNLOADLOCALCOPY="`
- `0x18013da25`: ` MSIPACKAGEDOWNLOADLOCALCOPY="`
- `0x18013ca51`: `Specified instance %s via transform %s is already installed. MSINEWINSTANCE requires a new instance that is not installed.`
- `0x18013cb63`: `Product code changing transform not found in transforms list. MSINEWINSTANCE property requires existance of instance transform.`
- `0x18013cc8b`: `Unable to obtain registered PackageCode for instance install %s`
- `0x18013ce38`: `Adding MSIINSTANCEGUID to command line.`
- `0x18013ce6a`: ` MSIINSTANCEGUID=`
- `0x18013d492`: `Attempting to recache package via ProductCode. Beginning source resolution.`
- `0x18013f117`: `Cleaning up uninstalled install packages, if any exist`
- `0x18013f292`: `Unable to delete the file outside of the engine. LastError = %d`
- `0x18013f35a`: `Unable to delete the file outside of the engine. LastError = %d`

## pseudocode

```c
__int64 __fastcall CreateAndRunEngine(
        unsigned int a1,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6,
        struct IMsiRecord *a7)
{
  int v11; // ecx
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // rcx
  int v16; // eax
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
  int v36; // r12d
  unsigned int PackageCodeAndLanguageFromStorage; // r14d
  const unsigned __int16 *v38; // r9
  const WCHAR *v39; // rax
  const unsigned __int16 *v40; // rax
  const WCHAR *v41; // rax
  __int64 v42; // rbx
  const unsigned __int16 *v43; // rax
  void (__fastcall *v44)(__int64, __int64); // rdi
  __int64 v45; // rax
  const unsigned __int16 *v46; // rax
  int v47; // ecx
  DWORD CurrentDirectoryW; // eax
  unsigned int v49; // ebx
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
  _QWORD *v81; // rax
  IMsiData *v82; // rcx
  _QWORD *v83; // rax
  __int64 v84; // rbx
  __int64 v85; // rax
  _QWORD *v86; // rax
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
  __int64 (__fastcall *v127)(struct IMsiServices *, unsigned __int16 *, _QWORD, __int64, int); // rbx
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
  int NewState; // [rsp+20h] [rbp-E0h]
  int NewStatea; // [rsp+20h] [rbp-E0h]
  int v244; // [rsp+28h] [rbp-D8h]
  int v245; // [rsp+30h] [rbp-D0h]
  int v246; // [rsp+38h] [rbp-C8h]
  BOOL v247; // [rsp+38h] [rbp-C8h]
  int v248; // [rsp+40h] [rbp-C0h]
  int v249; // [rsp+50h] [rbp-B0h]
  int v250; // [rsp+60h] [rbp-A0h]
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
  bool v264; // [rsp+70h] [rbp-90h] BYREF
  char v265; // [rsp+71h] [rbp-8Fh]
  bool v266; // [rsp+72h] [rbp-8Eh] BYREF
  char v267; // [rsp+73h] [rbp-8Dh]
  IMsiData *v268; // [rsp+78h] [rbp-88h] BYREF
  BOOL v269; // [rsp+80h] [rbp-80h]
  IMsiData *v270; // [rsp+88h] [rbp-78h] BYREF
  __int64 v271; // [rsp+90h] [rbp-70h] BYREF
  bool v272[8]; // [rsp+98h] [rbp-68h] BYREF
  struct IMsiStorage *v273; // [rsp+A0h] [rbp-60h] BYREF
  struct IMsiRecord *Record; // [rsp+A8h] [rbp-58h] BYREF
  struct IMsiDatabase *v275; // [rsp+B0h] [rbp-50h] BYREF
  int v276; // [rsp+B8h] [rbp-48h]
  char v277; // [rsp+BCh] [rbp-44h]
  IMsiData *v278; // [rsp+C0h] [rbp-40h] BYREF
  IMsiData *v279; // [rsp+C8h] [rbp-38h] BYREF
  IMsiData *v280; // [rsp+D0h] [rbp-30h] BYREF
  IMsiData *v281; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v282; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v283; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v284; // [rsp+F0h] [rbp-10h] BYREF
  int v285; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v286; // [rsp+FCh] [rbp-4h] BYREF
  __int64 v287; // [rsp+100h] [rbp+0h] BYREF
  IMsiData *v288; // [rsp+108h] [rbp+8h] BYREF
  IMsiData *v289; // [rsp+110h] [rbp+10h] BYREF
  IMsiData *v290; // [rsp+118h] [rbp+18h] BYREF
  IMsiData *v291; // [rsp+120h] [rbp+20h] BYREF
  int v292; // [rsp+128h] [rbp+28h]
  IMsiData *v293; // [rsp+130h] [rbp+30h] BYREF
  IMsiData *v294; // [rsp+138h] [rbp+38h] BYREF
  __int64 v295; // [rsp+140h] [rbp+40h] BYREF
  IMsiData *v296; // [rsp+148h] [rbp+48h] BYREF
  __int64 v297; // [rsp+150h] [rbp+50h] BYREF
  IMsiData *v298; // [rsp+158h] [rbp+58h] BYREF
  __int64 v299; // [rsp+160h] [rbp+60h] BYREF
  IMsiData *v300; // [rsp+168h] [rbp+68h] BYREF
  IMsiData *v301; // [rsp+170h] [rbp+70h] BYREF
  IMsiData *v302; // [rsp+178h] [rbp+78h] BYREF
  IMsiData *v303; // [rsp+180h] [rbp+80h] BYREF
  IMsiData *v304; // [rsp+188h] [rbp+88h] BYREF
  IMsiData *v305; // [rsp+190h] [rbp+90h] BYREF
  IMsiData *v306; // [rsp+198h] [rbp+98h] BYREF
  IMsiData *v307; // [rsp+1A0h] [rbp+A0h] BYREF
  IMsiData *v308; // [rsp+1A8h] [rbp+A8h] BYREF
  IMsiData *v309; // [rsp+1B0h] [rbp+B0h] BYREF
  int v310; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned int v311; // [rsp+1BCh] [rbp+BCh] BYREF
  IMsiData *v312; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v313; // [rsp+1C8h] [rbp+C8h] BYREF
  IMsiData *v314; // [rsp+1D0h] [rbp+D0h] BYREF
  IMsiData *v315; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned int v316; // [rsp+1E0h] [rbp+E0h]
  IMsiData *v317; // [rsp+1E8h] [rbp+E8h] BYREF
  char v318[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  IMsiData *v319; // [rsp+1F8h] [rbp+F8h] BYREF
  IMsiData *v320; // [rsp+200h] [rbp+100h] BYREF
  IMsiData *v321; // [rsp+208h] [rbp+108h] BYREF
  struct IMsiServices *v322; // [rsp+210h] [rbp+110h]
  __int64 v323; // [rsp+218h] [rbp+118h] BYREF
  IMsiData *v324; // [rsp+220h] [rbp+120h] BYREF
  IMsiData *v325; // [rsp+228h] [rbp+128h] BYREF
  IMsiData *v326; // [rsp+230h] [rbp+130h] BYREF
  IMsiData *v327; // [rsp+238h] [rbp+138h] BYREF
  IMsiData *v328; // [rsp+240h] [rbp+140h] BYREF
  IMsiData *v329; // [rsp+248h] [rbp+148h] BYREF
  DWORD v330; // [rsp+250h] [rbp+150h] BYREF
  DWORD v331; // [rsp+254h] [rbp+154h] BYREF
  int v332; // [rsp+258h] [rbp+158h] BYREF
  int v333; // [rsp+25Ch] [rbp+15Ch] BYREF
  __int64 v334; // [rsp+260h] [rbp+160h] BYREF
  __int64 v335; // [rsp+268h] [rbp+168h] BYREF
  __int64 v336; // [rsp+270h] [rbp+170h]
  IMsiData *v337; // [rsp+278h] [rbp+178h] BYREF
  __int64 v338; // [rsp+280h] [rbp+180h] BYREF
  int v339; // [rsp+288h] [rbp+188h]
  int v340; // [rsp+28Ch] [rbp+18Ch] BYREF
  IMsiData *v341; // [rsp+290h] [rbp+190h] BYREF
  IMsiData *v342; // [rsp+298h] [rbp+198h] BYREF
  IMsiData *v343; // [rsp+2A0h] [rbp+1A0h] BYREF
  IMsiData *v344; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v345; // [rsp+2B0h] [rbp+1B0h] BYREF
  IMsiData *v346; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v347; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned int v348; // [rsp+2C8h] [rbp+1C8h] BYREF
  DWORD pcchValueBuf[2]; // [rsp+2CCh] [rbp+1CCh] BYREF
  unsigned int v350; // [rsp+2D4h] [rbp+1D4h] BYREF
  int v351; // [rsp+2D8h] [rbp+1D8h]
  IMsiData *v352; // [rsp+2E0h] [rbp+1E0h] BYREF
  const unsigned __int16 *v353; // [rsp+2E8h] [rbp+1E8h]
  __int64 v354; // [rsp+2F0h] [rbp+1F0h] BYREF
  char v355[8]; // [rsp+2F8h] [rbp+1F8h] BYREF
  struct IMsiServer *MsiServer; // [rsp+300h] [rbp+200h] BYREF
  __int64 v357; // [rsp+308h] [rbp+208h] BYREF
  IMsiData *v358; // [rsp+310h] [rbp+210h] BYREF
  struct IMsiRecord *v359; // [rsp+318h] [rbp+218h]
  const unsigned __int16 *v360; // [rsp+320h] [rbp+220h]
  IMsiData *v361; // [rsp+328h] [rbp+228h] BYREF
  IMsiData *v362; // [rsp+330h] [rbp+230h] BYREF
  IMsiData *v363; // [rsp+338h] [rbp+238h] BYREF
  IMsiData *v364; // [rsp+340h] [rbp+240h] BYREF
  IMsiData *v365; // [rsp+348h] [rbp+248h] BYREF
  IMsiData *v366; // [rsp+350h] [rbp+250h] BYREF
  IMsiData *v367; // [rsp+358h] [rbp+258h] BYREF
  IMsiData *v368; // [rsp+360h] [rbp+260h] BYREF
  IMsiData *v369; // [rsp+368h] [rbp+268h] BYREF
  IMsiData *v370; // [rsp+370h] [rbp+270h] BYREF
  IMsiData *v371; // [rsp+378h] [rbp+278h] BYREF
  IMsiData *v372; // [rsp+380h] [rbp+280h] BYREF
  IMsiData *v373; // [rsp+388h] [rbp+288h] BYREF
  unsigned __int16 *v374; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 *v375; // [rsp+398h] [rbp+298h] BYREF
  IMsiData *v376; // [rsp+3A0h] [rbp+2A0h] BYREF
  IMsiData *v377; // [rsp+3A8h] [rbp+2A8h] BYREF
  IMsiData *v378; // [rsp+3B0h] [rbp+2B0h] BYREF
  IMsiData *v379; // [rsp+3B8h] [rbp+2B8h] BYREF
  IMsiData *v380; // [rsp+3C0h] [rbp+2C0h] BYREF
  IMsiData *v381; // [rsp+3C8h] [rbp+2C8h] BYREF
  IMsiData *v382; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v383; // [rsp+3D8h] [rbp+2D8h] BYREF
  IMsiData *v384; // [rsp+3E0h] [rbp+2E0h] BYREF
  IMsiData *v385; // [rsp+3E8h] [rbp+2E8h] BYREF
  IMsiData *v386; // [rsp+3F0h] [rbp+2F0h] BYREF
  IMsiData *v387; // [rsp+3F8h] [rbp+2F8h] BYREF
  IMsiData *v388; // [rsp+400h] [rbp+300h] BYREF
  IMsiData *v389; // [rsp+408h] [rbp+308h] BYREF
  IMsiData *v390; // [rsp+410h] [rbp+310h] BYREF
  IMsiData *v391; // [rsp+418h] [rbp+318h] BYREF
  IMsiData *v392; // [rsp+420h] [rbp+320h] BYREF
  IMsiData *v393; // [rsp+428h] [rbp+328h] BYREF
  IMsiData *v394; // [rsp+430h] [rbp+330h] BYREF
  char v395[8]; // [rsp+438h] [rbp+338h] BYREF
  char v396[8]; // [rsp+440h] [rbp+340h] BYREF
  _DWORD *v397; // [rsp+448h] [rbp+348h] BYREF
  char v398[8]; // [rsp+450h] [rbp+350h] BYREF
  LPWSTR lpBuffer; // [rsp+458h] [rbp+358h] BYREF
  DWORD nBufferLength; // [rsp+460h] [rbp+360h]
  unsigned __int16 *v401; // [rsp+470h] [rbp+370h] BYREF
  signed int v402; // [rsp+478h] [rbp+378h]
  int v403; // [rsp+47Ch] [rbp+37Ch]
  char v404; // [rsp+480h] [rbp+380h] BYREF
  PCNZWCH lpString1; // [rsp+488h] [rbp+388h] BYREF
  signed int v406; // [rsp+490h] [rbp+390h]
  LPWSTR lpValueBuf; // [rsp+4A0h] [rbp+3A0h] BYREF
  DWORD v408; // [rsp+4A8h] [rbp+3A8h]
  char v409; // [rsp+4B0h] [rbp+3B0h] BYREF
  LPWSTR v410; // [rsp+4B8h] [rbp+3B8h] BYREF
  DWORD v411; // [rsp+4C0h] [rbp+3C0h]
  char v412; // [rsp+4C8h] [rbp+3C8h] BYREF
  _QWORD v413[4]; // [rsp+4D0h] [rbp+3D0h] BYREF
  LPCWSTR szProduct; // [rsp+4F0h] [rbp+3F0h] BYREF
  int v415; // [rsp+4F8h] [rbp+3F8h]
  _BYTE v416[80]; // [rsp+500h] [rbp+400h] BYREF
  struct _RTL_CRITICAL_SECTION hKey[2]; // [rsp+550h] [rbp+450h] BYREF
  wchar_t *v418; // [rsp+5A0h] [rbp+4A0h] BYREF
  int v419; // [rsp+5A8h] [rbp+4A8h]
  int v420; // [rsp+5ACh] [rbp+4ACh]
  _BYTE v421[208]; // [rsp+5B0h] [rbp+4B0h] BYREF
  unsigned __int16 *v422; // [rsp+680h] [rbp+580h] BYREF
  int v423; // [rsp+688h] [rbp+588h]
  int v424; // [rsp+68Ch] [rbp+58Ch]
  _BYTE v425[208]; // [rsp+690h] [rbp+590h] BYREF
  LPCWSTR lpString; // [rsp+760h] [rbp+660h] BYREF
  int v427; // [rsp+768h] [rbp+668h]
  int v428; // [rsp+76Ch] [rbp+66Ch]
  char v429; // [rsp+770h] [rbp+670h] BYREF
  wchar_t *String; // [rsp+840h] [rbp+740h] BYREF
  int v431; // [rsp+848h] [rbp+748h]
  int v432; // [rsp+84Ch] [rbp+74Ch]
  _BYTE v433[208]; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v434[272]; // [rsp+920h] [rbp+820h] BYREF
  WCHAR ValueBuf[40]; // [rsp+A30h] [rbp+930h] BYREF
  WCHAR String2[40]; // [rsp+A80h] [rbp+980h] BYREF

  v336 = a5;
  v359 = a7;
  v353 = a4;
  v360 = a3;
  v339 = 0;
  PopulateDomainBasedAllowLockdownMediaDefault();
  v11 = ((__int64 (__fastcall *)(_QWORD))OLE32::CoInitialize)(0);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147417850 )
    return 1603;
  v272[0] = v11 >= 0;
  ResetCachedPolicyValuesW();
  CImpersonate::CImpersonate((CImpersonate *)v355, 1);
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
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>((__int64)&lpString1, v16);
  v402 = 1;
  v401 = (unsigned __int16 *)&v404;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>((__int64)v413, 261);
  memset_0(v416, 0, 0x4Eu);
  v415 = 39;
  szProduct = (LPCWSTR)v416;
  if ( !lpString1 || !v413[0] || !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v401, 261, 0) )
  {
    CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>((__int64)&szProduct);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)v413);
    CAPITempBuffer<unsigned short,1>::Destroy(&v401);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpString1);
    CImpersonate::~CImpersonate((CImpersonate *)v355);
    CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v272);
    return 14;
  }
  *v401 = 0;
  *szProduct = 0;
  v17 = g_piSharedServices;
  v322 = g_piSharedServices;
  v264 = 0;
  v266 = 0;
  v347 = 0;
  v323 = 0;
  v273 = 0;
  v338 = 0;
  v276 = 7;
  v286 = 0;
  v303 = (IMsiData *)&MsiString::s_NullString;
  v337 = (IMsiData *)&MsiString::s_NullString;
  v308 = (IMsiData *)&MsiString::s_NullString;
  v312 = (IMsiData *)&MsiString::s_NullString;
  v302 = (IMsiData *)&MsiString::s_NullString;
  v296 = (IMsiData *)&MsiString::s_NullString;
  v291 = (IMsiData *)&MsiString::s_NullString;
  v329 = (IMsiData *)&MsiString::s_NullString;
  v328 = (IMsiData *)&MsiString::s_NullString;
  v327 = (IMsiData *)&MsiString::s_NullString;
  v288 = (IMsiData *)&MsiString::s_NullString;
  v326 = (IMsiData *)&MsiString::s_NullString;
  v325 = (IMsiData *)&MsiString::s_NullString;
  MsiString::MsiString((MsiString *)&v270, a4);
  IMsiData::Release(v312);
  v312 = (IMsiData *)&MsiString::s_NullString;
  v18 = *(_QWORD *)MsiString::MsiString((MsiString *)&v362, L"REINSTALLMODE");
  IMsiData::Release(v337);
  v337 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v303);
  v303 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v308);
  v308 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v296);
  v296 = (IMsiData *)&MsiString::s_NullString;
  v19 = MsiString::operator unsigned short const *(&v270);
  ProcessCommandLine(v19, 0, &v296, &v308, 0, &v303, &v337, v18, &v312, 1, 0, 0, 0);
  IMsiData::Release(v362);
  IMsiData::Release(v302);
  v302 = (IMsiData *)&MsiString::s_NullString;
  v20 = *(_QWORD *)MsiString::MsiString((MsiString *)&v363, L"RUNONCEENTRY");
  v21 = MsiString::operator unsigned short const *(&v270);
  LOBYTE(v250) = 0;
  ProcessCommandLine(v21, 0, 0, 0, 0, 0, 0, v20, &v302, 1, 0, 0, v250);
  IMsiData::Release(v363);
  IMsiData::Release(v329);
  v329 = (IMsiData *)&MsiString::s_NullString;
  v22 = *(_QWORD *)MsiString::MsiString((MsiString *)&v364, L"MSINEWINSTANCE");
  v23 = MsiString::operator unsigned short const *(&v270);
  LOBYTE(v251) = 0;
  ProcessCommandLine(v23, 0, 0, 0, 0, 0, 0, v22, &v329, 1, 0, 0, v251);
  IMsiData::Release(v364);
  IMsiData::Release(v291);
  v291 = (IMsiData *)&MsiString::s_NullString;
  v24 = *(_QWORD *)MsiString::MsiString((MsiString *)&v365, L"MSIINSTANCEGUID");
  v25 = MsiString::operator unsigned short const *(&v270);
  LOBYTE(v252) = 0;
  ProcessCommandLine(v25, 0, 0, 0, 0, 0, 0, v24, &v291, 1, 0, 0, v252);
  IMsiData::Release(v365);
  IMsiData::Release(v328);
  v328 = (IMsiData *)&MsiString::s_NullString;
  v26 = MsiString::MsiString((MsiString *)&v366, L"TRANSFORMSSECURE");
  LOBYTE(v253) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v26, &v328, 1, 0, 0, v253);
  IMsiData::Release(v366);
  IMsiData::Release(v327);
  v327 = (IMsiData *)&MsiString::s_NullString;
  v27 = MsiString::MsiString((MsiString *)&v367, L"TRANSFORMSATSOURCE");
  LOBYTE(v254) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v27, &v327, 1, 0, 0, v254);
  IMsiData::Release(v367);
  IMsiData::Release(v288);
  v288 = (IMsiData *)&MsiString::s_NullString;
  v28 = MsiString::MsiString((MsiString *)&v368, L"MSIPACKAGEDOWNLOADLOCALCOPY");
  LOBYTE(v255) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v28, &v288, 1, 0, 0, v255);
  IMsiData::Release(v368);
  IMsiData::Release(v326);
  v326 = (IMsiData *)&MsiString::s_NullString;
  v29 = MsiString::MsiString((MsiString *)&v369, L"MSIPATCHDOWNLOADLOCALCOPY");
  LOBYTE(v256) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v29, &v326, 1, 0, 0, v256);
  IMsiData::Release(v369);
  IMsiData::Release(v325);
  v325 = (IMsiData *)&MsiString::s_NullString;
  v30 = MsiString::MsiString((MsiString *)&v370, L"REBOOT");
  LOBYTE(v257) = 0;
  ProcessCommandLine(a4, 0, 0, 0, 0, 0, 0, *(_QWORD *)v30, &v325, 1, 0, 0, v257);
  IMsiData::Release(v370);
  if ( a3 && *a3 )
    MsiString::operator=(&v303, a3);
  if ( !IsAdmin()
    && (*(_BYTE *)MsiString::operator unsigned short const *(&v325) & 0xDF) == 0x46
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
  v31 = MsiString::Compare(&v303, 0, L"ADMIN");
  v351 = v31;
  v269 = v31 != 0;
  v32 = MsiString::Compare(&v303, 0, L"ADVERTISE");
  v339 = v32;
  if ( v31 || v32 )
  {
    v285 = 1;
    if ( v31 )
      MsiString::TextSize((MsiString *)&v308);
  }
  else
  {
    v285 = 0;
  }
  v33 = 0;
  v34 = 1024;
  do
  {
    v34 >>= 1;
    ++v33;
  }
  while ( (v34 & 1) == 0 );
  MsiString::LowerCase((MsiString *)&v312);
  v292 = MsiString::Compare(&v312, 6, &aRpoedcamusv_0[v33]);
  v35 = v292;
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v326) )
  {
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v308) )
      goto LABEL_35;
    v36 = a6;
    if ( (a6 & 0x2000) == 0 || !IsAdmin() )
      goto LABEL_35;
  }
  else
  {
    v36 = a6;
  }
  v267 = 0;
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v329) )
  {
    if ( !(unsigned int)MsiString::TextSize((MsiString *)&v296) || (unsigned int)MsiString::TextSize((MsiString *)&v291) )
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
    if ( v336 )
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
    v267 = 1;
  }
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v291) )
  {
    v39 = (const WCHAR *)MsiString::operator unsigned short const *(&v291);
    if ( ((MsiQueryProductStateW(v39) - 1) & 0xFFFFFFFB) != 0 )
    {
      if ( g_dmDiagnosticMode )
      {
        v40 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v291);
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
    memset_0(v433, 0, 0xC8u);
    v431 = 100;
    v432 = 100;
    String = (wchar_t *)v433;
    v41 = (const WCHAR *)MsiString::operator unsigned short const *(&v291);
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
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
      goto LABEL_35;
    }
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&String);
  }
  if ( (!g_scServerContext || g_scServerContext == 3) && (unsigned int)MsiString::TextSize((MsiString *)&v302) )
  {
    MsiServer = CreateMsiServer();
    v42 = (__int64)MsiServer;
    if ( MsiServer )
    {
      if ( g_dmDiagnosticMode )
      {
        v43 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v302);
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
        v42 = (__int64)MsiServer;
      }
      v44 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 72LL);
      v45 = MsiString::operator unsigned short const *(&v302);
      v44(v42, v45);
      v35 = v292;
    }
    else if ( g_dmDiagnosticMode )
    {
      v46 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v302);
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
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&MsiServer);
  }
  if ( a1 == 1 )
  {
    if ( (int)StringCchCopyW((unsigned __int16 *)lpString1, v406, a2) < 0 )
      goto LABEL_72;
    v403 = 1;
    if ( !(unsigned int)ExpandPath((unsigned __int16 *)lpString1) )
    {
      PackageCodeAndLanguageFromStorage = 87;
      goto LABEL_289;
    }
    CTempBuffer<unsigned short,1>::SetSize(&lpString1);
    if ( !lpString1 || (int)StringCchCopyW((unsigned __int16 *)lpString1, v406, v401) < 0 )
    {
LABEL_72:
      PackageCodeAndLanguageFromStorage = 14;
      goto LABEL_289;
    }
  }
  LODWORD(qword_180309704) = qword_180309704 + 1;
  CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>((__int64)&lpBuffer, 260);
  if ( !lpBuffer )
  {
LABEL_77:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
    goto LABEL_72;
  }
  v47 = g_scServerContext;
  if ( !g_scServerContext || g_scServerContext == 3 )
  {
    *lpBuffer = 0;
    CurrentDirectoryW = GetCurrentDirectoryW(nBufferLength, lpBuffer);
    if ( CurrentDirectoryW > nBufferLength )
    {
      CTempBuffer<unsigned short,1>::SetSize(&lpBuffer);
      if ( !lpBuffer )
        goto LABEL_77;
      *lpBuffer = 0;
      GetCurrentDirectoryW(nBufferLength, lpBuffer);
    }
    MsiString::operator+=(&v270, L" CURRENTDIRECTORY=\"");
    MsiString::operator+=(&v270, lpBuffer);
    MsiString::operator+=(&v270, L"\"");
    v49 = 2;
    if ( qword_180309940 != 0x2000 )
      v49 = qword_180309940;
    MsiString::operator+=(&v270, L" CLIENTUILEVEL=");
    v50 = MsiString::MsiString((MsiString *)&v371, v49);
    MsiString::operator+=(&v270, v50);
    IMsiData::Release(v371);
    MsiString::operator+=(&v270, L" ");
    if ( dword_1803097B8 || dword_180309978 )
    {
      MsiString::operator+=(&v270, L" MSICLIENTUSESEXTERNALUI=");
      v51 = MsiString::MsiString((MsiString *)&v372, 1);
      MsiString::operator+=(&v270, v51);
      IMsiData::Release(v372);
      MsiString::operator+=(&v270, L" ");
    }
    MsiString::operator+=(&v270, L" CLIENTPROCESSID=");
    CurrentProcessId = GetCurrentProcessId();
    v53 = MsiString::MsiString((MsiString *)&v373, CurrentProcessId);
    MsiString::operator+=(&v270, v53);
    IMsiData::Release(v373);
    MsiString::operator+=(&v270, L" ");
    v374 = L"SeShutdownPrivilege";
    AdjustTokenPrivileges((const unsigned __int16 **)&v374, 1, 1, 0, 0, 0);
    v375 = L"SeIncreaseQuotaPrivilege";
    AdjustTokenPrivileges((const unsigned __int16 **)&v375, 1, 1, 0, 0, 0);
    v47 = g_scServerContext;
  }
  if ( (_BYTE)dword_180309950 )
  {
    v36 |= 8u;
    a6 = v36;
  }
  if ( BYTE1(dword_180309950) )
  {
    v36 |= 0x8000u;
    a6 = v36;
  }
  if ( BYTE2(dword_180309950) )
  {
    v36 |= 0x10000u;
    a6 = v36;
  }
  if ( HIBYTE(dword_180309950) )
  {
    v36 |= 0x20000u;
    a6 = v36;
  }
  if ( byte_180309954 )
  {
    v36 |= 0x800000u;
    a6 = v36;
  }
  if ( !v336 && (!v47 || v47 == 3) && ((unsigned int)(qword_180309940 - 2) <= 1 || qword_180309940 == 0x2000) )
  {
    if ( !v47 )
    {
      if ( a1 != 1 || (v36 & 0x800) != 0 )
        goto LABEL_565;
      if ( IsInstallingFromTSClient(lpString1) )
      {
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
        PackageCodeAndLanguageFromStorage = 1645;
        goto LABEL_289;
      }
      if ( !g_scServerContext )
      {
LABEL_565:
        if ( (unsigned int)MsiString::TextSize((MsiString *)&v288) )
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
    v54 = MsiString::operator unsigned short const *(&v270);
    if ( a1 == 1 )
      a2 = lpString1;
    PackageCodeAndLanguageFromStorage = RunServerSideInstall(a1, a2, (__int64)a3, v54, v36, (__int64)v17, v359);
    g_uiReturnCode = PackageCodeAndLanguageFromStorage;
LABEL_288:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
    goto LABEL_289;
  }
  PackageCodeAndLanguageFromStorage = 0;
  if ( v47 == 2 )
  {
    v341 = (IMsiData *)&MsiString::s_NullString;
    v319 = (IMsiData *)&MsiString::s_NullString;
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v341 = (IMsiData *)&MsiString::s_NullString;
    v55 = MsiString::MsiString((MsiString *)&v376, L"CLIENTUILEVEL");
    LOBYTE(v258) = 0;
    ProcessCommandLine(v353, 0, 0, 0, 0, 0, 0, *(_QWORD *)v55, &v341, 1, 0, 0, v258);
    IMsiData::Release(v376);
    IMsiData::Release(v319);
    v319 = (IMsiData *)&MsiString::s_NullString;
    v56 = MsiString::MsiString((MsiString *)&v377, L"CLIENTPROCESSID");
    LOBYTE(v259) = 0;
    ProcessCommandLine(v353, 0, 0, 0, 0, 0, 0, *(_QWORD *)v56, &v319, 1, 0, 0, v259);
    IMsiData::Release(v377);
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v341) )
    {
      v57 = MsiString::operator int(&v341);
      if ( v57 != 0x80000000 )
        dword_180309774 = v57;
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v319) )
    {
      v58 = MsiString::operator int(&v319);
      if ( v58 != 0x80000000 )
        dword_18030977C = v58;
    }
    IMsiData::Release(v319);
    IMsiData::Release(v341);
  }
  v59 = v360;
  if ( v360 )
  {
    MsiString::operator+=(&v270, L" ACTION=");
    MsiString::operator+=(&v270, v59);
  }
  v60 = v336;
  if ( v336 || (v265 = 0, a1 == 2) )
    v265 = 1;
  v335 = 0;
  v268 = (IMsiData *)&MsiString::s_NullString;
  if ( a1 != 1 )
  {
    if ( v285 )
      goto LABEL_244;
    if ( a1 )
      goto LABEL_270;
    if ( ((MsiQueryProductStateW(a2) - 1) & 0xFFFFFFFB) != 0 )
    {
LABEL_247:
      IMsiData::Release(v268);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
      PackageCodeAndLanguageFromStorage = 1605;
      goto LABEL_289;
    }
    memset_0(v421, 0, 0xC8u);
    v418 = (wchar_t *)v421;
    v419 = 100;
    v420 = 100;
    if ( (unsigned int)GetProductInfo(a2, L"Language") )
      v286 = wcstol(v418, 0, 10);
    v420 = 100;
    if ( (unsigned int)GetProductInfo(a2, L"InstanceType") && wcstol(v418, 0, 10) == 1 )
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
      MsiString::operator+=(&v270, L" MSIINSTANCEGUID=");
      MsiString::operator+=(&v270, a2);
    }
    if ( (v36 & 2) != 0 )
    {
      memset_0(v425, 0, 0xC8u);
      v423 = 100;
      v424 = 100;
      v422 = (unsigned __int16 *)v425;
      if ( !(unsigned int)GetProductInfo(a2, L"Clients") )
      {
LABEL_257:
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v422);
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v418);
        goto LABEL_247;
      }
      v344 = (IMsiData *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 296LL))(v60);
      MsiString::MsiString((MsiString *)&v301, v422);
      v343 = (IMsiData *)MsiString::Extract(&v301, 0, 38);
      MsiString::Remove(&v301, 0, 39);
      if ( *(_WORD *)MsiString::operator unsigned short const *(&v301) == 58 )
      {
        v101 = MsiString::operator unsigned short const *(&v344);
        if ( !(unsigned int)MsiString::Compare(&v343, 3, v101) )
        {
          IMsiData::Release(v343);
          IMsiData::Release(v301);
          IMsiData::Release(v344);
          goto LABEL_257;
        }
        a1 = 2;
        MsiString::Remove(&v301, 0, 1);
        MsiString::Remove(&v301, 4, 1);
        MsiString::operator=(&v268, &v301);
        a2 = (const WCHAR *)MsiString::operator unsigned short const *(&v268);
        goto LABEL_266;
      }
      if ( (int)StringCchCopyW((unsigned __int16 *)szProduct, v415, a2) >= 0 )
      {
        v276 = 7;
LABEL_266:
        IMsiData::Release(v343);
        IMsiData::Release(v301);
        IMsiData::Release(v344);
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v422);
LABEL_269:
        PackageCodeAndLanguageFromStorage = 0;
        CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v418);
        goto LABEL_270;
      }
      IMsiData::Release(v343);
      IMsiData::Release(v301);
      IMsiData::Release(v344);
      CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v422);
    }
    else if ( (int)StringCchCopyW((unsigned __int16 *)szProduct, v415, a2) >= 0 )
    {
      v276 = 7;
      goto LABEL_269;
    }
    CTempBuffer<unsigned short,100>::~CTempBuffer<unsigned short,100>((__int64)&v418);
    goto LABEL_136;
  }
  v264 = IsURL(a2, &v266);
  if ( !v264 )
  {
    v61 = CComPointer<IEnumMsiRecord>::operator=(&v273);
    v62 = (unsigned __int16 *)a2;
LABEL_139:
    LOBYTE(NewState) = 0;
    PackageCodeAndLanguageFromStorage = OpenAndValidateMsiStorage(v62, 0, v17, v61, NewState, 0, 0);
    goto LABEL_167;
  }
  if ( v266 )
  {
    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v401, 261, 0) )
    {
LABEL_136:
      IMsiData::Release(v268);
      goto LABEL_77;
    }
    v348 = v402;
    if ( MsiConvertFileUrlToFilePath(lpString1, v401, &v348, 0) )
    {
      v61 = CComPointer<IEnumMsiRecord>::operator=(&v273);
      v62 = v401;
      goto LABEL_139;
    }
LABEL_244:
    PackageCodeAndLanguageFromStorage = 87;
    goto LABEL_270;
  }
  v293 = (IMsiData *)&MsiString::s_NullString;
  if ( (unsigned int)MsiString::TextSize((MsiString *)&v288) && g_scServerContext == 2 && IsAdmin() )
  {
    v63 = (const WCHAR *)MsiString::operator unsigned short const *(&v288);
    if ( MsiGetFileAttributesEx(v63, 0, 0, 0, 0, 0) != -1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v64 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v288);
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
      MsiString::operator=(&v293, &v288);
      v65 = 1;
      v264 = 1;
      goto LABEL_160;
    }
  }
  else if ( (unsigned int)MsiString::TextSize((MsiString *)&v288) )
  {
    IMsiData::Release(v293);
LABEL_149:
    IMsiData::Release(v268);
LABEL_112:
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
    goto LABEL_35;
  }
  IMsiData::Release(v293);
  v293 = (IMsiData *)&MsiString::s_NullString;
  PackageCodeAndLanguageFromStorage = DownloadUrlFile(lpString1, &v293, &v264, 0);
  if ( PackageCodeAndLanguageFromStorage == 1602 )
  {
    IMsiData::Release(v293);
    IMsiData::Release(v268);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
    goto LABEL_289;
  }
  v65 = v264;
  if ( !v264 )
    goto LABEL_165;
  if ( !PackageCodeAndLanguageFromStorage )
  {
    MsiString::MsiString((MsiString *)&v378, lpString1);
    CDeleteUrlLocalFileOnClose::SetFileName((CDeleteUrlLocalFileOnClose *)&v347, v293);
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
      MsiString::operator+=(&v270, L" MSIPACKAGEDOWNLOADLOCALCOPY=\"");
      MsiString::operator+=(&v270, &v293);
      MsiString::operator+=(&v270, L"\" ");
    }
    IMsiData::Release(v378);
    v65 = v264;
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
    v66 = CComPointer<IEnumMsiRecord>::operator=(&v273);
    v67 = MsiString::operator unsigned short const *(&v293);
    LOBYTE(NewState) = 0;
    PackageCodeAndLanguageFromStorage = OpenAndValidateMsiStorage(v67, 0, v17, v66, NewState, 0, 0);
    v68 = MsiString::TextSize((MsiString *)&v293);
    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v401, (unsigned int)(v68 + 1), 0) )
    {
      IMsiData::Release(v293);
      goto LABEL_136;
    }
    MsiString::CopyToBuf((MsiString *)&v293, v401, v402 - 1);
  }
LABEL_166:
  IMsiData::Release(v293);
LABEL_167:
  if ( PackageCodeAndLanguageFromStorage )
    goto LABEL_270;
  if ( !v267 )
  {
    PackageCodeAndLanguageFromStorage = GetPackageCodeAndLanguageFromStorage(v273, String2, &v286);
    if ( PackageCodeAndLanguageFromStorage )
      goto LABEL_270;
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v291) )
    {
      memset_0(ValueBuf, 0, PackageCodeAndLanguageFromStorage + 78);
      pcchValueBuf[0] = 39;
      v98 = (const WCHAR *)MsiString::operator unsigned short const *(&v291);
      if ( MsiGetProductInfoW(v98, L"PackageCode", ValueBuf, pcchValueBuf) )
      {
        if ( g_dmDiagnosticMode )
        {
          v99 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v291);
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
        CComPointer<IMsiDatabase>::operator=(&v273, 0);
        goto LABEL_149;
      }
      if ( v35 || !lstrcmpiW(ValueBuf, String2) )
      {
        v100 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v291);
        if ( (int)StringCchCopyW((unsigned __int16 *)szProduct, v415, v100) < 0 )
          goto LABEL_136;
      }
    }
    else
    {
      PackageCodeAndLanguageFromStorage = MsiGetProductCodeFromPackageCodeW(String2, (unsigned __int16 *)szProduct);
    }
    v276 = 3;
    goto LABEL_270;
  }
  if ( *(_WORD *)MsiString::operator unsigned short const *(&v296) == 64 )
  {
    v69 = 3;
  }
  else
  {
    v69 = 0;
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v296) != 124 )
      goto LABEL_174;
    v69 = 4;
  }
  MsiString::Remove(&v296, 0, 1);
LABEL_174:
  if ( (unsigned int)MsiString::operator int(&v328) == 1
    || (unsigned int)MsiString::operator int(&v327) == 1
    || (unsigned int)GetIntegerPolicyValue(3)
    || (unsigned int)GetIntegerPolicyValue(4) )
  {
    v69 = 1;
  }
  v294 = (IMsiData *)&MsiString::s_NullString;
  v295 = 0;
  v297 = 0;
  v299 = 0;
  if ( !g_scServerContext || g_scServerContext == 3 )
  {
    MsiString::operator=(&v294, lpBuffer);
  }
  else
  {
    IMsiData::Release((IMsiData *)&MsiString::s_NullString);
    v294 = (IMsiData *)&MsiString::s_NullString;
    v70 = MsiString::MsiString((MsiString *)&v379, L"CURRENTDIRECTORY");
    LOBYTE(v258) = 0;
    ProcessCommandLine(v353, 0, 0, 0, 0, 0, 0, *(_QWORD *)v70, &v294, 1, 0, 0, v258);
    IMsiData::Release(v379);
  }
  v289 = (IMsiData *)&MsiString::s_NullString;
  v298 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release((IMsiData *)&MsiString::s_NullString);
  v298 = (IMsiData *)&MsiString::s_NullString;
  IMsiData::Release(v289);
  v289 = (IMsiData *)&MsiString::s_NullString;
  v71 = SplitPath(lpString1, &v289, &v298);
  if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v297, v71) )
  {
    CComPointer<IMsiDatabase>::operator=(&v273, 0);
LABEL_185:
    IMsiData::Release(v298);
    IMsiData::Release(v289);
    IMsiData::Release(v294);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v299);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v297);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v295);
    IMsiData::Release(v268);
    CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
    PackageCodeAndLanguageFromStorage = 1624;
    goto LABEL_289;
  }
  v72 = 0;
  v277 = 1;
  v267 = 0;
  v73 = v264 ? 47 : 92;
  v316 = v73;
  while ( (unsigned int)MsiString::TextSize((MsiString *)&v296) )
  {
    v279 = (IMsiData *)MsiString::ExtractAndRemove(&v296, 2, 59);
    if ( *(_WORD *)MsiString::operator unsigned short const *(&v279) == 58 )
    {
      MsiString::Remove(&v279, 0, 1);
      v74 = v273;
      v75 = *(__int64 (__fastcall **)(struct IMsiStorage *, __int64, _QWORD, __int64))(*(_QWORD *)v273 + 64LL);
      v76 = CComPointer<IEnumMsiRecord>::operator=(&v295);
      v77 = MsiString::operator unsigned short const *(&v279);
      v78 = v75(v74, v77, 0, v76);
      if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v297, v78) )
        goto LABEL_214;
      v72 = v267;
      goto LABEL_207;
    }
    if ( v69 <= 1 )
    {
      v79 = MsiString::operator unsigned short const *(&v279);
      v80 = PathType(v79);
      v300 = (IMsiData *)&MsiString::s_NullString;
      if ( v80 != 3 )
      {
        v231 = v69 == 0;
        v69 = 2;
        if ( !v231 )
          v69 = 3;
LABEL_199:
        MsiString::operator=(&v300, &v279);
        if ( v69 == 2 )
        {
          MsiString::operator=(&v279, &v294);
          v81 = MsiString::MsiString(&v380, 92);
          MsiString::operator+=(&v279, v81);
          v82 = v380;
        }
        else
        {
          MsiString::operator=(&v279, &v289);
          v83 = MsiString::MsiString(&v381, v73);
          MsiString::operator+=(&v279, v83);
          v82 = v381;
        }
        IMsiData::Release(v82);
        MsiString::operator+=(&v279, &v300);
        goto LABEL_203;
      }
      v69 = 4;
    }
    else
    {
      v300 = (IMsiData *)&MsiString::s_NullString;
      if ( v69 == 2 || v69 == 3 )
        goto LABEL_199;
    }
LABEL_203:
    v84 = CComPointer<IEnumMsiRecord>::operator=(&v295);
    v85 = MsiString::operator unsigned short const *(&v279);
    LOBYTE(NewState) = 0;
    if ( (unsigned int)OpenAndValidateMsiStorage(v85, 2, v322, v84, NewState, 0, 0) )
    {
      if ( v69 != 2 )
        goto LABEL_216;
      MsiString::operator=(&v279, &v289);
      v86 = MsiString::MsiString(&v382, v73);
      MsiString::operator+=(&v279, v86);
      IMsiData::Release(v382);
      MsiString::operator+=(&v279, &v300);
      v87 = CComPointer<IEnumMsiRecord>::operator=(&v295);
      v88 = MsiString::operator unsigned short const *(&v279);
      LOBYTE(NewState) = 0;
      if ( (unsigned int)OpenAndValidateMsiStorage(v88, 2, v322, v87, NewState, 0, 0) )
      {
LABEL_216:
        CComPointer<IMsiDatabase>::operator=(&v273, 0);
        IMsiData::Release(v300);
        goto LABEL_215;
      }
    }
    IMsiData::Release(v300);
LABEL_207:
    v89 = v295;
    v90 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v295 + 136LL);
    v91 = CComPointer<IEnumMsiRecord>::operator=(&v299);
    v92 = v90(v89, 0, v91);
    if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v297, v92) )
    {
LABEL_214:
      CComPointer<IMsiDatabase>::operator=(&v273, 0);
LABEL_215:
      IMsiData::Release(v279);
      goto LABEL_185;
    }
    v307 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v299 + 40LL))(v299, 9);
    v342 = (IMsiData *)MsiString::Extract(&v307, 0, 38);
    MsiString::Remove(&v307, 3, 59);
    v309 = (IMsiData *)MsiString::Extract(&v307, 0, 38);
    v93 = MsiString::operator unsigned short const *(&v309);
    if ( !(unsigned int)MsiString::Compare(&v342, 1, v93) )
    {
      if ( v72 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_224;
        v97 = L"Only one product code changing transform is allowed in multiple instance support.  More than one product c"
               "ode changing transform has been supplied.";
        goto LABEL_223;
      }
      if ( !v277 )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_224;
        v97 = L"The instance transform must be the first transform in the transforms list of the TRANSFORMS property";
LABEL_223:
        DebugString(10, 0, 0, v97, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_224;
      }
      v72 = 1;
      v267 = 1;
      if ( (v36 & 0x10) == 0 )
      {
        v94 = (const WCHAR *)MsiString::operator unsigned short const *(&v309);
        if ( ((MsiQueryProductStateW(v94) - 1) & 0xFFFFFFFB) == 0 )
        {
          if ( g_dmDiagnosticMode )
          {
            v95 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v296);
            v96 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v309);
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
          CComPointer<IMsiDatabase>::operator=(&v273, 0);
          IMsiData::Release(v309);
          IMsiData::Release(v342);
          IMsiData::Release(v307);
          IMsiData::Release(v279);
LABEL_225:
          IMsiData::Release(v298);
          IMsiData::Release(v289);
          IMsiData::Release(v294);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v299);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v297);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v295);
          goto LABEL_149;
        }
      }
    }
    v277 = 0;
    IMsiData::Release(v309);
    IMsiData::Release(v342);
    IMsiData::Release(v307);
    IMsiData::Release(v279);
    v73 = v316;
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
    CComPointer<IMsiDatabase>::operator=(&v273, 0);
    goto LABEL_225;
  }
  PackageCodeAndLanguageFromStorage = 1605;
  v276 = 3;
  IMsiData::Release(v298);
  IMsiData::Release(v289);
  IMsiData::Release(v294);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v299);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v297);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v295);
  v17 = v322;
LABEL_270:
  Record = CreateRecord(3u);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64))(*(_QWORD *)Record + 104LL))(Record, 1);
  (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)Record + 104LL))(Record, 2, v286);
  v102 = Record;
  v103 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)Record + 104LL);
  Codepage = MsiGetCodepage(v286);
  v103(v102, 3, Codepage);
  MsiUIMessageContext::Invoke(&g_MessageContext, 184549376, Record);
  v105 = v285;
  if ( v285 )
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
      CComPointer<IMsiDatabase>::operator=(&v338, MsiHandle);
      if ( !v338 )
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
    if ( v292 )
    {
      v36 |= 0x80u;
      v276 = 2;
      a6 = v36;
    }
    if ( v105 || a1 == 3 )
    {
      PackageCodeAndLanguageFromStorage = 1605;
LABEL_363:
      if ( a1 )
      {
        v276 = 2;
        goto LABEL_365;
      }
LABEL_286:
      CComPointer<IMsiDatabase>::operator=(&v273, 0);
LABEL_287:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
      IMsiData::Release(v268);
      goto LABEL_288;
    }
    if ( a1 == 2 )
    {
      *v401 = 58;
      if ( (int)StringCchCopyW(v401 + 1, v402 - 1, a2) < 0 )
      {
LABEL_299:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
        goto LABEL_136;
      }
LABEL_359:
      if ( PackageCodeAndLanguageFromStorage != 1605 )
      {
        if ( PackageCodeAndLanguageFromStorage )
          goto LABEL_286;
LABEL_365:
        v281 = (IMsiData *)&MsiString::s_NullString;
        PackageCodeAndLanguageFromStorage = 14;
        v340 = 0;
        v310 = 0;
        if ( !qword_180309780
          || CMsiTransaction::m_pMsiTransaction
          && CMsiTransaction::FMultiPackageTransaction((CMsiTransaction *)CMsiTransaction::m_pMsiTransaction) )
        {
          goto LABEL_447;
        }
        v283 = 0;
        v275 = 0;
        v280 = (IMsiData *)&MsiString::s_NullString;
        v278 = (IMsiData *)&MsiString::s_NullString;
        v282 = 0;
        v284 = 0;
        v125 = (struct IMsiRecord **)CComPointer<IEnumMsiRecord>::operator=(&v284);
        v126 = CMsiIpiReader::GetInProgressInstallInfo((CMsiIpiReader *)v318, v17, v125);
        if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v282, v126)
          || v284 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v284 + 24LL))(v284)
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
          CComPointer<IMsiDatabase>::operator=(&v275, v136);
          v133 = v275;
          if ( !v275 )
            goto LABEL_446;
        }
        else
        {
          v127 = *(__int64 (__fastcall **)(struct IMsiServices *, unsigned __int16 *, _QWORD, __int64, int))(*(_QWORD *)v17 + 224LL);
          v128 = CComPointer<IEnumMsiRecord>::operator=(&v283);
          v129 = v127(v17, v401, 0, v128, NewState);
          if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v282, v129) )
            goto LABEL_446;
          v130 = *(__int64 (__fastcall **)(struct IMsiServices *, __int64, __int64, __int64))(*(_QWORD *)v17 + 112LL);
          v131 = CComPointer<IEnumMsiRecord>::operator=(&v275);
          v132 = v130(v17, v283, 1, v131);
          if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v282, v132) )
            goto LABEL_446;
          v133 = v275;
        }
        v287 = 0;
        v271 = 0;
        v137 = 0;
        v138 = *(_QWORD *)v133;
        v285 = 0;
        v139 = *(__int64 (__fastcall **)(struct IMsiDatabase *, _QWORD, _QWORD, __int64))(v138 + 80);
        v140 = CComPointer<IEnumMsiRecord>::operator=(&v287);
        v141 = MsiString::MsiString((MsiString *)&v385, L"Property");
        v142 = v139(v133, *(_QWORD *)v141, 0, v140);
        if ( *(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v282, v142)
          || (v143 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v287 + 128LL))(v287, 0),
              !*(_QWORD *)CComPointer<IMsiDatabase>::operator=(&v271, v143)) )
        {
          v150 = 0;
        }
        else
        {
          v144 = v287;
          v145 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v287 + 96LL);
          v146 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const wchar_t *))(*(_QWORD *)v275 + 120LL))(
                   v275,
                   L"Property");
          v137 = v145(v144, v146);
          if ( v137 )
          {
            v147 = v287;
            v148 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v287 + 96LL);
            v149 = (*(__int64 (__fastcall **)(struct IMsiDatabase *, const wchar_t *))(*(_QWORD *)v275 + 120LL))(
                     v275,
                     L"Value");
            v150 = v148(v147, v149);
            if ( v150 )
            {
              v151 = 0;
LABEL_390:
              IMsiData::Release(v385);
              if ( v151 )
                goto LABEL_391;
              v152 = v271;
              v153 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 48LL);
              v154 = iColumnBit(v137);
              v153(v152, v154);
              v155 = v271;
              v156 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v271 + 96LL);
              v157 = MsiString::MsiString((MsiString *)&v386, L"ProductLanguage");
              v156(v155, v137, *(_QWORD *)v157);
              IMsiData::Release(v386);
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v271 + 40LL))(v271) )
                goto LABEL_391;
              v358 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 64LL))(v271, v150);
              v316 = MsiString::operator int(&v358);
              IMsiData::Release(v358);
              if ( !a1 )
              {
                v408 = 1;
                lpValueBuf = (LPWSTR)&v409;
                if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpValueBuf, 260, 0) )
                {
                  v330 = v408;
                  while ( 1 )
                  {
                    ProductInfoW = MsiGetProductInfoW(a2, L"ProductName", lpValueBuf, &v330);
                    if ( ProductInfoW != 234 )
                      break;
                    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpValueBuf, v330 + 1, 0) )
                      goto LABEL_395;
                  }
                  if ( !ProductInfoW )
                  {
                    MsiString::operator=(&v280, a2);
                    MsiString::operator=(&v278, lpValueBuf);
                    p_lpValueBuf = &lpValueBuf;
LABEL_416:
                    CAPITempBuffer<unsigned short,1>::Destroy(p_lpValueBuf);
LABEL_417:
                    v352 = 0;
                    v178 = *(_QWORD *)MsiString::MsiString((MsiString *)&v389, L"MSIFASTINSTALL");
                    v179 = MsiString::operator unsigned short const *(&v270);
                    LOBYTE(v258) = 0;
                    LODWORD(v178) = ProcessCommandLine(v179, 0, 0, 0, 0, 0, 0, v178, &v352, 1, 0, 0, v258);
                    IMsiData::Release(v389);
                    if ( (_DWORD)v178 )
                    {
                      if ( v352 )
                      {
                        v180 = (*(__int64 (__fastcall **)(IMsiData *))(*(_QWORD *)v352 + 32LL))(v352);
                        IMsiData::Release(v352);
                        if ( v180 == 0x80000000 )
                          LOBYTE(v180) = 0;
                      }
                      else
                      {
                        v346 = (IMsiData *)&MsiString::s_NullString;
                        LOBYTE(v180) = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v271 + 32LL))(v271);
                        v181 = v271;
                        v182 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 48LL);
                        v183 = iColumnBit(v137);
                        v182(v181, v183);
                        v184 = v271;
                        v185 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v271 + 96LL);
                        v186 = MsiString::MsiString((MsiString *)&v390, L"MSIFASTINSTALL");
                        v185(v184, v137, *(_QWORD *)v186);
                        IMsiData::Release(v390);
                        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v271 + 40LL))(v271) )
                        {
                          v187 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 64LL))(
                                               v271,
                                               v150);
                          IMsiData::Release(v346);
                          v346 = v187;
                          LOBYTE(v180) = MsiString::operator int(&v346);
                        }
                        IMsiData::Release(v346);
                      }
                      v304 = (IMsiData *)&MsiString::s_NullString;
                      v315 = (IMsiData *)&MsiString::s_NullString;
                      v317 = (IMsiData *)&MsiString::s_NullString;
                      v306 = (IMsiData *)&MsiString::s_NullString;
                      IMsiData::Release((IMsiData *)&MsiString::s_NullString);
                      v304 = (IMsiData *)&MsiString::s_NullString;
                      v188 = 2;
                      v189 = MsiString::MsiString((MsiString *)&v394, L"CLIENTUILEVEL");
                      LOBYTE(v260) = 0;
                      v190 = v353;
                      if ( !(unsigned int)ProcessCommandLine(
                                            v353,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            *(_QWORD *)v189,
                                            &v304,
                                            1,
                                            0,
                                            0,
                                            v260) )
                        goto LABEL_429;
                      IMsiData::Release(v315);
                      v315 = (IMsiData *)&MsiString::s_NullString;
                      v188 = 6;
                      v191 = MsiString::MsiString((MsiString *)&v393, L"REMOVE");
                      LOBYTE(v261) = 0;
                      if ( !(unsigned int)ProcessCommandLine(
                                            v190,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            *(_QWORD *)v191,
                                            &v315,
                                            1,
                                            0,
                                            0,
                                            v261) )
                        goto LABEL_429;
                      IMsiData::Release(v317);
                      v188 = 14;
                      v317 = (IMsiData *)&MsiString::s_NullString;
                      v192 = MsiString::MsiString((MsiString *)&v392, L"FASTOEM");
                      LOBYTE(v262) = 0;
                      if ( !(unsigned int)ProcessCommandLine(
                                            v190,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            0,
                                            *(_QWORD *)v192,
                                            &v317,
                                            1,
                                            0,
                                            0,
                                            v262) )
                        goto LABEL_429;
                      IMsiData::Release(v306);
                      v306 = (IMsiData *)&MsiString::s_NullString;
                      v188 = 30;
                      v193 = MsiString::MsiString((MsiString *)&v391, L"MSICLIENTUSESEMBEDDEDUI");
                      LOBYTE(v263) = 0;
                      if ( (unsigned int)ProcessCommandLine(
                                           v190,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           0,
                                           *(_QWORD *)v193,
                                           &v306,
                                           1,
                                           0,
                                           0,
                                           v263) )
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
                            IMsiData::Release(v392);
                          if ( (v188 & 4) != 0 )
                            IMsiData::Release(v393);
                          IMsiData::Release(v394);
                          if ( v194 )
                          {
                            IMsiData::Release(v306);
                            IMsiData::Release(v317);
                            IMsiData::Release(v315);
                            IMsiData::Release(v304);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v271);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v287);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v284);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v282);
                            IMsiData::Release(v278);
                            IMsiData::Release(v280);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v275);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v283);
LABEL_447:
                            v202 = a6;
                            v199 = v269;
                            goto LABEL_448;
                          }
                          v195 = 0;
                          if ( (unsigned int)MsiString::TextSize((MsiString *)&v304)
                            && (unsigned int)MsiString::operator int(&v304) != 0x80000000 )
                          {
                            v196 = MsiString::operator int(&v304);
                            if ( (unsigned int)MsiString::TextSize((MsiString *)&v306) )
                              v196 = 2;
                            v197 = (unsigned int)MsiString::Compare(&v315, 1, L"ALL") != 0;
                            if ( (v180 & 1) != 0 || (unsigned int)MsiString::TextSize((MsiString *)&v317) )
                              v195 = 1;
                            v332 = 0;
                            v333 = 0;
                            v198 = MsiString::operator unsigned short const *(&v280);
                            v199 = v269;
                            GetProductState(v198, v269, &v332, &v333);
                            v200 = MsiString::operator unsigned short const *(&v278);
                            LOWORD(v249) = v316;
                            LOBYTE(v246) = v195;
                            LOBYTE(v201) = v332 != 0;
                            LOBYTE(v245) = v197;
                            v202 = a6;
                            LOBYTE(v203) = v333 != 0;
                            LOBYTE(v244) = v351 != 0;
                            v204 = a6 >> 4;
                            LOBYTE(NewState) = v339 != 0;
                            LOBYTE(v204) = (a6 & 0x10) != 0;
                            CMsiSystemChange::SetSystemChangeInfo(
                              qword_180309780,
                              v204,
                              v203,
                              v201,
                              NewState,
                              v244,
                              v245,
                              v246,
                              v200,
                              v196,
                              v249);
                            CMsiSystemChange::BeginSystemChange(qword_180309780, v275);
                            IMsiData::Release(v306);
                            IMsiData::Release(v317);
                            IMsiData::Release(v315);
                            IMsiData::Release(v304);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v271);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v287);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v284);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v282);
                            IMsiData::Release(v278);
                            IMsiData::Release(v280);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v275);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v283);
LABEL_448:
                            if ( v276 == 2 )
                            {
                              if ( a1 - 2 <= 1 )
                                goto LABEL_501;
                              if ( !v264 )
                              {
                                v321 = (IMsiData *)&MsiString::s_NullString;
                                IMsiData::Release((IMsiData *)&MsiString::s_NullString);
                                v321 = (IMsiData *)&MsiString::s_NullString;
                                IMsiData::Release(v281);
                                v247 = v199;
                                v205 = v322;
                                v281 = (IMsiData *)&MsiString::s_NullString;
                                LastError = CopyTempDatabase(v401, &v281, &v340, &v321, v322, 0, &v310, v247);
                                if ( LastError )
                                  goto LABEL_481;
                                v207 = &v335;
                                if ( v265 )
                                  v207 = 0;
                                v208 = v401;
                                if ( a1 == 1 )
                                  v208 = (void *)lpString1;
                                v209 = CComPointer<IEnumMsiRecord>::operator=(&v273);
                                v210 = MsiString::operator unsigned short const *(&v281);
                                LOBYTE(NewStatea) = v265 ^ 1;
                                LastError = OpenAndValidateMsiStorage(v210, 0, v205, v209, NewStatea, v208, v207);
                                if ( LastError )
                                {
LABEL_481:
                                  CComPointer<IMsiDatabase>::operator=(&v273, 0);
                                  if ( v310 )
                                  {
                                    if ( g_scServerContext == 2 )
                                    {
                                      CElevate::CElevate((CElevate *)v395, 1);
                                      v225 = (const WCHAR *)MsiString::operator unsigned short const *(&v281);
                                      DeleteFileW(v225);
                                      CElevate::~CElevate((CElevate *)v395);
                                    }
                                    else
                                    {
                                      v226 = (const WCHAR *)MsiString::operator unsigned short const *(&v281);
                                      DeleteFileW(v226);
                                    }
                                  }
                                  IMsiData::Release(v321);
                                  goto LABEL_486;
                                }
                                if ( v340 )
                                {
                                  MsiString::operator+=(&v270, L" CURRENTMEDIAVOLUMELABEL=\"");
                                  if ( (unsigned int)MsiString::TextSize((MsiString *)&v321) )
                                    MsiString::operator+=(&v270, &v321);
                                  else
                                    MsiString::operator+=(&v270, L"?");
                                  MsiString::operator+=(&v270, L"\"");
                                }
                                IMsiData::Release(v321);
LABEL_463:
                                if ( !v264 )
                                  goto LABEL_469;
                                v211 = v402;
                                if ( v266 )
                                {
                                  if ( v402 < v406 )
                                  {
                                    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                                             &v401,
                                                             (unsigned int)v406,
                                                             0) )
                                      goto LABEL_497;
                                    v211 = v402;
                                  }
                                  if ( (int)StringCchCopyW(v401, v211, lpString1 + 7) >= 0 )
                                    goto LABEL_469;
LABEL_497:
                                  IMsiData::Release(v281);
                                  goto LABEL_287;
                                }
                                v311 = v402;
                                if ( !(unsigned int)MsiCanonicalizeUrl(lpString1, v401, &v311, 0x20000000u) )
                                {
                                  LastError = GetLastError();
                                  if ( LastError == 122 )
                                  {
                                    if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v401, v311, 0) )
                                      goto LABEL_497;
                                    if ( !(unsigned int)MsiCanonicalizeUrl(lpString1, v401, &v311, 0x20000000u) )
                                      goto LABEL_521;
                                  }
                                  else if ( LastError )
                                  {
LABEL_521:
                                    CComPointer<IMsiDatabase>::operator=(&v273, 0);
                                    goto LABEL_486;
                                  }
                                }
LABEL_469:
                                LODWORD(qword_180309704) = qword_180309704 + 1;
                                v212 = v335;
                                v213 = v273;
                                v313 = 0;
                                v214 = 0;
                                v215 = v338;
                                v216 = MsiString::operator unsigned short const *(&v270);
                                v292 = CreateInitializedEngine(
                                         v401,
                                         szProduct,
                                         v216,
                                         1,
                                         2,
                                         v213,
                                         v215,
                                         v336,
                                         v202,
                                         &v323,
                                         v212,
                                         v359);
                                v217 = v292;
                                CComPointer<IMsiDatabase>::operator=(&v273, 0);
                                v324 = (IMsiData *)&MsiString::s_NullString;
                                if ( !v217 )
                                {
                                  v218 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v323 + 80LL))(v323);
                                  CComPointer<IMsiDatabase>::operator=(&v313, v218);
                                  v219 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v323 + 112LL))(
                                           v323,
                                           v360,
                                           0);
                                  v361 = (IMsiData *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v323 + 800LL))(v323);
                                  MsiString::operator=(&v324, &v361);
                                  IMsiData::Release(v361);
                                  g_uiReturnCode = MapInstallActionReturnToError(v219);
                                  v220 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v323 + 48LL))(
                                           v323,
                                           v219);
                                  if ( !g_scServerContext )
                                    v214 = v220 == -3;
                                  v217 = MapInstallActionReturnToError(v220);
                                  v292 = v217;
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v323 + 16LL))(v323);
                                }
                                LODWORD(qword_180309704) = qword_180309704 + 1;
                                if ( v310 )
                                {
                                  if ( g_scServerContext == 2 )
                                  {
                                    CElevate::CElevate((CElevate *)v396, 1);
                                    v221 = (const WCHAR *)MsiString::operator unsigned short const *(&v281);
                                    if ( !DeleteFileW(v221) )
                                    {
                                      v222 = 10;
                                      if ( GetLastError() == 32 )
                                      {
                                        do
                                        {
                                          if ( v222 <= 0 )
                                            break;
                                          v223 = (const WCHAR *)MsiString::operator unsigned short const *(&v281);
                                          if ( DeleteFileW(v223) )
                                            break;
                                          --v222;
                                          v224 = GetLastError();
                                          Sleep(0xC8u);
                                        }
                                        while ( v224 == 32 );
                                      }
                                    }
                                    CElevate::~CElevate((CElevate *)v396);
                                  }
                                  else
                                  {
                                    v232 = (const WCHAR *)MsiString::operator unsigned short const *(&v281);
                                    DeleteFileW(v232);
                                  }
                                }
                                if ( v313 && (v202 & 0x103) == 0 )
                                {
                                  v354 = 0;
                                  if ( g_scServerContext == 2 )
                                  {
                                    v233 = (*(unsigned __int8 (**)(void))(*(_QWORD *)v313 + 56LL))() == 0;
                                  }
                                  else
                                  {
                                    v233 = 1;
                                    GrabExecuteMutex((struct CMutex *)&v354);
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
                                      CMutex::Release((CMutex *)&v354);
                                      IMsiData::Release(v324);
                                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v313);
                                      IMsiData::Release(v281);
                                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
                                      IMsiData::Release(v268);
                                      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
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
                                    v397 = v234;
                                    (*(void (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v313 + 80LL))(
                                      v313,
                                      v234,
                                      v235);
                                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v397);
                                  }
                                  CMutex::Release((CMutex *)&v354);
                                }
                                if ( (unsigned int)MsiString::TextSize((MsiString *)&v324) )
                                {
                                  do
                                  {
                                    v314 = (IMsiData *)MsiString::ExtractAndRemove(&v324, 2, 59);
                                    if ( (unsigned int)MsiString::TextSize((MsiString *)&v314) )
                                    {
                                      if ( g_scServerContext == 2 )
                                      {
                                        CElevate::CElevate((CElevate *)v398, 1);
                                        if ( g_dmDiagnosticMode )
                                        {
                                          v236 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v314);
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
                                        v237 = (const WCHAR *)MsiString::operator unsigned short const *(&v314);
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
                                        CElevate::~CElevate((CElevate *)v398);
                                      }
                                      else
                                      {
                                        if ( g_dmDiagnosticMode )
                                        {
                                          v239 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v314);
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
                                        v240 = (const WCHAR *)MsiString::operator unsigned short const *(&v314);
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
                                    IMsiData::Release(v314);
                                  }
                                  while ( (unsigned int)MsiString::TextSize((MsiString *)&v324) );
                                  v217 = v292;
                                }
                                if ( v214 && v313 )
                                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v313 + 40LL))(v313);
                                CComPointer<IMsiDatabase>::operator=(&v313, 0);
                                IMsiData::Release(v324);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v313);
                                IMsiData::Release(v281);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
                                IMsiData::Release(v268);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
                                IMsiData::Release(v270);
                                IMsiData::Release(v325);
                                IMsiData::Release(v326);
                                IMsiData::Release(v288);
                                IMsiData::Release(v327);
                                IMsiData::Release(v328);
                                IMsiData::Release(v329);
                                IMsiData::Release(v291);
                                IMsiData::Release(v296);
                                IMsiData::Release(v302);
                                IMsiData::Release(v312);
                                IMsiData::Release(v308);
                                IMsiData::Release(v337);
                                IMsiData::Release(v303);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v338);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v273);
                                CDeleteUrlLocalFileOnClose::~CDeleteUrlLocalFileOnClose((CDeleteUrlLocalFileOnClose *)&v347);
                                CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>((__int64)&szProduct);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)v413);
                                CAPITempBuffer<unsigned short,1>::Destroy(&v401);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpString1);
                                CImpersonate::~CImpersonate((CImpersonate *)v355);
                                CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v272);
                                return v217;
                              }
                            }
                            if ( a1 == 1 && v276 == 1 )
                            {
                              v227 = CComPointer<IEnumMsiRecord>::operator=(&v273);
                              LOBYTE(NewState) = 0;
                              LastError = OpenAndValidateMsiStorage(v401, 0, v322, v227, NewState, 0, 0);
                              if ( LastError )
                              {
LABEL_486:
                                IMsiData::Release(v281);
                                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
                                IMsiData::Release(v268);
                                CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
                                PackageCodeAndLanguageFromStorage = LastError;
                                goto LABEL_289;
                              }
                              if ( v265
                                || (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *, _QWORD))ADVAPI32::SaferCreateLevel)(
                                                   1,
                                                   0x40000,
                                                   1,
                                                   &v335,
                                                   0) )
                              {
                                v229 = v402;
                                if ( v402 < v406 )
                                {
                                  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(
                                                           &v401,
                                                           (unsigned int)v406,
                                                           0) )
                                    goto LABEL_497;
                                  v229 = v402;
                                }
                                if ( (int)StringCchCopyW(v401, v229, lpString1) < 0 )
                                  goto LABEL_497;
                                goto LABEL_463;
                              }
                              goto LABEL_492;
                            }
LABEL_501:
                            if ( v264 && v276 == 2 && !v265 )
                            {
                              LOBYTE(v244) = 0;
                              v230 = VerifyMsiObjectAgainstSAFER(v322, v273, v401, lpString1, 0, v244, &v335);
                              if ( !v230 )
                                goto LABEL_463;
                              CComPointer<IMsiDatabase>::operator=(&v273, 0);
                              v231 = v230 == 1;
                            }
                            else
                            {
                              if ( a1 )
                              {
                                if ( a1 - 2 <= 1 )
                                  goto LABEL_463;
                              }
                              else if ( v276 == 1 )
                              {
                                if ( v265
                                  || (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *, _QWORD))ADVAPI32::SaferCreateLevel)(
                                                     1,
                                                     0x40000,
                                                     1,
                                                     &v335,
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
                              v231 = v265 == 0;
                            }
                            if ( !v231 )
                              goto LABEL_463;
LABEL_494:
                            IMsiData::Release(v281);
                            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
                            IMsiData::Release(v268);
                            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
                            PackageCodeAndLanguageFromStorage = 1625;
                            goto LABEL_289;
                          }
                          IMsiData::Release(v306);
                          IMsiData::Release(v317);
                          IMsiData::Release(v315);
                          IMsiData::Release(v304);
                          goto LABEL_391;
                        }
                      }
                      v188 &= ~0x10u;
                      IMsiData::Release(v391);
                      goto LABEL_431;
                    }
LABEL_391:
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v271);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v287);
LABEL_446:
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v284);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v282);
                    IMsiData::Release(v278);
                    IMsiData::Release(v280);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v275);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v283);
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
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v271 + 32LL))(v271);
              v161 = v271;
              v162 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 48LL);
              v163 = iColumnBit(v137);
              v162(v161, v163);
              v164 = v271;
              v165 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v271 + 96LL);
              v166 = MsiString::MsiString((MsiString *)&v387, L"ProductCode");
              v165(v164, v137, *(_QWORD *)v166);
              IMsiData::Release(v387);
              if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v271 + 40LL))(v271) )
                goto LABEL_391;
              v167 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 64LL))(v271, v150);
              IMsiData::Release(v280);
              v280 = v167;
              v410 = (LPWSTR)&v412;
              v411 = 1;
              if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v410, 260, 0) )
              {
LABEL_406:
                v158 = &v410;
                goto LABEL_396;
              }
              v331 = v411;
              while ( 1 )
              {
                v168 = v410;
                v169 = (const WCHAR *)MsiString::operator unsigned short const *(&v280);
                v170 = MsiGetProductInfoW(v169, L"ProductName", v168, &v331);
                if ( v170 != 234 )
                  break;
                if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v410, v331 + 1, 0) )
                  goto LABEL_406;
              }
              if ( v170 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v271 + 32LL))(v271);
                v171 = v271;
                v172 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 48LL);
                v173 = iColumnBit(v137);
                v172(v171, v173);
                v174 = v271;
                v175 = *(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v271 + 96LL);
                v176 = MsiString::MsiString((MsiString *)&v388, L"ProductName");
                v175(v174, v137, *(_QWORD *)v176);
                IMsiData::Release(v388);
                if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v271 + 40LL))(v271) )
                  goto LABEL_406;
                v177 = (IMsiData *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v271 + 64LL))(v271, v150);
                IMsiData::Release(v278);
                v278 = v177;
              }
              else
              {
                MsiString::operator=(&v278, v410);
              }
              p_lpValueBuf = &v410;
              goto LABEL_416;
            }
          }
          else
          {
            v150 = v285;
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
      v403 = 1;
      PackageCodeAndLanguageFromStorage = GetPackageFullPath(szProduct);
    }
    else if ( a1 )
    {
      PackageCodeAndLanguageFromStorage = 1605;
    }
    else
    {
      v305 = (IMsiData *)&MsiString::s_NullString;
      v320 = (IMsiData *)&MsiString::s_NullString;
      v334 = 0;
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
      CResolveSource::CResolveSource((CResolveSource *)v434, v17, 1);
      IMsiData::Release(v320);
      v320 = (IMsiData *)&MsiString::s_NullString;
      IMsiData::Release(v305);
      LOBYTE(v248) = 0;
      v305 = (IMsiData *)&MsiString::s_NullString;
      v112 = CResolveSource::ResolveSource(v434, szProduct, 0, 1, &v305, &v320, 1, 0, v248, 0, 0);
      CComPointer<IMsiDatabase>::operator=(&v334, v112);
      if ( v334 )
      {
        PackageCodeAndLanguageFromStorage = 1605;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v334 + 56LL))(v334, 1) != 2720 )
          PackageCodeAndLanguageFromStorage = 1612;
      }
      else
      {
        CRegHandle::CRegHandle((CRegHandle *)hKey);
        LOBYTE(NewState) = 0;
        if ( (unsigned int)OpenSourceListKeyW(szProduct, 0, (__int64)hKey) )
        {
          PackageCodeAndLanguageFromStorage = 1605;
        }
        else
        {
          v427 = 100;
          lpString = (LPCWSTR)&v429;
          v428 = 100;
          pcchValueBuf[1] = 0;
          MsiRegQueryValueExW((HKEY)hKey[0].DebugInfo, L"PackageName", (__int64)&lpString, 0);
          v113 = lstrlenW(lpString);
          v114 = (unsigned int)MsiString::TextSize((MsiString *)&v305) + v113 + 1;
          if ( v402 < (int)v114 && !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v401, v114, 0)
            || (v116 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v305),
                (int)StringCchCopyW(v401, v402, v116) < 0)
            || (int)StringCchCatW(v401, v402, lpString) < 0 )
          {
            CAPITempBuffer<unsigned short,100>::Destroy(&lpString);
            CRegHandle::~CRegHandle(hKey);
            CResolveSource::~CResolveSource((CResolveSource *)v434);
            CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v334);
            IMsiData::Release(v320);
            v115 = v305;
LABEL_313:
            IMsiData::Release(v115);
            goto LABEL_299;
          }
          CAPITempBuffer<unsigned short,100>::Destroy(&lpString);
        }
        CRegHandle::~CRegHandle(hKey);
      }
      CResolveSource::~CResolveSource((CResolveSource *)v434);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v334);
      IMsiData::Release(v320);
      IMsiData::Release(v305);
    }
    if ( PackageCodeAndLanguageFromStorage )
      goto LABEL_359;
    if ( v264 )
      goto LABEL_365;
    v290 = (IMsiData *)&MsiString::s_NullString;
    if ( !IsURL(v401, &v266) )
      goto LABEL_352;
    if ( v266 )
    {
      v350 = v402;
      CTempBuffer<unsigned short,1>::SetSize(&lpString1);
      if ( !lpString1 || (int)StringCchCopyW((unsigned __int16 *)lpString1, v406, v401) < 0 )
      {
LABEL_332:
        v115 = v290;
        goto LABEL_313;
      }
      if ( MsiConvertFileUrlToFilePath(lpString1, v401, &v350, 0) )
      {
        v118 = CComPointer<IEnumMsiRecord>::operator=(&v273);
        LOBYTE(NewState) = 0;
        v117 = OpenAndValidateMsiStorage(v401, 0, v17, v118, NewState, 0, 0);
      }
      else
      {
        v117 = GetLastError();
      }
      PackageCodeAndLanguageFromStorage = v117;
LABEL_352:
      if ( !v264 || PackageCodeAndLanguageFromStorage )
        goto LABEL_358;
      v122 = CComPointer<IEnumMsiRecord>::operator=(&v273);
      v123 = MsiString::operator unsigned short const *(&v290);
      LOBYTE(NewState) = 0;
      PackageCodeAndLanguageFromStorage = OpenAndValidateMsiStorage(v123, 0, v17, v122, NewState, 0, 0);
      CTempBuffer<unsigned short,1>::SetSize(&lpString1);
      if ( lpString1 )
      {
        if ( (int)StringCchCopyW((unsigned __int16 *)lpString1, v406, v401) >= 0 )
        {
          v124 = MsiString::TextSize((MsiString *)&v290);
          if ( (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&v401, (unsigned int)(v124 + 1), 0) )
          {
            MsiString::CopyToBuf((MsiString *)&v290, v401, v402 - 1);
LABEL_358:
            IMsiData::Release(v290);
            goto LABEL_359;
          }
        }
      }
      goto LABEL_332;
    }
    if ( (unsigned int)MsiString::TextSize((MsiString *)&v288) && g_scServerContext == 2 && IsAdmin() )
    {
      v119 = (const WCHAR *)MsiString::operator unsigned short const *(&v288);
      if ( MsiGetFileAttributesEx(v119, 0, 0, 0, 0, 0) != -1 )
      {
        if ( g_dmDiagnosticMode )
        {
          v120 = (const unsigned __int16 *)MsiString::operator unsigned short const *(&v288);
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
        MsiString::operator=(&v290, &v288);
        v264 = 1;
        goto LABEL_352;
      }
    }
    else if ( (unsigned int)MsiString::TextSize((MsiString *)&v288) )
    {
      PackageCodeAndLanguageFromStorage = 1639;
      goto LABEL_352;
    }
    IMsiData::Release(v290);
    v290 = (IMsiData *)&MsiString::s_NullString;
    v121 = DownloadUrlFile(v401, &v290, &v264, 0);
    PackageCodeAndLanguageFromStorage = v121;
    if ( v121 == 1602 )
    {
      CComPointer<IMsiDatabase>::operator=(&v273, 0);
      IMsiData::Release(v290);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
      IMsiData::Release(v268);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
      PackageCodeAndLanguageFromStorage = 1602;
      goto LABEL_289;
    }
    if ( !v264 )
      goto LABEL_358;
    if ( !v121 )
    {
      MsiString::MsiString((MsiString *)&v384, v401);
      CDeleteUrlLocalFileOnClose::SetFileName((CDeleteUrlLocalFileOnClose *)&v347, v290);
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
        MsiString::operator+=(&v270, L" MSIPACKAGEDOWNLOADLOCALCOPY=\"");
        MsiString::operator+=(&v270, &v290);
        MsiString::operator+=(&v270, L"\" ");
      }
      IMsiData::Release(v384);
    }
    goto LABEL_352;
  }
  v383 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v336 + 72LL))(v336);
  v345 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v383 + 168LL))(v383, 1);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v383);
  v106 = v345;
  if ( !v345 )
    goto LABEL_273;
  v107 = *(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD, __int64))(*(_QWORD *)v345 + 64LL);
  v108 = CComPointer<IEnumMsiRecord>::operator=(&v273);
  v357 = v107(v106, a2, 0, v108);
  if ( !v357 )
  {
    v276 = 0;
    PackageCodeAndLanguageFromStorage = 0;
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v357);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v345);
LABEL_277:
    v105 = v285;
    goto LABEL_293;
  }
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v357);
LABEL_273:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v345);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&Record);
  IMsiData::Release(v268);
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpBuffer);
  PackageCodeAndLanguageFromStorage = 1631;
LABEL_289:
  IMsiData::Release(v270);
  IMsiData::Release(v325);
  IMsiData::Release(v326);
  IMsiData::Release(v288);
  IMsiData::Release(v327);
  IMsiData::Release(v328);
  IMsiData::Release(v329);
  IMsiData::Release(v291);
  IMsiData::Release(v296);
  IMsiData::Release(v302);
  IMsiData::Release(v312);
  IMsiData::Release(v308);
  IMsiData::Release(v337);
  IMsiData::Release(v303);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v338);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>((__int64 *)&v273);
  CDeleteUrlLocalFileOnClose::~CDeleteUrlLocalFileOnClose((CDeleteUrlLocalFileOnClose *)&v347);
  CTempBuffer<unsigned short,39>::~CTempBuffer<unsigned short,39>((__int64)&szProduct);
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)v413);
  CAPITempBuffer<unsigned short,1>::Destroy(&v401);
  CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>((__int64)&lpString1);
  CImpersonate::~CImpersonate((CImpersonate *)v355);
  CCoUninitialize::~CCoUninitialize((CCoUninitialize *)v272);
  return PackageCodeAndLanguageFromStorage;
}

```

## disassembly

```asm
0x18013ae34  push    rbp
0x18013ae36  push    rbx
0x18013ae37  push    rsi
0x18013ae38  push    rdi
0x18013ae39  push    r12
0x18013ae3b  push    r13
0x18013ae3d  push    r14
0x18013ae3f  push    r15
0x18013ae41  lea     rbp, [rsp-9E8h]
0x18013ae49  sub     rsp, 0AE8h
0x18013ae50  mov     rax, cs:__security_cookie
0x18013ae57  xor     rax, rsp
0x18013ae5a  mov     [rbp+0A20h+var_50], rax
0x18013ae61  mov     rax, [rbp+0A20h+arg_20]
0x18013ae68  xor     r12d, r12d
0x18013ae6b  mov     [rbp+0A20h+var_8B0], rax
0x18013ae72  mov     rdi, r9
0x18013ae75  mov     rax, [rbp+0A20h+arg_30]
0x18013ae7c  mov     r14, r8
0x18013ae7f  mov     [rbp+0A20h+var_808], rax
0x18013ae86  mov     r15, rdx
0x18013ae89  mov     [rbp+0A20h+var_838], r9
0x18013ae90  mov     r13d, ecx
0x18013ae93  mov     [rbp+0A20h+var_800], r8
0x18013ae9a  mov     [rbp+0A20h+var_898], r12d
0x18013aea1  call    ?PopulateDomainBasedAllowLockdownMediaDefault@@YAXXZ; PopulateDomainBasedAllowLockdownMediaDefault(void)
0x18013aea6  mov     rax, cs:?CoInitialize@OLE32@@3P6AJPEAX@ZEA; long (*OLE32::CoInitialize)(void *)
0x18013aead  xor     ecx, ecx
0x18013aeaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013aeb4  mov     edx, 80000000h
0x18013aeb9  mov     ecx, eax
0x18013aebb  add     eax, edx
0x18013aebd  test    edx, eax
0x18013aebf  jnz     short loc_18013AED3
0x18013aec1  cmp     ecx, 80010106h
0x18013aec7  jz      short loc_18013AED3
0x18013aec9  mov     eax, 643h
0x18013aece  jmp     loc_18013F56E
0x18013aed3  shr     ecx, 1Fh
0x18013aed6  xor     cl, 1
0x18013aed9  mov     [rbp+0A20h+var_A88], cl
0x18013aedc  call    ?ResetCachedPolicyValuesW@@YAXXZ; ResetCachedPolicyValuesW(void)
0x18013aee1  mov     dl, 1; bool
0x18013aee3  lea     rcx, [rbp+0A20h+var_828]; this
0x18013aeea  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x18013aeef  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18013aef6  lea     rbx, aNull; "(NULL)"
0x18013aefd  jz      short loc_18013AF5E
0x18013aeff  mov     rcx, rdi; unsigned __int16 *
0x18013af02  call    ?LoggedCommandLine@@YAPEBGPEBG@Z; LoggedCommandLine(ushort const *)
0x18013af07  mov     [rsp+0B20h+var_AC8], r12; void *
0x18013af0c  lea     rdx, Default
0x18013af13  mov     [rsp+0B20h+var_AD0], r12d; unsigned int
0x18013af18  lea     r9, aRunengineProdu; "******* RunEngine:\r\n           ******"...
0x18013af1f  mov     [rsp+0B20h+var_AD8], rbx; unsigned __int16 *
0x18013af24  test    r14, r14
0x18013af27  mov     [rsp+0B20h+var_AE0], rbx; unsigned __int16 *
0x18013af2c  mov     r8, r14
0x18013af2f  cmovz   r8, rdx
0x18013af33  mov     [rsp+0B20h+var_AE8], rbx; unsigned __int16 *
0x18013af38  mov     [rsp+0B20h+var_AF0], rax; unsigned __int16 *
0x18013af3d  test    r15, r15
0x18013af40  mov     [rsp+0B20h+var_AF8], r8; unsigned __int16 *
0x18013af45  mov     rcx, r15
0x18013af48  cmovz   rcx, rdx
0x18013af4c  xor     edx, edx; unsigned __int16
0x18013af4e  mov     [rsp+0B20h+NewState], rcx; unsigned __int16 *
0x18013af53  xor     r8d, r8d; int
0x18013af56  lea     ecx, [rdx+9]; int
0x18013af59  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18013af5e  mov     ebx, 105h
0x18013af63  test    r15, r15
0x18013af66  jz      short loc_18013AF75
0x18013af68  mov     rcx, r15; lpString
0x18013af6b  call    cs:__imp_lstrlenW
0x18013af71  inc     eax
0x18013af73  jmp     short loc_18013AF77
0x18013af75  mov     eax, ebx
0x18013af77  mov     edx, eax
0x18013af79  lea     rcx, [rbp+0A20h+lpString1]
0x18013af80  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x18013af85  lea     rax, [rbp+0A20h+var_6A0]
0x18013af8c  mov     [rbp+0A20h+var_6A8], 1
0x18013af96  mov     edx, ebx
0x18013af98  mov     [rbp+0A20h+var_6B0], rax
0x18013af9f  lea     rcx, [rbp+0A20h+var_650]
0x18013afa6  call    ??0?$CTempBuffer@G$00@@QEAA@H@Z; CTempBuffer<ushort,1>::CTempBuffer<ushort,1>(int)
0x18013afab  xor     edx, edx; Val
0x18013afad  lea     rcx, [rbp+0A20h+var_620]; void *
0x18013afb4  lea     r8d, [rdx+4Eh]; Size
0x18013afb8  call    memset_0
0x18013afbd  lea     rax, [rbp+0A20h+var_620]
0x18013afc4  mov     [rbp+0A20h+var_628], 27h ; '''
0x18013afce  mov     [rbp+0A20h+szProduct], rax
0x18013afd5  cmp     [rbp+0A20h+lpString1], r12
0x18013afdc  jz      loc_18013F524
0x18013afe2  cmp     [rbp+0A20h+var_650], r12
0x18013afe9  jz      loc_18013F524
0x18013afef  xor     r8d, r8d
0x18013aff2  lea     rcx, [rbp+0A20h+var_6B0]
0x18013aff9  mov     edx, ebx
0x18013affb  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18013b000  test    al, al
0x18013b002  jz      loc_18013F524
0x18013b008  mov     rax, [rbp+0A20h+var_6B0]
0x18013b00f  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b016  mov     rdx, rdi; unsigned __int16 *
0x18013b019  lea     rcx, [rbp+0A20h+var_A98]; this
0x18013b01d  mov     [rax], r12w
0x18013b021  mov     rax, [rbp+0A20h+szProduct]
0x18013b028  mov     [rax], r12w
0x18013b02c  mov     rsi, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18013b033  mov     [rbp+0A20h+var_910], rsi
0x18013b03a  mov     [rsp+0B20h+var_AB0], r12b
0x18013b03f  mov     [rsp+0B20h+var_AAE], r12b
0x18013b044  mov     [rbp+0A20h+var_860], r12
0x18013b04b  mov     [rbp+0A20h+var_908], r12
0x18013b052  mov     [rbp+0A20h+var_A80], r12
0x18013b056  mov     [rbp+0A20h+var_8A0], r12
0x18013b05d  mov     [rbp+0A20h+var_A68], 7
0x18013b064  mov     [rbp+0A20h+var_A24], r12w
0x18013b069  mov     [rbp+0A20h+var_9A0], rbx
0x18013b070  mov     [rbp+0A20h+var_8A8], rbx
0x18013b077  mov     [rbp+0A20h+var_978], rbx
0x18013b07e  mov     [rbp+0A20h+var_960], rbx
0x18013b085  mov     [rbp+0A20h+var_9A8], rbx
0x18013b089  mov     [rbp+0A20h+var_9D8], rbx
0x18013b08d  mov     [rbp+0A20h+var_A00], rbx
0x18013b091  mov     [rbp+0A20h+var_8D8], rbx
0x18013b098  mov     [rbp+0A20h+var_8E0], rbx
0x18013b09f  mov     [rbp+0A20h+var_8E8], rbx
0x18013b0a6  mov     [rbp+0A20h+var_A18], rbx
0x18013b0aa  mov     [rbp+0A20h+var_8F0], rbx
0x18013b0b1  mov     [rbp+0A20h+var_8F8], rbx
0x18013b0b8  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x18013b0bd  mov     rcx, [rbp+0A20h+var_960]; this
0x18013b0c4  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b0c9  lea     rdx, aReinstallmode; "REINSTALLMODE"
0x18013b0d0  mov     [rbp+0A20h+var_960], rbx
0x18013b0d7  lea     rcx, [rbp+0A20h+var_7F0]; this
0x18013b0de  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18013b0e3  mov     rcx, [rbp+0A20h+var_8A8]; this
0x18013b0ea  mov     rbx, [rax]
0x18013b0ed  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b0f2  mov     rcx, [rbp+0A20h+var_9A0]; this
0x18013b0f9  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b100  mov     [rbp+0A20h+var_8A8], rax
0x18013b107  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b10c  mov     rcx, [rbp+0A20h+var_978]; this
0x18013b113  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b11a  mov     [rbp+0A20h+var_9A0], rax
0x18013b121  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b126  mov     rcx, [rbp+0A20h+var_9D8]; this
0x18013b12a  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b131  mov     [rbp+0A20h+var_978], rax
0x18013b138  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b13d  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b144  lea     rcx, [rbp+0A20h+var_A98]
0x18013b148  mov     [rbp+0A20h+var_9D8], rax
0x18013b14c  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18013b151  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x18013b156  lea     rcx, [rbp+0A20h+var_960]
0x18013b15d  mov     [rsp+0B20h+var_AC8], r12
0x18013b162  lea     r9, [rbp+0A20h+var_978]
0x18013b169  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18013b16e  lea     r8, [rbp+0A20h+var_9D8]
0x18013b172  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x18013b17a  xor     edx, edx
0x18013b17c  mov     [rsp+0B20h+var_AE0], rcx
0x18013b181  lea     rcx, [rbp+0A20h+var_8A8]
0x18013b188  mov     [rsp+0B20h+var_AE8], rbx
0x18013b18d  mov     [rsp+0B20h+var_AF0], rcx
0x18013b192  lea     rcx, [rbp+0A20h+var_9A0]
0x18013b199  mov     [rsp+0B20h+var_AF8], rcx
0x18013b19e  mov     rcx, rax
0x18013b1a1  mov     [rsp+0B20h+NewState], r12
0x18013b1a6  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18013b1ab  mov     rcx, [rbp+0A20h+var_7F0]; this
0x18013b1b2  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b1b7  mov     rcx, [rbp+0A20h+var_9A8]; this
0x18013b1bb  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b1c0  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b1c7  mov     [rbp+0A20h+var_9A8], rax
0x18013b1cb  lea     rdx, aRunonceentry; "RUNONCEENTRY"
0x18013b1d2  lea     rcx, [rbp+0A20h+var_7E8]; this
0x18013b1d9  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18013b1de  lea     rcx, [rbp+0A20h+var_A98]
0x18013b1e2  mov     rbx, [rax]
0x18013b1e5  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18013b1ea  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x18013b1ef  lea     rcx, [rbp+0A20h+var_9A8]
0x18013b1f3  mov     [rsp+0B20h+var_AC8], r12
0x18013b1f8  xor     r9d, r9d
0x18013b1fb  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18013b200  xor     r8d, r8d
0x18013b203  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x18013b20b  xor     edx, edx
0x18013b20d  mov     [rsp+0B20h+var_AE0], rcx
0x18013b212  mov     rcx, rax
0x18013b215  mov     [rsp+0B20h+var_AE8], rbx
0x18013b21a  mov     [rsp+0B20h+var_AF0], r12
0x18013b21f  mov     [rsp+0B20h+var_AF8], r12
0x18013b224  mov     [rsp+0B20h+NewState], r12
0x18013b229  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18013b22e  mov     rcx, [rbp+0A20h+var_7E8]; this
0x18013b235  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b23a  mov     rcx, [rbp+0A20h+var_8D8]; this
0x18013b241  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b246  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b24d  lea     rdx, aMsinewinstance_0; "MSINEWINSTANCE"
0x18013b254  mov     [rbp+0A20h+var_8D8], rax
0x18013b25b  lea     rcx, [rbp+0A20h+var_7E0]; this
0x18013b262  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18013b267  lea     rcx, [rbp+0A20h+var_A98]
0x18013b26b  mov     rbx, [rax]
0x18013b26e  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18013b273  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x18013b278  lea     rcx, [rbp+0A20h+var_8D8]
0x18013b27f  mov     [rsp+0B20h+var_AC8], r12
0x18013b284  xor     r9d, r9d
0x18013b287  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18013b28c  xor     r8d, r8d
0x18013b28f  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x18013b297  xor     edx, edx
0x18013b299  mov     [rsp+0B20h+var_AE0], rcx
0x18013b29e  mov     rcx, rax
0x18013b2a1  mov     [rsp+0B20h+var_AE8], rbx
0x18013b2a6  mov     [rsp+0B20h+var_AF0], r12
0x18013b2ab  mov     [rsp+0B20h+var_AF8], r12
0x18013b2b0  mov     [rsp+0B20h+NewState], r12
0x18013b2b5  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18013b2ba  mov     rcx, [rbp+0A20h+var_7E0]; this
0x18013b2c1  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b2c6  mov     rcx, [rbp+0A20h+var_A00]; this
0x18013b2ca  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b2cf  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b2d6  lea     rdx, aMsiinstancegui; "MSIINSTANCEGUID"
0x18013b2dd  mov     [rbp+0A20h+var_A00], rax
0x18013b2e1  lea     rcx, [rbp+0A20h+var_7D8]; this
0x18013b2e8  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18013b2ed  lea     rcx, [rbp+0A20h+var_A98]
0x18013b2f1  mov     rbx, [rax]
0x18013b2f4  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18013b2f9  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x18013b2fe  lea     rcx, [rbp+0A20h+var_A00]
0x18013b302  mov     [rsp+0B20h+var_AC8], r12
0x18013b307  xor     r9d, r9d
0x18013b30a  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18013b30f  xor     r8d, r8d
0x18013b312  mov     dword ptr [rsp+0B20h+var_AD8], 1
0x18013b31a  xor     edx, edx
0x18013b31c  mov     [rsp+0B20h+var_AE0], rcx
0x18013b321  mov     rcx, rax
0x18013b324  mov     [rsp+0B20h+var_AE8], rbx
0x18013b329  mov     [rsp+0B20h+var_AF0], r12
0x18013b32e  mov     [rsp+0B20h+var_AF8], r12
0x18013b333  mov     [rsp+0B20h+NewState], r12
0x18013b338  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18013b33d  mov     rcx, [rbp+0A20h+var_7D8]; this
0x18013b344  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b349  mov     rcx, [rbp+0A20h+var_8E0]; this
0x18013b350  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b355  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b35c  mov     [rbp+0A20h+var_8E0], rax
0x18013b363  lea     rdx, aTransformssecu_1; "TRANSFORMSSECURE"
0x18013b36a  lea     rcx, [rbp+0A20h+var_7D0]; this
0x18013b371  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18013b376  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x18013b37b  lea     rcx, [rbp+0A20h+var_8E0]
0x18013b382  mov     [rsp+0B20h+var_AC8], r12
0x18013b387  mov     ebx, 1
0x18013b38c  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18013b391  xor     r9d, r9d
0x18013b394  mov     rax, [rax]
0x18013b397  xor     r8d, r8d
0x18013b39a  mov     dword ptr [rsp+0B20h+var_AD8], ebx
0x18013b39e  xor     edx, edx
0x18013b3a0  mov     [rsp+0B20h+var_AE0], rcx
0x18013b3a5  mov     rcx, rdi
0x18013b3a8  mov     [rsp+0B20h+var_AE8], rax
0x18013b3ad  mov     [rsp+0B20h+var_AF0], r12
0x18013b3b2  mov     [rsp+0B20h+var_AF8], r12
0x18013b3b7  mov     [rsp+0B20h+NewState], r12
0x18013b3bc  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18013b3c1  mov     rcx, [rbp+0A20h+var_7D0]; this
0x18013b3c8  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b3cd  mov     rcx, [rbp+0A20h+var_8E8]; this
0x18013b3d4  call    ?Release@IMsiData@@QEBAKXZ; IMsiData::Release(void)
0x18013b3d9  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18013b3e0  lea     rdx, aTransformsatso_0; "TRANSFORMSATSOURCE"
0x18013b3e7  mov     [rbp+0A20h+var_8E8], rax
0x18013b3ee  lea     rcx, [rbp+0A20h+var_7C8]; this
0x18013b3f5  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18013b3fa  mov     byte ptr [rsp+0B20h+var_AC0], r12b
0x18013b3ff  lea     rcx, [rbp+0A20h+var_8E8]
0x18013b406  mov     [rsp+0B20h+var_AC8], r12
0x18013b40b  xor     r9d, r9d
0x18013b40e  mov     qword ptr [rsp+0B20h+var_AD0], r12
0x18013b413  xor     r8d, r8d
0x18013b416  mov     rax, [rax]
  ... truncated ...
```
