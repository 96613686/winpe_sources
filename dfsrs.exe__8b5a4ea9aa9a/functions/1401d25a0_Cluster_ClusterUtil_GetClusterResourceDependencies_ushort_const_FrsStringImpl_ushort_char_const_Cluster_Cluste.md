# Cluster::ClusterUtil::GetClusterResourceDependencies(ushort const *,FrsStringImpl<ushort,char> const &,Cluster::_ClusterResourceType,Cluster::ClusterResourceFilter *,Cluster::RetrievalErrorPolicy,std::vector<Cluster::ClusterResource,std::allocator<Cluster::ClusterResource>> &)

- ea: `0x1401d25a0`
- end: `0x1401d295b`
- name: `?GetClusterResourceDependencies@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBGAEBV?$FrsStringImpl@GD@@W4_ClusterResourceType@2@PEAVClusterResourceFilter@2@W4RetrievalErrorPolicy@2@AEAV?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwType, __int64)`
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x1401d09fc`
- `0x1401d571c`
- `0x1401d6e60`
- `0x1401d7e98`

## callees

- `0x14000cb00`
- `0x140011408`
- `0x14001e19c`
- `0x1400238e4`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401cff28`
- `0x1401d1594`
- `0x1401d15fc`
- `0x1401d2110`
- `0x1401d25a0`
- `0x1401d56ec`
- `0x1401d759c`
- `0x1401d7bfc`
- `0x1401d964c`
- `0x1401d96d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401d26ff`
- `KERNEL32!GetLastError` at `0x1401d26ff`
- `KERNEL32!GetCurrentThreadId` at `0x1401d266d`
- `KERNEL32!GetCurrentThreadId` at `0x1401d26f1`
- `KERNEL32!GetCurrentThreadId` at `0x1401d284b`
- `KERNEL32!GetCurrentThreadId` at `0x1401d28fc`
- `KERNEL32!GetCurrentThreadId` at `0x1401d266d`
- `KERNEL32!GetCurrentThreadId` at `0x1401d26f1`
- `KERNEL32!GetCurrentThreadId` at `0x1401d284b`
- `KERNEL32!GetCurrentThreadId` at `0x1401d28fc`
- `CLUSAPI!ClusterResourceCloseEnum` at `0x1401d28b4`
- `CLUSAPI!ClusterResourceCloseEnum` at `0x1401d28b4`
- `CLUSAPI!ClusterResourceEnum` at `0x1401d2765`
- `CLUSAPI!ClusterResourceEnum` at `0x1401d27b9`
- `CLUSAPI!ClusterResourceEnum` at `0x1401d2765`
- `CLUSAPI!ClusterResourceEnum` at `0x1401d27b9`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x1401d26d5`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x1401d26d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Cluster::ClusterUtil::GetClusterResourceDependencies(
        unsigned __int16 *a1,
        __int64 a2,
        DWORD a3,
        Cluster::ClusterResourceFilter *a4,
        DWORD dwType,
        __int64 a6)
{
  __int64 v8; // rdi
  struct _HRESENUM *v9; // rsi
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  struct FrsStatus *ResourceInformation; // rbx
  DWORD v17; // ebx
  DWORD LastError; // eax
  __int64 v19; // rcx
  DWORD v20; // r15d
  DWORD v21; // r14d
  unsigned __int16 *v22; // r12
  DWORD v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  DWORD v28; // eax
  __int64 v29; // rcx
  HRESOURCE hResource; // [rsp+58h] [rbp-39h] BYREF
  struct _HCLUSTER *v32; // [rsp+60h] [rbp-31h] BYREF
  char v33[8]; // [rsp+68h] [rbp-29h] BYREF
  char v34[8]; // [rsp+70h] [rbp-21h] BYREF
  const wchar_t *v35; // [rsp+78h] [rbp-19h] BYREF
  int v36; // [rsp+80h] [rbp-11h]
  int v37; // [rsp+84h] [rbp-Dh]
  const wchar_t *v38; // [rsp+88h] [rbp-9h]
  unsigned __int16 *v39; // [rsp+E8h] [rbp+57h] BYREF
  DWORD cchName; // [rsp+F8h] [rbp+67h] BYREF
  Cluster::ClusterResourceFilter *v41; // [rsp+100h] [rbp+6Fh]

  v41 = a4;
  v39 = a1;
  v8 = 0;
  v32 = 0;
  hResource = 0;
  v9 = 0;
  std::vector<ServiceInfo *>::end(a6, &v39);
  v11 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                    v10,
                    v33);
  std::vector<Cluster::ClusterResource>::erase(v12, v34, *v11);
  if ( a3 - 1 <= 3 )
    goto LABEL_7;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
  {
    v35 = L"Cluster::ClusterUtil::GetClusterResourceDependencies";
    v36 = 2898;
    v37 = 2;
    v38 = L"CLUS";
    cchName = a3;
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v35, L"[CLUSTER] Not a valid resource type. resType:%?", &cchName);
  }
  CurrentThreadId = GetCurrentThreadId();
  ResourceInformation = (struct FrsStatus *)FrsStatusList::PushNewError(
                                              v15,
                                              87,
                                              0,
                                              1,
                                              "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                              "Cluster::ClusterUtil::GetClusterResourceDependencies",
                                              2899,
                                              CurrentThreadId,
                                              0);
  if ( !ResourceInformation )
  {
LABEL_7:
    ResourceInformation = Cluster::ClusterUtil::OpenClusterAndResource(
                            v13,
                            (const unsigned __int16 *)(*(_QWORD *)a2 + 18LL),
                            &v32,
                            &hResource);
    if ( !ResourceInformation )
    {
      v9 = ClusterResourceOpenEnum(hResource, 1u);
      if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v17 = GetCurrentThreadId();
        LastError = GetLastError();
        ResourceInformation = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                    v19,
                                                    LastError,
                                                    0,
                                                    1,
                                                    "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                    "Cluster::ClusterUtil::GetClusterResourceDependencies",
                                                    2918,
                                                    v17,
                                                    0);
      }
    }
  }
  v20 = 0;
  while ( !ResourceInformation )
  {
    dwType = 0;
    cchName = 0;
    v39 = 0;
    v21 = ClusterResourceEnum(v9, v20, &dwType, 0, &cchName);
    if ( v21
      || (++cchName,
          v22 = (unsigned __int16 *)operator_new(saturated_mul(cchName, 2u)),
          v39 = v22,
          (v21 = ClusterResourceEnum(v9, v20, &dwType, v22, &cchName)) != 0) )
    {
      if ( v21 == 259 )
      {
        scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v39);
        break;
      }
      v23 = GetCurrentThreadId();
      ResourceInformation = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                  v24,
                                                  v21,
                                                  0,
                                                  1,
                                                  "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
                                                  "Cluster::ClusterUtil::GetClusterResourceDependencies",
                                                  3014,
                                                  v23,
                                                  0);
    }
    else
    {
      Cluster::ClusterResource::ClusterResource((Cluster::ClusterResource *)&v35);
      ResourceInformation = Cluster::ClusterResource::LoadResourceInformation(
                              (Cluster::ClusterResource *)&v35,
                              v32,
                              v22);
      if ( !ResourceInformation
        && (!v41
         || (unsigned int)Cluster::ClusterResourceFilter::FilterResource(v41, (struct Cluster::ClusterResource *)&v35))
        && (a3 == 4 || a3 == (unsigned int)Cluster::ClusterResource::GetResourceClusterType(&v35)) )
      {
        std::vector<Cluster::ClusterResource>::push_back(a6, &v35);
      }
      Cluster::ClusterResource::~ClusterResource((Cluster::ClusterResource *)&v35);
    }
    ++v20;
    scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v39);
  }
  if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    ClusterResourceCloseEnum(v9);
  Cluster::ClusterUtil::CloseResourceHandle(&hResource);
  Cluster::ClusterUtil::CloseClusterHandle(&v32);
  if ( ResourceInformation )
  {
    std::vector<ServiceInfo *>::end(a6, &v39);
    v26 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(
                      v25,
                      v34);
    std::vector<Cluster::ClusterResource>::erase(v27, v33, *v26);
    v28 = GetCurrentThreadId();
    return FrsStatusList::PushNewError(
             v29,
             *((unsigned int *)ResourceInformation + 1),
             *((unsigned int *)ResourceInformation + 2),
             *(unsigned int *)ResourceInformation,
             "base\\fs\\remotefs\\frs\\src\\cluster\\cluster.cpp",
             "Cluster::ClusterUtil::GetClusterResourceDependencies",
             3046,
             v28,
             ResourceInformation);
  }
  return v8;
}

```

## disassembly

```asm
0x1401d25a0  mov     rax, rsp
0x1401d25a3  mov     [rax+10h], rbx
0x1401d25a7  mov     [rax+20h], r9
0x1401d25ab  mov     [rax+8], rcx
0x1401d25af  push    rbp
0x1401d25b0  push    rsi
0x1401d25b1  push    rdi
0x1401d25b2  push    r12
0x1401d25b4  push    r13
0x1401d25b6  push    r14
0x1401d25b8  push    r15
0x1401d25ba  lea     rbp, [rax-4Fh]
0x1401d25be  sub     rsp, 0A0h
0x1401d25c5  mov     r13d, r8d
0x1401d25c8  mov     r14, rdx
0x1401d25cb  xor     edi, edi
0x1401d25cd  mov     [rbp+47h+var_78], rdi
0x1401d25d1  mov     [rbp+47h+hResource], rdi
0x1401d25d5  mov     esi, edi
0x1401d25d7  lea     rdx, [rbp+47h+arg_0]
0x1401d25db  mov     r12, [rbp+47h+arg_28]
0x1401d25df  mov     rcx, r12
0x1401d25e2  call    ?end@?$vector@PEAVServiceInfo@@V?$allocator@PEAVServiceInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVServiceInfo@@@std@@@std@@@2@XZ; std::vector<ServiceInfo *>::end(void)
0x1401d25e7  mov     r9, [rax]
0x1401d25ea  lea     rdx, [rbp+47h+var_70]
0x1401d25ee  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x1401d25f3  mov     r8, [rax]
0x1401d25f6  lea     rdx, [rbp+47h+var_68]
0x1401d25fa  call    ?erase@?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@0@Z; std::vector<Cluster::ClusterResource>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>)
0x1401d25ff  lea     eax, [r13-1]
0x1401d2603  lea     r12, aClusterCluster_46; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d260a  lea     r15, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d2611  cmp     eax, 3
0x1401d2614  jbe     loc_1401D26B2
0x1401d261a  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1401d2621  test    rax, rax
0x1401d2624  jz      short loc_1401D266D
0x1401d2626  cmp     [rax+40h], edi
0x1401d2629  jz      short loc_1401D266D
0x1401d262b  cmp     dword ptr [rax+38h], 2
0x1401d262f  jl      short loc_1401D266D
0x1401d2631  lea     rax, aClusterCluster_23; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d2638  mov     [rbp+47h+var_60], rax
0x1401d263c  mov     [rbp+47h+var_58], 0B52h
0x1401d2643  mov     [rbp+47h+var_54], 2
0x1401d264a  lea     rax, aClus; "CLUS"
0x1401d2651  mov     [rbp+47h+var_50], rax
0x1401d2655  mov     [rbp+47h+cchName], r13d
0x1401d2659  lea     r8, [rbp+47h+cchName]
0x1401d265d  lea     rdx, aClusterNotAVal; "[CLUSTER] Not a valid resource type. re"...
0x1401d2664  lea     rcx, [rbp+47h+var_60]
0x1401d2668  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1401d266d  call    cs:__imp_GetCurrentThreadId
0x1401d2674  nop     dword ptr [rax+rax+00h]
0x1401d2679  mov     [rsp+40h], rdi
0x1401d267e  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401d2682  mov     [rsp+0D0h+var_A0], 0B53h
0x1401d268a  mov     qword ptr [rsp+0D0h+var_A8], r12
0x1401d268f  mov     [rsp+0D0h+lpcchName], r15
0x1401d2694  mov     r9d, 1
0x1401d269a  xor     r8d, r8d
0x1401d269d  lea     edx, [r9+56h]
0x1401d26a1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d26a6  mov     rbx, rax
0x1401d26a9  test    rax, rax
0x1401d26ac  jnz     loc_1401D2739
0x1401d26b2  mov     rdx, [r14]
0x1401d26b5  add     rdx, 12h; unsigned __int16 *
0x1401d26b9  lea     r9, [rbp+47h+hResource]; struct _HRESOURCE **
0x1401d26bd  lea     r8, [rbp+47h+var_78]; struct _HCLUSTER **
0x1401d26c1  call    ?OpenClusterAndResource@ClusterUtil@Cluster@@SAPEAVFrsStatus@@PEBG0AEAPEAU_HCLUSTER@@AEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::OpenClusterAndResource(ushort const *,ushort const *,_HCLUSTER * &,_HRESOURCE * &)
0x1401d26c6  mov     rbx, rax
0x1401d26c9  test    rax, rax
0x1401d26cc  jnz     short loc_1401D2739
0x1401d26ce  lea     edx, [rax+1]; dwType
0x1401d26d1  mov     rcx, [rbp+47h+hResource]; hResource
0x1401d26d5  call    cs:__imp_ClusterResourceOpenEnum
0x1401d26dc  nop     dword ptr [rax+rax+00h]
0x1401d26e1  mov     rsi, rax
0x1401d26e4  lea     rcx, [rax+1]
0x1401d26e8  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1401d26ef  jnz     short loc_1401D2739
0x1401d26f1  call    cs:__imp_GetCurrentThreadId
0x1401d26f8  nop     dword ptr [rax+rax+00h]
0x1401d26fd  mov     ebx, eax
0x1401d26ff  call    cs:__imp_GetLastError
0x1401d2706  nop     dword ptr [rax+rax+00h]
0x1401d270b  mov     [rsp+40h], rdi
0x1401d2710  mov     dword ptr [rsp+0D0h+var_98], ebx
0x1401d2714  mov     [rsp+0D0h+var_A0], 0B66h
0x1401d271c  mov     qword ptr [rsp+0D0h+var_A8], r12
0x1401d2721  mov     [rsp+0D0h+lpcchName], r15
0x1401d2726  mov     r9d, 1
0x1401d272c  xor     r8d, r8d
0x1401d272f  mov     edx, eax
0x1401d2731  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d2736  mov     rbx, rax
0x1401d2739  mov     r15d, edi
0x1401d273c  test    rbx, rbx
0x1401d273f  jnz     loc_1401D28A7
0x1401d2745  mov     [rbp+47h+dwType], edi
0x1401d2748  mov     [rbp+47h+cchName], edi
0x1401d274b  mov     [rbp+47h+arg_0], rdi
0x1401d274f  lea     rax, [rbp+47h+cchName]
0x1401d2753  mov     [rsp+0D0h+lpcchName], rax; lpcchName
0x1401d2758  xor     r9d, r9d; lpszName
0x1401d275b  lea     r8, [rbp+47h+dwType]; lpdwType
0x1401d275f  mov     edx, r15d; dwIndex
0x1401d2762  mov     rcx, rsi; hResEnum
0x1401d2765  call    cs:__imp_ClusterResourceEnum
0x1401d276c  nop     dword ptr [rax+rax+00h]
0x1401d2771  mov     r14d, eax
0x1401d2774  test    eax, eax
0x1401d2776  jnz     loc_1401D2842
0x1401d277c  mov     eax, [rbp+47h+cchName]
0x1401d277f  inc     eax
0x1401d2781  mov     [rbp+47h+cchName], eax
0x1401d2784  mov     ecx, eax
0x1401d2786  lea     eax, [rbx+2]
0x1401d2789  mul     rcx
0x1401d278c  lea     rcx, [rbx-1]
0x1401d2790  cmovo   rax, rcx
0x1401d2794  mov     rcx, rax; unsigned __int64
0x1401d2797  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401d279c  mov     r12, rax
0x1401d279f  mov     [rbp+47h+arg_0], rax
0x1401d27a3  lea     rax, [rbp+47h+cchName]
0x1401d27a7  mov     [rsp+0D0h+lpcchName], rax; lpcchName
0x1401d27ac  mov     r9, r12; lpszName
0x1401d27af  lea     r8, [rbp+47h+dwType]; lpdwType
0x1401d27b3  mov     edx, r15d; dwIndex
0x1401d27b6  mov     rcx, rsi; hResEnum
0x1401d27b9  call    cs:__imp_ClusterResourceEnum
0x1401d27c0  nop     dword ptr [rax+rax+00h]
0x1401d27c5  mov     r14d, eax
0x1401d27c8  test    eax, eax
0x1401d27ca  jnz     short loc_1401D283B
0x1401d27cc  lea     rcx, [rbp+47h+var_60]; this
0x1401d27d0  call    ??0ClusterResource@Cluster@@QEAA@XZ; Cluster::ClusterResource::ClusterResource(void)
0x1401d27d5  nop
0x1401d27d6  mov     r8, r12; unsigned __int16 *
0x1401d27d9  mov     rdx, [rbp+47h+var_78]; struct _HCLUSTER *
0x1401d27dd  lea     rcx, [rbp+47h+var_60]; this
0x1401d27e1  call    ?LoadResourceInformation@ClusterResource@Cluster@@QEAAPEAVFrsStatus@@PEAU_HCLUSTER@@PEBG@Z; Cluster::ClusterResource::LoadResourceInformation(_HCLUSTER *,ushort const *)
0x1401d27e6  mov     rbx, rax
0x1401d27e9  test    rax, rax
0x1401d27ec  jnz     short loc_1401D2829
0x1401d27ee  mov     rax, [rbp+47h+arg_18]
0x1401d27f2  test    rax, rax
0x1401d27f5  jz      short loc_1401D2807
0x1401d27f7  lea     rdx, [rbp+47h+var_60]; struct Cluster::ClusterResource *
0x1401d27fb  mov     rcx, rax; this
0x1401d27fe  call    ?FilterResource@ClusterResourceFilter@Cluster@@QEAAHAEAVClusterResource@2@@Z; Cluster::ClusterResourceFilter::FilterResource(Cluster::ClusterResource &)
0x1401d2803  test    eax, eax
0x1401d2805  jz      short loc_1401D2829
0x1401d2807  cmp     r13d, 4
0x1401d280b  jz      short loc_1401D281B
0x1401d280d  lea     rcx, [rbp+47h+var_60]
0x1401d2811  call    ?GetResourceClusterType@ClusterResource@Cluster@@QEBA?AW4_ClusterResourceType@2@XZ; Cluster::ClusterResource::GetResourceClusterType(void)
0x1401d2816  cmp     r13d, eax
0x1401d2819  jnz     short loc_1401D2829
0x1401d281b  lea     rdx, [rbp+47h+var_60]
0x1401d281f  mov     rcx, [rbp+47h+arg_28]
0x1401d2823  call    ?push_back@?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@QEAAXAEBVClusterResource@Cluster@@@Z; std::vector<Cluster::ClusterResource>::push_back(Cluster::ClusterResource const &)
0x1401d2828  nop
0x1401d2829  lea     rcx, [rbp+47h+var_60]; this
0x1401d282d  call    ??1ClusterResource@Cluster@@QEAA@XZ; Cluster::ClusterResource::~ClusterResource(void)
0x1401d2832  lea     r12, aClusterCluster_46; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d2839  jmp     short loc_1401D288D
0x1401d283b  lea     r12, aClusterCluster_46; "Cluster::ClusterUtil::GetClusterResourc"...
0x1401d2842  cmp     r14d, 103h
0x1401d2849  jz      short loc_1401D289E
0x1401d284b  call    cs:__imp_GetCurrentThreadId
0x1401d2852  nop     dword ptr [rax+rax+00h]
0x1401d2857  mov     [rsp+40h], rdi
0x1401d285c  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401d2860  mov     [rsp+0D0h+var_A0], 0BC6h
0x1401d2868  mov     qword ptr [rsp+0D0h+var_A8], r12
0x1401d286d  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d2874  mov     [rsp+0D0h+lpcchName], rax
0x1401d2879  mov     r9d, 1
0x1401d287f  xor     r8d, r8d
0x1401d2882  mov     edx, r14d
0x1401d2885  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d288a  mov     rbx, rax
0x1401d288d  inc     r15d
0x1401d2890  lea     rcx, [rbp+47h+arg_0]
0x1401d2894  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d2899  jmp     loc_1401D273C
0x1401d289e  lea     rcx, [rbp+47h+arg_0]
0x1401d28a2  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401d28a7  lea     rax, [rsi-1]
0x1401d28ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401d28af  ja      short loc_1401D28C0
0x1401d28b1  mov     rcx, rsi; hResEnum
0x1401d28b4  call    cs:__imp_ClusterResourceCloseEnum
0x1401d28bb  nop     dword ptr [rax+rax+00h]
0x1401d28c0  lea     rcx, [rbp+47h+hResource]; struct _HRESOURCE **
0x1401d28c4  call    ?CloseResourceHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HRESOURCE@@@Z; Cluster::ClusterUtil::CloseResourceHandle(_HRESOURCE * &)
0x1401d28c9  lea     rcx, [rbp+47h+var_78]; struct _HCLUSTER **
0x1401d28cd  call    ?CloseClusterHandle@ClusterUtil@Cluster@@SAXAEAPEAU_HCLUSTER@@@Z; Cluster::ClusterUtil::CloseClusterHandle(_HCLUSTER * &)
0x1401d28d2  test    rbx, rbx
0x1401d28d5  jz      short loc_1401D293C
0x1401d28d7  lea     rdx, [rbp+47h+arg_0]
0x1401d28db  mov     rcx, [rbp+47h+arg_28]
0x1401d28df  call    ?end@?$vector@PEAVServiceInfo@@V?$allocator@PEAVServiceInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVServiceInfo@@@std@@@std@@@2@XZ; std::vector<ServiceInfo *>::end(void)
0x1401d28e4  mov     r9, [rax]
0x1401d28e7  lea     rdx, [rbp+47h+var_68]
0x1401d28eb  call    ?end@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@3@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::set<_GUID>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::set<_GUID>>>,0>>::end(void)
0x1401d28f0  mov     r8, [rax]
0x1401d28f3  lea     rdx, [rbp+47h+var_70]
0x1401d28f7  call    ?erase@?$vector@VClusterResource@Cluster@@V?$allocator@VClusterResource@Cluster@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VClusterResource@Cluster@@@std@@@std@@@2@0@Z; std::vector<Cluster::ClusterResource>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Cluster::ClusterResource>>>)
0x1401d28fc  call    cs:__imp_GetCurrentThreadId
0x1401d2903  nop     dword ptr [rax+rax+00h]
0x1401d2908  mov     [rsp+40h], rbx
0x1401d290d  mov     dword ptr [rsp+0D0h+var_98], eax
0x1401d2911  mov     [rsp+0D0h+var_A0], 0BE6h
0x1401d2919  mov     qword ptr [rsp+0D0h+var_A8], r12
0x1401d291e  lea     rax, dwType; "base\\fs\\remotefs\\frs\\src\\cluster\\"...
0x1401d2925  mov     [rsp+0D0h+lpcchName], rax
0x1401d292a  mov     r9d, [rbx]
0x1401d292d  mov     r8d, [rbx+8]
0x1401d2931  mov     edx, [rbx+4]
0x1401d2934  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401d2939  mov     rdi, rax
0x1401d293c  mov     rax, rdi
0x1401d293f  mov     rbx, [rsp+0D0h+arg_8]
0x1401d2947  add     rsp, 0A0h
0x1401d294e  pop     r15
0x1401d2950  pop     r14
0x1401d2952  pop     r13
0x1401d2954  pop     r12
0x1401d2956  pop     rdi
0x1401d2957  pop     rsi
0x1401d2958  pop     rbp
0x1401d2959  retn
```
