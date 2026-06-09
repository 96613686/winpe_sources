# ClusNode::ConfigureNode(std::vector<wchar_t,std::allocator<wchar_t>> &,std::vector<uchar,std::allocator<uchar>> const &,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,_CLUSTER_CERT *,ulong,bool,ulong *,bool,ushort)

- ea: `0x1800465e0`
- end: `0x180047430`
- name: `?ConfigureNode@ClusNode@@QEAAXAEAV?$vector@_WV?$allocator@_W@std@@@std@@AEBV?$vector@EV?$allocator@E@std@@@3@PEAU_CLUSTER_CERT@@222K_NPEAK3G@Z`
- size: `3664`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, unsigned int, char, BYTE *lpData, char, __int16)`
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180036c8c`
- `0x180040790`
- `0x1800791d0`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x180028f30`
- `0x180029410`
- `0x18003180c`
- `0x180033190`
- `0x1800332b8`
- `0x18003b03c`
- `0x1800463cc`
- `0x1800465e0`
- `0x180047938`
- `0x1800479f8`
- `0x18006ebd8`
- `0x18006ed20`
- `0x18006f06c`
- `0x18006f22c`
- `0x18009f420`
- `0x1800acfe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004669b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800467e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004669b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800467e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ab1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046ed5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046f3a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046fa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047022`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800470a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047113`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047305`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004736f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d1d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046d98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046ed5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046f3a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180046fa7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047022`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800470a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047113`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047305`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004736f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046c8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047214`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180046c8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180047214`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046cd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046ce8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004726d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046cd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046ce8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004726d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800473d2`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800473d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046e2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046e2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046e6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800472ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046e6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800472ca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800467c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800468f5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800467c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800468f5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180046a9c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180046a9c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004667a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004670d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004667a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004670d`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180046b69`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180046b69`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180046a39`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180046a39`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180046833`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180046952`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180046833`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180046952`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180046bd2`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180046bd2`

## string_xrefs

- `0x180046c7e`: `SYSTEM\CurrentControlSet\Services\ClusSvc\Parameters`
- `0x180046e21`: `SYSTEM\CurrentControlSet\Services\ClusSvc\Parameters`
- `0x180046e5f`: `CreateInMixedMode`
- `0x180047109`: `AdminAccessPoint`
- `0x18004712c`: `AdminAccessPoint`
- `0x1800466a4`: `Failed to get buffer size for the ClusSvc service entry on '%ws'`
- `0x18004672b`: `Failed to interrogate the ClusSvc service entry on '%ws'`
- `0x18004676f`: `The ClusSvc service is already installed on '%ws'`
- `0x1800467e9`: `Failed to open the NetFT driver entry on '%ws'`
- `0x18004691b`: `Failed to open the ClusDisk driver entry on '%ws'`
- `0x180046a57`: `Failed to enable the ClusSvc service entry on '%ws'`
- `0x180046aba`: `Failed to set ClusSvc service SID Type to "Unrestricted" on %ws`
- `0x180046be9`: `Failed to connect to remote registry on node %ws`
- `0x180046ca4`: `Failed to create service parameters key on node %ws`
- `0x180046cce`: `NodeCreatedFlag`
- `0x180046cde`: `QuorumConfig`
- `0x180046d3d`: `Failed to set %ws value in registry on node %ws`
- `0x180046db8`: `Failed to set %ws value in registry on node %ws`
- `0x180046ef9`: `Failed to set %ws value in registry on node %ws`
- `0x180047042`: `Failed to set %ws value in registry on node %ws`
- `0x1800470c4`: `Failed to set %ws value in registry on node %ws`
- `0x180047133`: `Failed to set %ws value in registry on node %ws`
- `0x180047321`: `Failed to set %ws value in registry on node %ws`
- `0x180046ece`: `CreateInUplevelOnlyMode`
- `0x180046ef2`: `CreateInUplevelOnlyMode`
- `0x180046f5a`: `Failed to set the %ws value in registry on node %ws`
- `0x180046fc7`: `Failed to set the %ws value in registry on node %ws`
- `0x180047018`: `CreatedFromDownlevel`
- `0x18004703b`: `CreatedFromDownlevel`
- `0x18004719e`: `Failed to configure Cluster Secret via CPrep Server `
- `0x180047205`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters`
- `0x18004722d`: `SYSTEM\CurrentControlSet\Services\IKEEXT\Parameters`
- `0x180047234`: `Failed to create %ws key on node %ws`
- `0x180047386`: `Failed to set NLBSFlags value in registry on node %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ClusNode::ConfigureNode(
        PhaseManager **a1,
        __int64 a2,
        __int64 a3,
        struct _CLUSTER_CERT *a4,
        struct _CLUSTER_CERT *a5,
        struct _CLUSTER_CERT *a6,
        struct _CLUSTER_CERT *a7,
        unsigned int a8,
        char a9,
        BYTE *lpData,
        char a11,
        unsigned __int16 a12)
{
  BOOL v15; // eax
  __int64 v16; // rbx
  DWORD LastError; // eax
  BOOL v18; // eax
  PhaseManager **v19; // rcx
  __int64 v20; // rbx
  DWORD v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  SC_HANDLE v24; // rax
  __int64 v25; // rbx
  DWORD v26; // eax
  __int64 v27; // rbx
  DWORD v28; // eax
  __int64 v29; // rax
  __int64 v30; // rax
  SC_HANDLE v31; // rax
  __int64 v32; // rbx
  DWORD v33; // eax
  __int64 v34; // rbx
  DWORD v35; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rbx
  DWORD v39; // eax
  BOOL v40; // eax
  PhaseManager **v41; // rcx
  __int64 v42; // rbx
  DWORD v43; // eax
  __int64 v44; // rax
  int v45; // ebx
  __int64 v46; // rax
  DWORD v47; // ebx
  __int64 v48; // rax
  const WCHAR *v49; // rax
  LSTATUS v50; // ebx
  __int64 v51; // rax
  PhaseManager *v52; // rcx
  HKEY *v53; // r14
  LSTATUS v54; // ebx
  __int64 v55; // rax
  const BYTE *v56; // rax
  LSTATUS v57; // ebx
  __int64 v58; // rax
  LSTATUS v59; // ebx
  __int64 v60; // rax
  bool v61; // bl
  const wchar_t *v62; // rax
  HKEY v63; // rcx
  LSTATUS v64; // ebx
  __int64 v65; // rax
  LSTATUS v66; // ebx
  __int64 v67; // rax
  LSTATUS v68; // ebx
  __int64 v69; // rax
  LSTATUS v70; // ebx
  __int64 v71; // rax
  __int64 v72; // rax
  LSTATUS v73; // ebx
  __int64 v74; // rax
  LSTATUS v75; // ebx
  __int64 v76; // rax
  const wchar_t *v77; // rax
  int v78; // eax
  LSTATUS v79; // ebx
  __int64 v80; // rax
  LSTATUS v81; // ebx
  __int64 v82; // rax
  LSTATUS v83; // ebx
  __int64 v84; // rax
  _BYTE v86[4]; // [rsp+60h] [rbp-1DC8h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-1DC4h] BYREF
  BYTE v88[4]; // [rsp+68h] [rbp-1DC0h] BYREF
  DWORD pcbBytesNeeded; // [rsp+6Ch] [rbp-1DBCh] BYREF
  HKEY v90; // [rsp+70h] [rbp-1DB8h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-1DB0h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-1DACh] BYREF
  DWORD v93; // [rsp+80h] [rbp-1DA8h] BYREF
  BYTE v94[4]; // [rsp+84h] [rbp-1DA4h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-1DA0h] BYREF
  int Info; // [rsp+90h] [rbp-1D98h] BYREF
  BYTE Data[4]; // [rsp+94h] [rbp-1D94h] BYREF
  BYTE v98[4]; // [rsp+98h] [rbp-1D90h] BYREF
  BYTE v99[4]; // [rsp+9Ch] [rbp-1D8Ch] BYREF
  HKEY hKey[2]; // [rsp+A0h] [rbp-1D88h] BYREF
  struct _CLUSTER_CERT *v101; // [rsp+B0h] [rbp-1D78h]
  struct _CLUSTER_CERT *v102; // [rsp+B8h] [rbp-1D70h]
  struct _CLUSTER_CERT *v103; // [rsp+C0h] [rbp-1D68h]
  __int64 v104; // [rsp+C8h] [rbp-1D60h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+D0h] [rbp-1D58h] BYREF
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+E8h] [rbp-1D40h] BYREF
  int v107; // [rsp+F0h] [rbp-1D38h]
  ClusRtl::ExceptionMsg *v108; // [rsp+100h] [rbp-1D28h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+108h] [rbp-1D20h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+130h] [rbp-1CF8h] BYREF
  _BYTE v111[272]; // [rsp+240h] [rbp-1BE8h] BYREF
  _BYTE v112[272]; // [rsp+350h] [rbp-1AD8h] BYREF
  _BYTE v113[272]; // [rsp+460h] [rbp-19C8h] BYREF
  _BYTE v114[272]; // [rsp+570h] [rbp-18B8h] BYREF
  _BYTE v115[272]; // [rsp+680h] [rbp-17A8h] BYREF
  _BYTE v116[272]; // [rsp+790h] [rbp-1698h] BYREF
  _BYTE v117[272]; // [rsp+8A0h] [rbp-1588h] BYREF
  _BYTE v118[272]; // [rsp+9B0h] [rbp-1478h] BYREF
  _BYTE v119[272]; // [rsp+AC0h] [rbp-1368h] BYREF
  _BYTE v120[272]; // [rsp+BD0h] [rbp-1258h] BYREF
  _BYTE v121[272]; // [rsp+CE0h] [rbp-1148h] BYREF
  _BYTE v122[272]; // [rsp+DF0h] [rbp-1038h] BYREF
  _BYTE v123[272]; // [rsp+F00h] [rbp-F28h] BYREF
  _BYTE v124[272]; // [rsp+1010h] [rbp-E18h] BYREF
  _BYTE v125[272]; // [rsp+1120h] [rbp-D08h] BYREF
  _BYTE v126[272]; // [rsp+1230h] [rbp-BF8h] BYREF
  _BYTE v127[272]; // [rsp+1340h] [rbp-AE8h] BYREF
  _BYTE v128[272]; // [rsp+1450h] [rbp-9D8h] BYREF
  _BYTE v129[272]; // [rsp+1560h] [rbp-8C8h] BYREF
  _BYTE v130[272]; // [rsp+1670h] [rbp-7B8h] BYREF
  _BYTE v131[272]; // [rsp+1780h] [rbp-6A8h] BYREF
  _BYTE v132[272]; // [rsp+1890h] [rbp-598h] BYREF
  _BYTE v133[272]; // [rsp+19A0h] [rbp-488h] BYREF
  _BYTE v134[272]; // [rsp+1AB0h] [rbp-378h] BYREF
  _BYTE v135[272]; // [rsp+1BC0h] [rbp-268h] BYREF
  _BYTE v136[272]; // [rsp+1CD0h] [rbp-158h] BYREF

  v104 = a2;
  v103 = a5;
  v102 = a6;
  v101 = a7;
  phkResult = 0;
  v90 = 0;
  pcbBytesNeeded = 0;
  v15 = QueryServiceConfigW((SC_HANDLE)a1[16], 0, 0, &pcbBytesNeeded);
  try
  {
    if ( !v15 && GetLastError() != 122 )
    {
      v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      LastError = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)pExceptionObject,
        LastError,
        L"Failed to get buffer size for the ClusSvc service entry on '%ws'",
        v16);
      throw (ClusRtl::ExceptionMsg *)pExceptionObject;
    }
    v86[0] = 0;
    std::vector<unsigned char>::vector<unsigned char>(&lpServiceConfig, pcbBytesNeeded, v86);
    v18 = QueryServiceConfigW((SC_HANDLE)a1[16], lpServiceConfig, v107 - (_DWORD)lpServiceConfig, &pcbBytesNeeded);
    v19 = a1 + 6;
    if ( !v18 )
    {
      v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19);
      v21 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v111,
        v21,
        L"Failed to interrogate the ClusSvc service entry on '%ws'",
        v20);
      throw (ClusRtl::ExceptionMsg *)v111;
    }
    if ( lpServiceConfig->dwStartType != 4 )
    {
      v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v112,
        5065,
        L"The ClusSvc service is already installed on '%ws'",
        v22);
      throw (ClusRtl::ExceptionMsg *)v112;
    }
    v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v19);
    PhaseManager::StartPhase(a1[1], 102, v23);
    v24 = OpenServiceW((SC_HANDLE)a1[15], L"NetFT", 0x80u);
    a1[17] = (PhaseManager *)v24;
    if ( !v24 )
    {
      v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      v26 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v113,
        v26,
        L"Failed to open the NetFT driver entry on '%ws'",
        v25);
      throw (ClusRtl::ExceptionMsg *)v113;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !ControlService(v24, 4u, &ServiceStatus) )
    {
      v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      v28 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v114,
        v28,
        L"Failed to interrogate the NetFT driver entry on '%ws'",
        v27);
      throw (ClusRtl::ExceptionMsg *)v114;
    }
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      v29 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v115,
        1062,
        L"The NetFT driver has not been started on '%ws'",
        v29);
      throw (ClusRtl::ExceptionMsg *)v115;
    }
    PhaseManager::EndPhase(a1[1], 0, ClusterSetupPhaseInformational);
    v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
    PhaseManager::StartPhase(a1[1], 103, v30);
    v31 = OpenServiceW((SC_HANDLE)a1[15], L"ClusDisk", 0x80u);
    a1[18] = (PhaseManager *)v31;
    if ( !v31 )
    {
      v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      v33 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v116,
        v33,
        L"Failed to open the ClusDisk driver entry on '%ws'",
        v32);
      throw (ClusRtl::ExceptionMsg *)v116;
    }
    if ( !ControlService(v31, 4u, &ServiceStatus) )
    {
      v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      v35 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v117,
        v35,
        L"Failed to interrogate the ClusDisk driver entry on '%ws'",
        v34);
      throw (ClusRtl::ExceptionMsg *)v117;
    }
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v118,
        1062,
        L"The ClusDisk driver has not been started on '%ws'",
        v36);
      throw (ClusRtl::ExceptionMsg *)v118;
    }
    PhaseManager::EndPhase(a1[1], 0, ClusterSetupPhaseInformational);
    v37 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
    PhaseManager::StartPhase(a1[1], 104, v37);
    if ( !ChangeServiceConfigW((SC_HANDLE)a1[16], 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v38 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      v39 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v119,
        v39,
        L"Failed to enable the ClusSvc service entry on '%ws'",
        v38);
      throw (ClusRtl::ExceptionMsg *)v119;
    }
    Info = 1;
    v40 = ChangeServiceConfig2W((SC_HANDLE)a1[16], 5u, &Info);
    v41 = a1 + 6;
    if ( !v40 )
    {
      v42 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v41);
      v43 = GetLastError();
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v120,
        v43,
        L"Failed to set ClusSvc service SID Type to \"Unrestricted\" on %ws",
        v42);
      throw (ClusRtl::ExceptionMsg *)v120;
    }
    v44 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v41);
    v45 = ClRtlSetSCMFailureActions(v44);
    if ( v45 )
    {
      v46 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v121,
        v45,
        L"Failed to set SCM failure actions on %ws",
        v46);
      throw (ClusRtl::ExceptionMsg *)v121;
    }
    CRevertToken::CRevertToken((PHANDLE)hKey);
    *((_DWORD *)a1 + 38) = 2;
    a1[20] = (PhaseManager *)SCMStateChangeNotify;
    a1[21] = (PhaseManager *)a1;
    v47 = NotifyServiceStatusChangeW((SC_HANDLE)a1[16], 0xEu, (PSERVICE_NOTIFYW)(a1 + 19));
    if ( v47 )
    {
      v48 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v122,
        v47,
        L"Failed to set state change notify for node %ws",
        v48);
      throw (ClusRtl::ExceptionMsg *)v122;
    }
    CRevertToken::~CRevertToken((CRevertToken *)hKey);
    v49 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
    v50 = RegConnectRegistryW(v49, HKEY_LOCAL_MACHINE, &phkResult);
    if ( v50 )
    {
      v51 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v123,
        v50,
        L"Failed to connect to remote registry on node %ws",
        v51);
      throw (ClusRtl::ExceptionMsg *)v123;
    }
    v52 = *a1;
    SecurityAttributes.nLength = *((_DWORD *)*a1 + 12) - *((_DWORD *)*a1 + 10);
    *(&SecurityAttributes.nLength + 1) = 0;
    SecurityAttributes.lpSecurityDescriptor = (LPVOID)*((_QWORD *)v52 + 5);
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    dwDisposition = 0;
    v53 = (HKEY *)(a1 + 29);
    v54 = RegCreateKeyExW(
            phkResult,
            L"SYSTEM\\CurrentControlSet\\Services\\ClusSvc\\Parameters",
            0,
            0,
            0,
            0x10003u,
            &SecurityAttributes,
            (PHKEY)a1 + 29,
            &dwDisposition);
    if ( v54 )
    {
      v55 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v124,
        v54,
        L"Failed to create service parameters key on node %ws",
        v55);
      throw (ClusRtl::ExceptionMsg *)v124;
    }
    RegDeleteValueW(*v53, L"NodeCreatedFlag");
    RegDeleteValueW(*v53, L"QuorumConfig");
    v56 = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 2);
    v57 = RegSetValueExW(*v53, L"ClusterName", 0, 1u, v56, 2 * *((_DWORD *)a1 + 8) + 2);
    if ( v57 )
    {
      v58 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v125,
        v57,
        L"Failed to set %ws value in registry on node %ws",
        L"ClusterName",
        v58);
      throw (ClusRtl::ExceptionMsg *)v125;
    }
    *(_DWORD *)Data = 1;
    v59 = RegSetValueExW(*v53, L"ClusterFirstRun", 0, 4u, Data, 4u);
    if ( v59 )
    {
      v60 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v126,
        v59,
        L"Failed to set %ws value in registry on node %ws",
        L"ClusterFirstRun",
        v60);
      throw (ClusRtl::ExceptionMsg *)v126;
    }
    if ( !a11 )
    {
      hKey[0] = 0;
      v61 = 1;
      cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(hKey);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\ClusSvc\\Parameters", 0, 1u, hKey) )
      {
        *(_DWORD *)v88 = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey[0], L"CreateInMixedMode", 0, 0, v88, &cbData) )
          v61 = *(_DWORD *)v88 != 1;
      }
      v62 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      if ( ((unsigned __int8)-(GetFunctionalLevelOnNode(v62) != 0) & v61) != 0 )
      {
        v63 = *v53;
        if ( a9 )
        {
          cbData = 14;
          *(_DWORD *)v88 = 1;
          v66 = RegSetValueExW(v63, L"NodeMinimumMajorVersion", 0, 4u, (const BYTE *)&cbData, 4u);
          if ( v66 )
          {
            v67 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
            ClusRtl::ExceptionMsg::ExceptionMsg(
              (ClusRtl::ExceptionMsg *)v128,
              v66,
              L"Failed to set the %ws value in registry on node %ws",
              L"NodeMinimumMajorVersion",
              v67);
            throw (ClusRtl::ExceptionMsg *)v128;
          }
          v68 = RegSetValueExW(*v53, L"NodeMinimumUpgradeVersion", 0, 4u, v88, 4u);
          if ( v68 )
          {
            v69 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
            ClusRtl::ExceptionMsg::ExceptionMsg(
              (ClusRtl::ExceptionMsg *)v129,
              v68,
              L"Failed to set the %ws value in registry on node %ws",
              L"NodeMinimumUpgradeVersion",
              v69);
            throw (ClusRtl::ExceptionMsg *)v129;
          }
          *(_DWORD *)v98 = 1;
          v70 = RegSetValueExW(*v53, L"CreatedFromDownlevel", 0, 4u, v98, 4u);
          if ( v70 )
          {
            v71 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
            ClusRtl::ExceptionMsg::ExceptionMsg(
              (ClusRtl::ExceptionMsg *)v130,
              v70,
              L"Failed to set %ws value in registry on node %ws",
              L"CreatedFromDownlevel",
              v71);
            throw (ClusRtl::ExceptionMsg *)v130;
          }
        }
        else
        {
          cbData = 1;
          v64 = RegSetValueExW(v63, L"CreateInUplevelOnlyMode", 0, 4u, (const BYTE *)&cbData, 4u);
          if ( v64 )
          {
            v65 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
            ClusRtl::ExceptionMsg::ExceptionMsg(
              (ClusRtl::ExceptionMsg *)v127,
              v64,
              L"Failed to set %ws value in registry on node %ws",
              L"CreateInUplevelOnlyMode",
              v65);
            throw (ClusRtl::ExceptionMsg *)v127;
          }
        }
      }
      cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(hKey);
    }
    v72 = *(_QWORD *)(a3 + 8);
    if ( *(_QWORD *)a3 != v72 )
    {
      v73 = RegSetValueExW(*v53, L"InstanceGuid", 0, 3u, *(const BYTE **)a3, v72 - *(_QWORD *)a3);
      if ( v73 )
      {
        v74 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v131,
          v73,
          L"Failed to set %ws value in registry on node %ws",
          L"InstanceGuid",
          v74);
        throw (ClusRtl::ExceptionMsg *)v131;
      }
    }
    if ( lpData )
    {
      v75 = RegSetValueExW(*v53, L"AdminAccessPoint", 0, 4u, lpData, 4u);
      if ( v75 )
      {
        v76 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v132,
          v75,
          L"Failed to set %ws value in registry on node %ws",
          L"AdminAccessPoint",
          v76);
        throw (ClusRtl::ExceptionMsg *)v132;
      }
    }
    v77 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
    v78 = ConfigClusterCert(v77, a4, v103, v102, v101, a12);
    if ( v78 < 0 )
    {
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v133,
        v78,
        L"Failed to configure Cluster Secret via CPrep Server ");
      throw (ClusRtl::ExceptionMsg *)v133;
    }
    cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&v90);
    v79 = RegCreateKeyExW(
            phkResult,
            L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters",
            0,
            0,
            0,
            0x10003u,
            0,
            &v90,
            &dwDisposition);
    if ( v79 )
    {
      v80 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v134,
        v79,
        L"Failed to create %ws key on node %ws",
        L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT\\Parameters",
        v80);
      throw (ClusRtl::ExceptionMsg *)v134;
    }
    RegDeleteValueW(v90, L"FailoverClusterRestoreNLBSFlags");
    *(_DWORD *)v99 = 1;
    *(_DWORD *)v94 = 0;
    Type = 0;
    v93 = 4;
    if ( !RegQueryValueExW(v90, L"NLBSFlags", 0, &Type, v94, &v93) && Type == 4 && v93 == 4 )
    {
      v81 = RegSetValueExW(v90, L"FailoverClusterRestoreNLBSFlags", 0, 4u, v94, 4u);
      if ( v81 )
      {
        v82 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
        ClusRtl::ExceptionMsg::ExceptionMsg(
          (ClusRtl::ExceptionMsg *)v135,
          v81,
          L"Failed to set %ws value in registry on node %ws",
          L"FailoverClusterRestoreNLBSFlags",
          v82);
        throw (ClusRtl::ExceptionMsg *)v135;
      }
    }
    v83 = RegSetValueExW(v90, L"NLBSFlags", 0, 4u, v99, 4u);
    if ( v83 )
    {
      v84 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 6);
      ClusRtl::ExceptionMsg::ExceptionMsg(
        (ClusRtl::ExceptionMsg *)v136,
        v83,
        L"Failed to set NLBSFlags value in registry on node %ws",
        v84);
      throw (ClusRtl::ExceptionMsg *)v136;
    }
    ClusNode::SetSQMHash((ClusNode *)a1, a8);
    ClusNode::SetMembershipInfo(a1, v104);
    RegFlushKey(*v53);
    PhaseManager::EndPhase(a1[1], 0, ClusterSetupPhaseInformational);
  }
  catch ( ClusRtl::ExceptionMsg *v108 )
  {
    TraceMsg(2, 0, L"ClusNode::ConfigureNode", 503, L"exception - error %d: %ws", *((_DWORD *)v108 + 64), v108);
    throw;
  }
  std::vector<unsigned char>::_Tidy(&lpServiceConfig);
  cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&v90);
  return cxl::AutoHandle<HKEY__ *,long,&long RegCloseKey(HKEY__ *),0>::Close(&phkResult);
}

```

## disassembly

```asm
0x1800465e0  push    rbx
0x1800465e2  push    rsi
0x1800465e3  push    rdi
0x1800465e4  push    r12
0x1800465e6  push    r13
0x1800465e8  push    r14
0x1800465ea  push    r15
0x1800465ec  mov     eax, 1DF0h
0x1800465f1  call    _alloca_probe
0x1800465f6  sub     rsp, rax
0x1800465f9  mov     rax, cs:__security_cookie
0x180046600  xor     rax, rsp
0x180046603  mov     [rsp+1E28h+var_48], rax
0x18004660b  mov     r13, r9
0x18004660e  mov     r15, r8
0x180046611  mov     [rsp+1E28h+var_1D60], rdx
0x180046619  mov     rsi, rcx
0x18004661c  mov     rax, [rsp+1E28h+arg_20]
0x180046624  mov     [rsp+1E28h+var_1D68], rax
0x18004662c  mov     rax, [rsp+1E28h+arg_28]
0x180046634  mov     [rsp+1E28h+var_1D70], rax
0x18004663c  mov     rax, [rsp+1E28h+arg_30]
0x180046644  mov     [rsp+1E28h+var_1D78], rax
0x18004664c  mov     r12, [rsp+1E28h+lpData]
0x180046654  xor     r14d, r14d
0x180046657  mov     [rsp+1E28h+phkResult], r14
0x18004665f  mov     [rsp+1E28h+var_1DB8], r14
0x180046664  mov     [rsp+1E28h+pcbBytesNeeded], r14d
0x180046669  lea     r9, [rsp+1E28h+pcbBytesNeeded]; pcbBytesNeeded
0x18004666e  xor     r8d, r8d; cbBufSize
0x180046671  xor     edx, edx; lpServiceConfig
0x180046673  mov     rcx, [rcx+80h]; hService
0x18004667a  call    cs:__imp_QueryServiceConfigW
0x180046680  test    eax, eax
0x180046682  jnz     short loc_1800466CE
0x180046684  call    cs:__imp_GetLastError
0x18004668a  cmp     eax, 7Ah ; 'z'
0x18004668d  jz      short loc_1800466CE
0x18004668f  lea     rcx, [rsi+30h]
0x180046693  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046698  mov     rbx, rax
0x18004669b  call    cs:__imp_GetLastError
0x1800466a1  mov     r9, rbx
0x1800466a4  lea     r8, aFailedToGetBuf; "Failed to get buffer size for the ClusS"...
0x1800466ab  mov     edx, eax; int
0x1800466ad  lea     rcx, [rsp+1E28h+pExceptionObject]; this
0x1800466b5  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800466ba  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800466c1  lea     rcx, [rsp+1E28h+pExceptionObject]; pExceptionObject
0x1800466c9  call    _CxxThrowException_0
0x1800466ce  mov     [rsp+1E28h+var_1DC8], r14b
0x1800466d3  mov     edx, [rsp+1E28h+pcbBytesNeeded]
0x1800466d7  lea     r8, [rsp+1E28h+var_1DC8]
0x1800466dc  lea     rcx, [rsp+1E28h+lpServiceConfig]
0x1800466e4  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x1800466e9  nop
0x1800466ea  mov     rdx, [rsp+1E28h+lpServiceConfig]; lpServiceConfig
0x1800466f2  lea     rdi, [rsi+30h]
0x1800466f6  mov     r8d, [rsp+1E28h+var_1D38]
0x1800466fe  sub     r8d, edx; cbBufSize
0x180046701  lea     r9, [rsp+1E28h+pcbBytesNeeded]; pcbBytesNeeded
0x180046706  mov     rcx, [rsi+80h]; hService
0x18004670d  call    cs:__imp_QueryServiceConfigW
0x180046713  mov     rcx, rdi
0x180046716  test    eax, eax
0x180046718  jnz     short loc_180046755
0x18004671a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004671f  mov     rbx, rax
0x180046722  call    cs:__imp_GetLastError
0x180046728  mov     r9, rbx
0x18004672b  lea     r8, aFailedToInterr_0; "Failed to interrogate the ClusSvc servi"...
0x180046732  mov     edx, eax; int
0x180046734  lea     rcx, [rsp+1E28h+var_1BE8]; this
0x18004673c  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046741  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180046748  lea     rcx, [rsp+1E28h+var_1BE8]; pExceptionObject
0x180046750  call    _CxxThrowException_0
0x180046755  mov     ebx, 4
0x18004675a  mov     rax, [rsp+1E28h+lpServiceConfig]
0x180046762  cmp     [rax+4], ebx
0x180046765  jz      short loc_18004679C
0x180046767  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004676c  mov     r9, rax
0x18004676f  lea     r8, aTheClussvcServ; "The ClusSvc service is already installe"...
0x180046776  mov     edx, 13C9h; int
0x18004677b  lea     rcx, [rsp+1E28h+var_1AD8]; this
0x180046783  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046788  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004678f  lea     rcx, [rsp+1E28h+var_1AD8]; pExceptionObject
0x180046797  call    _CxxThrowException_0
0x18004679c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800467a1  mov     r8, rax
0x1800467a4  mov     edx, 66h ; 'f'
0x1800467a9  mov     rcx, [rsi+8]
0x1800467ad  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x1800467b2  mov     r8d, 80h; dwDesiredAccess
0x1800467b8  lea     rdx, aNetft; "NetFT"
0x1800467bf  mov     rcx, [rsi+78h]; hSCManager
0x1800467c3  call    cs:__imp_OpenServiceW
0x1800467c9  mov     [rsi+88h], rax
0x1800467d0  test    rax, rax
0x1800467d3  jnz     short loc_180046813
0x1800467d5  mov     rcx, rdi
0x1800467d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800467dd  mov     rbx, rax
0x1800467e0  call    cs:__imp_GetLastError
0x1800467e6  mov     r9, rbx
0x1800467e9  lea     r8, aFailedToOpenTh_1; "Failed to open the NetFT driver entry o"...
0x1800467f0  mov     edx, eax; int
0x1800467f2  lea     rcx, [rsp+1E28h+var_19C8]; this
0x1800467fa  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800467ff  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180046806  lea     rcx, [rsp+1E28h+var_19C8]; pExceptionObject
0x18004680e  call    _CxxThrowException_0
0x180046813  xorps   xmm0, xmm0
0x180046816  movups  xmmword ptr [rsp+1E28h+ServiceStatus.dwServiceType], xmm0
0x18004681e  movups  xmmword ptr [rsp+1E28h+ServiceStatus.dwWin32ExitCode], xmm0
0x180046826  lea     r8, [rsp+1E28h+ServiceStatus]; lpServiceStatus
0x18004682e  mov     edx, ebx; dwControl
0x180046830  mov     rcx, rax; hService
0x180046833  call    cs:__imp_ControlService
0x180046839  test    eax, eax
0x18004683b  jnz     short loc_18004687B
0x18004683d  mov     rcx, rdi
0x180046840  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046845  mov     rbx, rax
0x180046848  call    cs:__imp_GetLastError
0x18004684e  mov     r9, rbx
0x180046851  lea     r8, aFailedToInterr; "Failed to interrogate the NetFT driver "...
0x180046858  mov     edx, eax; int
0x18004685a  lea     rcx, [rsp+1E28h+var_18B8]; this
0x180046862  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046867  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004686e  lea     rcx, [rsp+1E28h+var_18B8]; pExceptionObject
0x180046876  call    _CxxThrowException_0
0x18004687b  cmp     [rsp+1E28h+ServiceStatus.dwCurrentState], ebx
0x180046882  jz      short loc_1800468BC
0x180046884  mov     rcx, rdi
0x180046887  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004688c  mov     r9, rax
0x18004688f  lea     r8, aTheNetftDriver; "The NetFT driver has not been started o"...
0x180046896  mov     edx, 426h; int
0x18004689b  lea     rcx, [rsp+1E28h+var_17A8]; this
0x1800468a3  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800468a8  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800468af  lea     rcx, [rsp+1E28h+var_17A8]; pExceptionObject
0x1800468b7  call    _CxxThrowException_0
0x1800468bc  xor     edx, edx; unsigned int
0x1800468be  lea     r8d, [rdx+1]; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x1800468c2  mov     rcx, [rsi+8]; this
0x1800468c6  call    ?EndPhase@PhaseManager@@QEAAXKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::EndPhase(ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x1800468cb  mov     rcx, rdi
0x1800468ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800468d3  mov     r8, rax
0x1800468d6  mov     edx, 67h ; 'g'
0x1800468db  mov     rcx, [rsi+8]
0x1800468df  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x1800468e4  mov     r8d, 80h; dwDesiredAccess
0x1800468ea  lea     rdx, aClusdisk; "ClusDisk"
0x1800468f1  mov     rcx, [rsi+78h]; hSCManager
0x1800468f5  call    cs:__imp_OpenServiceW
0x1800468fb  mov     [rsi+90h], rax
0x180046902  test    rax, rax
0x180046905  jnz     short loc_180046945
0x180046907  mov     rcx, rdi
0x18004690a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004690f  mov     rbx, rax
0x180046912  call    cs:__imp_GetLastError
0x180046918  mov     r9, rbx
0x18004691b  lea     r8, aFailedToOpenTh; "Failed to open the ClusDisk driver entr"...
0x180046922  mov     edx, eax; int
0x180046924  lea     rcx, [rsp+1E28h+var_1698]; this
0x18004692c  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046931  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180046938  lea     rcx, [rsp+1E28h+var_1698]; pExceptionObject
0x180046940  call    _CxxThrowException_0
0x180046945  lea     r8, [rsp+1E28h+ServiceStatus]; lpServiceStatus
0x18004694d  mov     edx, ebx; dwControl
0x18004694f  mov     rcx, rax; hService
0x180046952  call    cs:__imp_ControlService
0x180046958  test    eax, eax
0x18004695a  jnz     short loc_18004699A
0x18004695c  mov     rcx, rdi
0x18004695f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046964  mov     rbx, rax
0x180046967  call    cs:__imp_GetLastError
0x18004696d  mov     r9, rbx
0x180046970  lea     r8, aFailedToInterr_1; "Failed to interrogate the ClusDisk driv"...
0x180046977  mov     edx, eax; int
0x180046979  lea     rcx, [rsp+1E28h+var_1588]; this
0x180046981  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046986  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x18004698d  lea     rcx, [rsp+1E28h+var_1588]; pExceptionObject
0x180046995  call    _CxxThrowException_0
0x18004699a  cmp     [rsp+1E28h+ServiceStatus.dwCurrentState], ebx
0x1800469a1  jz      short loc_1800469DB
0x1800469a3  mov     rcx, rdi
0x1800469a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800469ab  mov     r9, rax
0x1800469ae  lea     r8, aTheClusdiskDri; "The ClusDisk driver has not been starte"...
0x1800469b5  mov     edx, 426h; int
0x1800469ba  lea     rcx, [rsp+1E28h+var_1478]; this
0x1800469c2  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x1800469c7  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x1800469ce  lea     rcx, [rsp+1E28h+var_1478]; pExceptionObject
0x1800469d6  call    _CxxThrowException_0
0x1800469db  mov     ebx, 1
0x1800469e0  mov     r8d, ebx; enum _CLUSTER_SETUP_PHASE_SEVERITY
0x1800469e3  xor     edx, edx; unsigned int
0x1800469e5  mov     rcx, [rsi+8]; this
0x1800469e9  call    ?EndPhase@PhaseManager@@QEAAXKW4_CLUSTER_SETUP_PHASE_SEVERITY@@@Z; PhaseManager::EndPhase(ulong,_CLUSTER_SETUP_PHASE_SEVERITY)
0x1800469ee  mov     rcx, rdi
0x1800469f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800469f6  mov     r8, rax
0x1800469f9  lea     edx, [rbx+67h]
0x1800469fc  mov     rcx, [rsi+8]
0x180046a00  call    ?StartPhase@PhaseManager@@QEAAXW4_CLUSTER_SETUP_PHASE@@PEB_WW4Enum@CancelAllowed@@@Z; PhaseManager::StartPhase(_CLUSTER_SETUP_PHASE,wchar_t const *,CancelAllowed::Enum)
0x180046a05  mov     [rsp+1E28h+lpDisplayName], r14; lpDisplayName
0x180046a0a  mov     [rsp+1E28h+lpPassword], r14; lpPassword
0x180046a0f  mov     [rsp+1E28h+lpServiceStartName], r14; lpServiceStartName
0x180046a14  mov     [rsp+1E28h+lpDependencies], r14; lpDependencies
0x180046a19  mov     [rsp+1E28h+lpdwTagId], r14; lpdwTagId
0x180046a1e  mov     [rsp+1E28h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x180046a23  mov     [rsp+1E28h+lpBinaryPathName], r14; lpBinaryPathName
0x180046a28  or      edx, 0FFFFFFFFh; dwServiceType
0x180046a2b  mov     r9d, edx; dwErrorControl
0x180046a2e  lea     r8d, [rbx+1]; dwStartType
0x180046a32  mov     rcx, [rsi+80h]; hService
0x180046a39  call    cs:__imp_ChangeServiceConfigW
0x180046a3f  test    eax, eax
0x180046a41  jnz     short loc_180046A81
0x180046a43  mov     rcx, rdi
0x180046a46  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046a4b  mov     rbx, rax
0x180046a4e  call    cs:__imp_GetLastError
0x180046a54  mov     r9, rbx
0x180046a57  lea     r8, aFailedToEnable; "Failed to enable the ClusSvc service en"...
0x180046a5e  mov     edx, eax; int
0x180046a60  lea     rcx, [rsp+1E28h+var_1368]; this
0x180046a68  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046a6d  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180046a74  lea     rcx, [rsp+1E28h+var_1368]; pExceptionObject
0x180046a7c  call    _CxxThrowException_0
0x180046a81  mov     [rsp+1E28h+Info], ebx
0x180046a88  lea     r8, [rsp+1E28h+Info]; lpInfo
0x180046a90  mov     edx, 5; dwInfoLevel
0x180046a95  mov     rcx, [rsi+80h]; hService
0x180046a9c  call    cs:__imp_ChangeServiceConfig2W
0x180046aa2  mov     rcx, rdi
0x180046aa5  test    eax, eax
0x180046aa7  jnz     short loc_180046AE4
0x180046aa9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046aae  mov     rbx, rax
0x180046ab1  call    cs:__imp_GetLastError
0x180046ab7  mov     r9, rbx
0x180046aba  lea     r8, aFailedToSetClu; "Failed to set ClusSvc service SID Type "...
0x180046ac1  mov     edx, eax; int
0x180046ac3  lea     rcx, [rsp+1E28h+var_1258]; this
0x180046acb  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046ad0  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180046ad7  lea     rcx, [rsp+1E28h+var_1258]; pExceptionObject
0x180046adf  call    _CxxThrowException_0
0x180046ae4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046ae9  mov     rcx, rax
0x180046aec  call    ClRtlSetSCMFailureActions
0x180046af1  mov     ebx, eax
0x180046af3  test    eax, eax
0x180046af5  jz      short loc_180046B2C
0x180046af7  mov     rcx, rdi
0x180046afa  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046aff  mov     r9, rax
0x180046b02  lea     r8, aFailedToSetScm; "Failed to set SCM failure actions on %w"...
0x180046b09  mov     edx, ebx; int
0x180046b0b  lea     rcx, [rsp+1E28h+var_1148]; this
0x180046b13  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046b18  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180046b1f  lea     rcx, [rsp+1E28h+var_1148]; pExceptionObject
0x180046b27  call    _CxxThrowException_0
0x180046b2c  lea     rcx, [rsp+1E28h+hKey]; TokenHandle
0x180046b34  call    ??0CRevertToken@@QEAA@XZ; CRevertToken::CRevertToken(void)
0x180046b39  nop
0x180046b3a  lea     r8, [rsi+98h]; pNotifyBuffer
0x180046b41  mov     dword ptr [r8], 2
0x180046b48  lea     rax, ?SCMStateChangeNotify@@YAXPEAX@Z; SCMStateChangeNotify(void *)
0x180046b4f  mov     [rsi+0A0h], rax
0x180046b56  mov     [rsi+0A8h], rsi
0x180046b5d  mov     edx, 0Eh; dwNotifyMask
0x180046b62  mov     rcx, [rsi+80h]; hService
0x180046b69  call    cs:__imp_NotifyServiceStatusChangeW
0x180046b6f  mov     ebx, eax
0x180046b71  test    eax, eax
0x180046b73  jz      short loc_180046BAB
0x180046b75  mov     rcx, rdi
0x180046b78  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046b7d  mov     r9, rax
0x180046b80  lea     r8, aFailedToSetSta; "Failed to set state change notify for n"...
0x180046b87  mov     edx, ebx; int
0x180046b89  lea     rcx, [rsp+1E28h+var_1038]; this
0x180046b91  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180046b96  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
  ... truncated ...
```
