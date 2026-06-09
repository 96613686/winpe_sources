# CWin32Service::LoadPropertyValuesNT(SC_HANDLE__ *,ushort const *,CInstance *,ulong,CAdvApi32Api *)

- ea: `0x18005bf0c`
- end: `0x18005c66a`
- name: `?LoadPropertyValuesNT@CWin32Service@@AEAAJPEAUSC_HANDLE__@@PEBGPEAVCInstance@@KPEAVCAdvApi32Api@@@Z`
- size: `1886`
- prototype: `int(CWin32Service *__hidden this, struct SC_HANDLE__ *, const unsigned __int16 *, struct CInstance *, unsigned int, struct CAdvApi32Api *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005bd74`

## callees

- `0x18000ab30`
- `0x180013ae0`
- `0x180044b1c`
- `0x18005bf0c`
- `0x18006cf9c`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bf5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c353`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c188`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c19b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c1b0`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c1c5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c1da`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c3cc`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c188`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c19b`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c1b0`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c1c5`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c1da`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18005c3cc`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18005c61f`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18005c61f`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c142`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c159`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c173`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c446`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c142`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c159`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c173`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18005c446`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c110`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c12c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c1f6`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c25d`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c27e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c291`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c318`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c42b`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c4af`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c50a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c529`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c548`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c567`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c588`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c59f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c5b6`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c5ea`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c601`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c632`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c110`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c12c`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c1f6`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c25d`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c27e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c291`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c318`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c42b`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c4af`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c50a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c529`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c548`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c567`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c588`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c59f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c5b6`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c5ea`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c601`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18005c632`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x18005c60c`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x18005c60c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005bf4e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005bf4e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005c39c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005c641`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005c39c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005c641`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005c054`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18005c054`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18005c232`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18005c232`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005c346`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005c38e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005c346`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005c38e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18005c2bc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18005c301`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18005c2bc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18005c301`

## string_xrefs

- `0x18005c5d9`: `Win32_Service`
- `0x18005c17e`: `ProcessId`
- `0x18005c1a6`: `ServiceSpecificExitCode`
- `0x18005c3e7`: `ServiceType`
- `0x18005c421`: `ServiceType`
- `0x18005c581`: `ServiceType`
- `0x18005c51f`: `PathName`
- `0x18005c5f0`: `Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWin32Service::LoadPropertyValuesNT(
        CWin32Service *this,
        SC_HANDLE a2,
        const unsigned __int16 *a3,
        struct CInstance *a4,
        unsigned int a5,
        struct CAdvApi32Api *a6)
{
  const unsigned __int16 *v7; // r12
  SC_HANDLE v8; // rsi
  DWORD LastError; // eax
  enum _SC_STATUS_TYPE v10; // r8d
  unsigned int v11; // r13d
  unsigned int v13; // r14d
  int v14; // edi
  char v15; // r12
  bool v16; // zf
  DWORD v17; // eax
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  int v23; // edi
  const unsigned __int16 *v24; // r8
  bool v25; // di
  BOOL v26; // eax
  const unsigned __int16 *v27; // r8
  const unsigned __int16 **v28; // rdi
  struct _QUERY_SERVICE_CONFIGW *v29; // rdi
  BOOL v30; // r14d
  struct _QUERY_SERVICE_CONFIGW *v31; // rax
  const unsigned __int16 *v32; // r8
  DWORD dwStartType; // ecx
  DWORD v34; // ecx
  DWORD v35; // ecx
  DWORD v36; // ecx
  const unsigned __int16 *v37; // r8
  DWORD dwErrorControl; // ecx
  DWORD v39; // ecx
  DWORD v40; // ecx
  const unsigned __int16 *v41; // r8
  const unsigned __int16 *lpBinaryPathName; // r8
  const unsigned __int16 *lpServiceStartName; // r8
  const unsigned __int16 *lpDisplayName; // r8
  unsigned int v45; // edi
  const struct CHString *LocalComputerName; // rax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-C8h]
  DWORD cbBufSize; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+44h] [rbp-A4h]
  unsigned int v50; // [rsp+4Ch] [rbp-9Ch]
  unsigned int v51; // [rsp+50h] [rbp-98h]
  void *v52; // [rsp+58h] [rbp-90h]
  unsigned int v53; // [rsp+60h] [rbp-88h] BYREF
  DWORD v54; // [rsp+64h] [rbp-84h]
  SC_HANDLE v55; // [rsp+68h] [rbp-80h] BYREF
  Provider *v56; // [rsp+70h] [rbp-78h]
  _BYTE ServiceStatus[32]; // [rsp+78h] [rbp-70h] BYREF
  int v58; // [rsp+98h] [rbp-50h]

  v7 = a3;
  v52 = (void *)a3;
  v56 = this;
  v8 = OpenServiceW(a2, a3, 0x85u);
  v55 = v8;
  LastError = GetLastError();
  v54 = LastError;
  v11 = 0;
  if ( !v8 && (LastError == 1060 || LastError == 123) )
  {
    SmartCloseServiceHandle::~SmartCloseServiceHandle(&v55);
    return 2147749890LL;
  }
  v13 = a5 & 0x1FF800;
  if ( (a5 & 0x7FE) == 0 )
  {
    if ( !v13 )
    {
LABEL_104:
      v45 = 0;
      goto LABEL_105;
    }
LABEL_43:
    CInstance::SetCharSplat(a4, L"Caption", v7);
    CInstance::SetCharSplat(a4, L"DisplayName", v7);
    if ( v8
      && (cbBufSize = 0, !QueryServiceConfig2W(v8, 1u, 0, 0, &cbBufSize))
      && GetLastError() == 122
      && (v28 = (const unsigned __int16 **)operator new(cbBufSize), (v52 = v28) != 0) )
    {
      try
      {
        if ( QueryServiceConfig2W(v8, 1u, (LPBYTE)v28, cbBufSize, &cbBufSize) )
          CInstance::SetCharSplat(a4, L"Description", *v28);
      }
      catch ( ... )
      {
        operator delete(v52);
        throw;
      }
      operator delete(v28);
      v29 = 0;
    }
    else
    {
      v29 = 0;
      if ( !v8 )
      {
        v30 = 0;
        goto LABEL_58;
      }
    }
    cbBufSize = 0;
    v30 = QueryServiceConfigW(v8, 0, 0, &cbBufSize);
    if ( !v30 && GetLastError() == 122 )
    {
      v31 = (struct _QUERY_SERVICE_CONFIGW *)operator new(cbBufSize);
      v29 = v31;
      if ( !v31 )
      {
        CloseServiceHandle(v8);
        return 2147749894LL;
      }
      memset_0(v31, 0, cbBufSize);
      v30 = QueryServiceConfigW(v8, v29, cbBufSize, &cbBufSize);
    }
LABEL_58:
    v52 = v29;
    if ( !v30 )
    {
      CInstance::SetCharSplat(a4, L"ServiceType", L"Unknown");
      CInstance::SetCharSplat(a4, L"StartMode", L"Unknown");
      CInstance::SetCharSplat(a4, L"ErrorControl", L"Unknown");
LABEL_101:
      operator delete(v29);
      goto LABEL_102;
    }
    CInstance::SetDWORD(a4, L"TagId", v29->dwTagId);
    if ( (v29->dwServiceType & 0xFFFFFEFF) == 1 )
    {
      v32 = L"Kernel Driver";
    }
    else if ( (v29->dwServiceType & 0xFFFFFEFF) == 2 )
    {
      v32 = L"File System Driver";
    }
    else
    {
      if ( (v29->dwServiceType & 0xFFFFFEFF) != 0x10 )
      {
        if ( (v29->dwServiceType & 0xFFFFFEFF) == 0x20 )
          CInstance::SetCharSplat(a4, L"ServiceType", L"Share Process");
        else
          CInstance::SetCharSplat(a4, L"ServiceType", L"Unknown");
LABEL_69:
        CInstance::Setbool(a4, L"DesktopInteract", v29->dwServiceType & 0x100);
        dwStartType = v29->dwStartType;
        if ( dwStartType )
        {
          v34 = dwStartType - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v36 = v35 - 1;
              if ( v36 )
              {
                if ( v36 == 1 )
                  CInstance::SetCharSplat(a4, L"StartMode", L"Disabled");
                else
                  CInstance::SetCharSplat(a4, L"StartMode", L"Unknown");
LABEL_81:
                dwErrorControl = v29->dwErrorControl;
                if ( dwErrorControl )
                {
                  v39 = dwErrorControl - 1;
                  if ( v39 )
                  {
                    v40 = v39 - 1;
                    if ( v40 )
                    {
                      if ( v40 == 1 )
                        CInstance::SetCharSplat(a4, L"ErrorControl", L"Critical");
                      else
                        CInstance::SetCharSplat(a4, L"ErrorControl", L"Unknown");
                      goto LABEL_91;
                    }
                    v41 = L"Severe";
                  }
                  else
                  {
                    v41 = L"Normal";
                  }
                }
                else
                {
                  v41 = L"Ignore";
                }
                CInstance::SetCharSplat(a4, L"ErrorControl", v41);
LABEL_91:
                lpBinaryPathName = v29->lpBinaryPathName;
                if ( lpBinaryPathName && *lpBinaryPathName )
                  CInstance::SetCharSplat(a4, L"PathName", lpBinaryPathName);
                lpServiceStartName = v29->lpServiceStartName;
                if ( lpServiceStartName && *lpServiceStartName )
                  CInstance::SetCharSplat(a4, L"StartName", lpServiceStartName);
                lpDisplayName = v29->lpDisplayName;
                if ( lpDisplayName && *lpDisplayName )
                {
                  CInstance::SetCharSplat(a4, L"DisplayName", lpDisplayName);
                  CInstance::SetCharSplat(a4, L"Caption", v29->lpDisplayName);
                }
                goto LABEL_101;
              }
              v37 = L"Manual";
            }
            else
            {
              v37 = L"Auto";
            }
          }
          else
          {
            v37 = L"System";
          }
        }
        else
        {
          v37 = L"Boot";
        }
        CInstance::SetCharSplat(a4, L"StartMode", v37);
        goto LABEL_81;
      }
      v32 = L"Own Process";
    }
    CInstance::SetCharSplat(a4, L"ServiceType", v32);
    goto LABEL_69;
  }
  cbBufSize = 0;
  if ( !v8 )
    goto LABEL_34;
  v51 = 0;
  v14 = 0;
  v15 = 0;
  v49 = 0;
  v50 = 0;
  *(_OWORD *)ServiceStatus = 0;
  if ( !a6 )
  {
    *(_OWORD *)&ServiceStatus[12] = 0;
    v17 = QueryServiceStatus(v8, (LPSERVICE_STATUS)ServiceStatus);
    if ( v17 != 1 )
      goto LABEL_15;
    goto LABEL_14;
  }
  *(_OWORD *)&ServiceStatus[16] = 0;
  v58 = 0;
  v53 = 0;
  v16 = !CAdvApi32Api::QueryServiceStatusEx(a6, v8, v10, ServiceStatus, pcbBytesNeeded, &v53, (int *)&cbBufSize);
  v17 = cbBufSize;
  if ( !v16 && cbBufSize == 1 )
  {
    v51 = *(_DWORD *)&ServiceStatus[28];
LABEL_14:
    v49 = *(_QWORD *)&ServiceStatus[16];
    v50 = *(_DWORD *)&ServiceStatus[24];
    v11 = *(_DWORD *)&ServiceStatus[12];
    v15 = ServiceStatus[8];
    v14 = *(_DWORD *)&ServiceStatus[4];
  }
LABEL_15:
  if ( v17 )
  {
    v18 = v14 - 1;
    if ( !v18 )
    {
      CInstance::SetCharSplat(a4, L"State", L"Stopped");
      v25 = 0;
      goto LABEL_33;
    }
    v19 = v18 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              if ( v23 == 1 )
                CInstance::SetCharSplat(a4, L"State", L"Paused");
              else
                CInstance::SetCharSplat(a4, L"State", L"Unknown");
              goto LABEL_31;
            }
            v24 = L"Pause Pending";
          }
          else
          {
            v24 = L"Continue Pending";
          }
        }
        else
        {
          v24 = L"Running";
        }
      }
      else
      {
        v24 = L"Stop Pending";
      }
    }
    else
    {
      v24 = L"Start Pending";
    }
    CInstance::SetCharSplat(a4, L"State", v24);
LABEL_31:
    v25 = 1;
LABEL_33:
    CInstance::Setbool(a4, L"Started", v25);
    CInstance::Setbool(a4, L"AcceptStop", v15 & 1);
    CInstance::Setbool(a4, L"AcceptPause", (v15 & 2) != 0);
    CInstance::SetDWORD(a4, L"ProcessId", v51);
    CInstance::SetDWORD(a4, L"ExitCode", v11);
    CInstance::SetDWORD(a4, L"ServiceSpecificExitCode", v49);
    CInstance::SetDWORD(a4, L"CheckPoint", HIDWORD(v49));
    CInstance::SetDWORD(a4, L"WaitHint", v50);
    goto LABEL_35;
  }
LABEL_34:
  v25 = 1;
  CInstance::SetCharSplat(a4, L"State", L"Unknown");
LABEL_35:
  if ( (a5 & 0x400) == 0 )
    goto LABEL_42;
  if ( v8 )
  {
    memset(ServiceStatus, 0, 28);
    if ( !v25 || (v26 = ControlService(v8, 4u, (LPSERVICE_STATUS)ServiceStatus), v27 = L"Degraded", v26) )
    {
      CInstance::SetCharSplat(a4, L"Status", L"OK");
      goto LABEL_42;
    }
  }
  else
  {
    v27 = L"UNKNOWN";
  }
  CInstance::SetCharSplat(a4, L"Status", v27);
LABEL_42:
  v7 = (const unsigned __int16 *)v52;
  if ( v13 )
    goto LABEL_43;
LABEL_102:
  if ( v8 )
    goto LABEL_104;
  v45 = -2147217405;
  if ( v54 != 5 )
    goto LABEL_104;
LABEL_105:
  CInstance::SetCharSplat(a4, L"CreationClassName", L"Win32_Service");
  CInstance::SetCharSplat(a4, L"SystemCreationClassName", L"Win32_ComputerSystem");
  LocalComputerName = Provider::GetLocalComputerName(v56);
  CInstance::SetCHString(a4, L"SystemName", LocalComputerName);
  CInstance::SetCharSplat(a4, L"Name", v7);
  if ( v8 )
    CloseServiceHandle(v8);
  return v45;
}

```

## disassembly

```asm
0x18005bf0c  push    rbx
0x18005bf0e  push    rsi
0x18005bf0f  push    rdi
0x18005bf10  push    r12
0x18005bf12  push    r13
0x18005bf14  push    r14
0x18005bf16  sub     rsp, 0B8h
0x18005bf1d  mov     rax, cs:__security_cookie
0x18005bf24  xor     rax, rsp
0x18005bf27  mov     [rsp+0E8h+var_48], rax
0x18005bf2f  mov     rbx, r9
0x18005bf32  mov     r12, r8
0x18005bf35  mov     [rsp+0E8h+var_90], r8
0x18005bf3a  mov     rax, rdx
0x18005bf3d  mov     [rsp+0E8h+var_78], rcx
0x18005bf42  mov     r8d, 85h; dwDesiredAccess
0x18005bf48  mov     rdx, r12; lpServiceName
0x18005bf4b  mov     rcx, rax; hSCManager
0x18005bf4e  call    cs:__imp_OpenServiceW
0x18005bf54  mov     rsi, rax
0x18005bf57  mov     [rsp+0E8h+var_80], rax
0x18005bf5c  call    cs:__imp_GetLastError
0x18005bf62  mov     [rsp+0E8h+var_84], eax
0x18005bf66  xor     r13d, r13d
0x18005bf69  test    rsi, rsi
0x18005bf6c  jnz     short loc_18005BF8E
0x18005bf6e  cmp     eax, 424h
0x18005bf73  jz      short loc_18005BF7A
0x18005bf75  cmp     eax, 7Bh ; '{'
0x18005bf78  jnz     short loc_18005BF8E
0x18005bf7a  lea     rcx, [rsp+0E8h+var_80]; this
0x18005bf7f  call    ??1SmartCloseServiceHandle@@QEAA@XZ; SmartCloseServiceHandle::~SmartCloseServiceHandle(void)
0x18005bf84  mov     eax, 80041002h
0x18005bf89  jmp     loc_18005C649
0x18005bf8e  mov     r14d, [rsp+0E8h+arg_20]
0x18005bf96  and     r14d, 1FF800h
0x18005bf9d  test    [rsp+0E8h+arg_20], 7FEh
0x18005bfa8  jnz     short loc_18005BFB8
0x18005bfaa  test    r14d, r14d
0x18005bfad  jz      loc_18005C5D6
0x18005bfb3  jmp     loc_18005C271
0x18005bfb8  mov     [rsp+0E8h+cbBufSize], r13d
0x18005bfbd  test    rsi, rsi
0x18005bfc0  jz      loc_18005C1E2
0x18005bfc6  mov     [rsp+0E8h+var_98], r13d
0x18005bfcb  mov     edi, r13d
0x18005bfce  mov     r12d, r13d
0x18005bfd1  xor     edx, edx
0x18005bfd3  mov     [rsp+0E8h+var_A4], edx
0x18005bfd7  mov     [rsp+0E8h+var_A0], edx
0x18005bfdb  mov     [rsp+0E8h+var_9C], edx
0x18005bfdf  mov     rcx, [rsp+0E8h+arg_28]; this
0x18005bfe7  xorps   xmm0, xmm0
0x18005bfea  movups  xmmword ptr [rsp+0E8h+ServiceStatus], xmm0
0x18005bfef  test    rcx, rcx
0x18005bff2  jz      short loc_18005C044
0x18005bff4  xor     eax, eax
0x18005bff6  movups  xmmword ptr [rsp+0E8h+ServiceStatus+10h], xmm0
0x18005bffe  mov     [rsp+0E8h+var_50], eax
0x18005c005  mov     [rsp+0E8h+var_88], edx
0x18005c009  lea     rax, [rsp+0E8h+cbBufSize]
0x18005c00e  mov     [rsp+0E8h+var_B8], rax; int *
0x18005c013  lea     rax, [rsp+0E8h+var_88]
0x18005c018  mov     [rsp+0E8h+var_C0], rax; unsigned int *
0x18005c01d  lea     r9, [rsp+0E8h+ServiceStatus]; unsigned __int8 *
0x18005c022  mov     rdx, rsi; struct SC_HANDLE__ *
0x18005c025  call    ?QueryServiceStatusEx@CAdvApi32Api@@QEAA_NPEAUSC_HANDLE__@@W4_SC_STATUS_TYPE@@PEAEKPEAKPEAH@Z; CAdvApi32Api::QueryServiceStatusEx(SC_HANDLE__ *,_SC_STATUS_TYPE,uchar *,ulong,ulong *,int *)
0x18005c02a  test    al, al
0x18005c02c  mov     eax, [rsp+0E8h+cbBufSize]
0x18005c030  jz      short loc_18005C094
0x18005c032  cmp     eax, 1
0x18005c035  jnz     short loc_18005C094
0x18005c037  mov     ecx, dword ptr [rsp+0E8h+ServiceStatus+1Ch]
0x18005c03e  mov     [rsp+0E8h+var_98], ecx
0x18005c042  jmp     short loc_18005C05F
0x18005c044  movups  xmmword ptr [rsp+0E8h+ServiceStatus+0Ch], xmm0
0x18005c04c  lea     rdx, [rsp+0E8h+ServiceStatus]; lpServiceStatus
0x18005c051  mov     rcx, rsi; hService
0x18005c054  call    cs:__imp_QueryServiceStatus
0x18005c05a  cmp     eax, 1
0x18005c05d  jnz     short loc_18005C094
0x18005c05f  mov     ecx, dword ptr [rsp+0E8h+ServiceStatus+10h]
0x18005c066  mov     [rsp+0E8h+var_A4], ecx
0x18005c06a  mov     ecx, dword ptr [rsp+0E8h+ServiceStatus+14h]
0x18005c071  mov     [rsp+0E8h+var_A0], ecx
0x18005c075  mov     ecx, dword ptr [rsp+0E8h+ServiceStatus+18h]
0x18005c07c  mov     [rsp+0E8h+var_9C], ecx
0x18005c080  mov     r13d, dword ptr [rsp+0E8h+ServiceStatus+0Ch]
0x18005c088  mov     r12d, dword ptr [rsp+0E8h+ServiceStatus+8]
0x18005c090  mov     edi, dword ptr [rsp+0E8h+ServiceStatus+4]
0x18005c094  test    eax, eax
0x18005c096  jz      loc_18005C1E2
0x18005c09c  sub     edi, 1
0x18005c09f  jz      short loc_18005C11B
0x18005c0a1  sub     edi, 1
0x18005c0a4  jz      short loc_18005C0FF
0x18005c0a6  sub     edi, 1
0x18005c0a9  jz      short loc_18005C0F6
0x18005c0ab  sub     edi, 1
0x18005c0ae  jz      short loc_18005C0ED
0x18005c0b0  sub     edi, 1
0x18005c0b3  jz      short loc_18005C0E4
0x18005c0b5  sub     edi, 1
0x18005c0b8  jz      short loc_18005C0DB
0x18005c0ba  lea     rdx, aState; "State"
0x18005c0c1  mov     rcx, rbx
0x18005c0c4  cmp     edi, 1
0x18005c0c7  jz      short loc_18005C0D2
0x18005c0c9  lea     r8, aUnknown_0; "Unknown"
0x18005c0d0  jmp     short loc_18005C110
0x18005c0d2  lea     r8, aPaused; "Paused"
0x18005c0d9  jmp     short loc_18005C110
0x18005c0db  lea     r8, aPausePending; "Pause Pending"
0x18005c0e2  jmp     short loc_18005C106
0x18005c0e4  lea     r8, aContinuePendin; "Continue Pending"
0x18005c0eb  jmp     short loc_18005C106
0x18005c0ed  lea     r8, aRunning; "Running"
0x18005c0f4  jmp     short loc_18005C106
0x18005c0f6  lea     r8, aStopPending; "Stop Pending"
0x18005c0fd  jmp     short loc_18005C106
0x18005c0ff  lea     r8, aStartPending; "Start Pending"
0x18005c106  lea     rdx, aState; "State"
0x18005c10d  mov     rcx, rbx
0x18005c110  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c116  mov     dil, 1
0x18005c119  jmp     short loc_18005C135
0x18005c11b  lea     r8, aStopped; "Stopped"
0x18005c122  lea     rdx, aState; "State"
0x18005c129  mov     rcx, rbx
0x18005c12c  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c132  xor     dil, dil
0x18005c135  mov     r8b, dil
0x18005c138  lea     rdx, aStarted; "Started"
0x18005c13f  mov     rcx, rbx
0x18005c142  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18005c148  mov     r8b, r12b
0x18005c14b  and     r8b, 1
0x18005c14f  lea     rdx, aAcceptstop; "AcceptStop"
0x18005c156  mov     rcx, rbx
0x18005c159  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18005c15f  shr     r12d, 1
0x18005c162  and     r12b, 1
0x18005c166  mov     r8b, r12b
0x18005c169  lea     rdx, aAcceptpause; "AcceptPause"
0x18005c170  mov     rcx, rbx
0x18005c173  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18005c179  mov     r8d, [rsp+0E8h+var_98]
0x18005c17e  lea     rdx, aProcessid; "ProcessId"
0x18005c185  mov     rcx, rbx
0x18005c188  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18005c18e  mov     r8d, r13d
0x18005c191  lea     rdx, aExitcode; "ExitCode"
0x18005c198  mov     rcx, rbx
0x18005c19b  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18005c1a1  mov     r8d, [rsp+0E8h+var_A4]
0x18005c1a6  lea     rdx, aServicespecifi; "ServiceSpecificExitCode"
0x18005c1ad  mov     rcx, rbx
0x18005c1b0  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18005c1b6  mov     r8d, [rsp+0E8h+var_A0]
0x18005c1bb  lea     rdx, aCheckpoint; "CheckPoint"
0x18005c1c2  mov     rcx, rbx
0x18005c1c5  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18005c1cb  mov     r8d, [rsp+0E8h+var_9C]
0x18005c1d0  lea     rdx, aWaithint; "WaitHint"
0x18005c1d7  mov     rcx, rbx
0x18005c1da  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18005c1e0  jmp     short loc_18005C1FC
0x18005c1e2  mov     dil, 1
0x18005c1e5  lea     r8, aUnknown_0; "Unknown"
0x18005c1ec  lea     rdx, aState; "State"
0x18005c1f3  mov     rcx, rbx
0x18005c1f6  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c1fc  xor     r13d, r13d
0x18005c1ff  test    [rsp+0E8h+arg_20], 400h
0x18005c20a  jz      short loc_18005C263
0x18005c20c  test    rsi, rsi
0x18005c20f  jz      short loc_18005C24C
0x18005c211  xorps   xmm0, xmm0
0x18005c214  movups  xmmword ptr [rsp+0E8h+ServiceStatus], xmm0
0x18005c219  movups  xmmword ptr [rsp+0E8h+ServiceStatus+0Ch], xmm0
0x18005c221  test    dil, dil
0x18005c224  jz      short loc_18005C243
0x18005c226  lea     r8, [rsp+0E8h+ServiceStatus]; lpServiceStatus
0x18005c22b  lea     edx, [r13+4]; dwControl
0x18005c22f  mov     rcx, rsi; hService
0x18005c232  call    cs:__imp_ControlService
0x18005c238  test    eax, eax
0x18005c23a  lea     r8, aDegraded; "Degraded"
0x18005c241  jz      short loc_18005C253
0x18005c243  lea     r8, aOk; "OK"
0x18005c24a  jmp     short loc_18005C253
0x18005c24c  lea     r8, aUnknown_1; "UNKNOWN"
0x18005c253  lea     rdx, aStatus; "Status"
0x18005c25a  mov     rcx, rbx
0x18005c25d  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c263  mov     r12, [rsp+0E8h+var_90]
0x18005c268  test    r14d, r14d
0x18005c26b  jz      loc_18005C5C5
0x18005c271  mov     r8, r12
0x18005c274  lea     rdx, aCaption; "Caption"
0x18005c27b  mov     rcx, rbx
0x18005c27e  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c284  mov     r8, r12
0x18005c287  lea     rdx, aDisplayname; "DisplayName"
0x18005c28e  mov     rcx, rbx
0x18005c291  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c297  test    rsi, rsi
0x18005c29a  jz      loc_18005C32C
0x18005c2a0  mov     [rsp+0E8h+cbBufSize], r13d
0x18005c2a5  lea     rax, [rsp+0E8h+cbBufSize]
0x18005c2aa  mov     [rsp+0E8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005c2af  xor     r9d, r9d; cbBufSize
0x18005c2b2  xor     r8d, r8d; lpBuffer
0x18005c2b5  lea     edx, [r9+1]; dwInfoLevel
0x18005c2b9  mov     rcx, rsi; hService
0x18005c2bc  call    cs:__imp_QueryServiceConfig2W
0x18005c2c2  test    eax, eax
0x18005c2c4  jnz     short loc_18005C32C
0x18005c2c6  call    cs:__imp_GetLastError
0x18005c2cc  cmp     eax, 7Ah ; 'z'
0x18005c2cf  jnz     short loc_18005C32C
0x18005c2d1  mov     ecx, [rsp+0E8h+cbBufSize]; unsigned __int64
0x18005c2d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c2da  mov     rdi, rax
0x18005c2dd  mov     [rsp+0E8h+var_90], rax
0x18005c2e2  test    rax, rax
0x18005c2e5  jz      short loc_18005C32C
0x18005c2e7  lea     rax, [rsp+0E8h+cbBufSize]
0x18005c2ec  mov     [rsp+0E8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005c2f1  mov     r9d, [rsp+0E8h+cbBufSize]; cbBufSize
0x18005c2f6  mov     r8, rdi; lpBuffer
0x18005c2f9  mov     edx, 1; dwInfoLevel
0x18005c2fe  mov     rcx, rsi; hService
0x18005c301  call    cs:__imp_QueryServiceConfig2W
0x18005c307  test    eax, eax
0x18005c309  jz      short loc_18005C31F
0x18005c30b  mov     r8, [rdi]
0x18005c30e  lea     rdx, aDescription; "Description"
0x18005c315  mov     rcx, rbx
0x18005c318  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18005c31e  nop
0x18005c31f  mov     rcx, rdi; void *
0x18005c322  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005c327  mov     rdi, r13
0x18005c32a  jmp     short loc_18005C334
0x18005c32c  mov     rdi, r13
0x18005c32f  test    rsi, rsi
0x18005c332  jz      short loc_18005C3AC
0x18005c334  mov     [rsp+0E8h+cbBufSize], r13d
0x18005c339  lea     r9, [rsp+0E8h+cbBufSize]; pcbBytesNeeded
0x18005c33e  xor     r8d, r8d; cbBufSize
0x18005c341  xor     edx, edx; lpServiceConfig
0x18005c343  mov     rcx, rsi; hService
0x18005c346  call    cs:__imp_QueryServiceConfigW
0x18005c34c  mov     r14d, eax
0x18005c34f  test    eax, eax
0x18005c351  jnz     short loc_18005C3AF
0x18005c353  call    cs:__imp_GetLastError
0x18005c359  cmp     eax, 7Ah ; 'z'
0x18005c35c  jnz     short loc_18005C3AF
0x18005c35e  mov     ecx, [rsp+0E8h+cbBufSize]; unsigned __int64
0x18005c362  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c367  mov     rdi, rax
0x18005c36a  test    rax, rax
0x18005c36d  jz      short loc_18005C399
0x18005c36f  mov     r8d, [rsp+0E8h+cbBufSize]; Size
0x18005c374  xor     edx, edx; Val
0x18005c376  mov     rcx, rax; void *
0x18005c379  call    memset_0
0x18005c37e  lea     r9, [rsp+0E8h+cbBufSize]; pcbBytesNeeded
0x18005c383  mov     r8d, [rsp+0E8h+cbBufSize]; cbBufSize
0x18005c388  mov     rdx, rdi; lpServiceConfig
0x18005c38b  mov     rcx, rsi; hService
0x18005c38e  call    cs:__imp_QueryServiceConfigW
0x18005c394  mov     r14d, eax
0x18005c397  jmp     short loc_18005C3AF
0x18005c399  mov     rcx, rsi; hSCObject
0x18005c39c  call    cs:__imp_CloseServiceHandle
0x18005c3a2  mov     eax, 80041006h
0x18005c3a7  jmp     loc_18005C649
0x18005c3ac  mov     r14d, r13d
0x18005c3af  mov     [rsp+0E8h+var_90], rdi
0x18005c3b4  mov     rcx, rbx
0x18005c3b7  cmp     r14d, 1
0x18005c3bb  jnz     loc_18005C57A
0x18005c3c1  mov     r8d, [rdi+20h]
0x18005c3c5  lea     rdx, aTagid; "TagId"
0x18005c3cc  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18005c3d2  mov     eax, [rdi]
0x18005c3d4  btr     eax, 8
0x18005c3d8  sub     eax, r14d
0x18005c3db  jz      short loc_18005C41A
0x18005c3dd  sub     eax, r14d
0x18005c3e0  jz      short loc_18005C411
0x18005c3e2  sub     eax, 0Eh
0x18005c3e5  jz      short loc_18005C408
0x18005c3e7  lea     rdx, aServicetype; "ServiceType"
0x18005c3ee  mov     rcx, rbx
0x18005c3f1  cmp     eax, 10h
0x18005c3f4  jz      short loc_18005C3FF
  ... truncated ...
```
