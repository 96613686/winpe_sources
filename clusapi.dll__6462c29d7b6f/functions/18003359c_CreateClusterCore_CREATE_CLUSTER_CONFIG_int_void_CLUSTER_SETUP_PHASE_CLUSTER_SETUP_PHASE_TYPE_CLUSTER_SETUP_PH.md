# CreateClusterCore(_CREATE_CLUSTER_CONFIG *,int (*)(void *,_CLUSTER_SETUP_PHASE,_CLUSTER_SETUP_PHASE_TYPE,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,wchar_t const *,ulong),void *,_HCLUSTER * &)

- ea: `0x18003359c`
- end: `0x180036286`
- name: `?CreateClusterCore@@YAKPEAU_CREATE_CLUSTER_CONFIG@@P6AHPEAXW4_CLUSTER_SETUP_PHASE@@W4_CLUSTER_SETUP_PHASE_TYPE@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@KPEB_WK@Z1AEAPEAU_HCLUSTER@@@Z`
- size: `11498`
- prototype: `unsigned int __fastcall(struct _CREATE_CLUSTER_CONFIG *, int (*)(void *, enum _CLUSTER_SETUP_PHASE, enum _CLUSTER_SETUP_PHASE_TYPE, enum _CLUSTER_SETUP_PHASE_SEVERITY, unsigned int, const wchar_t *, unsigned int), void *, struct _HCLUSTER **)`
- caller_count: `1`
- callee_count: `80`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180041dd0`

## callees

- `0x1800012bc`
- `0x18000140c`
- `0x180002f50`
- `0x180003320`
- `0x180003510`
- `0x180003c14`
- `0x180003c44`
- `0x18001236c`
- `0x1800123b0`
- `0x180019030`
- `0x18001cb44`
- `0x18001cc2c`
- `0x18001ce04`
- `0x18001dbcc`
- `0x18001ef44`
- `0x1800240a8`
- `0x180024d98`
- `0x180028f30`
- `0x180029410`
- `0x180029578`
- `0x180029978`
- `0x180029a04`
- `0x18002a7a0`
- `0x180031728`
- `0x18003180c`
- `0x180031c44`
- `0x180031f74`
- `0x180032718`
- `0x180032bc0`
- `0x18003359c`
- `0x18003628c`
- `0x180036c8c`
- `0x180037278`
- `0x180037824`
- `0x180038494`
- `0x18003901c`
- `0x180039e50`
- `0x18003b190`
- `0x18003b410`
- `0x18003b5c8`
- `0x18003be68`
- `0x18003c2ec`
- `0x18003d85c`
- `0x18003dea8`
- `0x18003e070`
- `0x18003e828`
- `0x18003f114`
- `0x18004036c`
- `0x1800403a4`
- `0x18004046c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034161`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003482b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003482b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800350a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360bf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035790`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180035790`

## string_xrefs

- `0x1800336d7`: `Cluster creation start, pConfig->dwVersion %d.`
- `0x1800336e9`: `CreateClusterCore`
- `0x1800337d2`: `CreateClusterCore`
- `0x1800338a6`: `CreateClusterCore`
- `0x1800338da`: `CreateClusterCore`
- `0x180033957`: `CreateClusterCore`
- `0x1800339f4`: `CreateClusterCore`
- `0x180033c5e`: `CreateClusterCore`
- `0x180033e7b`: `CreateClusterCore`
- `0x180033f34`: `CreateClusterCore`
- `0x180033ff3`: `CreateClusterCore`
- `0x180034040`: `CreateClusterCore`
- `0x1800340a5`: `CreateClusterCore`
- `0x18003418b`: `CreateClusterCore`
- `0x1800342fc`: `CreateClusterCore`
- `0x18003449a`: `CreateClusterCore`
- `0x180034580`: `CreateClusterCore`
- `0x18003471b`: `CreateClusterCore`
- `0x1800347ee`: `CreateClusterCore`
- `0x1800350e7`: `CreateClusterCore`
- `0x180035381`: `CreateClusterCore`
- `0x180035c87`: `CreateClusterCore`
- `0x18003373a`: `Validating Create Cluster Config domaind + credentials information.`
- `0x1800337ed`: `Invalid create cluster configuration, domain/user/pass must all be set or all be null.`
- `0x180033894`: `Create Cluster config credentials information is not available, config version < CLUSAPI_VERSION_GA, treating as all null Credentials`
- `0x1800338c8`: `Cluster management point type requires Active Directory, Validating that all nodes are domain joined.`
- `0x180033acd`: `Not all nodes are domain joined, but credentials were provided.  Configuring Domain-joined cluster on Domainless nodes.`
- `0x180033e69`: `Error in creating cluster. Invalid arguments passed. Error %d. Cannot create ADLess management point on downlevel nodes.`
- `0x180033f22`: `Error in creating cluster. Invalid arguments passed. Error %d. Cannot create ADOnly management point on downlevel nodes.`
- `0x180034093`: `Error in create Cluster: Unable to parse cluster name %ws. Error %d.`
- `0x180034179`: `Error in create cluster. Node name same as cluster name %ws.`
- `0x1800342ea`: `Error in create cluster. Invalid IP address specified.`
- `0x180034488`: `Create Cluster Phase Count: %d.`
- `0x18003625a`: `Create cluster %ws failed as no nodes are valid to proceed further.`
- `0x180035d4f`: `Failed to create cluster name %ws in AD. Error %d.`
- `0x180035d85`: `Failed to create empty cluster %ws`
- `0x180035db1`: `Failed to create or update one or more core resource types.`
- `0x180035e13`: `Failed to create Cluster Group.`
- `0x180035ec1`: `Failed to create Available Storage group.`
- `0x180035fcc`: `Failed to copy undecorated IP address resource name %ws.`
- `0x1800350d5`: `Failed to create IP address %ws/%d`
- `0x180036088`: `Failed to create any IP addresses`
- `0x1800360c8`: `Failed to create network name %ws`
- `0x180035827`: `clusapi!CreateClusterCore`
- `0x180035897`: `clusapi!CreateClusterCore`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=3
__int64 __fastcall CreateClusterCore(
        struct _CREATE_CLUSTER_CONFIG *a1,
        DWORD (__stdcall *a2)(HCLUSTER hCluster, LPCWSTR lpszClusterStorageEnclosureName, DWORD dwTimeout, DWORD dwFlags),
        void *a3,
        struct _HCLUSTER **a4)
{
  struct _CREATE_CLUSTER_CONFIG *v5; // r13
  _BYTE *p_fEmptyCluster; // rsi
  wchar_t *v7; // rbx
  char v8; // r15
  _WORD *v9; // rax
  char v10; // r12
  PCWSTR lpszClusterName; // rax
  _WORD *v12; // rax
  wchar_t *v13; // rcx
  DWORD n; // edi
  int IsMachineDomainJoined; // eax
  unsigned int v17; // esi
  wchar_t *v18; // rcx
  wchar_t *v19; // rcx
  struct _CREATE_CLUSTER_CONFIG *v20; // r15
  PCWSTR **p_ppszNodeNames; // rdi
  __int64 p_pIpEntries; // r8
  DWORD dwVersion; // edx
  CLUSTER_MGMT_POINT_RESTYPE managementPointResType; // ecx
  __int32 v25; // ecx
  wchar_t *v26; // rcx
  int v27; // r9d
  wchar_t *v28; // rcx
  const wchar_t *v29; // rdx
  _WORD *v30; // rax
  unsigned int *v31; // r10
  char v32; // r12
  int NodeClusterUpgradeVersionAllNodes; // edi
  unsigned __int16 v34; // cx
  wchar_t *v35; // rcx
  wchar_t *v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // esi
  const WCHAR *v39; // r9
  wchar_t *v40; // rcx
  PCWSTR *ppszNodeNames; // rdi
  DWORD i; // ebx
  wchar_t *v43; // rcx
  wchar_t *v44; // rcx
  PCLUSTER_IP_ENTRY pIpEntries; // rax
  DWORD cIpEntries; // ecx
  wchar_t *v47; // rcx
  DWORD (__stdcall *v48)(HCLUSTER, LPCWSTR, DWORD, DWORD); // r15
  int v49; // r8d
  int v50; // ecx
  int v51; // edx
  BOOLEAN v52; // bl
  struct CreateClusterADState *v53; // rdi
  const wchar_t *v54; // rax
  const wchar_t ***v55; // r15
  wchar_t *v56; // rsi
  char v57; // bl
  const wchar_t *v58; // r9
  const wchar_t *v59; // rax
  const wchar_t *v60; // rcx
  CLUSTER_MGMT_POINT_TYPE v61; // r12d
  __int64 EmptyCluster; // rax
  HKEY ClusterKey; // rbx
  DWORD LastError; // ebx
  __int64 v65; // rdx
  wchar_t *v66; // rcx
  struct _CREATE_CLUSTER_CONFIG *v67; // r15
  unsigned int updated; // eax
  unsigned int v69; // edi
  __int64 v70; // rdx
  wchar_t *v71; // rcx
  __int64 v72; // r9
  __int64 v73; // rax
  unsigned int v74; // eax
  unsigned int v75; // edi
  __int64 v76; // rdx
  wchar_t *v77; // rcx
  unsigned int *p_dwVersion; // rbx
  struct _HRESOURCE *v79; // r15
  struct _HGROUP *v80; // r12
  HCLUSTER *v81; // r12
  int CoreResTypes; // eax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rax
  _DWORD *v87; // r8
  __int64 v88; // rax
  struct _HGROUP *ClusterGroup; // rax
  int v90; // r12d
  int v91; // eax
  int v92; // eax
  int v93; // eax
  __int64 v94; // rax
  const wchar_t *v95; // rax
  struct _HCLUSTER **v96; // r12
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 *v99; // r8
  __int64 v100; // rax
  void *v101; // rax
  int v102; // r12d
  int v103; // eax
  int v104; // eax
  int v105; // edi
  int v106; // eax
  int v107; // eax
  DWORD v108; // ebx
  CLUSTER_MGMT_POINT_TYPE v109; // r12d
  DWORD *v110; // rdi
  char v111; // r13
  DWORD j; // r12d
  __int64 v113; // rax
  const wchar_t *v114; // rax
  int v115; // eax
  __int64 v116; // r15
  PCWSTR lpszIpAddress; // rdi
  __int64 v118; // rax
  const wchar_t *v119; // rax
  int v120; // eax
  struct _HRESOURCE *IPAddress; // rbx
  enum _CLUSTER_SETUP_PHASE_SEVERITY v122; // r8d
  int v123; // eax
  __int64 v124; // r8
  struct CreateClusterADState *v125; // r15
  __int64 v126; // rax
  __int64 v127; // rbx
  wchar_t *v128; // rdi
  __int64 v129; // rax
  int v130; // eax
  struct _HRESOURCE *NetworkName; // rbx
  const WCHAR *v132; // rax
  int v133; // eax
  int v134; // eax
  int v135; // eax
  int v136; // eax
  int v137; // eax
  int v138; // eax
  __int64 v139; // rax
  __int64 v140; // rax
  DWORD v141; // eax
  rsize_t v142; // r9
  __int64 v143; // rdx
  __int64 v144; // rcx
  __int64 v145; // r8
  __int64 v146; // r8
  int v147; // r9d
  unsigned int v148; // ebx
  char v149; // r12
  struct _HCLUSTER **v150; // r15
  struct _HGROUP *v151; // r15
  __int64 v152; // rax
  __int64 v153; // rax
  unsigned int v154; // eax
  enum _CLUSTER_SETUP_PHASE_SEVERITY v155; // r8d
  CLUSTER_GROUP_STATE ClusterGroupState; // eax
  int v157; // r15d
  enum _CLUSTER_SETUP_PHASE_SEVERITY v158; // r8d
  struct _HRESOURCE *v159; // r15
  __int64 v160; // rax
  const wchar_t *v161; // rax
  unsigned int v162; // eax
  enum _CLUSTER_SETUP_PHASE_SEVERITY v163; // r8d
  unsigned int v164; // eax
  enum _CLUSTER_SETUP_PHASE_SEVERITY v165; // r8d
  _QWORD *v166; // rax
  DWORD v167; // r15d
  DWORD *v168; // rcx
  __int64 v169; // rdx
  unsigned int v170; // eax
  enum _CLUSTER_SETUP_PHASE_SEVERITY v171; // r8d
  unsigned __int64 m; // r15
  const wchar_t *v173; // rax
  __int64 v174; // rax
  __int64 v175; // rdx
  enum _CLUSTER_SETUP_PHASE_SEVERITY v176; // r8d
  unsigned int v177; // eax
  enum _CLUSTER_SETUP_PHASE_SEVERITY v178; // eax
  _QWORD *v179; // rdx
  DWORD v180; // ebx
  DWORD *k; // r15
  struct _HRESOURCE *v182; // rcx
  unsigned __int64 v183; // rbx
  __int64 v184; // r8
  __int64 v185; // rdx
  ClusNode *v186; // rcx
  __int64 v187; // rdx
  wchar_t *v188; // rcx
  __int64 v189; // rax
  wchar_t *v190; // rcx
  _QWORD *v191; // rax
  int v192; // edx
  _QWORD *v193; // rax
  DWORD v194; // eax
  DWORD v195; // eax
  DWORD v196; // eax
  int v197; // ebx
  __int64 v198; // rax
  __int64 v199; // rax
  int v200; // edx
  const WCHAR *v201; // r9
  __int64 v202; // rbx
  DWORD v203; // eax
  _QWORD *v204; // rax
  int v205; // edx
  _QWORD *v206; // rax
  _QWORD *v207; // rax
  wchar_t *v208; // [rsp+20h] [rbp-2388h]
  wchar_t *v209; // [rsp+20h] [rbp-2388h]
  wchar_t *v210; // [rsp+28h] [rbp-2380h]
  wchar_t *v211; // [rsp+28h] [rbp-2380h]
  wchar_t *v212; // [rsp+28h] [rbp-2380h]
  wchar_t *v213; // [rsp+28h] [rbp-2380h]
  wchar_t *v214; // [rsp+28h] [rbp-2380h]
  wchar_t *v215; // [rsp+30h] [rbp-2378h]
  wchar_t *v216; // [rsp+30h] [rbp-2378h]
  char v217; // [rsp+30h] [rbp-2378h]
  wchar_t *v218; // [rsp+30h] [rbp-2378h]
  CLUSTER_MGMT_POINT_TYPE v219; // [rsp+38h] [rbp-2370h]
  unsigned int v220; // [rsp+50h] [rbp-2358h] BYREF
  wchar_t *v221; // [rsp+58h] [rbp-2350h] BYREF
  CLUSTER_MGMT_POINT_TYPE managementPointType; // [rsp+60h] [rbp-2348h] BYREF
  char v223; // [rsp+64h] [rbp-2344h]
  char v224; // [rsp+65h] [rbp-2343h]
  int v225; // [rsp+68h] [rbp-2340h] BYREF
  char v226; // [rsp+6Ch] [rbp-233Ch]
  BOOLEAN fEmptyCluster; // [rsp+6Dh] [rbp-233Bh]
  bool v228; // [rsp+6Eh] [rbp-233Ah]
  unsigned __int16 v229[2]; // [rsp+70h] [rbp-2338h] BYREF
  unsigned int v230; // [rsp+74h] [rbp-2334h] BYREF
  _BYTE v231[16]; // [rsp+78h] [rbp-2330h] BYREF
  unsigned int v232[4]; // [rsp+88h] [rbp-2320h] BYREF
  __int64 v233; // [rsp+98h] [rbp-2310h]
  CLUSTER_CLOUD_TYPE v234; // [rsp+A0h] [rbp-2308h] BYREF
  struct _HCLUSTER **v235; // [rsp+A8h] [rbp-2300h]
  HGROUP hGroup; // [rsp+B0h] [rbp-22F8h]
  wchar_t *v237; // [rsp+B8h] [rbp-22F0h] BYREF
  HKEY v238; // [rsp+C0h] [rbp-22E8h]
  PCLUSTER_IP_ENTRY *v239; // [rsp+C8h] [rbp-22E0h] BYREF
  struct _CREATE_CLUSTER_CONFIG *v240; // [rsp+D0h] [rbp-22D8h]
  void *Block; // [rsp+D8h] [rbp-22D0h]
  unsigned int *p_cNodes; // [rsp+E0h] [rbp-22C8h]
  _QWORD v243[2]; // [rsp+E8h] [rbp-22C0h] BYREF
  int v244; // [rsp+F8h] [rbp-22B0h]
  int v245; // [rsp+FCh] [rbp-22ACh]
  int v246; // [rsp+100h] [rbp-22A8h]
  int v247; // [rsp+104h] [rbp-22A4h]
  __int64 v248; // [rsp+108h] [rbp-22A0h]
  int v249; // [rsp+110h] [rbp-2298h] BYREF
  void *Source[2]; // [rsp+118h] [rbp-2290h] BYREF
  __int64 v251; // [rsp+128h] [rbp-2280h]
  PCWSTR **v252; // [rsp+130h] [rbp-2278h] BYREF
  DWORD *p_cIpEntries; // [rsp+138h] [rbp-2270h]
  struct CreateClusterADState *v254; // [rsp+140h] [rbp-2268h] BYREF
  HRESOURCE hResource; // [rsp+148h] [rbp-2260h]
  struct CreateClusterADState *v256; // [rsp+150h] [rbp-2258h] BYREF
  HLOCAL hMem; // [rsp+158h] [rbp-2250h]
  struct _CREATE_CLUSTER_CONFIG *v258; // [rsp+160h] [rbp-2248h]
  __int64 v259[2]; // [rsp+168h] [rbp-2240h] BYREF
  int v260; // [rsp+178h] [rbp-2230h] BYREF
  int v261; // [rsp+17Ch] [rbp-222Ch] BYREF
  int v262; // [rsp+180h] [rbp-2228h] BYREF
  __int64 v263; // [rsp+188h] [rbp-2220h] BYREF
  _DWORD v264[2]; // [rsp+190h] [rbp-2218h] BYREF
  struct _CREATE_CLUSTER_CONFIG *v265; // [rsp+198h] [rbp-2210h]
  struct _HCLUSTER **v266; // [rsp+1A0h] [rbp-2208h]
  _QWORD v267[2]; // [rsp+1A8h] [rbp-2200h] BYREF
  void *v268; // [rsp+1B8h] [rbp-21F0h]
  _QWORD v269[4]; // [rsp+1C0h] [rbp-21E8h] BYREF
  ClusRtl::ExceptionMsg *v270; // [rsp+1E0h] [rbp-21C8h] BYREF
  int v271[20]; // [rsp+210h] [rbp-2198h] BYREF
  __int128 v272; // [rsp+260h] [rbp-2148h] BYREF
  __int64 v273; // [rsp+270h] [rbp-2138h]
  __int64 v274; // [rsp+278h] [rbp-2130h]
  __int128 v275; // [rsp+280h] [rbp-2128h] BYREF
  __int64 v276; // [rsp+290h] [rbp-2118h]
  __int64 v277; // [rsp+298h] [rbp-2110h]
  _BYTE v278[32]; // [rsp+2A0h] [rbp-2108h] BYREF
  __int128 Destination; // [rsp+2C0h] [rbp-20E8h] BYREF
  _BYTE v280[272]; // [rsp+2D0h] [rbp-20D8h] BYREF
  _BYTE v281[272]; // [rsp+3E0h] [rbp-1FC8h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+4F0h] [rbp-1EB8h] BYREF
  _BYTE v283[272]; // [rsp+600h] [rbp-1DA8h] BYREF
  _BYTE v284[272]; // [rsp+710h] [rbp-1C98h] BYREF
  _BYTE v285[272]; // [rsp+820h] [rbp-1B88h] BYREF
  _BYTE v286[272]; // [rsp+930h] [rbp-1A78h] BYREF
  _BYTE v287[272]; // [rsp+A40h] [rbp-1968h] BYREF
  _BYTE v288[272]; // [rsp+B50h] [rbp-1858h] BYREF
  _BYTE v289[272]; // [rsp+C60h] [rbp-1748h] BYREF
  _BYTE v290[272]; // [rsp+D70h] [rbp-1638h] BYREF
  _BYTE v291[272]; // [rsp+E80h] [rbp-1528h] BYREF
  _BYTE v292[272]; // [rsp+F90h] [rbp-1418h] BYREF
  _BYTE v293[272]; // [rsp+10A0h] [rbp-1308h] BYREF
  _BYTE v294[272]; // [rsp+11B0h] [rbp-11F8h] BYREF
  _BYTE v295[272]; // [rsp+12C0h] [rbp-10E8h] BYREF
  _BYTE v296[272]; // [rsp+13D0h] [rbp-FD8h] BYREF
  _BYTE v297[272]; // [rsp+14E0h] [rbp-EC8h] BYREF
  _BYTE v298[272]; // [rsp+15F0h] [rbp-DB8h] BYREF
  _BYTE v299[272]; // [rsp+1700h] [rbp-CA8h] BYREF
  _BYTE v300[272]; // [rsp+1810h] [rbp-B98h] BYREF
  _BYTE v301[272]; // [rsp+1920h] [rbp-A88h] BYREF
  _BYTE v302[272]; // [rsp+1A30h] [rbp-978h] BYREF
  _BYTE v303[272]; // [rsp+1B40h] [rbp-868h] BYREF
  _BYTE v304[272]; // [rsp+1C50h] [rbp-758h] BYREF
  _BYTE v305[272]; // [rsp+1D60h] [rbp-648h] BYREF
  _BYTE v306[272]; // [rsp+1E70h] [rbp-538h] BYREF
  _BYTE v307[272]; // [rsp+1F80h] [rbp-428h] BYREF
  __int64 v308[10]; // [rsp+2090h] [rbp-318h] BYREF
  int v309; // [rsp+20E0h] [rbp-2C8h] BYREF
  char v310[124]; // [rsp+20E4h] [rbp-2C4h] BYREF
  wchar_t v311[256]; // [rsp+2160h] [rbp-248h] BYREF

  v235 = a4;
  v240 = a1;
  v265 = a1;
  v5 = a1;
  v258 = a1;
  v266 = a4;
  p_fEmptyCluster = &a1->fEmptyCluster;
  v238 = (HKEY)&a1->fEmptyCluster;
  fEmptyCluster = a1->fEmptyCluster;
  *(_OWORD *)v232 = 0;
  v233 = 0;
  *(_OWORD *)Source = 0;
  v251 = 0;
  Destination = 0;
  v272 = 0;
  v273 = 0;
  v274 = 7;
  LOWORD(v272) = 0;
  v269[0] = &cxl::TimeSpan::`vftable';
  v269[1] = 0;
  v269[2] = &cxl::MonotonicDateTime::`vftable';
  v269[3] = *(_QWORD *)(cxl::MonotonicDateTime::get_Now(v259) + 8);
  v221 = 0;
  v7 = 0;
  v237 = 0;
  v234 = CLUSTER_CLOUD_TYPE_NONE;
  std::map<unsigned long,std::wstring>::map<unsigned long,std::wstring>(v231);
  TraceMsg(4, 0, L"CreateClusterCore", 1885, L"Cluster creation start, pConfig->dwVersion %d.", v5->dwVersion);
  if ( fEmptyCluster )
  {
    managementPointType = CLUSTER_MGMT_POINT_TYPE_NONE;
  }
  else
  {
    if ( a1->dwVersion < 0x702 )
    {
      managementPointType = CLUSTER_MGMT_POINT_TYPE_CNO;
      v223 = 0;
      v226 = 0;
      v8 = 1;
      v224 = 1;
      goto LABEL_20;
    }
    managementPointType = a1->managementPointType;
  }
  v223 = 0;
  v226 = 0;
  v8 = 1;
  v224 = 1;
  if ( a1->dwVersion < 0xC05 )
  {
LABEL_20:
    v10 = 1;
    TraceMsg(
      4,
      0,
      L"CreateClusterCore",
      1937,
      L"Create Cluster config credentials information is not available, config version < CLUSAPI_VERSION_GA, treating as a"
       "ll null Credentials");
    goto LABEL_21;
  }
  TraceMsg(4, 0, L"CreateClusterCore", 1909, L"Validating Create Cluster Config domaind + credentials information.");
  v9 = *(_WORD **)&a1[1].dwVersion;
  if ( !v9 )
  {
    if ( !a1[1].lpszClusterName && !*(_QWORD *)&a1[1].cNodes )
    {
      TraceMsg(4, 0, L"CreateClusterCore", 1914, L"All Credentials are empty.");
      v10 = 1;
      goto LABEL_21;
    }
LABEL_16:
    TraceMsg(
      2,
      0,
      L"CreateClusterCore",
      1930,
      L"Invalid create cluster configuration, domain/user/pass must all be set or all be null.");
    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
    CTSmartPtr_PolicyLocalMem::DestroyMem(0);
    v13 = v221;
    v221 = 0;
    CTSmartPtr_PolicyLocalMem::DestroyMem(v13);
    std::wstring::_Tidy_deallocate(&v272);
    std::vector<unsigned char>::_Tidy(Source);
    if ( *(_QWORD *)v232 )
      std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
    return 87;
  }
  if ( !*v9 )
    goto LABEL_16;
  lpszClusterName = a1[1].lpszClusterName;
  if ( !lpszClusterName )
    goto LABEL_16;
  if ( !*lpszClusterName )
    goto LABEL_16;
  v12 = *(_WORD **)&a1[1].cNodes;
  if ( !v12 || !*v12 )
    goto LABEL_16;
  v10 = 0;
  TraceMsg(4, 0, L"CreateClusterCore", 1924, L"All Credentials are valid.");
  v223 = 1;
LABEL_21:
  if ( ((managementPointType - 1) & 0xFFFFFFFD) != 0 )
  {
LABEL_342:
    try
    {
      v20 = v240;
      p_ppszNodeNames = &v240->ppszNodeNames;
      v252 = &v240->ppszNodeNames;
      p_cNodes = &v240->cNodes;
      GetClusterCloudType(v240->cNodes, v240->ppszNodeNames, &v234);
    }
    catch ( ClusRtl::ExceptionMsg *v270 )
    {
      TraceMsg(
        2,
        0,
        L"CreateClusterCore",
        1997,
        L"Exception - Error getting Cluster Node Type.  Error: %d, Msg: %s",
        *((_DWORD *)v270 + 64),
        v270);
      v234 = CLUSTER_CLOUD_TYPE_NONE;
      v7 = v237;
      v5 = v258;
      v20 = v258;
      v240 = v258;
      v235 = v266;
      p_fEmptyCluster = v238;
      p_ppszNodeNames = v252;
    }
    p_pIpEntries = 7;
    dwVersion = v20->dwVersion;
    if ( v20->dwVersion < 0xA00 )
    {
      if ( v234 )
      {
        v27 = 1;
        if ( v234 == CLUSTER_CLOUD_TYPE_AZURE )
        {
LABEL_51:
          v230 = v27;
          if ( (dwVersion & 0xFFFFFF00) < 0x600 )
          {
            TraceMsg(
              2,
              0,
              L"CreateClusterCore",
              2030,
              L"Error in creating cluster. ClusAPI client is of an older version of windows.");
            std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
            CTSmartPtr_PolicyLocalMem::DestroyMem(v7);
            v28 = v221;
            v221 = 0;
            CTSmartPtr_PolicyLocalMem::DestroyMem(v28);
            std::wstring::_Tidy_deallocate(&v272);
            std::vector<unsigned char>::_Tidy(Source);
            if ( *(_QWORD *)v232 )
              std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
            return 50;
          }
          v275 = 0;
          v276 = 0;
          v277 = 7;
          LOWORD(v275) = 0;
          if ( !*p_cNodes )
          {
            v29 = L"Node count is zero";
LABEL_57:
            std::wstring::assign(&v275, v29, p_pIpEntries);
LABEL_304:
            v189 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v275);
            TraceMsg(
              2,
              0,
              L"CreateClusterCore",
              2090,
              L"Error in creating cluster. Invalid arguments passed: %s. Error %d. ",
              v189,
              87);
            std::wstring::_Tidy_deallocate(&v275);
            std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
            CTSmartPtr_PolicyLocalMem::DestroyMem(v7);
            v190 = v221;
            v221 = 0;
            CTSmartPtr_PolicyLocalMem::DestroyMem(v190);
            std::wstring::_Tidy_deallocate(&v272);
            std::vector<unsigned char>::_Tidy(Source);
            if ( *(_QWORD *)v232 )
              std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
            return 87;
          }
          if ( !*p_ppszNodeNames )
          {
            v29 = L"Node list is null";
            goto LABEL_57;
          }
          v30 = v20->lpszClusterName;
          if ( !v30 )
          {
            v29 = L"Cluster Name is null";
            goto LABEL_57;
          }
          if ( !*v30 )
          {
            v29 = L"Cluster Name is empty";
            goto LABEL_57;
          }
          if ( *p_fEmptyCluster )
          {
            if ( v20->cIpEntries || (p_pIpEntries = (__int64)&v20->pIpEntries, v239 = &v20->pIpEntries, v20->pIpEntries) )
            {
              std::wstring::assign(&v275, L"Empty Cluster flag set, but IPs were specified", p_pIpEntries);
              goto LABEL_304;
            }
          }
          else
          {
            if ( IsManagementPointIPDependent(managementPointType, v27) && (!v20->cIpEntries || !v20->pIpEntries) )
            {
              v29 = L"Cluster requires IPs, but no IPs were specified";
              goto LABEL_57;
            }
            p_pIpEntries = (__int64)&v5->pIpEntries;
            v239 = &v5->pIpEntries;
          }
          if ( (unsigned int)managementPointType > CLUSTER_MGMT_POINT_TYPE_CNO_ONLY )
          {
            v29 = L"Invalid ManagementPointType";
            goto LABEL_57;
          }
          v228 = IsManagementPointIPDependent(managementPointType, v27);
          if ( v228 )
          {
            if ( !v20->cIpEntries || !*(_QWORD *)p_pIpEntries )
            {
              v29 = L"ManagementPointType does require IPs, but no IPS were specified";
              goto LABEL_57;
            }
          }
          else if ( v20->cIpEntries || v20->pIpEntries )
          {
            v29 = L"ManagementPointType does not require IPs, but IPs were specified";
            goto LABEL_57;
          }
          v229[0] = 0;
          v32 = 0;
          v229[0] = GetNodeClusterMajorVersionAllNodes(*p_ppszNodeNames, *v31);
          NodeClusterUpgradeVersionAllNodes = (unsigned __int16)GetNodeClusterUpgradeVersionAllNodes(
                                                                  *p_ppszNodeNames,
                                                                  *p_cNodes);
          if ( managementPointType != CLUSTER_MGMT_POINT_TYPE_DNS_ONLY && (*p_fEmptyCluster || managementPointType) )
          {
            v34 = v229[0];
          }
          else
          {
            v34 = v229[0];
            if ( v229[0] < 8u )
            {
              LODWORD(v210) = 87;
              TraceMsg(
                2,
                0,
                L"CreateClusterCore",
                2108,
                L"Error in creating cluster. Invalid arguments passed. Error %d. Cannot create ADLess management point on "
                 "downlevel nodes.",
                v210);
              std::wstring::_Tidy_deallocate(&v275);
              std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
              CTSmartPtr_PolicyLocalMem::DestroyMem(v7);
              v35 = v221;
              v221 = 0;
              CTSmartPtr_PolicyLocalMem::DestroyMem(v35);
              std::wstring::_Tidy_deallocate(&v272);
              std::vector<unsigned char>::_Tidy(Source);
              if ( *(_QWORD *)v232 )
                std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
              return 87;
            }
          }
          if ( managementPointType == CLUSTER_MGMT_POINT_TYPE_CNO_ONLY && v34 < 9u )
          {
            LODWORD(v210) = 87;
            TraceMsg(
              2,
              0,
              L"CreateClusterCore",
              2113,
              L"Error in creating cluster. Invalid arguments passed. Error %d. Cannot create ADOnly management point on downlevel nodes.",
              v210);
            std::wstring::_Tidy_deallocate(&v275);
            std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
            CTSmartPtr_PolicyLocalMem::DestroyMem(v7);
            v36 = v221;
            v221 = 0;
            CTSmartPtr_PolicyLocalMem::DestroyMem(v36);
            std::wstring::_Tidy_deallocate(&v272);
            std::vector<unsigned char>::_Tidy(Source);
            if ( *(_QWORD *)v232 )
              std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
            return 87;
          }
          if ( v34 > 0xEu )
          {
            LODWORD(v210) = v34;
            TraceMsg(
              4,
              0,
              L"CreateClusterCore",
              2130,
              L"The nodes would form a cluster at version %d.%d but this client only supports creating at %d.%d, creating "
               "in downlevel mode.",
              v210,
              NodeClusterUpgradeVersionAllNodes,
              14,
              1);
            v32 = 1;
            v34 = v229[0];
          }
          if ( v34 > 0xBu || (v225 = 0, v34 == 11) && (unsigned __int16)NodeClusterUpgradeVersionAllNodes >= 2u )
          {
            LODWORD(v215) = NodeClusterUpgradeVersionAllNodes;
            LODWORD(v210) = v34;
            TraceMsg(
              4,
              0,
              L"CreateClusterCore",
              2137,
              L"Cluster creation version is %d.%d, enabling long password support.",
              v210,
              v215);
            v225 = 1;
          }
          v37 = ClRtlParseDistinguishedName(v20->lpszClusterName, &v221, &v237);
          v38 = v37;
          v220 = v37;
          if ( v37 )
          {
            v39 = &base;
            if ( v20->lpszClusterName )
              v39 = v20->lpszClusterName;
            LODWORD(v215) = v37;
            TraceMsg(
              2,
              0,
              L"CreateClusterCore",
              2151,
              L"Error in create Cluster: Unable to parse cluster name %ws. Error %d.",
              v39,
              v215);
            std::wstring::_Tidy_deallocate(&v275);
            std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
            CTSmartPtr_PolicyLocalMem::DestroyMem(v237);
            v40 = v221;
            v221 = 0;
            CTSmartPtr_PolicyLocalMem::DestroyMem(v40);
            std::wstring::_Tidy_deallocate(&v272);
            std::vector<unsigned char>::_Tidy(Source);
            if ( *(_QWORD *)v232 )
              std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
            return v38;
          }
          ppszNodeNames = v20->ppszNodeNames;
          for ( i = v20->cNodes; i; --i )
          {
            if ( !*ppszNodeNames || !**ppszNodeNames )
            {
              std::wstring::_Tidy_deallocate(&v275);
              std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
              CTSmartPtr_PolicyLocalMem::DestroyMem(v237);
              v44 = v221;
              v221 = 0;
              CTSmartPtr_PolicyLocalMem::DestroyMem(v44);
              std::wstring::_Tidy_deallocate(&v272);
              std::vector<unsigned char>::_Tidy(Source);
              if ( *(_QWORD *)v232 )
                std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
              return 87;
            }
            if ( !(unsigned int)_o__wcsicmp(v221) )
            {
              TraceMsg(
                2,
                0,
                L"CreateClusterCore",
                2170,
                L"Error in create cluster. Node name same as cluster name %ws.",
                v221);
              std::wstring::_Tidy_deallocate(&v275);
              std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
              CTSmartPtr_PolicyLocalMem::DestroyMem(v237);
              v43 = v221;
              v221 = 0;
              CTSmartPtr_PolicyLocalMem::DestroyMem(v43);
              std::wstring::_Tidy_deallocate(&v272);
              std::vector<unsigned char>::_Tidy(Source);
              if ( *(_QWORD *)v232 )
                std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
              return 87;
            }
            ++ppszNodeNames;
          }
          pIpEntries = v240->pIpEntries;
          p_cIpEntries = &v240->cIpEntries;
          cIpEntries = v240->cIpEntries;
          if ( cIpEntries )
          {
            while ( pIpEntries->lpszIpAddress && *pIpEntries->lpszIpAddress && pIpEntries->dwPrefixLength )
            {
              ++pIpEntries;
              if ( !--cIpEntries )
                goto LABEL_126;
            }
            TraceMsg(2, 0, L"CreateClusterCore", 2190, L"Error in create cluster. Invalid IP address specified.");
            std::wstring::_Tidy_deallocate(&v275);
            std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
            CTSmartPtr_PolicyLocalMem::DestroyMem(v237);
            v47 = v221;
            v221 = 0;
            CTSmartPtr_PolicyLocalMem::DestroyMem(v47);
            std::wstring::_Tidy_deallocate(&v272);
            std::vector<unsigned char>::_Tidy(Source);
            if ( *(_QWORD *)v232 )
              std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
            return 87;
          }
LABEL_126:
          hGroup = 0;
          hMem = 0;
          Block = 0;
          v268 = 0;
          hResource = 0;
          v258 = 0;
          v238 = 0;
          v267[0] = &v240->cIpEntries;
          v48 = a2;
          if ( !a2 )
            v48 = get_startup_argv_mode;
          v49 = *p_cNodes + 2 * (*p_cNodes + 2);
          if ( managementPointType )
          {
            switch ( managementPointType )
            {
              case CLUSTER_MGMT_POINT_TYPE_CNO:
LABEL_132:
                v50 = 2;
                v51 = 2;
                goto LABEL_136;
              case CLUSTER_MGMT_POINT_TYPE_DNS_ONLY:
                v51 = 1;
LABEL_135:
                v50 = 0;
LABEL_136:
                v52 = fEmptyCluster;
                if ( !fEmptyCluster )
                  v49 += v50 + v51 + v228 + 4;
                v243[0] = v48;
                v243[1] = a3;
                v244 = 1;
                v245 = v49;
                v246 = 0;
                v247 = 1;
                v248 = 0;
                LODWORD(v210) = v49;
                TraceMsg(4, 0, L"CreateClusterCore", 2260, L"Create Cluster Phase Count: %d.", v210);
                v256 = 0;
                v53 = 0;
                v254 = 0;
                ClusterGlobalData::ClusterGlobalData((ClusterGlobalData *)v271);
                PhaseManager::StartPhase(v243, 1, v221);
                ClusterGlobalData::Initialize((ClusterGlobalData *)v271, *p_cNodes);
                if ( v226 )
                {
                  HelperFormatMessage(v278, g_ClusapiModule, 30);
                  v54 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v278);
                  PhaseManager::ReportPhaseStatus((PhaseManager *)v243, v54, 0, ClusterSetupPhaseWarning);
                  std::wstring::_Tidy_deallocate(v278);
                }
                PhaseManager::EndPhase((PhaseManager *)v243, 0, ClusterSetupPhaseInformational);
                LODWORD(v211) = *p_cNodes;
                TraceMsg(
                  4,
                  0,
                  L"CreateClusterCore",
                  2294,
                  L"Validating nodes specified to the API. Node count: %d.",
                  v211);
                std::map<unsigned long,std::wstring>::map<unsigned long,std::wstring>(v259);
                v55 = v252;
                ValidateNodeState(
                  (int)v221,
                  *p_cNodes,
                  (int)*v252,
                  (int)v271,
                  (PhaseManager *)v243,
                  (__int64)v232,
                  (__int64)v259);
                if ( *(_QWORD *)v232 == *(_QWORD *)&v232[2] )
                {
                  v206 = (_QWORD *)CTSmartObj<wchar_t *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyLocalMem>>::Get(&v221);
                  ClusRtl::ExceptionMsg::ExceptionMsg(
                    (ClusRtl::ExceptionMsg *)v281,
                    v38,
                    L"Create cluster %ws failed as no nodes are valid to proceed further.",
                    *v206);
                  throw (ClusRtl::ExceptionMsg *)v281;
                }
                GetLocalizedObjectNames(v243, *v55, *p_cNodes, v231);
                if ( v52 || ((managementPointType - 1) & 0xFFFFFFFD) != 0 )
                {
                  v56 = v237;
                  v57 = v223;
                }
                else
                {
                  try
                  {
                    v56 = v237;
                    v57 = v223;
                    if ( v223 )
                    {
                      v58 = *(const wchar_t **)&v240[1].cNodes;
                      v59 = *(const wchar_t **)&v240[1].dwVersion;
                      v60 = v240[1].lpszClusterName;
                    }
                    else
                    {
                      v58 = 0;
                      v59 = 0;
                      v60 = 0;
                    }
                    v220 = CreateClusterNameInAD(
                             (struct PhaseManager *)v243,
                             **v55,
                             v221,
                             v58,
                             v59,
                             v60,
                             v237,
                             0,
                             &v256,
                             v225);
                    if ( v220 )
                    {
                      v191 = (_QWORD *)CTSmartObj<wchar_t *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyLocalMem>>::Get(&v221);
                      LODWORD(v208) = v192;
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)pExceptionObject,
                        v192,
                        L"Failed to create cluster name %ws in AD. Error %d.",
                        *v191,
                        v208);
                      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
                    }
                    CTSmartObj<CreateClusterADState *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(
                      &v254,
                      0);
                    v53 = v256;
                    v254 = v256;
                  }
                  catch ( std::exception )
                  {
                    v207 = (_QWORD *)CTSmartObj<wchar_t *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyLocalMem>>::Get(&v221);
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v283,
                      574,
                      L"Failed to create cluster name %ws in AD, handling std exception",
                      *v207);
                    throw (ClusRtl::ExceptionMsg *)v283;
                  }
                }
                LODWORD(v216) = (__int64)(*(_QWORD *)&v232[2] - *(_QWORD *)v232) >> 3;
                TraceMsg(
                  4,
                  0,
                  L"CreateClusterCore",
                  2348,
                  L"Creating empty cluster %ws. Valid nodes count: %d.",
                  v221,
                  v216);
                v217 = v32;
                v61 = managementPointType;
                EmptyCluster = CreateEmptyCluster(
                                 (_DWORD)v221,
                                 (unsigned int)v232,
                                 (unsigned int)v259,
                                 (unsigned int)v271,
                                 (__int64)v243,
                                 managementPointType,
                                 v217,
                                 v229[0],
                                 (__int64)&v220);
                *v235 = (struct _HCLUSTER *)EmptyCluster;
                if ( !EmptyCluster )
                {
                  v193 = (_QWORD *)CTSmartObj<wchar_t *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyLocalMem>>::Get(&v221);
                  ClusRtl::ExceptionMsg::ExceptionMsg(
                    (ClusRtl::ExceptionMsg *)v284,
                    v220,
                    L"Failed to create empty cluster %ws",
                    *v193);
                  throw (ClusRtl::ExceptionMsg *)v284;
                }
                PhaseManager::StartPhase(v243, 201, v221);
                CCHlpAddClusterProperties(*v235);
                if ( v224 || !v57 || ((v61 - 1) & 0xFFFFFFFD) != 0 )
                {
                  v75 = v220;
                }
                else
                {
                  TraceMsg(
                    4,
                    0,
                    L"CreateClusterCore",
                    2373,
                    L"Domain joined cluster on nodes without domain membership, populating Domain information into cluster DB");
                  ClusterKey = GetClusterKey(*v235, 3u);
                  v263 = (__int64)ClusterKey;
                  if ( !ClusterKey )
                  {
                    LastError = GetLastError();
                    LODWORD(v212) = LastError;
                    TraceMsg(2, 0, L"CreateClusterCore", 2379, L"Failed to obtain cluster root key, error %d.", v212);
                    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v259);
                    ClusterGlobalData::~ClusterGlobalData((ClusterGlobalData *)v271);
                    CTSmartObj<CreateClusterADState *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(
                      &v254,
                      v65);
                    std::wstring::_Tidy_deallocate(&v275);
                    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
                    CTSmartPtr_PolicyLocalMem::DestroyMem(v56);
                    v66 = v221;
                    v221 = 0;
                    CTSmartPtr_PolicyLocalMem::DestroyMem(v66);
                    std::wstring::_Tidy_deallocate(&v272);
                    std::vector<unsigned char>::_Tidy(Source);
                    if ( *(_QWORD *)v232 )
                      std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
                    return LastError;
                  }
                  std::wstring::wstring(v278, (char *)v53 + 72);
                  v67 = v240;
                  updated = UpdateDomainInformationInClusterDB(
                              *v235,
                              ClusterKey,
                              *(_QWORD *)&v240[1].cNodes,
                              *(_QWORD *)&v240[1].dwVersion,
                              (__int64)v240[1].lpszClusterName);
                  v69 = updated;
                  if ( updated )
                  {
                    LODWORD(v213) = updated;
                    TraceMsg(
                      2,
                      0,
                      L"CreateClusterCore",
                      2388,
                      L"Failed to set AD domain information in clusdb, error %d.",
                      v213);
                    std::wstring::_Tidy_deallocate(v278);
                    ClusterRegCloseKeyCommon(ClusterKey, 1);
                    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v259);
                    ClusterGlobalData::~ClusterGlobalData((ClusterGlobalData *)v271);
                    CTSmartObj<CreateClusterADState *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(
                      &v254,
                      v70);
                    std::wstring::_Tidy_deallocate(&v275);
                    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
                    CTSmartPtr_PolicyLocalMem::DestroyMem(v56);
                    v71 = v221;
                    v221 = 0;
                    CTSmartPtr_PolicyLocalMem::DestroyMem(v71);
                    std::wstring::_Tidy_deallocate(&v272);
                    std::vector<unsigned char>::_Tidy(Source);
                    if ( *(_QWORD *)v232 )
                      std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
                    return v69;
                  }
                  v72 = *(_QWORD *)&v67[1].cNodes;
                  v73 = -1;
                  do
                    ++v73;
                  while ( *(_WORD *)(v72 + 2 * v73) );
                  v74 = ClusterRegSetValueEx((int)ClusterKey, (int)L"ADDomainName", 1, v72, 2 * (int)v73 + 2, 0);
                  v75 = v74;
                  if ( v74 )
                  {
                    LODWORD(v214) = v74;
                    TraceMsg(
                      2,
                      0,
                      L"CreateClusterCore",
                      2399,
                      L"Failed to set AD domain name in clusdb, error %d.",
                      v214);
                    std::wstring::_Tidy_deallocate(v278);
                    ClusterRegCloseKeyCommon(ClusterKey, 1);
                    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v259);
                    ClusterGlobalData::~ClusterGlobalData((ClusterGlobalData *)v271);
                    CTSmartObj<CreateClusterADState *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(
                      &v254,
                      v76);
                    std::wstring::_Tidy_deallocate(&v275);
                    std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
                    CTSmartPtr_PolicyLocalMem::DestroyMem(v56);
                    v77 = v221;
                    v221 = 0;
                    CTSmartPtr_PolicyLocalMem::DestroyMem(v77);
                    std::wstring::_Tidy_deallocate(&v272);
                    std::vector<unsigned char>::_Tidy(Source);
                    if ( *(_QWORD *)v232 )
                      std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
                    return v75;
                  }
                  std::wstring::_Tidy_deallocate(v278);
                  ClusterRegCloseKeyCommon(ClusterKey, 1);
                }
                PhaseManager::EndPhase((PhaseManager *)v243, 0, ClusterSetupPhaseInformational);
                if ( fEmptyCluster )
                {
                  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v259);
                  p_dwVersion = &v240->dwVersion;
                  v79 = 0;
                  v80 = 0;
                }
                else
                {
                  PhaseManager::StartPhase(v243, 202, v221);
                  v81 = v235;
                  CoreResTypes = CreateCoreResTypes(v235, v229, v231, 0);
                  if ( CoreResTypes )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v285,
                      CoreResTypes,
                      L"Failed to create or update one or more core resource types.");
                    throw (ClusRtl::ExceptionMsg *)v285;
                  }
                  PhaseManager::EndPhase((PhaseManager *)v243, 0, ClusterSetupPhaseInformational);
                  v220 = 14200;
                  v83 = std::map<unsigned long,std::wstring>::operator[](v231, &v220);
                  v84 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v83);
                  PhaseManager::StartPhase(v243, 203, v84);
                  v238 = GetClusterKey(*v81, 2u);
                  if ( !v238 )
                  {
                    v194 = GetLastError();
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v286,
                      v194,
                      L"Failed to obtain Cluster Root Key.");
                    throw (ClusRtl::ExceptionMsg *)v286;
                  }
                  if ( *((_WORD *)*v81 + 162) < 7u )
                  {
                    v261 = 14200;
                    v88 = std::map<unsigned long,std::wstring>::operator[](v231, &v261);
                    v86 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v88);
                    v87 = 0;
                  }
                  else
                  {
                    v264[0] = 1;
                    v264[1] = 1;
                    v260 = 14200;
                    v85 = std::map<unsigned long,std::wstring>::operator[](v231, &v260);
                    v86 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v85);
                    v87 = v264;
                  }
                  ClusterGroup = (struct _HGROUP *)CreateClusterGroupEx(*v81, v86, v87);
                  v90 = (int)ClusterGroup;
                  hGroup = ClusterGroup;
                  if ( !ClusterGroup )
                  {
                    v195 = GetLastError();
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v287,
                      v195,
                      L"Failed to create Cluster Group.");
                    throw (ClusRtl::ExceptionMsg *)v287;
                  }
                  v91 = AddGroupProperties(ClusterGroup);
                  if ( v91 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v288,
                      v91,
                      L"Failed to set properties on Cluster Group.");
                    throw (ClusRtl::ExceptionMsg *)v288;
                  }
                  v220 = 0;
                  v92 = ClusterGroupControlEx(v90, 0, 50331705, 0, 0, (__int64)v308, 80, (__int64)&v220, 0);
                  if ( v92 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v289,
                      v92,
                      L"Failed to obtain GUID for Cluster Group.");
                    throw (ClusRtl::ExceptionMsg *)v289;
                  }
                  v93 = ClusterRegSetValueEx((int)v238, (int)L"ClusterGroup", 1, (int)v308, v220, 0);
                  if ( v93 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v290,
                      v93,
                      L"Failed to set GUID for Cluster Group.");
                    throw (ClusRtl::ExceptionMsg *)v290;
                  }
                  v249 = 14207;
                  v94 = std::map<unsigned long,std::wstring>::operator[](v231, &v249);
                  v95 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v94);
                  PhaseManager::ContinuePhase((PhaseManager *)v243, v95, 0, ClusterSetupPhaseInformational);
                  v96 = v235;
                  if ( *((_WORD *)*v235 + 162) < 7u )
                  {
                    v262 = 14207;
                    v100 = std::map<unsigned long,std::wstring>::operator[](v231, &v262);
                    v98 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v100);
                    v99 = 0;
                  }
                  else
                  {
                    v263 = 0x200000001LL;
                    v249 = 14207;
                    v97 = std::map<unsigned long,std::wstring>::operator[](v231, &v249);
                    v98 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v97);
                    v99 = &v263;
                  }
                  v101 = (void *)CreateClusterGroupEx(*v96, v98, v99);
                  v102 = (int)v101;
                  hMem = v101;
                  if ( !v101 )
                  {
                    v196 = GetLastError();
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v291,
                      v196,
                      L"Failed to create Available Storage group.");
                    throw (ClusRtl::ExceptionMsg *)v291;
                  }
                  v103 = AddGroupProperties((HGROUP)v101);
                  if ( v103 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v292,
                      v103,
                      L"Failed to set properties on Available Storage group.");
                    throw (ClusRtl::ExceptionMsg *)v292;
                  }
                  v104 = ClusterGroupControlEx(v102, 0, 50331705, 0, 0, (__int64)v308, 80, (__int64)&v220, 0);
                  if ( v104 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v293,
                      v104,
                      L"Failed to obtain GUID for Available Storage group.");
                    throw (ClusRtl::ExceptionMsg *)v293;
                  }
                  v105 = (int)v238;
                  v106 = ClusterRegSetValueEx((int)v238, (int)L"AvailableStorage", 1, (int)v308, v220, 0);
                  if ( v106 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v294,
                      v106,
                      L"Failed to set GUID for Available Storage group.");
                    throw (ClusRtl::ExceptionMsg *)v294;
                  }
                  v107 = SetGroupFailoverThreshold(v102);
                  v108 = v107;
                  if ( v107 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v295,
                      v107,
                      L"Failed to set Failover Threshold for Available Storage group.");
                    throw (ClusRtl::ExceptionMsg *)v295;
                  }
                  PhaseManager::EndPhase((PhaseManager *)v243, 0, ClusterSetupPhaseInformational);
                  v109 = managementPointType;
                  if ( managementPointType )
                  {
                    if ( v228 )
                    {
                      v110 = p_cIpEntries;
                      Block = operator new[](saturated_mul(*p_cIpEntries, 8u));
                      v268 = Block;
                      memset_0(Block, 0, 8LL * *v110);
                      v111 = 0;
                      for ( j = 0; j < *v110; ++j )
                      {
                        if ( j )
                        {
                          v116 = j;
                          lpszIpAddress = (*v239)[j].lpszIpAddress;
                          LODWORD(v252) = 14203;
                          v118 = std::map<unsigned long,std::wstring>::operator[](v231, &v252);
                          v119 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v118);
                          v120 = StringCchPrintfW(v311, 0x100u, v119, lpszIpAddress);
                          if ( v120 < 0 )
                          {
                            if ( (v120 & 0x1FFF0000) != 0x70000 || (v200 = (unsigned __int16)v120, !(_WORD)v120) )
                              v200 = v120;
                            v201 = &base;
                            if ( (*v239)[j].lpszIpAddress )
                              v201 = (*v239)[j].lpszIpAddress;
                            LODWORD(v209) = (*v239)[j].dwPrefixLength;
                            ClusRtl::ExceptionMsg::ExceptionMsg(
                              (ClusRtl::ExceptionMsg *)v297,
                              v200,
                              L"Failed to construct decorated IP address resource name for the specified IP address %ws/%d.",
                              v201,
                              v209);
                            throw (ClusRtl::ExceptionMsg *)v297;
                          }
                          PhaseManager::ContinuePhase((PhaseManager *)v243, v311, 0, ClusterSetupPhaseInformational);
                        }
                        else
                        {
                          v220 = 14202;
                          v113 = std::map<unsigned long,std::wstring>::operator[](v231, &v220);
                          v114 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v113);
                          v115 = StringCchCopyW(v311, 0x100u, v114);
                          if ( v115 < 0 )
                          {
                            if ( (v115 & 0x1FFF0000) != 0x70000 || (v197 = (unsigned __int16)v115, !(_WORD)v115) )
                              v197 = v115;
                            v225 = 14202;
                            v198 = std::map<unsigned long,std::wstring>::operator[](v231, &v225);
                            v199 = std::wstring::c_str(v198);
                            ClusRtl::ExceptionMsg::ExceptionMsg(
                              (ClusRtl::ExceptionMsg *)v296,
                              v197,
                              L"Failed to copy undecorated IP address resource name %ws.",
                              v199);
                            throw (ClusRtl::ExceptionMsg *)v296;
                          }
                          PhaseManager::StartPhase(v243, 204, v311);
                          v116 = 0;
                        }
                        IPAddress = (struct _HRESOURCE *)CreateIPAddress(
                                                           *v235,
                                                           hGroup,
                                                           v311,
                                                           (*v239)[v116].lpszIpAddress,
                                                           (*v239)[v116].dwPrefixLength);
                        *((_QWORD *)Block + v116) = IPAddress;
                        if ( IPAddress )
                        {
                          v309 = 91;
                          memset_0(v310, 0, sizeof(v310));
                          v220 = 0;
                          v123 = ClusterpResourceControl(
                                   IPAddress,
                                   0,
                                   0x1000039u,
                                   0,
                                   0,
                                   (char *)&v309 + 2,
                                   0x7Eu,
                                   &v220,
                                   0,
                                   0);
                          v108 = v123;
                          if ( v123 )
                          {
                            ClusRtl::ExceptionMsg::ExceptionMsg(
                              (ClusRtl::ExceptionMsg *)v298,
                              v123,
                              L"Failed to get resource ID of cluster IP address resource '%ws'",
                              v311);
                            throw (ClusRtl::ExceptionMsg *)v298;
                          }
                          if ( v273 )
                            std::wstring::append(&v272, L"or ");
                          else
                            std::wstring::assign(&v272, L"(", v124);
                          v111 = 1;
                          std::wstring::append(&v272, &v309);
                          std::wstring::append(&v272, L"]");
                        }
                        else
                        {
                          v108 = GetLastError();
                          PhaseManager::ContinuePhase((PhaseManager *)v243, v108, v122);
                          LODWORD(v218) = (*v239)[v116].dwPrefixLength;
                          TraceMsg(
                            2,
                            0,
                            L"CreateClusterCore",
                            2618,
                            L"Failed to create IP address %ws/%d",
                            (*v239)[v116].lpszIpAddress,
                            v218);
                        }
                        v110 = p_cIpEntries;
                      }
                      if ( !v111 )
                      {
                        ClusRtl::ExceptionMsg::ExceptionMsg(
                          (ClusRtl::ExceptionMsg *)v299,
                          v108,
                          L"Failed to create any IP addresses");
                        throw (ClusRtl::ExceptionMsg *)v299;
                      }
                      PhaseManager::EndPhase((PhaseManager *)v243, 0, ClusterSetupPhaseInformational);
                      v109 = managementPointType;
                    }
                    PhaseManager::StartPhase(v243, 205, v221);
                    v125 = v256;
                    LODWORD(v252) = 14208;
                    v126 = std::map<unsigned long,std::wstring>::operator[](v231, &v252);
                    v127 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v126);
                    v128 = v221;
                    LODWORD(v239) = 14201;
                    v129 = std::map<unsigned long,std::wstring>::operator[](v231, &v239);
                    v130 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v129);
                    v219 = v109;
                    v80 = hGroup;
                    NetworkName = (struct _HRESOURCE *)CreateNetworkName(
                                                         (unsigned int)v243,
                                                         (unsigned int)*v235,
                                                         (_DWORD)hGroup,
                                                         v130,
                                                         (__int64)v128,
                                                         v127,
                                                         (__int64)v125,
                                                         v219,
                                                         v230,
                                                         v225);
                    hResource = NetworkName;
                    v258 = (struct _CREATE_CLUSTER_CONFIG *)NetworkName;
                    if ( !NetworkName )
                    {
                      v202 = *(_QWORD *)CTSmartObj<wchar_t *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyLocalMem>>::Get(&v221);
                      v203 = GetLastError();
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)v300,
                        v203,
                        L"Failed to create network name %ws",
                        v202);
                      throw (ClusRtl::ExceptionMsg *)v300;
                    }
                    if ( v228 )
                    {
                      std::wstring::append(&v272, L")");
                      v132 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v272);
                      if ( SetClusterResourceDependencyExpression(NetworkName, v132) )
                      {
                        v204 = (_QWORD *)CTSmartObj<wchar_t *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyLocalMem>>::Get(&v221);
                        ClusRtl::ExceptionMsg::ExceptionMsg(
                          (ClusRtl::ExceptionMsg *)v301,
                          v205,
                          L"Failed to set dependency expression of network name %ws.",
                          *v204);
                        throw (ClusRtl::ExceptionMsg *)v301;
                      }
                    }
                    PhaseManager::EndPhase((PhaseManager *)v243, 0, ClusterSetupPhaseInformational);
                    v105 = (int)v238;
                  }
                  else
                  {
                    v80 = hGroup;
                  }
                  v133 = ClusterRegSetValueEx(v105, (int)L"DetectedCloudPlatform", 4, (int)&v234, 4, 0);
                  if ( v133 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v302,
                      v133,
                      L"Failed to set Cluster Cloud Type.");
                    throw (ClusRtl::ExceptionMsg *)v302;
                  }
                  if ( v234 == CLUSTER_CLOUD_TYPE_AZURE )
                  {
                    TraceMsg(
                      4,
                      0,
                      L"CreateClusterCore",
                      2701,
                      L"Detected that cluster is running on Azure, applying Azure networking threshold/delay settings.");
                    managementPointType = 30;
                    v134 = ClusterRegSetValueEx(v105, (int)L"SameSubnetThreshold", 4, (int)&managementPointType, 4, 0);
                    if ( v134 )
                    {
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)v303,
                        v134,
                        L"Failed to set Same Subnet Threshold.");
                      throw (ClusRtl::ExceptionMsg *)v303;
                    }
                    managementPointType = 1000;
                    v135 = ClusterRegSetValueEx(v105, (int)L"SameSubnetDelay", 4, (int)&managementPointType, 4, 0);
                    if ( v135 )
                    {
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)v304,
                        v135,
                        L"Failed to set Same Subnet Delay.");
                      throw (ClusRtl::ExceptionMsg *)v304;
                    }
                    managementPointType = 1000;
                    v136 = ClusterRegSetValueEx(v105, (int)L"CrossSubnetDelay", 4, (int)&managementPointType, 4, 0);
                    if ( v136 )
                    {
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)v305,
                        v136,
                        L"Failed to set Same Subnet Threshold.");
                      throw (ClusRtl::ExceptionMsg *)v305;
                    }
                    managementPointType = 30;
                    v137 = ClusterRegSetValueEx(v105, (int)L"CrossSubnetThreshold", 4, (int)&managementPointType, 4, 0);
                    if ( v137 )
                    {
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)v306,
                        v137,
                        L"Failed to set Same Subnet Delay.");
                      throw (ClusRtl::ExceptionMsg *)v306;
                    }
                    managementPointType = CLUSTER_MGMT_POINT_TYPE_CNO;
                    v138 = ClusterRegSetValueEx(v105, (int)L"DetectManagedEvents", 4, (int)&managementPointType, 4, 0);
                    if ( v138 )
                    {
                      ClusRtl::ExceptionMsg::ExceptionMsg(
                        (ClusRtl::ExceptionMsg *)v307,
                        v138,
                        L"Failed to set Same Subnet Delay.");
                      throw (ClusRtl::ExceptionMsg *)v307;
                    }
                  }
                  v225 = 14200;
                  v139 = std::map<unsigned long,std::wstring>::operator[](v231, &v225);
                  v140 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v139);
                  PhaseManager::StartPhase(v243, 206, v140);
                  v141 = OnlineClusterGroup(v80, 0);
                  v75 = v141;
                  if ( v141 == 997 )
                  {
                    v75 = 0;
                    v141 = 0;
                  }
                  if ( v141 )
                  {
                    ClusRtl::ExceptionMsg::ExceptionMsg(
                      (ClusRtl::ExceptionMsg *)v280,
                      v75,
                      L"Cluster group failed to go online");
                    throw (ClusRtl::ExceptionMsg *)v280;
                  }
                  PhaseManager::EndPhase(v243, 0, 0, 1);
                  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v259);
                  p_dwVersion = &v240->dwVersion;
                  v79 = hResource;
                }
                if ( !(unsigned int)GetClusterInstanceId(*v235) )
                {
                  if ( (void *)((char *)Source[1] - (char *)Source[0]) == (void *)16 )
                  {
                    memcpy_s_0(&Destination, (const rsize_t)Source[0], Source[0], v142);
                  }
                  else
                  {
                    std::wstring::wstring(v278, Source[0]);
                    Destination = *(_OWORD *)cxl::Guid::Guid(v267, v278);
                    std::wstring::_Tidy_deallocate(v278);
                  }
                }
                v145 = *(_QWORD *)(cxl::Stopwatch::elapsed(v269, v267) + 8);
                if ( (unsigned int)dword_18011D048 > 5 && (unsigned __int8)tlgKeywordOn(v144, v143, v145) )
                {
                  v225 = v146 / 10000 % 1000;
                  v230 = v75;
                  managementPointType = *p_cNodes;
                  v220 = *p_dwVersion;
                  v267[0] = &Destination;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    v225,
                    (unsigned int)byte_1801060B3,
                    v146,
                    v147,
                    (__int64)v267,
                    (__int64)&v220,
                    (__int64)&managementPointType,
                    (__int64)&v230,
                    (__int64)&v225);
                }
                if ( !v75 )
                {
                  if ( v79 )
                    CloseClusterResource(v79);
                  v179 = Block;
                  if ( Block )
                  {
                    v180 = 0;
                    for ( k = p_cIpEntries; v180 < *k; ++v180 )
                    {
                      v182 = (struct _HRESOURCE *)v179[v180];
                      if ( v182 )
                      {
                        CloseClusterResource(v182);
                        v179 = Block;
                      }
                    }
                    operator delete(v179);
                  }
                  if ( v80 )
                    CloseClusterGroupCommon(v80, 1);
                  if ( hMem )
                    CloseClusterGroupCommon(hMem, 1);
                  goto LABEL_293;
                }
                v148 = 0;
                v149 = 1;
                v150 = v235;
                if ( *v235 )
                {
                  CloseCluster(*v235);
                  *v150 = 0;
                  v151 = hGroup;
                  if ( hGroup )
                  {
                    v225 = 14200;
                    v152 = std::map<unsigned long,std::wstring>::operator[](v231, &v225);
                    v153 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v152);
                    PhaseManager::StartPhase(v243, 999, v153);
                    v154 = OfflineClusterGroupEx2((int)v151, 0, 0, 0, 0);
                    v148 = v154;
                    if ( v154 )
                    {
                      if ( v154 == 997 )
                      {
                        ClusterGroupState = GetClusterGroupState(v151, 0, 0);
                        v157 = 0;
                        while ( ClusterGroupState == ClusterGroupPending )
                        {
                          Sleep(0x3E8u);
                          ClusterGroupState = GetClusterGroupState(hGroup, 0, 0);
                          if ( ++v157 >= 30 )
                          {
                            if ( ClusterGroupState == ClusterGroupPending )
                              PhaseManager::ContinuePhase((PhaseManager *)v243, 0x5B4u, v158);
                            break;
                          }
                        }
                      }
                      else
                      {
                        PhaseManager::ContinuePhase((PhaseManager *)v243, v154, v155);
                      }
                    }
                    v159 = hResource;
                    if ( hResource )
                    {
                      v225 = 14201;
                      v160 = std::map<unsigned long,std::wstring>::operator[](v231, &v225);
                      v161 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v160);
                      PhaseManager::ContinuePhase((PhaseManager *)v243, v161, 0, ClusterSetupPhaseInformational);
                      v162 = SetCoreFlag_0(v159);
                      if ( v162 )
                        PhaseManager::ContinuePhase((PhaseManager *)v243, v162, v163);
                      v164 = DeleteClusterResourceEx(v159, L"clusapi!CreateClusterCore");
                      v148 = v164;
                      if ( v164 )
                        PhaseManager::ContinuePhase((PhaseManager *)v243, v164, v165);
                      CloseClusterResource(v159);
                    }
                    v166 = Block;
                    if ( Block )
                    {
                      v167 = 0;
                      v168 = p_cIpEntries;
                      while ( v167 < *v168 )
                      {
                        v169 = v166[v167];
                        if ( v169 )
                        {
                          PhaseManager::ContinuePhase(
                            (PhaseManager *)v243,
                            *(const wchar_t **)(v169 + 48),
                            0,
                            ClusterSetupPhaseInformational);
                          v170 = DeleteClusterResourceEx(*((_QWORD *)Block + v167), L"clusapi!CreateClusterCore");
                          v148 = v170;
                          if ( v170 )
                            PhaseManager::ContinuePhase((PhaseManager *)v243, v170, v171);
                          CloseClusterResource(*((HRESOURCE *)Block + v167));
                          v166 = Block;
                          v168 = p_cIpEntries;
                        }
                        ++v167;
                      }
                      operator delete(v166);
                    }
                    v149 = 0;
                    CloseClusterGroupCommon(hGroup, 1);
                  }
                  if ( hMem )
                    CloseClusterGroupCommon(hMem, 1);
                }
                for ( m = 0; m < (__int64)(*(_QWORD *)&v232[2] - *(_QWORD *)v232) >> 3; ++m )
                {
                  v173 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*(_QWORD *)(*(_QWORD *)v232 + 8 * m) + 48LL);
                  if ( v149 )
                  {
                    PhaseManager::StartPhase(v243, 999, v173);
                    v149 = 0;
                  }
                  else
                  {
                    PhaseManager::ContinuePhase((PhaseManager *)v243, v173, 0, ClusterSetupPhaseInformational);
                  }
                  v174 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*(_QWORD *)(*(_QWORD *)v232 + 8 * m) + 48LL);
                  v148 = ClRtlCleanupNode(v174, v175, 1320000, 0);
                }
                if ( v149 )
                  PhaseManager::StartPhase(v243, 999, v221);
                else
                  PhaseManager::ContinuePhase((PhaseManager *)v243, v221, 0, ClusterSetupPhaseInformational);
                if ( v256 )
                {
                  if ( *((_BYTE *)v256 + 24) )
                  {
                    v177 = ClusterADObject::DeleteAccount(*((ClusterADObject **)v256 + 1));
                  }
                  else
                  {
                    if ( !*((_BYTE *)v256 + 25) )
                      goto LABEL_277;
                    v177 = ClusterADObject::DisableAccount(*((ClusterADObject **)v256 + 1));
                  }
                  if ( (v177 & 0x1FFF0000) == 0x70000 )
                  {
                    v148 = (unsigned __int16)v177;
                    if ( (_WORD)v177 )
                      goto LABEL_278;
                  }
                  v148 = v177;
                }
LABEL_277:
                if ( !v148 )
                {
                  v178 = ClusterSetupPhaseInformational;
                  goto LABEL_280;
                }
LABEL_278:
                PhaseManager::ContinuePhase((PhaseManager *)v243, v148, v176);
                v178 = ClusterSetupPhaseWarning;
LABEL_280:
                PhaseManager::EndPhase((PhaseManager *)v243, v148, v178);
LABEL_293:
                v183 = 0;
                v184 = *(_QWORD *)&v232[2];
                v185 = *(_QWORD *)v232;
                if ( (__int64)(*(_QWORD *)&v232[2] - *(_QWORD *)v232) >> 3 )
                {
                  do
                  {
                    v186 = *(ClusNode **)(v185 + 8 * v183);
                    if ( v186 )
                    {
                      ClusNode::`scalar deleting destructor'(v186, v185);
                      v184 = *(_QWORD *)&v232[2];
                      v185 = *(_QWORD *)v232;
                    }
                    ++v183;
                  }
                  while ( v183 < (v184 - v185) >> 3 );
                }
                if ( v238 )
                  ClusterRegCloseKeyCommon(v238, 1);
                ClusterGlobalData::~ClusterGlobalData((ClusterGlobalData *)v271);
                CTSmartObj<CreateClusterADState *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(
                  &v254,
                  v187);
                std::wstring::_Tidy_deallocate(&v275);
                std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
                CTSmartPtr_PolicyLocalMem::DestroyMem(v56);
                v188 = v221;
                v221 = 0;
                CTSmartPtr_PolicyLocalMem::DestroyMem(v188);
                std::wstring::_Tidy_deallocate(&v272);
                std::vector<unsigned char>::_Tidy(Source);
                if ( *(_QWORD *)v232 )
                  std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
                return v75;
              case CLUSTER_MGMT_POINT_TYPE_CNO_ONLY:
                goto LABEL_132;
            }
          }
          v51 = 0;
          goto LABEL_135;
        }
      }
    }
    else
    {
      managementPointResType = v20->managementPointResType;
      if ( managementPointResType )
      {
        v25 = managementPointResType - 1;
        if ( v25 )
        {
          if ( v25 != 1 )
          {
            std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
            CTSmartPtr_PolicyLocalMem::DestroyMem(v7);
            v26 = v221;
            v221 = 0;
            CTSmartPtr_PolicyLocalMem::DestroyMem(v26);
            std::wstring::_Tidy_deallocate(&v272);
            std::vector<unsigned char>::_Tidy(Source);
            if ( *(_QWORD *)v232 )
              std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
            return 87;
          }
          goto LABEL_47;
        }
      }
      else if ( v234 == CLUSTER_CLOUD_TYPE_AZURE )
      {
LABEL_47:
        v27 = 1;
        goto LABEL_51;
      }
    }
    v27 = 0;
    goto LABEL_51;
  }
  TraceMsg(
    4,
    0,
    L"CreateClusterCore",
    1944,
    L"Cluster management point type requires Active Directory, Validating that all nodes are domain joined.");
  for ( n = 0; n < v240->cNodes; ++n )
  {
    if ( !v8 )
      goto LABEL_31;
    v225 = 0;
    IsMachineDomainJoined = ClRtlIsMachineDomainJoined(v240->ppszNodeNames[n], &v225);
    v17 = IsMachineDomainJoined;
    if ( IsMachineDomainJoined )
    {
      TraceMsg(
        2,
        0,
        L"CreateClusterCore",
        1953,
        L"Failed to determine if machine %ws is domain joined. Error %d.",
        v240->ppszNodeNames[n],
        IsMachineDomainJoined);
      std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
      CTSmartPtr_PolicyLocalMem::DestroyMem(0);
      v18 = v221;
      v221 = 0;
      CTSmartPtr_PolicyLocalMem::DestroyMem(v18);
      std::wstring::_Tidy_deallocate(&v272);
      std::vector<unsigned char>::_Tidy(Source);
      if ( *(_QWORD *)v232 )
        std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
      return v17;
    }
    v8 = v225 != 0 ? v224 : 0;
    v224 = v8;
  }
  if ( v8 )
  {
LABEL_38:
    p_fEmptyCluster = v238;
    goto LABEL_342;
  }
LABEL_31:
  if ( !v10 )
  {
    TraceMsg(
      4,
      0,
      L"CreateClusterCore",
      1983,
      L"Not all nodes are domain joined, but credentials were provided.  Configuring Domain-joined cluster on Domainless nodes.");
    goto LABEL_38;
  }
  if ( managementPointType != CLUSTER_MGMT_POINT_TYPE_CNO_ONLY )
  {
    TraceMsg(
      3,
      0,
      L"CreateClusterCore",
      1977,
      L"Not all nodes are domain joined! Switching from CLUSTER_MGMT_POINT_TYPE_CNO to CLUSTER_MGMT_POINT_TYPE_DNS_ONLY");
    managementPointType = CLUSTER_MGMT_POINT_TYPE_DNS_ONLY;
    v226 = 1;
    p_fEmptyCluster = v238;
    goto LABEL_342;
  }
  TraceMsg(
    2,
    0,
    L"CreateClusterCore",
    1973,
    L"CLUSTER_MGMT_POINT_TYPE_CNO_ONLY was specified but not all machines are domain joined, cannot fallback to CLUSTER_MG"
     "MT_POINT_TYPE_DNS_ONLY for this scenario");
  std::_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::wstring,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::wstring>>,0>>(v231);
  CTSmartPtr_PolicyLocalMem::DestroyMem(0);
  v19 = v221;
  v221 = 0;
  CTSmartPtr_PolicyLocalMem::DestroyMem(v19);
  std::wstring::_Tidy_deallocate(&v272);
  std::vector<unsigned char>::_Tidy(Source);
  if ( *(_QWORD *)v232 )
    std::_Deallocate<16>(*(_QWORD *)v232, (v233 - *(_QWORD *)v232) & 0xFFFFFFFFFFFFFFF8uLL);
  return 87;
}

```

## disassembly

```asm
0x18003359c  mov     [rsp+arg_10], r8
0x1800335a1  mov     [rsp+arg_8], rdx
0x1800335a6  push    rbx
0x1800335a7  push    rsi
0x1800335a8  push    rdi
0x1800335a9  push    r12
0x1800335ab  push    r13
0x1800335ad  push    r14
0x1800335af  push    r15
0x1800335b1  mov     eax, 2370h
0x1800335b6  call    _alloca_probe
0x1800335bb  sub     rsp, rax
0x1800335be  mov     rax, cs:__security_cookie
0x1800335c5  xor     rax, rsp
0x1800335c8  mov     [rsp+23A8h+var_48], rax
0x1800335d0  mov     rax, r9
0x1800335d3  mov     [rsp+23A8h+var_2300], rax
0x1800335db  mov     rdi, rcx
0x1800335de  mov     [rsp+23A8h+var_22D8], rcx
0x1800335e6  mov     [rsp+23A8h+var_2210], rcx
0x1800335ee  mov     r13, rcx
0x1800335f1  mov     [rsp+23A8h+var_2248], rcx
0x1800335f9  mov     [rsp+23A8h+var_2208], rax
0x180033601  xor     r14d, r14d
0x180033604  lea     rsi, [rcx+30h]
0x180033608  mov     [rsp+23A8h+var_22E8], rsi
0x180033610  mov     r15b, [rsi]
0x180033613  mov     [rsp+23A8h+var_233B], r15b
0x180033618  xorps   xmm0, xmm0
0x18003361b  movdqu  xmmword ptr [rsp+23A8h+var_2320], xmm0
0x180033624  mov     [rsp+23A8h+var_2310], r14
0x18003362c  movdqu  xmmword ptr [rsp+23A8h+Source], xmm0
0x180033635  mov     [rsp+23A8h+var_2280], r14
0x18003363d  movups  [rsp+23A8h+Destination], xmm0
0x180033645  xorps   xmm1, xmm1
0x180033648  movups  [rsp+23A8h+var_2148], xmm1
0x180033650  mov     [rsp+23A8h+var_2138], r14
0x180033658  mov     [rsp+23A8h+var_2130], 7
0x180033664  mov     word ptr [rsp+23A8h+var_2148], r14w
0x18003366d  lea     rax, ??_7TimeSpan@cxl@@6B@; const cxl::TimeSpan::`vftable'
0x180033674  mov     [rsp+23A8h+var_21E8], rax
0x18003367c  mov     [rsp+23A8h+var_21E0], r14
0x180033684  lea     rax, ??_7MonotonicDateTime@cxl@@6B@; const cxl::MonotonicDateTime::`vftable'
0x18003368b  mov     [rsp+23A8h+var_21D8], rax
0x180033693  lea     rcx, [rsp+23A8h+var_2240]
0x18003369b  call    ?get_Now@MonotonicDateTime@cxl@@SA?AU12@XZ; cxl::MonotonicDateTime::get_Now(void)
0x1800336a0  mov     rcx, [rax+8]
0x1800336a4  mov     [rsp+23A8h+var_21D0], rcx
0x1800336ac  mov     [rsp+23A8h+var_2350], r14
0x1800336b1  mov     ebx, r14d
0x1800336b4  mov     [rsp+23A8h+var_22F0], rbx
0x1800336bc  mov     [rsp+23A8h+var_2308], r14d
0x1800336c4  lea     rcx, [rsp+23A8h+var_2330]
0x1800336c9  call    ??0?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAA@XZ; std::map<ulong,std::wstring>::map<ulong,std::wstring>(void)
0x1800336ce  nop
0x1800336cf  mov     eax, [r13+0]
0x1800336d3  mov     dword ptr [rsp+23A8h+var_2380], eax
0x1800336d7  lea     rax, aClusterCreatio_0; "Cluster creation start, pConfig->dwVers"...
0x1800336de  mov     [rsp+23A8h+var_2388], rax
0x1800336e3  mov     r9d, 75Dh
0x1800336e9  lea     r12, aCreateclusterc; "CreateClusterCore"
0x1800336f0  mov     r8, r12
0x1800336f3  xor     edx, edx
0x1800336f5  lea     ecx, [rdx+4]
0x1800336f8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800336fd  test    r15b, r15b
0x180033700  jz      short loc_180033709
0x180033702  mov     [rsp+23A8h+var_2348], r14d
0x180033707  jmp     short loc_18003371C
0x180033709  cmp     dword ptr [rdi], 702h
0x18003370f  jb      loc_180033877
0x180033715  mov     eax, [rdi+34h]
0x180033718  mov     [rsp+23A8h+var_2348], eax
0x18003371c  mov     [rsp+23A8h+var_2344], r14b
0x180033721  mov     [rsp+23A8h+var_233C], r14b
0x180033726  mov     r15b, 1
0x180033729  mov     [rsp+23A8h+var_2343], r15b
0x18003372e  cmp     dword ptr [rdi], 0C05h
0x180033734  jb      loc_180033891
0x18003373a  lea     rax, aValidatingCrea; "Validating Create Cluster Config domain"...
0x180033741  mov     [rsp+23A8h+var_2388], rax
0x180033746  mov     r9d, 775h
0x18003374c  mov     r8, r12
0x18003374f  xor     edx, edx
0x180033751  lea     ecx, [rdx+4]
0x180033754  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033759  mov     rax, [rdi+40h]
0x18003375d  test    rax, rax
0x180033760  jnz     short loc_180033799
0x180033762  cmp     [rdi+48h], r14
0x180033766  jnz     loc_1800337ED
0x18003376c  cmp     [rdi+50h], r14
0x180033770  jnz     short loc_1800337ED
0x180033772  lea     rax, aAllCredentials; "All Credentials are empty."
0x180033779  mov     [rsp+23A8h+var_2388], rax
0x18003377e  mov     r9d, 77Ah
0x180033784  mov     r8, r12
0x180033787  xor     edx, edx
0x180033789  lea     ecx, [rdx+4]
0x18003378c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033791  mov     r12b, r15b
0x180033794  jmp     loc_1800338B7
0x180033799  cmp     [rax], r14w
0x18003379d  jz      short loc_1800337ED
0x18003379f  mov     rax, [rdi+48h]
0x1800337a3  test    rax, rax
0x1800337a6  jz      short loc_1800337ED
0x1800337a8  cmp     [rax], r14w
0x1800337ac  jz      short loc_1800337ED
0x1800337ae  mov     rax, [rdi+50h]
0x1800337b2  test    rax, rax
0x1800337b5  jz      short loc_1800337ED
0x1800337b7  cmp     [rax], r14w
0x1800337bb  jz      short loc_1800337ED
0x1800337bd  mov     r12b, r14b
0x1800337c0  lea     rax, aAllCredentials_0; "All Credentials are valid."
0x1800337c7  mov     [rsp+23A8h+var_2388], rax
0x1800337cc  mov     r9d, 784h
0x1800337d2  lea     r8, aCreateclusterc; "CreateClusterCore"
0x1800337d9  xor     edx, edx
0x1800337db  lea     ecx, [rdx+4]
0x1800337de  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800337e3  mov     [rsp+23A8h+var_2344], r15b
0x1800337e8  jmp     loc_1800338B7
0x1800337ed  lea     rax, aInvalidCreateC; "Invalid create cluster configuration, d"...
0x1800337f4  mov     [rsp+23A8h+var_2388], rax
0x1800337f9  mov     r9d, 78Ah
0x1800337ff  mov     r8, r12
0x180033802  xor     edx, edx
0x180033804  lea     ecx, [rdx+2]
0x180033807  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003380c  nop
0x18003380d  lea     rcx, [rsp+23A8h+var_2330]
0x180033812  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x180033817  nop
0x180033818  xor     ecx, ecx; void *
0x18003381a  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x18003381f  nop
0x180033820  mov     rcx, [rsp+23A8h+var_2350]; void *
0x180033825  mov     [rsp+23A8h+var_2350], r14
0x18003382a  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x18003382f  nop
0x180033830  lea     rcx, [rsp+23A8h+var_2148]
0x180033838  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003383d  nop
0x18003383e  lea     rcx, [rsp+23A8h+Source]
0x180033846  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003384b  nop
0x18003384c  mov     rcx, qword ptr [rsp+23A8h+var_2320]
0x180033854  test    rcx, rcx
0x180033857  jz      short loc_18003386D
0x180033859  mov     rdx, [rsp+23A8h+var_2310]
0x180033861  sub     rdx, rcx
0x180033864  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180033868  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003386d  mov     eax, 57h ; 'W'
0x180033872  jmp     loc_180035D15
0x180033877  mov     [rsp+23A8h+var_2348], 1
0x18003387f  mov     [rsp+23A8h+var_2344], r14b
0x180033884  mov     [rsp+23A8h+var_233C], r14b
0x180033889  mov     r15b, 1
0x18003388c  mov     [rsp+23A8h+var_2343], r15b
0x180033891  mov     r12b, 1
0x180033894  lea     rax, aCreateClusterC; "Create Cluster config credentials infor"...
0x18003389b  mov     [rsp+23A8h+var_2388], rax
0x1800338a0  mov     r9d, 791h
0x1800338a6  lea     r8, aCreateclusterc; "CreateClusterCore"
0x1800338ad  xor     edx, edx
0x1800338af  lea     ecx, [rdx+4]
0x1800338b2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800338b7  mov     eax, [rsp+23A8h+var_2348]
0x1800338bb  dec     eax
0x1800338bd  test    eax, 0FFFFFFFDh
0x1800338c2  jnz     loc_180033AF1
0x1800338c8  lea     rax, aClusterManagem; "Cluster management point type requires "...
0x1800338cf  mov     [rsp+23A8h+var_2388], rax
0x1800338d4  mov     r9d, 798h
0x1800338da  lea     r8, aCreateclusterc; "CreateClusterCore"
0x1800338e1  xor     edx, edx
0x1800338e3  lea     ecx, [rdx+4]
0x1800338e6  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800338eb  mov     edi, r14d
0x1800338ee  mov     rax, [rsp+23A8h+var_22D8]
0x1800338f6  cmp     edi, [rax+10h]
0x1800338f9  jnb     loc_1800339EB
0x1800338ff  test    r15b, r15b
0x180033902  jz      loc_1800339F4
0x180033908  mov     [rsp+23A8h+var_2340], r14d
0x18003390d  mov     r15d, edi
0x180033910  mov     rcx, [rax+18h]
0x180033914  lea     rdx, [rsp+23A8h+var_2340]
0x180033919  mov     rcx, [rcx+r15*8]
0x18003391d  call    ClRtlIsMachineDomainJoined
0x180033922  mov     esi, eax
0x180033924  test    eax, eax
0x180033926  jz      loc_1800339D1
0x18003392c  mov     rcx, [rsp+23A8h+var_22D8]
0x180033934  mov     rcx, [rcx+18h]
0x180033938  mov     dword ptr [rsp+23A8h+var_2378], eax
0x18003393c  mov     rcx, [rcx+r15*8]
0x180033940  mov     [rsp+23A8h+var_2380], rcx
0x180033945  lea     rax, aFailedToDeterm_1; "Failed to determine if machine %ws is d"...
0x18003394c  mov     [rsp+23A8h+var_2388], rax
0x180033951  mov     r9d, 7A1h
0x180033957  lea     r8, aCreateclusterc; "CreateClusterCore"
0x18003395e  xor     edx, edx
0x180033960  lea     ecx, [rdx+2]
0x180033963  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033968  nop
0x180033969  lea     rcx, [rsp+23A8h+var_2330]
0x18003396e  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x180033973  nop
0x180033974  mov     rcx, rbx; void *
0x180033977  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x18003397c  nop
0x18003397d  mov     rcx, [rsp+23A8h+var_2350]; void *
0x180033982  mov     [rsp+23A8h+var_2350], r14
0x180033987  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x18003398c  nop
0x18003398d  lea     rcx, [rsp+23A8h+var_2148]
0x180033995  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003399a  nop
0x18003399b  lea     rcx, [rsp+23A8h+Source]
0x1800339a3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800339a8  nop
0x1800339a9  mov     rcx, qword ptr [rsp+23A8h+var_2320]
0x1800339b1  test    rcx, rcx
0x1800339b4  jz      short loc_1800339CA
0x1800339b6  mov     rdx, [rsp+23A8h+var_2310]
0x1800339be  sub     rdx, rcx
0x1800339c1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800339c5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800339ca  mov     eax, esi
0x1800339cc  jmp     loc_180035D15
0x1800339d1  mov     eax, [rsp+23A8h+var_2340]
0x1800339d5  neg     eax
0x1800339d7  sbb     cl, cl
0x1800339d9  and     cl, [rsp+23A8h+var_2343]
0x1800339dd  mov     r15b, cl
0x1800339e0  mov     [rsp+23A8h+var_2343], cl
0x1800339e4  inc     edi
0x1800339e6  jmp     loc_1800338EE
0x1800339eb  test    r15b, r15b
0x1800339ee  jnz     loc_180033AE9
0x1800339f4  lea     r8, aCreateclusterc; "CreateClusterCore"
0x1800339fb  xor     edx, edx
0x1800339fd  test    r12b, r12b
0x180033a00  jz      loc_180033ACD
0x180033a06  cmp     [rsp+23A8h+var_2348], 3
0x180033a0b  jnz     loc_180033A97
0x180033a11  lea     rax, aClusterMgmtPoi; "CLUSTER_MGMT_POINT_TYPE_CNO_ONLY was sp"...
0x180033a18  mov     [rsp+23A8h+var_2388], rax
0x180033a1d  mov     r9d, 7B5h
0x180033a23  lea     ecx, [rdx+2]
0x180033a26  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033a2b  nop
0x180033a2c  lea     rcx, [rsp+23A8h+var_2330]
0x180033a31  call    ??1?$_Tree@V?$_Tmap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::wstring,std::less<ulong>,std::allocator<std::pair<ulong const,std::wstring>>,0>>(void)
0x180033a36  nop
0x180033a37  mov     rcx, rbx; void *
0x180033a3a  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x180033a3f  nop
0x180033a40  mov     rcx, [rsp+23A8h+var_2350]; void *
0x180033a45  mov     [rsp+23A8h+var_2350], r14
0x180033a4a  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x180033a4f  nop
0x180033a50  lea     rcx, [rsp+23A8h+var_2148]
0x180033a58  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033a5d  nop
0x180033a5e  lea     rcx, [rsp+23A8h+Source]
0x180033a66  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180033a6b  nop
0x180033a6c  mov     rcx, qword ptr [rsp+23A8h+var_2320]
0x180033a74  test    rcx, rcx
0x180033a77  jz      short loc_180033A8D
0x180033a79  mov     rdx, [rsp+23A8h+var_2310]
0x180033a81  sub     rdx, rcx
0x180033a84  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180033a88  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180033a8d  mov     eax, 57h ; 'W'
0x180033a92  jmp     loc_180035D15
0x180033a97  lea     rax, aNotAllNodesAre; "Not all nodes are domain joined! Switch"...
0x180033a9e  mov     [rsp+23A8h+var_2388], rax
0x180033aa3  mov     r9d, 7B9h
0x180033aa9  mov     ecx, 3
0x180033aae  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033ab3  mov     r12d, 2
0x180033ab9  mov     [rsp+23A8h+var_2348], r12d
0x180033abe  mov     [rsp+23A8h+var_233C], 1
0x180033ac3  mov     rsi, [rsp+23A8h+var_22E8]
0x180033acb  jmp     short loc_180033AF7
0x180033acd  lea     rax, aNotAllNodesAre_0; "Not all nodes are domain joined, but cr"...
0x180033ad4  mov     [rsp+23A8h+var_2388], rax
0x180033ad9  mov     r9d, 7BFh
0x180033adf  mov     ecx, 4
0x180033ae4  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180033ae9  mov     rsi, [rsp+23A8h+var_22E8]
0x180033af1  mov     r12d, 2
0x180033af7  mov     r15, [rsp+23A8h+var_22D8]
0x180033aff  lea     rdi, [r15+18h]
  ... truncated ...
```
