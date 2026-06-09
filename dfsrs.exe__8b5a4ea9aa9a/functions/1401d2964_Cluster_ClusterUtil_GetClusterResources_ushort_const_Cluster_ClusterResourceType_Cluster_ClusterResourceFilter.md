# Cluster::ClusterUtil::GetClusterResources(ushort const *,Cluster::_ClusterResourceType,Cluster::ClusterResourceFilter *,Cluster::RetrievalErrorPolicy,std::vector<Cluster::ClusterResource,std::allocator<Cluster::ClusterResource>> &)

- ea: `0x1401d2964`
- end: `0x1401d2e8e`
- name: `?GetClusterResources@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGW4_ClusterResourceType@2@PEAVClusterResourceFilter@2@W4RetrievalErrorPolicy@2@AEAV?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@@Z`
- size: `1322`
- prototype: ``
- caller_count: `8`
- callee_count: `23`
- tags: `registry_config, service_task`

## callers

- `0x14002018c`
- `0x140026430`
- `0x14010060c`
- `0x140141910`
- `0x1401d42b4`
- `0x1401d48d8`
- `0x1401d4bc4`
- `0x1401d654c`

## callees

- `0x14000cb00`
- `0x14000e34c`
- `0x14000ee94`
- `0x140011408`
- `0x14001c1ac`
- `0x14001cfa0`
- `0x14001e19c`
- `0x1400238e4`
- `0x14002c548`
- `0x14003c228`
- `0x14004671c`
- `0x14004691c`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401cff28`
- `0x1401d1594`
- `0x1401d2110`
- `0x1401d2964`
- `0x1401d60c8`
- `0x1401d759c`
- `0x1401d7cc0`
- `0x1401d964c`
- `0x1401d96d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401d2b80`
- `KERNEL32!GetLastError` at `0x1401d2b80`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2aa6`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2b72`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2d3f`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2e28`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2aa6`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2b72`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2d3f`
- `KERNEL32!GetCurrentThreadId` at `0x1401d2e28`
- `CLUSAPI!ClusterResourceTypeCloseEnum` at `0x1401d2dba`
- `CLUSAPI!ClusterResourceTypeCloseEnum` at `0x1401d2dba`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x1401d2b51`
- `CLUSAPI!ClusterResourceTypeOpenEnum` at `0x1401d2b51`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x1401d2bf3`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x1401d2c49`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x1401d2bf3`
- `CLUSAPI!ClusterResourceTypeEnum` at `0x1401d2c49`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Cluster::ClusterUtil::GetClusterResources(
        __int64 a1,
        int a2,
        Cluster::ClusterResourceFilter *a3,
        int a4,
        __int64 a5)
{
  __int64 v6; // rdi
  struct _HRESTYPEENUM *v7; // r13
  __int64 v8; // rsi
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  struct FrsStatus *StorageResourceTypeList; // rax
  __int64 v15; // rax
  DWORD CurrentThreadId; // eax
  __int64 v17; // rcx
  unsigned int *ResourceInformation; // rbx
  unsigned int v19; // r12d
  __int64 v20; // rcx
  __int64 v21; // r14
  __int64 v22; // rdx
  DWORD v23; // ebx
  DWORD LastError; // eax
  DWORD v25; // r15d
  DWORD v26; // esi
  WCHAR *v27; // r13
  DWORD v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  __int64 v32; // rcx
  DWORD v33; // eax
  __int64 v34; // rcx
  struct FrsStatus *v36; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A8h] BYREF
  HRESTYPEENUM hResTypeEnum; // [rsp+68h] [rbp-A0h]
  HCLUSTER hCluster; // [rsp+70h] [rbp-98h] BYREF
  WCHAR *v40; // [rsp+78h] [rbp-90h] BYREF
  void **v41; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v42[3]; // [rsp+88h] [rbp-80h] BYREF
  WCHAR *v43; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v45[8]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v46[8]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v47[8]; // [rsp+C0h] [rbp-48h] BYREF
  const wchar_t *v48; // [rsp+C8h] [rbp-40h] BYREF
  int v49; // [rsp+D0h] [rbp-38h]
  int v50; // [rsp+D4h] [rbp-34h]
  const wchar_t *v51; // [rsp+D8h] [rbp-30h]
  const wchar_t *v52; // [rsp+E0h] [rbp-28h] BYREF
  int v53; // [rsp+E8h] [rbp-20h]
  int v54; // [rsp+ECh] [rbp-1Ch]
  const wchar_t *v55; // [rsp+F0h] [rbp-18h]
  _BYTE v56[112]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 dwType; // [rsp+178h] [rbp+70h] BYREF
  DWORD cchName; // [rsp+180h] [rbp+78h] BYREF
  Cluster::ClusterResourceFilter *v59; // [rsp+188h] [rbp+80h]
  int v60; // [rsp+190h] [rbp+88h]

  v60 = a4;
  v59 = a3;
  dwType = a1;
  v6 = 0;
  hCluster = 0;
  v7 = 0;
  hResTypeEnum = 0;
  ObjList<FrsStringImpl<unsigned short,char>>::ObjList<FrsStringImpl<unsigned short,char>>(&v41);
  v8 = a5;
  std::vector<ServiceInfo *>::end(a5, v45);
  v10 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                    v9,
                    v46);
  std::vector<Cluster::ClusterResource>::erase(v11, v47, *v10);
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1:
        v15 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v37, L"DFS Replicated Folder");
        std::vector<FrsStringImpl<unsigned short,char>>::push_back(v42, v15);
        goto LABEL_6;
      case 2:
        StorageResourceTypeList = (struct FrsStatus *)Cluster::ClusterUtil::GetStorageResourceTypeList(0, &v41, L"CLUS");
        goto LABEL_14;
      case 3:
        v12 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v37, L"Network Name");
        std::vector<FrsStringImpl<unsigned short,char>>::push_back(v42, v12);
LABEL_6:
        FrsStringImpl<char,unsigned short>::ReleaseBody(&v37);
LABEL_15:
        ResourceInformation = (unsigned int *)Cluster::ClusterUtil::OpenClusterHandle(v13, &hCluster);
        v36 = (struct FrsStatus *)ResourceInformation;
        goto LABEL_16;
    }
  }
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v48 = L"Cluster::ClusterUtil::GetClusterResources";
    v49 = 3117;
    v50 = 2;
    v51 = L"CLUS";
    LODWORD(v37) = a2;
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v48, L"[CLUSTER] Not a valid resource type. resType:%?", &v37);
  }
  CurrentThreadId = GetCurrentThreadId();
  StorageResourceTypeList = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                  v17,
                                                  87,
                                                  0,
                                                  1,
                                                  "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                  "Cluster::ClusterUtil::GetClusterResources",
                                                  3118,
                                                  CurrentThreadId,
                                                  0);
LABEL_14:
  ResourceInformation = (unsigned int *)StorageResourceTypeList;
  v36 = StorageResourceTypeList;
  if ( !StorageResourceTypeList )
    goto LABEL_15;
LABEL_16:
  v19 = 0;
  if ( ResourceInformation )
    goto LABEL_48;
  v20 = v42[0];
  v21 = (__int64)(v42[1] - v42[0]) >> 3;
  do
  {
    if ( v19 >= (unsigned int)v21 )
      break;
    v22 = *(_QWORD *)(v20 + 8LL * v19);
    v44 = v22;
    if ( !*(_BYTE *)(v22 + 16) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v22);
      ResourceInformation = (unsigned int *)v36;
    }
    if ( !ResourceInformation )
    {
      v7 = ClusterResourceTypeOpenEnum(hCluster, (LPCWSTR)(v22 + 18), 2u);
      hResTypeEnum = v7;
      if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v23 = GetCurrentThreadId();
        LastError = GetLastError();
        ResourceInformation = (unsigned int *)FrsStatusList::PushNewError(
                                                "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                LastError,
                                                0,
                                                1,
                                                "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                "Cluster::ClusterUtil::GetClusterResources",
                                                3144,
                                                v23,
                                                0);
        v36 = (struct FrsStatus *)ResourceInformation;
      }
    }
    v25 = 0;
    while ( !ResourceInformation )
    {
      LODWORD(dwType) = 0;
      cchName = 0;
      v40 = 0;
      v26 = ClusterResourceTypeEnum(v7, v25, (LPDWORD)&dwType, 0, &cchName);
      if ( !v26 )
      {
        v27 = (WCHAR *)operator_new(saturated_mul(++cchName, 2u));
        v40 = v27;
        v26 = ClusterResourceTypeEnum(hResTypeEnum, v25, (LPDWORD)&dwType, v27, &cchName);
        if ( !v26 )
        {
          Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)v56);
          ResourceInformation = (unsigned int *)Cluster::ClusterResource::LoadResourceInformation(
                                                  (Cluster::ClusterResource *)v56,
                                                  hCluster,
                                                  v27);
          v36 = (struct FrsStatus *)ResourceInformation;
          if ( ResourceInformation )
          {
            if ( v60 == 2 )
            {
              if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
              {
                v52 = L"Cluster::ClusterUtil::GetClusterResources";
                v53 = 3217;
                v54 = 3;
                v55 = L"CLUS";
                v43 = v27;
                dbgobj::DbgPrint<unsigned short,unsigned short const *,FrsStatus>(
                  &v52,
                  L"[CLUSTER] (Ignored) Failed to retrieve resource information. Skipping resource. resName:%? Error:%?",
                  &v43,
                  ResourceInformation);
              }
              CLEAR_ERROR(&v36);
              ResourceInformation = (unsigned int *)v36;
            }
          }
          else if ( !v59
                 || (unsigned int)Cluster::ClusterResourceFilter::FilterResource(
                                    v59,
                                    (struct Cluster::ClusterResource *)v56) )
          {
            std::vector<Cluster::ClusterResource>::push_back(a5, v56);
          }
          Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)v56);
          goto LABEL_42;
        }
        v7 = hResTypeEnum;
      }
      if ( v26 == 259 )
      {
        scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v40);
        break;
      }
      v28 = GetCurrentThreadId();
      ResourceInformation = (unsigned int *)FrsStatusList::PushNewError(
                                              v29,
                                              v26,
                                              0,
                                              1,
                                              "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                              "Cluster::ClusterUtil::GetClusterResources",
                                              3237,
                                              v28,
                                              0);
      v36 = (struct FrsStatus *)ResourceInformation;
LABEL_42:
      ++v25;
      scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v40);
      v7 = hResTypeEnum;
    }
    if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      ClusterResourceTypeCloseEnum(v7);
    FrsStringImpl<char,unsigned short>::ReleaseBody(&v44);
    ++v19;
    v20 = v42[0];
  }
  while ( !ResourceInformation );
  v8 = a5;
LABEL_48:
  Cluster::ClusterUtil::CloseClusterHandle(&hCluster);
  if ( ResourceInformation )
  {
    std::vector<ServiceInfo *>::end(v8, v47);
    v31 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v30,
                      v46);
    std::vector<Cluster::ClusterResource>::erase(v32, v45, *v31);
    v33 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v34,
           ResourceInformation[1],
           ResourceInformation[2],
           *ResourceInformation,
           "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
           "Cluster::ClusterUtil::GetClusterResources",
           3267,
           v33,
           ResourceInformation);
  }
  v41 = &ObjList<FrsStringImpl<unsigned short,char>>::`vftable';
  std::vector<FrsStringImpl<unsigned short,char>>::_Tidy(v42);
  return v6;
}

```

## disassembly

```asm
0x1401d2964  mov     rax, rsp
0x1401d2967  mov     [rax+20h], r9d
0x1401d296b  mov     [rax+18h], r8
0x1401d296f  mov     [rax+8], rcx
0x1401d2973  push    rbp
0x1401d2974  push    rbx
0x1401d2975  push    rsi
0x1401d2976  push    rdi
0x1401d2977  push    r12
0x1401d2979  push    r13
0x1401d297b  push    r14
0x1401d297d  push    r15
0x1401d297f  lea     rbp, [rax-68h]
0x1401d2983  sub     rsp, 128h
0x1401d298a  mov     ebx, edx
0x1401d298c  xor     edi, edi
0x1401d298e  mov     [rsp+160h+hCluster], rdi
0x1401d2993  mov     r13d, edi
0x1401d2996  mov     [rsp+160h+hResTypeEnum], rdi
0x1401d299b  lea     rcx, [rsp+160h+var_E8]
0x1401d29a0  call    ??0?$ObjList@V?$FrsStringImpl@GD@@@@QEAA@XZ; ObjList<FrsStringImpl<ushort,char>>::ObjList<FrsStringImpl<ushort,char>>(void)
0x1401d29a5  nop
0x1401d29a6  lea     rdx, [rbp+60h+var_B8]
0x1401d29aa  mov     rsi, [rbp+60h+arg_20]
0x1401d29b1  mov     rcx, rsi
0x1401d29b4  call    ?end@?$vector@PEAVServiceInfo@@V?$allocator@PEAVServiceInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVServiceInfo@@@std@@@std@@@2@XZ; std::vector<ServiceInfo *>::end(void)
0x1401d29b9  mov     r9, [rax]
0x1401d29bc  lea     rdx, [rbp+60h+var_B0]
0x1401d29c0  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x1401d29c5  mov     r8, [rax]
0x1401d29c8  lea     rdx, [rbp+60h+var_A8]
0x1401d29cc  call    ?erase@?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@0@Z; std::vector<Cluster::ClusterResource>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>)
0x1401d29d1  mov     ecx, ebx
0x1401d29d3  lea     rdx, aClusterCluster_62; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d29da  lea     r8, aClus; "CLUS"
0x1401d29e1  lea     r15, aClusterCluster_54; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d29e8  lea     r14, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d29ef  test    ebx, ebx
0x1401d29f1  jz      short loc_1401D2A60
0x1401d29f3  sub     ecx, 1
0x1401d29f6  jz      short loc_1401D2A3F
0x1401d29f8  sub     ecx, 1
0x1401d29fb  jz      short loc_1401D2A30
0x1401d29fd  cmp     ecx, 1
0x1401d2a00  jnz     short loc_1401D2A60
0x1401d2a02  lea     rdx, aNetworkName; "Network Name"
0x1401d2a09  lea     rcx, [rsp+160h+var_108]
0x1401d2a0e  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d2a13  nop
0x1401d2a14  mov     rdx, rax
0x1401d2a17  lea     rcx, [rbp+60h+var_E0]
0x1401d2a1b  call    ?push_back@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXAEBV?$FrsStringImpl@GD@@@Z; std::vector<FrsStringImpl<ushort,char>>::push_back(FrsStringImpl<ushort,char> const &)
0x1401d2a20  nop
0x1401d2a21  lea     rcx, [rsp+160h+var_108]
0x1401d2a26  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d2a2b  jmp     loc_1401D2AEC
0x1401d2a30  lea     rdx, [rsp+160h+var_E8]
0x1401d2a35  call    ?GetStorageResourceTypeList@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGAEAV?$ObjList@V?$FrsStringImpl@GD@@@@@Z; Cluster::ClusterUtil::GetStorageResourceTypeList(ushort const *,ObjList<FrsStringImpl<ushort,char>> &)
0x1401d2a3a  jmp     loc_1401D2ADF
0x1401d2a3f  lea     rdx, szResourceType; "DFS Replicated Folder"
0x1401d2a46  lea     rcx, [rsp+160h+var_108]
0x1401d2a4b  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1401d2a50  nop
0x1401d2a51  mov     rdx, rax
0x1401d2a54  lea     rcx, [rbp+60h+var_E0]
0x1401d2a58  call    ?push_back@?$vector@V?$FrsStringImpl@GD@@V?$allocator@V?$FrsStringImpl@GD@@@std@@@std@@QEAAXAEBV?$FrsStringImpl@GD@@@Z; std::vector<FrsStringImpl<ushort,char>>::push_back(FrsStringImpl<ushort,char> const &)
0x1401d2a5d  nop
0x1401d2a5e  jmp     short loc_1401D2A21
0x1401d2a60  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d2a67  test    rax, rax
0x1401d2a6a  jz      short loc_1401D2AA6
0x1401d2a6c  cmp     [rax+40h], edi
0x1401d2a6f  jz      short loc_1401D2AA6
0x1401d2a71  cmp     dword ptr [rax+38h], 2
0x1401d2a75  jl      short loc_1401D2AA6
0x1401d2a77  mov     [rbp+60h+var_A0], rdx
0x1401d2a7b  mov     [rbp+60h+var_98], 0C2Dh
0x1401d2a82  mov     [rbp+60h+var_94], 2
0x1401d2a89  mov     [rbp+60h+var_90], r8
0x1401d2a8d  mov     dword ptr [rsp+160h+var_108], ebx
0x1401d2a91  lea     r8, [rsp+160h+var_108]
0x1401d2a96  lea     rdx, aClusterNotAVal; "[CLUSTER] Not a valid resource type. re"...
0x1401d2a9d  lea     rcx, [rbp+60h+var_A0]
0x1401d2aa1  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1401d2aa6  call    cs:__imp_GetCurrentThreadId
0x1401d2aad  nop     dword ptr [rax+rax+00h]
0x1401d2ab2  mov     [rsp+40h], rdi
0x1401d2ab7  mov     dword ptr [rsp+160h+var_128], eax
0x1401d2abb  mov     [rsp+160h+var_130], 0C2Eh
0x1401d2ac3  mov     qword ptr [rsp+160h+var_138], r15
0x1401d2ac8  mov     [rsp+160h+lpcchName], r14
0x1401d2acd  mov     r9d, 1
0x1401d2ad3  xor     r8d, r8d
0x1401d2ad6  lea     edx, [r9+56h]
0x1401d2ada  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d2adf  mov     rbx, rax
0x1401d2ae2  mov     [rsp+160h+var_110], rax
0x1401d2ae7  test    rax, rax
0x1401d2aea  jnz     short loc_1401D2AFE
0x1401d2aec  lea     rdx, [rsp+160h+hCluster]; struct _HCLUSTER **
0x1401d2af1  call    ?OpenClusterHandle@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::OpenClusterHandle(ushort const *,_HCLUSTER * &)
0x1401d2af6  mov     rbx, rax
0x1401d2af9  mov     [rsp+160h+var_110], rax
0x1401d2afe  mov     r12d, edi
0x1401d2b01  test    rbx, rbx
0x1401d2b04  jnz     loc_1401D2DF5
0x1401d2b0a  mov     r14, [rbp+60h+var_D8]
0x1401d2b0e  mov     rcx, [rbp+60h+var_E0]
0x1401d2b12  sub     r14, rcx
0x1401d2b15  sar     r14, 3
0x1401d2b19  cmp     r12d, r14d
0x1401d2b1c  jnb     loc_1401D2DE7
0x1401d2b22  mov     eax, r12d
0x1401d2b25  mov     rdx, [rcx+rax*8]
0x1401d2b29  mov     [rbp+60h+var_C0], rdx
0x1401d2b2d  cmp     [rdx+10h], dil
0x1401d2b31  jnz     short loc_1401D2B3B
0x1401d2b33  lock inc dword ptr [rdx]
0x1401d2b36  mov     rbx, [rsp+160h+var_110]
0x1401d2b3b  test    rbx, rbx
0x1401d2b3e  jnz     loc_1401D2BC6
0x1401d2b44  add     rdx, 12h; lpszResourceTypeName
0x1401d2b48  lea     r8d, [rbx+2]; dwType
0x1401d2b4c  mov     rcx, [rsp+160h+hCluster]; hCluster
0x1401d2b51  call    cs:__imp_ClusterResourceTypeOpenEnum
0x1401d2b58  nop     dword ptr [rax+rax+00h]
0x1401d2b5d  mov     r13, rax
0x1401d2b60  mov     [rsp+160h+hResTypeEnum], rax
0x1401d2b65  lea     rcx, [rax+1]
0x1401d2b69  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1401d2b70  jnz     short loc_1401D2BC6
0x1401d2b72  call    cs:__imp_GetCurrentThreadId
0x1401d2b79  nop     dword ptr [rax+rax+00h]
0x1401d2b7e  mov     ebx, eax
0x1401d2b80  call    cs:__imp_GetLastError
0x1401d2b87  nop     dword ptr [rax+rax+00h]
0x1401d2b8c  mov     [rsp+40h], rdi
0x1401d2b91  mov     dword ptr [rsp+160h+var_128], ebx
0x1401d2b95  mov     [rsp+160h+var_130], 0C48h
0x1401d2b9d  mov     qword ptr [rsp+160h+var_138], r15
0x1401d2ba2  lea     rcx, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d2ba9  mov     [rsp+160h+lpcchName], rcx
0x1401d2bae  mov     r9d, 1
0x1401d2bb4  xor     r8d, r8d
0x1401d2bb7  mov     edx, eax
0x1401d2bb9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d2bbe  mov     rbx, rax
0x1401d2bc1  mov     [rsp+160h+var_110], rax
0x1401d2bc6  mov     r15d, edi
0x1401d2bc9  test    rbx, rbx
0x1401d2bcc  jnz     loc_1401D2DAD
0x1401d2bd2  mov     dword ptr [rbp+60h+dwType], edi
0x1401d2bd5  mov     [rbp+60h+cchName], edi
0x1401d2bd8  mov     [rsp+160h+var_F0], rdi
0x1401d2bdd  lea     rax, [rbp+60h+cchName]
0x1401d2be1  mov     [rsp+160h+lpcchName], rax; lpcchName
0x1401d2be6  xor     r9d, r9d; lpszName
0x1401d2be9  lea     r8, [rbp+60h+dwType]; lpdwType
0x1401d2bed  mov     edx, r15d; dwIndex
0x1401d2bf0  mov     rcx, r13; hResTypeEnum
0x1401d2bf3  call    cs:__imp_ClusterResourceTypeEnum
0x1401d2bfa  nop     dword ptr [rax+rax+00h]
0x1401d2bff  mov     esi, eax
0x1401d2c01  test    eax, eax
0x1401d2c03  jnz     loc_1401D2D37
0x1401d2c09  mov     eax, [rbp+60h+cchName]
0x1401d2c0c  inc     eax
0x1401d2c0e  mov     [rbp+60h+cchName], eax
0x1401d2c11  mov     ecx, eax
0x1401d2c13  lea     eax, [rbx+2]
0x1401d2c16  mul     rcx
0x1401d2c19  lea     rcx, [rbx-1]
0x1401d2c1d  cmovo   rax, rcx
0x1401d2c21  mov     rcx, rax; unsigned __int64
0x1401d2c24  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d2c29  mov     r13, rax
0x1401d2c2c  mov     [rsp+160h+var_F0], rax
0x1401d2c31  lea     rax, [rbp+60h+cchName]
0x1401d2c35  mov     [rsp+160h+lpcchName], rax; lpcchName
0x1401d2c3a  mov     r9, r13; lpszName
0x1401d2c3d  lea     r8, [rbp+60h+dwType]; lpdwType
0x1401d2c41  mov     edx, r15d; dwIndex
0x1401d2c44  mov     rcx, [rsp+160h+hResTypeEnum]; hResTypeEnum
0x1401d2c49  call    cs:__imp_ClusterResourceTypeEnum
0x1401d2c50  nop     dword ptr [rax+rax+00h]
0x1401d2c55  mov     esi, eax
0x1401d2c57  test    eax, eax
0x1401d2c59  jnz     loc_1401D2D32
0x1401d2c5f  lea     rcx, [rbp+60h+var_70]; this
0x1401d2c63  call    ??0ClusterResource@Cluster@@QEAA@XZ; Cluster::ClusterResource::ClusterResource(void)
0x1401d2c68  nop
0x1401d2c69  mov     r8, r13; unsigned __int16 *
0x1401d2c6c  mov     rdx, [rsp+160h+hCluster]; struct _HCLUSTER *
0x1401d2c71  lea     rcx, [rbp+60h+var_70]; this
0x1401d2c75  call    ?LoadResourceInformation@ClusterResource@Cluster@@QEAAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBG@Z; Cluster::ClusterResource::LoadResourceInformation(_HCLUSTER *,ushort const *)
0x1401d2c7a  mov     rbx, rax
0x1401d2c7d  mov     [rsp+160h+var_110], rax
0x1401d2c82  test    rax, rax
0x1401d2c85  jnz     short loc_1401D2CB9
0x1401d2c87  mov     rax, [rbp+60h+arg_10]
0x1401d2c8e  test    rax, rax
0x1401d2c91  jz      short loc_1401D2CA7
0x1401d2c93  lea     rdx, [rbp+60h+var_70]; struct Cluster::ClusterResource *
0x1401d2c97  mov     rcx, rax; this
0x1401d2c9a  call    ?FilterResource@ClusterResourceFilter@Cluster@@QEAAHAEAVClusterResource@2@@Z; Cluster::ClusterResourceFilter::FilterResource(Cluster::ClusterResource &)
0x1401d2c9f  test    eax, eax
0x1401d2ca1  jz      loc_1401D2D27
0x1401d2ca7  lea     rdx, [rbp+60h+var_70]
0x1401d2cab  mov     rcx, [rbp+60h+arg_20]
0x1401d2cb2  call    ?push_back@?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@QEAAXAEBVClusterResource@Cluster@@@Z; std::vector<Cluster::ClusterResource>::push_back(Cluster::ClusterResource const &)
0x1401d2cb7  jmp     short loc_1401D2D27
0x1401d2cb9  cmp     [rbp+60h+arg_18], 2
0x1401d2cc0  jnz     short loc_1401D2D27
0x1401d2cc2  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d2cc9  test    rax, rax
0x1401d2ccc  jz      short loc_1401D2D18
0x1401d2cce  cmp     [rax+40h], edi
0x1401d2cd1  jz      short loc_1401D2D18
0x1401d2cd3  cmp     dword ptr [rax+38h], 3
0x1401d2cd7  jl      short loc_1401D2D18
0x1401d2cd9  lea     rax, aClusterCluster_62; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d2ce0  mov     [rbp+60h+var_88], rax
0x1401d2ce4  mov     [rbp+60h+var_80], 0C91h
0x1401d2ceb  mov     [rbp+60h+var_7C], 3
0x1401d2cf2  lea     rax, aClus; "CLUS"
0x1401d2cf9  mov     [rbp+60h+var_78], rax
0x1401d2cfd  mov     [rbp+60h+var_C8], r13
0x1401d2d01  mov     r9, rbx
0x1401d2d04  lea     r8, [rbp+60h+var_C8]
0x1401d2d08  lea     rdx, aClusterIgnored_51; "[CLUSTER] (Ignored) Failed to retrieve "...
0x1401d2d0f  lea     rcx, [rbp+60h+var_88]
0x1401d2d13  call    ??$DbgPrint@GPEBGVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBQEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,ushort const *,FrsStatus>(ushort const *,ushort const * const &,FrsStatus const &)
0x1401d2d18  lea     rcx, [rsp+160h+var_110]; struct FrsStatus **
0x1401d2d1d  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401d2d22  mov     rbx, [rsp+160h+var_110]
0x1401d2d27  lea     rcx, [rbp+60h+var_70]; this
0x1401d2d2b  call    ??1ClusterResource@Cluster@@QEAA@XZ; Cluster::ClusterResource::~ClusterResource(void)
0x1401d2d30  jmp     short loc_1401D2D8C
0x1401d2d32  mov     r13, [rsp+160h+hResTypeEnum]
0x1401d2d37  cmp     esi, 103h
0x1401d2d3d  jz      short loc_1401D2DA3
0x1401d2d3f  call    cs:__imp_GetCurrentThreadId
0x1401d2d46  nop     dword ptr [rax+rax+00h]
0x1401d2d4b  mov     [rsp+40h], rdi
0x1401d2d50  mov     dword ptr [rsp+160h+var_128], eax
0x1401d2d54  mov     [rsp+160h+var_130], 0CA5h
0x1401d2d5c  lea     rax, aClusterCluster_54; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d2d63  mov     qword ptr [rsp+160h+var_138], rax
0x1401d2d68  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d2d6f  mov     [rsp+160h+lpcchName], rax
0x1401d2d74  mov     r9d, 1
0x1401d2d7a  xor     r8d, r8d
0x1401d2d7d  mov     edx, esi
0x1401d2d7f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d2d84  mov     rbx, rax
0x1401d2d87  mov     [rsp+160h+var_110], rax
0x1401d2d8c  inc     r15d
0x1401d2d8f  lea     rcx, [rsp+160h+var_F0]
0x1401d2d94  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d2d99  mov     r13, [rsp+160h+hResTypeEnum]
0x1401d2d9e  jmp     loc_1401D2BC9
0x1401d2da3  lea     rcx, [rsp+160h+var_F0]
0x1401d2da8  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d2dad  lea     rax, [r13-1]
0x1401d2db1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401d2db5  ja      short loc_1401D2DC7
0x1401d2db7  mov     rcx, r13; hResTypeEnum
0x1401d2dba  call    cs:__imp_ClusterResourceTypeCloseEnum
0x1401d2dc1  nop     dword ptr [rax+rax+00h]
0x1401d2dc6  nop
0x1401d2dc7  lea     rcx, [rbp+60h+var_C0]
0x1401d2dcb  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401d2dd0  inc     r12d
0x1401d2dd3  test    rbx, rbx
0x1401d2dd6  mov     rcx, [rbp+60h+var_E0]
0x1401d2dda  lea     r15, aClusterCluster_54; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d2de1  jz      loc_1401D2B19
0x1401d2de7  mov     rsi, [rbp+60h+arg_20]
0x1401d2dee  lea     r14, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d2df5  lea     rcx, [rsp+160h+hCluster]; struct _HCLUSTER **
0x1401d2dfa  call    ?CloseClusterHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::CloseClusterHandle(_HCLUSTER * &)
0x1401d2dff  test    rbx, rbx
0x1401d2e02  jz      short loc_1401D2E61
0x1401d2e04  lea     rdx, [rbp+60h+var_A8]
0x1401d2e08  mov     rcx, rsi
0x1401d2e0b  call    ?end@?$vector@PEAVServiceInfo@@V?$allocator@PEAVServiceInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVServiceInfo@@@std@@@std@@@2@XZ; std::vector<ServiceInfo *>::end(void)
0x1401d2e10  mov     r9, [rax]
0x1401d2e13  lea     rdx, [rbp+60h+var_B0]
0x1401d2e17  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x1401d2e1c  mov     r8, [rax]
0x1401d2e1f  lea     rdx, [rbp+60h+var_B8]
0x1401d2e23  call    ?erase@?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@0@Z; std::vector<Cluster::ClusterResource>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>)
0x1401d2e28  call    cs:__imp_GetCurrentThreadId
0x1401d2e2f  nop     dword ptr [rax+rax+00h]
0x1401d2e34  mov     [rsp+40h], rbx
0x1401d2e39  mov     dword ptr [rsp+160h+var_128], eax
0x1401d2e3d  mov     [rsp+160h+var_130], 0CC3h
0x1401d2e45  mov     qword ptr [rsp+160h+var_138], r15
0x1401d2e4a  mov     [rsp+160h+lpcchName], r14
0x1401d2e4f  mov     r9d, [rbx]
  ... truncated ...
```
