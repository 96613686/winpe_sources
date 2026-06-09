# ServiceEntry(ulong,ushort * * const,_TCPSVCS_GLOBAL_DATA *)

- ea: `0x180001e60`
- end: `0x180002725`
- name: `?ServiceEntry@@YAXKQEAPEAGPEAU_TCPSVCS_GLOBAL_DATA@@@Z`
- size: `2245`
- prototype: `void __fastcall(__int64, unsigned __int16 **const, void (**)(void))`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001958`
- `0x180001a0c`
- `0x180001e60`
- `0x180002760`
- `0x180002afc`
- `0x180002e34`
- `0x180003118`
- `0x180003490`
- `0x1800036a4`
- `0x180005010`

## import_xrefs

- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x180001f88`
- `ADVAPI32!RegisterServiceCtrlHandlerA` at `0x180001f88`
- `KERNEL32!CloseHandle` at `0x18000246b`
- `KERNEL32!CloseHandle` at `0x18000246b`
- `KERNEL32!GetLastError` at `0x180001f9a`
- `KERNEL32!GetLastError` at `0x180002058`
- `KERNEL32!GetLastError` at `0x1800020fd`
- `KERNEL32!GetLastError` at `0x1800022ee`
- `KERNEL32!GetLastError` at `0x180002539`
- `KERNEL32!GetLastError` at `0x180002568`
- `KERNEL32!GetLastError` at `0x180002620`
- `KERNEL32!GetLastError` at `0x180001f9a`
- `KERNEL32!GetLastError` at `0x180002058`
- `KERNEL32!GetLastError` at `0x1800020fd`
- `KERNEL32!GetLastError` at `0x1800022ee`
- `KERNEL32!GetLastError` at `0x180002539`
- `KERNEL32!GetLastError` at `0x180002568`
- `KERNEL32!GetLastError` at `0x180002620`
- `KERNEL32!CreateThread` at `0x1800020ef`
- `KERNEL32!CreateThread` at `0x1800020ef`
- `KERNEL32!WaitForSingleObject` at `0x180002235`
- `KERNEL32!WaitForSingleObject` at `0x180002407`
- `KERNEL32!WaitForSingleObject` at `0x180002235`
- `KERNEL32!WaitForSingleObject` at `0x180002407`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800022db`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800022db`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000260d`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000260d`
- `KERNEL32!ExitProcess` at `0x1800026f5`
- `KERNEL32!ExitProcess` at `0x1800026f5`
- `KERNEL32!GetCurrentProcess` at `0x1800026fc`
- `KERNEL32!GetCurrentProcess` at `0x1800026fc`
- `KERNEL32!TerminateProcess` at `0x180002707`
- `KERNEL32!TerminateProcess` at `0x180002707`
- `USER32!CloseDesktop` at `0x180002571`
- `USER32!CloseDesktop` at `0x18000258d`
- `USER32!CloseDesktop` at `0x180002571`
- `USER32!CloseDesktop` at `0x18000258d`
- `USER32!SetProcessWindowStation` at `0x18000203d`
- `USER32!SetProcessWindowStation` at `0x18000252f`
- `USER32!SetProcessWindowStation` at `0x18000203d`
- `USER32!SetProcessWindowStation` at `0x18000252f`
- `USER32!CloseWindowStation` at `0x18000257f`
- `USER32!CloseWindowStation` at `0x18000259b`
- `USER32!CloseWindowStation` at `0x18000257f`
- `USER32!CloseWindowStation` at `0x18000259b`
- `USER32!SetThreadDesktop` at `0x18000204e`
- `USER32!SetThreadDesktop` at `0x180002559`
- `USER32!SetThreadDesktop` at `0x18000204e`
- `USER32!SetThreadDesktop` at `0x180002559`
- `ole32!CoInitializeEx` at `0x180001ffe`
- `ole32!CoInitializeEx` at `0x180001ffe`
- `ole32!CoSuspendClassObjects` at `0x1800021b0`
- `ole32!CoSuspendClassObjects` at `0x180002361`
- `ole32!CoSuspendClassObjects` at `0x1800021b0`
- `ole32!CoSuspendClassObjects` at `0x180002361`
- `ole32!CoUninitialize` at `0x1800024b4`
- `ole32!CoUninitialize` at `0x1800024b4`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x1800023b7`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x1800023b7`
- `RPCRT4!RpcMgmtStopServerListening` at `0x180002377`
- `RPCRT4!RpcMgmtStopServerListening` at `0x180002377`
- `COADMIN!TerminateComAdmindata` at `0x180002471`
- `COADMIN!TerminateComAdmindata` at `0x180002471`
- `COADMIN!InitComAdmindata` at `0x180002078`
- `COADMIN!InitComAdmindata` at `0x180002078`
- `IisRTL!TerminateIISRTL` at `0x180002477`
- `IisRTL!TerminateIISRTL` at `0x180002477`
- `IisRTL!InitializeIISRTL` at `0x180001fe2`
- `IisRTL!InitializeIISRTL` at `0x180001fe2`
- `IisRTL!PuDbgPrint` at `0x180001f17`
- `IisRTL!PuDbgPrint` at `0x1800020bc`
- `IisRTL!PuDbgPrint` at `0x180002144`
- `IisRTL!PuDbgPrint` at `0x180002356`
- `IisRTL!PuDbgPrint` at `0x1800023b1`
- `IisRTL!PuDbgPrint` at `0x1800023f1`
- `IisRTL!PuDbgPrint` at `0x18000265d`
- `IisRTL!PuDbgPrint` at `0x180001f17`
- `IisRTL!PuDbgPrint` at `0x1800020bc`
- `IisRTL!PuDbgPrint` at `0x180002144`
- `IisRTL!PuDbgPrint` at `0x180002356`
- `IisRTL!PuDbgPrint` at `0x1800023b1`
- `IisRTL!PuDbgPrint` at `0x1800023f1`
- `IisRTL!PuDbgPrint` at `0x18000265d`
- `iisutil!?UnRegister@CEtwTracer@@QEAAKXZ` at `0x1800026c5`
- `iisutil!?UnRegister@CEtwTracer@@QEAAKXZ` at `0x1800026c5`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180001eda`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180001eda`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x180001eac`
- `iisutil!??0CEtwTracer@@QEAA@XZ` at `0x180001eac`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180001f4a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000220d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002275`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800024ae`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800024e6`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800026b3`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180001f4a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000220d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x180002275`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800024ae`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800024e6`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x1800026b3`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x1800026e1`
- `iisutil!??1CEtwTracer@@QEAA@XZ` at `0x1800026e1`

## string_xrefs

- `0x1800020a9`: `ServiceEntry`
- `0x180002120`: `ServiceEntry`
- `0x180002398`: `ServiceEntry`
- `0x1800023d8`: `ServiceEntry`
- `0x180002639`: `ServiceEntry`
- `0x180002132`: `Failed to initialize IIS metabase writer %x\n`
- `0x18000230a`: `Failed to create the timer queue for shutdown %x\n`
- `0x18000264b`: `Failed to delete the timer queue for shutdown %x\n`
- `0x180001ecc`: `iisadmin.dll`

## pseudocode

```c
void __fastcall ServiceEntry(__int64 a1, unsigned __int16 **const a2, void (**a3)(void))
{
  HANDLE v4; // rbp
  int v5; // r14d
  CEtwTracer *v6; // rax
  signed int v7; // r15d
  CEtwTracer *v8; // rax
  unsigned int v9; // eax
  signed int inited; // ebx
  signed int LastError; // eax
  bool v12; // cc
  signed int v13; // eax
  int v14; // eax
  signed int v15; // eax
  bool v16; // sf
  unsigned int i; // ebx
  int started; // edi
  int v19; // eax
  signed int v20; // eax
  int v21; // eax
  signed int v22; // eax
  struct CIISVssWriter *v23; // rcx
  __int64 v24; // rdx
  HWINSTA v25; // rdi
  HWINSTA v26; // r14
  HDESK v27; // rbp
  HDESK v28; // rsi
  signed int v29; // eax
  DWORD v30; // edi
  signed int v31; // eax
  CEtwTracer *v32; // rdi
  HANDLE CurrentProcess; // rax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-50h]
  DWORD ThreadId; // [rsp+90h] [rbp+18h] BYREF
  HANDLE phNewTimer; // [rsp+98h] [rbp+20h] BYREF

  phNewTimer = 0;
  v4 = 0;
  v5 = 0;
  v6 = (CEtwTracer *)operator new(0x40u);
  v7 = -2147467259;
  if ( !v6 )
  {
    g_pEtwGlobalTracer = 0;
    goto LABEL_67;
  }
  v8 = CEtwTracer::CEtwTracer(v6);
  g_pEtwGlobalTracer = v8;
  if ( !v8 )
  {
LABEL_67:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\tracing.cxx",
        42,
        "InitTracing",
        "Failed to allocation Tracing Infrastructure\n");
    inited = -2147024882;
    goto LABEL_70;
  }
  v9 = CEtwTracer::Register(v8, (const struct _GUID *)IISAdminGlobalGuid, L"iisadmin.dll", L"IISAdminMofResource");
  if ( v9 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\tracing.cxx",
        56,
        "InitTracing",
        "Failed to Register Tracing, ret=0x%x\n",
        v9);
    goto LABEL_6;
  }
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2) && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0 )
    CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminStatupGuid, 1u, 0, 0);
  g_svcStatus.dwServiceType = 32;
  g_svcStatus.dwCurrentState = 1;
  *(_QWORD *)&g_svcStatus.dwControlsAccepted = 4;
  *(_QWORD *)&g_svcStatus.dwServiceSpecificExitCode = 0;
  g_svcStatus.dwWaitHint = 0;
  g_hsvcStatus = RegisterServiceCtrlHandlerA("IISADMIN", ServiceControlHandler);
  if ( !g_hsvcStatus )
  {
    LastError = GetLastError();
    inited = LastError;
    v12 = LastError <= 0;
    goto LABEL_12;
  }
  g_svcStatus.dwWaitHint = GetStartupWaitHint();
  g_svcStatus.dwCurrentState = 2;
  *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
  g_svcStatus.dwCheckPoint = 1;
  LastError = ReportServiceStatus();
  inited = LastError;
  v12 = LastError <= 0;
  if ( LastError )
  {
LABEL_12:
    if ( !v12 )
      inited = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_70;
  }
  InitializeIISRTL();
  inited = InitDesktopWinsta();
  if ( inited >= 0 )
  {
    inited = CoInitializeEx(0, 0xCu);
    if ( inited >= 0 )
    {
      v5 = 1;
      inited = InitComSecurity();
      if ( inited >= 0 )
      {
        if ( !g_hWinStaPrev || !g_hDesktopPrev )
        {
LABEL_6:
          inited = -2147467259;
          goto LABEL_70;
        }
        if ( SetProcessWindowStation(g_hWinStaPrev) && SetThreadDesktop(g_hDesktopPrev) )
          goto LABEL_25;
        v13 = GetLastError();
        inited = v13;
        if ( v13 > 0 )
          inited = (unsigned __int16)v13 | 0x80070000;
        if ( inited >= 0 )
        {
LABEL_25:
          v14 = InitComAdmindata(g_pEtwGlobalTracer);
          inited = v14;
          if ( v14 >= 0 )
          {
            ThreadId = 0;
            v4 = CreateThread(0, 0, InitMDWriterThread, 0, 0, &ThreadId);
            if ( !v4 )
            {
              v15 = GetLastError();
              v16 = v15 < 0;
              if ( v15 > 0 )
              {
                v15 = (unsigned __int16)v15 | 0x80070000;
                v16 = v15 < 0;
              }
              if ( v16 && (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
                  692,
                  "ServiceEntry",
                  "Failed to initialize IIS metabase writer %x\n",
                  v15);
            }
            StartUpIndicateClientActivity();
            for ( i = 0; i < 2; ++i )
            {
              started = StartServiceExtension(
                          *((IID **)&off_180006110 + 2 * i),
                          *((unsigned __int16 **)&off_180006110 + 2 * i + 1));
              if ( started < 0 )
              {
                StopServiceExtensions();
                inited = started;
                goto LABEL_70;
              }
              StartUpIndicateClientActivity();
            }
            StartUpIndicateClientActivity();
            RegisterServiceExtensionCLSIDs();
            StartUpIndicateClientActivity();
            if ( a3 )
            {
              v19 = ((__int64 (*)(void))*a3)();
              inited = v19;
              if ( v19 )
              {
                if ( v19 > 0 )
                  inited = (unsigned __int16)v19 | 0x80070000;
                CoSuspendClassObjects();
                goto LABEL_71;
              }
            }
            g_svcStatus.dwControlsAccepted = 5;
            g_svcStatus.dwCurrentState = 4;
            *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
            *(_QWORD *)&g_svcStatus.dwCheckPoint = 0;
            inited = ReportServiceStatus();
            if ( *((_DWORD *)g_pEtwGlobalTracer + 2) && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 1) != 0 )
              CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminStatupGuid, 2u);
            if ( inited )
            {
              if ( inited > 0 )
                inited = (unsigned __int16)inited | 0x80070000;
            }
            else
            {
              v20 = WaitForSingleObject(g_hShutdownEvent, 0xFFFFFFFF);
              inited = v20;
              if ( v20 )
              {
                if ( v20 > 0 )
                  inited = (unsigned __int16)v20 | 0x80070000;
              }
              else
              {
                inited = started;
              }
              if ( *((_DWORD *)g_pEtwGlobalTracer + 2) && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0 )
                CEtwTracer::EtwTraceEvent(
                  (CEtwTracer *)g_pEtwGlobalTracer,
                  (const struct _GUID *)IISAdminShutdownGuid,
                  1u,
                  0,
                  0);
              g_svcStatus.dwCurrentState = 3;
              *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
              g_svcStatus.dwCheckPoint = 1;
              g_svcStatus.dwWaitHint = 10000;
              v21 = ReportServiceStatus();
              if ( v21 )
              {
                if ( v21 > 0 )
                  inited = (unsigned __int16)v21 | 0x80070000;
                else
                  inited = v21;
              }
              if ( !CreateTimerQueueTimer(&phNewTimer, 0, ShutdownCallback, 0, 0x2328u, 0x2328u, 1u)
                && (g_dwDebugFlags & 3) != 0 )
              {
                v22 = GetLastError();
                if ( v22 > 0 )
                  v22 = (unsigned __int16)v22 | 0x80070000;
                LODWORD(lpThreadId) = v22;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
                  818,
                  "ServiceEntry",
                  "Failed to create the timer queue for shutdown %x\n",
                  lpThreadId);
              }
            }
          }
          else if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
              682,
              "ServiceEntry",
              "Failed to initialize ABO 0x%08x\n",
              v14);
          }
        }
      }
    }
  }
LABEL_70:
  CoSuspendClassObjects();
  if ( a3 )
LABEL_71:
    a3[1]();
  if ( RpcMgmtStopServerListening(0) && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
      837,
      "ServiceEntry",
      "RpcMgmtStopServerListening returned 0x%08x",
      (_DWORD)lpThreadId);
  if ( RpcMgmtWaitServerListen() && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
      845,
      "ServiceEntry",
      "RpcMgmtWaitServerListen returned 0x%08x",
      (_DWORD)lpThreadId);
  StopServiceExtensions();
  if ( v4 )
  {
    if ( !WaitForSingleObject(v4, 0xFFFFFFFF) )
    {
      v23 = g_pIISVssWriter;
      if ( g_pIISVssWriter )
      {
        if ( g_fWriterSubscribed )
        {
          v24 = *((_QWORD *)g_pIISVssWriter + 1);
          if ( v24 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24 + 40LL))(*((_QWORD *)g_pIISVssWriter + 1));
            v23 = g_pIISVssWriter;
            g_fWriterSubscribed = 0;
          }
        }
        if ( v23 )
          (**(void (__fastcall ***)(struct CIISVssWriter *, __int64))v23)(v23, 1);
        g_pIISVssWriter = 0;
      }
    }
    CloseHandle(v4);
  }
  TerminateComAdmindata();
  TerminateIISRTL();
  if ( v5 )
  {
    if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
      && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0
      && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
    {
      CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminShutdownGuid, 0x14u);
    }
    CoUninitialize();
    if ( *((_DWORD *)g_pEtwGlobalTracer + 2)
      && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0
      && *((_DWORD *)g_pEtwGlobalTracer + 11) >= 4u )
    {
      CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminShutdownGuid, 0x15u);
    }
  }
  v25 = g_hWinStaPrev;
  v26 = g_hWinSta;
  v27 = g_hDesktop;
  v28 = g_hDesktopPrev;
  g_hWinSta = 0;
  g_hDesktop = 0;
  g_hWinStaPrev = 0;
  g_hDesktopPrev = 0;
  if ( v25 )
  {
    v7 = 0;
    if ( !SetProcessWindowStation(v25) )
    {
      v29 = GetLastError();
      v7 = v29;
      if ( v29 > 0 )
        v7 = (unsigned __int16)v29 | 0x80070000;
    }
  }
  if ( v28 )
  {
    if ( !SetThreadDesktop(v28) && v7 >= 0 )
      GetLastError();
    CloseDesktop(v28);
  }
  if ( v25 )
    CloseWindowStation(v25);
  if ( v27 )
    CloseDesktop(v27);
  if ( v26 )
    CloseWindowStation(v26);
  if ( g_hsvcStatus )
  {
    v30 = 0;
    if ( inited < 0 )
    {
      v30 = (unsigned __int16)inited;
      if ( (inited & 0x1FFF0000) != 0x70000 )
        v30 = 1066;
    }
    if ( phNewTimer )
    {
      ++g_svcStatus.dwCheckPoint;
      g_svcStatus.dwCurrentState = 3;
      *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
      g_svcStatus.dwWaitHint = 10000;
      ReportServiceStatus();
      if ( !DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && (g_dwDebugFlags & 3) != 0 )
      {
        v31 = GetLastError();
        if ( v31 > 0 )
          v31 = (unsigned __int16)v31 | 0x80070000;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
          939,
          "ServiceEntry",
          "Failed to delete the timer queue for shutdown %x\n",
          v31);
      }
      phNewTimer = 0;
    }
    g_svcStatus.dwCurrentState = 1;
    g_svcStatus.dwWin32ExitCode = v30;
    g_svcStatus.dwServiceSpecificExitCode = inited;
    *(_QWORD *)&g_svcStatus.dwCheckPoint = 0;
    ReportServiceStatus();
  }
  if ( *((_DWORD *)g_pEtwGlobalTracer + 2) && (*((_BYTE *)g_pEtwGlobalTracer + 40) & 2) != 0 )
    CEtwTracer::EtwTraceEvent((CEtwTracer *)g_pEtwGlobalTracer, (const struct _GUID *)IISAdminShutdownGuid, 2u);
  if ( g_pEtwGlobalTracer )
  {
    CEtwTracer::UnRegister((CEtwTracer *)g_pEtwGlobalTracer);
    v32 = (CEtwTracer *)g_pEtwGlobalTracer;
    g_pEtwGlobalTracer = 0;
    if ( v32 )
    {
      CEtwTracer::~CEtwTracer(v32);
      operator delete(v32);
    }
  }
  if ( inited >= 0 )
    ExitProcess(inited);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, inited);
}

```

## disassembly

```asm
0x180001e60  mov     rax, rsp
0x180001e63  mov     [rax+8], rbx
0x180001e67  push    rbp
0x180001e68  push    rsi
0x180001e69  push    rdi
0x180001e6a  push    r12
0x180001e6c  push    r13
0x180001e6e  push    r14
0x180001e70  push    r15
0x180001e72  sub     rsp, 40h
0x180001e76  xor     r12d, r12d
0x180001e79  mov     rsi, r8
0x180001e7c  mov     [rax+20h], r12
0x180001e80  mov     ebp, r12d
0x180001e83  mov     r14d, r12d
0x180001e86  lea     ecx, [r12+40h]; Size
0x180001e8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e90  lea     r13d, [r12+1]
0x180001e95  mov     edi, 80070000h
0x180001e9a  mov     r15d, 80004005h
0x180001ea0  test    rax, rax
0x180001ea3  jz      loc_18000231F
0x180001ea9  mov     rcx, rax
0x180001eac  call    cs:__imp_??0CEtwTracer@@QEAA@XZ; CEtwTracer::CEtwTracer(void)
0x180001eb2  mov     cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA, rax; CEtwTracer * g_pEtwGlobalTracer
0x180001eb9  test    rax, rax
0x180001ebc  jz      loc_180002326
0x180001ec2  lea     r9, aIisadminmofres; "IISAdminMofResource"
0x180001ec9  mov     rcx, rax
0x180001ecc  lea     r8, aIisadminDll_0; "iisadmin.dll"
0x180001ed3  lea     rdx, IISAdminGlobalGuid
0x180001eda  call    cs:__imp_?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z; CEtwTracer::Register(_GUID const *,ushort *,ushort *)
0x180001ee0  test    eax, eax
0x180001ee2  jz      short loc_180001F25
0x180001ee4  test    byte ptr cs:g_dwDebugFlags, 3
0x180001eeb  jz      short loc_180001F1D
0x180001eed  mov     rcx, cs:g_pDebug
0x180001ef4  lea     r9, aInittracing; "InitTracing"
0x180001efb  mov     dword ptr [rsp+78h+lpThreadId], eax
0x180001eff  lea     r8d, [r12+38h]
0x180001f04  lea     rax, aFailedToRegist; "Failed to Register Tracing, ret=0x%x\n"
0x180001f0b  lea     rdx, aInetsrvIisMbIi_2; "inetsrv\\iis\\mb\\iisadmin\\tracing.cxx"
0x180001f12  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180001f17  call    cs:__imp_PuDbgPrint
0x180001f1d  mov     ebx, r15d
0x180001f20  jmp     loc_180002361
0x180001f25  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180001f2c  cmp     [rcx+8], r12d
0x180001f30  jz      short loc_180001F50
0x180001f32  test    [rcx+28h], r13b
0x180001f36  jz      short loc_180001F50
0x180001f38  xor     r9d, r9d
0x180001f3b  mov     qword ptr [rsp+78h+dwCreationFlags], r12
0x180001f40  mov     r8d, r13d
0x180001f43  lea     rdx, IISAdminStatupGuid
0x180001f4a  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180001f50  lea     rdx, ?ServiceControlHandler@@YAXK@Z; lpHandlerProc
0x180001f57  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_svcStatus ...
0x180001f61  lea     rcx, ServiceName; "IISADMIN"
0x180001f68  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, r13d; _SERVICE_STATUS g_svcStatus ...
0x180001f6f  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 4; _SERVICE_STATUS g_svcStatus ...
0x180001f7a  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, r12; _SERVICE_STATUS g_svcStatus ...
0x180001f81  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, r12d; _SERVICE_STATUS g_svcStatus ...
0x180001f88  call    cs:__imp_RegisterServiceCtrlHandlerA
0x180001f8e  mov     cs:?g_hsvcStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hsvcStatus
0x180001f95  test    rax, rax
0x180001f98  jnz     short loc_180001FB4
0x180001f9a  call    cs:__imp_GetLastError
0x180001fa0  mov     ebx, eax
0x180001fa2  test    eax, eax
0x180001fa4  jle     loc_180002361
0x180001faa  movzx   ebx, ax
0x180001fad  or      ebx, edi
0x180001faf  jmp     loc_180002361
0x180001fb4  call    ?GetStartupWaitHint@@YAKXZ; GetStartupWaitHint(void)
0x180001fb9  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, eax; _SERVICE_STATUS g_svcStatus ...
0x180001fbf  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_svcStatus ...
0x180001fc9  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r12; _SERVICE_STATUS g_svcStatus ...
0x180001fd0  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r13d; _SERVICE_STATUS g_svcStatus ...
0x180001fd7  call    ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
0x180001fdc  mov     ebx, eax
0x180001fde  test    eax, eax
0x180001fe0  jnz     short loc_180001FA4
0x180001fe2  call    cs:__imp_InitializeIISRTL
0x180001fe8  call    ?InitDesktopWinsta@@YAJXZ; InitDesktopWinsta(void)
0x180001fed  mov     ebx, eax
0x180001fef  test    eax, eax
0x180001ff1  js      loc_180002361
0x180001ff7  mov     edx, 0Ch; dwCoInit
0x180001ffc  xor     ecx, ecx; pvReserved
0x180001ffe  call    cs:__imp_CoInitializeEx
0x180002004  mov     ebx, eax
0x180002006  test    eax, eax
0x180002008  js      loc_180002361
0x18000200e  mov     r14d, r13d
0x180002011  call    ?InitComSecurity@@YAJXZ; InitComSecurity(void)
0x180002016  mov     ebx, eax
0x180002018  test    eax, eax
0x18000201a  js      loc_180002361
0x180002020  mov     rcx, cs:?g_hWinStaPrev@@3PEAUHWINSTA__@@EA; hWinSta
0x180002027  test    rcx, rcx
0x18000202a  jz      loc_180001F1D
0x180002030  cmp     cs:?g_hDesktopPrev@@3PEAUHDESK__@@EA, r12; HDESK__ * g_hDesktopPrev
0x180002037  jz      loc_180001F1D
0x18000203d  call    cs:__imp_SetProcessWindowStation
0x180002043  test    eax, eax
0x180002045  jz      short loc_180002058
0x180002047  mov     rcx, cs:?g_hDesktopPrev@@3PEAUHDESK__@@EA; hDesktop
0x18000204e  call    cs:__imp_SetThreadDesktop
0x180002054  test    eax, eax
0x180002056  jnz     short loc_180002071
0x180002058  call    cs:__imp_GetLastError
0x18000205e  mov     ebx, eax
0x180002060  test    eax, eax
0x180002062  jle     short loc_180002069
0x180002064  movzx   ebx, ax
0x180002067  or      ebx, edi
0x180002069  test    ebx, ebx
0x18000206b  js      loc_180002361
0x180002071  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180002078  call    cs:__imp_InitComAdmindata
0x18000207e  mov     ebx, eax
0x180002080  test    eax, eax
0x180002082  jns     short loc_1800020C7
0x180002084  test    byte ptr cs:g_dwDebugFlags, 3
0x18000208b  jz      loc_180002361
0x180002091  mov     dword ptr [rsp+78h+lpThreadId], eax
0x180002095  mov     r8d, 2AAh
0x18000209b  lea     rax, aFailedToInitia; "Failed to initialize ABO 0x%08x\n"
0x1800020a2  mov     rcx, cs:g_pDebug
0x1800020a9  lea     r9, aServiceentry_0; "ServiceEntry"
0x1800020b0  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x1800020b7  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x1800020bc  call    cs:__imp_PuDbgPrint
0x1800020c2  jmp     loc_180002361
0x1800020c7  lea     rax, [rsp+78h+ThreadId]
0x1800020cf  mov     [rsp+78h+ThreadId], r12d
0x1800020d7  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x1800020dc  lea     r8, ?InitMDWriterThread@@YAKPEAX@Z; lpStartAddress
0x1800020e3  xor     r9d, r9d; lpParameter
0x1800020e6  mov     [rsp+78h+dwCreationFlags], r12d; dwCreationFlags
0x1800020eb  xor     edx, edx; dwStackSize
0x1800020ed  xor     ecx, ecx; lpThreadAttributes
0x1800020ef  call    cs:__imp_CreateThread
0x1800020f5  mov     rbp, rax
0x1800020f8  test    rax, rax
0x1800020fb  jnz     short loc_18000214A
0x1800020fd  call    cs:__imp_GetLastError
0x180002103  test    eax, eax
0x180002105  jle     short loc_18000210E
0x180002107  movzx   eax, ax
0x18000210a  or      eax, edi
0x18000210c  test    eax, eax
0x18000210e  jns     short loc_18000214A
0x180002110  test    byte ptr cs:g_dwDebugFlags, 3
0x180002117  jz      short loc_18000214A
0x180002119  mov     rcx, cs:g_pDebug
0x180002120  lea     r9, aServiceentry_0; "ServiceEntry"
0x180002127  mov     dword ptr [rsp+78h+lpThreadId], eax
0x18000212b  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180002132  lea     rax, aFailedToInitia_0; "Failed to initialize IIS metabase write"...
0x180002139  mov     r8d, 2B4h
0x18000213f  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180002144  call    cs:__imp_PuDbgPrint
0x18000214a  call    ?StartUpIndicateClientActivity@@YAXXZ; StartUpIndicateClientActivity(void)
0x18000214f  mov     ebx, r12d
0x180002152  lea     r13, off_180006110
0x180002159  mov     ecx, ebx
0x18000215b  add     rcx, rcx
0x18000215e  mov     rdx, [r13+rcx*8+8]; unsigned __int16 *
0x180002163  mov     rcx, [r13+rcx*8+0]; rclsid
0x180002168  call    ?StartServiceExtension@@YAJPEBU_GUID@@PEAG@Z; StartServiceExtension(_GUID const *,ushort *)
0x18000216d  mov     edi, eax
0x18000216f  test    eax, eax
0x180002171  js      loc_180002316
0x180002177  call    ?StartUpIndicateClientActivity@@YAXXZ; StartUpIndicateClientActivity(void)
0x18000217c  inc     ebx
0x18000217e  cmp     ebx, 2
0x180002181  jb      short loc_180002159
0x180002183  call    ?StartUpIndicateClientActivity@@YAXXZ; StartUpIndicateClientActivity(void)
0x180002188  call    ?RegisterServiceExtensionCLSIDs@@YAXXZ; RegisterServiceExtensionCLSIDs(void)
0x18000218d  call    ?StartUpIndicateClientActivity@@YAXXZ; StartUpIndicateClientActivity(void)
0x180002192  test    rsi, rsi
0x180002195  jz      short loc_1800021BB
0x180002197  mov     rax, [rsi]
0x18000219a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219f  mov     ebx, eax
0x1800021a1  test    eax, eax
0x1800021a3  jz      short loc_1800021BB
0x1800021a5  jle     short loc_1800021B0
0x1800021a7  movzx   ebx, ax
0x1800021aa  or      ebx, 80070000h
0x1800021b0  call    cs:__imp_CoSuspendClassObjects
0x1800021b6  jmp     loc_18000236C
0x1800021bb  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS g_svcStatus ...
0x1800021c5  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_svcStatus ...
0x1800021cf  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r12; _SERVICE_STATUS g_svcStatus ...
0x1800021d6  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r12; _SERVICE_STATUS g_svcStatus ...
0x1800021dd  call    ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
0x1800021e2  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x1800021e9  mov     ebx, eax
0x1800021eb  mov     r13d, r14d
0x1800021ee  cmp     [rcx+8], r12d
0x1800021f2  jz      short loc_180002213
0x1800021f4  test    [rcx+28h], r14b
0x1800021f8  jz      short loc_180002213
0x1800021fa  xor     r9d, r9d
0x1800021fd  mov     qword ptr [rsp+78h+dwCreationFlags], r12
0x180002202  lea     rdx, IISAdminStatupGuid
0x180002209  lea     r8d, [r9+2]
0x18000220d  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x180002213  test    ebx, ebx
0x180002215  jz      short loc_18000222B
0x180002217  jle     loc_180002361
0x18000221d  movzx   ebx, bx
0x180002220  or      ebx, 80070000h
0x180002226  jmp     loc_180002361
0x18000222b  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hHandle
0x180002232  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002235  call    cs:__imp_WaitForSingleObject
0x18000223b  mov     ebx, eax
0x18000223d  test    eax, eax
0x18000223f  jz      short loc_18000224E
0x180002241  jle     short loc_180002250
0x180002243  movzx   ebx, ax
0x180002246  or      ebx, 80070000h
0x18000224c  jmp     short loc_180002250
0x18000224e  mov     ebx, edi
0x180002250  mov     rcx, cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwGlobalTracer
0x180002257  cmp     [rcx+8], r12d
0x18000225b  jz      short loc_18000227B
0x18000225d  test    byte ptr [rcx+28h], 2
0x180002261  jz      short loc_18000227B
0x180002263  xor     r9d, r9d
0x180002266  mov     qword ptr [rsp+78h+dwCreationFlags], r12
0x18000226b  mov     r8d, r13d
0x18000226e  lea     rdx, IISAdminShutdownGuid
0x180002275  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000227b  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_svcStatus ...
0x180002285  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r12; _SERVICE_STATUS g_svcStatus ...
0x18000228c  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r13d; _SERVICE_STATUS g_svcStatus ...
0x180002293  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 2710h; _SERVICE_STATUS g_svcStatus ...
0x18000229d  call    ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
0x1800022a2  test    eax, eax
0x1800022a4  jz      short loc_1800022B5
0x1800022a6  jg      short loc_1800022AC
0x1800022a8  mov     ebx, eax
0x1800022aa  jmp     short loc_1800022B5
0x1800022ac  movzx   ebx, ax
0x1800022af  or      ebx, 80070000h
0x1800022b5  mov     eax, 2328h
0x1800022ba  mov     [rsp+78h+Flags], r13d; Flags
0x1800022bf  mov     dword ptr [rsp+78h+lpThreadId], eax; Period
0x1800022c3  lea     r8, ?ShutdownCallback@@YAXPEAXE@Z; Callback
0x1800022ca  xor     r9d, r9d; Parameter
0x1800022cd  mov     [rsp+78h+dwCreationFlags], eax; DueTime
0x1800022d1  xor     edx, edx; TimerQueue
0x1800022d3  lea     rcx, [rsp+78h+phNewTimer]; phNewTimer
0x1800022db  call    cs:__imp_CreateTimerQueueTimer
0x1800022e1  test    eax, eax
0x1800022e3  jnz     short loc_180002361
0x1800022e5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800022ec  jz      short loc_180002361
0x1800022ee  call    cs:__imp_GetLastError
0x1800022f4  test    eax, eax
0x1800022f6  jle     short loc_180002300
0x1800022f8  movzx   eax, ax
0x1800022fb  or      eax, 80070000h
0x180002300  mov     dword ptr [rsp+78h+lpThreadId], eax
0x180002304  mov     r8d, 332h
0x18000230a  lea     rax, aFailedToCreate; "Failed to create the timer queue for sh"...
0x180002311  jmp     loc_1800020A2
0x180002316  call    ?StopServiceExtensions@@YAXXZ; StopServiceExtensions(void)
0x18000231b  mov     ebx, edi
0x18000231d  jmp     short loc_180002361
0x18000231f  mov     cs:?g_pEtwGlobalTracer@@3PEAVCEtwTracer@@EA, r12; CEtwTracer * g_pEtwGlobalTracer
0x180002326  test    byte ptr cs:g_dwDebugFlags, 3
0x18000232d  jz      short loc_18000235C
0x18000232f  mov     rcx, cs:g_pDebug
0x180002336  lea     rax, aFailedToAlloca; "Failed to allocation Tracing Infrastruc"...
0x18000233d  lea     r9, aInittracing; "InitTracing"
0x180002344  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180002349  mov     r8d, 2Ah ; '*'
0x18000234f  lea     rdx, aInetsrvIisMbIi_2; "inetsrv\\iis\\mb\\iisadmin\\tracing.cxx"
0x180002356  call    cs:__imp_PuDbgPrint
0x18000235c  mov     ebx, 8007000Eh
0x180002361  call    cs:__imp_CoSuspendClassObjects
0x180002367  test    rsi, rsi
0x18000236a  jz      short loc_180002375
0x18000236c  mov     rax, [rsi+8]
0x180002370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002375  xor     ecx, ecx; Binding
0x180002377  call    cs:__imp_RpcMgmtStopServerListening
0x18000237d  test    eax, eax
0x18000237f  jz      short loc_1800023B7
0x180002381  test    byte ptr cs:g_dwDebugFlags, 3
0x180002388  jz      short loc_1800023B7
0x18000238a  mov     rcx, cs:g_pDebug
0x180002391  lea     rax, aRpcmgmtstopser; "RpcMgmtStopServerListening returned 0x%"...
0x180002398  lea     r9, aServiceentry_0; "ServiceEntry"
  ... truncated ...
```
