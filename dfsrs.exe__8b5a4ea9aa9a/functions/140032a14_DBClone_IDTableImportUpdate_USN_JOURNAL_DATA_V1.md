# DBClone::IDTableImportUpdate(USN_JOURNAL_DATA_V1)

- ea: `0x140032a14`
- end: `0x140034e20`
- name: `?IDTableImportUpdate@DBClone@@AEAAPEAVFrsStatus@@UUSN_JOURNAL_DATA_V1@@@Z`
- size: `9228`
- prototype: `struct FrsStatus *__fastcall(DBClone *__hidden this, struct USN_JOURNAL_DATA_V1 *__struct_ptr)`
- caller_count: `1`
- callee_count: `80`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14002f630`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x1400046cc`
- `0x14000c910`
- `0x14000e34c`
- `0x14000ee94`
- `0x140011408`
- `0x14001e704`
- `0x14001e710`
- `0x1400248f4`
- `0x140029750`
- `0x1400297f8`
- `0x140029974`
- `0x140029b10`
- `0x140029bc4`
- `0x140029c84`
- `0x140029d40`
- `0x14002a15c`
- `0x14002a204`
- `0x14002a36c`
- `0x14002a4c8`
- `0x14002a58c`
- `0x14002a6d0`
- `0x14002a778`
- `0x14002aae8`
- `0x14002beb4`
- `0x14002bf70`
- `0x14002c110`
- `0x14002c160`
- `0x14002c1c0`
- `0x14002c270`
- `0x14002c2f4`
- `0x14002c404`
- `0x14002c474`
- `0x14002d600`
- `0x140031984`
- `0x140031b44`
- `0x140032070`
- `0x140032a14`
- `0x140035304`
- `0x1400353fc`
- `0x1400370bc`
- `0x140037844`
- `0x14003792c`
- `0x1400379a8`
- `0x1400379ec`
- `0x140037e50`
- `0x140038618`
- `0x14006d494`
- `0x14006d568`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14003480a`
- `KERNEL32!WaitForSingleObject` at `0x14003480a`
- `KERNEL32!ResetEvent` at `0x14003476f`
- `KERNEL32!ResetEvent` at `0x14003476f`
- `KERNEL32!GetCurrentThreadId` at `0x1400335e0`
- `KERNEL32!GetCurrentThreadId` at `0x140033895`
- `KERNEL32!GetCurrentThreadId` at `0x1400339a1`
- `KERNEL32!GetCurrentThreadId` at `0x140033b0a`
- `KERNEL32!GetCurrentThreadId` at `0x140034b6b`
- `KERNEL32!GetCurrentThreadId` at `0x140034d3a`
- `KERNEL32!GetCurrentThreadId` at `0x1400335e0`
- `KERNEL32!GetCurrentThreadId` at `0x140033895`
- `KERNEL32!GetCurrentThreadId` at `0x1400339a1`
- `KERNEL32!GetCurrentThreadId` at `0x140033b0a`
- `KERNEL32!GetCurrentThreadId` at `0x140034b6b`
- `KERNEL32!GetCurrentThreadId` at `0x140034d3a`

## string_xrefs

- `0x140032b3a`: `DBClone::IDTableImportUpdate`
- `0x140032bfd`: `DBClone::IDTableImportUpdate`
- `0x140032c4e`: `DBClone::IDTableImportUpdate`
- `0x140032f24`: `DBClone::IDTableImportUpdate`
- `0x140032f91`: `DBClone::IDTableImportUpdate`
- `0x140033297`: `DBClone::IDTableImportUpdate`
- `0x140033589`: `DBClone::IDTableImportUpdate`
- `0x14003383e`: `DBClone::IDTableImportUpdate`
- `0x14003394d`: `DBClone::IDTableImportUpdate`
- `0x140033aa5`: `DBClone::IDTableImportUpdate`
- `0x140033bd2`: `DBClone::IDTableImportUpdate`
- `0x140033cd1`: `DBClone::IDTableImportUpdate`
- `0x140033dd1`: `DBClone::IDTableImportUpdate`
- `0x140033f19`: `DBClone::IDTableImportUpdate`
- `0x140034047`: `DBClone::IDTableImportUpdate`
- `0x14003412c`: `DBClone::IDTableImportUpdate`
- `0x14003426d`: `DBClone::IDTableImportUpdate`
- `0x1400344a0`: `DBClone::IDTableImportUpdate`
- `0x14003454b`: `DBClone::IDTableImportUpdate`
- `0x1400346f2`: `DBClone::IDTableImportUpdate`
- `0x14003482f`: `DBClone::IDTableImportUpdate`
- `0x140034996`: `DBClone::IDTableImportUpdate`
- `0x140034b01`: `DBClone::IDTableImportUpdate`
- `0x140032b82`: `Copying the IDTable`
- `0x140032cb1`: `Creating the ImportDirWalkerTask.`
- `0x140032f7c`: `Master version vector. csId:%? vvMaster:%?`
- `0x140032e7c`: `DBClone::IDTableImportUpdate`
- `0x1400335fd`: `DBClone::IDTableImportUpdate`
- `0x1400338b2`: `DBClone::IDTableImportUpdate`
- `0x1400339be`: `DBClone::IDTableImportUpdate`
- `0x140033b27`: `DBClone::IDTableImportUpdate`
- `0x140034b88`: `DBClone::IDTableImportUpdate`
- `0x140034c71`: `DBClone::IDTableImportUpdate`
- `0x1400330fc`: `DBClone record. csId:%? name:%? gvsn:%?`
- `0x1400335c3`: `Failed to get the master root record for csId:%? error:%?`
- `0x140033878`: `Failed to find/query the content set root on the file system. csId:%? error:%?`
- `0x140033984`: `Failed to get the content set record for csId:%? error:%?`
- `0x140033adc`: `Update content set record:%?`
- `0x1400343bb`: `(Updated file) mismatch. csId:%? name:%? gvsn:%?`
- `0x140034602`: `Duplicate DB entry. csId:%? idRec:%? error:%?`
- `0x140034663`: `Failed to Insert DB record. csId:%? idRec:%? error:%?`
- `0x1400349df`: `Removing deleted/modified changes for csId:%? from vvMaster:%?`
- `0x140034b39`: `Clone version vector. csId:%? vvClone:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
struct FrsStatus *__fastcall DBClone::IDTableImportUpdate(DBClone *this, struct USN_JOURNAL_DATA_V1 *a2)
{
  DBClone *v2; // r13
  __int64 v3; // r15
  struct FrsStatus *SessionAndBeginTransaction; // r12
  ImportDirWalkerTask *v5; // rdi
  unsigned int v6; // r14d
  char *v7; // rsi
  VsnManager *v8; // rax
  __int64 v9; // rdx
  VsnManager *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  Dword *v13; // r14
  Dword *v14; // rsi
  __int64 DisplayPath; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rbx
  char *v18; // r13
  struct Pdb *v19; // rsi
  DBClone *v20; // r14
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rsi
  ID_RECORD *v24; // r14
  unsigned int v25; // ebx
  Dword *v26; // rsi
  Dword *v27; // rdi
  __int64 v28; // rbx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  ID_RECORD *v31; // rcx
  _OWORD *v32; // rax
  __int64 v33; // rdx
  IDTable *v34; // rdi
  struct FrsStatus *v35; // rbx
  struct FrsStatus *v36; // rax
  ID_RECORD *v37; // rcx
  _OWORD *v38; // rax
  __int64 v39; // rdx
  struct FrsStatus *v40; // rbx
  struct FrsStatus *v41; // rax
  struct FrsStatus *v42; // rbx
  struct FrsStatus *v43; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v45; // rcx
  __int64 v46; // rbx
  FHandle *v47; // rdi
  DWORD v48; // eax
  __int64 v49; // rcx
  char v50; // al
  struct Pdb *v51; // rdi
  struct FrsStatus *v52; // r9
  DWORD v53; // eax
  __int64 v54; // rcx
  void **v55; // rax
  void *v56; // rcx
  DWORD v57; // eax
  __int64 v58; // rcx
  char *v59; // rbx
  char *v60; // rbx
  char *v61; // rbx
  __int64 v62; // rsi
  DBClone *v63; // rdi
  int v64; // edx
  void *v65; // rcx
  char *v66; // rbx
  __int64 v67; // rdx
  int v68; // ecx
  int v69; // ecx
  int v70; // edx
  unsigned __int64 v71; // rcx
  int v72; // r8d
  unsigned __int64 v73; // rdx
  int v74; // r8d
  int v75; // r9d
  __int64 v76; // rax
  VsnManager *v77; // rbx
  _QWORD *v78; // rcx
  struct FrsStatus *v79; // rax
  __int64 v80; // r8
  unsigned int v81; // eax
  char v82; // al
  DBClone *v83; // rbx
  int v84; // eax
  int v85; // edx
  LPCRITICAL_SECTION v86; // rax
  LPCRITICAL_SECTION v87; // rax
  const volatile int *v88; // rax
  DWORD v89; // eax
  __int64 v90; // rcx
  Dword *v91; // rsi
  Dword *v92; // rdi
  __int64 v93; // rbx
  _QWORD *v94; // rax
  void **v95; // rax
  DWORD v96; // eax
  __int64 v97; // rcx
  struct FrsStatus *v99; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v100; // [rsp+78h] [rbp-88h]
  DBClone *v101; // [rsp+80h] [rbp-80h]
  unsigned int v102; // [rsp+88h] [rbp-78h]
  unsigned int v103; // [rsp+8Ch] [rbp-74h] BYREF
  struct Db *v104; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v105; // [rsp+98h] [rbp-68h]
  __int64 v106; // [rsp+A0h] [rbp-60h] BYREF
  ID_RECORD *v107; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v108; // [rsp+B0h] [rbp-50h] BYREF
  struct Pdb *v109; // [rsp+B8h] [rbp-48h] BYREF
  int v110; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v111[16]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v112[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v113[40]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v114; // [rsp+110h] [rbp+10h] BYREF
  struct Db *v115; // [rsp+118h] [rbp+18h] BYREF
  struct Db *v116; // [rsp+120h] [rbp+20h] BYREF
  void **v117; // [rsp+128h] [rbp+28h] BYREF
  VsnManager *v118; // [rsp+130h] [rbp+30h] BYREF
  int v119; // [rsp+138h] [rbp+38h] BYREF
  FHandle *v120; // [rsp+140h] [rbp+40h]
  struct Pdb *v121; // [rsp+148h] [rbp+48h] BYREF
  ImportDirWalkerTask *v122; // [rsp+150h] [rbp+50h] BYREF
  char *v123; // [rsp+158h] [rbp+58h] BYREF
  ID_RECORD *v124; // [rsp+160h] [rbp+60h] BYREF
  VsnManager *ftLastWriteTime; // [rsp+168h] [rbp+68h] BYREF
  struct Pdb *v126; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v127[16]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v128; // [rsp+188h] [rbp+88h]
  struct USN_JOURNAL_DATA_V1 *v129; // [rsp+190h] [rbp+90h]
  __int64 v130; // [rsp+198h] [rbp+98h] BYREF
  char v131[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v132; // [rsp+1A8h] [rbp+A8h]
  char v133[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v134; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v135; // [rsp+1C0h] [rbp+C0h] BYREF
  const wchar_t *v136; // [rsp+1C8h] [rbp+C8h] BYREF
  int v137; // [rsp+1D0h] [rbp+D0h]
  int v138; // [rsp+1D4h] [rbp+D4h]
  const wchar_t *v139; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v140; // [rsp+1E0h] [rbp+E0h] BYREF
  int v141; // [rsp+1E8h] [rbp+E8h]
  int v142; // [rsp+1ECh] [rbp+ECh]
  const wchar_t *v143; // [rsp+1F0h] [rbp+F0h]
  const wchar_t *v144; // [rsp+1F8h] [rbp+F8h] BYREF
  int v145; // [rsp+200h] [rbp+100h]
  int v146; // [rsp+204h] [rbp+104h]
  const wchar_t *v147; // [rsp+208h] [rbp+108h]
  const wchar_t *v148; // [rsp+210h] [rbp+110h] BYREF
  int v149; // [rsp+218h] [rbp+118h]
  int v150; // [rsp+21Ch] [rbp+11Ch]
  const wchar_t *v151; // [rsp+220h] [rbp+120h]
  const wchar_t *v152; // [rsp+228h] [rbp+128h] BYREF
  int v153; // [rsp+230h] [rbp+130h]
  int v154; // [rsp+234h] [rbp+134h]
  const wchar_t *v155; // [rsp+238h] [rbp+138h]
  const wchar_t *v156; // [rsp+240h] [rbp+140h] BYREF
  int v157; // [rsp+248h] [rbp+148h]
  int v158; // [rsp+24Ch] [rbp+14Ch]
  const wchar_t *v159; // [rsp+250h] [rbp+150h]
  const wchar_t *v160; // [rsp+258h] [rbp+158h] BYREF
  int v161; // [rsp+260h] [rbp+160h]
  int v162; // [rsp+264h] [rbp+164h]
  const wchar_t *v163; // [rsp+268h] [rbp+168h]
  const wchar_t *v164; // [rsp+270h] [rbp+170h] BYREF
  int v165; // [rsp+278h] [rbp+178h]
  int v166; // [rsp+27Ch] [rbp+17Ch]
  const wchar_t *v167; // [rsp+280h] [rbp+180h]
  const wchar_t *v168; // [rsp+288h] [rbp+188h] BYREF
  int v169; // [rsp+290h] [rbp+190h]
  int v170; // [rsp+294h] [rbp+194h]
  const wchar_t *v171; // [rsp+298h] [rbp+198h]
  const wchar_t *v172; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v173; // [rsp+2A8h] [rbp+1A8h]
  int v174; // [rsp+2ACh] [rbp+1ACh]
  const wchar_t *v175; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v176; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v177; // [rsp+2C0h] [rbp+1C0h]
  int v178; // [rsp+2C4h] [rbp+1C4h]
  const wchar_t *v179; // [rsp+2C8h] [rbp+1C8h]
  const wchar_t *v180; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v181; // [rsp+2D8h] [rbp+1D8h]
  int v182; // [rsp+2DCh] [rbp+1DCh]
  const wchar_t *v183; // [rsp+2E0h] [rbp+1E0h]
  const wchar_t *v184; // [rsp+2E8h] [rbp+1E8h] BYREF
  int v185; // [rsp+2F0h] [rbp+1F0h]
  int v186; // [rsp+2F4h] [rbp+1F4h]
  const wchar_t *v187; // [rsp+2F8h] [rbp+1F8h]
  const wchar_t *v188; // [rsp+300h] [rbp+200h] BYREF
  int v189; // [rsp+308h] [rbp+208h]
  int v190; // [rsp+30Ch] [rbp+20Ch]
  const wchar_t *v191; // [rsp+310h] [rbp+210h]
  const wchar_t *v192; // [rsp+318h] [rbp+218h] BYREF
  int v193; // [rsp+320h] [rbp+220h]
  int v194; // [rsp+324h] [rbp+224h]
  const wchar_t *v195; // [rsp+328h] [rbp+228h]
  const wchar_t *v196; // [rsp+330h] [rbp+230h] BYREF
  int v197; // [rsp+338h] [rbp+238h]
  int v198; // [rsp+33Ch] [rbp+23Ch]
  const wchar_t *v199; // [rsp+340h] [rbp+240h]
  const wchar_t *v200; // [rsp+348h] [rbp+248h] BYREF
  int v201; // [rsp+350h] [rbp+250h]
  int v202; // [rsp+354h] [rbp+254h]
  const wchar_t *v203; // [rsp+358h] [rbp+258h]
  const wchar_t *v204; // [rsp+360h] [rbp+260h] BYREF
  int v205; // [rsp+368h] [rbp+268h]
  int v206; // [rsp+36Ch] [rbp+26Ch]
  const wchar_t *v207; // [rsp+370h] [rbp+270h]
  const wchar_t *v208; // [rsp+378h] [rbp+278h] BYREF
  int v209; // [rsp+380h] [rbp+280h]
  int v210; // [rsp+384h] [rbp+284h]
  const wchar_t *v211; // [rsp+388h] [rbp+288h]
  const wchar_t *v212; // [rsp+390h] [rbp+290h] BYREF
  int v213; // [rsp+398h] [rbp+298h]
  int v214; // [rsp+39Ch] [rbp+29Ch]
  const wchar_t *v215; // [rsp+3A0h] [rbp+2A0h]
  const wchar_t *v216; // [rsp+3A8h] [rbp+2A8h] BYREF
  int v217; // [rsp+3B0h] [rbp+2B0h]
  int v218; // [rsp+3B4h] [rbp+2B4h]
  const wchar_t *v219; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v220; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v221; // [rsp+3C8h] [rbp+2C8h]
  int v222; // [rsp+3CCh] [rbp+2CCh]
  const wchar_t *v223; // [rsp+3D0h] [rbp+2D0h]
  const wchar_t *v224; // [rsp+3D8h] [rbp+2D8h] BYREF
  int v225; // [rsp+3E0h] [rbp+2E0h]
  int v226; // [rsp+3E4h] [rbp+2E4h]
  const wchar_t *v227; // [rsp+3E8h] [rbp+2E8h]
  const wchar_t *v228; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v229; // [rsp+3F8h] [rbp+2F8h]
  int v230; // [rsp+3FCh] [rbp+2FCh]
  const wchar_t *v231; // [rsp+400h] [rbp+300h]
  const wchar_t *v232; // [rsp+408h] [rbp+308h] BYREF
  int v233; // [rsp+410h] [rbp+310h]
  int v234; // [rsp+414h] [rbp+314h]
  const wchar_t *v235; // [rsp+418h] [rbp+318h]
  const wchar_t *v236; // [rsp+420h] [rbp+320h] BYREF
  int v237; // [rsp+428h] [rbp+328h]
  int v238; // [rsp+42Ch] [rbp+32Ch]
  const wchar_t *v239; // [rsp+430h] [rbp+330h]
  const wchar_t *v240; // [rsp+438h] [rbp+338h] BYREF
  int v241; // [rsp+440h] [rbp+340h]
  int v242; // [rsp+444h] [rbp+344h]
  const wchar_t *v243; // [rsp+448h] [rbp+348h]
  const wchar_t *v244; // [rsp+450h] [rbp+350h] BYREF
  int v245; // [rsp+458h] [rbp+358h]
  int v246; // [rsp+45Ch] [rbp+35Ch]
  const wchar_t *v247; // [rsp+460h] [rbp+360h]
  const wchar_t *v248; // [rsp+468h] [rbp+368h] BYREF
  int v249; // [rsp+470h] [rbp+370h]
  int v250; // [rsp+474h] [rbp+374h]
  const wchar_t *v251; // [rsp+478h] [rbp+378h]
  _BYTE v252[16]; // [rsp+480h] [rbp+380h] BYREF
  void **v253; // [rsp+490h] [rbp+390h] BYREF
  char v254[8]; // [rsp+498h] [rbp+398h] BYREF
  char v255[8]; // [rsp+4A0h] [rbp+3A0h] BYREF
  char v256[8]; // [rsp+4A8h] [rbp+3A8h] BYREF
  char v257[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v258[8]; // [rsp+4B8h] [rbp+3B8h] BYREF
  char v259[8]; // [rsp+4C0h] [rbp+3C0h] BYREF
  char v260[8]; // [rsp+4C8h] [rbp+3C8h] BYREF
  char v261[8]; // [rsp+4D0h] [rbp+3D0h] BYREF
  char v262[8]; // [rsp+4D8h] [rbp+3D8h] BYREF
  FHandle *v263; // [rsp+4E0h] [rbp+3E0h]
  struct USN_JOURNAL_DATA_V1 v264; // [rsp+4F0h] [rbp+3F0h] BYREF
  struct _GUID v265; // [rsp+530h] [rbp+430h] BYREF
  __int128 v266; // [rsp+540h] [rbp+440h] BYREF
  unsigned int v267; // [rsp+550h] [rbp+450h]
  struct _BY_HANDLE_FILE_INFORMATION v268; // [rsp+558h] [rbp+458h] BYREF
  __int128 v269; // [rsp+590h] [rbp+490h] BYREF
  __int64 v270; // [rsp+5A0h] [rbp+4A0h]
  _BYTE v271[48]; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v272[56]; // [rsp+5D8h] [rbp+4D8h] BYREF
  _BYTE v273[80]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v274; // [rsp+660h] [rbp+560h]
  char v275[48]; // [rsp+6A0h] [rbp+5A0h] BYREF
  char v276[48]; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v277[88]; // [rsp+700h] [rbp+600h] BYREF
  __int128 v278; // [rsp+758h] [rbp+658h]
  int v279; // [rsp+768h] [rbp+668h]
  __int128 v280; // [rsp+76Ch] [rbp+66Ch]
  __int64 v281; // [rsp+77Ch] [rbp+67Ch]
  unsigned __int16 v282[262]; // [rsp+79Ch] [rbp+69Ch] BYREF
  __int64 v283; // [rsp+9A8h] [rbp+8A8h] BYREF
  __int64 v284[4]; // [rsp+9B0h] [rbp+8B0h] BYREF
  void *v285[2]; // [rsp+9D0h] [rbp+8D0h] BYREF
  char v286[768]; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v287[16]; // [rsp+CE0h] [rbp+BE0h] BYREF
  __int64 v288; // [rsp+CF0h] [rbp+BF0h]
  __int64 v289; // [rsp+F90h] [rbp+E90h]
  _BYTE v290[24]; // [rsp+FB0h] [rbp+EB0h] BYREF
  char v291[132]; // [rsp+FC8h] [rbp+EC8h] BYREF
  char v292; // [rsp+104Ch] [rbp+F4Ch] BYREF
  void *v293[98]; // [rsp+1280h] [rbp+1180h] BYREF
  void *Block; // [rsp+1590h] [rbp+1490h] BYREF
  void *v295; // [rsp+18A0h] [rbp+17A0h] BYREF

  v129 = a2;
  v2 = this;
  v101 = this;
  v3 = 0;
  memset_0(v273, 0, 0x88u);
  SessionAndBeginTransaction = 0;
  v99 = 0;
  IDTable::iterator::iterator((IDTable::iterator *)v285);
  IDTable::iterator::iterator((IDTable::iterator *)v293);
  v126 = 0;
  v121 = 0;
  v109 = 0;
  v116 = 0;
  v115 = 0;
  v104 = 0;
  memset(&v268, 0, sizeof(v268));
  v108 = 0;
  FilePath::FilePath((FilePath *)&v253);
  v117 = &NtfsFileSystem::`vftable';
  v120 = 0;
  v106 = 0;
  std::deque<UID_VISIT>::deque<UID_VISIT>(v113);
  v118 = 0;
  v5 = 0;
  v122 = 0;
  std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v111);
  std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v112);
  v105 = 0;
  v6 = *((_DWORD *)v2 + 88);
  v102 = v6;
  v100 = 0;
  v103 = 0;
  ID_RECORD::ID_RECORD((ID_RECORD *)v277);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v156 = L"DBClone::IDTableImportUpdate";
    v157 = 3299;
    v158 = 4;
    v159 = L"DBCL";
    dbgobj::DbgPrint<unsigned short>(&v156, L"Copying the IDTable");
  }
  v7 = (char *)v2 + 120;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v2 + 15) + 48LL))((__int64)v2 + 120) )
  {
    *((_QWORD *)v2 + 10) = 11;
    ftLastWriteTime = (VsnManager *)operator new(0x80u);
    v8 = VsnManager::VsnManager(ftLastWriteTime, (const struct _GUID *)v2 + 4, (DBClone *)((char *)v2 + 80));
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v118, v8);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v152 = L"DBClone::IDTableImportUpdate";
      v153 = 3318;
      v154 = 4;
      v155 = L"DBCL";
      v130 = *((_QWORD *)v2 + 10);
      dbgobj::DbgPrint<unsigned short,Guid,VERSION>(&v152, v9, (char *)v2 + 64, &v130);
    }
    v6 = v102;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))((__int64)v2 + 120) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v148 = L"DBClone::IDTableImportUpdate";
      v149 = 3327;
      v150 = 4;
      v151 = L"DBCL";
      dbgobj::DbgPrint<unsigned short>(&v148, L"Creating the ImportDirWalkerTask.");
    }
    v10 = (VsnManager *)operator new(0x178u);
    ftLastWriteTime = v10;
    v11 = *(_QWORD *)(*((_QWORD *)v2 + 5) + 1344LL);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 40LL))((__int64)v2 + 120);
    v5 = (ImportDirWalkerTask *)ImportDirWalkerTask::ImportDirWalkerTask(
                                  v10,
                                  &v118,
                                  (char *)v2 + 264,
                                  *((_QWORD *)v2 + 41),
                                  *((_QWORD *)v2 + 42),
                                  v12,
                                  v11);
    v122 = v5;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))((__int64)v2 + 120)
    || (SessionAndBeginTransaction = DBClone::GetSessionAndBeginTransaction(
                                       *((struct LdbManager **)v2 + 40),
                                       1,
                                       1,
                                       &v115,
                                       &v121),
        (v99 = SessionAndBeginTransaction) == 0) )
  {
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))((__int64)v2 + 120)
      || (SessionAndBeginTransaction = DBClone::GetSessionAndBeginTransaction(
                                         *((struct LdbManager **)v2 + 40),
                                         0,
                                         1,
                                         &v116,
                                         &v126),
          (v99 = SessionAndBeginTransaction) == 0) )
    {
      if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*((_QWORD *)v2 + 15) + 48LL))((__int64)v2 + 120) )
      {
        SessionAndBeginTransaction = DBClone::GetSessionAndBeginTransaction(
                                       *((struct LdbManager **)v2 + 41),
                                       0,
                                       0,
                                       &v104,
                                       &v109);
        v99 = SessionAndBeginTransaction;
      }
    }
  }
  v13 = Dword::Dword((Dword *)v271, v6, 10);
  v14 = Dword::Dword((Dword *)v272, 0, 10);
  v132 = (char *)v2 + 200;
  DisplayPath = FilePath::GetDisplayPath((char *)v2 + 200);
  v123 = (char *)v2 + 280;
  v16 = (_QWORD *)FrsGUIDToStringW(v131, (char *)v2 + 280);
  FrsEvent::Log(1073744240, *v16 + 18LL, DisplayPath, v14, v13, 0);
  FrsStringImpl<char,unsigned short>::ReleaseBody(v131);
  v17 = **((_QWORD **)v2 + 11);
  v114 = v17;
  if ( !SessionAndBeginTransaction )
  {
    v18 = (char *)v2 + 120;
    v19 = v121;
    v20 = v101;
    while ( 1 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
        || v17 == *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                               (char *)v20 + 88,
                               v255) )
      {
        v2 = v101;
        if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)v101 + 15) + 48LL))((char *)v101 + 120) && v100 )
        {
          v91 = Dword::Dword((Dword *)v272, v100, 10);
          v92 = Dword::Dword((Dword *)v271, v105, 10);
          v93 = FilePath::GetDisplayPath((char *)v2 + 200);
          v94 = (_QWORD *)FrsGUIDToStringW(&v123, (char *)v2 + 280);
          FrsEvent::Log(1073744242, *v94 + 18LL, v93, v92, v91, 0);
          FrsStringImpl<char,unsigned short>::ReleaseBody(&v123);
        }
        break;
      }
      v265 = *(struct _GUID *)std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<UID const,UpdateReference *>>>>::operator*(&v114);
      if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
      {
        SessionAndBeginTransaction = DbUtil::VersionVector(
                                       *((struct DbManager **)v20 + 40),
                                       &v265,
                                       (struct VersionChainVector *)v111);
        v99 = SessionAndBeginTransaction;
        if ( !SessionAndBeginTransaction
          && g_DebugLog
          && LODWORD(g_DebugLog[1].LockSemaphore)
          && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
        {
          v144 = L"DBClone::IDTableImportUpdate";
          v145 = 3400;
          v146 = 4;
          v147 = L"DBCL";
          dbgobj::DbgPrint<unsigned short,_GUID,VersionChainVector>(
            &v144,
            L"Master version vector. csId:%? vvMaster:%?",
            &v265,
            v111);
        }
      }
      if ( v19 )
      {
        v269 = 0;
        v270 = 0;
        v21 = IDTable::begin(v19, &Block, &v265, &v269);
        IDTable::iterator::operator=(v285, v21);
        operator delete[](Block);
        v22 = IDTable::end(v19, &v295);
        IDTable::iterator::operator=(v293, v22);
        operator delete[](v295);
        if ( JErrToFrsStatus::Map(*((_DWORD *)v285[0] + 7)) == 9200 )
        {
          v23 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<UID const,UpdateReference *>>>>::operator*(&v114);
          v128 = v23;
          while ( 1 )
          {
            if ( SessionAndBeginTransaction
              || (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
              || !(unsigned int)FrsTableIterator::operator!=(v285, v293) )
            {
              goto LABEL_235;
            }
            ID_RECORD::ID_RECORD((ID_RECORD *)v290, (const struct ID_RECORD *)v286);
            v24 = 0;
            v107 = 0;
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
            {
              v140 = L"DBClone::IDTableImportUpdate";
              v141 = 3430;
              v142 = 5;
              v143 = L"DBCL";
              dbgobj::DbgPrint<unsigned short,_GUID,unsigned short [261],GVSN>(
                (unsigned int)&v140,
                (unsigned int)L"DBClone record. csId:%? name:%? gvsn:%?",
                (unsigned int)&v265,
                (unsigned int)&v292,
                (__int64)v291);
            }
            v25 = v105 + 1;
            v105 = v25;
            if ( !(_WORD)v25 )
            {
              v102 -= 0x10000;
              v26 = Dword::Dword((Dword *)v275, v102, 10);
              v27 = Dword::Dword((Dword *)v276, v25, 10);
              v28 = FilePath::GetDisplayPath(v132);
              v29 = (_QWORD *)FrsGUIDToStringW(v133, v123);
              FrsEvent::Log(1073744240, *v29 + 18LL, v28, v27, v26, 0);
              FrsStringImpl<char,unsigned short>::ReleaseBody(v133);
              v23 = v128;
            }
            if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
            {
              v124 = (ID_RECORD *)operator new(0x2C8u);
              v31 = ID_RECORD::ID_RECORD(v124);
              v107 = v31;
              v32 = v290;
              v33 = 5;
              do
              {
                *(_OWORD *)v31 = *v32;
                *((_OWORD *)v31 + 1) = v32[1];
                *((_OWORD *)v31 + 2) = v32[2];
                *((_OWORD *)v31 + 3) = v32[3];
                *((_OWORD *)v31 + 4) = v32[4];
                *((_OWORD *)v31 + 5) = v32[5];
                *((_OWORD *)v31 + 6) = v32[6];
                v31 = (ID_RECORD *)((char *)v31 + 128);
                *((_OWORD *)v31 - 1) = v32[7];
                v32 += 8;
                --v33;
              }
              while ( v33 );
              *(_OWORD *)v31 = *v32;
              *((_OWORD *)v31 + 1) = v32[1];
              *((_OWORD *)v31 + 2) = v32[2];
              *((_OWORD *)v31 + 3) = v32[3];
              *((_QWORD *)v31 + 8) = *((_QWORD *)v32 + 8);
              std::deque<ID_RECORD *>::push_back(v113, &v107);
              v24 = v107;
            }
            v34 = v109;
            while ( 1 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
              {
                v136 = L"DBClone::IDTableImportUpdate";
                v137 = 3468;
                v138 = 5;
                v139 = L"DBCL";
                dbgobj::DbgPrint<unsigned short,_GUID,ID_RECORD>(&v136, v30, &v265, v24);
              }
              DBClone::CommitBeginTransactionOrRollBack(v115, 1, 0, 0, &v99, 0x23F0u);
              DBClone::CommitBeginTransactionOrRollBack(v116, 1, 0, 0, &v99, 0x23F0u);
              SessionAndBeginTransaction = v99;
              if ( v99 )
                goto LABEL_234;
              if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                && *((_QWORD *)v24 + 2) == 1 )
              {
                v40 = IDTable::Retrieve(v34, v24, (struct ID_RECORD *)v277);
                v99 = v40;
                DBClone::CommitBeginTransactionOrRollBack(v104, 0, 0, 0, &v99, 0x23F9u);
                SessionAndBeginTransaction = v99;
                if ( v40 && !v99 && !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                {
                  v41 = IDTable::Retrieve(v126, v24, (struct ID_RECORD *)v277);
                  SessionAndBeginTransaction = v41;
                  v99 = v41;
                  v42 = v41;
                  if ( !v41 )
                    goto LABEL_297;
                  v43 = v41;
                  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                  {
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                    {
                      v168 = L"DBClone::IDTableImportUpdate";
                      v169 = 3531;
                      v170 = 2;
                      v171 = L"DBCL";
                      dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                        &v168,
                        L"Failed to get the master root record for csId:%? error:%?",
                        &v265,
                        v43);
                    }
                    CLEAR_ERROR(&v99);
                    CurrentThreadId = GetCurrentThreadId();
                    SessionAndBeginTransaction = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                       v45,
                                                                       9604,
                                                                       0,
                                                                       3,
                                                                       "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                                       "DBClone::IDTableImportUpdate",
                                                                       3540,
                                                                       CurrentThreadId,
                                                                       0);
                    v42 = SessionAndBeginTransaction;
                    v99 = SessionAndBeginTransaction;
                    v43 = SessionAndBeginTransaction;
                  }
                  if ( !v43 )
                  {
LABEL_297:
                    if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                    {
                      v47 = v120;
                    }
                    else
                    {
                      v46 = *(_QWORD *)(v23 + 16);
                      v124 = (ID_RECORD *)v46;
                      if ( !*(_BYTE *)(v46 + 16) )
                        _InterlockedIncrement((volatile signed __int32 *)v46);
                      if ( v120 )
                        (**(void (__fastcall ***)(FHandle *, __int64))v120)(v120, 1);
                      v263 = (FHandle *)operator new(0x10u);
                      v47 = FHandle::FHandle(v263, (struct FileSystem *)&v117);
                      v120 = v47;
                      SessionAndBeginTransaction = FHandle::OpenPath(
                                                     v47,
                                                     (const unsigned __int16 *)(v46 + 18),
                                                     0xA0u,
                                                     3u,
                                                     0x24u);
                      v42 = SessionAndBeginTransaction;
                      v99 = SessionAndBeginTransaction;
                      FrsStringImpl<char,unsigned short>::ReleaseBody(&v124);
                    }
                    if ( !v42 )
                    {
                      if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                        || (SessionAndBeginTransaction = FHandle::GetFid(v47, (struct FileId *)&v108),
                            (v99 = SessionAndBeginTransaction) == 0) )
                      {
                        if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                          || (SessionAndBeginTransaction = (struct FrsStatus *)NtfsFileSystem::GetFileInfo(
                                                                                 &v117,
                                                                                 (char *)v101 + 264,
                                                                                 &v108,
                                                                                 &v106,
                                                                                 0,
                                                                                 0,
                                                                                 0,
                                                                                 0,
                                                                                 0,
                                                                                 0),
                              (v99 = SessionAndBeginTransaction) == 0) )
                        {
                          if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                          {
                            v283 = v106;
                            v281 = 3;
                            v278 = 0;
                            v279 = 0;
                            ID_RECORD::SetFlags((ID_RECORD *)v277, 0x405u);
                            v284[0] = v108;
                            v280 = 0;
                            v99 = IDTable::Insert(v109, (const struct ID_RECORD *)v277);
                            DBClone::CommitBeginTransactionOrRollBack(v104, 0, v103 >= 0x20, &v103, &v99, 0x23F9u);
                            SessionAndBeginTransaction = v99;
                            goto LABEL_96;
                          }
                          goto LABEL_97;
                        }
                      }
                    }
                  }
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                  {
                    v164 = L"DBClone::IDTableImportUpdate";
                    v165 = 3626;
                    v166 = 2;
                    v167 = L"DBCL";
                    dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                      &v164,
                      L"Failed to find/query the content set root on the file system. csId:%? error:%?",
                      &v265,
                      SessionAndBeginTransaction);
                  }
                  CLEAR_ERROR(&v99);
                  v48 = GetCurrentThreadId();
                  SessionAndBeginTransaction = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                     v49,
                                                                     9198,
                                                                     0,
                                                                     3,
                                                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                                     "DBClone::IDTableImportUpdate",
                                                                     3636,
                                                                     v48,
                                                                     0);
                  v99 = SessionAndBeginTransaction;
LABEL_96:
                  if ( !SessionAndBeginTransaction )
                  {
LABEL_97:
                    v50 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18);
                    v51 = v109;
                    if ( !v50 )
                    {
                      v52 = CSTable::Retrieve(
                              (struct Pdb *)((char *)v109 + 168),
                              &v265,
                              (struct CONTENT_SET_RECORD *)v273);
                      v99 = v52;
                      if ( v52 )
                      {
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                        {
                          v160 = L"DBClone::IDTableImportUpdate";
                          v161 = 3650;
                          v162 = 2;
                          v163 = L"DBCL";
                          dbgobj::DbgPrint<unsigned short,_GUID,FrsStatus>(
                            &v160,
                            L"Failed to get the content set record for csId:%? error:%?",
                            &v265,
                            v52);
                        }
                        CLEAR_ERROR(&v99);
                        v53 = GetCurrentThreadId();
                        v99 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v54,
                                                    9604,
                                                    0,
                                                    3,
                                                    "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                    "DBClone::IDTableImportUpdate",
                                                    3659,
                                                    v53,
                                                    0);
                      }
                      DBClone::CommitBeginTransactionOrRollBack(v104, 0, 0, 0, &v99, 0x23F0u);
                      SessionAndBeginTransaction = v99;
                    }
                    if ( !SessionAndBeginTransaction
                      && !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                    {
                      v274 = v106;
                      v99 = CSTable::Update(
                              (struct Pdb *)((char *)v51 + 168),
                              &v265,
                              (const struct CONTENT_SET_RECORD *)v273);
                      DBClone::CommitBeginTransactionOrRollBack(v104, 0, v103 >= 0x20, &v103, &v99, 0x23F9u);
                      if ( g_DebugLog
                        && LODWORD(g_DebugLog[1].LockSemaphore)
                        && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                      {
                        v184 = L"DBClone::IDTableImportUpdate";
                        v185 = 3692;
                        v186 = 4;
                        v187 = L"DBCL";
                        dbgobj::DbgPrint<unsigned short,CONTENT_SET_RECORD>(
                          &v184,
                          L"Update content set record:%?",
                          v273);
                      }
                      SessionAndBeginTransaction = v99;
                    }
                  }
                }
                v55 = (void **)std::deque<ID_RECORD *>::back(v113);
                if ( !*v55 )
                {
                  v57 = GetCurrentThreadId();
                  SessionAndBeginTransaction = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                     v58,
                                                                     4317,
                                                                     0,
                                                                     3,
                                                                     "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                                     "DBClone::IDTableImportUpdate",
                                                                     3711,
                                                                     v57,
                                                                     0);
                  v99 = SessionAndBeginTransaction;
                  goto LABEL_233;
                }
                v56 = *v55;
                while ( 2 )
                {
                  operator delete[](v56);
LABEL_232:
                  std::deque<ID_RECORD *>::pop_back(v113);
                  while ( 1 )
                  {
LABEL_233:
                    if ( SessionAndBeginTransaction )
                      goto LABEL_234;
LABEL_147:
                    if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                      || (unsigned __int8)std::deque<UID_VISIT>::empty(v113) )
                    {
                      goto LABEL_234;
                    }
                    v62 = *(_QWORD *)std::deque<ID_RECORD *>::back(v113);
                    v134 = v62 + 156;
                    v63 = v101;
                    SessionAndBeginTransaction = NtfsFileSystem::GetFileInfo(
                                                   (NtfsFileSystem *)&v117,
                                                   (DBClone *)((char *)v101 + 264),
                                                   (const struct FileId *)&v108,
                                                   (const unsigned __int16 *)(v62 + 156),
                                                   (struct Usn *)&v106,
                                                   (struct FileId *)(v62 + 688),
                                                   0,
                                                   &v268,
                                                   0);
                    v99 = SessionAndBeginTransaction;
                    if ( !SessionAndBeginTransaction )
                      break;
                    VersionChainVector::Insert(v112, v260, v62 + 24);
                    *((_DWORD *)v63 + 38) = 1;
                    ++v100;
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                    {
                      v216 = L"DBClone::IDTableImportUpdate";
                      v217 = 3916;
                      v218 = 3;
                      v219 = L"DBCL";
                      dbgobj::DbgPrint<unsigned short,GVSN,unsigned short const *,FrsStatus>(
                        (unsigned int)&v216,
                        v64,
                        v62 + 24,
                        (unsigned int)&v134,
                        (__int64)SessionAndBeginTransaction);
                    }
                    CLEAR_ERROR(&v99);
                    if ( v62 )
                    {
                      v65 = (void *)v62;
LABEL_156:
                      operator delete[](v65);
                    }
                    while ( 1 )
                    {
                      std::deque<ID_RECORD *>::pop_back(v113);
                      if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                        || (unsigned __int8)std::deque<UID_VISIT>::empty(v113) )
                      {
                        break;
                      }
                      v66 = *(char **)std::deque<ID_RECORD *>::back(v113);
                      VersionChainVector::Insert(v112, v259, v66 + 24);
                      if ( v66 )
                      {
                        v65 = v66;
                        goto LABEL_156;
                      }
                    }
                    SessionAndBeginTransaction = v99;
                  }
                  if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                    goto LABEL_298;
                  v68 = *((_DWORD *)v63 + 37);
                  v266 = 0;
                  v267 = 0;
                  if ( v106 >= v129->NextUsn )
                  {
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                    {
                      v188 = L"DBClone::IDTableImportUpdate";
                      v189 = 3972;
                      v190 = 4;
                      v191 = L"DBCL";
                      dbgobj::DbgPrint<unsigned short,__int64,__int64>(&v188, v67, &v106);
                    }
                    goto LABEL_204;
                  }
                  if ( !v68 )
                    goto LABEL_204;
                  v69 = v68 - 1;
                  if ( v69 )
                  {
                    if ( v69 == 1 )
                    {
                      if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                        || (SessionAndBeginTransaction = DBClone::GetValidationHash(
                                                           v63,
                                                           (DBClone *)((char *)v63 + 264),
                                                           (struct FileId *)(v62 + 688),
                                                           (struct HASH *)&v266),
                            (v99 = SessionAndBeginTransaction) == 0) )
                      {
                        v71 = *(_QWORD *)(v62 + 88) - v266;
                        if ( !v71 )
                        {
                          v71 = *(_QWORD *)(v62 + 96) - *((_QWORD *)&v266 + 1);
                          if ( !v71 )
                            v71 = *(unsigned int *)(v62 + 104) - (unsigned __int64)v267;
                        }
                        if ( v71 || *(_DWORD *)(v62 + 148) != v268.dwFileAttributes )
                        {
                          if ( g_DebugLog
                            && LODWORD(g_DebugLog[1].LockSemaphore)
                            && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                          {
                            v192 = L"DBClone::IDTableImportUpdate";
                            v193 = 4085;
                            v194 = 3;
                            v195 = L"DBCL";
                            dbgobj::DbgPrint<unsigned short,HASH,unsigned long,ID_RECORD>(
                              (unsigned int)&v192,
                              v70,
                              (unsigned int)&v266,
                              (unsigned int)&v268,
                              v62);
                          }
                          goto LABEL_199;
                        }
                      }
                    }
                  }
                  else if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                         || (SessionAndBeginTransaction = DBClone::GetValidationHash(
                                                            v63,
                                                            (DBClone *)((char *)v63 + 264),
                                                            (struct FileId *)(v62 + 688),
                                                            (struct HASH *)&v266),
                             (v99 = SessionAndBeginTransaction) == 0) )
                  {
                    if ( *(_QWORD *)(v62 + 108) != *(_QWORD *)&v268.ftLastWriteTime )
                      goto LABEL_193;
                    v72 = *(_DWORD *)(v62 + 148);
                    if ( (v72 & 0x10) == 0
                      && (*(_DWORD *)(v62 + 116) != v268.nFileSizeLow || *(_DWORD *)(v62 + 120) != v268.nFileSizeHigh) )
                    {
                      goto LABEL_193;
                    }
                    v73 = *(_QWORD *)(v62 + 88) - v266;
                    if ( !v73 )
                    {
                      v73 = *(_QWORD *)(v62 + 96) - *((_QWORD *)&v266 + 1);
                      if ( !v73 )
                        v73 = *(unsigned int *)(v62 + 104) - (unsigned __int64)v267;
                    }
                    if ( v73 || v72 != v268.dwFileAttributes )
                    {
LABEL_193:
                      v74 = 0;
                      v75 = 0;
                      v76 = *(_QWORD *)(v62 + 108);
                      if ( (*(_BYTE *)(v62 + 148) & 0x10) == 0 )
                      {
                        v74 = *(_DWORD *)(v62 + 116);
                        v75 = *(_DWORD *)(v62 + 120);
                      }
                      if ( g_DebugLog
                        && LODWORD(g_DebugLog[1].LockSemaphore)
                        && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                      {
                        v196 = L"DBClone::IDTableImportUpdate";
                        v197 = 4045;
                        v198 = 3;
                        v199 = L"DBCL";
                        v119 = v75;
                        v110 = v74;
                        v135 = v76;
                        ftLastWriteTime = (VsnManager *)v268.ftLastWriteTime;
                        dbgobj::DbgPrint<unsigned short,HASH,_FILETIME,unsigned long,unsigned long,unsigned long,HASH,_FILETIME,unsigned long,unsigned long,unsigned long,ID_RECORD>(
                          (unsigned int)&v196,
                          (unsigned int)L"DBCL",
                          (unsigned int)&v266,
                          (unsigned int)&ftLastWriteTime,
                          (__int64)&v268.nFileSizeLow,
                          (__int64)&v268.nFileSizeHigh,
                          (__int64)&v268,
                          v62 + 88,
                          (__int64)&v135,
                          (__int64)&v110,
                          (__int64)&v119,
                          v62 + 148,
                          v62);
                      }
LABEL_199:
                      std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v252);
                      VersionChainVector::Insert(v112, v258, v62 + 24);
                      *((_DWORD *)v63 + 38) = 1;
                      if ( g_DebugLog
                        && LODWORD(g_DebugLog[1].LockSemaphore)
                        && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                      {
                        v200 = L"DBClone::IDTableImportUpdate";
                        v201 = 4110;
                        v202 = 3;
                        v203 = L"DBCL";
                        dbgobj::DbgPrint<unsigned short,_GUID,unsigned short [261],GVSN>(
                          (unsigned int)&v200,
                          (unsigned int)L"(Updated file) mismatch. csId:%? name:%? gvsn:%?",
                          (unsigned int)&v265,
                          v62 + 156,
                          v62 + 24);
                      }
                      FileTime::Decrement((struct _FILETIME *)(v62 + 132));
                      v77 = v118;
                      VsnManager::GetNextVersion(
                        v118,
                        &v265,
                        (DBClone *)((char *)v63 + 80),
                        (struct VersionChainVector *)v252);
                      *(_OWORD *)(v62 + 24) = *(_OWORD *)((char *)v77 + 88);
                      *(_QWORD *)(v62 + 40) = *((_QWORD *)v63 + 10);
                      VersionChainVector::Insert(v112, v257, v62 + 24);
                      ++v100;
                      std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v252);
                    }
                  }
LABEL_204:
                  *(_OWORD *)(v62 + 108) = 0;
                  *(_OWORD *)(v62 + 88) = 0;
                  *(_DWORD *)(v62 + 104) = 0;
                  if ( !SessionAndBeginTransaction )
                  {
LABEL_298:
                    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                    {
                      v108 = *(_QWORD *)(v62 + 688);
                      *(_QWORD *)(v62 + 680) = v106;
                      ID_RECORD::SetFlags((ID_RECORD *)v62, 5u);
                      if ( (unsigned __int8)operator==(v62 + 124, 2) )
                      {
                        *v78 = 3;
                      }
                      else if ( (unsigned __int8)operator==(v78, 0)
                             && g_DebugLog
                             && LODWORD(g_DebugLog[1].LockSemaphore)
                             && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                      {
                        v204 = L"DBClone::IDTableImportUpdate";
                        v205 = 4176;
                        v206 = 3;
                        v207 = L"DBCL";
                        dbgobj::DbgPrint<unsigned short,ID_RECORD>(
                          &v204,
                          L"Ignored. A record with unfenced value. idRec:%?",
                          v62);
                      }
                      v79 = IDTable::Insert(v109, (const struct ID_RECORD *)v62);
                      v99 = v79;
                      if ( v79 )
                      {
                        if ( FrsStatus::GetPreviousErrorCode(v79) == -1605 )
                        {
                          if ( g_DebugLog
                            && LODWORD(g_DebugLog[1].LockSemaphore)
                            && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                          {
                            v212 = L"DBClone::IDTableImportUpdate";
                            v213 = 4188;
                            v214 = 4;
                            v215 = L"DBCL";
                            dbgobj::DbgPrint<unsigned short,_GUID,ID_RECORD,FrsStatus>(
                              (unsigned int)&v212,
                              (unsigned int)L"Duplicate DB entry. csId:%? idRec:%? error:%?",
                              (unsigned int)&v265,
                              v62,
                              v80);
                          }
                          CLEAR_ERROR(&v99);
                        }
                        else if ( g_DebugLog
                               && LODWORD(g_DebugLog[1].LockSemaphore)
                               && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                        {
                          v248 = L"DBClone::IDTableImportUpdate";
                          v249 = 4195;
                          v250 = 2;
                          v251 = L"DBCL";
                          dbgobj::DbgPrint<unsigned short,_GUID,ID_RECORD,FrsStatus>(
                            (unsigned int)&v248,
                            (unsigned int)L"Failed to Insert DB record. csId:%? idRec:%? error:%?",
                            (unsigned int)&v265,
                            v62,
                            v80);
                        }
                      }
                      else if ( g_DebugLog
                             && LODWORD(g_DebugLog[1].LockSemaphore)
                             && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                      {
                        v208 = L"DBClone::IDTableImportUpdate";
                        v209 = 4185;
                        v210 = 4;
                        v211 = L"DBCL";
                        dbgobj::DbgPrint<unsigned short,ID_RECORD>(&v208, L"Insert DB record. idRec:%?", v62);
                      }
                      DBClone::CommitBeginTransactionOrRollBack(v104, 0, v103 >= 0x20, &v103, &v99, 0x23F0u);
                      SessionAndBeginTransaction = v99;
                    }
                  }
                  if ( v62 )
                  {
                    v56 = (void *)v62;
                    continue;
                  }
                  goto LABEL_232;
                }
              }
              if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                && *((_QWORD *)v24 + 2) == 2 )
              {
                while ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                     && !(unsigned __int8)std::deque<UID_VISIT>::empty(v113) )
                {
                  v59 = *(char **)std::deque<ID_RECORD *>::back(v113);
                  VersionChainVector::Insert(v112, v262, v59 + 24);
                  *((_DWORD *)v101 + 38) = 1;
                  ++v100;
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                  {
                    v172 = L"DBClone::IDTableImportUpdate";
                    v173 = 3734;
                    v174 = 3;
                    v175 = L"DBCL";
                    dbgobj::DbgPrint<unsigned short,GVSN>(&v172, L"(Tombstone) mismatch. gvsn:%?", v59 + 24);
                  }
                  if ( v59 )
                    operator delete[](v59);
                  std::deque<ID_RECORD *>::pop_back(v113);
                }
                goto LABEL_234;
              }
              if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) )
                goto LABEL_147;
              ID_RECORD::ID_RECORD((ID_RECORD *)v287);
              v35 = IDTable::Retrieve(v34, (ID_RECORD *)((char *)v24 + 48), (struct ID_RECORD *)v287);
              v99 = v35;
              DBClone::CommitBeginTransactionOrRollBack(v104, 0, 0, 0, &v99, 0x23F9u);
              SessionAndBeginTransaction = v99;
              if ( v99 )
                goto LABEL_234;
              if ( !v35 )
                break;
              v36 = IDTable::Retrieve(v126, (ID_RECORD *)((char *)v24 + 48), (struct ID_RECORD *)v287);
              SessionAndBeginTransaction = v36;
              v99 = v36;
              if ( v36 )
              {
                if ( *((_DWORD *)v36 + 1) == 9209 )
                {
                  CLEAR_ERROR(&v99);
                  SessionAndBeginTransaction = v99;
                  if ( !v99 )
                  {
                    while ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                         && !(unsigned __int8)std::deque<UID_VISIT>::empty(v113) )
                    {
                      v60 = *(char **)std::deque<ID_RECORD *>::back(v113);
                      VersionChainVector::Insert(v112, v256, v60 + 24);
                      *((_DWORD *)v101 + 38) = 1;
                      ++v100;
                      if ( g_DebugLog
                        && LODWORD(g_DebugLog[1].LockSemaphore)
                        && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                      {
                        v176 = L"DBClone::IDTableImportUpdate";
                        v177 = 3828;
                        v178 = 3;
                        v179 = L"DBCL";
                        dbgobj::DbgPrint<unsigned short,GVSN>(&v176, L"(Missing parent) mismatch. gvsn:%?", v60 + 24);
                      }
                      if ( v60 )
                        operator delete[](v60);
                      std::deque<ID_RECORD *>::pop_back(v113);
                    }
                  }
                  goto LABEL_234;
                }
                goto LABEL_233;
              }
              v124 = (ID_RECORD *)operator new(0x2C8u);
              v37 = ID_RECORD::ID_RECORD(v124);
              v107 = v37;
              v38 = v287;
              v39 = 5;
              do
              {
                *(_OWORD *)v37 = *v38;
                *((_OWORD *)v37 + 1) = v38[1];
                *((_OWORD *)v37 + 2) = v38[2];
                *((_OWORD *)v37 + 3) = v38[3];
                *((_OWORD *)v37 + 4) = v38[4];
                *((_OWORD *)v37 + 5) = v38[5];
                *((_OWORD *)v37 + 6) = v38[6];
                v37 = (ID_RECORD *)((char *)v37 + 128);
                *((_OWORD *)v37 - 1) = v38[7];
                v38 += 8;
                --v39;
              }
              while ( v39 );
              *(_OWORD *)v37 = *v38;
              *((_OWORD *)v37 + 1) = v38[1];
              *((_OWORD *)v37 + 2) = v38[2];
              *((_OWORD *)v37 + 3) = v38[3];
              *((_QWORD *)v37 + 8) = *((_QWORD *)v38 + 8);
              std::deque<ID_RECORD *>::push_back(v113, &v107);
              v24 = v107;
            }
            if ( (*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) || v288 != 2 )
            {
              v108 = v289;
              goto LABEL_233;
            }
            while ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18)
                 && !(unsigned __int8)std::deque<UID_VISIT>::empty(v113) )
            {
              v61 = *(char **)std::deque<ID_RECORD *>::back(v113);
              VersionChainVector::Insert(v112, v261, v61 + 24);
              *((_DWORD *)v101 + 38) = 1;
              ++v100;
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
              {
                v180 = L"DBClone::IDTableImportUpdate";
                v181 = 3859;
                v182 = 3;
                v183 = L"DBCL";
                dbgobj::DbgPrint<unsigned short,GVSN>(&v180, L"(Parent tombstone) mismatch. gvsn:%?", v61 + 24);
              }
              if ( v61 )
                operator delete[](v61);
              std::deque<ID_RECORD *>::pop_back(v113);
            }
LABEL_234:
            IDTable::iterator::operator++((IDTable::iterator *)v285);
            v81 = JErrToFrsStatus::Map(*((_DWORD *)v285[0] + 7));
            v23 = v128;
            if ( v81 != 9200 )
            {
LABEL_235:
              v5 = v122;
              v19 = v121;
              v20 = v101;
              break;
            }
          }
        }
        SessionAndBeginTransaction = DbUtil::CommitTransaction(v104, SessionAndBeginTransaction, 0);
        v99 = SessionAndBeginTransaction;
        if ( !SessionAndBeginTransaction )
        {
          v82 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18);
          v83 = v101;
          if ( !v82 )
          {
            v84 = *((_DWORD *)v101 + 37);
            if ( v84 )
            {
              if ( v84 != 3 )
              {
                std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(v127);
                ResetEvent(*((HANDLE *)v83 + 42));
                v264 = *v129;
                ImportDirWalkerTask::QueueImportCleanupJob(
                  v5,
                  &v265,
                  &v264,
                  (const struct FileId *)v284,
                  v282,
                  (const struct UID *)v277,
                  &v283,
                  (struct VersionChainVector *)v127,
                  (DBClone *)((char *)v83 + 80));
                WaitForSingleObject(*((HANDLE *)v83 + 42), 0xFFFFFFFF);
                if ( VersionChainVector::NumberOfIntervals((VersionChainVector *)v127) )
                {
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                  {
                    v220 = L"DBClone::IDTableImportUpdate";
                    v221 = 4277;
                    v222 = 4;
                    v223 = L"DBCL";
                    dbgobj::DbgPrint<unsigned short,_GUID,VersionChainVector,VersionChainVector>(
                      (unsigned int)&v220,
                      v85,
                      (unsigned int)&v265,
                      (unsigned int)v127,
                      (__int64)v111);
                  }
                  VersionChainVector::Union((VersionChainVector *)v111, (const struct VersionChainVector *)v127);
                  v86 = g_DebugLog;
                  if ( g_DebugLog )
                  {
                    if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
                    {
                      v224 = L"DBClone::IDTableImportUpdate";
                      v225 = 4284;
                      v226 = 4;
                      v227 = L"DBCL";
                      dbgobj::DbgPrint<unsigned short,VersionChainVector>(&v224, L"vvAdded:%?", v127);
                      v86 = g_DebugLog;
                    }
                    if ( v86 && LODWORD(v86[1].LockSemaphore) && SLODWORD(v86[1].OwningThread) >= 4 )
                    {
                      v228 = L"DBClone::IDTableImportUpdate";
                      v229 = 4285;
                      v230 = 4;
                      v231 = L"DBCL";
                      dbgobj::DbgPrint<unsigned short,VersionChainVector>(&v228, L"vvClone:%?", v111);
                    }
                  }
                  *((_DWORD *)v83 + 38) = 1;
                }
                std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v127);
              }
            }
          }
          if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)v18 + 48LL))(v18) && *((_DWORD *)v83 + 38) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v232 = L"DBClone::IDTableImportUpdate";
              v233 = 4298;
              v234 = 4;
              v235 = L"DBCL";
              dbgobj::DbgPrint<unsigned short,_GUID,VersionChainVector>(
                &v232,
                L"Removing deleted/modified changes for csId:%? from vvMaster:%?",
                &v265,
                v111);
            }
            VersionChainVector::Delete((VersionChainVector *)v111, (const struct VersionChainVector *)v112);
            v87 = g_DebugLog;
            if ( g_DebugLog )
            {
              if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
              {
                v236 = L"DBClone::IDTableImportUpdate";
                v237 = 4304;
                v238 = 4;
                v239 = L"DBCL";
                dbgobj::DbgPrint<unsigned short,VersionChainVector>(&v236, L"vvDiff:%?", v112);
                v87 = g_DebugLog;
              }
              if ( v87 && LODWORD(v87[1].LockSemaphore) && SLODWORD(v87[1].OwningThread) >= 4 )
              {
                v240 = L"DBClone::IDTableImportUpdate";
                v241 = 4305;
                v242 = 4;
                v243 = L"DBCL";
                dbgobj::DbgPrint<unsigned short,VersionChainVector>(&v240, L"vvClone:%?", v111);
              }
            }
            v88 = (const volatile int *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v18 + 40LL))(v18);
            SessionAndBeginTransaction = DbUtil::UpdateVersionVector(
                                           *((struct DbManager **)v83 + 41),
                                           &v265,
                                           (const struct VersionChainVector *)v111,
                                           0,
                                           v88);
            v99 = SessionAndBeginTransaction;
            if ( !SessionAndBeginTransaction
              && g_DebugLog
              && LODWORD(g_DebugLog[1].LockSemaphore)
              && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v244 = L"DBClone::IDTableImportUpdate";
              v245 = 4314;
              v246 = 4;
              v247 = L"DBCL";
              dbgobj::DbgPrint<unsigned short,_GUID,VersionChainVector>(
                &v244,
                L"Clone version vector. csId:%? vvClone:%?",
                &v265,
                v111);
            }
          }
          v20 = v101;
        }
      }
      else
      {
        v89 = GetCurrentThreadId();
        SessionAndBeginTransaction = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                           v90,
                                                           4317,
                                                           0,
                                                           3,
                                                           "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
                                                           "DBClone::IDTableImportUpdate",
                                                           3415,
                                                           v89,
                                                           0);
        v99 = SessionAndBeginTransaction;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,VvCompactTask *>>>,std::_Iterator_base0>::operator++(&v114);
      if ( SessionAndBeginTransaction )
      {
        v2 = v101;
        break;
      }
      v17 = v114;
    }
  }
  if ( v104 )
  {
    SessionAndBeginTransaction = DbUtil::CommitTransaction(v104, SessionAndBeginTransaction, 0);
    (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)v2 + 41) + 64LL))(*((_QWORD *)v2 + 41), &v104);
  }
  if ( v115 )
  {
    SessionAndBeginTransaction = DbUtil::CommitTransaction(v115, SessionAndBeginTransaction, 0);
    (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)v2 + 40) + 64LL))(*((_QWORD *)v2 + 40), &v115);
  }
  if ( v116 )
  {
    SessionAndBeginTransaction = DbUtil::CommitTransaction(v116, SessionAndBeginTransaction, 0);
    (*(void (__fastcall **)(_QWORD, struct Db **))(**((_QWORD **)v2 + 40) + 64LL))(*((_QWORD *)v2 + 40), &v116);
  }
  while ( !(unsigned __int8)std::deque<UID_VISIT>::empty(v113) )
  {
    v95 = (void **)std::deque<ID_RECORD *>::back(v113);
    if ( *v95 )
      operator delete[](*v95);
    std::deque<ID_RECORD *>::pop_back(v113);
  }
  if ( SessionAndBeginTransaction )
  {
    v96 = GetCurrentThreadId();
    v3 = FrsStatusList::PushNewError(
           v97,
           *((unsigned int *)SessionAndBeginTransaction + 1),
           *((unsigned int *)SessionAndBeginTransaction + 2),
           *(unsigned int *)SessionAndBeginTransaction,
           "base\\fs\\remotefs\\frs\\src\\main\\dbclone.cpp",
           "DBClone::IDTableImportUpdate",
           4370,
           v96,
           SessionAndBeginTransaction);
  }
  std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v112);
  std::_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>::~_Tree<std::_Tmap_traits<Guid,IntervalSet,std::less<Guid>,std::allocator<std::pair<Guid const,IntervalSet>>,0>>(v111);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v122);
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v118);
  std::deque<_FRS_RDC_SOURCE_NEED>::~deque<_FRS_RDC_SOURCE_NEED>(v113);
  v117 = &FileSystem::`vftable';
  v253 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(v254);
  operator delete[](v293[0]);
  operator delete[](v285[0]);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x140032a14  mov     [rsp-8+arg_10], rbx
0x140032a19  push    rbp
0x140032a1a  push    rsi
0x140032a1b  push    rdi
0x140032a1c  push    r12
0x140032a1e  push    r13
0x140032a20  push    r14
0x140032a22  push    r15
0x140032a24  lea     rbp, [rsp-1AC0h]
0x140032a2c  mov     eax, 1BC0h
0x140032a31  call    _alloca_probe
0x140032a36  sub     rsp, rax
0x140032a39  mov     rax, cs:__security_cookie
0x140032a40  xor     rax, rsp
0x140032a43  mov     [rbp+1AF0h+var_40], rax
0x140032a4a  mov     [rbp+1AF0h+var_1A60], rdx
0x140032a51  mov     r13, rcx
0x140032a54  mov     [rbp+1AF0h+var_1B70], rcx
0x140032a58  xor     r15d, r15d
0x140032a5b  xor     edx, edx; Val
0x140032a5d  mov     r8d, 88h; Size
0x140032a63  lea     rcx, [rbp+1AF0h+var_15E0]; void *
0x140032a6a  call    memset_0
0x140032a6f  mov     r12d, r15d
0x140032a72  mov     [rsp+1BF0h+var_1B80], r15
0x140032a77  lea     rcx, [rbp+1AF0h+var_1220]; this
0x140032a7e  call    ??0iterator@IDTable@@QEAA@XZ; IDTable::iterator::iterator(void)
0x140032a83  nop
0x140032a84  lea     rcx, [rbp+1AF0h+var_970]; this
0x140032a8b  call    ??0iterator@IDTable@@QEAA@XZ; IDTable::iterator::iterator(void)
0x140032a90  nop
0x140032a91  mov     [rbp+1AF0h+var_1A80], r15
0x140032a95  mov     [rbp+1AF0h+var_1AA8], r15
0x140032a99  mov     [rbp+1AF0h+var_1B38], r15
0x140032a9d  mov     [rbp+1AF0h+var_1AD0], r15
0x140032aa1  mov     [rbp+1AF0h+var_1AD8], r15
0x140032aa5  mov     [rbp+1AF0h+var_1B60], r15
0x140032aa9  xorps   xmm0, xmm0
0x140032aac  xor     eax, eax
0x140032aae  movups  xmmword ptr [rbp+1AF0h+var_1698.dwFileAttributes], xmm0
0x140032ab5  movups  xmmword ptr [rbp+1AF0h+var_1698.ftLastAccessTime.dwHighDateTime], xmm0
0x140032abc  movups  xmmword ptr [rbp+1AF0h+var_1698.nFileSizeHigh], xmm0
0x140032ac3  mov     [rbp+1AF0h+var_1698.nFileIndexLow], eax
0x140032ac9  mov     [rbp+1AF0h+var_1B40], r15
0x140032acd  lea     rcx, [rbp+1AF0h+var_1760]; this
0x140032ad4  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x140032ad9  nop
0x140032ada  lea     rax, ??_7NtfsFileSystem@@6B@; const NtfsFileSystem::`vftable'
0x140032ae1  mov     [rbp+1AF0h+var_1AC8], rax
0x140032ae5  mov     [rbp+1AF0h+var_1AB0], r15
0x140032ae9  mov     [rbp+1AF0h+var_1B50], r15
0x140032aed  lea     rcx, [rbp+1AF0h+var_1B08]
0x140032af1  call    ??0?$deque@UUID_VISIT@@V?$allocator@UUID_VISIT@@@std@@@std@@QEAA@XZ; std::deque<UID_VISIT>::deque<UID_VISIT>(void)
0x140032af6  nop
0x140032af7  mov     [rbp+1AF0h+var_1AC0], r15
0x140032afb  mov     edi, r15d
0x140032afe  mov     [rbp+1AF0h+var_1AA0], r15
0x140032b02  lea     rcx, [rbp+1AF0h+var_1B28]
0x140032b06  call    ??0?$map@U_GUID@@VVvInfo@VvCompactMan@LdbManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VVvInfo@VvCompactMan@LdbManager@@@std@@@6@@std@@QEAA@XZ; std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(void)
0x140032b0b  nop
0x140032b0c  lea     rcx, [rbp+1AF0h+var_1B18]
0x140032b10  call    ??0?$map@U_GUID@@VVvInfo@VvCompactMan@LdbManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VVvInfo@VvCompactMan@LdbManager@@@std@@@6@@std@@QEAA@XZ; std::map<_GUID,LdbManager::VvCompactMan::VvInfo>::map<_GUID,LdbManager::VvCompactMan::VvInfo>(void)
0x140032b15  nop
0x140032b16  mov     [rbp+1AF0h+var_1B58], r15d
0x140032b1a  mov     r14d, [r13+160h]
0x140032b21  mov     [rbp+1AF0h+var_1B68], r14d
0x140032b25  mov     [rsp+1BF0h+var_1B78], r15d
0x140032b2a  mov     [rbp+1AF0h+var_1B64], r15d
0x140032b2e  lea     rcx, [rbp+1AF0h+var_14F0]; this
0x140032b35  call    ??0ID_RECORD@@QEAA@XZ; ID_RECORD::ID_RECORD(void)
0x140032b3a  lea     rbx, aDbcloneIdtable_1; "DBClone::IDTableImportUpdate"
0x140032b41  lea     rcx, aDbcl; "DBCL"
0x140032b48  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140032b4f  test    rax, rax
0x140032b52  jz      short loc_140032B95
0x140032b54  cmp     [rax+40h], r15d
0x140032b58  jz      short loc_140032B95
0x140032b5a  cmp     dword ptr [rax+38h], 4
0x140032b5e  jl      short loc_140032B95
0x140032b60  mov     [rbp+1AF0h+var_19B0], rbx
0x140032b67  mov     [rbp+1AF0h+var_19A8], 0CE3h
0x140032b71  mov     [rbp+1AF0h+var_19A4], 4
0x140032b7b  mov     [rbp+1AF0h+var_19A0], rcx
0x140032b82  lea     rdx, aCopyingTheIdta; "Copying the IDTable"
0x140032b89  lea     rcx, [rbp+1AF0h+var_19B0]
0x140032b90  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140032b95  lea     rsi, [r13+78h]
0x140032b99  mov     rax, [rsi]
0x140032b9c  mov     rcx, rsi
0x140032b9f  mov     rax, [rax+30h]
0x140032ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032ba8  test    al, al
0x140032baa  jnz     loc_140032C59
0x140032bb0  lea     rbx, [r13+50h]
0x140032bb4  mov     qword ptr [rbx], 0Bh
0x140032bbb  mov     ecx, 80h; Size
0x140032bc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140032bc5  mov     [rbp+1AF0h+var_1A88], rax
0x140032bc9  mov     r8, rbx; struct VERSION *
0x140032bcc  lea     rdx, [r13+40h]; struct _GUID *
0x140032bd0  mov     rcx, rax; this
0x140032bd3  call    ??0VsnManager@@QEAA@AEBU_GUID@@AEBVVERSION@@@Z; VsnManager::VsnManager(_GUID const &,VERSION const &)
0x140032bd8  nop
0x140032bd9  mov     rdx, rax
0x140032bdc  lea     rcx, [rbp+1AF0h+var_1AC0]
0x140032be0  call    ?Set@?$ScopedRef@VShutdownRestartTask@VolumeManager@@@@AEAAXPEAVShutdownRestartTask@VolumeManager@@@Z; ScopedRef<VolumeManager::ShutdownRestartTask>::Set(VolumeManager::ShutdownRestartTask *)
0x140032be5  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140032bec  test    rax, rax
0x140032bef  jz      short loc_140032C4E
0x140032bf1  cmp     [rax+40h], r15d
0x140032bf5  jz      short loc_140032C4E
0x140032bf7  cmp     dword ptr [rax+38h], 4
0x140032bfb  jl      short loc_140032C4E
0x140032bfd  lea     rax, aDbcloneIdtable_1; "DBClone::IDTableImportUpdate"
0x140032c04  mov     [rbp+1AF0h+var_19C8], rax
0x140032c0b  mov     [rbp+1AF0h+var_19C0], 0CF6h
0x140032c15  mov     [rbp+1AF0h+var_19BC], 4
0x140032c1f  lea     rax, aDbcl; "DBCL"
0x140032c26  mov     [rbp+1AF0h+var_19B8], rax
0x140032c2d  mov     rax, [rbx]
0x140032c30  mov     [rbp+1AF0h+var_1A58], rax
0x140032c37  lea     r9, [rbp+1AF0h+var_1A58]
0x140032c3e  lea     r8, [r13+40h]
0x140032c42  lea     rcx, [rbp+1AF0h+var_19C8]
0x140032c49  call    ??$DbgPrint@GVGuid@@VVERSION@@@dbgobj@@QEAA_KPEBGAEBVGuid@@AEBVVERSION@@@Z; dbgobj::DbgPrint<ushort,Guid,VERSION>(ushort const *,Guid const &,VERSION const &)
0x140032c4e  lea     rbx, aDbcloneIdtable_1; "DBClone::IDTableImportUpdate"
0x140032c55  mov     r14d, [rbp+1AF0h+var_1B68]
0x140032c59  mov     rax, [rsi]
0x140032c5c  mov     rcx, rsi
0x140032c5f  mov     rax, [rax+30h]
0x140032c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032c68  test    al, al
0x140032c6a  jnz     loc_140032D26
0x140032c70  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140032c77  test    rax, rax
0x140032c7a  jz      short loc_140032CC4
0x140032c7c  cmp     [rax+40h], r15d
0x140032c80  jz      short loc_140032CC4
0x140032c82  cmp     dword ptr [rax+38h], 4
0x140032c86  jl      short loc_140032CC4
0x140032c88  mov     [rbp+1AF0h+var_19E0], rbx
0x140032c8f  mov     [rbp+1AF0h+var_19D8], 0CFFh
0x140032c99  mov     [rbp+1AF0h+var_19D4], 4
0x140032ca3  lea     rax, aDbcl; "DBCL"
0x140032caa  mov     [rbp+1AF0h+var_19D0], rax
0x140032cb1  lea     rdx, aCreatingTheImp; "Creating the ImportDirWalkerTask."
0x140032cb8  lea     rcx, [rbp+1AF0h+var_19E0]
0x140032cbf  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x140032cc4  mov     ecx, 178h; Size
0x140032cc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140032cce  mov     rdi, rax
0x140032cd1  mov     [rbp+1AF0h+var_1A88], rax
0x140032cd5  mov     rcx, [r13+28h]
0x140032cd9  mov     rbx, [rcx+540h]
0x140032ce0  mov     rcx, [rsi]
0x140032ce3  mov     rax, [rcx+28h]
0x140032ce7  mov     rcx, rsi
0x140032cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032cef  mov     rcx, [r13+150h]
0x140032cf6  lea     r8, [r13+108h]
0x140032cfd  mov     [rsp+1BF0h+var_1BC0], rbx
0x140032d02  mov     [rsp+1BF0h+var_1BC8], rax
0x140032d07  mov     [rsp+1BF0h+var_1BD0], rcx
0x140032d0c  mov     r9, [r13+148h]
0x140032d13  lea     rdx, [rbp+1AF0h+var_1AC0]
0x140032d17  mov     rcx, rdi
0x140032d1a  call    ??0ImportDirWalkerTask@@QEAA@AEAV?$ScopedRef@VVsnManager@@@@AEAVVolumeId@@PEAVLdbManager@@PEAXAEDHPEAVTaskPool@@@Z; ImportDirWalkerTask::ImportDirWalkerTask(ScopedRef<VsnManager> &,VolumeId &,LdbManager *,void *,int const volatile &,TaskPool *)
0x140032d1f  mov     rdi, rax
0x140032d22  mov     [rbp+1AF0h+var_1AA0], rax
0x140032d26  mov     rax, [rsi]
0x140032d29  mov     rcx, rsi
0x140032d2c  mov     rax, [rax+30h]
0x140032d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032d35  test    al, al
0x140032d37  jnz     short loc_140032D67
0x140032d39  lea     rax, [rbp+1AF0h+var_1AA8]
0x140032d3d  mov     [rsp+1BF0h+var_1BD0], rax; struct Pdb **
0x140032d42  lea     r9, [rbp+1AF0h+var_1AD8]; struct Db **
0x140032d46  mov     edx, 1; int
0x140032d4b  mov     r8d, edx; int
0x140032d4e  mov     rcx, [r13+140h]; struct LdbManager *
0x140032d55  call    ?GetSessionAndBeginTransaction@DBClone@@CAPEAVFrsStatus@@PEAVLdbManager@@HHAEAPEAVDb@@AEAPEAVPdb@@@Z; DBClone::GetSessionAndBeginTransaction(LdbManager *,int,int,Db * &,Pdb * &)
0x140032d5a  mov     r12, rax
0x140032d5d  mov     [rsp+1BF0h+var_1B80], rax
0x140032d62  test    rax, rax
0x140032d65  jnz     short loc_140032DE1
0x140032d67  mov     rax, [rsi]
0x140032d6a  mov     rcx, rsi
0x140032d6d  mov     rax, [rax+30h]
0x140032d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032d76  test    al, al
0x140032d78  jnz     short loc_140032DA6
0x140032d7a  lea     rax, [rbp+1AF0h+var_1A80]
0x140032d7e  mov     [rsp+1BF0h+var_1BD0], rax; struct Pdb **
0x140032d83  lea     r9, [rbp+1AF0h+var_1AD0]; struct Db **
0x140032d87  xor     edx, edx; int
0x140032d89  lea     r8d, [rdx+1]; int
0x140032d8d  mov     rcx, [r13+140h]; struct LdbManager *
0x140032d94  call    ?GetSessionAndBeginTransaction@DBClone@@CAPEAVFrsStatus@@PEAVLdbManager@@HHAEAPEAVDb@@AEAPEAVPdb@@@Z; DBClone::GetSessionAndBeginTransaction(LdbManager *,int,int,Db * &,Pdb * &)
0x140032d99  mov     r12, rax
0x140032d9c  mov     [rsp+1BF0h+var_1B80], rax
0x140032da1  test    rax, rax
0x140032da4  jnz     short loc_140032DE1
0x140032da6  mov     rax, [r13+78h]
0x140032daa  lea     rcx, [r13+78h]
0x140032dae  mov     rax, [rax+30h]
0x140032db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032db7  test    al, al
0x140032db9  jnz     short loc_140032DE1
0x140032dbb  lea     rax, [rbp+1AF0h+var_1B38]
0x140032dbf  mov     [rsp+1BF0h+var_1BD0], rax; struct Pdb **
0x140032dc4  lea     r9, [rbp+1AF0h+var_1B60]; struct Db **
0x140032dc8  xor     r8d, r8d; int
0x140032dcb  xor     edx, edx; int
0x140032dcd  mov     rcx, [r13+148h]; struct LdbManager *
0x140032dd4  call    ?GetSessionAndBeginTransaction@DBClone@@CAPEAVFrsStatus@@PEAVLdbManager@@HHAEAPEAVDb@@AEAPEAVPdb@@@Z; DBClone::GetSessionAndBeginTransaction(LdbManager *,int,int,Db * &,Pdb * &)
0x140032dd9  mov     r12, rax
0x140032ddc  mov     [rsp+1BF0h+var_1B80], rax
0x140032de1  mov     ebx, 0Ah
0x140032de6  mov     r8d, ebx; int
0x140032de9  mov     edx, r14d; unsigned int
0x140032dec  lea     rcx, [rbp+1AF0h+var_1648]; this
0x140032df3  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x140032df8  mov     r14, rax
0x140032dfb  mov     r8d, ebx; int
0x140032dfe  xor     edx, edx; unsigned int
0x140032e00  lea     rcx, [rbp+1AF0h+var_1618]; this
0x140032e07  call    ??0Dword@@QEAA@KH@Z; Dword::Dword(ulong,int)
0x140032e0c  mov     rsi, rax
0x140032e0f  lea     rax, [r13+0C8h]
0x140032e16  mov     [rbp+1AF0h+var_1A48], rax
0x140032e1d  mov     rcx, rax
0x140032e20  call    ?GetDisplayPath@FilePath@@SAPEBGAEBV?$FrsStringImpl@GD@@@Z; FilePath::GetDisplayPath(FrsStringImpl<ushort,char> const &)
0x140032e25  mov     rbx, rax
0x140032e28  lea     rax, [r13+118h]
0x140032e2f  mov     [rbp+1AF0h+var_1A98], rax
0x140032e33  mov     rdx, rax
0x140032e36  lea     rcx, [rbp+1AF0h+var_1A50]
0x140032e3d  call    ?FrsGUIDToStringW@@YA?AV?$FrsStringImpl@GD@@AEBU_GUID@@@Z; FrsGUIDToStringW(_GUID const &)
0x140032e42  nop
0x140032e43  mov     rdx, [rax]
0x140032e46  add     rdx, 12h
0x140032e4a  mov     dword ptr [rsp+1BF0h+var_1BC8], r15d
0x140032e4f  mov     [rsp+1BF0h+var_1BD0], r14
0x140032e54  mov     r9, rsi
0x140032e57  mov     r8, rbx
0x140032e5a  mov     ecx, 40000970h
0x140032e5f  call    ?Log@FrsEvent@@SAXW4FrsEventsEnum4@@PEBG111W4LogUseDebugLog@EventLog@@@Z; FrsEvent::Log(FrsEventsEnum4,ushort const *,ushort const *,ushort const *,ushort const *,EventLog::LogUseDebugLog)
0x140032e64  nop
0x140032e65  lea     rcx, [rbp+1AF0h+var_1A50]
0x140032e6c  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x140032e71  mov     rbx, [r13+58h]
0x140032e75  mov     rbx, [rbx]
0x140032e78  mov     [rbp+1AF0h+var_1AE0], rbx
0x140032e7c  lea     rsi, aDbcloneIdtable_2; "DBClone::IDTableImportUpdate"
0x140032e83  lea     r14, aBaseFsRemotefs_5; "base\\fs\\remotefs\\frs\\src\\main\\dbc"...
0x140032e8a  test    r12, r12
0x140032e8d  jnz     loc_140034C78
0x140032e93  add     r13, 78h ; 'x'
0x140032e97  mov     rsi, [rbp+1AF0h+var_1AA8]
0x140032e9b  mov     r14, [rbp+1AF0h+var_1B70]
0x140032e9f  mov     rax, [r13+0]
0x140032ea3  mov     rcx, r13
0x140032ea6  mov     rax, [rax+30h]
0x140032eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032eaf  test    al, al
0x140032eb1  jnz     loc_140034BBD
0x140032eb7  lea     rdx, [rbp+1AF0h+var_1750]
0x140032ebe  lea     rcx, [r14+58h]
0x140032ec2  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x140032ec7  cmp     rbx, [rax]
0x140032eca  jz      loc_140034BBD
0x140032ed0  lea     rcx, [rbp+1AF0h+var_1AE0]
0x140032ed4  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVUID@@PEAVUpdateReference@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBVUID@@PEAVUpdateReference@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<UID const,UpdateReference *>>>>::operator*(void)
0x140032ed9  movups  xmm0, xmmword ptr [rax]
0x140032edc  movdqu  xmmword ptr [rbp+1AF0h+var_16C0.Data1], xmm0
0x140032ee4  test    r12, r12
0x140032ee7  jnz     loc_140032F91
0x140032eed  mov     rax, [r13+0]
0x140032ef1  mov     rcx, r13
0x140032ef4  mov     rax, [rax+30h]
0x140032ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032efd  test    al, al
0x140032eff  jnz     loc_140032F91
0x140032f05  lea     r8, [rbp+1AF0h+var_1B28]; struct VersionChainVector *
0x140032f09  lea     rdx, [rbp+1AF0h+var_16C0]; struct _GUID *
0x140032f10  mov     rcx, [r14+140h]; struct DbManager *
0x140032f17  call    ?VersionVector@DbUtil@@SAPEAVFrsStatus@@PEAVDbManager@@AEBU_GUID@@AEAVVersionChainVector@@@Z; DbUtil::VersionVector(DbManager *,_GUID const &,VersionChainVector &)
0x140032f1c  mov     r12, rax
0x140032f1f  mov     [rsp+1BF0h+var_1B80], rax
0x140032f24  lea     rbx, aDbcloneIdtable_1; "DBClone::IDTableImportUpdate"
0x140032f2b  test    rax, rax
0x140032f2e  jnz     short loc_140032F98
0x140032f30  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140032f37  test    rax, rax
0x140032f3a  jz      short loc_140032F98
0x140032f3c  cmp     [rax+40h], r15d
0x140032f40  jz      short loc_140032F98
0x140032f42  cmp     dword ptr [rax+38h], 4
0x140032f46  jl      short loc_140032F98
  ... truncated ...
```
