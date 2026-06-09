# ModifyNetworkName

- ea: `0x18003cbdc`
- end: `0x18003d204`
- name: `ModifyNetworkName`
- size: `1576`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180037824`
- `0x180041f00`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x180014638`
- `0x1800149f8`
- `0x18001cc2c`
- `0x180025478`
- `0x180029578`
- `0x18003cbdc`
- `0x18003dea8`
- `0x180052d30`
- `0x180063cb0`
- `0x180064f20`
- `0x180065190`
- `0x180065590`
- `0x18006f06c`
- `0x18006f910`
- `0x18007554c`
- `0x180094ce8`
- `0x180096894`
- `0x180096b88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d089`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003cf8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003cf8d`

## string_xrefs

- `0x18003d024`: `Failed to modify computer object for Cluster Name %ws. Error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ModifyNetworkName(
        PhaseManager *a1,
        struct _HCLUSTER *a2,
        const WCHAR *a3,
        const wchar_t *a4,
        wchar_t *a5,
        struct CreateClusterADState *a6,
        int a7,
        struct _HRESOURCE *hResource,
        int a9,
        int a10)
{
  struct _HRESOURCE *v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rcx
  HKEY ClusterKey; // r15
  HKEY ClusterResourceKey; // r13
  DWORD LastError; // ebx
  wchar_t *v19; // rax
  int v20; // r9d
  __int64 v21; // rbx
  __int64 v22; // rax
  _BYTE *v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned int v27; // eax
  wchar_t *v29; // [rsp+28h] [rbp-380h]
  __int64 v30; // [rsp+30h] [rbp-378h]
  __int64 v31; // [rsp+30h] [rbp-378h]
  DWORD nSize; // [rsp+50h] [rbp-358h] BYREF
  int v33[2]; // [rsp+58h] [rbp-350h] BYREF
  DWORD *p_nSize; // [rsp+60h] [rbp-348h]
  PhaseManager *v35; // [rsp+68h] [rbp-340h]
  HCLUSTER hCluster; // [rsp+70h] [rbp-338h]
  wchar_t *v37; // [rsp+78h] [rbp-330h]
  struct CreateClusterADState *v38; // [rsp+80h] [rbp-328h]
  HKEY v39; // [rsp+88h] [rbp-320h]
  HKEY v40; // [rsp+90h] [rbp-318h]
  struct _HRESOURCE *v41; // [rsp+98h] [rbp-310h]
  _BYTE v42[16]; // [rsp+A0h] [rbp-308h] BYREF
  void *v43; // [rsp+B0h] [rbp-2F8h]
  int v44; // [rsp+B8h] [rbp-2F0h]
  _BYTE v45[32]; // [rsp+C8h] [rbp-2E0h] BYREF
  _BYTE v46[40]; // [rsp+E8h] [rbp-2C0h] BYREF
  int v47[20]; // [rsp+110h] [rbp-298h] BYREF
  WCHAR Buffer[256]; // [rsp+160h] [rbp-248h] BYREF

  *(_QWORD *)v33 = a4;
  hCluster = a2;
  v35 = a1;
  v37 = a5;
  v38 = a6;
  v13 = hResource;
  v41 = hResource;
  nSize = 0;
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v42);
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HRESOURCE *>(
                           v14,
                           hResource)
    || !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           v15,
                           a2) )
  {
    LastError = 6;
    goto LABEL_49;
  }
  ClusterKey = 0;
  v39 = 0;
  ClusterResourceKey = 0;
  LastError = MylstrlenW(a4, 0x40u, &nSize);
  if ( LastError )
    goto LABEL_43;
  nSize = 2 * nSize + 2;
  LastError = SetCoreFlag_0(hResource);
  if ( LastError )
  {
    if ( !a3 )
      a3 = &base;
    v19 = L"Failed to set core flag for NetName resource %ws. Error %d.";
    v20 = 6864;
LABEL_42:
    LODWORD(v30) = LastError;
    TraceMsg(2u, 0, (__int64)L"ModifyNetworkName", v20, v19, a3, v30);
LABEL_43:
    SetCoreFlag_0(v13);
LABEL_44:
    if ( !ClusterResourceKey )
      goto LABEL_46;
    goto LABEL_45;
  }
  ClusterResourceKey = GetClusterResourceKey(hResource, 2u);
  v40 = ClusterResourceKey;
  if ( !ClusterResourceKey )
  {
    LastError = GetLastError();
    if ( !a3 )
      a3 = &base;
    TraceMsg(
      2u,
      0,
      (__int64)L"ModifyNetworkName",
      6872,
      L"Failed to get Cluster Resource Key for NetName resource %ws. Error %d.",
      a3,
      LastError);
LABEL_32:
    if ( !LastError )
      goto LABEL_44;
    goto LABEL_43;
  }
  LastError = ClusterRegSetValueEx((int)ClusterResourceKey, (int)L"CoreCurrentName", 1, v33[0], nSize, 0);
  if ( LastError )
  {
    if ( !a3 )
      a3 = &base;
    v19 = L"Failed to set core current name for NetName resource %ws. Error %d.";
    v20 = 6885;
    goto LABEL_42;
  }
  if ( a9 )
  {
    TraceMsg(4u, 0, (__int64)L"ModifyNetworkName", 6902, L"ModifyNetworkName: Setting Propery \"DnsName\" On DNN CNO");
    v24 = std::wstring::wstring(v45, *(_QWORD *)v33);
    v25 = std::wstring::wstring(v46, L"DnsName");
    nSize = 65539;
    *(_QWORD *)v33 = v24;
    p_nSize = &nSize;
    cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v42, v25, v33);
    std::wstring::_Tidy_deallocate(v46);
    v23 = v45;
  }
  else
  {
    TraceMsg(4u, 0, (__int64)L"ModifyNetworkName", 6897, L"ModifyNetworkName: Setting Propery \"Name\" On SNN CNO");
    v21 = std::wstring::wstring(v46, *(_QWORD *)v33);
    v22 = std::wstring::wstring(v45, L"Name");
    nSize = 65539;
    *(_QWORD *)v33 = v21;
    p_nSize = &nSize;
    cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(v42, v22, v33);
    std::wstring::_Tidy_deallocate(v45);
    v23 = v46;
  }
  std::wstring::_Tidy_deallocate(v23);
  LastError = ClusterpResourceControl(hResource, 0, 0x1400086u, v43, v44 - (_DWORD)v43, 0, 0, 0, 0, 0);
  if ( LastError )
  {
    if ( !a3 )
      a3 = &base;
    v19 = L"Failed to set private properties for NetName %ws. Error %d.";
    v20 = 6918;
    goto LABEL_42;
  }
  PhaseManager::EndPhase(v35, 0, ClusterSetupPhaseInformational);
  if ( ((a7 - 1) & 0xFFFFFFFD) == 0 )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    nSize = 256;
    if ( !GetComputerNameExW(ComputerNameDnsDomain, Buffer, &nSize) )
    {
      LastError = GetLastError();
      LODWORD(v29) = LastError;
      TraceMsg(2u, 0, (__int64)L"ModifyNetworkName", 6935, L"Failed to get DNS domain name. Error %d.", v29);
      goto LABEL_32;
    }
    try
    {
      v27 = ModifyClusterObjectInADAndInitInCluster(v35, v38, hCluster, hResource, v37, Buffer, a10);
    }
    catch ( std::exception )
    {
      v33[0] = 574;
      TraceMsg(
        2u,
        0,
        (__int64)L"ModifyNetworkName",
        6961,
        L"Failed to modify computer object for Cluster Name in AD, handling std exception");
      ClusterKey = v39;
      ClusterResourceKey = v40;
      LastError = v33[0];
      v13 = v41;
      goto LABEL_43;
    }
    LastError = v27;
    if ( v27 )
    {
      if ( !a3 )
        a3 = &base;
      LODWORD(v31) = v27;
      TraceMsg(
        2u,
        0,
        (__int64)L"ModifyNetworkName",
        6954,
        L"Failed to modify computer object for Cluster Name %ws. Error %d.",
        a3,
        v31);
      goto LABEL_43;
    }
  }
  ClusterKey = GetClusterKey(hCluster, 2u);
  if ( !ClusterKey )
  {
    LODWORD(v29) = LastError;
    TraceMsg(2u, 0, (__int64)L"ModifyNetworkName", 6969, L"Failed to get cluster key. Error %d.", v29);
    LastError = GetLastError();
    goto LABEL_32;
  }
  nSize = 0;
  LastError = ClusterpResourceControl(hResource, 0, 0x1000039u, 0, 0, v47, 0x50u, &nSize, 0, 0);
  if ( LastError )
  {
    if ( !a3 )
      a3 = &base;
    v19 = L"Failed to get resource Id for NetName %ws. Error %d.";
    v20 = 6987;
    goto LABEL_42;
  }
  LastError = ClusterRegSetValueEx((int)ClusterKey, (int)L"ClusterNameResource", 1, (int)v47, nSize, 0);
  if ( LastError )
  {
    if ( !a3 )
      a3 = &base;
    v19 = L"Failed to set resource Id key in cluster database for NetName %ws. Error %d.";
    v20 = 6999;
    goto LABEL_42;
  }
LABEL_45:
  ClusterRegCloseKeyCommon(ClusterResourceKey, 1);
LABEL_46:
  if ( ClusterKey )
    ClusterRegCloseKeyCommon(ClusterKey, 1);
LABEL_49:
  cxl::PropertyList::~PropertyList((cxl::PropertyList *)v42);
  return LastError;
}

```

## disassembly

```asm
0x18003cbdc  push    rbx
0x18003cbde  push    rsi
0x18003cbdf  push    r12
0x18003cbe1  push    r13
0x18003cbe3  push    r14
0x18003cbe5  push    r15
0x18003cbe7  sub     rsp, 378h
0x18003cbee  mov     rax, cs:__security_cookie
0x18003cbf5  xor     rax, rsp
0x18003cbf8  mov     [rsp+3A8h+var_48], rax
0x18003cc00  mov     rbx, r9
0x18003cc03  mov     qword ptr [rsp+3A8h+var_350], rbx
0x18003cc08  mov     rsi, r8
0x18003cc0b  mov     r14, rdx
0x18003cc0e  mov     [rsp+3A8h+hCluster], rdx
0x18003cc13  mov     [rsp+3A8h+var_340], rcx
0x18003cc18  mov     rax, [rsp+3A8h+arg_20]
0x18003cc20  mov     [rsp+3A8h+var_330], rax
0x18003cc25  mov     rax, [rsp+3A8h+arg_28]
0x18003cc2d  mov     [rsp+3A8h+var_328], rax
0x18003cc35  mov     r12, [rsp+3A8h+hResource]
0x18003cc3d  mov     [rsp+3A8h+var_310], r12
0x18003cc45  mov     [rsp+3A8h+nSize], 0
0x18003cc4d  lea     rcx, [rsp+3A8h+var_308]; this
0x18003cc55  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18003cc5a  nop
0x18003cc5b  mov     rdx, r12
0x18003cc5e  call    ??$Contains@PEAU_HRESOURCE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HRESOURCE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HRESOURCE *>(_HRESOURCE *)
0x18003cc63  test    al, al
0x18003cc65  jz      loc_18003D1CE
0x18003cc6b  mov     rdx, r14
0x18003cc6e  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18003cc73  test    al, al
0x18003cc75  jz      loc_18003D1CE
0x18003cc7b  xor     r15d, r15d
0x18003cc7e  mov     [rsp+3A8h+var_320], r15
0x18003cc86  xor     r13d, r13d
0x18003cc89  lea     r8, [rsp+3A8h+nSize]; unsigned int *
0x18003cc8e  lea     edx, [r15+40h]; unsigned int
0x18003cc92  mov     rcx, rbx; wchar_t *
0x18003cc95  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18003cc9a  mov     ebx, eax
0x18003cc9c  test    eax, eax
0x18003cc9e  jnz     loc_18003D19E
0x18003cca4  mov     eax, [rsp+3A8h+nSize]
0x18003cca8  lea     eax, ds:2[rax*2]
0x18003ccaf  mov     [rsp+3A8h+nSize], eax
0x18003ccb3  mov     dl, 1
0x18003ccb5  mov     rcx, r12; hResource
0x18003ccb8  call    SetCoreFlag_0
0x18003ccbd  mov     ebx, eax
0x18003ccbf  test    eax, eax
0x18003ccc1  jz      short loc_18003CCE7
0x18003ccc3  lea     rax, base
0x18003ccca  test    rsi, rsi
0x18003cccd  cmovz   rsi, rax
0x18003ccd1  lea     rax, aFailedToSetCor_1; "Failed to set core flag for NetName res"...
0x18003ccd8  mov     r9d, 1AD0h
0x18003ccde  lea     ecx, [r15+2]
0x18003cce2  jmp     loc_18003D182
0x18003cce7  mov     r14d, 2
0x18003cced  mov     edx, r14d; samDesired
0x18003ccf0  mov     rcx, r12; hResource
0x18003ccf3  call    GetClusterResourceKey
0x18003ccf8  mov     r13, rax
0x18003ccfb  mov     [rsp+3A8h+var_318], rax
0x18003cd03  test    rax, rax
0x18003cd06  jnz     short loc_18003CD4F
0x18003cd08  call    cs:__imp_GetLastError
0x18003cd0e  mov     ebx, eax
0x18003cd10  lea     rax, base
0x18003cd17  test    rsi, rsi
0x18003cd1a  cmovz   rsi, rax
0x18003cd1e  mov     dword ptr [rsp+3A8h+var_378], ebx
0x18003cd22  mov     [rsp+3A8h+var_380], rsi
0x18003cd27  lea     rax, aFailedToGetClu_0; "Failed to get Cluster Resource Key for "...
0x18003cd2e  mov     [rsp+3A8h+var_388], rax
0x18003cd33  mov     r9d, 1AD8h
0x18003cd39  lea     r8, aModifynetworkn_0; "ModifyNetworkName"
0x18003cd40  xor     edx, edx
0x18003cd42  mov     ecx, r14d
0x18003cd45  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003cd4a  jmp     loc_18003D091
0x18003cd4f  mov     [rsp+3A8h+var_380], r15; wchar_t *
0x18003cd54  mov     eax, [rsp+3A8h+nSize]
0x18003cd58  mov     dword ptr [rsp+3A8h+var_388], eax; int
0x18003cd5c  mov     r9, qword ptr [rsp+3A8h+var_350]; int
0x18003cd61  mov     r8d, 1; int
0x18003cd67  lea     rdx, aCorecurrentnam; "CoreCurrentName"
0x18003cd6e  mov     rcx, r13; int
0x18003cd71  call    ClusterRegSetValueEx
0x18003cd76  mov     ebx, eax
0x18003cd78  test    eax, eax
0x18003cd7a  jz      short loc_18003CD9C
0x18003cd7c  lea     rax, base
0x18003cd83  test    rsi, rsi
0x18003cd86  cmovz   rsi, rax
0x18003cd8a  lea     rax, aFailedToSetCor_0; "Failed to set core current name for Net"...
0x18003cd91  mov     r9d, 1AE5h
0x18003cd97  jmp     loc_18003D17F
0x18003cd9c  lea     r8, aModifynetworkn_0; "ModifyNetworkName"
0x18003cda3  xor     edx, edx
0x18003cda5  lea     ecx, [rdx+4]
0x18003cda8  cmp     [rsp+3A8h+arg_40], r15d
0x18003cdb0  jnz     loc_18003CE3F
0x18003cdb6  lea     rax, aModifynetworkn; "ModifyNetworkName: Setting Propery \"Na"...
0x18003cdbd  mov     [rsp+3A8h+var_388], rax
0x18003cdc2  mov     r9d, 1AF1h
0x18003cdc8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003cdcd  mov     rdx, qword ptr [rsp+3A8h+var_350]
0x18003cdd2  lea     rcx, [rsp+3A8h+var_2C0]
0x18003cdda  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003cddf  mov     rbx, rax
0x18003cde2  lea     rdx, aName; "Name"
0x18003cde9  lea     rcx, [rsp+3A8h+var_2E0]
0x18003cdf1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003cdf6  nop
0x18003cdf7  mov     [rsp+3A8h+nSize], 10003h
0x18003cdff  mov     qword ptr [rsp+3A8h+var_350], rbx
0x18003ce04  lea     rcx, [rsp+3A8h+nSize]
0x18003ce09  mov     [rsp+3A8h+var_348], rcx
0x18003ce0e  lea     r8, [rsp+3A8h+var_350]
0x18003ce13  mov     rdx, rax
0x18003ce16  lea     rcx, [rsp+3A8h+var_308]
0x18003ce1e  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x18003ce23  nop
0x18003ce24  lea     rcx, [rsp+3A8h+var_2E0]
0x18003ce2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ce31  nop
0x18003ce32  lea     rcx, [rsp+3A8h+var_2C0]
0x18003ce3a  jmp     loc_18003CEC3
0x18003ce3f  lea     rax, aModifynetworkn_1; "ModifyNetworkName: Setting Propery \"Dn"...
0x18003ce46  mov     [rsp+3A8h+var_388], rax
0x18003ce4b  mov     r9d, 1AF6h
0x18003ce51  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003ce56  mov     rdx, qword ptr [rsp+3A8h+var_350]
0x18003ce5b  lea     rcx, [rsp+3A8h+var_2E0]
0x18003ce63  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003ce68  mov     rbx, rax
0x18003ce6b  lea     rdx, aDnsname; "DnsName"
0x18003ce72  lea     rcx, [rsp+3A8h+var_2C0]
0x18003ce7a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003ce7f  nop
0x18003ce80  mov     [rsp+3A8h+nSize], 10003h
0x18003ce88  mov     qword ptr [rsp+3A8h+var_350], rbx
0x18003ce8d  lea     rcx, [rsp+3A8h+nSize]
0x18003ce92  mov     [rsp+3A8h+var_348], rcx
0x18003ce97  lea     r8, [rsp+3A8h+var_350]
0x18003ce9c  mov     rdx, rax
0x18003ce9f  lea     rcx, [rsp+3A8h+var_308]
0x18003cea7  call    ??$AddPropertyT@V_lambda_5d897758465b3281188928bc355bf98e_@@@PropertyList@cxl@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV_lambda_5d897758465b3281188928bc355bf98e_@@@Z; cxl::PropertyList::AddPropertyT<_lambda_5d897758465b3281188928bc355bf98e_>(std::wstring const &,_lambda_5d897758465b3281188928bc355bf98e_ const &)
0x18003ceac  nop
0x18003cead  lea     rcx, [rsp+3A8h+var_2C0]
0x18003ceb5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ceba  nop
0x18003cebb  lea     rcx, [rsp+3A8h+var_2E0]
0x18003cec3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cec8  mov     r9, [rsp+3A8h+var_2F8]; void *
0x18003ced0  mov     eax, [rsp+3A8h+var_2F0]
0x18003ced7  sub     eax, r9d
0x18003ceda  mov     [rsp+3A8h+var_360], 0; wchar_t *
0x18003cee3  mov     [rsp+3A8h+var_368], 0; bool
0x18003cee8  mov     [rsp+3A8h+var_370], 0; unsigned int *
0x18003cef1  mov     dword ptr [rsp+3A8h+var_378], 0; unsigned int
0x18003cef9  mov     [rsp+3A8h+var_380], 0; void *
0x18003cf02  mov     dword ptr [rsp+3A8h+var_388], eax; unsigned int
0x18003cf06  xor     edx, edx; struct _HNODE *
0x18003cf08  mov     r8d, 1400086h; unsigned int
0x18003cf0e  mov     rcx, r12; struct _HRESOURCE *
0x18003cf11  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x18003cf16  mov     ebx, eax
0x18003cf18  test    eax, eax
0x18003cf1a  jz      short loc_18003CF3C
0x18003cf1c  lea     rax, base
0x18003cf23  test    rsi, rsi
0x18003cf26  cmovz   rsi, rax
0x18003cf2a  lea     rax, aFailedToSetPri_1; "Failed to set private properties for Ne"...
0x18003cf31  mov     r9d, 1B06h
0x18003cf37  jmp     loc_18003D17F
0x18003cf3c  xor     edx, edx; unsigned int
0x18003cf3e  lea     r8d, [rdx+1]; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x18003cf42  mov     rcx, [rsp+3A8h+var_340]; this
0x18003cf47  call    ?EndPhase@PhaseManager@@QEAAXKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::EndPhase(ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x18003cf4c  mov     eax, [rsp+3A8h+arg_30]
0x18003cf53  dec     eax
0x18003cf55  test    eax, 0FFFFFFFDh
0x18003cf5a  jnz     loc_18003D04D
0x18003cf60  xor     edx, edx; Val
0x18003cf62  mov     r8d, 200h; Size
0x18003cf68  lea     rcx, [rsp+3A8h+Buffer]; void *
0x18003cf70  call    memset_0
0x18003cf75  mov     [rsp+3A8h+nSize], 100h
0x18003cf7d  lea     r8, [rsp+3A8h+nSize]; nSize
0x18003cf82  lea     rdx, [rsp+3A8h+Buffer]; lpBuffer
0x18003cf8a  mov     ecx, r14d; NameType
0x18003cf8d  call    cs:__imp_GetComputerNameExW
0x18003cf93  test    eax, eax
0x18003cf95  jnz     short loc_18003CFCB
0x18003cf97  call    cs:__imp_GetLastError
0x18003cf9d  mov     ebx, eax
0x18003cf9f  mov     dword ptr [rsp+3A8h+var_380], eax
0x18003cfa3  lea     rax, aFailedToGetDns; "Failed to get DNS domain name. Error %d"...
0x18003cfaa  mov     [rsp+3A8h+var_388], rax
0x18003cfaf  mov     r9d, 1B17h
0x18003cfb5  lea     r8, aModifynetworkn_0; "ModifyNetworkName"
0x18003cfbc  xor     edx, edx
0x18003cfbe  mov     ecx, r14d
0x18003cfc1  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003cfc6  jmp     loc_18003D091
0x18003cfcb  mov     eax, [rsp+3A8h+arg_48]
0x18003cfd2  mov     dword ptr [rsp+3A8h+var_378], eax; int
0x18003cfd6  lea     rax, [rsp+3A8h+Buffer]
0x18003cfde  mov     [rsp+3A8h+var_380], rax; wchar_t *
0x18003cfe3  mov     rax, [rsp+3A8h+var_330]
0x18003cfe8  mov     [rsp+3A8h+var_388], rax; wchar_t *
0x18003cfed  mov     r9, r12; struct _HRESOURCE *
0x18003cff0  mov     r8, [rsp+3A8h+hCluster]; struct _HCLUSTER *
0x18003cff5  mov     rdx, [rsp+3A8h+var_328]; struct CreateClusterADState *
0x18003cffd  mov     rcx, [rsp+3A8h+var_340]; this
0x18003d002  call    ?ModifyClusterObjectInADAndInitInCluster@@YAKAEAVPhaseManager@@PEAVCreateClusterADState@@PEAU_HCLUSTER@@PEAU_HRESOURCE@@PEB_W4H@Z; ModifyClusterObjectInADAndInitInCluster(PhaseManager &,CreateClusterADState *,_HCLUSTER *,_HRESOURCE *,wchar_t const *,wchar_t const *,int)
0x18003d007  mov     ebx, eax
0x18003d009  test    eax, eax
0x18003d00b  jz      short loc_18003D04D
0x18003d00d  lea     rax, base
0x18003d014  test    rsi, rsi
0x18003d017  cmovz   rsi, rax
0x18003d01b  mov     dword ptr [rsp+3A8h+var_378], ebx
0x18003d01f  mov     [rsp+3A8h+var_380], rsi
0x18003d024  lea     rax, aFailedToModify_2; "Failed to modify computer object for Cl"...
0x18003d02b  mov     [rsp+3A8h+var_388], rax
0x18003d030  mov     r9d, 1B2Ah
0x18003d036  lea     r8, aModifynetworkn_0; "ModifyNetworkName"
0x18003d03d  xor     edx, edx
0x18003d03f  mov     ecx, r14d
0x18003d042  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003d047  nop
0x18003d048  jmp     loc_18003D19E
0x18003d04d  mov     edx, r14d; samDesired
0x18003d050  mov     rcx, [rsp+3A8h+hCluster]; hCluster
0x18003d055  call    GetClusterKey
0x18003d05a  mov     r15, rax
0x18003d05d  xor     edx, edx; struct _HNODE *
0x18003d05f  test    rax, rax
0x18003d062  jnz     short loc_18003D0BF
0x18003d064  mov     dword ptr [rsp+3A8h+var_380], ebx
0x18003d068  lea     rax, aFailedToGetClu; "Failed to get cluster key. Error %d."
0x18003d06f  mov     [rsp+3A8h+var_388], rax
0x18003d074  mov     r9d, 1B39h
0x18003d07a  lea     r8, aModifynetworkn_0; "ModifyNetworkName"
0x18003d081  mov     ecx, r14d
0x18003d084  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003d089  call    cs:__imp_GetLastError
0x18003d08f  mov     ebx, eax
0x18003d091  test    ebx, ebx
0x18003d093  jz      loc_18003D1A8
0x18003d099  jmp     loc_18003D19E
0x18003d09e  mov     r15, [rsp+3A8h+var_320]
0x18003d0a6  mov     r13, [rsp+3A8h+var_318]
0x18003d0ae  mov     ebx, [rsp+3A8h+var_350]
0x18003d0b2  mov     r12, [rsp+3A8h+var_310]
0x18003d0ba  jmp     loc_18003D19E
0x18003d0bf  mov     [rsp+3A8h+nSize], 0
0x18003d0c7  mov     [rsp+3A8h+var_360], 0; wchar_t *
0x18003d0d0  mov     [rsp+3A8h+var_368], 0; bool
0x18003d0d5  lea     rax, [rsp+3A8h+nSize]
0x18003d0da  mov     [rsp+3A8h+var_370], rax; unsigned int *
0x18003d0df  mov     dword ptr [rsp+3A8h+var_378], 50h ; 'P'; unsigned int
0x18003d0e7  lea     rax, [rsp+3A8h+var_298]
0x18003d0ef  mov     [rsp+3A8h+var_380], rax; void *
0x18003d0f4  mov     dword ptr [rsp+3A8h+var_388], 0; unsigned int
0x18003d0fc  xor     r9d, r9d; void *
0x18003d0ff  mov     r8d, 1000039h; unsigned int
0x18003d105  mov     rcx, r12; struct _HRESOURCE *
0x18003d108  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x18003d10d  mov     ebx, eax
0x18003d10f  test    eax, eax
0x18003d111  jz      short loc_18003D130
0x18003d113  lea     rax, base
0x18003d11a  test    rsi, rsi
0x18003d11d  cmovz   rsi, rax
0x18003d121  lea     rax, aFailedToGetRes_3; "Failed to get resource Id for NetName %"...
0x18003d128  mov     r9d, 1B4Bh
0x18003d12e  jmp     short loc_18003D17F
0x18003d130  mov     [rsp+3A8h+var_380], 0; wchar_t *
0x18003d139  mov     eax, [rsp+3A8h+nSize]
0x18003d13d  mov     dword ptr [rsp+3A8h+var_388], eax; int
0x18003d141  lea     r9, [rsp+3A8h+var_298]; int
0x18003d149  mov     r8d, 1; int
0x18003d14f  lea     rdx, aClusternameres; "ClusterNameResource"
0x18003d156  mov     rcx, r15; int
0x18003d159  call    ClusterRegSetValueEx
0x18003d15e  mov     ebx, eax
0x18003d160  test    eax, eax
0x18003d162  jz      short loc_18003D1AD
0x18003d164  lea     rax, base
0x18003d16b  test    rsi, rsi
0x18003d16e  cmovz   rsi, rax
0x18003d172  lea     rax, aFailedToSetRes; "Failed to set resource Id key in cluste"...
0x18003d179  mov     r9d, 1B57h
0x18003d17f  mov     ecx, r14d
  ... truncated ...
```
