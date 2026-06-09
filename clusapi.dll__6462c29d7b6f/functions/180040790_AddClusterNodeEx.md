# AddClusterNodeEx

- ea: `0x180040790`
- end: `0x180041bf5`
- name: `AddClusterNodeEx`
- size: `5221`
- prototype: ``
- caller_count: `1`
- callee_count: `74`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180040770`

## callees

- `0x1800012bc`
- `0x180001370`
- `0x180002f50`
- `0x180003320`
- `0x180003c14`
- `0x180003c44`
- `0x180014638`
- `0x180019030`
- `0x18001aa48`
- `0x18001cc2c`
- `0x18001ce04`
- `0x18001cf54`
- `0x18001dee8`
- `0x18001ecdc`
- `0x18001feac`
- `0x180023f10`
- `0x1800240a8`
- `0x180024d98`
- `0x180025478`
- `0x180028f30`
- `0x180029410`
- `0x1800294f0`
- `0x180029578`
- `0x180029a04`
- `0x18002a7a0`
- `0x18002acc0`
- `0x18002adc0`
- `0x18002c220`
- `0x18002f130`
- `0x18002fb94`
- `0x1800303c4`
- `0x180031728`
- `0x18003180c`
- `0x180031c44`
- `0x180031f74`
- `0x180032234`
- `0x180032258`
- `0x180032718`
- `0x180032770`
- `0x18003302c`
- `0x1800386a0`
- `0x180038b2c`
- `0x18003a1f0`
- `0x18003aa0c`
- `0x18003b410`
- `0x18003b5c8`
- `0x18003baf8`
- `0x18003bb08`
- `0x18003bb68`
- `0x18003be68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040ad8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180040ad8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180040ac3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180040ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004150d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004150d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041bbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004098d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800415ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800416aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004098d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800415ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800416aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180040d81`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180040d81`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18004097c`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18004097c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800412bd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800412bd`

## string_xrefs

- `0x180041ac0`: `Failed to start the cluster service on node %ws`
- `0x18004182c`: `Node %ws is already a member of this cluster`
- `0x18004175d`: `There is already a fault domain with the node name.`
- `0x18004178b`: `Add Node failed as the supplied nodes are incompatible with the functional level of the specified cluster.`
- `0x180041b8d`: `Add Node failed as the supplied nodes are incompatible with the functional level of the specified cluster.`
- `0x180041910`: `Node %ws is not Arc joined or does not have access to the storage account configured for the cloud witness`
- `0x18004106b`: `Adding node to cluster configuration`
- `0x180041a84`: `Failed to open handle to notify port`
- `0x180041b62`: `Cluster service on node %ws never reached Up state`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
struct _HNODE *__fastcall AddClusterNodeEx(
        struct _HCLUSTER *a1,
        wchar_t *a2,
        int (*a3)(void *, enum _CLUSTER_SETUP_PHASE, enum _CLUSTER_SETUP_PHASE_TYPE, enum _CLUSTER_SETUP_PHASE_SEVERITY, unsigned int, const wchar_t *, unsigned int),
        void *a4,
        __int64 a5)
{
  struct _HCLUSTER *v7; // r13
  DWORD v8; // ecx
  struct _HNODE *result; // rax
  __int64 v11; // r15
  __int64 v12; // rbx
  DWORD (__stdcall *v13)(HCLUSTER, LPCWSTR, DWORD, DWORD); // rbx
  const WCHAR *v14; // rax
  const wchar_t *v15; // rbx
  wchar_t *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  _QWORD *v19; // rbx
  __int64 v20; // rsi
  unsigned __int16 NodeClusterMajorVersionAllNodes; // bx
  unsigned __int16 ClusterFunctionalLevel; // ax
  unsigned __int16 v23; // si
  unsigned __int16 NodeClusterUpgradeVersionAllNodes; // bx
  unsigned __int16 ClusterUpgradeVersion; // ax
  _QWORD *v26; // rbx
  struct _HCLUSENUM *v27; // rbx
  WCHAR *v28; // r12
  int v29; // eax
  DWORD i; // r14d
  unsigned int v31; // eax
  struct _HNODE *v32; // rax
  struct _HNODE *v33; // rsi
  DWORD NumericNodeId; // ebx
  int ClusterCert; // eax
  char v36; // al
  wchar_t *v37; // r14
  int v38; // ebx
  int v39; // eax
  int v40; // eax
  DWORD EnumCount; // eax
  unsigned int v42; // ebx
  char *v43; // rsi
  char *v44; // rax
  size_t v45; // rbx
  DWORD v46; // ebx
  SC_HANDLE *v47; // rsi
  struct _HCHANGE *ClusterNotifyPort; // r14
  __int64 v49; // rax
  __int64 v50; // r8
  struct _HCLUSTER *v51; // rax
  unsigned int v52; // esi
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // r8
  rsize_t v56; // r9
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  unsigned int v60; // edx
  struct _HNODE *v61; // rbx
  unsigned int v62; // r14d
  DWORD v63; // eax
  int v64; // edx
  DWORD v65; // eax
  DWORD v66; // eax
  HINSTANCE ClusApiModule; // rax
  __int64 v68; // rax
  const wchar_t *v69; // rax
  DWORD v70; // eax
  const wchar_t *NodeName; // rbx
  DWORD v72; // eax
  DWORD v73; // ebx
  HINSTANCE v74; // rax
  __int64 v75; // rax
  const wchar_t *v76; // rax
  const wchar_t *v77; // rax
  DWORD LastError; // eax
  ClusRtl::ExceptionMsg *v79; // rbx
  LPDWORD lpcchName; // [rsp+20h] [rbp-1CD8h]
  LPDWORD lpcchNamea; // [rsp+20h] [rbp-1CD8h]
  int cchCount2[2]; // [rsp+28h] [rbp-1CD0h]
  int cchCount2a[2]; // [rsp+28h] [rbp-1CD0h]
  unsigned int v84; // [rsp+64h] [rbp-1C94h] BYREF
  DWORD dwErrCode; // [rsp+68h] [rbp-1C90h]
  DWORD cchName; // [rsp+6Ch] [rbp-1C8Ch] BYREF
  unsigned int v87; // [rsp+70h] [rbp-1C88h] BYREF
  DWORD v88; // [rsp+74h] [rbp-1C84h] BYREF
  unsigned int v89; // [rsp+78h] [rbp-1C80h] BYREF
  PCNZWCH lpString2; // [rsp+80h] [rbp-1C78h] BYREF
  __int64 v91[2]; // [rsp+88h] [rbp-1C70h] BYREF
  __int64 v92; // [rsp+98h] [rbp-1C60h]
  unsigned int v93; // [rsp+A0h] [rbp-1C58h] BYREF
  _QWORD v94[2]; // [rsp+A8h] [rbp-1C50h] BYREF
  int v95; // [rsp+B8h] [rbp-1C40h]
  __int64 v96; // [rsp+BCh] [rbp-1C3Ch]
  int v97; // [rsp+C4h] [rbp-1C34h]
  WCHAR *v98; // [rsp+C8h] [rbp-1C30h]
  __int64 v99[2]; // [rsp+D0h] [rbp-1C28h] BYREF
  struct _HCLUSENUM *v100; // [rsp+E0h] [rbp-1C18h]
  struct _CLUSTER_CERT *v101; // [rsp+E8h] [rbp-1C10h]
  struct _HCHANGE *v102; // [rsp+F0h] [rbp-1C08h]
  int v103[2]; // [rsp+F8h] [rbp-1C00h] BYREF
  void *v104; // [rsp+100h] [rbp-1BF8h]
  __int64 v105; // [rsp+108h] [rbp-1BF0h]
  DWORD dwType[2]; // [rsp+110h] [rbp-1BE8h] BYREF
  wchar_t *v107; // [rsp+118h] [rbp-1BE0h]
  struct _CLUSTER_CERT *v108; // [rsp+120h] [rbp-1BD8h]
  struct _CLUSTER_CERT *v109; // [rsp+128h] [rbp-1BD0h]
  struct _CLUSTER_CERT *v110; // [rsp+130h] [rbp-1BC8h]
  struct _HCLUSTER *v111; // [rsp+138h] [rbp-1BC0h]
  __int128 v112; // [rsp+140h] [rbp-1BB8h] BYREF
  __int64 v113; // [rsp+150h] [rbp-1BA8h]
  _QWORD v114[2]; // [rsp+158h] [rbp-1BA0h] BYREF
  void *Source[2]; // [rsp+168h] [rbp-1B90h] BYREF
  __int64 v116; // [rsp+178h] [rbp-1B80h]
  ClusNode *v117; // [rsp+180h] [rbp-1B78h]
  _QWORD v118[4]; // [rsp+188h] [rbp-1B70h] BYREF
  char v119; // [rsp+1A8h] [rbp-1B50h]
  int v120[4]; // [rsp+1B0h] [rbp-1B48h] BYREF
  __int64 v121; // [rsp+1C0h] [rbp-1B38h]
  _QWORD v122[3]; // [rsp+1C8h] [rbp-1B30h] BYREF
  _QWORD v123[3]; // [rsp+1E0h] [rbp-1B18h] BYREF
  _QWORD v124[3]; // [rsp+1F8h] [rbp-1B00h] BYREF
  _QWORD v125[3]; // [rsp+210h] [rbp-1AE8h] BYREF
  ClusRtl::ExceptionMsg *v126; // [rsp+228h] [rbp-1AD0h] BYREF
  cxl::Exception *v127; // [rsp+230h] [rbp-1AC8h] BYREF
  std::system_error *v128; // [rsp+238h] [rbp-1AC0h] BYREF
  int v129[20]; // [rsp+240h] [rbp-1AB8h] BYREF
  _QWORD v130[6]; // [rsp+290h] [rbp-1A68h] BYREF
  _OWORD v131[2]; // [rsp+2C0h] [rbp-1A38h] BYREF
  __int128 Destination; // [rsp+2E0h] [rbp-1A18h] BYREF
  _OWORD v133[2]; // [rsp+2F0h] [rbp-1A08h] BYREF
  _OWORD v134[2]; // [rsp+310h] [rbp-19E8h] BYREF
  __int128 v135; // [rsp+330h] [rbp-19C8h] BYREF
  __m128i si128; // [rsp+340h] [rbp-19B8h]
  _BYTE pExceptionObject[272]; // [rsp+350h] [rbp-19A8h] BYREF
  _BYTE v138[272]; // [rsp+460h] [rbp-1898h] BYREF
  _BYTE v139[272]; // [rsp+570h] [rbp-1788h] BYREF
  _BYTE v140[272]; // [rsp+680h] [rbp-1678h] BYREF
  _BYTE v141[272]; // [rsp+790h] [rbp-1568h] BYREF
  _BYTE v142[272]; // [rsp+8A0h] [rbp-1458h] BYREF
  _BYTE v143[272]; // [rsp+9B0h] [rbp-1348h] BYREF
  _BYTE v144[272]; // [rsp+AC0h] [rbp-1238h] BYREF
  _BYTE v145[272]; // [rsp+BD0h] [rbp-1128h] BYREF
  _BYTE v146[272]; // [rsp+CE0h] [rbp-1018h] BYREF
  _BYTE v147[272]; // [rsp+DF0h] [rbp-F08h] BYREF
  _BYTE v148[272]; // [rsp+F00h] [rbp-DF8h] BYREF
  _BYTE v149[272]; // [rsp+1010h] [rbp-CE8h] BYREF
  _BYTE v150[272]; // [rsp+1120h] [rbp-BD8h] BYREF
  _BYTE v151[272]; // [rsp+1230h] [rbp-AC8h] BYREF
  _BYTE v152[272]; // [rsp+1340h] [rbp-9B8h] BYREF
  _BYTE v153[272]; // [rsp+1450h] [rbp-8A8h] BYREF
  _BYTE v154[272]; // [rsp+1560h] [rbp-798h] BYREF
  _BYTE v155[272]; // [rsp+1670h] [rbp-688h] BYREF
  _BYTE v156[272]; // [rsp+1780h] [rbp-578h] BYREF
  _BYTE v157[272]; // [rsp+1890h] [rbp-468h] BYREF
  _BYTE v158[272]; // [rsp+19A0h] [rbp-358h] BYREF
  WCHAR szName[256]; // [rsp+1AB0h] [rbp-248h] BYREF
  std::exception *v160; // [rsp+1CB0h] [rbp-48h] BYREF

  v107 = a2;
  v7 = a1;
  v111 = a1;
  v114[0] = a2;
  if ( ((unsigned int)a3 & 0x1000000) != 0 )
  {
    v8 = 50;
LABEL_91:
    SetLastError(v8);
    return 0;
  }
  if ( ((unsigned int)a3 & 0x10000000) != 0 )
    return AddClusterNodeOnSQLPAL(a1, a2, a3, a4);
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v8 = 6;
    goto LABEL_91;
  }
  try
  {
    *(_OWORD *)Source = 0;
    v116 = 0;
    Destination = 0;
    v88 = 0;
    v84 = -1;
    lpString2 = 0;
    *(_OWORD *)v91 = 0;
    v92 = 0;
    v131[0] = 0;
    v131[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v131[0]) = 0;
    std::vector<unsigned char>::vector<unsigned char>(v123, 15436);
    v101 = (struct _CLUSTER_CERT *)v123[0];
    std::vector<unsigned char>::vector<unsigned char>(v122, 15436);
    v11 = v122[0];
    v110 = (struct _CLUSTER_CERT *)v122[0];
    std::vector<unsigned char>::vector<unsigned char>(v125, 15436);
    v12 = v125[0];
    v109 = (struct _CLUSTER_CERT *)v125[0];
    std::vector<unsigned char>::vector<unsigned char>(v124, 15436);
    v108 = (struct _CLUSTER_CERT *)v124[0];
    v118[0] = v101;
    v118[1] = v11;
    v118[2] = v12;
    v118[3] = v124[0];
    v119 = 0;
    v13 = get_startup_argv_mode;
    if ( a4 )
      v13 = (DWORD (__stdcall *)(HCLUSTER, LPCWSTR, DWORD, DWORD))a4;
    TraceMsg(4, 0, L"AddClusterNodeEx", 4157, L"Total number of phases in Add Node: %d.", 9);
    if ( !AreAnyAccessesGranted(*((_DWORD *)v7 + 80), 0x10000003u) )
    {
      SetLastError(5u);
      v119 = 1;
      lambda_66dc03098420d3811bd76db77a07ee69_::operator()(v118);
      std::vector<unsigned char>::_Tidy(v124);
      std::vector<unsigned char>::_Tidy(v125);
      std::vector<unsigned char>::_Tidy(v122);
      std::vector<unsigned char>::_Tidy(v123);
      std::wstring::_Tidy_deallocate(v131);
      if ( v91[0] )
      {
        std::_Deallocate<16>(v91[0], (v92 - v91[0]) & 0xFFFFFFFFFFFFFFF8uLL);
        *(_OWORD *)v91 = 0;
        v92 = 0;
      }
      std::vector<unsigned char>::_Tidy(Source);
      return 0;
    }
    v100 = 0;
    v102 = 0;
    v94[0] = v13;
    v94[1] = a5;
    v95 = 1;
    v96 = 9;
    v97 = 1;
    v98 = 0;
    ClusterGlobalData::ClusterGlobalData((ClusterGlobalData *)v129);
    try
    {
      if ( !a2 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)pExceptionObject, 87, L"Missing newNodeName");
        throw (ClusRtl::ExceptionMsg *)pExceptionObject;
      }
      v14 = newdup(a2);
      v15 = v14;
      lpString2 = v14;
      if ( !v14 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v138, 14, L"No memory for node label");
        throw (ClusRtl::ExceptionMsg *)v138;
      }
      v16 = wcschr(v14, 0x2Eu);
      if ( v16 )
        *v16 = 0;
      if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)v7 + 2)) )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v139,
          87,
          L"Node name is same as target cluster name");
        throw (ClusRtl::ExceptionMsg *)v139;
      }
      if ( FaultDomainExists(v7, v15) )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v140,
          183,
          L"There is already a fault domain with the node name.");
        throw (ClusRtl::ExceptionMsg *)v140;
      }
      ClusterGlobalData::Initialize((ClusterGlobalData *)v129, 1u);
      std::map<unsigned long,std::wstring>::map<unsigned long,std::wstring>(v99);
      ValidateNodeState(
        *((_QWORD *)v7 + 2),
        1,
        (int)&lpString2,
        (int)v129,
        (PhaseManager *)v94,
        (__int64)v91,
        (__int64)v99);
      v17 = v91[1];
      v18 = v91[0];
      if ( v91[0] == v91[1] )
      {
        LastError = GetLastError();
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v158,
          LastError,
          L"Add Node failed as specified node %ws is not valid.",
          lpString2);
        throw (ClusRtl::ExceptionMsg *)v158;
      }
      v112 = 0;
      v113 = 0;
      v19 = (_QWORD *)v91[0];
      v20 = v91[1];
      while ( v19 != (_QWORD *)v20 )
      {
        *(_QWORD *)dwType = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*v19 + 48LL);
        std::vector<wchar_t const *>::_Emplace_one_at_back<wchar_t const *>(&v112, dwType);
        ++v19;
        v17 = v91[1];
        v18 = v91[0];
      }
      NodeClusterMajorVersionAllNodes = GetNodeClusterMajorVersionAllNodes(v112, (v17 - v18) >> 3);
      ClusterFunctionalLevel = GetClusterFunctionalLevel(v7);
      v23 = ClusterFunctionalLevel;
      LOWORD(dwErrCode) = ClusterFunctionalLevel;
      if ( !ClusterFunctionalLevel || NodeClusterMajorVersionAllNodes < ClusterFunctionalLevel )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v157,
          5075,
          L"Add Node failed as the supplied nodes are incompatible with the functional level of the specified cluster.");
        throw (ClusRtl::ExceptionMsg *)v157;
      }
      if ( NodeClusterMajorVersionAllNodes == ClusterFunctionalLevel && ClusterFunctionalLevel > 8u )
      {
        NodeClusterUpgradeVersionAllNodes = GetNodeClusterUpgradeVersionAllNodes(v112, (v91[1] - v91[0]) >> 3);
        ClusterUpgradeVersion = GetClusterUpgradeVersion(v7);
        if ( NodeClusterUpgradeVersionAllNodes < ClusterUpgradeVersion
          && ClusterUpgradeVersion
          && (v23 != 9 || (unsigned __int16)(ClusterUpgradeVersion - 6) > 1u) )
        {
          ClusRtl::ExceptionMsg::ExceptionMsg(
            (ClusRtl::ExceptionMsg *)v141,
            5075,
            L"Add Node failed as the supplied nodes are incompatible with the functional level of the specified cluster.");
          throw (ClusRtl::ExceptionMsg *)v141;
        }
      }
      v26 = (_QWORD *)v99[0];
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned long>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,unsigned long>,void *>>>(
        v99,
        v99,
        *(_QWORD *)(v99[0] + 8));
      v26[1] = v26;
      *v26 = v26;
      v26[2] = v26;
      v99[1] = 0;
      v117 = *(ClusNode **)v91[0];
      PhaseManager::StartPhase(v94, 300, *((_QWORD *)v7 + 2));
      v27 = ClusterOpenEnum(v7, 1u);
      v100 = v27;
      if ( !v27 )
      {
        v63 = GetLastError();
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v142,
          v63,
          L"Failed to get node enumeration handle");
        throw (ClusRtl::ExceptionMsg *)v142;
      }
      cchName = 256;
      v89 = 0;
      v87 = 0;
      v28 = (WCHAR *)lpString2;
      v29 = MylstrlenW(lpString2, 0x100u, &v89);
      if ( v29 < 0 )
      {
        if ( (v29 & 0x1FFF0000) != 0x70000 || (v64 = (unsigned __int16)v29, !(_WORD)v29) )
          v64 = v29;
        ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v143, v64, L"Failed to calculate node label size");
        throw (ClusRtl::ExceptionMsg *)v143;
      }
      for ( i = 0; !ClusterEnum(v27, i, dwType, szName, &cchName); ++i )
      {
        v98 = szName;
        v31 = 256;
        if ( v89 < 0x100 )
          v31 = v89;
        if ( CompareStringW(0x400u, 1u, szName, cchName, v28, v31) == 2 )
        {
          ClusRtl::ExceptionMsg::ExceptionMsg(
            (ClusRtl::ExceptionMsg *)v144,
            5065,
            L"Node %ws is already a member of this cluster",
            v28);
          throw (ClusRtl::ExceptionMsg *)v144;
        }
        cchName = 256;
        v32 = OpenClusterNodeImpl(v7, szName, 0x10000000u, 0, 1);
        v33 = v32;
        if ( !v32 )
        {
          v65 = GetLastError();
          ClusRtl::ExceptionMsg::ExceptionMsg(
            (ClusRtl::ExceptionMsg *)v145,
            v65,
            L"Failed to get handle to node %ws",
            szName);
          throw (ClusRtl::ExceptionMsg *)v145;
        }
        NumericNodeId = GetNumericNodeId(v32);
        v88 = NumericNodeId;
        if ( NumericNodeId == -1 )
        {
          v66 = GetLastError();
          ClusRtl::ExceptionMsg::ExceptionMsg(
            (ClusRtl::ExceptionMsg *)v146,
            v66,
            L"Failed to get node ID for node %ws",
            szName);
          throw (ClusRtl::ExceptionMsg *)v146;
        }
        std::wstring::wstring(v130, szName);
        *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](v99, v130) = NumericNodeId;
        std::wstring::_Tidy_deallocate(v130);
        if ( !v87 && ((GetClusterNodeState(v33) + 1) & 0xFFFFFFFD) != 0 )
        {
          GetSQMHash(szName, &v87);
          ClusterCert = RetrieveClusterCert(szName, v101, v110, v109, v108, dwErrCode);
          if ( ClusterCert < 0 )
          {
            ClusRtl::ExceptionMsg::ExceptionMsg(
              (ClusRtl::ExceptionMsg *)v147,
              ClusterCert,
              L"Failed to Get Cluster Secret via CPrep Server on node %ws",
              szName);
            throw (ClusRtl::ExceptionMsg *)v147;
          }
        }
        CloseClusterNodeCommon(v33, 1);
        v27 = v100;
      }
      v135 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v135) = 0;
      v134[0] = 0;
      v134[1] = si128;
      LOWORD(v134[0]) = 0;
      v133[0] = 0;
      v133[1] = si128;
      LOWORD(v133[0]) = 0;
      v36 = IsClusterConfiguredWithManagedIdentityCloudWitness(v7, &v135, v134, v133);
      v37 = v107;
      if ( v36 )
      {
        std::wstring::wstring(v130, v107);
        v38 = CheckIfNodeIsArcJoinedAndHasAccessToStorageAccount(v130, &v135, v134, v133);
        std::wstring::_Tidy_deallocate(v130);
        if ( v38 < 0 )
        {
          if ( (v38 & 0x1FFF0000) == 0x70000 )
            v38 = (unsigned __int16)v38;
          ClusRtl::ExceptionMsg::ExceptionMsg(
            (ClusRtl::ExceptionMsg *)v148,
            v38,
            L"Node %ws is not Arc joined or does not have access to the storage account configured for the cloud witness",
            v37);
          throw (ClusRtl::ExceptionMsg *)v148;
        }
        v27 = v100;
      }
      v98 = 0;
      v39 = ComputeMaximumNumberOfNodes(v7, &v84);
      if ( v39 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v149,
          v39,
          L"Failed to determine max number of nodes for this cluster");
        throw (ClusRtl::ExceptionMsg *)v149;
      }
      v40 = ComputeMaximumNumberOfNodes(v37, &v84);
      if ( v40 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v150,
          v40,
          L"Failed to obtain max number of nodes for node being added");
        throw (ClusRtl::ExceptionMsg *)v150;
      }
      EnumCount = ClusterGetEnumCount(v27);
      if ( EnumCount >= v84 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v151, 5934, L"Cluster membership is full");
        throw (ClusRtl::ExceptionMsg *)v151;
      }
      if ( !v87 )
      {
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v152,
          5036,
          L"Unable to get the SQM Hash from any node");
        throw (ClusRtl::ExceptionMsg *)v152;
      }
      PhaseManager::EndPhase((PhaseManager *)v94, 0, ClusterSetupPhaseInformational);
      TraceMsg(4, 0, L"AddClusterNodeEx", 4443, L"Applying NetworkATC intents on new node");
      PhaseManager::StartPhase(v94, 303, v37);
      if ( (unsigned int)IsNetworkATCFeatureInstalled(v37) )
      {
        cchCount2[0] = SetupNodeATCIntents(v7, v37, (const WCHAR ***)v99, (PhaseManager *)v94);
        TraceMsg(4, 0, L"AddClusterNodeEx", 4450, L"SetupNodeATCIntents returned %d ", *(_QWORD *)cchCount2);
      }
      PhaseManager::EndPhase((PhaseManager *)v94, 0, ClusterSetupPhaseInformational);
      TraceMsg(4, 0, L"AddClusterNodeEx", 4459, L"Adding node to cluster configuration");
      PhaseManager::StartPhase(v94, 301, v28);
      v93 = 256;
      std::vector<unsigned char>::vector<unsigned char>(v103, 256);
      v130[0] = "ApiAddNode";
      v130[1] = (char *)v7 + 40;
      v130[2] = v28;
      v130[3] = &v88;
      v130[4] = &v93;
      v130[5] = *(_QWORD *)v103;
      v42 = ReconnectOnError<AddNodeFunctor>(v130, v7);
      if ( v42 )
      {
        ClusApiModule = GetClusApiModule();
        LODWORD(lpcchName) = v42;
        v68 = HelperFormatMessage(v130, ClusApiModule, 23);
        std::wstring::operator=(v131, v68);
        std::wstring::~wstring(v130);
        v69 = (const wchar_t *)std::wstring::c_str(v131);
        PhaseManager::ReportPhaseStatus((PhaseManager *)v94, v69, v42, ClusterSetupPhaseFatal);
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v153,
          v42,
          L"Failed to add node %ws to cluster",
          v28,
          lpcchName);
        throw (ClusRtl::ExceptionMsg *)v153;
      }
      v43 = (char *)v104;
      if ( (char *)v93 < (char *)v104 - *(_QWORD *)v103 )
      {
        v44 = (char *)(*(_QWORD *)v103 + v93);
LABEL_61:
        v104 = v44;
        goto LABEL_62;
      }
      if ( (char *)v93 > (char *)v104 - *(_QWORD *)v103 )
      {
        if ( v93 <= (unsigned __int64)(v105 - *(_QWORD *)v103) )
        {
          v45 = v93 - ((unsigned __int64)v104 - *(_QWORD *)v103);
          memset_0(v104, 0, v45);
          v44 = &v43[v45];
          goto LABEL_61;
        }
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v103, v93);
      }
LABEL_62:
      v46 = v88;
      std::wstring::wstring(v130, v28);
      *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](v99, v130) = v46;
      std::wstring::_Tidy_deallocate(v130);
      *(_OWORD *)v120 = 0;
      v121 = 0;
      CCHlpBuildMultiSzNodeMap(v99, v120);
      PhaseManager::EndPhase((PhaseManager *)v94, 0, ClusterSetupPhaseInformational);
      v47 = (SC_HANDLE *)v117;
      ClusNode::ConfigureNode(
        (PhaseManager **)v117,
        (__int64)v120,
        (__int64)v103,
        v101,
        v110,
        v109,
        v108,
        v87,
        0,
        0,
        1,
        dwErrCode);
      PhaseManager::StartPhase(v94, 105, v37);
      ClusterNotifyPort = CreateClusterNotifyPort((HCHANGE)0xFFFFFFFFFFFFFFFFLL, v7, 1u, 0);
      v102 = ClusterNotifyPort;
      if ( !ClusterNotifyPort )
      {
        v70 = GetLastError();
        ClusRtl::ExceptionMsg::ExceptionMsg((ClusRtl::ExceptionMsg *)v154, v70, L"Failed to open handle to notify port");
        throw (ClusRtl::ExceptionMsg *)v154;
      }
      if ( !StartServiceW(v47[16], 0, 0) )
      {
        NodeName = ClusNode::GetNodeName((ClusNode *)v47);
        v72 = GetLastError();
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v155,
          v72,
          L"Failed to start the cluster service on node %ws",
          NodeName);
        throw (ClusRtl::ExceptionMsg *)v155;
      }
      PhaseManager::EndPhase((PhaseManager *)v94, 0, ClusterSetupPhaseInformational);
      v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v47 + 6);
      PhaseManager::StartPhase(v94, 302, v49);
      v51 = (struct _HCLUSTER *)WaitForNodeUp(v94, v7, v50, v91);
      if ( !v51 )
      {
        v73 = GetLastError();
        v74 = GetClusApiModule();
        LODWORD(lpcchNamea) = v73;
        v75 = HelperFormatMessage(v130, v74, 24);
        std::wstring::operator=(v131, v75);
        std::wstring::~wstring(v130);
        v76 = (const wchar_t *)std::wstring::c_str(v131);
        PhaseManager::ReportPhaseStatus((PhaseManager *)v94, v76, v73, ClusterSetupPhaseFatal);
        v77 = ClusNode::GetNodeName((ClusNode *)v47);
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v156,
          v73,
          L"Cluster service on node %ws never reached Up state",
          v77,
          lpcchNamea);
        throw (ClusRtl::ExceptionMsg *)v156;
      }
      CloseCluster(v51);
      PhaseManager::EndPhase((PhaseManager *)v94, 0, ClusterSetupPhaseInformational);
      std::vector<wchar_t>::_Tidy(v120);
      std::vector<unsigned char>::_Tidy(v103);
      std::wstring::_Tidy_deallocate(v133);
      std::wstring::_Tidy_deallocate(v134);
      std::wstring::_Tidy_deallocate(&v135);
      if ( (_QWORD)v112 )
      {
        std::_Deallocate<16>(v112, (v113 - v112) & 0xFFFFFFFFFFFFFFF8uLL);
        v112 = 0;
        v113 = 0;
      }
      v52 = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v99);
    }
    catch ( ClusRtl::ExceptionMsg *v126 )
    {
      v79 = v126;
      v84 = *((_DWORD *)v126 + 64);
      PhaseManager::EndPhase(v94, v84, 0, 3);
      TraceMsg(
        2,
        0,
        L"AddClusterNodeEx",
        4565,
        L"Exception - error %d while adding node %ws: %ws.",
        *((_DWORD *)v79 + 64),
        v114[0],
        v79);
      v7 = v111;
      v28 = (WCHAR *)lpString2;
      v52 = v84;
      ClusterNotifyPort = v102;
    }
    catch ( std::exception *v160 )
    {
      TraceMsg(2, 0, L"AddClusterNodeEx", 4569, L"Exception - std");
      v84 = 14;
      PhaseManager::EndPhase(v94, 14, 0, 3);
      v7 = v111;
      v28 = (WCHAR *)lpString2;
      v52 = v84;
      ClusterNotifyPort = v102;
    }
    if ( !(unsigned int)GetClusterInstanceId(v7) )
    {
      if ( (void *)((char *)Source[1] - (char *)Source[0]) == (void *)16 )
      {
        memcpy_s_0(&Destination, (const rsize_t)Source[0], Source[0], v56);
      }
      else
      {
        std::wstring::wstring(v130, Source[0]);
        Destination = *(_OWORD *)cxl::Guid::Guid(v114, v130);
        std::wstring::_Tidy_deallocate(v130);
      }
    }
    if ( (unsigned int)dword_18011D048 > 5 && (unsigned __int8)tlgKeywordOn(v54, v53, v55) )
    {
      v84 = v52;
      cchName = v88;
      v114[0] = &Destination;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v57,
        (unsigned int)&byte_18010605F,
        v58,
        v59,
        (__int64)v114,
        (__int64)&cchName,
        (__int64)&v84);
    }
    if ( v100 )
      ClusterCloseEnumCommon(v100, 1);
    if ( ClusterNotifyPort )
      CloseClusterNotifyPort(ClusterNotifyPort);
    v61 = OpenClusterNodeImpl(v7, v28, 0x10000000u, 0, 1);
    if ( !v61 )
    {
      v52 = GetLastError();
      cchCount2a[0] = v52;
      TraceMsg(2, 0, L"AddClusterNodeEx", 4597, L"Failed to get handle to new node - %d.", *(_QWORD *)cchCount2a);
    }
    if ( v52 )
    {
      v62 = 0;
      PhaseManager::StartPhase(v94, 999, v28);
      if ( v61 )
      {
        TraceMsg(4, 0, L"AddClusterNodeEx", 4610, L"Evicting node %ws", v28);
        v62 = EvictNode(0, v7, v28);
        CloseClusterNodeCommon(v61, 1);
        v61 = 0;
      }
      PhaseManager::EndPhase((PhaseManager *)v94, v62, (enum _CLUSTER_SETUP_PHASE_SEVERITY)((v62 != 0) + 1));
    }
    if ( v91[0] != v91[1] && *(_QWORD *)v91[0] )
      ClusNode::`scalar deleting destructor'(*(ClusNode **)v91[0], v60);
    operator delete(v28);
    SetLastError(v52);
    ClusterGlobalData::~ClusterGlobalData((ClusterGlobalData *)v129);
    v119 = 1;
    lambda_66dc03098420d3811bd76db77a07ee69_::operator()(v118);
    std::vector<unsigned char>::_Tidy(v124);
    std::vector<unsigned char>::_Tidy(v125);
    std::vector<unsigned char>::_Tidy(v122);
    std::vector<unsigned char>::_Tidy(v123);
    std::wstring::_Tidy_deallocate(v131);
    if ( v91[0] )
    {
      std::_Deallocate<16>(v91[0], (v92 - v91[0]) & 0xFFFFFFFFFFFFFFF8uLL);
      *(_OWORD *)v91 = 0;
      v92 = 0;
    }
    std::vector<unsigned char>::_Tidy(Source);
    result = v61;
  }
  catch ( cxl::Exception *v127 )
  {
    dwErrCode = cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v127 + 88));
    v8 = dwErrCode;
    goto LABEL_91;
  }
  catch ( std::system_error *v128 )
  {
    dwErrCode = *((_DWORD *)v128 + 6);
    v8 = dwErrCode;
    goto LABEL_91;
  }
  catch ( std::bad_alloc )
  {
    dwErrCode = 14;
    v8 = 14;
    goto LABEL_91;
  }
  catch ( std::exception )
  {
    dwErrCode = 1359;
    v8 = 1359;
    goto LABEL_91;
  }
  catch ( ... )
  {
    dwErrCode = 1359;
    v8 = 1359;
    goto LABEL_91;
  }
  return result;
}

```

## disassembly

```asm
0x180040790  push    rbx
0x180040792  push    rsi
0x180040793  push    rdi
0x180040794  push    r12
0x180040796  push    r13
0x180040798  push    r14
0x18004079a  push    r15
0x18004079c  mov     eax, 1CC0h
0x1800407a1  call    _alloca_probe
0x1800407a6  sub     rsp, rax
0x1800407a9  mov     rax, cs:__security_cookie
0x1800407b0  xor     rax, rsp
0x1800407b3  mov     [rsp+1CF8h+var_40], rax
0x1800407bb  mov     rsi, r9
0x1800407be  mov     r12, rdx
0x1800407c1  mov     [rsp+1CF8h+var_1BE0], rdx
0x1800407c9  mov     r13, rcx
0x1800407cc  mov     [rsp+1CF8h+var_1BC0], rcx
0x1800407d4  mov     [rsp+1CF8h+var_1BA0], rdx
0x1800407dc  mov     r14, [rsp+1CF8h+arg_20]
0x1800407e4  bt      r8d, 18h
0x1800407e9  jnb     short loc_1800407F5
0x1800407eb  mov     ecx, 32h ; '2'
0x1800407f0  jmp     loc_1800416AA
0x1800407f5  bt      r8d, 1Ch
0x1800407fa  jnb     short loc_180040806
0x1800407fc  call    ?AddClusterNodeOnSQLPAL@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WP6AHPEAXW4_CLUSTER_SETUP_PHASE@@W4_CLUSTER_SETUP_PHASE_TYPE@@W4_CLUSTER_SETUP_PHASE_SEVERITY@@K1K@Z2@Z; AddClusterNodeOnSQLPAL(_HCLUSTER *,wchar_t const *,int (*)(void *,_CLUSTER_SETUP_PHASE,_CLUSTER_SETUP_PHASE_TYPE,_CLUSTER_SETUP_PHASE_SEVERITY,ulong,wchar_t const *,ulong),void *)
0x180040801  jmp     loc_1800416B2
0x180040806  mov     rdx, r13
0x180040809  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18004080e  xor     edi, edi
0x180040810  test    al, al
0x180040812  jnz     short loc_18004081C
0x180040814  lea     ecx, [rdi+6]
0x180040817  jmp     loc_1800416AA
0x18004081c  xorps   xmm0, xmm0
0x18004081f  movdqu  xmmword ptr [rsp+1CF8h+Source], xmm0
0x180040828  mov     [rsp+1CF8h+var_1B80], rdi
0x180040830  movups  [rsp+1CF8h+Destination], xmm0
0x180040838  mov     [rsp+1CF8h+var_1C84], edi
0x18004083c  mov     [rsp+1CF8h+var_1C94], 0FFFFFFFFh
0x180040844  mov     [rsp+1CF8h+lpString2], rdi
0x18004084c  movdqu  xmmword ptr [rsp+1CF8h+var_1C70], xmm0
0x180040855  mov     [rsp+1CF8h+var_1C60], rdi
0x18004085d  movups  [rsp+1CF8h+var_1A38], xmm0
0x180040865  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004086d  movdqu  [rsp+1CF8h+var_1A28], xmm1
0x180040876  mov     word ptr [rsp+1CF8h+var_1A38], di
0x18004087e  mov     ebx, 3C4Ch
0x180040883  mov     edx, ebx
0x180040885  lea     rcx, [rsp+1CF8h+var_1B18]
0x18004088d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180040892  nop
0x180040893  mov     rax, [rsp+1CF8h+var_1B18]
0x18004089b  mov     [rsp+1CF8h+var_1C10], rax
0x1800408a3  mov     edx, ebx
0x1800408a5  lea     rcx, [rsp+1CF8h+var_1B30]
0x1800408ad  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800408b2  nop
0x1800408b3  mov     r15, [rsp+1CF8h+var_1B30]
0x1800408bb  mov     [rsp+1CF8h+var_1BC8], r15
0x1800408c3  mov     edx, ebx
0x1800408c5  lea     rcx, [rsp+1CF8h+var_1AE8]
0x1800408cd  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800408d2  nop
0x1800408d3  mov     rbx, [rsp+1CF8h+var_1AE8]
0x1800408db  mov     [rsp+1CF8h+var_1BD0], rbx
0x1800408e3  mov     edx, 3C4Ch
0x1800408e8  lea     rcx, [rsp+1CF8h+var_1B00]
0x1800408f0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800408f5  nop
0x1800408f6  mov     rax, [rsp+1CF8h+var_1B00]
0x1800408fe  mov     [rsp+1CF8h+var_1BD8], rax
0x180040906  mov     rcx, [rsp+1CF8h+var_1C10]
0x18004090e  mov     [rsp+1CF8h+var_1B70], rcx
0x180040916  mov     [rsp+1CF8h+var_1B68], r15
0x18004091e  mov     [rsp+1CF8h+var_1B60], rbx
0x180040926  mov     [rsp+1CF8h+var_1B58], rax
0x18004092e  mov     [rsp+1CF8h+var_1B50], dil
0x180040936  lea     rbx, _get_startup_argv_mode
0x18004093d  test    rsi, rsi
0x180040940  cmovnz  rbx, rsi
0x180040944  mov     esi, 9
0x180040949  mov     [rsp+1CF8h+cchCount2], esi
0x18004094d  lea     rax, aTotalNumberOfP; "Total number of phases in Add Node: %d."
0x180040954  mov     [rsp+1CF8h+lpcchName], rax
0x180040959  mov     r9d, 103Dh
0x18004095f  lea     r8, aAddclusternode_1; "AddClusterNodeEx"
0x180040966  xor     edx, edx
0x180040968  lea     ecx, [rsi-5]
0x18004096b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180040970  mov     edx, 10000003h; DesiredAccess
0x180040975  mov     ecx, [r13+140h]; GrantedAccess
0x18004097c  call    cs:__imp_AreAnyAccessesGranted
0x180040982  test    eax, eax
0x180040984  jnz     loc_180040A3D
0x18004098a  lea     ecx, [rsi-4]; dwErrCode
0x18004098d  call    cs:__imp_SetLastError
0x180040993  nop
0x180040994  lea     r15d, [rsi-8]
0x180040998  mov     [rsp+1CF8h+var_1B50], r15b
0x1800409a0  lea     rcx, [rsp+1CF8h+var_1B70]
0x1800409a8  call    _lambda_66dc03098420d3811bd76db77a07ee69___operator__
0x1800409ad  nop
0x1800409ae  lea     rcx, [rsp+1CF8h+var_1B00]
0x1800409b6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800409bb  nop
0x1800409bc  lea     rcx, [rsp+1CF8h+var_1AE8]
0x1800409c4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800409c9  nop
0x1800409ca  lea     rcx, [rsp+1CF8h+var_1B30]
0x1800409d2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800409d7  nop
0x1800409d8  lea     rcx, [rsp+1CF8h+var_1B18]
0x1800409e0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800409e5  nop
0x1800409e6  lea     rcx, [rsp+1CF8h+var_1A38]
0x1800409ee  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800409f3  nop
0x1800409f4  mov     rcx, [rsp+1CF8h+var_1C70]
0x1800409fc  test    rcx, rcx
0x1800409ff  jz      short loc_180040A29
0x180040a01  mov     rdx, [rsp+1CF8h+var_1C60]
0x180040a09  sub     rdx, rcx
0x180040a0c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180040a10  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040a15  xorps   xmm0, xmm0
0x180040a18  movdqu  xmmword ptr [rsp+1CF8h+var_1C70], xmm0
0x180040a21  mov     [rsp+1CF8h+var_1C60], rdi
0x180040a29  lea     rcx, [rsp+1CF8h+Source]
0x180040a31  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180040a36  xor     eax, eax
0x180040a38  jmp     loc_1800416B2
0x180040a3d  mov     [rsp+1CF8h+var_1C18], rdi
0x180040a45  mov     [rsp+1CF8h+var_1C08], rdi
0x180040a4d  mov     [rsp+1CF8h+var_1C98], dil
0x180040a52  mov     [rsp+1CF8h+var_1C50], rbx
0x180040a5a  mov     [rsp+1CF8h+var_1C48], r14
0x180040a62  mov     r15d, 1
0x180040a68  mov     [rsp+1CF8h+var_1C40], r15d
0x180040a70  mov     [rsp+1CF8h+var_1C3C], rsi
0x180040a78  mov     [rsp+1CF8h+var_1C34], r15d
0x180040a80  mov     [rsp+1CF8h+var_1C30], rdi
0x180040a88  lea     rcx, [rsp+1CF8h+var_1AB8]; this
0x180040a90  call    ??0ClusterGlobalData@@QEAA@XZ; ClusterGlobalData::ClusterGlobalData(void)
0x180040a95  nop
0x180040a96  test    r12, r12
0x180040a99  jz      loc_1800416DB
0x180040a9f  mov     rcx, r12; wchar_t *
0x180040aa2  call    ?newdup@@YAPEA_WPEB_W@Z; newdup(wchar_t const *)
0x180040aa7  mov     rbx, rax
0x180040aaa  mov     [rsp+1CF8h+lpString2], rax
0x180040ab2  test    rax, rax
0x180040ab5  jz      loc_180041707
0x180040abb  mov     edx, 2Eh ; '.'; Ch
0x180040ac0  mov     rcx, rbx; Str
0x180040ac3  call    cs:__imp_wcschr
0x180040ac9  test    rax, rax
0x180040acc  jz      short loc_180040AD1
0x180040ace  mov     [rax], di
0x180040ad1  mov     rdx, rbx
0x180040ad4  mov     rcx, [r13+10h]
0x180040ad8  call    cs:__imp__o__wcsicmp
0x180040ade  test    eax, eax
0x180040ae0  jz      loc_180041732
0x180040ae6  mov     rdx, rbx; wchar_t *
0x180040ae9  mov     rcx, r13; struct _HCLUSTER *
0x180040aec  call    ?FaultDomainExists@@YA_NPEAU_HCLUSTER@@PEB_W@Z; FaultDomainExists(_HCLUSTER *,wchar_t const *)
0x180040af1  test    al, al
0x180040af3  jnz     loc_18004175D
0x180040af9  mov     edx, r15d; unsigned int
0x180040afc  lea     rcx, [rsp+1CF8h+var_1AB8]; this
0x180040b04  call    ?Initialize@ClusterGlobalData@@QEAAXK@Z; ClusterGlobalData::Initialize(ulong)
0x180040b09  lea     rcx, [rsp+1CF8h+var_1C28]
0x180040b11  call    ??0?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@QEAA@XZ; std::map<ulong,std::wstring>::map<ulong,std::wstring>(void)
0x180040b16  nop
0x180040b17  lea     rax, [rsp+1CF8h+var_1C28]
0x180040b1f  mov     [rsp+1CF8h+var_1CC8], rax; __int64
0x180040b24  lea     rax, [rsp+1CF8h+var_1C70]
0x180040b2c  mov     qword ptr [rsp+1CF8h+cchCount2], rax; __int64
0x180040b31  lea     rax, [rsp+1CF8h+var_1C50]
0x180040b39  mov     [rsp+1CF8h+lpcchName], rax; PhaseManager *
0x180040b3e  lea     r9, [rsp+1CF8h+var_1AB8]; int
0x180040b46  lea     r8, [rsp+1CF8h+lpString2]; int
0x180040b4e  mov     edx, r15d; int
0x180040b51  mov     rcx, [r13+10h]; int
0x180040b55  call    ?ValidateNodeState@@YAXPEB_WKPEAPEB_WAEAVClusterGlobalData@@AEAVPhaseManager@@AEAV?$vector@PEAVClusNode@@V?$allocator@PEAVClusNode@@@std@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@2@@4@@Z; ValidateNodeState(wchar_t const *,ulong,wchar_t const * *,ClusterGlobalData &,PhaseManager &,std::vector<ClusNode *> &,std::map<std::wstring,ulong> &)
0x180040b5a  mov     rdx, [rsp+1CF8h+var_1C70+8]
0x180040b62  mov     rax, [rsp+1CF8h+var_1C70]
0x180040b6a  cmp     rax, rdx
0x180040b6d  jz      loc_180041BBB
0x180040b73  xorps   xmm0, xmm0
0x180040b76  movdqu  [rsp+1CF8h+var_1BB8], xmm0
0x180040b7f  mov     [rsp+1CF8h+var_1BA8], rdi
0x180040b87  mov     rbx, rax
0x180040b8a  mov     rsi, rdx
0x180040b8d  mov     r14d, 8
0x180040b93  cmp     rbx, rsi
0x180040b96  jz      short loc_180040BD6
0x180040b98  mov     rcx, [rbx]
0x180040b9b  add     rcx, 30h ; '0'
0x180040b9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180040ba4  mov     qword ptr [rsp+1CF8h+dwType], rax
0x180040bac  lea     rdx, [rsp+1CF8h+dwType]
0x180040bb4  lea     rcx, [rsp+1CF8h+var_1BB8]
0x180040bbc  call    ??$_Emplace_one_at_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@AEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::_Emplace_one_at_back<wchar_t const *>(wchar_t const * &&)
0x180040bc1  add     rbx, r14
0x180040bc4  mov     rdx, [rsp+1CF8h+var_1C70+8]
0x180040bcc  mov     rax, [rsp+1CF8h+var_1C70]
0x180040bd4  jmp     short loc_180040B93
0x180040bd6  sub     rdx, rax
0x180040bd9  sar     rdx, 3
0x180040bdd  mov     rcx, qword ptr [rsp+1CF8h+var_1BB8]
0x180040be5  call    GetNodeClusterMajorVersionAllNodes
0x180040bea  movzx   ebx, ax
0x180040bed  mov     rcx, r13; hCluster
0x180040bf0  call    ?GetClusterFunctionalLevel@@YAGPEAU_HCLUSTER@@@Z; GetClusterFunctionalLevel(_HCLUSTER *)
0x180040bf5  movzx   esi, ax
0x180040bf8  mov     word ptr [rsp+1CF8h+dwErrCode], ax
0x180040bfd  test    ax, ax
0x180040c00  jz      loc_180041B8D
0x180040c06  cmp     bx, ax
0x180040c09  jb      loc_180041B8D
0x180040c0f  jnz     short loc_180040C6C
0x180040c11  cmp     ax, r14w
0x180040c15  jbe     short loc_180040C6C
0x180040c17  mov     rdx, [rsp+1CF8h+var_1C70+8]
0x180040c1f  sub     rdx, [rsp+1CF8h+var_1C70]
0x180040c27  sar     rdx, 3
0x180040c2b  mov     rcx, qword ptr [rsp+1CF8h+var_1BB8]
0x180040c33  call    GetNodeClusterUpgradeVersionAllNodes
0x180040c38  movzx   ebx, ax
0x180040c3b  mov     rcx, r13; struct _HCLUSTER *
0x180040c3e  call    ?GetClusterUpgradeVersion@@YAGPEAU_HCLUSTER@@@Z; GetClusterUpgradeVersion(_HCLUSTER *)
0x180040c43  movzx   ecx, ax
0x180040c46  cmp     bx, ax
0x180040c49  jnb     short loc_180040C6C
0x180040c4b  test    ax, ax
0x180040c4e  jz      short loc_180040C6C
0x180040c50  mov     eax, 9
0x180040c55  cmp     si, ax
0x180040c58  jnz     loc_18004178B
0x180040c5e  sub     cx, 6
0x180040c62  cmp     cx, r15w
0x180040c66  ja      loc_18004178B
0x180040c6c  mov     rbx, [rsp+1CF8h+var_1C28]
0x180040c74  mov     r8, [rbx+8]
0x180040c78  lea     rdx, [rsp+1CF8h+var_1C28]
0x180040c80  lea     rcx, [rsp+1CF8h+var_1C28]
0x180040c88  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ulong>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,ulong>,void *>> &,std::_Tree_node<std::pair<std::wstring const,ulong>,void *> *)
0x180040c8d  mov     [rbx+8], rbx
0x180040c91  mov     [rbx], rbx
0x180040c94  mov     [rbx+10h], rbx
0x180040c98  mov     [rsp+1CF8h+var_1C20], rdi
0x180040ca0  mov     rax, [rsp+1CF8h+var_1C70]
0x180040ca8  mov     rcx, [rax]
0x180040cab  mov     [rsp+1CF8h+var_1B78], rcx
0x180040cb3  mov     r8, [r13+10h]
0x180040cb7  mov     edx, 12Ch
0x180040cbc  lea     rcx, [rsp+1CF8h+var_1C50]
0x180040cc4  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x180040cc9  mov     edx, r15d; dwType
0x180040ccc  mov     rcx, r13; hCluster
0x180040ccf  call    ClusterOpenEnum
0x180040cd4  mov     rbx, rax
0x180040cd7  mov     [rsp+1CF8h+var_1C18], rax
0x180040cdf  test    rax, rax
0x180040ce2  jz      loc_1800417B8
0x180040ce8  mov     esi, 100h
0x180040ced  mov     [rsp+1CF8h+cchName], esi
0x180040cf1  mov     [rsp+1CF8h+var_1C80], edi
0x180040cf5  mov     [rsp+1CF8h+var_1C88], edi
0x180040cf9  lea     r8, [rsp+1CF8h+var_1C80]; unsigned int *
0x180040cfe  mov     edx, esi; unsigned int
0x180040d00  mov     r12, [rsp+1CF8h+lpString2]
0x180040d08  mov     rcx, r12; wchar_t *
0x180040d0b  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x180040d10  test    eax, eax
0x180040d12  js      loc_1800417E8
0x180040d18  mov     r14d, edi
0x180040d1b  lea     rax, [rsp+1CF8h+cchName]
0x180040d20  mov     [rsp+1CF8h+lpcchName], rax; lpcchName
0x180040d25  lea     r9, [rsp+1CF8h+szName]; lpszName
0x180040d2d  lea     r8, [rsp+1CF8h+dwType]; lpdwType
0x180040d35  mov     edx, r14d; dwIndex
0x180040d38  mov     rcx, rbx; hEnum
0x180040d3b  call    ClusterEnum
0x180040d40  test    eax, eax
0x180040d42  jnz     loc_180040E9C
0x180040d48  lea     rax, [rsp+1CF8h+szName]
0x180040d50  mov     [rsp+1CF8h+var_1C30], rax
0x180040d58  mov     eax, esi
0x180040d5a  cmp     [rsp+1CF8h+var_1C80], esi
0x180040d5e  cmovb   eax, [rsp+1CF8h+var_1C80]
0x180040d63  mov     [rsp+1CF8h+cchCount2], eax; cchCount2
0x180040d67  mov     [rsp+1CF8h+lpcchName], r12; lpString2
0x180040d6c  mov     r9d, [rsp+1CF8h+cchName]; cchCount1
0x180040d71  lea     r8, [rsp+1CF8h+szName]; lpString1
0x180040d79  mov     edx, r15d; dwCmpFlags
0x180040d7c  mov     ecx, 400h; Locale
  ... truncated ...
```
