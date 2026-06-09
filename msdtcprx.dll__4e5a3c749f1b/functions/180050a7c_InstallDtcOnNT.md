# InstallDtcOnNT

- ea: `0x180050a7c`
- end: `0x180051223`
- name: `InstallDtcOnNT`
- size: `1959`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180051df0`

## callees

- `0x180006054`
- `0x18000c6bc`
- `0x18001156c`
- `0x180011ac0`
- `0x18002f534`
- `0x180050a7c`
- `0x1800512f8`
- `0x180073390`
- `0x180081d9e`
- `0x180081dd0`
- `0x180081e90`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180051111`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180051111`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005112a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005112a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050bfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005103d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800510b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800511d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180050be2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180050c8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180050be2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180050c8d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800511ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800511f8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800511ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800511f8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180050de4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180050de4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180050d9d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180050d9d`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x180050f0d`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x180050f0d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180050fab`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180051033`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18005106e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800510ae`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180050fab`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180051033`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18005106e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800510ae`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180050e5d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180050e5d`

## string_xrefs

- `0x180050be8`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050e77`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050f46`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050f6a`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x1800510e7`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050bef`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050b20`: `Coordinates transactions that span multiple resource managers, such as databases, message queues, and file systems. If this service is stopped, these transactions will not occur. If this service is disabled, any services that explicitly depend on it will fail to start. `
- `0x180050c06`: `InstallDtcOnNT: GetSystemDirectoryW failed.`
- `0x180050ca3`: `InstallDtcOnNT: GetSystemDirectoryW failed.`
- `0x180050c2d`: `COMRES.DLL`
- `0x180050cca`: `COMRES.DLL`
- `0x180050c51`: `InstallDtcOnNT: failed to print to wszDisplayName.`
- `0x180050cee`: `InstallDtcOnNT: failed to print to wszServiceDescription.`
- `0x180050d3f`: `InstallDtcOnNT: Failed to get the DTC Security Configuration options`
- `0x180050dc7`: `InstallDtcOnNT: Failed to open the SCM manager`
- `0x180050e80`: `InstallDtcOnNT: Failed to change the configuration of MSDTC service.`
- `0x180050f23`: `InstallDtcOnNT: Failed to create the MSDTC service.`
- `0x180050f37`: `Created MsDtc Service. Msdtc Service will be running as NetworkService`
- `0x1800511e2`: `InstallDtcOnNT: The call to OpenService failed with an unexpected hr`
- `0x180050f7d`: `InstallDtcOnNT: SetAccountInfoInRegistryW failed.`
- `0x180050fc1`: `InstallDtcOnNT: ChangeServiceConfig2W call failed.`
- `0x180051049`: `InstallDtcOnNT: ChangeServiceConfig2W to set Failure Actions call failed.`
- `0x180051084`: `InstallDtcOnNT: ChangeServiceConfig2W to set service SID call failed.`
- `0x180051097`: `SeChangeNotifyPrivilege`
- `0x1800510c4`: `InstallDtcOnNT: ChangeServiceConfig2W to set service privileges call failed.`
- `0x1800510f7`: `About to create performance counter registry keys`
- `0x180051108`: `msdtcuiu.dll`
- `0x180051120`: `PerfDllRegisterServer`
- `0x180051140`: `Executing lodctr msdtcprf.ini command`
- `0x180051171`: `lodctr msdtcprf.ini command failed with errorcode = %d`
- `0x1800511a0`: `GetProcAddress PerfDllRegisterServer failed`
- `0x1800511b5`: `LoadlibraryExA msdtcuiu.dll failed`
- `0x180050e0c`: `NT AUTHORITY\NetworkService`
- `0x180050eb4`: `NT AUTHORITY\NetworkService`

## pseudocode

```c
__int64 __fastcall InstallDtcOnNT(struct ITmInstance *a1, const WCHAR *a2, __int64 a3, DWORD a4)
{
  __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  const wchar_t *v9; // rcx
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm1
  UINT SystemDirectoryW; // eax
  DWORD LastError; // eax
  int v20; // eax
  UINT v21; // eax
  DWORD v22; // eax
  int v23; // eax
  DWORD v24; // eax
  unsigned int v25; // r9d
  char *v26; // rdx
  int v28; // eax
  unsigned int v29; // ebx
  SC_HANDLE v30; // r12
  SC_HANDLE v31; // rax
  SC_HANDLE v32; // rsi
  DWORD v33; // eax
  DWORD v34; // eax
  char *v35; // rdx
  unsigned int v36; // r9d
  int v37; // eax
  DWORD v38; // eax
  int v39; // edx
  int v40; // eax
  __int64 v41; // rcx
  DWORD v42; // eax
  DWORD v43; // eax
  DWORD v44; // eax
  HMODULE Library; // rax
  void (*ProcAddress)(void); // rax
  char *v47; // rcx
  unsigned int v48; // r9d
  char *v49; // rdx
  int v50; // ecx
  DWORD v51; // eax
  DWORD v52; // eax
  LPCWSTR lpBinaryPathName; // [rsp+20h] [rbp-E0h]
  unsigned int v54; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwStartType; // [rsp+74h] [rbp-8Ch] BYREF
  LPCWSTR lpMachineName; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+84h] [rbp-7Ch] BYREF
  int v59; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpServiceName; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *Info; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v62[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v63; // [rsp+A8h] [rbp-58h]
  int v64; // [rsp+B8h] [rbp-48h]
  int v65; // [rsp+BCh] [rbp-44h]
  _DWORD *v66; // [rsp+C0h] [rbp-40h]
  _DWORD v67[10]; // [rsp+C8h] [rbp-38h] BYREF
  char v68[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v69; // [rsp+100h] [rbp+0h]
  __int128 v70; // [rsp+110h] [rbp+10h]
  __int128 v71; // [rsp+120h] [rbp+20h]
  _BYTE v72[28]; // [rsp+130h] [rbp+30h]
  _BYTE v73[420]; // [rsp+14Ch] [rbp+4Ch] BYREF
  WCHAR DisplayName; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR Buffer[279]; // [rsp+2F2h] [rbp+1F2h] BYREF
  WCHAR BinaryPathName[272]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v77; // [rsp+740h] [rbp+640h] BYREF
  WCHAR v78[1023]; // [rsp+742h] [rbp+642h] BYREF
  unsigned __int16 v79[271]; // [rsp+F40h] [rbp+E40h] BYREF
  _BYTE v80[1506]; // [rsp+115Eh] [rbp+105Eh] BYREF

  v69 = *(_OWORD *)L"t Distributed Transaction Coordinator";
  *(_OWORD *)v68 = *(_OWORD *)L"Microsoft Distributed Transaction Coordinator";
  v71 = *(_OWORD *)L"ansaction Coordinator";
  lpServiceName = a2;
  v70 = *(_OWORD *)L"buted Transaction Coordinator";
  *(_OWORD *)v72 = *(_OWORD *)L"n Coordinator";
  *(_OWORD *)&v72[12] = *(_OWORD *)L"dinator";
  dwStartType = a4;
  memset_0(v73, 0, sizeof(v73));
  v7 = 4;
  v8 = v79;
  v9 = L"Coordinates transactions that span multiple resource managers, such as databases, message queues, and file system"
        "s. If this service is stopped, these transactions will not occur. If this service is disabled, any services that"
        " explicitly depend on it will fail to start. ";
  do
  {
    v10 = *((_OWORD *)v9 + 1);
    *(_OWORD *)v8 = *(_OWORD *)v9;
    v11 = *((_OWORD *)v9 + 2);
    *((_OWORD *)v8 + 1) = v10;
    v12 = *((_OWORD *)v9 + 3);
    *((_OWORD *)v8 + 2) = v11;
    v13 = *((_OWORD *)v9 + 4);
    *((_OWORD *)v8 + 3) = v12;
    v14 = *((_OWORD *)v9 + 5);
    *((_OWORD *)v8 + 4) = v13;
    v15 = *((_OWORD *)v9 + 6);
    *((_OWORD *)v8 + 5) = v14;
    v16 = *((_OWORD *)v9 + 7);
    v9 += 64;
    *((_OWORD *)v8 + 6) = v15;
    *((_OWORD *)v8 + 7) = v16;
    v8 += 64;
    --v7;
  }
  while ( v7 );
  v17 = *(_OWORD *)(v9 + 7);
  *(_OWORD *)v8 = *(_OWORD *)v9;
  *(_OWORD *)(v8 + 7) = v17;
  memset_0(v80, 0, sizeof(v80));
  Info = 0;
  v59 = 0;
  v58 = 0;
  v57 = 0;
  lpMachineName = 0;
  StringCchPrintfW(BinaryPathName, 0x110u, L"%s\\msdtc.exe", a3);
  DisplayName = 64;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x115u);
  if ( SystemDirectoryW )
  {
    v20 = StringCchPrintfW(&Buffer[SystemDirectoryW], 277LL - SystemDirectoryW, L"\\%s,-%d", L"COMRES.DLL", 2797);
    if ( v20 >= 0 )
      goto LABEL_8;
    TraceFileW(
      v20,
      L"InstallDtcOnNT: failed to print to wszDisplayName.",
      L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
      0x654u);
  }
  else
  {
    LastError = GetLastError();
    TraceFile(
      LastError,
      "InstallDtcOnNT: GetSystemDirectoryW failed.",
      "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
      0x64Bu);
  }
  StringCchCopyW(&DisplayName, 0x116u, (const unsigned __int16 *)v68);
LABEL_8:
  v77 = 64;
  v21 = GetSystemDirectoryW(v78, 0x3FFu);
  if ( v21 )
  {
    LODWORD(lpBinaryPathName) = 2798;
    v23 = StringCchPrintfW(&v78[v21], 1023LL - v21, L"\\%s,-%d", L"COMRES.DLL", lpBinaryPathName);
    if ( v23 >= 0 )
      goto LABEL_13;
    TraceFileW(
      v23,
      L"InstallDtcOnNT: failed to print to wszServiceDescription.",
      L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
      0x669u);
  }
  else
  {
    v22 = GetLastError();
    TraceFile(
      v22,
      "InstallDtcOnNT: GetSystemDirectoryW failed.",
      "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
      0x65Eu);
  }
  StringCchCopyW(&v77, 0x400u, v79);
LABEL_13:
  v24 = (*(__int64 (__fastcall **)(struct ITmInstance *, int *, int *, int *))(*(_QWORD *)a1 + 280LL))(
          a1,
          &v59,
          &v58,
          &v57);
  if ( v24 )
  {
    v25 = 1652;
    v26 = "InstallDtcOnNT: Failed to get the DTC Security Configuration options";
LABEL_15:
    TraceFile(v24, v26, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v25);
    return 2147500037LL;
  }
  v28 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPCWSTR *))(*(_QWORD *)a1 + 40LL))(a1, &lpMachineName);
  v29 = v28;
  if ( v28 >= 0 )
  {
    v30 = OpenSCManagerW(lpMachineName, 0, 0xF003Fu);
    CoTaskMemFree((LPVOID)lpMachineName);
    lpMachineName = 0;
    if ( !v30 )
    {
      v24 = GetLastError();
      v25 = 1684;
      v26 = "InstallDtcOnNT: Failed to open the SCM manager";
      goto LABEL_15;
    }
    v54 = 0;
    v31 = OpenServiceW(v30, a2, 0xF00FEu);
    v32 = v31;
    if ( v31 )
    {
      if ( !ChangeServiceConfigW(
              v31,
              0x10u,
              dwStartType,
              1u,
              BinaryPathName,
              &cchOriginalDestLength,
              0,
              L"RPCSS",
              ServiceStartName,
              &Password,
              &DisplayName) )
      {
        v33 = GetLastError();
        TraceFile(
          v33,
          "InstallDtcOnNT: Failed to change the configuration of MSDTC service.",
          "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
          0x6B2u);
        v29 = -2147467259;
      }
    }
    else
    {
      if ( GetLastError() != 1060 )
      {
        v52 = GetLastError();
        TraceFile(
          v52,
          "InstallDtcOnNT: The call to OpenService failed with an unexpected hr",
          "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
          0x6E3u);
        v29 = -2147467259;
LABEL_55:
        CloseServiceHandle(v30);
        return v29;
      }
      v32 = CreateServiceW(
              v30,
              lpServiceName,
              &DisplayName,
              0xF00FEu,
              0x10u,
              dwStartType,
              1u,
              BinaryPathName,
              0,
              0,
              L"RPCSS",
              ServiceStartName,
              &Password);
      if ( v32 )
      {
        v54 = 1;
        v35 = "Created MsDtc Service. Msdtc Service will be running as NetworkService";
        v34 = 0;
        v36 = 1755;
      }
      else
      {
        v29 = -2147467259;
        v34 = GetLastError();
        v35 = "InstallDtcOnNT: Failed to create the MSDTC service.";
        v36 = 1749;
      }
      TraceFile(v34, v35, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v36);
    }
    if ( !v29 )
    {
      v37 = SetAccountInfoInRegistryW(a1, ServiceStartName);
      v29 = v37;
      if ( v37 < 0 )
        TraceFile(
          v37,
          "InstallDtcOnNT: SetAccountInfoInRegistryW failed.",
          "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
          0x6EDu);
      if ( !v29 )
      {
        Info = &v77;
        if ( !ChangeServiceConfig2W(v32, 1u, &Info) )
        {
          v38 = GetLastError();
          TraceFile(
            v38,
            "InstallDtcOnNT: ChangeServiceConfig2W call failed.",
            "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
            0x6FCu);
          v29 = -2147467259;
        }
        v62[1] = 0;
        v39 = 0;
        v65 = 0;
        do
        {
          v40 = 10000 * v39;
          v41 = (unsigned int)v39++;
          v67[2 * v41] = 1;
          v67[2 * v41 + 1] = v40 + 1000;
        }
        while ( v39 < 3 );
        v67[7] = 1000;
        v66 = v67;
        v67[6] = 0;
        v62[0] = 30;
        v64 = 4;
        v63 = 0;
        if ( !ChangeServiceConfig2W(v32, 2u, v62) )
        {
          v42 = GetLastError();
          TraceFile(
            v42,
            "InstallDtcOnNT: ChangeServiceConfig2W to set Failure Actions call failed.",
            "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
            0x719u);
          v29 = -2147467259;
        }
        dwStartType = 1;
        if ( !ChangeServiceConfig2W(v32, 5u, &dwStartType) )
        {
          v43 = GetLastError();
          TraceFile(
            v43,
            "InstallDtcOnNT: ChangeServiceConfig2W to set service SID call failed.",
            "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
            0x729u);
          v29 = -2147467259;
        }
        lpServiceName = L"SeChangeNotifyPrivilege";
        if ( !ChangeServiceConfig2W(v32, 6u, &lpServiceName) )
        {
          v44 = GetLastError();
          TraceFile(
            v44,
            "InstallDtcOnNT: ChangeServiceConfig2W to set service privileges call failed.",
            "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
            0x739u);
          v29 = -2147467259;
        }
      }
    }
    if ( !v54 )
    {
LABEL_52:
      if ( v32 )
        CloseServiceHandle(v32);
      goto LABEL_55;
    }
    TraceFile(
      0,
      "About to create performance counter registry keys",
      "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
      0x744u);
    Library = LoadLibraryExA("msdtcuiu.dll", 0, 0);
    if ( Library )
    {
      ProcAddress = (void (*)(void))GetProcAddress(Library, "PerfDllRegisterServer");
      if ( ProcAddress )
      {
        ProcAddress();
        TraceFile(0, "Executing lodctr msdtcprf.ini command", "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0x752u);
        v54 = 0;
        v29 = RunCmd(v47, &v54);
        if ( !v29 && v54 != -1 )
          goto LABEL_52;
        StringCchPrintfA(v68, 0x85u, "lodctr msdtcprf.ini command failed with errorcode = %d", v54);
        v48 = 1884;
        v49 = v68;
        v50 = v29;
        goto LABEL_51;
      }
      v51 = GetLastError();
      v48 = 1889;
      v49 = "GetProcAddress PerfDllRegisterServer failed";
    }
    else
    {
      v51 = GetLastError();
      v48 = 1894;
      v49 = "LoadlibraryExA msdtcuiu.dll failed";
    }
    v50 = v51;
LABEL_51:
    TraceFile(v50, v49, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v48);
    goto LABEL_52;
  }
  TraceFileW(v28, L"ITmInstance::GetHostName failed", L"com\\complus\\dtc\\dtc\\adme\\deployment.cpp", 0x685u);
  return v29;
}

```

## disassembly

```asm
0x180050a7c  push    rbp
0x180050a7e  push    rbx
0x180050a7f  push    rsi
0x180050a80  push    rdi
0x180050a81  push    r12
0x180050a83  push    r13
0x180050a85  push    r14
0x180050a87  push    r15
0x180050a89  lea     rbp, [rsp-1658h]
0x180050a91  mov     eax, 1758h
0x180050a96  call    _alloca_probe
0x180050a9b  sub     rsp, rax
0x180050a9e  mov     rax, cs:__security_cookie
0x180050aa5  xor     rax, rsp
0x180050aa8  mov     [rbp+1690h+var_50], rax
0x180050aaf  movaps  xmm1, xmmword ptr cs:aMicrosoftDistr+10h; "t Distributed Transaction Coordinator"
0x180050ab6  mov     rbx, r8
0x180050ab9  movaps  xmm0, xmmword ptr cs:aMicrosoftDistr; "Microsoft Distributed Transaction Coord"...
0x180050ac0  mov     rdi, rdx
0x180050ac3  movaps  [rbp+1690h+var_1690], xmm1
0x180050ac7  mov     r15, rcx
0x180050aca  movaps  xmm1, xmmword ptr cs:aMicrosoftDistr+30h; "ansaction Coordinator"
0x180050ad1  lea     rcx, [rbp+1690h+var_1644]; void *
0x180050ad5  movaps  xmmword ptr [rbp+1690h+var_16A0], xmm0
0x180050ad9  mov     r8d, 1A4h; Size
0x180050adf  movaps  xmm0, xmmword ptr cs:aMicrosoftDistr+20h; "buted Transaction Coordinator"
0x180050ae6  movaps  [rbp+1690h+var_1670], xmm1
0x180050aea  movups  xmm1, xmmword ptr cs:aMicrosoftDistr+4Ch; "dinator"
0x180050af1  mov     [rbp+1690h+lpServiceName], rdx
0x180050af5  xor     edx, edx; Val
0x180050af7  movaps  [rbp+1690h+var_1680], xmm0
0x180050afb  movaps  xmm0, xmmword ptr cs:aMicrosoftDistr+40h; "n Coordinator"
0x180050b02  movaps  xmmword ptr [rbp+1690h+var_1660], xmm0
0x180050b06  movups  xmmword ptr [rbp+1690h+var_1660+0Ch], xmm1
0x180050b0a  mov     [rsp+1790h+dwStartType], r9d
0x180050b0f  call    memset_0
0x180050b14  mov     edx, 4
0x180050b19  lea     rax, [rbp+1690h+var_850]
0x180050b20  lea     rcx, aCoordinatesTra; "Coordinates transactions that span mult"...
0x180050b27  lea     r8d, [rdx+7Ch]
0x180050b2b  movups  xmm0, xmmword ptr [rcx]
0x180050b2e  movups  xmm1, xmmword ptr [rcx+10h]
0x180050b32  movups  xmmword ptr [rax], xmm0
0x180050b35  movups  xmm0, xmmword ptr [rcx+20h]
0x180050b39  movups  xmmword ptr [rax+10h], xmm1
0x180050b3d  movups  xmm1, xmmword ptr [rcx+30h]
0x180050b41  movups  xmmword ptr [rax+20h], xmm0
0x180050b45  movups  xmm0, xmmword ptr [rcx+40h]
0x180050b49  movups  xmmword ptr [rax+30h], xmm1
0x180050b4d  movups  xmm1, xmmword ptr [rcx+50h]
0x180050b51  movups  xmmword ptr [rax+40h], xmm0
0x180050b55  movups  xmm0, xmmword ptr [rcx+60h]
0x180050b59  movups  xmmword ptr [rax+50h], xmm1
0x180050b5d  movups  xmm1, xmmword ptr [rcx+70h]
0x180050b61  add     rcx, r8
0x180050b64  movups  xmmword ptr [rax+60h], xmm0
0x180050b68  movups  xmmword ptr [rax+70h], xmm1
0x180050b6c  add     rax, r8
0x180050b6f  sub     rdx, 1; Val
0x180050b73  jnz     short loc_180050B2B
0x180050b75  movups  xmm0, xmmword ptr [rcx]
0x180050b78  mov     r8d, 5E2h; Size
0x180050b7e  movups  xmm1, xmmword ptr [rcx+0Eh]
0x180050b82  lea     rcx, [rbp+1690h+var_632]; void *
0x180050b89  movups  xmmword ptr [rax], xmm0
0x180050b8c  movups  xmmword ptr [rax+0Eh], xmm1
0x180050b90  call    memset_0
0x180050b95  xor     r14d, r14d
0x180050b98  lea     r8, aSMsdtcExe; "%s\\msdtc.exe"
0x180050b9f  mov     r9, rbx
0x180050ba2  mov     [rbp+1690h+Info], r14
0x180050ba6  mov     edx, 110h; unsigned __int64
0x180050bab  mov     [rbp+1690h+var_1708], r14d
0x180050baf  lea     rcx, [rbp+1690h+BinaryPathName]; unsigned __int16 *
0x180050bb6  mov     [rbp+1690h+var_170C], r14d
0x180050bba  mov     [rbp+1690h+var_1710], r14d
0x180050bbe  mov     [rsp+1790h+lpMachineName], r14
0x180050bc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180050bc8  mov     ebx, 115h
0x180050bcd  lea     r12d, [r14+40h]
0x180050bd1  mov     edx, ebx; uSize
0x180050bd3  mov     [rbp+1690h+DisplayName], r12w
0x180050bdb  lea     rcx, [rbp+1690h+Buffer]; lpBuffer
0x180050be2  call    cs:__imp_GetSystemDirectoryW
0x180050be8  lea     r13, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050bef  lea     rsi, aComComplusDtcD_8; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050bf6  test    eax, eax
0x180050bf8  jnz     short loc_180050C19
0x180050bfa  call    cs:__imp_GetLastError
0x180050c00  mov     r9d, 64Bh; unsigned int
0x180050c06  lea     rdx, aInstalldtconnt_6; "InstallDtcOnNT: GetSystemDirectoryW fai"...
0x180050c0d  mov     ecx, eax; int
0x180050c0f  mov     r8, r13; char *
0x180050c12  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050c17  jmp     short loc_180050C62
0x180050c19  mov     eax, eax
0x180050c1b  lea     rcx, [rbp+1690h+Buffer]
0x180050c22  sub     rbx, rax
0x180050c25  mov     dword ptr [rsp+1790h+lpBinaryPathName], 0AEDh
0x180050c2d  lea     r9, aComresDll_0; "COMRES.DLL"
0x180050c34  mov     rdx, rbx; unsigned __int64
0x180050c37  lea     r8, aSD; "\\%s,-%d"
0x180050c3e  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180050c42  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180050c47  test    eax, eax
0x180050c49  jns     short loc_180050C77
0x180050c4b  mov     r9d, 654h; unsigned int
0x180050c51  lea     rdx, aInstalldtconnt_9; "InstallDtcOnNT: failed to print to wszD"...
0x180050c58  mov     r8, rsi; unsigned __int16 *
0x180050c5b  mov     ecx, eax; int
0x180050c5d  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180050c62  lea     r8, [rbp+1690h+var_16A0]; unsigned __int16 *
0x180050c66  mov     edx, 116h; unsigned __int64
0x180050c6b  lea     rcx, [rbp+1690h+DisplayName]; unsigned __int16 *
0x180050c72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180050c77  mov     ebx, 3FFh
0x180050c7c  mov     [rbp+1690h+var_1050], r12w
0x180050c84  mov     edx, ebx; uSize
0x180050c86  lea     rcx, [rbp+1690h+var_104E]; lpBuffer
0x180050c8d  call    cs:__imp_GetSystemDirectoryW
0x180050c93  test    eax, eax
0x180050c95  jnz     short loc_180050CB6
0x180050c97  call    cs:__imp_GetLastError
0x180050c9d  mov     r9d, 65Eh; unsigned int
0x180050ca3  lea     rdx, aInstalldtconnt_6; "InstallDtcOnNT: GetSystemDirectoryW fai"...
0x180050caa  mov     ecx, eax; int
0x180050cac  mov     r8, r13; char *
0x180050caf  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050cb4  jmp     short loc_180050CFF
0x180050cb6  mov     eax, eax
0x180050cb8  lea     rcx, [rbp+1690h+var_104E]
0x180050cbf  sub     rbx, rax
0x180050cc2  mov     dword ptr [rsp+1790h+lpBinaryPathName], 0AEEh
0x180050cca  lea     r9, aComresDll_0; "COMRES.DLL"
0x180050cd1  mov     rdx, rbx; unsigned __int64
0x180050cd4  lea     r8, aSD; "\\%s,-%d"
0x180050cdb  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180050cdf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180050ce4  test    eax, eax
0x180050ce6  jns     short loc_180050D17
0x180050ce8  mov     r9d, 669h; unsigned int
0x180050cee  lea     rdx, aInstalldtconnt_3; "InstallDtcOnNT: failed to print to wszS"...
0x180050cf5  mov     r8, rsi; unsigned __int16 *
0x180050cf8  mov     ecx, eax; int
0x180050cfa  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180050cff  lea     r8, [rbp+1690h+var_850]; unsigned __int16 *
0x180050d06  mov     edx, 400h; unsigned __int64
0x180050d0b  lea     rcx, [rbp+1690h+var_1050]; unsigned __int16 *
0x180050d12  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180050d17  mov     rax, [r15]
0x180050d1a  lea     r9, [rbp+1690h+var_1710]
0x180050d1e  lea     r8, [rbp+1690h+var_170C]
0x180050d22  mov     rcx, r15
0x180050d25  lea     rdx, [rbp+1690h+var_1708]
0x180050d29  mov     rax, [rax+118h]
0x180050d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d35  test    eax, eax
0x180050d37  jz      short loc_180050D5A
0x180050d39  mov     r9d, 674h; unsigned int
0x180050d3f  lea     rdx, aInstalldtconnt_4; "InstallDtcOnNT: Failed to get the DTC S"...
0x180050d46  mov     ecx, eax; int
0x180050d48  mov     r8, r13; char *
0x180050d4b  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050d50  mov     eax, 80004005h
0x180050d55  jmp     loc_180051200
0x180050d5a  mov     rax, [r15]
0x180050d5d  lea     rdx, [rsp+1790h+lpMachineName]
0x180050d62  mov     rcx, r15
0x180050d65  mov     rax, [rax+28h]
0x180050d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d6e  mov     ebx, eax
0x180050d70  test    eax, eax
0x180050d72  jns     short loc_180050D90
0x180050d74  mov     r9d, 685h; unsigned int
0x180050d7a  lea     rdx, aItminstanceGet; "ITmInstance::GetHostName failed"
0x180050d81  mov     r8, rsi; unsigned __int16 *
0x180050d84  mov     ecx, eax; int
0x180050d86  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x180050d8b  jmp     loc_1800511FE
0x180050d90  mov     rcx, [rsp+1790h+lpMachineName]; lpMachineName
0x180050d95  xor     edx, edx; lpDatabaseName
0x180050d97  mov     r8d, 0F003Fh; dwDesiredAccess
0x180050d9d  call    cs:__imp_OpenSCManagerW
0x180050da3  mov     rcx, [rsp+1790h+lpMachineName]; pv
0x180050da8  mov     r12, rax
0x180050dab  call    cs:__imp_CoTaskMemFree
0x180050db1  mov     [rsp+1790h+lpMachineName], r14
0x180050db6  test    r12, r12
0x180050db9  jnz     short loc_180050DD3
0x180050dbb  call    cs:__imp_GetLastError
0x180050dc1  mov     r9d, 694h
0x180050dc7  lea     rdx, aInstalldtconnt_10; "InstallDtcOnNT: Failed to open the SCM "...
0x180050dce  jmp     loc_180050D46
0x180050dd3  mov     r8d, 0F00FEh; dwDesiredAccess
0x180050dd9  mov     [rsp+1790h+var_1720], r14d
0x180050dde  mov     rdx, rdi; lpServiceName
0x180050de1  mov     rcx, r12; hSCManager
0x180050de4  call    cs:__imp_OpenServiceW
0x180050dea  mov     rsi, rax
0x180050ded  mov     edi, 80004005h
0x180050df2  test    rax, rax
0x180050df5  jz      loc_180050E93
0x180050dfb  mov     r8d, [rsp+1790h+dwStartType]; dwStartType
0x180050e00  lea     rax, [rbp+1690h+DisplayName]
0x180050e07  mov     [rsp+1790h+lpDisplayName], rax; lpDisplayName
0x180050e0c  lea     r13, ServiceStartName; "NT AUTHORITY\\NetworkService"
0x180050e13  lea     rax, Password
0x180050e1a  mov     rcx, rsi; hService
0x180050e1d  mov     [rsp+1790h+lpPassword], rax; lpPassword
0x180050e22  lea     rax, Dependencies; "RPCSS"
0x180050e29  mov     [rsp+1790h+lpServiceStartName], r13; lpServiceStartName
0x180050e2e  mov     [rsp+1790h+lpDependencies], rax; lpDependencies
0x180050e33  lea     rax, cchOriginalDestLength
0x180050e3a  mov     [rsp+1790h+lpdwTagId], r14; lpdwTagId
0x180050e3f  mov     r14d, 1
0x180050e45  mov     [rsp+1790h+lpLoadOrderGroup], rax; lpLoadOrderGroup
0x180050e4a  mov     r9d, r14d; dwErrorControl
0x180050e4d  lea     rax, [rbp+1690h+BinaryPathName]
0x180050e54  mov     [rsp+1790h+lpBinaryPathName], rax; lpBinaryPathName
0x180050e59  lea     edx, [r14+0Fh]; dwServiceType
0x180050e5d  call    cs:__imp_ChangeServiceConfigW
0x180050e63  test    eax, eax
0x180050e65  jnz     loc_180050F54
0x180050e6b  call    cs:__imp_GetLastError
0x180050e71  mov     r9d, 6B2h; unsigned int
0x180050e77  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050e7e  mov     ecx, eax; int
0x180050e80  lea     rdx, aInstalldtconnt_2; "InstallDtcOnNT: Failed to change the co"...
0x180050e87  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050e8c  mov     ebx, edi
0x180050e8e  jmp     loc_180050F54
0x180050e93  call    cs:__imp_GetLastError
0x180050e99  cmp     eax, 424h
0x180050e9e  jnz     loc_1800511D6
0x180050ea4  mov     rdx, [rbp+1690h+lpServiceName]; lpServiceName
0x180050ea8  lea     rax, Password
0x180050eaf  mov     [rsp+1790h+var_1730], rax; lpPassword
0x180050eb4  lea     r13, ServiceStartName; "NT AUTHORITY\\NetworkService"
0x180050ebb  mov     [rsp+1790h+var_1738], r13; lpServiceStartName
0x180050ec0  lea     rax, Dependencies; "RPCSS"
0x180050ec7  mov     [rsp+1790h+lpDisplayName], rax; lpDependencies
0x180050ecc  lea     r8, [rbp+1690h+DisplayName]; lpDisplayName
0x180050ed3  mov     [rsp+1790h+lpPassword], r14; lpdwTagId
0x180050ed8  lea     rax, [rbp+1690h+BinaryPathName]
0x180050edf  mov     [rsp+1790h+lpServiceStartName], r14; lpLoadOrderGroup
0x180050ee4  mov     r9d, 0F00FEh; dwDesiredAccess
0x180050eea  mov     [rsp+1790h+lpDependencies], rax; lpBinaryPathName
0x180050eef  mov     r14d, 1
0x180050ef5  mov     eax, [rsp+1790h+dwStartType]
0x180050ef9  mov     rcx, r12; hSCManager
0x180050efc  mov     dword ptr [rsp+1790h+lpdwTagId], r14d; dwErrorControl
0x180050f01  mov     dword ptr [rsp+1790h+lpLoadOrderGroup], eax; dwStartType
0x180050f05  mov     dword ptr [rsp+1790h+lpBinaryPathName], 10h; dwServiceType
0x180050f0d  call    cs:__imp_CreateServiceW
0x180050f13  mov     rsi, rax
0x180050f16  test    rax, rax
0x180050f19  jnz     short loc_180050F32
0x180050f1b  mov     ebx, edi
0x180050f1d  call    cs:__imp_GetLastError
0x180050f23  lea     rdx, aInstalldtconnt_11; "InstallDtcOnNT: Failed to create the MS"...
0x180050f2a  mov     r9d, 6D5h
0x180050f30  jmp     short loc_180050F46
0x180050f32  mov     [rsp+1790h+var_1720], r14d
0x180050f37  lea     rdx, aCreatedMsdtcSe; "Created MsDtc Service. Msdtc Service wi"...
0x180050f3e  xor     eax, eax
0x180050f40  mov     r9d, 6DBh; unsigned int
0x180050f46  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050f4d  mov     ecx, eax; int
0x180050f4f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050f54  test    ebx, ebx
0x180050f56  jnz     loc_1800510D9
0x180050f5c  mov     rdx, r13; unsigned __int16 *
0x180050f5f  mov     rcx, r15; struct ITmInstance *
0x180050f62  call    ?SetAccountInfoInRegistryW@@YAJPEAUITmInstance@@PEAG@Z; SetAccountInfoInRegistryW(ITmInstance *,ushort *)
0x180050f67  xor     r15d, r15d
0x180050f6a  lea     r13, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050f71  mov     ebx, eax
0x180050f73  test    eax, eax
0x180050f75  jns     short loc_180050F8E
0x180050f77  mov     r9d, 6EDh; unsigned int
0x180050f7d  lea     rdx, aInstalldtconnt_5; "InstallDtcOnNT: SetAccountInfoInRegistr"...
0x180050f84  mov     r8, r13; char *
0x180050f87  mov     ecx, eax; int
0x180050f89  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050f8e  test    ebx, ebx
0x180050f90  jnz     loc_1800510DC
0x180050f96  lea     rax, [rbp+1690h+var_1050]
0x180050f9d  mov     edx, r14d; dwInfoLevel
0x180050fa0  lea     r8, [rbp+1690h+Info]; lpInfo
0x180050fa4  mov     [rbp+1690h+Info], rax
0x180050fa8  mov     rcx, rsi; hService
0x180050fab  call    cs:__imp_ChangeServiceConfig2W
0x180050fb1  test    eax, eax
0x180050fb3  jnz     short loc_180050FD4
0x180050fb5  call    cs:__imp_GetLastError
0x180050fbb  mov     r9d, 6FCh; unsigned int
0x180050fc1  lea     rdx, aInstalldtconnt_7; "InstallDtcOnNT: ChangeServiceConfig2W c"...
0x180050fc8  mov     ecx, eax; int
0x180050fca  mov     r8, r13; char *
0x180050fcd  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
  ... truncated ...
```
