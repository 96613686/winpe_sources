# FrsReplicator::BringContentSetOnline(FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &,_GUID const &)

- ea: `0x1400e8e1c`
- end: `0x1400ea7ae`
- name: `?BringContentSetOnline@FrsReplicator@@QEAAXAEBV?$FrsStringImpl@GD@@AEBU_GUID@@11@Z`
- size: `6546`
- prototype: ``
- caller_count: `2`
- callee_count: `66`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14002018c`
- `0x140039910`

## callees

- `0x1400036a0`
- `0x14000daa0`
- `0x14000dd10`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x14001c480`
- `0x14001cfa0`
- `0x14001e408`
- `0x1400217d0`
- `0x140022ce4`
- `0x140022d1c`
- `0x1400249f4`
- `0x14002c2f4`
- `0x1400370bc`
- `0x1400391c4`
- `0x14003af50`
- `0x14003df48`
- `0x14003e0ac`
- `0x14003f2b0`
- `0x14003f2f4`
- `0x14003f338`
- `0x140040a18`
- `0x140044f3c`
- `0x140044fc4`
- `0x14004509c`
- `0x140047e14`
- `0x140047e4c`
- `0x140050eb8`
- `0x140052594`
- `0x140058128`
- `0x1400595e4`
- `0x1400e60c0`
- `0x1400e61a0`
- `0x1400e625c`
- `0x1400e6338`
- `0x1400e6408`
- `0x1400e65ac`
- `0x1400e6740`
- `0x1400e6818`
- `0x1400e68f8`
- `0x1400e6a78`
- `0x1400e6b78`
- `0x1400e7f10`
- `0x1400e839c`
- `0x1400e8e1c`
- `0x1400ead04`
- `0x1400ec084`
- `0x1400ec26c`
- `0x1400ed320`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400e8fd0`
- `KERNEL32!GetCurrentThreadId` at `0x1400e94f0`
- `KERNEL32!GetCurrentThreadId` at `0x1400e95c2`
- `KERNEL32!GetCurrentThreadId` at `0x1400e967c`
- `KERNEL32!GetCurrentThreadId` at `0x1400e8fd0`
- `KERNEL32!GetCurrentThreadId` at `0x1400e94f0`
- `KERNEL32!GetCurrentThreadId` at `0x1400e95c2`
- `KERNEL32!GetCurrentThreadId` at `0x1400e967c`

## string_xrefs

- `0x1400e8f27`: `[CLUSTER] Bringing content set online. resName:%? csId:%? rgId:%? volId:%?`
- `0x1400e8f9f`: `[CLUSTER] Volume ID Table does not contain a mapping for the specified volume. Rebuilding the Volume ID Table. resName:%? csId:%? volId:%?`
- `0x1400e9088`: `[CLUSTER] Removing stale configurations from g_ConfigContext. resName:%? csId:%? rgId:%? volId:%?`
- `0x1400e918b`: `[CLUSTER] Failed to bring the content set online. Unable to retrieve configuration of the content set's replica set. resName:%? csId:%? rgId:%?`
- `0x1400e90fc`: `[CLUSTER] Retrieving configuration of the content set's replica set. resName:%? csId:%? rgId:%?`
- `0x1400e9254`: `[CLUSTER] Retrieved replica set configuration from g_ConfigContext resName:%? csId:%? rgId:%?`
- `0x1400e91fa`: `[CLUSTER] Retrieved replica set configuration from XML file. resName:%? csId:%? rgId:%?`
- `0x1400e9346`: `[CLUSTER] Failed to bring the content set online. Unable to retrieve configuration of the content set's volume. resName: %? csId:%? volId:%?`
- `0x1400e92c8`: `[CLUSTER] Retrieving configuration of the content set's volume. resName:%? csId:%? volId:%?`
- `0x1400e93ed`: `[CLUSTER] Retrieved volume configuration from g_ConfigContext. resName:%? csId:%? volId:%?`
- `0x1400e93a4`: `[CLUSTER] Retrieved volume configuration from XML file. resName:%? csId:%? volId:%?`
- `0x1400e97ae`: `[CLUSTER] Failed to get root path's disk resource name from volume ID table. csId:%? csPath:%?`
- `0x1400e9b9c`: `[CLUSTER] Starting replica set's ReplicaSetManager. resName:%? csId:%? csName:%? rgId:%? rgName:%?`
- `0x1400e9b0f`: `[CLUSTER] Adding replica set's configuration to g_ConfigContext. resName:%? csId:%? csName:%? rgId:%? rgName:%?`
- `0x1400e9d40`: `[CLUSTER] Adding volume's configuration to g_ConfigContext. resName:%? csId:%? csName:%? volId:%? volPath:%?`
- `0x1400e9c63`: `[CLUSTER] Failed to bring the content set online. Unable to start the replica set's ReplicaSetManager. resName:%? csId:%? csName:%? rgId:%? rgName:%?`
- `0x1400e9e64`: `[CLUSTER] Failed to bring the content set online. Unable to start the volume's VolumeManager. resName:%? csId:%? csName:%? volId:%? volPath:%?`
- `0x1400e9dcd`: `[CLUSTER] Starting volume's VolumeManager. resName:%? csId:%? csName:%? volId:%? volPath:%?`
- `0x1400ea073`: `[CLUSTER] Starting content set's ContentSetManager. resName:%? csId:%? csName:%? volId:%? volPath:%?`
- `0x1400e9fbd`: `[CLUSTER] Setting content set's autoStart flag to TRUE. resName:%? csId:%? csName:%? volId:%? volPath:%?`
- `0x1400ea14a`: `[CLUSTER] (Ignored) ContentSetManager creation deferred due to VolumeManager shutdown. resName:%? csId:%? csName:%? volId:%? volPath:%?`
- `0x1400ea658`: `[CLUSTER] Removing replica set configuration that was added to g_ConfigContext during failed online. resName:%? csId:%? csName:%? rgId:%? rgName:%?`
- `0x1400ea6f1`: `[CLUSTER] Removing volume configuration that was added to g_ConfigContext during failed online. resName:%? csId:%? csName:%? volId:%? volPath:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall FrsReplicator::BringContentSetOnline(
        FrsReplicator *a1,
        _QWORD *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        struct _GUID *a5)
{
  const struct _GUID *v5; // r15
  const struct _GUID *v6; // r12
  int v7; // r13d
  const struct _GUID *v8; // r14
  ConfigContext *v9; // rcx
  __int64 v10; // rbx
  struct Config::ReplicaSet *v11; // rdi
  struct _GUID *v12; // rsi
  char v13; // al
  VolumeIdTable *VolumeTable; // rax
  ConfigContext *v15; // rcx
  VolumeIdTable *v16; // rax
  ConfigContext *v17; // rcx
  VolumeIdTable *v18; // rax
  DWORD CurrentThreadId; // eax
  __int64 v20; // rcx
  int v21; // edx
  struct FrsStatus *ReplicaSetConfiguration; // r15
  __int64 v23; // rcx
  LPCRITICAL_SECTION v24; // rcx
  const wchar_t *v25; // rdx
  const wchar_t **v26; // rcx
  unsigned int v27; // esi
  char *v28; // r14
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rdx
  struct Config::ContentSet *ContentSet; // rax
  BOOL v36; // r14d
  int v37; // edx
  struct Config::ContentSet *v38; // rax
  int v39; // edx
  ConfigContext *v40; // rcx
  VolumeIdTable *v41; // r14
  ConfigContext *v42; // rcx
  __int64 v43; // rax
  VolumeIdTable *v44; // r14
  int v45; // edx
  __int64 v46; // rax
  int v47; // r14d
  const unsigned __int16 *v48; // rax
  const unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // rax
  int v51; // edx
  ConfigContext *v52; // rcx
  ConfigContext *v53; // rcx
  ConfigContext *v54; // rcx
  ConfigContext *v55; // rcx
  int v56; // eax
  VolumeManager *v57; // r14
  bool v58; // zf
  LPCRITICAL_SECTION v59; // rax
  __int64 v60; // rdx
  const wchar_t *v61; // rax
  __int64 v62; // r15
  __int64 v63; // rdx
  const wchar_t *v64; // rax
  struct FrsStatus *v65; // rax
  __int64 v66; // rdx
  const wchar_t *v67; // rax
  const unsigned __int16 *v68; // rax
  const struct _GUID *v69; // r14
  unsigned int v70; // r15d
  char v71; // al
  const unsigned __int16 *v72; // rax
  const unsigned __int16 *v73; // rax
  __int64 v74; // r13
  unsigned __int16 *v75; // r15
  __int64 v76; // r12
  _QWORD *v77; // rax
  void *v78; // r14
  const struct _GUID *v79; // r15
  int v80; // r12d
  int v82; // [rsp+30h] [rbp-D0h]
  DWORD v83; // [rsp+38h] [rbp-C8h]
  struct FrsStatus *v85; // [rsp+60h] [rbp-A0h] BYREF
  struct Config::ReplicaSet *v86; // [rsp+68h] [rbp-98h] BYREF
  Config::Volume *v87; // [rsp+70h] [rbp-90h] BYREF
  int v88; // [rsp+78h] [rbp-88h] BYREF
  FrsReplicator *v89; // [rsp+80h] [rbp-80h]
  __int64 v90; // [rsp+88h] [rbp-78h] BYREF
  struct FrsStatus *v91; // [rsp+90h] [rbp-70h] BYREF
  int v92; // [rsp+98h] [rbp-68h]
  int v93; // [rsp+9Ch] [rbp-64h]
  VolumeManager *v94; // [rsp+A0h] [rbp-60h] BYREF
  const struct _GUID *v95; // [rsp+A8h] [rbp-58h]
  _QWORD *v96; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v97; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v98; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v99; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v100; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v101; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v102; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v103; // [rsp+E8h] [rbp-18h] BYREF
  Dword *v104; // [rsp+F0h] [rbp-10h] BYREF
  char v105[8]; // [rsp+F8h] [rbp-8h] BYREF
  char v106[8]; // [rsp+100h] [rbp+0h] BYREF
  char v107[8]; // [rsp+108h] [rbp+8h] BYREF
  char v108[8]; // [rsp+110h] [rbp+10h] BYREF
  VolumeManager *v109; // [rsp+118h] [rbp+18h] BYREF
  const wchar_t *v110; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v111; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v112[2]; // [rsp+130h] [rbp+30h] BYREF
  char v113[8]; // [rsp+140h] [rbp+40h] BYREF
  void *Block; // [rsp+148h] [rbp+48h] BYREF
  char v115[8]; // [rsp+150h] [rbp+50h] BYREF
  char v116[8]; // [rsp+158h] [rbp+58h] BYREF
  const wchar_t *v117; // [rsp+160h] [rbp+60h] BYREF
  int v118; // [rsp+168h] [rbp+68h]
  int v119; // [rsp+16Ch] [rbp+6Ch]
  const wchar_t *v120; // [rsp+170h] [rbp+70h]
  const wchar_t *v121; // [rsp+178h] [rbp+78h] BYREF
  int v122; // [rsp+180h] [rbp+80h]
  int v123; // [rsp+184h] [rbp+84h]
  const wchar_t *v124; // [rsp+188h] [rbp+88h]
  const wchar_t *v125; // [rsp+190h] [rbp+90h] BYREF
  int v126; // [rsp+198h] [rbp+98h]
  int v127; // [rsp+19Ch] [rbp+9Ch]
  const wchar_t *v128; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v129; // [rsp+1A8h] [rbp+A8h] BYREF
  int v130; // [rsp+1B0h] [rbp+B0h]
  int v131; // [rsp+1B4h] [rbp+B4h]
  const wchar_t *v132; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v133; // [rsp+1C0h] [rbp+C0h] BYREF
  int v134; // [rsp+1C8h] [rbp+C8h]
  int v135; // [rsp+1CCh] [rbp+CCh]
  const wchar_t *v136; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v137; // [rsp+1D8h] [rbp+D8h] BYREF
  int v138; // [rsp+1E0h] [rbp+E0h]
  int v139; // [rsp+1E4h] [rbp+E4h]
  const wchar_t *v140; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v141; // [rsp+1F0h] [rbp+F0h] BYREF
  int v142; // [rsp+1F8h] [rbp+F8h]
  int v143; // [rsp+1FCh] [rbp+FCh]
  const wchar_t *v144; // [rsp+200h] [rbp+100h]
  const wchar_t *v145; // [rsp+208h] [rbp+108h] BYREF
  int v146; // [rsp+210h] [rbp+110h]
  int v147; // [rsp+214h] [rbp+114h]
  const wchar_t *v148; // [rsp+218h] [rbp+118h]
  const wchar_t *v149; // [rsp+220h] [rbp+120h] BYREF
  int v150; // [rsp+228h] [rbp+128h]
  int v151; // [rsp+22Ch] [rbp+12Ch]
  const wchar_t *v152; // [rsp+230h] [rbp+130h]
  const wchar_t *v153; // [rsp+238h] [rbp+138h] BYREF
  int v154; // [rsp+240h] [rbp+140h]
  int v155; // [rsp+244h] [rbp+144h]
  const wchar_t *v156; // [rsp+248h] [rbp+148h]
  const wchar_t *v157; // [rsp+250h] [rbp+150h] BYREF
  int v158; // [rsp+258h] [rbp+158h]
  int v159; // [rsp+25Ch] [rbp+15Ch]
  const wchar_t *v160; // [rsp+260h] [rbp+160h]
  const wchar_t *v161; // [rsp+268h] [rbp+168h] BYREF
  int v162; // [rsp+270h] [rbp+170h]
  int v163; // [rsp+274h] [rbp+174h]
  const wchar_t *v164; // [rsp+278h] [rbp+178h]
  const wchar_t *v165; // [rsp+280h] [rbp+180h] BYREF
  int v166; // [rsp+288h] [rbp+188h]
  int v167; // [rsp+28Ch] [rbp+18Ch]
  const wchar_t *v168; // [rsp+290h] [rbp+190h]
  const wchar_t *v169; // [rsp+298h] [rbp+198h] BYREF
  int v170; // [rsp+2A0h] [rbp+1A0h]
  int v171; // [rsp+2A4h] [rbp+1A4h]
  const wchar_t *v172; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v173; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v174; // [rsp+2B8h] [rbp+1B8h]
  int v175; // [rsp+2BCh] [rbp+1BCh]
  const wchar_t *v176; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v177; // [rsp+2C8h] [rbp+1C8h] BYREF
  int v178; // [rsp+2D0h] [rbp+1D0h]
  int v179; // [rsp+2D4h] [rbp+1D4h]
  const wchar_t *v180; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v181; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v182; // [rsp+2E8h] [rbp+1E8h]
  int v183; // [rsp+2ECh] [rbp+1ECh]
  const wchar_t *v184; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v185; // [rsp+2F8h] [rbp+1F8h] BYREF
  int v186; // [rsp+300h] [rbp+200h]
  int v187; // [rsp+304h] [rbp+204h]
  const wchar_t *v188; // [rsp+308h] [rbp+208h]
  const wchar_t *v189; // [rsp+310h] [rbp+210h] BYREF
  int v190; // [rsp+318h] [rbp+218h]
  int v191; // [rsp+31Ch] [rbp+21Ch]
  const wchar_t *v192; // [rsp+320h] [rbp+220h]
  const wchar_t *v193; // [rsp+328h] [rbp+228h] BYREF
  int v194; // [rsp+330h] [rbp+230h]
  int v195; // [rsp+334h] [rbp+234h]
  const wchar_t *v196; // [rsp+338h] [rbp+238h]
  const wchar_t *v197; // [rsp+340h] [rbp+240h] BYREF
  int v198; // [rsp+348h] [rbp+248h]
  int v199; // [rsp+34Ch] [rbp+24Ch]
  const wchar_t *v200; // [rsp+350h] [rbp+250h]
  const wchar_t *v201; // [rsp+358h] [rbp+258h] BYREF
  int v202; // [rsp+360h] [rbp+260h]
  int v203; // [rsp+364h] [rbp+264h]
  const wchar_t *v204; // [rsp+368h] [rbp+268h]
  const wchar_t *v205; // [rsp+370h] [rbp+270h] BYREF
  int v206; // [rsp+378h] [rbp+278h]
  int v207; // [rsp+37Ch] [rbp+27Ch]
  const wchar_t *v208; // [rsp+380h] [rbp+280h]
  const wchar_t *v209; // [rsp+388h] [rbp+288h] BYREF
  int v210; // [rsp+390h] [rbp+290h]
  int v211; // [rsp+394h] [rbp+294h]
  const wchar_t *v212; // [rsp+398h] [rbp+298h]
  const wchar_t *v213; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v214; // [rsp+3A8h] [rbp+2A8h]
  int v215; // [rsp+3ACh] [rbp+2ACh]
  const wchar_t *v216; // [rsp+3B0h] [rbp+2B0h]
  const wchar_t *v217; // [rsp+3B8h] [rbp+2B8h] BYREF
  int v218; // [rsp+3C0h] [rbp+2C0h]
  int v219; // [rsp+3C4h] [rbp+2C4h]
  const wchar_t *v220; // [rsp+3C8h] [rbp+2C8h]
  const wchar_t *v221; // [rsp+3D0h] [rbp+2D0h] BYREF
  int v222; // [rsp+3D8h] [rbp+2D8h]
  int v223; // [rsp+3DCh] [rbp+2DCh]
  const wchar_t *v224; // [rsp+3E0h] [rbp+2E0h]
  const wchar_t *v225; // [rsp+3E8h] [rbp+2E8h] BYREF
  int v226; // [rsp+3F0h] [rbp+2F0h]
  int v227; // [rsp+3F4h] [rbp+2F4h]
  const wchar_t *v228; // [rsp+3F8h] [rbp+2F8h]
  const wchar_t *v229; // [rsp+400h] [rbp+300h] BYREF
  int v230; // [rsp+408h] [rbp+308h]
  int v231; // [rsp+40Ch] [rbp+30Ch]
  const wchar_t *v232; // [rsp+410h] [rbp+310h]
  const wchar_t *v233; // [rsp+418h] [rbp+318h] BYREF
  int v234; // [rsp+420h] [rbp+320h]
  int v235; // [rsp+424h] [rbp+324h]
  const wchar_t *v236; // [rsp+428h] [rbp+328h]
  _BYTE v237[272]; // [rsp+430h] [rbp+330h] BYREF
  const wchar_t *v238; // [rsp+540h] [rbp+440h] BYREF
  int v239; // [rsp+548h] [rbp+448h]
  int v240; // [rsp+54Ch] [rbp+44Ch]
  const wchar_t *v241; // [rsp+550h] [rbp+450h]
  _BYTE v242[40]; // [rsp+570h] [rbp+470h] BYREF
  char v243; // [rsp+598h] [rbp+498h]
  __int64 v244; // [rsp+5A0h] [rbp+4A0h]
  char v245[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  char v246[8]; // [rsp+5B8h] [rbp+4B8h] BYREF
  __int128 v247; // [rsp+5C0h] [rbp+4C0h]
  char v248[8]; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int128 v249; // [rsp+5D8h] [rbp+4D8h]
  char v250[8]; // [rsp+5E8h] [rbp+4E8h] BYREF
  char v251[8]; // [rsp+5F0h] [rbp+4F0h] BYREF
  char v252[8]; // [rsp+5F8h] [rbp+4F8h] BYREF
  BOOL v253; // [rsp+600h] [rbp+500h]
  struct _GUID v254; // [rsp+604h] [rbp+504h]
  __int128 v255; // [rsp+614h] [rbp+514h]

  v5 = a4;
  v6 = a3;
  v95 = a3;
  v7 = (int)a2;
  v96 = a2;
  v89 = a1;
  v8 = a5;
  v9 = 0;
  v10 = 0;
  v90 = 0;
  v11 = 0;
  v86 = 0;
  v12 = 0;
  v87 = 0;
  v98 = &FrsStringImpl<unsigned short,char>::s_Empty;
  v13 = byte_140315A80;
  if ( !byte_140315A80 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v10 = v90;
    v11 = v86;
    v12 = (struct _GUID *)v87;
    v13 = 0;
  }
  v97 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !v13 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
    v10 = v90;
    v11 = v86;
    v12 = (struct _GUID *)v87;
  }
  v92 = 0;
  v93 = 0;
  v88 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v117 = L"FrsReplicator::BringContentSetOnline";
    v118 = 591;
    v119 = 4;
    v120 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID>(
      (unsigned int)&v117,
      (unsigned int)L"[CLUSTER] Bringing content set online. resName:%? csId:%? rgId:%? volId:%?",
      (_DWORD)a2,
      (_DWORD)a3,
      (__int64)a4,
      (__int64)a5);
  }
  VolumeTable = ConfigContext::GetVolumeTable(v9);
  if ( !(unsigned int)VolumeIdTable::ContainsVolumeId(VolumeTable, a5) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v121 = L"FrsReplicator::BringContentSetOnline";
      v122 = 607;
      v123 = 4;
      v124 = L"FREP";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
        (unsigned int)&v121,
        (unsigned int)L"[CLUSTER] Volume ID Table does not contain a mapping for the specified volume. Rebuilding the Volu"
                       "me ID Table. resName:%? csId:%? volId:%?",
        v7,
        (_DWORD)v6,
        (__int64)a5);
    }
    v16 = ConfigContext::GetVolumeTable(v15);
    VolumeIdTable::Rebuild(v16);
    v18 = ConfigContext::GetVolumeTable(v17);
    if ( !(unsigned int)VolumeIdTable::ContainsVolumeId(v18, a5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      ReplicaSetConfiguration = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                      v20,
                                                      9225,
                                                      0,
                                                      3,
                                                      "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                                                      "FrsReplicator::BringContentSetOnline",
                                                      653,
                                                      CurrentThreadId,
                                                      0);
      v85 = ReplicaSetConfiguration;
      if ( ReplicaSetConfiguration )
      {
LABEL_130:
        v24 = g_DebugLog;
        goto LABEL_134;
      }
      v5 = a4;
    }
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v125 = L"FrsReplicator::BringContentSetOnline";
    v126 = 688;
    v127 = 4;
    v128 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID>(
      (unsigned int)&v125,
      (unsigned int)L"[CLUSTER] Removing stale configurations from g_ConfigContext. resName:%? csId:%? rgId:%? volId:%?",
      v7,
      (_DWORD)v6,
      (__int64)v5,
      (__int64)a5);
  }
  FrsReplicator::RemoveStaleConfigurationFromConfigContext(v89, v5, a5);
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v129 = L"FrsReplicator::BringContentSetOnline";
    v130 = 710;
    v131 = 4;
    v132 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
      (unsigned int)&v129,
      (unsigned int)L"[CLUSTER] Retrieving configuration of the content set's replica set. resName:%? csId:%? rgId:%?",
      v7,
      (_DWORD)v6,
      (__int64)v5);
  }
  ReplicaSetConfiguration = (struct FrsStatus *)FrsReplicator::GetReplicaSetConfiguration(v23, v5, &v86, &v88);
  v85 = ReplicaSetConfiguration;
  v24 = g_DebugLog;
  if ( ReplicaSetConfiguration )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v133 = L"FrsReplicator::BringContentSetOnline";
      v134 = 719;
      v135 = 2;
      v136 = L"FREP";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
        (unsigned int)&v133,
        (unsigned int)L"[CLUSTER] Failed to bring the content set online. Unable to retrieve configuration of the content "
                       "set's replica set. resName:%? csId:%? rgId:%?",
        v7,
        (_DWORD)v6,
        (__int64)a4);
LABEL_39:
      v24 = g_DebugLog;
    }
  }
  else if ( v88 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v137 = L"FrsReplicator::BringContentSetOnline";
      v138 = 728;
      v139 = 4;
      v140 = L"FREP";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
        (unsigned int)&v137,
        (unsigned int)L"[CLUSTER] Retrieved replica set configuration from XML file. resName:%? csId:%? rgId:%?",
        v7,
        (_DWORD)v6,
        (__int64)a4);
      goto LABEL_39;
    }
  }
  else if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v141 = L"FrsReplicator::BringContentSetOnline";
    v142 = 741;
    v143 = 4;
    v144 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
      (unsigned int)&v141,
      (unsigned int)L"[CLUSTER] Retrieved replica set configuration from g_ConfigContext resName:%? csId:%? rgId:%?",
      v7,
      (_DWORD)v6,
      (__int64)a4);
    goto LABEL_39;
  }
  if ( ReplicaSetConfiguration )
    goto LABEL_133;
  if ( v24 && LODWORD(v24[1].LockSemaphore) && SLODWORD(v24[1].OwningThread) >= 4 )
  {
    v145 = L"FrsReplicator::BringContentSetOnline";
    v146 = 755;
    v147 = 4;
    v148 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
      (unsigned int)&v145,
      (unsigned int)L"[CLUSTER] Retrieving configuration of the content set's volume. resName:%? csId:%? volId:%?",
      v7,
      (_DWORD)v6,
      (__int64)a5);
  }
  ReplicaSetConfiguration = (struct FrsStatus *)FrsReplicator::GetVolumeConfiguration(v24, a5, &v87, &v88);
  v85 = ReplicaSetConfiguration;
  v24 = g_DebugLog;
  if ( ReplicaSetConfiguration )
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 2 )
      goto LABEL_60;
    v149 = L"FrsReplicator::BringContentSetOnline";
    v150 = 764;
    v151 = 2;
    v152 = L"FREP";
    v25 = L"[CLUSTER] Failed to bring the content set online. Unable to retrieve configuration of the content set's volume"
           ". resName: %? csId:%? volId:%?";
    v26 = &v149;
  }
  else if ( v88 )
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
      goto LABEL_60;
    v153 = L"FrsReplicator::BringContentSetOnline";
    v154 = 773;
    v155 = 4;
    v156 = L"FREP";
    v25 = L"[CLUSTER] Retrieved volume configuration from XML file. resName:%? csId:%? volId:%?";
    v26 = &v153;
  }
  else
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 4 )
      goto LABEL_60;
    v157 = L"FrsReplicator::BringContentSetOnline";
    v158 = 786;
    v159 = 4;
    v160 = L"FREP";
    v25 = L"[CLUSTER] Retrieved volume configuration from g_ConfigContext. resName:%? csId:%? volId:%?";
    v26 = &v157;
  }
  dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID>(
    (_DWORD)v26,
    (_DWORD)v25,
    v7,
    (_DWORD)v6,
    (__int64)a5);
  v24 = g_DebugLog;
LABEL_60:
  if ( !ReplicaSetConfiguration )
  {
    v27 = 0;
    v11 = v86;
    v28 = (char *)v86 + 824;
    while ( v27 < (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v28 + 40LL))(v28) )
    {
      v30 = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v28 + 48LL))(v28, v27);
      v31 = *(_QWORD *)(v30 + 32) - *(_QWORD *)&v6->Data1;
      if ( !v31 )
        v31 = *(_QWORD *)(v30 + 40) - *(_QWORD *)v6->Data4;
      if ( !v31 )
      {
        v32 = 1;
        goto LABEL_69;
      }
      ++v27;
    }
    v32 = 0;
LABEL_69:
    v12 = (struct _GUID *)v87;
    if ( v32 )
    {
      v99 = 0;
      ContentSet = Config::Volume::FindContentSet(v87, v6, 0);
      ScopedRef<Config::ContentSet>::Set(&v99, ContentSet);
      v36 = v99 != 0;
      ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v99);
      if ( v36 )
      {
        v38 = Config::Volume::FindContentSet((Config::Volume *)v12, v6, 0);
        ScopedRef<Config::ContentSet>::Set(&v90, v38);
        v10 = v90;
        if ( (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(v90 + 1120)) )
          goto LABEL_89;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
        {
          v169 = L"FrsReplicator::BringContentSetOnline";
          v170 = 855;
          v171 = 2;
          v172 = L"FREP";
          dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam>(
            (unsigned int)&v169,
            v39,
            v7,
            (_DWORD)v6,
            v10 + 240);
        }
        v83 = GetCurrentThreadId();
        v82 = 861;
        v34 = 9052;
LABEL_88:
        ReplicaSetConfiguration = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                        v33,
                                                        v34,
                                                        0,
                                                        3,
                                                        "base\\fs\\remotefs\\frs\\src\\sync\\frsreplicator.cpp",
                                                        "FrsReplicator::BringContentSetOnline",
                                                        v82,
                                                        v83,
                                                        0);
        v85 = ReplicaSetConfiguration;
        if ( ReplicaSetConfiguration )
        {
LABEL_131:
          v24 = g_DebugLog;
          v8 = a5;
          goto LABEL_134;
        }
LABEL_89:
        VolumeId::VolumeId((VolumeId *)v242);
        v41 = ConfigContext::GetVolumeTable(v40);
        FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v105, *(_QWORD *)(v10 + 616) + 18LL);
        ReplicaSetConfiguration = (struct FrsStatus *)VolumeIdTable::FindVolumeFromFilePath(v41);
        v85 = ReplicaSetConfiguration;
        FrsStringImpl<char,unsigned short>::ReleaseBody(v105);
        if ( ReplicaSetConfiguration || !v243 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v173 = L"FrsReplicator::BringContentSetOnline";
            v174 = 892;
            v175 = 2;
            v176 = L"FREP";
            dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::PathParam>(
              &v173,
              L"[CLUSTER] Failed to get root path's disk resource name from volume ID table. csId:%? csPath:%?",
              v10 + 112,
              v10 + 576);
          }
        }
        else
        {
          v43 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v106, v244 + 18);
          FrsStringImpl<unsigned short,char>::Set(&v98, v43);
          FrsStringImpl<char,unsigned short>::ReleaseBody(v106);
        }
        if ( ReplicaSetConfiguration )
          goto LABEL_111;
        v44 = ConfigContext::GetVolumeTable(v42);
        FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v107, *(_QWORD *)(v10 + 704) + 18LL);
        ReplicaSetConfiguration = (struct FrsStatus *)VolumeIdTable::FindVolumeFromFilePath(v44);
        v85 = ReplicaSetConfiguration;
        FrsStringImpl<char,unsigned short>::ReleaseBody(v107);
        if ( ReplicaSetConfiguration || !v243 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v177 = L"FrsReplicator::BringContentSetOnline";
            v178 = 910;
            v179 = 2;
            v180 = L"FREP";
            dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::PathParam,Config::PathParam>(
              (unsigned int)&v177,
              v45,
              v10 + 112,
              v10 + 576,
              v10 + 664);
          }
        }
        else
        {
          v46 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v108, v244 + 18);
          FrsStringImpl<unsigned short,char>::Set(&v97, v46);
          FrsStringImpl<char,unsigned short>::ReleaseBody(v108);
        }
        if ( ReplicaSetConfiguration )
        {
LABEL_111:
          v8 = a5;
        }
        else
        {
          Cluster::DfsrResourcePropertyList::DfsrResourcePropertyList((Cluster::DfsrResourcePropertyList *)v245);
          v47 = Config::BoolParam::Get((Config::BoolParam *)(v10 + 1200));
          FrsStringImpl<unsigned short,char>::Set(v245, *(_QWORD *)(v10 + 616) + 18LL);
          v48 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
          FrsStringImpl<unsigned short,char>::Set(v246, v48);
          v247 = *(_OWORD *)(v10 + 144);
          v49 = Config::StringParam::Get((struct Config::ReplicaSet *)((char *)v11 + 448));
          FrsStringImpl<unsigned short,char>::Set(v248, v49);
          v249 = *((_OWORD *)v11 + 22);
          FrsStringImpl<unsigned short,char>::Set(v250, *(_QWORD *)(v10 + 704) + 18LL);
          FrsStringImpl<unsigned short,char>::Set(v251, *(_QWORD *)(v10 + 832) + 18LL);
          v50 = Config::StringParam::Get((Config::StringParam *)(v10 + 1560));
          FrsStringImpl<unsigned short,char>::Set(v252, v50);
          v253 = v47 != 0;
          v8 = a5;
          v254 = *a5;
          v255 = *(_OWORD *)(v10 + 480);
          ReplicaSetConfiguration = (struct FrsStatus *)Cluster::ClusterUtil::IsDfsrResourceInSyncWithParam(v7);
          v85 = ReplicaSetConfiguration;
          if ( ReplicaSetConfiguration
            && g_DebugLog
            && LODWORD(g_DebugLog[1].LockSemaphore)
            && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v181 = L"FrsReplicator::BringContentSetOnline";
            v182 = 955;
            v183 = 2;
            v184 = L"FREP";
            dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,Cluster::DfsrResourcePropertyList,FrsStringImpl<unsigned short,char>,FrsStringImpl<unsigned short,char>>(
              (unsigned int)&v181,
              v51,
              v7,
              (unsigned int)v245,
              (__int64)&v98,
              (__int64)&v97);
          }
          Cluster::DfsrResourcePropertyList::~DfsrResourcePropertyList((Cluster::DfsrResourcePropertyList *)v245);
        }
        VolumeId::~VolumeId((VolumeId *)v242);
        if ( !ReplicaSetConfiguration
          && !(unsigned int)ReplicaSetManagerMap::Contains((FrsReplicator *)((char *)v89 + 144), a4) )
        {
          if ( !(unsigned int)ConfigContext::ContainsReplicaSet(v52, a4) )
          {
            if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
            {
              v185 = L"FrsReplicator::BringContentSetOnline";
              v186 = 984;
              v187 = 4;
              v188 = L"FREP";
              dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::StringParam>(
                (unsigned int)&v185,
                (unsigned int)L"[CLUSTER] Adding replica set's configuration to g_ConfigContext. resName:%? csId:%? csName"
                               ":%? rgId:%? rgName:%?",
                v7,
                (_DWORD)v6,
                v10 + 240,
                (__int64)a4,
                (__int64)v11 + 448);
            }
            ConfigContext::AddReplicaSet(v53, v11);
            v92 = 1;
          }
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
          {
            v189 = L"FrsReplicator::BringContentSetOnline";
            v190 = 1002;
            v191 = 4;
            v192 = L"FREP";
            dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::StringParam>(
              (unsigned int)&v189,
              (unsigned int)L"[CLUSTER] Starting replica set's ReplicaSetManager. resName:%? csId:%? csName:%? rgId:%? rgName:%?",
              v7,
              (_DWORD)v6,
              v10 + 240,
              (__int64)a4,
              (__int64)v11 + 448);
          }
          Config::ReplicaSetDiff::ReplicaSetDiff(v237, 1);
          Config::ReplicaSetDiff::Diff((Config::ReplicaSetDiff *)v237, 0, v11);
          ReplicaSetConfiguration = FrsReplicator::UpdateReplicaSet(v89, (struct Config::ReplicaSetDiff *)v237);
          v85 = ReplicaSetConfiguration;
          if ( ReplicaSetConfiguration
            && g_DebugLog
            && LODWORD(g_DebugLog[1].LockSemaphore)
            && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
          {
            v193 = L"FrsReplicator::BringContentSetOnline";
            v194 = 1015;
            v195 = 2;
            v196 = L"FREP";
            dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::StringParam>(
              (unsigned int)&v193,
              (unsigned int)L"[CLUSTER] Failed to bring the content set online. Unable to start the replica set's ReplicaS"
                             "etManager. resName:%? csId:%? csName:%? rgId:%? rgName:%?",
              v7,
              (_DWORD)v6,
              v10 + 240,
              (__int64)a4,
              (__int64)v11 + 448);
          }
          Config::ReplicaSetDiff::~ReplicaSetDiff((Config::ReplicaSetDiff *)v237);
          goto LABEL_130;
        }
        goto LABEL_131;
      }
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v165 = L"FrsReplicator::BringContentSetOnline";
        v166 = 825;
        v167 = 2;
        v168 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,Config::PathParam>(
          (unsigned int)&v165,
          v37,
          v7,
          (_DWORD)v6,
          (__int64)a5,
          (__int64)&v12[15]);
      }
      v83 = GetCurrentThreadId();
      v82 = 832;
    }
    else
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
      {
        v161 = L"FrsReplicator::BringContentSetOnline";
        v162 = 811;
        v163 = 2;
        v164 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,Config::StringParam>(
          (unsigned int)&v161,
          v29,
          v7,
          (_DWORD)v6,
          (__int64)a4,
          (__int64)v11 + 448);
      }
      v83 = GetCurrentThreadId();
      v82 = 818;
    }
    v34 = 9028;
    goto LABEL_88;
  }
  v12 = (struct _GUID *)v87;
LABEL_133:
  v11 = v86;
LABEL_134:
  if ( ReplicaSetConfiguration )
    goto LABEL_198;
  if ( (unsigned int)VolumeManagerMap::Contains((FrsReplicator *)((char *)v89 + 8), v8) )
    goto LABEL_151;
  if ( !(unsigned int)ConfigContext::ContainsVolume(v54, v8) )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v197 = L"FrsReplicator::BringContentSetOnline";
      v198 = 1041;
      v199 = 4;
      v200 = L"FREP";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::PathParam>(
        (unsigned int)&v197,
        (unsigned int)L"[CLUSTER] Adding volume's configuration to g_ConfigContext. resName:%? csId:%? csName:%? volId:%? volPath:%?",
        v7,
        (_DWORD)v6,
        v10 + 240,
        (__int64)v8,
        (__int64)&v12[15]);
    }
    ConfigContext::AddVolume(v55, (struct Config::Volume *)v12);
    v93 = 1;
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v201 = L"FrsReplicator::BringContentSetOnline";
    v202 = 1059;
    v203 = 4;
    v204 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::PathParam>(
      (unsigned int)&v201,
      (unsigned int)L"[CLUSTER] Starting volume's VolumeManager. resName:%? csId:%? csName:%? volId:%? volPath:%?",
      v7,
      (_DWORD)v6,
      v10 + 240,
      (__int64)v8,
      (__int64)&v12[15]);
  }
  ReplicaSetConfiguration = FrsReplicator::CreateClusteredVolumeManager(v89, (struct Config::Volume *)v12);
  v85 = ReplicaSetConfiguration;
  if ( !ReplicaSetConfiguration )
    goto LABEL_151;
  v24 = g_DebugLog;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v205 = L"FrsReplicator::BringContentSetOnline";
    v206 = 1070;
    v207 = 2;
    v208 = L"FREP";
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::PathParam>(
      (unsigned int)&v205,
      (unsigned int)L"[CLUSTER] Failed to bring the content set online. Unable to start the volume's VolumeManager. resNam"
                     "e:%? csId:%? csName:%? volId:%? volPath:%?",
      v7,
      (_DWORD)v6,
      v10 + 240,
      (__int64)v8,
      (__int64)&v12[15]);
LABEL_151:
    v24 = g_DebugLog;
  }
  if ( ReplicaSetConfiguration )
    goto LABEL_198;
  v94 = 0;
  VolumeManagerMap::Find((FrsReplicator *)((char *)v89 + 8), v12 + 9, &v94);
  v56 = Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount);
  v57 = v94;
  v58 = v56 == 0;
  v59 = g_DebugLog;
  if ( !v58 )
  {
    if ( !g_DebugLog )
    {
LABEL_165:
      v62 = (__int64)a5;
      goto LABEL_166;
    }
    if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v209 = L"FrsReplicator::BringContentSetOnline";
      v210 = 1095;
      v211 = 5;
      v212 = L"FREP";
      v109 = v94;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v209,
        L"[VMREF] Added reference to volume manager. ptr:%p",
        &v109);
      v59 = g_DebugLog;
    }
  }
  if ( !v59 || !LODWORD(v59[1].LockSemaphore) || SLODWORD(v59[1].OwningThread) < 4 )
    goto LABEL_165;
  v213 = L"FrsReplicator::BringContentSetOnline";
  v214 = 1101;
  v215 = 4;
  v216 = L"FREP";
  v60 = (__int64)&v12[15];
  if ( v10 )
    v61 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
  else
    v61 = L"<>";
  v110 = v61;
  v62 = (__int64)a5;
  dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,unsigned short const *,_GUID,Config::PathParam>(
    (unsigned int)&v213,
    (unsigned int)L"[CLUSTER] Setting content set's autoStart flag to TRUE. resName:%? csId:%? csName:%? volId:%? volPath:%?",
    v7,
    (_DWORD)v6,
    (__int64)&v110,
    (__int64)a5,
    v60);
LABEL_166:
  *(_DWORD *)(v10 + 1604) = 1;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v217 = L"FrsReplicator::BringContentSetOnline";
    v218 = 1109;
    v219 = 4;
    v220 = L"FREP";
    v63 = (__int64)&v12[15];
    if ( v10 )
      v64 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
    else
      v64 = L"<>";
    v111 = v64;
    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,unsigned short const *,_GUID,Config::PathParam>(
      (unsigned int)&v217,
      (unsigned int)L"[CLUSTER] Starting content set's ContentSetManager. resName:%? csId:%? csName:%? volId:%? volPath:%?",
      v7,
      (_DWORD)v6,
      (__int64)&v111,
      v62,
      v63);
  }
  v65 = VolumeManager::BringContentSetOnline(v57, (struct Config::ContentSet *)v10);
  ReplicaSetConfiguration = v65;
  v91 = v65;
  v85 = v65;
  if ( v65 && *((_DWORD *)v65 + 1) == 9451 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
    {
      v221 = L"FrsReplicator::BringContentSetOnline";
      v222 = 1122;
      v223 = 3;
      v224 = L"FREP";
      v66 = (__int64)&v12[15];
      if ( v10 )
        v67 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
      else
        v67 = L"<>";
      v112[0] = v67;
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,unsigned short const *,_GUID,Config::PathParam>(
        (unsigned int)&v221,
        (unsigned int)L"[CLUSTER] (Ignored) ContentSetManager creation deferred due to VolumeManager shutdown. resName:%? "
                       "csId:%? csName:%? volId:%? volPath:%?",
        v7,
        (_DWORD)v6,
        (__int64)v112,
        (__int64)a5,
        v66);
    }
    CLEAR_ERROR(&v85);
    ReplicaSetConfiguration = v85;
    v91 = v85;
  }
  if ( !ReplicaSetConfiguration )
  {
    FrsReplicator::SetContentSetStatus(v89, v6, 3);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
    {
      v225 = L"FrsReplicator::BringContentSetOnline";
      v226 = 1149;
      v227 = 4;
      v228 = L"FREP";
      dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,Config::GuidParam,Config::StringParam,Config::GuidParam,Config::StringParam,Config::GuidParam,Config::PathParam>(
        (unsigned int)&v225,
        (_DWORD)v11 + 448,
        v7,
        v10 + 112,
        v10 + 240,
        (__int64)v11 + 320,
        (__int64)v11 + 448,
        (__int64)&v12[7],
        (__int64)&v12[15]);
    }
    v112[1] = *(_QWORD *)(v10 + 704) + 18LL;
    FrsGUIDToStringW(&v103, a4);
    Config::StringParam::Get((struct Config::ReplicaSet *)((char *)v11 + 448));
    FrsGUIDToStringW(v113, v95);
    v68 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
    FrsEvent::Log(1073750832, v68);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v113);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v103);
    ReplicaSetConfiguration = v91;
    LODWORD(v6) = (_DWORD)v95;
    v7 = (int)v96;
  }
  if ( v57 )
  {
    if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::DebugVolumeManagerRefCount)
      && g_DebugLog
      && LODWORD(g_DebugLog[1].LockSemaphore)
      && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
    {
      v229 = L"FrsReplicator::BringContentSetOnline";
      v230 = 1173;
      v231 = 5;
      v232 = L"FREP";
      v104 = v57;
      dbgobj::DbgPrint<unsigned short,unsigned __int64>(
        &v229,
        L"[VMREF] Release reference to volume manager. ptr:%p",
        &v104);
    }
    ScopedRef<VolumeManager::ShutdownRestartTask>::Set(&v94, 0);
  }
  ScopedRef<VvUpData>::~ScopedRef<VvUpData>(&v94);
  if ( ReplicaSetConfiguration )
  {
    v24 = g_DebugLog;
LABEL_198:
    if ( v24 && LODWORD(v24[1].LockSemaphore) )
    {
      v69 = a4;
      if ( SLODWORD(v24[1].OwningThread) >= 2 )
      {
        v233 = L"FrsReplicator::BringContentSetOnline";
        v234 = 1220;
        v235 = 2;
        v236 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,_GUID,_GUID,FrsStatus>(
          (unsigned int)&v233,
          v21,
          v7,
          (_DWORD)v6,
          (__int64)a4,
          (__int64)a5,
          (__int64)ReplicaSetConfiguration);
      }
    }
    else
    {
      v69 = a4;
    }
    FrsStatusString::FrsStatusString((FrsStatusString *)&Block, ReplicaSetConfiguration);
    v70 = *((_DWORD *)ReplicaSetConfiguration + 1);
    CLEAR_ERROR(&v85);
    v91 = (struct FrsStatus *)&FrsStringImpl<unsigned short,char>::s_Empty;
    v71 = byte_140315A80;
    if ( !byte_140315A80 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      v10 = v90;
      v11 = v86;
      v12 = (struct _GUID *)v87;
      v71 = 0;
    }
    v102 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !v71 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      v10 = v90;
      v11 = v86;
      v12 = (struct _GUID *)v87;
      v71 = byte_140315A80;
    }
    v101 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !v71 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      v10 = v90;
      v11 = v86;
      v12 = (struct _GUID *)v87;
      v71 = byte_140315A80;
    }
    v100 = &FrsStringImpl<unsigned short,char>::s_Empty;
    if ( !v71 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
      v10 = v90;
      v11 = v86;
      v12 = (struct _GUID *)v87;
    }
    if ( v10 )
    {
      v72 = Config::StringParam::Get((Config::StringParam *)(v10 + 240));
      FrsStringImpl<unsigned short,char>::Set(&v91, v72);
      FrsStringImpl<unsigned short,char>::Set(&v102, *(_QWORD *)(v10 + 616) + 18LL);
      FrsStringImpl<unsigned short,char>::Set(&v101, *(_QWORD *)(v10 + 704) + 18LL);
    }
    if ( v11 )
    {
      v73 = Config::StringParam::Get((struct Config::ReplicaSet *)((char *)v11 + 448));
      FrsStringImpl<unsigned short,char>::Set(&v100, v73);
    }
    v104 = Dword::Dword((Dword *)&v238, v70, 10);
    v103 = v101 + 9;
    v74 = *(_QWORD *)FrsGUIDToStringW(v116, v69) + 18LL;
    v75 = v100 + 9;
    v76 = *v96 + 18LL;
    v77 = (_QWORD *)FrsGUIDToStringW(v115, v95);
    v78 = Block;
    FrsEvent::Log(3221234481LL, (char *)v91 + 18, v102 + 9, *v77 + 18LL, v76, v75, v74, v103, v104, Block);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v115);
    FrsStringImpl<char,unsigned short>::ReleaseBody(v116);
    v79 = v95;
    v80 = (int)v96;
    FrsReplicator::BringContentSetOffline(v89, v96, v95, a4, a5, 1);
    if ( v92 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v238 = L"FrsReplicator::BringContentSetOnline";
        v239 = 1279;
        v240 = 4;
        v241 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::StringParam>(
          (unsigned int)&v238,
          (unsigned int)L"[CLUSTER] Removing replica set configuration that was added to g_ConfigContext during failed onl"
                         "ine. resName:%? csId:%? csName:%? rgId:%? rgName:%?",
          v80,
          (_DWORD)v79,
          v10 + 240,
          (__int64)a4,
          (__int64)v11 + 448);
      }
      ConfigContext::RemoveReplicaSet(g_ConfigContext, a4);
    }
    if ( v93 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v238 = L"FrsReplicator::BringContentSetOnline";
        v239 = 1301;
        v240 = 4;
        v241 = L"FREP";
        dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,_GUID,Config::StringParam,_GUID,Config::PathParam>(
          (unsigned int)&v238,
          (unsigned int)L"[CLUSTER] Removing volume configuration that was added to g_ConfigContext during failed online. "
                         "resName:%? csId:%? csName:%? volId:%? volPath:%?",
          v80,
          (_DWORD)v79,
          v10 + 240,
          (__int64)a5,
          (__int64)&v12[15]);
      }
      ConfigContext::RemoveVolume(g_ConfigContext, a5);
    }
    FrsReplicator::SetContentSetStatus(v89, v79, 4);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v100);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v101);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v102);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v91);
    operator delete[](v78);
  }
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v97);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v98);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v87);
  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v86);
  return ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v90);
}

```

## disassembly

```asm
0x1400e8e1c  push    rbp
0x1400e8e1e  push    rbx
0x1400e8e1f  push    rsi
0x1400e8e20  push    rdi
0x1400e8e21  push    r12
0x1400e8e23  push    r13
0x1400e8e25  push    r14
0x1400e8e27  push    r15
0x1400e8e29  lea     rbp, [rsp-548h]
0x1400e8e31  sub     rsp, 648h
0x1400e8e38  mov     rax, cs:__security_cookie
0x1400e8e3f  xor     rax, rsp
0x1400e8e42  mov     [rbp+580h+var_50], rax
0x1400e8e49  mov     r15, r9
0x1400e8e4c  mov     [rsp+680h+var_630], r9
0x1400e8e51  mov     r12, r8
0x1400e8e54  mov     [rbp+580h+var_5D8], r8
0x1400e8e58  mov     r13, rdx
0x1400e8e5b  mov     [rbp+580h+var_5D0], rdx
0x1400e8e5f  mov     [rbp+580h+var_600], rcx
0x1400e8e63  mov     r14, [rbp+580h+arg_20]
0x1400e8e6a  mov     [rsp+680h+var_628], r14
0x1400e8e6f  xor     ecx, ecx
0x1400e8e71  mov     ebx, ecx
0x1400e8e73  mov     [rbp+580h+var_5F8], rcx
0x1400e8e77  mov     edi, ecx
0x1400e8e79  mov     [rsp+680h+var_618], rcx
0x1400e8e7e  mov     esi, ecx
0x1400e8e80  mov     [rsp+680h+var_610], rcx
0x1400e8e85  lea     rdx, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400e8e8c  mov     [rbp+580h+var_5C0], rdx
0x1400e8e90  mov     al, cs:byte_140315A80
0x1400e8e96  test    al, al
0x1400e8e98  jnz     short loc_1400E8EB5
0x1400e8e9a  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400e8ea1  mov     rbx, [rbp+580h+var_5F8]
0x1400e8ea5  mov     rdi, [rsp+680h+var_618]
0x1400e8eaa  mov     rsi, [rsp+680h+var_610]
0x1400e8eaf  mov     al, cs:byte_140315A80
0x1400e8eb5  mov     [rbp+580h+var_5C8], rdx
0x1400e8eb9  test    al, al
0x1400e8ebb  jnz     short loc_1400E8ED2
0x1400e8ebd  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1400e8ec4  mov     rbx, [rbp+580h+var_5F8]
0x1400e8ec8  mov     rdi, [rsp+680h+var_618]
0x1400e8ecd  mov     rsi, [rsp+680h+var_610]
0x1400e8ed2  mov     [rbp+580h+var_5E8], ecx
0x1400e8ed5  mov     [rbp+580h+var_5E4], ecx
0x1400e8ed8  mov     [rsp+680h+var_608], ecx
0x1400e8edc  lea     rdx, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e8ee3  lea     r8, aFrep; "FREP"
0x1400e8eea  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e8ef1  test    rax, rax
0x1400e8ef4  jz      short loc_1400E8F37
0x1400e8ef6  cmp     [rax+40h], ecx
0x1400e8ef9  jz      short loc_1400E8F37
0x1400e8efb  cmp     dword ptr [rax+38h], 4
0x1400e8eff  jl      short loc_1400E8F37
0x1400e8f01  mov     [rbp+580h+var_520], rdx
0x1400e8f05  mov     [rbp+580h+var_518], 24Fh
0x1400e8f0c  mov     [rbp+580h+var_514], 4
0x1400e8f13  mov     [rbp+580h+var_510], r8
0x1400e8f17  mov     [rsp+680h+var_658], r14
0x1400e8f1c  mov     [rsp+680h+var_660], r9
0x1400e8f21  mov     r9, r12
0x1400e8f24  mov     r8, r13
0x1400e8f27  lea     rdx, aClusterBringin_2; "[CLUSTER] Bringing content set online. "...
0x1400e8f2e  lea     rcx, [rbp+580h+var_520]
0x1400e8f32  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@22@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &,_GUID const &)
0x1400e8f37  call    ?GetVolumeTable@ConfigContext@@QEAAPEAVVolumeIdTable@@XZ; ConfigContext::GetVolumeTable(void)
0x1400e8f3c  mov     rdx, r14; struct _GUID *
0x1400e8f3f  mov     rcx, rax; this
0x1400e8f42  call    ?ContainsVolumeId@VolumeIdTable@@QEAAHAEBU_GUID@@@Z; VolumeIdTable::ContainsVolumeId(_GUID const &)
0x1400e8f47  test    eax, eax
0x1400e8f49  jnz     loc_1400E902F
0x1400e8f4f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e8f56  test    rax, rax
0x1400e8f59  jz      short loc_1400E8FAF
0x1400e8f5b  cmp     dword ptr [rax+40h], 0
0x1400e8f5f  jz      short loc_1400E8FAF
0x1400e8f61  cmp     dword ptr [rax+38h], 4
0x1400e8f65  jl      short loc_1400E8FAF
0x1400e8f67  lea     rax, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e8f6e  mov     [rbp+580h+var_508], rax
0x1400e8f72  mov     [rbp+580h+var_500], 25Fh
0x1400e8f7c  mov     [rbp+580h+var_4FC], 4
0x1400e8f86  lea     rax, aFrep; "FREP"
0x1400e8f8d  mov     [rbp+580h+var_4F8], rax
0x1400e8f94  mov     [rsp+680h+var_660], r14
0x1400e8f99  mov     r9, r12
0x1400e8f9c  mov     r8, r13
0x1400e8f9f  lea     rdx, aClusterVolumeI; "[CLUSTER] Volume ID Table does not cont"...
0x1400e8fa6  lea     rcx, [rbp+580h+var_508]
0x1400e8faa  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@2@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &)
0x1400e8faf  call    ?GetVolumeTable@ConfigContext@@QEAAPEAVVolumeIdTable@@XZ; ConfigContext::GetVolumeTable(void)
0x1400e8fb4  mov     rcx, rax; this
0x1400e8fb7  call    ?Rebuild@VolumeIdTable@@QEAAXXZ; VolumeIdTable::Rebuild(void)
0x1400e8fbc  call    ?GetVolumeTable@ConfigContext@@QEAAPEAVVolumeIdTable@@XZ; ConfigContext::GetVolumeTable(void)
0x1400e8fc1  mov     rdx, r14; struct _GUID *
0x1400e8fc4  mov     rcx, rax; this
0x1400e8fc7  call    ?ContainsVolumeId@VolumeIdTable@@QEAAHAEBU_GUID@@@Z; VolumeIdTable::ContainsVolumeId(_GUID const &)
0x1400e8fcc  test    eax, eax
0x1400e8fce  jnz     short loc_1400E902F
0x1400e8fd0  call    cs:__imp_GetCurrentThreadId
0x1400e8fd7  nop     dword ptr [rax+rax+00h]
0x1400e8fdc  and     [rsp+680h+var_640], 0
0x1400e8fe2  mov     dword ptr [rsp+680h+var_648], eax
0x1400e8fe6  mov     dword ptr [rsp+680h+var_650], 28Dh
0x1400e8fee  lea     rax, aFrsreplicatorB; "FrsReplicator::BringContentSetOnline"
0x1400e8ff5  mov     [rsp+680h+var_658], rax
0x1400e8ffa  lea     rax, aBaseFsRemotefs_28; "base\\fs\\remotefs\\frs\\src\\sync\\frs"...
0x1400e9001  mov     [rsp+680h+var_660], rax
0x1400e9006  mov     r9d, 3
0x1400e900c  xor     r8d, r8d
0x1400e900f  mov     edx, 2409h
0x1400e9014  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400e9019  mov     r15, rax
0x1400e901c  mov     [rsp+680h+var_620], rax
0x1400e9021  test    rax, rax
0x1400e9024  jnz     loc_1400E9C83
0x1400e902a  mov     r15, [rsp+680h+var_630]
0x1400e902f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e9036  xor     edi, edi
0x1400e9038  test    rax, rax
0x1400e903b  jz      short loc_1400E909B
0x1400e903d  cmp     [rax+40h], edi
0x1400e9040  jz      short loc_1400E909B
0x1400e9042  cmp     dword ptr [rax+38h], 4
0x1400e9046  jl      short loc_1400E909B
0x1400e9048  lea     rax, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e904f  mov     [rbp+580h+var_4F0], rax
0x1400e9056  mov     [rbp+580h+var_4E8], 2B0h
0x1400e9060  mov     [rbp+580h+var_4E4], 4
0x1400e906a  lea     rax, aFrep; "FREP"
0x1400e9071  mov     [rbp+580h+var_4E0], rax
0x1400e9078  mov     [rsp+680h+var_658], r14
0x1400e907d  mov     [rsp+680h+var_660], r15
0x1400e9082  mov     r9, r12
0x1400e9085  mov     r8, r13
0x1400e9088  lea     rdx, aClusterRemovin_0; "[CLUSTER] Removing stale configurations"...
0x1400e908f  lea     rcx, [rbp+580h+var_4F0]
0x1400e9096  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@22@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &,_GUID const &)
0x1400e909b  mov     r8, r14; struct _GUID *
0x1400e909e  mov     rdx, r15; struct _GUID *
0x1400e90a1  mov     rcx, [rbp+580h+var_600]; this
0x1400e90a5  call    ?RemoveStaleConfigurationFromConfigContext@FrsReplicator@@IEAAXAEBU_GUID@@0@Z; FrsReplicator::RemoveStaleConfigurationFromConfigContext(_GUID const &,_GUID const &)
0x1400e90aa  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e90b1  test    rax, rax
0x1400e90b4  jz      short loc_1400E910F
0x1400e90b6  cmp     [rax+40h], edi
0x1400e90b9  jz      short loc_1400E910F
0x1400e90bb  cmp     dword ptr [rax+38h], 4
0x1400e90bf  jl      short loc_1400E910F
0x1400e90c1  lea     rax, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e90c8  mov     [rbp+580h+var_4D8], rax
0x1400e90cf  mov     [rbp+580h+var_4D0], 2C6h
0x1400e90d9  mov     [rbp+580h+var_4CC], 4
0x1400e90e3  lea     rax, aFrep; "FREP"
0x1400e90ea  mov     [rbp+580h+var_4C8], rax
0x1400e90f1  mov     [rsp+680h+var_660], r15
0x1400e90f6  mov     r9, r12
0x1400e90f9  mov     r8, r13
0x1400e90fc  lea     rdx, aClusterRetriev_3; "[CLUSTER] Retrieving configuration of t"...
0x1400e9103  lea     rcx, [rbp+580h+var_4D8]
0x1400e910a  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@2@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &)
0x1400e910f  lea     r9, [rsp+680h+var_608]
0x1400e9114  lea     r8, [rsp+680h+var_618]
0x1400e9119  mov     rdx, r15
0x1400e911c  call    ?GetReplicaSetConfiguration@FrsReplicator@@IEAAPEAVFrsStatus@@AEBU_GUID@@AEAV?$ScopedRef@VReplicaSet@Config@@@@PEAH@Z; FrsReplicator::GetReplicaSetConfiguration(_GUID const &,ScopedRef<Config::ReplicaSet> &,int *)
0x1400e9121  mov     r15, rax
0x1400e9124  mov     [rsp+680h+var_620], rax
0x1400e9129  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e9130  test    rax, rax
0x1400e9133  jz      short loc_1400E919E
0x1400e9135  test    rcx, rcx
0x1400e9138  jz      loc_1400E9274
0x1400e913e  cmp     [rcx+40h], edi
0x1400e9141  jz      loc_1400E9274
0x1400e9147  cmp     dword ptr [rcx+38h], 2
0x1400e914b  jl      loc_1400E9274
0x1400e9151  lea     rax, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e9158  mov     [rbp+580h+var_4C0], rax
0x1400e915f  mov     [rbp+580h+var_4B8], 2CFh
0x1400e9169  mov     [rbp+580h+var_4B4], 2
0x1400e9173  lea     rax, aFrep; "FREP"
0x1400e917a  mov     [rbp+580h+var_4B0], rax
0x1400e9181  mov     rcx, [rsp+680h+var_630]
0x1400e9186  mov     [rsp+680h+var_660], rcx
0x1400e918b  lea     rdx, aClusterFailedT_28; "[CLUSTER] Failed to bring the content s"...
0x1400e9192  lea     rcx, [rbp+580h+var_4C0]
0x1400e9199  jmp     loc_1400E9262
0x1400e919e  cmp     [rsp+680h+var_608], edi
0x1400e91a2  jz      short loc_1400E920A
0x1400e91a4  test    rcx, rcx
0x1400e91a7  jz      loc_1400E9274
0x1400e91ad  cmp     [rcx+40h], edi
0x1400e91b0  jz      loc_1400E9274
0x1400e91b6  cmp     dword ptr [rcx+38h], 4
0x1400e91ba  jl      loc_1400E9274
0x1400e91c0  lea     rax, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e91c7  mov     [rbp+580h+var_4A8], rax
0x1400e91ce  mov     [rbp+580h+var_4A0], 2D8h
0x1400e91d8  mov     [rbp+580h+var_49C], 4
0x1400e91e2  lea     rax, aFrep; "FREP"
0x1400e91e9  mov     [rbp+580h+var_498], rax
0x1400e91f0  mov     rcx, [rsp+680h+var_630]
0x1400e91f5  mov     [rsp+680h+var_660], rcx
0x1400e91fa  lea     rdx, aClusterRetriev_0; "[CLUSTER] Retrieved replica set configu"...
0x1400e9201  lea     rcx, [rbp+580h+var_4A8]
0x1400e9208  jmp     short loc_1400E9262
0x1400e920a  test    rcx, rcx
0x1400e920d  jz      short loc_1400E9274
0x1400e920f  cmp     [rcx+40h], edi
0x1400e9212  jz      short loc_1400E9274
0x1400e9214  cmp     dword ptr [rcx+38h], 4
0x1400e9218  jl      short loc_1400E9274
0x1400e921a  lea     rax, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e9221  mov     [rbp+580h+var_490], rax
0x1400e9228  mov     [rbp+580h+var_488], 2E5h
0x1400e9232  mov     [rbp+580h+var_484], 4
0x1400e923c  lea     rax, aFrep; "FREP"
0x1400e9243  mov     [rbp+580h+var_480], rax
0x1400e924a  mov     rcx, [rsp+680h+var_630]
0x1400e924f  mov     [rsp+680h+var_660], rcx
0x1400e9254  lea     rdx, aClusterRetriev; "[CLUSTER] Retrieved replica set configu"...
0x1400e925b  lea     rcx, [rbp+580h+var_490]
0x1400e9262  mov     r9, r12
0x1400e9265  mov     r8, r13
0x1400e9268  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@2@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &)
0x1400e926d  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e9274  test    r15, r15
0x1400e9277  jnz     loc_1400E9C9F
0x1400e927d  lea     rsi, aFrsreplicatorB_0; "FrsReplicator::BringContentSetOnline"
0x1400e9284  test    rcx, rcx
0x1400e9287  jz      short loc_1400E92DB
0x1400e9289  cmp     [rcx+40h], edi
0x1400e928c  jz      short loc_1400E92DB
0x1400e928e  cmp     dword ptr [rcx+38h], 4
0x1400e9292  jl      short loc_1400E92DB
0x1400e9294  mov     [rbp+580h+var_478], rsi
0x1400e929b  mov     [rbp+580h+var_470], 2F3h
0x1400e92a5  mov     [rbp+580h+var_46C], 4
0x1400e92af  lea     rax, aFrep; "FREP"
0x1400e92b6  mov     [rbp+580h+var_468], rax
0x1400e92bd  mov     [rsp+680h+var_660], r14
0x1400e92c2  mov     r9, r12
0x1400e92c5  mov     r8, r13
0x1400e92c8  lea     rdx, aClusterRetriev_2; "[CLUSTER] Retrieving configuration of t"...
0x1400e92cf  lea     rcx, [rbp+580h+var_478]
0x1400e92d6  call    ??$DbgPrint@GV?$FrsStringImpl@GD@@U_GUID@@U2@@dbgobj@@QEAA_KPEBGAEBV?$FrsStringImpl@GD@@AEBU_GUID@@2@Z; dbgobj::DbgPrint<ushort,FrsStringImpl<ushort,char>,_GUID,_GUID>(ushort const *,FrsStringImpl<ushort,char> const &,_GUID const &,_GUID const &)
0x1400e92db  lea     r9, [rsp+680h+var_608]
0x1400e92e0  lea     r8, [rsp+680h+var_610]
0x1400e92e5  mov     rdx, r14
0x1400e92e8  call    ?GetVolumeConfiguration@FrsReplicator@@IEAAPEAVFrsStatus@@AEBU_GUID@@AEAV?$ScopedRef@VVolume@Config@@@@PEAH@Z; FrsReplicator::GetVolumeConfiguration(_GUID const &,ScopedRef<Config::Volume> &,int *)
0x1400e92ed  mov     r15, rax
0x1400e92f0  mov     [rsp+680h+var_620], rax
0x1400e92f5  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400e92fc  test    rax, rax
0x1400e92ff  jz      short loc_1400E9359
0x1400e9301  test    rcx, rcx
0x1400e9304  jz      loc_1400E9412
0x1400e930a  cmp     [rcx+40h], edi
0x1400e930d  jz      loc_1400E9412
0x1400e9313  cmp     dword ptr [rcx+38h], 2
0x1400e9317  jl      loc_1400E9412
0x1400e931d  mov     [rbp+580h+var_460], rsi
0x1400e9324  mov     [rbp+580h+var_458], 2FCh
0x1400e932e  mov     [rbp+580h+var_454], 2
0x1400e9338  lea     rax, aFrep; "FREP"
0x1400e933f  mov     [rbp+580h+var_450], rax
0x1400e9346  lea     rdx, aClusterFailedT_13; "[CLUSTER] Failed to bring the content s"...
0x1400e934d  lea     rcx, [rbp+580h+var_460]
0x1400e9354  jmp     loc_1400E93FB
0x1400e9359  cmp     [rsp+680h+var_608], edi
0x1400e935d  jz      short loc_1400E93B4
0x1400e935f  test    rcx, rcx
0x1400e9362  jz      loc_1400E9412
0x1400e9368  cmp     [rcx+40h], edi
0x1400e936b  jz      loc_1400E9412
0x1400e9371  cmp     dword ptr [rcx+38h], 4
0x1400e9375  jl      loc_1400E9412
0x1400e937b  mov     [rbp+580h+var_448], rsi
0x1400e9382  mov     [rbp+580h+var_440], 305h
0x1400e938c  mov     [rbp+580h+var_43C], 4
0x1400e9396  lea     rax, aFrep; "FREP"
0x1400e939d  mov     [rbp+580h+var_438], rax
0x1400e93a4  lea     rdx, aClusterRetriev_1; "[CLUSTER] Retrieved volume configuratio"...
0x1400e93ab  lea     rcx, [rbp+580h+var_448]
0x1400e93b2  jmp     short loc_1400E93FB
0x1400e93b4  test    rcx, rcx
0x1400e93b7  jz      short loc_1400E9412
0x1400e93b9  cmp     [rcx+40h], edi
0x1400e93bc  jz      short loc_1400E9412
0x1400e93be  cmp     dword ptr [rcx+38h], 4
0x1400e93c2  jl      short loc_1400E9412
0x1400e93c4  mov     [rbp+580h+var_430], rsi
0x1400e93cb  mov     [rbp+580h+var_428], 312h
0x1400e93d5  mov     [rbp+580h+var_424], 4
0x1400e93df  lea     rax, aFrep; "FREP"
0x1400e93e6  mov     [rbp+580h+var_420], rax
  ... truncated ...
```
