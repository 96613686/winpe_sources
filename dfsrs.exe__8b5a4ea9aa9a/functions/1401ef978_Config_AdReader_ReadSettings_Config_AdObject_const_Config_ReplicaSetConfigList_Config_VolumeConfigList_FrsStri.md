# Config::AdReader::ReadSettings(Config::AdObject const *,Config::ReplicaSetConfigList *,Config::VolumeConfigList *,FrsStringImpl<ushort,char> &,Config::ContentSetList &)

- ea: `0x1401ef978`
- end: `0x1401f1491`
- name: `?ReadSettings@AdReader@Config@@IEAAPEAVFrsStatus@@PEBVAdObject@2@PEAVReplicaSetConfigList@2@PEAVVolumeConfigList@2@AEAV?$FrsStringImpl@GD@@AEAVContentSetList@2@@Z`
- size: `6937`
- prototype: `__int64 __usercall@<rax>(Config::AdReader *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `72`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1401ec574`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x140003a6c`
- `0x140003ba0`
- `0x140003c08`
- `0x14000cd1c`
- `0x14000daa0`
- `0x14000dd10`
- `0x14000e34c`
- `0x14000ee94`
- `0x140010680`
- `0x140011234`
- `0x140014df4`
- `0x14001a5cc`
- `0x14001bf80`
- `0x14001cfa0`
- `0x14001cfe0`
- `0x14001d390`
- `0x14001e19c`
- `0x14002169c`
- `0x14002179c`
- `0x1400217d0`
- `0x140022d1c`
- `0x140023794`
- `0x1400248f4`
- `0x1400249f4`
- `0x14003af50`
- `0x140040a18`
- `0x140041500`
- `0x140044898`
- `0x140044f3c`
- `0x140047e14`
- `0x140047e4c`
- `0x140048b10`
- `0x140052c18`
- `0x140055a64`
- `0x140056a98`
- `0x1400595e4`
- `0x140059ed8`
- `0x1400c967c`
- `0x1400e7f10`
- `0x1401b9494`
- `0x1401ba1bc`
- `0x1401bce38`
- `0x1401bebec`
- `0x1401befb8`
- `0x1401bf310`
- `0x1401ce910`
- `0x1401cff28`
- `0x1401d0078`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401f02db`
- `KERNEL32!GetCurrentThreadId` at `0x1401f0681`
- `KERNEL32!GetCurrentThreadId` at `0x1401f087e`
- `KERNEL32!GetCurrentThreadId` at `0x1401f142d`
- `KERNEL32!GetCurrentThreadId` at `0x1401f02db`
- `KERNEL32!GetCurrentThreadId` at `0x1401f0681`
- `KERNEL32!GetCurrentThreadId` at `0x1401f087e`
- `KERNEL32!GetCurrentThreadId` at `0x1401f142d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f0163`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f01a8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f035f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f043f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f0aa4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f0cb6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f0163`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f01a8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f035f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f043f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f0aa4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401f0cb6`

## string_xrefs

- `0x1401efde2`: `Dropped invalid contentSet configuration ID. csId:%ws`
- `0x1401f02c8`: `[CLUSTER] Invalid content set configuration detected. Clustered content set should be configured on shared disks and VCO resources belonging to same group. csId:%? csName:%? csPath:%? csStagingPath:%? resVcoName:%? resRootPathDisk:%? resStagingPathDisk:%?`
- `0x1401efd9d`: `Config::AdReader::ReadSettings`
- `0x1401f0243`: `Config::AdReader::ReadSettings`
- `0x1401f0505`: `Config::AdReader::ReadSettings`
- `0x1401f060a`: `Config::AdReader::ReadSettings`
- `0x1401f0807`: `Config::AdReader::ReadSettings`
- `0x1401f0ad9`: `Config::AdReader::ReadSettings`
- `0x1401f0c43`: `Config::AdReader::ReadSettings`
- `0x1401f0d68`: `Config::AdReader::ReadSettings`
- `0x1401f0df9`: `Config::AdReader::ReadSettings`
- `0x1401f0e84`: `Config::AdReader::ReadSettings`
- `0x1401f11c7`: `Config::AdReader::ReadSettings`
- `0x1401f066e`: `[CLUSTER] Invalid content set configuration detected. Clustered content set should be configured on shared disks. csId:%? csName:%? csPath:%? csStagingPath:%?`
- `0x1401f086b`: `[CLUSTER] Invalid content set configuration detected. Non-Clustered content set should be configured on local disks. csId:%? csName:%? csPath:%? csStagingPath`
- `0x1401ef9ef`: `Config::AdReader::ReadSettings`
- `0x1401f02f8`: `Config::AdReader::ReadSettings`
- `0x1401f069e`: `Config::AdReader::ReadSettings`
- `0x1401f089b`: `Config::AdReader::ReadSettings`
- `0x1401f1416`: `Config::AdReader::ReadSettings`
- `0x1401f05a3`: `[CLUSTER] Failed to get content set shared disks and VCO resources information. csId:%? csName:%? csPath:%? csStagingPath:%? resVcoName:%? resRootPathDisk:%? resStagingPathDisk:%?`
- `0x1401f0d11`: `[CLUSTER] The clustered content set root path has changed. DFSR will delete the existing content set information and resource. DFSR will add this new content set at next poll oldCsPath:%? newCsPath:%?`
- `0x1401f0b14`: `[CLUSTER] The content set root path has changed. DFSR will delete the existing content set information and add this new content set at next poll. oldCsPath:%? newCsPath:%?`
- `0x1401f0e34`: `[CLUSTER] Cannot check all resources so unable to make a decision on the content set. Adding it to missing content set list and skip it this time. csId:%? csPath:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall Config::AdReader::ReadSettings(
        Config::AdReader *this,
        struct Config::AdObject *a2,
        Config::ReplicaSetConfigList *a3,
        Config::VolumeConfigList *a4,
        __int64 a5,
        __int64 a6)
{
  Config::ReplicaSetConfigList *v6; // r15
  struct Config::AdObject *v7; // r14
  Config::AdReader *v8; // r13
  __int64 v9; // rsi
  unsigned int v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  struct Config::AdObject *v15; // rax
  struct Config::AdAttr *Attr; // rax
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rbx
  Config::AdStrAttr *v20; // rax
  BOOL v21; // r12d
  const struct _GUID *Value; // rax
  const struct Config::ReplicaSetConfig *v23; // r15
  const unsigned __int16 *v24; // rax
  struct Member *v25; // rbx
  int v26; // r14d
  Config::AdReader *v27; // rcx
  ConfigContext *v28; // rcx
  VolumeIdTable *VolumeTable; // rax
  struct Config::AdObject *v30; // rdi
  __int64 v31; // rdx
  Config::AdAttrList **v32; // rax
  Config::AdAttrList *v33; // rdi
  __int64 v34; // r14
  __int64 v35; // rax
  const unsigned __int16 *v36; // rax
  struct Config::ContentSet *v37; // rbx
  const unsigned __int16 *ServerName; // rax
  int v39; // edx
  struct FrsStatus *v40; // rax
  ConfigContext *v41; // rcx
  struct FrsStatus *VolumeFromFilePath; // r14
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // r10
  const unsigned __int16 *v46; // r11
  const wchar_t *DisplayPath; // rax
  const unsigned __int16 *v48; // rdx
  const unsigned __int16 *v49; // rcx
  ConfigContext *v50; // rcx
  VolumeIdTable *v51; // rdi
  unsigned __int16 *v52; // r13
  ConfigContext *v53; // rcx
  VolumeIdTable *v54; // rdi
  __int64 v55; // rax
  const unsigned __int16 *v56; // rcx
  __int64 v57; // r13
  __int64 v58; // r15
  const unsigned __int16 *v59; // rax
  struct _HCLUSTER *v60; // rdi
  _QWORD *ResourceClusterGroupName; // rax
  int v62; // r15d
  _QWORD *v63; // r8
  _QWORD *v64; // rax
  _QWORD *v65; // r8
  bool v66; // di
  unsigned int v67; // r15d
  DWORD CurrentThreadId; // eax
  __int64 v69; // rcx
  _QWORD *v70; // rax
  _QWORD *v71; // r8
  int v72; // edi
  const unsigned __int16 *v73; // rdi
  const struct Config::ReplicaSetConfig *v74; // r13
  const unsigned __int16 *v75; // rax
  _QWORD *v76; // rax
  _QWORD *v77; // r8
  int v78; // edi
  const unsigned __int16 *v79; // rdi
  const unsigned __int16 *v80; // rax
  __int64 v81; // r10
  DWORD v82; // eax
  __int64 v83; // rcx
  const unsigned __int16 *v84; // rdi
  const unsigned __int16 *v85; // rax
  const unsigned __int16 *v86; // rdi
  const unsigned __int16 *v87; // rax
  DWORD v88; // eax
  __int64 v89; // rcx
  __int64 v90; // r8
  __int64 v91; // rdi
  const unsigned __int16 *v92; // rax
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // r9
  __int64 v96; // r11
  __int64 v97; // rcx
  int v98; // r10d
  __int64 v99; // r8
  __int64 v100; // rdi
  const unsigned __int16 *v101; // rax
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // r9
  __int64 v105; // r11
  __int64 v106; // rcx
  int v107; // r10d
  _QWORD *v108; // r12
  struct Config::ContentSet *ContentSet; // rax
  __int64 v110; // rdi
  int v111; // eax
  int v112; // edx
  int v113; // edx
  int v114; // r15d
  unsigned int i; // edi
  __int64 v116; // rdx
  __int64 v117; // rax
  EventThrottle *v118; // rdi
  struct Config::ContentSet *v119; // rax
  Config::BoolParam *v120; // rcx
  struct Config::VolumeConfig **v121; // r8
  int v122; // eax
  int v123; // edx
  const unsigned __int16 *v124; // rdi
  const unsigned __int16 *v125; // rax
  __int64 v126; // r8
  __int64 v127; // r9
  __int64 v128; // r10
  const unsigned __int16 *v129; // r11
  const wchar_t *v130; // rax
  __int64 v131; // rcx
  struct Config::VolumeConfig **v132; // r8
  const unsigned __int16 *v133; // rax
  __int64 v134; // rdx
  const unsigned __int16 *v135; // rax
  __int64 v136; // rdx
  DWORD v137; // eax
  __int64 v138; // rcx
  __int64 v140; // [rsp+38h] [rbp-C8h]
  struct FrsStatus *v141; // [rsp+50h] [rbp-B0h] BYREF
  int v142; // [rsp+58h] [rbp-A8h]
  void **v143; // [rsp+60h] [rbp-A0h] BYREF
  char v144[8]; // [rsp+68h] [rbp-98h] BYREF
  BOOL v145; // [rsp+70h] [rbp-90h]
  struct Config::AdObject *v146; // [rsp+78h] [rbp-88h]
  Config::ReplicaSetConfigList *v147; // [rsp+80h] [rbp-80h]
  __int64 v148; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v149; // [rsp+90h] [rbp-70h] BYREF
  struct Config::ContentSet *v150; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v151; // [rsp+A0h] [rbp-60h]
  int v152; // [rsp+A4h] [rbp-5Ch]
  const struct Config::ReplicaSetConfig *v153; // [rsp+A8h] [rbp-58h]
  unsigned int v154; // [rsp+B0h] [rbp-50h]
  unsigned int v155; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v156; // [rsp+B8h] [rbp-48h] BYREF
  int v157; // [rsp+BCh] [rbp-44h]
  unsigned int v158; // [rsp+C0h] [rbp-40h]
  struct Member *v159; // [rsp+C8h] [rbp-38h]
  struct _HCLUSTER *v160; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v161; // [rsp+D8h] [rbp-28h]
  __int64 v162; // [rsp+E0h] [rbp-20h] BYREF
  struct Config::AdObject *v163; // [rsp+E8h] [rbp-18h]
  Config::AdReader *v164; // [rsp+F0h] [rbp-10h]
  __int64 v165; // [rsp+F8h] [rbp-8h]
  Config::VolumeConfigList *v166; // [rsp+100h] [rbp+0h]
  void **v167; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v168[3]; // [rsp+110h] [rbp+10h] BYREF
  char v169[8]; // [rsp+128h] [rbp+28h] BYREF
  char v170[8]; // [rsp+130h] [rbp+30h] BYREF
  char v171[8]; // [rsp+138h] [rbp+38h] BYREF
  char v172[8]; // [rsp+140h] [rbp+40h] BYREF
  char v173[8]; // [rsp+148h] [rbp+48h] BYREF
  char v174[8]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v175; // [rsp+158h] [rbp+58h]
  __int64 v176; // [rsp+160h] [rbp+60h] BYREF
  __int64 v177; // [rsp+168h] [rbp+68h] BYREF
  __int64 v178; // [rsp+170h] [rbp+70h] BYREF
  char v179[8]; // [rsp+178h] [rbp+78h] BYREF
  char v180[8]; // [rsp+180h] [rbp+80h] BYREF
  char v181[8]; // [rsp+188h] [rbp+88h] BYREF
  char v182[8]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v183; // [rsp+198h] [rbp+98h] BYREF
  __int64 v184; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v185; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v186; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v187; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v188; // [rsp+1C0h] [rbp+C0h]
  __int64 v189; // [rsp+1C8h] [rbp+C8h]
  char *v190; // [rsp+1D0h] [rbp+D0h] BYREF
  const wchar_t *v191; // [rsp+1D8h] [rbp+D8h] BYREF
  int v192; // [rsp+1E0h] [rbp+E0h]
  int v193; // [rsp+1E4h] [rbp+E4h]
  const wchar_t *v194; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v195; // [rsp+1F0h] [rbp+F0h] BYREF
  int v196; // [rsp+1F8h] [rbp+F8h]
  int v197; // [rsp+1FCh] [rbp+FCh]
  const wchar_t *v198; // [rsp+200h] [rbp+100h]
  const wchar_t *v199; // [rsp+208h] [rbp+108h] BYREF
  int v200; // [rsp+210h] [rbp+110h]
  int v201; // [rsp+214h] [rbp+114h]
  const wchar_t *v202; // [rsp+218h] [rbp+118h]
  const wchar_t *v203; // [rsp+220h] [rbp+120h] BYREF
  int v204; // [rsp+228h] [rbp+128h]
  int v205; // [rsp+22Ch] [rbp+12Ch]
  const wchar_t *v206; // [rsp+230h] [rbp+130h]
  const wchar_t *v207; // [rsp+238h] [rbp+138h] BYREF
  int v208; // [rsp+240h] [rbp+140h]
  int v209; // [rsp+244h] [rbp+144h]
  const wchar_t *v210; // [rsp+248h] [rbp+148h]
  const wchar_t *v211; // [rsp+250h] [rbp+150h] BYREF
  int v212; // [rsp+258h] [rbp+158h]
  int v213; // [rsp+25Ch] [rbp+15Ch]
  const wchar_t *v214; // [rsp+260h] [rbp+160h]
  const wchar_t *v215; // [rsp+268h] [rbp+168h] BYREF
  int v216; // [rsp+270h] [rbp+170h]
  int v217; // [rsp+274h] [rbp+174h]
  const wchar_t *v218; // [rsp+278h] [rbp+178h]
  const wchar_t *v219; // [rsp+280h] [rbp+180h] BYREF
  int v220; // [rsp+288h] [rbp+188h]
  int v221; // [rsp+28Ch] [rbp+18Ch]
  const wchar_t *v222; // [rsp+290h] [rbp+190h]
  const wchar_t *v223; // [rsp+298h] [rbp+198h] BYREF
  int v224; // [rsp+2A0h] [rbp+1A0h]
  int v225; // [rsp+2A4h] [rbp+1A4h]
  const wchar_t *v226; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v227; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v228; // [rsp+2B8h] [rbp+1B8h]
  int v229; // [rsp+2BCh] [rbp+1BCh]
  const wchar_t *v230; // [rsp+2C0h] [rbp+1C0h]
  const wchar_t *v231; // [rsp+2C8h] [rbp+1C8h] BYREF
  int v232; // [rsp+2D0h] [rbp+1D0h]
  int v233; // [rsp+2D4h] [rbp+1D4h]
  const wchar_t *v234; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v235; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v236; // [rsp+2E8h] [rbp+1E8h]
  int v237; // [rsp+2ECh] [rbp+1ECh]
  const wchar_t *v238; // [rsp+2F0h] [rbp+1F0h]
  _BYTE v239[48]; // [rsp+2F8h] [rbp+1F8h] BYREF
  Config::ContentSet *v240; // [rsp+328h] [rbp+228h]
  void *v241; // [rsp+330h] [rbp+230h]
  Config::Member *v242; // [rsp+338h] [rbp+238h]
  _BYTE v243[48]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v244[48]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v245[48]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v246[40]; // [rsp+3D0h] [rbp+2D0h] BYREF
  char v247; // [rsp+3F8h] [rbp+2F8h]
  __int64 v248; // [rsp+400h] [rbp+300h]
  _BYTE v249[40]; // [rsp+408h] [rbp+308h] BYREF
  char v250; // [rsp+430h] [rbp+330h]
  __int64 v251; // [rsp+438h] [rbp+338h]
  _QWORD v252[2]; // [rsp+440h] [rbp+340h] BYREF
  __int64 v253; // [rsp+450h] [rbp+350h]
  __int64 v254; // [rsp+458h] [rbp+358h]

  v166 = a4;
  v6 = a3;
  v147 = a3;
  v7 = a2;
  v146 = a2;
  v8 = this;
  v164 = this;
  v165 = a5;
  v161 = a6;
  v9 = 0;
  v151 = 0;
  v10 = 0;
  v158 = 0;
  v11 = *((_QWORD *)a2 + 10);
  if ( (unsigned int)((__int64)(*(_QWORD *)(v11 + 16) - *(_QWORD *)(v11 + 8)) >> 3) )
  {
    do
    {
      if ( !*(_DWORD *)(*((_QWORD *)v8 + 5) + 40LL) )
        break;
      v12 = *(_QWORD *)std::vector<ShutdownObject *>::at(v11 + 8, v10);
      v188 = v12;
      if ( (*(_BYTE *)(v12 + 89) & 0xEF) != 0 )
        goto LABEL_220;
      v13 = 0;
      v157 = 0;
      v14 = *(_QWORD *)(v12 + 80);
      if ( !(unsigned int)((__int64)(*(_QWORD *)(v14 + 16) - *(_QWORD *)(v14 + 8)) >> 3) )
        goto LABEL_220;
      while ( *(_DWORD *)(*((_QWORD *)v8 + 5) + 40LL) )
      {
        v15 = *(struct Config::AdObject **)std::vector<ShutdownObject *>::at(v14 + 8, v13);
        v163 = v15;
        if ( (*((_BYTE *)v15 + 89) & 0xEF) != 0 )
          goto LABEL_218;
        Attr = Config::AdAttrList::FindAttr(v15, L"msDFSR-MemberReference");
        if ( !Attr )
          goto LABEL_218;
        v17 = *((_QWORD *)Attr + 3);
        v189 = v17;
        if ( !v17 )
          goto LABEL_218;
        v18 = *(_QWORD *)(v17 + 72);
        v19 = *(_QWORD *)(v18 + 72);
        if ( !v19 )
          goto LABEL_218;
        v20 = Config::AdAttrList::FindAttr(*(Config::AdAttrList **)(v18 + 72), L"msDFSR-ReplicationGroupType");
        v21 = 0;
        v145 = 0;
        if ( (*(_BYTE *)(v17 + 89) & 0xEF) != 0 || (*(_BYTE *)(v19 + 89) & 0xEF) != 0 )
          goto LABEL_218;
        if ( v20 )
        {
          v21 = Config::AdStrAttr::GetInt32(v20) == 1;
          v145 = v21;
        }
        Value = (const struct _GUID *)Config::AdBinAttr::GetValue(*(Config::AdBinAttr **)(v19 + 56));
        v23 = Config::ReplicaSetConfigList::Find(v6, Value);
        v153 = v23;
        if ( v23 )
          goto LABEL_19;
        v241 = operator new(0x98u);
        v23 = (const struct Config::ReplicaSetConfig *)Config::ReplicaSetConfig::ReplicaSetConfig(v241, 1);
        v153 = v23;
        v24 = Config::AdStrAttr::GetValue(*((Config::AdStrAttr **)v7 + 6));
        Config::AdReader::ReadReplicaSet(v165, v19, *((_QWORD *)v23 + 18), v24, v165);
        if ( *(_DWORD *)(*((_QWORD *)v8 + 5) + 28LL)
          || (unsigned int)Config::BoolParam::Get((Config::BoolParam *)(*((_QWORD *)v23 + 18) + 528LL)) != 1 )
        {
          (*(void (__fastcall **)(Config::ReplicaSetConfigList *, const struct Config::ReplicaSetConfig *))(*(_QWORD *)v147 + 32LL))(
            v147,
            v23);
LABEL_19:
          v242 = (Config::Member *)operator new(0x218u);
          v25 = (struct Member *)Config::Member::Member(v242);
          v159 = v25;
          v156 = 0;
          v155 = 0;
          v26 = 0;
          v142 = 0;
          v152 = 0;
          (*(void (__fastcall **)(__int64, struct Member *))(*(_QWORD *)(*((_QWORD *)v23 + 18) + 904LL) + 32LL))(
            *((_QWORD *)v23 + 18) + 904LL,
            v25);
          Config::AdReader::ReadComputer(v8, v146, v25);
          Config::AdReader::ReadSubscriber(v27, v163, v25);
          Config::AdReader::ReadConnectionSettings(
            v8,
            (const struct Config::AdObject *)v17,
            v25,
            &v156,
            &v155,
            *((const struct Config::ReplicaSet **)v23 + 18));
          VolumeTable = ConfigContext::GetVolumeTable(v28);
          VolumeIdTable::Rebuild(VolumeTable);
          v154 = 0;
          v30 = v163;
          if ( !(unsigned int)((__int64)(*(_QWORD *)(*((_QWORD *)v163 + 10) + 16LL)
                                       - *(_QWORD *)(*((_QWORD *)v163 + 10) + 8LL)) >> 3) )
          {
LABEL_200:
            if ( dword_140319440 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
            {
              Init_thread_header(&dword_140319440);
              if ( dword_140319440 == -1 )
              {
                EventThrottle::EventThrottle((EventThrottle *)qword_140319448);
                atexit(Config::AdReader::ReadSettings_::_11_::_dynamic_atexit_destructor_for__eventThrottle__);
                Init_thread_footer(&dword_140319440);
              }
            }
            if ( !v21 )
            {
              if ( *(_DWORD *)(*((_QWORD *)v8 + 5) + 40LL) )
              {
                if ( v152 )
                {
                  if ( !v26 && !v155 )
                  {
                    Config::AdConfig::anyReadErrors = 1;
                    if ( (unsigned int)EventThrottle::IsRipe((EventThrottle *)qword_140319448, 1, 0) )
                    {
                      v133 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v23 + 18) + 448LL));
                      FrsEvent::Log(2147489668LL, v134 + 368, v133, &v25[19]);
                    }
                  }
                }
              }
              if ( (unsigned int)((__int64)(*(_QWORD *)(*((_QWORD *)v30 + 10) + 16LL)
                                          - *(_QWORD *)(*((_QWORD *)v30 + 10) + 8LL)) >> 3) )
              {
                if ( *(_DWORD *)(*((_QWORD *)v8 + 5) + 40LL) )
                {
                  if ( v26 )
                  {
                    if ( !v156 )
                    {
                      Config::AdConfig::anyReadErrors = 1;
                      if ( (unsigned int)EventThrottle::IsRipe((EventThrottle *)qword_140319448, 1, 0) )
                      {
                        v135 = Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v23 + 18) + 448LL));
                        FrsEvent::Log(2147489670LL, v136 + 368, v135, &v25[19]);
                      }
                    }
                  }
                }
              }
            }
            v7 = v146;
            goto LABEL_217;
          }
          while ( 2 )
          {
            if ( !*(_DWORD *)(*((_QWORD *)v8 + 5) + 40LL) )
            {
LABEL_199:
              v25 = v159;
              goto LABEL_200;
            }
            FilePath::FilePath((FilePath *)&v143);
            v32 = (Config::AdAttrList **)std::vector<ShutdownObject *>::at(*((_QWORD *)v30 + 10) + 8LL, v31);
            v33 = *v32;
            if ( (*((_BYTE *)*v32 + 89) & 0xEF) != 0 )
            {
              v143 = &FilePath::`vftable';
              FrsStringImpl<char,unsigned short>::ReleaseBody(v144);
              goto LABEL_198;
            }
            v34 = *((_QWORD *)Config::AdAttrList::FindAttr(*v32, L"msDFSR-ContentSetGuid") + 3);
            if ( (*(_BYTE *)(v34 + 89) & 0xEF) != 0 )
            {
LABEL_24:
              v143 = &FilePath::`vftable';
              FrsStringImpl<char,unsigned short>::ReleaseBody(v144);
              v26 = v142;
              goto LABEL_198;
            }
            v150 = 0;
            v240 = (Config::ContentSet *)operator new(0x658u);
            v35 = Config::ContentSet::ContentSet(v240);
            ScopedRef<Config::ContentSet>::Set(&v150, v35);
            v36 = Config::AdStrAttr::GetValue(*((Config::AdStrAttr **)v146 + 6));
            v37 = v150;
            Config::AdReader::ReadSubscription(v165, v33, v34, v189, v150, v36, v165);
            ServerName = Config::AdSession::GetServerName(*((Config::AdSession **)v8 + 5));
            v40 = Config::ContentSet::Validate(v37, v39, ServerName);
            VolumeFromFilePath = v40;
            v141 = v40;
            if ( v40 )
            {
              if ( *((_DWORD *)v40 + 1) == 9109 )
              {
                if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                {
                  v191 = L"Config::AdReader::ReadSettings";
                  v192 = 10441;
                  v193 = 3;
                  v194 = L"CFAD";
                  v190 = (char *)v37 + 160;
                  dbgobj::DbgPrint<unsigned short,unsigned short const *>(
                    &v191,
                    L"Dropped invalid contentSet configuration ID. csId:%ws",
                    &v190);
                }
                CLEAR_ERROR(&v141);
                Config::AdConfig::anyReadErrors = 1;
                ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v150);
                goto LABEL_24;
              }
              if ( *((_DWORD *)v40 + 1) == 9110 )
              {
                CLEAR_ERROR(&v141);
                Config::AdConfig::anyReadErrors = 1;
              }
              else
              {
                CLEAR_ERROR(&v141);
              }
              VolumeFromFilePath = v141;
            }
            if ( v21
              && *(_DWORD *)(*((_QWORD *)v8 + 5) + 36LL)
              && !(unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1200))
              && *((_DWORD *)v8 + 2) )
            {
              Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v23 + 18) + 448LL));
              v46 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
              if ( *((_QWORD *)v37 + 77) == -18 )
                DisplayPath = &pServiceName;
              else
                DisplayPath = (const wchar_t *)FilePath::GetDisplayPath((char *)v37 + 616);
              LODWORD(v140) = 0;
              FrsEvent::Log(1073746440, (char *)v37 + 160, DisplayPath, v46, v45, v44, v43, v140);
              Config::BoolParam::Set((struct Config::ContentSet *)((char *)v37 + 1200), 1);
            }
            if ( !VolumeFromFilePath )
            {
              VolumeId::VolumeId((VolumeId *)v249);
              VolumeId::VolumeId((VolumeId *)v246);
              if ( FrsStringUtils::StrLen((FrsStringUtils *)(*((_QWORD *)v37 + 88) + 18LL), v48) )
              {
                FilePath::Set((FilePath *)&v143, v49);
              }
              else
              {
                FilePath::Set((FilePath *)&v143, (const unsigned __int16 *)(*((_QWORD *)v37 + 77) + 18LL));
                FilePath::Append((FilePath *)&v143, L"DfsrPrivate");
                FilePath::Append((FilePath *)&v143, L"Staging");
              }
              v51 = ConfigContext::GetVolumeTable(v50);
              v52 = (unsigned __int16 *)((char *)v37 + 616);
              v149 = (unsigned __int16 *)((char *)v37 + 616);
              FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v169, *((_QWORD *)v37 + 77) + 18LL);
              VolumeFromFilePath = (struct FrsStatus *)VolumeIdTable::FindVolumeFromFilePath(v51);
              v141 = VolumeFromFilePath;
              FrsStringImpl<char,unsigned short>::ReleaseBody(v169);
              if ( !VolumeFromFilePath )
              {
                v54 = ConfigContext::GetVolumeTable(v53);
                v55 = FilePath::GetDisplayPath(v144);
                FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v170, v55);
                VolumeFromFilePath = (struct FrsStatus *)VolumeIdTable::FindVolumeFromFilePath(v54);
                v141 = VolumeFromFilePath;
                FrsStringImpl<char,unsigned short>::ReleaseBody(v170);
                if ( !VolumeFromFilePath )
                {
                  if ( (unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1520)) )
                  {
                    if ( v250 && v247 )
                    {
                      Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v239);
                      Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v244);
                      Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v243);
                      v160 = 0;
                      VolumeFromFilePath = Cluster::ClusterUtil::OpenClusterHandle(v56, &v160);
                      v141 = VolumeFromFilePath;
                      v57 = v248;
                      v58 = v251;
                      if ( VolumeFromFilePath )
                        goto LABEL_79;
                      v59 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 1560));
                      v60 = v160;
                      VolumeFromFilePath = Cluster::ClusterResource::LoadResourceInformation(
                                             (Cluster::ClusterResource *)v239,
                                             v160,
                                             v59);
                      v141 = VolumeFromFilePath;
                      if ( VolumeFromFilePath
                        || (v175 = v58 + 18,
                            VolumeFromFilePath = Cluster::ClusterResource::LoadResourceInformation(
                                                   (Cluster::ClusterResource *)v244,
                                                   v60,
                                                   (const unsigned __int16 *)(v58 + 18)),
                            (v141 = VolumeFromFilePath) != 0)
                        || (v148 = v57 + 18,
                            VolumeFromFilePath = Cluster::ClusterResource::LoadResourceInformation(
                                                   (Cluster::ClusterResource *)v243,
                                                   v60,
                                                   (const unsigned __int16 *)(v57 + 18)),
                            (v141 = VolumeFromFilePath) != 0) )
                      {
LABEL_79:
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                        {
                          v199 = L"Config::AdReader::ReadSettings";
                          v200 = 10608;
                          v201 = 2;
                          v202 = L"CFAD";
                          v183 = v57 + 18;
                          v184 = v58 + 18;
                          v185 = FilePath::GetDisplayPath(v144);
                          dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::StringParam,Config::PathParam,unsigned short const *,Config::StringParam,unsigned short const *,unsigned short const *>(
                            (unsigned int)&v199,
                            (unsigned int)L"[CLUSTER] Failed to get content set shared disks and VCO resources information"
                                           ". csId:%? csName:%? csPath:%? csStagingPath:%? resVcoName:%? resRootPathDisk:"
                                           "%? resStagingPathDisk:%?",
                            (_DWORD)v37 + 112,
                            (_DWORD)v37 + 240,
                            (__int64)v37 + 576,
                            (__int64)&v185,
                            v81,
                            (__int64)&v184,
                            (__int64)&v183);
                        }
                      }
                      else
                      {
                        Cluster::ClusterResource::GetResourceClusterGroupName(v239, v174);
                        ResourceClusterGroupName = (_QWORD *)Cluster::ClusterResource::GetResourceClusterGroupName(
                                                               v244,
                                                               v173);
                        v62 = v151 | 3;
                        v66 = 1;
                        if ( !(unsigned int)_o__wcsicmp(*v63 + 18LL, *ResourceClusterGroupName + 18LL) )
                        {
                          Cluster::ClusterResource::GetResourceClusterGroupName(v239, v172);
                          v64 = (_QWORD *)Cluster::ClusterResource::GetResourceClusterGroupName(v243, v171);
                          v62 |= 0xCu;
                          if ( !(unsigned int)_o__wcsicmp(*v65 + 18LL, *v64 + 18LL) )
                            v66 = 0;
                        }
                        if ( (v62 & 8) != 0 )
                        {
                          v62 &= ~8u;
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v171);
                        }
                        if ( (v62 & 4) != 0 )
                        {
                          v62 &= ~4u;
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v172);
                        }
                        v67 = v62 & 0xFFFFFFFD;
                        v151 = v67;
                        FrsStringImpl<char,unsigned short>::ReleaseBody(v173);
                        if ( (v67 & 1) != 0 )
                        {
                          v151 = v67 & 0xFFFFFFFE;
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v174);
                        }
                        if ( v66 )
                        {
                          if ( g_DebugLog
                            && LODWORD(g_DebugLog[1].LockSemaphore)
                            && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                          {
                            v195 = L"Config::AdReader::ReadSettings";
                            v196 = 10560;
                            v197 = 2;
                            v198 = L"CFAD";
                            v176 = v148;
                            v177 = v175;
                            v178 = FilePath::GetDisplayPath(v144);
                            dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::StringParam,Config::PathParam,unsigned short const *,Config::StringParam,unsigned short const *,unsigned short const *>(
                              (unsigned int)&v195,
                              (unsigned int)L"[CLUSTER] Invalid content set configuration detected. Clustered content set "
                                             "should be configured on shared disks and VCO resources belonging to same gr"
                                             "oup. csId:%? csName:%? csPath:%? csStagingPath:%? resVcoName:%? resRootPath"
                                             "Disk:%? resStagingPathDisk:%?",
                              (_DWORD)v37 + 112,
                              (_DWORD)v37 + 240,
                              (__int64)v37 + 576,
                              (__int64)&v178,
                              (__int64)v37 + 1560,
                              (__int64)&v177,
                              (__int64)&v176);
                          }
                          CurrentThreadId = GetCurrentThreadId();
                          VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                     v69,
                                                                     9119,
                                                                     0,
                                                                     3,
                                                                     "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                                                     "Config::AdReader::ReadSettings",
                                                                     10573,
                                                                     CurrentThreadId,
                                                                     0);
                          v141 = VolumeFromFilePath;
                          Cluster::ClusterResource::GetResourceClusterGroupName(v239, v180);
                          v70 = (_QWORD *)Cluster::ClusterResource::GetResourceClusterGroupName(v244, v179);
                          v72 = _o__wcsicmp(*v71 + 18LL, *v70 + 18LL);
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v179);
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v180);
                          if ( v72 )
                          {
                            v73 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 1560));
                            FilePath::GetDisplayPath(v144);
                            v74 = v153;
                            Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v153 + 18) + 448LL));
                            v75 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
                            HIDWORD(v140) = HIDWORD(v73);
                            FrsEvent::Log(3221234576LL, v75);
                          }
                          else
                          {
                            v74 = v153;
                          }
                          Cluster::ClusterResource::GetResourceClusterGroupName(v239, v182);
                          v76 = (_QWORD *)Cluster::ClusterResource::GetResourceClusterGroupName(v243, v181);
                          v78 = _o__wcsicmp(*v77 + 18LL, *v76 + 18LL);
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v181);
                          FrsStringImpl<char,unsigned short>::ReleaseBody(v182);
                          if ( v78 )
                          {
                            v79 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 1560));
                            FilePath::GetDisplayPath(v144);
                            Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v74 + 18) + 448LL));
                            v80 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
                            HIDWORD(v140) = HIDWORD(v79);
                            FrsEvent::Log(3221234577LL, v80);
                          }
                        }
                      }
                      Cluster::ClusterUtil::CloseClusterHandle(&v160);
                      Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v243);
                      Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v244);
                      Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v239);
                      v52 = v149;
                    }
                    else
                    {
                      if ( g_DebugLog
                        && LODWORD(g_DebugLog[1].LockSemaphore)
                        && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                      {
                        v203 = L"Config::AdReader::ReadSettings";
                        v204 = 10625;
                        v205 = 2;
                        v206 = L"CFAD";
                        v186 = FilePath::GetDisplayPath(v144);
                        dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::StringParam,Config::PathParam,unsigned short const *>(
                          (unsigned int)&v203,
                          (unsigned int)L"[CLUSTER] Invalid content set configuration detected. Clustered content set shou"
                                         "ld be configured on shared disks. csId:%? csName:%? csPath:%? csStagingPath:%?",
                          (_DWORD)v37 + 112,
                          (_DWORD)v37 + 240,
                          (__int64)v37 + 576,
                          (__int64)&v186);
                      }
                      v82 = GetCurrentThreadId();
                      VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                                 v83,
                                                                 9117,
                                                                 0,
                                                                 3,
                                                                 "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                                                 "Config::AdReader::ReadSettings",
                                                                 10633,
                                                                 v82,
                                                                 0);
                      v141 = VolumeFromFilePath;
                      if ( !v250 )
                      {
                        v84 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 1560));
                        FilePath::GetDisplayPath(v144);
                        Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v23 + 18) + 448LL));
                        v85 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
                        HIDWORD(v140) = HIDWORD(v84);
                        FrsEvent::Log(3221234572LL, v85);
                      }
                      if ( !v247 )
                      {
                        v86 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 1560));
                        FilePath::GetDisplayPath(v144);
                        Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v23 + 18) + 448LL));
                        v87 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
                        HIDWORD(v140) = HIDWORD(v86);
                        FrsEvent::Log(3221234574LL, v87);
                      }
                    }
                  }
                  else if ( v250 || v247 )
                  {
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                    {
                      v207 = L"Config::AdReader::ReadSettings";
                      v208 = 10680;
                      v209 = 2;
                      v210 = L"CFAD";
                      v187 = FilePath::GetDisplayPath(v144);
                      dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::StringParam,Config::PathParam,unsigned short const *>(
                        (unsigned int)&v207,
                        (unsigned int)L"[CLUSTER] Invalid content set configuration detected. Non-Clustered content set sh"
                                       "ould be configured on local disks. csId:%? csName:%? csPath:%? csStagingPath",
                        (_DWORD)v37 + 112,
                        (_DWORD)v37 + 240,
                        (__int64)v37 + 576,
                        (__int64)&v187);
                    }
                    v88 = GetCurrentThreadId();
                    VolumeFromFilePath = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                               v89,
                                                               9118,
                                                               0,
                                                               3,
                                                               "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
                                                               "Config::AdReader::ReadSettings",
                                                               10688,
                                                               v88,
                                                               0);
                    v141 = VolumeFromFilePath;
                    if ( v250 )
                    {
                      Config::BoolParam::Get((Config::BoolParam *)(*((_QWORD *)v23 + 18) + 528LL));
                      FilePath::GetDisplayPath(v144);
                      v91 = v90 + 368;
                      Config::StringParam::Get((Config::StringParam *)(v90 + 448));
                      v92 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
                      v97 = 3221234573LL;
                      if ( v98 == 1 )
                        v97 = 3221234580LL;
                      LODWORD(v140) = 0;
                      FrsEvent::Log(v97, v92, v94, v95, v93, v91, v96, v140);
                    }
                    if ( v247 )
                    {
                      Config::BoolParam::Get((Config::BoolParam *)(*((_QWORD *)v23 + 18) + 528LL));
                      FilePath::GetDisplayPath(v144);
                      v100 = v99 + 368;
                      Config::StringParam::Get((Config::StringParam *)(v99 + 448));
                      v101 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
                      v106 = 3221234575LL;
                      if ( v107 == 1 )
                        v106 = 3221234581LL;
                      LODWORD(v140) = 0;
                      FrsEvent::Log(v106, v101, v103, v104, v102, v100, v105, v140);
                    }
                  }
                }
              }
              VolumeId::~VolumeId((VolumeId *)v246);
              VolumeId::~VolumeId((VolumeId *)v249);
              if ( !VolumeFromFilePath )
              {
                v148 = 0;
                v108 = (_QWORD *)((char *)v37 + 144);
                ContentSet = ConfigContext::GetContentSet(v41, (const struct _GUID *)v37 + 9, 0);
                ScopedRef<Config::ContentSet>::Set(&v148, ContentSet);
                v110 = v148;
                if ( v148 )
                {
                  v149 = &FrsStringImpl<unsigned short,char>::s_Empty;
                  if ( !byte_140315A80 )
                  {
                    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
                    VolumeFromFilePath = v141;
                    v37 = v150;
                    v110 = v148;
                  }
                  FrsStringImpl<unsigned short,char>::Set(&v149, *(_QWORD *)(v110 + 616) + 18LL);
                  Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1520));
                  v111 = Config::BoolParam::Get((Config::BoolParam *)(v110 + 1520));
                  if ( v111 == v112 && !(unsigned int)_o__wcsicmp(v149 + 9, *(_QWORD *)v52 + 18LL) )
                  {
                    FrsStringImpl<char,unsigned short>::ReleaseBody(&v149);
                    goto LABEL_155;
                  }
                  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                  {
                    v211 = L"Config::AdReader::ReadSettings";
                    v212 = 10767;
                    v213 = 3;
                    v214 = L"CFAD";
                    dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,Config::PathParam>(
                      &v211,
                      L"[CLUSTER] The content set root path has changed. DFSR will delete the existing content set informa"
                       "tion and add this new content set at next poll. oldCsPath:%? newCsPath:%?",
                      &v149,
                      (char *)v37 + 576);
                  }
                  Config::AdConfig::subscriptionsChecksum = 0;
                  FrsStringImpl<char,unsigned short>::ReleaseBody(&v149);
LABEL_116:
                  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v148);
                  ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v150);
                  v143 = &FilePath::`vftable';
                  FrsStringImpl<char,unsigned short>::ReleaseBody(v144);
                  v26 = v142;
LABEL_197:
                  v21 = v145;
LABEL_198:
                  ++v154;
                  v30 = v163;
                  v23 = v153;
                  v8 = v164;
                  if ( v154 >= (unsigned int)((__int64)(*(_QWORD *)(*((_QWORD *)v163 + 10) + 16LL)
                                                      - *(_QWORD *)(*((_QWORD *)v163 + 10) + 8LL)) >> 3) )
                    goto LABEL_199;
                  continue;
                }
                if ( (unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1520)) )
                {
                  ObjList<Cluster::ClusterResource>::ObjList<Cluster::ClusterResource>(&v167);
                  VolumeFromFilePath = (struct FrsStatus *)Cluster::ClusterUtil::GetOwnedDfsrResources(1, &v167);
                  v141 = VolumeFromFilePath;
                  if ( VolumeFromFilePath )
                  {
                    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                    {
                      v231 = L"Config::AdReader::ReadSettings";
                      v232 = 10894;
                      v233 = 3;
                      v234 = L"CFAD";
                      dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::PathParam,FrsStatus>(
                        (unsigned int)&v231,
                        v113,
                        (_DWORD)v37 + 112,
                        (_DWORD)v37 + 576,
                        (__int64)VolumeFromFilePath);
                    }
                    CLEAR_ERROR(&v141);
                    VolumeFromFilePath = v141;
                  }
                  else
                  {
                    Cluster::DfsrResourcePropertyList::DfsrResourcePropertyList((Cluster::DfsrResourcePropertyList *)v252);
                    v114 = 0;
                    for ( i = 0; i < -1431655765 * (unsigned int)((__int64)(v168[1] - v168[0]) >> 4); ++i )
                    {
                      ObjList<Cluster::ClusterResource>::GetAt(&v167, v245, i);
                      VolumeFromFilePath = Cluster::ClusterUtil::GetDfsrResourceProperties(
                                             (const struct Cluster::ClusterResource *)v245,
                                             (struct Cluster::DfsrResourcePropertyList *)v252);
                      v141 = VolumeFromFilePath;
                      if ( VolumeFromFilePath )
                      {
                        if ( g_DebugLog
                          && LODWORD(g_DebugLog[1].LockSemaphore)
                          && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                        {
                          v215 = L"Config::AdReader::ReadSettings";
                          v216 = 10845;
                          v217 = 3;
                          v218 = L"CFAD";
                          dbgobj::DbgPrint<unsigned short,Cluster::ClusterResource,FrsStatus>(
                            &v215,
                            L"[CLUSTER] (Ignored) Failed to check DFSR resource at this time. res:%?. Error:%?",
                            v245,
                            VolumeFromFilePath);
                        }
                        CLEAR_ERROR(&v141);
                        v114 = 1;
                        VolumeFromFilePath = v141;
                      }
                      else
                      {
                        v117 = v253 - *v108;
                        if ( v253 == *v108 )
                          v117 = v254 - *((_QWORD *)v37 + 19);
                        if ( !v117 )
                        {
                          if ( g_DebugLog
                            && LODWORD(g_DebugLog[1].LockSemaphore)
                            && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
                          {
                            v219 = L"Config::AdReader::ReadSettings";
                            v220 = 10833;
                            v221 = 5;
                            v222 = L"CFAD";
                            dbgobj::DbgPrint<unsigned short,Cluster::DfsrResourcePropertyList>(&v219, v116, v252);
                          }
                          Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v245);
                          if ( (unsigned int)_o__wcsicmp(v252[0] + 18LL, *(_QWORD *)v52 + 18LL) )
                          {
                            if ( g_DebugLog
                              && LODWORD(g_DebugLog[1].LockSemaphore)
                              && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                            {
                              v223 = L"Config::AdReader::ReadSettings";
                              v224 = 10860;
                              v225 = 3;
                              v226 = L"CFAD";
                              dbgobj::DbgPrint<unsigned short,FrsStringImpl<unsigned short,char>,Config::PathParam>(
                                &v223,
                                L"[CLUSTER] The clustered content set root path has changed. DFSR will delete the existing"
                                 " content set information and resource. DFSR will add this new content set at next poll "
                                 "oldCsPath:%? newCsPath:%?",
                                v252,
                                (char *)v37 + 576);
                            }
                            Config::AdConfig::subscriptionsChecksum = 0;
LABEL_135:
                            Cluster::DfsrResourcePropertyList::~DfsrResourcePropertyList((Cluster::DfsrResourcePropertyList *)v252);
                            v167 = &ObjList<Cluster::ClusterResource>::`vftable';
                            std::vector<Cluster::ClusterResource>::_Tidy(v168);
                            goto LABEL_116;
                          }
                          goto LABEL_148;
                        }
                      }
                      Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v245);
                    }
                    if ( v114 )
                    {
                      if ( g_DebugLog
                        && LODWORD(g_DebugLog[1].LockSemaphore)
                        && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
                      {
                        v227 = L"Config::AdReader::ReadSettings";
                        v228 = 10875;
                        v229 = 3;
                        v230 = L"CFAD";
                        dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::PathParam>(
                          &v227,
                          L"[CLUSTER] Cannot check all resources so unable to make a decision on the content set. Adding i"
                           "t to missing content set list and skip it this time. csId:%? csPath:%?",
                          (char *)v37 + 112,
                          (char *)v37 + 576);
                      }
                      (*(void (__fastcall **)(__int64, struct Config::ContentSet *))(*(_QWORD *)v161 + 32LL))(v161, v37);
                      goto LABEL_135;
                    }
LABEL_148:
                    Cluster::DfsrResourcePropertyList::~DfsrResourcePropertyList((Cluster::DfsrResourcePropertyList *)v252);
                  }
                  v167 = &ObjList<Cluster::ClusterResource>::`vftable';
                  std::vector<Cluster::ClusterResource>::_Tidy(v168);
                }
LABEL_155:
                ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v148);
              }
              v8 = v164;
            }
            break;
          }
          v118 = 0;
          v162 = 0;
          v119 = ConfigContext::GetContentSet(v41, (const struct _GUID *)v37 + 9, 0);
          ScopedRef<Config::ContentSet>::Set(&v162, v119);
          if ( v162 )
            v118 = (EventThrottle *)(v162 + 1608);
          if ( (unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1120)) )
          {
            if ( v118 )
              *((_DWORD *)v118 + 2) = 0;
            if ( !VolumeFromFilePath && (unsigned int)Config::VolumeConfigList::AddContentSet(v166, v37, v121, 1) )
            {
              v122 = Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1200));
              v26 = v142;
              if ( v122 )
                v26 = ++v142;
              else
                ++v152;
LABEL_196:
              ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v162);
              ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(&v150);
              v143 = &FilePath::`vftable';
              FrsStringImpl<char,unsigned short>::ReleaseBody(v144);
              goto LABEL_197;
            }
            if ( (unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1520)) )
              (*(void (__fastcall **)(__int64, struct Config::ContentSet *))(*(_QWORD *)v161 + 32LL))(v161, v37);
            if ( !*((_DWORD *)v8 + 2) )
            {
LABEL_189:
              if ( VolumeFromFilePath )
              {
                if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
                {
                  v235 = L"Config::AdReader::ReadSettings";
                  v236 = 11012;
                  v237 = 2;
                  v238 = L"CFAD";
                  dbgobj::DbgPrint<unsigned short,Config::GuidParam,Config::StringParam,Config::PathParam,FrsStatus>(
                    (unsigned int)&v235,
                    v123,
                    (_DWORD)v37 + 112,
                    (_DWORD)v37 + 240,
                    (__int64)v37 + 576,
                    (__int64)VolumeFromFilePath);
                }
                CLEAR_ERROR(&v141);
              }
              v26 = v142;
              goto LABEL_196;
            }
            if ( (unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1520)) )
            {
              v124 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 1560));
              FilePath::GetDisplayPath(v144);
              Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v153 + 18) + 448LL));
              v125 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
              HIDWORD(v140) = HIDWORD(v124);
              FrsEvent::Log(3221234582LL, v125);
              goto LABEL_189;
            }
            Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v153 + 18) + 448LL));
            v129 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
            if ( *((_QWORD *)v37 + 77) == -18 )
              v130 = &pServiceName;
            else
              v130 = (const wchar_t *)FilePath::GetDisplayPath((char *)v37 + 616);
            v131 = 3221231876LL;
          }
          else
          {
            if ( (unsigned int)Config::BoolParam::Get(v120) )
              goto LABEL_189;
            if ( !VolumeFromFilePath
              && !(unsigned int)Config::VolumeConfigList::AddContentSet(v166, v37, v132, 0)
              && (unsigned int)Config::BoolParam::Get((struct Config::ContentSet *)((char *)v37 + 1520)) )
            {
              (*(void (__fastcall **)(__int64, struct Config::ContentSet *))(*(_QWORD *)v161 + 32LL))(v161, v37);
            }
            if ( !*((_DWORD *)v8 + 2) || v118 && !(unsigned int)EventThrottle::IsRipe(v118, 1, 0) )
              goto LABEL_189;
            Config::StringParam::Get((Config::StringParam *)(*((_QWORD *)v153 + 18) + 448LL));
            v129 = Config::StringParam::Get((struct Config::ContentSet *)((char *)v37 + 240));
            if ( *((_QWORD *)v37 + 77) == -18 )
              v130 = &pServiceName;
            else
              v130 = (const wchar_t *)FilePath::GetDisplayPath((char *)v37 + 616);
            v131 = 1073745938;
          }
          LODWORD(v140) = 0;
          FrsEvent::Log(v131, (char *)v37 + 160, v130, v129, v128, v127, v126, v140);
          goto LABEL_189;
        }
        (**(void (__fastcall ***)(const struct Config::ReplicaSetConfig *, __int64))v23)(v23, 1);
LABEL_217:
        v6 = v147;
LABEL_218:
        v13 = (unsigned int)(v157 + 1);
        v157 = v13;
        v14 = *(_QWORD *)(v188 + 80);
        if ( (unsigned int)v13 >= (unsigned int)((__int64)(*(_QWORD *)(v14 + 16) - *(_QWORD *)(v14 + 8)) >> 3) )
          break;
      }
      v10 = v158;
LABEL_220:
      v158 = ++v10;
      v11 = *((_QWORD *)v7 + 10);
    }
    while ( v10 < (unsigned int)((__int64)(*(_QWORD *)(v11 + 16) - *(_QWORD *)(v11 + 8)) >> 3) );
  }
  if ( !*(_DWORD *)(*((_QWORD *)v8 + 5) + 40LL) )
  {
    v137 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v138,
             1236,
             0,
             1,
             "base\\fs\\remotefs\\frs\\src\\ad\\ad.cpp",
             "Config::AdReader::ReadSettings",
             11073,
             v137,
             0);
  }
  return v9;
}

```

## disassembly

```asm
0x1401ef978  push    rbp
0x1401ef97a  push    rbx
0x1401ef97b  push    rsi
0x1401ef97c  push    rdi
0x1401ef97d  push    r12
0x1401ef97f  push    r13
0x1401ef981  push    r14
0x1401ef983  push    r15
0x1401ef985  lea     rbp, [rsp-3D8h]
0x1401ef98d  sub     rsp, 4D8h
0x1401ef994  mov     rax, cs:__security_cookie
0x1401ef99b  xor     rax, rsp
0x1401ef99e  mov     [rbp+410h+var_50], rax
0x1401ef9a5  mov     [rbp+410h+var_410], r9
0x1401ef9a9  mov     r15, r8
0x1401ef9ac  mov     [rbp+410h+var_490], r8
0x1401ef9b0  mov     r14, rdx
0x1401ef9b3  mov     [rsp+510h+var_498], rdx
0x1401ef9b8  mov     r13, rcx
0x1401ef9bb  mov     [rbp+410h+var_420], rcx
0x1401ef9bf  mov     rax, [rbp+410h+arg_20]
0x1401ef9c6  mov     [rbp+410h+var_418], rax
0x1401ef9ca  mov     rax, [rbp+410h+arg_28]
0x1401ef9d1  mov     [rbp+410h+var_438], rax
0x1401ef9d5  xor     esi, esi
0x1401ef9d7  mov     [rbp+410h+var_470], esi
0x1401ef9da  mov     ebx, esi
0x1401ef9dc  mov     [rbp+410h+var_450], ebx
0x1401ef9df  mov     rcx, [rdx+50h]
0x1401ef9e3  mov     rax, [rcx+10h]
0x1401ef9e7  sub     rax, [rcx+8]
0x1401ef9eb  sar     rax, 3
0x1401ef9ef  lea     rdi, aConfigAdreader_6; "Config::AdReader::ReadSettings"
0x1401ef9f6  lea     r12, aBaseFsRemotefs_10; "base\\fs\\remotefs\\frs\\src\\ad\\ad.cp"...
0x1401ef9fd  test    eax, eax
0x1401ef9ff  jz      loc_1401F1424
0x1401efa05  mov     rax, [r13+28h]
0x1401efa09  cmp     [rax+28h], esi
0x1401efa0c  jz      loc_1401F1416
0x1401efa12  add     rcx, 8
0x1401efa16  mov     edx, ebx
0x1401efa18  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401efa1d  mov     rax, [rax]
0x1401efa20  mov     [rbp+410h+var_350], rax
0x1401efa27  test    byte ptr [rax+59h], 0EFh
0x1401efa2b  jnz     loc_1401F13F9
0x1401efa31  mov     edx, esi
0x1401efa33  mov     [rbp+410h+var_454], edx
0x1401efa36  mov     rcx, [rax+50h]
0x1401efa3a  mov     rax, [rcx+10h]
0x1401efa3e  sub     rax, [rcx+8]
0x1401efa42  sar     rax, 3
0x1401efa46  test    eax, eax
0x1401efa48  jz      loc_1401F13F9
0x1401efa4e  mov     rax, [r13+28h]
0x1401efa52  cmp     [rax+28h], esi
0x1401efa55  jz      loc_1401F13F6
0x1401efa5b  add     rcx, 8
0x1401efa5f  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401efa64  mov     rax, [rax]
0x1401efa67  mov     [rbp+410h+var_428], rax
0x1401efa6b  test    byte ptr [rax+59h], 0EFh
0x1401efa6f  jnz     loc_1401F13CF
0x1401efa75  lea     rdx, aMsdfsrMemberre_0; "msDFSR-MemberReference"
0x1401efa7c  mov     rcx, rax; this
0x1401efa7f  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401efa84  test    rax, rax
0x1401efa87  jz      loc_1401F13CF
0x1401efa8d  mov     rdi, [rax+18h]
0x1401efa91  mov     [rbp+410h+var_348], rdi
0x1401efa98  test    rdi, rdi
0x1401efa9b  jz      loc_1401F13CF
0x1401efaa1  mov     rax, [rdi+48h]
0x1401efaa5  mov     rbx, [rax+48h]
0x1401efaa9  test    rbx, rbx
0x1401efaac  jz      loc_1401F13CF
0x1401efab2  lea     rdx, aMsdfsrReplicat_0; "msDFSR-ReplicationGroupType"
0x1401efab9  mov     rcx, rbx; this
0x1401efabc  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401efac1  mov     r12d, esi
0x1401efac4  mov     [rsp+510h+var_4A0], esi
0x1401efac8  test    byte ptr [rdi+59h], 0EFh
0x1401efacc  jnz     loc_1401F13CF
0x1401efad2  test    byte ptr [rbx+59h], 0EFh
0x1401efad6  jnz     loc_1401F13CF
0x1401efadc  test    rax, rax
0x1401efadf  jz      short loc_1401EFAF9
0x1401efae1  mov     rcx, rax; this
0x1401efae4  call    ?GetInt32@AdStrAttr@Config@@QEBAHXZ; Config::AdStrAttr::GetInt32(void)
0x1401efae9  mov     ecx, 1
0x1401efaee  cmp     eax, ecx
0x1401efaf0  cmovz   r12d, ecx
0x1401efaf4  mov     [rsp+510h+var_4A0], r12d
0x1401efaf9  mov     rcx, [rbx+38h]; this
0x1401efafd  call    ?GetValue@AdBinAttr@Config@@QEBAPEBEXZ; Config::AdBinAttr::GetValue(void)
0x1401efb02  mov     rdx, rax; struct _GUID *
0x1401efb05  mov     rcx, r15; this
0x1401efb08  call    ?Find@ReplicaSetConfigList@Config@@QEBAPEBVReplicaSetConfig@2@PEBU_GUID@@@Z; Config::ReplicaSetConfigList::Find(_GUID const *)
0x1401efb0d  mov     r15, rax
0x1401efb10  mov     [rbp+410h+var_468], rax
0x1401efb14  test    rax, rax
0x1401efb17  jnz     loc_1401EFBB2
0x1401efb1d  mov     ecx, 98h; Size
0x1401efb22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401efb27  mov     [rbp+410h+var_1E0], rax
0x1401efb2e  lea     edx, [r15+1]
0x1401efb32  mov     rcx, rax
0x1401efb35  call    ??0ReplicaSetConfig@Config@@QEAA@W4_FRS_CONFIG_SOURCE@@@Z; Config::ReplicaSetConfig::ReplicaSetConfig(_FRS_CONFIG_SOURCE)
0x1401efb3a  mov     r15, rax
0x1401efb3d  mov     [rbp+410h+var_468], rax
0x1401efb41  mov     rcx, [r14+30h]; this
0x1401efb45  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401efb4a  mov     rcx, [rbp+410h+var_418]
0x1401efb4e  mov     [rsp+510h+var_4F0], rcx
0x1401efb53  mov     r9, rax
0x1401efb56  mov     r8, [r15+90h]
0x1401efb5d  mov     rdx, rbx
0x1401efb60  call    ?ReadReplicaSet@AdReader@Config@@IEAAXPEBVAdObject@2@PEAVReplicaSet@2@PEBGAEAV?$FrsStringImpl@GD@@@Z; Config::AdReader::ReadReplicaSet(Config::AdObject const *,Config::ReplicaSet *,ushort const *,FrsStringImpl<ushort,char> &)
0x1401efb65  mov     rax, [r13+28h]
0x1401efb69  cmp     [rax+1Ch], esi
0x1401efb6c  jnz     short loc_1401EFB9F
0x1401efb6e  mov     rcx, [r15+90h]
0x1401efb75  add     rcx, 210h; this
0x1401efb7c  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1401efb81  mov     ecx, 1
0x1401efb86  cmp     eax, ecx
0x1401efb88  jnz     short loc_1401EFB9F
0x1401efb8a  mov     rax, [r15]
0x1401efb8d  mov     edx, ecx
0x1401efb8f  mov     rcx, r15
0x1401efb92  mov     rax, [rax]
0x1401efb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401efb9a  jmp     loc_1401F13CB
0x1401efb9f  mov     rcx, [rbp+410h+var_490]
0x1401efba3  mov     rax, [rcx]
0x1401efba6  mov     rdx, r15
0x1401efba9  mov     rax, [rax+20h]
0x1401efbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401efbb2  mov     ecx, 218h; Size
0x1401efbb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401efbbc  mov     [rbp+410h+var_1D8], rax
0x1401efbc3  mov     rcx, rax; this
0x1401efbc6  call    ??0Member@Config@@QEAA@XZ; Config::Member::Member(void)
0x1401efbcb  mov     rbx, rax
0x1401efbce  mov     [rbp+410h+var_448], rax
0x1401efbd2  mov     [rbp+410h+var_458], esi
0x1401efbd5  mov     [rbp+410h+var_45C], esi
0x1401efbd8  mov     r14d, esi
0x1401efbdb  mov     [rsp+510h+var_4B8], esi
0x1401efbdf  mov     [rbp+410h+var_46C], esi
0x1401efbe2  mov     rcx, [r15+90h]
0x1401efbe9  add     rcx, 388h
0x1401efbf0  mov     rdx, [rcx]
0x1401efbf3  mov     rax, [rdx+20h]
0x1401efbf7  mov     rdx, rbx
0x1401efbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401efbff  mov     r8, rbx; struct Member *
0x1401efc02  mov     rdx, [rsp+510h+var_498]; struct Config::AdObject *
0x1401efc07  mov     rcx, r13; this
0x1401efc0a  call    ?ReadComputer@AdReader@Config@@IEAAPEAVFrsStatus@@PEBVAdObject@2@PEAVMember@2@@Z; Config::AdReader::ReadComputer(Config::AdObject const *,Config::Member *)
0x1401efc0f  mov     r8, rbx; struct Member *
0x1401efc12  mov     rdx, [rbp+410h+var_428]; struct Config::AdObject *
0x1401efc16  call    ?ReadSubscriber@AdReader@Config@@IEAAXPEBVAdObject@2@PEAVMember@2@@Z; Config::AdReader::ReadSubscriber(Config::AdObject const *,Config::Member *)
0x1401efc1b  mov     rax, [r15+90h]
0x1401efc22  mov     [rsp+510h+var_4E8], rax; struct Config::ReplicaSet *
0x1401efc27  lea     rax, [rbp+410h+var_45C]
0x1401efc2b  mov     [rsp+510h+var_4F0], rax; unsigned int *
0x1401efc30  lea     r9, [rbp+410h+var_458]; unsigned int *
0x1401efc34  mov     r8, rbx; struct Member *
0x1401efc37  mov     rdx, rdi; struct Config::AdObject *
0x1401efc3a  mov     rcx, r13; this
0x1401efc3d  call    ?ReadConnectionSettings@AdReader@Config@@IEAAXPEBVAdObject@2@PEAVMember@2@AEAK2PEBVReplicaSet@2@@Z; Config::AdReader::ReadConnectionSettings(Config::AdObject const *,Config::Member *,ulong &,ulong &,Config::ReplicaSet const *)
0x1401efc42  call    ?GetVolumeTable@ConfigContext@@QEAAPEAVVolumeIdTable@@XZ; ConfigContext::GetVolumeTable(void)
0x1401efc47  mov     rcx, rax; this
0x1401efc4a  call    ?Rebuild@VolumeIdTable@@QEAAXXZ; VolumeIdTable::Rebuild(void)
0x1401efc4f  mov     edx, esi
0x1401efc51  mov     [rbp+410h+var_460], edx
0x1401efc54  mov     rdi, [rbp+410h+var_428]
0x1401efc58  mov     rax, [rdi+50h]
0x1401efc5c  mov     rcx, [rax+10h]
0x1401efc60  sub     rcx, [rax+8]
0x1401efc64  sar     rcx, 3
0x1401efc68  test    ecx, ecx
0x1401efc6a  jz      loc_1401F128D
0x1401efc70  mov     rax, [r13+28h]
0x1401efc74  cmp     [rax+28h], esi
0x1401efc77  jz      loc_1401F1289
0x1401efc7d  lea     rcx, [rsp+510h+var_4B0]; this
0x1401efc82  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x1401efc87  nop
0x1401efc88  mov     rcx, [rdi+50h]
0x1401efc8c  add     rcx, 8
0x1401efc90  call    ?at@?$vector@PEAVShutdownObject@@V?$allocator@PEAVShutdownObject@@@std@@@std@@QEAAAEAPEAVShutdownObject@@_K@Z; std::vector<ShutdownObject *>::at(unsigned __int64)
0x1401efc95  mov     rdi, [rax]
0x1401efc98  test    byte ptr [rdi+59h], 0EFh
0x1401efc9c  jz      short loc_1401EFCB9
0x1401efc9e  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1401efca5  mov     [rsp+510h+var_4B0], rax
0x1401efcaa  lea     rcx, [rsp+510h+var_4A8]
0x1401efcaf  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401efcb4  jmp     loc_1401F125D
0x1401efcb9  lea     rdx, aMsdfsrContents_0; "msDFSR-ContentSetGuid"
0x1401efcc0  mov     rcx, rdi; this
0x1401efcc3  call    ?FindAttr@AdAttrList@Config@@QEBAPEAVAdAttr@2@PEBG@Z; Config::AdAttrList::FindAttr(ushort const *)
0x1401efcc8  mov     r14, [rax+18h]
0x1401efccc  test    byte ptr [r14+59h], 0EFh
0x1401efcd1  jz      short loc_1401EFCF3
0x1401efcd3  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x1401efcda  mov     [rsp+510h+var_4B0], rax
0x1401efcdf  lea     rcx, [rsp+510h+var_4A8]
0x1401efce4  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401efce9  mov     r14d, [rsp+510h+var_4B8]
0x1401efcee  jmp     loc_1401F125D
0x1401efcf3  mov     [rbp+410h+var_478], rsi
0x1401efcf7  mov     ecx, 658h; Size
0x1401efcfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401efd01  mov     [rbp+410h+var_1E8], rax
0x1401efd08  mov     rcx, rax; this
0x1401efd0b  call    ??0ContentSet@Config@@QEAA@XZ; Config::ContentSet::ContentSet(void)
0x1401efd10  nop
0x1401efd11  mov     rdx, rax
0x1401efd14  lea     rcx, [rbp+410h+var_478]
0x1401efd18  call    ?Set@?$ScopedRef@VContentSet@Config@@@@AEAAXPEAVContentSet@Config@@@Z; ScopedRef<Config::ContentSet>::Set(Config::ContentSet *)
0x1401efd1d  mov     rax, [rsp+510h+var_498]
0x1401efd22  mov     rcx, [rax+30h]; this
0x1401efd26  call    ?GetValue@AdStrAttr@Config@@QEBAPEBGXZ; Config::AdStrAttr::GetValue(void)
0x1401efd2b  mov     rcx, [rbp+410h+var_418]
0x1401efd2f  mov     [rsp+510h+var_4E0], rcx
0x1401efd34  mov     [rsp+510h+var_4E8], rax
0x1401efd39  mov     rbx, [rbp+410h+var_478]
0x1401efd3d  mov     [rsp+510h+var_4F0], rbx
0x1401efd42  mov     r9, [rbp+410h+var_348]
0x1401efd49  mov     r8, r14
0x1401efd4c  mov     rdx, rdi
0x1401efd4f  call    ?ReadSubscription@AdReader@Config@@IEAAXPEBVAdObject@2@00PEAVContentSet@2@PEBGAEAV?$FrsStringImpl@GD@@@Z; Config::AdReader::ReadSubscription(Config::AdObject const *,Config::AdObject const *,Config::AdObject const *,Config::ContentSet *,ushort const *,FrsStringImpl<ushort,char> &)
0x1401efd54  mov     rcx, [r13+28h]; this
0x1401efd58  call    ?GetServerName@AdSession@Config@@QEBAPEBGXZ; Config::AdSession::GetServerName(void)
0x1401efd5d  mov     r8, rax; unsigned __int16 *
0x1401efd60  mov     rcx, rbx; this
0x1401efd63  call    ?Validate@ContentSet@Config@@QEBAPEAVFrsStatus@@HPEBG@Z; Config::ContentSet::Validate(int,ushort const *)
0x1401efd68  mov     r14, rax
0x1401efd6b  mov     [rsp+510h+var_4C0], rax
0x1401efd70  test    rax, rax
0x1401efd73  jz      loc_1401EFE40
0x1401efd79  cmp     dword ptr [rax+4], 2395h
0x1401efd80  jnz     loc_1401EFE17
0x1401efd86  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401efd8d  test    rax, rax
0x1401efd90  jz      short loc_1401EFDF5
0x1401efd92  cmp     [rax+40h], esi
0x1401efd95  jz      short loc_1401EFDF5
0x1401efd97  cmp     dword ptr [rax+38h], 3
0x1401efd9b  jl      short loc_1401EFDF5
0x1401efd9d  lea     rax, aConfigAdreader_8; "Config::AdReader::ReadSettings"
0x1401efda4  mov     [rbp+410h+var_338], rax
0x1401efdab  mov     [rbp+410h+var_330], 28C9h
0x1401efdb5  mov     [rbp+410h+var_32C], 3
0x1401efdbf  lea     rax, aCfad; "CFAD"
0x1401efdc6  mov     [rbp+410h+var_328], rax
0x1401efdcd  add     rbx, 0A0h
0x1401efdd4  mov     [rbp+410h+var_340], rbx
0x1401efddb  lea     r8, [rbp+410h+var_340]
0x1401efde2  lea     rdx, aDroppedInvalid; "Dropped invalid contentSet configuratio"...
0x1401efde9  lea     rcx, [rbp+410h+var_338]
0x1401efdf0  call    ??$DbgPrint@GPEBG@dbgobj@@QEAA_KPEBGAEBQEBG@Z; dbgobj::DbgPrint<ushort,ushort const *>(ushort const *,ushort const * const &)
0x1401efdf5  lea     rcx, [rsp+510h+var_4C0]; struct FrsStatus **
0x1401efdfa  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401efdff  mov     cs:?anyReadErrors@AdConfig@Config@@1HA, 1; int Config::AdConfig::anyReadErrors
0x1401efe09  lea     rcx, [rbp+410h+var_478]
0x1401efe0d  call    ??1?$ScopedRef@VReplicaSet@Config@@@@QEAA@XZ; ScopedRef<Config::ReplicaSet>::~ScopedRef<Config::ReplicaSet>(void)
0x1401efe12  jmp     loc_1401EFCD3
0x1401efe17  lea     rcx, [rsp+510h+var_4C0]; struct FrsStatus **
0x1401efe1c  cmp     dword ptr [rax+4], 2396h
0x1401efe23  jnz     short loc_1401EFE36
0x1401efe25  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401efe2a  mov     cs:?anyReadErrors@AdConfig@Config@@1HA, 1; int Config::AdConfig::anyReadErrors
0x1401efe34  jmp     short loc_1401EFE3B
0x1401efe36  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401efe3b  mov     r14, [rsp+510h+var_4C0]
0x1401efe40  test    r12d, r12d
0x1401efe43  jz      loc_1401EFF03
0x1401efe49  mov     rax, [r13+28h]
0x1401efe4d  cmp     [rax+24h], esi
0x1401efe50  jz      loc_1401EFF03
0x1401efe56  lea     rdi, [rbx+4B0h]
0x1401efe5d  mov     rcx, rdi; this
0x1401efe60  call    ?Get@BoolParam@Config@@QEBA?BHXZ; Config::BoolParam::Get(void)
0x1401efe65  test    eax, eax
0x1401efe67  jnz     loc_1401EFF03
0x1401efe6d  cmp     [r13+8], esi
0x1401efe71  jz      loc_1401EFF03
0x1401efe77  mov     r8, [rbp+410h+var_448]
0x1401efe7b  add     r8, 98h
0x1401efe82  mov     rcx, [r15+90h]
0x1401efe89  lea     r9, [rcx+170h]
0x1401efe90  add     rcx, 1C0h; this
0x1401efe97  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
0x1401efe9c  mov     r10, rax
0x1401efe9f  lea     rcx, [rbx+0F0h]; this
0x1401efea6  call    ?Get@StringParam@Config@@QEBAPEBGXZ; Config::StringParam::Get(void)
  ... truncated ...
```
