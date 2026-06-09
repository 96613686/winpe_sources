# RemoveClusterNameAccount

- ea: `0x180045a00`
- end: `0x18004637f`
- name: `RemoveClusterNameAccount`
- size: `2431`
- prototype: `DWORD __stdcall(HCLUSTER hCluster, BOOL bDeleteComputerObjects)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002f50`
- `0x180013ae4`
- `0x180014638`
- `0x180019030`
- `0x18001cc2c`
- `0x180028f30`
- `0x180029578`
- `0x18002fb04`
- `0x180037ae8`
- `0x180039028`
- `0x18003a1f0`
- `0x18003acf0`
- `0x18003d834`
- `0x18003e198`
- `0x180045a00`
- `0x180052d30`
- `0x180063cb0`
- `0x180064d10`
- `0x180064f20`
- `0x180065190`
- `0x18006cf40`
- `0x18006f910`
- `0x180095144`
- `0x180096894`
- `0x180096b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045ab7`

## string_xrefs

- `0x180045ec7`: `DeleteNonCoreVCOs failed - status = %d`
- `0x180045b3b`: `AdminAccessPoint`
- `0x180045f9e`: `AdminAccessPoint`
- `0x180045a7f`: `RemoveClusterNameAccount`
- `0x180045ad5`: `RemoveClusterNameAccount`
- `0x180045b66`: `RemoveClusterNameAccount`
- `0x180045be1`: `RemoveClusterNameAccount`
- `0x180045c27`: `RemoveClusterNameAccount`
- `0x180045cf2`: `RemoveClusterNameAccount`
- `0x180045de6`: `RemoveClusterNameAccount`
- `0x180045ea0`: `RemoveClusterNameAccount`
- `0x180045ed9`: `RemoveClusterNameAccount`
- `0x180045f7a`: `RemoveClusterNameAccount`
- `0x180045fcf`: `RemoveClusterNameAccount`
- `0x1800460cf`: `RemoveClusterNameAccount`
- `0x18004625f`: `RemoveClusterNameAccount`
- `0x180046316`: `RemoveClusterNameAccount`
- `0x180045dd4`: `Failed to set CNO Object to be deleted upon Resource ADAware downgrade, error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
DWORD __stdcall RemoveClusterNameAccount(HCLUSTER hCluster, BOOL bDeleteComputerObjects)
{
  DWORD result; // eax
  unsigned __int16 ClusterFunctionalLevel; // ax
  HKEY ClusterKey; // rdi
  DWORD LastError; // ebx
  LONG v9; // eax
  DWORD v10; // ebx
  unsigned int CoreClusterNameResource; // eax
  DWORD v12; // ebx
  CLUSTER_RESOURCE_STATE ClusterResourceState; // eax
  DWORD AllNonCoreNameResources; // eax
  DWORD v15; // ebx
  int v16; // eax
  struct _HRESOURCE **i; // rbx
  unsigned int v18; // eax
  DWORD v19; // eax
  DWORD v20; // ebx
  unsigned int v21; // eax
  DWORD v22; // r12d
  __int64 v23; // rax
  wchar_t *v24; // [rsp+28h] [rbp-110h]
  wchar_t *v25; // [rsp+28h] [rbp-110h]
  __int64 v26; // [rsp+30h] [rbp-108h]
  __int64 v27; // [rsp+30h] [rbp-108h]
  unsigned int *v28; // [rsp+38h] [rbp-100h]
  __int64 v29; // [rsp+40h] [rbp-F8h]
  int v30; // [rsp+50h] [rbp-E8h] BYREF
  __int128 v31; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-D0h]
  HRESOURCE hResource; // [rsp+70h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+80h] [rbp-B8h] BYREF
  DWORD dwValueType; // [rsp+84h] [rbp-B4h] BYREF
  int v37; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v38[16]; // [rsp+90h] [rbp-A8h] BYREF
  void *v39; // [rsp+A0h] [rbp-98h]
  int v40; // [rsp+A8h] [rbp-90h]
  _QWORD v41[4]; // [rsp+B8h] [rbp-80h] BYREF
  cxl::Exception *v42; // [rsp+D8h] [rbp-60h] BYREF
  std::system_error *v43; // [rsp+E0h] [rbp-58h] BYREF
  _BYTE v44[32]; // [rsp+E8h] [rbp-50h] BYREF

  if ( !hCluster )
    return 6;
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hCluster,
                           hCluster) )
    return 6;
  try
  {
    ClusterFunctionalLevel = GetClusterFunctionalLevel(hCluster);
    if ( ClusterFunctionalLevel < 0xAu )
    {
      TraceMsg(
        2,
        0,
        L"RemoveClusterNameAccount",
        10101,
        L"Cluster's major version %d is lesser than Redstone.",
        ClusterFunctionalLevel);
      return 5904;
    }
    ClusterKey = GetClusterKey(hCluster, 3u);
    v41[2] = ClusterKey;
    if ( !ClusterKey )
    {
      LastError = GetLastError();
      TraceMsg(2, 0, L"RemoveClusterNameAccount", 10109, L"Failed to obtain cluster root key, error %d.", LastError);
      return LastError;
    }
    v30 = 2;
    *(_DWORD *)Data = 0;
    cbData = 4;
    dwValueType = 0;
    v9 = ClusterRegQueryValue(ClusterKey, L"AdminAccessPoint", &dwValueType, Data, &cbData);
    v10 = v9;
    if ( v9 )
    {
      TraceMsg(
        2,
        0,
        L"RemoveClusterNameAccount",
        10121,
        L"Failed to get management point type from clusdb, error %d.",
        v9);
      ClusterRegCloseKeyCommon(ClusterKey, 1);
      return v10;
    }
    if ( *(_DWORD *)Data == 1 )
    {
      hResource = 0;
      CoreClusterNameResource = GetCoreClusterNameResource(hCluster, &hResource);
      v12 = CoreClusterNameResource;
      if ( CoreClusterNameResource )
      {
        TraceMsg(
          2,
          0,
          L"RemoveClusterNameAccount",
          10138,
          L"Failed to get CNO Resource, error %d.",
          CoreClusterNameResource);
        CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
        ClusterRegCloseKeyCommon(ClusterKey, 1);
        return v12;
      }
      ClusterResourceState = GetClusterResourceState(hResource, 0, 0, 0, 0);
      if ( ClusterResourceState == ClusterResourceStateUnknown )
      {
        TraceMsg(2, 0, L"RemoveClusterNameAccount", 10146, L"Failed to get Resource state for the CNO, error %d.", 0);
        CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
        ClusterRegCloseKeyCommon(ClusterKey, 1);
        return 0;
      }
      if ( ClusterResourceState != ClusterResourceOffline )
      {
        TraceMsg(2, 0, L"RemoveClusterNameAccount", 10152, L"The CNO is not offline");
        CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
        ClusterRegCloseKeyCommon(ClusterKey, 1);
        return 5023;
      }
      TraceMsg(4, 0, L"RemoveClusterNameAccount", 10157, L"Getting all VCOs, and verifying that they are offline");
      std::vector<_GUID>::vector<_GUID>(&v31);
      AllNonCoreNameResources = GetAllNonCoreNameResources(hCluster);
      v15 = AllNonCoreNameResources;
      if ( AllNonCoreNameResources )
      {
        TraceMsg(
          2,
          0,
          L"RemoveClusterNameAccount",
          10164,
          L"Enumerating all Non-Core Names failed., error %d.",
          AllNonCoreNameResources);
        if ( !(_QWORD)v31 )
        {
LABEL_21:
          CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
          ClusterRegCloseKeyCommon(ClusterKey, 1);
          return v15;
        }
LABEL_20:
        std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
          v31,
          *((_QWORD *)&v31 + 1));
        std::_Deallocate<16>(v31, 8 * ((v32 - (__int64)v31) >> 3));
        v31 = 0;
        v32 = 0;
        goto LABEL_21;
      }
      TraceMsg(
        4,
        0,
        L"RemoveClusterNameAccount",
        10169,
        L"Setting Private Propery \"%s\" On All VCOs to %d",
        L"ADAware",
        v30);
      v16 = SetNetNameCleanupType(hCluster);
      if ( v16 )
      {
        LODWORD(v24) = v16;
        TraceMsg(
          3,
          0,
          L"RemoveClusterNameAccount",
          10174,
          L"Failed to set CNO Object to be deleted upon Resource ADAware downgrade, error %d.",
          v24);
      }
      cxl::PropertyList::PropertyList((cxl::PropertyList *)v38);
      std::wstring::wstring(v44, L"ADAware");
      cbData = v30;
      v37 = 65538;
      v41[0] = &cbData;
      v41[1] = &v37;
      cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(v38, v44, v41);
      std::wstring::_Tidy_deallocate(v44);
      for ( i = (struct _HRESOURCE **)v31; i != *((struct _HRESOURCE ***)&v31 + 1); i += 5 )
      {
        v22 = ClusterpResourceControl(*i, 0, 0x1400086u, v39, v40 - (_DWORD)v39, 0, 0, 0, 0, 0);
        if ( v22 )
        {
          v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i + 1);
          LODWORD(v29) = v22;
          LODWORD(v27) = v30;
          TraceMsg(
            2,
            0,
            L"RemoveClusterNameAccount",
            10186,
            L"Failed to set private property '%s' to '%d' on name '%s', error %d.",
            L"ADAware",
            v27,
            v23,
            v29);
          cxl::PropertyList::~PropertyList((cxl::PropertyList *)v38);
          if ( (_QWORD)v31 )
          {
            std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
              v31,
              *((_QWORD *)&v31 + 1));
            std::_Deallocate<16>(v31, 8 * ((v32 - (__int64)v31) >> 3));
            v31 = 0;
            v32 = 0;
          }
          CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
          ClusterRegCloseKeyCommon(ClusterKey, 1);
          return v22;
        }
      }
      if ( bDeleteComputerObjects )
      {
        TraceMsg(4, 0, L"RemoveClusterNameAccount", 10193, L" Deleting all VCO objects.");
        v18 = DeleteNonCoreVCOs(hCluster);
        v15 = v18;
        if ( v18 )
        {
          LODWORD(v24) = v18;
          TraceMsg(2, 0, L"RemoveClusterNameAccount", 10197, L"DeleteNonCoreVCOs failed - status = %d", v24);
          cxl::PropertyList::~PropertyList((cxl::PropertyList *)v38);
          if ( !(_QWORD)v31 )
            goto LABEL_21;
          goto LABEL_20;
        }
      }
      TraceMsg(4, 0, L"RemoveClusterNameAccount", 10203, L" Starting CNO downgrade");
      v19 = ClusterRegSetValueEx((int)ClusterKey, (int)L"AdminAccessPoint", 4, (int)&v30, 4, 0);
      v20 = v19;
      if ( v19 )
      {
        LODWORD(v25) = v19;
        TraceMsg(
          2,
          0,
          L"RemoveClusterNameAccount",
          10208,
          L"Failed to set management point type in clusdb, error %d.",
          v25);
        cxl::PropertyList::~PropertyList((cxl::PropertyList *)v38);
        if ( (_QWORD)v31 )
        {
LABEL_32:
          std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
            v31,
            *((_QWORD *)&v31 + 1));
          std::_Deallocate<16>(v31, 8 * ((v32 - (__int64)v31) >> 3));
          v31 = 0;
          v32 = 0;
        }
      }
      else
      {
        v21 = ClusterpResourceControl(hResource, 0, 0x1400086u, v39, v40 - (_DWORD)v39, 0, 0, 0, 0, 0);
        v20 = v21;
        if ( !v21 )
        {
          cxl::PropertyList::~PropertyList((cxl::PropertyList *)v38);
          if ( (_QWORD)v31 )
          {
            std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
              v31,
              *((_QWORD *)&v31 + 1));
            std::_Deallocate<16>(v31, 8 * ((v32 - (__int64)v31) >> 3));
            v31 = 0;
            v32 = 0;
          }
          CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
          ClusterRegCloseKeyCommon(ClusterKey, 1);
          return 0;
        }
        LODWORD(v28) = v21;
        LODWORD(v26) = v30;
        TraceMsg(
          2,
          0,
          L"RemoveClusterNameAccount",
          10215,
          L"Failed to set private property '%s' to '%d' on name the CNO, error %d.",
          L"ADAware",
          v26,
          v28);
        cxl::PropertyList::~PropertyList((cxl::PropertyList *)v38);
        if ( (_QWORD)v31 )
          goto LABEL_32;
      }
      CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(&hResource);
      ClusterRegCloseKeyCommon(ClusterKey, 1);
      return v20;
    }
    TraceMsg(
      2,
      0,
      L"RemoveClusterNameAccount",
      10128,
      L"Cannot Downgrade cluster from Management Point Type: %d, To Management point: %d.",
      *(_DWORD *)Data,
      v30);
    ClusterRegCloseKeyCommon(ClusterKey, 1);
    result = 87;
  }
  catch ( cxl::Exception *v42 )
  {
    return cxl::ErrorCode::GetWinError((cxl::Exception *)((char *)v42 + 88));
  }
  catch ( std::system_error *v43 )
  {
    return *((_DWORD *)v43 + 6);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( std::exception )
  {
    return 1359;
  }
  catch ( ... )
  {
    return 1359;
  }
  return result;
}

```

## disassembly

```asm
0x180045a00  mov     [rsp+arg_10], rbx
0x180045a05  mov     [rsp+arg_18], rsi
0x180045a0a  push    rdi
0x180045a0b  push    r12
0x180045a0d  push    r13
0x180045a0f  push    r14
0x180045a11  push    r15
0x180045a13  sub     rsp, 110h
0x180045a1a  mov     rax, cs:__security_cookie
0x180045a21  xor     rax, rsp
0x180045a24  mov     [rsp+138h+var_30], rax
0x180045a2c  mov     r13d, edx
0x180045a2f  mov     r15, rcx
0x180045a32  xor     r12d, r12d
0x180045a35  test    rcx, rcx
0x180045a38  jnz     short loc_180045A42
0x180045a3a  lea     eax, [rcx+6]
0x180045a3d  jmp     loc_180046351
0x180045a42  mov     rdx, r15
0x180045a45  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180045a4a  test    al, al
0x180045a4c  jnz     short loc_180045A58
0x180045a4e  mov     eax, 6
0x180045a53  jmp     loc_180046351
0x180045a58  mov     rcx, r15; hCluster
0x180045a5b  call    ?GetClusterFunctionalLevel@@YAGPEAU_HCLUSTER@@@Z; GetClusterFunctionalLevel(_HCLUSTER *)
0x180045a60  cmp     ax, 0Ah
0x180045a64  jnb     short loc_180045A9A
0x180045a66  movzx   eax, ax
0x180045a69  mov     dword ptr [rsp+138h+var_110], eax
0x180045a6d  lea     rax, aClusterSMajorV_0; "Cluster's major version %d is lesser th"...
0x180045a74  mov     [rsp+138h+lpcbData], rax
0x180045a79  mov     r9d, 2775h
0x180045a7f  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045a86  xor     edx, edx
0x180045a88  lea     ecx, [rdx+2]
0x180045a8b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045a90  mov     eax, 1710h
0x180045a95  jmp     loc_180046351
0x180045a9a  mov     edx, 3; samDesired
0x180045a9f  mov     rcx, r15; hCluster
0x180045aa2  call    GetClusterKey
0x180045aa7  mov     rdi, rax
0x180045aaa  mov     [rsp+138h+var_70], rax
0x180045ab2  test    rax, rax
0x180045ab5  jnz     short loc_180045AFE
0x180045ab7  call    cs:__imp_GetLastError
0x180045abd  mov     ebx, eax
0x180045abf  mov     dword ptr [rsp+138h+var_110], eax
0x180045ac3  lea     rax, aFailedToObtain_4; "Failed to obtain cluster root key, erro"...
0x180045aca  mov     [rsp+138h+lpcbData], rax
0x180045acf  mov     r9d, 277Dh
0x180045ad5  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045adc  xor     edx, edx
0x180045ade  lea     ecx, [rdi+2]
0x180045ae1  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045ae6  nop
0x180045ae7  test    rdi, rdi
0x180045aea  jz      short loc_180045AF7
0x180045aec  lea     edx, [rdi+1]; int
0x180045aef  mov     rcx, rdi; HKEY
0x180045af2  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180045af7  mov     eax, ebx
0x180045af9  jmp     loc_180046351
0x180045afe  mov     r14d, 2
0x180045b04  mov     [rsp+138h+var_E8], r14d
0x180045b09  mov     dword ptr [rsp+138h+Data], r12d
0x180045b11  mov     [rsp+138h+cbData], 4
0x180045b19  mov     [rsp+138h+dwValueType], r12d
0x180045b21  lea     rax, [rsp+138h+cbData]
0x180045b26  mov     [rsp+138h+lpcbData], rax; lpcbData
0x180045b2b  lea     r9, [rsp+138h+Data]; lpData
0x180045b33  lea     r8, [rsp+138h+dwValueType]; lpdwValueType
0x180045b3b  lea     rdx, aAdminaccesspoi; "AdminAccessPoint"
0x180045b42  mov     rcx, rdi; hKey
0x180045b45  call    ClusterRegQueryValue
0x180045b4a  mov     ebx, eax
0x180045b4c  test    eax, eax
0x180045b4e  jz      short loc_180045B90
0x180045b50  mov     dword ptr [rsp+138h+var_110], eax
0x180045b54  lea     rax, aFailedToGetMan; "Failed to get management point type fro"...
0x180045b5b  mov     [rsp+138h+lpcbData], rax
0x180045b60  mov     r9d, 2789h
0x180045b66  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045b6d  xor     edx, edx
0x180045b6f  mov     ecx, r14d
0x180045b72  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045b77  nop
0x180045b78  test    rdi, rdi
0x180045b7b  jz      short loc_180045B89
0x180045b7d  lea     edx, [r14-1]; int
0x180045b81  mov     rcx, rdi; HKEY
0x180045b84  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180045b89  mov     eax, ebx
0x180045b8b  jmp     loc_180046351
0x180045b90  mov     ecx, dword ptr [rsp+138h+Data]
0x180045b97  mov     esi, 1
0x180045b9c  mov     eax, [rsp+138h+var_E8]
0x180045ba0  cmp     ecx, esi
0x180045ba2  jnz     loc_1800462FC
0x180045ba8  cmp     eax, r14d
0x180045bab  jnz     loc_1800462FC
0x180045bb1  mov     [rsp+138h+hResource], r12
0x180045bb6  lea     rdx, [rsp+138h+hResource]; struct _HRESOURCE **
0x180045bbb  mov     rcx, r15; hCluster
0x180045bbe  call    ?GetCoreClusterNameResource@@YAKPEAU_HCLUSTER@@PEAPEAU_HRESOURCE@@@Z; GetCoreClusterNameResource(_HCLUSTER *,_HRESOURCE * *)
0x180045bc3  mov     ebx, eax
0x180045bc5  xor     edx, edx; lpszNodeName
0x180045bc7  test    eax, eax
0x180045bc9  jz      short loc_180045C12
0x180045bcb  mov     dword ptr [rsp+138h+var_110], eax
0x180045bcf  lea     rax, aFailedToGetCno; "Failed to get CNO Resource, error %d."
0x180045bd6  mov     [rsp+138h+lpcbData], rax
0x180045bdb  mov     r9d, 279Ah
0x180045be1  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045be8  mov     ecx, r14d
0x180045beb  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045bf0  nop
0x180045bf1  lea     rcx, [rsp+138h+hResource]
0x180045bf6  call    ?Release@?$CTSmartObj@PEAU_HRESOURCE@@V?$CAutoHandle_Policy@PEAU_HRESOURCE@@@@@@QEAAXXZ; CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(void)
0x180045bfb  nop
0x180045bfc  test    rdi, rdi
0x180045bff  jz      short loc_180045C0B
0x180045c01  mov     edx, esi; int
0x180045c03  mov     rcx, rdi; HKEY
0x180045c06  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180045c0b  mov     eax, ebx
0x180045c0d  jmp     loc_180046351
0x180045c12  mov     [rsp+138h+lpcbData], r12; lpcchGroupName
0x180045c17  xor     r9d, r9d; lpszGroupName
0x180045c1a  xor     r8d, r8d; lpcchNodeName
0x180045c1d  mov     rcx, [rsp+138h+hResource]; hResource
0x180045c22  call    GetClusterResourceState
0x180045c27  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045c2e  xor     edx, edx
0x180045c30  cmp     eax, 0FFFFFFFFh
0x180045c33  jnz     short loc_180045C76
0x180045c35  mov     dword ptr [rsp+138h+var_110], r12d
0x180045c3a  lea     rax, aFailedToGetRes_0; "Failed to get Resource state for the CN"...
0x180045c41  mov     [rsp+138h+lpcbData], rax
0x180045c46  mov     r9d, 27A2h
0x180045c4c  mov     ecx, r14d
0x180045c4f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045c54  nop
0x180045c55  lea     rcx, [rsp+138h+hResource]
0x180045c5a  call    ?Release@?$CTSmartObj@PEAU_HRESOURCE@@V?$CAutoHandle_Policy@PEAU_HRESOURCE@@@@@@QEAAXXZ; CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(void)
0x180045c5f  nop
0x180045c60  test    rdi, rdi
0x180045c63  jz      short loc_180045C6F
0x180045c65  mov     edx, esi; int
0x180045c67  mov     rcx, rdi; HKEY
0x180045c6a  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180045c6f  xor     eax, eax
0x180045c71  jmp     loc_180046351
0x180045c76  cmp     eax, 3
0x180045c79  jz      short loc_180045CBA
0x180045c7b  lea     rax, aTheCnoIsNotOff; "The CNO is not offline"
0x180045c82  mov     [rsp+138h+lpcbData], rax
0x180045c87  mov     r9d, 27A8h
0x180045c8d  mov     ecx, r14d
0x180045c90  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045c95  nop
0x180045c96  lea     rcx, [rsp+138h+hResource]
0x180045c9b  call    ?Release@?$CTSmartObj@PEAU_HRESOURCE@@V?$CAutoHandle_Policy@PEAU_HRESOURCE@@@@@@QEAAXXZ; CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(void)
0x180045ca0  nop
0x180045ca1  test    rdi, rdi
0x180045ca4  jz      short loc_180045CB0
0x180045ca6  mov     edx, esi; int
0x180045ca8  mov     rcx, rdi; HKEY
0x180045cab  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180045cb0  mov     eax, 139Fh
0x180045cb5  jmp     loc_180046351
0x180045cba  lea     rax, aGettingAllVcos; "Getting all VCOs, and verifying that th"...
0x180045cc1  mov     [rsp+138h+lpcbData], rax
0x180045cc6  mov     r9d, 27ADh
0x180045ccc  mov     ecx, 4
0x180045cd1  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045cd6  lea     rcx, [rsp+138h+var_E0]
0x180045cdb  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180045ce0  nop
0x180045ce1  lea     r8, [rsp+138h+var_E0]
0x180045ce6  mov     edx, esi
0x180045ce8  mov     rcx, r15; hCluster
0x180045ceb  call    ?GetAllNonCoreNameResources@@YAKPEAU_HCLUSTER@@HAEAV?$vector@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@@Z; GetAllNonCoreNameResources(_HCLUSTER *,int,std::vector<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>> &)
0x180045cf0  mov     ebx, eax
0x180045cf2  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045cf9  xor     edx, edx
0x180045cfb  test    eax, eax
0x180045cfd  jz      loc_180045D91
0x180045d03  mov     dword ptr [rsp+138h+var_110], eax
0x180045d07  lea     rax, aEnumeratingAll_0; "Enumerating all Non-Core Names failed.,"...
0x180045d0e  mov     [rsp+138h+lpcbData], rax
0x180045d13  mov     r9d, 27B4h
0x180045d19  mov     ecx, r14d
0x180045d1c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045d21  nop
0x180045d22  mov     rcx, qword ptr [rsp+138h+var_E0]
0x180045d27  test    rcx, rcx
0x180045d2a  jz      short loc_180045D70
0x180045d2c  mov     rdx, qword ptr [rsp+138h+var_E0+8]
0x180045d31  call    ??$_Destroy_range@V?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring> *,std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring> * const,std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>> &)
0x180045d36  mov     rcx, qword ptr [rsp+138h+var_E0]
0x180045d3b  mov     rax, [rsp+138h+var_D0]
0x180045d40  sub     rax, rcx
0x180045d43  sar     rax, 3
0x180045d47  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x180045d51  imul    rax, rdx
0x180045d55  lea     rdx, [rax+rax*4]
0x180045d59  shl     rdx, 3
0x180045d5d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180045d62  xorps   xmm0, xmm0
0x180045d65  movdqu  [rsp+138h+var_E0], xmm0
0x180045d6b  mov     [rsp+138h+var_D0], r12
0x180045d70  lea     rcx, [rsp+138h+hResource]
0x180045d75  call    ?Release@?$CTSmartObj@PEAU_HRESOURCE@@V?$CAutoHandle_Policy@PEAU_HRESOURCE@@@@@@QEAAXXZ; CTSmartObj<_HRESOURCE *,CAutoHandle_Policy<_HRESOURCE *>>::Release(void)
0x180045d7a  nop
0x180045d7b  test    rdi, rdi
0x180045d7e  jz      short loc_180045D8A
0x180045d80  mov     edx, esi; int
0x180045d82  mov     rcx, rdi; HKEY
0x180045d85  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x180045d8a  mov     eax, ebx
0x180045d8c  jmp     loc_180046351
0x180045d91  mov     eax, [rsp+138h+var_E8]
0x180045d95  mov     dword ptr [rsp+138h+var_108], eax
0x180045d99  lea     rax, aAdaware; "ADAware"
0x180045da0  mov     [rsp+138h+var_110], rax
0x180045da5  lea     rax, aSettingPrivate; "Setting Private Propery \"%s\" On All V"...
0x180045dac  mov     [rsp+138h+lpcbData], rax
0x180045db1  mov     r9d, 27B9h
0x180045db7  mov     ecx, 4
0x180045dbc  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045dc1  mov     edx, r13d
0x180045dc4  mov     rcx, r15
0x180045dc7  call    SetNetNameCleanupType
0x180045dcc  test    eax, eax
0x180045dce  jz      short loc_180045DF7
0x180045dd0  mov     dword ptr [rsp+138h+var_110], eax
0x180045dd4  lea     rax, aFailedToSetCno; "Failed to set CNO Object to be deleted "...
0x180045ddb  mov     [rsp+138h+lpcbData], rax
0x180045de0  mov     r9d, 27BEh
0x180045de6  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045ded  xor     edx, edx
0x180045def  lea     ecx, [rdx+3]
0x180045df2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045df7  lea     rcx, [rsp+138h+var_A8]; this
0x180045dff  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x180045e04  nop
0x180045e05  mov     ebx, [rsp+138h+var_E8]
0x180045e09  lea     rdx, aAdaware; "ADAware"
0x180045e10  lea     rcx, [rsp+138h+var_50]
0x180045e18  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180045e1d  nop
0x180045e1e  mov     [rsp+138h+cbData], ebx
0x180045e22  mov     [rsp+138h+var_B0], 10002h
0x180045e2d  lea     rax, [rsp+138h+cbData]
0x180045e32  mov     [rsp+138h+var_80], rax
0x180045e3a  lea     rax, [rsp+138h+var_B0]
0x180045e42  mov     [rsp+138h+var_78], rax
0x180045e4a  lea     r8, [rsp+138h+var_80]
0x180045e52  lea     rdx, [rsp+138h+var_50]
0x180045e5a  lea     rcx, [rsp+138h+var_A8]
0x180045e62  call    ??$AddPropertyT@V_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_>(std::wstring const &,_lambda_a945c21e4f5b4a83c77c0f81b6ab26fd_ const &)
0x180045e67  nop
0x180045e68  lea     rcx, [rsp+138h+var_50]
0x180045e70  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180045e75  mov     rbx, qword ptr [rsp+138h+var_E0]
0x180045e7a  cmp     rbx, qword ptr [rsp+138h+var_E0+8]
0x180045e7f  jnz     loc_1800461DC
0x180045e85  test    r13d, r13d
0x180045e88  jz      loc_180045F68
0x180045e8e  lea     rax, aDeletingAllVco; " Deleting all VCO objects."
0x180045e95  mov     [rsp+138h+lpcbData], rax
0x180045e9a  mov     r9d, 27D1h
0x180045ea0  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045ea7  xor     edx, edx
0x180045ea9  lea     ecx, [rdx+4]
0x180045eac  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045eb1  mov     rcx, r15; struct _HCLUSTER *
0x180045eb4  call    ?DeleteNonCoreVCOs@@YAKPEAU_HCLUSTER@@@Z; DeleteNonCoreVCOs(_HCLUSTER *)
0x180045eb9  mov     ebx, eax
0x180045ebb  test    eax, eax
0x180045ebd  jz      loc_180045F68
0x180045ec3  mov     dword ptr [rsp+138h+var_110], eax
0x180045ec7  lea     rax, aDeletenoncorev; "DeleteNonCoreVCOs failed - status = %d"
0x180045ece  mov     [rsp+138h+lpcbData], rax
0x180045ed3  mov     r9d, 27D5h
0x180045ed9  lea     r8, aRemoveclustern_0; "RemoveClusterNameAccount"
0x180045ee0  xor     edx, edx
0x180045ee2  mov     ecx, r14d
0x180045ee5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180045eea  nop
0x180045eeb  lea     rcx, [rsp+138h+var_A8]; this
0x180045ef3  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180045ef8  nop
0x180045ef9  mov     rcx, qword ptr [rsp+138h+var_E0]
0x180045efe  test    rcx, rcx
0x180045f01  jz      short loc_180045F47
0x180045f03  mov     rdx, qword ptr [rsp+138h+var_E0+8]
0x180045f08  call    ??$_Destroy_range@V?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@YAXPEAU?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@QEAU10@AEAV?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring> *,std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring> * const,std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>> &)
  ... truncated ...
```
