# CGPService::Start(ulong)

- ea: `0x180035570`
- end: `0x180035f64`
- name: `?Start@CGPService@@SAKK@Z`
- size: `2548`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180035f70`

## callees

- `0x180008e18`
- `0x1800116a8`
- `0x180034c34`
- `0x1800350e4`
- `0x1800351bc`
- `0x180035300`
- `0x1800353b4`
- `0x180035460`
- `0x180035570`
- `0x180036340`
- `0x180054ce8`
- `0x180075ec0`
- `0x18007d770`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003559a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003559a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035672`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035672`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003564e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035f44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003564e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035e59`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035809`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035c1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035809`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035c1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035e0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035ec5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035e0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180035ec5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035627`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800355f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800355f9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180035e4b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180035e4b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800357c9`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800357c9`
- `DSROLE!DsRoleFreeMemory` at `0x180035868`
- `DSROLE!DsRoleFreeMemory` at `0x1800358b5`
- `DSROLE!DsRoleFreeMemory` at `0x180035868`
- `DSROLE!DsRoleFreeMemory` at `0x1800358b5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035ab8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035afb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035b91`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035d80`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035ab8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035afb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035b91`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180035d80`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800359da`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800359da`

## string_xrefs

- `0x180035c56`: `CGPService::Start CreateThreadpoolTimer for Idle failed with 0x%x. Continuing service start.`
- `0x180035c95`: `CGPService::Start CreateThreadpoolTimer for Idle failed with 0x%x. Continuing service start.`
- `0x18003584c`: `CGPService::Start CreateThreadpoolTimer for SYSVOL failed with 0x%x. Continuing service start.`
- `0x18003589c`: `CGPService::Start CreateThreadpoolTimer for SYSVOL failed with 0x%x. Continuing service start.`
- `0x1800355b9`: `CGPService::Start with flags = 0x%x.`
- `0x1800355e3`: `CGPService::Start with flags = 0x%x.`
- `0x180035a22`: `CGPService::Start with flags = 0x%x.`
- `0x180035a4f`: `CGPService::Start with flags = 0x%x.`
- `0x1800356d8`: `CGPService::Start: InstantiateGPEngine`
- `0x1800356ff`: `CGPService::Start: InstantiateGPEngine`
- `0x180035771`: `CGPService::Start: GetAOACConfig`
- `0x180035798`: `CGPService::Start: GetAOACConfig`
- `0x1800358dc`: `CGPService::Start DsRoleGetPrimaryDomainInformation() failed with error=0x%x`
- `0x180035909`: `CGPService::Start DsRoleGetPrimaryDomainInformation() failed with error=0x%x`
- `0x180035931`: `CGPService::Start AOAC is not in use or disabled.`
- `0x18003595b`: `CGPService::Start AOAC is not in use or disabled.`
- `0x18003598e`: `CGPService::Start: RegisterServiceCtrlHandlerEx`
- `0x1800359b8`: `CGPService::Start: RegisterServiceCtrlHandlerEx`
- `0x180035b20`: `CGPService::Start: InitializeGPSubSystem`
- `0x180035b4a`: `CGPService::Start: InitializeGPSubSystem`
- `0x180035bb6`: `CGPService::Start: CreateGPSessions`
- `0x180035bdd`: `CGPService::Start: CreateGPSessions`
- `0x180035e2b`: `CGPService::Start: SetThreadpoolTimer %d. seconds for idle timer`
- `0x180035e7d`: `CGPService::Start: SetThreadpoolTimer %d. seconds for idle timer`
- `0x180035ee6`: `CGPService::Start: SetThreadpoolTimer %d. seconds for SYSVOL timer.`
- `0x180035f13`: `CGPService::Start: SetThreadpoolTimer %d. seconds for SYSVOL timer.`
- `0x180035d27`: `Updating the service status to be RUNNING.`
- `0x180035d4f`: `Updating the service status to be RUNNING.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGPService::Start(unsigned int a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  CGPService *v5; // rax
  CGPService *v6; // rax
  SERVICE_STATUS_HANDLE *v7; // rbx
  CGPApplicationService *v8; // rax
  unsigned int *v9; // rdx
  CGPApplicationService *v10; // rax
  unsigned int AOACConfig; // eax
  __int64 v12; // r15
  DWORD PrimaryDomainInformation; // eax
  int v14; // eax
  void (*v15)(unsigned int, const unsigned __int16 *, ...); // rdi
  signed int LastError; // eax
  signed int v17; // eax
  SERVICE_STATUS_HANDLE v18; // rax
  unsigned int GPSessions; // edi
  unsigned int *v20; // r13
  _DWORD *v21; // r12
  int v22; // eax
  int v23; // eax
  void (*v24)(unsigned int, const unsigned __int16 *, ...); // rbp
  signed int v25; // eax
  signed int v26; // eax
  HLOCAL hMem[10]; // [rsp+48h] [rbp-50h] BYREF
  struct _FILETIME pftDueTime; // [rsp+A8h] [rbp+10h] BYREF
  PBYTE Buffer; // [rsp+B0h] [rbp+18h] BYREF
  struct _FILETIME v30; // [rsp+B8h] [rbp+20h] BYREF

  v2 = lpCriticalSection;
  if ( lpCriticalSection )
    EnterCriticalSection(lpCriticalSection);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::Start with flags = 0x%x.", a1);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::Start with flags = 0x%x.", a1);
    }
  }
  EnableMitigations();
  CGPService::s_ServiceInitTime = GetTickCount();
  hMem[0] = 0;
  hMem[1] = 0;
  CGPOperationalEvent::ReportEventW((CGPOperationalEvent *)hMem, v3);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  CGPService::s_dwResumeTick = 0;
  Buffer = 0;
  if ( CGPService::s_pInstance )
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
  if ( !CGPService::s_hEventInitialized )
    CGPService::s_hEventInitialized = CreateEventW(0, 1, 0, 0);
  v5 = (CGPService *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  pftDueTime = (struct _FILETIME)v5;
  if ( !v5 || (v6 = CGPService::CGPService(v5), (v7 = (SERVICE_STATUS_HANDLE *)v6) == 0) )
  {
    GPSessions = 14;
    goto LABEL_158;
  }
  if ( (a1 & 0x80000000) != 0 )
    *((_DWORD *)v6 + 32) = 1;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::Start: InstantiateGPEngine");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::Start: InstantiateGPEngine");
    }
  }
  v8 = (CGPApplicationService *)operator new(0x168u, (const struct std::nothrow_t *)&std::nothrow);
  pftDueTime = (struct _FILETIME)v8;
  if ( v8 )
    v10 = CGPApplicationService::CGPApplicationService(v8, v9);
  else
    v10 = 0;
  v7[11] = (SERVICE_STATUS_HANDLE)v10;
  if ( !v10 )
  {
    GPSessions = 14;
    goto LABEL_156;
  }
  pftDueTime.dwLowDateTime = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180128070);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::Start: GetAOACConfig");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::Start: GetAOACConfig");
    }
  }
  AOACConfig = GetAOACConfig();
  v12 = AOACConfig;
  if ( AOACConfig == 1 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::Start AOAC is not in use or disabled.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::Start AOAC is not in use or disabled.");
      }
    }
    goto LABEL_66;
  }
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  if ( PrimaryDomainInformation )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          2u,
          L"CGPService::Start DsRoleGetPrimaryDomainInformation() failed with error=0x%x",
          PrimaryDomainInformation);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"CGPService::Start DsRoleGetPrimaryDomainInformation() failed with error=0x%x",
          PrimaryDomainInformation);
      }
    }
    goto LABEL_66;
  }
  v14 = *(_DWORD *)Buffer;
  if ( *(_DWORD *)Buffer <= 1u )
    pftDueTime.dwLowDateTime = 1;
  if ( (unsigned int)(v14 - 4) <= 1 )
  {
    g_sysvolTimer = CreateThreadpoolTimer(ValidateSYSVOLTimerCallback, 0, 0);
    if ( !g_sysvolTimer )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v15 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v15(
            2u,
            L"CGPService::Start CreateThreadpoolTimer for SYSVOL failed with 0x%x. Continuing service start.",
            (unsigned int)LastError);
          DsRoleFreeMemory(Buffer);
          goto LABEL_66;
        }
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v17 = GetLastError();
          if ( v17 > 0 )
            v17 = (unsigned __int16)v17 | 0x80070000;
          RedirectDebugMsg(
            2u,
            L"CGPService::Start CreateThreadpoolTimer for SYSVOL failed with 0x%x. Continuing service start.",
            (unsigned int)v17);
        }
      }
    }
  }
  DsRoleFreeMemory(Buffer);
LABEL_66:
  if ( !*((_DWORD *)v7 + 32) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::Start: RegisterServiceCtrlHandlerEx");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::Start: RegisterServiceCtrlHandlerEx");
      }
    }
    v18 = RegisterServiceCtrlHandlerExW(L"gpsvc", CGPService::GPServiceHandlerEx, v7);
    *v7 = v18;
    if ( !v18 )
    {
      *((_DWORD *)v7 + 14) = 32;
      *((_DWORD *)v7 + 16) = 0;
      *((_DWORD *)v7 + 18) = 0;
      GPSessions = GetLastError();
      goto LABEL_138;
    }
  }
  if ( (a1 & 1) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::Start with flags = 0x%x.", a1);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::Start with flags = 0x%x.", a1);
      }
    }
    *((_DWORD *)v7 + 12) = 1;
    *((_DWORD *)v7 + 11) = 1;
  }
  v20 = (unsigned int *)(v7 + 10);
  if ( *((_DWORD *)v7 + 32) )
  {
    v21 = (_DWORD *)v7 + 19;
  }
  else
  {
    GPSessions = 0;
    *((_DWORD *)v7 + 14) = 32;
    *(SERVICE_STATUS_HANDLE *)((char *)v7 + 60) = (SERVICE_STATUS_HANDLE)2;
    *(SERVICE_STATUS_HANDLE *)((char *)v7 + 68) = 0;
    *((_DWORD *)v7 + 30) = 1;
    v21 = (_DWORD *)v7 + 19;
    *((_DWORD *)v7 + 19) = 1;
    *v20 = 0;
    if ( !SetServiceStatus(*v7, (LPSERVICE_STATUS)v7 + 2) )
      GPSessions = GetLastError();
    if ( GPSessions )
      goto LABEL_156;
  }
  v22 = ++*((_DWORD *)v7 + 30);
  if ( !*((_DWORD *)v7 + 32) )
  {
    *((_DWORD *)v7 + 15) = 2;
    *v21 = v22;
    *v20 = 0;
    if ( !SetServiceStatus(*v7, (LPSERVICE_STATUS)v7 + 2) )
      GetLastError();
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::Start: InitializeGPSubSystem");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::Start: InitializeGPSubSystem");
    }
  }
  GPSessions = CGPService::InitializeGPSubSystem((CGPService *)v7);
  if ( !GPSessions )
  {
    v23 = ++*((_DWORD *)v7 + 30);
    if ( !*((_DWORD *)v7 + 32) )
    {
      *((_DWORD *)v7 + 15) = 2;
      *v21 = v23;
      *v20 = GPSessions;
      if ( !SetServiceStatus(*v7, (LPSERVICE_STATUS)v7 + 2) )
        GetLastError();
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::Start: CreateGPSessions");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::Start: CreateGPSessions");
      }
    }
    GPSessions = CGPService::CreateGPSessions((CGPService *)v7, a1);
    if ( !GPSessions )
    {
      if ( pftDueTime.dwLowDateTime )
      {
        g_idleTimer = CreateThreadpoolTimer(ServiceIdleTimerCallback, 0, 0);
        if ( !g_idleTimer )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v24 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v25 = GetLastError();
              if ( v25 > 0 )
                v25 = (unsigned __int16)v25 | 0x80070000;
              v24(
                2u,
                L"CGPService::Start CreateThreadpoolTimer for Idle failed with 0x%x. Continuing service start.",
                (unsigned int)v25);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v26 = GetLastError();
              if ( v26 > 0 )
                v26 = (unsigned __int16)v26 | 0x80070000;
              RedirectDebugMsg(
                2u,
                L"CGPService::Start CreateThreadpoolTimer for Idle failed with 0x%x. Continuing service start.",
                (unsigned int)v26);
            }
          }
        }
      }
      if ( *((_DWORD *)v7 + 32) )
        goto LABEL_124;
      if ( CSvcHostGlobalData::s_pSvchostGlobalData )
      {
        GPSessions = (*((__int64 (__fastcall **)(SERVICE_STATUS_HANDLE *, const WCHAR *, SERVICE_STATUS_HANDLE, void (__fastcall *)(void *, unsigned __int8), SERVICE_STATUS_HANDLE *, int))CSvcHostGlobalData::s_pSvchostGlobalData
                      + 24))(
                       v7 + 2,
                       L"gpsvc",
                       v7[1],
                       CGPService::WaitForServiceStopCallback,
                       v7,
                       8);
        if ( !GPSessions )
        {
          if ( *((_DWORD *)v7 + 32) )
          {
LABEL_124:
            GPSessions = 0;
            goto LABEL_135;
          }
          GPSessions = 0;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"Updating the service status to be RUNNING.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"Updating the service status to be RUNNING.");
            }
          }
          *((_DWORD *)v7 + 15) = 4;
          *v21 = 0;
          *v20 = 0;
          *((_DWORD *)v7 + 16) = 321;
          if ( !SetServiceStatus(*v7, (LPSERVICE_STATUS)v7 + 2) )
            GPSessions = GetLastError();
          if ( !GPSessions )
          {
LABEL_135:
            *((_DWORD *)v7 + 6) = 1;
            if ( *((_DWORD *)v7 + 32) )
            {
              CGPService::DoAsyncInitialization(v7);
            }
            else if ( !QueueUserWorkItem(CGPService::DoAsyncInitialization, v7, 0) )
            {
              GPSessions = GetLastError();
LABEL_138:
              if ( !GPSessions )
              {
                *((_DWORD *)CGPService::s_pInstance + 11) = 0;
                if ( g_idleTimer )
                {
                  pftDueTime = (struct _FILETIME)(-10000000 * v12);
                  SetThreadpoolTimer(g_idleTimer, &pftDueTime, 1000 * v12, 0);
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(
                        4u,
                        L"CGPService::Start: SetThreadpoolTimer %d. seconds for idle timer",
                        (unsigned int)v12);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(
                        4u,
                        L"CGPService::Start: SetThreadpoolTimer %d. seconds for idle timer",
                        (unsigned int)v12);
                    }
                  }
                }
                if ( g_sysvolTimer )
                {
                  v30.dwHighDateTime = -2;
                  v30.dwLowDateTime = -1705032704;
                  SetThreadpoolTimer(g_sysvolTimer, &v30, 0x927C0u, 0);
                  if ( *(_DWORD *)&g_dwDebugLevel )
                  {
                    if ( g_lpDebugMsg )
                    {
                      g_lpDebugMsg(4u, L"CGPService::Start: SetThreadpoolTimer %d. seconds for SYSVOL timer.", 600);
                    }
                    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                    {
                      RedirectDebugMsg(4u, L"CGPService::Start: SetThreadpoolTimer %d. seconds for SYSVOL timer.", 600);
                    }
                  }
                }
                goto LABEL_158;
              }
              goto LABEL_156;
            }
            CGPService::s_pInstance = (CGPService *)v7;
            goto LABEL_138;
          }
        }
      }
      else
      {
        GPSessions = 21;
      }
    }
  }
LABEL_156:
  CGPService::StopAndFreeService((struct CGPService *)v7, GPSessions);
LABEL_158:
  if ( v2 )
    LeaveCriticalSection(v2);
  return GPSessions;
}

```

## disassembly

```asm
0x180035570  mov     [rsp+arg_0], rbx
0x180035575  push    rbp
0x180035576  push    rsi
0x180035577  push    rdi
0x180035578  push    r12
0x18003557a  push    r13
0x18003557c  push    r14
0x18003557e  push    r15
0x180035580  sub     rsp, 60h
0x180035584  mov     ebp, ecx
0x180035586  mov     rsi, cs:lpCriticalSection
0x18003558d  mov     [rsp+98h+var_58], rsi
0x180035592  test    rsi, rsi
0x180035595  jz      short loc_1800355A1
0x180035597  mov     rcx, rsi; lpCriticalSection
0x18003559a  call    cs:__imp_EnterCriticalSection
0x1800355a0  nop
0x1800355a1  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800355a8  jz      short loc_1800355F4
0x1800355aa  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800355b1  test    rax, rax
0x1800355b4  jz      short loc_1800355CC
0x1800355b6  mov     r8d, ebp
0x1800355b9  lea     rdx, aCgpserviceStar_7; "CGPService::Start with flags = 0x%x."
0x1800355c0  mov     ecx, 4
0x1800355c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355ca  jmp     short loc_1800355F4
0x1800355cc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800355d4  jz      short loc_1800355F4
0x1800355d6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800355de  jz      short loc_1800355F4
0x1800355e0  mov     r8d, ebp
0x1800355e3  lea     rdx, aCgpserviceStar_7; "CGPService::Start with flags = 0x%x."
0x1800355ea  mov     ecx, 4; unsigned int
0x1800355ef  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800355f4  call    ?EnableMitigations@@YAXXZ; EnableMitigations(void)
0x1800355f9  call    cs:__imp_GetTickCount
0x1800355ff  mov     cs:?s_ServiceInitTime@CGPService@@0KA, eax; ulong CGPService::s_ServiceInitTime
0x180035605  xor     r12d, r12d
0x180035608  mov     [rsp+98h+hMem], r12
0x18003560d  mov     [rsp+98h+var_48], r12
0x180035612  lea     rcx, [rsp+98h+hMem]; this
0x180035617  call    ?ReportEventW@CGPOperationalEvent@@QEAAKPEBU_EVENT_DESCRIPTOR@@@Z; CGPOperationalEvent::ReportEventW(_EVENT_DESCRIPTOR const *)
0x18003561c  nop
0x18003561d  mov     rcx, [rsp+98h+hMem]; hMem
0x180035622  test    rcx, rcx
0x180035625  jz      short loc_18003562D
0x180035627  call    cs:__imp_LocalFree
0x18003562d  mov     cs:?s_dwResumeTick@CGPService@@0KA, r12d; ulong CGPService::s_dwResumeTick
0x180035634  mov     [rsp+98h+Buffer], r12
0x18003563c  cmp     cs:?s_pInstance@CGPService@@2PEAV1@EA, 0; CGPService * CGPService::s_pInstance
0x180035644  jz      short loc_18003565B
0x180035646  test    rsi, rsi
0x180035649  jz      short loc_180035654
0x18003564b  mov     rcx, rsi; lpCriticalSection
0x18003564e  call    cs:__imp_LeaveCriticalSection
0x180035654  xor     eax, eax
0x180035656  jmp     loc_180035F4C
0x18003565b  cmp     cs:?s_hEventInitialized@CGPService@@0PEAXEA, 0; void * CGPService::s_hEventInitialized
0x180035663  jnz     short loc_18003567F
0x180035665  xor     r9d, r9d; lpName
0x180035668  xor     r8d, r8d; bInitialState
0x18003566b  mov     edx, 1; bManualReset
0x180035670  xor     ecx, ecx; lpEventAttributes
0x180035672  call    cs:__imp_CreateEventW
0x180035678  mov     cs:?s_hEventInitialized@CGPService@@0PEAXEA, rax; void * CGPService::s_hEventInitialized
0x18003567f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035686  mov     ecx, 88h; unsigned __int64
0x18003568b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035690  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x180035698  test    rax, rax
0x18003569b  jz      loc_180035F37
0x1800356a1  mov     rcx, rax; this
0x1800356a4  call    ??0CGPService@@QEAA@XZ; CGPService::CGPService(void)
0x1800356a9  mov     rbx, rax
0x1800356ac  test    rax, rax
0x1800356af  jz      loc_180035F37
0x1800356b5  test    ebp, ebp
0x1800356b7  jns     short loc_1800356C3
0x1800356b9  mov     dword ptr [rax+80h], 1
0x1800356c3  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800356ca  jz      short loc_180035710
0x1800356cc  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800356d3  test    rax, rax
0x1800356d6  jz      short loc_1800356EB
0x1800356d8  lea     rdx, aCgpserviceStar_10; "CGPService::Start: InstantiateGPEngine"
0x1800356df  mov     ecx, 4
0x1800356e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356e9  jmp     short loc_180035710
0x1800356eb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800356f3  jz      short loc_180035710
0x1800356f5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800356fd  jz      short loc_180035710
0x1800356ff  lea     rdx, aCgpserviceStar_10; "CGPService::Start: InstantiateGPEngine"
0x180035706  mov     ecx, 4; unsigned int
0x18003570b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180035710  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035717  mov     ecx, 168h; unsigned __int64
0x18003571c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180035721  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x180035729  test    rax, rax
0x18003572c  jz      short loc_180035738
0x18003572e  mov     rcx, rax; this
0x180035731  call    ??0CGPApplicationService@@QEAA@PEAK@Z; CGPApplicationService::CGPApplicationService(ulong *)
0x180035736  jmp     short loc_18003573B
0x180035738  mov     rax, r12
0x18003573b  mov     [rbx+58h], rax
0x18003573f  test    rax, rax
0x180035742  jz      loc_180035F26
0x180035748  mov     [rsp+98h+pftDueTime.dwLowDateTime], r12d
0x180035750  lea     rcx, dword_180128070; CallbackContext
0x180035757  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003575c  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180035763  jz      short loc_1800357A9
0x180035765  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003576c  test    rax, rax
0x18003576f  jz      short loc_180035784
0x180035771  lea     rdx, aCgpserviceStar_8; "CGPService::Start: GetAOACConfig"
0x180035778  mov     ecx, 4
0x18003577d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035782  jmp     short loc_1800357A9
0x180035784  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003578c  jz      short loc_1800357A9
0x18003578e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035796  jz      short loc_1800357A9
0x180035798  lea     rdx, aCgpserviceStar_8; "CGPService::Start: GetAOACConfig"
0x18003579f  mov     ecx, 4; unsigned int
0x1800357a4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800357a9  call    ?GetAOACConfig@@YAKXZ; GetAOACConfig(void)
0x1800357ae  mov     r15d, eax
0x1800357b1  cmp     eax, 1
0x1800357b4  jz      loc_18003591C
0x1800357ba  lea     r8, [rsp+98h+Buffer]; Buffer
0x1800357c2  mov     edx, 1; InfoLevel
0x1800357c7  xor     ecx, ecx; lpServer
0x1800357c9  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800357cf  test    eax, eax
0x1800357d1  jnz     loc_1800358C0
0x1800357d7  mov     rcx, [rsp+98h+Buffer]
0x1800357df  mov     eax, [rcx]
0x1800357e1  cmp     eax, 1
0x1800357e4  ja      short loc_1800357F1
0x1800357e6  mov     [rsp+98h+pftDueTime.dwLowDateTime], 1
0x1800357f1  add     eax, 0FFFFFFFCh
0x1800357f4  cmp     eax, 1
0x1800357f7  ja      loc_1800358AD
0x1800357fd  xor     r8d, r8d; pcbe
0x180035800  xor     edx, edx; pv
0x180035802  lea     rcx, ?ValidateSYSVOLTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180035809  call    cs:__imp_CreateThreadpoolTimer
0x18003580f  mov     cs:?g_sysvolTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_sysvolTimer
0x180035816  test    rax, rax
0x180035819  jnz     loc_1800358AD
0x18003581f  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x180035825  jz      loc_1800358AD
0x18003582b  mov     rdi, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180035832  test    rdi, rdi
0x180035835  jz      short loc_180035873
0x180035837  call    cs:__imp_GetLastError
0x18003583d  test    eax, eax
0x18003583f  jle     short loc_180035849
0x180035841  movzx   eax, ax
0x180035844  or      eax, 80070000h
0x180035849  mov     r8d, eax
0x18003584c  lea     rdx, aCgpserviceStar_9; "CGPService::Start CreateThreadpoolTimer"...
0x180035853  mov     ecx, 2
0x180035858  mov     rax, rdi
0x18003585b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035860  mov     rcx, [rsp+98h+Buffer]; Buffer
0x180035868  call    cs:__imp_DsRoleFreeMemory
0x18003586e  jmp     loc_18003596C
0x180035873  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003587b  jz      short loc_1800358AD
0x18003587d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035885  jz      short loc_1800358AD
0x180035887  call    cs:__imp_GetLastError
0x18003588d  test    eax, eax
0x18003588f  jle     short loc_180035899
0x180035891  movzx   eax, ax
0x180035894  or      eax, 80070000h
0x180035899  mov     r8d, eax
0x18003589c  lea     rdx, aCgpserviceStar_9; "CGPService::Start CreateThreadpoolTimer"...
0x1800358a3  mov     ecx, 2; unsigned int
0x1800358a8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800358ad  mov     rcx, [rsp+98h+Buffer]; Buffer
0x1800358b5  call    cs:__imp_DsRoleFreeMemory
0x1800358bb  jmp     loc_18003596C
0x1800358c0  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800358c7  jz      loc_18003596C
0x1800358cd  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800358d4  test    r9, r9
0x1800358d7  jz      short loc_1800358F2
0x1800358d9  mov     r8d, eax
0x1800358dc  lea     rdx, aCgpserviceStar_5; "CGPService::Start DsRoleGetPrimaryDomai"...
0x1800358e3  mov     ecx, 2
0x1800358e8  mov     rax, r9
0x1800358eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358f0  jmp     short loc_18003596C
0x1800358f2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800358fa  jz      short loc_18003596C
0x1800358fc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035904  jz      short loc_18003596C
0x180035906  mov     r8d, eax
0x180035909  lea     rdx, aCgpserviceStar_5; "CGPService::Start DsRoleGetPrimaryDomai"...
0x180035910  mov     ecx, 2; unsigned int
0x180035915  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003591a  jmp     short loc_18003596C
0x18003591c  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180035923  jz      short loc_18003596C
0x180035925  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003592c  test    r9, r9
0x18003592f  jz      short loc_180035947
0x180035931  lea     rdx, aCgpserviceStar_1; "CGPService::Start AOAC is not in use or"...
0x180035938  mov     ecx, 4
0x18003593d  mov     rax, r9
0x180035940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035945  jmp     short loc_18003596C
0x180035947  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18003594f  jz      short loc_18003596C
0x180035951  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035959  jz      short loc_18003596C
0x18003595b  lea     rdx, aCgpserviceStar_1; "CGPService::Start AOAC is not in use or"...
0x180035962  mov     ecx, 4; unsigned int
0x180035967  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003596c  cmp     dword ptr [rbx+80h], 0
0x180035973  jnz     loc_180035A04
0x180035979  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180035980  jz      short loc_1800359C9
0x180035982  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180035989  test    r9, r9
0x18003598c  jz      short loc_1800359A4
0x18003598e  lea     rdx, aCgpserviceStar_4; "CGPService::Start: RegisterServiceCtrlH"...
0x180035995  mov     ecx, 4
0x18003599a  mov     rax, r9
0x18003599d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359a2  jmp     short loc_1800359C9
0x1800359a4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800359ac  jz      short loc_1800359C9
0x1800359ae  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800359b6  jz      short loc_1800359C9
0x1800359b8  lea     rdx, aCgpserviceStar_4; "CGPService::Start: RegisterServiceCtrlH"...
0x1800359bf  mov     ecx, 4; unsigned int
0x1800359c4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800359c9  mov     r8, rbx; lpContext
0x1800359cc  lea     rdx, ?GPServiceHandlerEx@CGPService@@CAKKKPEAX0@Z; lpHandlerProc
0x1800359d3  lea     rcx, aGpsvc; "gpsvc"
0x1800359da  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800359e0  mov     [rbx], rax
0x1800359e3  test    rax, rax
0x1800359e6  jnz     short loc_180035A04
0x1800359e8  mov     dword ptr [rbx+38h], 20h ; ' '
0x1800359ef  mov     [rbx+40h], r12d
0x1800359f3  mov     [rbx+48h], r12d
0x1800359f7  call    cs:__imp_GetLastError
0x1800359fd  mov     edi, eax
0x1800359ff  jmp     loc_180035DBD
0x180035a04  test    bpl, 1
0x180035a08  jz      short loc_180035A6E
0x180035a0a  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180035a11  jz      short loc_180035A60
0x180035a13  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180035a1a  test    r9, r9
0x180035a1d  jz      short loc_180035A38
0x180035a1f  mov     r8d, ebp
0x180035a22  lea     rdx, aCgpserviceStar_7; "CGPService::Start with flags = 0x%x."
0x180035a29  mov     ecx, 4
0x180035a2e  mov     rax, r9
0x180035a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a36  jmp     short loc_180035A60
0x180035a38  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180035a40  jz      short loc_180035A60
0x180035a42  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180035a4a  jz      short loc_180035A60
0x180035a4c  mov     r8d, ebp
0x180035a4f  lea     rdx, aCgpserviceStar_7; "CGPService::Start with flags = 0x%x."
0x180035a56  mov     ecx, 4; unsigned int
0x180035a5b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180035a60  mov     dword ptr [rbx+30h], 1
0x180035a67  mov     dword ptr [rbx+2Ch], 1
0x180035a6e  lea     r14, [rbx+38h]
0x180035a72  lea     r13, [rbx+50h]
0x180035a76  cmp     dword ptr [rbx+80h], 0
0x180035a7d  jz      short loc_180035A85
0x180035a7f  lea     r12, [rbx+4Ch]
0x180035a83  jmp     short loc_180035AD2
0x180035a85  mov     edi, r12d
0x180035a88  mov     dword ptr [r14], 20h ; ' '
0x180035a8f  mov     qword ptr [rbx+3Ch], 2
0x180035a97  mov     [rbx+44h], r12
0x180035a9b  mov     dword ptr [rbx+78h], 1
0x180035aa2  lea     r12, [rbx+4Ch]
0x180035aa6  mov     dword ptr [r12], 1
0x180035aae  mov     [r13+0], edi
0x180035ab2  mov     rdx, r14; lpServiceStatus
0x180035ab5  mov     rcx, [rbx]; hServiceStatus
0x180035ab8  call    cs:__imp_SetServiceStatus
0x180035abe  test    eax, eax
0x180035ac0  jnz     short loc_180035ACA
0x180035ac2  call    cs:__imp_GetLastError
0x180035ac8  mov     edi, eax
  ... truncated ...
```
