# CWin32Service::LoadPropertyValuesWin2K(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS &,ushort const *,CInstance *,ulong,CAdvApi32Api *)

- ea: `0x1800143b0`
- end: `0x180014c52`
- name: `?LoadPropertyValuesWin2K@CWin32Service@@AEAAJPEAUSC_HANDLE__@@AEAU_SERVICE_STATUS_PROCESS@@PEBGPEAVCInstance@@KPEAVCAdvApi32Api@@@Z`
- size: `2210`
- prototype: `int(CWin32Service *__hidden this, struct SC_HANDLE__ *, struct _SERVICE_STATUS_PROCESS *, const unsigned __int16 *, struct CInstance *, unsigned int, struct CAdvApi32Api *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014044`

## callees

- `0x1800143b0`
- `0x18008bb9c`
- `0x1800fc902`
- `0x1800fc980`

## import_xrefs

- `msvcrt!free` at `0x18001463e`
- `msvcrt!free` at `0x180014709`
- `msvcrt!free` at `0x1800147e0`
- `msvcrt!free` at `0x18001463e`
- `msvcrt!free` at `0x180014709`
- `msvcrt!free` at `0x1800147e0`
- `msvcrt!malloc` at `0x1800145e8`
- `msvcrt!malloc` at `0x1800146b7`
- `msvcrt!malloc` at `0x18001474d`
- `msvcrt!malloc` at `0x1800145e8`
- `msvcrt!malloc` at `0x1800146b7`
- `msvcrt!malloc` at `0x18001474d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001473a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001489c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001473a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001489c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800144ea`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800144ff`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180014514`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180014529`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001453c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800148d1`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800144ea`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800144ff`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180014514`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x180014529`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18001453c`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x1800148d1`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180014843`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x180014843`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800144a2`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800144ba`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800144d5`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180014634`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001493c`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180014bf2`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800144a2`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800144ba`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x1800144d5`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180014634`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x18001493c`
- `framedynos!?Setbool@CInstance@@QEAA_NPEBG_N@Z` at `0x180014bf2`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001448a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014596`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001465f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014672`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800146ff`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800147a3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800147ba`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800147d1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001480e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014825`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014856`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014921`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001497e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800149a1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800149e3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014a29`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014a60`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014a80`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014b49`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014b86`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001448a`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014596`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001465f`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014672`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800146ff`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800147a3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800147ba`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800147d1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001480e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014825`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014856`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014921`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18001497e`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800149a1`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x1800149e3`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014a29`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014a60`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014a80`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014b49`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x180014b86`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180014830`
- `framedynos!?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ` at `0x180014830`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001488e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001488e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800147f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800147f7`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180014577`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180014577`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001472d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001477a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001472d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18001477a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800145cb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180014619`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001469e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800146e8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800145cb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180014619`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18001469e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800146e8`

## string_xrefs

- `0x1800147fd`: `Win32_Service`
- `0x1800144e0`: `ProcessId`
- `0x18001450a`: `ServiceSpecificExitCode`
- `0x18001479c`: `ServiceType`
- `0x1800148f4`: `ServiceType`
- `0x180014917`: `ServiceType`
- `0x180014a76`: `PathName`
- `0x180014814`: `Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWin32Service::LoadPropertyValuesWin2K(
        CWin32Service *this,
        SC_HANDLE a2,
        struct _SERVICE_STATUS_PROCESS *a3,
        unsigned __int16 *a4,
        struct CInstance *a5,
        unsigned int a6,
        struct CAdvApi32Api *a7)
{
  unsigned int v8; // r13d
  unsigned int v9; // r12d
  SC_HANDLE v10; // rbx
  DWORD dwCurrentState; // eax
  DWORD dwControlsAccepted; // r15d
  DWORD dwWaitHint; // esi
  bool v14; // r8
  _DWORD *v15; // rax
  _DWORD *v16; // rsi
  const unsigned __int16 *v17; // r14
  const unsigned __int16 **v18; // rax
  const unsigned __int16 **v19; // rsi
  struct _QUERY_SERVICE_CONFIGW *v20; // rsi
  BOOL v21; // r15d
  DWORD v22; // r15d
  struct _QUERY_SERVICE_CONFIGW *v23; // rax
  const struct CHString *LocalComputerName; // rax
  DWORD LastError; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  const unsigned __int16 *v30; // r8
  DWORD dwStartType; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  const unsigned __int16 *v34; // r8
  DWORD dwErrorControl; // eax
  const unsigned __int16 *v36; // r8
  const unsigned __int16 *lpBinaryPathName; // r8
  const unsigned __int16 *lpServiceStartName; // r8
  const unsigned __int16 *lpDisplayName; // r8
  DWORD v40; // eax
  DWORD v41; // eax
  DWORD v42; // eax
  DWORD v43; // eax
  DWORD v44; // eax
  bool v45; // [rsp+30h] [rbp-A8h]
  DWORD cbBufSize; // [rsp+34h] [rbp-A4h] BYREF
  unsigned __int16 *v47; // [rsp+38h] [rbp-A0h]
  DWORD v48; // [rsp+40h] [rbp-98h]
  DWORD dwWin32ExitCode; // [rsp+44h] [rbp-94h]
  DWORD dwServiceSpecificExitCode; // [rsp+48h] [rbp-90h]
  DWORD dwCheckPoint; // [rsp+4Ch] [rbp-8Ch]
  void *v52; // [rsp+50h] [rbp-88h]
  int v53; // [rsp+58h] [rbp-80h] BYREF
  int v54; // [rsp+5Ch] [rbp-7Ch] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-78h] BYREF
  SC_HANDLE v56; // [rsp+68h] [rbp-70h]
  Provider *v57; // [rsp+70h] [rbp-68h]
  _SERVICE_STATUS ServiceStatus; // [rsp+78h] [rbp-60h] BYREF

  v47 = a4;
  v57 = this;
  v8 = a6 & 0x1FF800;
  if ( (a6 & 0x7FE) == 0 && !v8 )
  {
    v9 = 0;
    v17 = a4;
LABEL_42:
    CInstance::SetCharSplat(a5, L"CreationClassName", L"Win32_Service");
    CInstance::SetCharSplat(a5, L"SystemCreationClassName", L"Win32_ComputerSystem");
    LocalComputerName = Provider::GetLocalComputerName(v57);
    CInstance::SetCHString(a5, L"SystemName", LocalComputerName);
    CInstance::SetCharSplat(a5, L"Name", v17);
    return v9;
  }
  v9 = 0;
  v10 = 0;
  v56 = 0;
  LODWORD(v52) = a6 & 0x400;
  if ( (a6 & 0x400) == 0 && (v48 = 0, !v8)
    || (v10 = OpenServiceW(a2, a4, 0x85u), v56 = v10, LastError = GetLastError(), v48 = LastError, v10)
    || LastError != 1060 && LastError != 123 )
  {
    if ( (a6 & 0x7FE) == 0 )
      goto LABEL_12;
    cbBufSize = a3->dwProcessId;
    dwCurrentState = a3->dwCurrentState;
    dwControlsAccepted = a3->dwControlsAccepted;
    dwWin32ExitCode = a3->dwWin32ExitCode;
    dwServiceSpecificExitCode = a3->dwServiceSpecificExitCode;
    dwCheckPoint = a3->dwCheckPoint;
    dwWaitHint = a3->dwWaitHint;
    if ( dwCurrentState == 1 )
    {
      CInstance::SetCharSplat(a5, L"State", L"Stopped");
      v14 = 0;
      goto LABEL_7;
    }
    if ( dwCurrentState == 4 )
    {
      CInstance::SetCharSplat(a5, L"State", L"Running");
    }
    else
    {
      v40 = dwCurrentState - 2;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( v41 )
        {
          v42 = v41 - 2;
          if ( v42 )
          {
            v43 = v42 - 1;
            if ( v43 )
            {
              if ( v43 == 1 )
                CInstance::SetCharSplat(a5, L"State", L"Paused");
              else
                CInstance::SetCharSplat(a5, L"State", L"Unknown");
              v14 = 1;
LABEL_7:
              v45 = v14;
              CInstance::Setbool(a5, L"Started", v14);
              CInstance::Setbool(a5, L"AcceptStop", dwControlsAccepted & 1);
              CInstance::Setbool(a5, L"AcceptPause", (dwControlsAccepted & 2) != 0);
              CInstance::SetDWORD(a5, L"ProcessId", cbBufSize);
              CInstance::SetDWORD(a5, L"ExitCode", dwWin32ExitCode);
              CInstance::SetDWORD(a5, L"ServiceSpecificExitCode", dwServiceSpecificExitCode);
              CInstance::SetDWORD(a5, L"CheckPoint", dwCheckPoint);
              CInstance::SetDWORD(a5, L"WaitHint", dwWaitHint);
              if ( (_DWORD)v52 )
              {
                if ( v10 )
                {
                  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
                  if ( v45 && !ControlService(v10, 4u, &ServiceStatus) )
                    CInstance::SetCharSplat(a5, L"Status", L"Degraded");
                  else
                    CInstance::SetCharSplat(a5, L"Status", L"OK");
                }
                else
                {
                  CInstance::SetCharSplat(a5, L"Status", L"UNKNOWN");
                }
              }
LABEL_12:
              if ( (a6 & 0x1000000) != 0 && v10 )
              {
                cbBufSize = 0;
                if ( QueryServiceConfig2W(v10, 3u, 0, 0, &cbBufSize) )
                {
                  CInstance::Setbool(a5, L"DelayedAutoStart", MEMORY[0] != 0);
                }
                else if ( GetLastError() == 122 )
                {
                  v15 = malloc(cbBufSize);
                  v16 = v15;
                  if ( !v15 )
                  {
                    v53 = 0;
                    throw (CHeap_Exception *)&v53;
                  }
                  v52 = v15;
                  try
                  {
                    if ( QueryServiceConfig2W(v10, 3u, (LPBYTE)v15, cbBufSize, &cbBufSize) )
                      CInstance::Setbool(a5, L"DelayedAutoStart", *v16 != 0);
                  }
                  catch ( ... )
                  {
                    if ( v52 )
                      free(v52);
                    throw;
                  }
                  free(v16);
                }
              }
              v17 = v47;
              if ( !v8 )
                goto LABEL_39;
              CInstance::SetCharSplat(a5, L"Caption", v47);
              CInstance::SetCharSplat(a5, L"DisplayName", v17);
              if ( v10 )
              {
                cbBufSize = 0;
                if ( !QueryServiceConfig2W(v10, 1u, 0, 0, &cbBufSize) && GetLastError() == 122 )
                {
                  v18 = (const unsigned __int16 **)malloc(cbBufSize);
                  v19 = v18;
                  if ( !v18 )
                  {
                    v54 = 0;
                    throw (CHeap_Exception *)&v54;
                  }
                  v47 = (unsigned __int16 *)v18;
                  try
                  {
                    if ( QueryServiceConfig2W(v10, 1u, (LPBYTE)v18, cbBufSize, &cbBufSize) )
                      CInstance::SetCharSplat(a5, L"Description", *v19);
                  }
                  catch ( ... )
                  {
                    if ( v47 )
                      free(v47);
                    throw;
                  }
                  free(v19);
                }
              }
              v20 = 0;
              if ( v10 )
              {
                cbBufSize = 0;
                v21 = QueryServiceConfigW(v10, 0, 0, &cbBufSize);
                if ( !v21 && GetLastError() == 122 )
                {
                  v22 = cbBufSize;
                  v23 = (struct _QUERY_SERVICE_CONFIGW *)malloc(cbBufSize);
                  v20 = v23;
                  if ( !v23 )
                  {
                    pExceptionObject = 0;
                    throw (CHeap_Exception *)&pExceptionObject;
                  }
                  memset_0(v23, 0, v22);
                  v21 = QueryServiceConfigW(v10, v20, v22, &cbBufSize);
                }
              }
              else
              {
                v21 = 0;
              }
              v47 = (unsigned __int16 *)v20;
              if ( !v21 )
              {
                CInstance::SetCharSplat(a5, L"ServiceType", L"Unknown");
                CInstance::SetCharSplat(a5, L"StartMode", L"Unknown");
                CInstance::SetCharSplat(a5, L"ErrorControl", L"Unknown");
LABEL_37:
                if ( v20 )
                  free(v20);
LABEL_39:
                if ( !v10 && v48 == 5 )
                  v9 = -2147217405;
                if ( v10 )
                  CloseServiceHandle(v10);
                goto LABEL_42;
              }
              CInstance::SetDWORD(a5, L"TagId", v20->dwTagId);
              v27 = v20->dwServiceType & 0xFFFFFEFF;
              if ( v27 == 16 )
              {
                v30 = L"Own Process";
              }
              else
              {
                v28 = v27 - 1;
                if ( v28 )
                {
                  v29 = v28 - 1;
                  if ( v29 )
                  {
                    if ( v29 == 30 )
                      CInstance::SetCharSplat(a5, L"ServiceType", L"Share Process");
                    else
                      CInstance::SetCharSplat(a5, L"ServiceType", L"Unknown");
LABEL_54:
                    CInstance::Setbool(a5, L"DesktopInteract", v20->dwServiceType & 0x100);
                    dwStartType = v20->dwStartType;
                    if ( dwStartType == 2 )
                    {
                      v34 = L"Auto";
                    }
                    else if ( dwStartType )
                    {
                      v32 = dwStartType - 1;
                      if ( v32 )
                      {
                        v33 = v32 - 2;
                        if ( v33 )
                        {
                          if ( v33 == 1 )
                            CInstance::SetCharSplat(a5, L"StartMode", L"Disabled");
                          else
                            CInstance::SetCharSplat(a5, L"StartMode", L"Unknown");
LABEL_61:
                          dwErrorControl = v20->dwErrorControl;
                          if ( dwErrorControl == 1 )
                          {
                            v36 = L"Normal";
                          }
                          else if ( dwErrorControl )
                          {
                            v44 = dwErrorControl - 2;
                            if ( v44 )
                            {
                              if ( v44 == 1 )
                                CInstance::SetCharSplat(a5, L"ErrorControl", L"Critical");
                              else
                                CInstance::SetCharSplat(a5, L"ErrorControl", L"Unknown");
                              goto LABEL_64;
                            }
                            v36 = L"Severe";
                          }
                          else
                          {
                            v36 = L"Ignore";
                          }
                          CInstance::SetCharSplat(a5, L"ErrorControl", v36);
LABEL_64:
                          lpBinaryPathName = v20->lpBinaryPathName;
                          if ( lpBinaryPathName && *lpBinaryPathName )
                            CInstance::SetCharSplat(a5, L"PathName", lpBinaryPathName);
                          lpServiceStartName = v20->lpServiceStartName;
                          if ( lpServiceStartName && *lpServiceStartName )
                            CInstance::SetCharSplat(a5, L"StartName", lpServiceStartName);
                          lpDisplayName = v20->lpDisplayName;
                          if ( lpDisplayName && *lpDisplayName )
                          {
                            CInstance::SetCharSplat(a5, L"DisplayName", lpDisplayName);
                            CInstance::SetCharSplat(a5, L"Caption", v20->lpDisplayName);
                          }
                          goto LABEL_37;
                        }
                        v34 = L"Manual";
                      }
                      else
                      {
                        v34 = L"System";
                      }
                    }
                    else
                    {
                      v34 = L"Boot";
                    }
                    CInstance::SetCharSplat(a5, L"StartMode", v34);
                    goto LABEL_61;
                  }
                  v30 = L"File System Driver";
                }
                else
                {
                  v30 = L"Kernel Driver";
                }
              }
              CInstance::SetCharSplat(a5, L"ServiceType", v30);
              goto LABEL_54;
            }
            CInstance::SetCharSplat(a5, L"State", L"Pause Pending");
          }
          else
          {
            CInstance::SetCharSplat(a5, L"State", L"Continue Pending");
          }
        }
        else
        {
          CInstance::SetCharSplat(a5, L"State", L"Stop Pending");
        }
      }
      else
      {
        CInstance::SetCharSplat(a5, L"State", L"Start Pending");
      }
    }
    v14 = 1;
    goto LABEL_7;
  }
  return 2147749890LL;
}

```

## disassembly

```asm
0x1800143b0  push    rbx
0x1800143b2  push    rsi
0x1800143b3  push    rdi
0x1800143b4  push    r12
0x1800143b6  push    r13
0x1800143b8  push    r14
0x1800143ba  push    r15
0x1800143bc  sub     rsp, 0A0h
0x1800143c3  mov     rax, cs:__security_cookie
0x1800143ca  xor     rax, rsp
0x1800143cd  mov     [rsp+0D8h+var_40], rax
0x1800143d5  mov     [rsp+0D8h+var_A0], r9
0x1800143da  mov     rsi, r8
0x1800143dd  mov     r10, rdx
0x1800143e0  mov     [rsp+0D8h+var_68], rcx
0x1800143e5  mov     rdi, [rsp+0D8h+arg_20]
0x1800143ed  mov     r14d, [rsp+0D8h+arg_28]
0x1800143f5  mov     r15d, r14d
0x1800143f8  mov     r13d, r14d
0x1800143fb  and     r13d, 1FF800h
0x180014402  and     r15d, 7FEh
0x180014409  jz      loc_180014ABE
0x18001440f  xor     r12d, r12d
0x180014412  mov     ebx, r12d
0x180014415  mov     [rsp+0D8h+var_70], rbx
0x18001441a  mov     eax, r14d
0x18001441d  and     eax, 400h
0x180014422  mov     dword ptr [rsp+0D8h+var_88], eax
0x180014426  jnz     loc_180014882
0x18001442c  mov     [rsp+0D8h+var_98], r12d
0x180014431  test    r13d, r13d
0x180014434  jnz     loc_180014882
0x18001443a  and     r14d, 1000000h
0x180014441  test    r15d, r15d
0x180014444  jz      loc_18001459C
0x18001444a  mov     eax, [rsi+1Ch]
0x18001444d  mov     [rsp+0D8h+cbBufSize], eax
0x180014451  mov     eax, [rsi+4]
0x180014454  mov     r15d, [rsi+8]
0x180014458  mov     ecx, [rsi+0Ch]
0x18001445b  mov     [rsp+0D8h+var_94], ecx
0x18001445f  mov     ecx, [rsi+10h]
0x180014462  mov     [rsp+0D8h+var_90], ecx
0x180014466  mov     ecx, [rsi+14h]
0x180014469  mov     [rsp+0D8h+var_8C], ecx
0x18001446d  mov     esi, [rsi+18h]
0x180014470  cmp     eax, 1
0x180014473  jnz     loc_180014A0F
0x180014479  lea     r8, aStopped; "Stopped"
0x180014480  lea     rdx, aState; "State"
0x180014487  mov     rcx, rdi
0x18001448a  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180014490  xor     r8b, r8b
0x180014493  mov     [rsp+0D8h+var_A8], r8b
0x180014498  lea     rdx, aStarted; "Started"
0x18001449f  mov     rcx, rdi
0x1800144a2  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800144a8  movzx   r8d, r15b
0x1800144ac  and     r8b, 1
0x1800144b0  lea     rdx, aAcceptstop; "AcceptStop"
0x1800144b7  mov     rcx, rdi
0x1800144ba  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800144c0  shr     r15d, 1
0x1800144c3  and     r15b, 1
0x1800144c7  movzx   r8d, r15b
0x1800144cb  lea     rdx, aAcceptpause; "AcceptPause"
0x1800144d2  mov     rcx, rdi
0x1800144d5  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x1800144db  mov     r8d, [rsp+0D8h+cbBufSize]
0x1800144e0  lea     rdx, aProcessid; "ProcessId"
0x1800144e7  mov     rcx, rdi
0x1800144ea  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x1800144f0  mov     r8d, [rsp+0D8h+var_94]
0x1800144f5  lea     rdx, aExitcode; "ExitCode"
0x1800144fc  mov     rcx, rdi
0x1800144ff  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180014505  mov     r8d, [rsp+0D8h+var_90]
0x18001450a  lea     rdx, aServicespecifi; "ServiceSpecificExitCode"
0x180014511  mov     rcx, rdi
0x180014514  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001451a  mov     r8d, [rsp+0D8h+var_8C]
0x18001451f  lea     rdx, aCheckpoint; "CheckPoint"
0x180014526  mov     rcx, rdi
0x180014529  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18001452f  mov     r8d, esi
0x180014532  lea     rdx, aWaithint; "WaitHint"
0x180014539  mov     rcx, rdi
0x18001453c  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x180014542  cmp     dword ptr [rsp+0D8h+var_88], 0
0x180014547  jz      short loc_18001459C
0x180014549  test    rbx, rbx
0x18001454c  jz      loc_180014BD0
0x180014552  xorps   xmm0, xmm0
0x180014555  xor     eax, eax
0x180014557  movups  xmmword ptr [rsp+0D8h+ServiceStatus.dwServiceType], xmm0
0x18001455c  movups  xmmword ptr [rsp+0D8h+ServiceStatus.dwWin32ExitCode], xmm0
0x180014564  cmp     [rsp+0D8h+var_A8], al
0x180014568  jz      short loc_180014585
0x18001456a  lea     r8, [rsp+0D8h+ServiceStatus]; lpServiceStatus
0x18001456f  mov     edx, 4; dwControl
0x180014574  mov     rcx, rbx; hService
0x180014577  call    cs:__imp_ControlService
0x18001457d  test    eax, eax
0x18001457f  jz      loc_180014BC4
0x180014585  lea     r8, aOk; "OK"
0x18001458c  lea     rdx, aStatus; "Status"
0x180014593  mov     rcx, rdi
0x180014596  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001459c  test    r14d, r14d
0x18001459f  jz      loc_180014644
0x1800145a5  test    rbx, rbx
0x1800145a8  jz      loc_180014644
0x1800145ae  mov     [rsp+0D8h+cbBufSize], r12d
0x1800145b3  lea     rax, [rsp+0D8h+cbBufSize]
0x1800145b8  mov     [rsp+0D8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800145bd  xor     r9d, r9d; cbBufSize
0x1800145c0  xor     r8d, r8d; lpBuffer
0x1800145c3  mov     edx, 3; dwInfoLevel
0x1800145c8  mov     rcx, rbx; hService
0x1800145cb  call    cs:__imp_QueryServiceConfig2W
0x1800145d1  test    eax, eax
0x1800145d3  jnz     loc_180014BDC
0x1800145d9  call    cs:__imp_GetLastError
0x1800145df  cmp     eax, 7Ah ; 'z'
0x1800145e2  jnz     short loc_180014644
0x1800145e4  mov     ecx, [rsp+0D8h+cbBufSize]; Size
0x1800145e8  call    cs:__imp_malloc
0x1800145ee  mov     rsi, rax
0x1800145f1  test    rax, rax
0x1800145f4  jz      loc_180014B00
0x1800145fa  mov     [rsp+0D8h+var_88], rax
0x1800145ff  lea     rax, [rsp+0D8h+cbBufSize]
0x180014604  mov     [rsp+0D8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180014609  mov     r9d, [rsp+0D8h+cbBufSize]; cbBufSize
0x18001460e  mov     r8, rsi; lpBuffer
0x180014611  mov     edx, 3; dwInfoLevel
0x180014616  mov     rcx, rbx; hService
0x180014619  call    cs:__imp_QueryServiceConfig2W
0x18001461f  test    eax, eax
0x180014621  jz      short loc_18001463B
0x180014623  cmp     dword ptr [rsi], 0
0x180014626  setnz   r8b
0x18001462a  lea     rdx, aDelayedautosta; "DelayedAutoStart"
0x180014631  mov     rcx, rdi
0x180014634  call    cs:__imp_?Setbool@CInstance@@QEAA_NPEBG_N@Z; CInstance::Setbool(ushort const *,bool)
0x18001463a  nop
0x18001463b  mov     rcx, rsi; Block
0x18001463e  call    cs:__imp_free
0x180014644  mov     r14, [rsp+0D8h+var_A0]
0x180014649  test    r13d, r13d
0x18001464c  jz      loc_1800147E6
0x180014652  mov     r8, r14
0x180014655  lea     rdx, aCaption; "Caption"
0x18001465c  mov     rcx, rdi
0x18001465f  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180014665  mov     r8, r14
0x180014668  lea     rdx, aDisplayname; "DisplayName"
0x18001466f  mov     rcx, rdi
0x180014672  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180014678  test    rbx, rbx
0x18001467b  jz      loc_18001470F
0x180014681  mov     [rsp+0D8h+cbBufSize], r12d
0x180014686  lea     rax, [rsp+0D8h+cbBufSize]
0x18001468b  mov     [rsp+0D8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180014690  xor     r9d, r9d; cbBufSize
0x180014693  xor     r8d, r8d; lpBuffer
0x180014696  mov     edx, 1; dwInfoLevel
0x18001469b  mov     rcx, rbx; hService
0x18001469e  call    cs:__imp_QueryServiceConfig2W
0x1800146a4  test    eax, eax
0x1800146a6  jnz     short loc_18001470F
0x1800146a8  call    cs:__imp_GetLastError
0x1800146ae  cmp     eax, 7Ah ; 'z'
0x1800146b1  jnz     short loc_18001470F
0x1800146b3  mov     ecx, [rsp+0D8h+cbBufSize]; Size
0x1800146b7  call    cs:__imp_malloc
0x1800146bd  mov     rsi, rax
0x1800146c0  test    rax, rax
0x1800146c3  jz      loc_180014AE9
0x1800146c9  mov     [rsp+0D8h+var_A0], rax
0x1800146ce  lea     rax, [rsp+0D8h+cbBufSize]
0x1800146d3  mov     [rsp+0D8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800146d8  mov     r9d, [rsp+0D8h+cbBufSize]; cbBufSize
0x1800146dd  mov     r8, rsi; lpBuffer
0x1800146e0  mov     edx, 1; dwInfoLevel
0x1800146e5  mov     rcx, rbx; hService
0x1800146e8  call    cs:__imp_QueryServiceConfig2W
0x1800146ee  test    eax, eax
0x1800146f0  jz      short loc_180014706
0x1800146f2  mov     r8, [rsi]
0x1800146f5  lea     rdx, aDescription; "Description"
0x1800146fc  mov     rcx, rdi
0x1800146ff  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180014705  nop
0x180014706  mov     rcx, rsi; Block
0x180014709  call    cs:__imp_free
0x18001470f  mov     rsi, r12
0x180014712  test    rbx, rbx
0x180014715  jz      loc_180014AB6
0x18001471b  mov     [rsp+0D8h+cbBufSize], r12d
0x180014720  lea     r9, [rsp+0D8h+cbBufSize]; pcbBytesNeeded
0x180014725  xor     r8d, r8d; cbBufSize
0x180014728  xor     edx, edx; lpServiceConfig
0x18001472a  mov     rcx, rbx; hService
0x18001472d  call    cs:__imp_QueryServiceConfigW
0x180014733  mov     r15d, eax
0x180014736  test    eax, eax
0x180014738  jnz     short loc_180014783
0x18001473a  call    cs:__imp_GetLastError
0x180014740  cmp     eax, 7Ah ; 'z'
0x180014743  jnz     short loc_180014783
0x180014745  mov     r15d, [rsp+0D8h+cbBufSize]
0x18001474a  mov     ecx, r15d; Size
0x18001474d  call    cs:__imp_malloc
0x180014753  mov     rsi, rax
0x180014756  test    rax, rax
0x180014759  jz      loc_180014AD2
0x18001475f  mov     r8d, r15d; Size
0x180014762  xor     edx, edx; Val
0x180014764  mov     rcx, rax; void *
0x180014767  call    memset_0
0x18001476c  lea     r9, [rsp+0D8h+cbBufSize]; pcbBytesNeeded
0x180014771  mov     r8d, r15d; cbBufSize
0x180014774  mov     rdx, rsi; lpServiceConfig
0x180014777  mov     rcx, rbx; hService
0x18001477a  call    cs:__imp_QueryServiceConfigW
0x180014780  mov     r15d, eax
0x180014783  mov     [rsp+0D8h+var_A0], rsi
0x180014788  mov     rcx, rdi
0x18001478b  cmp     r15d, 1
0x18001478f  jz      loc_1800148C6
0x180014795  lea     r8, aUnknown_0; "Unknown"
0x18001479c  lea     rdx, aServicetype; "ServiceType"
0x1800147a3  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800147a9  lea     r8, aUnknown_0; "Unknown"
0x1800147b0  lea     rdx, aStartmode; "StartMode"
0x1800147b7  mov     rcx, rdi
0x1800147ba  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800147c0  lea     r8, aUnknown_0; "Unknown"
0x1800147c7  lea     rdx, aErrorcontrol; "ErrorControl"
0x1800147ce  mov     rcx, rdi
0x1800147d1  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x1800147d7  nop
0x1800147d8  test    rsi, rsi
0x1800147db  jz      short loc_1800147E6
0x1800147dd  mov     rcx, rsi; Block
0x1800147e0  call    cs:__imp_free
0x1800147e6  test    rbx, rbx
0x1800147e9  jz      loc_1800149F9
0x1800147ef  test    rbx, rbx
0x1800147f2  jz      short loc_1800147FD
0x1800147f4  mov     rcx, rbx; hSCObject
0x1800147f7  call    cs:__imp_CloseServiceHandle
0x1800147fd  lea     r8, aWin32Service; "Win32_Service"
0x180014804  lea     rdx, aCreationclassn; "CreationClassName"
0x18001480b  mov     rcx, rdi
0x18001480e  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x180014814  lea     r8, aWin32Computers_0; "Win32_ComputerSystem"
0x18001481b  lea     rdx, aSystemcreation; "SystemCreationClassName"
0x180014822  mov     rcx, rdi
0x180014825  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001482b  mov     rcx, [rsp+0D8h+var_68]
0x180014830  call    cs:__imp_?GetLocalComputerName@Provider@@IEAAAEBVCHString@@XZ; Provider::GetLocalComputerName(void)
0x180014836  mov     r8, rax
0x180014839  lea     rdx, aSystemname; "SystemName"
0x180014840  mov     rcx, rdi
0x180014843  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x180014849  mov     r8, r14
0x18001484c  lea     rdx, aName; "Name"
0x180014853  mov     rcx, rdi
0x180014856  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18001485c  mov     eax, r12d
0x18001485f  mov     rcx, [rsp+0D8h+var_40]
0x180014867  xor     rcx, rsp; StackCookie
0x18001486a  call    __security_check_cookie
0x18001486f  add     rsp, 0A0h
0x180014876  pop     r15
0x180014878  pop     r14
0x18001487a  pop     r13
0x18001487c  pop     r12
0x18001487e  pop     rdi
0x18001487f  pop     rsi
0x180014880  pop     rbx
0x180014881  retn
0x180014882  mov     r8d, 85h; dwDesiredAccess
0x180014888  mov     rdx, r9; lpServiceName
0x18001488b  mov     rcx, r10; hSCManager
0x18001488e  call    cs:__imp_OpenServiceW
0x180014894  mov     rbx, rax
0x180014897  mov     [rsp+0D8h+var_70], rax
0x18001489c  call    cs:__imp_GetLastError
0x1800148a2  mov     [rsp+0D8h+var_98], eax
0x1800148a6  test    rbx, rbx
0x1800148a9  jnz     loc_18001443A
0x1800148af  cmp     eax, 424h
0x1800148b4  jz      short loc_1800148BF
0x1800148b6  cmp     eax, 7Bh ; '{'
0x1800148b9  jnz     loc_18001443A
0x1800148bf  mov     eax, 80041002h
0x1800148c4  jmp     short loc_18001485F
  ... truncated ...
```
