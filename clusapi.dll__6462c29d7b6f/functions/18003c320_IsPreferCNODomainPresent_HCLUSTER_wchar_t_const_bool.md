# IsPreferCNODomainPresent(_HCLUSTER *,wchar_t const *,bool &)

- ea: `0x18003c320`
- end: `0x18003c6ca`
- name: `?IsPreferCNODomainPresent@@YAKPEAU_HCLUSTER@@PEB_WAEA_N@Z`
- size: `938`
- prototype: `unsigned int __fastcall(HCLUSTER hCluster, const wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e828`

## callees

- `0x180002f50`
- `0x180014638`
- `0x18001fe48`
- `0x18001feac`
- `0x18002acc0`
- `0x18002c220`
- `0x18003c320`
- `0x180057f5c`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c57e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c57e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c571`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c571`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c5d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c5d7`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18003c50b`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18003c50b`

## string_xrefs

- `0x18003c565`: `SYSTEM\CurrentControlSet\Services\ClusSvc\Parameters`
- `0x18003c4c0`: `Local node is part of cluster, trying to connect local registry`
- `0x18003c524`: `IsPreferCNODomainPresent: RegConnectRegistry to node %ws failed with error %d.`
- `0x18003c588`: `IsPreferCNODomainPresent: RegOpenKeyEx failed with error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsPreferCNODomainPresent(HCLUSTER hCluster, const wchar_t *a2, bool *a3)
{
  struct _HNODE *v7; // rdi
  struct _HCLUSENUM *v8; // rbx
  DWORD LastError; // edi
  DWORD v10; // eax
  DWORD v11; // r15d
  WCHAR *v12; // rcx
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  const wchar_t *v15; // rax
  __int64 v16; // r9
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  struct _HNODE *v18; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwType; // [rsp+68h] [rbp-98h] BYREF
  struct _HCLUSENUM *v26; // [rsp+70h] [rbp-90h]
  WCHAR szName[256]; // [rsp+80h] [rbp-80h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hCluster,
                           hCluster) )
    return 6;
  *a3 = 0;
  cchName = 256;
  v7 = OpenClusterNodeImpl(hCluster, a2, 0x10000000u, 0, 1);
  v18 = v7;
  if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    TraceMsg(
      4,
      0,
      L"IsPreferCNODomainPresent",
      9249,
      L"Local node is part of cluster, trying to connect local registry");
  }
  else
  {
    TraceMsg(
      4,
      0,
      L"IsPreferCNODomainPresent",
      9229,
      L"Local node is not part of cluster, trying to connect to first node of the cluster");
    v8 = ClusterOpenEnum(hCluster, 1u);
    v26 = v8;
    if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      TraceMsg(
        2,
        0,
        L"IsPreferCNODomainPresent",
        9234,
        L"IsPreferCNODomainPresent: Failed to get node enum handle %d",
        LastError);
      if ( (unsigned __int64)v8 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        ClusterCloseEnumCommon(v8, 1);
      cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(&v18);
      return LastError;
    }
    v10 = ClusterEnum(v8, 0, &dwType, szName, &cchName);
    v11 = v10;
    if ( v10 )
    {
      TraceMsg(
        2,
        0,
        L"IsPreferCNODomainPresent",
        9243,
        L"IsPreferCNODomainPresent: ClusterEnum failed with error %d.",
        v10);
      ClusterCloseEnumCommon(v8, 1);
      cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(&v18);
      return v11;
    }
    ClusterCloseEnumCommon(v8, 1);
  }
  phkResult = 0;
  hKey = 0;
  v12 = szName;
  if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    v12 = 0;
  v13 = RegConnectRegistryW(v12, HKEY_LOCAL_MACHINE, &phkResult);
  v14 = v13;
  if ( v13 )
  {
    TraceMsg(
      2,
      0,
      L"IsPreferCNODomainPresent",
      9257,
      L"IsPreferCNODomainPresent: RegConnectRegistry to node %ws failed with error %d.",
      szName,
      v13);
LABEL_16:
    cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(&v18);
    return v14;
  }
  v14 = RegOpenKeyExW(phkResult, L"SYSTEM\\CurrentControlSet\\Services\\ClusSvc\\Parameters", 0, 1u, &hKey);
  RegCloseKey(phkResult);
  if ( v14 )
  {
    v15 = L"IsPreferCNODomainPresent: RegOpenKeyEx failed with error %d.";
    v16 = 9269;
LABEL_23:
    LODWORD(lpcbData) = v14;
    TraceMsg(2, 0, L"IsPreferCNODomainPresent", v16, v15, lpcbData);
    goto LABEL_16;
  }
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v14 = RegQueryValueExW(hKey, L"PreferCNODomain", 0, &Type, Data, &cbData);
  RegCloseKey(hKey);
  if ( v14 == 2 )
  {
    *a3 = 0;
    v14 = 0;
    goto LABEL_16;
  }
  if ( v14 )
  {
    v15 = L"IsPreferCNODomainPresent: RegQueryValueEx failed with error %d.";
    v16 = 9290;
    goto LABEL_23;
  }
  if ( Type == 4 && cbData == 4 )
  {
    if ( *(_DWORD *)Data == 1 )
    {
      TraceMsg(Type, 0, L"IsPreferCNODomainPresent", 9301, L"IsPreferCNODomainPresent: Prefer CNO domain is enabled.");
      *a3 = 1;
    }
    cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(&v18);
    return 0;
  }
  else
  {
    LODWORD(lpcbData) = Type;
    TraceMsg(
      2,
      0,
      L"IsPreferCNODomainPresent",
      9295,
      L"IsPreferCNODomainPresent: Unexpected reg type (%d) or size of data (%d)",
      lpcbData,
      cbData);
    cxl::AutoHandle<_HNODE *,int,&int CloseClusterNode(_HNODE *),0>::Close(&v18);
    return 13;
  }
}

```

## disassembly

```asm
0x18003c320  mov     [rsp-8+arg_18], rbx
0x18003c325  push    rbp
0x18003c326  push    rsi
0x18003c327  push    rdi
0x18003c328  push    r12
0x18003c32a  push    r15
0x18003c32c  lea     rbp, [rsp-190h]
0x18003c334  sub     rsp, 290h
0x18003c33b  mov     rax, cs:__security_cookie
0x18003c342  xor     rax, rsp
0x18003c345  mov     [rbp+1B0h+var_30], rax
0x18003c34c  mov     r12, r8
0x18003c34f  mov     rdi, rdx
0x18003c352  mov     rbx, rcx
0x18003c355  mov     rdx, rcx
0x18003c358  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18003c35d  test    al, al
0x18003c35f  jnz     short loc_18003C36B
0x18003c361  mov     eax, 6
0x18003c366  jmp     loc_18003C6A4
0x18003c36b  mov     byte ptr [r12], 0
0x18003c370  mov     [rsp+2B0h+cchName], 100h
0x18003c378  mov     r15d, 1
0x18003c37e  mov     dword ptr [rsp+2B0h+lpcchName], r15d; int
0x18003c383  xor     r9d, r9d; unsigned int *
0x18003c386  mov     r8d, 10000000h; unsigned int
0x18003c38c  mov     rdx, rdi; wchar_t *
0x18003c38f  mov     rcx, rbx; struct _HCLUSTER *
0x18003c392  call    ?OpenClusterNodeImpl@@YAPEAU_HNODE@@PEAU_HCLUSTER@@PEB_WKPEAKH@Z; OpenClusterNodeImpl(_HCLUSTER *,wchar_t const *,ulong,ulong *,int)
0x18003c397  mov     rdi, rax
0x18003c39a  mov     [rsp+2B0h+var_270], rax
0x18003c39f  inc     rax
0x18003c3a2  lea     rsi, aIsprefercnodom_4; "IsPreferCNODomainPresent"
0x18003c3a9  xor     edx, edx
0x18003c3ab  lea     ecx, [rdx+4]
0x18003c3ae  mov     r8, rsi
0x18003c3b1  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003c3b7  jnz     loc_18003C4C0
0x18003c3bd  lea     rax, aLocalNodeIsNot; "Local node is not part of cluster, tryi"...
0x18003c3c4  mov     [rsp+2B0h+lpcchName], rax
0x18003c3c9  mov     r9d, 240Dh
0x18003c3cf  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c3d4  mov     edx, r15d; dwType
0x18003c3d7  mov     rcx, rbx; hCluster
0x18003c3da  call    ClusterOpenEnum
0x18003c3df  mov     rbx, rax
0x18003c3e2  mov     [rsp+2B0h+var_240], rax
0x18003c3e7  inc     rax
0x18003c3ea  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003c3f0  jnz     short loc_18003C445
0x18003c3f2  call    cs:__imp_GetLastError
0x18003c3f8  mov     edi, eax
0x18003c3fa  mov     dword ptr [rsp+2B0h+lpcbData], eax
0x18003c3fe  lea     rax, aIsprefercnodom_6; "IsPreferCNODomainPresent: Failed to get"...
0x18003c405  mov     [rsp+2B0h+lpcchName], rax
0x18003c40a  mov     r9d, 2412h
0x18003c410  mov     r8, rsi
0x18003c413  xor     edx, edx
0x18003c415  lea     ecx, [rdx+2]
0x18003c418  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c41d  nop
0x18003c41e  lea     rcx, [rbx-1]
0x18003c422  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003c426  ja      short loc_18003C434
0x18003c428  mov     edx, r15d; int
0x18003c42b  mov     rcx, rbx; struct _HCLUSENUM *
0x18003c42e  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x18003c433  nop
0x18003c434  lea     rcx, [rsp+2B0h+var_270]
0x18003c439  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18003c43e  mov     eax, edi
0x18003c440  jmp     loc_18003C6A4
0x18003c445  lea     rax, [rsp+2B0h+cchName]
0x18003c44a  mov     [rsp+2B0h+lpcchName], rax; lpcchName
0x18003c44f  lea     r9, [rbp+1B0h+szName]; lpszName
0x18003c453  lea     r8, [rsp+2B0h+dwType]; lpdwType
0x18003c458  xor     edx, edx; dwIndex
0x18003c45a  mov     rcx, rbx; hEnum
0x18003c45d  call    ClusterEnum
0x18003c462  mov     r15d, eax
0x18003c465  test    eax, eax
0x18003c467  jz      short loc_18003C4AD
0x18003c469  mov     dword ptr [rsp+2B0h+lpcbData], eax
0x18003c46d  lea     rax, aIsprefercnodom_5; "IsPreferCNODomainPresent: ClusterEnum f"...
0x18003c474  mov     [rsp+2B0h+lpcchName], rax
0x18003c479  mov     r9d, 241Bh
0x18003c47f  mov     r8, rsi
0x18003c482  xor     edx, edx
0x18003c484  lea     ecx, [rdx+2]
0x18003c487  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c48c  nop
0x18003c48d  mov     edx, 1; int
0x18003c492  mov     rcx, rbx; struct _HCLUSENUM *
0x18003c495  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x18003c49a  nop
0x18003c49b  lea     rcx, [rsp+2B0h+var_270]
0x18003c4a0  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18003c4a5  mov     eax, r15d
0x18003c4a8  jmp     loc_18003C6A4
0x18003c4ad  mov     r15d, 1
0x18003c4b3  mov     edx, r15d; int
0x18003c4b6  mov     rcx, rbx; struct _HCLUSENUM *
0x18003c4b9  call    ?ClusterCloseEnumCommon@@YAKPEAU_HCLUSENUM@@H@Z; ClusterCloseEnumCommon(_HCLUSENUM *,int)
0x18003c4be  jmp     short loc_18003C4D7
0x18003c4c0  lea     rax, aLocalNodeIsPar; "Local node is part of cluster, trying t"...
0x18003c4c7  mov     [rsp+2B0h+lpcchName], rax
0x18003c4cc  mov     r9d, 2421h
0x18003c4d2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c4d7  mov     [rsp+2B0h+phkResult], 0
0x18003c4e0  mov     [rsp+2B0h+hKey], 0
0x18003c4e9  dec     rdi
0x18003c4ec  cmp     rdi, 0FFFFFFFFFFFFFFFDh
0x18003c4f0  setbe   dl
0x18003c4f3  lea     rcx, [rbp+1B0h+szName]
0x18003c4f7  xor     eax, eax
0x18003c4f9  test    dl, dl
0x18003c4fb  cmovnz  rcx, rax; lpMachineName
0x18003c4ff  lea     r8, [rsp+2B0h+phkResult]; phkResult
0x18003c504  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18003c50b  call    cs:__imp_RegConnectRegistryW
0x18003c511  mov     ebx, eax
0x18003c513  test    eax, eax
0x18003c515  jz      short loc_18003C555
0x18003c517  mov     [rsp+2B0h+var_280], eax
0x18003c51b  lea     rax, [rbp+1B0h+szName]
0x18003c51f  mov     [rsp+2B0h+lpcbData], rax
0x18003c524  lea     rax, aIsprefercnodom_0; "IsPreferCNODomainPresent: RegConnectReg"...
0x18003c52b  mov     [rsp+2B0h+lpcchName], rax
0x18003c530  mov     r9d, 2429h
0x18003c536  mov     r8, rsi
0x18003c539  xor     edx, edx
0x18003c53b  lea     ecx, [rdx+2]
0x18003c53e  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c543  nop
0x18003c544  lea     rcx, [rsp+2B0h+var_270]
0x18003c549  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18003c54e  mov     eax, ebx
0x18003c550  jmp     loc_18003C6A4
0x18003c555  lea     rax, [rsp+2B0h+hKey]
0x18003c55a  mov     [rsp+2B0h+lpcchName], rax; phkResult
0x18003c55f  mov     r9d, r15d; samDesired
0x18003c562  xor     r8d, r8d; ulOptions
0x18003c565  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Cl"...
0x18003c56c  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x18003c571  call    cs:__imp_RegOpenKeyExW
0x18003c577  mov     ebx, eax
0x18003c579  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x18003c57e  call    cs:__imp_RegCloseKey
0x18003c584  test    ebx, ebx
0x18003c586  jz      short loc_18003C597
0x18003c588  lea     rax, aIsprefercnodom_7; "IsPreferCNODomainPresent: RegOpenKeyEx "...
0x18003c58f  mov     r9d, 2435h
0x18003c595  jmp     short loc_18003C60C
0x18003c597  mov     [rsp+2B0h+Type], 0
0x18003c59f  mov     dword ptr [rsp+2B0h+Data], 0
0x18003c5a7  mov     [rsp+2B0h+cbData], 4
0x18003c5af  lea     rax, [rsp+2B0h+cbData]
0x18003c5b4  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18003c5b9  lea     rax, [rsp+2B0h+Data]
0x18003c5be  mov     [rsp+2B0h+lpcchName], rax; lpData
0x18003c5c3  lea     r9, [rsp+2B0h+Type]; lpType
0x18003c5c8  xor     r8d, r8d; lpReserved
0x18003c5cb  lea     rdx, aPrefercnodomai; "PreferCNODomain"
0x18003c5d2  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003c5d7  call    cs:__imp_RegQueryValueExW
0x18003c5dd  mov     ebx, eax
0x18003c5df  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003c5e4  call    cs:__imp_RegCloseKey
0x18003c5ea  cmp     ebx, 2
0x18003c5ed  jnz     short loc_18003C5FB
0x18003c5ef  mov     byte ptr [r12], 0
0x18003c5f4  xor     ebx, ebx
0x18003c5f6  jmp     loc_18003C544
0x18003c5fb  test    ebx, ebx
0x18003c5fd  jz      short loc_18003C627
0x18003c5ff  lea     rax, aIsprefercnodom_3; "IsPreferCNODomainPresent: RegQueryValue"...
0x18003c606  mov     r9d, 244Ah
0x18003c60c  mov     dword ptr [rsp+2B0h+lpcbData], ebx
0x18003c610  mov     [rsp+2B0h+lpcchName], rax
0x18003c615  mov     r8, rsi
0x18003c618  xor     edx, edx
0x18003c61a  lea     ecx, [rdx+2]
0x18003c61d  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c622  jmp     loc_18003C544
0x18003c627  mov     eax, [rsp+2B0h+cbData]
0x18003c62b  mov     ecx, [rsp+2B0h+Type]
0x18003c62f  cmp     ecx, 4
0x18003c632  jnz     short loc_18003C66D
0x18003c634  cmp     eax, ecx
0x18003c636  jnz     short loc_18003C66D
0x18003c638  cmp     dword ptr [rsp+2B0h+Data], r15d
0x18003c63d  jnz     short loc_18003C65F
0x18003c63f  lea     rax, aIsprefercnodom; "IsPreferCNODomainPresent: Prefer CNO do"...
0x18003c646  mov     [rsp+2B0h+lpcchName], rax
0x18003c64b  mov     r9d, 2455h
0x18003c651  mov     r8, rsi
0x18003c654  xor     edx, edx
0x18003c656  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c65b  mov     [r12], r15b
0x18003c65f  lea     rcx, [rsp+2B0h+var_270]
0x18003c664  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18003c669  xor     eax, eax
0x18003c66b  jmp     short loc_18003C6A4
0x18003c66d  mov     [rsp+2B0h+var_280], eax
0x18003c671  mov     dword ptr [rsp+2B0h+lpcbData], ecx
0x18003c675  lea     rax, aIsprefercnodom_2; "IsPreferCNODomainPresent: Unexpected re"...
0x18003c67c  mov     [rsp+2B0h+lpcchName], rax
0x18003c681  mov     r9d, 244Fh
0x18003c687  mov     r8, rsi
0x18003c68a  xor     edx, edx
0x18003c68c  lea     ecx, [rdx+2]
0x18003c68f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003c694  nop
0x18003c695  lea     rcx, [rsp+2B0h+var_270]
0x18003c69a  call    ?Close@?$AutoHandle@PEAU_HNODE@@H$1?CloseClusterNode@@YAHPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODE *,int,&CloseClusterNode(_HNODE *),0>::Close(void)
0x18003c69f  mov     eax, 0Dh
0x18003c6a4  mov     rcx, [rbp+1B0h+var_30]
0x18003c6ab  xor     rcx, rsp; StackCookie
0x18003c6ae  call    __security_check_cookie
0x18003c6b3  mov     rbx, [rsp+2B0h+arg_18]
0x18003c6bb  add     rsp, 290h
0x18003c6c2  pop     r15
0x18003c6c4  pop     r12
0x18003c6c6  pop     rdi
0x18003c6c7  pop     rsi
0x18003c6c8  pop     rbp
0x18003c6c9  retn
```
