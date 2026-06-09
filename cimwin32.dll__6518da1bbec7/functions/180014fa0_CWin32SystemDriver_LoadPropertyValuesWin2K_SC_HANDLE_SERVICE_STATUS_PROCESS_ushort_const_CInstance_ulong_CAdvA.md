# CWin32SystemDriver::LoadPropertyValuesWin2K(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS &,ushort const *,CInstance *,ulong,CAdvApi32Api *)

- ea: `0x180014fa0`
- end: `0x18001594d`
- name: `?LoadPropertyValuesWin2K@CWin32SystemDriver@@AEAAJPEAUSC_HANDLE__@@AEAU_SERVICE_STATUS_PROCESS@@PEBGPEAVCInstance@@KPEAVCAdvApi32Api@@@Z`
- size: `2477`
- prototype: `__int64 __fastcall(CWin32SystemDriver *__hidden this, struct SC_HANDLE__ *, struct _SERVICE_STATUS_PROCESS *, const unsigned __int16 *, struct CInstance *, unsigned int, struct CAdvApi32Api *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180014c68`

## callees

- `0x180014fa0`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180015393`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180015489`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001571f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180015393`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180015489`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001571f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001557e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001557e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800157c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001554d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015795`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001554d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015795`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180015374`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18001546a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180015700`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180015374`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18001546a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180015700`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180015354`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18001544a`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x180015354`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18001544a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180015031`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180015524`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18001576c`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180015031`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180015524`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18001576c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180015176`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001518b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180015255`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180015176`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001518b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180015255`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180015574`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800157b8`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180015574`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x1800157b8`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001512e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180015146`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180015161`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800152da`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001512e`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180015146`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180015161`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800152da`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180015385`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18001547b`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180015711`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180015385`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x18001547b`
- `framedynos!?GetBuffer@CHString@@QEAAPEAGH@Z` at `0x180015711`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800153a3`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180015499`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x18001572f`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x1800153a3`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x180015499`
- `framedynos!?ReleaseBuffer@CHString@@QEAAXH@Z` at `0x18001572f`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800153f3`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800154e9`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800153f3`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800154e9`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x1800153b9`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x1800154af`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x1800153b9`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x1800154af`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x180015343`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x180015439`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x180015343`
- `framedynos!?Left@CHString@@QEBA?AV1@H@Z` at `0x180015439`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180015741`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18001574f`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180015761`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180015741`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x18001574f`
- `framedynos!??YCHString@@QEAAAEBV0@PEBG@Z` at `0x180015761`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180015117`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800151c3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800151e4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800151f7`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001527c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800152be`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001530a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180015661`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180015117`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800151c3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800151e4`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800151f7`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001527c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800152be`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001530a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180015661`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180015028`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180015028`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18001532c`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x18001532c`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800153e4`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800154da`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800153e4`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x1800154da`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180014ff1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015008`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18001501f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015044`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18001520a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800155b1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800155f1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015605`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015619`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015906`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18001591d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180014ff1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015008`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18001501f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015044`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18001520a`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800155b1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x1800155f1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015605`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015619`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x180015906`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBG0@Z` at `0x18001591d`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x1800153d2`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x1800154c8`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x1800153d2`
- `framedynos!??H@YA?AVCHString@@AEBV0@G@Z` at `0x1800154c8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015361`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800153ff`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001540b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015417`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015423`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015457`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800154f5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015501`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001550d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015519`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001558a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015687`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015813`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015361`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800153ff`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001540b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015417`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015423`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015457`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800154f5`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015501`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001550d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015519`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18001558a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015687`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180015813`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800150bb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800150bb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800155d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015696`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800155d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015696`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001562d`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18001562d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015238`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180015238`

## string_xrefs

- `0x180015181`: `ServiceSpecificExitCode`
- `0x180015272`: `ServiceType`
- `0x1800158b9`: `ServiceType`
- `0x1800158ff`: `ServiceType`
- `0x18001534a`: `System32\`
- `0x180015440`: `\SystemRoot\System32\`
- `0x18001556a`: `PathName`
- `0x1800157ae`: `PathName`
- `0x18001500e`: `Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWin32SystemDriver::LoadPropertyValuesWin2K(
        CWin32SystemDriver *this,
        SC_HANDLE a2,
        struct _SERVICE_STATUS_PROCESS *a3,
        const unsigned __int16 *a4,
        struct CInstance *a5,
        unsigned int a6)
{
  const struct CHString *LocalComputerName; // rax
  const unsigned __int16 *v9; // rax
  unsigned int v10; // r12d
  unsigned int v11; // r14d
  SC_HANDLE v13; // rbx
  DWORD LastError; // eax
  DWORD dwCurrentState; // eax
  DWORD dwControlsAccepted; // r15d
  bool v17; // r13
  const unsigned __int16 *v18; // r8
  LPCWSTR v19; // rsi
  DWORD v20; // eax
  const unsigned __int16 *v21; // r8
  CInstance *v22; // rcx
  const unsigned __int16 *v23; // r8
  CInstance *v24; // rcx
  const unsigned __int16 *v25; // r8
  CInstance *v26; // rcx
  CHString *v27; // rax
  int v28; // esi
  WCHAR *Buffer; // rax
  __int64 v30; // rsi
  __int64 v31; // rax
  __int64 v32; // rax
  CHString *v33; // rax
  int v34; // esi
  WCHAR *v35; // rax
  __int64 v36; // rsi
  __int64 v37; // rax
  __int64 v38; // rax
  const WCHAR *v39; // rax
  HANDLE FileW; // rsi
  const unsigned __int16 *lpServiceStartName; // r8
  const unsigned __int16 *lpDisplayName; // r8
  const unsigned __int16 *v43; // rdx
  const unsigned __int16 *v44; // r8
  CInstance *v45; // rcx
  WCHAR *v46; // rax
  const WCHAR *v47; // rax
  DWORD v48; // eax
  DWORD v49; // eax
  DWORD v50; // eax
  DWORD v51; // eax
  DWORD dwWin32ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpServiceName; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v54; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v55; // [rsp+58h] [rbp-A8h]
  SC_HANDLE hSCManager; // [rsp+60h] [rbp-A0h] BYREF
  char v57[8]; // [rsp+68h] [rbp-98h] BYREF
  char v58[8]; // [rsp+70h] [rbp-90h] BYREF
  SC_HANDLE v59; // [rsp+78h] [rbp-88h]
  struct _SERVICE_STATUS ServiceStatus; // [rsp+80h] [rbp-80h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+A0h] [rbp-60h] BYREF

  lpServiceName = a4;
  hSCManager = a2;
  CInstance::SetCHString(a5, L"Name", a4);
  CInstance::SetCHString(a5, L"CreationClassName", L"Win32_SystemDriver");
  CInstance::SetCHString(a5, L"SystemCreationClassName", L"Win32_ComputerSystem");
  LocalComputerName = Provider::GetLocalComputerName(this);
  v9 = (const unsigned __int16 *)CHString::operator unsigned short const *(LocalComputerName);
  CInstance::SetCHString(a5, L"SystemName", v9);
  v10 = a6 & 0x1FF800;
  if ( (a6 & 0x4DE) == 0 && !v10 )
    return 0;
  v11 = 0;
  v13 = 0;
  v59 = 0;
  if ( (a6 & 0x400) == 0 && (v55 = 0, !v10)
    || (v13 = OpenServiceW(hSCManager, lpServiceName, 0x85u), v59 = v13,
                                                              LastError = GetLastError(),
                                                              v55 = LastError,
                                                              v13)
    || LastError != 1060 && LastError != 123 )
  {
    if ( (a6 & 0x4DE) == 0 )
      goto LABEL_15;
    dwCurrentState = a3->dwCurrentState;
    dwControlsAccepted = a3->dwControlsAccepted;
    dwWin32ExitCode = a3->dwWin32ExitCode;
    LODWORD(hSCManager) = a3->dwServiceSpecificExitCode;
    if ( dwCurrentState == 1 )
    {
      CInstance::SetCharSplat(a5, L"State", L"Stopped");
      v17 = 0;
      goto LABEL_10;
    }
    if ( dwCurrentState == 4 )
    {
      v44 = L"Running";
    }
    else
    {
      v48 = dwCurrentState - 2;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( v49 )
        {
          v50 = v49 - 2;
          if ( v50 )
          {
            v51 = v50 - 1;
            if ( v51 )
            {
              v45 = a5;
              if ( v51 == 1 )
                v44 = L"Paused";
              else
                v44 = L"Unknown";
              goto LABEL_54;
            }
            v44 = L"Pause Pending";
          }
          else
          {
            v44 = L"Continue Pending";
          }
        }
        else
        {
          v44 = L"Stop Pending";
        }
      }
      else
      {
        v44 = L"Start Pending";
      }
    }
    v45 = a5;
LABEL_54:
    CInstance::SetCharSplat(v45, L"State", v44);
    v17 = 1;
LABEL_10:
    CInstance::Setbool(a5, L"Started", v17);
    CInstance::Setbool(a5, L"AcceptStop", dwControlsAccepted & 1);
    CInstance::Setbool(a5, L"AcceptPause", (dwControlsAccepted & 2) != 0);
    CInstance::SetDWORD(a5, L"ExitCode", dwWin32ExitCode);
    CInstance::SetDWORD(a5, L"ServiceSpecificExitCode", (unsigned int)hSCManager);
    if ( (a6 & 0x400) != 0 )
    {
      if ( v13 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !v17 || ControlService(v13, 4u, &ServiceStatus) )
          v18 = L"OK";
        else
          v18 = L"Degraded";
      }
      else
      {
        v18 = L"UNKNOWN";
      }
      CInstance::SetCharSplat(a5, L"Status", v18);
    }
LABEL_15:
    if ( !v10 )
      goto LABEL_43;
    v19 = lpServiceName;
    CInstance::SetCharSplat(a5, L"Caption", lpServiceName);
    CInstance::SetCharSplat(a5, L"DisplayName", lpServiceName);
    CInstance::SetCHString(a5, L"Description", lpServiceName);
    memset_0(&ServiceConfig, 0, 0x400u);
    LODWORD(hSCManager) = 0;
    if ( !QueryServiceConfigW(v13, &ServiceConfig, 0x400u, (LPDWORD)&hSCManager) )
    {
      CInstance::SetCHString(a5, L"ServiceType", L"Unknown");
      CInstance::SetCHString(a5, L"StartMode", L"Unknown");
      lpDisplayName = L"Unknown";
      v43 = L"ErrorControl";
LABEL_48:
      CInstance::SetCHString(a5, v43, lpDisplayName);
LABEL_43:
      if ( !v13 && v55 == 5 )
        v11 = -2147217405;
      if ( v13 )
        CloseServiceHandle(v13);
      return v11;
    }
    CInstance::SetDWORD(a5, L"TagId", ServiceConfig.dwTagId);
    v20 = ServiceConfig.dwServiceType & 0xFFFFFEFF;
    if ( (ServiceConfig.dwServiceType & 0xFFFFFEFF) == 1 )
    {
      v21 = L"Kernel Driver";
    }
    else if ( v20 == 2 )
    {
      v21 = L"File System Driver";
    }
    else
    {
      if ( v20 != 16 )
      {
        v22 = a5;
        if ( v20 == 32 )
          v21 = L"Share Process";
        else
          v21 = L"Unknown";
LABEL_20:
        CInstance::SetCharSplat(v22, L"ServiceType", v21);
        if ( ServiceConfig.dwStartType )
        {
          switch ( ServiceConfig.dwStartType )
          {
            case 1u:
              v23 = L"System";
              break;
            case 2u:
              v23 = L"Auto";
              break;
            case 3u:
              v23 = L"Manual";
              break;
            default:
              v24 = a5;
              if ( ServiceConfig.dwStartType == 4 )
                v23 = L"Disabled";
              else
                v23 = L"Unknown";
LABEL_27:
              CInstance::SetCharSplat(v24, L"StartMode", v23);
              CInstance::Setbool(a5, L"DesktopInteract", ServiceConfig.dwServiceType & 0x100);
              if ( ServiceConfig.dwErrorControl )
              {
                if ( ServiceConfig.dwErrorControl == 1 )
                {
                  v25 = L"Normal";
                }
                else
                {
                  if ( ServiceConfig.dwErrorControl != 2 )
                  {
                    v26 = a5;
                    if ( ServiceConfig.dwErrorControl == 3 )
                      v25 = L"Critical";
                    else
                      v25 = L"Unknown";
LABEL_32:
                    CInstance::SetCharSplat(v26, L"ErrorControl", v25);
                    if ( ServiceConfig.lpBinaryPathName && *ServiceConfig.lpBinaryPathName )
                    {
                      CHString::CHString((CHString *)&dwWin32ExitCode, ServiceConfig.lpBinaryPathName);
                      v27 = (CHString *)CHString::Left(&dwWin32ExitCode, &lpServiceName, 9);
                      v28 = CHString::CompareNoCase(v27, L"System32\\");
                      CHString::~CHString((CHString *)&lpServiceName);
                      if ( !v28 )
                      {
                        CHString::CHString((CHString *)&lpServiceName);
                        Buffer = CHString::GetBuffer((CHString *)&lpServiceName, 260);
                        GetSystemDirectoryW(Buffer, 0x104u);
                        CHString::ReleaseBuffer((CHString *)&lpServiceName, -1);
                        v30 = CHString::Mid(&dwWin32ExitCode, &v54, 9);
                        v31 = operator+(v58, &lpServiceName, 92);
                        v32 = operator+(v57, v31, v30);
                        CHString::operator=(&dwWin32ExitCode, v32);
                        CHString::~CHString((CHString *)v57);
                        CHString::~CHString((CHString *)v58);
                        CHString::~CHString((CHString *)&v54);
                        CHString::~CHString((CHString *)&lpServiceName);
                      }
                      v33 = (CHString *)CHString::Left(&dwWin32ExitCode, &v54, 21);
                      v34 = CHString::CompareNoCase(v33, L"\\SystemRoot\\System32\\");
                      CHString::~CHString((CHString *)&v54);
                      if ( !v34 )
                      {
                        CHString::CHString((CHString *)&lpServiceName);
                        v35 = CHString::GetBuffer((CHString *)&lpServiceName, 260);
                        GetSystemDirectoryW(v35, 0x104u);
                        CHString::ReleaseBuffer((CHString *)&lpServiceName, -1);
                        v36 = CHString::Mid(&dwWin32ExitCode, v57, 21);
                        v37 = operator+(v58, &lpServiceName, 92);
                        v38 = operator+(&v54, v37, v36);
                        CHString::operator=(&dwWin32ExitCode, v38);
                        CHString::~CHString((CHString *)&v54);
                        CHString::~CHString((CHString *)v58);
                        CHString::~CHString((CHString *)v57);
                        CHString::~CHString((CHString *)&lpServiceName);
                      }
                      v39 = (const WCHAR *)CHString::operator unsigned short const *(&dwWin32ExitCode);
                      FileW = CreateFileW(v39, 0x80000000, 3u, 0, 3u, 0, 0);
                      v54 = FileW;
                      if ( FileW != (HANDLE)-1LL )
                        goto LABEL_39;
                      CHString::~CHString((CHString *)&dwWin32ExitCode);
                      if ( v13 )
LABEL_58:
                        CloseServiceHandle(v13);
                    }
                    else
                    {
                      CHString::CHString((CHString *)&dwWin32ExitCode);
                      v46 = CHString::GetBuffer((CHString *)&dwWin32ExitCode, 260);
                      GetSystemDirectoryW(v46, 0x104u);
                      CHString::ReleaseBuffer((CHString *)&dwWin32ExitCode, -1);
                      CHString::operator+=(&dwWin32ExitCode, L"\\drivers\\");
                      CHString::operator+=(&dwWin32ExitCode, v19);
                      CHString::operator+=(&dwWin32ExitCode, L".sys");
                      v47 = (const WCHAR *)CHString::operator unsigned short const *(&dwWin32ExitCode);
                      FileW = CreateFileW(v47, 0x80000000, 3u, 0, 3u, 0, 0);
                      v54 = FileW;
                      if ( FileW != (HANDLE)-1LL )
                      {
LABEL_39:
                        CInstance::SetCHString(a5, L"PathName", (const struct CHString *)&dwWin32ExitCode);
                        CloseHandle(FileW);
                        CHString::~CHString((CHString *)&dwWin32ExitCode);
                        lpServiceStartName = ServiceConfig.lpServiceStartName;
                        if ( !ServiceConfig.lpServiceStartName || !*ServiceConfig.lpServiceStartName )
                          lpServiceStartName = (const unsigned __int16 *)&Data;
                        CInstance::SetCHString(a5, L"StartName", lpServiceStartName);
                        if ( !ServiceConfig.lpDisplayName || !*ServiceConfig.lpDisplayName )
                          goto LABEL_43;
                        CInstance::SetCHString(a5, L"DisplayName", ServiceConfig.lpDisplayName);
                        CInstance::SetCHString(a5, L"Caption", ServiceConfig.lpDisplayName);
                        lpDisplayName = ServiceConfig.lpDisplayName;
                        v43 = L"Description";
                        goto LABEL_48;
                      }
                      CHString::~CHString((CHString *)&dwWin32ExitCode);
                      if ( v13 )
                        goto LABEL_58;
                    }
                    return 2147749890LL;
                  }
                  v25 = L"Severe";
                }
              }
              else
              {
                v25 = L"Ignore";
              }
              v26 = a5;
              goto LABEL_32;
          }
        }
        else
        {
          v23 = L"Boot";
        }
        v24 = a5;
        goto LABEL_27;
      }
      v21 = L"Own Process";
    }
    v22 = a5;
    goto LABEL_20;
  }
  return 2147749890LL;
}

```

## disassembly

```asm
0x180014fa0  push    rbp
0x180014fa2  push    rbx
0x180014fa3  push    rsi
0x180014fa4  push    rdi
0x180014fa5  push    r12
0x180014fa7  push    r13
0x180014fa9  push    r14
0x180014fab  push    r15
0x180014fad  lea     rbp, [rsp-3B8h]
0x180014fb5  sub     rsp, 4B8h
0x180014fbc  mov     rax, cs:__security_cookie
0x180014fc3  xor     rax, rsp
0x180014fc6  mov     [rbp+3F0h+var_50], rax
0x180014fcd  mov     [rsp+4F0h+lpServiceName], r9
0x180014fd2  mov     r13, r8
0x180014fd5  mov     [rsp+4F0h+hSCManager], rdx
0x180014fda  mov     rbx, rcx
0x180014fdd  mov     rdi, [rbp+3F0h+arg_20]
0x180014fe4  mov     r8, r9
0x180014fe7  lea     rdx, aName; "Name"
0x180014fee  mov     rcx, rdi
0x180014ff1  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180014ff7  lea     r8, aWin32Systemdri; "Win32_SystemDriver"
0x180014ffe  lea     rdx, aCreationclassn; "CreationClassName"
0x180015005  mov     rcx, rdi
0x180015008  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x18001500e  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x180015015  lea     rdx, aSystemcreation; "SystemCreationClassName"
0x18001501c  mov     rcx, rdi
0x18001501f  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180015025  mov     rcx, rbx
0x180015028  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x18001502e  mov     rcx, rax
0x180015031  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180015037  mov     r8, rax
0x18001503a  lea     rdx, aSystemname; "SystemName"
0x180015041  mov     rcx, rdi
0x180015044  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x18001504a  mov     esi, [rbp+3F0h+arg_28]
0x180015050  mov     r15d, esi
0x180015053  mov     r12d, esi
0x180015056  and     r12d, 1FF800h
0x18001505d  and     r15d, 4DEh
0x180015064  jnz     short loc_180015094
0x180015066  test    r12d, r12d
0x180015069  jnz     short loc_180015094
0x18001506b  xor     r14d, r14d
0x18001506e  mov     eax, r14d
0x180015071  mov     rcx, [rbp+3F0h+var_50]
0x180015078  xor     rcx, rsp; StackCookie
0x18001507b  call    __security_check_cookie
0x180015080  add     rsp, 4B8h
0x180015087  pop     r15
0x180015089  pop     r14
0x18001508b  pop     r13
0x18001508d  pop     r12
0x18001508f  pop     rdi
0x180015090  pop     rsi
0x180015091  pop     rbx
0x180015092  pop     rbp
0x180015093  retn
0x180015094  xor     r14d, r14d
0x180015097  mov     ebx, r14d
0x18001509a  mov     [rsp+4F0h+var_478], rbx
0x18001509f  and     esi, 400h
0x1800150a5  jz      loc_18001566F
0x1800150ab  mov     r8d, 85h; dwDesiredAccess
0x1800150b1  mov     rdx, [rsp+4F0h+lpServiceName]; lpServiceName
0x1800150b6  mov     rcx, [rsp+4F0h+hSCManager]; hSCManager
0x1800150bb  call    cs:__imp_OpenServiceW
0x1800150c1  mov     rbx, rax
0x1800150c4  mov     [rsp+4F0h+var_478], rax
0x1800150c9  call    cs:__imp_GetLastError
0x1800150cf  mov     [rsp+4F0h+var_498], eax
0x1800150d3  test    rbx, rbx
0x1800150d6  jz      loc_180015828
0x1800150dc  test    r15d, r15d
0x1800150df  jz      loc_1800151C9
0x1800150e5  mov     eax, [r13+4]
0x1800150e9  mov     r15d, [r13+8]
0x1800150ed  mov     ecx, [r13+0Ch]
0x1800150f1  mov     [rsp+4F0h+var_4B0], ecx
0x1800150f5  mov     ecx, [r13+10h]
0x1800150f9  mov     dword ptr [rsp+4F0h+hSCManager], ecx
0x1800150fd  cmp     eax, 1
0x180015100  jnz     loc_180015647
0x180015106  lea     r8, aStopped; "Stopped"
0x18001510d  lea     rdx, aState; "State"
0x180015114  mov     rcx, rdi
0x180015117  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001511d  xor     r13b, r13b
0x180015120  movzx   r8d, r13b
0x180015124  lea     rdx, aStarted; "Started"
0x18001512b  mov     rcx, rdi
0x18001512e  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180015134  movzx   r8d, r15b
0x180015138  and     r8b, 1
0x18001513c  lea     rdx, aAcceptstop; "AcceptStop"
0x180015143  mov     rcx, rdi
0x180015146  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18001514c  shr     r15d, 1
0x18001514f  and     r15b, 1
0x180015153  movzx   r8d, r15b
0x180015157  lea     rdx, aAcceptpause; "AcceptPause"
0x18001515e  mov     rcx, rdi
0x180015161  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x180015167  mov     r8d, [rsp+4F0h+var_4B0]
0x18001516c  lea     rdx, aExitcode; "ExitCode"
0x180015173  mov     rcx, rdi
0x180015176  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001517c  mov     r8d, dword ptr [rsp+4F0h+hSCManager]
0x180015181  lea     rdx, aServicespecifi; "ServiceSpecificExitCode"
0x180015188  mov     rcx, rdi
0x18001518b  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180015191  test    esi, esi
0x180015193  jz      short loc_1800151C9
0x180015195  test    rbx, rbx
0x180015198  jz      loc_1800158AD
0x18001519e  xorps   xmm0, xmm0
0x1800151a1  movups  xmmword ptr [rbp+3F0h+ServiceStatus.dwServiceType], xmm0
0x1800151a5  movups  xmmword ptr [rbp+3F0h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800151a9  test    r13b, r13b
0x1800151ac  jnz     loc_180015621
0x1800151b2  lea     r8, aOk; "OK"
0x1800151b9  lea     rdx, aStatus; "Status"
0x1800151c0  mov     rcx, rdi
0x1800151c3  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800151c9  test    r12d, r12d
0x1800151cc  jz      loc_1800155C0
0x1800151d2  mov     rsi, [rsp+4F0h+lpServiceName]
0x1800151d7  mov     r8, rsi
0x1800151da  lea     rdx, aCaption; "Caption"
0x1800151e1  mov     rcx, rdi
0x1800151e4  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800151ea  mov     r8, rsi
0x1800151ed  lea     rdx, aDisplayname; "DisplayName"
0x1800151f4  mov     rcx, rdi
0x1800151f7  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800151fd  mov     r8, rsi
0x180015200  lea     rdx, aDescription; "Description"
0x180015207  mov     rcx, rdi
0x18001520a  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCHString(ushort const *,ushort const *)
0x180015210  xor     edx, edx; Val
0x180015212  mov     r8d, 400h; Size
0x180015218  lea     rcx, [rbp+3F0h+ServiceConfig]; void *
0x18001521c  call    memset_0
0x180015221  mov     dword ptr [rsp+4F0h+hSCManager], r14d
0x180015226  lea     r9, [rsp+4F0h+hSCManager]; pcbBytesNeeded
0x18001522b  mov     r8d, 400h; cbBufSize
0x180015231  lea     rdx, [rbp+3F0h+ServiceConfig]; lpServiceConfig
0x180015235  mov     rcx, rbx; hService
0x180015238  call    cs:__imp_QueryServiceConfigW
0x18001523e  mov     rcx, rdi
0x180015241  cmp     eax, 1
0x180015244  jnz     loc_1800158F8
0x18001524a  mov     r8d, [rbp+3F0h+ServiceConfig.dwTagId]
0x18001524e  lea     rdx, aTagid; "TagId"
0x180015255  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001525b  mov     eax, [rbp+3F0h+ServiceConfig.dwServiceType]
0x18001525e  btr     eax, 8
0x180015262  cmp     eax, 1
0x180015265  jnz     loc_1800156B2
0x18001526b  lea     r8, aKernelDriver; "Kernel Driver"
0x180015272  lea     rdx, aServicetype; "ServiceType"
0x180015279  mov     rcx, rdi
0x18001527c  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180015282  mov     eax, [rbp+3F0h+ServiceConfig.dwStartType]
0x180015285  test    eax, eax
0x180015287  jz      short loc_1800152AD
0x180015289  sub     eax, 1
0x18001528c  jz      loc_1800156A6
0x180015292  sub     eax, 1
0x180015295  jz      loc_1800156EF
0x18001529b  sub     eax, 1
0x18001529e  jnz     loc_1800157CE
0x1800152a4  lea     r8, aManual; "Manual"
0x1800152ab  jmp     short loc_1800152B4
0x1800152ad  lea     r8, aBoot; "Boot"
0x1800152b4  mov     rcx, rdi
0x1800152b7  lea     rdx, aStartmode; "StartMode"
0x1800152be  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800152c4  mov     r8d, [rbp+3F0h+ServiceConfig.dwServiceType]
0x1800152c8  shr     r8d, 8
0x1800152cc  and     r8b, 1
0x1800152d0  lea     rdx, aDesktopinterac; "DesktopInteract"
0x1800152d7  mov     rcx, rdi
0x1800152da  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800152e0  mov     eax, [rbp+3F0h+ServiceConfig.dwErrorControl]
0x1800152e3  test    eax, eax
0x1800152e5  jz      short loc_1800152F9
0x1800152e7  sub     eax, 1
0x1800152ea  jnz     loc_1800156C7
0x1800152f0  lea     r8, aNormal; "Normal"
0x1800152f7  jmp     short loc_180015300
0x1800152f9  lea     r8, aIgnore; "Ignore"
0x180015300  lea     rdx, aErrorcontrol; "ErrorControl"
0x180015307  mov     rcx, rdi
0x18001530a  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180015310  mov     rdx, [rbp+3F0h+ServiceConfig.lpBinaryPathName]
0x180015314  test    rdx, rdx
0x180015317  jz      loc_1800156FB
0x18001531d  cmp     word ptr [rdx], 0
0x180015321  jz      loc_1800156FB
0x180015327  lea     rcx, [rsp+4F0h+var_4B0]
0x18001532c  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x180015332  nop
0x180015333  mov     r8d, 9
0x180015339  lea     rdx, [rsp+4F0h+lpServiceName]
0x18001533e  lea     rcx, [rsp+4F0h+var_4B0]
0x180015343  call    cs:__imp_?Left@CHString@@QEBA?AV1@H@Z; CHString::Left(int)
0x180015349  nop
0x18001534a  lea     rdx, aSystem32_0; "System32\\"
0x180015351  mov     rcx, rax
0x180015354  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x18001535a  mov     esi, eax
0x18001535c  lea     rcx, [rsp+4F0h+lpServiceName]
0x180015361  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180015367  test    esi, esi
0x180015369  jnz     loc_180015429
0x18001536f  lea     rcx, [rsp+4F0h+lpServiceName]
0x180015374  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18001537a  nop
0x18001537b  mov     edx, 104h
0x180015380  lea     rcx, [rsp+4F0h+lpServiceName]
0x180015385  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x18001538b  mov     rcx, rax; lpBuffer
0x18001538e  mov     edx, 104h; uSize
0x180015393  call    cs:__imp_GetSystemDirectoryW
0x180015399  mov     edx, 0FFFFFFFFh
0x18001539e  lea     rcx, [rsp+4F0h+lpServiceName]
0x1800153a3  call    cs:__imp_?ReleaseBuffer@CHString@@QEAAXH@Z; CHString::ReleaseBuffer(int)
0x1800153a9  mov     r8d, 9
0x1800153af  lea     rdx, [rsp+4F0h+var_4A0]
0x1800153b4  lea     rcx, [rsp+4F0h+var_4B0]
0x1800153b9  call    cs:__imp_?Mid@CHString@@QEBA?AV1@H@Z; CHString::Mid(int)
0x1800153bf  mov     rsi, rax
0x1800153c2  mov     r8d, 5Ch ; '\'
0x1800153c8  lea     rdx, [rsp+4F0h+lpServiceName]
0x1800153cd  lea     rcx, [rsp+4F0h+var_480]
0x1800153d2  call    cs:__imp_??H@YA?AVCHString@@AEBV0@G@Z; operator+(CHString const &,ushort)
0x1800153d8  nop
0x1800153d9  mov     r8, rsi
0x1800153dc  mov     rdx, rax
0x1800153df  lea     rcx, [rsp+4F0h+var_488]
0x1800153e4  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x1800153ea  nop
0x1800153eb  mov     rdx, rax
0x1800153ee  lea     rcx, [rsp+4F0h+var_4B0]
0x1800153f3  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800153f9  nop
0x1800153fa  lea     rcx, [rsp+4F0h+var_488]
0x1800153ff  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180015405  nop
0x180015406  lea     rcx, [rsp+4F0h+var_480]
0x18001540b  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180015411  nop
0x180015412  lea     rcx, [rsp+4F0h+var_4A0]
0x180015417  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18001541d  nop
0x18001541e  lea     rcx, [rsp+4F0h+lpServiceName]
0x180015423  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180015429  mov     r8d, 15h
0x18001542f  lea     rdx, [rsp+4F0h+var_4A0]
0x180015434  lea     rcx, [rsp+4F0h+var_4B0]
0x180015439  call    cs:__imp_?Left@CHString@@QEBA?AV1@H@Z; CHString::Left(int)
0x18001543f  nop
0x180015440  lea     rdx, aSystemrootSyst; "\\SystemRoot\\System32\\"
0x180015447  mov     rcx, rax
0x18001544a  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x180015450  mov     esi, eax
0x180015452  lea     rcx, [rsp+4F0h+var_4A0]
0x180015457  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18001545d  test    esi, esi
0x18001545f  jnz     loc_18001551F
0x180015465  lea     rcx, [rsp+4F0h+lpServiceName]
0x18001546a  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180015470  nop
0x180015471  mov     edx, 104h
0x180015476  lea     rcx, [rsp+4F0h+lpServiceName]
0x18001547b  call    cs:__imp_?GetBuffer@CHString@@QEAAPEAGH@Z; CHString::GetBuffer(int)
0x180015481  mov     rcx, rax; lpBuffer
0x180015484  mov     edx, 104h; uSize
0x180015489  call    cs:__imp_GetSystemDirectoryW
0x18001548f  mov     edx, 0FFFFFFFFh
0x180015494  lea     rcx, [rsp+4F0h+lpServiceName]
0x180015499  call    cs:__imp_?ReleaseBuffer@CHString@@QEAAXH@Z; CHString::ReleaseBuffer(int)
0x18001549f  mov     r8d, 15h
0x1800154a5  lea     rdx, [rsp+4F0h+var_488]
0x1800154aa  lea     rcx, [rsp+4F0h+var_4B0]
0x1800154af  call    cs:__imp_?Mid@CHString@@QEBA?AV1@H@Z; CHString::Mid(int)
0x1800154b5  mov     rsi, rax
0x1800154b8  mov     r8d, 5Ch ; '\'
0x1800154be  lea     rdx, [rsp+4F0h+lpServiceName]
0x1800154c3  lea     rcx, [rsp+4F0h+var_480]
0x1800154c8  call    cs:__imp_??H@YA?AVCHString@@AEBV0@G@Z; operator+(CHString const &,ushort)
0x1800154ce  nop
0x1800154cf  mov     r8, rsi
0x1800154d2  mov     rdx, rax
0x1800154d5  lea     rcx, [rsp+4F0h+var_4A0]
0x1800154da  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
  ... truncated ...
```
