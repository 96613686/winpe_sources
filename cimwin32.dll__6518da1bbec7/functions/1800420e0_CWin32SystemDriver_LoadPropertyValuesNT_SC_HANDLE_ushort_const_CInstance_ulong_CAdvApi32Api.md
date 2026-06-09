# CWin32SystemDriver::LoadPropertyValuesNT(SC_HANDLE__ *,ushort const *,CInstance *,ulong,CAdvApi32Api *)

- ea: `0x1800420e0`
- end: `0x180042b0c`
- name: `?LoadPropertyValuesNT@CWin32SystemDriver@@AEAAJPEAUSC_HANDLE__@@PEBGPEAVCInstance@@KPEAVCAdvApi32Api@@@Z`
- size: `2604`
- prototype: `int(CWin32SystemDriver *__hidden this, struct SC_HANDLE__ *, const unsigned __int16 *, struct CInstance *, unsigned int, struct CAdvApi32Api *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180041e84`

## callees

- `0x1800420e0`
- `0x18006cf9c`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042734`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004282a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042962`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042734`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18004282a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180042962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042932`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042932`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800421a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800421a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800428f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800429df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800428f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800429df`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180042715`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004280b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180042943`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180042715`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18004280b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180042943`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800426f5`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800427eb`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800426f5`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x1800427eb`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18004216e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800428c5`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800429af`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18004216e`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800428c5`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800429af`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800421ef`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004243c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180042451`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180042553`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800421ef`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18004243c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180042451`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180042553`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180042928`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180042a06`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180042928`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180042a06`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800423f1`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18004240b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180042427`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180042650`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800423f1`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18004240b`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180042427`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180042650`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180042726`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18004281c`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180042954`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180042726`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18004281c`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180042954`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180042744`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x18004283a`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180042972`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180042744`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x18004283a`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180042972`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180042794`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18004288a`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x180042794`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18004288a`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x18004275a`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x180042850`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x18004275a`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x180042850`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x1800426e4`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x1800427da`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x1800426e4`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x1800427da`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180042984`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180042992`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x1800429a4`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180042984`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180042992`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x1800429a4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180042386`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800423d7`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004246f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800424cc`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004258e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800425a3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800425cb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180042634`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800426ab`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180042386`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800423d7`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004246f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800424cc`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18004258e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800425a3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800425cb`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180042634`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800426ab`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180042165`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180042165`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800426cd`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x1800426cd`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180042785`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x18004287b`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180042785`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x18004287b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004212e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042145`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004215c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042181`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800424e7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800424fa`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004250d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042a43`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042a6b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042a7f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042aa0`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042ab7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042ace`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004212e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042145`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004215c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042181`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800424e7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800424fa`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18004250d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042a43`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042a6b`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042a7f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042aa0`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042ab7`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180042ace`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x180042773`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x180042869`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x180042773`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x180042869`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004229c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180042702`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427a0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427ac`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427b8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427c4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427f8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180042896`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800428a2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800428ae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800428ba`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004290e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180042a1c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004229c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180042702`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427a0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427ac`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427b8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427c4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800427f8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180042896`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800428a2`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800428ae`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800428ba`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18004290e`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180042a1c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042193`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042193`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004223c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042270`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004223c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042270`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004233a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004233a`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18004249f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18004249f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800421d6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180042536`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800421d6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180042536`

## string_xrefs

- `0x180042447`: `ServiceSpecificExitCode`
- `0x18004256d`: `ServiceType`
- `0x1800425c4`: `ServiceType`
- `0x180042a99`: `ServiceType`
- `0x1800426eb`: `System32\`
- `0x1800427e1`: `\SystemRoot\System32\`
- `0x18004291e`: `PathName`
- `0x1800429fc`: `PathName`
- `0x18004214b`: `Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWin32SystemDriver::LoadPropertyValuesNT(
        CWin32SystemDriver *this,
        SC_HANDLE a2,
        const unsigned __int16 *a3,
        struct CInstance *a4,
        unsigned int a5,
        struct CAdvApi32Api *a6)
{
  const struct CHString *LocalComputerName; // rax
  const unsigned __int16 *v11; // rax
  SC_HANDLE v12; // rbx
  DWORD LastError; // r13d
  enum _SC_STATUS_TYPE v14; // r8d
  unsigned int v15; // r14d
  unsigned int v16; // edi
  bool v18; // al
  int v19; // edx
  int v20; // ecx
  BOOL v21; // eax
  bool v22; // al
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // r8
  CInstance *v25; // rcx
  const unsigned __int16 *v26; // r8
  CInstance *v27; // rcx
  const unsigned __int16 *v28; // r8
  CInstance *v29; // rcx
  const unsigned __int16 *v30; // r8
  CHString *v31; // rax
  int v32; // edi
  WCHAR *Buffer; // rax
  __int64 v34; // rdi
  __int64 v35; // rax
  __int64 v36; // rax
  CHString *v37; // rax
  int v38; // edi
  WCHAR *v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rax
  __int64 v42; // rax
  const WCHAR *v43; // rax
  HANDLE FileW; // rdi
  WCHAR *v45; // rax
  const WCHAR *v46; // rax
  const unsigned __int16 *lpServiceStartName; // r8
  const unsigned __int16 *lpDisplayName; // r8
  const unsigned __int16 *v49; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  bool v51; // [rsp+40h] [rbp-C0h]
  int v52; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v53; // [rsp+50h] [rbp-B0h] BYREF
  int v54; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v55; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v57[8]; // [rsp+70h] [rbp-90h] BYREF
  SC_HANDLE v58; // [rsp+78h] [rbp-88h]
  _BYTE ServiceStatus[32]; // [rsp+80h] [rbp-80h] BYREF
  int v60; // [rsp+A0h] [rbp-60h]
  struct _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+B0h] [rbp-50h] BYREF

  pcbBytesNeeded = 0;
  CInstance::SetCHString(a4, L"Name", a3);
  CInstance::SetCHString(a4, L"CreationClassName", L"Win32_SystemDriver");
  CInstance::SetCHString(a4, L"SystemCreationClassName", L"Win32_ComputerSystem");
  LocalComputerName = Provider::GetLocalComputerName(this);
  v11 = (const unsigned __int16 *)CHString::operator unsigned short const *(LocalComputerName);
  CInstance::SetCHString(a4, L"SystemName", v11);
  v12 = OpenServiceW(a2, a3, 0x85u);
  v58 = v12;
  LastError = GetLastError();
  if ( !v12 && (LastError == 1060 || LastError == 123) )
    return 2147749890LL;
  memset_0(&ServiceConfig, 0, 0x400u);
  if ( QueryServiceConfigW(v12, &ServiceConfig, 0x400u, &pcbBytesNeeded) )
  {
    CInstance::SetDWORD(a4, L"TagId", ServiceConfig.dwTagId);
    if ( (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 0x20 || (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 0x10 )
    {
LABEL_11:
      if ( !v12 )
        return 2147749890LL;
LABEL_12:
      CloseServiceHandle(v12);
      return 2147749890LL;
    }
  }
  v15 = 0;
  v16 = a5 & 0x1FF800;
  if ( (a5 & 0x4DE) != 0 )
  {
    v52 = 0;
    if ( !a6 )
      goto LABEL_24;
    memset(ServiceStatus, 0, sizeof(ServiceStatus));
    v60 = 0;
    v53 = 0;
    v18 = CAdvApi32Api::QueryServiceStatusEx(a6, v12, v14, ServiceStatus, dwCreationDisposition, &v53, &v52);
    v19 = v52;
    if ( v18 && v52 == 1 )
      goto LABEL_22;
    v20 = 0;
    v54 = 0;
    v53 = 0;
    v52 = 0;
    if ( !v19 )
    {
LABEL_24:
      memset(ServiceStatus, 0, 28);
      v21 = QueryServiceStatus(v12, (LPSERVICE_STATUS)ServiceStatus);
      if ( v21 )
      {
LABEL_22:
        v20 = *(_DWORD *)&ServiceStatus[4];
        v53 = *(_DWORD *)&ServiceStatus[12];
        v54 = *(_DWORD *)&ServiceStatus[8];
        v52 = *(_DWORD *)&ServiceStatus[16];
        goto LABEL_27;
      }
      if ( !v21 )
      {
        v51 = 0;
        CInstance::SetCharSplat(a4, L"State", L"Unknown");
        goto LABEL_39;
      }
      v20 = 0;
      v53 = 0;
      v52 = 0;
      v54 = 0;
    }
LABEL_27:
    switch ( v20 )
    {
      case 1:
        CInstance::SetCharSplat(a4, L"State", L"Stopped");
        v22 = 0;
        goto LABEL_37;
      case 2:
        v23 = L"Start Pending";
        goto LABEL_36;
      case 3:
        v23 = L"Stop Pending";
        goto LABEL_36;
      case 4:
        v23 = L"Running";
        goto LABEL_36;
      case 5:
        v23 = L"Continue Pending";
        goto LABEL_36;
      case 6:
        v23 = L"Pause Pending";
        goto LABEL_36;
      case 7:
        v23 = L"Paused";
        goto LABEL_36;
      default:
        v23 = L"Unknown";
LABEL_36:
        CInstance::SetCharSplat(a4, L"State", v23);
        v22 = 1;
LABEL_37:
        v51 = v22;
        CInstance::Setbool(a4, L"Started", v22);
        CInstance::Setbool(a4, L"AcceptStop", v54 & 1);
        CInstance::Setbool(a4, L"AcceptPause", (v54 & 2) != 0);
        CInstance::SetDWORD(a4, L"ExitCode", v53);
        CInstance::SetDWORD(a4, L"ServiceSpecificExitCode", v52);
        break;
    }
LABEL_39:
    if ( (a5 & 0x400) != 0 )
    {
      if ( v12 )
      {
        memset(ServiceStatus, 0, 28);
        if ( !v51 || ControlService(v12, 4u, (LPSERVICE_STATUS)ServiceStatus) )
          v24 = L"OK";
        else
          v24 = L"Degraded";
      }
      else
      {
        v24 = L"Unknown";
      }
      CInstance::SetCharSplat(a4, L"Status", v24);
    }
    if ( !v16 )
      goto LABEL_7;
    goto LABEL_48;
  }
  if ( !v16 )
    goto LABEL_7;
LABEL_48:
  CInstance::SetCHString(a4, L"Caption", a3);
  CInstance::SetCHString(a4, L"DisplayName", a3);
  CInstance::SetCHString(a4, L"Description", a3);
  memset_0(&ServiceConfig, 0, 0x400u);
  if ( !QueryServiceConfigW(v12, &ServiceConfig, 0x400u, &pcbBytesNeeded) )
  {
    CInstance::SetCHString(a4, L"ServiceType", L"Unknown");
    CInstance::SetCHString(a4, L"StartMode", L"Unknown");
    lpDisplayName = L"Unknown";
    v49 = L"ErrorControl";
    goto LABEL_99;
  }
  CInstance::SetDWORD(a4, L"TagId", ServiceConfig.dwTagId);
  if ( (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 1 )
  {
    v26 = L"Kernel Driver";
    goto LABEL_58;
  }
  if ( (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 2 )
  {
    v26 = L"File System Driver";
LABEL_58:
    v25 = a4;
    goto LABEL_59;
  }
  v25 = a4;
  if ( (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 0x10 )
  {
    CInstance::SetCharSplat(a4, L"ServiceType", L"Own Process");
    v15 = -2147217406;
    goto LABEL_60;
  }
  if ( (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 0x20 )
  {
    CInstance::SetCharSplat(a4, L"ServiceType", L"Share Process");
    v15 = -2147217406;
    goto LABEL_60;
  }
  v26 = L"Unknown";
LABEL_59:
  CInstance::SetCharSplat(v25, L"ServiceType", v26);
LABEL_60:
  switch ( ServiceConfig.dwStartType )
  {
    case 0u:
      v28 = L"Boot";
      goto LABEL_71;
    case 1u:
      v28 = L"System";
      goto LABEL_71;
    case 2u:
      v28 = L"Auto";
      goto LABEL_71;
    case 3u:
      v28 = L"Manual";
LABEL_71:
      v27 = a4;
      goto LABEL_72;
  }
  v27 = a4;
  if ( ServiceConfig.dwStartType == 4 )
    v28 = L"Disabled";
  else
    v28 = L"Unknown";
LABEL_72:
  CInstance::SetCharSplat(v27, L"StartMode", v28);
  CInstance::Setbool(a4, L"DesktopInteract", ServiceConfig.dwServiceType & 0x100);
  if ( ServiceConfig.dwErrorControl )
  {
    if ( ServiceConfig.dwErrorControl == 1 )
    {
      v30 = L"Normal";
    }
    else
    {
      if ( ServiceConfig.dwErrorControl != 2 )
      {
        v29 = a4;
        if ( ServiceConfig.dwErrorControl == 3 )
          v30 = L"Critical";
        else
          v30 = L"Unknown";
        goto LABEL_82;
      }
      v30 = L"Severe";
    }
  }
  else
  {
    v30 = L"Ignore";
  }
  v29 = a4;
LABEL_82:
  CInstance::SetCharSplat(v29, L"ErrorControl", v30);
  if ( ServiceConfig.lpBinaryPathName && *ServiceConfig.lpBinaryPathName )
  {
    CHString::CHString((CHString *)&v52, ServiceConfig.lpBinaryPathName);
    v31 = (CHString *)CHString::Left(&v52, &v53, 9);
    v32 = CHString::CompareNoCase(v31, L"System32\\");
    CHString::~CHString((CHString *)&v53);
    if ( !v32 )
    {
      CHString::CHString((CHString *)&v53);
      Buffer = CHString::GetBuffer((CHString *)&v53, 260);
      GetSystemDirectoryW(Buffer, 0x104u);
      CHString::ReleaseBuffer((CHString *)&v53, -1);
      v34 = CHString::Mid(&v52, &v55, 9);
      v35 = operator+(v57, &v53, 92);
      v36 = operator+(&v54, v35, v34);
      CHString::operator=(&v52, v36);
      CHString::~CHString((CHString *)&v54);
      CHString::~CHString((CHString *)v57);
      CHString::~CHString((CHString *)&v55);
      CHString::~CHString((CHString *)&v53);
    }
    v37 = (CHString *)CHString::Left(&v52, &v55, 21);
    v38 = CHString::CompareNoCase(v37, L"\\SystemRoot\\System32\\");
    CHString::~CHString((CHString *)&v55);
    if ( !v38 )
    {
      CHString::CHString((CHString *)&v53);
      v39 = CHString::GetBuffer((CHString *)&v53, 260);
      GetSystemDirectoryW(v39, 0x104u);
      CHString::ReleaseBuffer((CHString *)&v53, -1);
      v40 = CHString::Mid(&v52, &v54, 21);
      v41 = operator+(v57, &v53, 92);
      v42 = operator+(&v55, v41, v40);
      CHString::operator=(&v52, v42);
      CHString::~CHString((CHString *)&v55);
      CHString::~CHString((CHString *)v57);
      CHString::~CHString((CHString *)&v54);
      CHString::~CHString((CHString *)&v53);
    }
    v43 = (const WCHAR *)CHString::operator unsigned short const *(&v52);
    FileW = CreateFileW(v43, 0x80000000, 3u, 0, 3u, 0, 0);
    v55 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      CHString::~CHString((CHString *)&v52);
      goto LABEL_11;
    }
  }
  else
  {
    CHString::CHString((CHString *)&v52);
    v45 = CHString::GetBuffer((CHString *)&v52, 260);
    GetSystemDirectoryW(v45, 0x104u);
    CHString::ReleaseBuffer((CHString *)&v52, -1);
    CHString::operator+=(&v52, L"\\drivers\\");
    CHString::operator+=(&v52, a3);
    CHString::operator+=(&v52, L".sys");
    v46 = (const WCHAR *)CHString::operator unsigned short const *(&v52);
    FileW = CreateFileW(v46, 0x80000000, 3u, 0, 3u, 0, 0);
    v55 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      CHString::~CHString((CHString *)&v52);
      if ( !v12 )
        return 2147749890LL;
      goto LABEL_12;
    }
  }
  CInstance::SetCHString(a4, L"PathName", (const struct CHString *)&v52);
  CloseHandle(FileW);
  CHString::~CHString((CHString *)&v52);
  lpServiceStartName = ServiceConfig.lpServiceStartName;
  if ( !ServiceConfig.lpServiceStartName || !*ServiceConfig.lpServiceStartName )
    lpServiceStartName = (const unsigned __int16 *)&Data;
  CInstance::SetCHString(a4, L"StartName", lpServiceStartName);
  if ( !ServiceConfig.lpDisplayName || !*ServiceConfig.lpDisplayName )
    goto LABEL_7;
  CInstance::SetCHString(a4, L"DisplayName", ServiceConfig.lpDisplayName);
  CInstance::SetCHString(a4, L"Caption", ServiceConfig.lpDisplayName);
  lpDisplayName = ServiceConfig.lpDisplayName;
  v49 = L"Description";
LABEL_99:
  CInstance::SetCHString(a4, v49, lpDisplayName);
LABEL_7:
  if ( !v12 )
  {
    v15 = 0;
    if ( LastError == 5 )
      v15 = -2147217405;
  }
  if ( v12 )
    CloseServiceHandle(v12);
  return v15;
}

```

## disassembly

```asm
0x1800420e0  push    rbp
0x1800420e2  push    rbx
0x1800420e3  push    rsi
0x1800420e4  push    rdi
0x1800420e5  push    r12
0x1800420e7  push    r13
0x1800420e9  push    r14
0x1800420eb  push    r15
0x1800420ed  lea     rbp, [rsp-3C8h]
0x1800420f5  sub     rsp, 4C8h
0x1800420fc  mov     rax, cs:__security_cookie
0x180042103  xor     rax, rsp
0x180042106  mov     [rbp+400h+var_50], rax
0x18004210d  mov     r15, r9
0x180042110  mov     r12, r8
0x180042113  mov     rdi, rdx
0x180042116  mov     rbx, rcx
0x180042119  xor     esi, esi
0x18004211b  mov     [rsp+500h+pcbBytesNeeded], esi
0x18004211f  mov     [rsp+500h+var_488], rsi
0x180042124  lea     rdx, aName; "Name"
0x18004212b  mov     rcx, r9
0x18004212e  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180042134  lea     r8, aWin32Systemdri; "Win32_SystemDriver"
0x18004213b  lea     rdx, aCreationclassn; "CreationClassName"
0x180042142  mov     rcx, r15
0x180042145  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x18004214b  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180042152  lea     rdx, aSystemcreation; "SystemCreationClassName"
0x180042159  mov     rcx, r15
0x18004215c  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180042162  mov     rcx, rbx
0x180042165  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x18004216b  mov     rcx, rax
0x18004216e  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180042174  mov     r8, rax
0x180042177  lea     rdx, aSystemname; "SystemName"
0x18004217e  mov     rcx, r15
0x180042181  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180042187  mov     r8d, 85h; dwDesiredAccess
0x18004218d  mov     rdx, r12; lpServiceName
0x180042190  mov     rcx, rdi; hSCManager
0x180042193  call    cs:__imp_OpenServiceW
0x180042199  mov     rbx, rax
0x18004219c  mov     [rsp+500h+var_488], rax
0x1800421a1  call    cs:__imp_GetLastError
0x1800421a7  mov     r13d, eax
0x1800421aa  test    rbx, rbx
0x1800421ad  jz      loc_18004227D
0x1800421b3  xor     edx, edx; Val
0x1800421b5  mov     r8d, 400h; Size
0x1800421bb  lea     rcx, [rbp+400h+ServiceConfig]; void *
0x1800421bf  call    memset_0
0x1800421c4  lea     r9, [rsp+500h+pcbBytesNeeded]; pcbBytesNeeded
0x1800421c9  mov     r8d, 400h; cbBufSize
0x1800421cf  lea     rdx, [rbp+400h+ServiceConfig]; lpServiceConfig
0x1800421d3  mov     rcx, rbx; hService
0x1800421d6  call    cs:__imp_QueryServiceConfigW
0x1800421dc  cmp     eax, 1
0x1800421df  jnz     short loc_180042206
0x1800421e1  mov     r8d, [rbp+400h+ServiceConfig.dwTagId]
0x1800421e5  lea     rdx, aTagid; "TagId"
0x1800421ec  mov     rcx, r15
0x1800421ef  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800421f5  mov     eax, [rbp+400h+ServiceConfig.dwServiceType]
0x1800421f8  btr     eax, 8
0x1800421fc  cmp     eax, 20h ; ' '
0x1800421ff  jz      short loc_180042268
0x180042201  cmp     eax, 10h
0x180042204  jz      short loc_180042268
0x180042206  mov     r14d, esi
0x180042209  mov     esi, [rbp+400h+arg_20]
0x18004220f  mov     edi, esi
0x180042211  and     edi, 1FF800h
0x180042217  test    esi, 4DEh
0x18004221d  jnz     loc_1800422AA
0x180042223  test    edi, edi
0x180042225  jnz     loc_1800424DA
0x18004222b  test    rbx, rbx
0x18004222e  jz      loc_180042AD9
0x180042234  test    rbx, rbx
0x180042237  jz      short loc_180042242
0x180042239  mov     rcx, rbx; hSCObject
0x18004223c  call    cs:__imp_CloseServiceHandle
0x180042242  mov     eax, r14d
0x180042245  mov     rcx, [rbp+400h+var_50]
0x18004224c  xor     rcx, rsp; StackCookie
0x18004224f  call    __security_check_cookie
0x180042254  add     rsp, 4C8h
0x18004225b  pop     r15
0x18004225d  pop     r14
0x18004225f  pop     r13
0x180042261  pop     r12
0x180042263  pop     rdi
0x180042264  pop     rsi
0x180042265  pop     rbx
0x180042266  pop     rbp
0x180042267  retn
0x180042268  test    rbx, rbx
0x18004226b  jz      short loc_180042276
0x18004226d  mov     rcx, rbx; hSCObject
0x180042270  call    cs:__imp_CloseServiceHandle
0x180042276  mov     eax, 80041002h
0x18004227b  jmp     short loc_180042245
0x18004227d  cmp     r13d, 424h
0x180042284  jz      short loc_180042290
0x180042286  cmp     r13d, 7Bh ; '{'
0x18004228a  jnz     loc_1800421B3
0x180042290  mov     eax, 80041002h
0x180042295  jmp     short loc_180042245
0x180042297  lea     rcx, [rsp+500h+var_4B8]
0x18004229c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800422a2  nop
0x1800422a3  test    rbx, rbx
0x1800422a6  jz      short loc_180042276
0x1800422a8  jmp     short loc_18004226D
0x1800422aa  mov     [rsp+500h+var_4B8], r14d
0x1800422af  mov     rcx, [rbp+400h+arg_28]; this
0x1800422b6  test    rcx, rcx
0x1800422b9  jz      short loc_180042328
0x1800422bb  xorps   xmm0, xmm0
0x1800422be  xor     eax, eax
0x1800422c0  movups  xmmword ptr [rbp+400h+ServiceStatus], xmm0
0x1800422c4  movups  xmmword ptr [rbp+400h+ServiceStatus+10h], xmm0
0x1800422c8  mov     [rbp+400h+var_460], eax
0x1800422cb  mov     [rsp+500h+var_4B0], eax
0x1800422cf  lea     rax, [rsp+500h+var_4B8]
0x1800422d4  mov     [rsp+500h+hTemplateFile], rax; int *
0x1800422d9  lea     rax, [rsp+500h+var_4B0]
0x1800422de  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], rax; unsigned int *
0x1800422e3  lea     r9, [rbp+400h+ServiceStatus]; unsigned __int8 *
0x1800422e7  mov     rdx, rbx; struct SC_HANDLE__ *
0x1800422ea  call    ?QueryServiceStatusEx@CAdvApi32Api@@QEAA_NPEAUSC_HANDLE__@@W4_SC_STATUS_TYPE@@PEAEKPEAKPEAH@Z; CAdvApi32Api::QueryServiceStatusEx(SC_HANDLE__ *,_SC_STATUS_TYPE,uchar *,ulong,ulong *,int *)
0x1800422ef  mov     edx, [rsp+500h+var_4B8]
0x1800422f3  test    al, al
0x1800422f5  jz      short loc_180042316
0x1800422f7  cmp     edx, 1
0x1800422fa  jnz     short loc_180042316
0x1800422fc  mov     ecx, dword ptr [rbp+400h+ServiceStatus+4]
0x1800422ff  mov     eax, dword ptr [rbp+400h+ServiceStatus+8]
0x180042302  mov     [rsp+500h+var_4A8], eax
0x180042306  mov     eax, dword ptr [rbp+400h+ServiceStatus+0Ch]
0x180042309  mov     [rsp+500h+var_4B0], eax
0x18004230d  mov     eax, dword ptr [rbp+400h+ServiceStatus+10h]
0x180042310  mov     [rsp+500h+var_4B8], eax
0x180042314  jmp     short loc_18004235B
0x180042316  xor     ecx, ecx
0x180042318  mov     [rsp+500h+var_4A8], ecx
0x18004231c  mov     [rsp+500h+var_4B0], ecx
0x180042320  mov     [rsp+500h+var_4B8], ecx
0x180042324  test    edx, edx
0x180042326  jnz     short loc_18004235B
0x180042328  xorps   xmm0, xmm0
0x18004232b  movups  xmmword ptr [rbp+400h+ServiceStatus], xmm0
0x18004232f  movups  xmmword ptr [rbp+400h+ServiceStatus+0Ch], xmm0
0x180042333  lea     rdx, [rbp+400h+ServiceStatus]; lpServiceStatus
0x180042337  mov     rcx, rbx; hService
0x18004233a  call    cs:__imp_QueryServiceStatus
0x180042340  cmp     eax, 1
0x180042343  jz      short loc_1800422FC
0x180042345  test    eax, eax
0x180042347  jz      loc_180042459
0x18004234d  xor     ecx, ecx
0x18004234f  mov     [rsp+500h+var_4B0], ecx
0x180042353  mov     [rsp+500h+var_4B8], ecx
0x180042357  mov     [rsp+500h+var_4A8], ecx
0x18004235b  dec     ecx; switch 7 cases
0x18004235d  cmp     ecx, 6
0x180042360  ja      short def_180042373; jumptable 0000000180042373 default case
0x180042362  lea     rdx, __ImageBase
0x180042369  mov     eax, ds:(jpt_180042373 - 180000000h)[rdx+rcx*4]
0x180042370  add     rax, rdx
0x180042373  jmp     rax; switch jump
0x180042375  lea     r8, aStopped; jumptable 0000000180042373 case 1
0x18004237c  lea     rdx, aState; "State"
0x180042383  mov     rcx, r15
0x180042386  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18004238c  xor     al, al
0x18004238e  jmp     short loc_1800423DF
0x180042390  lea     r8, aStartPending; jumptable 0000000180042373 case 2
0x180042397  jmp     short loc_1800423CD
0x180042399  lea     r8, aStopPending; jumptable 0000000180042373 case 3
0x1800423a0  jmp     short loc_1800423CD
0x1800423a2  lea     r8, aRunning; jumptable 0000000180042373 case 4
0x1800423a9  jmp     short loc_1800423CD
0x1800423ab  lea     r8, aContinuePendin; jumptable 0000000180042373 case 5
0x1800423b2  jmp     short loc_1800423CD
0x1800423b4  lea     r8, aPausePending; jumptable 0000000180042373 case 6
0x1800423bb  jmp     short loc_1800423CD
0x1800423bd  lea     r8, aPaused; jumptable 0000000180042373 case 7
0x1800423c4  jmp     short loc_1800423CD
0x1800423c6  lea     r8, aUnknown_0; jumptable 0000000180042373 default case
0x1800423cd  lea     rdx, aState; "State"
0x1800423d4  mov     rcx, r15
0x1800423d7  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800423dd  mov     al, 1
0x1800423df  mov     [rsp+500h+var_4C0], al
0x1800423e3  movzx   r8d, al
0x1800423e7  lea     rdx, aStarted; "Started"
0x1800423ee  mov     rcx, r15
0x1800423f1  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800423f7  movzx   r8d, byte ptr [rsp+500h+var_4A8]
0x1800423fd  and     r8b, 1
0x180042401  lea     rdx, aAcceptstop; "AcceptStop"
0x180042408  mov     rcx, r15
0x18004240b  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180042411  mov     r8d, [rsp+500h+var_4A8]
0x180042416  shr     r8d, 1
0x180042419  and     r8b, 1
0x18004241d  lea     rdx, aAcceptpause; "AcceptPause"
0x180042424  mov     rcx, r15
0x180042427  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18004242d  mov     r8d, [rsp+500h+var_4B0]
0x180042432  lea     rdx, aExitcode; "ExitCode"
0x180042439  mov     rcx, r15
0x18004243c  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180042442  mov     r8d, [rsp+500h+var_4B8]
0x180042447  lea     rdx, aServicespecifi; "ServiceSpecificExitCode"
0x18004244e  mov     rcx, r15
0x180042451  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180042457  jmp     short loc_180042475
0x180042459  mov     [rsp+500h+var_4C0], r14b
0x18004245e  lea     r8, aUnknown_0; "Unknown"
0x180042465  lea     rdx, aState; "State"
0x18004246c  mov     rcx, r15
0x18004246f  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180042475  bt      esi, 0Ah
0x180042479  jnb     short loc_1800424D2
0x18004247b  test    rbx, rbx
0x18004247e  jz      short loc_1800424BB
0x180042480  xorps   xmm0, xmm0
0x180042483  xor     eax, eax
0x180042485  movups  xmmword ptr [rbp+400h+ServiceStatus], xmm0
0x180042489  movups  xmmword ptr [rbp+400h+ServiceStatus+0Ch], xmm0
0x18004248d  cmp     [rsp+500h+var_4C0], al
0x180042491  jz      short loc_1800424B2
0x180042493  lea     r8, [rbp+400h+ServiceStatus]; lpServiceStatus
0x180042497  mov     edx, 4; dwControl
0x18004249c  mov     rcx, rbx; hService
0x18004249f  call    cs:__imp_ControlService
0x1800424a5  test    eax, eax
0x1800424a7  jnz     short loc_1800424B2
0x1800424a9  lea     r8, aDegraded; "Degraded"
0x1800424b0  jmp     short loc_1800424C2
0x1800424b2  lea     r8, aOk; "OK"
0x1800424b9  jmp     short loc_1800424C2
0x1800424bb  lea     r8, aUnknown_0; "Unknown"
0x1800424c2  lea     rdx, aStatus; "Status"
0x1800424c9  mov     rcx, r15
0x1800424cc  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800424d2  test    edi, edi
0x1800424d4  jz      loc_18004222B
0x1800424da  mov     r8, r12
0x1800424dd  lea     rdx, aCaption; "Caption"
0x1800424e4  mov     rcx, r15
0x1800424e7  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x1800424ed  mov     r8, r12
0x1800424f0  lea     rdx, aDisplayname; "DisplayName"
0x1800424f7  mov     rcx, r15
0x1800424fa  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180042500  mov     r8, r12
0x180042503  lea     rdx, aDescription; "Description"
0x18004250a  mov     rcx, r15
0x18004250d  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180042513  xor     edx, edx; Val
0x180042515  mov     r8d, 400h; Size
0x18004251b  lea     rcx, [rbp+400h+ServiceConfig]; void *
0x18004251f  call    memset_0
0x180042524  lea     r9, [rsp+500h+pcbBytesNeeded]; pcbBytesNeeded
0x180042529  mov     r8d, 400h; cbBufSize
0x18004252f  lea     rdx, [rbp+400h+ServiceConfig]; lpServiceConfig
0x180042533  mov     rcx, rbx; hService
0x180042536  call    cs:__imp_QueryServiceConfigW
0x18004253c  mov     rcx, r15
0x18004253f  cmp     eax, 1
0x180042542  jnz     loc_180042A92
0x180042548  mov     r8d, [rbp+400h+ServiceConfig.dwTagId]
0x18004254c  lea     rdx, aTagid; "TagId"
0x180042553  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180042559  mov     eax, [rbp+400h+ServiceConfig.dwServiceType]
0x18004255c  btr     eax, 8
0x180042560  sub     eax, 1
0x180042563  jz      short loc_1800425BA
0x180042565  sub     eax, 1
0x180042568  jz      short loc_1800425B1
0x18004256a  sub     eax, 0Eh
0x18004256d  lea     rdx, aServicetype; "ServiceType"
0x180042574  mov     rcx, r15
0x180042577  jz      short loc_18004259C
0x180042579  cmp     eax, 10h
0x18004257c  jz      short loc_180042587
0x18004257e  lea     r8, aUnknown_0; "Unknown"
0x180042585  jmp     short loc_1800425CB
0x180042587  lea     r8, aShareProcess; "Share Process"
0x18004258e  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180042594  mov     r14d, 80041002h
0x18004259a  jmp     short loc_1800425D1
0x18004259c  lea     r8, aOwnProcess; "Own Process"
0x1800425a3  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800425a9  mov     r14d, 80041002h
  ... truncated ...
```
