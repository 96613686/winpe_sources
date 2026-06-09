# RefreshQosPolicy(_THSTATE *)

- ea: `0x18034b574`
- end: `0x18034e2a0`
- name: `?RefreshQosPolicy@@YAKPEAU_THSTATE@@@Z`
- size: `11564`
- prototype: `unsigned int __fastcall(struct _THSTATE *)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1803501d0`

## callees

- `0x180006360`
- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000bb80`
- `0x18000ed84`
- `0x18000efd8`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x18002a060`
- `0x180030af8`
- `0x180037ce0`
- `0x18003e3e0`
- `0x180048664`
- `0x180080bdc`
- `0x1800f998c`
- `0x18016a884`
- `0x18016a9f4`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1801c4a34`
- `0x1801d0ea0`
- `0x1801d19dc`
- `0x1801d614c`
- `0x1801d9c4c`
- `0x1801f3190`
- `0x1802b68e4`
- `0x180346e18`
- `0x18034b110`
- `0x18034b574`
- `0x180453340`

## import_xrefs

- `NTDSATQ!AtqCloseQosClass` at `0x18034d74e`
- `NTDSATQ!AtqCloseQosClass` at `0x18034d74e`
- `NTDSATQ!AtqUpdateQosClass` at `0x18034d426`
- `NTDSATQ!AtqUpdateQosClass` at `0x18034d426`
- `NTDSATQ!AtqCreateQosClass` at `0x18034db10`
- `NTDSATQ!AtqCreateQosClass` at `0x18034db10`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18034dff8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18034dff8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18034de24`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18034de24`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18034df0d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18034df0d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedObjectAce` at `0x18034cd12`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedObjectAce` at `0x18034cd12`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18034ca55`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18034ca55`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18034e0e0`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18034e125`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18034e0e0`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18034e125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034ca65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034cd23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034d433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034db21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034de32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034df1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034e006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034e133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034ca65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034cd23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034d433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034db21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034de32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034df1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034e006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18034e133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18034e258`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180472e80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18034e258`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180472e80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18034ca04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18034ca04`

## pseudocode

```c
__int64 __fastcall RefreshQosPolicy(struct _THSTATE *a1)
{
  int v2; // esi
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // r9
  BOOL v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  BOOL v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  BOOL v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // r8
  __int64 v30; // r9
  BOOL v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // r8
  __int64 v37; // r9
  BOOL v38; // ebx
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // r8
  __int64 v44; // r9
  BOOL v45; // ebx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // r8
  __int64 v51; // r9
  BOOL v52; // ebx
  __int64 v53; // rax
  int v54; // r12d
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // r8
  __int64 v60; // r9
  BOOL v61; // ebx
  int v63; // eax
  _QWORD *v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r9
  __int64 v69; // r8
  __int64 v70; // r9
  BOOL v71; // r13d
  int v72; // eax
  DWORD LastError; // r15d
  DWORD AttVal; // eax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r13
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // r8
  __int64 v81; // r9
  int v82; // eax
  __int16 v83; // cx
  int v84; // edx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // r8
  __int64 v90; // r9
  BOOL v91; // r15d
  int v92; // eax
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // r12
  int v98; // r15d
  __int64 v99; // r8
  __int64 v100; // r9
  int v101; // eax
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // r8
  __int64 v107; // r9
  int v108; // eax
  __int64 v109; // rdx
  __int64 v110; // rcx
  __int64 v111; // r8
  __int64 v112; // r9
  __int64 v113; // r8
  __int64 v114; // r9
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  __int64 v120; // r8
  __int64 v121; // r9
  __int64 v122; // rdx
  __int64 v123; // rcx
  int v124; // ebx
  __int64 v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // r8
  __int64 v128; // r9
  int v129; // ebx
  __int64 v130; // r8
  __int64 v131; // r9
  int v132; // eax
  int v133; // ecx
  unsigned int v134; // ebx
  __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // r8
  __int64 v138; // r9
  __int64 v139; // r8
  __int64 v140; // r9
  __int16 v141; // ax
  int v142; // edx
  _BYTE *v143; // r9
  unsigned int v144; // r10d
  __int64 v145; // rbx
  unsigned int v146; // r13d
  __int64 v147; // rdx
  __int64 v148; // rax
  __int64 v149; // r8
  __int64 v150; // rax
  __int64 v151; // r8
  unsigned int i; // ebx
  __int64 v153; // rdx
  __int64 v154; // rcx
  __int64 v155; // r8
  __int64 v156; // r9
  __int64 v157; // r8
  __int64 v158; // r9
  BOOL v159; // ebx
  __int16 v160; // ax
  int v161; // edx
  __int64 v162; // r8
  unsigned int *v163; // rax
  const WCHAR *v164; // rcx
  __int64 v165; // rax
  unsigned int v166; // ebx
  void *v167; // rax
  const wchar_t *v168; // r8
  size_t v169; // rdx
  __int64 v170; // rdx
  __int64 v171; // rcx
  int v172; // r13d
  __int64 v173; // r8
  __int64 v174; // r9
  __int64 v175; // r8
  __int64 v176; // r9
  int v177; // eax
  unsigned int v178; // r13d
  bool v179; // zf
  __int64 v180; // rdx
  __int64 v181; // rbx
  __int64 v182; // rax
  int v183; // edx
  __int64 v184; // rax
  __int64 v185; // rdx
  __int64 v186; // rcx
  __int64 v187; // r8
  __int64 v188; // r9
  int v189; // ebx
  __int64 v190; // r8
  __int64 v191; // r9
  int v192; // eax
  int v193; // ecx
  int v194; // r13d
  _QWORD *v195; // rcx
  __int64 v196; // rax
  LPOVERLAPPED v197; // rbx
  __int64 v198; // rdx
  __int64 v199; // rcx
  __int64 v200; // r9
  int v201; // eax
  int v202; // eax
  __int64 v203; // rcx
  __int64 v204; // r8
  int v205; // eax
  __int64 v206; // rcx
  __int64 v207; // r8
  int v208; // eax
  __int64 v209; // rcx
  __int64 v210; // r8
  __int64 v211; // r9
  int v212; // eax
  int v213; // eax
  int v214; // eax
  unsigned int v215; // ebx
  unsigned int v216; // ecx
  __int64 v217; // rdx
  bool v218; // zf
  __int64 v219; // r9
  _QWORD *v220; // r8
  __int64 v221; // rax
  __int64 v222; // rax
  LPOVERLAPPED v223; // r13
  __int64 v224; // rdx
  __int64 v225; // rcx
  int v226; // r11d
  int v227; // eax
  int v228; // eax
  __int64 v229; // rcx
  int v230; // eax
  __int64 v231; // rcx
  __int64 v232; // r8
  __int64 v233; // r9
  int v234; // eax
  __int64 v235; // rcx
  __int64 v236; // r8
  __int64 v237; // r9
  int v238; // eax
  int v239; // eax
  int v240; // eax
  __int64 v241; // rdx
  __int64 v242; // rcx
  __int64 v243; // r8
  __int64 v244; // r9
  __int64 v245; // r8
  __int64 v246; // r9
  __int64 v247; // rax
  __m128i v248; // xmm1
  unsigned int v249; // edx
  unsigned __int64 v250; // xmm0_8
  __int64 v251; // r13
  __int64 v252; // rax
  LPOVERLAPPED v253; // rbx
  __int64 v254; // rdx
  __int64 v255; // rcx
  __int64 v256; // r8
  __int64 v257; // r9
  __int64 v258; // r8
  __int64 v259; // r9
  __int64 v260; // rdx
  __int64 v261; // rcx
  __int64 v262; // r8
  __int64 v263; // r9
  __int64 v264; // r8
  __int64 v265; // r9
  __int64 v266; // rdx
  __int64 v267; // rcx
  __int64 v268; // r8
  __int64 v269; // r9
  __int64 v270; // r8
  __int64 v271; // r9
  void *v272; // rax
  void *v273; // rbx
  __int64 v274; // rdx
  __int64 v275; // rcx
  __int64 v276; // r8
  __int64 v277; // r9
  __int64 v278; // r8
  __int64 v279; // r9
  unsigned int v280; // eax
  struct _QOS_POLICY_RECORD *v281; // rax
  struct _QOS_POLICY_RECORD *v282; // [rsp+60h] [rbp-1068h]
  void *v283; // [rsp+68h] [rbp-1060h]
  unsigned int v284; // [rsp+70h] [rbp-1058h] BYREF
  int v285; // [rsp+74h] [rbp-1054h]
  int v286; // [rsp+78h] [rbp-1050h]
  unsigned int v287; // [rsp+7Ch] [rbp-104Ch]
  int v288; // [rsp+80h] [rbp-1048h]
  size_t Size; // [rsp+88h] [rbp-1040h]
  unsigned int v290; // [rsp+90h] [rbp-1038h]
  __int64 v291; // [rsp+98h] [rbp-1030h]
  void *Src; // [rsp+A0h] [rbp-1028h]
  __int64 v293; // [rsp+A8h] [rbp-1020h] BYREF
  DWORD dwBufferLength; // [rsp+B0h] [rbp-1018h] BYREF
  PACL pAcl; // [rsp+B8h] [rbp-1010h]
  _QWORD *v296; // [rsp+C0h] [rbp-1008h]
  struct _THSTATE *v297; // [rsp+C8h] [rbp-1000h]
  _DWORD v298[2]; // [rsp+D0h] [rbp-FF8h] BYREF
  unsigned int v299; // [rsp+D8h] [rbp-FF0h]
  _QWORD v300[2]; // [rsp+E0h] [rbp-FE8h] BYREF
  __int16 v301; // [rsp+F0h] [rbp-FD8h]
  int v302; // [rsp+F2h] [rbp-FD6h]
  __int16 v303; // [rsp+F6h] [rbp-FD2h]
  __int64 v304; // [rsp+F8h] [rbp-FD0h]
  __int128 v305; // [rsp+100h] [rbp-FC8h]
  __int64 v306; // [rsp+110h] [rbp-FB8h] BYREF
  int v307; // [rsp+118h] [rbp-FB0h]
  int Internal; // [rsp+11Ch] [rbp-FACh]
  int v309; // [rsp+120h] [rbp-FA8h]
  int v310; // [rsp+128h] [rbp-FA0h]
  int v311; // [rsp+12Ch] [rbp-F9Ch]
  __int64 v312; // [rsp+130h] [rbp-F98h]
  __int64 v313; // [rsp+138h] [rbp-F90h]
  __int64 v314; // [rsp+140h] [rbp-F88h]
  __int64 v315; // [rsp+150h] [rbp-F78h]
  int v316; // [rsp+158h] [rbp-F70h]
  int *v317; // [rsp+168h] [rbp-F60h]
  __int64 v318; // [rsp+170h] [rbp-F58h] BYREF
  int v319; // [rsp+178h] [rbp-F50h]
  int v320; // [rsp+17Ch] [rbp-F4Ch]
  int v321; // [rsp+180h] [rbp-F48h]
  int v322; // [rsp+188h] [rbp-F40h]
  int v323; // [rsp+18Ch] [rbp-F3Ch]
  __int64 v324; // [rsp+190h] [rbp-F38h]
  __int64 v325; // [rsp+198h] [rbp-F30h]
  __int64 v326; // [rsp+1A0h] [rbp-F28h]
  __int64 v327; // [rsp+1B0h] [rbp-F18h]
  int v328; // [rsp+1B8h] [rbp-F10h]
  int *v329; // [rsp+1C8h] [rbp-F00h]
  __int64 v330; // [rsp+1D0h] [rbp-EF8h] BYREF
  int v331; // [rsp+1D8h] [rbp-EF0h]
  int v332; // [rsp+1DCh] [rbp-EECh]
  int v333; // [rsp+1E0h] [rbp-EE8h]
  int v334; // [rsp+1E8h] [rbp-EE0h]
  int v335; // [rsp+1ECh] [rbp-EDCh]
  __int64 v336; // [rsp+1F0h] [rbp-ED8h]
  __int64 v337; // [rsp+1F8h] [rbp-ED0h]
  __int64 v338; // [rsp+200h] [rbp-EC8h]
  __int64 v339; // [rsp+210h] [rbp-EB8h]
  int v340; // [rsp+218h] [rbp-EB0h]
  int *v341; // [rsp+228h] [rbp-EA0h]
  _OWORD pSecurityDescriptor[2]; // [rsp+230h] [rbp-E98h] BYREF
  __int64 v343; // [rsp+250h] [rbp-E78h]
  __int64 v344; // [rsp+260h] [rbp-E68h] BYREF
  int v345; // [rsp+268h] [rbp-E60h]
  int v346; // [rsp+26Ch] [rbp-E5Ch]
  int v347; // [rsp+270h] [rbp-E58h]
  int v348; // [rsp+278h] [rbp-E50h]
  int v349; // [rsp+27Ch] [rbp-E4Ch]
  __int64 v350; // [rsp+280h] [rbp-E48h]
  __int64 v351; // [rsp+288h] [rbp-E40h]
  __int64 v352; // [rsp+290h] [rbp-E38h]
  __int64 v353; // [rsp+2A0h] [rbp-E28h]
  int v354; // [rsp+2A8h] [rbp-E20h]
  int *v355; // [rsp+2B8h] [rbp-E10h]
  PACL v356; // [rsp+2C0h] [rbp-E08h]
  _BYTE v357[24]; // [rsp+2D0h] [rbp-DF8h] BYREF
  int v358; // [rsp+2E8h] [rbp-DE0h]
  int v359; // [rsp+2F0h] [rbp-DD8h]
  __int64 v360; // [rsp+2F8h] [rbp-DD0h]
  struct _DSNAME *QosPolicyDsName; // [rsp+380h] [rbp-D48h] BYREF
  char v362; // [rsp+388h] [rbp-D40h]
  int v363; // [rsp+394h] [rbp-D34h]
  _BYTE *v364; // [rsp+398h] [rbp-D30h]
  _QWORD *v365; // [rsp+3A0h] [rbp-D28h]
  __int64 ResObj; // [rsp+3A8h] [rbp-D20h]
  char v367[52]; // [rsp+3B0h] [rbp-D18h] BYREF
  int v368; // [rsp+3E4h] [rbp-CE4h]
  int v369; // [rsp+3F8h] [rbp-CD0h]
  _BYTE v370[16]; // [rsp+480h] [rbp-C48h] BYREF
  unsigned int v371; // [rsp+490h] [rbp-C38h]
  _BYTE v372[248]; // [rsp+498h] [rbp-C30h] BYREF
  _DWORD pOwner[4]; // [rsp+590h] [rbp-B38h] BYREF
  __int64 v374; // [rsp+5A0h] [rbp-B28h] BYREF
  char v375[72]; // [rsp+5A8h] [rbp-B20h] BYREF
  _DWORD *v377; // [rsp+640h] [rbp-A88h]
  _DWORD *v378; // [rsp+690h] [rbp-A38h]
  _DWORD *v379; // [rsp+6E0h] [rbp-9E8h]
  _DWORD *v380; // [rsp+730h] [rbp-998h]
  int v381; // [rsp+780h] [rbp-948h] BYREF
  char *v382; // [rsp+788h] [rbp-940h]
  int v383; // [rsp+7A0h] [rbp-928h]
  __int64 *v384; // [rsp+7A8h] [rbp-920h]
  __int64 v385; // [rsp+7B8h] [rbp-910h] BYREF
  int v386; // [rsp+7C0h] [rbp-908h]
  __int64 *v387; // [rsp+7C8h] [rbp-900h]
  __int64 v388; // [rsp+7D8h] [rbp-8F0h] BYREF
  int v389; // [rsp+7E0h] [rbp-8E8h]
  __int64 *v390; // [rsp+7E8h] [rbp-8E0h]
  __int64 v391; // [rsp+7F8h] [rbp-8D0h] BYREF
  int v392; // [rsp+9A0h] [rbp-728h] BYREF
  char *v393; // [rsp+9A8h] [rbp-720h]
  int v394; // [rsp+9C0h] [rbp-708h]
  __int64 *v395; // [rsp+9C8h] [rbp-700h]
  __int64 v396; // [rsp+9D8h] [rbp-6F0h] BYREF
  int v397; // [rsp+9E0h] [rbp-6E8h]
  __int64 *v398; // [rsp+9E8h] [rbp-6E0h]
  __int64 v399; // [rsp+9F8h] [rbp-6D0h] BYREF
  int v400; // [rsp+A00h] [rbp-6C8h]
  __int64 *v401; // [rsp+A08h] [rbp-6C0h]
  __int64 v402; // [rsp+A18h] [rbp-6B0h] BYREF
  int v403; // [rsp+BC0h] [rbp-508h] BYREF
  __int64 v404; // [rsp+BC8h] [rbp-500h]
  int v405; // [rsp+BE0h] [rbp-4E8h]
  __int64 *v406; // [rsp+BE8h] [rbp-4E0h]
  __int64 v407; // [rsp+BF8h] [rbp-4D0h] BYREF
  int v408; // [rsp+C00h] [rbp-4C8h]
  __int64 *v409; // [rsp+C08h] [rbp-4C0h]
  __int64 v410; // [rsp+C18h] [rbp-4B0h] BYREF
  int v411; // [rsp+C20h] [rbp-4A8h]
  __int64 *v412; // [rsp+C28h] [rbp-4A0h]
  __int64 v413; // [rsp+C38h] [rbp-490h] BYREF
  int v414; // [rsp+DE0h] [rbp-2E8h] BYREF
  char *v415; // [rsp+DE8h] [rbp-2E0h]
  int v416; // [rsp+E00h] [rbp-2C8h]
  __int64 *v417; // [rsp+E08h] [rbp-2C0h]
  __int64 v418; // [rsp+E18h] [rbp-2B0h] BYREF
  char v419[24]; // [rsp+1000h] [rbp-C8h] BYREF
  char v420[32]; // [rsp+1018h] [rbp-B0h] BYREF
  char v421[32]; // [rsp+1038h] [rbp-90h] BYREF
  char v422[32]; // [rsp+1058h] [rbp-70h] BYREF
  char v423[32]; // [rsp+1078h] [rbp-50h] BYREF

  v297 = a1;
  pAcl = (PACL)a1;
  v298[0] = 0;
  strcpy(v419, "msDS-LdapQosPolicy");
  strcpy(v422, "msDS-LdapQosPolicyTrigger");
  strcpy(v420, "msDS-LdapQosPolicyMaxCpu");
  strcpy(v421, "msDS-LdapQosPolicyTarget");
  strcpy(v423, "msDS-ReplicationQoSPolicy");
  memset_0(&QosPolicyDsName, 0, 0x100u);
  memset_0(v370, 0, 0x110u);
  memset_0(v357, 0, 0xB0u);
  v293 = 0;
  v374 = 0;
  memset_0(v375, 0, 0x1D8u);
  v300[0] = 6;
  v300[1] = &v374;
  v301 = 22092;
  v302 = 0;
  v303 = 0;
  v304 = 0;
  v305 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v343 = 0;
  dwBufferLength = 0;
  v2 = 1;
  pOwner[0] = 257;
  pOwner[1] = 83886080;
  pOwner[2] = 18;
  v3 = SCGetClassByName(a1, 18, v419);
  if ( !v3 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v5, v4)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v5, v4, v6, v7)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v10 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v5, v4, v8, v9)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v5, v4)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985512,
        2,
        4,
        v2,
        v10,
        53,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
        (__int64)v419);
    }
    return 87;
  }
  v374 = SCGetAttById(a1, 589826);
  if ( !v374 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v12, v11)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v12, v11, v13, v14)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v17 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v12, v11)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v12, v11, v15, v16)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v12, v11)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985518,
        2,
        4,
        v2,
        v17,
        54,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    }
    return 87;
  }
  if ( !SCGetAttById(a1, 131192) )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v19, v18)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v19, v18)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v19, v18, v20, v21)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v24 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v19, v18)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v19, v18, v22, v23)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v19, v18)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985524,
        2,
        4,
        v2,
        v24,
        55,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    }
    return 87;
  }
  v377 = (_DWORD *)SCGetAttByName(a1, 25, v422);
  if ( !v377 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v26, v25)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v26, v25)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v26, v25, v27, v28)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v31 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v26, v25)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v26, v25, v29, v30)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v26, v25)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985530,
        2,
        4,
        v2,
        v31,
        56,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
        (__int64)v422);
    }
    return 87;
  }
  v378 = (_DWORD *)SCGetAttByName(a1, 24, v420);
  if ( !v378 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v33, v32)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v33, v32, v34, v35)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v38 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v33, v32, v36, v37)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v33, v32)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985536,
        2,
        4,
        v2,
        v38,
        57,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
        (__int64)v420);
    }
    return 87;
  }
  v379 = (_DWORD *)SCGetAttByName(a1, 24, v421);
  if ( !v379 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v40, v39)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v40, v39, v41, v42)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v45 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v40, v39)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v40, v39, v43, v44)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v40, v39)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985542,
        2,
        4,
        v2,
        v45,
        58,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
        (__int64)v421);
    }
    return 87;
  }
  v380 = (_DWORD *)SCGetAttById(a1, 3);
  if ( !v380 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v47, v46)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v48, v49)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v52 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v47, v46)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v47, v46, v50, v51)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v47, v46)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985548,
        2,
        4,
        v2,
        v52,
        59,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    }
    return 87;
  }
  v53 = SCGetAttByName(a1, 25, v423);
  v54 = v53;
  if ( !v53 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v56, v55)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v56, v55, v57, v58)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v61 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v56, v55)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v56, v55, v59, v60)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( !(unsigned int)THStateCheckForTraceOverride(v56, v55)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985554,
        2,
        4,
        v2,
        v61,
        60,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    }
    return 87;
  }
  v357[8] = 73;
  v357[16] = 0;
  v358 = 0;
  v359 = 4;
  v360 = v3 + 20;
  QosPolicyDsName = GetQosPolicyDsName(a1);
  if ( !QosPolicyDsName )
    return 87;
  v362 = 1;
  v363 |= 1u;
  v365 = v300;
  v364 = v357;
  v368 = 589826;
  v369 = 2;
  InitCommarg(v367);
  v63 = *((_DWORD *)a1 + 1401);
  LODWORD(Size) = -__CFSHR__(v63, 12);
  LODWORD(v291) = Size;
  v64 = (_QWORD *)((char *)a1 + 5576);
  v296 = (_QWORD *)*((_QWORD *)a1 + 697);
  Src = v296;
  *((_DWORD *)a1 + 1401) = v63 | 0x800;
  *((_QWORD *)a1 + 697) = 0;
  DBOpen2(1, (char *)a1 + 5576);
  v286 = DBFindDSName(*((_QWORD *)a1 + 697), QosPolicyDsName);
  if ( v286 )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v66, v65)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v66, v65, v67, v68)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v71 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v66, v65)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v66, v65, v69, v70)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
      if ( (unsigned int)THStateCheckForTraceOverride(v66, v65)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) == 0, v72 = 0, !v179) )
      {
        v72 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985594,
        2,
        4,
        v72,
        v71,
        61,
        (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    }
    LastError = 1168;
    v286 = 1168;
    goto LABEL_278;
  }
  v293 = 0;
  v284 = 0;
  AttVal = dbGetAttVal(*v64, 1, v54, 0, 0, (__int64)&v284, (__int64)v298, (__int64)&v293);
  LastError = AttVal;
  v286 = AttVal;
  if ( AttVal )
  {
    if ( AttVal != 8995 )
    {
      v77 = 0;
      if ( !(unsigned int)IncrementWPPPerfCountersForLevel(3)
        && !(unsigned int)THStateCheckForTraceOverride(v76, v75)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 4)
        && (!gfTraceToSecondProvider
         || !(unsigned int)THStateCheckForTraceOverride(v76, v75)
         && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v76, v75, v78, v79)
          || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 4))) )
      {
        goto LABEL_279;
      }
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v76, v75)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v76, v75, v80, v81)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 4)) )
      {
        LODWORD(v77) = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v76, v75)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 4) == 0, v82 = 0, !v179) )
      {
        v82 = 1;
      }
      v83 = 65;
      v84 = 201985642;
      goto LABEL_277;
    }
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
      || (unsigned int)THStateCheckForTraceOverride(v86, v85)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v86, v85)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v86, v85, v87, v88)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
    {
      v91 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v86, v85)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v86, v85, v89, v90)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4));
      if ( (unsigned int)THStateCheckForTraceOverride(v86, v85)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4) == 0, v92 = 0, !v179) )
      {
        v92 = 1;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985631,
        5,
        4,
        v92,
        v91,
        64,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    }
    v293 = 0;
    gReplQosClassGUID = *(_OWORD *)&gNullGuid;
    v286 = 0;
  }
  else
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
      || (unsigned int)THStateCheckForTraceOverride(v94, v93)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v94, v93)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v94, v93, v95, v96)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
    {
      v97 = v293;
      v98 = 0;
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v94, v93)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v94, v93, v99, v100)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
      {
        v98 = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v94, v93)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4) == 0, v101 = 0, !v179) )
      {
        v101 = 1;
      }
      WPP_SF__DS_NAME_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985614,
        5,
        4,
        v101,
        v98,
        62,
        &WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
        v97);
    }
    LastError = DBFindDSName(*v64, v293);
    v286 = LastError;
    if ( LastError || (LastError = DBFillGuidAndSid(*v64, v293), (v286 = LastError) != 0) )
    {
      v77 = 0;
      if ( !(unsigned int)IncrementWPPPerfCountersForLevel(3)
        && !(unsigned int)THStateCheckForTraceOverride(v117, v116)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 4)
        && (!gfTraceToSecondProvider
         || !(unsigned int)THStateCheckForTraceOverride(v117, v116)
         && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v117, v116, v118, v119)
          || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 4))) )
      {
        goto LABEL_279;
      }
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v117, v116)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v117, v116, v120, v121)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 4)) )
      {
        LODWORD(v77) = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v117, v116)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 4) == 0, v82 = 0, !v179) )
      {
        v82 = 1;
      }
      v83 = 63;
      v84 = 201985623;
LABEL_277:
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v84,
        3,
        4,
        v82,
        v77,
        v83,
        (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
LABEL_278:
      v77 = 0;
      goto LABEL_279;
    }
  }
  v286 = DBFindDSName(*v64, QosPolicyDsName);
  if ( v286 )
  {
    v77 = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v103, v102)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v103, v102)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v103, v102, v104, v105)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v103, v102)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v103, v102, v106, v107)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
      {
        LODWORD(v77) = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v103, v102)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) == 0, v108 = 0, !v179) )
      {
        v108 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985649,
        2,
        4,
        v108,
        v77,
        66,
        (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
      v77 = 0;
    }
    LastError = 1168;
  }
  else
  {
    ResObj = CreateResObj(*v64, QosPolicyDsName);
    LastError = LocalSearch(a1, &QosPolicyDsName, v370, 0);
    v286 = LastError;
    v77 = 0;
    if ( !LastError )
      goto LABEL_279;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v110, v109)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v110, v109)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v110, v109, v111, v112)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v110, v109)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v110, v109, v113, v114)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
      {
        LODWORD(v77) = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v110, v109)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) == 0, v115 = 0, !v179) )
      {
        v115 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985660,
        2,
        4,
        v115,
        v77,
        67,
        (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
      v77 = 0;
    }
    LastError = 1359;
  }
  v286 = LastError;
LABEL_279:
  DBClose(*v64, 1);
  *v64 = v296;
  v123 = (unsigned int)((_DWORD)Size << 11);
  v124 = (int)v297;
  *((_DWORD *)v297 + 1401) = v123 ^ (*((_DWORD *)v297 + 1401) ^ ((_DWORD)Size << 11)) & 0xFFFFF7FF;
  if ( LastError )
    return LastError;
  v282 = 0;
  pAcl = 0;
  v283 = 0;
  v284 = 0;
  if ( (unsigned int)THStateCheckForTraceOverride(v123, v122)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v126, v125)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v126, v125, v127, v128)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
  {
    v129 = 0;
    if ( gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v126, v125)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v126, v125, v130, v131)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
    {
      v129 = 1;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v126, v125)
      || (v132 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 4), v133 = 0, v132) )
    {
      v133 = 1;
    }
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201985680,
      5,
      4,
      v133,
      v129,
      68,
      (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
    v124 = (int)v297;
  }
  AcquireSRWLockExclusive(&srwQosPolicyRecordLock);
  if ( !v371 )
  {
    v144 = v284;
    v134 = 0;
    goto LABEL_381;
  }
  pAcl = (PACL)THAlloc_(v124, 1, 1024, 1, 0, 201985687);
  v356 = pAcl;
  v134 = 0;
  if ( !InitializeAcl(pAcl, 0x400u, 4u) )
  {
    LastError = GetLastError();
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v136, v135)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v136, v135)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v136, v135, v137, v138)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v136, v135)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v136, v135, v139, v140)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
      {
        v134 = 1;
      }
      if ( !(unsigned int)THStateCheckForTraceOverride(v136, v135)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
      {
        v2 = 0;
      }
      v141 = 69;
      v142 = 201985691;
      goto LABEL_314;
    }
    goto LABEL_603;
  }
  v77 = DSAllocAux(48LL * v371, 201985695);
  v282 = (struct _QOS_POLICY_RECORD *)v77;
  if ( !v77 )
  {
    LastError = 14;
    goto LABEL_603;
  }
  v143 = v372;
  v296 = v372;
  v144 = v284;
  while ( v143 && v144 < v371 )
  {
    v288 = 0;
    v145 = v77 + 48LL * v144;
    v291 = v145;
    *(_DWORD *)(v145 + 16) = 100;
    *(_DWORD *)(v145 + 20) = 100;
    *(_OWORD *)v145 = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v143 + 4) + 16LL) + 8LL);
    v288 = 1;
    *(_QWORD *)(v145 + 32) = **(_QWORD **)(*(_QWORD *)(*((_QWORD *)v143 + 4) + 112LL) + 8LL);
    v146 = 2;
    v288 = 2;
    v147 = *((_QWORD *)v143 + 4);
    if ( *(_DWORD *)(v147 + 192) == *v377 )
    {
      v148 = *(_QWORD *)(v147 + 208);
      if ( v148 )
      {
        *(_DWORD *)(v145 + 16) = **(_DWORD **)(v148 + 8);
        v147 = *((_QWORD *)v143 + 4);
      }
      v146 = 3;
      v288 = 3;
    }
    v149 = 96LL * v146;
    if ( *(_DWORD *)(v149 + v147) == *v378 )
    {
      v150 = *(_QWORD *)(v149 + v147 + 16);
      if ( v150 )
      {
        *(_DWORD *)(v145 + 20) = **(_DWORD **)(v150 + 8);
        v147 = *((_QWORD *)v143 + 4);
      }
      v288 = ++v146;
    }
    v151 = 96LL * v146;
    Size = v151;
    if ( *(_DWORD *)(v151 + v147) == *v379 )
    {
      if ( *(_QWORD *)(v151 + v147 + 16) )
      {
        for ( i = 0; ; ++i )
        {
          v298[1] = i;
          v147 = *((_QWORD *)v143 + 4);
          if ( i >= *(_DWORD *)(v147 + v151 + 8) )
          {
            v145 = v291;
            goto LABEL_353;
          }
          if ( !AddAccessAllowedObjectAce(
                  pAcl,
                  4u,
                  0,
                  1u,
                  *(GUID **)(*(_QWORD *)(v147 + 16) + 8LL),
                  0,
                  *(PSID *)(*(_QWORD *)(v147 + v151 + 16) + 16LL * i + 8)) )
            break;
          v151 = Size;
          v143 = v296;
        }
        LastError = GetLastError();
        if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
          && !(unsigned int)THStateCheckForTraceOverride(v154, v153)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
          && (!gfTraceToSecondProvider
           || !(unsigned int)THStateCheckForTraceOverride(v154, v153)
           && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v154, v153, v155, v156)
            || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4))) )
        {
          goto LABEL_602;
        }
        v159 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v154, v153)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v154, v153, v157, v158)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
        if ( !(unsigned int)THStateCheckForTraceOverride(v154, v153)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
        {
          v2 = 0;
        }
        v160 = 70;
        v161 = 201985749;
        goto LABEL_350;
      }
LABEL_353:
      v288 = ++v146;
    }
    v162 = 96LL * v146;
    if ( *(_DWORD *)(v162 + v147) == *v380 )
    {
      v163 = *(unsigned int **)(v162 + v147 + 16);
      if ( v163 )
      {
        Src = (void *)*((_QWORD *)v163 + 1);
        Size = *v163;
        v164 = L"NTDS";
        if ( *(_DWORD *)gfADAM )
          v164 = gpszAdamServiceName;
        v165 = -1;
        do
          ++v165;
        while ( v164[v165] );
        v166 = ((unsigned int)Size >> 1) + v165 + 5;
        v167 = (void *)THAlloc_((_DWORD)v297, v166, 2, 1, 0, 201985766);
        *(_QWORD *)(v291 + 24) = v167;
        memcpy_0(v167, Src, Size);
        StringCchCatW(*(STRSAFE_LPWSTR *)(v291 + 24), v166, L" (");
        v168 = L"NTDS";
        if ( *(_DWORD *)gfADAM )
          v168 = gpszAdamServiceName;
        StringCchCatW(*(STRSAFE_LPWSTR *)(v291 + 24), v166, v168);
        v169 = v166;
        v145 = v291;
        StringCchCatW(*(STRSAFE_LPWSTR *)(v291 + 24), v169, L")");
        v288 = v146 + 1;
      }
    }
    v172 = 0;
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
      || (unsigned int)THStateCheckForTraceOverride(v171, v170)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v171, v170)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v171, v170, v173, v174)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
    {
      LODWORD(Size) = *(_DWORD *)(v145 + 20);
      LODWORD(v291) = *(_DWORD *)(v145 + 16);
      if ( gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v171, v170)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v171, v170, v175, v176)
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
      {
        v172 = 1;
      }
      if ( (unsigned int)THStateCheckForTraceOverride(v171, v170)
        || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4) == 0, v177 = 0, !v179) )
      {
        v177 = 1;
      }
      WPP_SF__guid_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201985781,
        5,
        4,
        v177,
        v172,
        71,
        (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
        v145);
    }
    v144 = v284 + 1;
    v284 = v144;
    v299 = v144;
    v143 = (_BYTE *)*v296;
    v296 = (_QWORD *)*v296;
    v77 = (__int64)v282;
    v134 = 0;
  }
LABEL_381:
  while ( 1 )
  {
    v287 = v134;
    if ( v134 >= gulQosPolicyRecordCount )
      break;
    v178 = 0;
    v290 = 0;
    while ( 1 )
    {
      v179 = v178 == v144;
      if ( v178 >= v144 )
        break;
      v180 = 48LL * v178;
      v181 = 48LL * v134;
      v182 = *(_QWORD *)((char *)gpQosPolicyRecords + v181) - *(_QWORD *)((char *)v282 + v180);
      if ( !v182 )
        v182 = *(_QWORD *)((char *)gpQosPolicyRecords + v181 + 8) - *(_QWORD *)((char *)v282 + v180 + 8);
      if ( !v182 )
      {
        if ( *(_QWORD *)((char *)gpQosPolicyRecords + v181 + 32) != *(_QWORD *)((char *)v282 + v180 + 32) )
        {
          v183 = 0;
          v285 = 0;
          v184 = *(_QWORD *)((char *)gpQosPolicyRecords + v181) - gReplQosClassGUID;
          if ( !v184 )
            v184 = *(_QWORD *)((char *)gpQosPolicyRecords + v181 + 8) - *((_QWORD *)&gReplQosClassGUID + 1);
          if ( !v184 )
            v183 = 1;
          v285 = v183;
          if ( gpDsEventConfig
            && (SHIDWORD(gpDsEventConfig[8].Internal) >= 3
             || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(3082, 3)
             || (unsigned int)DoLogMsgOverride(1073744800)) )
          {
            memset_0(&v306, 0, 0x60u);
            v306 = 0;
            Internal = gpDsEventConfig[8].Internal;
            v309 = 3;
            v307 = 1073744800;
            v310 = 0;
            v311 = 1;
            v317 = &v381;
            v381 = 8;
            v382 = (char *)v282 + v181;
            v306 = 1;
            v383 = 5;
            v385 = *(unsigned int *)((char *)v282 + v181 + 16);
            v384 = &v385;
            v306 = 2;
            v386 = 5;
            v388 = *(unsigned int *)((char *)v282 + v181 + 20);
            v387 = &v388;
            v389 = 16;
            v391 = v285;
            v390 = &v391;
            v306 = 4;
            v314 = 0;
            v313 = 3082;
            v312 = 1;
            v315 = 0;
            v316 = 0;
            DoLogEventAndTrace(&v306);
          }
          if ( (unsigned int)IncrementWPPPerfCountersForLevel(5)
            || (unsigned int)THStateCheckForTraceOverride(v186, v185)
            || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4)
            || gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v186, v185)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v186, v185, v187, v188)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
          {
            Src = (char *)gpQosPolicyRecords + v181;
            v189 = 0;
            if ( gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v186, v185)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v186, v185, v190, v191)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 5, 4)) )
            {
              v189 = 1;
            }
            if ( (unsigned int)THStateCheckForTraceOverride(v186, v185)
              || (v192 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 4), v193 = 0, v192) )
            {
              v193 = 1;
            }
            WPP_SF__guid_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              201985815,
              5,
              4,
              v193,
              v189,
              72,
              (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
              (__int64)Src);
          }
          if ( !(unsigned int)AtqUpdateQosClass((char *)v282 + 48 * v178, (char *)v282 + 48 * v178 + 16) )
          {
            LastError = GetLastError();
            goto LABEL_602;
          }
          v144 = v284;
        }
        v134 = v287;
        v179 = v178 == v144;
        break;
      }
      v290 = ++v178;
      v134 = v287;
    }
    if ( v179 )
    {
      v194 = 0;
      v285 = 0;
      v195 = (_QWORD *)((char *)gpQosPolicyRecords + 48 * v134);
      v196 = *v195 - gReplQosClassGUID;
      if ( *v195 == (_QWORD)gReplQosClassGUID )
        v196 = v195[1] - *((_QWORD *)&gReplQosClassGUID + 1);
      if ( !v196 )
      {
        v194 = 1;
        v285 = 1;
        gReplQosClassGUID = *(_OWORD *)&gNullGuid;
      }
      v197 = gpDsEventConfig;
      if ( !gpDsEventConfig )
        goto LABEL_431;
      if ( SHIDWORD(gpDsEventConfig[8].Internal) >= 3
        || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(3082, 3) )
      {
LABEL_429:
        memset_0(&v344, 0, 0x60u);
        v344 = 0;
        v346 = v197[8].Internal;
        v347 = 3;
        v345 = 1073744801;
        v348 = 0;
        v349 = 1;
        v355 = &v414;
        v414 = 8;
        v134 = v287;
        v415 = (char *)gpQosPolicyRecords + 48 * v287;
        v416 = 16;
        v418 = v194;
        v417 = &v418;
        v344 = 2;
        v352 = 0;
        v351 = 3082;
        v350 = 1;
        v353 = 0;
        v354 = 0;
        DoLogEventAndTrace(&v344);
      }
      else
      {
        if ( (unsigned int)DoLogMsgOverride(1073744801) )
        {
          v197 = gpDsEventConfig;
          goto LABEL_429;
        }
LABEL_431:
        v134 = v287;
      }
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(5) )
        goto LABEL_439;
      v201 = THStateCheckForTraceOverride(v199, v198);
      LODWORD(v200) = 0;
      if ( v201
        || (v202 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 4), v200 = 0, v202)
        || gfTraceToSecondProvider
        && ((v205 = THStateCheckForTraceOverride(v203, v198), LODWORD(v200) = 0, v205)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier(v206, v198, v207, 0)
         && (v208 = CheckWPPLevelFlagsEnabledForProvider(1, 5, 4), v200 = 0, v208)) )
      {
LABEL_439:
        v209 = 48LL * v134;
        Src = (char *)gpQosPolicyRecords + v209;
        if ( gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v209, v198)
           || (v212 = ThStateCheckIfTraceToSecondProvier(v209, v198, v210, v211), LODWORD(v200) = 0, v212)
           && (v213 = CheckWPPLevelFlagsEnabledForProvider(1, 5, 4), LODWORD(v200) = 0, v213)) )
        {
          LODWORD(Size) = 1;
        }
        else
        {
          LODWORD(Size) = v200;
        }
        if ( (unsigned int)THStateCheckForTraceOverride(v209, v198)
          || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4) == 0, v214 = 0, !v179) )
        {
          v214 = 1;
        }
        WPP_SF__guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          201985846,
          5,
          4,
          v214,
          Size,
          73,
          (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
          (__int64)Src);
      }
      AtqCloseQosClass((char *)gpQosPolicyRecords + 48 * v134, v198, v204, v200);
      v144 = v284;
    }
    ++v134;
  }
  v215 = 0;
  v290 = 0;
  v77 = (__int64)v282;
  while ( 1 )
  {
    if ( v215 >= v144 )
    {
      if ( v293 )
      {
        v247 = gReplQosClassGUID - *(_QWORD *)(v293 + 8);
        if ( (_QWORD)gReplQosClassGUID == *(_QWORD *)(v293 + 8) )
          v247 = *((_QWORD *)&gReplQosClassGUID + 1) - *(_QWORD *)(v293 + 16);
        if ( v247 )
        {
          v248 = *(__m128i *)(v293 + 8);
          gReplQosClassGUID = (__int128)v248;
          v249 = 0;
          v290 = 0;
          v250 = _mm_srli_si128(v248, 8).m128i_u64[0];
          while ( v249 < v144 )
          {
            v251 = 48LL * v249 + v77;
            v252 = v248.m128i_i64[0] - *(_QWORD *)v251;
            if ( v248.m128i_i64[0] == *(_QWORD *)v251 )
              v252 = v250 - *(_QWORD *)(v251 + 8);
            if ( !v252 )
            {
              v253 = gpDsEventConfig;
              if ( !gpDsEventConfig )
                break;
              if ( SHIDWORD(gpDsEventConfig[8].Internal) < 3
                && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(3082, 3)) )
              {
                if ( !(unsigned int)DoLogMsgOverride(1073744800) )
                  break;
                v253 = gpDsEventConfig;
              }
              memset_0(&v330, 0, 0x60u);
              v330 = 0;
              v332 = v253[8].Internal;
              v333 = 3;
              v331 = 1073744800;
              v334 = 0;
              v335 = 1;
              v341 = &v403;
              v403 = 8;
              v404 = v251;
              v330 = 1;
              v405 = 5;
              v407 = *(unsigned int *)(v251 + 16);
              v406 = &v407;
              v330 = 2;
              v408 = 5;
              v410 = *(unsigned int *)(v251 + 20);
              v409 = &v410;
              v411 = 16;
              v413 = 1;
              v412 = &v413;
              v330 = 4;
              v338 = 0;
              v337 = 3082;
              v336 = 1;
              v339 = 0;
              v340 = 0;
              DoLogEventAndTrace(&v330);
              break;
            }
            v290 = ++v249;
            v77 = (__int64)v282;
          }
        }
      }
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        LastError = GetLastError();
        if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
          && !(unsigned int)THStateCheckForTraceOverride(v255, v254)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
          && (!gfTraceToSecondProvider
           || !(unsigned int)THStateCheckForTraceOverride(v255, v254)
           && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v255, v254, v256, v257)
            || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4))) )
        {
          goto LABEL_602;
        }
        v159 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v255, v254)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v255, v254, v258, v259)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
        if ( !(unsigned int)THStateCheckForTraceOverride(v255, v254)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
        {
          v2 = 0;
        }
        v160 = 76;
        v161 = 201985915;
LABEL_350:
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v161,
          2,
          4,
          v2,
          v159,
          v160,
          (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
LABEL_602:
        v77 = (__int64)v282;
        goto LABEL_603;
      }
      if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 1) )
      {
        LastError = GetLastError();
        if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
          && !(unsigned int)THStateCheckForTraceOverride(v261, v260)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
          && (!gfTraceToSecondProvider
           || !(unsigned int)THStateCheckForTraceOverride(v261, v260)
           && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v261, v260, v262, v263)
            || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4))) )
        {
          goto LABEL_602;
        }
        v159 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v261, v260)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v261, v260, v264, v265)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
        if ( !(unsigned int)THStateCheckForTraceOverride(v261, v260)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
        {
          v2 = 0;
        }
        v160 = 77;
        v161 = 201985922;
        goto LABEL_350;
      }
      if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pAcl, 0) )
      {
        LastError = GetLastError();
        if ( !(unsigned int)IncrementWPPPerfCountersForLevel(2)
          && !(unsigned int)THStateCheckForTraceOverride(v267, v266)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
          && (!gfTraceToSecondProvider
           || !(unsigned int)THStateCheckForTraceOverride(v267, v266)
           && (!(unsigned int)ThStateCheckIfTraceToSecondProvier(v267, v266, v268, v269)
            || !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4))) )
        {
          goto LABEL_602;
        }
        v159 = gfTraceToSecondProvider
            && ((unsigned int)THStateCheckForTraceOverride(v267, v266)
             || (unsigned int)ThStateCheckIfTraceToSecondProvier(v267, v266, v270, v271)
             && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
        if ( !(unsigned int)THStateCheckForTraceOverride(v267, v266)
          && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
        {
          v2 = 0;
        }
        v160 = 78;
        v161 = 201985929;
        goto LABEL_350;
      }
      MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
      v272 = (void *)DSAllocAux(dwBufferLength, 201985940);
      v273 = v272;
      v283 = v272;
      if ( v272 )
      {
        if ( MakeSelfRelativeSD(pSecurityDescriptor, v272, &dwBufferLength) )
        {
          DSFreeAux(*(_QWORD *)&gpQosPolicySd, 201985954);
          *(_QWORD *)&gpQosPolicySd = v273;
          v273 = 0;
          v280 = gulQosPolicyRecordCount;
          gulQosPolicyRecordCount = v284;
          v299 = v280;
          v281 = gpQosPolicyRecords;
          gpQosPolicyRecords = v282;
          v77 = (__int64)v281;
          goto LABEL_604;
        }
        LastError = GetLastError();
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v275, v274)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v275, v274)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier(v275, v274, v276, v277)
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
        {
          v159 = gfTraceToSecondProvider
              && ((unsigned int)THStateCheckForTraceOverride(v275, v274)
               || (unsigned int)ThStateCheckIfTraceToSecondProvier(v275, v274, v278, v279)
               && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4));
          if ( !(unsigned int)THStateCheckForTraceOverride(v275, v274)
            && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
          {
            v2 = 0;
          }
          v160 = 79;
          v161 = 201985949;
          goto LABEL_350;
        }
      }
      else
      {
        LastError = 14;
      }
      v77 = (__int64)v282;
      goto LABEL_604;
    }
    v216 = 0;
    v217 = v215;
    while ( 1 )
    {
      v287 = v216;
      v218 = v216 == gulQosPolicyRecordCount;
      if ( v216 >= gulQosPolicyRecordCount )
        break;
      v217 = v215;
      v219 = 48LL * v215;
      v220 = (_QWORD *)((char *)gpQosPolicyRecords + 48 * v216);
      v221 = *v220 - *(_QWORD *)(v219 + v77);
      if ( *v220 == *(_QWORD *)(v219 + v77) )
        v221 = v220[1] - *(_QWORD *)(v219 + v77 + 8);
      if ( !v221 )
      {
        v218 = v216 == gulQosPolicyRecordCount;
        break;
      }
      ++v216;
    }
    if ( v218 )
      break;
LABEL_508:
    v290 = ++v215;
  }
  v285 = 0;
  if ( v293 )
  {
    v222 = *(_QWORD *)(v77 + 48 * v217) - *(_QWORD *)(v293 + 8);
    if ( !v222 )
      v222 = *(_QWORD *)(v77 + 48 * v217 + 8) - *(_QWORD *)(v293 + 16);
    if ( !v222 )
    {
      v285 = 1;
      gReplQosClassGUID = *(_OWORD *)(v293 + 8);
    }
  }
  v223 = gpDsEventConfig;
  if ( gpDsEventConfig )
  {
    if ( SHIDWORD(gpDsEventConfig[8].Internal) >= 3
      || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(3082, 3) )
    {
LABEL_472:
      memset_0(&v318, 0, 0x60u);
      v318 = 0;
      v320 = v223[8].Internal;
      v321 = 3;
      v319 = 1073744799;
      v322 = 0;
      v323 = 1;
      v329 = &v392;
      v392 = 8;
      v393 = (char *)v282 + 48 * v215;
      v318 = 1;
      v394 = 5;
      v396 = *((unsigned int *)v393 + 4);
      v395 = &v396;
      v318 = 2;
      v397 = 5;
      v399 = *((unsigned int *)v393 + 5);
      v398 = &v399;
      v400 = 16;
      v402 = v285;
      v401 = &v402;
      v318 = 4;
      v326 = 0;
      v325 = 3082;
      v324 = 1;
      v327 = 0;
      v328 = 0;
      DoLogEventAndTrace(&v318);
    }
    else if ( (unsigned int)DoLogMsgOverride(1073744799) )
    {
      v223 = gpDsEventConfig;
      goto LABEL_472;
    }
  }
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(5) )
    goto LABEL_480;
  v227 = THStateCheckForTraceOverride(v225, v224);
  v226 = 0;
  if ( v227
    || (v228 = CheckWPPLevelFlagsEnabledForProvider(0, 5, 4), v226 = 0, v228)
    || gfTraceToSecondProvider
    && ((v230 = THStateCheckForTraceOverride(v229, v224), v226 = 0, v230)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v231, v224, v232, v233)
     && (v234 = CheckWPPLevelFlagsEnabledForProvider(1, 5, 4), v226 = 0, v234)) )
  {
LABEL_480:
    v235 = 48LL * v215;
    Src = (char *)v282 + v235;
    if ( gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v235, v224)
       || (v238 = ThStateCheckIfTraceToSecondProvier(v235, v224, v236, v237), v226 = 0, v238)
       && (v239 = CheckWPPLevelFlagsEnabledForProvider(1, 5, 4), v226 = 0, v239)) )
    {
      LODWORD(Size) = 1;
    }
    else
    {
      LODWORD(Size) = v226;
    }
    if ( (unsigned int)THStateCheckForTraceOverride(v235, v224)
      || (v179 = (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 5, 4) == 0, v240 = 0, !v179) )
    {
      v240 = 1;
    }
    WPP_SF__guid_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201985882,
      5,
      4,
      v240,
      Size,
      74,
      (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids,
      (__int64)Src);
  }
  v77 = (__int64)v282;
  if ( (unsigned int)AtqCreateQosClass((char *)v282 + 48 * v215, (char *)v282 + 48 * v215 + 16) )
  {
    v144 = v284;
    goto LABEL_508;
  }
  LastError = GetLastError();
  v134 = 0;
  if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
    || (unsigned int)THStateCheckForTraceOverride(v242, v241)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v242, v241)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v242, v241, v243, v244)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
  {
    if ( gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v242, v241)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v242, v241, v245, v246)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 4)) )
    {
      v134 = 1;
    }
    if ( !(unsigned int)THStateCheckForTraceOverride(v242, v241)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 4) )
    {
      v2 = 0;
    }
    v141 = 75;
    v142 = 201985885;
LABEL_314:
    WPP_SF__ATTRTYP_LOG_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v142,
      2,
      4,
      v2,
      v134,
      v141,
      (__int64)&WPP_a5a644baa346369d746d9aa64496ba03_Traceguids);
  }
LABEL_603:
  v273 = v283;
LABEL_604:
  ReleaseSRWLockExclusive(&srwQosPolicyRecordLock);
  if ( v77 )
    DSFreeAux(v77, 201985972);
  if ( v273 )
    DSFreeAux(v273, 201985976);
  if ( !LastError )
    return RefreshDefaultQosPolicy(v297);
  return LastError;
}

```

## disassembly

```asm
0x18034b574  mov     [rsp+arg_8], rbx
0x18034b579  mov     [rsp+arg_10], rsi
0x18034b57e  push    rdi
0x18034b57f  push    r12
0x18034b581  push    r13
0x18034b583  push    r14
0x18034b585  push    r15
0x18034b587  mov     eax, 10A0h
0x18034b58c  call    _alloca_probe
0x18034b591  sub     rsp, rax
0x18034b594  mov     rax, cs:__security_cookie
0x18034b59b  xor     rax, rsp
0x18034b59e  mov     [rsp+10C8h+var_30], rax
0x18034b5a6  mov     r13, rcx
0x18034b5a9  mov     [rsp+10C8h+var_1000], rcx
0x18034b5b1  mov     [rsp+10C8h+pAcl], rcx
0x18034b5b9  xor     r15d, r15d
0x18034b5bc  mov     [rsp+10C8h+var_FF8], r15d
0x18034b5c4  movups  xmm0, xmmword ptr cs:aMsdsLdapqospol; "msDS-LdapQosPolicy"
0x18034b5cb  movups  xmmword ptr [rsp+10C8h+var_C8], xmm0
0x18034b5d3  mov     eax, dword ptr cs:aMsdsLdapqospol+0Fh; "icy"
0x18034b5d9  mov     dword ptr [rsp+10C8h+var_C8+0Fh], eax
0x18034b5e0  movups  xmm0, xmmword ptr cs:aMsdsLdapqospol_1; "msDS-LdapQosPolicyTrigger"
0x18034b5e7  movups  xmmword ptr [rsp+10C8h+var_70], xmm0
0x18034b5ef  movups  xmm1, xmmword ptr cs:aMsdsLdapqospol_1+0Ah; "osPolicyTrigger"
0x18034b5f6  movups  xmmword ptr [rsp+10C8h+var_70+0Ah], xmm1
0x18034b5fe  movups  xmm0, xmmword ptr cs:aMsdsLdapqospol_3; "msDS-LdapQosPolicyMaxCpu"
0x18034b605  movups  xmmword ptr [rsp+10C8h+var_B0], xmm0
0x18034b60d  movups  xmm1, xmmword ptr cs:aMsdsLdapqospol_3+9; "QosPolicyMaxCpu"
0x18034b614  movups  xmmword ptr [rsp+10C8h+var_B0+9], xmm1
0x18034b61c  movups  xmm0, xmmword ptr cs:aMsdsLdapqospol_0; "msDS-LdapQosPolicyTarget"
0x18034b623  movups  xmmword ptr [rsp+10C8h+var_90], xmm0
0x18034b62b  movups  xmm1, xmmword ptr cs:aMsdsLdapqospol_0+9; "QosPolicyTarget"
0x18034b632  movups  xmmword ptr [rsp+10C8h+var_90+9], xmm1
0x18034b63a  movups  xmm0, xmmword ptr cs:aMsdsReplicatio; "msDS-ReplicationQoSPolicy"
0x18034b641  movups  xmmword ptr [rsp+10C8h+var_50], xmm0
0x18034b649  movups  xmm1, xmmword ptr cs:aMsdsReplicatio+0Ah; "cationQoSPolicy"
0x18034b650  movups  xmmword ptr [rsp+10C8h+var_50+0Ah], xmm1
0x18034b658  xor     edx, edx; Val
0x18034b65a  mov     r8d, 100h; Size
0x18034b660  lea     rcx, [rsp+10C8h+var_D48]; void *
0x18034b668  call    memset_0
0x18034b66d  xor     edx, edx; Val
0x18034b66f  mov     r8d, 110h; Size
0x18034b675  lea     rcx, [rsp+10C8h+var_C48]; void *
0x18034b67d  call    memset_0
0x18034b682  xor     edx, edx; Val
0x18034b684  mov     r8d, 0B0h; Size
0x18034b68a  lea     rcx, [rsp+10C8h+var_DF8]; void *
0x18034b692  call    memset_0
0x18034b697  mov     [rsp+10C8h+var_1020], r15
0x18034b69f  mov     [rsp+10C8h+var_B28], r15
0x18034b6a7  xor     edx, edx; Val
0x18034b6a9  mov     r8d, 1D8h; Size
0x18034b6af  lea     rcx, [rsp+10C8h+var_B20]; void *
0x18034b6b7  call    memset_0
0x18034b6bc  mov     [rsp+10C8h+var_FE8], 6
0x18034b6c8  lea     rax, [rsp+10C8h+var_B28]
0x18034b6d0  mov     [rsp+10C8h+var_FE0], rax
0x18034b6d8  mov     [rsp+10C8h+var_FD8], 564Ch
0x18034b6e2  xor     eax, eax
0x18034b6e4  mov     [rsp+10C8h+var_FD6], eax
0x18034b6eb  mov     [rsp+10C8h+var_FD2], ax
0x18034b6f3  mov     [rsp+10C8h+var_FD0], r15
0x18034b6fb  xorps   xmm0, xmm0
0x18034b6fe  movups  [rsp+10C8h+var_FC8], xmm0
0x18034b706  xorps   xmm1, xmm1
0x18034b709  movups  [rsp+10C8h+pSecurityDescriptor], xmm1
0x18034b711  movups  [rsp+10C8h+var_E88], xmm1
0x18034b719  mov     [rsp+10C8h+var_E78], rax
0x18034b721  mov     [rsp+10C8h+dwBufferLength], r15d
0x18034b729  lea     esi, [rax+1]
0x18034b72c  mov     [rsp+10C8h+pOwner], 101h
0x18034b737  mov     [rsp+10C8h+var_B34], 5000000h
0x18034b742  lea     edx, [rax+12h]
0x18034b745  mov     [rsp+10C8h+var_B30], edx
0x18034b74c  lea     r8, [rsp+10C8h+var_C8]
0x18034b754  mov     rcx, r13
0x18034b757  call    SCGetClassByName
0x18034b75c  mov     rbx, rax
0x18034b75f  test    rax, rax
0x18034b762  jnz     loc_18034B850
0x18034b768  lea     r14d, [r15+2]
0x18034b76c  mov     ecx, r14d
0x18034b76f  call    IncrementWPPPerfCountersForLevel
0x18034b774  test    eax, eax
0x18034b776  jnz     short loc_18034B7D0
0x18034b778  call    THStateCheckForTraceOverride
0x18034b77d  test    eax, eax
0x18034b77f  jnz     short loc_18034B7D0
0x18034b781  lea     edi, [rsi+3]
0x18034b784  mov     r8d, edi
0x18034b787  mov     edx, r14d
0x18034b78a  xor     ecx, ecx
0x18034b78c  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b791  test    eax, eax
0x18034b793  jnz     short loc_18034B7D5
0x18034b795  mov     eax, cs:gfTraceToSecondProvider
0x18034b79b  test    eax, eax
0x18034b79d  jz      loc_18034BFE1
0x18034b7a3  call    THStateCheckForTraceOverride
0x18034b7a8  test    eax, eax
0x18034b7aa  jnz     short loc_18034B7D5
0x18034b7ac  call    ThStateCheckIfTraceToSecondProvier
0x18034b7b1  test    eax, eax
0x18034b7b3  jz      loc_18034BFE1
0x18034b7b9  mov     r8d, edi
0x18034b7bc  mov     edx, r14d
0x18034b7bf  mov     ecx, esi
0x18034b7c1  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b7c6  test    eax, eax
0x18034b7c8  jz      loc_18034BFE1
0x18034b7ce  jmp     short loc_18034B7D5
0x18034b7d0  mov     edi, 4
0x18034b7d5  mov     eax, cs:gfTraceToSecondProvider
0x18034b7db  test    eax, eax
0x18034b7dd  jz      short loc_18034B806
0x18034b7df  call    THStateCheckForTraceOverride
0x18034b7e4  test    eax, eax
0x18034b7e6  jnz     short loc_18034B802
0x18034b7e8  call    ThStateCheckIfTraceToSecondProvier
0x18034b7ed  test    eax, eax
0x18034b7ef  jz      short loc_18034B806
0x18034b7f1  mov     r8d, edi
0x18034b7f4  mov     edx, r14d
0x18034b7f7  mov     ecx, esi
0x18034b7f9  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b7fe  test    eax, eax
0x18034b800  jz      short loc_18034B806
0x18034b802  mov     ebx, esi
0x18034b804  jmp     short loc_18034B809
0x18034b806  mov     ebx, r15d
0x18034b809  call    THStateCheckForTraceOverride
0x18034b80e  test    eax, eax
0x18034b810  jnz     short loc_18034B826
0x18034b812  mov     r8d, edi
0x18034b815  mov     edx, r14d
0x18034b818  xor     ecx, ecx
0x18034b81a  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b81f  test    eax, eax
0x18034b821  jnz     short loc_18034B826
0x18034b823  mov     esi, r15d
0x18034b826  lea     rax, [rsp+10C8h+var_C8]
0x18034b82e  mov     [rsp+10C8h+var_1088], rax
0x18034b833  lea     r12, WPP_a5a644baa346369d746d9aa64496ba03_Traceguids
0x18034b83a  mov     [rsp+10C8h+var_1090], r12
0x18034b83f  mov     word ptr [rsp+10C8h+pSid], 35h ; '5'
0x18034b846  mov     edx, 0C0A0DE8h
0x18034b84b  jmp     loc_18034BD6B
0x18034b850  mov     edx, 90002h
0x18034b855  mov     rcx, r13
0x18034b858  call    SCGetAttById
0x18034b85d  mov     [rsp+10C8h+var_B28], rax
0x18034b865  test    rax, rax
0x18034b868  jnz     loc_18034B949
0x18034b86e  lea     r14d, [rax+2]
0x18034b872  mov     ecx, r14d
0x18034b875  call    IncrementWPPPerfCountersForLevel
0x18034b87a  test    eax, eax
0x18034b87c  jnz     short loc_18034B8D6
0x18034b87e  call    THStateCheckForTraceOverride
0x18034b883  test    eax, eax
0x18034b885  jnz     short loc_18034B8D6
0x18034b887  lea     edi, [rax+4]
0x18034b88a  mov     r8d, edi
0x18034b88d  mov     edx, r14d
0x18034b890  xor     ecx, ecx
0x18034b892  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b897  test    eax, eax
0x18034b899  jnz     short loc_18034B8DB
0x18034b89b  mov     eax, cs:gfTraceToSecondProvider
0x18034b8a1  test    eax, eax
0x18034b8a3  jz      loc_18034BFE1
0x18034b8a9  call    THStateCheckForTraceOverride
0x18034b8ae  test    eax, eax
0x18034b8b0  jnz     short loc_18034B8DB
0x18034b8b2  call    ThStateCheckIfTraceToSecondProvier
0x18034b8b7  test    eax, eax
0x18034b8b9  jz      loc_18034BFE1
0x18034b8bf  mov     r8d, edi
0x18034b8c2  mov     edx, r14d
0x18034b8c5  mov     ecx, esi
0x18034b8c7  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b8cc  test    eax, eax
0x18034b8ce  jz      loc_18034BFE1
0x18034b8d4  jmp     short loc_18034B8DB
0x18034b8d6  mov     edi, 4
0x18034b8db  mov     eax, cs:gfTraceToSecondProvider
0x18034b8e1  test    eax, eax
0x18034b8e3  jz      short loc_18034B90C
0x18034b8e5  call    THStateCheckForTraceOverride
0x18034b8ea  test    eax, eax
0x18034b8ec  jnz     short loc_18034B908
0x18034b8ee  call    ThStateCheckIfTraceToSecondProvier
0x18034b8f3  test    eax, eax
0x18034b8f5  jz      short loc_18034B90C
0x18034b8f7  mov     r8d, edi
0x18034b8fa  mov     edx, r14d
0x18034b8fd  mov     ecx, esi
0x18034b8ff  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b904  test    eax, eax
0x18034b906  jz      short loc_18034B90C
0x18034b908  mov     ebx, esi
0x18034b90a  jmp     short loc_18034B90F
0x18034b90c  mov     ebx, r15d
0x18034b90f  call    THStateCheckForTraceOverride
0x18034b914  test    eax, eax
0x18034b916  jnz     short loc_18034B92C
0x18034b918  mov     r8d, edi
0x18034b91b  mov     edx, r14d
0x18034b91e  xor     ecx, ecx
0x18034b920  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b925  test    eax, eax
0x18034b927  jnz     short loc_18034B92C
0x18034b929  mov     esi, r15d
0x18034b92c  lea     r12, WPP_a5a644baa346369d746d9aa64496ba03_Traceguids
0x18034b933  mov     [rsp+10C8h+var_1090], r12
0x18034b938  mov     word ptr [rsp+10C8h+pSid], 36h ; '6'
0x18034b93f  mov     edx, 0C0A0DEEh
0x18034b944  jmp     loc_18034BF7C
0x18034b949  mov     edx, 20078h
0x18034b94e  mov     rcx, r13
0x18034b951  call    SCGetAttById
0x18034b956  mov     [rsp+10C8h+var_AD8], rax
0x18034b95e  test    rax, rax
0x18034b961  jnz     loc_18034BA42
0x18034b967  lea     r14d, [rax+2]
0x18034b96b  mov     ecx, r14d
0x18034b96e  call    IncrementWPPPerfCountersForLevel
0x18034b973  test    eax, eax
0x18034b975  jnz     short loc_18034B9CF
0x18034b977  call    THStateCheckForTraceOverride
0x18034b97c  test    eax, eax
0x18034b97e  jnz     short loc_18034B9CF
0x18034b980  lea     edi, [rax+4]
0x18034b983  mov     r8d, edi
0x18034b986  mov     edx, r14d
0x18034b989  xor     ecx, ecx
0x18034b98b  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b990  test    eax, eax
0x18034b992  jnz     short loc_18034B9D4
0x18034b994  mov     eax, cs:gfTraceToSecondProvider
0x18034b99a  test    eax, eax
0x18034b99c  jz      loc_18034BFE1
0x18034b9a2  call    THStateCheckForTraceOverride
0x18034b9a7  test    eax, eax
0x18034b9a9  jnz     short loc_18034B9D4
0x18034b9ab  call    ThStateCheckIfTraceToSecondProvier
0x18034b9b0  test    eax, eax
0x18034b9b2  jz      loc_18034BFE1
0x18034b9b8  mov     r8d, edi
0x18034b9bb  mov     edx, r14d
0x18034b9be  mov     ecx, esi
0x18034b9c0  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b9c5  test    eax, eax
0x18034b9c7  jz      loc_18034BFE1
0x18034b9cd  jmp     short loc_18034B9D4
0x18034b9cf  mov     edi, 4
0x18034b9d4  mov     eax, cs:gfTraceToSecondProvider
0x18034b9da  test    eax, eax
0x18034b9dc  jz      short loc_18034BA05
0x18034b9de  call    THStateCheckForTraceOverride
0x18034b9e3  test    eax, eax
0x18034b9e5  jnz     short loc_18034BA01
0x18034b9e7  call    ThStateCheckIfTraceToSecondProvier
0x18034b9ec  test    eax, eax
0x18034b9ee  jz      short loc_18034BA05
0x18034b9f0  mov     r8d, edi
0x18034b9f3  mov     edx, r14d
0x18034b9f6  mov     ecx, esi
0x18034b9f8  call    CheckWPPLevelFlagsEnabledForProvider
0x18034b9fd  test    eax, eax
0x18034b9ff  jz      short loc_18034BA05
0x18034ba01  mov     ebx, esi
0x18034ba03  jmp     short loc_18034BA08
0x18034ba05  mov     ebx, r15d
0x18034ba08  call    THStateCheckForTraceOverride
0x18034ba0d  test    eax, eax
0x18034ba0f  jnz     short loc_18034BA25
0x18034ba11  mov     r8d, edi
0x18034ba14  mov     edx, r14d
0x18034ba17  xor     ecx, ecx
0x18034ba19  call    CheckWPPLevelFlagsEnabledForProvider
0x18034ba1e  test    eax, eax
0x18034ba20  jnz     short loc_18034BA25
0x18034ba22  mov     esi, r15d
0x18034ba25  lea     r12, WPP_a5a644baa346369d746d9aa64496ba03_Traceguids
0x18034ba2c  mov     [rsp+10C8h+var_1090], r12
0x18034ba31  mov     word ptr [rsp+10C8h+pSid], 37h ; '7'
0x18034ba38  mov     edx, 0C0A0DF4h
0x18034ba3d  jmp     loc_18034BF7C
0x18034ba42  lea     r8, [rsp+10C8h+var_70]
0x18034ba4a  mov     r14d, 19h
0x18034ba50  mov     edx, r14d
0x18034ba53  mov     rcx, r13
0x18034ba56  call    SCGetAttByName
0x18034ba5b  mov     [rsp+10C8h+var_A88], rax
0x18034ba63  test    rax, rax
0x18034ba66  jnz     loc_18034BB54
0x18034ba6c  lea     r14d, [rax+2]
  ... truncated ...
```
